# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x180004a90`
- end: `0x180004aac`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `28`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e64`
- `0x180003f88`
- `0x1800040ac`
- `0x1800041d0`
- `0x1800042dc`
- `0x1800043e8`
- `0x180004500`
- `0x1800060fc`
- `0x180006374`

## callees

- `0x1800049ec`
- `0x180004a90`

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
0x180004a90  push    rbx
0x180004a92  sub     rsp, 20h
0x180004a96  mov     rbx, rcx
0x180004a99  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004a9e  test    eax, eax
0x180004aa0  js      short loc_180004AA6
0x180004aa2  mov     byte ptr [rbx+28h], 1
0x180004aa6  add     rsp, 20h
0x180004aaa  pop     rbx
0x180004aab  retn
```
