# RtlCopyContext

- ea: `0x1400fd9b8`
- end: `0x1400fdb75`
- name: `RtlCopyContext`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140096d40`

## callees

- `0x1400d86cc`
- `0x1400d8714`
- `0x1400d8ff4`
- `0x1400d927c`
- `0x1400d9434`
- `0x1400fd9b8`

## pseudocode

```c
__int64 __fastcall RtlCopyContext(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  int *v8; // rax
  unsigned int *v9; // r8
  unsigned int v10; // r12d
  int v11; // r14d
  unsigned int v12; // r14d
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 v15; // rsi
  char v16; // r14
  int v17; // [rsp+30h] [rbp-58h] BYREF
  _DWORD *ContextFlagsLocation; // [rsp+38h] [rbp-50h]
  int v19; // [rsp+A8h] [rbp+20h] BYREF

  v17 = 0;
  v19 = 0;
  result = RtlpValidateContextFlags(a2, 0);
  if ( (int)result >= 0 )
  {
    ContextFlagsLocation = (_DWORD *)RtlpGetContextFlagsLocation(a1, a2);
    v8 = (int *)RtlpGetContextFlagsLocation(a3, v7);
    v10 = *v9;
    v11 = *v8;
    result = RtlpValidateContextFlags(a2 | *v8 | *v9, 0);
    if ( (int)result >= 0 )
    {
      v12 = a2 & v11;
      result = RtlpValidateContextFlags(v12, &v17);
      if ( (int)result >= 0 )
      {
        result = RtlpValidateContextFlags(v10, &v19);
        v13 = result;
        if ( (int)result >= 0 )
        {
          if ( (~v19 & v17) != 0 )
          {
            return 2147483653LL;
          }
          else
          {
            v14 = 0;
            v15 = 0;
            RtlpCopyLegacyContext(0, a1, v12, a3);
            *ContextFlagsLocation |= v10;
            if ( (v19 & 0xFFFFFFFE) != 0 )
            {
              if ( (v12 & 0x10000) != 0 )
              {
                v15 = a3 + 716;
                v14 = a1 + 716;
                if ( (v12 & 0x10020) == 65568 && (v10 & 0x10020) != 65568 )
                  *(_DWORD *)(a1 + 728) = 716;
              }
              else if ( (a2 & 0x100000) != 0 )
              {
                v15 = a3 + 1232;
                v14 = a1 + 1232;
              }
              else if ( (a2 & 0x200000) != 0 )
              {
                v15 = a3 + 416;
                v14 = a1 + 416;
              }
              else if ( (a2 & 0x400000) != 0 )
              {
                v15 = a3 + 912;
                v14 = a1 + 912;
              }
            }
            v16 = v17;
            if ( (v17 & 2) == 0
              || (result = RtlpCopyXStateChunk(0, v14, v14, v15, v15, a2), v13 = result, (int)result >= 0) )
            {
              if ( (v16 & 4) == 0 )
                return v13;
              result = RtlpCopyKernelCetChunk(0, v14, v14, v15, v15);
              v13 = result;
              if ( (int)result >= 0 )
                return v13;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400fd9b8  mov     rax, rsp
0x1400fd9bb  push    rbx
0x1400fd9bc  push    rbp
0x1400fd9bd  push    rsi
0x1400fd9be  push    rdi
0x1400fd9bf  push    r12
0x1400fd9c1  push    r13
0x1400fd9c3  push    r14
0x1400fd9c5  push    r15
0x1400fd9c7  sub     rsp, 48h
0x1400fd9cb  mov     ebp, edx
0x1400fd9cd  mov     dword ptr [rax-58h], 0
0x1400fd9d4  mov     r13, rcx
0x1400fd9d7  mov     dword ptr [rax+20h], 0
0x1400fd9de  mov     ecx, ebp
0x1400fd9e0  xor     edx, edx
0x1400fd9e2  mov     r15, r8
0x1400fd9e5  call    RtlpValidateContextFlags
0x1400fd9ea  test    eax, eax
0x1400fd9ec  js      loc_1400FDB63
0x1400fd9f2  mov     edx, ebp
0x1400fd9f4  mov     rcx, r13
0x1400fd9f7  call    RtlpGetContextFlagsLocation
0x1400fd9fc  mov     rcx, r15
0x1400fd9ff  mov     [rsp+88h+var_50], rax
0x1400fda04  mov     r8, rax
0x1400fda07  call    RtlpGetContextFlagsLocation
0x1400fda0c  mov     r12d, [r8]
0x1400fda0f  xor     edx, edx
0x1400fda11  mov     ecx, r12d
0x1400fda14  mov     r14d, [rax]
0x1400fda17  or      ecx, r14d
0x1400fda1a  or      ecx, ebp
0x1400fda1c  call    RtlpValidateContextFlags
0x1400fda21  test    eax, eax
0x1400fda23  js      loc_1400FDB63
0x1400fda29  and     r14d, ebp
0x1400fda2c  lea     rdx, [rsp+88h+var_58]
0x1400fda31  mov     ecx, r14d
0x1400fda34  call    RtlpValidateContextFlags
0x1400fda39  test    eax, eax
0x1400fda3b  js      loc_1400FDB63
0x1400fda41  lea     rdx, [rsp+88h+arg_18]
0x1400fda49  mov     ecx, r12d
0x1400fda4c  call    RtlpValidateContextFlags
0x1400fda51  mov     ebx, eax
0x1400fda53  test    eax, eax
0x1400fda55  js      loc_1400FDB63
0x1400fda5b  mov     eax, [rsp+88h+arg_18]
0x1400fda62  not     eax
0x1400fda64  test    [rsp+88h+var_58], eax
0x1400fda68  jz      short loc_1400FDA74
0x1400fda6a  mov     eax, 80000005h
0x1400fda6f  jmp     loc_1400FDB63
0x1400fda74  mov     r9, r15
0x1400fda77  mov     r8d, r14d
0x1400fda7a  mov     rdx, r13
0x1400fda7d  xor     ecx, ecx
0x1400fda7f  xor     edi, edi
0x1400fda81  xor     esi, esi
0x1400fda83  call    RtlpCopyLegacyContext
0x1400fda88  mov     rax, [rsp+88h+var_50]
0x1400fda8d  or      [rax], r12d
0x1400fda90  test    [rsp+88h+arg_18], 0FFFFFFFEh
0x1400fda9b  jz      short loc_1400FDB16
0x1400fda9d  bt      r14d, 10h
0x1400fdaa2  jnb     short loc_1400FDAD6
0x1400fdaa4  mov     eax, 10020h
0x1400fdaa9  lea     rsi, [r15+2CCh]
0x1400fdab0  and     r14d, eax
0x1400fdab3  lea     rdi, [r13+2CCh]
0x1400fdaba  cmp     r14d, eax
0x1400fdabd  setz    cl
0x1400fdac0  and     r12d, eax
0x1400fdac3  cmp     r12d, eax
0x1400fdac6  setnz   al
0x1400fdac9  test    al, cl
0x1400fdacb  jz      short loc_1400FDB16
0x1400fdacd  mov     dword ptr [rdi+0Ch], 2CCh
0x1400fdad4  jmp     short loc_1400FDB16
0x1400fdad6  bt      ebp, 14h
0x1400fdada  jnb     short loc_1400FDAEC
0x1400fdadc  lea     rsi, [r15+4D0h]
0x1400fdae3  lea     rdi, [r13+4D0h]
0x1400fdaea  jmp     short loc_1400FDB16
0x1400fdaec  bt      ebp, 15h
0x1400fdaf0  jnb     short loc_1400FDB02
0x1400fdaf2  lea     rsi, [r15+1A0h]
0x1400fdaf9  lea     rdi, [r13+1A0h]
0x1400fdb00  jmp     short loc_1400FDB16
0x1400fdb02  bt      ebp, 16h
0x1400fdb06  jnb     short loc_1400FDB16
0x1400fdb08  lea     rsi, [r15+390h]
0x1400fdb0f  lea     rdi, [r13+390h]
0x1400fdb16  mov     r14d, [rsp+88h+var_58]
0x1400fdb1b  test    r14b, 2
0x1400fdb1f  jz      short loc_1400FDB40
0x1400fdb21  mov     [rsp+88h+var_60], ebp
0x1400fdb25  mov     r9, rsi
0x1400fdb28  mov     r8, rdi
0x1400fdb2b  mov     [rsp+88h+var_68], rsi
0x1400fdb30  mov     rdx, rdi
0x1400fdb33  xor     ecx, ecx
0x1400fdb35  call    RtlpCopyXStateChunk
0x1400fdb3a  mov     ebx, eax
0x1400fdb3c  test    eax, eax
0x1400fdb3e  js      short loc_1400FDB63
0x1400fdb40  test    r14b, 4
0x1400fdb44  jz      short loc_1400FDB61
0x1400fdb46  mov     r9, rsi
0x1400fdb49  mov     [rsp+88h+var_68], rsi
0x1400fdb4e  mov     r8, rdi
0x1400fdb51  mov     rdx, rdi
0x1400fdb54  xor     ecx, ecx
0x1400fdb56  call    RtlpCopyKernelCetChunk
0x1400fdb5b  mov     ebx, eax
0x1400fdb5d  test    eax, eax
0x1400fdb5f  js      short loc_1400FDB63
0x1400fdb61  mov     eax, ebx
0x1400fdb63  add     rsp, 48h
0x1400fdb67  pop     r15
0x1400fdb69  pop     r14
0x1400fdb6b  pop     r13
0x1400fdb6d  pop     r12
0x1400fdb6f  pop     rdi
0x1400fdb70  pop     rsi
0x1400fdb71  pop     rbp
0x1400fdb72  pop     rbx
0x1400fdb73  retn
```
