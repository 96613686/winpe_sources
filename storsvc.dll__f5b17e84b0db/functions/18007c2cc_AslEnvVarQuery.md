# AslEnvVarQuery

- ea: `0x18007c2cc`
- end: `0x18007c4f7`
- name: `AslEnvVarQuery`
- size: `555`
- prototype: `__int64 __fastcall(WCHAR *, const wchar_t *, unsigned __int64, _WORD *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18007be18`

## callees

- `0x18000dcfc`
- `0x18000dd98`
- `0x18007c2cc`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c348`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c330`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c330`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007c35e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007c35e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007c3fb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007c407`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007c3fb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007c407`

## string_xrefs

- `0x18007c31e`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AslEnvVarQuery(
        WCHAR *a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        _WORD *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rsi
  HMODULE Library; // rax
  HMODULE v12; // rbx
  __int64 (*ProcAddress)(void); // rax
  unsigned __int64 v14; // rdi
  __int64 result; // rax
  WCHAR *v16; // rbp
  WCHAR *v17; // r13
  WCHAR *v18; // r15
  WCHAR v19; // bx
  WCHAR v20; // di
  int v21; // edx
  WCHAR v22; // ax
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rsi

  if ( a3 < 0xA || wcsnicmp(a2, L"systemroot", 0xAu) )
  {
    if ( !a1 )
      return 3221225728LL;
    v16 = (WCHAR *)&a2[a3];
    while ( 1 )
    {
      if ( !*a1 )
        return 3221225728LL;
      v17 = a1;
      v18 = (WCHAR *)a2;
      if ( a2 >= v16 )
      {
LABEL_25:
        if ( v18 == v16 && *a1 == 61 )
        {
          v21 = 1;
          goto LABEL_34;
        }
      }
      else
      {
        while ( *a1 )
        {
          v19 = *a1;
          v20 = RtlUpcaseUnicodeChar(*v18);
          if ( RtlUpcaseUnicodeChar(v19) == v20 )
          {
            ++a1;
            if ( ++v18 < v16 )
              continue;
          }
          goto LABEL_25;
        }
      }
      v22 = *a1;
      if ( !*a1 )
        goto LABEL_38;
      do
      {
        if ( v22 == 61 && a1 != v17 )
          break;
        v22 = *++a1;
      }
      while ( *a1 );
      if ( !*a1 )
        goto LABEL_38;
      v21 = 0;
LABEL_34:
      v23 = a1;
      do
      {
        if ( (__int64)(((char *)a1 - (char *)v23) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
          break;
        ++a1;
      }
      while ( *a1 );
      if ( v21 )
      {
        v24 = a1 - (v23 + 1);
        if ( v24 < a5 )
        {
          memcpy_0(a4, v23 + 1, 2 * v24);
          a4[v24] = 0;
          result = 0;
        }
        else
        {
          if ( a4 && a5 )
            *a4 = 0;
          result = 3221225507LL;
          ++v24;
        }
        *a6 = v24;
        return result;
      }
LABEL_38:
      ++a1;
    }
  }
  v10 = (__int64)Src;
  if ( !Src )
  {
    v10 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v12 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v10 = ProcAddress();
      FreeLibrary(v12);
    }
    Src = (void *)v10;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v10 + 2 * v14) );
  if ( v14 < a5 )
  {
    memcpy_0(a4, (const void *)v10, 2 * v14);
    a4[v14] = 0;
    result = 0;
  }
  else
  {
    if ( a4 )
    {
      if ( a5 )
        *a4 = 0;
    }
    result = 3221225507LL;
    ++v14;
  }
  *a6 = v14;
  return result;
}

```

## disassembly

```asm
0x18007c2cc  push    rbx
0x18007c2ce  push    rbp
0x18007c2cf  push    rsi
0x18007c2d0  push    rdi
0x18007c2d1  push    r12
0x18007c2d3  push    r13
0x18007c2d5  push    r14
0x18007c2d7  push    r15
0x18007c2d9  sub     rsp, 28h
0x18007c2dd  xor     r15d, r15d
0x18007c2e0  mov     rbx, r8
0x18007c2e3  mov     r14, r9
0x18007c2e6  mov     r12, rdx
0x18007c2e9  mov     rsi, rcx
0x18007c2ec  lea     r8d, [r15+0Ah]; MaxCount
0x18007c2f0  cmp     rbx, r8
0x18007c2f3  jb      loc_18007C3CB
0x18007c2f9  lea     rdx, aSystemroot_1; "systemroot"
0x18007c300  mov     rcx, r12; String1
0x18007c303  call    _wcsnicmp
0x18007c308  test    eax, eax
0x18007c30a  jnz     loc_18007C3CB
0x18007c310  mov     rsi, cs:Src
0x18007c317  test    rsi, rsi
0x18007c31a  jnz     short loc_18007C36B
0x18007c31c  xor     edx, edx; hFile
0x18007c31e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18007c325  mov     r8d, 800h; dwFlags
0x18007c32b  mov     esi, 7FFE0030h
0x18007c330  call    cs:__imp_LoadLibraryExW
0x18007c336  mov     rbx, rax
0x18007c339  test    rax, rax
0x18007c33c  jz      short loc_18007C364
0x18007c33e  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18007c345  mov     rcx, rax; hModule
0x18007c348  call    cs:__imp_GetProcAddress
0x18007c34e  test    rax, rax
0x18007c351  jz      short loc_18007C35B
0x18007c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c358  mov     rsi, rax
0x18007c35b  mov     rcx, rbx; hLibModule
0x18007c35e  call    cs:__imp_FreeLibrary
0x18007c364  mov     cs:Src, rsi
0x18007c36b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007c36f  inc     rdi
0x18007c372  cmp     [rsi+rdi*2], r15w
0x18007c377  jnz     short loc_18007C36F
0x18007c379  cmp     rdi, [rsp+68h+arg_20]
0x18007c381  jb      short loc_18007C3A1
0x18007c383  test    r14, r14
0x18007c386  jz      short loc_18007C397
0x18007c388  cmp     [rsp+68h+arg_20], 1
0x18007c391  jb      short loc_18007C397
0x18007c393  mov     [r14], r15w
0x18007c397  mov     eax, 0C0000023h
0x18007c39c  inc     rdi
0x18007c39f  jmp     short loc_18007C3BB
0x18007c3a1  lea     rbx, [rdi+rdi]
0x18007c3a5  mov     rdx, rsi; Src
0x18007c3a8  mov     r8, rbx; Size
0x18007c3ab  mov     rcx, r14; void *
0x18007c3ae  call    memcpy_0
0x18007c3b3  mov     [rbx+r14], r15w
0x18007c3b8  mov     eax, r15d
0x18007c3bb  mov     rcx, [rsp+68h+arg_28]
0x18007c3c3  mov     [rcx], rdi
0x18007c3c6  jmp     loc_18007C4E6
0x18007c3cb  test    rsi, rsi
0x18007c3ce  jz      loc_18007C4E1
0x18007c3d4  lea     rbp, [r12+rbx*2]
0x18007c3d8  cmp     [rsi], r15w
0x18007c3dc  jz      loc_18007C4E1
0x18007c3e2  mov     r13, rsi
0x18007c3e5  mov     r15, r12
0x18007c3e8  cmp     r12, rbp
0x18007c3eb  jnb     short loc_18007C41F
0x18007c3ed  xor     eax, eax
0x18007c3ef  cmp     [rsi], ax
0x18007c3f2  jz      short loc_18007C434
0x18007c3f4  movzx   ecx, word ptr [r15]; Source
0x18007c3f8  movzx   ebx, word ptr [rsi]
0x18007c3fb  call    cs:__imp_RtlUpcaseUnicodeChar
0x18007c401  movzx   ecx, bx; Source
0x18007c404  movzx   edi, ax
0x18007c407  call    cs:__imp_RtlUpcaseUnicodeChar
0x18007c40d  cmp     ax, di
0x18007c410  jnz     short loc_18007C41F
0x18007c412  add     rsi, 2
0x18007c416  add     r15, 2
0x18007c41a  cmp     r15, rbp
0x18007c41d  jb      short loc_18007C3ED
0x18007c41f  cmp     r15, rbp
0x18007c422  jnz     short loc_18007C434
0x18007c424  cmp     word ptr [rsi], 3Dh ; '='
0x18007c428  jnz     short loc_18007C434
0x18007c42a  mov     edx, 1
0x18007c42f  xor     r15d, r15d
0x18007c432  jmp     short loc_18007C45F
0x18007c434  movzx   eax, word ptr [rsi]
0x18007c437  xor     r15d, r15d
0x18007c43a  test    ax, ax
0x18007c43d  jz      short loc_18007C482
0x18007c43f  cmp     ax, 3Dh ; '='
0x18007c443  jnz     short loc_18007C44A
0x18007c445  cmp     rsi, r13
0x18007c448  jnz     short loc_18007C456
0x18007c44a  add     rsi, 2
0x18007c44e  movzx   eax, word ptr [rsi]
0x18007c451  test    ax, ax
0x18007c454  jnz     short loc_18007C43F
0x18007c456  cmp     [rsi], r15w
0x18007c45a  jz      short loc_18007C482
0x18007c45c  mov     edx, r15d
0x18007c45f  mov     rcx, rsi
0x18007c462  mov     rax, rsi
0x18007c465  sub     rax, rcx
0x18007c468  and     rax, 0FFFFFFFFFFFFFFFEh
0x18007c46c  cmp     rax, 0FFFEh
0x18007c472  jge     short loc_18007C47E
0x18007c474  add     rsi, 2
0x18007c478  cmp     [rsi], r15w
0x18007c47c  jnz     short loc_18007C462
0x18007c47e  test    edx, edx
0x18007c480  jnz     short loc_18007C48B
0x18007c482  add     rsi, 2
0x18007c486  jmp     loc_18007C3D8
0x18007c48b  mov     rdi, [rsp+68h+arg_28]
0x18007c493  lea     rdx, [rcx+2]; Src
0x18007c497  sub     rsi, rdx
0x18007c49a  sar     rsi, 1
0x18007c49d  cmp     rsi, [rsp+68h+arg_20]
0x18007c4a5  jb      short loc_18007C4C5
0x18007c4a7  test    r14, r14
0x18007c4aa  jz      short loc_18007C4BB
0x18007c4ac  cmp     [rsp+68h+arg_20], 1
0x18007c4b5  jb      short loc_18007C4BB
0x18007c4b7  mov     [r14], r15w
0x18007c4bb  mov     eax, 0C0000023h
0x18007c4c0  inc     rsi
0x18007c4c3  jmp     short loc_18007C4DC
0x18007c4c5  lea     rbx, [rsi+rsi]
0x18007c4c9  mov     rcx, r14; void *
0x18007c4cc  mov     r8, rbx; Size
0x18007c4cf  call    memcpy_0
0x18007c4d4  mov     [rbx+r14], r15w
0x18007c4d9  mov     eax, r15d
0x18007c4dc  mov     [rdi], rsi
0x18007c4df  jmp     short loc_18007C4E6
0x18007c4e1  mov     eax, 0C0000100h
0x18007c4e6  add     rsp, 28h
0x18007c4ea  pop     r15
0x18007c4ec  pop     r14
0x18007c4ee  pop     r13
0x18007c4f0  pop     r12
0x18007c4f2  pop     rdi
0x18007c4f3  pop     rsi
0x18007c4f4  pop     rbp
0x18007c4f5  pop     rbx
0x18007c4f6  retn
```
