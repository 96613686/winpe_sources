# LogAdapter::WdsLogger::~WdsLogger(void)

- ea: `0x180002800`
- end: `0x180002879`
- name: `??1WdsLogger@LogAdapter@@UEAA@XZ`
- size: `121`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002930`
- `0x18001bba0`

## callees

- `0x180002800`
- `0x180004130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000281f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000281f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002815`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180002815`
- `ntdll!RtlDeleteCriticalSection` at `0x180002859`
- `ntdll!RtlDeleteCriticalSection` at `0x180002859`
- `ntdll!RtlRaiseStatus` at `0x180002865`
- `ntdll!RtlRaiseStatus` at `0x180002865`

## pseudocode

```c
void __fastcall LogAdapter::WdsLogger::~WdsLogger(struct _RTL_CRITICAL_SECTION *this)
{
  HMODULE v2; // rcx
  int v3; // eax

  v2 = *(HMODULE *)&this[105].LockCount;
  if ( v2 )
  {
    if ( !FreeLibrary(v2) )
    {
      GetLastError();
      __fastfail(7u);
    }
    *(_QWORD *)&this[105].LockCount = 0;
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&LogAdapter::Logger::`vftable';
  LogAdapter::Logger::Close((LogAdapter::Logger *)this);
  if ( LOBYTE(this[105].DebugInfo) )
  {
    v3 = RtlDeleteCriticalSection(this + 104);
    if ( v3 < 0 )
      RtlRaiseStatus(v3);
    LOBYTE(this[105].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x180002800  push    rbx
0x180002802  sub     rsp, 20h
0x180002806  mov     rbx, rcx
0x180002809  mov     rcx, [rcx+1070h]; hLibModule
0x180002810  test    rcx, rcx
0x180002813  jz      short loc_180002837
0x180002815  call    cs:__imp_FreeLibrary
0x18000281b  test    eax, eax
0x18000281d  jnz     short loc_18000282C
0x18000281f  call    cs:__imp_GetLastError
0x180002825  mov     ecx, 7
0x18000282a  int     29h; Win8: RtlFailFast(ecx)
0x18000282c  mov     qword ptr [rbx+1070h], 0
0x180002837  lea     rax, ??_7Logger@LogAdapter@@6B@; const LogAdapter::Logger::`vftable'
0x18000283e  mov     rcx, rbx; this
0x180002841  mov     [rbx], rax
0x180002844  call    ?Close@Logger@LogAdapter@@UEAAXXZ; LogAdapter::Logger::Close(void)
0x180002849  cmp     byte ptr [rbx+1068h], 0
0x180002850  jz      short loc_180002873
0x180002852  lea     rcx, [rbx+1040h]; CriticalSection
0x180002859  call    cs:__imp_RtlDeleteCriticalSection
0x18000285f  test    eax, eax
0x180002861  jns     short loc_18000286C
0x180002863  mov     ecx, eax; Status
0x180002865  call    cs:__imp_RtlRaiseStatus
0x18000286b  int     3; Trap to Debugger
0x18000286c  mov     byte ptr [rbx+1068h], 0
0x180002873  add     rsp, 20h
0x180002877  pop     rbx
0x180002878  retn
```
