# BaseSrvActivationContextCacheDuplicateKey

- ea: `0x1800054c0`
- end: `0x1800055ea`
- name: `BaseSrvActivationContextCacheDuplicateKey`
- size: `298`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004fa0`

## callees

- `0x1800054c0`
- `0x1800055f0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000556f`
- `ntdll!RtlFreeHeap` at `0x180005599`
- `ntdll!RtlFreeHeap` at `0x1800055c4`
- `ntdll!RtlFreeHeap` at `0x18000556f`
- `ntdll!RtlFreeHeap` at `0x180005599`
- `ntdll!RtlFreeHeap` at `0x1800055c4`

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
0x1800054c0  mov     [rsp+arg_0], rbx
0x1800054c5  mov     [rsp+arg_8], rsi
0x1800054ca  push    rdi
0x1800054cb  sub     rsp, 20h
0x1800054cf  xorps   xmm0, xmm0
0x1800054d2  mov     rdi, rdx
0x1800054d5  movups  xmmword ptr [rcx], xmm0
0x1800054d8  mov     rbx, rcx
0x1800054db  movups  xmmword ptr [rcx+10h], xmm0
0x1800054df  movups  xmmword ptr [rcx+20h], xmm0
0x1800054e3  movups  xmmword ptr [rcx+30h], xmm0
0x1800054e7  movups  xmmword ptr [rcx+40h], xmm0
0x1800054eb  movups  xmmword ptr [rcx+50h], xmm0
0x1800054ef  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x1800054f4  mov     esi, eax
0x1800054f6  test    eax, eax
0x1800054f8  js      short loc_180005557
0x1800054fa  lea     rdx, [rdi+18h]
0x1800054fe  lea     rcx, [rbx+18h]
0x180005502  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x180005507  mov     esi, eax
0x180005509  test    eax, eax
0x18000550b  js      short loc_180005557
0x18000550d  mov     rax, [rdi+10h]
0x180005511  lea     rdx, [rdi+30h]
0x180005515  mov     [rbx+10h], rax
0x180005519  lea     rcx, [rbx+30h]
0x18000551d  mov     rax, [rdi+28h]
0x180005521  mov     [rbx+28h], rax
0x180005525  movzx   eax, word ptr [rdi+42h]
0x180005529  mov     [rbx+42h], ax
0x18000552d  movups  xmm0, xmmword ptr [rdi+48h]
0x180005531  movups  xmmword ptr [rbx+48h], xmm0
0x180005535  movsd   xmm1, qword ptr [rdi+58h]
0x18000553a  movsd   qword ptr [rbx+58h], xmm1
0x18000553f  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x180005544  mov     esi, eax
0x180005546  test    eax, eax
0x180005548  js      short loc_180005557
0x18000554a  movzx   eax, word ptr [rdi+40h]
0x18000554e  mov     [rbx+40h], ax
0x180005552  jmp     loc_1800055D7
0x180005557  mov     r8, [rbx+8]; P
0x18000555b  test    r8, r8
0x18000555e  jz      short loc_180005581
0x180005560  mov     rcx, gs:60h
0x180005569  xor     edx, edx; Flags
0x18000556b  mov     rcx, [rcx+30h]; HeapHandle
0x18000556f  call    cs:__imp_RtlFreeHeap
0x180005576  nop     dword ptr [rax+rax+00h]
0x18000557b  xorps   xmm0, xmm0
0x18000557e  movups  xmmword ptr [rbx], xmm0
0x180005581  mov     r8, [rbx+20h]; P
0x180005585  test    r8, r8
0x180005588  jz      short loc_1800055AC
0x18000558a  mov     rcx, gs:60h
0x180005593  xor     edx, edx; Flags
0x180005595  mov     rcx, [rcx+30h]; HeapHandle
0x180005599  call    cs:__imp_RtlFreeHeap
0x1800055a0  nop     dword ptr [rax+rax+00h]
0x1800055a5  xorps   xmm0, xmm0
0x1800055a8  movups  xmmword ptr [rbx+18h], xmm0
0x1800055ac  mov     r8, [rbx+38h]; P
0x1800055b0  test    r8, r8
0x1800055b3  jz      short loc_1800055D7
0x1800055b5  mov     rcx, gs:60h
0x1800055be  xor     edx, edx; Flags
0x1800055c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800055c4  call    cs:__imp_RtlFreeHeap
0x1800055cb  nop     dword ptr [rax+rax+00h]
0x1800055d0  xorps   xmm0, xmm0
0x1800055d3  movups  xmmword ptr [rbx+30h], xmm0
0x1800055d7  mov     rbx, [rsp+28h+arg_0]
0x1800055dc  mov     eax, esi
0x1800055de  mov     rsi, [rsp+28h+arg_8]
0x1800055e3  add     rsp, 20h
0x1800055e7  pop     rdi
0x1800055e8  retn
```
