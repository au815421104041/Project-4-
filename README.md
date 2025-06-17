import scala.io.StdIn._
object two {
  def main(args: Array[String]): Unit = {
    println(s"-----WELL COME-----")
    println(s"WHAT YOU WANT:")
    println(s"1.VIEW BOOKS")
    println(s"2.SEARCH BOOKS")
    println(s"3.ADD BOOK")
    println(s"4.BOOKS STATUS")
   // val objviewbooks    = new  viewbooks()



    val input = scala.io.StdIn.readInt()
    input match {
      case 1 => "BOOKS THERE";   val objsearchbooks  = new  searchbooks();
                                 println(objsearchbooks.bookname)
      case 2 => "WHAT BOOKS";    val objsearchbooks  = new  searchbooks();
                                 objsearchbooks.getbooks()
      case 3 => "ADD BOOKS";     val objaddbooks     = new  addbooks();
                                 println(objaddbooks.bookname)
      case 4 => "BOOK PROCESS";  val objbokstatus    = new  bookstatus();
                                 println(objbokstatus.bookname)
      case _ => "WRONG OPTIONS"; println("WRONG OPTIONS")
        }
    }
  }
abstract class viewbooks {
    var bookname    = List("aaa", "bbb", "ccc", "ddd", "eee", "fff", "ggg", "hhh", "iii", "jjj", "kkk", "lll")
    val bookauther  = List("aa", "bb", "cc", "dd", "ee", "ff", "gg", "hh", "ii", "jj", "kk", "ll")
    val bookid      = List("1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12")
    def getbooks();
  }
  class searchbooks extends viewbooks {
    def getbooks(): Unit = {
      println("enter book name:")
      val booktitle = readLine()
      for (i <- bookname) {
        if (i.equals(booktitle)) {
          val xx = if (booktitle.contains(booktitle)) booktitle + "    available"
          println(s"book status :$xx")
          System.exit(0)
        }
      }
      println("enter book auther:")
      val bookpublisher = readLine()
      for (i <- bookauther) {
        if (i.equals(bookpublisher)) {
          val yy = if (bookauther.contains(bookpublisher)) bookpublisher + "     available"
          println(s"book status :$yy")
          System.exit(0)
        }
      }
      println("enter book id:")
      val booknumber = readLine()
      for (i <- bookid) {
        if (i.equals(booknumber)) {
          val zz = if (bookid.contains(booknumber)) booknumber + "    available"
          println(s"book status :$zz")
          System.exit(0)
        }
      }
    }
  }
  class addbooks extends searchbooks  {
      println("enter the newbook")
      var newbook = readLine()
      bookname = bookname :+ newbook
      println("added List:")
  }
   class bookstatus extends searchbooks  {
    println("Enter book Name:")
    var booktitle = readLine()
    for (i <- bookname) {
      if (i.equals(booktitle)) {
        val xx = if (bookname.contains(booktitle)) booktitle +"    available" else "not available"
        println(s"book status :$xx")
      }
    }
}
