# CWcnSoftApTransport::~CWcnSoftApTransport(void)

- ea: `0x1800491bc`
- end: `0x18004921e`
- name: `??1CWcnSoftApTransport@@UEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CWcnSoftApTransport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180049230`

## callees

- `0x18001e490`
- `0x180052290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800491f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800491f1`

## pseudocode

```c
void __fastcall CWcnSoftApTransport::~CWcnSoftApTransport(CWcnSoftApTransport *this)
{
  char *v2; // rbx

  *(_QWORD *)this = &CWcnSoftApTransport::`vftable'{for `IWcnTransport'};
  v2 = (char *)this + 136;
  *((_QWORD *)this + 2) = &CWcnSoftApTransport::`vftable'{for `IWcnSinkController'};
  CWcnSoftApApiWrapper::DisableSoftAp((CWcnSoftApTransport *)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
  CWcnMessage::Clear((CWcnSoftApTransport *)((char *)this + 80));
  CWcnMessage::Clear((CWcnSoftApTransport *)((char *)this + 24));
  *(_QWORD *)this = &IWcnTransport::`vftable';
}

```

## disassembly

```asm
0x1800491bc  mov     [rsp+arg_0], rbx
0x1800491c1  push    rdi
0x1800491c2  sub     rsp, 20h
0x1800491c6  lea     rax, ??_7CWcnSoftApTransport@@6BIWcnTransport@@@; const CWcnSoftApTransport::`vftable'{for `IWcnTransport'}
0x1800491cd  mov     rdi, rcx
0x1800491d0  mov     [rcx], rax
0x1800491d3  lea     rbx, [rcx+88h]
0x1800491da  lea     rax, ??_7CWcnSoftApTransport@@6BIWcnSinkController@@@; const CWcnSoftApTransport::`vftable'{for `IWcnSinkController'}
0x1800491e1  mov     [rcx+10h], rax
0x1800491e5  mov     rcx, rbx; this
0x1800491e8  call    ?DisableSoftAp@CWcnSoftApApiWrapper@@QEAAXXZ; CWcnSoftApApiWrapper::DisableSoftAp(void)
0x1800491ed  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800491f1  call    cs:__imp_DeleteCriticalSection
0x1800491f7  lea     rcx, [rdi+50h]; this
0x1800491fb  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x180049200  lea     rcx, [rdi+18h]; this
0x180049204  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x180049209  mov     rbx, [rsp+28h+arg_0]
0x18004920e  lea     rax, ??_7IWcnTransport@@6B@; const IWcnTransport::`vftable'
0x180049215  mov     [rdi], rax
0x180049218  add     rsp, 20h
0x18004921c  pop     rdi
0x18004921d  retn
```
