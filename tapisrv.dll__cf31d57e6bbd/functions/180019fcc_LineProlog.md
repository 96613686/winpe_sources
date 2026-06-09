# LineProlog

- ea: `0x180019fcc`
- end: `0x18001a612`
- name: `LineProlog`
- size: `1606`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int *, unsigned int, LPHANDLE lpTargetHandle, _DWORD *, unsigned int, _QWORD *, _QWORD *, unsigned int, unsigned int *, char **)`
- caller_count: `90`
- callee_count: `8`
- tags: ``

## callers

- `0x180007570`
- `0x180007810`
- `0x180007ba0`
- `0x180007df0`
- `0x180008090`
- `0x1800081d0`
- `0x1800082b0`
- `0x1800083a0`
- `0x180008500`
- `0x180008b50`
- `0x180008d20`
- `0x180009010`
- `0x180009340`
- `0x180009440`
- `0x180009510`
- `0x180009810`
- `0x180009ab0`
- `0x180009cc0`
- `0x180009e00`
- `0x180009f50`
- `0x18000a580`
- `0x18000a820`
- `0x18000a9d0`
- `0x18000ab90`
- `0x18000ae10`
- `0x18000af50`
- `0x18000b170`
- `0x18000b52c`
- `0x18000b734`
- `0x18000bc80`
- `0x18000bed0`
- `0x18000c320`
- `0x18000cea0`
- `0x18000d180`
- `0x18000d360`
- `0x18000d980`
- `0x18000e2a0`
- `0x18000e420`
- `0x18000f080`
- `0x18000f180`
- `0x18000f6a0`
- `0x18000f930`
- `0x18000fe60`
- `0x180010660`
- `0x180010c30`
- `0x180010d40`
- `0x1800112a0`
- `0x180011430`
- `0x180011600`
- `0x180011b10`

## callees

- `0x180006f24`
- `0x180007460`
- `0x180019fcc`
- `0x18002c8d4`
- `0x18002f660`
- `0x18003dc84`
- `0x18003e2f0`
- `0x18003e3b4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001a54d`
- `KERNEL32!HeapAlloc` at `0x18001a54d`

## string_xrefs

- `0x18001a5ba`: `LineProlog: OpenContext %u`

## pseudocode

```c
__int64 __fastcall LineProlog(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int a5,
        LPHANDLE lpTargetHandle,
        _DWORD *a7,
        unsigned int a8,
        _QWORD *a9,
        _QWORD *a10,
        unsigned int a11,
        unsigned int *a12,
        char **a13)
{
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rsi
  unsigned int v17; // edx
  unsigned int *v18; // r15
  _DWORD *valid; // rdx
  char *LineLookupEntry; // rax
  int v21; // eax
  _QWORD *v22; // r15
  __int64 v23; // rcx
  char *v24; // rax
  char *v25; // r14
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // r14
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  _DWORD *v33; // rax
  __int64 v34; // rcx
  _DWORD *v35; // rsi
  unsigned int v36; // eax
  __int64 v37; // rdx
  int v39; // [rsp+30h] [rbp-48h]
  int v40; // [rsp+34h] [rbp-44h]
  __int64 v41; // [rsp+48h] [rbp-30h]

  TRACELogPrint(524290, "LineProlog:  -- enter");
  TRACELogPrint(262146, "LineProlog: dwArg %lx", a3);
  if ( lpTargetHandle )
  {
    *lpTargetHandle = 0;
    *a7 = 0;
  }
  *a12 = 0;
  if ( a10 )
    *a10 = 0;
  if ( !dword_180051918 )
  {
    v14 = -2147483568;
    goto LABEL_79;
  }
  v15 = a1;
  if ( *(_QWORD *)(a1 + 56) == -1 )
  {
    v14 = -2147483566;
    goto LABEL_79;
  }
  v14 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v16 = 0;
  if ( a2 != 1 )
  {
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
      {
        v22 = a10;
        goto LABEL_65;
      }
      if ( (dword_180051900 & 2) == 0 || (*(_BYTE *)(a1 + 216) & 1) != 0 )
      {
        v18 = a4;
        *a4 = a5;
      }
      else
      {
        if ( a5 >= *(_DWORD *)(a1 + 96) || (v17 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4LL * a5), v17 == -1) )
        {
          v14 = -2147483646;
          goto LABEL_79;
        }
        v18 = a4;
        *a4 = v17;
        v15 = a1;
      }
      if ( a3 )
      {
        valid = (_DWORD *)IsValidLineApp(a3, v15);
        if ( !valid )
          v14 = -2147483628;
      }
      else
      {
        valid = 0;
      }
      if ( a10 )
      {
        v39 = valid[7];
        v40 = 0;
        if ( *valid != 1347436876 )
          v14 = -2147483628;
      }
      if ( !v14 )
      {
        LineLookupEntry = GetLineLookupEntry(*v18);
        if ( !LineLookupEntry )
        {
          v14 = -2147483646;
          goto LABEL_79;
        }
        if ( *((_DWORD *)LineLookupEntry + 8) )
        {
          v14 = -2147483582;
          goto LABEL_79;
        }
        v16 = *((_QWORD *)LineLookupEntry + 3);
        if ( !v16 )
        {
          v14 = -2147483581;
          goto LABEL_79;
        }
        *a13 = LineLookupEntry;
        if ( lpTargetHandle )
        {
          if ( (*(_BYTE *)(v16 + 24) & 1) != 0 )
          {
            v21 = WaitForMutex(*(HANDLE *)(v16 + 8), lpTargetHandle, 1448038992);
            v22 = a10;
            goto LABEL_36;
          }
        }
      }
      goto LABEL_64;
    }
    TRACELogPrint(262146, "LineProlog: ANY_RT_HLINE");
    v24 = (char *)ReferenceObject(v23, a3, 1229734732);
    v25 = v24;
    if ( v24 )
    {
      TRACELogPrint(262146, "LineProlog: ReferenceObject returned ptLineClient %p", v24);
      if ( *((_QWORD *)v25 + 1) != a1 )
      {
        v14 = -2147483605;
        goto LABEL_79;
      }
      *a12 = a3;
      *a13 = v25;
      v26 = *((_QWORD *)v25 + 4);
      v16 = *(_QWORD *)(v26 + 192);
      *(_QWORD *)a4 = *(_QWORD *)(v26 + 200);
      v22 = a10;
      if ( a10 )
      {
        v39 = *(_DWORD *)(*((_QWORD *)v25 + 2) + 28LL);
        v40 = *((_DWORD *)v25 + 18);
        v41 = *(unsigned int *)(*((_QWORD *)v25 + 4) + 208LL);
      }
      if ( *(_DWORD *)v25 == 1229734732 )
      {
        if ( lpTargetHandle
          && (*(_BYTE *)(v16 + 24) & 1) != 0
          && !(unsigned int)WaitForMutex(*(HANDLE *)(v16 + 8), lpTargetHandle, 1448038992) )
        {
          TRACELogPrint(65538, "LineProlog: waitformutex failed");
LABEL_37:
          v14 = -2147483576;
          goto LABEL_65;
        }
      }
      else
      {
        v14 = -2147483605;
      }
      goto LABEL_65;
    }
    TRACELogPrint(65538, "LineProlog: ReferenceObject returned NULL");
    v14 = -2147483605;
LABEL_64:
    v22 = a10;
    goto LABEL_65;
  }
  TRACELogPrint(262146, "LineProlog: ANY_RT_HCALL ");
  v28 = (_QWORD *)ReferenceObject(v27, a3, 1229734723);
  v29 = v28;
  if ( !v28 )
  {
    v14 = -2147483624;
    goto LABEL_64;
  }
  TRACELogPrint(262146, "LineProlog: ReferenceObject returned ptCallClient %p", v28);
  if ( v29[1] != a1 )
  {
    v14 = -2147483624;
    goto LABEL_79;
  }
  if ( *((_DWORD *)v29 + 8) < a5 )
  {
    v14 = -2147483578;
    goto LABEL_79;
  }
  *a12 = a3;
  *a13 = (char *)v29;
  v30 = v29[3];
  v16 = *(_QWORD *)(v30 + 24);
  *(_QWORD *)a4 = *(_QWORD *)(v30 + 40);
  v22 = a10;
  if ( a10 )
  {
    v31 = v29[2];
    v39 = *(_DWORD *)(*(_QWORD *)(v31 + 16) + 28LL);
    v40 = *(_DWORD *)(v31 + 72);
    v41 = *(unsigned int *)(*(_QWORD *)(v31 + 32) + 208LL);
  }
  if ( *(_DWORD *)v29 == 1229734723 )
  {
    if ( lpTargetHandle && (*(_BYTE *)(v16 + 24) & 1) != 0 )
    {
      v21 = WaitForMutex(*(HANDLE *)(v16 + 8), lpTargetHandle, 1448038992);
LABEL_36:
      if ( v21 )
        goto LABEL_65;
      goto LABEL_37;
    }
  }
  else
  {
    v14 = -2147483624;
  }
LABEL_65:
  if ( v14 )
    goto LABEL_79;
  if ( a9 )
  {
    v32 = *(_QWORD *)(v16 + 8LL * a8 + 128);
    *a9 = v32;
    if ( !v32 )
    {
      v14 = -2147483575;
      goto LABEL_79;
    }
  }
  if ( !v22 )
    goto LABEL_79;
  v33 = HeapAlloc(ghTapisrvHeap, 8u, 0x78u);
  v35 = v33;
  if ( !v33 )
  {
LABEL_71:
    v14 = -2147483580;
    goto LABEL_79;
  }
  v36 = NewObject(v34, v33, 0);
  v35[18] = v36;
  if ( !v36 )
  {
    ServerFree(v35);
    goto LABEL_71;
  }
  *v35 = 1129927489;
  *((_QWORD *)v35 + 4) = a1;
  v35[15] = v39;
  v35[16] = v40;
  v37 = v41;
  if ( a2 == 3 )
    v37 = v36;
  *((_QWORD *)v35 + 3) = v37;
  TRACELogPrint(262146, "LineProlog: OpenContext %u", v40);
  v35[14] = 1;
  v14 = a11;
  if ( !a11 )
    v14 = v35[18];
  v35[19] = v14;
  *v22 = v35;
LABEL_79:
  TRACELogPrint(524290, "LienProlog: exit, result = x%lx", v14);
  return v14;
}

```

## disassembly

```asm
0x180019fcc  mov     rax, rsp
0x180019fcf  mov     [rax+18h], rbx
0x180019fd3  mov     [rax+20h], r9
0x180019fd7  mov     [rax+10h], edx
0x180019fda  mov     [rax+8], rcx
0x180019fde  push    rsi
0x180019fdf  push    r12
0x180019fe1  push    r13
0x180019fe3  push    r14
0x180019fe5  push    r15
0x180019fe7  sub     rsp, 50h
0x180019feb  mov     r12d, r8d
0x180019fee  lea     rdx, aLineprologEnte; "LineProlog:  -- enter"
0x180019ff5  mov     ecx, 80002h
0x180019ffa  call    TRACELogPrint
0x180019fff  mov     r8d, r12d
0x18001a002  lea     rdx, aLineprologDwar; "LineProlog: dwArg %lx"
0x18001a009  mov     ecx, 40002h
0x18001a00e  call    TRACELogPrint
0x18001a013  mov     r13, [rsp+78h+lpTargetHandle]
0x18001a01b  test    r13, r13
0x18001a01e  jz      short loc_18001A036
0x18001a020  mov     qword ptr [r13+0], 0
0x18001a028  mov     rax, [rsp+78h+arg_30]
0x18001a030  mov     dword ptr [rax], 0
0x18001a036  mov     r15, [rsp+78h+arg_58]
0x18001a03e  mov     dword ptr [r15], 0
0x18001a045  mov     r14, [rsp+78h+arg_48]
0x18001a04d  test    r14, r14
0x18001a050  jz      short loc_18001A059
0x18001a052  mov     qword ptr [r14], 0
0x18001a059  cmp     cs:dword_180051918, 0
0x18001a060  jnz     short loc_18001A06C
0x18001a062  mov     ebx, 80000050h
0x18001a067  jmp     loc_18001A5E6
0x18001a06c  mov     rdx, [rsp+78h+arg_0]
0x18001a074  cmp     qword ptr [rdx+38h], 0FFFFFFFFFFFFFFFFh
0x18001a079  jnz     short loc_18001A085
0x18001a07b  mov     ebx, 80000052h
0x18001a080  jmp     loc_18001A5E6
0x18001a085  xor     ebx, ebx
0x18001a087  mov     [rsp+78h+var_48], ebx
0x18001a08b  mov     [rsp+78h+var_44], ebx
0x18001a08f  mov     [rsp+78h+var_30], rbx
0x18001a094  xor     esi, esi
0x18001a096  mov     [rsp+78h+var_38], rsi
0x18001a09b  mov     eax, [rsp+78h+arg_8]
0x18001a0a2  sub     eax, 1
0x18001a0a5  jz      loc_18001A3A2
0x18001a0ab  sub     eax, 1
0x18001a0ae  jz      loc_18001A22D
0x18001a0b4  cmp     eax, 1
0x18001a0b7  jnz     loc_18001A4E5
0x18001a0bd  test    byte ptr cs:dword_180051900, 2
0x18001a0c4  jz      short loc_18001A119
0x18001a0c6  test    [rdx+0D8h], al
0x18001a0cc  jnz     short loc_18001A119
0x18001a0ce  mov     eax, [rsp+78h+arg_20]
0x18001a0d5  cmp     eax, [rdx+60h]
0x18001a0d8  jnb     short loc_18001A0FD
0x18001a0da  mov     ecx, eax
0x18001a0dc  mov     rax, [rdx+58h]
0x18001a0e0  mov     edx, [rax+rcx*4]
0x18001a0e3  cmp     edx, 0FFFFFFFFh
0x18001a0e6  jz      short loc_18001A0FD
0x18001a0e8  mov     r15, [rsp+78h+arg_18]
0x18001a0f0  mov     [r15], edx
0x18001a0f3  mov     rdx, [rsp+78h+arg_0]
0x18001a0fb  jmp     short loc_18001A12B
0x18001a0fd  mov     ebx, 80000002h
0x18001a102  mov     [rsp+78h+var_40], ebx
0x18001a106  jmp     loc_18001A5E6
0x18001a10b  mov     ebx, 8000002Bh
0x18001a110  mov     [rsp+78h+var_40], ebx
0x18001a114  jmp     loc_18001A5E6
0x18001a119  mov     eax, [rsp+78h+arg_20]
0x18001a120  mov     r15, [rsp+78h+arg_18]
0x18001a128  mov     [r15], eax
0x18001a12b  test    r12d, r12d
0x18001a12e  jz      short loc_18001A149
0x18001a130  mov     ecx, r12d
0x18001a133  call    IsValidLineApp
0x18001a138  mov     rdx, rax
0x18001a13b  mov     ecx, 80000014h
0x18001a140  test    rax, rax
0x18001a143  jnz     short loc_18001A150
0x18001a145  mov     ebx, ecx
0x18001a147  jmp     short loc_18001A150
0x18001a149  xor     edx, edx
0x18001a14b  mov     ecx, 80000014h
0x18001a150  test    r14, r14
0x18001a153  jz      short loc_18001A191
0x18001a155  mov     eax, [rdx+1Ch]
0x18001a158  mov     [rsp+78h+var_48], eax
0x18001a15c  mov     [rsp+78h+var_44], 0
0x18001a164  cmp     dword ptr [rdx], 5050414Ch
0x18001a16a  cmovnz  ebx, ecx
0x18001a16d  mov     [rsp+78h+var_40], ebx
0x18001a171  jmp     short loc_18001A191
0x18001a173  mov     ebx, 80000014h
0x18001a178  mov     [rsp+78h+var_40], ebx
0x18001a17c  mov     r13, [rsp+78h+lpTargetHandle]
0x18001a184  mov     rsi, [rsp+78h+var_38]
0x18001a189  mov     r15, [rsp+78h+arg_18]
0x18001a191  test    ebx, ebx
0x18001a193  jnz     loc_18001A4F6
0x18001a199  mov     ecx, [r15]
0x18001a19c  call    GetLineLookupEntry
0x18001a1a1  mov     r8, rax
0x18001a1a4  test    rax, rax
0x18001a1a7  jnz     short loc_18001A1B3
0x18001a1a9  mov     ebx, 80000002h
0x18001a1ae  jmp     loc_18001A5E6
0x18001a1b3  cmp     dword ptr [rax+20h], 0
0x18001a1b7  jz      short loc_18001A1C3
0x18001a1b9  mov     ebx, 80000042h
0x18001a1be  jmp     loc_18001A5E6
0x18001a1c3  mov     rsi, [rax+18h]
0x18001a1c7  test    rsi, rsi
0x18001a1ca  jnz     short loc_18001A1D6
0x18001a1cc  mov     ebx, 80000043h
0x18001a1d1  jmp     loc_18001A5E6
0x18001a1d6  mov     rax, [rsp+78h+arg_60]
0x18001a1de  mov     [rax], r8
0x18001a1e1  test    r13, r13
0x18001a1e4  jz      loc_18001A4F6
0x18001a1ea  test    byte ptr [rsi+18h], 1
0x18001a1ee  jz      loc_18001A4F6
0x18001a1f4  mov     [rsp+78h+var_58], 564F5250h; int
0x18001a1fc  mov     r9, rsi
0x18001a1ff  mov     r8, [rsp+78h+arg_30]
0x18001a207  mov     rdx, r13; lpTargetHandle
0x18001a20a  mov     rcx, [rsi+8]; hSourceHandle
0x18001a20e  call    WaitForMutex
0x18001a213  mov     r15, [rsp+78h+arg_48]
0x18001a21b  test    eax, eax
0x18001a21d  jnz     loc_18001A4FE
0x18001a223  mov     ebx, 80000048h
0x18001a228  jmp     loc_18001A4FE
0x18001a22d  lea     rdx, aLineprologAnyR; "LineProlog: ANY_RT_HLINE"
0x18001a234  mov     ecx, 40002h
0x18001a239  call    TRACELogPrint
0x18001a23e  mov     r8d, 494C434Ch
0x18001a244  mov     edx, r12d
0x18001a247  call    ReferenceObject
0x18001a24c  mov     r14, rax
0x18001a24f  mov     [rsp+78h+arg_58], rax
0x18001a257  test    rax, rax
0x18001a25a  jz      loc_18001A387
0x18001a260  mov     r8, rax
0x18001a263  lea     rdx, aLineprologRefe_1; "LineProlog: ReferenceObject returned pt"...
0x18001a26a  mov     ecx, 40002h
0x18001a26f  call    TRACELogPrint
0x18001a274  mov     rax, [rsp+78h+arg_0]
0x18001a27c  cmp     [r14+8], rax
0x18001a280  jz      short loc_18001A28C
0x18001a282  mov     ebx, 8000002Bh
0x18001a287  jmp     loc_18001A5E6
0x18001a28c  mov     [r15], r12d
0x18001a28f  mov     rax, [rsp+78h+arg_60]
0x18001a297  mov     [rax], r14
0x18001a29a  mov     rax, [r14+20h]
0x18001a29e  mov     rsi, [rax+0C0h]
0x18001a2a5  mov     [rsp+78h+var_38], rsi
0x18001a2aa  mov     rax, [rax+0C8h]
0x18001a2b1  mov     r15, [rsp+78h+arg_18]
0x18001a2b9  mov     [r15], rax
0x18001a2bc  mov     r15, [rsp+78h+arg_48]
0x18001a2c4  test    r15, r15
0x18001a2c7  jz      short loc_18001A2EB
0x18001a2c9  mov     rax, [r14+10h]
0x18001a2cd  mov     ecx, [rax+1Ch]
0x18001a2d0  mov     [rsp+78h+var_48], ecx
0x18001a2d4  mov     eax, [r14+48h]
0x18001a2d8  mov     [rsp+78h+var_44], eax
0x18001a2dc  mov     rax, [r14+20h]
0x18001a2e0  mov     ecx, [rax+0D0h]
0x18001a2e6  mov     [rsp+78h+var_30], rcx
0x18001a2eb  jmp     short loc_18001A320
0x18001a2ed  lea     rdx, aLineprologExce; "LineProlog: exception"
0x18001a2f4  mov     ecx, 10002h
0x18001a2f9  call    TRACELogPrint
0x18001a2fe  mov     ebx, 8000002Bh
0x18001a303  mov     r13, [rsp+78h+lpTargetHandle]
0x18001a30b  mov     rsi, [rsp+78h+var_38]
0x18001a310  mov     r14, [rsp+78h+arg_58]
0x18001a318  mov     r15, [rsp+78h+arg_48]
0x18001a320  test    ebx, ebx
0x18001a322  jnz     short loc_18001A37D
0x18001a324  cmp     dword ptr [r14], 494C434Ch
0x18001a32b  jnz     short loc_18001A37D
0x18001a32d  test    r13, r13
0x18001a330  jz      loc_18001A4FE
0x18001a336  test    byte ptr [rsi+18h], 1
0x18001a33a  jz      loc_18001A4FE
0x18001a340  mov     [rsp+78h+var_58], 564F5250h; int
0x18001a348  mov     r9, rsi
0x18001a34b  mov     r8, [rsp+78h+arg_30]
0x18001a353  mov     rdx, r13; lpTargetHandle
0x18001a356  mov     rcx, [rsi+8]; hSourceHandle
0x18001a35a  call    WaitForMutex
0x18001a35f  test    eax, eax
0x18001a361  jnz     loc_18001A4FE
0x18001a367  lea     rdx, aLineprologWait; "LineProlog: waitformutex failed"
0x18001a36e  mov     ecx, 10002h
0x18001a373  call    TRACELogPrint
0x18001a378  jmp     loc_18001A223
0x18001a37d  mov     ebx, 8000002Bh
0x18001a382  jmp     loc_18001A4FE
0x18001a387  lea     rdx, aLineprologRefe_0; "LineProlog: ReferenceObject returned NU"...
0x18001a38e  mov     ecx, 10002h
0x18001a393  call    TRACELogPrint
0x18001a398  mov     ebx, 8000002Bh
0x18001a39d  jmp     loc_18001A4F6
0x18001a3a2  lea     rdx, aLineprologAnyR_0; "LineProlog: ANY_RT_HCALL "
0x18001a3a9  mov     ecx, 40002h
0x18001a3ae  call    TRACELogPrint
0x18001a3b3  mov     r8d, 494C4343h
0x18001a3b9  mov     edx, r12d
0x18001a3bc  call    ReferenceObject
0x18001a3c1  mov     r14, rax
0x18001a3c4  mov     [rsp+78h+arg_58], rax
0x18001a3cc  test    rax, rax
0x18001a3cf  jz      loc_18001A4F1
0x18001a3d5  mov     r8, rax
0x18001a3d8  lea     rdx, aLineprologRefe; "LineProlog: ReferenceObject returned pt"...
0x18001a3df  mov     ecx, 40002h
0x18001a3e4  call    TRACELogPrint
0x18001a3e9  mov     rax, [rsp+78h+arg_0]
0x18001a3f1  cmp     [r14+8], rax
0x18001a3f5  jz      short loc_18001A401
0x18001a3f7  mov     ebx, 80000018h
0x18001a3fc  jmp     loc_18001A5E6
0x18001a401  mov     eax, [rsp+78h+arg_20]
0x18001a408  cmp     [r14+20h], eax
0x18001a40c  jnb     short loc_18001A418
0x18001a40e  mov     ebx, 80000046h
0x18001a413  jmp     loc_18001A5E6
0x18001a418  mov     [r15], r12d
0x18001a41b  mov     rax, [rsp+78h+arg_60]
0x18001a423  mov     [rax], r14
0x18001a426  mov     rax, [r14+18h]
0x18001a42a  mov     rsi, [rax+18h]
0x18001a42e  mov     [rsp+78h+var_38], rsi
0x18001a433  mov     rax, [rax+28h]
0x18001a437  mov     r15, [rsp+78h+arg_18]
0x18001a43f  mov     [r15], rax
0x18001a442  mov     r15, [rsp+78h+arg_48]
0x18001a44a  test    r15, r15
0x18001a44d  jz      short loc_18001A474
0x18001a44f  mov     rdx, [r14+10h]
0x18001a453  mov     rax, [rdx+10h]
0x18001a457  mov     ecx, [rax+1Ch]
0x18001a45a  mov     [rsp+78h+var_48], ecx
0x18001a45e  mov     eax, [rdx+48h]
0x18001a461  mov     [rsp+78h+var_44], eax
0x18001a465  mov     rax, [rdx+20h]
0x18001a469  mov     ecx, [rax+0D0h]
0x18001a46f  mov     [rsp+78h+var_30], rcx
0x18001a474  jmp     short loc_18001A4A9
0x18001a476  lea     rdx, aLineprologExce; "LineProlog: exception"
0x18001a47d  mov     ecx, 10002h
0x18001a482  call    TRACELogPrint
0x18001a487  mov     ebx, 80000018h
0x18001a48c  mov     r13, [rsp+78h+lpTargetHandle]
0x18001a494  mov     rsi, [rsp+78h+var_38]
0x18001a499  mov     r14, [rsp+78h+arg_58]
0x18001a4a1  mov     r15, [rsp+78h+arg_48]
0x18001a4a9  test    ebx, ebx
0x18001a4ab  jnz     short loc_18001A4EA
0x18001a4ad  cmp     dword ptr [r14], 494C4343h
0x18001a4b4  jnz     short loc_18001A4EA
0x18001a4b6  test    r13, r13
0x18001a4b9  jz      short loc_18001A4FE
0x18001a4bb  test    byte ptr [rsi+18h], 1
0x18001a4bf  jz      short loc_18001A4FE
0x18001a4c1  mov     [rsp+78h+var_58], 564F5250h; int
0x18001a4c9  mov     r9, rsi
0x18001a4cc  mov     r8, [rsp+78h+arg_30]
0x18001a4d4  mov     rdx, r13; lpTargetHandle
0x18001a4d7  mov     rcx, [rsi+8]; hSourceHandle
0x18001a4db  call    WaitForMutex
0x18001a4e0  jmp     loc_18001A21B
0x18001a4e5  mov     r15, r14
0x18001a4e8  jmp     short loc_18001A4FE
0x18001a4ea  mov     ebx, 80000018h
0x18001a4ef  jmp     short loc_18001A4FE
0x18001a4f1  mov     ebx, 80000018h
0x18001a4f6  mov     r15, [rsp+78h+arg_48]
0x18001a4fe  test    ebx, ebx
0x18001a500  jnz     loc_18001A5E6
0x18001a506  mov     rdx, [rsp+78h+arg_40]
0x18001a50e  test    rdx, rdx
0x18001a511  jz      short loc_18001A534
0x18001a513  mov     eax, [rsp+78h+arg_38]
0x18001a51a  mov     rcx, [rsi+rax*8+80h]
0x18001a522  mov     [rdx], rcx
0x18001a525  test    rcx, rcx
0x18001a528  jnz     short loc_18001A534
0x18001a52a  mov     ebx, 80000049h
  ... truncated ...
```
