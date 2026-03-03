package com.example.cartodevisitasdigital

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.res.stringResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.cartodevisitasdigital.ui.theme.CartãoDeVisitasDigitalTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            CartãoDeVisitasDigitalTheme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                    Column(Modifier.padding(innerPadding)) {
                        Foto()
                        Perfil()
                        Cargo()
                        Social()
                    }

                }
            }
        }
    }
}

@Composable
fun Perfil(modifier: Modifier = Modifier) {
    Text(
        text = "Cristiano Ronaldo do Santos Aveiro",
        modifier = modifier.padding(15.dp)

    )
}

@Composable
fun Cargo(modifier: Modifier = Modifier){
    Text(
        text = "Mais conhecido como Cristiano Ronaldo ou CR7, o jogador de futebol é entitulado o melhor de todos os tempos (GOAT)",
        modifier = modifier.padding(15.dp)
    )
}

@Composable
fun Social(modifier: Modifier = Modifier){
    Row {
        val icons = modifier
            .size(40.dp)
            .padding(10.dp)
        Image(
            painter = painterResource(id = R.drawable.insta),
            contentDescription = stringResource(id = R.string.instagram),
            modifier = icons
        )
        Text(
            text = "@cristiano",
            fontSize = 15.sp,

        )
        Image(
            painter = painterResource(id = R.drawable.youtu),
            contentDescription = stringResource(id = R.string.youtube),
            modifier = icons
        )
        Text(
            text = "UR · Cristiano",
            fontSize = 15.sp,

        )
        Image(
            painter = painterResource(id = R.drawable.x),
            contentDescription = stringResource(id = R.string.ekis),
            modifier = icons
        )
        Text(

            text = "@Cristiano",
            fontSize = 15.sp,
          
        )

    }
}

@Composable
fun Foto(modifier: Modifier = Modifier){
    val imagem = modifier
        .size(420.dp)

    Image(
        painter = painterResource(id = R.drawable.ronaldo),
        contentDescription = stringResource(id = R.string.ronaldo_lindao),
        modifier = imagem
    )
}
