# _File::OpenFile_::_11_::_lambda_1_::operator()

- ea: `0x180031250`
- end: `0x1800314e7`
- name: `_File::OpenFile_::_11_::_lambda_1_::operator()`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800227b4`

## callees

- `0x180023548`
- `0x180031250`
- `0x180032c8c`
- `0x180033b94`
- `0x180033cdc`
- `0x180038fa4`

## pseudocode

```c
__int64 __fastcall File::OpenFile_::_11_::_lambda_1_::operator()(__int64 *a1)
{
  __int128 *FileHeader; // rax
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm2
  __int128 v6; // xmm3
  __int128 v7; // xmm4
  __int128 v8; // xmm5
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  _OWORD *v11; // rax
  __int64 result; // rax
  __int128 pExceptionObject; // [rsp+28h] [rbp-79h] BYREF
  __int64 v14; // [rsp+38h] [rbp-69h]
  int v15; // [rsp+40h] [rbp-61h]
  int v16; // [rsp+44h] [rbp-5Dh]
  int v17; // [rsp+48h] [rbp-59h]
  _BYTE v18[168]; // [rsp+50h] [rbp-51h] BYREF

  *(_QWORD *)(*a1 + 792) = GetLogSize(*(void **)(*a1 + 672));
  if ( *(_QWORD *)(*a1 + 792) < 0x11000u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
    }
    v14 = 0;
    v15 = 1500;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 353;
    throw (EvtException *)&pExceptionObject;
  }
  FileHeader = (__int128 *)ReadFileHeader(v18, *(_QWORD *)(*a1 + 672));
  v3 = *FileHeader;
  v4 = FileHeader[1];
  v5 = FileHeader[2];
  v6 = FileHeader[3];
  v7 = FileHeader[4];
  v8 = FileHeader[5];
  v9 = FileHeader[6];
  v10 = FileHeader[7];
  v11 = (_OWORD *)*a1;
  v11[1] = v3;
  v11[2] = v4;
  v11[3] = v5;
  v11[4] = v6;
  v11[5] = v7;
  v11[6] = v8;
  v11[7] = v9;
  v11[8] = v10;
  if ( !IsFileHeaderValid((PUCHAR)(*a1 + 16)) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
    }
    v14 = 0;
    v15 = 1500;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 361;
    throw (EvtException *)&pExceptionObject;
  }
  result = *a1;
  if ( *(_WORD *)(*a1 + 54) > 3u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 15035);
    }
    v14 = 0;
    v15 = 15035;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 366;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *(_WORD *)(*a1 + 54) < 3u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 15034);
    }
    v14 = 0;
    v15 = 15034;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 371;
    throw (EvtException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180031250  mov     rax, rsp
0x180031253  mov     [rax+8], rdi
0x180031257  push    rbp
0x180031258  lea     rbp, [rax-5Fh]
0x18003125c  sub     rsp, 0F0h
0x180031263  mov     rdi, rcx
0x180031266  movaps  xmmword ptr [rax-18h], xmm6
0x18003126a  mov     rcx, [rcx]
0x18003126d  movaps  xmmword ptr [rax-28h], xmm7
0x180031271  mov     rcx, [rcx+2A0h]; void *
0x180031278  call    ?GetLogSize@@YA_KPEAX@Z; GetLogSize(void *)
0x18003127d  mov     rdx, [rdi]
0x180031280  mov     [rdx+318h], rax
0x180031287  mov     rdx, [rdi]
0x18003128a  cmp     qword ptr [rdx+318h], 11000h
0x180031295  jnb     short loc_180031308
0x180031297  mov     rcx, cs:WPP_GLOBAL_Control
0x18003129e  lea     rax, WPP_GLOBAL_Control
0x1800312a5  mov     edi, 5DCh
0x1800312aa  cmp     rcx, rax
0x1800312ad  jz      short loc_1800312D6
0x1800312af  test    dword ptr [rcx+1Ch], 8000h
0x1800312b6  jz      short loc_1800312D6
0x1800312b8  cmp     byte ptr [rcx+19h], 2
0x1800312bc  jb      short loc_1800312D6
0x1800312be  mov     rcx, [rcx+10h]
0x1800312c2  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800312c9  mov     edx, 0Eh
0x1800312ce  mov     r9d, edi
0x1800312d1  call    WPP_SF_D
0x1800312d6  xorps   xmm0, xmm0
0x1800312d9  mov     [rbp+57h+var_C0], 0
0x1800312e1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800312e8  mov     [rbp+57h+var_B8], edi
0x1800312eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800312ef  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800312f6  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800312fb  mov     [rbp+57h+var_B0], 161h
0x180031302  call    _CxxThrowException_0
0x180031308  mov     rdx, [rdx+2A0h]
0x18003130f  lea     rcx, [rbp+57h+var_A8]
0x180031313  call    ReadFileHeader
0x180031318  movups  xmm0, xmmword ptr [rax]
0x18003131b  movups  xmm1, xmmword ptr [rax+10h]
0x18003131f  movups  xmm2, xmmword ptr [rax+20h]
0x180031323  movups  xmm3, xmmword ptr [rax+30h]
0x180031327  movups  xmm4, xmmword ptr [rax+40h]
0x18003132b  movups  xmm5, xmmword ptr [rax+50h]
0x18003132f  movups  xmm6, xmmword ptr [rax+60h]
0x180031333  movups  xmm7, xmmword ptr [rax+70h]
0x180031337  mov     rax, [rdi]
0x18003133a  movups  xmmword ptr [rax+10h], xmm0
0x18003133e  movups  xmmword ptr [rax+20h], xmm1
0x180031342  movups  xmmword ptr [rax+30h], xmm2
0x180031346  movups  xmmword ptr [rax+40h], xmm3
0x18003134a  movups  xmmword ptr [rax+50h], xmm4
0x18003134e  movups  xmmword ptr [rax+60h], xmm5
0x180031352  movups  xmmword ptr [rax+70h], xmm6
0x180031356  movups  xmmword ptr [rax+80h], xmm7
0x18003135d  mov     rcx, [rdi]
0x180031360  add     rcx, 10h; Buffer
0x180031364  call    ?IsFileHeaderValid@@YA_NAEBUFileHeader@@@Z; IsFileHeaderValid(FileHeader const &)
0x180031369  test    al, al
0x18003136b  jnz     short loc_1800313DE
0x18003136d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031374  lea     rax, WPP_GLOBAL_Control
0x18003137b  mov     edi, 5DCh
0x180031380  cmp     rcx, rax
0x180031383  jz      short loc_1800313AC
0x180031385  test    dword ptr [rcx+1Ch], 8000h
0x18003138c  jz      short loc_1800313AC
0x18003138e  cmp     byte ptr [rcx+19h], 2
0x180031392  jb      short loc_1800313AC
0x180031394  mov     rcx, [rcx+10h]
0x180031398  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003139f  mov     edx, 0Fh
0x1800313a4  mov     r9d, edi
0x1800313a7  call    WPP_SF_D
0x1800313ac  xorps   xmm0, xmm0
0x1800313af  mov     [rbp+57h+var_C0], 0
0x1800313b7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800313be  mov     [rbp+57h+var_B8], edi
0x1800313c1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800313c5  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800313cc  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800313d1  mov     [rbp+57h+var_B0], 169h
0x1800313d8  call    _CxxThrowException_0
0x1800313de  mov     rax, [rdi]
0x1800313e1  cmp     word ptr [rax+36h], 3
0x1800313e6  jbe     short loc_180031459
0x1800313e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313ef  lea     rax, WPP_GLOBAL_Control
0x1800313f6  mov     edi, 3ABBh
0x1800313fb  cmp     rcx, rax
0x1800313fe  jz      short loc_180031427
0x180031400  test    dword ptr [rcx+1Ch], 8000h
0x180031407  jz      short loc_180031427
0x180031409  cmp     byte ptr [rcx+19h], 2
0x18003140d  jb      short loc_180031427
0x18003140f  mov     rcx, [rcx+10h]
0x180031413  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003141a  mov     edx, 10h
0x18003141f  mov     r9d, edi
0x180031422  call    WPP_SF_D
0x180031427  xorps   xmm0, xmm0
0x18003142a  mov     [rbp+57h+var_C0], 0
0x180031432  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031439  mov     [rbp+57h+var_B8], edi
0x18003143c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031440  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x180031447  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18003144c  mov     [rbp+57h+var_B0], 16Eh
0x180031453  call    _CxxThrowException_0
0x180031459  jnb     short loc_1800314CC
0x18003145b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031462  lea     rax, WPP_GLOBAL_Control
0x180031469  mov     edi, 3ABAh
0x18003146e  cmp     rcx, rax
0x180031471  jz      short loc_18003149A
0x180031473  test    dword ptr [rcx+1Ch], 8000h
0x18003147a  jz      short loc_18003149A
0x18003147c  cmp     byte ptr [rcx+19h], 2
0x180031480  jb      short loc_18003149A
0x180031482  mov     rcx, [rcx+10h]
0x180031486  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003148d  mov     edx, 11h
0x180031492  mov     r9d, edi
0x180031495  call    WPP_SF_D
0x18003149a  xorps   xmm0, xmm0
0x18003149d  mov     [rbp+57h+var_C0], 0
0x1800314a5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800314ac  mov     [rbp+57h+var_B8], edi
0x1800314af  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800314b3  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800314ba  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800314bf  mov     [rbp+57h+var_B0], 173h
0x1800314c6  call    _CxxThrowException_0
0x1800314cc  lea     r11, [rsp+0F0h+var_s0]
0x1800314d4  mov     rdi, [r11+10h]
0x1800314d8  movaps  xmm6, xmmword ptr [r11-10h]
0x1800314dd  movaps  xmm7, xmmword ptr [r11-20h]
0x1800314e2  mov     rsp, r11
0x1800314e5  pop     rbp
0x1800314e6  retn
```
