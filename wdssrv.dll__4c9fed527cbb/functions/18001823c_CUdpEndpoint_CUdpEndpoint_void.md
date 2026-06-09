# CUdpEndpoint::~CUdpEndpoint(void)

- ea: `0x18001823c`
- end: `0x18001832a`
- name: `??1CUdpEndpoint@@UEAA@XZ`
- size: `238`
- prototype: `void __fastcall(CUdpEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018370`

## callees

- `0x1800181bc`
- `0x18001823c`
- `0x18001a474`
- `0x18001d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001830d`
- `KERNEL32!DeleteCriticalSection` at `0x18001830d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800182a6`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800182f4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800182a6`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800182f4`

## string_xrefs

- `0x18001828e`: `[%s][UDP][Ep=%s] Deleted.`

## pseudocode

```c
void __fastcall CUdpEndpoint::~CUdpEndpoint(CUdpEndpoint *this)
{
  __int64 v2; // r9
  __int64 v3; // r9
  const wchar_t *v4; // r9
  __int64 v5; // rcx

  *(_QWORD *)this = &CUdpEndpoint::`vftable'{for `CRefCount'};
  *((_QWORD *)this + 2) = &CUdpEndpoint::`vftable'{for `IMulticastCallback'};
  CUdpEndpoint::Shutdown(this);
  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    v3 = *(_QWORD *)(v2 + 64);
    if ( v3 )
      v4 = *(const wchar_t **)(v3 + 16);
    else
      v4 = L"<Unknown>";
  }
  else
  {
    v4 = L"(Unknown)";
  }
  CTrace::Trace((CTrace *)qword_180039310, 0x10000u, L"[%s][UDP][Ep=%s] Deleted.", v4, (char *)this + 2040);
  if ( *((_DWORD *)this + 234) )
  {
    v5 = *((_QWORD *)this + 9);
    if ( v5 )
      (*(void (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v5 + 40LL))(
        v5,
        (char *)this + 988,
        (char *)this + 940);
  }
  CTrace::Trace((CTrace *)qword_180039310, 0x10000u, L"UpdEndpoint::~UdpEndpoint = %p\n", this);
  CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::~CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>((__int64)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &CRefCount::`vftable';
}

```

## disassembly

```asm
0x18001823c  push    rbx
0x18001823e  sub     rsp, 30h
0x180018242  lea     rax, ??_7CUdpEndpoint@@6BCRefCount@@@; const CUdpEndpoint::`vftable'{for `CRefCount'}
0x180018249  mov     rbx, rcx
0x18001824c  mov     [rcx], rax
0x18001824f  lea     rax, ??_7CUdpEndpoint@@6BIMulticastCallback@@@; const CUdpEndpoint::`vftable'{for `IMulticastCallback'}
0x180018256  mov     [rcx+10h], rax
0x18001825a  call    ?Shutdown@CUdpEndpoint@@QEAAKXZ; CUdpEndpoint::Shutdown(void)
0x18001825f  mov     r9, [rbx+48h]
0x180018263  lea     rax, [rbx+7F8h]
0x18001826a  test    r9, r9
0x18001826d  jz      short loc_180018287
0x18001826f  mov     r9, [r9+40h]
0x180018273  test    r9, r9
0x180018276  jz      short loc_18001827E
0x180018278  mov     r9, [r9+10h]
0x18001827c  jmp     short loc_18001828E
0x18001827e  lea     r9, aUnknown_0; "<Unknown>"
0x180018285  jmp     short loc_18001828E
0x180018287  lea     r9, aUnknown_1; "(Unknown)"
0x18001828e  lea     r8, aSUdpEpSDeleted; "[%s][UDP][Ep=%s] Deleted."
0x180018295  mov     [rsp+38h+var_18], rax
0x18001829a  mov     edx, 10000h
0x18001829f  lea     rcx, qword_180039310
0x1800182a6  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800182ad  nop     dword ptr [rax+rax+00h]
0x1800182b2  cmp     dword ptr [rbx+3A8h], 0
0x1800182b9  jz      short loc_1800182DE
0x1800182bb  mov     rcx, [rbx+48h]
0x1800182bf  test    rcx, rcx
0x1800182c2  jz      short loc_1800182DE
0x1800182c4  mov     rax, [rcx]
0x1800182c7  lea     r8, [rbx+3ACh]
0x1800182ce  lea     rdx, [rbx+3DCh]
0x1800182d5  mov     rax, [rax+28h]
0x1800182d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182de  mov     r9, rbx
0x1800182e1  lea     r8, aUpdendpointUdp_0; "UpdEndpoint::~UdpEndpoint = %p\n"
0x1800182e8  mov     edx, 10000h
0x1800182ed  lea     rcx, qword_180039310
0x1800182f4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800182fb  nop     dword ptr [rax+rax+00h]
0x180018300  lea     rcx, [rbx+60h]
0x180018304  call    ??1?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@UEAA@XZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::~CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>(void)
0x180018309  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001830d  call    cs:__imp_DeleteCriticalSection
0x180018314  nop     dword ptr [rax+rax+00h]
0x180018319  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x180018320  mov     [rbx], rax
0x180018323  add     rsp, 30h
0x180018327  pop     rbx
0x180018328  retn
```
