# BaseSrvActivationContextCacheFreeEntry

- ea: `0x1800053a0`
- end: `0x1800054b0`
- name: `BaseSrvActivationContextCacheFreeEntry`
- size: `272`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004cb0`
- `0x180004e90`
- `0x180004fa0`

## callees

- `0x1800053a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800053c1`
- `ntdll!RtlFreeHeap` at `0x1800053ec`
- `ntdll!RtlFreeHeap` at `0x180005417`
- `ntdll!RtlFreeHeap` at `0x180005462`
- `ntdll!RtlFreeHeap` at `0x180005493`
- `ntdll!RtlFreeHeap` at `0x1800053c1`
- `ntdll!RtlFreeHeap` at `0x1800053ec`
- `ntdll!RtlFreeHeap` at `0x180005417`
- `ntdll!RtlFreeHeap` at `0x180005462`
- `ntdll!RtlFreeHeap` at `0x180005493`
- `ntdll!NtClose` at `0x180005433`
- `ntdll!NtClose` at `0x180005433`

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
0x1800053a0  push    rbx
0x1800053a2  sub     rsp, 20h
0x1800053a6  mov     r8, [rcx+18h]; P
0x1800053aa  mov     rbx, rcx
0x1800053ad  test    r8, r8
0x1800053b0  jz      short loc_1800053D4
0x1800053b2  mov     rcx, gs:60h
0x1800053bb  xor     edx, edx; Flags
0x1800053bd  mov     rcx, [rcx+30h]; HeapHandle
0x1800053c1  call    cs:__imp_RtlFreeHeap
0x1800053c8  nop     dword ptr [rax+rax+00h]
0x1800053cd  xorps   xmm0, xmm0
0x1800053d0  movups  xmmword ptr [rbx+10h], xmm0
0x1800053d4  mov     r8, [rbx+30h]; P
0x1800053d8  test    r8, r8
0x1800053db  jz      short loc_1800053FF
0x1800053dd  mov     rcx, gs:60h
0x1800053e6  xor     edx, edx; Flags
0x1800053e8  mov     rcx, [rcx+30h]; HeapHandle
0x1800053ec  call    cs:__imp_RtlFreeHeap
0x1800053f3  nop     dword ptr [rax+rax+00h]
0x1800053f8  xorps   xmm0, xmm0
0x1800053fb  movups  xmmword ptr [rbx+28h], xmm0
0x1800053ff  mov     r8, [rbx+48h]; P
0x180005403  test    r8, r8
0x180005406  jz      short loc_18000542A
0x180005408  mov     rcx, gs:60h
0x180005411  xor     edx, edx; Flags
0x180005413  mov     rcx, [rcx+30h]; HeapHandle
0x180005417  call    cs:__imp_RtlFreeHeap
0x18000541e  nop     dword ptr [rax+rax+00h]
0x180005423  xorps   xmm0, xmm0
0x180005426  movups  xmmword ptr [rbx+40h], xmm0
0x18000542a  mov     rcx, [rbx+70h]; Handle
0x18000542e  test    rcx, rcx
0x180005431  jz      short loc_180005447
0x180005433  call    cs:__imp_NtClose
0x18000543a  nop     dword ptr [rax+rax+00h]
0x18000543f  mov     qword ptr [rbx+70h], 0
0x180005447  mov     r8, [rbx+98h]; P
0x18000544e  test    r8, r8
0x180005451  jz      short loc_180005478
0x180005453  mov     rcx, gs:60h
0x18000545c  xor     edx, edx; Flags
0x18000545e  mov     rcx, [rcx+30h]; HeapHandle
0x180005462  call    cs:__imp_RtlFreeHeap
0x180005469  nop     dword ptr [rax+rax+00h]
0x18000546e  xorps   xmm0, xmm0
0x180005471  movups  xmmword ptr [rbx+90h], xmm0
0x180005478  mov     r8, [rbx+0A8h]; P
0x18000547f  test    r8, r8
0x180005482  jz      short loc_1800054A9
0x180005484  mov     rcx, gs:60h
0x18000548d  xor     edx, edx; Flags
0x18000548f  mov     rcx, [rcx+30h]; HeapHandle
0x180005493  call    cs:__imp_RtlFreeHeap
0x18000549a  nop     dword ptr [rax+rax+00h]
0x18000549f  xorps   xmm0, xmm0
0x1800054a2  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800054a9  add     rsp, 20h
0x1800054ad  pop     rbx
0x1800054ae  retn
```
