# CWdsTransportServicePolicy::Initialize(CWdsTransportServer *)

- ea: `0x18000d194`
- end: `0x18000d21d`
- name: `?Initialize@CWdsTransportServicePolicy@@AEAAJPEAVCWdsTransportServer@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, struct CWdsTransportServer *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cdf0`

## callees

- `0x18000d194`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d1c1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d1fe`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d1c1`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000d1fe`

## string_xrefs

- `0x18000d1a6`: `-> CWdsTransportServicePolicy::Initialize(0x%p)`
- `0x18000d1eb`: `<- CWdsTransportServicePolicy::Initialize(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::Initialize(
        CWdsTransportServicePolicy *this,
        struct CWdsTransportServer *a2)
{
  unsigned int v4; // edi
  unsigned int v6; // [rsp+20h] [rbp-18h]

  v4 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportServicePolicy::Initialize(0x%p)", this);
  if ( *((_DWORD *)this + 30) )
  {
    v4 = -1055915767;
  }
  else
  {
    *((_QWORD *)this + 8) = a2;
    *((_DWORD *)this + 30) = 1;
  }
  v6 = v4;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportServicePolicy::Initialize(0x%p) =%x", this, v6);
  return v4;
}

```

## disassembly

```asm
0x18000d194  mov     [rsp+arg_0], rbx
0x18000d199  mov     [rsp+arg_8], rsi
0x18000d19e  push    rdi
0x18000d19f  sub     rsp, 30h
0x18000d1a3  mov     rsi, rdx
0x18000d1a6  lea     r8, aCwdstransports_57; "-> CWdsTransportServicePolicy::Initiali"...
0x18000d1ad  mov     rbx, rcx
0x18000d1b0  mov     r9, rcx
0x18000d1b3  mov     edx, 10000h
0x18000d1b8  lea     rcx, qword_18003B770
0x18000d1bf  xor     edi, edi
0x18000d1c1  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d1c8  nop     dword ptr [rax+rax+00h]
0x18000d1cd  cmp     [rbx+78h], edi
0x18000d1d0  jz      short loc_18000D1D9
0x18000d1d2  mov     edi, 0C1100109h
0x18000d1d7  jmp     short loc_18000D1E4
0x18000d1d9  mov     [rbx+40h], rsi
0x18000d1dd  mov     dword ptr [rbx+78h], 1
0x18000d1e4  mov     r9, rbx
0x18000d1e7  mov     [rsp+38h+var_18], edi
0x18000d1eb  lea     r8, aCwdstransports_10; "<- CWdsTransportServicePolicy::Initiali"...
0x18000d1f2  mov     edx, 10000h
0x18000d1f7  lea     rcx, qword_18003B770
0x18000d1fe  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000d205  nop     dword ptr [rax+rax+00h]
0x18000d20a  mov     rbx, [rsp+38h+arg_0]
0x18000d20f  mov     eax, edi
0x18000d211  mov     rsi, [rsp+38h+arg_8]
0x18000d216  add     rsp, 30h
0x18000d21a  pop     rdi
0x18000d21b  retn
```
