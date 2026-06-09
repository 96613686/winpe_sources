# CDNNSenoneEvaluator::PrepareModelEvaluation(int)

- ea: `0x18008bdd0`
- end: `0x18008bf41`
- name: `?PrepareModelEvaluation@CDNNSenoneEvaluator@@UEAAXH@Z`
- size: `369`
- prototype: `void __fastcall(CDNNSenoneEvaluator *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18008ba54`
- `0x18008bdd0`
- `0x18008c318`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008be47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008be90`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008be47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18008be90`

## pseudocode

```c
void __fastcall CDNNSenoneEvaluator::PrepareModelEvaluation(CDNNSenoneEvaluator *this, unsigned int a2)
{
  _DWORD *v2; // r14
  unsigned int *v4; // r15
  unsigned int v5; // r8d
  unsigned int v6; // r13d
  unsigned int v7; // ebp
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // ebx

  v2 = (_DWORD *)((char *)this + 204);
  if ( (!(a2 % *((_DWORD *)this + 61)) || !*v2) && (signed int)a2 >= *v2 )
  {
    v4 = (unsigned int *)((char *)this + 200);
    v5 = *((_DWORD *)this + 64);
    v6 = *((_DWORD *)this + 7) / v5;
    if ( !*v2 )
    {
      v7 = 0;
      if ( *v4 )
      {
        do
        {
          v8 = *((_QWORD *)this + 26);
          v9 = 32LL * v7;
          WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(v9 + v8), 0);
          ++v7;
          *(_DWORD *)(v9 + v8 + 24) = -1;
        }
        while ( v7 < *v4 );
        v5 = *((_DWORD *)this + 64);
      }
    }
    if ( *v4 )
    {
      v10 = *((_QWORD *)this + 26);
      v11 = 32LL * (int)(v6 % *v4);
      if ( *(_DWORD *)(v11 + v10 + 24) == -1 )
      {
        CDNNSenoneEvaluator::Evaluate(this, *(struct CMLP **)(*((_QWORD *)this + 2) + 96LL), v6 * v5);
        v12 = *(_QWORD *)(*((_QWORD *)this + 2) + 96LL);
      }
      else
      {
        WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(v11 + v10), 0);
        *(_DWORD *)(v11 + v10 + 24) = -1;
        v12 = *(_QWORD *)(v11 + *((_QWORD *)this + 26) + 16);
      }
      v13 = v6 + 1;
      *((_QWORD *)this + 29) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 8)
                                                     + 8LL * (unsigned int)(*(_DWORD *)(v12 + 16) - 1))
                                         + 24LL);
      CDNNSenoneEvaluator::TryStartParallelEvaluation(this, v6 + 1);
    }
    else
    {
      CDNNSenoneEvaluator::Evaluate(this, *(struct CMLP **)(*((_QWORD *)this + 2) + 96LL), v6 * v5);
      v13 = v6 + 1;
      *((_QWORD *)this + 29) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 96LL) + 8LL)
                                                     + 8LL
                                                     * (unsigned int)(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 2)
                                                                                            + 96LL)
                                                                                + 16LL)
                                                                    - 1))
                                         + 24LL);
    }
    *v2 = *((_DWORD *)this + 64) * v13;
  }
}

```

## disassembly

```asm
0x18008bdd0  push    rbx
0x18008bdd2  push    rbp
0x18008bdd3  push    rsi
0x18008bdd4  push    rdi
0x18008bdd5  push    r13
0x18008bdd7  push    r14
0x18008bdd9  push    r15
0x18008bddb  sub     rsp, 20h
0x18008bddf  mov     r8d, edx
0x18008bde2  lea     r14, [rcx+0CCh]
0x18008bde9  xor     edx, edx
0x18008bdeb  mov     eax, r8d
0x18008bdee  div     dword ptr [rcx+0F4h]
0x18008bdf4  mov     rsi, rcx
0x18008bdf7  test    edx, edx
0x18008bdf9  jz      short loc_18008BE05
0x18008bdfb  cmp     dword ptr [r14], 0
0x18008bdff  jnz     loc_18008BF32
0x18008be05  cmp     r8d, [r14]
0x18008be08  jl      loc_18008BF32
0x18008be0e  mov     eax, [rcx+1Ch]
0x18008be11  lea     r15, [rcx+0C8h]
0x18008be18  mov     r8d, [rcx+100h]
0x18008be1f  xor     edx, edx
0x18008be21  div     r8d
0x18008be24  cmp     dword ptr [r14], 0
0x18008be28  mov     r13d, eax
0x18008be2b  jnz     short loc_18008BE63
0x18008be2d  xor     ebp, ebp
0x18008be2f  cmp     [r15], ebp
0x18008be32  jbe     short loc_18008BE63
0x18008be34  mov     rbx, [rsi+0D0h]
0x18008be3b  xor     edx, edx; fCancelPendingCallbacks
0x18008be3d  mov     edi, ebp
0x18008be3f  shl     rdi, 5
0x18008be43  mov     rcx, [rdi+rbx]; pwk
0x18008be47  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008be4d  inc     ebp
0x18008be4f  mov     dword ptr [rdi+rbx+18h], 0FFFFFFFFh
0x18008be57  cmp     ebp, [r15]
0x18008be5a  jb      short loc_18008BE34
0x18008be5c  mov     r8d, [rsi+100h]
0x18008be63  cmp     dword ptr [r15], 0
0x18008be67  jbe     loc_18008BEF0
0x18008be6d  mov     rdi, [rsi+0D0h]
0x18008be74  xor     edx, edx
0x18008be76  mov     eax, r13d
0x18008be79  div     dword ptr [r15]
0x18008be7c  movsxd  rbx, edx
0x18008be7f  shl     rbx, 5
0x18008be83  cmp     dword ptr [rbx+rdi+18h], 0FFFFFFFFh
0x18008be88  jz      short loc_18008BEAC
0x18008be8a  mov     rcx, [rbx+rdi]; pwk
0x18008be8e  xor     edx, edx; fCancelPendingCallbacks
0x18008be90  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008be96  mov     dword ptr [rbx+rdi+18h], 0FFFFFFFFh
0x18008be9e  mov     rax, [rsi+0D0h]
0x18008bea5  mov     rdx, [rbx+rax+10h]
0x18008beaa  jmp     short loc_18008BEC8
0x18008beac  mov     rdx, [rsi+10h]
0x18008beb0  mov     rcx, rsi; this
0x18008beb3  imul    r8d, r13d; int
0x18008beb7  mov     rdx, [rdx+60h]; struct CMLP *
0x18008bebb  call    ?Evaluate@CDNNSenoneEvaluator@@QEAAXPEAVCMLP@@H@Z; CDNNSenoneEvaluator::Evaluate(CMLP *,int)
0x18008bec0  mov     rax, [rsi+10h]
0x18008bec4  mov     rdx, [rax+60h]
0x18008bec8  mov     ecx, [rdx+10h]
0x18008becb  lea     ebx, [r13+1]
0x18008becf  mov     rax, [rdx+8]
0x18008bed3  dec     ecx
0x18008bed5  mov     edx, ebx; int
0x18008bed7  mov     rax, [rax+rcx*8]
0x18008bedb  mov     rcx, rsi; this
0x18008bede  mov     rax, [rax+18h]
0x18008bee2  mov     [rsi+0E8h], rax
0x18008bee9  call    ?TryStartParallelEvaluation@CDNNSenoneEvaluator@@IEAAXH@Z; CDNNSenoneEvaluator::TryStartParallelEvaluation(int)
0x18008beee  jmp     short loc_18008BF28
0x18008bef0  mov     rdx, [rsi+10h]
0x18008bef4  mov     rcx, rsi; this
0x18008bef7  imul    r8d, r13d; int
0x18008befb  mov     rdx, [rdx+60h]; struct CMLP *
0x18008beff  call    ?Evaluate@CDNNSenoneEvaluator@@QEAAXPEAVCMLP@@H@Z; CDNNSenoneEvaluator::Evaluate(CMLP *,int)
0x18008bf04  mov     rax, [rsi+10h]
0x18008bf08  lea     ebx, [r13+1]
0x18008bf0c  mov     rdx, [rax+60h]
0x18008bf10  mov     ecx, [rdx+10h]
0x18008bf13  mov     rax, [rdx+8]
0x18008bf17  dec     ecx
0x18008bf19  mov     rcx, [rax+rcx*8]
0x18008bf1d  mov     rax, [rcx+18h]
0x18008bf21  mov     [rsi+0E8h], rax
0x18008bf28  imul    ebx, [rsi+100h]
0x18008bf2f  mov     [r14], ebx
0x18008bf32  add     rsp, 20h
0x18008bf36  pop     r15
0x18008bf38  pop     r14
0x18008bf3a  pop     r13
0x18008bf3c  pop     rdi
0x18008bf3d  pop     rsi
0x18008bf3e  pop     rbp
0x18008bf3f  pop     rbx
0x18008bf40  retn
```
