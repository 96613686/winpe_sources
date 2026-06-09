# VidTriggerpDeletePort

- ea: `0x140097e74`
- end: `0x140097f16`
- name: `VidTriggerpDeletePort`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140097f1c`

## callees

- `0x140038630`
- `0x140097e74`

## import_xrefs

- `winhvr!WinHvDisconnectPort` at `0x140097e8b`
- `winhvr!WinHvDisconnectPort` at `0x140097e8b`
- `winhvr!WinHvDeletePort` at `0x140097edd`
- `winhvr!WinHvDeletePort` at `0x140097edd`
- `winhvr!WinHvFreePortId` at `0x140097ec5`
- `winhvr!WinHvFreePortId` at `0x140097ec5`

## string_xrefs

- `0x140097eaa`: `VidTriggerpDeletePort`
- `0x140097efc`: `VidTriggerpDeletePort`

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
      VidTraceErrorInternal0("VidTriggerpDeletePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 965);
  }
  else
  {
    VidTraceErrorInternal0("VidTriggerpDeletePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 952);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140097e74  mov     [rsp+arg_0], rbx
0x140097e79  push    rdi
0x140097e7a  sub     rsp, 20h
0x140097e7e  mov     edx, [rcx+88h]
0x140097e84  mov     rdi, rcx
0x140097e87  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140097e8b  call    cs:__imp_WinHvDisconnectPort
0x140097e92  nop     dword ptr [rax+rax+00h]
0x140097e97  mov     ebx, eax
0x140097e99  test    eax, eax
0x140097e9b  jns     short loc_140097EB8
0x140097e9d  mov     r8d, 3B8h
0x140097ea3  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097eaa  lea     rcx, aVidtriggerpdel; "VidTriggerpDeletePort"
0x140097eb1  call    VidTraceErrorInternal0
0x140097eb6  jmp     short loc_140097F08
0x140097eb8  mov     ecx, [rdi+88h]
0x140097ebe  mov     ebx, 0FFFFFFh
0x140097ec3  and     ecx, ebx
0x140097ec5  call    cs:__imp_WinHvFreePortId
0x140097ecc  nop     dword ptr [rax+rax+00h]
0x140097ed1  mov     edx, [rdi+7Ch]
0x140097ed4  mov     rcx, [rdi]
0x140097ed7  or      [rdi+88h], ebx
0x140097edd  call    cs:__imp_WinHvDeletePort
0x140097ee4  nop     dword ptr [rax+rax+00h]
0x140097ee9  mov     ebx, eax
0x140097eeb  test    eax, eax
0x140097eed  jns     short loc_140097F08
0x140097eef  mov     r8d, 3C5h
0x140097ef5  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097efc  lea     rcx, aVidtriggerpdel; "VidTriggerpDeletePort"
0x140097f03  call    VidTraceErrorInternal0
0x140097f08  mov     eax, ebx
0x140097f0a  mov     rbx, [rsp+28h+arg_0]
0x140097f0f  add     rsp, 20h
0x140097f13  pop     rdi
0x140097f14  retn
```
