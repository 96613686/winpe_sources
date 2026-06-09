# CDevNode::GetProblemCode(void)

- ea: `0x18000ace8`
- end: `0x18000ad30`
- name: `?GetProblemCode@CDevNode@@QEAAKXZ`
- size: `72`
- prototype: `__int64 __fastcall(CDevNode *this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800045d0`
- `0x180006d2c`
- `0x180006f18`
- `0x180007b44`
- `0x180008ac0`

## callees

- `0x18000a618`
- `0x18000ace8`
- `0x18000ad94`

## pseudocode

```c
__int64 __fastcall CDevNode::GetProblemCode(CDevNode *this)
{
  unsigned int v1; // ebx
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v4 = 0;
  if ( CDevNode::DevicePropertyExists(this, &DEVPKEY_Device_ProblemCode) )
  {
    CDevNode::GetProperty(this, &DEVPKEY_Device_ProblemCode, &v4);
    return v4;
  }
  return v1;
}

```

## disassembly

```asm
0x18000ace8  mov     [rsp+arg_0], rbx
0x18000aced  push    rdi
0x18000acee  sub     rsp, 20h
0x18000acf2  xor     ebx, ebx
0x18000acf4  lea     rdx, DEVPKEY_Device_ProblemCode; struct _DEVPROPKEY *
0x18000acfb  mov     [rsp+28h+arg_8], ebx
0x18000acff  mov     rdi, rcx
0x18000ad02  call    ?DevicePropertyExists@CDevNode@@QEAAEAEBU_DEVPROPKEY@@@Z; CDevNode::DevicePropertyExists(_DEVPROPKEY const &)
0x18000ad07  test    al, al
0x18000ad09  jz      short loc_18000AD23
0x18000ad0b  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000ad10  mov     rcx, rdi; this
0x18000ad13  lea     rdx, DEVPKEY_Device_ProblemCode; struct _DEVPROPKEY *
0x18000ad1a  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAK@Z; CDevNode::GetProperty(_DEVPROPKEY const &,ulong &)
0x18000ad1f  mov     ebx, [rsp+28h+arg_8]
0x18000ad23  mov     eax, ebx
0x18000ad25  mov     rbx, [rsp+28h+arg_0]
0x18000ad2a  add     rsp, 20h
0x18000ad2e  pop     rdi
0x18000ad2f  retn
```
