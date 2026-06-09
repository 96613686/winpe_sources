# CShareMediaCore::~CShareMediaCore(void)

- ea: `0x180007e5c`
- end: `0x180007ff0`
- name: `??1CShareMediaCore@@QEAA@XZ`
- size: `404`
- prototype: `void __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000d000`

## callees

- `0x18000366c`
- `0x180003860`
- `0x180007e5c`
- `0x180009cac`
- `0x180009d40`
- `0x1800107d4`
- `0x180015afc`
- `0x180015dd8`
- `0x18001e010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180007eba`
- `KERNEL32!CloseHandle` at `0x180007ee4`
- `KERNEL32!CloseHandle` at `0x180007eba`
- `KERNEL32!CloseHandle` at `0x180007ee4`
- `KERNEL32!DeleteCriticalSection` at `0x180007fa4`
- `KERNEL32!DeleteCriticalSection` at `0x180007fae`
- `KERNEL32!DeleteCriticalSection` at `0x180007fa4`
- `KERNEL32!DeleteCriticalSection` at `0x180007fae`
- `ntdll!WinSqmIsOptedIn` at `0x180007f31`
- `ntdll!WinSqmIsOptedIn` at `0x180007f31`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f9a`

## pseudocode

```c
void __fastcall CShareMediaCore::~CShareMediaCore(CShareMediaCore *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  struct __POSITION *v4; // rdx
  CSqmSessionMgr *v5; // rcx
  __int64 v6; // rcx
  CSqmSessionMgr *v7; // rcx

  *(_QWORD *)this = &CShareMediaCore::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  if ( *((_QWORD *)this + 19) )
  {
    CShareMediaCore::EndDeviceEnumeration(this);
    CloseHandle(*((HANDLE *)this + 19));
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 20) )
  {
    CShareMediaCore::EndNetworkStateChangeThread(this);
    CloseHandle(*((HANDLE *)this + 20));
    *((_QWORD *)this + 20) = 0;
  }
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 32LL))(v2, *((unsigned int *)this + 12));
    v3 = *((_QWORD *)this + 5);
    if ( v3 )
    {
      *((_QWORD *)this + 5) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    *((_DWORD *)this + 12) = 0;
  }
  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    v4 = (struct __POSITION *)*((_QWORD *)this + 28);
    if ( v4 )
    {
      CShareMediaCore::_SQMSetDataPoints(this, v4);
      if ( _pSqmSessionMgr )
        CSqmSessionMgr::ReleaseContext(v5, *((struct __POSITION **)this + 28));
      *((_QWORD *)this + 28) = 0;
    }
  }
  v6 = *((_QWORD *)this + 27);
  if ( v6 )
  {
    *((_QWORD *)this + 27) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  SysFreeString(*((BSTR *)this + 25));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  CSqmSessionMgr::Term(v7);
  DllRelease();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
}

```

## disassembly

```asm
0x180007e5c  mov     [rsp+arg_0], rbx
0x180007e61  push    rsi
0x180007e62  sub     rsp, 20h
0x180007e66  lea     rax, ??_7CShareMediaCore@@6B@; const CShareMediaCore::`vftable'
0x180007e6d  mov     rbx, rcx
0x180007e70  mov     [rcx], rax
0x180007e73  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e7a  lea     rsi, WPP_GLOBAL_Control
0x180007e81  cmp     rcx, rsi
0x180007e84  jz      short loc_180007EA1
0x180007e86  test    byte ptr [rcx+1Ch], 20h
0x180007e8a  jz      short loc_180007EA1
0x180007e8c  mov     rcx, [rcx+10h]
0x180007e90  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180007e97  mov     edx, 0Ch
0x180007e9c  call    WPP_SF_
0x180007ea1  cmp     qword ptr [rbx+98h], 0
0x180007ea9  jz      short loc_180007ECB
0x180007eab  mov     rcx, rbx; this
0x180007eae  call    ?EndDeviceEnumeration@CShareMediaCore@@QEAAJXZ; CShareMediaCore::EndDeviceEnumeration(void)
0x180007eb3  mov     rcx, [rbx+98h]; hObject
0x180007eba  call    cs:__imp_CloseHandle
0x180007ec0  mov     qword ptr [rbx+98h], 0
0x180007ecb  cmp     qword ptr [rbx+0A0h], 0
0x180007ed3  jz      short loc_180007EF5
0x180007ed5  mov     rcx, rbx; this
0x180007ed8  call    ?EndNetworkStateChangeThread@CShareMediaCore@@QEAAJXZ; CShareMediaCore::EndNetworkStateChangeThread(void)
0x180007edd  mov     rcx, [rbx+0A0h]; hObject
0x180007ee4  call    cs:__imp_CloseHandle
0x180007eea  mov     qword ptr [rbx+0A0h], 0
0x180007ef5  mov     rcx, [rbx+28h]
0x180007ef9  test    rcx, rcx
0x180007efc  jz      short loc_180007F31
0x180007efe  mov     rax, [rcx]
0x180007f01  mov     edx, [rbx+30h]
0x180007f04  mov     rax, [rax+20h]
0x180007f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f0d  mov     rcx, [rbx+28h]
0x180007f11  test    rcx, rcx
0x180007f14  jz      short loc_180007F2A
0x180007f16  mov     qword ptr [rbx+28h], 0
0x180007f1e  mov     rax, [rcx]
0x180007f21  mov     rax, [rax+10h]
0x180007f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2a  mov     dword ptr [rbx+30h], 0
0x180007f31  call    cs:__imp_WinSqmIsOptedIn
0x180007f37  test    eax, eax
0x180007f39  jz      short loc_180007F70
0x180007f3b  mov     rdx, [rbx+0E0h]; struct __POSITION *
0x180007f42  test    rdx, rdx
0x180007f45  jz      short loc_180007F70
0x180007f47  mov     rcx, rbx; this
0x180007f4a  call    ?_SQMSetDataPoints@CShareMediaCore@@AEAAXPEAU__POSITION@@@Z; CShareMediaCore::_SQMSetDataPoints(__POSITION *)
0x180007f4f  cmp     cs:?_pSqmSessionMgr@@3PEAVCSqmSessionMgr@@EA, 0; CSqmSessionMgr * _pSqmSessionMgr
0x180007f57  jz      short loc_180007F65
0x180007f59  mov     rdx, [rbx+0E0h]; struct __POSITION *
0x180007f60  call    ?ReleaseContext@CSqmSessionMgr@@QEAAXPEAU__POSITION@@@Z; CSqmSessionMgr::ReleaseContext(__POSITION *)
0x180007f65  mov     qword ptr [rbx+0E0h], 0
0x180007f70  mov     rcx, [rbx+0D8h]
0x180007f77  test    rcx, rcx
0x180007f7a  jz      short loc_180007F93
0x180007f7c  mov     qword ptr [rbx+0D8h], 0
0x180007f87  mov     rax, [rcx]
0x180007f8a  mov     rax, [rax+10h]
0x180007f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f93  mov     rcx, [rbx+0C8h]; bstrString
0x180007f9a  call    cs:__imp_SysFreeString
0x180007fa0  lea     rcx, [rbx+48h]; lpCriticalSection
0x180007fa4  call    cs:__imp_DeleteCriticalSection
0x180007faa  lea     rcx, [rbx+70h]; lpCriticalSection
0x180007fae  call    cs:__imp_DeleteCriticalSection
0x180007fb4  call    ?Term@CSqmSessionMgr@@QEAAXXZ; CSqmSessionMgr::Term(void)
0x180007fb9  call    DllRelease
0x180007fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fc5  cmp     rcx, rsi
0x180007fc8  jz      short loc_180007FE5
0x180007fca  test    byte ptr [rcx+1Ch], 20h
0x180007fce  jz      short loc_180007FE5
0x180007fd0  mov     rcx, [rcx+10h]
0x180007fd4  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180007fdb  mov     edx, 0Dh
0x180007fe0  call    WPP_SF_
0x180007fe5  mov     rbx, [rsp+28h+arg_0]
0x180007fea  add     rsp, 20h
0x180007fee  pop     rsi
0x180007fef  retn
```
