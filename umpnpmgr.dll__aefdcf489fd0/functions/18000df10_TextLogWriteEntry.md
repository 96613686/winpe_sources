# TextLogWriteEntry

- ea: `0x18000df10`
- end: `0x18000e377`
- name: `TextLogWriteEntry`
- size: `1127`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800104d8`
- `0x1800177e0`

## callees

- `0x18000c9d0`
- `0x18000df10`
- `0x18000e380`
- `0x18000e540`
- `0x18000fb9c`
- `0x1800109dc`
- `0x180017d24`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e31b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e0a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e321`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000e1f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000e1f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e064`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e064`

## pseudocode

```c
__int64 __fastcall TextLogWriteEntry(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, int a5)
{
  char *v5; // rax
  char *v6; // r15
  DWORD LastError; // ebx
  __int64 v8; // rcx
  __int64 v9; // r14
  __int64 v10; // rax
  int v11; // eax
  const char *v12; // rbx
  _DWORD *v13; // r11
  unsigned int v14; // edi
  int v15; // ecx
  bool v16; // zf
  unsigned int v17; // ecx
  unsigned int v18; // eax
  LPVOID *v19; // r13
  char *v20; // rax
  char *v21; // rsi
  DWORD v22; // ecx
  const char *v23; // r8
  HRESULT v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  _BYTE *v27; // rdi
  __int64 v28; // r8
  _BYTE *v29; // rax
  int v30; // ebp
  unsigned __int16 v31; // ax
  __int16 v32; // r9
  __int64 v33; // r10
  __int64 v34; // rdx
  bool v35; // cf
  _BYTE *v36; // r8
  int v37; // ebx
  int v38; // esi
  int v39; // edi
  HRESULT v40; // eax
  DWORD inserted; // eax
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-80h] BYREF
  char v47[24]; // [rsp+68h] [rbp-70h] BYREF
  char pszDest[24]; // [rsp+80h] [rbp-58h] BYREF

  v5 = (char *)pStrBufCreate(0);
  v6 = v5;
  if ( v5 )
  {
    v8 = *((_QWORD *)v5 + 1);
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(v8 + v10) );
    *((_DWORD *)v6 + 1) = v10;
    v11 = a5 & 0xF;
    if ( v11 == 1 )
    {
      v12 = "!!!  ";
    }
    else if ( v11 == 2 )
    {
      v12 = "!    ";
    }
    else if ( (a5 & 0x10) != 0 )
    {
      v12 = ">>>  ";
    }
    else if ( (a5 & 0x20) != 0 )
    {
      v12 = "<<<  ";
    }
    else
    {
      v12 = "   . ";
      if ( (a5 & 0x40) == 0 )
        v12 = "     ";
    }
    do
      ++v9;
    while ( v12[v9] );
    v13 = v6 + 4;
    v14 = *(_DWORD *)v6;
    v15 = *((_DWORD *)v6 + 1) + 1;
    v16 = (_DWORD)v9 + v15 == 0;
    v17 = v9 + v15;
    v18 = 1;
    if ( !v16 )
      v18 = v17;
    *(_QWORD *)&SystemTime.wYear = v6 + 4;
    if ( v14 < v18 )
    {
      v14 = ((v18 + 1023) & 0xFFFFFC00) + 1024;
      v20 = (char *)HeapAlloc(hHeap, 0, v14);
      v21 = v20;
      if ( !v20 )
      {
        v22 = 8;
LABEL_75:
        SetLastError(v22);
        goto LABEL_76;
      }
      memset_0(v20, 0, v14);
      v23 = (const char *)*((_QWORD *)v6 + 1);
      v19 = (LPVOID *)(v6 + 8);
      if ( v23 )
      {
        v24 = StringCchCopyA(v21, v14, v23);
        if ( v24 < 0 )
        {
          SetLastError((unsigned __int16)v24);
          HeapFree(hHeap, 0, v21);
          goto LABEL_76;
        }
        HeapFree(hHeap, 0, *v19);
      }
      v13 = *(_DWORD **)&SystemTime.wYear;
      *v19 = v21;
      *(_DWORD *)v6 = v14;
    }
    else
    {
      v19 = (LPVOID *)(v6 + 8);
    }
    v25 = v14;
    v26 = 2147483646;
    if ( (unsigned __int64)v14 - 1 > 0x7FFFFFFE )
    {
      v31 = 87;
    }
    else
    {
      v27 = *v19;
      v28 = (unsigned int)v25;
      v29 = *v19;
      do
      {
        if ( !*v29 )
          break;
        ++v29;
        --v28;
      }
      while ( v28 );
      v30 = 0;
      v31 = 87;
      v32 = 87;
      if ( v28 )
      {
        v32 = 0;
        v33 = v25 - v28;
      }
      else
      {
        v33 = 0;
      }
      if ( v28 )
      {
        v35 = v25 == v33;
        v34 = v25 - v33;
        if ( v35 || v34 == 1 )
        {
          if ( *v12 )
          {
            if ( v27 )
LABEL_46:
              v31 = 122;
            v27[v33] = 0;
            goto LABEL_74;
          }
        }
        else
        {
          v36 = &v27[v33];
          while ( v26 )
          {
            if ( !*v12 )
            {
              if ( !v34 )
              {
LABEL_45:
                *(v36 - 1) = 0;
                goto LABEL_46;
              }
              break;
            }
            *v36++ = *v12++;
            --v26;
            if ( !--v34 )
              goto LABEL_45;
          }
          *v36 = 0;
        }
        *v13 += v9;
        v37 = 0;
        if ( (a5 & 0x30) != 0 )
        {
          v38 = 1;
          LOBYTE(v37) = (a5 & 0x10000) != 0;
          v39 = v37;
          if ( (a5 & 0x10000) == 0 )
          {
LABEL_66:
            if ( (unsigned int)StrBufCatA(v6, a3)
              && (!v39 || (!v37 || (unsigned int)StrBufCatA(v6, v47)) && (unsigned int)StrBufCatA(v6, pszDest)) )
            {
              inserted = TextLogInsertString(a1, a2, *v19);
LABEL_77:
              LastError = inserted;
              goto LABEL_78;
            }
LABEL_76:
            inserted = GetLastError();
            goto LABEL_77;
          }
        }
        else
        {
          v39 = 0;
          v38 = 0;
          if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 12LL) & 0x8000000) != 0 )
          {
            v30 = 1;
          }
          else
          {
            if ( (a5 & 0x10000) == 0 )
              goto LABEL_65;
            v39 = 1;
          }
        }
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        v40 = StringCchPrintfA(
                pszDest,
                0x14u,
                " %02d:%02d:%02d.%03d",
                SystemTime.wHour,
                SystemTime.wMinute,
                SystemTime.wSecond,
                SystemTime.wMilliseconds);
        if ( v40 < 0
          || v37
          && (v40 = StringCchPrintfA(
                      v47,
                      0x14u,
                      " %04d/%02d/%02d",
                      SystemTime.wYear,
                      SystemTime.wMonth,
                      SystemTime.wDay),
              v40 < 0) )
        {
          LastError = (unsigned __int16)v40;
          goto LABEL_78;
        }
        if ( v30 && (v37 && !(unsigned int)StrBufCatA(v6, v47) || !(unsigned int)StrBufCatA(v6, pszDest)) )
          goto LABEL_76;
        if ( v38 )
          goto LABEL_66;
LABEL_65:
        if ( !(unsigned int)StrBufCatA(v6, " ") )
          goto LABEL_76;
        goto LABEL_66;
      }
      v31 = v32;
    }
LABEL_74:
    v22 = v31;
    goto LABEL_75;
  }
  StrBufDestroyA(0);
  LastError = GetLastError();
  v6 = 0;
LABEL_78:
  StrBufDestroyA(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000df10  push    rbx
0x18000df12  push    rbp
0x18000df13  push    r15
0x18000df15  sub     rsp, 0C0h
0x18000df1c  mov     rax, cs:__security_cookie
0x18000df23  xor     rax, rsp
0x18000df26  mov     [rsp+0D8h+var_40], rax
0x18000df2e  mov     [rsp+0D8h+var_90], rcx
0x18000df33  xor     ecx, ecx
0x18000df35  mov     [rsp+0D8h+var_88], r8
0x18000df3a  mov     [rsp+0D8h+var_98], edx
0x18000df3e  call    pStrBufCreate
0x18000df43  mov     r15, rax
0x18000df46  test    rax, rax
0x18000df49  jnz     short loc_18000DF64
0x18000df4b  xor     ecx, ecx; lpMem
0x18000df4d  call    StrBufDestroyA
0x18000df52  call    cs:__imp_GetLastError
0x18000df58  xor     ebp, ebp
0x18000df5a  mov     ebx, eax
0x18000df5c  mov     r15d, ebp
0x18000df5f  jmp     loc_18000E351
0x18000df64  mov     rcx, [rax+8]
0x18000df68  mov     [rsp+0D8h+var_20], rdi
0x18000df70  mov     [rsp+0D8h+var_28], r12
0x18000df78  mov     [rsp+0D8h+var_38], r14
0x18000df80  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000df87  mov     rax, r14
0x18000df8a  nop     word ptr [rax+rax+00h]
0x18000df90  inc     rax
0x18000df93  cmp     byte ptr [rcx+rax], 0
0x18000df97  jnz     short loc_18000DF90
0x18000df99  mov     r12d, [rsp+0D8h+arg_20]
0x18000dfa1  mov     [r15+4], eax
0x18000dfa5  mov     eax, r12d
0x18000dfa8  and     eax, 0Fh
0x18000dfab  cmp     eax, 1
0x18000dfae  jnz     short loc_18000DFB9
0x18000dfb0  lea     rbx, asc_18001E1B0; "!!!  "
0x18000dfb7  jmp     short loc_18000E000
0x18000dfb9  cmp     eax, 2
0x18000dfbc  jnz     short loc_18000DFC7
0x18000dfbe  lea     rbx, asc_18001E1B8; "!    "
0x18000dfc5  jmp     short loc_18000E000
0x18000dfc7  test    r12b, 10h
0x18000dfcb  jz      short loc_18000DFD6
0x18000dfcd  lea     rbx, asc_18001CA4C; ">>>  "
0x18000dfd4  jmp     short loc_18000E000
0x18000dfd6  test    r12b, 20h
0x18000dfda  jz      short loc_18000DFE5
0x18000dfdc  lea     rbx, asc_18001E1C0; "<<<  "
0x18000dfe3  jmp     short loc_18000E000
0x18000dfe5  test    r12b, 40h
0x18000dfe9  lea     rbx, asc_18001E1C8; "   . "
0x18000dff0  lea     rax, asc_18001E1D0; "     "
0x18000dff7  cmovz   rbx, rax
0x18000dffb  nop     dword ptr [rax+rax+00h]
0x18000e000  inc     r14
0x18000e003  cmp     byte ptr [rbx+r14], 0
0x18000e008  jnz     short loc_18000E000
0x18000e00a  mov     ecx, [r15+4]
0x18000e00e  lea     r11, [r15+4]
0x18000e012  mov     edi, [r15]
0x18000e015  inc     ecx
0x18000e017  add     ecx, r14d
0x18000e01a  mov     [rsp+0D8h+arg_18], rsi
0x18000e022  mov     eax, 1
0x18000e027  mov     [rsp+0D8h+var_30], r13
0x18000e02f  cmovnz  eax, ecx
0x18000e032  mov     qword ptr [rsp+0D8h+SystemTime.wYear], r11
0x18000e037  cmp     edi, eax
0x18000e039  jb      short loc_18000E044
0x18000e03b  lea     r13, [r15+8]
0x18000e03f  jmp     loc_18000E0E4
0x18000e044  mov     rcx, cs:hHeap; hHeap
0x18000e04b  lea     edi, [rax+3FFh]
0x18000e051  and     edi, 0FFFFFC00h
0x18000e057  xor     edx, edx; dwFlags
0x18000e059  add     edi, 400h
0x18000e05f  mov     r8d, edi; dwBytes
0x18000e062  mov     ebp, edi
0x18000e064  call    cs:__imp_HeapAlloc
0x18000e06a  mov     rsi, rax
0x18000e06d  test    rax, rax
0x18000e070  jnz     short loc_18000E07C
0x18000e072  mov     ecx, 8
0x18000e077  jmp     loc_18000E31B
0x18000e07c  mov     r8, rbp; Size
0x18000e07f  xor     edx, edx; Val
0x18000e081  mov     rcx, rsi; void *
0x18000e084  call    memset_0
0x18000e089  mov     r8, [r15+8]; pszSrc
0x18000e08d  lea     r13, [r15+8]
0x18000e091  test    r8, r8
0x18000e094  jz      short loc_18000E0D8
0x18000e096  mov     rdx, rbp; cchDest
0x18000e099  mov     rcx, rsi; pszDest
0x18000e09c  call    StringCchCopyA
0x18000e0a1  test    eax, eax
0x18000e0a3  jns     short loc_18000E0C5
0x18000e0a5  movzx   ecx, ax; dwErrCode
0x18000e0a8  call    cs:__imp_SetLastError
0x18000e0ae  mov     rcx, cs:hHeap; hHeap
0x18000e0b5  mov     r8, rsi; lpMem
0x18000e0b8  xor     edx, edx; dwFlags
0x18000e0ba  call    cs:__imp_HeapFree
0x18000e0c0  jmp     loc_18000E321
0x18000e0c5  mov     r8, [r13+0]; lpMem
0x18000e0c9  xor     edx, edx; dwFlags
0x18000e0cb  mov     rcx, cs:hHeap; hHeap
0x18000e0d2  call    cs:__imp_HeapFree
0x18000e0d8  mov     r11, qword ptr [rsp+0D8h+SystemTime.wYear]
0x18000e0dd  mov     [r13+0], rsi
0x18000e0e1  mov     [r15], edi
0x18000e0e4  mov     edx, edi
0x18000e0e6  mov     ecx, 7FFFFFFEh
0x18000e0eb  lea     rax, [rdx-1]
0x18000e0ef  cmp     rax, rcx
0x18000e0f2  ja      loc_18000E313
0x18000e0f8  mov     rdi, [r13+0]
0x18000e0fc  mov     r8d, edx
0x18000e0ff  mov     rax, rdi
0x18000e102  cmp     byte ptr [rax], 0
0x18000e105  jz      short loc_18000E110
0x18000e107  inc     rax
0x18000e10a  sub     r8, 1
0x18000e10e  jnz     short loc_18000E102
0x18000e110  xor     ebp, ebp
0x18000e112  mov     eax, 80070057h
0x18000e117  test    r8, r8
0x18000e11a  mov     r9d, eax
0x18000e11d  cmovnz  r9d, ebp
0x18000e121  jz      short loc_18000E12B
0x18000e123  mov     r10, rdx
0x18000e126  sub     r10, r8
0x18000e129  jmp     short loc_18000E12E
0x18000e12b  mov     r10, rbp
0x18000e12e  test    r8, r8
0x18000e131  jz      loc_18000E30E
0x18000e137  sub     rdx, r10
0x18000e13a  cmp     rdx, 1
0x18000e13e  ja      short loc_18000E14C
0x18000e140  cmp     [rbx], bpl
0x18000e143  jz      short loc_18000E18E
0x18000e145  test    rdi, rdi
0x18000e148  jnz     short loc_18000E179
0x18000e14a  jmp     short loc_18000E17E
0x18000e14c  lea     r8, [r10+rdi]
0x18000e150  test    rcx, rcx
0x18000e153  jz      short loc_18000E18B
0x18000e155  movzx   eax, byte ptr [rbx]
0x18000e158  test    al, al
0x18000e15a  jz      short loc_18000E170
0x18000e15c  mov     [r8], al
0x18000e15f  inc     rbx
0x18000e162  inc     r8
0x18000e165  dec     rcx
0x18000e168  sub     rdx, 1
0x18000e16c  jnz     short loc_18000E150
0x18000e16e  jmp     short loc_18000E175
0x18000e170  test    rdx, rdx
0x18000e173  jnz     short loc_18000E18B
0x18000e175  mov     [r8-1], bpl
0x18000e179  mov     eax, 8007007Ah
0x18000e17e  mov     [r10+rdi], bpl
0x18000e182  test    eax, eax
0x18000e184  jns     short loc_18000E18E
0x18000e186  jmp     loc_18000E318
0x18000e18b  mov     [r8], bpl
0x18000e18e  add     [r11], r14d
0x18000e191  mov     ebx, ebp
0x18000e193  mov     r14, [rsp+0D8h+var_90]
0x18000e198  test    r12b, 30h
0x18000e19c  jz      short loc_18000E1BF
0x18000e19e  test    [rsp+0D8h+arg_20], 10000h
0x18000e1a9  mov     esi, 1
0x18000e1ae  setnz   bl
0x18000e1b1  mov     edi, ebx
0x18000e1b3  bt      r12d, 10h
0x18000e1b8  jb      short loc_18000E1E7
0x18000e1ba  jmp     loc_18000E2BE
0x18000e1bf  mov     rax, [r14+20h]
0x18000e1c3  mov     edi, ebp
0x18000e1c5  mov     esi, ebp
0x18000e1c7  test    dword ptr [rax+0Ch], 8000000h
0x18000e1ce  jz      short loc_18000E1D7
0x18000e1d0  mov     ebp, 1
0x18000e1d5  jmp     short loc_18000E1E7
0x18000e1d7  bt      r12d, 10h
0x18000e1dc  jnb     loc_18000E2AB
0x18000e1e2  mov     edi, 1
0x18000e1e7  xorps   xmm0, xmm0
0x18000e1ea  lea     rcx, [rsp+0D8h+SystemTime]; lpSystemTime
0x18000e1ef  movups  xmmword ptr [rsp+0D8h+SystemTime.wYear], xmm0
0x18000e1f4  call    cs:__imp_GetLocalTime
0x18000e1fa  movzx   ecx, [rsp+0D8h+SystemTime.wSecond]
0x18000e1ff  lea     r8, pszFormat; " %02d:%02d:%02d.%03d"
0x18000e206  movzx   edx, [rsp+0D8h+SystemTime.wMinute]
0x18000e20b  movzx   eax, [rsp+0D8h+SystemTime.wMilliseconds]
0x18000e210  movzx   r9d, [rsp+0D8h+SystemTime.wHour]
0x18000e216  mov     [rsp+0D8h+var_A8], eax
0x18000e21a  mov     [rsp+0D8h+var_B0], ecx
0x18000e21e  lea     rcx, [rsp+0D8h+pszDest]; pszDest
0x18000e226  mov     [rsp+0D8h+var_B8], edx
0x18000e22a  mov     edx, 14h; cchDest
0x18000e22f  call    StringCchPrintfA
0x18000e234  test    eax, eax
0x18000e236  js      short loc_18000E26E
0x18000e238  test    ebx, ebx
0x18000e23a  jz      short loc_18000E276
0x18000e23c  movzx   ecx, [rsp+0D8h+SystemTime.wMonth]
0x18000e241  lea     r8, a04d02d02d; " %04d/%02d/%02d"
0x18000e248  movzx   eax, [rsp+0D8h+SystemTime.wDay]
0x18000e24d  mov     edx, 14h; cchDest
0x18000e252  movzx   r9d, [rsp+0D8h+SystemTime.wYear]
0x18000e258  mov     [rsp+0D8h+var_B0], eax
0x18000e25c  mov     [rsp+0D8h+var_B8], ecx
0x18000e260  lea     rcx, [rsp+0D8h+var_70]; pszDest
0x18000e265  call    StringCchPrintfA
0x18000e26a  test    eax, eax
0x18000e26c  jns     short loc_18000E276
0x18000e26e  movzx   ebx, ax
0x18000e271  jmp     loc_18000E329
0x18000e276  test    ebp, ebp
0x18000e278  jz      short loc_18000E2A7
0x18000e27a  test    ebx, ebx
0x18000e27c  jz      short loc_18000E293
0x18000e27e  lea     rdx, [rsp+0D8h+var_70]
0x18000e283  mov     rcx, r15
0x18000e286  call    StrBufCatA
0x18000e28b  test    eax, eax
0x18000e28d  jz      loc_18000E321
0x18000e293  lea     rdx, [rsp+0D8h+pszDest]
0x18000e29b  mov     rcx, r15
0x18000e29e  call    StrBufCatA
0x18000e2a3  test    eax, eax
0x18000e2a5  jz      short loc_18000E321
0x18000e2a7  test    esi, esi
0x18000e2a9  jnz     short loc_18000E2BE
0x18000e2ab  lea     rdx, asc_18001E200; " "
0x18000e2b2  mov     rcx, r15
0x18000e2b5  call    StrBufCatA
0x18000e2ba  test    eax, eax
0x18000e2bc  jz      short loc_18000E321
0x18000e2be  mov     rdx, [rsp+0D8h+var_88]
0x18000e2c3  mov     rcx, r15
0x18000e2c6  call    StrBufCatA
0x18000e2cb  test    eax, eax
0x18000e2cd  jz      short loc_18000E321
0x18000e2cf  test    edi, edi
0x18000e2d1  jz      short loc_18000E2FC
0x18000e2d3  test    ebx, ebx
0x18000e2d5  jz      short loc_18000E2E8
0x18000e2d7  lea     rdx, [rsp+0D8h+var_70]
0x18000e2dc  mov     rcx, r15
0x18000e2df  call    StrBufCatA
0x18000e2e4  test    eax, eax
0x18000e2e6  jz      short loc_18000E321
0x18000e2e8  lea     rdx, [rsp+0D8h+pszDest]
0x18000e2f0  mov     rcx, r15
0x18000e2f3  call    StrBufCatA
0x18000e2f8  test    eax, eax
0x18000e2fa  jz      short loc_18000E321
0x18000e2fc  mov     r8, [r13+0]
0x18000e300  mov     rcx, r14
0x18000e303  mov     edx, [rsp+0D8h+var_98]
0x18000e307  call    TextLogInsertString
0x18000e30c  jmp     short loc_18000E327
0x18000e30e  mov     eax, r9d
0x18000e311  jmp     short loc_18000E318
0x18000e313  mov     eax, 80070057h
0x18000e318  movzx   ecx, ax; dwErrCode
0x18000e31b  call    cs:__imp_SetLastError
0x18000e321  call    cs:__imp_GetLastError
0x18000e327  mov     ebx, eax
0x18000e329  mov     r13, [rsp+0D8h+var_30]
0x18000e331  mov     rsi, [rsp+0D8h+arg_18]
0x18000e339  mov     rdi, [rsp+0D8h+var_20]
0x18000e341  mov     r12, [rsp+0D8h+var_28]
0x18000e349  mov     r14, [rsp+0D8h+var_38]
0x18000e351  mov     rcx, r15; lpMem
0x18000e354  call    StrBufDestroyA
0x18000e359  mov     eax, ebx
0x18000e35b  mov     rcx, [rsp+0D8h+var_40]
0x18000e363  xor     rcx, rsp; StackCookie
0x18000e366  call    __security_check_cookie
0x18000e36b  add     rsp, 0C0h
0x18000e372  pop     r15
0x18000e374  pop     rbp
0x18000e375  pop     rbx
0x18000e376  retn
```
