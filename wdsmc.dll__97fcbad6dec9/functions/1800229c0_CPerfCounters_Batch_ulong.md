# CPerfCounters::Batch(ulong,...)

- ea: `0x1800229c0`
- end: `0x180022a2e`
- name: `?Batch@CPerfCounters@@QEAAKKZZ`
- size: `110`
- prototype: `unsigned int(CPerfCounters *__hidden this, unsigned int, ...)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180002368`
- `0x1800026b8`
- `0x180003f10`
- `0x180004184`
- `0x18000b430`
- `0x18000b560`
- `0x18000b8e8`
- `0x18000bdd4`
- `0x18000e65c`
- `0x18000e7c8`
- `0x18000ff2c`
- `0x180012c98`
- `0x1800132cc`
- `0x180013c10`
- `0x1800148b4`
- `0x1800150c0`
- `0x180015424`
- `0x1800154b4`
- `0x180015c34`
- `0x1800191c0`
- `0x1800193f8`

## callees

- `0x1800229c0`

## pseudocode

```c
__int64 CPerfCounters::Batch(CPerfCounters *this, unsigned int a2, ...)
{
  __int64 result; // rax
  va_list v3; // r8
  int v6; // r11d
  __int64 v7; // r9
  va_list v8; // rdx
  unsigned int v9; // ecx
  unsigned __int64 v10; // rdx
  va_list va; // [rsp+40h] [rbp+18h] BYREF

  va_start(va, a2);
  result = 0;
  va_copy(v3, va);
  v6 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v7 = *(unsigned int *)v3;
      v8 = v3;
      v3 += 24;
      v9 = *((_DWORD *)v3 - 2);
      if ( (unsigned int)v7 >= *((_DWORD *)this + 6) )
        break;
      if ( *((_DWORD *)v8 + 2) )
        v10 = -v9;
      else
        v10 = v9;
      _InterlockedExchangeAdd64((volatile signed __int64 *)(*((_QWORD *)this + 1) + 8 * v7), v10);
      if ( ++v6 >= a2 )
        return result;
    }
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x1800229c0  mov     [rsp+arg_8], edx
0x1800229c4  mov     [rsp+arg_10], r8
0x1800229c9  mov     [rsp+arg_18], r9
0x1800229ce  push    rbx
0x1800229cf  push    rdi
0x1800229d0  sub     rsp, 18h
0x1800229d4  xor     eax, eax
0x1800229d6  lea     r8, [rsp+28h+arg_10]
0x1800229db  mov     [rsp+28h+var_28], r8
0x1800229df  mov     r10d, edx
0x1800229e2  mov     rdi, rcx
0x1800229e5  mov     r11d, eax
0x1800229e8  test    edx, edx
0x1800229ea  jz      short loc_180022A27
0x1800229ec  mov     r9d, [r8]
0x1800229ef  lea     rdx, [r8]
0x1800229f2  lea     r8, [r8+18h]
0x1800229f6  mov     ecx, [r8-8]
0x1800229fa  cmp     r9d, [rdi+18h]
0x1800229fe  jnb     short loc_180022A22
0x180022a00  mov     rbx, [rdi+8]
0x180022a04  cmp     [rdx+8], eax
0x180022a07  jnz     short loc_180022A0D
0x180022a09  mov     edx, ecx
0x180022a0b  jmp     short loc_180022A12
0x180022a0d  neg     ecx
0x180022a0f  movsxd  rdx, ecx
0x180022a12  lock xadd [rbx+r9*8], rdx
0x180022a18  inc     r11d
0x180022a1b  cmp     r11d, r10d
0x180022a1e  jb      short loc_1800229EC
0x180022a20  jmp     short loc_180022A27
0x180022a22  mov     eax, 57h ; 'W'
0x180022a27  add     rsp, 18h
0x180022a2b  pop     rdi
0x180022a2c  pop     rbx
0x180022a2d  retn
```
