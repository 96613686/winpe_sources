# CanConvertToUnicode(uint)

- ea: `0x100401520`
- end: `0x1004015b3`
- name: `?CanConvertToUnicode@@YAJI@Z`
- size: `147`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100418330`
- `0x1004186a0`
- `0x10041b970`
- `0x100423260`

## callees

- `0x100401520`
- `0x100439df0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x100401557`
- `ole32!CoCreateInstance` at `0x100401557`

## pseudocode

```c
HRESULT __fastcall CanConvertToUnicode(unsigned int a1)
{
  struct IMultiLanguage2 *v2; // rcx
  HRESULT result; // eax
  bool v4; // zf
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v2 = s_pMultiLanguage2;
  if ( s_pMultiLanguage2 )
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, _QWORD, __int64))v2->lpVtbl->IsConvertible)(v2, a1, 1200);
  ppv = 0;
  result = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
  v4 = result == 0;
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    result = 0;
    v4 = 1;
  }
  if ( v4 )
  {
    v2 = s_pMultiLanguage2;
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, _QWORD, __int64))v2->lpVtbl->IsConvertible)(v2, a1, 1200);
  }
  return result;
}

```

## disassembly

```asm
0x100401520  push    rbx
0x100401522  sub     rsp, 30h
0x100401526  mov     ebx, ecx
0x100401528  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x10040152f  test    rcx, rcx
0x100401532  jnz     short loc_100401592
0x100401534  mov     [rsp+38h+arg_8], rcx
0x100401539  lea     rax, [rsp+38h+arg_8]
0x10040153e  lea     r8d, [rcx+1]; dwClsContext
0x100401542  mov     [rsp+38h+ppv], rax; ppv
0x100401547  lea     rcx, CLSID_CMultiLanguage; rclsid
0x10040154e  xor     edx, edx; pUnkOuter
0x100401550  lea     r9, IID_IMultiLanguage2; riid
0x100401557  call    cs:__imp_CoCreateInstance
0x10040155d  test    eax, eax
0x10040155f  js      short loc_100401589
0x100401561  mov     rcx, [rsp+38h+arg_8]
0x100401566  xor     eax, eax
0x100401568  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x100401571  jz      short loc_100401585
0x100401573  mov     rcx, [rsp+38h+arg_8]
0x100401578  mov     rax, [rcx]
0x10040157b  mov     rax, [rax+10h]
0x10040157f  call    cs:__guard_dispatch_icall_fptr
0x100401585  xor     eax, eax
0x100401587  test    eax, eax
0x100401589  jnz     short loc_1004015AD
0x10040158b  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100401592  mov     rax, [rcx]
0x100401595  mov     r8d, 4B0h
0x10040159b  mov     edx, ebx
0x10040159d  mov     rax, [rax+40h]
0x1004015a1  add     rsp, 30h
0x1004015a5  pop     rbx
0x1004015a6  jmp     cs:__guard_dispatch_icall_fptr
0x1004015ad  add     rsp, 30h
0x1004015b1  pop     rbx
0x1004015b2  retn
```
