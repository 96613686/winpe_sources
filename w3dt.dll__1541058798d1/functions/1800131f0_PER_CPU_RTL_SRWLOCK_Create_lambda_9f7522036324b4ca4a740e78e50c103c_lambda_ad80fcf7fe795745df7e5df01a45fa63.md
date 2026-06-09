# PER_CPU__RTL_SRWLOCK_::Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___

- ea: `0x1800131f0`
- end: `0x1800132c6`
- name: `PER_CPU__RTL_SRWLOCK_::Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001060`

## callees

- `0x180012d44`
- `0x1800131f0`
- `0x180016072`

## import_xrefs

- `msvcrt!_aligned_malloc` at `0x180013253`
- `msvcrt!_aligned_malloc` at `0x180013253`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001329e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001329e`

## pseudocode

```c
__int64 __fastcall PER_CPU__RTL_SRWLOCK_::Create__lambda_9f7522036324b4ca4a740e78e50c103c___lambda_ad80fcf7fe795745df7e5df01a45fa63___(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // r14
  size_t v7; // rbp
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rax
  size_t Alignment[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(Alignment[0]) = 0;
  v14 = 0;
  result = PER_CPU<_RTL_SRWLOCK>::GetProcessorInformation(Alignment, &v14);
  if ( (int)result >= 0 )
  {
    if ( LODWORD(Alignment[0]) >= 8 )
      v5 = Alignment[0];
    else
      v5 = (LODWORD(Alignment[0]) + 7) & ~(LODWORD(Alignment[0]) - 1);
    v6 = LODWORD(Alignment[0]);
    v7 = LODWORD(Alignment[0]) + v5 * v14;
    v8 = _aligned_malloc(v7, LODWORD(Alignment[0]));
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, v7);
      v10 = v14;
      *v9 = (char *)v9 + v6;
      v9[1] = v5;
      v9[2] = v10;
      if ( v10 )
      {
        v11 = 0;
        v12 = 0;
        do
        {
          InitializeSRWLock((PSRWLOCK)(*v9 + v9[1] * v12));
          v12 = ++v11;
        }
        while ( (unsigned __int64)v11 < v9[2] );
      }
      result = 0;
      *a3 = v9;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800131f0  mov     rax, rsp
0x1800131f3  mov     [rax+8], rbx
0x1800131f7  mov     [rax+10h], rbp
0x1800131fb  push    rsi
0x1800131fc  push    rdi
0x1800131fd  push    r14
0x1800131ff  sub     rsp, 30h
0x180013203  lea     rdx, [rax+20h]
0x180013207  mov     dword ptr [rax-28h], 0
0x18001320e  lea     rcx, [rax-28h]
0x180013212  mov     dword ptr [rax+20h], 0
0x180013219  mov     rsi, r8
0x18001321c  call    ?GetProcessorInformation@?$PER_CPU@U_RTL_SRWLOCK@@@@CAJPEAK0@Z; PER_CPU<_RTL_SRWLOCK>::GetProcessorInformation(ulong *,ulong *)
0x180013221  test    eax, eax
0x180013223  js      loc_1800132B3
0x180013229  mov     ecx, dword ptr [rsp+48h+Alignment]
0x18001322d  cmp     ecx, 8
0x180013230  jnb     short loc_18001323E
0x180013232  lea     ebx, [rcx-1]
0x180013235  not     ebx
0x180013237  lea     eax, [rcx+7]
0x18001323a  and     ebx, eax
0x18001323c  jmp     short loc_180013240
0x18001323e  mov     ebx, ecx
0x180013240  mov     eax, [rsp+48h+arg_18]
0x180013244  mov     r14, rcx
0x180013247  imul    eax, ebx
0x18001324a  mov     rdx, rcx; Alignment
0x18001324d  add     eax, ecx
0x18001324f  mov     ecx, eax; Size
0x180013251  mov     ebp, eax
0x180013253  call    cs:__imp__aligned_malloc
0x180013259  mov     rdi, rax
0x18001325c  test    rax, rax
0x18001325f  jnz     short loc_180013268
0x180013261  mov     eax, 8007000Eh
0x180013266  jmp     short loc_1800132B3
0x180013268  mov     r8, rbp; Size
0x18001326b  xor     edx, edx; Val
0x18001326d  mov     rcx, rdi; void *
0x180013270  call    memset_0
0x180013275  mov     ecx, [rsp+48h+arg_18]
0x180013279  lea     rax, [r14+rdi]
0x18001327d  mov     [rdi], rax
0x180013280  mov     eax, ebx
0x180013282  mov     [rdi+8], rax
0x180013286  mov     [rdi+10h], rcx
0x18001328a  test    rcx, rcx
0x18001328d  jz      short loc_1800132AE
0x18001328f  xor     ebx, ebx
0x180013291  xor     eax, eax
0x180013293  imul    rax, [rdi+8]
0x180013298  add     rax, [rdi]
0x18001329b  mov     rcx, rax; SRWLock
0x18001329e  call    cs:__imp_InitializeSRWLock
0x1800132a4  inc     ebx
0x1800132a6  mov     eax, ebx
0x1800132a8  cmp     rax, [rdi+10h]
0x1800132ac  jb      short loc_180013293
0x1800132ae  xor     eax, eax
0x1800132b0  mov     [rsi], rdi
0x1800132b3  mov     rbx, [rsp+48h+arg_0]
0x1800132b8  mov     rbp, [rsp+48h+arg_8]
0x1800132bd  add     rsp, 30h
0x1800132c1  pop     r14
0x1800132c3  pop     rdi
0x1800132c4  pop     rsi
0x1800132c5  retn
```
