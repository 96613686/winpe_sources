# ?get_Name@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z

- ea: `0x18002e100`
- end: `0x18002e196`
- name: `?get_Name@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18002e100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e170`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e170`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e182`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e13d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e13d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002e151`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002e151`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e15a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e15a`

## pseudocode

```c
__int64 __fastcall _get_Name__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAPEAG_Z(__int64 a1, BSTR *a2)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const WCHAR *v7; // rcx
  const OLECHAR *FileNameW; // rax
  BSTR v9; // rax

  if ( !a2 )
    return 2147500035LL;
  v5 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v5 )
  {
    v6 = v5 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  }
  else
  {
    v6 = 8;
  }
  v7 = (const WCHAR *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v7 = *(const WCHAR **)v7;
  FileNameW = PathFindFileNameW(v7);
  v9 = SysAllocString(FileNameW);
  *a2 = v9;
  if ( v9 )
  {
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 0;
  }
  else
  {
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18002e100  push    rbx
0x18002e102  push    rsi
0x18002e103  push    rdi
0x18002e104  push    r14
0x18002e106  sub     rsp, 28h
0x18002e10a  mov     r14, rdx
0x18002e10d  mov     rsi, rcx
0x18002e110  test    rdx, rdx
0x18002e113  jnz     short loc_18002E124
0x18002e115  mov     eax, 80004003h
0x18002e11a  add     rsp, 28h
0x18002e11e  pop     r14
0x18002e120  pop     rdi
0x18002e121  pop     rsi
0x18002e122  pop     rbx
0x18002e123  retn
0x18002e124  add     rcx, 10h
0x18002e128  mov     rax, rsi
0x18002e12b  neg     rax
0x18002e12e  sbb     rbx, rbx
0x18002e131  and     rbx, rcx
0x18002e134  jz      short loc_18002E18F
0x18002e136  lea     rdi, [rbx+8]
0x18002e13a  mov     rcx, rdi; lpCriticalSection
0x18002e13d  call    cs:__imp_EnterCriticalSection
0x18002e143  lea     rcx, [rsi+50h]
0x18002e147  cmp     qword ptr [rcx+18h], 8
0x18002e14c  jb      short loc_18002E151
0x18002e14e  mov     rcx, [rcx]; pszPath
0x18002e151  call    cs:__imp_PathFindFileNameW
0x18002e157  mov     rcx, rax; psz
0x18002e15a  call    cs:__imp_SysAllocString
0x18002e160  mov     [r14], rax
0x18002e163  test    rax, rax
0x18002e166  jz      short loc_18002E17A
0x18002e168  test    rbx, rbx
0x18002e16b  jz      short loc_18002E176
0x18002e16d  mov     rcx, rdi; lpCriticalSection
0x18002e170  call    cs:__imp_LeaveCriticalSection
0x18002e176  xor     eax, eax
0x18002e178  jmp     short loc_18002E11A
0x18002e17a  test    rbx, rbx
0x18002e17d  jz      short loc_18002E188
0x18002e17f  mov     rcx, rdi; lpCriticalSection
0x18002e182  call    cs:__imp_LeaveCriticalSection
0x18002e188  mov     eax, 8007000Eh
0x18002e18d  jmp     short loc_18002E11A
0x18002e18f  mov     edi, 8
0x18002e194  jmp     short loc_18002E143
```
