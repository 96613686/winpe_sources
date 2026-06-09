# IUnknown_DoContextMenuPopup

- ea: `0x180024010`
- end: `0x18002409e`
- name: `IUnknown_DoContextMenuPopup`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012550`
- `0x180024010`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002404d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002404d`

## pseudocode

```c
__int64 __fastcall IUnknown_DoContextMenuPopup(IUnknown *a1, __int64 a2, unsigned int a3, __int64 a4)
{
  HRESULT v7; // edi
  void *ppvOut; // [rsp+30h] [rbp-38h] BYREF

  ppvOut = 0;
  v7 = IUnknown_QueryService(a1, &IID_IContextMenuSite, &GUID_0811aebe_0b87_4c54_9e72_548cf649016b, &ppvOut);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, __int64))(*(_QWORD *)ppvOut + 24LL))(ppvOut, a2, a3, a4);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024010  push    rbx
0x180024012  push    rbp
0x180024013  push    rsi
0x180024014  push    rdi
0x180024015  sub     rsp, 48h
0x180024019  mov     rax, cs:__security_cookie
0x180024020  xor     rax, rsp
0x180024023  mov     [rsp+68h+var_30], rax
0x180024028  mov     rbx, r9
0x18002402b  mov     [rsp+68h+ppvOut], 0
0x180024034  mov     ebp, r8d
0x180024037  lea     r9, [rsp+68h+ppvOut]; ppvOut
0x18002403c  mov     rsi, rdx
0x18002403f  lea     r8, _GUID_0811aebe_0b87_4c54_9e72_548cf649016b; riid
0x180024046  lea     rdx, IID_IContextMenuSite; guidService
0x18002404d  call    cs:__imp_IUnknown_QueryService
0x180024053  mov     edi, eax
0x180024055  test    eax, eax
0x180024057  js      short loc_180024086
0x180024059  mov     rcx, [rsp+68h+ppvOut]
0x18002405e  mov     r9, rbx
0x180024061  mov     r8d, ebp
0x180024064  mov     rdx, rsi
0x180024067  mov     rax, [rcx]
0x18002406a  mov     rax, [rax+18h]
0x18002406e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024073  mov     rcx, [rsp+68h+ppvOut]
0x180024078  mov     edi, eax
0x18002407a  mov     rax, [rcx]
0x18002407d  mov     rax, [rax+10h]
0x180024081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024086  mov     eax, edi
0x180024088  mov     rcx, [rsp+68h+var_30]
0x18002408d  xor     rcx, rsp; StackCookie
0x180024090  call    __security_check_cookie
0x180024095  add     rsp, 48h
0x180024099  pop     rdi
0x18002409a  pop     rsi
0x18002409b  pop     rbp
0x18002409c  pop     rbx
0x18002409d  retn
```
