# ATL::CAtlComModule::CAtlComModule(void)

- ea: `0x1800014c0`
- end: `0x180001540`
- name: `??0CAtlComModule@ATL@@QEAA@XZ`
- size: `128`
- prototype: `__int64 __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800014a0`

## callees

- `0x1800014c0`
- `0x180001700`

## pseudocode

```c
void *__fastcall ATL::CAtlComModule::CAtlComModule(ATL::CAtlComModule *this)
{
  bool v1; // sf
  void *result; // rax

  qword_180014AF0 = 0;
  ATL::_AtlComModule = 0;
  qword_180014AB8 = (__int64)&_ImageBase;
  qword_180014AC0 = (__int64)&_pobjMap_CWscAdmin;
  qword_180014AC8 = (__int64)&_pobjMapEntryLast;
  xmmword_180014AD0 = 0;
  xmmword_180014AE0 = 0;
  v1 = (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)&xmmword_180014AD0) < 0;
  result = &ATL::_AtlComModule;
  if ( v1 )
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  else
    ATL::_AtlComModule = 72;
  return result;
}

```

## disassembly

```asm
0x1800014c0  sub     rsp, 28h
0x1800014c4  xor     eax, eax
0x1800014c6  lea     rcx, xmmword_180014AD0; this
0x1800014cd  mov     cs:qword_180014AF0, rax
0x1800014d4  xorps   xmm0, xmm0
0x1800014d7  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, eax; ATL::CAtlComModule ATL::_AtlComModule
0x1800014dd  lea     rax, __ImageBase
0x1800014e4  mov     cs:qword_180014AB8, rax
0x1800014eb  lea     rax, __pobjMap_CWscAdmin
0x1800014f2  mov     cs:qword_180014AC0, rax
0x1800014f9  lea     rax, __pobjMapEntryLast
0x180001500  mov     cs:qword_180014AC8, rax
0x180001507  movups  cs:xmmword_180014AD0, xmm0
0x18000150e  movups  cs:xmmword_180014AE0, xmm0
0x180001515  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000151a  test    eax, eax
0x18000151c  lea     rax, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180001523  jns     short loc_180001531
0x180001525  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000152c  add     rsp, 28h
0x180001530  retn
0x180001531  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000153b  add     rsp, 28h
0x18000153f  retn
```
