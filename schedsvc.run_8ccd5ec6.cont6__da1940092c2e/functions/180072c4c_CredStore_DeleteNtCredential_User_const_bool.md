# CredStore::DeleteNtCredential(User const &,bool)

- ea: `0x180072c4c`
- end: `0x180072cce`
- name: `?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z`
- size: `130`
- prototype: `__int64 __fastcall(CredStore *__hidden this, const struct User *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d7ac`
- `0x180047ee0`

## callees

- `0x18000cc40`
- `0x18005616c`
- `0x180072c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ca0`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180072c7d`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180072c7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredStore::DeleteNtCredential(struct _RTL_CRITICAL_SECTION *this, const struct User *a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  LPCWSTR TargetName; // [rsp+48h] [rbp+20h] BYREF

  TargetName = 0;
  v2 = CredStore::ReleaseRefUserRecord(this, a2, (unsigned __int16 **)&TargetName);
  if ( !v2 && !CredDeleteW(TargetName, 2u, 0x4004u) && GetLastError() != 1168 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  operator delete((void *)TargetName);
  return v2;
}

```

## disassembly

```asm
0x180072c4c  push    rbx
0x180072c4e  sub     rsp, 20h
0x180072c52  mov     [rsp+28h+TargetName], 0
0x180072c5b  lea     r8, [rsp+28h+TargetName]
0x180072c60  call    ?ReleaseRefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::ReleaseRefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)
0x180072c65  mov     ebx, eax
0x180072c67  test    eax, eax
0x180072c69  js      short loc_180072CBB
0x180072c6b  test    eax, eax
0x180072c6d  jnz     short loc_180072CBB
0x180072c6f  lea     edx, [rax+2]; Type
0x180072c72  mov     r8d, 4004h; Flags
0x180072c78  mov     rcx, [rsp+28h+TargetName]; TargetName
0x180072c7d  call    cs:__imp_CredDeleteW
0x180072c84  nop     dword ptr [rax+rax+00h]
0x180072c89  test    eax, eax
0x180072c8b  jnz     short loc_180072CBB
0x180072c8d  call    cs:__imp_GetLastError
0x180072c94  nop     dword ptr [rax+rax+00h]
0x180072c99  cmp     eax, 490h
0x180072c9e  jz      short loc_180072CBB
0x180072ca0  call    cs:__imp_GetLastError
0x180072ca7  nop     dword ptr [rax+rax+00h]
0x180072cac  mov     ebx, eax
0x180072cae  test    eax, eax
0x180072cb0  jle     short loc_180072CBB
0x180072cb2  movzx   ebx, ax
0x180072cb5  or      ebx, 80070000h
0x180072cbb  mov     rcx, [rsp+28h+TargetName]; void *
0x180072cc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180072cc5  mov     eax, ebx
0x180072cc7  add     rsp, 20h
0x180072ccb  pop     rbx
0x180072ccc  retn
```
