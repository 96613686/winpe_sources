# BaseSrvActivationContextCacheDuplicateKey

- ea: `0x1800056a0`
- end: `0x1800057ca`
- name: `BaseSrvActivationContextCacheDuplicateKey`
- size: `298`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005170`

## callees

- `0x1800056a0`
- `0x1800057d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000574f`
- `ntdll!RtlFreeHeap` at `0x180005779`
- `ntdll!RtlFreeHeap` at `0x1800057a4`
- `ntdll!RtlFreeHeap` at `0x18000574f`
- `ntdll!RtlFreeHeap` at `0x180005779`
- `ntdll!RtlFreeHeap` at `0x1800057a4`

## pseudocode

```c
__int64 __fastcall BaseSrvActivationContextCacheDuplicateKey(__int64 a1, __int64 a2)
{
  int v4; // esi
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8

  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  v4 = BaseSrvActivationContextCacheDuplicateUnicodeString(a1, (const void **)a2);
  if ( v4 < 0
    || (v4 = BaseSrvActivationContextCacheDuplicateUnicodeString(a1 + 24, (const void **)(a2 + 24)), v4 < 0)
    || (*(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16),
        *(_QWORD *)(a1 + 40) = *(_QWORD *)(a2 + 40),
        *(_WORD *)(a1 + 66) = *(_WORD *)(a2 + 66),
        *(_OWORD *)(a1 + 72) = *(_OWORD *)(a2 + 72),
        *(_QWORD *)(a1 + 88) = *(_QWORD *)(a2 + 88),
        v4 = BaseSrvActivationContextCacheDuplicateUnicodeString(a1 + 48, (const void **)(a2 + 48)),
        v4 < 0) )
  {
    v5 = *(void **)(a1 + 8);
    if ( v5 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      *(_OWORD *)a1 = 0;
    }
    v6 = *(void **)(a1 + 32);
    if ( v6 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      *(_OWORD *)(a1 + 24) = 0;
    }
    v7 = *(void **)(a1 + 56);
    if ( v7 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      *(_OWORD *)(a1 + 48) = 0;
    }
  }
  else
  {
    *(_WORD *)(a1 + 64) = *(_WORD *)(a2 + 64);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800056a0  mov     [rsp+arg_0], rbx
0x1800056a5  mov     [rsp+arg_8], rsi
0x1800056aa  push    rdi
0x1800056ab  sub     rsp, 20h
0x1800056af  xorps   xmm0, xmm0
0x1800056b2  mov     rdi, rdx
0x1800056b5  movups  xmmword ptr [rcx], xmm0
0x1800056b8  mov     rbx, rcx
0x1800056bb  movups  xmmword ptr [rcx+10h], xmm0
0x1800056bf  movups  xmmword ptr [rcx+20h], xmm0
0x1800056c3  movups  xmmword ptr [rcx+30h], xmm0
0x1800056c7  movups  xmmword ptr [rcx+40h], xmm0
0x1800056cb  movups  xmmword ptr [rcx+50h], xmm0
0x1800056cf  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x1800056d4  mov     esi, eax
0x1800056d6  test    eax, eax
0x1800056d8  js      short loc_180005737
0x1800056da  lea     rdx, [rdi+18h]
0x1800056de  lea     rcx, [rbx+18h]
0x1800056e2  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x1800056e7  mov     esi, eax
0x1800056e9  test    eax, eax
0x1800056eb  js      short loc_180005737
0x1800056ed  mov     rax, [rdi+10h]
0x1800056f1  lea     rdx, [rdi+30h]
0x1800056f5  mov     [rbx+10h], rax
0x1800056f9  lea     rcx, [rbx+30h]
0x1800056fd  mov     rax, [rdi+28h]
0x180005701  mov     [rbx+28h], rax
0x180005705  movzx   eax, word ptr [rdi+42h]
0x180005709  mov     [rbx+42h], ax
0x18000570d  movups  xmm0, xmmword ptr [rdi+48h]
0x180005711  movups  xmmword ptr [rbx+48h], xmm0
0x180005715  movsd   xmm1, qword ptr [rdi+58h]
0x18000571a  movsd   qword ptr [rbx+58h], xmm1
0x18000571f  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x180005724  mov     esi, eax
0x180005726  test    eax, eax
0x180005728  js      short loc_180005737
0x18000572a  movzx   eax, word ptr [rdi+40h]
0x18000572e  mov     [rbx+40h], ax
0x180005732  jmp     loc_1800057B7
0x180005737  mov     r8, [rbx+8]; P
0x18000573b  test    r8, r8
0x18000573e  jz      short loc_180005761
0x180005740  mov     rcx, gs:60h
0x180005749  xor     edx, edx; Flags
0x18000574b  mov     rcx, [rcx+30h]; HeapHandle
0x18000574f  call    cs:__imp_RtlFreeHeap
0x180005756  nop     dword ptr [rax+rax+00h]
0x18000575b  xorps   xmm0, xmm0
0x18000575e  movups  xmmword ptr [rbx], xmm0
0x180005761  mov     r8, [rbx+20h]; P
0x180005765  test    r8, r8
0x180005768  jz      short loc_18000578C
0x18000576a  mov     rcx, gs:60h
0x180005773  xor     edx, edx; Flags
0x180005775  mov     rcx, [rcx+30h]; HeapHandle
0x180005779  call    cs:__imp_RtlFreeHeap
0x180005780  nop     dword ptr [rax+rax+00h]
0x180005785  xorps   xmm0, xmm0
0x180005788  movups  xmmword ptr [rbx+18h], xmm0
0x18000578c  mov     r8, [rbx+38h]; P
0x180005790  test    r8, r8
0x180005793  jz      short loc_1800057B7
0x180005795  mov     rcx, gs:60h
0x18000579e  xor     edx, edx; Flags
0x1800057a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800057a4  call    cs:__imp_RtlFreeHeap
0x1800057ab  nop     dword ptr [rax+rax+00h]
0x1800057b0  xorps   xmm0, xmm0
0x1800057b3  movups  xmmword ptr [rbx+30h], xmm0
0x1800057b7  mov     rbx, [rsp+28h+arg_0]
0x1800057bc  mov     eax, esi
0x1800057be  mov     rsi, [rsp+28h+arg_8]
0x1800057c3  add     rsp, 20h
0x1800057c7  pop     rdi
0x1800057c8  retn
```
