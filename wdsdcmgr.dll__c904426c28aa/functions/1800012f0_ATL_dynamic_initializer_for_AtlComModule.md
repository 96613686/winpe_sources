# ATL::_dynamic_initializer_for___AtlComModule__

- ea: `0x1800012f0`
- end: `0x18000136a`
- name: `ATL::_dynamic_initializer_for___AtlComModule__`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800012f0`
- `0x180001cd0`
- `0x18001575c`
- `0x180015c9d`

## pseudocode

```c
int ATL::_dynamic_initializer_for___AtlComModule__()
{
  memset_0(&stru_18001DF90, 0, sizeof(stru_18001DF90));
  ATL::_AtlComModule = 0;
  qword_18001DF78 = 0x180000000uLL;
  qword_18001DF80 = (__int64)_pobjMapEntryLast;
  qword_18001DF88 = (__int64)_pobjMapEntryLast;
  if ( (int)ATL::CComCriticalSection::Init(&stru_18001DF90) >= 0 )
    ATL::_AtlComModule = 72;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  return atexit(ATL::_dynamic_atexit_destructor_for___AtlComModule__);
}

```

## disassembly

```asm
0x1800012f0  sub     rsp, 28h
0x1800012f4  xor     edx, edx; Val
0x1800012f6  lea     rcx, stru_18001DF90; void *
0x1800012fd  lea     r8d, [rdx+28h]; Size
0x180001301  call    memset_0
0x180001306  and     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000130d  lea     rax, cs:180000000h
0x180001314  mov     cs:qword_18001DF78, rax
0x18000131b  lea     rcx, stru_18001DF90; this
0x180001322  lea     rax, __pobjMapEntryLast
0x180001329  mov     cs:qword_18001DF80, rax
0x180001330  lea     rax, __pobjMapEntryLast
0x180001337  mov     cs:qword_18001DF88, rax
0x18000133e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180001343  test    eax, eax
0x180001345  jns     short loc_180001350
0x180001347  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000134e  jmp     short loc_18000135A
0x180001350  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 48h ; 'H'; ATL::CAtlComModule ATL::_AtlComModule
0x18000135a  lea     rcx, ATL___dynamic_atexit_destructor_for___AtlComModule__
0x180001361  add     rsp, 28h
0x180001365  jmp     atexit
```
