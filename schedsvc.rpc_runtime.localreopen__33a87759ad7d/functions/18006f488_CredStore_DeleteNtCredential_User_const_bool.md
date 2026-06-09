# CredStore::DeleteNtCredential(User const &,bool)

- ea: `0x18006f488`
- end: `0x18006f4f7`
- name: `?DeleteNtCredential@CredStore@@QEAAJAEBVUser@@_N@Z`
- size: `111`
- prototype: `__int64 __fastcall(CredStore *__hidden this, const struct User *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800213f8`
- `0x180045df0`

## callees

- `0x18001a260`
- `0x1800538f4`
- `0x18006f488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4d0`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18006f4b9`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18006f4b9`

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
0x18006f488  push    rbx
0x18006f48a  sub     rsp, 20h
0x18006f48e  mov     [rsp+28h+TargetName], 0
0x18006f497  lea     r8, [rsp+28h+TargetName]
0x18006f49c  call    ?ReleaseRefUserRecord@CredStore@@AEAAJAEBVUser@@AEAV?$AutoVectorPtr@G@wmi@@@Z; CredStore::ReleaseRefUserRecord(User const &,wmi::AutoVectorPtr<ushort> &)
0x18006f4a1  mov     ebx, eax
0x18006f4a3  test    eax, eax
0x18006f4a5  js      short loc_18006F4E5
0x18006f4a7  test    eax, eax
0x18006f4a9  jnz     short loc_18006F4E5
0x18006f4ab  lea     edx, [rax+2]; Type
0x18006f4ae  mov     r8d, 4004h; Flags
0x18006f4b4  mov     rcx, [rsp+28h+TargetName]; TargetName
0x18006f4b9  call    cs:__imp_CredDeleteW
0x18006f4bf  test    eax, eax
0x18006f4c1  jnz     short loc_18006F4E5
0x18006f4c3  call    cs:__imp_GetLastError
0x18006f4c9  cmp     eax, 490h
0x18006f4ce  jz      short loc_18006F4E5
0x18006f4d0  call    cs:__imp_GetLastError
0x18006f4d6  mov     ebx, eax
0x18006f4d8  test    eax, eax
0x18006f4da  jle     short loc_18006F4E5
0x18006f4dc  movzx   ebx, ax
0x18006f4df  or      ebx, 80070000h
0x18006f4e5  mov     rcx, [rsp+28h+TargetName]; void *
0x18006f4ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006f4ef  mov     eax, ebx
0x18006f4f1  add     rsp, 20h
0x18006f4f5  pop     rbx
0x18006f4f6  retn
```
