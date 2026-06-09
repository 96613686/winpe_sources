# SpCreateFileMapping(void *,ulong,ulong,ulong,ushort const *,ulong)

- ea: `0x1800fdf04`
- end: `0x1800fe023`
- name: `?SpCreateFileMapping@@YAPEAXPEAXKKKPEBGK@Z`
- size: `287`
- prototype: `void *__fastcall(HANDLE hFile, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800fd7c4`

## callees

- `0x1800034b0`
- `0x1800067d4`
- `0x1800117c0`
- `0x1800c774c`
- `0x1800fdf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fdfea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fdfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fdfd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fdfd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fdff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fdff5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800fdf7e`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800fdf7e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800fdfc5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800fdfc5`

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
0x1800fdf04  mov     [rsp+arg_8], rbx
0x1800fdf09  mov     [rsp+arg_10], rsi
0x1800fdf0e  push    rdi
0x1800fdf0f  sub     rsp, 280h
0x1800fdf16  mov     rax, cs:__security_cookie
0x1800fdf1d  xor     rax, rsp
0x1800fdf20  mov     [rsp+288h+var_18], rax
0x1800fdf28  mov     edx, 4; unsigned int
0x1800fdf2d  mov     rsi, rcx
0x1800fdf30  mov     r8d, edx; unsigned int
0x1800fdf33  lea     rcx, [rsp+288h+var_258]; this
0x1800fdf38  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x1800fdf3d  xor     r8d, r8d; unsigned __int16 *
0x1800fdf40  lea     rcx, [rsp+288h+var_238]; this
0x1800fdf45  call    ?Initialize@PrefixedObjectName@@AEAAJPEBG0@Z; PrefixedObjectName::Initialize(ushort const *,ushort const *)
0x1800fdf4a  mov     ecx, eax; int
0x1800fdf4c  call    ?SetLastErrorIfFailed@@YA_NJ@Z; SetLastErrorIfFailed(long)
0x1800fdf51  xor     ebx, ebx
0x1800fdf53  test    al, al
0x1800fdf55  jnz     loc_1800FDFF0
0x1800fdf5b  xor     edi, edi
0x1800fdf5d  cmp     edi, 64h ; 'd'
0x1800fdf60  jge     loc_1800FDFF0
0x1800fdf66  movzx   eax, [rsp+288h+var_238]
0x1800fdf6b  neg     ax
0x1800fdf6e  lea     rax, [rsp+288h+var_238]
0x1800fdf73  sbb     r8, r8
0x1800fdf76  xor     edx, edx; bInheritHandle
0x1800fdf78  and     r8, rax; lpName
0x1800fdf7b  lea     ecx, [rdx+4]; dwDesiredAccess
0x1800fdf7e  call    cs:__imp_OpenFileMappingW
0x1800fdf84  mov     rbx, rax
0x1800fdf87  test    rax, rax
0x1800fdf8a  jnz     short loc_1800FDFE5
0x1800fdf8c  movzx   eax, [rsp+288h+var_238]
0x1800fdf91  mov     r8d, 8000002h; flProtect
0x1800fdf97  neg     ax
0x1800fdf9a  lea     rax, [rsp+288h+var_238]
0x1800fdf9f  sbb     rcx, rcx
0x1800fdfa2  and     rcx, rax
0x1800fdfa5  mov     eax, [rsp+288h+var_258]
0x1800fdfa9  neg     eax
0x1800fdfab  mov     [rsp+288h+lpName], rcx; lpName
0x1800fdfb0  lea     rax, [rsp+288h+var_258]
0x1800fdfb5  mov     [rsp+288h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800fdfb9  sbb     rdx, rdx
0x1800fdfbc  mov     rcx, rsi; hFile
0x1800fdfbf  and     rdx, rax; lpFileMappingAttributes
0x1800fdfc2  xor     r9d, r9d; dwMaximumSizeHigh
0x1800fdfc5  call    cs:__imp_CreateFileMappingW
0x1800fdfcb  mov     rbx, rax
0x1800fdfce  test    rax, rax
0x1800fdfd1  jnz     short loc_1800FDFF0
0x1800fdfd3  call    cs:__imp_GetLastError
0x1800fdfd9  cmp     eax, 5
0x1800fdfdc  jnz     short loc_1800FDFF0
0x1800fdfde  inc     edi
0x1800fdfe0  jmp     loc_1800FDF5D
0x1800fdfe5  mov     ecx, 0B7h; dwErrCode
0x1800fdfea  call    cs:__imp_SetLastError
0x1800fdff0  mov     rcx, [rsp+288h+hMem]; hMem
0x1800fdff5  call    cs:__imp_LocalFree
0x1800fdffb  mov     rax, rbx
0x1800fdffe  mov     rcx, [rsp+288h+var_18]
0x1800fe006  xor     rcx, rsp; StackCookie
0x1800fe009  call    __security_check_cookie
0x1800fe00e  lea     r11, [rsp+288h+var_8]
0x1800fe016  mov     rbx, [r11+18h]
0x1800fe01a  mov     rsi, [r11+20h]
0x1800fe01e  mov     rsp, r11
0x1800fe021  pop     rdi
0x1800fe022  retn
```
