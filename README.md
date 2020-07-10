# TUGAS5_Grafkom_L_672018114
#include <GL/glu.h>
#include <GL/glut.h>

void init(void);
void Layar(void);
void keyboard(unsigned char, int, int);
void ukuran(int, int);
void mouse(int button, int state, int x, int y);
void mouseMotion(int x, int y);
void ayamayam(void);
void goib(void);
void kaget(void);
void bukaan(void);
void jiyah(void);
float xrot = 0.0f;
float yrot = 0.0f;
float xdiff = 0.0f;
float ydiff = 0.0f;
bool mouseDown = false;
int lololo, hareudang;

void ndelok()
{
    glLoadIdentity();
       gluLookAt(0.0f, 0.0f, 3.0f, 0.0f, 0.0f, 0.0f, 0.0f, 1.0f, 0.0f);
       glRotatef(xrot, 1.0f,0.0f, 0.0f);
       glRotatef(yrot, 0.0f, 1.0f, 0.0f);
}

void init(void){
  glClearColor(0, 0, 0, 0);
   glMatrixMode(GL_PROJECTION);
   glEnable(GL_DEPTH_TEST);
   lololo=1;
   hareudang=1;
   glMatrixMode(GL_MODELVIEW);
   glPointSize(4.0);
   glLineWidth(6.0f);
   }

    void bukaan (void){
            //pintu
    glBegin(GL_QUADS);
    glColor3ub(165,42,42);
    glVertex3f(-5,-30,30.1);
    glVertex3f(-5,-10,30.1);
    glVertex3f(5,-10,30.1);
    glVertex3f(5,-30,30.1);
    glEnd();

    }

    void goib (void){
    //depan
    glLineWidth(4.0f);
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(-5,-30,30.1);
    glVertex3f(-5,-10,30.1);
    glVertex3f(5,-10,30.1);
    glVertex3f(5,-30,30.1);
    glEnd();
    glBegin(GL_POLYGON);
    glColor3ub(224,224,224);
    glVertex3f(-30,-10,30);
    glVertex3f(-30,30,30);
    glVertex3f(0,45,30);
    glVertex3f(30,30,30);
    glVertex3f(30,-10,30);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(30,-10,30);
    glVertex3f(5,-10,30);
    glVertex3f(5,-30,30);
    glVertex3f(30,-30,30);
    glEnd();

    glBegin(GL_POLYGON);
    glVertex3f(-30,-10,30);
    glVertex3f(-5,-10,30);
    glVertex3f(-5,-30,30);
    glVertex3f(-30,-30,30);
    glEnd();
    glBegin(GL_QUADS);
    glColor3ub(220,220,220);
    glVertex3f(-15,0,30);
    glVertex3f(-15,0,50);
    glVertex3f(15,0,50);
    glVertex3f(15,0,30);
    glEnd();
    glBegin(GL_QUADS);
    glColor3ub(192,192,192);
    glVertex3f(-15,-5,30);
    glVertex3f(-15,-5,50);
    glVertex3f(15,-5,50);
    glVertex3f(15,-5,30);
    glEnd();
    glBegin(GL_QUADS);
    glColor3ub(211,211,211);
    glVertex3f(-15,0,30);
    glVertex3f(-15,0,50);
    glVertex3f(-15,-5,50);
    glVertex3f(-15,-5,30);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(-15,0,50);
    glVertex3f(15,0,50);
    glVertex3f(15,-5,50);
    glVertex3f(-15,-5,50);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(15,0,50);
    glVertex3f(15,0,30);
    glVertex3f(15,-5,30);
    glVertex3f(15,-5,50);
    glEnd();

    //atas
    glBegin(GL_QUADS);
    glColor3ub(102,51,0);
    glVertex3f(-35,28,35);
    glVertex3f(0,45,35);
    glVertex3f(0,45,-35);
    glVertex3f(-35,28,-35);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(0,45,35);
    glVertex3f(35,28,35);
    glVertex3f(35,28,-35);
    glVertex3f(0,45,-35);
    glEnd();
    //atas garis
    glLineWidth(14.0f);
    glBegin(GL_LINE_LOOP);
    glVertex3f(-35,28,35);
    glVertex3f(0,45,35);
    glVertex3f(0,45,-35);
    glVertex3f(-35,28,-35);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glVertex3f(0,45,35);
    glVertex3f(35,28,35);
    glVertex3f(35,28,-35);
    glVertex3f(0,45,-35);
    glEnd();

        //belakang
    glPushMatrix();
    glBegin(GL_POLYGON);
    glColor3ub(96,96,96);
    glVertex3f(-30,-30,-30);
    glVertex3f(-30,30,-30);
    glVertex3f(0,45,-30);
    glVertex3f(30,30,-30);
    glVertex3f(30,-30,-30);
    glEnd();


    //kanan
    glBegin(GL_QUADS);
    glColor3ub(192,192,192);
    glVertex3f(30,30,30);
    glVertex3f(30,-30,30);
    glVertex3f(30,-30,-30);
    glVertex3f(30,30,-30);
    glEnd();
    //kiri
    glBegin(GL_QUADS);
    glColor3ub(192,192,192);
    glVertex3f(-30,30,30);
    glVertex3f(-30,-30,30);
    glVertex3f(-30,-30,-30);
    glVertex3f(-30,30,-30);
    glEnd();
    }
    void kaget (void){
    //jendela
    //1
    glBegin(GL_QUADS);
    glColor3ub(245,245,245);
    glVertex3f(-20,10,30.1);
    glVertex3f(-20,20,30.1);
    glVertex3f(-10,20,30.1);
    glVertex3f(-10,10,30.1);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(-20,10,30.1);
    glVertex3f(-20,20,30.1);
    glVertex3f(-10,20,30.1);
    glVertex3f(-10,10,30.1);
    glEnd();
    //2
    glBegin(GL_QUADS);
    glColor3ub(245,245,245);
    glVertex3f(30.1,20,-10);
    glVertex3f(30.1,20,-20);
    glVertex3f(30.1,10,-20);
    glVertex3f(30.1,10,-10);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(30.1,20,-10);
    glVertex3f(30.1,20,-20);
    glVertex3f(30.1,10,-20);
    glVertex3f(30.1,10,-10);
    glEnd();

        //3
    glBegin(GL_QUADS);
    glColor3ub(245,245,245);
    glVertex3f(-30.1,10,-20);
    glVertex3f(-30.1,20,-20);
    glVertex3f(-30.1,20,-10);
    glVertex3f(-30.1,10,-10);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(-30.1,10,-20);
    glVertex3f(-30.1,20,-20);
    glVertex3f(-30.1,20,-10);
    glVertex3f(-30.1,10,-10);
    glEnd();

    //4
    glBegin(GL_QUADS);
    glColor3ub(245,245,245);
    glVertex3f(-20,10,-30.1);
    glVertex3f(-20,20,-30.1);
    glVertex3f(-10,20,-30.1);
    glVertex3f(-10,10,-30.1);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(-20,10,-30.1);
    glVertex3f(-20,20,-30.1);
    glVertex3f(-10,20,-30.1);
    glVertex3f(-10,10,-30.1);
    glEnd();

    //kamar
    glBegin(GL_POLYGON);
    glColor3ub(255,255,255);
    glVertex3f(-29.1,-29.1,-29.1);
    glVertex3f(-20,-29.1,-29.1);
    glVertex3f(-20,-29.1,0);
    glVertex3f(-30,-29.1,0);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-29.1,-25,-30);
    glVertex3f(-20,-25,-30);
    glVertex3f(-20,-25,0);
    glVertex3f(-29.1,-25,0);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-29.1,-29.1,0);
    glVertex3f(-29.1,-29.1,-29.1);
    glVertex3f(-29.1,-25,-30);
    glVertex3f(-29.1,-25,0);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-20,-29.1,0);
    glVertex3f(-30,-29.1,0);
    glVertex3f(-30,-25,0);
    glVertex3f(-20,-25,0);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-29.1,-29.1,-29.1);
    glVertex3f(-20,-29.1,-29.1);
    glVertex3f(-20,-25,-29.1);
    glVertex3f(-29.1,-25,-29.1);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-20,-29.1,-29.1);
    glVertex3f(-20,-29.1,0);
    glVertex3f(-20,-25,0);
    glVertex3f(-20,-25,-29.1);
    glEnd();
    //ac
    glLineWidth(8.0f);
    glBegin(GL_LINES);
    glColor3ub(192,192,192);
    glVertex3f(-10,24,-24.5);
    glVertex3f(10,24,-24.5);
    glEnd();
    glLineWidth(2.0f);
    glBegin(GL_LINES);
    glColor3ub(0,0,0);
    glVertex3f(-10,21,-24.5);
    glVertex3f(10,21,-24.5);
    glEnd();
    glBegin(GL_POLYGON);
    glColor3ub(224,255,255);
    glVertex3f(-10,20,-25);
    glVertex3f(-10,25,-25);
    glVertex3f(10,25,-25);
    glVertex3f(10,20,-25);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-10,25,-25);
    glVertex3f(-10,25,-29.5);
    glVertex3f(10,25,-29.5);
    glVertex3f(10,25,-25);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-10,20,-25);
    glVertex3f(-10,20,-29.5);
    glVertex3f(10,20,-29.5);
    glVertex3f(10,20,-25);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(-10,25,-25);
    glVertex3f(-10,25,-29.5);
    glVertex3f(-10,20,-29.5);
    glVertex3f(-10,20,-25);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(10,25,-25);
    glVertex3f(10,25,-29.5);
    glVertex3f(10,20,-29.5);
    glVertex3f(10,20,-25);
    glEnd();
    //tv
    glBegin(GL_QUADS);
    glColor3ub(0,128,255);
    glVertex3f(28,-5,10);
    glVertex3f(28,-20,10);
    glVertex3f(28,-20,-5);
    glVertex3f(28,-5,-5);
    glEnd();
    glLineWidth(2.0f);
    glBegin(GL_LINE_LOOP);
    glColor3ub(0,0,0);
    glVertex3f(28,-5,10);
    glVertex3f(28,-20,10);
    glVertex3f(28,-20,-5);
    glVertex3f(28,-5,-5);
    glEnd();
    //sampah
    glBegin(GL_POLYGON);
    glColor3ub(0,0,0);
    glVertex3f(28,-25,-28);
    glVertex3f(22,-25,-28);
    glVertex3f(22,-25,-22);
    glVertex3f(28,-25,-22);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3ub(0,206,209);
    glVertex3f(28,-25,-28);
    glVertex3f(22,-25,-28);
    glVertex3f(22,-29.5,-28);
    glVertex3f(28,-29.5,-28);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(28,-25,-22);
    glVertex3f(22,-25,-22);
    glVertex3f(22,-29.5,-22);
    glVertex3f(28,-29.5,-22);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(22,-25,-28);
    glVertex3f(22,-25,-22);
    glVertex3f(22,-29.5,-22);
    glVertex3f(22,-29.5,-28);
    glEnd();
    glBegin(GL_POLYGON);
    glVertex3f(28,-25,-28);
    glVertex3f(28,-25,-22);
    glVertex3f(28,-29.5,-22);
    glVertex3f(28,-29.5,-28);
    glEnd();
    //karpet
    glBegin(GL_QUADS);
    glColor3ub(225,0,0);
    glVertex3f(29,-29.5,20);
    glVertex3f(0,-29.5,20);
    glVertex3f(0,-29.5,-15);
    glVertex3f(29,-29.5,-15);
    glEnd();
    //meja
    glBegin(GL_QUADS);
    glColor3ub(139,69,19);
    glVertex3f(29,-25,15);
    glVertex3f(20,-25,15);
    glVertex3f(20,-25,-10);
    glVertex3f(29,-25,-10);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(29,-25,15);
    glVertex3f(20,-25,15);
    glVertex3f(20,-29,15);
    glVertex3f(29,-29,15);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(20,-25,15);
    glVertex3f(20,-25,-10);
    glVertex3f(20,-29,-10);
    glVertex3f(20,-29,15);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(20,-25,-10);
    glVertex3f(29,-25,-10);
    glVertex3f(29,-29,-10);
    glVertex3f(20,-29,-10);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(29,-29,15);
    glVertex3f(20,-29,15);
    glVertex3f(20,-29,-10);
    glVertex3f(29,-29,-10);
    glEnd();

    glColor3ub(211,211,211);
    glLineWidth(2.0f);
    glBegin(GL_LINE_LOOP);
    glVertex3f(-29.1,-25,-29.1);
    glVertex3f(-20,-25,-29.1);
    glVertex3f(-20,-25,0);
    glVertex3f(-29.1,-25,0);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glVertex3f(-29.1,-29.1,0);
    glVertex3f(-29.1,-29.1,-29.1);
    glVertex3f(-29.1,-25,-29.1);
    glVertex3f(-29.1,-25,0);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glVertex3f(-20,-29.1,0);
    glVertex3f(-29.1,-29.1,0);
    glVertex3f(-29.1,-25,0);
    glVertex3f(-20,-25,0);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glVertex3f(-29.1,-29.1,-29.1);
    glVertex3f(-20,-29.1,-29.1);
    glVertex3f(-20,-25,-29.1);
    glVertex3f(-30,-25,-29.1);
    glEnd();
    glBegin(GL_LINE_LOOP);
    glVertex3f(-20,-29.1,-29.1);
    glVertex3f(-20,-29.1,0);
    glVertex3f(-20,-25,0);
    glVertex3f(-20,-25,-29.1);
    glEnd();

    //lantaiatas
    glBegin(GL_POLYGON);
    glColor3ub(112, 123, 124);
    glVertex3f(-30,-30,30);
    glVertex3f(30,-30,30);
    glVertex3f(30,-30,-30);
    glVertex3f(-30,-30,-30);
    glEnd();
    glBegin(GL_POLYGON);
    glColor3ub(255, 153, 51);
    glVertex3f(-15,-30,30);
    glVertex3f(15,-30,30);
    glVertex3f(15,-30,45);
    glVertex3f(-15,-30,45);
    glEnd();
    glLineWidth(12.0f);
    glBegin(GL_LINE_LOOP);
    glColor3ub(112, 123, 124);
    glVertex3f(-29.5,-30,29.5);
    glVertex3f(29.5,-30,29.5);
    glVertex3f(29.5,-30,-29.5);
    glVertex3f(-29.5,-30,-29.5);
    glEnd();

    //lantai bawah
    glBegin(GL_QUADS);
    glColor3ub(112, 123, 124);
    glVertex3f(-30,-35,30);
    glVertex3f(30,-35,30);
    glVertex3f(30,-35,-30);
    glVertex3f(-30,-35,-30);
    glVertex3f(-15,-35,30);
    glVertex3f(15,-35,30);
    glVertex3f(15,-35,45);
    glVertex3f(-15,-35,45);
    glEnd();
    glBegin(GL_LINES);
    glColor3ub(112, 123, 124);
    glVertex3f(-30,-35,30);
    glVertex3f(30,-35,30);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(112, 0, 0);
    glVertex3f(-30,-30,30);
    glVertex3f(-30,-30,-30);
    glVertex3f(-30,-35,-30);
    glVertex3f(-30,-35,30);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(112, 0, 0);
    glVertex3f(30,-30,30);
    glVertex3f(30,-30,-30);
    glVertex3f(30,-35,-30);
    glVertex3f(30,-35,30);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(112, 0, 0);
    glVertex3f(-30,-30,30);
    glVertex3f(30,-30,30);
    glVertex3f(30,-35,30);
    glVertex3f(-30,-35,30);
    glEnd();

    glBegin(GL_QUADS);
    glVertex3f(30,-30,-30);
    glVertex3f(-30,-30,-30);
    glVertex3f(-30,-35,-30);
    glVertex3f(30,-35,-30);
    glEnd();

    glBegin(GL_QUADS);
    glVertex3f(-15,-35,30);
    glVertex3f(15,-35,30);
    glVertex3f(-15,-35,30);
    glVertex3f(15,-35,30);
    glEnd();
    //lis
    glBegin(GL_QUADS);
    glVertex3f(15,-35,45);
    glVertex3f(15,-35,30);
    glVertex3f(15,-30,30);
    glVertex3f(15,-30,45);
    glEnd();
    glBegin(GL_QUADS);
    glVertex3f(-15,-35,45);
    glVertex3f(-15,-35,30);
    glVertex3f(-15,-30,30);
    glVertex3f(-15,-30,45);
    glEnd();

    glBegin(GL_QUADS);
    glVertex3f(15,-30,45);
    glVertex3f(-15,-30,45);
    glVertex3f(-15,-35,45);
    glVertex3f(15,-35,45);
    glEnd();

    //suket
    glBegin(GL_POLYGON);
    glColor3ub(0, 153, 0);
    glVertex3f(-60,-35,60);
    glVertex3f(60,-35,60);
    glVertex3f(60,-35,-60);
    glVertex3f(-60,-35,-60);
    glEnd();
    }
    void jiyah (void){
        kaget();
        goib();
        bukaan();}

    void Layar(void){
    if (lololo){
        if(hareudang){
        glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
        jiyah();}
        else
        glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
        kaget();
        goib();
    }
    else
        glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
        kaget();

    glPopMatrix();
    glutSwapBuffers();
    }

    void idle()
{
    if (!mouseDown)
    {
        xrot += 0.3f;
        yrot += 0.4f;
    }
    glutPostRedisplay();
}

void mouse(int button, int state, int x, int y)
{

    if (button == GLUT_LEFT_BUTTON && state == GLUT_DOWN)
    {
        mouseDown = true;
        xdiff = x - yrot;
        ydiff = -y + xrot;
    }
    else
        mouseDown = false;


}

void mouseMotion(int x, int y)
{
    ndelok();
    if (mouseDown)
    {
        yrot = x - xdiff;
        xrot = y + ydiff;

        glutPostRedisplay();
    }

}
void ukuran(int lebar, int tinggi)
{
    if (tinggi == 0) tinggi =1;

    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective(50, lebar / tinggi, 5, 500);
    glTranslated(0, -5, -150);
    glMatrixMode(GL_MODELVIEW);

}

void keyboard(unsigned char key, int x, int y)
{

    switch(key)
    {
        case 'w':
        case 'W':
            glTranslated(0,0,3);
            break;
        case 'd':
        case 'D':
            glTranslated(3,0,0);
            break;
        case 's':
        case 'S':
            glTranslated(0,0,-3);
            break;
        case 'a':
        case 'A':
            glTranslated(-3,0,0);
            break;
        case '7':
            glTranslated(0,3,0);
            break;
        case '9':
            glTranslated(0,-3,0);
            break;
        case '2':
            glRotated(2,1,0,0);
            break;
        case '8':
            glRotated(-2,1,0,0);
            break;
        case '6':
            glRotated(2,0,1,0);
            break;
        case '4':
            glRotated(-2,1,0,0);
            break;
        case '1':
            glRotated(2,0,0,1);
            break;
        case '3':
            glRotated(-2,0,0,1);
            break;
        case '5':
            if (lololo)
            {
                lololo = 0;
            }
            else
            {
                lololo = 1;
            }break;
        case 'e':
        case 'E':
            if (hareudang)
            {
                hareudang = 0;
            }
            else
            {
                hareudang = 1;
            }
            break;

    }
    Layar();


}

int main(int argc, char **argv){
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE);
    glutInitWindowPosition(250, 80);
    glutInitWindowSize(800, 600);
    glutCreateWindow("Laurensius Phillipus Ramawijaya - 672018114");
    init();
    glutDisplayFunc(Layar);
    glutKeyboardFunc(keyboard);
    glutMouseFunc(mouse);
    glutMotionFunc(mouseMotion);
    glutReshapeFunc(ukuran);
    glutMainLoop();

    return 0;
}
