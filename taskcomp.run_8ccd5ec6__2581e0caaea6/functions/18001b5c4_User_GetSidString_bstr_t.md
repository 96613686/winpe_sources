# User::GetSidString(_bstr_t &)

- ea: `0x18001b5c4`
- end: `0x18001b683`
- name: `?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(User *__hidden this, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019214`

## callees

- `0x180003f7c`
- `0x1800050d0`
- `0x1800051c4`
- `0x18001b5c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b65f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b65f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b651`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b610`
- `OLEAUT32!__imp_SysAllocString` at `0x18001b610`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001b5f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001b5f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall User::GetSidString(User *this, struct _bstr_t *a2)
{
  __int64 v3; // rcx
  unsigned __int16 *v5; // rax
  bool v6; // r8
  _bstr_t *v7; // rax
  unsigned int v8; // ebx
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  char v11; // [rsp+40h] [rbp+18h] BYREF
  LPWSTR *p_StringSid; // [rsp+48h] [rbp+20h]

  v3 = *(_QWORD *)this;
  if ( !v3 )
    return 2147549183LL;
  StringSid = 0;
  if ( ConvertSidToStringSidW(*(PSID *)(v3 + 32), &StringSid) )
  {
    p_StringSid = &StringSid;
    v5 = SysAllocString(StringSid);
    if ( v5 )
    {
      v7 = _bstr_t::_bstr_t((_bstr_t *)&v11, v5, v6);
      _bstr_t::operator=(a2, v7);
      _bstr_t::~_bstr_t((_bstr_t *)&v11);
      v8 = 0;
    }
    else
    {
      v8 = -2147024882;
    }
    LocalFree(StringSid);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x18001b5c4  push    rbx
0x18001b5c6  sub     rsp, 20h
0x18001b5ca  mov     rbx, rdx
0x18001b5cd  mov     rcx, [rcx]
0x18001b5d0  test    rcx, rcx
0x18001b5d3  jnz     short loc_18001B5DF
0x18001b5d5  mov     eax, 8000FFFFh
0x18001b5da  jmp     loc_18001B67C
0x18001b5df  mov     [rsp+28h+StringSid], 0
0x18001b5e8  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18001b5ed  mov     rcx, [rcx+20h]; Sid
0x18001b5f1  call    cs:__imp_ConvertSidToStringSidW
0x18001b5f8  nop     dword ptr [rax+rax+00h]
0x18001b5fd  test    eax, eax
0x18001b5ff  jz      short loc_18001B65F
0x18001b601  lea     rax, [rsp+28h+StringSid]
0x18001b606  mov     [rsp+28h+arg_18], rax
0x18001b60b  mov     rcx, [rsp+28h+StringSid]; psz
0x18001b610  call    cs:__imp_SysAllocString
0x18001b617  nop     dword ptr [rax+rax+00h]
0x18001b61c  test    rax, rax
0x18001b61f  jz      short loc_18001B647
0x18001b621  mov     rdx, rax; unsigned __int16 *
0x18001b624  lea     rcx, [rsp+28h+arg_10]; this
0x18001b629  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001b62e  mov     rdx, rax
0x18001b631  mov     rcx, rbx
0x18001b634  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001b639  lea     rcx, [rsp+28h+arg_10]; this
0x18001b63e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001b643  xor     ebx, ebx
0x18001b645  jmp     short loc_18001B64C
0x18001b647  mov     ebx, 8007000Eh
0x18001b64c  mov     rcx, [rsp+28h+StringSid]; hMem
0x18001b651  call    cs:__imp_LocalFree
0x18001b658  nop     dword ptr [rax+rax+00h]
0x18001b65d  jmp     short loc_18001B67A
0x18001b65f  call    cs:__imp_GetLastError
0x18001b666  nop     dword ptr [rax+rax+00h]
0x18001b66b  mov     ebx, eax
0x18001b66d  test    eax, eax
0x18001b66f  jle     short loc_18001B67A
0x18001b671  movzx   ebx, ax
0x18001b674  or      ebx, 80070000h
0x18001b67a  mov     eax, ebx
0x18001b67c  add     rsp, 20h
0x18001b680  pop     rbx
0x18001b681  retn
```
