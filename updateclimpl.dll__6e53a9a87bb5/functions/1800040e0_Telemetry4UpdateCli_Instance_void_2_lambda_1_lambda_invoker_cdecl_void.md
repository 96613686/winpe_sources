# `Telemetry4UpdateCli::Instance(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void)

- ea: `0x1800040e0`
- end: `0x180004150`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@Telemetry4UpdateCli@@KAPEAV3@XZ@SA@XZ`
- size: `112`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800040e0`
- `0x180010310`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000411a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000411a`

## pseudocode

```c
void __fastcall `Telemetry4UpdateCli::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_()
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`Telemetry4UpdateCli::Instance'::`2'::wrapper, 1u, &fPending, &Context) )
  {
    if ( !fPending )
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)Context + 24LL))(Context, 0);
  }
}

```

## disassembly

```asm
0x1800040e0  sub     rsp, 48h
0x1800040e4  mov     rax, cs:__security_cookie
0x1800040eb  xor     rax, rsp
0x1800040ee  mov     [rsp+48h+var_18], rax
0x1800040f3  lea     r9, [rsp+48h+Context]; lpContext
0x1800040f8  mov     [rsp+48h+Context], 0
0x180004101  lea     r8, [rsp+48h+fPending]; fPending
0x180004106  mov     [rsp+48h+fPending], 0
0x18000410e  mov     edx, 1; dwFlags
0x180004113  lea     rcx, ?wrapper@?1??Instance@Telemetry4UpdateCli@@KAPEAV2@XZ@4V?$static_lazy@VTelemetry4UpdateCli@@@details@wil@@A; lpInitOnce
0x18000411a  call    cs:__imp_InitOnceBeginInitialize
0x180004120  test    eax, eax
0x180004122  jz      short loc_18000413E
0x180004124  cmp     [rsp+48h+fPending], 0
0x180004129  jnz     short loc_18000413E
0x18000412b  mov     rcx, [rsp+48h+Context]
0x180004130  xor     edx, edx
0x180004132  mov     rax, [rcx]
0x180004135  mov     rax, [rax+18h]
0x180004139  call    _guard_dispatch_icall
0x18000413e  mov     rcx, [rsp+48h+var_18]
0x180004143  xor     rcx, rsp; StackCookie
0x180004146  call    __security_check_cookie
0x18000414b  add     rsp, 48h
0x18000414f  retn
```
