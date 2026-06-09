# operator new(unsigned __int64)

- ea: `0x180008f6c`
- end: `0x180008fb3`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x180008404`
- `0x180008610`
- `0x180008850`
- `0x1800090c0`
- `0x18001004c`
- `0x18001042c`
- `0x18001058c`
- `0x180011de8`
- `0x18001286c`
- `0x18001292c`
- `0x180012ae8`
- `0x18001406c`
- `0x180014168`
- `0x18001d9c7`

## callees

- `0x180008f24`
- `0x180008f6c`
- `0x180009832`
- `0x18000983e`

## import_xrefs

- `msvcrt!malloc` at `0x180008f86`
- `msvcrt!malloc` at `0x180008f86`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008f6c  push    rbx
0x180008f6e  sub     rsp, 40h
0x180008f72  mov     rbx, rcx
0x180008f75  jmp     short loc_180008F86
0x180008f77  mov     rcx, rbx; Size
0x180008f7a  call    _callnewh_0
0x180008f7f  test    eax, eax
0x180008f81  jz      short loc_180008F97
0x180008f83  mov     rcx, rbx; Size
0x180008f86  call    cs:__imp_malloc
0x180008f8c  test    rax, rax
0x180008f8f  jz      short loc_180008F77
0x180008f91  add     rsp, 40h
0x180008f95  pop     rbx
0x180008f96  retn
0x180008f97  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008f9c  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180008fa1  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180008fa8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008fad  call    _CxxThrowException_0
```
