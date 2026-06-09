# User::GetSidString(_bstr_t &)

- ea: `0x18003f940`
- end: `0x18003fa3c`
- name: `?GetSidString@User@@QEBAJAEAV_bstr_t@@@Z`
- size: `252`
- prototype: `int(User *__hidden this, struct _bstr_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800538f4`
- `0x18006f0d0`
- `0x18006f5d0`
- `0x18006fd64`

## callees

- `0x18000dc30`
- `0x180030f80`
- `0x18003f940`
- `0x180052118`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003f9a8`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f975`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f9c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f9c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003f96b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003f96b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall User::GetSidString(User *this, struct _bstr_t *a2)
{
  __int64 v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx
  BSTR v7; // rsi
  unsigned int v8; // ebx
  BSTR *v9; // rax
  struct IErrorInfo *v10; // rdx
  BSTR *v11; // rdi
  LPWSTR StringSid; // [rsp+40h] [rbp+8h] BYREF
  BSTR *v13; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR *p_StringSid; // [rsp+58h] [rbp+20h]

  v3 = *(_QWORD *)this;
  if ( !v3 )
    return 2147549183LL;
  StringSid = 0;
  if ( ConvertSidToStringSidW(*(PSID *)(v3 + 32), &StringSid) )
  {
    p_StringSid = &StringSid;
    v7 = SysAllocString(StringSid);
    if ( v7 )
    {
      v9 = (BSTR *)operator new(0x18u);
      v11 = v9;
      v13 = v9;
      if ( v9 )
      {
        v9[1] = 0;
        *((_DWORD *)v9 + 4) = 1;
        *v9 = v7;
      }
      else
      {
        v11 = 0;
      }
      v13 = v11;
      if ( !v11 )
        _com_raise_error(-2147024882, v10);
      _InterlockedIncrement((volatile signed __int32 *)v11 + 4);
      _bstr_t::~_bstr_t(a2);
      *(_QWORD *)a2 = v11;
      _bstr_t::~_bstr_t((_bstr_t *)&v13);
      v8 = 0;
    }
    else
    {
      v8 = -2147024882;
    }
    LocalFree(StringSid);
    return v8;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v5;
  }
}

```

## disassembly

```asm
0x18003f940  mov     [rsp+arg_8], rbx
0x18003f945  push    rbp
0x18003f946  push    rsi
0x18003f947  push    rdi
0x18003f948  sub     rsp, 20h
0x18003f94c  mov     rbx, rdx
0x18003f94f  mov     rcx, [rcx]
0x18003f952  test    rcx, rcx
0x18003f955  jz      loc_18003FA2C
0x18003f95b  xor     ebp, ebp
0x18003f95d  mov     [rsp+38h+StringSid], rbp
0x18003f962  lea     rdx, [rsp+38h+StringSid]; StringSid
0x18003f967  mov     rcx, [rcx+20h]; Sid
0x18003f96b  call    cs:__imp_ConvertSidToStringSidW
0x18003f971  test    eax, eax
0x18003f973  jnz     short loc_18003F999
0x18003f975  call    cs:__imp_GetLastError
0x18003f97b  mov     ebx, eax
0x18003f97d  test    eax, eax
0x18003f97f  jle     short loc_18003F98A
0x18003f981  movzx   ebx, ax
0x18003f984  or      ebx, 80070000h
0x18003f98a  mov     eax, ebx
0x18003f98c  mov     rbx, [rsp+38h+arg_8]
0x18003f991  add     rsp, 20h
0x18003f995  pop     rdi
0x18003f996  pop     rsi
0x18003f997  pop     rbp
0x18003f998  retn
0x18003f999  lea     rax, [rsp+38h+StringSid]
0x18003f99e  mov     [rsp+38h+arg_18], rax
0x18003f9a3  mov     rcx, [rsp+38h+StringSid]; psz
0x18003f9a8  call    cs:__imp_SysAllocString
0x18003f9ae  mov     rsi, rax
0x18003f9b1  test    rax, rax
0x18003f9b4  jnz     short loc_18003F9D5
0x18003f9b6  mov     ebx, 8007000Eh
0x18003f9bb  mov     rcx, [rsp+38h+StringSid]; hMem
0x18003f9c0  call    cs:__imp_LocalFree
0x18003f9c6  mov     eax, ebx
0x18003f9c8  mov     rbx, [rsp+38h+arg_8]
0x18003f9cd  add     rsp, 20h
0x18003f9d1  pop     rdi
0x18003f9d2  pop     rsi
0x18003f9d3  pop     rbp
0x18003f9d4  retn
0x18003f9d5  mov     ecx, 18h; dwBytes
0x18003f9da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f9df  mov     rdi, rax
0x18003f9e2  mov     [rsp+38h+arg_10], rax
0x18003f9e7  test    rax, rax
0x18003f9ea  jz      short loc_18003FA36
0x18003f9ec  mov     [rax+8], rbp
0x18003f9f0  mov     dword ptr [rax+10h], 1
0x18003f9f7  mov     [rax], rsi
0x18003f9fa  mov     [rsp+38h+arg_10], rdi
0x18003f9ff  test    rdi, rdi
0x18003fa02  jnz     short loc_18003FA0F
0x18003fa04  mov     ecx, 8007000Eh; int
0x18003fa09  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x18003fa0f  lock inc dword ptr [rdi+10h]
0x18003fa13  mov     rcx, rbx; this
0x18003fa16  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003fa1b  mov     [rbx], rdi
0x18003fa1e  lea     rcx, [rsp+38h+arg_10]; this
0x18003fa23  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18003fa28  mov     ebx, ebp
0x18003fa2a  jmp     short loc_18003F9BB
0x18003fa2c  mov     eax, 8000FFFFh
0x18003fa31  jmp     loc_18003F98C
0x18003fa36  mov     rdi, rbp
0x18003fa39  jmp     short loc_18003F9FA
```
