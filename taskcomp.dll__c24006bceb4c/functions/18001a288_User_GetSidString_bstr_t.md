# User::GetSidString(_bstr_t &)

- ea: `0x18001a288`
- end: `0x18001a32e`
- name: `?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(User *__hidden this, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018108`

## callees

- `0x180003dac`
- `0x180004e50`
- `0x180004f28`
- `0x18001a288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a309`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a2ce`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a2ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a2b5`

## pseudocode

```c
__int64 __fastcall User::GetSidString(User *this, struct _bstr_t *a2)
{
  __int64 v3; // rcx
  unsigned __int16 *v5; // rax
  _bstr_t *v6; // rax
  unsigned int v7; // ebx
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  char v10; // [rsp+40h] [rbp+18h] BYREF
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
      v6 = _bstr_t::_bstr_t((_bstr_t *)&v10, v5);
      _bstr_t::operator=(a2, (__int64)v6);
      _bstr_t::~_bstr_t((_bstr_t *)&v10);
      v7 = 0;
    }
    else
    {
      v7 = -2147024882;
    }
    LocalFree(StringSid);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v7;
}

```

## disassembly

```asm
0x18001a288  push    rbx
0x18001a28a  sub     rsp, 20h
0x18001a28e  mov     rbx, rdx
0x18001a291  mov     rcx, [rcx]
0x18001a294  test    rcx, rcx
0x18001a297  jnz     short loc_18001A2A3
0x18001a299  mov     eax, 8000FFFFh
0x18001a29e  jmp     loc_18001A328
0x18001a2a3  mov     [rsp+28h+StringSid], 0
0x18001a2ac  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18001a2b1  mov     rcx, [rcx+20h]; Sid
0x18001a2b5  call    cs:__imp_ConvertSidToStringSidW
0x18001a2bb  test    eax, eax
0x18001a2bd  jz      short loc_18001A311
0x18001a2bf  lea     rax, [rsp+28h+StringSid]
0x18001a2c4  mov     [rsp+28h+arg_18], rax
0x18001a2c9  mov     rcx, [rsp+28h+StringSid]; psz
0x18001a2ce  call    cs:__imp_SysAllocString
0x18001a2d4  test    rax, rax
0x18001a2d7  jz      short loc_18001A2FF
0x18001a2d9  mov     rdx, rax; unsigned __int16 *
0x18001a2dc  lea     rcx, [rsp+28h+arg_10]; this
0x18001a2e1  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18001a2e6  mov     rdx, rax
0x18001a2e9  mov     rcx, rbx
0x18001a2ec  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18001a2f1  lea     rcx, [rsp+28h+arg_10]; this
0x18001a2f6  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001a2fb  xor     ebx, ebx
0x18001a2fd  jmp     short loc_18001A304
0x18001a2ff  mov     ebx, 8007000Eh
0x18001a304  mov     rcx, [rsp+28h+StringSid]; hMem
0x18001a309  call    cs:__imp_LocalFree
0x18001a30f  jmp     short loc_18001A326
0x18001a311  call    cs:__imp_GetLastError
0x18001a317  mov     ebx, eax
0x18001a319  test    eax, eax
0x18001a31b  jle     short loc_18001A326
0x18001a31d  movzx   ebx, ax
0x18001a320  or      ebx, 80070000h
0x18001a326  mov     eax, ebx
0x18001a328  add     rsp, 20h
0x18001a32c  pop     rbx
0x18001a32d  retn
```
