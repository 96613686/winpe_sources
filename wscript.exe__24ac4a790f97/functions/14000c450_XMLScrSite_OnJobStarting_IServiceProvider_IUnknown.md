# XMLScrSite::OnJobStarting(IServiceProvider *,IUnknown *)

- ea: `0x14000c450`
- end: `0x14000c4b1`
- name: `?OnJobStarting@XMLScrSite@@UEAAJPEAUIServiceProvider@@PEAUIUnknown@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, struct IServiceProvider *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x140008558`
- `0x14000c450`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnJobStarting(CHost **this, struct IServiceProvider *a2, struct IUnknown *a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  struct IDispatch *v6; // [rsp+40h] [rbp+18h] BYREF

  lpVtbl = a3->lpVtbl;
  v6 = 0;
  if ( ((int (__fastcall *)(struct IUnknown *, GUID *, struct IDispatch **))lpVtbl->QueryInterface)(
         a3,
         &IID_IDispatch,
         &v6) < 0 )
    return 2147500037LL;
  CHost::SetScriptDispatch(this[2], v6);
  ((void (__fastcall *)(struct IDispatch *))v6->lpVtbl->Release)(v6);
  return 0;
}

```

## disassembly

```asm
0x14000c450  push    rbx
0x14000c452  sub     rsp, 20h
0x14000c456  mov     rax, [r8]
0x14000c459  lea     rdx, IID_IDispatch
0x14000c460  mov     r9, r8
0x14000c463  mov     [rsp+28h+arg_10], 0
0x14000c46c  mov     rbx, rcx
0x14000c46f  lea     r8, [rsp+28h+arg_10]
0x14000c474  mov     rcx, r9
0x14000c477  mov     rax, [rax]
0x14000c47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c47f  test    eax, eax
0x14000c481  jns     short loc_14000C48A
0x14000c483  mov     eax, 80004005h
0x14000c488  jmp     short loc_14000C4AB
0x14000c48a  mov     rdx, [rsp+28h+arg_10]; struct IDispatch *
0x14000c48f  mov     rcx, [rbx+10h]; this
0x14000c493  call    ?SetScriptDispatch@CHost@@QEAAXPEAUIDispatch@@@Z; CHost::SetScriptDispatch(IDispatch *)
0x14000c498  mov     rcx, [rsp+28h+arg_10]
0x14000c49d  mov     rax, [rcx]
0x14000c4a0  mov     rax, [rax+10h]
0x14000c4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4a9  xor     eax, eax
0x14000c4ab  add     rsp, 20h
0x14000c4af  pop     rbx
0x14000c4b0  retn
```
