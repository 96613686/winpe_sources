# ATL::AtlThrowImpl(long)

- ea: `0x18000c404`
- end: `0x18000c41e`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c24c`
- `0x18000c3b8`
- `0x18000c434`
- `0x18000df04`
- `0x18000df44`

## callees

- `0x180002e7a`

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
0x18000c404  sub     rsp, 28h
0x18000c408  mov     [rsp+28h+pExceptionObject], ecx
0x18000c40c  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000c413  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000c418  call    _CxxThrowException_0
```
