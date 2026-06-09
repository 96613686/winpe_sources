# ATL::AtlThrowImpl(long)

- ea: `0x180003ca8`
- end: `0x180003cc2`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ab8`
- `0x1800033ac`
- `0x180003934`
- `0x180003b44`

## callees

- `0x18000252c`

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
0x180003ca8  sub     rsp, 28h
0x180003cac  mov     [rsp+28h+pExceptionObject], ecx
0x180003cb0  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180003cb7  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180003cbc  call    _CxxThrowException_0
```
