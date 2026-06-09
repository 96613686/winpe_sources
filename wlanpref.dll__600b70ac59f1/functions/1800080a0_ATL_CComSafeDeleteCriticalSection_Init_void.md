# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x1800080a0`
- end: `0x1800080bc`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005a34`
- `0x180005b64`
- `0x180005c9c`
- `0x180005dd4`
- `0x180005f04`
- `0x180006030`
- `0x180006160`
- `0x180006290`
- `0x1800063c0`
- `0x1800064f0`
- `0x180006620`
- `0x180006744`
- `0x180006848`
- `0x180006950`
- `0x180006a74`
- `0x180006b78`
- `0x180006c90`
- `0x180006d94`
- `0x180006e98`
- `0x180006f9c`
- `0x180007080`
- `0x180007184`
- `0x180007288`
- `0x1800073a0`
- `0x18000bfbc`
- `0x18000c234`
- `0x18000db34`
- `0x18000dc28`
- `0x180012088`
- `0x180012730`
- `0x1800135c8`
- `0x180013c48`
- `0x180014158`

## callees

- `0x180007ffc`
- `0x1800080a0`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeDeleteCriticalSection::Init(ATL::CComSafeDeleteCriticalSection *this)
{
  __int64 result; // rax

  result = ATL::CComCriticalSection::Init(this);
  if ( (int)result >= 0 )
    *((_BYTE *)this + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x1800080a0  push    rbx
0x1800080a2  sub     rsp, 20h
0x1800080a6  mov     rbx, rcx
0x1800080a9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800080ae  test    eax, eax
0x1800080b0  js      short loc_1800080B6
0x1800080b2  mov     byte ptr [rbx+28h], 1
0x1800080b6  add     rsp, 20h
0x1800080ba  pop     rbx
0x1800080bb  retn
```
