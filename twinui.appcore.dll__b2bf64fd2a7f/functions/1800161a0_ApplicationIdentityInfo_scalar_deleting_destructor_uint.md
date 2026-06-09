# ApplicationIdentityInfo::`scalar deleting destructor'(uint)

- ea: `0x1800161a0`
- end: `0x18001624b`
- name: `??_GApplicationIdentityInfo@@UEAAPEAXI@Z`
- size: `171`
- prototype: `void *__fastcall(ApplicationIdentityInfo *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800161a0`
- `0x180020d5c`
- `0x18002b1d4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001620d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800161fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001620d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ApplicationIdentityInfo *__fastcall ApplicationIdentityInfo::`scalar deleting destructor'(
        ApplicationIdentityInfo *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 16);
  if ( v4 )
  {
    *((_QWORD *)this + 16) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 23) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IApplicationIdentityInfo,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IApplicationIdentityInfo,Microsoft::WRL::FtmBase>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x90);
  return this;
}

```

## disassembly

```asm
0x1800161a0  mov     [rsp+arg_0], rbx
0x1800161a5  push    rdi
0x1800161a6  sub     rsp, 20h
0x1800161aa  mov     edi, edx
0x1800161ac  mov     rbx, rcx
0x1800161af  mov     rcx, [rcx+80h]
0x1800161b6  test    rcx, rcx
0x1800161b9  jz      short loc_1800161D3
0x1800161bb  mov     qword ptr [rbx+80h], 0
0x1800161c6  mov     rax, [rcx]
0x1800161c9  mov     rax, [rax+10h]
0x1800161cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161d2  nop
0x1800161d3  mov     rcx, [rbx+78h]; string
0x1800161d7  call    cs:__imp_WindowsDeleteString
0x1800161dd  mov     qword ptr [rbx+78h], 0
0x1800161e5  mov     rcx, [rbx+70h]; string
0x1800161e9  call    cs:__imp_WindowsDeleteString
0x1800161ef  mov     qword ptr [rbx+70h], 0
0x1800161f7  mov     rcx, [rbx+68h]; string
0x1800161fb  call    cs:__imp_WindowsDeleteString
0x180016201  mov     qword ptr [rbx+68h], 0
0x180016209  mov     rcx, [rbx+60h]; string
0x18001620d  call    cs:__imp_WindowsDeleteString
0x180016213  mov     qword ptr [rbx+60h], 0
0x18001621b  mov     dword ptr [rbx+5Ch], 0C0000001h
0x180016222  mov     rcx, rbx; this
0x180016225  call    ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithGITSite@@@Details@23@UIServiceProvider@@UIApplicationIdentityInfo@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IApplicationIdentityInfo,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IApplicationIdentityInfo,Microsoft::WRL::FtmBase>(void)
0x18001622a  test    dil, 1
0x18001622e  jz      short loc_18001623D
0x180016230  mov     edx, 90h; struct std::nothrow_t *
0x180016235  mov     rcx, rbx; void *
0x180016238  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001623d  mov     rax, rbx
0x180016240  mov     rbx, [rsp+28h+arg_0]
0x180016245  add     rsp, 20h
0x180016249  pop     rdi
0x18001624a  retn
```
