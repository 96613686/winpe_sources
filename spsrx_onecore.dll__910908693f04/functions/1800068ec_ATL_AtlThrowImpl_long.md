# ATL::AtlThrowImpl(long)

- ea: `0x1800068ec`
- end: `0x180006906`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056c0`
- `0x1800062a8`
- `0x180006510`
- `0x180007f84`

## callees

- `0x1800031b0`

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
0x1800068ec  sub     rsp, 28h
0x1800068f0  mov     [rsp+28h+pExceptionObject], ecx
0x1800068f4  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800068fb  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180006900  call    _CxxThrowException_0
```
