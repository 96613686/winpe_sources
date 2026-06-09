# SHCoCreateInstanceAC

- ea: `0x18002c3e0`
- end: `0x18002c468`
- name: `SHCoCreateInstanceAC`
- size: `136`
- prototype: `__int64 __fastcall(IID *rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, IID *riid, LPVOID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012550`
- `0x18002c3e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c44a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002c44a`
- `apphelp!ApphelpCheckShellObject` at `0x18002c428`
- `apphelp!ApphelpCheckShellObject` at `0x18002c428`

## pseudocode

```c
HRESULT __fastcall SHCoCreateInstanceAC(IID *rclsid, LPUNKNOWN pUnkOuter, DWORD dwClsContext, IID *riid, LPVOID *ppv)
{
  ULONGLONG pullFlags; // [rsp+30h] [rbp-38h] BYREF

  pullFlags = 0;
  *ppv = 0;
  if ( ApphelpCheckShellObject(rclsid, 1, &pullFlags) )
    return CoCreateInstance(rclsid, pUnkOuter, dwClsContext, riid, ppv);
  else
    return -2147024891;
}

```

## disassembly

```asm
0x18002c3e0  push    rbx
0x18002c3e2  push    rbp
0x18002c3e3  push    rsi
0x18002c3e4  push    rdi
0x18002c3e5  push    r14
0x18002c3e7  sub     rsp, 40h
0x18002c3eb  mov     rax, cs:__security_cookie
0x18002c3f2  xor     rax, rsp
0x18002c3f5  mov     [rsp+68h+var_30], rax
0x18002c3fa  mov     rdi, [rsp+68h+arg_20]
0x18002c402  mov     ebp, r8d
0x18002c405  mov     rsi, rdx
0x18002c408  mov     [rsp+68h+pullFlags], 0
0x18002c411  lea     r8, [rsp+68h+pullFlags]; pullFlags
0x18002c416  mov     edx, 1; bShimIfNecessary
0x18002c41b  mov     r14, r9
0x18002c41e  mov     rbx, rcx
0x18002c421  mov     qword ptr [rdi], 0
0x18002c428  call    cs:__imp_ApphelpCheckShellObject
0x18002c42e  test    eax, eax
0x18002c430  jnz     short loc_18002C439
0x18002c432  mov     eax, 80070005h
0x18002c437  jmp     short loc_18002C450
0x18002c439  mov     r9, r14; riid
0x18002c43c  mov     [rsp+68h+ppv], rdi; ppv
0x18002c441  mov     r8d, ebp; dwClsContext
0x18002c444  mov     rdx, rsi; pUnkOuter
0x18002c447  mov     rcx, rbx; rclsid
0x18002c44a  call    cs:__imp_CoCreateInstance
0x18002c450  mov     rcx, [rsp+68h+var_30]
0x18002c455  xor     rcx, rsp; StackCookie
0x18002c458  call    __security_check_cookie
0x18002c45d  add     rsp, 40h
0x18002c461  pop     r14
0x18002c463  pop     rdi
0x18002c464  pop     rsi
0x18002c465  pop     rbp
0x18002c466  pop     rbx
0x18002c467  retn
```
