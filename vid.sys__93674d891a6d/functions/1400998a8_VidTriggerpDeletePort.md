# VidTriggerpDeletePort

- ea: `0x1400998a8`
- end: `0x14009994a`
- name: `VidTriggerpDeletePort`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140099950`

## callees

- `0x1400386a0`
- `0x1400998a8`

## import_xrefs

- `winhvr!WinHvDisconnectPort` at `0x1400998bf`
- `winhvr!WinHvDisconnectPort` at `0x1400998bf`
- `winhvr!WinHvDeletePort` at `0x140099911`
- `winhvr!WinHvDeletePort` at `0x140099911`
- `winhvr!WinHvFreePortId` at `0x1400998f9`
- `winhvr!WinHvFreePortId` at `0x1400998f9`

## string_xrefs

- `0x1400998de`: `VidTriggerpDeletePort`
- `0x140099930`: `VidTriggerpDeletePort`

## pseudocode

```c
__int64 __fastcall VidTriggerpDeletePort(__int64 *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx

  v2 = WinHvDisconnectPort(-1, *((unsigned int *)a1 + 34));
  if ( v2 >= 0 )
  {
    WinHvFreePortId(a1[17] & 0xFFFFFF);
    v3 = *((unsigned int *)a1 + 31);
    v4 = *a1;
    *((_DWORD *)a1 + 34) |= 0xFFFFFFu;
    v2 = WinHvDeletePort(v4, v3);
    if ( v2 < 0 )
      VidTraceErrorInternal0("VidTriggerpDeletePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 966);
  }
  else
  {
    VidTraceErrorInternal0("VidTriggerpDeletePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 953);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400998a8  mov     [rsp+arg_0], rbx
0x1400998ad  push    rdi
0x1400998ae  sub     rsp, 20h
0x1400998b2  mov     edx, [rcx+88h]
0x1400998b8  mov     rdi, rcx
0x1400998bb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400998bf  call    cs:__imp_WinHvDisconnectPort
0x1400998c6  nop     dword ptr [rax+rax+00h]
0x1400998cb  mov     ebx, eax
0x1400998cd  test    eax, eax
0x1400998cf  jns     short loc_1400998EC
0x1400998d1  mov     r8d, 3B9h
0x1400998d7  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x1400998de  lea     rcx, aVidtriggerpdel; "VidTriggerpDeletePort"
0x1400998e5  call    VidTraceErrorInternal0
0x1400998ea  jmp     short loc_14009993C
0x1400998ec  mov     ecx, [rdi+88h]
0x1400998f2  mov     ebx, 0FFFFFFh
0x1400998f7  and     ecx, ebx
0x1400998f9  call    cs:__imp_WinHvFreePortId
0x140099900  nop     dword ptr [rax+rax+00h]
0x140099905  mov     edx, [rdi+7Ch]
0x140099908  mov     rcx, [rdi]
0x14009990b  or      [rdi+88h], ebx
0x140099911  call    cs:__imp_WinHvDeletePort
0x140099918  nop     dword ptr [rax+rax+00h]
0x14009991d  mov     ebx, eax
0x14009991f  test    eax, eax
0x140099921  jns     short loc_14009993C
0x140099923  mov     r8d, 3C6h
0x140099929  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140099930  lea     rcx, aVidtriggerpdel; "VidTriggerpDeletePort"
0x140099937  call    VidTraceErrorInternal0
0x14009993c  mov     eax, ebx
0x14009993e  mov     rbx, [rsp+28h+arg_0]
0x140099943  add     rsp, 20h
0x140099947  pop     rdi
0x140099948  retn
```
