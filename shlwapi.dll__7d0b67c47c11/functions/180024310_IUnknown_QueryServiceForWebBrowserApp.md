# IUnknown_QueryServiceForWebBrowserApp

- ea: `0x180024310`
- end: `0x1800243a4`
- name: `IUnknown_QueryServiceForWebBrowserApp`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800243b0`

## callees

- `0x180012550`
- `0x180024310`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180024350`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180024350`

## pseudocode

```c
__int64 __fastcall IUnknown_QueryServiceForWebBrowserApp(IUnknown *a1, __int64 a2, _QWORD *a3)
{
  HRESULT v5; // ebx
  void *ppvOut; // [rsp+30h] [rbp-28h] BYREF

  *a3 = 0;
  ppvOut = 0;
  v5 = IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
         &ppvOut);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(void *, GUID *, __int64, _QWORD *))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           &IID_IWebBrowserApp,
           a2,
           a3);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024310  push    rbx
0x180024312  push    rsi
0x180024313  push    rdi
0x180024314  sub     rsp, 40h
0x180024318  mov     rax, cs:__security_cookie
0x18002431f  xor     rax, rsp
0x180024322  mov     [rsp+58h+var_20], rax
0x180024327  mov     rdi, r8
0x18002432a  mov     qword ptr [r8], 0
0x180024331  mov     rsi, rdx
0x180024334  mov     [rsp+58h+ppvOut], 0
0x18002433d  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180024344  lea     rdx, SID_STopLevelBrowser; guidService
0x18002434b  lea     r9, [rsp+58h+ppvOut]; ppvOut
0x180024350  call    cs:__imp_IUnknown_QueryService
0x180024356  mov     ebx, eax
0x180024358  test    eax, eax
0x18002435a  js      short loc_18002438D
0x18002435c  mov     rcx, [rsp+58h+ppvOut]
0x180024361  lea     rdx, IID_IWebBrowserApp
0x180024368  mov     r9, rdi
0x18002436b  mov     r8, rsi
0x18002436e  mov     rax, [rcx]
0x180024371  mov     rax, [rax+18h]
0x180024375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002437a  mov     rcx, [rsp+58h+ppvOut]
0x18002437f  mov     ebx, eax
0x180024381  mov     rax, [rcx]
0x180024384  mov     rax, [rax+10h]
0x180024388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002438d  mov     eax, ebx
0x18002438f  mov     rcx, [rsp+58h+var_20]
0x180024394  xor     rcx, rsp; StackCookie
0x180024397  call    __security_check_cookie
0x18002439c  add     rsp, 40h
0x1800243a0  pop     rdi
0x1800243a1  pop     rsi
0x1800243a2  pop     rbx
0x1800243a3  retn
```
