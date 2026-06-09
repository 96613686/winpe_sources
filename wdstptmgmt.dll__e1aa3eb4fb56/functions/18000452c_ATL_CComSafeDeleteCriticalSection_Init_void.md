# ATL::CComSafeDeleteCriticalSection::Init(void)

- ea: `0x18000452c`
- end: `0x180004549`
- name: `?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CComSafeDeleteCriticalSection *__hidden this)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005914`
- `0x1800061fc`
- `0x180006cc4`
- `0x180007f84`
- `0x1800080b0`
- `0x1800081d0`
- `0x180008a30`
- `0x180009e50`
- `0x18000b2d0`
- `0x18000cd08`
- `0x18000f204`
- `0x18000ff30`
- `0x180011128`
- `0x180011220`
- `0x180011344`
- `0x1800148c0`
- `0x180015530`
- `0x1800162d0`
- `0x1800174c4`
- `0x180018410`
- `0x180018db0`
- `0x180019750`

## callees

- `0x1800044fc`
- `0x18000452c`

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
0x18000452c  push    rbx
0x18000452e  sub     rsp, 20h
0x180004532  mov     rbx, rcx
0x180004535  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000453a  test    eax, eax
0x18000453c  js      short loc_180004542
0x18000453e  mov     byte ptr [rbx+28h], 1
0x180004542  add     rsp, 20h
0x180004546  pop     rbx
0x180004547  retn
```
