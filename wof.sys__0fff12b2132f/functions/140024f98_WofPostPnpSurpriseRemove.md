# WofPostPnpSurpriseRemove

- ea: `0x140024f98`
- end: `0x140025036`
- name: `WofPostPnpSurpriseRemove`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024f20`

## callees

- `0x1400014d0`
- `0x140011640`
- `0x140024f98`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140025017`
- `FLTMGR!FltReleaseContext` at `0x140025017`

## pseudocode

```c
__int64 __fastcall WofPostPnpSurpriseRemove(__int64 a1, __int64 a2, void *a3)
{
  bool v3; // sf
  char *v4; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rcx
  void (__fastcall *v7)(char *); // rax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+18h] BYREF

  Context = a3;
  v3 = *(int *)(a1 + 24) < 0;
  Context = 0;
  if ( !v3 )
  {
    WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
    v4 = (char *)Context;
    v5 = 0;
    do
    {
      v6 = 424LL * v5;
      if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v6) )
      {
        v7 = *(void (__fastcall **)(char *))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v6 + 128);
        if ( v7 )
          v7(&v4[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v6 + 20)]);
      }
      ++v5;
    }
    while ( v5 <= *((_DWORD *)v4 + 43) );
    *((_DWORD *)v4 + 43) = 0;
    FltReleaseContext(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x140024f98  mov     r11, rsp
0x140024f9b  mov     [r11+8], rbx
0x140024f9f  mov     [r11+10h], rbp
0x140024fa3  mov     [r11+18h], r8
0x140024fa7  push    rdi
0x140024fa8  sub     rsp, 20h
0x140024fac  cmp     dword ptr [rcx+18h], 0
0x140024fb0  mov     rax, rdx
0x140024fb3  mov     qword ptr [r11+18h], 0
0x140024fbb  jl      short loc_140025023
0x140024fbd  mov     rcx, [rax+18h]; Instance
0x140024fc1  lea     rdx, [r11+18h]
0x140024fc5  call    WofGetVolumeContext
0x140024fca  mov     rdi, [rsp+28h+Context]
0x140024fcf  lea     rbp, WPP_MAIN_CB.Queue+10h
0x140024fd6  xor     ebx, ebx
0x140024fd8  mov     eax, ebx
0x140024fda  imul    rcx, rax, 1A8h
0x140024fe1  cmp     byte ptr [rcx+rbp], 0
0x140024fe5  jz      short loc_140025000
0x140024fe7  mov     rax, [rcx+rbp+80h]
0x140024fef  test    rax, rax
0x140024ff2  jz      short loc_140025000
0x140024ff4  mov     ecx, [rcx+rbp+14h]
0x140024ff8  add     rcx, rdi
0x140024ffb  call    _guard_dispatch_icall
0x140025000  inc     ebx
0x140025002  cmp     ebx, [rdi+0ACh]
0x140025008  jbe     short loc_140024FD8
0x14002500a  mov     rcx, rdi; Context
0x14002500d  mov     dword ptr [rdi+0ACh], 0
0x140025017  call    cs:__imp_FltReleaseContext
0x14002501e  nop     dword ptr [rax+rax+00h]
0x140025023  mov     rbx, [rsp+28h+arg_0]
0x140025028  xor     eax, eax
0x14002502a  mov     rbp, [rsp+28h+arg_8]
0x14002502f  add     rsp, 20h
0x140025033  pop     rdi
0x140025034  retn
```
