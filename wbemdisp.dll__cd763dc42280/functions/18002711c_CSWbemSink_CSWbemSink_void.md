# CSWbemSink::~CSWbemSink(void)

- ea: `0x18002711c`
- end: `0x1800271cb`
- name: `??1CSWbemSink@@QEAA@XZ`
- size: `175`
- prototype: `void __fastcall(CSWbemSink *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180027224`

## callees

- `0x18000c8b0`
- `0x18002711c`
- `0x1800271d4`
- `0x180036010`

## import_xrefs

- `msvcrt!free` at `0x1800271b0`
- `msvcrt!free` at `0x1800271b0`

## pseudocode

```c
void __fastcall CSWbemSink::~CSWbemSink(CSWbemSink *this, unsigned int a2)
{
  __int64 v3; // rax
  CConnectionPoint *v4; // rcx

  *(_QWORD *)this = &CSWbemSink::`vftable'{for `ISWbemSink'};
  *((_QWORD *)this + 1) = &CSWbemSink::`vftable'{for `IConnectionPointContainer'};
  *((_QWORD *)this + 2) = &CSWbemSink::`vftable'{for `IProvideClassInfo2'};
  *((_QWORD *)this + 3) = &CSWbemSink::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 4) = &CSWbemSink::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 5) = &CSWbemSink::`vftable'{for `ISWbemPrivateSinkLocator'};
  v3 = *((_QWORD *)this + 19);
  if ( v3 )
  {
    *(_QWORD *)(v3 + 8) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 16LL))(*((_QWORD *)this + 19));
    *((_QWORD *)this + 19) = 0;
  }
  v4 = (CConnectionPoint *)*((_QWORD *)this + 16);
  if ( v4 )
    CConnectionPoint::`scalar deleting destructor'(v4, a2);
  free(*((void **)this + 17));
  _InterlockedDecrement(&g_cObj);
  CDispatchHelp::~CDispatchHelp((CSWbemSink *)((char *)this + 48));
}

```

## disassembly

```asm
0x18002711c  push    rbx
0x18002711e  sub     rsp, 20h
0x180027122  mov     rbx, rcx
0x180027125  lea     rax, ??_7CSWbemSink@@6BISWbemSink@@@; const CSWbemSink::`vftable'{for `ISWbemSink'}
0x18002712c  mov     [rcx], rax
0x18002712f  lea     rax, ??_7CSWbemSink@@6BIConnectionPointContainer@@@; const CSWbemSink::`vftable'{for `IConnectionPointContainer'}
0x180027136  mov     [rcx+8], rax
0x18002713a  lea     rax, ??_7CSWbemSink@@6BIProvideClassInfo2@@@; const CSWbemSink::`vftable'{for `IProvideClassInfo2'}
0x180027141  mov     [rcx+10h], rax
0x180027145  lea     rax, ??_7CSWbemSink@@6BIObjectSafety@@@; const CSWbemSink::`vftable'{for `IObjectSafety'}
0x18002714c  mov     [rcx+18h], rax
0x180027150  lea     rax, ??_7CSWbemSink@@6BISupportErrorInfo@@@; const CSWbemSink::`vftable'{for `ISupportErrorInfo'}
0x180027157  mov     [rcx+20h], rax
0x18002715b  lea     rax, ??_7CSWbemSink@@6BISWbemPrivateSinkLocator@@@; const CSWbemSink::`vftable'{for `ISWbemPrivateSinkLocator'}
0x180027162  mov     [rcx+28h], rax
0x180027166  mov     rax, [rcx+98h]
0x18002716d  test    rax, rax
0x180027170  jz      short loc_180027198
0x180027172  mov     qword ptr [rax+8], 0
0x18002717a  mov     rcx, [rcx+98h]
0x180027181  mov     rax, [rcx]
0x180027184  mov     rax, [rax+10h]
0x180027188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002718d  mov     qword ptr [rbx+98h], 0
0x180027198  mov     rcx, [rbx+80h]; this
0x18002719f  test    rcx, rcx
0x1800271a2  jz      short loc_1800271A9
0x1800271a4  call    ??_GCConnectionPoint@@QEAAPEAXI@Z; CConnectionPoint::`scalar deleting destructor'(uint)
0x1800271a9  mov     rcx, [rbx+88h]; Block
0x1800271b0  call    cs:__imp_free
0x1800271b6  lock dec cs:?g_cObj@@3JA; long g_cObj
0x1800271bd  lea     rcx, [rbx+30h]; this
0x1800271c1  add     rsp, 20h
0x1800271c5  pop     rbx
0x1800271c6  jmp     ??1CDispatchHelp@@UEAA@XZ; CDispatchHelp::~CDispatchHelp(void)
```
