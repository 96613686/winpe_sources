# ATL::AtlThrowImpl(long)

- ea: `0x180001b24`
- end: `0x180001b48`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `36`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b88`

## callees

- `0x180001ad0`
- `0x180002d00`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1, int a2)
{
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  pExceptionObject = a1;
  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a2);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180001b24  mov     [rsp+pExceptionObject], ecx
0x180001b28  sub     rsp, 28h
0x180001b2c  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180001b31  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180001b36  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180001b3d  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180001b42  call    _CxxThrowException_0
```
