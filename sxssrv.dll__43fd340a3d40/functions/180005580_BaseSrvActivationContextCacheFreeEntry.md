# BaseSrvActivationContextCacheFreeEntry

- ea: `0x180005580`
- end: `0x180005690`
- name: `BaseSrvActivationContextCacheFreeEntry`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004e60`
- `0x180005050`
- `0x180005170`

## callees

- `0x180005580`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800055a1`
- `ntdll!RtlFreeHeap` at `0x1800055cc`
- `ntdll!RtlFreeHeap` at `0x1800055f7`
- `ntdll!RtlFreeHeap` at `0x180005642`
- `ntdll!RtlFreeHeap` at `0x180005673`
- `ntdll!RtlFreeHeap` at `0x1800055a1`
- `ntdll!RtlFreeHeap` at `0x1800055cc`
- `ntdll!RtlFreeHeap` at `0x1800055f7`
- `ntdll!RtlFreeHeap` at `0x180005642`
- `ntdll!RtlFreeHeap` at `0x180005673`
- `ntdll!NtClose` at `0x180005613`
- `ntdll!NtClose` at `0x180005613`

## pseudocode

```c
char __fastcall BaseSrvActivationContextCacheFreeEntry(__int64 a1)
{
  void *v1; // r8
  char result; // al
  void *v4; // r8
  void *v5; // r8
  void *v6; // rcx
  void *v7; // r8
  void *v8; // r8

  v1 = *(void **)(a1 + 24);
  if ( v1 )
  {
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    *(_OWORD *)(a1 + 16) = 0;
  }
  v4 = *(void **)(a1 + 48);
  if ( v4 )
  {
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    *(_OWORD *)(a1 + 40) = 0;
  }
  v5 = *(void **)(a1 + 72);
  if ( v5 )
  {
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    *(_OWORD *)(a1 + 64) = 0;
  }
  v6 = *(void **)(a1 + 112);
  if ( v6 )
  {
    result = NtClose(v6);
    *(_QWORD *)(a1 + 112) = 0;
  }
  v7 = *(void **)(a1 + 152);
  if ( v7 )
  {
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *(_OWORD *)(a1 + 144) = 0;
  }
  v8 = *(void **)(a1 + 168);
  if ( v8 )
  {
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    *(_OWORD *)(a1 + 160) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005580  push    rbx
0x180005582  sub     rsp, 20h
0x180005586  mov     r8, [rcx+18h]; P
0x18000558a  mov     rbx, rcx
0x18000558d  test    r8, r8
0x180005590  jz      short loc_1800055B4
0x180005592  mov     rcx, gs:60h
0x18000559b  xor     edx, edx; Flags
0x18000559d  mov     rcx, [rcx+30h]; HeapHandle
0x1800055a1  call    cs:__imp_RtlFreeHeap
0x1800055a8  nop     dword ptr [rax+rax+00h]
0x1800055ad  xorps   xmm0, xmm0
0x1800055b0  movups  xmmword ptr [rbx+10h], xmm0
0x1800055b4  mov     r8, [rbx+30h]; P
0x1800055b8  test    r8, r8
0x1800055bb  jz      short loc_1800055DF
0x1800055bd  mov     rcx, gs:60h
0x1800055c6  xor     edx, edx; Flags
0x1800055c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800055cc  call    cs:__imp_RtlFreeHeap
0x1800055d3  nop     dword ptr [rax+rax+00h]
0x1800055d8  xorps   xmm0, xmm0
0x1800055db  movups  xmmword ptr [rbx+28h], xmm0
0x1800055df  mov     r8, [rbx+48h]; P
0x1800055e3  test    r8, r8
0x1800055e6  jz      short loc_18000560A
0x1800055e8  mov     rcx, gs:60h
0x1800055f1  xor     edx, edx; Flags
0x1800055f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800055f7  call    cs:__imp_RtlFreeHeap
0x1800055fe  nop     dword ptr [rax+rax+00h]
0x180005603  xorps   xmm0, xmm0
0x180005606  movups  xmmword ptr [rbx+40h], xmm0
0x18000560a  mov     rcx, [rbx+70h]; Handle
0x18000560e  test    rcx, rcx
0x180005611  jz      short loc_180005627
0x180005613  call    cs:__imp_NtClose
0x18000561a  nop     dword ptr [rax+rax+00h]
0x18000561f  mov     qword ptr [rbx+70h], 0
0x180005627  mov     r8, [rbx+98h]; P
0x18000562e  test    r8, r8
0x180005631  jz      short loc_180005658
0x180005633  mov     rcx, gs:60h
0x18000563c  xor     edx, edx; Flags
0x18000563e  mov     rcx, [rcx+30h]; HeapHandle
0x180005642  call    cs:__imp_RtlFreeHeap
0x180005649  nop     dword ptr [rax+rax+00h]
0x18000564e  xorps   xmm0, xmm0
0x180005651  movups  xmmword ptr [rbx+90h], xmm0
0x180005658  mov     r8, [rbx+0A8h]; P
0x18000565f  test    r8, r8
0x180005662  jz      short loc_180005689
0x180005664  mov     rcx, gs:60h
0x18000566d  xor     edx, edx; Flags
0x18000566f  mov     rcx, [rcx+30h]; HeapHandle
0x180005673  call    cs:__imp_RtlFreeHeap
0x18000567a  nop     dword ptr [rax+rax+00h]
0x18000567f  xorps   xmm0, xmm0
0x180005682  movups  xmmword ptr [rbx+0A0h], xmm0
0x180005689  add     rsp, 20h
0x18000568d  pop     rbx
0x18000568e  retn
```
