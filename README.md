class MyAdapter(private val itemCount: Int) : RecyclerView.Adapter<MyAdapter.MyViewHolder>() {

    // ViewHolder для RecyclerView
    class MyViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView)

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): MyViewHolder {
        // Создаем View для каждого элемента RecyclerView
        val view = LayoutInflater.from(parent.context).inflate(R.layout.item_card, parent, false)
        return MyViewHolder(view)
    }

    override fun onBindViewHolder(holder: MyViewHolder, position: Int) {
        // Ничего не делаем, так как данные уже в макете
    }

    override fun getItemCount(): Int {
        return itemCount // Возвращаем количество элементов
    }
}




class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Находим RecyclerView
        val recyclerView: RecyclerView = findViewById(R.id.recyclerView)

        // Устанавливаем GridLayoutManager с 2 столбцами
        val numberOfColumns = 2
        recyclerView.layoutManager = GridLayoutManager(this, numberOfColumns)

        // Указываем количество элементов
        val itemCount = 10 // Например, 10 элементов

        // Создаем адаптер и передаем количество элементов
        val adapter = MyAdapter(itemCount)

        // Устанавливаем адаптер для RecyclerView
        recyclerView.adapter = adapter
    }
}




<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recyclerView"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:padding="8dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>



<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    app:
