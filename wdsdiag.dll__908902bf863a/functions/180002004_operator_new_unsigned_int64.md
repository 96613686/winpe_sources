# operator new(unsigned __int64)

- ea: `0x180002004`
- end: `0x18000207d`
- name: `??2@YAPEAX_K@Z`
- size: `121`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002160`

## callees

- `0x180001be0`
- `0x180001fa0`
- `0x180001fc4`
- `0x180002004`
- `0x180002116`
- `0x18000211c`

## import_xrefs

- `msvcrt!malloc` at `0x18000201e`
- `msvcrt!malloc` at `0x18000201e`

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
      if ( (dword_180005618 & 1) == 0 )
      {
        dword_180005618 |= 1u;
        std::bad_alloc::bad_alloc((std::bad_alloc *)&qword_180005600);
        atexit(operator_new_::_7_::_dynamic_atexit_destructor_for__nomem__);
      }
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const struct std::bad_alloc *)&qword_180005600);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002004  push    rbx
0x180002006  sub     rsp, 40h
0x18000200a  mov     rbx, rcx
0x18000200d  jmp     short loc_18000201E
0x18000200f  mov     rcx, rbx; Size
0x180002012  call    _callnewh_0
0x180002017  test    eax, eax
0x180002019  jz      short loc_18000202F
0x18000201b  mov     rcx, rbx; Size
0x18000201e  call    cs:__imp_malloc
0x180002024  test    rax, rax
0x180002027  jz      short loc_18000200F
0x180002029  add     rsp, 40h
0x18000202d  pop     rbx
0x18000202e  retn
0x18000202f  mov     eax, cs:dword_180005618
0x180002035  test    al, 1
0x180002037  jnz     short loc_18000205A
0x180002039  or      eax, 1
0x18000203c  lea     rcx, qword_180005600; this
0x180002043  mov     cs:dword_180005618, eax
0x180002049  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18000204e  lea     rcx, _operator_new____7____dynamic_atexit_destructor_for__nomem__; void (__cdecl *)()
0x180002055  call    atexit
0x18000205a  lea     rdx, qword_180005600; struct std::bad_alloc *
0x180002061  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002066  call    ??0bad_alloc@std@@QEAA@AEBV01@@Z; std::bad_alloc::bad_alloc(std::bad_alloc const &)
0x18000206b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180002072  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002077  call    _CxxThrowException_0
```
