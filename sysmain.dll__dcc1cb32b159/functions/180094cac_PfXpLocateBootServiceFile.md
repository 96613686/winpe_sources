# PfXpLocateBootServiceFile

- ea: `0x180094cac`
- end: `0x180094d68`
- name: `PfXpLocateBootServiceFile`
- size: `188`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPCWSTR pszSrc@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180093660`
- `0x180094654`

## callees

- `0x180058394`
- `0x180094cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094ccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094ccf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180094cc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180094cc5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094d26`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094d4b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094d26`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180094d4b`

## pseudocode

```c
__int64 __fastcall PfXpLocateBootServiceFile(STRSAFE_LPCWSTR pszSrc, int a2, WCHAR *a3, __int64 a4, unsigned int *a5)
{
  UINT SystemDirectoryW; // eax
  size_t v9; // rdx
  unsigned int v10; // edx
  __int64 v11; // rdi
  unsigned int v12; // ecx
  size_t v13; // rdx
  size_t v14; // rdx
  size_t v15; // rdx
  DWORD FileAttributesW; // eax

  SystemDirectoryW = GetSystemDirectoryW(a3, 0x104u);
  if ( SystemDirectoryW )
  {
    v11 = SystemDirectoryW + 1;
    v12 = v11 + a2 + 9;
    *a5 = v12;
    if ( v12 <= 0x104 )
    {
      StringCchCatW(a3, v9, L"\\");
      StringCchCatW(a3, v13, L"drivers\\");
      StringCchCatW(a3, v14, pszSrc);
      if ( GetFileAttributesW(a3) == -1 )
      {
        a3[v11] = 0;
        StringCchCatW(a3, v15, pszSrc);
        FileAttributesW = GetFileAttributesW(a3);
        v10 = 2;
        if ( FileAttributesW != -1 )
          return 0;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      return 122;
    }
  }
  else
  {
    return GetLastError();
  }
  return v10;
}

```

## disassembly

```asm
0x180094cac  push    rbx
0x180094cae  push    rbp
0x180094caf  push    rsi
0x180094cb0  push    rdi
0x180094cb1  sub     rsp, 28h
0x180094cb5  mov     esi, edx
0x180094cb7  mov     rbp, rcx
0x180094cba  mov     edx, 104h; uSize
0x180094cbf  mov     rcx, r8; lpBuffer
0x180094cc2  mov     rbx, r8
0x180094cc5  call    cs:__imp_GetSystemDirectoryW
0x180094ccb  test    eax, eax
0x180094ccd  jnz     short loc_180094CDC
0x180094ccf  call    cs:__imp_GetLastError
0x180094cd5  mov     edx, eax
0x180094cd7  jmp     loc_180094D5D
0x180094cdc  lea     edi, [rax+1]
0x180094cdf  mov     rax, [rsp+48h+arg_20]
0x180094ce4  lea     ecx, [rsi+9]
0x180094ce7  add     ecx, edi
0x180094ce9  mov     [rax], ecx
0x180094ceb  cmp     ecx, 104h
0x180094cf1  jbe     short loc_180094CFA
0x180094cf3  mov     edx, 7Ah ; 'z'
0x180094cf8  jmp     short loc_180094D5D
0x180094cfa  lea     r8, asc_1800BF1BC; "\\"
0x180094d01  mov     rcx, rbx; pszDest
0x180094d04  call    StringCchCatW
0x180094d09  lea     r8, aDrivers; "drivers\\"
0x180094d10  mov     rcx, rbx; pszDest
0x180094d13  call    StringCchCatW
0x180094d18  mov     r8, rbp; pszSrc
0x180094d1b  mov     rcx, rbx; pszDest
0x180094d1e  call    StringCchCatW
0x180094d23  mov     rcx, rbx; lpFileName
0x180094d26  call    cs:__imp_GetFileAttributesW
0x180094d2c  or      esi, 0FFFFFFFFh
0x180094d2f  cmp     eax, esi
0x180094d31  jz      short loc_180094D37
0x180094d33  xor     edx, edx
0x180094d35  jmp     short loc_180094D5D
0x180094d37  xor     eax, eax
0x180094d39  mov     r8, rbp; pszSrc
0x180094d3c  mov     rcx, rbx; pszDest
0x180094d3f  mov     [rbx+rdi*2], ax
0x180094d43  call    StringCchCatW
0x180094d48  mov     rcx, rbx; lpFileName
0x180094d4b  call    cs:__imp_GetFileAttributesW
0x180094d51  xor     ecx, ecx
0x180094d53  mov     edx, 2
0x180094d58  cmp     eax, esi
0x180094d5a  cmovnz  edx, ecx
0x180094d5d  mov     eax, edx
0x180094d5f  add     rsp, 28h
0x180094d63  pop     rdi
0x180094d64  pop     rsi
0x180094d65  pop     rbp
0x180094d66  pop     rbx
0x180094d67  retn
```
