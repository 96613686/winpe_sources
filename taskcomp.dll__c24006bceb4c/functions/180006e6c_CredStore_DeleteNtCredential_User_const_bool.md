# CredStore::DeleteNtCredential(User const &,bool)

- ea: `0x180006e6c`
- end: `0x180006f02`
- name: `?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z`
- size: `150`
- prototype: `__int64 __fastcall(CredStore *this, const struct User *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005b98`

## callees

- `0x180004e50`
- `0x180006e6c`
- `0x180007100`
- `0x1800074c8`
- `0x18001726c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006edb`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180006ec4`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180006ec4`

## pseudocode

```c
__int64 __fastcall CredStore::DeleteNtCredential(CredStore *this, const struct User *a2)
{
  unsigned __int16 *v2; // rcx
  unsigned int AliasCredId; // ebx
  signed int LastError; // eax
  char v6; // [rsp+48h] [rbp+20h] BYREF

  v2 = *(unsigned __int16 **)User::GetAccount(a2, &v6);
  if ( v2 )
    v2 = *(unsigned __int16 **)v2;
  AliasCredId = CredStore::GetAliasCredId(v2);
  _bstr_t::~_bstr_t((_bstr_t *)&v6);
  if ( !AliasCredId && !CredDeleteW(0, 2u, 0x4004u) && GetLastError() != 1168 )
  {
    LastError = GetLastError();
    AliasCredId = LastError;
    if ( LastError > 0 )
      AliasCredId = (unsigned __int16)LastError | 0x80070000;
  }
  operator delete(0);
  return AliasCredId;
}

```

## disassembly

```asm
0x180006e6c  mov     [rsp+TargetName], rcx
0x180006e71  push    rbx
0x180006e72  sub     rsp, 20h
0x180006e76  mov     rcx, rdx
0x180006e79  mov     [rsp+28h+TargetName], 0
0x180006e82  lea     rdx, [rsp+28h+arg_18]
0x180006e87  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180006e8c  nop
0x180006e8d  mov     rcx, [rax]
0x180006e90  test    rcx, rcx
0x180006e93  jz      short loc_180006E98
0x180006e95  mov     rcx, [rcx]; unsigned __int16 *
0x180006e98  lea     rdx, [rsp+28h+TargetName]
0x180006e9d  call    ?GetAliasCredId@CredStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetAliasCredId(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180006ea2  mov     ebx, eax
0x180006ea4  lea     rcx, [rsp+28h+arg_18]; this
0x180006ea9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180006eae  test    ebx, ebx
0x180006eb0  js      short loc_180006EF0
0x180006eb2  jnz     short loc_180006EF0
0x180006eb4  mov     edx, 2; Type
0x180006eb9  mov     r8d, 4004h; Flags
0x180006ebf  mov     rcx, [rsp+28h+TargetName]; TargetName
0x180006ec4  call    cs:__imp_CredDeleteW
0x180006eca  test    eax, eax
0x180006ecc  jnz     short loc_180006EF0
0x180006ece  call    cs:__imp_GetLastError
0x180006ed4  cmp     eax, 490h
0x180006ed9  jz      short loc_180006EF0
0x180006edb  call    cs:__imp_GetLastError
0x180006ee1  mov     ebx, eax
0x180006ee3  test    eax, eax
0x180006ee5  jle     short loc_180006EF0
0x180006ee7  movzx   ebx, ax
0x180006eea  or      ebx, 80070000h
0x180006ef0  mov     rcx, [rsp+28h+TargetName]; Block
0x180006ef5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006efa  mov     eax, ebx
0x180006efc  add     rsp, 20h
0x180006f00  pop     rbx
0x180006f01  retn
```
