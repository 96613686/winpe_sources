# RealSystemParametersInfoA(uint,uint,void *,uint)

- ea: `0x18004d5d0`
- end: `0x18004dbdb`
- name: `?RealSystemParametersInfoA@@YAHIIPEAXI@Z`
- size: `1547`
- prototype: `int(unsigned int, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18002ce00`
- `0x180043b70`
- `0x18004d5d0`
- `0x18004dbe4`
- `0x1800945d0`
- `0x180095408`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserSystemParametersInfo` at `0x18004d6cf`
- `win32u!NtUserSystemParametersInfo` at `0x18004d6cf`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004d873`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18004d873`
- `ntdll!RtlFreeHeap` at `0x18004dbd0`
- `ntdll!RtlFreeHeap` at `0x18004dbd0`
- `ntdll!RtlAllocateHeap` at `0x18004d975`
- `ntdll!RtlAllocateHeap` at `0x18004d9a2`
- `ntdll!RtlAllocateHeap` at `0x18004d975`
- `ntdll!RtlAllocateHeap` at `0x18004d9a2`

## pseudocode

```c
_BOOL8 __fastcall RealSystemParametersInfoA(unsigned int a1, DWORD a2, char *a3, unsigned int a4)
{
  struct tagLOGFONTW *v7; // rdi
  BOOL v9; // r15d
  DWORD v10; // r13d
  int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // esi
  unsigned int v14; // esi
  unsigned int v15; // esi
  unsigned int v16; // esi
  unsigned int v17; // esi
  int v19; // ecx
  int v20; // r15d
  const WCHAR *Heap; // rax
  __int64 v22; // rax
  struct tagLOGFONTA *v23; // rcx
  struct tagLOGFONTW *v24; // rdx
  int v25; // eax
  bool v26; // zf
  bool v27; // cc
  signed int v28; // ebx
  signed int v29; // eax
  int v30; // eax
  ULONG ResultSize[2]; // [rsp+30h] [rbp-D0h] BYREF
  PVOID v32[4]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v33[24]; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+74h] [rbp-8Ch]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  int v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+84h] [rbp-7Ch]
  struct tagLOGFONTW v40; // [rsp+88h] [rbp-78h] BYREF
  int v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+E8h] [rbp-18h]
  struct tagLOGFONTW v43; // [rsp+ECh] [rbp-14h] BYREF
  int v44; // [rsp+148h] [rbp+48h]
  int v45; // [rsp+14Ch] [rbp+4Ch]
  struct tagLOGFONTW v46; // [rsp+150h] [rbp+50h] BYREF
  struct tagLOGFONTW v47; // [rsp+1ACh] [rbp+ACh] BYREF
  struct tagLOGFONTW v48; // [rsp+208h] [rbp+108h] BYREF
  int v49; // [rsp+264h] [rbp+164h]
  __int128 v50; // [rsp+270h] [rbp+170h] BYREF
  struct tagLOGFONTW v51; // [rsp+280h] [rbp+180h] BYREF
  struct tagLOGFONTW v52; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v53[528]; // [rsp+340h] [rbp+240h] BYREF

  v7 = (struct tagLOGFONTW *)a3;
  memset_0(&v34, 0, 0x1F8u);
  memset_0(&v50, 0, 0x6Cu);
  memset_0(&v52, 0, sizeof(v52));
  memset_0(v53, 0, 0x208u);
  *(_QWORD *)ResultSize = a3;
  v9 = 0;
  v10 = a2;
  memset(v32, 0, sizeof(v32));
  LODWORD(v32[3]) = 0;
  memset(v33, 0, sizeof(v33));
  if ( a1 <= 0x36 )
  {
    if ( a1 == 54 )
    {
      v27 = (unsigned int)(*(_DWORD *)a3 - 1) <= 0x1B;
      goto LABEL_77;
    }
    if ( a1 <= 0x2B )
    {
      switch ( a1 )
      {
        case 0x2Bu:
          if ( !a3 )
            goto LABEL_15;
          v26 = *(_DWORD *)a3 == 20;
          goto LABEL_119;
        case 0x14u:
          if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFCuLL )
          {
            a2 = -1;
          }
          else
          {
            if ( !RtlCaptureAnsiString((struct _IN_STRING *)v32, a3, 1) )
              goto LABEL_15;
            v7 = (struct tagLOGFONTW *)v32[2];
            a2 = 0;
          }
          break;
        case 0x15u:
          v25 = -1;
          if ( a2 != 0xFFFF )
            v25 = a2;
          a2 = v25;
          if ( v25 == -1 )
          {
            a2 = -1;
          }
          else if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( !RtlCaptureAnsiString((struct _IN_STRING *)v32, a3, 1) )
              goto LABEL_15;
            v7 = (struct tagLOGFONTW *)v32[2];
          }
          break;
        case 0x1Fu:
          v7 = &v52;
          break;
        case 0x22u:
          CopyLogFontAtoW(&v52, (struct tagLOGFONTA *)a3);
          v7 = &v52;
          a2 = 92;
          break;
        case 0x29u:
          if ( !a3 || ((*(_DWORD *)a3 - 340) & 0xFFFFFFFB) != 0 )
            goto LABEL_15;
          v34 = 504;
          v7 = (struct tagLOGFONTW *)&v34;
          a2 = 504;
          break;
        case 0x2Au:
          if ( !a3 || ((*(_DWORD *)a3 - 340) & 0xFFFFFFFB) != 0 )
            goto LABEL_15;
          v19 = *((_DWORD *)a3 + 4);
          v20 = 256;
          if ( v19 > 256 )
          {
            *((_DWORD *)a3 + 4) = 256;
            v19 = 256;
          }
          if ( *((int *)a3 + 5) <= 256 )
            v20 = *((_DWORD *)a3 + 5);
          else
            *((_DWORD *)a3 + 5) = 256;
          v35 = *((_DWORD *)a3 + 1);
          v36 = *((_DWORD *)a3 + 2);
          v37 = *((_DWORD *)a3 + 3);
          v41 = *((_DWORD *)a3 + 21);
          v42 = *((_DWORD *)a3 + 22);
          v44 = *((_DWORD *)a3 + 38);
          v30 = *((_DWORD *)a3 + 39);
          v38 = v19;
          v45 = v30;
          v39 = v20;
          CopyLogFontAtoW(&v40, (struct tagLOGFONTA *)(a3 + 24));
          CopyLogFontAtoW(&v43, (struct tagLOGFONTA *)(a3 + 92));
          CopyLogFontAtoW(&v46, (struct tagLOGFONTA *)(a3 + 160));
          CopyLogFontAtoW(&v47, (struct tagLOGFONTA *)(a3 + 220));
          CopyLogFontAtoW(&v48, (struct tagLOGFONTA *)(a3 + 280));
          if ( *(_DWORD *)a3 == 340 )
          {
            a2 = 500;
            v34 = 500;
          }
          else
          {
            a2 = 504;
            v49 = *((_DWORD *)a3 + 85);
            v34 = 504;
          }
          v7 = (struct tagLOGFONTW *)&v34;
          break;
      }
      goto LABEL_8;
    }
    switch ( a1 )
    {
      case ',':
        if ( !a3 || *(_DWORD *)a3 != 20 )
          goto LABEL_15;
        a2 = 20;
        goto LABEL_8;
      case '-':
        if ( !a3 || *(_DWORD *)a3 != 76 )
          goto LABEL_15;
        v7 = (struct tagLOGFONTW *)&v50;
        goto LABEL_8;
      case '.':
        if ( !a3 || *(_DWORD *)a3 != 76 )
          goto LABEL_15;
        v50 = *(_OWORD *)a3;
        CopyLogFontAtoW(&v51, (struct tagLOGFONTA *)(a3 + 16));
        v7 = (struct tagLOGFONTW *)&v50;
        a2 = 108;
        goto LABEL_8;
      case '2':
        v27 = (unsigned int)(*(_DWORD *)a3 - 1) <= 0x17;
LABEL_77:
        if ( !v27 )
          goto LABEL_15;
        goto LABEL_8;
    }
    if ( a1 != 52 )
      goto LABEL_8;
LABEL_75:
    v27 = (unsigned int)(*(_DWORD *)a3 - 1) <= 7;
    goto LABEL_77;
  }
  if ( a1 > 0x49 )
  {
    if ( a1 == 97 )
      goto LABEL_15;
    if ( a1 != 115 )
    {
      if ( a1 != 116 && a1 != 117 )
      {
        if ( a1 == 8215 && (unsigned int)((_DWORD)a3 - 1) <= 3 )
          goto LABEL_15;
        goto LABEL_8;
      }
      if ( !a3 )
        goto LABEL_15;
      v26 = *(_DWORD *)a3 == 12;
LABEL_119:
      if ( !v26 )
        goto LABEL_15;
      goto LABEL_8;
    }
    if ( !a3 || !a2 )
      goto LABEL_15;
    v7 = (struct tagLOGFONTW *)v53;
    a2 = 260;
LABEL_8:
    v11 = NtUserSystemParametersInfo(a1, a2, v7, a4);
    v9 = v11;
    v12 = a1 - 31;
    if ( v12 )
    {
      v13 = v12 - 10;
      if ( v13 )
      {
        v14 = v13 - 4;
        if ( v14 )
        {
          v15 = v14 - 21;
          if ( v15 )
          {
            v16 = v15 - 15;
            if ( v16 && (v17 = v16 - 1) != 0 )
            {
              if ( v17 == 33 )
              {
                v28 = v10 - 1;
                v29 = WCSToMBEx(0, v7, -1, ResultSize, v10 - 1, 0);
                if ( v29 < (int)(v10 - 1) )
                  v28 = v29;
                *(_BYTE *)(v28 + *(_QWORD *)ResultSize) = 0;
              }
            }
            else if ( v11 && (a4 & 1) != 0 )
            {
              v9 = SetVideoTimeout(a2);
            }
          }
          else
          {
            ResultSize[0] = 0;
            if ( pwcHighContrastScheme )
            {
              v22 = -1;
              do
                ++v22;
              while ( pwcHighContrastScheme[v22] );
              RtlUnicodeToMultiByteN(pcHighContrastScheme, 0x80u, ResultSize, pwcHighContrastScheme, 2 * v22 + 2);
            }
            *(_QWORD *)&v7->lfEscapement = pcHighContrastScheme;
          }
          goto LABEL_15;
        }
        v23 = (struct tagLOGFONTA *)(a3 + 16);
        *(_OWORD *)a3 = v50;
        *(_DWORD *)a3 = 76;
        v24 = &v51;
      }
      else
      {
        v26 = *(_DWORD *)a3 == 344;
        *((_DWORD *)a3 + 1) = v35;
        *((_DWORD *)a3 + 2) = v36;
        *((_DWORD *)a3 + 3) = v37;
        *((_DWORD *)a3 + 4) = v38;
        *((_DWORD *)a3 + 5) = v39;
        *((_DWORD *)a3 + 21) = v41;
        *((_DWORD *)a3 + 22) = v42;
        *((_DWORD *)a3 + 38) = v44;
        *((_DWORD *)a3 + 39) = v45;
        if ( v26 )
          *((_DWORD *)a3 + 85) = v49;
        CopyLogFontWtoA((struct tagLOGFONTA *)(a3 + 24), &v40);
        CopyLogFontWtoA((struct tagLOGFONTA *)(a3 + 92), &v43);
        CopyLogFontWtoA((struct tagLOGFONTA *)(a3 + 160), &v46);
        CopyLogFontWtoA((struct tagLOGFONTA *)(a3 + 220), &v47);
        v23 = (struct tagLOGFONTA *)(a3 + 280);
        v24 = &v48;
      }
    }
    else
    {
      v24 = &v52;
      v23 = (struct tagLOGFONTA *)a3;
    }
    CopyLogFontWtoA(v23, v24);
    goto LABEL_15;
  }
  switch ( a1 )
  {
    case 'I':
LABEL_82:
      if ( !a3 )
        goto LABEL_15;
      v26 = *(_DWORD *)a3 == 8;
      goto LABEL_119;
    case ':':
      goto LABEL_75;
    case '<':
      v27 = (unsigned int)(*(_DWORD *)a3 - 1) <= 0xB;
      goto LABEL_77;
    case '@':
      v27 = (unsigned int)(*(_DWORD *)a3 - 1) <= 0x37;
      goto LABEL_77;
  }
  if ( a1 != 66 )
  {
    if ( a1 == 67 )
    {
      *(_DWORD *)v33 = 16;
      if ( !a3 )
        goto LABEL_15;
      if ( *(_DWORD *)a3 != 16 )
        goto LABEL_15;
      *(_DWORD *)&v33[4] = *((_DWORD *)a3 + 1);
      v7 = (struct tagLOGFONTW *)v33;
      if ( !RtlCaptureAnsiString((struct _IN_STRING *)v32, *((const char **)a3 + 1), 1) )
        goto LABEL_15;
      *(_OWORD *)&v33[8] = *(_OWORD *)v32[2];
      goto LABEL_8;
    }
    if ( a1 != 72 )
      goto LABEL_8;
    goto LABEL_82;
  }
  if ( a3 && *(_DWORD *)a3 == 16 )
  {
    if ( !pcHighContrastScheme )
    {
      pcHighContrastScheme = (PCHAR)RtlAllocateHeap(pUserHeap, 8u, 0x100u);
      if ( !pcHighContrastScheme )
      {
        v9 = 0;
        goto LABEL_15;
      }
    }
    Heap = pwcHighContrastScheme;
    if ( pwcHighContrastScheme
      || (Heap = (const WCHAR *)RtlAllocateHeap(pUserHeap, 8u, 0x100u), v9 = 0, (pwcHighContrastScheme = Heap) != 0) )
    {
      *((_QWORD *)a3 + 1) = Heap;
      goto LABEL_8;
    }
  }
LABEL_15:
  if ( LODWORD(v32[3]) )
    RtlFreeHeap(pUserHeap, 0, v32[1]);
  return v9;
}

```

## disassembly

```asm
0x18004d5d0  push    rbp
0x18004d5d2  push    rbx
0x18004d5d3  push    rsi
0x18004d5d4  push    rdi
0x18004d5d5  push    r12
0x18004d5d7  push    r13
0x18004d5d9  push    r14
0x18004d5db  push    r15
0x18004d5dd  lea     rbp, [rsp-468h]
0x18004d5e5  sub     rsp, 568h
0x18004d5ec  mov     rax, cs:__security_cookie
0x18004d5f3  xor     rax, rsp
0x18004d5f6  mov     [rbp+4A0h+var_50], rax
0x18004d5fd  mov     rbx, r8
0x18004d600  mov     r14d, edx
0x18004d603  mov     esi, ecx
0x18004d605  mov     rdi, r8
0x18004d608  xor     edx, edx; Val
0x18004d60a  lea     rcx, [rsp+5A0h+var_530]; void *
0x18004d60f  mov     r8d, 1F8h; Size
0x18004d615  mov     r12d, r9d
0x18004d618  call    memset_0
0x18004d61d  xor     edx, edx; Val
0x18004d61f  lea     rcx, [rbp+4A0h+var_330]; void *
0x18004d626  lea     r8d, [rdx+6Ch]; Size
0x18004d62a  call    memset_0
0x18004d62f  xor     edx, edx; Val
0x18004d631  lea     rcx, [rbp+4A0h+var_2C0]; void *
0x18004d638  lea     r8d, [rdx+5Ch]; Size
0x18004d63c  call    memset_0
0x18004d641  xor     edx, edx; Val
0x18004d643  lea     rcx, [rbp+4A0h+var_260]; void *
0x18004d64a  mov     r8d, 208h; Size
0x18004d650  call    memset_0
0x18004d655  xor     eax, eax
0x18004d657  mov     qword ptr [rsp+5A0h+ResultSize], rbx
0x18004d65c  xorps   xmm0, xmm0
0x18004d65f  mov     [rsp+5A0h+var_538], rax
0x18004d664  xor     r15d, r15d
0x18004d667  mov     r13d, r14d
0x18004d66a  mov     [rsp+5A0h+var_568], r15w
0x18004d670  lea     edx, [rax+1]
0x18004d673  movups  xmmword ptr [rsp+5A0h+P], xmm0
0x18004d678  movups  xmmword ptr [rsp+5A0h+P+0Eh], xmm0
0x18004d67d  mov     [rsp+5A0h+var_550], r15d
0x18004d682  movups  [rsp+5A0h+var_548], xmm0
0x18004d687  cmp     esi, 36h ; '6'
0x18004d68a  jbe     loc_18004D748
0x18004d690  cmp     esi, 49h ; 'I'
0x18004d693  jbe     loc_18004D7CC
0x18004d699  mov     eax, esi
0x18004d69b  sub     eax, 61h ; 'a'
0x18004d69e  jz      short loc_18004D717
0x18004d6a0  sub     eax, 12h
0x18004d6a3  jz      loc_18004DB17
0x18004d6a9  sub     eax, edx
0x18004d6ab  jz      loc_18004DB09
0x18004d6b1  sub     eax, edx
0x18004d6b3  jz      loc_18004DB09
0x18004d6b9  cmp     eax, 1FA2h
0x18004d6be  jz      loc_18004DAF8
0x18004d6c4  mov     r9d, r12d
0x18004d6c7  mov     r8, rdi
0x18004d6ca  mov     edx, r14d
0x18004d6cd  mov     ecx, esi
0x18004d6cf  call    cs:__imp_NtUserSystemParametersInfo
0x18004d6d5  movsxd  r15, eax
0x18004d6d8  sub     esi, 1Fh
0x18004d6db  jz      loc_18004DBB3
0x18004d6e1  sub     esi, 0Ah
0x18004d6e4  jz      loc_18004D889
0x18004d6ea  sub     esi, 4
0x18004d6ed  jz      loc_18004DB92
0x18004d6f3  sub     esi, 15h
0x18004d6f6  jz      loc_18004D837
0x18004d6fc  sub     esi, 0Fh
0x18004d6ff  jz      loc_18004DB70
0x18004d705  sub     esi, 1
0x18004d708  jz      loc_18004DB70
0x18004d70e  cmp     esi, 21h ; '!'
0x18004d711  jz      loc_18004DB3B
0x18004d717  cmp     [rsp+5A0h+var_550], 0
0x18004d71c  jnz     loc_18004DBC2
0x18004d722  mov     eax, r15d
0x18004d725  mov     rcx, [rbp+4A0h+var_50]
0x18004d72c  xor     rcx, rsp; StackCookie
0x18004d72f  call    __security_check_cookie
0x18004d734  add     rsp, 568h
0x18004d73b  pop     r15
0x18004d73d  pop     r14
0x18004d73f  pop     r13
0x18004d741  pop     r12
0x18004d743  pop     rdi
0x18004d744  pop     rsi
0x18004d745  pop     rbx
0x18004d746  pop     rbp
0x18004d747  retn
0x18004d748  jz      loc_18004DAC4
0x18004d74e  cmp     esi, 2Bh ; '+'
0x18004d751  ja      loc_18004DA7C
0x18004d757  jz      loc_18004DA6B
0x18004d75d  mov     eax, esi
0x18004d75f  sub     eax, 14h
0x18004d762  jz      loc_18004DA38
0x18004d768  sub     eax, edx
0x18004d76a  jz      loc_18004D9ED
0x18004d770  sub     eax, 0Ah
0x18004d773  jz      loc_18004D9E1
0x18004d779  sub     eax, 3
0x18004d77c  jz      loc_18004D9C0
0x18004d782  sub     eax, 7
0x18004d785  jz      loc_18004D931
0x18004d78b  cmp     eax, edx
0x18004d78d  jnz     loc_18004D6C4
0x18004d793  test    rbx, rbx
0x18004d796  jz      loc_18004D717
0x18004d79c  mov     eax, [rbx]
0x18004d79e  mov     edi, 154h
0x18004d7a3  sub     eax, edi
0x18004d7a5  test    eax, 0FFFFFFFBh
0x18004d7aa  jnz     loc_18004D717
0x18004d7b0  mov     ecx, [rbx+10h]
0x18004d7b3  lea     r15d, [rdi-54h]
0x18004d7b7  cmp     ecx, r15d
0x18004d7ba  jle     loc_18009E26A
0x18004d7c0  mov     [rbx+10h], r15d
0x18004d7c4  mov     ecx, r15d
0x18004d7c7  jmp     loc_18009E26A
0x18004d7cc  jz      loc_18004DADE
0x18004d7d2  mov     eax, esi
0x18004d7d4  sub     eax, 3Ah ; ':'
0x18004d7d7  jz      loc_18004DAA9
0x18004d7dd  sub     eax, 2
0x18004d7e0  jz      loc_18004DAEF
0x18004d7e6  sub     eax, 4
0x18004d7e9  jz      loc_18004DAB2
0x18004d7ef  sub     eax, 2
0x18004d7f2  jnz     loc_18004DACD
0x18004d7f8  test    rbx, rbx
0x18004d7fb  jz      loc_18004D717
0x18004d801  cmp     dword ptr [rbx], 10h
0x18004d804  jnz     loc_18004D717
0x18004d80a  cmp     cs:?pcHighContrastScheme@@3PEADEA, 0; char * pcHighContrastScheme
0x18004d812  mov     r15d, 100h
0x18004d818  jz      loc_18004D966
0x18004d81e  mov     rax, cs:?pwcHighContrastScheme@@3PEAGEA; ushort * pwcHighContrastScheme
0x18004d825  test    rax, rax
0x18004d828  jz      loc_18004D993
0x18004d82e  mov     [rbx+8], rax
0x18004d832  jmp     loc_18004D6C4
0x18004d837  mov     r9, cs:?pwcHighContrastScheme@@3PEAGEA; UnicodeString
0x18004d83e  xor     ecx, ecx
0x18004d840  mov     [rsp+5A0h+ResultSize], ecx
0x18004d844  test    r9, r9
0x18004d847  jz      short loc_18004D879
0x18004d849  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d84d  inc     rax
0x18004d850  cmp     [r9+rax*2], cx
0x18004d855  jnz     short loc_18004D84D
0x18004d857  mov     rcx, cs:?pcHighContrastScheme@@3PEADEA; MbString
0x18004d85e  lea     eax, ds:2[rax*2]
0x18004d865  lea     r8, [rsp+5A0h+ResultSize]; ResultSize
0x18004d86a  mov     [rsp+5A0h+UnicodeSize], eax; UnicodeSize
0x18004d86e  mov     edx, 80h; MbSize
0x18004d873  call    cs:__imp_RtlUnicodeToMultiByteN
0x18004d879  mov     rax, cs:?pcHighContrastScheme@@3PEADEA; char * pcHighContrastScheme
0x18004d880  mov     [rdi+8], rax
0x18004d884  jmp     loc_18004D717
0x18004d889  cmp     dword ptr [rbx], 158h
0x18004d88f  mov     eax, [rsp+5A0h+var_52C]
0x18004d893  mov     [rbx+4], eax
0x18004d896  mov     eax, [rsp+5A0h+var_528]
0x18004d89a  mov     [rbx+8], eax
0x18004d89d  mov     eax, [rsp+5A0h+var_524]
0x18004d8a1  mov     [rbx+0Ch], eax
0x18004d8a4  mov     eax, [rbp+4A0h+var_520]
0x18004d8a7  mov     [rbx+10h], eax
0x18004d8aa  mov     eax, [rbp+4A0h+var_51C]
0x18004d8ad  mov     [rbx+14h], eax
0x18004d8b0  mov     eax, [rbp+4A0h+var_4BC]
0x18004d8b3  mov     [rbx+54h], eax
0x18004d8b6  mov     eax, [rbp+4A0h+var_4B8]
0x18004d8b9  mov     [rbx+58h], eax
0x18004d8bc  mov     eax, [rbp+4A0h+var_458]
0x18004d8bf  mov     [rbx+98h], eax
0x18004d8c5  mov     eax, [rbp+4A0h+var_454]
0x18004d8c8  mov     [rbx+9Ch], eax
0x18004d8ce  jnz     short loc_18004D8DC
0x18004d8d0  mov     eax, [rbp+4A0h+var_33C]
0x18004d8d6  mov     [rbx+154h], eax
0x18004d8dc  lea     rcx, [rbx+18h]; struct tagLOGFONTA *
0x18004d8e0  lea     rdx, [rbp+4A0h+var_518]; struct tagLOGFONTW *
0x18004d8e4  call    ?CopyLogFontWtoA@@YAXPEAUtagLOGFONTA@@PEAUtagLOGFONTW@@@Z; CopyLogFontWtoA(tagLOGFONTA *,tagLOGFONTW *)
0x18004d8e9  lea     rcx, [rbx+5Ch]; struct tagLOGFONTA *
0x18004d8ed  lea     rdx, [rbp+4A0h+var_4B4]; struct tagLOGFONTW *
0x18004d8f1  call    ?CopyLogFontWtoA@@YAXPEAUtagLOGFONTA@@PEAUtagLOGFONTW@@@Z; CopyLogFontWtoA(tagLOGFONTA *,tagLOGFONTW *)
0x18004d8f6  lea     rcx, [rbx+0A0h]; struct tagLOGFONTA *
0x18004d8fd  lea     rdx, [rbp+4A0h+var_450]; struct tagLOGFONTW *
0x18004d901  call    ?CopyLogFontWtoA@@YAXPEAUtagLOGFONTA@@PEAUtagLOGFONTW@@@Z; CopyLogFontWtoA(tagLOGFONTA *,tagLOGFONTW *)
0x18004d906  lea     rcx, [rbx+0DCh]; struct tagLOGFONTA *
0x18004d90d  lea     rdx, [rbp+4A0h+var_3F4]; struct tagLOGFONTW *
0x18004d914  call    ?CopyLogFontWtoA@@YAXPEAUtagLOGFONTA@@PEAUtagLOGFONTW@@@Z; CopyLogFontWtoA(tagLOGFONTA *,tagLOGFONTW *)
0x18004d919  lea     rcx, [rbx+118h]; struct tagLOGFONTA *
0x18004d920  lea     rdx, [rbp+4A0h+var_398]; struct tagLOGFONTW *
0x18004d927  call    ?CopyLogFontWtoA@@YAXPEAUtagLOGFONTA@@PEAUtagLOGFONTW@@@Z; CopyLogFontWtoA(tagLOGFONTA *,tagLOGFONTW *)
0x18004d92c  jmp     loc_18004D717
0x18004d931  test    rbx, rbx
0x18004d934  jz      loc_18004D717
0x18004d93a  mov     eax, [rbx]
0x18004d93c  mov     edi, 154h
0x18004d941  sub     eax, edi
0x18004d943  test    eax, 0FFFFFFFBh
0x18004d948  jnz     loc_18004D717
0x18004d94e  mov     [rsp+5A0h+var_530], 1F8h
0x18004d956  lea     rdi, [rsp+5A0h+var_530]
0x18004d95b  mov     r14d, 1F8h
0x18004d961  jmp     loc_18004D6C4
0x18004d966  mov     rcx, cs:pUserHeap; HeapHandle
0x18004d96d  mov     r8, r15; Size
0x18004d970  mov     edx, 8; Flags
0x18004d975  call    cs:__imp_RtlAllocateHeap
0x18004d97b  mov     cs:?pcHighContrastScheme@@3PEADEA, rax; char * pcHighContrastScheme
0x18004d982  test    rax, rax
0x18004d985  jnz     loc_18004D81E
0x18004d98b  xor     r15d, r15d
0x18004d98e  jmp     loc_18004D717
0x18004d993  mov     rcx, cs:pUserHeap; HeapHandle
0x18004d99a  mov     r8, r15; Size
0x18004d99d  mov     edx, 8; Flags
0x18004d9a2  call    cs:__imp_RtlAllocateHeap
0x18004d9a8  xor     r15d, r15d
0x18004d9ab  mov     cs:?pwcHighContrastScheme@@3PEAGEA, rax; ushort * pwcHighContrastScheme
0x18004d9b2  test    rax, rax
0x18004d9b5  jnz     loc_18004D82E
0x18004d9bb  jmp     loc_18004D717
0x18004d9c0  mov     rdx, rbx; struct tagLOGFONTA *
0x18004d9c3  lea     rcx, [rbp+4A0h+var_2C0]; struct tagLOGFONTW *
0x18004d9ca  call    ?CopyLogFontAtoW@@YAXPEAUtagLOGFONTW@@PEAUtagLOGFONTA@@@Z; CopyLogFontAtoW(tagLOGFONTW *,tagLOGFONTA *)
0x18004d9cf  lea     rdi, [rbp+4A0h+var_2C0]
0x18004d9d6  mov     r14d, 5Ch ; '\'
0x18004d9dc  jmp     loc_18004D6C4
0x18004d9e1  lea     rdi, [rbp+4A0h+var_2C0]
0x18004d9e8  jmp     loc_18004D6C4
0x18004d9ed  or      ecx, 0FFFFFFFFh
0x18004d9f0  cmp     r14d, 0FFFFh
0x18004d9f7  mov     eax, ecx
0x18004d9f9  cmovnz  eax, r14d
0x18004d9fd  mov     r14d, eax
0x18004da00  cmp     eax, ecx
0x18004da02  jz      loc_18009E339
0x18004da08  lea     rax, [rbx-1]
0x18004da0c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004da10  ja      loc_18004D6C4
0x18004da16  mov     r8d, edx; int
0x18004da19  lea     rcx, [rsp+5A0h+var_568]; struct _IN_STRING *
0x18004da1e  mov     rdx, rbx; char *
0x18004da21  call    ?RtlCaptureAnsiString@@YAHPEAU_IN_STRING@@PEBDH@Z; RtlCaptureAnsiString(_IN_STRING *,char const *,int)
0x18004da26  test    eax, eax
0x18004da28  jz      loc_18004D717
0x18004da2e  mov     rdi, [rsp+5A0h+P+0Eh]
0x18004da33  jmp     loc_18004D6C4
0x18004da38  lea     rax, [rbx-1]
0x18004da3c  cmp     rax, 0FFFFFFFFFFFFFFFCh
0x18004da40  ja      loc_18009E341
0x18004da46  mov     r8d, edx; int
0x18004da49  lea     rcx, [rsp+5A0h+var_568]; struct _IN_STRING *
0x18004da4e  mov     rdx, rbx; char *
0x18004da51  call    ?RtlCaptureAnsiString@@YAHPEAU_IN_STRING@@PEBDH@Z; RtlCaptureAnsiString(_IN_STRING *,char const *,int)
0x18004da56  test    eax, eax
0x18004da58  jz      loc_18004D717
0x18004da5e  mov     rdi, [rsp+5A0h+P+0Eh]
0x18004da63  mov     r14d, r15d
0x18004da66  jmp     loc_18004D6C4
0x18004da6b  test    rbx, rbx
0x18004da6e  jz      loc_18004D717
0x18004da74  cmp     dword ptr [rbx], 14h
0x18004da77  jmp     loc_18009E3D3
0x18004da7c  mov     eax, esi
0x18004da7e  sub     eax, 2Ch ; ','
0x18004da81  jz      loc_18009E3B3
0x18004da87  sub     eax, edx
0x18004da89  jz      loc_18009E395
0x18004da8f  sub     eax, edx
0x18004da91  jz      loc_18009E356
0x18004da97  sub     eax, 4
0x18004da9a  jz      loc_18009E34A
0x18004daa0  cmp     eax, 2
0x18004daa3  jnz     loc_18004D6C4
0x18004daa9  mov     eax, [rbx]
0x18004daab  sub     eax, edx
0x18004daad  cmp     eax, 7
0x18004dab0  jmp     short loc_18004DAB9
0x18004dab2  mov     eax, [rbx]
0x18004dab4  sub     eax, edx
0x18004dab6  cmp     eax, 37h ; '7'
0x18004dab9  jbe     loc_18004D6C4
0x18004dabf  jmp     loc_18004D717
0x18004dac4  mov     eax, [rbx]
0x18004dac6  sub     eax, edx
0x18004dac8  cmp     eax, 1Bh
  ... truncated ...
```
