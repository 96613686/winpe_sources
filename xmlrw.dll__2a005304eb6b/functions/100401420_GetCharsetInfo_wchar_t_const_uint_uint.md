# GetCharsetInfo(wchar_t const *,uint *,uint *)

- ea: `0x100401420`
- end: `0x10040150c`
- name: `?GetCharsetInfo@@YAJPEB_WPEAI1@Z`
- size: `236`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100418330`
- `0x10041b970`
- `0x100420450`

## callees

- `0x100401420`
- `0x100426580`
- `0x100439df0`

## import_xrefs

- `KERNEL32!GetCPInfo` at `0x1004014db`
- `KERNEL32!GetCPInfo` at `0x1004014db`
- `ole32!CoCreateInstance` at `0x100401475`
- `ole32!CoCreateInstance` at `0x100401475`

## pseudocode

```c
HRESULT __fastcall GetCharsetInfo(const wchar_t *a1, unsigned int *a2, unsigned int *a3)
{
  struct IMultiLanguage2 *v5; // rcx
  HRESULT result; // eax
  bool v8; // zf
  UINT v9; // ecx
  UINT MaxCharSize; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-B8h] BYREF
  _cpinfo CPInfo; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE v13[4]; // [rsp+50h] [rbp-98h] BYREF
  UINT CodePage; // [rsp+54h] [rbp-94h]

  v5 = s_pMultiLanguage2;
  if ( s_pMultiLanguage2 )
  {
LABEL_8:
    result = ((__int64 (__fastcall *)(struct IMultiLanguage2 *, const wchar_t *, _BYTE *))v5->lpVtbl->GetCharsetInfo)(
               v5,
               a1,
               v13);
    if ( !result )
    {
      v9 = CodePage;
      *a2 = CodePage;
      if ( a3 )
      {
        v8 = !GetCPInfo(v9, &CPInfo);
        MaxCharSize = 4;
        result = 0;
        if ( !v8 )
          MaxCharSize = CPInfo.MaxCharSize;
        *a3 = MaxCharSize;
      }
    }
    return result;
  }
  ppv = 0;
  result = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
  v8 = result == 0;
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    result = 0;
    v8 = 1;
  }
  if ( v8 )
  {
    v5 = s_pMultiLanguage2;
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x100401420  push    rbx
0x100401422  push    rsi
0x100401423  push    rdi
0x100401424  sub     rsp, 0D0h
0x10040142b  mov     rax, cs:__security_cookie
0x100401432  xor     rax, rsp
0x100401435  mov     [rsp+0E8h+var_28], rax
0x10040143d  mov     rbx, rcx
0x100401440  mov     rdi, r8
0x100401443  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10040144a  mov     rsi, rdx
0x10040144d  test    rcx, rcx
0x100401450  jnz     short loc_1004014B0
0x100401452  mov     [rsp+0E8h+var_B8], rcx
0x100401457  lea     rax, [rsp+0E8h+var_B8]
0x10040145c  lea     r8d, [rcx+1]; dwClsContext
0x100401460  mov     [rsp+0E8h+ppv], rax; ppv
0x100401465  lea     rcx, CLSID_CMultiLanguage; rclsid
0x10040146c  xor     edx, edx; pUnkOuter
0x10040146e  lea     r9, IID_IMultiLanguage2; riid
0x100401475  call    cs:__imp_CoCreateInstance
0x10040147b  test    eax, eax
0x10040147d  js      short loc_1004014A7
0x10040147f  mov     rcx, [rsp+0E8h+var_B8]
0x100401484  xor     eax, eax
0x100401486  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x10040148f  jz      short loc_1004014A3
0x100401491  mov     rcx, [rsp+0E8h+var_B8]
0x100401496  mov     rax, [rcx]
0x100401499  mov     rax, [rax+10h]
0x10040149d  call    cs:__guard_dispatch_icall_fptr
0x1004014a3  xor     eax, eax
0x1004014a5  test    eax, eax
0x1004014a7  jnz     short loc_1004014F1
0x1004014a9  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x1004014b0  mov     rax, [rcx]
0x1004014b3  lea     r8, [rsp+0E8h+var_98]
0x1004014b8  mov     rdx, rbx
0x1004014bb  mov     rax, [rax+38h]
0x1004014bf  call    cs:__guard_dispatch_icall_fptr
0x1004014c5  mov     ebx, eax
0x1004014c7  test    eax, eax
0x1004014c9  jnz     short loc_1004014F1
0x1004014cb  mov     ecx, [rsp+0E8h+CodePage]; CodePage
0x1004014cf  mov     [rsi], ecx
0x1004014d1  test    rdi, rdi
0x1004014d4  jz      short loc_1004014F1
0x1004014d6  lea     rdx, [rsp+0E8h+CPInfo]; lpCPInfo
0x1004014db  call    cs:__imp_GetCPInfo
0x1004014e1  test    eax, eax
0x1004014e3  mov     ecx, 4
0x1004014e8  mov     eax, ebx
0x1004014ea  cmovnz  ecx, [rsp+0E8h+CPInfo.MaxCharSize]
0x1004014ef  mov     [rdi], ecx
0x1004014f1  mov     rcx, [rsp+0E8h+var_28]
0x1004014f9  xor     rcx, rsp; StackCookie
0x1004014fc  call    __security_check_cookie
0x100401501  add     rsp, 0D0h
0x100401508  pop     rdi
0x100401509  pop     rsi
0x10040150a  pop     rbx
0x10040150b  retn
```
