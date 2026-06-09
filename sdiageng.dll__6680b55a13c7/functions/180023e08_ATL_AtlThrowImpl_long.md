# ATL::AtlThrowImpl(long)

- ea: `0x180023e08`
- end: `0x180023e2a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180023d08`
- `0x180023fa0`
- `0x1800240a0`
- `0x1800241a0`
- `0x180024cec`
- `0x180024e2c`
- `0x180025080`
- `0x180025270`
- `0x1800253e0`
- `0x180025904`
- `0x180025c50`
- `0x1800260f8`

## callees

- `0x180001c86`
- `0x180023bf4`

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
0x180023e08  sub     rsp, 28h
0x180023e0c  mov     edx, ecx; int
0x180023e0e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180023e13  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180023e18  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180023e1f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180023e24  call    _CxxThrowException_0
```
