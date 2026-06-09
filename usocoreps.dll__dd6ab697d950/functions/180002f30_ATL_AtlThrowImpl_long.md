# ATL::AtlThrowImpl(long)

- ea: `0x180002f30`
- end: `0x180002f52`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000271c`
- `0x180002cf8`
- `0x180003394`
- `0x180003978`
- `0x180003b5c`
- `0x180004a94`

## callees

- `0x180002112`
- `0x1800021c8`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a1);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180002f30  sub     rsp, 28h
0x180002f34  mov     edx, ecx; int
0x180002f36  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180002f3b  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180002f40  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180002f47  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180002f4c  call    _CxxThrowException_0
```
