# operator new(unsigned __int64)

- ea: `0x180008700`
- end: `0x180008747`
- name: `??2@YAPEAX_K@Z`
- size: `71`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `4`
- tags: ``

## callers

- `0x180007c34`
- `0x180007e28`
- `0x18000805c`
- `0x180008850`
- `0x18000f2ac`
- `0x18000f680`
- `0x18000f7dc`
- `0x180010f3c`
- `0x1800118ec`
- `0x1800119a4`
- `0x180011b54`
- `0x18001308c`
- `0x18001317c`
- `0x18001c48b`

## callees

- `0x1800086b8`
- `0x180008700`
- `0x180008fc2`
- `0x180008fce`

## import_xrefs

- `msvcrt!malloc` at `0x18000871a`
- `msvcrt!malloc` at `0x18000871a`

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
0x180008700  push    rbx
0x180008702  sub     rsp, 40h
0x180008706  mov     rbx, rcx
0x180008709  jmp     short loc_18000871A
0x18000870b  mov     rcx, rbx; Size
0x18000870e  call    _callnewh_0
0x180008713  test    eax, eax
0x180008715  jz      short loc_18000872B
0x180008717  mov     rcx, rbx; Size
0x18000871a  call    cs:__imp_malloc
0x180008720  test    rax, rax
0x180008723  jz      short loc_18000870B
0x180008725  add     rsp, 40h
0x180008729  pop     rbx
0x18000872a  retn
0x18000872b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008730  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180008735  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000873c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008741  call    _CxxThrowException_0
```
