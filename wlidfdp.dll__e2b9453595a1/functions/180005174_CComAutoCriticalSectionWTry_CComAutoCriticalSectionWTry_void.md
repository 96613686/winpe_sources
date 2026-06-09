# CComAutoCriticalSectionWTry::CComAutoCriticalSectionWTry(void)

- ea: `0x180005174`
- end: `0x1800051a7`
- name: `??0CComAutoCriticalSectionWTry@@QEAA@XZ`
- size: `51`
- prototype: `CComAutoCriticalSectionWTry *__fastcall(CComAutoCriticalSectionWTry *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800051b0`
- `0x180009be0`
- `0x180009cfc`

## callees

- `0x180003fac`
- `0x18000424c`
- `0x180005174`

## pseudocode

```c
CComAutoCriticalSectionWTry *__fastcall CComAutoCriticalSectionWTry::CComAutoCriticalSectionWTry(
        CComAutoCriticalSectionWTry *this)
{
  int v2; // eax

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  v2 = ATL::CComCriticalSection::Init(this);
  if ( v2 < 0 )
    ATL::AtlThrowImpl(v2);
  return this;
}

```

## disassembly

```asm
0x180005174  push    rbx
0x180005176  sub     rsp, 20h
0x18000517a  xorps   xmm0, xmm0
0x18000517d  xor     eax, eax
0x18000517f  movups  xmmword ptr [rcx], xmm0
0x180005182  mov     rbx, rcx
0x180005185  movups  xmmword ptr [rcx+10h], xmm0
0x180005189  mov     [rcx+20h], rax
0x18000518d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005192  test    eax, eax
0x180005194  jns     short loc_18000519E
0x180005196  mov     ecx, eax; int
0x180005198  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000519e  mov     rax, rbx
0x1800051a1  add     rsp, 20h
0x1800051a5  pop     rbx
0x1800051a6  retn
```
