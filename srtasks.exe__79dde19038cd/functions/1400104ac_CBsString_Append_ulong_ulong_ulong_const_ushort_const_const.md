# CBsString::_Append(ulong,ulong,ulong * const,ushort const * * const)

- ea: `0x1400104ac`
- end: `0x14001056b`
- name: `?_Append@CBsString@@AEAAJKKQEAKQEAPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(CBsString *this, unsigned int, int, unsigned int *const, const unsigned __int16 **const)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fe1c`
- `0x14000fe8c`
- `0x14000fedc`
- `0x140010574`

## callees

- `0x1400100b4`
- `0x1400104ac`
- `0x140010942`

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
0x1400104ac  mov     [rsp+arg_0], rbx
0x1400104b1  mov     [rsp+arg_10], r8d
0x1400104b6  push    rbp
0x1400104b7  push    rsi
0x1400104b8  push    rdi
0x1400104b9  push    r12
0x1400104bb  push    r13
0x1400104bd  push    r14
0x1400104bf  push    r15
0x1400104c1  sub     rsp, 20h
0x1400104c5  mov     r13, r9
0x1400104c8  mov     ebp, r8d
0x1400104cb  mov     r12d, edx
0x1400104ce  mov     rsi, rcx
0x1400104d1  test    edx, edx
0x1400104d3  jz      short loc_14001054F
0x1400104d5  test    r9, r9
0x1400104d8  jz      short loc_14001054F
0x1400104da  mov     r15, [rsp+58h+arg_20]
0x1400104e2  test    r15, r15
0x1400104e5  jz      short loc_14001054F
0x1400104e7  xor     edi, edi
0x1400104e9  test    r8d, r8d
0x1400104ec  jz      short loc_140010554
0x1400104ee  mov     edx, [rcx+8]
0x1400104f1  inc     r8d
0x1400104f4  add     edx, r8d; unsigned int
0x1400104f7  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1400104fc  mov     edi, eax
0x1400104fe  test    eax, eax
0x140010500  js      short loc_140010554
0x140010502  mov     edx, [rsi+8]
0x140010505  mov     rcx, [rsi]
0x140010508  mov     [rsp+58h+arg_8], 0
0x140010510  lea     r14, [rcx+rdx*2]
0x140010514  test    r12d, r12d
0x140010517  jz      short loc_140010544
0x140010519  mov     ebp, [rsp+58h+arg_8]
0x14001051d  mov     edx, ebp
0x14001051f  mov     rcx, r14; void *
0x140010522  mov     ebx, [r13+rdx*4+0]
0x140010527  mov     rdx, [r15+rdx*8]; Src
0x14001052b  add     rbx, rbx
0x14001052e  mov     r8, rbx; Size
0x140010531  call    memcpy_0
0x140010536  add     r14, rbx
0x140010539  inc     ebp
0x14001053b  cmp     ebp, r12d
0x14001053e  jb      short loc_14001051D
0x140010540  mov     ebp, [rsp+58h+arg_10]
0x140010544  xor     eax, eax
0x140010546  mov     [r14], ax
0x14001054a  add     [rsi+8], ebp
0x14001054d  jmp     short loc_140010554
0x14001054f  mov     edi, 80070057h
0x140010554  mov     rbx, [rsp+58h+arg_0]
0x140010559  mov     eax, edi
0x14001055b  add     rsp, 20h
0x14001055f  pop     r15
0x140010561  pop     r14
0x140010563  pop     r13
0x140010565  pop     r12
0x140010567  pop     rdi
0x140010568  pop     rsi
0x140010569  pop     rbp
0x14001056a  retn
```
