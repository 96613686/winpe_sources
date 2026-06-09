# SkmiConfigureBootKernelShadowStacks

- ea: `0x14006cd8c`
- end: `0x14006cfd8`
- name: `SkmiConfigureBootKernelShadowStacks`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005a0f8`

## callees

- `0x140003780`
- `0x14002b534`
- `0x140050ba4`
- `0x14006cd8c`
- `0x14006cfe0`
- `0x140076948`
- `0x14007c380`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 SkmiConfigureBootKernelShadowStacks()
{
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r15
  unsigned __int64 *v1; // rsi
  __int64 result; // rax
  unsigned int v3; // edi
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  unsigned __int64 *v6; // r14
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  int v9; // eax
  __int64 v10; // rbx
  __int64 *v11; // r14
  unsigned __int64 v12; // rbx
  __int64 PteTrace; // rax
  __int64 v14; // rsi
  PVOID *v15; // rdi
  PVOID StackBase; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h]
  __int64 BackTraceHash; // [rsp+90h] [rbp+8h] BYREF

  if ( (SkmiFlags & 0x80000) == 0 )
    return 0;
  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  v1 = *(unsigned __int64 **)(*(_QWORD *)(SkeLoaderBlock + 48) + 0x80000000F0LL);
  result = SkmiCreateNtBootShadowStack(v1[0x10000001D0LL], 2, (__int64)(v1 + 0x10000001D0LL));
  if ( (int)result >= 0 )
  {
    result = SkmiCreateNtBootShadowStack(v1[0x10000001D1LL], 1, (__int64)(v1 + 0x10000001D1LL));
    if ( (int)result >= 0 )
    {
      v3 = 1;
      v4 = v1[0x10000001D2LL] + 0x8000000000LL;
      while ( 1 )
      {
        v5 = v3;
        v6 = (unsigned __int64 *)(v4 + 8LL * v3);
        result = SkmiCreateNtBootShadowStack(*v6, 1, (__int64)v6);
        if ( (int)result < 0 )
          break;
        ++v3;
        *((_QWORD *)&ExceptionList[187].Next + v5) = *v6;
        if ( v3 > 4 )
        {
          v8 = (_QWORD *)(((v4 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL);
          v9 = SkmiRelocateBootPage(v8, v7, 1);
          v10 = *v8 >> 12;
          if ( !v9 )
          {
            BackTraceHash = v10 & 0xFFFFFFFFFFLL;
            if ( !(unsigned int)SkmiClaimPhysicalPages((ULONG_PTR)&BackTraceHash, 1, 0x8005u) )
              return 3221225496LL;
          }
          if ( (int)SkmiReserveNar(v1[0x10000001D2LL], 4096, 0, 0, 0, 0, 0) >= 0 )
          {
            v11 = (__int64 *)(((v1[0x10000001D2LL] >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
            v12 = (v10 << 12) & 0xFFFFFFFFFF000LL ^ 0x8000000000000021uLL;
            PteTrace = SkmiGetPteTrace(0, (unsigned int)(v1[0x10000001D2LL] >> 9) & 0xFFFFFFF8, 0, v12, *v11);
            v14 = PteTrace;
            if ( PteTrace )
            {
              v15 = (PVOID *)(PteTrace + 32);
              memset_0((void *)(PteTrace + 32), 0, 0x40u);
              if ( (SkmiFlags & 0x400000) != 0 )
              {
                StackBase = KeGetPcr()->NtTib.StackBase;
                if ( StackBase )
                {
                  if ( !RtlCaptureStackBackTrace((ULONG)StackBase, 8u, v15, (PULONG)&BackTraceHash) )
                  {
                    *(_QWORD *)(v14 + 40) = retaddr;
                    *v15 = (PVOID)SkmiGetInstructionPointer(v18, v17);
                  }
                }
              }
            }
            *v11 = v12;
          }
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14006cd8c  push    rbx
0x14006cd8e  push    rbp
0x14006cd8f  push    rsi
0x14006cd90  push    rdi
0x14006cd91  push    r12
0x14006cd93  push    r13
0x14006cd95  push    r14
0x14006cd97  push    r15
0x14006cd99  sub     rsp, 48h
0x14006cd9d  test    cs:SkmiFlags, 80000h
0x14006cda7  jz      loc_14006CFC4
0x14006cdad  mov     r15, gs:0
0x14006cdb6  mov     rsi, 80000000F0h
0x14006cdc0  mov     rax, cs:SkeLoaderBlock
0x14006cdc7  mov     edx, 2
0x14006cdcc  mov     rcx, [rax+30h]
0x14006cdd0  mov     rsi, [rcx+rsi]
0x14006cdd4  mov     rcx, 8000000E80h
0x14006cdde  add     rcx, rsi
0x14006cde1  mov     r8, rcx
0x14006cde4  mov     rcx, [rcx]
0x14006cde7  call    SkmiCreateNtBootShadowStack
0x14006cdec  xor     r12d, r12d
0x14006cdef  test    eax, eax
0x14006cdf1  js      loc_14006CFC6
0x14006cdf7  mov     rcx, 8000000E88h
0x14006ce01  lea     r13d, [r12+1]
0x14006ce06  add     rcx, rsi
0x14006ce09  mov     edx, r13d
0x14006ce0c  mov     r8, rcx
0x14006ce0f  mov     rcx, [rcx]
0x14006ce12  call    SkmiCreateNtBootShadowStack
0x14006ce17  test    eax, eax
0x14006ce19  js      loc_14006CFC6
0x14006ce1f  mov     rax, 8000000E90h
0x14006ce29  mov     edi, r13d
0x14006ce2c  mov     rbx, [rsi+rax]
0x14006ce30  mov     rax, 8000000000h
0x14006ce3a  add     rbx, rax
0x14006ce3d  mov     ebp, edi
0x14006ce3f  mov     edx, r13d
0x14006ce42  lea     r14, [rbx+rbp*8]
0x14006ce46  mov     rcx, [r14]
0x14006ce49  mov     r8, r14
0x14006ce4c  call    SkmiCreateNtBootShadowStack
0x14006ce51  test    eax, eax
0x14006ce53  js      loc_14006CFC6
0x14006ce59  mov     rax, [r14]
0x14006ce5c  add     edi, r13d
0x14006ce5f  mov     [r15+rbp*8+0BB0h], rax
0x14006ce67  cmp     edi, 4
0x14006ce6a  jbe     short loc_14006CE3D
0x14006ce6c  shr     rbx, 9
0x14006ce70  mov     rbp, 7FFFFFFFF8h
0x14006ce7a  and     rbx, rbp
0x14006ce7d  mov     rax, 0FFFFF68000000000h
0x14006ce87  add     rbx, rax
0x14006ce8a  mov     r8d, r13d
0x14006ce8d  mov     rcx, rbx
0x14006ce90  call    SkmiRelocateBootPage
0x14006ce95  mov     rbx, [rbx]
0x14006ce98  shr     rbx, 0Ch
0x14006ce9c  test    eax, eax
0x14006ce9e  jnz     short loc_14006CEDC
0x14006cea0  mov     rcx, 0FFFFFFFFFFh
0x14006ceaa  mov     rax, rbx
0x14006cead  and     rax, rcx
0x14006ceb0  mov     r8d, 8005h
0x14006ceb6  lea     rcx, [rsp+88h+BackTraceHash]
0x14006cebe  mov     [rsp+88h+BackTraceHash], rax
0x14006cec6  mov     edx, r13d
0x14006cec9  call    SkmiClaimPhysicalPages
0x14006cece  test    eax, eax
0x14006ced0  jnz     short loc_14006CEDC
0x14006ced2  mov     eax, 0C0000018h
0x14006ced7  jmp     loc_14006CFC6
0x14006cedc  mov     [rsp+88h+var_58], r12; __int64
0x14006cee1  mov     rdi, 8000000E90h
0x14006ceeb  mov     qword ptr [rsp+88h+var_60], r12; BackTraceHash
0x14006cef0  xor     r9d, r9d; int
0x14006cef3  xor     r8d, r8d; int
0x14006cef6  mov     [rsp+88h+var_68], r12; __int64
0x14006cefb  mov     edx, 1000h; int
0x14006cf00  mov     rcx, [rsi+rdi]; int
0x14006cf04  call    SkmiReserveNar
0x14006cf09  test    eax, eax
0x14006cf0b  js      loc_14006CFC4
0x14006cf11  mov     r14, [rsi+rdi]
0x14006cf15  shr     r14, 9
0x14006cf19  and     r14, rbp
0x14006cf1c  mov     rcx, 0FFFFF60000000000h
0x14006cf26  add     r14, rcx
0x14006cf29  shl     rbx, 0Ch
0x14006cf2d  mov     rax, 0FFFFFFFFFF000h
0x14006cf37  xor     r8d, r8d
0x14006cf3a  and     rbx, rax
0x14006cf3d  mov     rdx, r14
0x14006cf40  mov     rax, 8000000000000021h
0x14006cf4a  xor     ecx, ecx
0x14006cf4c  xor     rbx, rax
0x14006cf4f  mov     rax, [r14]
0x14006cf52  mov     r9, rbx
0x14006cf55  mov     [rsp+88h+var_68], rax
0x14006cf5a  call    SkmiGetPteTrace
0x14006cf5f  mov     rsi, rax
0x14006cf62  test    rax, rax
0x14006cf65  jz      short loc_14006CFC1
0x14006cf67  xor     edx, edx; Val
0x14006cf69  lea     rdi, [rax+20h]
0x14006cf6d  mov     rcx, rdi; void *
0x14006cf70  lea     r8d, [rdx+40h]; Size
0x14006cf74  call    memset_0
0x14006cf79  test    cs:SkmiFlags, 400000h
0x14006cf83  jz      short loc_14006CFC1
0x14006cf85  mov     rcx, gs:8; FramesToSkip
0x14006cf8e  test    rcx, rcx
0x14006cf91  jz      short loc_14006CFC1
0x14006cf93  lea     r9, [rsp+88h+BackTraceHash]; BackTraceHash
0x14006cf9b  mov     r8, rdi; BackTrace
0x14006cf9e  mov     edx, 8; FramesToCapture
0x14006cfa3  call    RtlCaptureStackBackTrace
0x14006cfa8  test    ax, ax
0x14006cfab  jnz     short loc_14006CFC1
0x14006cfad  mov     rax, [rsp+88h]
0x14006cfb5  mov     [rsi+28h], rax
0x14006cfb9  call    SkmiGetInstructionPointer
0x14006cfbe  mov     [rdi], rax
0x14006cfc1  mov     [r14], rbx
0x14006cfc4  xor     eax, eax
0x14006cfc6  add     rsp, 48h
0x14006cfca  pop     r15
0x14006cfcc  pop     r14
0x14006cfce  pop     r13
0x14006cfd0  pop     r12
0x14006cfd2  pop     rdi
0x14006cfd3  pop     rsi
0x14006cfd4  pop     rbp
0x14006cfd5  pop     rbx
0x14006cfd6  retn
```
