# operator new(unsigned __int64)

- ea: `0x180001c7c`
- end: `0x180001cc2`
- name: `??2@YAPEAX_K@Z`
- size: `70`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000242c`
- `0x180003858`
- `0x180003960`
- `0x180008098`

## callees

- `0x180001c24`
- `0x180001c7c`
- `0x180002411`
- `0x1800027f9`
- `0x18000283c`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
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
0x180001c7c  push    rbx
0x180001c7e  sub     rsp, 40h
0x180001c82  mov     rbx, rcx
0x180001c85  jmp     short loc_180001C96
0x180001c87  mov     rcx, rbx; Size
0x180001c8a  call    _callnewh_0
0x180001c8f  test    eax, eax
0x180001c91  jz      short loc_180001CA6
0x180001c93  mov     rcx, rbx; Size
0x180001c96  call    malloc_0
0x180001c9b  test    rax, rax
0x180001c9e  jz      short loc_180001C87
0x180001ca0  add     rsp, 40h
0x180001ca4  pop     rbx
0x180001ca5  retn
0x180001ca6  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001cab  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180001cb0  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001cb7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001cbc  call    _CxxThrowException_0
```
