# SpCreateFileMapping(void *,ulong,ulong,ulong,ushort const *,ulong)

- ea: `0x1800f1b60`
- end: `0x1800f1c7f`
- name: `?SpCreateFileMapping@@YAPEAXPEAXKKKPEBGK@Z`
- size: `287`
- prototype: `void *__fastcall(HANDLE hFile, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800f15bc`

## callees

- `0x18000c808`
- `0x18000eb90`
- `0x18000f110`
- `0x180079e30`
- `0x1800f1b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f1c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f1c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1c2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1c51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1c51`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800f1bda`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800f1bda`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800f1c21`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800f1c21`

## pseudocode

```c
HANDLE __fastcall SpCreateFileMapping(HANDLE hFile)
{
  const unsigned __int16 *v2; // rdx
  int v3; // eax
  HANDLE FileMappingW; // rbx
  int i; // edi
  int v7; // [rsp+30h] [rbp-258h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-250h]
  _WORD v9[272]; // [rsp+50h] [rbp-238h] BYREF

  CSpSecurityAttribute::CSpSecurityAttribute((CSpSecurityAttribute *)&v7, 4u, 4);
  v3 = PrefixedObjectName::Initialize((PrefixedObjectName *)v9, v2, 0);
  FileMappingW = 0;
  if ( !SetLastErrorIfFailed(v3) )
  {
    for ( i = 0; i < 100; ++i )
    {
      FileMappingW = OpenFileMappingW(4u, 0, (LPCWSTR)((unsigned __int64)v9 & -(__int64)(v9[0] != 0)));
      if ( FileMappingW )
      {
        SetLastError(0xB7u);
        break;
      }
      FileMappingW = CreateFileMappingW(
                       hFile,
                       (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v7 & -(__int64)(v7 != 0)),
                       0x8000002u,
                       0,
                       0,
                       (LPCWSTR)((unsigned __int64)v9 & -(__int64)(v9[0] != 0)));
      if ( FileMappingW || GetLastError() != 5 )
        break;
    }
  }
  LocalFree(hMem);
  return FileMappingW;
}

```

## disassembly

```asm
0x1800f1b60  mov     [rsp+arg_8], rbx
0x1800f1b65  mov     [rsp+arg_10], rsi
0x1800f1b6a  push    rdi
0x1800f1b6b  sub     rsp, 280h
0x1800f1b72  mov     rax, cs:__security_cookie
0x1800f1b79  xor     rax, rsp
0x1800f1b7c  mov     [rsp+288h+var_18], rax
0x1800f1b84  mov     edx, 4; unsigned int
0x1800f1b89  mov     rsi, rcx
0x1800f1b8c  mov     r8d, edx; unsigned int
0x1800f1b8f  lea     rcx, [rsp+288h+var_258]; this
0x1800f1b94  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x1800f1b99  xor     r8d, r8d; unsigned __int16 *
0x1800f1b9c  lea     rcx, [rsp+288h+var_238]; this
0x1800f1ba1  call    ?Initialize@PrefixedObjectName@@AEAAJPEBG0@Z; PrefixedObjectName::Initialize(ushort const *,ushort const *)
0x1800f1ba6  mov     ecx, eax; int
0x1800f1ba8  call    ?SetLastErrorIfFailed@@YA_NJ@Z; SetLastErrorIfFailed(long)
0x1800f1bad  xor     ebx, ebx
0x1800f1baf  test    al, al
0x1800f1bb1  jnz     loc_1800F1C4C
0x1800f1bb7  xor     edi, edi
0x1800f1bb9  cmp     edi, 64h ; 'd'
0x1800f1bbc  jge     loc_1800F1C4C
0x1800f1bc2  movzx   eax, [rsp+288h+var_238]
0x1800f1bc7  neg     ax
0x1800f1bca  lea     rax, [rsp+288h+var_238]
0x1800f1bcf  sbb     r8, r8
0x1800f1bd2  xor     edx, edx; bInheritHandle
0x1800f1bd4  and     r8, rax; lpName
0x1800f1bd7  lea     ecx, [rdx+4]; dwDesiredAccess
0x1800f1bda  call    cs:__imp_OpenFileMappingW
0x1800f1be0  mov     rbx, rax
0x1800f1be3  test    rax, rax
0x1800f1be6  jnz     short loc_1800F1C41
0x1800f1be8  movzx   eax, [rsp+288h+var_238]
0x1800f1bed  mov     r8d, 8000002h; flProtect
0x1800f1bf3  neg     ax
0x1800f1bf6  lea     rax, [rsp+288h+var_238]
0x1800f1bfb  sbb     rcx, rcx
0x1800f1bfe  and     rcx, rax
0x1800f1c01  mov     eax, [rsp+288h+var_258]
0x1800f1c05  neg     eax
0x1800f1c07  mov     [rsp+288h+lpName], rcx; lpName
0x1800f1c0c  lea     rax, [rsp+288h+var_258]
0x1800f1c11  mov     [rsp+288h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800f1c15  sbb     rdx, rdx
0x1800f1c18  mov     rcx, rsi; hFile
0x1800f1c1b  and     rdx, rax; lpFileMappingAttributes
0x1800f1c1e  xor     r9d, r9d; dwMaximumSizeHigh
0x1800f1c21  call    cs:__imp_CreateFileMappingW
0x1800f1c27  mov     rbx, rax
0x1800f1c2a  test    rax, rax
0x1800f1c2d  jnz     short loc_1800F1C4C
0x1800f1c2f  call    cs:__imp_GetLastError
0x1800f1c35  cmp     eax, 5
0x1800f1c38  jnz     short loc_1800F1C4C
0x1800f1c3a  inc     edi
0x1800f1c3c  jmp     loc_1800F1BB9
0x1800f1c41  mov     ecx, 0B7h; dwErrCode
0x1800f1c46  call    cs:__imp_SetLastError
0x1800f1c4c  mov     rcx, [rsp+288h+hMem]; hMem
0x1800f1c51  call    cs:__imp_LocalFree
0x1800f1c57  mov     rax, rbx
0x1800f1c5a  mov     rcx, [rsp+288h+var_18]
0x1800f1c62  xor     rcx, rsp; StackCookie
0x1800f1c65  call    __security_check_cookie
0x1800f1c6a  lea     r11, [rsp+288h+var_8]
0x1800f1c72  mov     rbx, [r11+18h]
0x1800f1c76  mov     rsi, [r11+20h]
0x1800f1c7a  mov     rsp, r11
0x1800f1c7d  pop     rdi
0x1800f1c7e  retn
```
