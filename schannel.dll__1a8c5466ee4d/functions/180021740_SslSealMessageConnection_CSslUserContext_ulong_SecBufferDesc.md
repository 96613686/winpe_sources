# SslSealMessageConnection(CSslUserContext *,ulong,_SecBufferDesc *)

- ea: `0x180021740`
- end: `0x180021d9f`
- name: `?SslSealMessageConnection@@YAJPEAUCSslUserContext@@KPEAU_SecBufferDesc@@@Z`
- size: `1631`
- prototype: `__int64 __fastcall(struct CSslUserContext *, unsigned int, struct _SecBufferDesc *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180027740`
- `0x180028030`
- `0x18004a4bc`

## callees

- `0x180021740`
- `0x180021da8`
- `0x180021de8`
- `0x180021e64`
- `0x180057c8c`
- `0x18005c3a0`
- `0x180088a54`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180021c75`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180021c75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021d4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021848`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021848`
- `ncrypt!SslEncryptPacket` at `0x180021b32`
- `ncrypt!SslEncryptPacket` at `0x180021b32`

## pseudocode

```c
__int64 __fastcall SslSealMessageConnection(struct CSslUserContext *a1, int a2, struct _SecBufferDesc *a3)
{
  CCipherMill *v5; // r10
  unsigned int cBuffers; // ecx
  __int64 v7; // rdx
  struct _SecBuffer *v8; // r9
  unsigned int i; // edx
  char *pvBuffer; // rcx
  char *v11; // rdx
  __int64 cbBuffer; // r8
  int v14; // r12d
  int v15; // eax
  __int64 v16; // r15
  int v17; // r13d
  int v18; // ebx
  int v19; // r14d
  int v20; // eax
  unsigned int v21; // ebx
  unsigned __int8 *v22; // rcx
  __int64 v23; // r14
  unsigned int v24; // eax
  struct _SecBuffer *v25; // rdi
  unsigned int v26; // ecx
  unsigned int v27; // edx
  int v28; // eax
  PSecBuffer pBuffers; // r11
  struct _SecBuffer *v30; // rsi
  void *Src[2]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int8 *v33; // [rsp+B0h] [rbp+18h]

  *(_OWORD *)Src = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  cBuffers = a3->cBuffers;
  if ( !cBuffers )
    goto LABEL_4;
  pBuffers = a3->pBuffers;
  v25 = 0;
  v30 = 0;
  for ( i = 0; i < cBuffers; ++i )
  {
    v8 = &pBuffers[i];
    if ( v8->BufferType == 1 )
    {
      v25 = &pBuffers[i];
    }
    else if ( v8->BufferType == 2 )
    {
      if ( v30 )
        v8 = v30;
      v30 = v8;
    }
  }
  if ( !v30 || !v25 )
  {
LABEL_4:
    if ( v5 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 5) == 0 )
      return 2148074248LL;
    v7 = 51;
LABEL_121:
    WPP_SF_dd(*((_QWORD *)v5 + 2), v7, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, 2148074248LL, -2146893048);
    return 2148074248LL;
  }
  pvBuffer = (char *)v25->pvBuffer;
  if ( !pvBuffer || (v11 = (char *)v30->pvBuffer) == 0 )
  {
    if ( v5 == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 5) == 0 )
      return 2148074248LL;
    v7 = 52;
    goto LABEL_121;
  }
  if ( (*((_DWORD *)a1 + 6) & 0xF0000) == 0 )
  {
    cbBuffer = v25->cbBuffer;
    if ( v11 == &pvBuffer[cbBuffer] )
    {
      Src[1] = v25->pvBuffer;
      v14 = 0;
      HIDWORD(Src[0]) = 0;
      v15 = v25->cbBuffer + v30->cbBuffer;
    }
    else
    {
      Src[1] = LocalAlloc(0x40u, (unsigned int)(cbBuffer + v30->cbBuffer));
      if ( !Src[1] )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 5) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
            2148074240LL,
            -2146893056);
        return 2148074240LL;
      }
      v14 = 1;
      v15 = v25->cbBuffer + v30->cbBuffer;
      v5 = WPP_GLOBAL_Control;
      HIDWORD(Src[0]) = 0;
    }
    LODWORD(Src[0]) = v15;
    v16 = v25->cbBuffer;
    v17 = 23;
    v33 = (unsigned __int8 *)v25->pvBuffer;
    if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)v5 + 2), 57, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v5 + 2), 58, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, (unsigned int)v16);
          v5 = WPP_GLOBAL_Control;
        }
        if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v5 + 2), 59, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, (unsigned int)v16);
            v5 = WPP_GLOBAL_Control;
          }
          if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
            {
              WPP_SF_d(*((_QWORD *)v5 + 2), 60, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, HIDWORD(Src[0]));
              v5 = WPP_GLOBAL_Control;
            }
            if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
            {
              WPP_SF_d(*((_QWORD *)v5 + 2), 61, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, LODWORD(Src[0]));
              v5 = WPP_GLOBAL_Control;
            }
          }
        }
      }
    }
    v18 = *((_DWORD *)a1 + 17);
    v19 = *((_DWORD *)a1 + 16);
    if ( a2 == 0x40000000 )
    {
      v20 = *((_DWORD *)a1 + 6);
      if ( (v20 & 0x800A2AAA) != 0 && !(_DWORD)v16 )
      {
        if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)v5 + 2), 10, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
          v5 = WPP_GLOBAL_Control;
        }
        goto LABEL_46;
      }
      if ( (v20 & 0x40051555) != 0 && (_DWORD)v16 == 4 )
      {
        v22 = v33;
        if ( !*v33 && !v33[1] && !v33[2] && !v33[3] && (v20 & 0x1000) == 0 )
        {
          if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)v5 + 2), 11, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
            v5 = WPP_GLOBAL_Control;
            v22 = v33;
          }
          v17 = 22;
          goto LABEL_59;
        }
LABEL_46:
        v21 = -2146893048;
        goto LABEL_47;
      }
      if ( (_DWORD)v16 != 2 || (unsigned __int8)(*v33 - 1) > 1u )
        goto LABEL_46;
      if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
        WPP_SF_dd(*((_QWORD *)v5 + 2), 12, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, *v33, v33[1]);
      if ( !IsValidAlert(v33[1]) )
        goto LABEL_46;
      v17 = 21;
    }
    v22 = v33;
LABEL_59:
    v23 = (unsigned int)(v18 + v19);
    if ( !v14 )
    {
      memmove_s((char *)v25->pvBuffer + v23, v25->cbBuffer, v25->pvBuffer, v25->cbBuffer);
      v5 = WPP_GLOBAL_Control;
      v22 = &v33[(unsigned int)v23];
      v33 = v22;
    }
    if ( (*((_DWORD *)a1 + 6) & 0x3000) != 0 )
    {
      v22[v16] = v17;
      v17 = 23;
      v5 = WPP_GLOBAL_Control;
      LODWORD(v16) = v16 + 1;
    }
    if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)v5 + 2), 62, &WPP_12c1054e772130c368912b44a071a70c_Traceguids);
        v5 = WPP_GLOBAL_Control;
        v22 = v33;
      }
      if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v5 + 2), 63, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, (unsigned int)v16);
          v5 = WPP_GLOBAL_Control;
          v22 = v33;
        }
        if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
          {
            WPP_SF_q(
              *((_QWORD *)v5 + 2),
              64,
              &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
              (char *)Src[1] + (unsigned int)v23);
            v5 = WPP_GLOBAL_Control;
            v22 = v33;
          }
          if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)v5 + 2),
                65,
                &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
                (unsigned int)(LODWORD(Src[0]) - v23));
              v5 = WPP_GLOBAL_Control;
              v22 = v33;
            }
            if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v5 + 28) & 4) != 0 )
              {
                WPP_SF_d(*((_QWORD *)v5 + 2), 66, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, HIDWORD(Src[0]));
                v5 = WPP_GLOBAL_Control;
                v22 = v33;
              }
              if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)v5 + 2),
                  67,
                  &WPP_12c1054e772130c368912b44a071a70c_Traceguids,
                  *((unsigned int *)a1 + 26));
                v22 = v33;
              }
            }
          }
        }
      }
    }
    v24 = SslEncryptPacket(
            *((_QWORD *)a1 + 11),
            *((_QWORD *)a1 + 6),
            v22,
            (unsigned int)v16,
            Src[1],
            Src[0],
            (char *)Src + 4,
            *((_QWORD *)a1 + 13),
            v17,
            0);
    ++*((_QWORD *)a1 + 13);
    v21 = v24;
    if ( !v24 )
    {
      v26 = HIDWORD(Src[0]);
      if ( HIDWORD(Src[0]) >= v25->cbBuffer )
        v26 = v25->cbBuffer;
      v27 = HIDWORD(Src[0]) - v26;
      v25->cbBuffer = v26;
      if ( v27 >= v30->cbBuffer )
        v27 = v30->cbBuffer;
      v30->cbBuffer = v27;
      if ( !v14 )
        goto LABEL_73;
      memcpy_0(v25->pvBuffer, Src[1], v25->cbBuffer);
      memcpy_0(v30->pvBuffer, (char *)Src[1] + v25->cbBuffer, v30->cbBuffer);
LABEL_92:
      LocalFree(Src[1]);
LABEL_73:
      v5 = WPP_GLOBAL_Control;
LABEL_48:
      if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control )
      {
        if ( (v28 = *((_DWORD *)v5 + 7), (v28 & 1) != 0) && v21 || (v28 & 4) != 0 )
          WPP_SF_dd(*((_QWORD *)v5 + 2), 71, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v21, v21);
      }
      return v21;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, v24);
      v5 = WPP_GLOBAL_Control;
    }
    v21 = -2146893015;
LABEL_47:
    if ( !v14 )
      goto LABEL_48;
    goto LABEL_92;
  }
  if ( v5 != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 5) != 0 )
    WPP_SF_dd(*((_QWORD *)v5 + 2), 53, &WPP_12c1054e772130c368912b44a071a70c_Traceguids, 2148074242LL, -2146893054);
  return 2148074242LL;
}

```

## disassembly

```asm
0x180021740  mov     [rsp+arg_8], edx
0x180021744  push    rbx
0x180021745  push    rbp
0x180021746  push    r14
0x180021748  sub     rsp, 80h
0x18002174f  xorps   xmm0, xmm0
0x180021752  mov     rbx, r8
0x180021755  movups  xmmword ptr [rsp+98h+Src], xmm0
0x18002175a  mov     rbp, rcx
0x18002175d  mov     r10, cs:WPP_GLOBAL_Control
0x180021764  lea     r14, WPP_GLOBAL_Control
0x18002176b  cmp     r10, r14
0x18002176e  jnz     short loc_1800217AB
0x180021770  mov     ecx, [rbx+4]
0x180021773  mov     [rsp+98h+arg_0], rsi
0x18002177b  mov     [rsp+98h+var_20], rdi
0x180021780  mov     [rsp+98h+var_38], r15
0x180021785  test    ecx, ecx
0x180021787  jnz     loc_180021BB7
0x18002178d  cmp     r10, r14
0x180021790  jz      loc_18008C56E
0x180021796  test    byte ptr [r10+1Ch], 5
0x18002179b  jz      loc_18008C56E
0x1800217a1  mov     edx, 33h ; '3'
0x1800217a6  jmp     loc_18008C550
0x1800217ab  test    byte ptr [r10+1Ch], 20h
0x1800217b0  jz      short loc_180021770
0x1800217b2  mov     rcx, [r10+10h]
0x1800217b6  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x1800217bd  mov     edx, 32h ; '2'
0x1800217c2  call    WPP_SF_
0x1800217c7  mov     r10, cs:WPP_GLOBAL_Control
0x1800217ce  jmp     short loc_180021770
0x1800217d0  mov     r9d, edx
0x1800217d3  shl     r9, 4
0x1800217d7  add     r9, r11
0x1800217da  mov     r8d, [r9+4]
0x1800217de  sub     r8d, 1
0x1800217e2  jz      loc_180021B5C
0x1800217e8  cmp     r8d, 1
0x1800217ec  jz      loc_180021BCC
0x1800217f2  inc     edx
0x1800217f4  cmp     edx, ecx
0x1800217f6  jb      short loc_1800217D0
0x1800217f8  test    rsi, rsi
0x1800217fb  jz      short loc_18002178D
0x1800217fd  test    rdi, rdi
0x180021800  jz      short loc_18002178D
0x180021802  mov     rcx, [rdi+8]
0x180021806  test    rcx, rcx
0x180021809  jz      loc_180021D81
0x18002180f  mov     rdx, [rsi+8]
0x180021813  test    rdx, rdx
0x180021816  jz      loc_180021D81
0x18002181c  test    dword ptr [rbp+18h], 0F0000h
0x180021823  jnz     loc_180021BA8
0x180021829  mov     r8d, [rdi]
0x18002182c  mov     [rsp+98h+var_28], r12
0x180021831  lea     rax, [rcx+r8]
0x180021835  cmp     rdx, rax
0x180021838  jz      loc_180021A9E
0x18002183e  mov     edx, [rsi]
0x180021840  mov     ecx, 40h ; '@'; uFlags
0x180021845  add     edx, r8d; uBytes
0x180021848  call    cs:__imp_LocalAlloc
0x18002184e  mov     [rsp+98h+Src+8], rax
0x180021853  test    rax, rax
0x180021856  jnz     short loc_180021897
0x180021858  mov     rcx, cs:WPP_GLOBAL_Control
0x18002185f  cmp     rcx, r14
0x180021862  jz      short loc_18002188D
0x180021864  test    byte ptr [rcx+1Ch], 5
0x180021868  jz      short loc_18002188D
0x18002186a  mov     rcx, [rcx+10h]
0x18002186e  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021875  mov     edx, 38h ; '8'
0x18002187a  mov     dword ptr [rsp+98h+var_78], 80090300h
0x180021882  mov     r9d, 80090300h
0x180021888  call    WPP_SF_dd
0x18002188d  mov     eax, 80090300h
0x180021892  jmp     loc_180021A04
0x180021897  mov     eax, [rsi]
0x180021899  mov     r12d, 1
0x18002189f  add     eax, [rdi]
0x1800218a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800218a8  mov     dword ptr [rsp+98h+Src+4], r15d
0x1800218ad  mov     dword ptr [rsp+98h+Src], eax
0x1800218b1  mov     rax, [rdi+8]
0x1800218b5  mov     r15d, [rdi]
0x1800218b8  mov     [rsp+98h+var_30], r13
0x1800218bd  mov     r13d, 17h
0x1800218c3  mov     [rsp+98h+arg_10], rax
0x1800218cb  cmp     r10, r14
0x1800218ce  jz      loc_180021966
0x1800218d4  test    byte ptr [r10+1Ch], 4
0x1800218d9  jz      short loc_1800218F7
0x1800218db  mov     rcx, [r10+10h]
0x1800218df  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x1800218e6  mov     edx, 39h ; '9'
0x1800218eb  call    WPP_SF_
0x1800218f0  mov     r10, cs:WPP_GLOBAL_Control
0x1800218f7  cmp     r10, r14
0x1800218fa  jz      short loc_180021966
0x1800218fc  test    byte ptr [r10+1Ch], 4
0x180021901  jz      short loc_180021922
0x180021903  mov     rcx, [r10+10h]
0x180021907  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x18002190e  mov     edx, 3Ah ; ':'
0x180021913  mov     r9d, r15d
0x180021916  call    WPP_SF_d
0x18002191b  mov     r10, cs:WPP_GLOBAL_Control
0x180021922  cmp     r10, r14
0x180021925  jz      short loc_180021966
0x180021927  test    byte ptr [r10+1Ch], 4
0x18002192c  jz      short loc_18002194D
0x18002192e  mov     rcx, [r10+10h]
0x180021932  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021939  mov     edx, 3Bh ; ';'
0x18002193e  mov     r9d, r15d
0x180021941  call    WPP_SF_d
0x180021946  mov     r10, cs:WPP_GLOBAL_Control
0x18002194d  cmp     r10, r14
0x180021950  jz      short loc_180021966
0x180021952  test    byte ptr [r10+1Ch], 4
0x180021957  jnz     loc_180021A78
0x18002195d  cmp     r10, r14
0x180021960  jnz     loc_180021C07
0x180021966  cmp     [rsp+98h+arg_8], 40000000h
0x180021971  mov     ebx, [rbp+44h]
0x180021974  mov     r14d, [rbp+40h]
0x180021978  jnz     loc_180021ABA
0x18002197e  mov     eax, [rbp+18h]
0x180021981  test    eax, 800A2AAAh
0x180021986  jz      short loc_180021991
0x180021988  test    r15d, r15d
0x18002198b  jz      loc_180021A27
0x180021991  test    eax, 40051555h
0x180021996  jnz     loc_180021A58
0x18002199c  cmp     r15d, 2
0x1800219a0  jnz     short loc_1800219DF
0x1800219a2  mov     r13, [rsp+98h+arg_10]
0x1800219aa  movzx   ecx, byte ptr [r13+0]
0x1800219af  lea     eax, [rcx-1]
0x1800219b2  cmp     al, 1
0x1800219b4  ja      short loc_1800219DF
0x1800219b6  lea     rax, WPP_GLOBAL_Control
0x1800219bd  cmp     r10, rax
0x1800219c0  jz      short loc_1800219CD
0x1800219c2  test    byte ptr [r10+1Ch], 4
0x1800219c7  jnz     loc_180021C38
0x1800219cd  movzx   ecx, byte ptr [r13+1]; unsigned __int8
0x1800219d2  call    ?IsValidAlert@@YAEE@Z; IsValidAlert(uchar)
0x1800219d7  test    al, al
0x1800219d9  jnz     loc_180021AB4
0x1800219df  lea     r14, WPP_GLOBAL_Control
0x1800219e6  mov     ebx, 80090308h
0x1800219eb  test    r12d, r12d
0x1800219ee  jnz     loc_180021D48
0x1800219f4  mov     r13, [rsp+98h+var_30]
0x1800219f9  cmp     r10, r14
0x1800219fc  jnz     loc_180021B8F
0x180021a02  mov     eax, ebx
0x180021a04  mov     r12, [rsp+98h+var_28]
0x180021a09  mov     r15, [rsp+98h+var_38]
0x180021a0e  mov     rdi, [rsp+98h+var_20]
0x180021a13  mov     rsi, [rsp+98h+arg_0]
0x180021a1b  add     rsp, 80h
0x180021a22  pop     r14
0x180021a24  pop     rbp
0x180021a25  pop     rbx
0x180021a26  retn
0x180021a27  lea     r14, WPP_GLOBAL_Control
0x180021a2e  cmp     r10, r14
0x180021a31  jz      short loc_1800219E6
0x180021a33  test    byte ptr [r10+1Ch], 2
0x180021a38  jz      short loc_1800219E6
0x180021a3a  mov     rcx, [r10+10h]
0x180021a3e  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021a45  mov     edx, 0Ah
0x180021a4a  call    WPP_SF_
0x180021a4f  mov     r10, cs:WPP_GLOBAL_Control
0x180021a56  jmp     short loc_1800219E6
0x180021a58  cmp     r15d, 4
0x180021a5c  jnz     loc_18002199C
0x180021a62  mov     rcx, [rsp+98h+arg_10]
0x180021a6a  cmp     byte ptr [rcx], 0
0x180021a6d  jnz     loc_1800219DF
0x180021a73  jmp     loc_18008C3A8
0x180021a78  mov     r9d, dword ptr [rsp+98h+Src+4]
0x180021a7d  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021a84  mov     rcx, [r10+10h]
0x180021a88  mov     edx, 3Ch ; '<'
0x180021a8d  call    WPP_SF_d
0x180021a92  mov     r10, cs:WPP_GLOBAL_Control
0x180021a99  jmp     loc_18002195D
0x180021a9e  mov     [rsp+98h+Src+8], rcx
0x180021aa3  mov     r12d, r15d
0x180021aa6  mov     dword ptr [rsp+98h+Src+4], r15d
0x180021aab  mov     eax, [rsi]
0x180021aad  add     eax, [rdi]
0x180021aaf  jmp     loc_1800218AD
0x180021ab4  mov     r13d, 15h
0x180021aba  mov     rcx, [rsp+98h+arg_10]
0x180021ac2  lea     rdx, WPP_GLOBAL_Control
0x180021ac9  add     r14d, ebx
0x180021acc  test    r12d, r12d
0x180021acf  jz      loc_180021C65
0x180021ad5  test    dword ptr [rbp+18h], 3000h
0x180021adc  jnz     loc_180021CA1
0x180021ae2  cmp     r10, rdx
0x180021ae5  jnz     loc_180021CBA
0x180021aeb  lea     r14, WPP_GLOBAL_Control
0x180021af2  mov     rax, [rbp+68h]
0x180021af6  mov     r8, rcx
0x180021af9  mov     rdx, [rbp+30h]
0x180021afd  mov     r9d, r15d
0x180021b00  mov     rcx, [rbp+58h]
0x180021b04  mov     [rsp+98h+var_50], 0
0x180021b0c  mov     [rsp+98h+var_58], r13d
0x180021b11  mov     [rsp+98h+var_60], rax
0x180021b16  lea     rax, [rsp+98h+Src+4]
0x180021b1b  mov     [rsp+98h+var_68], rax
0x180021b20  mov     eax, dword ptr [rsp+98h+Src]
0x180021b24  mov     [rsp+98h+var_70], eax
0x180021b28  mov     rax, [rsp+98h+Src+8]
0x180021b2d  mov     [rsp+98h+var_78], rax
0x180021b32  call    cs:__imp_SslEncryptPacket
0x180021b38  inc     qword ptr [rbp+68h]
0x180021b3c  mov     ebx, eax
0x180021b3e  test    eax, eax
0x180021b40  jz      short loc_180021B64
0x180021b42  mov     r10, cs:WPP_GLOBAL_Control
0x180021b49  cmp     r10, r14
0x180021b4c  jnz     loc_180021CF5
0x180021b52  mov     ebx, 80090329h
0x180021b57  jmp     loc_1800219EB
0x180021b5c  mov     rdi, r9
0x180021b5f  jmp     loc_1800217F2
0x180021b64  mov     edx, dword ptr [rsp+98h+Src+4]
0x180021b68  mov     ecx, edx
0x180021b6a  cmp     edx, [rdi]
0x180021b6c  cmovnb  ecx, [rdi]
0x180021b6f  sub     edx, ecx
0x180021b71  mov     [rdi], ecx
0x180021b73  cmp     edx, [rsi]
0x180021b75  cmovnb  edx, [rsi]
0x180021b78  mov     [rsi], edx
0x180021b7a  test    r12d, r12d
0x180021b7d  jnz     loc_180021D24
0x180021b83  mov     r10, cs:WPP_GLOBAL_Control
0x180021b8a  jmp     loc_1800219F4
0x180021b8f  mov     eax, [r10+1Ch]
0x180021b93  test    al, 1
0x180021b95  jnz     loc_180021D58
0x180021b9b  test    al, 4
0x180021b9d  jz      loc_180021A02
0x180021ba3  jmp     loc_180021D60
0x180021ba8  cmp     r10, r14
0x180021bab  jnz     short loc_180021BDB
0x180021bad  mov     eax, 80090302h
0x180021bb2  jmp     loc_180021A09
0x180021bb7  mov     r11, [rbx+8]
0x180021bbb  xor     r15d, r15d
0x180021bbe  mov     edi, r15d
0x180021bc1  mov     esi, r15d
0x180021bc4  mov     edx, r15d
0x180021bc7  jmp     loc_1800217D0
0x180021bcc  test    rsi, rsi
0x180021bcf  cmovnz  r9, rsi
0x180021bd3  mov     rsi, r9
0x180021bd6  jmp     loc_1800217F2
0x180021bdb  test    byte ptr [r10+1Ch], 5
0x180021be0  jz      short loc_180021BAD
0x180021be2  mov     rcx, [r10+10h]
0x180021be6  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021bed  mov     edx, 35h ; '5'
0x180021bf2  mov     dword ptr [rsp+98h+var_78], 80090302h
0x180021bfa  mov     r9d, 80090302h
0x180021c00  call    WPP_SF_dd
0x180021c05  jmp     short loc_180021BAD
0x180021c07  test    byte ptr [r10+1Ch], 4
0x180021c0c  jz      loc_180021966
0x180021c12  mov     r9d, dword ptr [rsp+98h+Src]
0x180021c17  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021c1e  mov     rcx, [r10+10h]
0x180021c22  mov     edx, 3Dh ; '='
0x180021c27  call    WPP_SF_d
0x180021c2c  mov     r10, cs:WPP_GLOBAL_Control
0x180021c33  jmp     loc_180021966
0x180021c38  movzx   eax, byte ptr [r13+1]
0x180021c3d  lea     r8, WPP_12c1054e772130c368912b44a071a70c_Traceguids
0x180021c44  mov     r9d, ecx
0x180021c47  mov     dword ptr [rsp+98h+var_78], eax
0x180021c4b  mov     rcx, [r10+10h]
0x180021c4f  mov     edx, 0Ch
0x180021c54  call    WPP_SF_dd
0x180021c59  mov     r10, cs:WPP_GLOBAL_Control
0x180021c60  jmp     loc_1800219CD
0x180021c65  mov     r8, [rdi+8]; Source
0x180021c69  mov     edx, [rdi]; DestinationSize
  ... truncated ...
```
