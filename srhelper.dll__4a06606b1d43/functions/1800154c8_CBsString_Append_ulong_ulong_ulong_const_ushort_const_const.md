# CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)

- ea: `0x1800154c8`
- end: `0x180015587`
- name: `?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(CBsString *this, unsigned int, int, unsigned int *const, const unsigned __int16 **const)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180014e30`
- `0x180014ec8`
- `0x180014f38`
- `0x1800152f0`
- `0x180015590`

## callees

- `0x18001509c`
- `0x1800154c8`
- `0x1800157b2`

## pseudocode

```c
__int64 __fastcall CBsString::_Append(
        CBsString *this,
        unsigned int a2,
        int a3,
        unsigned int *const a4,
        const unsigned __int16 **const a5)
{
  int v6; // ebp
  int v9; // edi
  _WORD *v10; // r14
  unsigned int v11; // ebp
  size_t v12; // rbx

  v6 = a3;
  if ( a2 && a4 && a5 )
  {
    v9 = 0;
    if ( a3 )
    {
      v9 = CBsString::ExtendBuffer(this, a3 + 1 + *((_DWORD *)this + 2));
      if ( v9 >= 0 )
      {
        v10 = (_WORD *)(*(_QWORD *)this + 2LL * *((unsigned int *)this + 2));
        if ( a2 )
        {
          v11 = 0;
          do
          {
            v12 = 2LL * a4[v11];
            memcpy_0(v10, a5[v11], v12);
            v10 = (_WORD *)((char *)v10 + v12);
            ++v11;
          }
          while ( v11 < a2 );
          v6 = a3;
        }
        *v10 = 0;
        *((_DWORD *)this + 2) += v6;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800154c8  mov     [rsp+arg_0], rbx
0x1800154cd  mov     [rsp+arg_10], r8d
0x1800154d2  push    rbp
0x1800154d3  push    rsi
0x1800154d4  push    rdi
0x1800154d5  push    r12
0x1800154d7  push    r13
0x1800154d9  push    r14
0x1800154db  push    r15
0x1800154dd  sub     rsp, 20h
0x1800154e1  mov     r13, r9
0x1800154e4  mov     ebp, r8d
0x1800154e7  mov     r12d, edx
0x1800154ea  mov     rsi, rcx
0x1800154ed  test    edx, edx
0x1800154ef  jz      short loc_18001556B
0x1800154f1  test    r9, r9
0x1800154f4  jz      short loc_18001556B
0x1800154f6  mov     r15, [rsp+58h+arg_20]
0x1800154fe  test    r15, r15
0x180015501  jz      short loc_18001556B
0x180015503  xor     edi, edi
0x180015505  test    r8d, r8d
0x180015508  jz      short loc_180015570
0x18001550a  mov     edx, [rcx+8]
0x18001550d  inc     r8d
0x180015510  add     edx, r8d; unsigned int
0x180015513  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180015518  mov     edi, eax
0x18001551a  test    eax, eax
0x18001551c  js      short loc_180015570
0x18001551e  mov     edx, [rsi+8]
0x180015521  mov     rcx, [rsi]
0x180015524  mov     [rsp+58h+arg_8], 0
0x18001552c  lea     r14, [rcx+rdx*2]
0x180015530  test    r12d, r12d
0x180015533  jz      short loc_180015560
0x180015535  mov     ebp, [rsp+58h+arg_8]
0x180015539  mov     edx, ebp
0x18001553b  mov     rcx, r14; void *
0x18001553e  mov     ebx, [r13+rdx*4+0]
0x180015543  mov     rdx, [r15+rdx*8]; Src
0x180015547  add     rbx, rbx
0x18001554a  mov     r8, rbx; Size
0x18001554d  call    memcpy_0
0x180015552  add     r14, rbx
0x180015555  inc     ebp
0x180015557  cmp     ebp, r12d
0x18001555a  jb      short loc_180015539
0x18001555c  mov     ebp, [rsp+58h+arg_10]
0x180015560  xor     eax, eax
0x180015562  mov     [r14], ax
0x180015566  add     [rsi+8], ebp
0x180015569  jmp     short loc_180015570
0x18001556b  mov     edi, 80070057h
0x180015570  mov     rbx, [rsp+58h+arg_0]
0x180015575  mov     eax, edi
0x180015577  add     rsp, 20h
0x18001557b  pop     r15
0x18001557d  pop     r14
0x18001557f  pop     r13
0x180015581  pop     r12
0x180015583  pop     rdi
0x180015584  pop     rsi
0x180015585  pop     rbp
0x180015586  retn
```
