# UdfSeqCacheInsertFlushWaitBlock

- ea: `0x140009f60`
- end: `0x140009fec`
- name: `UdfSeqCacheInsertFlushWaitBlock`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a060`
- `0x14002c9ac`

## callees

- `0x140009f60`
- `0x14001c080`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140009f91`
- `ntoskrnl!KeInitializeEvent` at `0x140009f91`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheInsertFlushWaitBlock(__int64 a1, _QWORD *a2, unsigned int a3)
{
  __int64 v4; // rbx
  int v6; // eax
  __int64 *v7; // rdi
  __int64 result; // rax

  v4 = a3;
  memset(a2, 0, 0x40u);
  KeInitializeEvent((PRKEVENT)(a2 + 2), SynchronizationEvent, 0);
  a2[6] = KeGetCurrentThread();
  v6 = *(_DWORD *)(a1 + 40 * v4 + 36);
  v7 = (__int64 *)(a1 + 624);
  *((_DWORD *)a2 + 10) = v6;
  result = *v7;
  if ( *(__int64 **)(*v7 + 8) != v7 )
    __fastfail(3u);
  *a2 = result;
  a2[1] = v7;
  *(_QWORD *)(result + 8) = a2;
  *v7 = (__int64)a2;
  return result;
}

```

## disassembly

```asm
0x140009f60  mov     [rsp+arg_0], rbx
0x140009f65  mov     [rsp+arg_8], rsi
0x140009f6a  push    rdi
0x140009f6b  sub     rsp, 20h
0x140009f6f  mov     rsi, rdx
0x140009f72  mov     ebx, r8d
0x140009f75  xor     edx, edx; Val
0x140009f77  mov     rdi, rcx
0x140009f7a  mov     rcx, rsi; void *
0x140009f7d  lea     r8d, [rdx+40h]; Size
0x140009f81  call    memset
0x140009f86  xor     r8d, r8d; State
0x140009f89  lea     rcx, [rsi+10h]; Event
0x140009f8d  lea     edx, [r8+1]; Type
0x140009f91  call    cs:__imp_KeInitializeEvent
0x140009f98  nop     dword ptr [rax+rax+00h]
0x140009f9d  mov     rax, gs:188h
0x140009fa6  lea     r8, [rbx+rbx*4]
0x140009faa  mov     [rsi+30h], rax
0x140009fae  mov     eax, [rdi+r8*8+24h]
0x140009fb3  add     rdi, 270h
0x140009fba  mov     [rsi+28h], eax
0x140009fbd  mov     rax, [rdi]
0x140009fc0  cmp     [rax+8], rdi
0x140009fc4  jz      short loc_140009FCD
0x140009fc6  mov     ecx, 3
0x140009fcb  int     29h; Win8: RtlFailFast(ecx)
0x140009fcd  mov     rbx, [rsp+28h+arg_0]
0x140009fd2  mov     [rsi], rax
0x140009fd5  mov     [rsi+8], rdi
0x140009fd9  mov     [rax+8], rsi
0x140009fdd  mov     [rdi], rsi
0x140009fe0  mov     rsi, [rsp+28h+arg_8]
0x140009fe5  add     rsp, 20h
0x140009fe9  pop     rdi
0x140009fea  retn
```
