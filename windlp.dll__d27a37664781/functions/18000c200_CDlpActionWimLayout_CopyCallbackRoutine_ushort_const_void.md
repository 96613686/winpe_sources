# CDlpActionWimLayout::CopyCallbackRoutine(ushort const *,void *)

- ea: `0x18000c200`
- end: `0x18000c4d0`
- name: `?CopyCallbackRoutine@CDlpActionWimLayout@@CA?AW4FILE_ENUM_ACTION@@PEBGPEAX@Z`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000200c`
- `0x18000b9a8`
- `0x18000c200`
- `0x18001fd60`
- `0x18003bbbc`
- `0x18003bc78`
- `0x18003d550`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c41c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c41c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000c27b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000c27b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c2c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c2f0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c31c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c2c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c2f0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c31c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c39b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c39b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c488`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c497`

## string_xrefs

- `0x18000c2d7`: `install.wim`
- `0x18000c303`: `install.esd`
- `0x18000c339`: `install*.swm`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionWimLayout::CopyCallbackRoutine(const WCHAR *a1, __int64 a2)
{
  const WCHAR *v3; // r15
  LPCWSTR v4; // rdi
  __int64 v6; // rbx
  LPWSTR v7; // r13
  __int64 v8; // rax
  void *v9; // r12
  const wchar_t *v10; // r15
  wchar_t *v11; // rax
  wchar_t *v12; // rsi
  const wchar_t *v13; // rax
  HANDLE ProcessHeap; // rax
  int v15; // eax
  DWORD FileAttributesW; // eax
  BOOL v17; // ebx
  unsigned int v18; // esi
  int v19; // ebx
  HANDLE v20; // rax
  int v21; // [rsp+30h] [rbp-D0h]
  LPWSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v24; // [rsp+48h] [rbp-B8h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = a1;
  v24 = a1;
  v4 = 0;
  lpFileName = 0;
  if ( !a1 )
    return 0;
  FilePart = 0;
  memset_0(Buffer, 0, 0x208u);
  v6 = -1;
  if ( GetFullPathNameW(v3, 0x104u, Buffer, &FilePart) && Buffer[0] && FilePart )
  {
    if ( CompareStringW(0x409u, 1u, FilePart, -1, L"boot.wim", -1) == 2
      || CompareStringW(0x409u, 1u, FilePart, -1, L"install.wim", -1) == 2
      || CompareStringW(0x409u, 1u, FilePart, -1, L"install.esd", -1) == 2 )
    {
LABEL_34:
      v18 = 1;
      goto LABEL_35;
    }
    v7 = FilePart;
    if ( FilePart )
    {
      v8 = StrDupe(L"install*.swm");
      v9 = (void *)v8;
      if ( v8 )
      {
        v21 = 0;
        v10 = (const wchar_t *)v8;
        while ( 1 )
        {
          v11 = wcschr_0(v10, 0x3Bu);
          v12 = v11;
          if ( v11 )
            *v11 = 0;
          if ( (unsigned int)WdsPathMatchSingleSpec(v7, v10) )
            break;
          v13 = v12 + 1;
          if ( !v12 )
            v13 = v10;
          v10 = v13;
          if ( !v12 )
            goto LABEL_20;
        }
        v21 = 1;
LABEL_20:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v9);
        if ( v21 )
          goto LABEL_34;
        v3 = v24;
      }
    }
  }
  if ( *(_DWORD *)(a2 + 828) && (unsigned int)StrStartsWithIC(v3, *(_QWORD *)(a2 + 720)) )
  {
    do
      ++v6;
    while ( *(_WORD *)(*(_QWORD *)(a2 + 720) + 2 * v6) );
    v15 = CMiscHelpersT<CEmptyType>::CombinePath(*(_QWORD *)(a2 + 728), &v3[v6 + 1], 0, &lpFileName);
    v4 = lpFileName;
    if ( v15 >= 0 )
    {
      FileAttributesW = GetFileAttributesW(lpFileName);
      v17 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v17 )
        goto LABEL_34;
    }
  }
  v18 = 0;
  v19 = 0;
  if ( *(_DWORD *)(a2 + 556) )
  {
    while ( !(unsigned int)StrStartsWithIC(v3, *(_QWORD *)(*(_QWORD *)(a2 + 560) + 8LL * v19)) )
    {
      if ( (unsigned int)++v19 >= *(_DWORD *)(a2 + 556) )
        goto LABEL_35;
    }
    goto LABEL_34;
  }
LABEL_35:
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v18;
}

```

## disassembly

```asm
0x18000c200  mov     [rsp-8+arg_10], rbx
0x18000c205  push    rbp
0x18000c206  push    rsi
0x18000c207  push    rdi
0x18000c208  push    r12
0x18000c20a  push    r13
0x18000c20c  push    r14
0x18000c20e  push    r15
0x18000c210  lea     rbp, [rsp-170h]
0x18000c218  sub     rsp, 270h
0x18000c21f  mov     rax, cs:__security_cookie
0x18000c226  xor     rax, rsp
0x18000c229  mov     [rbp+1A0h+var_40], rax
0x18000c230  mov     r14, rdx
0x18000c233  mov     r15, rcx
0x18000c236  mov     [rsp+2A0h+var_258], rcx
0x18000c23b  xor     r12d, r12d
0x18000c23e  mov     edi, r12d
0x18000c241  mov     [rsp+2A0h+lpFileName], r12
0x18000c246  test    rcx, rcx
0x18000c249  jnz     short loc_18000C252
0x18000c24b  xor     eax, eax
0x18000c24d  jmp     loc_18000C4A6
0x18000c252  mov     [rsp+2A0h+FilePart], r12
0x18000c257  xor     edx, edx; Val
0x18000c259  mov     r8d, 208h; Size
0x18000c25f  lea     rcx, [rsp+2A0h+Buffer]; void *
0x18000c264  call    memset_0
0x18000c269  lea     r9, [rsp+2A0h+FilePart]; lpFilePart
0x18000c26e  lea     r8, [rsp+2A0h+Buffer]; lpBuffer
0x18000c273  mov     edx, 104h; nBufferLength
0x18000c278  mov     rcx, r15; lpFileName
0x18000c27b  call    cs:__imp_GetFullPathNameW
0x18000c281  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c285  test    eax, eax
0x18000c287  jz      loc_18000C3C7
0x18000c28d  cmp     [rsp+2A0h+Buffer], r12w
0x18000c293  jz      loc_18000C3C7
0x18000c299  mov     r8, [rsp+2A0h+FilePart]; lpString1
0x18000c29e  test    r8, r8
0x18000c2a1  jz      loc_18000C3C7
0x18000c2a7  mov     [rsp+2A0h+cchCount2], ebx; cchCount2
0x18000c2ab  lea     rax, String2; "boot.wim"
0x18000c2b2  mov     [rsp+2A0h+lpString2], rax; lpString2
0x18000c2b7  mov     r9d, ebx; cchCount1
0x18000c2ba  lea     edx, [rbx+2]; dwCmpFlags
0x18000c2bd  mov     esi, 409h
0x18000c2c2  mov     ecx, esi; Locale
0x18000c2c4  call    cs:__imp_CompareStringW
0x18000c2ca  cmp     eax, 2
0x18000c2cd  jz      loc_18000C47E
0x18000c2d3  mov     [rsp+2A0h+cchCount2], ebx; cchCount2
0x18000c2d7  lea     rax, aInstallWim; "install.wim"
0x18000c2de  mov     [rsp+2A0h+lpString2], rax; lpString2
0x18000c2e3  mov     r9d, ebx; cchCount1
0x18000c2e6  mov     r8, [rsp+2A0h+FilePart]; lpString1
0x18000c2eb  lea     edx, [rbx+2]; dwCmpFlags
0x18000c2ee  mov     ecx, esi; Locale
0x18000c2f0  call    cs:__imp_CompareStringW
0x18000c2f6  cmp     eax, 2
0x18000c2f9  jz      loc_18000C47E
0x18000c2ff  mov     [rsp+2A0h+cchCount2], ebx; cchCount2
0x18000c303  lea     rax, aInstallEsd; "install.esd"
0x18000c30a  mov     [rsp+2A0h+lpString2], rax; lpString2
0x18000c30f  mov     r9d, ebx; cchCount1
0x18000c312  mov     r8, [rsp+2A0h+FilePart]; lpString1
0x18000c317  lea     edx, [rbx+2]; dwCmpFlags
0x18000c31a  mov     ecx, esi; Locale
0x18000c31c  call    cs:__imp_CompareStringW
0x18000c322  cmp     eax, 2
0x18000c325  jz      loc_18000C47E
0x18000c32b  mov     r13, [rsp+2A0h+FilePart]
0x18000c330  test    r13, r13
0x18000c333  jz      loc_18000C3C7
0x18000c339  lea     rcx, aInstallSwm; "install*.swm"
0x18000c340  call    StrDupe
0x18000c345  mov     r12, rax
0x18000c348  test    rax, rax
0x18000c34b  jz      short loc_18000C3C4
0x18000c34d  mov     [rsp+2A0h+var_270], 0
0x18000c355  mov     r15, rax
0x18000c358  mov     edx, 3Bh ; ';'; Ch
0x18000c35d  mov     rcx, r15; Str
0x18000c360  call    wcschr_0
0x18000c365  mov     rsi, rax
0x18000c368  test    rax, rax
0x18000c36b  jz      short loc_18000C372
0x18000c36d  xor     ecx, ecx
0x18000c36f  mov     [rax], cx
0x18000c372  mov     rdx, r15
0x18000c375  mov     rcx, r13
0x18000c378  call    WdsPathMatchSingleSpec
0x18000c37d  test    eax, eax
0x18000c37f  jnz     short loc_18000C393
0x18000c381  lea     rax, [rsi+2]
0x18000c385  test    rsi, rsi
0x18000c388  cmovz   rax, r15
0x18000c38c  mov     r15, rax
0x18000c38f  jnz     short loc_18000C358
0x18000c391  jmp     short loc_18000C39B
0x18000c393  mov     [rsp+2A0h+var_270], 1
0x18000c39b  call    cs:__imp_GetProcessHeap
0x18000c3a1  mov     rcx, rax; hHeap
0x18000c3a4  mov     r8, r12; lpMem
0x18000c3a7  xor     edx, edx; dwFlags
0x18000c3a9  call    cs:__imp_HeapFree
0x18000c3af  xor     r12d, r12d
0x18000c3b2  cmp     [rsp+2A0h+var_270], r12d
0x18000c3b7  jnz     loc_18000C47E
0x18000c3bd  mov     r15, [rsp+2A0h+var_258]
0x18000c3c2  jmp     short loc_18000C3C7
0x18000c3c4  xor     r12d, r12d
0x18000c3c7  cmp     [r14+33Ch], r12d
0x18000c3ce  jz      short loc_18000C448
0x18000c3d0  mov     rdx, [r14+2D0h]
0x18000c3d7  mov     rcx, r15
0x18000c3da  call    StrStartsWithIC
0x18000c3df  test    eax, eax
0x18000c3e1  jz      short loc_18000C448
0x18000c3e3  mov     rax, [r14+2D0h]
0x18000c3ea  inc     rbx
0x18000c3ed  cmp     [rax+rbx*2], r12w
0x18000c3f2  jnz     short loc_18000C3EA
0x18000c3f4  lea     rdx, [rbx+1]
0x18000c3f8  lea     rdx, [r15+rdx*2]
0x18000c3fc  lea     r9, [rsp+2A0h+lpFileName]
0x18000c401  xor     r8d, r8d
0x18000c404  mov     rcx, [r14+2D8h]
0x18000c40b  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000c410  mov     rdi, [rsp+2A0h+lpFileName]
0x18000c415  test    eax, eax
0x18000c417  js      short loc_18000C448
0x18000c419  mov     rcx, rdi; lpFileName
0x18000c41c  call    cs:__imp_GetFileAttributesW
0x18000c422  mov     ebx, eax
0x18000c424  cmp     eax, 0FFFFFFFFh
0x18000c427  jz      short loc_18000C433
0x18000c429  shr     ebx, 4
0x18000c42c  not     ebx
0x18000c42e  and     ebx, 1
0x18000c431  jmp     short loc_18000C436
0x18000c433  mov     ebx, r12d
0x18000c436  xor     ecx, ecx
0x18000c438  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c43d  xor     ecx, ecx
0x18000c43f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c444  test    ebx, ebx
0x18000c446  jnz     short loc_18000C47E
0x18000c448  mov     esi, r12d
0x18000c44b  mov     ebx, r12d
0x18000c44e  cmp     [r14+22Ch], r12d
0x18000c455  jbe     short loc_18000C483
0x18000c457  mov     rdx, [r14+230h]
0x18000c45e  movsxd  rax, ebx
0x18000c461  mov     rdx, [rdx+rax*8]
0x18000c465  mov     rcx, r15
0x18000c468  call    StrStartsWithIC
0x18000c46d  test    eax, eax
0x18000c46f  jnz     short loc_18000C47E
0x18000c471  inc     ebx
0x18000c473  cmp     ebx, [r14+22Ch]
0x18000c47a  jb      short loc_18000C457
0x18000c47c  jmp     short loc_18000C483
0x18000c47e  mov     esi, 1
0x18000c483  test    rdi, rdi
0x18000c486  jz      short loc_18000C4A4
0x18000c488  call    cs:__imp_GetProcessHeap
0x18000c48e  mov     rcx, rax; hHeap
0x18000c491  lea     r8, [rdi-4]; lpMem
0x18000c495  xor     edx, edx; dwFlags
0x18000c497  call    cs:__imp_HeapFree
0x18000c49d  xor     ecx, ecx
0x18000c49f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c4a4  mov     eax, esi
0x18000c4a6  mov     rcx, [rbp+1A0h+var_40]
0x18000c4ad  xor     rcx, rsp; StackCookie
0x18000c4b0  call    __security_check_cookie
0x18000c4b5  mov     rbx, [rsp+2A0h+arg_10]
0x18000c4bd  add     rsp, 270h
0x18000c4c4  pop     r15
0x18000c4c6  pop     r14
0x18000c4c8  pop     r13
0x18000c4ca  pop     r12
0x18000c4cc  pop     rdi
0x18000c4cd  pop     rsi
0x18000c4ce  pop     rbp
0x18000c4cf  retn
```
