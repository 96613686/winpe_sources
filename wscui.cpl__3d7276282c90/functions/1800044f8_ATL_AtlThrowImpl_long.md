# ATL::AtlThrowImpl(long)

- ea: `0x1800044f8`
- end: `0x180004512`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001890`
- `0x180004258`
- `0x1800047f8`
- `0x1800048b8`
- `0x180004c10`
- `0x180004c48`
- `0x180004d04`
- `0x180004dfc`
- `0x180005220`
- `0x1800090b8`

## callees

- `0x18000283c`

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
0x1800044f8  sub     rsp, 28h
0x1800044fc  mov     [rsp+28h+pExceptionObject], ecx
0x180004500  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180004507  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000450c  call    _CxxThrowException_0
```
