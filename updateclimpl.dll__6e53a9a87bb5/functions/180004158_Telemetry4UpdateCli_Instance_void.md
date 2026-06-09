# Telemetry4UpdateCli::Instance(void)

- ea: `0x180004158`
- end: `0x180004224`
- name: `?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ`
- size: `204`
- prototype: `struct Telemetry4UpdateCli *(void)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004230`
- `0x18000acf4`
- `0x18000c3d0`
- `0x18000c830`
- `0x18000cbb0`
- `0x18000d14c`

## callees

- `0x180003bd0`
- `0x180004158`
- `0x180010310`
- `0x1800106f0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004194`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180004194`

## pseudocode

```c
struct Telemetry4UpdateCli *Telemetry4UpdateCli::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-38h] BYREF
  int v2; // [rsp+28h] [rbp-30h]
  LPVOID Context; // [rsp+30h] [rbp-28h] BYREF
  BOOL fPending; // [rsp+38h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`Telemetry4UpdateCli::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    v1 = &`Telemetry4UpdateCli::Instance'::`2'::wrapper;
    Context = &qword_18001FF80;
    qword_18001FF80 = (__int64)&Telemetry4UpdateCli::`vftable';
    qword_18001FF88 = 0;
    byte_18001FF90 = 0;
    dword_18001FF94 = 0;
    qword_18001FF98 = (__int64)&`Telemetry4UpdateCli::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`Telemetry4UpdateCli::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<Telemetry4UpdateCli>::Completer::~Completer(&v1);
  }
  return (struct Telemetry4UpdateCli *)Context;
}

```

## disassembly

```asm
0x180004158  push    rdi
0x18000415a  sub     rsp, 50h
0x18000415e  mov     rax, cs:__security_cookie
0x180004165  xor     rax, rsp
0x180004168  mov     [rsp+58h+var_18], rax
0x18000416d  lea     rdi, ?wrapper@?1??Instance@Telemetry4UpdateCli@@KAPEAV2@XZ@4V?$static_lazy@VTelemetry4UpdateCli@@@details@wil@@A; wil::details::static_lazy<Telemetry4UpdateCli> `Telemetry4UpdateCli::Instance(void)'::`2'::wrapper
0x180004174  mov     [rsp+58h+Context], 0
0x18000417d  mov     rcx, rdi; lpInitOnce
0x180004180  mov     [rsp+58h+fPending], 0
0x180004188  lea     r9, [rsp+58h+Context]; lpContext
0x18000418d  xor     edx, edx; dwFlags
0x18000418f  lea     r8, [rsp+58h+fPending]; fPending
0x180004194  call    cs:__imp_InitOnceBeginInitialize
0x18000419a  test    eax, eax
0x18000419c  jz      short loc_18000420C
0x18000419e  cmp     [rsp+58h+fPending], 0
0x1800041a3  jz      short loc_18000420C
0x1800041a5  lea     rax, qword_18001FF80
0x1800041ac  mov     [rsp+58h+var_38], rdi
0x1800041b1  mov     [rsp+58h+Context], rax
0x1800041b6  lea     rax, ??_7Telemetry4UpdateCli@@6B@; const Telemetry4UpdateCli::`vftable'
0x1800041bd  mov     cs:qword_18001FF80, rax
0x1800041c4  mov     cs:qword_18001FF88, 0
0x1800041cf  mov     cs:byte_18001FF90, 0
0x1800041d6  mov     cs:dword_18001FF94, 0
0x1800041e0  lea     rax, ?__hInner@?1???0StaticHandle@Telemetry4UpdateCli@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Telemetry4UpdateCli::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800041e7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@Telemetry4UpdateCli@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x1800041ee  mov     cs:qword_18001FF98, rax
0x1800041f5  call    atexit
0x1800041fa  lea     rcx, [rsp+58h+var_38]
0x1800041ff  mov     [rsp+58h+var_30], 0
0x180004207  call    ??1Completer@?$static_lazy@VTelemetry4UpdateCli@@@details@wil@@QEAA@XZ; wil::details::static_lazy<Telemetry4UpdateCli>::Completer::~Completer(void)
0x18000420c  mov     rax, [rsp+58h+Context]
0x180004211  mov     rcx, [rsp+58h+var_18]
0x180004216  xor     rcx, rsp; StackCookie
0x180004219  call    __security_check_cookie
0x18000421e  add     rsp, 50h
0x180004222  pop     rdi
0x180004223  retn
```
