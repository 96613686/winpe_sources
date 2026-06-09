# operator new(unsigned __int64)

- ea: `0x180015068`
- end: `0x1800150af`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180001be0`
- `0x180007798`
- `0x180007960`
- `0x18000e194`
- `0x18000e504`
- `0x180011854`
- `0x18001577c`

## callees

- `0x18001501c`
- `0x180015068`
- `0x18001599c`
- `0x1800159a8`

## import_xrefs

- `msvcrt!malloc` at `0x180015082`
- `msvcrt!malloc` at `0x180015082`

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
0x180015068  push    rbx
0x18001506a  sub     rsp, 40h
0x18001506e  mov     rbx, rcx
0x180015071  jmp     short loc_180015082
0x180015073  mov     rcx, rbx; Size
0x180015076  call    _callnewh_0
0x18001507b  test    eax, eax
0x18001507d  jz      short loc_180015093
0x18001507f  mov     rcx, rbx; Size
0x180015082  call    cs:__imp_malloc
0x180015088  test    rax, rax
0x18001508b  jz      short loc_180015073
0x18001508d  add     rsp, 40h
0x180015091  pop     rbx
0x180015092  retn
0x180015093  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180015098  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18001509d  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800150a4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800150a9  call    _CxxThrowException_0
```
