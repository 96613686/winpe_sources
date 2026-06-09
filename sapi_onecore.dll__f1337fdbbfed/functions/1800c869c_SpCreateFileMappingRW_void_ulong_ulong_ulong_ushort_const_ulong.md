# SpCreateFileMappingRW(void *,ulong,ulong,ulong,ushort const *,ulong)

- ea: `0x1800c869c`
- end: `0x1800c87bb`
- name: `?SpCreateFileMappingRW@@YAPEAXPEAXKKKPEBGK@Z`
- size: `287`
- prototype: `void *(void *, unsigned int, unsigned int, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800c8308`

## callees

- `0x18000c808`
- `0x18000eb90`
- `0x18000f110`
- `0x180079e30`
- `0x1800c869c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c8782`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c8782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c876b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c876b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c878d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c878d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800c8717`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x1800c8717`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c875d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800c875d`

## pseudocode

```c
HANDLE __fastcall SpCreateFileMappingRW(void *a1, __int64 a2, __int64 a3, DWORD a4)
{
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  HANDLE FileMappingW; // rbx
  int i; // edi
  int v10; // [rsp+30h] [rbp-258h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-250h]
  _WORD v12[272]; // [rsp+50h] [rbp-238h] BYREF

  CSpSecurityAttribute::CSpSecurityAttribute((CSpSecurityAttribute *)&v10, 4u, 6);
  v6 = PrefixedObjectName::Initialize((PrefixedObjectName *)v12, v5, 0);
  FileMappingW = 0;
  if ( !SetLastErrorIfFailed(v6) )
  {
    for ( i = 0; i < 100; ++i )
    {
      FileMappingW = OpenFileMappingW(6u, 0, (LPCWSTR)((unsigned __int64)v12 & -(__int64)(v12[0] != 0)));
      if ( FileMappingW )
      {
        SetLastError(0xB7u);
        break;
      }
      FileMappingW = CreateFileMappingW(
                       (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                       (LPSECURITY_ATTRIBUTES)((unsigned __int64)&v10 & -(__int64)(v10 != 0)),
                       4u,
                       0,
                       a4,
                       (LPCWSTR)((unsigned __int64)v12 & -(__int64)(v12[0] != 0)));
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
0x1800c869c  mov     [rsp+arg_0], rbx
0x1800c86a1  mov     [rsp+arg_8], rsi
0x1800c86a6  push    rdi
0x1800c86a7  sub     rsp, 280h
0x1800c86ae  mov     rax, cs:__security_cookie
0x1800c86b5  xor     rax, rsp
0x1800c86b8  mov     [rsp+288h+var_18], rax
0x1800c86c0  mov     edx, 4; unsigned int
0x1800c86c5  lea     rcx, [rsp+288h+var_258]; this
0x1800c86ca  mov     esi, r9d
0x1800c86cd  lea     r8d, [rdx+2]; unsigned int
0x1800c86d1  call    ??0CSpSecurityAttribute@@QEAA@KK@Z; CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)
0x1800c86d6  xor     r8d, r8d; unsigned __int16 *
0x1800c86d9  lea     rcx, [rsp+288h+var_238]; this
0x1800c86de  call    ?Initialize@PrefixedObjectName@@AEAAJPEBG0@Z; PrefixedObjectName::Initialize(ushort const *,ushort const *)
0x1800c86e3  mov     ecx, eax; int
0x1800c86e5  call    ?SetLastErrorIfFailed@@YA_NJ@Z; SetLastErrorIfFailed(long)
0x1800c86ea  xor     ebx, ebx
0x1800c86ec  test    al, al
0x1800c86ee  jnz     loc_1800C8788
0x1800c86f4  xor     edi, edi
0x1800c86f6  cmp     edi, 64h ; 'd'
0x1800c86f9  jge     loc_1800C8788
0x1800c86ff  movzx   eax, [rsp+288h+var_238]
0x1800c8704  neg     ax
0x1800c8707  lea     rax, [rsp+288h+var_238]
0x1800c870c  sbb     r8, r8
0x1800c870f  xor     edx, edx; bInheritHandle
0x1800c8711  and     r8, rax; lpName
0x1800c8714  lea     ecx, [rdx+6]; dwDesiredAccess
0x1800c8717  call    cs:__imp_OpenFileMappingW
0x1800c871d  mov     rbx, rax
0x1800c8720  test    rax, rax
0x1800c8723  jnz     short loc_1800C877D
0x1800c8725  movzx   eax, [rsp+288h+var_238]
0x1800c872a  lea     r8d, [rbx+4]; flProtect
0x1800c872e  neg     ax
0x1800c8731  lea     rax, [rsp+288h+var_238]
0x1800c8736  sbb     rcx, rcx
0x1800c8739  and     rcx, rax
0x1800c873c  mov     eax, [rsp+288h+var_258]
0x1800c8740  neg     eax
0x1800c8742  mov     [rsp+288h+lpName], rcx; lpName
0x1800c8747  lea     rax, [rsp+288h+var_258]
0x1800c874c  mov     [rsp+288h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x1800c8750  sbb     rdx, rdx
0x1800c8753  xor     r9d, r9d; dwMaximumSizeHigh
0x1800c8756  and     rdx, rax; lpFileMappingAttributes
0x1800c8759  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800c875d  call    cs:__imp_CreateFileMappingW
0x1800c8763  mov     rbx, rax
0x1800c8766  test    rax, rax
0x1800c8769  jnz     short loc_1800C8788
0x1800c876b  call    cs:__imp_GetLastError
0x1800c8771  cmp     eax, 5
0x1800c8774  jnz     short loc_1800C8788
0x1800c8776  inc     edi
0x1800c8778  jmp     loc_1800C86F6
0x1800c877d  mov     ecx, 0B7h; dwErrCode
0x1800c8782  call    cs:__imp_SetLastError
0x1800c8788  mov     rcx, [rsp+288h+hMem]; hMem
0x1800c878d  call    cs:__imp_LocalFree
0x1800c8793  mov     rax, rbx
0x1800c8796  mov     rcx, [rsp+288h+var_18]
0x1800c879e  xor     rcx, rsp; StackCookie
0x1800c87a1  call    __security_check_cookie
0x1800c87a6  lea     r11, [rsp+288h+var_8]
0x1800c87ae  mov     rbx, [r11+10h]
0x1800c87b2  mov     rsi, [r11+18h]
0x1800c87b6  mov     rsp, r11
0x1800c87b9  pop     rdi
0x1800c87ba  retn
```
