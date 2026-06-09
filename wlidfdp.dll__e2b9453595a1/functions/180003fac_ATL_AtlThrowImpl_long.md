# ATL::AtlThrowImpl(long)

- ea: `0x180003fac`
- end: `0x180003fc6`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038d4`
- `0x180005174`
- `0x180008b44`
- `0x180008b7c`
- `0x180008e98`
- `0x180009fac`
- `0x18000a8e8`
- `0x18000ac5c`
- `0x18000ad0c`
- `0x18000b1c0`
- `0x18000b31c`

## callees

- `0x1800033c0`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  pExceptionObject = a1;
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180003fac  sub     rsp, 28h
0x180003fb0  mov     [rsp+28h+pExceptionObject], ecx
0x180003fb4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180003fbb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180003fc0  call    _CxxThrowException_0
```
