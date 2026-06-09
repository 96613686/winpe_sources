# CredStore::DeleteNtCredential(User const &,bool)

- ea: `0x1800072c0`
- end: `0x180007369`
- name: `?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z`
- size: `169`
- prototype: `__int64 __fastcall(CredStore *__hidden this, const struct User *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005efc`

## callees

- `0x1800050d0`
- `0x1800072c0`
- `0x18000757c`
- `0x180007988`
- `0x18001824c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000733b`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180007318`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180007318`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800072c0  mov     [rsp+TargetName], rcx
0x1800072c5  push    rbx
0x1800072c6  sub     rsp, 20h
0x1800072ca  mov     rcx, rdx
0x1800072cd  mov     [rsp+28h+TargetName], 0
0x1800072d6  lea     rdx, [rsp+28h+arg_18]
0x1800072db  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x1800072e0  nop
0x1800072e1  mov     rcx, [rax]
0x1800072e4  test    rcx, rcx
0x1800072e7  jz      short loc_1800072EC
0x1800072e9  mov     rcx, [rcx]; unsigned __int16 *
0x1800072ec  lea     rdx, [rsp+28h+TargetName]
0x1800072f1  call    ?GetAliasCredId@CredStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::GetAliasCredId(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x1800072f6  mov     ebx, eax
0x1800072f8  lea     rcx, [rsp+28h+arg_18]; this
0x1800072fd  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180007302  test    ebx, ebx
0x180007304  js      short loc_180007356
0x180007306  jnz     short loc_180007356
0x180007308  mov     edx, 2; Type
0x18000730d  mov     r8d, 4004h; Flags
0x180007313  mov     rcx, [rsp+28h+TargetName]; TargetName
0x180007318  call    cs:__imp_CredDeleteW
0x18000731f  nop     dword ptr [rax+rax+00h]
0x180007324  test    eax, eax
0x180007326  jnz     short loc_180007356
0x180007328  call    cs:__imp_GetLastError
0x18000732f  nop     dword ptr [rax+rax+00h]
0x180007334  cmp     eax, 490h
0x180007339  jz      short loc_180007356
0x18000733b  call    cs:__imp_GetLastError
0x180007342  nop     dword ptr [rax+rax+00h]
0x180007347  mov     ebx, eax
0x180007349  test    eax, eax
0x18000734b  jle     short loc_180007356
0x18000734d  movzx   ebx, ax
0x180007350  or      ebx, 80070000h
0x180007356  mov     rcx, [rsp+28h+TargetName]; Block
0x18000735b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007360  mov     eax, ebx
0x180007362  add     rsp, 20h
0x180007366  pop     rbx
0x180007367  retn
```
