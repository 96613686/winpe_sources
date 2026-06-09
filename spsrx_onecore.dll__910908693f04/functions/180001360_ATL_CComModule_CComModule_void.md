# ATL::CComModule::CComModule(void)

- ea: `0x180001360`
- end: `0x1800013d4`
- name: `??0CComModule@ATL@@QEAA@XZ`
- size: `116`
- prototype: `__int64 __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001360`
- `0x180001b50`

## pseudocode

```c
__int64 *__fastcall ATL::CComModule::CComModule(ATL::CComModule *this)
{
  qword_1800152E8 = 0;
  qword_1800152B8 = 0;
  xmmword_1800152C8 = 0;
  qword_1800152C0 = 0;
  xmmword_1800152D8 = 0;
  ATL::_pAtlModule = (ATL::CAtlModule *)&_Module;
  qword_1800152F0 = 0;
  if ( (int)ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)&xmmword_1800152C8) >= 0 )
    LODWORD(qword_1800152B8) = 56;
  _Module = (__int64)&ATL::CComModule::`vftable';
  return &_Module;
}

```

## disassembly

```asm
0x180001360  push    rbx
0x180001362  sub     rsp, 20h
0x180001366  xor     eax, eax
0x180001368  lea     rbx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000136f  xorps   xmm0, xmm0
0x180001372  mov     cs:qword_1800152E8, rax
0x180001379  lea     rcx, xmmword_1800152C8; this
0x180001380  mov     cs:qword_1800152B8, rax
0x180001387  movups  cs:xmmword_1800152C8, xmm0
0x18000138e  mov     cs:qword_1800152C0, rax
0x180001395  movups  cs:xmmword_1800152D8, xmm0
0x18000139c  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rbx; ATL::CAtlModule * ATL::_pAtlModule
0x1800013a3  mov     cs:qword_1800152F0, rax
0x1800013aa  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800013af  test    eax, eax
0x1800013b1  js      short loc_1800013BD
0x1800013b3  mov     dword ptr cs:qword_1800152B8, 38h ; '8'
0x1800013bd  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x1800013c4  mov     cs:?_Module@@3VCComModule@ATL@@A, rax; ATL::CComModule _Module
0x1800013cb  mov     rax, rbx
0x1800013ce  add     rsp, 20h
0x1800013d2  pop     rbx
0x1800013d3  retn
```
