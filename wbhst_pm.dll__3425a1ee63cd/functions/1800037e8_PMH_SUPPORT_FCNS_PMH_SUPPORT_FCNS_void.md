# PMH_SUPPORT_FCNS::~PMH_SUPPORT_FCNS(void)

- ea: `0x1800037e8`
- end: `0x180003878`
- name: `??1PMH_SUPPORT_FCNS@@AEAA@XZ`
- size: `144`
- prototype: `void __fastcall(PMH_SUPPORT_FCNS *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041c0`

## callees

- `0x180002ec0`
- `0x1800037e8`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003847`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003862`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003862`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003871`

## pseudocode

```c
void __fastcall PMH_SUPPORT_FCNS::~PMH_SUPPORT_FCNS(PMH_SUPPORT_FCNS *this)
{
  bool v1; // zf
  __int64 v3; // rcx

  v1 = *((_DWORD *)this + 46) == 0;
  *(_QWORD *)this = &PMH_SUPPORT_FCNS::`vftable'{for `IProcessHostSupportFunctions'};
  *((_QWORD *)this + 1) = &PMH_SUPPORT_FCNS::`vftable'{for `IApplicationPreloadUtil'};
  if ( v1 )
    PMH_SUPPORT_FCNS::Shutdown(this);
  v3 = *((_QWORD *)this + 29);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 29) = 0;
  }
  if ( *((_DWORD *)this + 47) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
    *((_DWORD *)this + 47) = 0;
  }
  *((_DWORD *)this + 4) = 1483958384;
  STRU::~STRU((PMH_SUPPORT_FCNS *)((char *)this + 120));
  STRU::~STRU((PMH_SUPPORT_FCNS *)((char *)this + 64));
}

```

## disassembly

```asm
0x1800037e8  push    rbx
0x1800037ea  sub     rsp, 20h
0x1800037ee  cmp     dword ptr [rcx+0B8h], 0
0x1800037f5  lea     rax, ??_7PMH_SUPPORT_FCNS@@6BIProcessHostSupportFunctions@@@; const PMH_SUPPORT_FCNS::`vftable'{for `IProcessHostSupportFunctions'}
0x1800037fc  mov     [rcx], rax
0x1800037ff  mov     rbx, rcx
0x180003802  lea     rax, ??_7PMH_SUPPORT_FCNS@@6BIApplicationPreloadUtil@@@; const PMH_SUPPORT_FCNS::`vftable'{for `IApplicationPreloadUtil'}
0x180003809  mov     [rcx+8], rax
0x18000380d  jnz     short loc_180003814
0x18000380f  call    ?Shutdown@PMH_SUPPORT_FCNS@@QEAAXXZ; PMH_SUPPORT_FCNS::Shutdown(void)
0x180003814  mov     rcx, [rbx+0E8h]
0x18000381b  test    rcx, rcx
0x18000381e  jz      short loc_180003837
0x180003820  mov     rax, [rcx]
0x180003823  mov     rax, [rax+10h]
0x180003827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000382c  mov     qword ptr [rbx+0E8h], 0
0x180003837  cmp     dword ptr [rbx+0BCh], 0
0x18000383e  jz      short loc_180003857
0x180003840  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180003847  call    cs:__imp_DeleteCriticalSection
0x18000384d  mov     dword ptr [rbx+0BCh], 0
0x180003857  lea     rcx, [rbx+78h]
0x18000385b  mov     dword ptr [rbx+10h], 58736870h
0x180003862  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003868  lea     rcx, [rbx+40h]
0x18000386c  add     rsp, 20h
0x180003870  pop     rbx
0x180003871  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
