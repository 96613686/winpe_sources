# AllocFullPathEx

- ea: `0x180010be0`
- end: `0x180010ef4`
- name: `AllocFullPathEx`
- size: `788`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000db70`
- `0x18000e2e4`
- `0x180010efc`
- `0x18001879c`

## callees

- `0x180010508`
- `0x180010be0`
- `0x180012744`
- `0x18003f074`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180010c20`
- `msvcrt!wcsncmp` at `0x180010c20`
- `msvcrt!wcsrchr` at `0x180010e80`
- `msvcrt!wcsrchr` at `0x180010e80`
- `KERNEL32!GetFullPathNameW` at `0x180010c3f`
- `KERNEL32!GetFullPathNameW` at `0x180010de1`
- `KERNEL32!GetFullPathNameW` at `0x180010c3f`
- `KERNEL32!GetFullPathNameW` at `0x180010de1`
- `KERNEL32!HeapFree` at `0x180010e2b`
- `KERNEL32!HeapFree` at `0x180010e53`
- `KERNEL32!HeapFree` at `0x180010e2b`
- `KERNEL32!HeapFree` at `0x180010e53`
- `KERNEL32!HeapAlloc` at `0x180010c90`
- `KERNEL32!HeapAlloc` at `0x180010c90`
- `KERNEL32!GetLastError` at `0x180010e08`
- `KERNEL32!GetLastError` at `0x180010ea1`
- `KERNEL32!GetLastError` at `0x180010e08`
- `KERNEL32!GetLastError` at `0x180010ea1`
- `KERNEL32!SetLastError` at `0x180010eb8`
- `KERNEL32!SetLastError` at `0x180010ece`
- `KERNEL32!SetLastError` at `0x180010eb8`
- `KERNEL32!SetLastError` at `0x180010ece`
- `KERNEL32!GetProcessHeap` at `0x180010c79`
- `KERNEL32!GetProcessHeap` at `0x180010e17`
- `KERNEL32!GetProcessHeap` at `0x180010e3f`
- `KERNEL32!GetProcessHeap` at `0x180010c79`
- `KERNEL32!GetProcessHeap` at `0x180010e17`
- `KERNEL32!GetProcessHeap` at `0x180010e3f`
- `ntdll!RtlFreeHeap` at `0x180010daa`
- `ntdll!RtlFreeHeap` at `0x180010daa`
- `ntdll!RtlAllocateHeap` at `0x180010d0b`
- `ntdll!RtlAllocateHeap` at `0x180010d0b`

## pseudocode

```c
_WORD *__fastcall AllocFullPathEx(unsigned __int16 *lpFileName, int a2, LPWSTR *a3)
{
  WCHAR *v3; // rdi
  unsigned __int16 *v6; // rsi
  _WORD *v7; // rbx
  DWORD LastError; // r12d
  DWORD FullPathNameW; // r14d
  DWORD v10; // r14d
  int v11; // r13d
  HANDLE ProcessHeap; // rax
  wchar_t *Heap; // rbp
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  unsigned int v16; // ecx
  __int64 v17; // rax
  size_t v18; // r13
  HRESULT v19; // eax
  unsigned __int16 v20; // r13
  HRESULT v21; // eax
  HANDLE v22; // rax
  HANDLE v23; // rax
  const wchar_t *v24; // rax
  wchar_t *v25; // rax
  WCHAR *v26; // rax
  DWORD v28; // [rsp+30h] [rbp-68h]
  const wchar_t *pszSrc; // [rsp+40h] [rbp-58h]
  size_t cchDest; // [rsp+48h] [rbp-50h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-48h] BYREF
  unsigned int cchToCopy; // [rsp+A0h] [rbp+8h]
  LPWSTR FilePart; // [rsp+B8h] [rbp+20h] BYREF

  v3 = 0;
  v6 = lpFileName;
  v7 = 0;
  LastError = 0;
  if ( lpFileName && *lpFileName )
  {
    if ( !wcsncmp(lpFileName, L"\\\\?\\", 4u) )
    {
      v24 = (const wchar_t *)WimStrDupe(v6);
      v7 = v24;
      if ( v24 )
      {
        if ( a3 )
        {
          if ( *v24 )
          {
            v25 = wcsrchr(v24, 0x5Cu);
            if ( v25 )
            {
              v26 = v25 + 1;
              if ( *v26 )
                v3 = v26;
            }
          }
          *a3 = v3;
        }
        return v7;
      }
      LastError = GetLastError();
      goto LABEL_40;
    }
    FullPathNameW = GetFullPathNameW(v6, 0, 0, 0);
    if ( !FullPathNameW )
      return v7;
    v10 = FullPathNameW + 1;
    v11 = 0;
    if ( a2 || v10 > 0xF8 )
    {
      v11 = 1;
      v10 += 4;
    }
    ProcessHeap = GetProcessHeap();
    v7 = HeapAlloc(ProcessHeap, 8u, 2LL * v10);
    if ( !v7 )
      return v7;
    FilePart = 0;
    Heap = 0;
    if ( v11 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v6[v14] );
      v15 = v6 + 1;
      if ( *v6 != 92 )
        v15 = v6;
      pszSrc = v15;
      v16 = v14 - 1;
      if ( *v6 != 92 )
        v16 = v14;
      cchToCopy = v16;
      v17 = v16 + 5;
      v18 = (unsigned int)v17;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v17);
      if ( !Heap )
      {
        NtCurrentTeb()->LastErrorValue = 8;
LABEL_22:
        Heap = 0;
        goto LABEL_23;
      }
      v19 = StringCchCopyNExW(Heap, v18, L"\\\\?\\", 4u, &pszDest, &cchDest, v28);
      v20 = v19;
      if ( v19 < 0 || (v21 = StringCchCopyNW(pszDest, cchDest, pszSrc, cchToCopy), v20 = v21, v21 < 0) )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        NtCurrentTeb()->LastErrorValue = v20;
        goto LABEL_22;
      }
      NtCurrentTeb()->LastErrorValue = 0;
    }
LABEL_23:
    if ( Heap )
      v6 = Heap;
    if ( GetFullPathNameW(v6, v10, v7, &FilePart) && *v7 )
    {
      if ( a3 )
        *a3 = FilePart;
    }
    else
    {
      LastError = GetLastError();
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v7);
      v7 = 0;
    }
    if ( Heap )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, Heap);
    }
LABEL_40:
    if ( LastError )
      SetLastError(LastError);
    return v7;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180010be0  mov     [rsp+arg_8], rbx
0x180010be5  push    rbp
0x180010be6  push    rsi
0x180010be7  push    rdi
0x180010be8  push    r12
0x180010bea  push    r13
0x180010bec  push    r14
0x180010bee  push    r15
0x180010bf0  sub     rsp, 60h
0x180010bf4  xor     edi, edi
0x180010bf6  mov     r15, r8
0x180010bf9  mov     ebp, edx
0x180010bfb  mov     rsi, rcx
0x180010bfe  mov     ebx, edi
0x180010c00  mov     r12d, edi
0x180010c03  test    rcx, rcx
0x180010c06  jz      loc_180010EC9
0x180010c0c  cmp     [rcx], di
0x180010c0f  jz      loc_180010EC9
0x180010c15  lea     r8d, [rdi+4]; MaxCount
0x180010c19  lea     rdx, pszSrc; "\\\\?\\"
0x180010c20  call    cs:__imp_wcsncmp
0x180010c27  nop     dword ptr [rax+rax+00h]
0x180010c2c  mov     rcx, rsi; unsigned __int16 *
0x180010c2f  test    eax, eax
0x180010c31  jz      loc_180010E61
0x180010c37  xor     r9d, r9d; lpFilePart
0x180010c3a  xor     r8d, r8d; lpBuffer
0x180010c3d  xor     edx, edx; nBufferLength
0x180010c3f  call    cs:__imp_GetFullPathNameW
0x180010c46  nop     dword ptr [rax+rax+00h]
0x180010c4b  mov     r14d, eax
0x180010c4e  test    eax, eax
0x180010c50  jz      loc_180010EC4
0x180010c56  inc     r14d
0x180010c59  mov     r13d, edi
0x180010c5c  test    ebp, ebp
0x180010c5e  jnz     short loc_180010C69
0x180010c60  cmp     r14d, 0F8h
0x180010c67  jbe     short loc_180010C73
0x180010c69  mov     r13d, 1
0x180010c6f  add     r14d, 4
0x180010c73  mov     ebx, r14d
0x180010c76  add     rbx, rbx
0x180010c79  call    cs:__imp_GetProcessHeap
0x180010c80  nop     dword ptr [rax+rax+00h]
0x180010c85  mov     r8, rbx; dwBytes
0x180010c88  mov     edx, 8; dwFlags
0x180010c8d  mov     rcx, rax; hHeap
0x180010c90  call    cs:__imp_HeapAlloc
0x180010c97  nop     dword ptr [rax+rax+00h]
0x180010c9c  mov     rbx, rax
0x180010c9f  test    rax, rax
0x180010ca2  jz      loc_180010EC4
0x180010ca8  mov     [rsp+98h+FilePart], rdi
0x180010cb0  mov     rbp, rdi
0x180010cb3  test    r13d, r13d
0x180010cb6  jz      loc_180010DC9
0x180010cbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010cc0  inc     rax
0x180010cc3  cmp     [rsi+rax*2], di
0x180010cc7  jnz     short loc_180010CC0
0x180010cc9  mov     edx, 5Ch ; '\'
0x180010cce  lea     rcx, [rsi+2]
0x180010cd2  cmp     dx, [rsi]
0x180010cd5  mov     edx, 8; Flags
0x180010cda  cmovnz  rcx, rsi
0x180010cde  mov     [rsp+98h+pszSrc], rcx
0x180010ce3  lea     ecx, [rax-1]
0x180010ce6  cmovnz  ecx, eax
0x180010ce9  mov     dword ptr [rsp+98h+cchToCopy], ecx
0x180010cf0  lea     eax, [rcx+5]
0x180010cf3  mov     rcx, gs:60h
0x180010cfc  lea     r8, ds:0[rax*2]; Size
0x180010d04  mov     r13d, eax
0x180010d07  mov     rcx, [rcx+30h]; HeapHandle
0x180010d0b  call    cs:__imp_RtlAllocateHeap
0x180010d12  nop     dword ptr [rax+rax+00h]
0x180010d17  mov     rbp, rax
0x180010d1a  test    rax, rax
0x180010d1d  jnz     short loc_180010D34
0x180010d1f  mov     rax, gs:30h
0x180010d28  mov     dword ptr [rax+68h], 8
0x180010d2f  jmp     loc_180010DC6
0x180010d34  lea     rax, [rsp+98h+cchDest]
0x180010d39  mov     r9d, 4; cchToCopy
0x180010d3f  mov     [rsp+98h+pcchRemaining], rax; pcchRemaining
0x180010d44  lea     r8, pszSrc; "\\\\?\\"
0x180010d4b  lea     rax, [rsp+98h+pszDest]
0x180010d50  mov     rdx, r13; cchDest
0x180010d53  mov     rcx, rbp; pszDest
0x180010d56  mov     [rsp+98h+ppszDestEnd], rax; ppszDestEnd
0x180010d5b  call    StringCchCopyNExW
0x180010d60  mov     r13d, eax
0x180010d63  test    eax, eax
0x180010d65  js      short loc_180010D98
0x180010d67  mov     r9d, dword ptr [rsp+98h+cchToCopy]; cchToCopy
0x180010d6f  mov     r8, [rsp+98h+pszSrc]; pszSrc
0x180010d74  mov     rdx, [rsp+98h+cchDest]; cchDest
0x180010d79  mov     rcx, [rsp+98h+pszDest]; pszDest
0x180010d7e  call    StringCchCopyNW
0x180010d83  mov     r13d, eax
0x180010d86  test    eax, eax
0x180010d88  js      short loc_180010D98
0x180010d8a  mov     rax, gs:30h
0x180010d93  mov     [rax+68h], edi
0x180010d96  jmp     short loc_180010DC9
0x180010d98  mov     rcx, gs:60h
0x180010da1  mov     r8, rbp; P
0x180010da4  xor     edx, edx; Flags
0x180010da6  mov     rcx, [rcx+30h]; HeapHandle
0x180010daa  call    cs:__imp_RtlFreeHeap
0x180010db1  nop     dword ptr [rax+rax+00h]
0x180010db6  mov     rax, gs:30h
0x180010dbf  movzx   ecx, r13w
0x180010dc3  mov     [rax+68h], ecx
0x180010dc6  mov     rbp, rdi
0x180010dc9  test    rbp, rbp
0x180010dcc  lea     r9, [rsp+98h+FilePart]; lpFilePart
0x180010dd4  mov     r8, rbx; lpBuffer
0x180010dd7  mov     edx, r14d; nBufferLength
0x180010dda  cmovnz  rsi, rbp
0x180010dde  mov     rcx, rsi; lpFileName
0x180010de1  call    cs:__imp_GetFullPathNameW
0x180010de8  nop     dword ptr [rax+rax+00h]
0x180010ded  test    eax, eax
0x180010def  jz      short loc_180010E08
0x180010df1  cmp     [rbx], di
0x180010df4  jz      short loc_180010E08
0x180010df6  test    r15, r15
0x180010df9  jz      short loc_180010E3A
0x180010dfb  mov     rax, [rsp+98h+FilePart]
0x180010e03  mov     [r15], rax
0x180010e06  jmp     short loc_180010E3A
0x180010e08  call    cs:__imp_GetLastError
0x180010e0f  nop     dword ptr [rax+rax+00h]
0x180010e14  mov     r12d, eax
0x180010e17  call    cs:__imp_GetProcessHeap
0x180010e1e  nop     dword ptr [rax+rax+00h]
0x180010e23  mov     r8, rbx; lpMem
0x180010e26  xor     edx, edx; dwFlags
0x180010e28  mov     rcx, rax; hHeap
0x180010e2b  call    cs:__imp_HeapFree
0x180010e32  nop     dword ptr [rax+rax+00h]
0x180010e37  mov     rbx, rdi
0x180010e3a  test    rbp, rbp
0x180010e3d  jz      short loc_180010EB0
0x180010e3f  call    cs:__imp_GetProcessHeap
0x180010e46  nop     dword ptr [rax+rax+00h]
0x180010e4b  mov     r8, rbp; lpMem
0x180010e4e  xor     edx, edx; dwFlags
0x180010e50  mov     rcx, rax; hHeap
0x180010e53  call    cs:__imp_HeapFree
0x180010e5a  nop     dword ptr [rax+rax+00h]
0x180010e5f  jmp     short loc_180010EB0
0x180010e61  call    WimStrDupe
0x180010e66  mov     rbx, rax
0x180010e69  test    rax, rax
0x180010e6c  jz      short loc_180010EA1
0x180010e6e  test    r15, r15
0x180010e71  jz      short loc_180010EC4
0x180010e73  cmp     [rax], di
0x180010e76  jz      short loc_180010E9C
0x180010e78  mov     edx, 5Ch ; '\'; Ch
0x180010e7d  mov     rcx, rax; Str
0x180010e80  call    cs:__imp_wcsrchr
0x180010e87  nop     dword ptr [rax+rax+00h]
0x180010e8c  test    rax, rax
0x180010e8f  jz      short loc_180010E9C
0x180010e91  add     rax, 2
0x180010e95  cmp     [rax], di
0x180010e98  cmovnz  rdi, rax
0x180010e9c  mov     [r15], rdi
0x180010e9f  jmp     short loc_180010EC4
0x180010ea1  call    cs:__imp_GetLastError
0x180010ea8  nop     dword ptr [rax+rax+00h]
0x180010ead  mov     r12d, eax
0x180010eb0  test    r12d, r12d
0x180010eb3  jz      short loc_180010EC4
0x180010eb5  mov     ecx, r12d; dwErrCode
0x180010eb8  call    cs:__imp_SetLastError
0x180010ebf  nop     dword ptr [rax+rax+00h]
0x180010ec4  mov     rax, rbx
0x180010ec7  jmp     short loc_180010EDC
0x180010ec9  mov     ecx, 57h ; 'W'; dwErrCode
0x180010ece  call    cs:__imp_SetLastError
0x180010ed5  nop     dword ptr [rax+rax+00h]
0x180010eda  xor     eax, eax
0x180010edc  mov     rbx, [rsp+98h+arg_8]
0x180010ee4  add     rsp, 60h
0x180010ee8  pop     r15
0x180010eea  pop     r14
0x180010eec  pop     r13
0x180010eee  pop     r12
0x180010ef0  pop     rdi
0x180010ef1  pop     rsi
0x180010ef2  pop     rbp
0x180010ef3  retn
```
