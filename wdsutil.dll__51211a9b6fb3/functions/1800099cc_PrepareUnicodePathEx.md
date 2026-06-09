# PrepareUnicodePathEx

- ea: `0x1800099cc`
- end: `0x180009fbb`
- name: `PrepareUnicodePathEx`
- size: `1519`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180009738`

## callees

- `0x180008b28`
- `0x180008bf4`
- `0x18000980c`
- `0x1800098f4`
- `0x1800099cc`
- `0x1800319c6`
- `0x1800319f0`

## import_xrefs

- `msvcrt!wcschr` at `0x180009b74`
- `msvcrt!wcschr` at `0x180009b92`
- `msvcrt!wcschr` at `0x180009b74`
- `msvcrt!wcschr` at `0x180009b92`
- `msvcrt!_wcsnicmp` at `0x180009ac6`
- `msvcrt!_wcsnicmp` at `0x180009b17`
- `msvcrt!_wcsnicmp` at `0x180009b4f`
- `msvcrt!_wcsnicmp` at `0x180009ac6`
- `msvcrt!_wcsnicmp` at `0x180009b17`
- `msvcrt!_wcsnicmp` at `0x180009b4f`
- `KERNEL32!GetLastError` at `0x180009a3c`
- `KERNEL32!GetLastError` at `0x180009a5c`
- `KERNEL32!GetLastError` at `0x180009e7e`
- `KERNEL32!GetLastError` at `0x180009e9a`
- `KERNEL32!GetLastError` at `0x180009f09`
- `KERNEL32!GetLastError` at `0x180009f25`
- `KERNEL32!GetLastError` at `0x180009a3c`
- `KERNEL32!GetLastError` at `0x180009a5c`
- `KERNEL32!GetLastError` at `0x180009e7e`
- `KERNEL32!GetLastError` at `0x180009e9a`
- `KERNEL32!GetLastError` at `0x180009f09`
- `KERNEL32!GetLastError` at `0x180009f25`
- `KERNEL32!HeapFree` at `0x180009efb`
- `KERNEL32!HeapFree` at `0x180009f67`
- `KERNEL32!HeapFree` at `0x180009efb`
- `KERNEL32!HeapFree` at `0x180009f67`
- `KERNEL32!GetProcessHeap` at `0x180009ee7`
- `KERNEL32!GetProcessHeap` at `0x180009f53`
- `KERNEL32!GetProcessHeap` at `0x180009ee7`
- `KERNEL32!GetProcessHeap` at `0x180009f53`
- `KERNEL32!SetLastError` at `0x180009f76`
- `KERNEL32!SetLastError` at `0x180009f8c`
- `KERNEL32!SetLastError` at `0x180009f76`
- `KERNEL32!SetLastError` at `0x180009f8c`
- `ntdll!RtlAllocateHeap` at `0x180009c44`
- `ntdll!RtlAllocateHeap` at `0x180009d94`
- `ntdll!RtlAllocateHeap` at `0x180009c44`
- `ntdll!RtlAllocateHeap` at `0x180009d94`
- `ntdll!RtlFreeHeap` at `0x180009cfb`
- `ntdll!RtlFreeHeap` at `0x180009e60`
- `ntdll!RtlFreeHeap` at `0x180009cfb`
- `ntdll!RtlFreeHeap` at `0x180009e60`

## pseudocode

```c
wchar_t *__fastcall PrepareUnicodePathEx(unsigned __int16 *a1)
{
  int v1; // r12d
  unsigned __int16 *v2; // r15
  WCHAR *v3; // r14
  signed int v4; // ebx
  signed int LastError; // eax
  bool v6; // sf
  signed int v7; // eax
  __int64 v8; // rsi
  unsigned __int64 v9; // rax
  wchar_t *Heap; // rdi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  BOOL v13; // ecx
  wchar_t *v14; // rax
  int v15; // eax
  const wchar_t *v16; // rbx
  __int64 v17; // r15
  bool v18; // zf
  HRESULT v19; // eax
  unsigned __int16 v20; // r15
  HRESULT v21; // eax
  HRESULT v22; // eax
  ULONG v23; // ecx
  const wchar_t *v24; // r13
  int v25; // r15d
  __int64 v26; // rbx
  __int64 v27; // rcx
  size_t v28; // r12
  HRESULT v29; // eax
  unsigned __int16 v30; // bx
  HRESULT v31; // eax
  HRESULT v32; // eax
  signed int v33; // eax
  bool v34; // sf
  signed int v35; // eax
  HANDLE ProcessHeap; // rax
  signed int v37; // eax
  bool v38; // sf
  signed int v39; // eax
  HANDLE v40; // rax
  DWORD v42; // [rsp+30h] [rbp-39h]
  DWORD v43; // [rsp+30h] [rbp-39h]
  DWORD v44; // [rsp+30h] [rbp-39h]
  size_t cchDest; // [rsp+40h] [rbp-29h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 *v47; // [rsp+50h] [rbp-19h]
  wchar_t String2[4]; // [rsp+58h] [rbp-11h] BYREF
  wchar_t pszSrc[8]; // [rsp+60h] [rbp-9h] BYREF

  v1 = 0;
  v47 = a1;
  v2 = a1;
  wcscpy(String2, L"\\\\?");
  wcscpy(pszSrc, L"\\\\?\\UNC");
  if ( !a1 || !*a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v3 = FormFullPathName(a1);
  if ( v3 )
  {
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError > 0 )
      v6 = 1;
    if ( !v6 )
      goto LABEL_92;
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_93;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v3[v9] );
  if ( v9 < 0x104 )
  {
LABEL_81:
    Heap = (wchar_t *)StrDupe(v2);
    if ( Heap )
    {
      LOWORD(v4) = 0;
      goto LABEL_94;
    }
    v37 = GetLastError();
    v38 = v37 < 0;
    if ( v37 > 0 )
      v38 = 1;
    if ( v38 )
    {
      v39 = GetLastError();
      v4 = v39;
      if ( v39 > 0 )
        v4 = (unsigned __int16)v39 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_94;
      goto LABEL_93;
    }
LABEL_92:
    LOWORD(v4) = 16389;
    goto LABEL_93;
  }
  Heap = 0;
  if ( wcsncmp_0(v3, String2, 3u) && _wcsnicmp(v3, pszSrc, 7u) )
  {
    if ( !v3 )
    {
      LOWORD(v4) = 87;
LABEL_93:
      Heap = 0;
      goto LABEL_94;
    }
    v11 = -1;
    do
      ++v11;
    while ( v3[v11] );
    if ( v11 < 2 || _wcsnicmp(v3, L"\\\\", 2u) )
    {
      v4 = 0;
    }
    else
    {
      v12 = -1;
      do
        ++v12;
      while ( v3[v12] );
      v13 = v12 >= 8 && _wcsnicmp(v3, L"\\\\?\\UNC\\", 8u) == 0;
      v14 = wcschr((WCHAR *)((char *)v3 + (v13 ? 16LL : 4LL)), 0x5Cu);
      if ( v14 )
      {
        wcschr(v14 + 1, 0x5Cu);
        v15 = 1;
        v4 = 0;
        goto LABEL_32;
      }
      v4 = -2147024883;
    }
    v15 = 0;
LABEL_32:
    if ( v4 < 0 )
      goto LABEL_93;
    cchDest = 0;
    if ( v15 == 1 )
    {
      v16 = v3 + 1;
      *(_QWORD *)String2 = 0;
      if ( v3 == (WCHAR *)-2LL )
      {
        NtCurrentTeb()->LastErrorValue = 87;
LABEL_72:
        Heap = 0;
        v33 = GetLastError();
        v34 = v33 < 0;
        if ( v33 > 0 )
          v34 = 1;
        if ( v34 )
        {
          v35 = GetLastError();
          v4 = v35;
          if ( v35 > 0 )
            v4 = (unsigned __int16)v35 | 0x80070000;
        }
        else
        {
          v4 = -2147467259;
        }
        goto LABEL_78;
      }
      v17 = -1;
      do
        ++v17;
      while ( pszSrc[v17] );
      do
        ++v8;
      while ( v16[v8] );
      if ( (_DWORD)v17 )
      {
        if ( pszSrc[(unsigned int)(v17 - 1)] == 92 )
        {
          v18 = *v16 == 92;
          if ( *v16 == 92 )
          {
            LODWORD(v8) = v8 - 1;
            v18 = *v16 == 92;
          }
          if ( !v18 )
            v16 = v3;
          ++v16;
        }
        else if ( *v16 != 92 )
        {
          v1 = 1;
        }
      }
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v17 + v1 + v8 + 1));
      if ( Heap )
      {
        v19 = StringCchCopyNExW(
                Heap,
                (unsigned int)(v17 + v1 + v8 + 1),
                pszSrc,
                (unsigned int)v17,
                (STRSAFE_LPWSTR *)String2,
                &cchDest,
                v42);
        v20 = v19;
        if ( v19 < 0
          || v1
          && (v21 = StringCchCopyNExW(
                      *(STRSAFE_LPWSTR *)String2,
                      cchDest,
                      L"\\",
                      1u,
                      (STRSAFE_LPWSTR *)String2,
                      &cchDest,
                      v43),
              v20 = v21,
              v21 < 0)
          || (v22 = StringCchCopyNW(*(STRSAFE_LPWSTR *)String2, cchDest, v16, (unsigned int)v8), v20 = v22, v22 < 0) )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v23 = v20;
LABEL_71:
          NtCurrentTeb()->LastErrorValue = v23;
          goto LABEL_72;
        }
        goto LABEL_69;
      }
    }
    else
    {
      pszDest = 0;
      v24 = v3;
      v25 = 0;
      v26 = -1;
      do
        ++v26;
      while ( String2[v26] );
      do
        ++v8;
      while ( v3[v8] );
      if ( (_DWORD)v26 )
      {
        if ( String2[(unsigned int)(v26 - 1)] == 92 )
        {
          if ( *v3 == 92 )
          {
            v24 = v3 + 1;
            LODWORD(v8) = v8 - 1;
          }
        }
        else if ( *v3 != 92 )
        {
          v25 = 1;
        }
      }
      v27 = (unsigned int)(v26 + v25 + v8 + 1);
      v28 = (unsigned int)v27;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v27);
      if ( Heap )
      {
        v29 = StringCchCopyNExW(Heap, v28, String2, (unsigned int)v26, &pszDest, &cchDest, v42);
        v30 = v29;
        if ( v29 < 0
          || v25 && (v31 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v44), v30 = v31, v31 < 0)
          || (v32 = StringCchCopyNW(pszDest, cchDest, v24, (unsigned int)v8), v30 = v32, v32 < 0) )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          v23 = v30;
          goto LABEL_71;
        }
LABEL_69:
        v4 = 0;
        NtCurrentTeb()->LastErrorValue = 0;
LABEL_78:
        v2 = v47;
        goto LABEL_79;
      }
    }
    NtCurrentTeb()->LastErrorValue = 8;
    goto LABEL_72;
  }
LABEL_79:
  if ( v4 < 0 )
  {
    if ( Heap )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, Heap);
    }
    goto LABEL_93;
  }
  if ( !Heap )
    goto LABEL_81;
LABEL_94:
  if ( v3 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v3);
  }
  SetLastError((unsigned __int16)v4);
  return Heap;
}

```

## disassembly

```asm
0x1800099cc  push    rbp
0x1800099ce  push    rbx
0x1800099cf  push    rsi
0x1800099d0  push    rdi
0x1800099d1  push    r12
0x1800099d3  push    r13
0x1800099d5  push    r14
0x1800099d7  push    r15
0x1800099d9  lea     rbp, [rsp-1Fh]
0x1800099de  sub     rsp, 88h
0x1800099e5  mov     rax, cs:__security_cookie
0x1800099ec  xor     rax, rsp
0x1800099ef  mov     [rbp+57h+var_50], rax
0x1800099f3  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC"
0x1800099fa  xor     r12d, r12d
0x1800099fd  mov     [rbp+57h+var_70], rcx
0x180009a01  mov     rax, 3F005C005Ch
0x180009a0b  mov     r15, rcx
0x180009a0e  mov     qword ptr [rbp+57h+String2], rax
0x180009a12  movdqu  xmmword ptr [rbp+57h+pszSrc], xmm0
0x180009a17  test    rcx, rcx
0x180009a1a  jz      loc_180009F87
0x180009a20  cmp     r12w, [rcx]
0x180009a24  jz      loc_180009F87
0x180009a2a  call    FormFullPathName
0x180009a2f  mov     r14, rax
0x180009a32  test    rax, rax
0x180009a35  jz      short loc_180009A3C
0x180009a37  mov     ebx, r12d
0x180009a3a  jmp     short loc_180009A7F
0x180009a3c  call    cs:__imp_GetLastError
0x180009a43  nop     dword ptr [rax+rax+00h]
0x180009a48  test    eax, eax
0x180009a4a  jle     short loc_180009A56
0x180009a4c  movzx   eax, ax
0x180009a4f  or      eax, 80070000h
0x180009a54  test    eax, eax
0x180009a56  jns     loc_180009F46
0x180009a5c  call    cs:__imp_GetLastError
0x180009a63  nop     dword ptr [rax+rax+00h]
0x180009a68  mov     ebx, eax
0x180009a6a  test    eax, eax
0x180009a6c  jle     short loc_180009A77
0x180009a6e  movzx   ebx, ax
0x180009a71  or      ebx, 80070000h
0x180009a77  test    ebx, ebx
0x180009a79  js      loc_180009F4B
0x180009a7f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009a83  mov     rax, rsi
0x180009a86  inc     rax
0x180009a89  cmp     [r14+rax*2], r12w
0x180009a8e  jnz     short loc_180009A86
0x180009a90  cmp     rax, 104h
0x180009a96  jb      loc_180009ECD
0x180009a9c  mov     r8d, 3; MaxCount
0x180009aa2  lea     rdx, [rbp+57h+String2]; String2
0x180009aa6  mov     rcx, r14; String1
0x180009aa9  mov     rdi, r12
0x180009aac  call    wcsncmp_0
0x180009ab1  test    eax, eax
0x180009ab3  jz      loc_180009EC0
0x180009ab9  mov     r8d, 7; MaxCount
0x180009abf  lea     rdx, [rbp+57h+pszSrc]; String2
0x180009ac3  mov     rcx, r14; String1
0x180009ac6  call    cs:__imp__wcsnicmp
0x180009acd  nop     dword ptr [rax+rax+00h]
0x180009ad2  test    eax, eax
0x180009ad4  jz      loc_180009EC0
0x180009ada  test    r14, r14
0x180009add  jnz     short loc_180009AE9
0x180009adf  mov     ebx, 80070057h
0x180009ae4  jmp     loc_180009F4B
0x180009ae9  mov     rax, rsi
0x180009aec  inc     rax
0x180009aef  cmp     [r14+rax*2], r12w
0x180009af4  jnz     short loc_180009AEC
0x180009af6  mov     edi, 5Ch ; '\'
0x180009afb  lea     r13d, [rdi-5Bh]
0x180009aff  cmp     rax, 2
0x180009b03  jb      loc_180009BA6
0x180009b09  lea     r8d, [rdi-5Ah]; MaxCount
0x180009b0d  mov     rcx, r14; String1
0x180009b10  lea     rdx, String2; "\\\\"
0x180009b17  call    cs:__imp__wcsnicmp
0x180009b1e  nop     dword ptr [rax+rax+00h]
0x180009b23  test    eax, eax
0x180009b25  jnz     short loc_180009BA6
0x180009b27  mov     rax, rsi
0x180009b2a  inc     rax
0x180009b2d  cmp     [r14+rax*2], r12w
0x180009b32  jnz     short loc_180009B2A
0x180009b34  cmp     rax, 8
0x180009b38  jnb     short loc_180009B3F
0x180009b3a  mov     ecx, r12d
0x180009b3d  jmp     short loc_180009B63
0x180009b3f  mov     r8d, 8; MaxCount
0x180009b45  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180009b4c  mov     rcx, r14; String1
0x180009b4f  call    cs:__imp__wcsnicmp
0x180009b56  nop     dword ptr [rax+rax+00h]
0x180009b5b  test    eax, eax
0x180009b5d  mov     ecx, r12d
0x180009b60  setz    cl
0x180009b63  neg     ecx
0x180009b65  mov     edx, edi; Ch
0x180009b67  sbb     rcx, rcx
0x180009b6a  and     ecx, 0Ch
0x180009b6d  add     rcx, 4
0x180009b71  add     rcx, r14; Str
0x180009b74  call    cs:__imp_wcschr
0x180009b7b  nop     dword ptr [rax+rax+00h]
0x180009b80  test    rax, rax
0x180009b83  jnz     short loc_180009B8C
0x180009b85  mov     ebx, 8007000Dh
0x180009b8a  jmp     short loc_180009BA9
0x180009b8c  mov     edx, edi; Ch
0x180009b8e  lea     rcx, [rax+2]; Str
0x180009b92  call    cs:__imp_wcschr
0x180009b99  nop     dword ptr [rax+rax+00h]
0x180009b9e  mov     eax, r13d
0x180009ba1  mov     ebx, r12d
0x180009ba4  jmp     short loc_180009BAC
0x180009ba6  mov     ebx, r12d
0x180009ba9  mov     eax, r12d
0x180009bac  test    ebx, ebx
0x180009bae  js      loc_180009F4B
0x180009bb4  mov     [rbp+57h+cchDest], r12
0x180009bb8  cmp     eax, r13d
0x180009bbb  jnz     loc_180009D25
0x180009bc1  lea     rbx, [r14+2]
0x180009bc5  mov     qword ptr [rbp+57h+String2], r12
0x180009bc9  test    rbx, rbx
0x180009bcc  jz      loc_180009D10
0x180009bd2  lea     rax, [rbp+57h+pszSrc]
0x180009bd6  mov     r15, rsi
0x180009bd9  xor     edx, edx
0x180009bdb  inc     r15
0x180009bde  cmp     [rax+r15*2], dx
0x180009be3  jnz     short loc_180009BDB
0x180009be5  inc     rsi
0x180009be8  cmp     [rbx+rsi*2], dx
0x180009bec  jnz     short loc_180009BE5
0x180009bee  test    r15d, r15d
0x180009bf1  jz      short loc_180009C1E
0x180009bf3  lea     eax, [r15-1]
0x180009bf7  cmp     di, [rbp+rax*2+57h+pszSrc]
0x180009bfc  jnz     short loc_180009C12
0x180009bfe  cmp     di, [rbx]
0x180009c01  jnz     short loc_180009C08
0x180009c03  dec     esi
0x180009c05  cmp     di, [rbx]
0x180009c08  cmovnz  rbx, r14
0x180009c0c  add     rbx, 2
0x180009c10  jmp     short loc_180009C1E
0x180009c12  test    r15d, r15d
0x180009c15  jz      short loc_180009C1E
0x180009c17  cmp     di, [rbx]
0x180009c1a  cmovnz  r12d, r13d
0x180009c1e  lea     ecx, [rsi+1]
0x180009c21  mov     edx, 8; Flags
0x180009c26  add     ecx, r12d
0x180009c29  add     ecx, r15d
0x180009c2c  mov     r13d, ecx
0x180009c2f  lea     r8, ds:0[rcx*2]; Size
0x180009c37  mov     rcx, gs:60h
0x180009c40  mov     rcx, [rcx+30h]; HeapHandle
0x180009c44  call    cs:__imp_RtlAllocateHeap
0x180009c4b  nop     dword ptr [rax+rax+00h]
0x180009c50  mov     rdi, rax
0x180009c53  test    rax, rax
0x180009c56  jz      loc_180009DA8
0x180009c5c  lea     rax, [rbp+57h+cchDest]
0x180009c60  mov     r9d, r15d; cchToCopy
0x180009c63  mov     [rsp+0C0h+pcchRemaining], rax; pcchRemaining
0x180009c68  lea     r8, [rbp+57h+pszSrc]; pszSrc
0x180009c6c  lea     rax, [rbp+57h+String2]
0x180009c70  mov     edx, r13d; cchDest
0x180009c73  mov     rcx, rdi; pszDest
0x180009c76  mov     [rsp+0C0h+ppszDestEnd], rax; ppszDestEnd
0x180009c7b  call    StringCchCopyNExW
0x180009c80  mov     r15d, eax
0x180009c83  test    eax, eax
0x180009c85  js      short loc_180009CE6
0x180009c87  test    r12d, r12d
0x180009c8a  jz      short loc_180009CC4
0x180009c8c  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180009c90  lea     rax, [rbp+57h+cchDest]
0x180009c94  mov     rcx, qword ptr [rbp+57h+String2]; pszDest
0x180009c98  lea     r8, pszSrc; "\\"
0x180009c9f  mov     [rsp+0C0h+pcchRemaining], rax; pcchRemaining
0x180009ca4  mov     r9d, 1; cchToCopy
0x180009caa  lea     rax, [rbp+57h+String2]
0x180009cae  mov     [rsp+0C0h+ppszDestEnd], rax; ppszDestEnd
0x180009cb3  call    StringCchCopyNExW
0x180009cb8  xor     r12d, r12d
0x180009cbb  mov     r15d, eax
0x180009cbe  test    eax, eax
0x180009cc0  jns     short loc_180009CC7
0x180009cc2  jmp     short loc_180009CE9
0x180009cc4  xor     r12d, r12d
0x180009cc7  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180009ccb  mov     r8, rbx; pszSrc
0x180009cce  mov     rcx, qword ptr [rbp+57h+String2]; pszDest
0x180009cd2  mov     r9d, esi; cchToCopy
0x180009cd5  call    StringCchCopyNW
0x180009cda  mov     r15d, eax
0x180009cdd  test    eax, eax
0x180009cdf  js      short loc_180009CE9
0x180009ce1  jmp     loc_180009E3C
0x180009ce6  xor     r12d, r12d
0x180009ce9  mov     rcx, gs:60h
0x180009cf2  mov     r8, rdi; P
0x180009cf5  xor     edx, edx; Flags
0x180009cf7  mov     rcx, [rcx+30h]; HeapHandle
0x180009cfb  call    cs:__imp_RtlFreeHeap
0x180009d02  nop     dword ptr [rax+rax+00h]
0x180009d07  movzx   ecx, r15w
0x180009d0b  jmp     loc_180009E6F
0x180009d10  mov     rax, gs:30h
0x180009d19  mov     dword ptr [rax+68h], 57h ; 'W'
0x180009d20  jmp     loc_180009E7B
0x180009d25  mov     [rbp+57h+pszDest], r12
0x180009d29  lea     rax, [rbp+57h+String2]
0x180009d2d  mov     r13, r14
0x180009d30  mov     r15d, r12d
0x180009d33  mov     rbx, rsi
0x180009d36  inc     rbx
0x180009d39  cmp     [rax+rbx*2], r12w
0x180009d3e  jnz     short loc_180009D36
0x180009d40  inc     rsi
0x180009d43  cmp     [r14+rsi*2], r12w
0x180009d48  jnz     short loc_180009D40
0x180009d4a  test    ebx, ebx
0x180009d4c  jz      short loc_180009D73
0x180009d4e  lea     eax, [rbx-1]
0x180009d51  cmp     di, [rbp+rax*2+57h+String2]
0x180009d56  jnz     short loc_180009D66
0x180009d58  cmp     di, [r14]
0x180009d5c  jnz     short loc_180009D73
0x180009d5e  lea     r13, [r14+2]
0x180009d62  dec     esi
0x180009d64  jmp     short loc_180009D73
0x180009d66  cmp     di, [r14]
0x180009d6a  mov     eax, 1
0x180009d6f  cmovnz  r15d, eax
0x180009d73  lea     ecx, [rsi+1]
0x180009d76  mov     edx, 8; Flags
0x180009d7b  add     ecx, r15d
0x180009d7e  add     ecx, ebx
0x180009d80  mov     r12d, ecx
0x180009d83  lea     r8, [rcx+rcx]; Size
0x180009d87  mov     rcx, gs:60h
0x180009d90  mov     rcx, [rcx+30h]; HeapHandle
0x180009d94  call    cs:__imp_RtlAllocateHeap
0x180009d9b  nop     dword ptr [rax+rax+00h]
0x180009da0  mov     rdi, rax
0x180009da3  test    rax, rax
0x180009da6  jnz     short loc_180009DC0
0x180009da8  mov     rax, gs:30h
0x180009db1  xor     r12d, r12d
0x180009db4  mov     dword ptr [rax+68h], 8
0x180009dbb  jmp     loc_180009E7B
0x180009dc0  lea     rax, [rbp+57h+cchDest]
0x180009dc4  mov     r9d, ebx; cchToCopy
0x180009dc7  mov     [rsp+0C0h+pcchRemaining], rax; pcchRemaining
0x180009dcc  lea     r8, [rbp+57h+String2]; pszSrc
0x180009dd0  lea     rax, [rbp+57h+pszDest]
0x180009dd4  mov     rdx, r12; cchDest
0x180009dd7  mov     rcx, rdi; pszDest
0x180009dda  mov     [rsp+0C0h+ppszDestEnd], rax; ppszDestEnd
0x180009ddf  call    StringCchCopyNExW
0x180009de4  xor     r12d, r12d
0x180009de7  mov     ebx, eax
0x180009de9  test    eax, eax
0x180009deb  js      short loc_180009E4E
0x180009ded  test    r15d, r15d
0x180009df0  jz      short loc_180009E23
0x180009df2  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180009df6  lea     rax, [rbp+57h+cchDest]
0x180009dfa  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180009dfe  lea     r9d, [r12+1]; cchToCopy
0x180009e03  mov     [rsp+0C0h+pcchRemaining], rax; pcchRemaining
0x180009e08  lea     r8, pszSrc; "\\"
0x180009e0f  lea     rax, [rbp+57h+pszDest]
0x180009e13  mov     [rsp+0C0h+ppszDestEnd], rax; ppszDestEnd
0x180009e18  call    StringCchCopyNExW
0x180009e1d  mov     ebx, eax
0x180009e1f  test    eax, eax
0x180009e21  js      short loc_180009E4E
0x180009e23  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180009e27  mov     r8, r13; pszSrc
0x180009e2a  mov     rcx, [rbp+57h+pszDest]; pszDest
0x180009e2e  mov     r9d, esi; cchToCopy
0x180009e31  call    StringCchCopyNW
0x180009e36  mov     ebx, eax
0x180009e38  test    eax, eax
0x180009e3a  js      short loc_180009E4E
0x180009e3c  mov     rax, gs:30h
0x180009e45  mov     ebx, r12d
0x180009e48  mov     [rax+68h], r12d
  ... truncated ...
```
