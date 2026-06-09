# ATL::CAtlComModule::CAtlComModule(void)

- ea: `0x1800014e0`
- end: `0x180001554`
- name: `??0CAtlComModule@ATL@@QEAA@XZ`
- size: `116`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001070`

## callees

- `0x1800014e0`
- `0x180001b50`

## pseudocode

```c
void *__fastcall ATL::CAtlComModule::CAtlComModule(ATL::CAtlComModule *this)
{
  bool v1; // sf
  void *result; // rax

  CriticalSection.SpinCount = 0;
  ATL::_AtlComModule = 0;
  qword_1800153B8 = 0x180000000uLL;
  qword_1800153C0 = (__int64)_pobjMapEntryLast;
  qword_1800153C8 = (__int64)_pobjMapEntryLast;
  *(_OWORD *)&CriticalSection.DebugInfo = 0;
  *(_OWORD *)&CriticalSection.OwningThread = 0;
  v1 = (int)ATL::CComCriticalSection::Init(&CriticalSection) < 0;
  result = &ATL::_AtlComModule;
  if ( !v1 )
    ATL::_AtlComModule = 72;
  return result;
}

```

## disassembly

```asm
0x1800014e0  sub     rsp, 28h
0x1800014e4  xor     eax, eax
0x1800014e6  lea     rcx, CriticalSection; this
0x1800014ed  mov     cs:CriticalSection.SpinCount, rax
0x1800014f4  xorps   xmm0, xmm0
0x1800014f7  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, eax; ATL::CAtlComModule ATL::_AtlComModule
0x1800014fd  lea     rax, cs:180000000h
0x180001504  mov     cs:qword_1800153B8, rax
0x18000150b  lea     rax, __pobjMapEntryLast
0x180001512  mov     cs:qword_1800153C0, rax
0x180001519  lea     rax, __pobjMapEntryLast
0x180001520  mov     cs:qword_1800153C8, rax
0x180001527  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18000152e  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180001535  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000153a  test    eax, eax
0x18000153c  lea     rax, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180001543  js      short loc_18000154F
0x180001545  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000154f  add     rsp, 28h
0x180001553  retn
```
