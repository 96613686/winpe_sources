# WinNatInjectionComplete

- ea: `0x1400136f0`
- end: `0x1400137cd`
- name: `WinNatInjectionComplete`
- size: `221`
- prototype: `void __stdcall(void *context, NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400132c0`
- `0x140013608`
- `0x1400137e0`
- `0x140017ec0`
- `0x140018010`
- `0x140018470`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x1400136f0`

## import_xrefs

- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140013751`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001378b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140013751`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001378b`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14001376a`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14001376a`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x1400137a2`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x1400137a2`

## pseudocode

```c
void __fastcall WinNatInjectionComplete(void *context, NET_BUFFER_LIST *netBufferList, __int64 dispatchLevel)
{
  NET_BUFFER_LIST *Alignment; // rdi
  NET_BUFFER_LIST *v5; // rbx
  NET_BUFFER_LIST *v6; // rsi
  struct _NET_BUFFER *FirstNetBuffer; // rbx

  if ( netBufferList )
  {
    Alignment = netBufferList;
    do
    {
      v5 = Alignment;
      v6 = Alignment;
      Alignment = (NET_BUFFER_LIST *)Alignment->Link.Alignment;
      if ( !v5->Context->Size )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(context, netBufferList, dispatchLevel);
      FirstNetBuffer = v5->FirstNetBuffer;
      if ( (v6->Context->ContextData[v6->Context->Offset] & 1) != 0 )
      {
        while ( FirstNetBuffer )
        {
          NdisAdvanceNetBufferDataStart(
            FirstNetBuffer,
            *(_DWORD *)(FirstNetBuffer->Link.Region + 40) - FirstNetBuffer->CurrentMdlOffset,
            1u,
            0);
          FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        }
        FwpsFreeNetBufferList0(v6);
      }
      else
      {
        while ( FirstNetBuffer )
        {
          NdisAdvanceNetBufferDataStart(
            FirstNetBuffer,
            *(_DWORD *)(FirstNetBuffer->Link.Region + 40) - FirstNetBuffer->CurrentMdlOffset,
            1u,
            (NET_BUFFER_FREE_MDL_HANDLER)WinNatFreeMdl);
          FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        }
        FwpsFreeCloneNetBufferList0(v6, 0);
      }
      if ( context )
        WinNatDereferenceGlobal();
    }
    while ( Alignment );
  }
}

```

## disassembly

```asm
0x1400136f0  test    rdx, rdx
0x1400136f3  jz      locret_1400137CB
0x1400136f9  push    rbx
0x1400136fa  push    rbp
0x1400136fb  push    rsi
0x1400136fc  push    rdi
0x1400136fd  push    r14
0x1400136ff  sub     rsp, 20h
0x140013703  mov     rdi, rdx
0x140013706  mov     rbp, rcx
0x140013709  xor     r14d, r14d
0x14001370c  mov     rbx, rdi
0x14001370f  mov     rsi, rdi
0x140013712  mov     rdi, [rdi]
0x140013715  mov     rax, [rbx+10h]
0x140013719  cmp     [rax+8], r14w
0x14001371e  jnz     short loc_140013725
0x140013720  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140013725  mov     rcx, [rsi+10h]
0x140013729  mov     rbx, [rbx+8]
0x14001372d  movzx   eax, word ptr [rcx+0Ah]
0x140013731  test    byte ptr [rax+rcx+10h], 1
0x140013736  jnz     short loc_14001379A
0x140013738  jmp     short loc_140013760
0x14001373a  mov     rax, [rbx+8]
0x14001373e  lea     r9, WinNatFreeMdl; FreeMdlHandler
0x140013745  mov     r8b, 1; FreeMdl
0x140013748  mov     rcx, rbx; NetBuffer
0x14001374b  mov     edx, [rax+28h]
0x14001374e  sub     edx, [rbx+10h]; DataOffsetDelta
0x140013751  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140013758  nop     dword ptr [rax+rax+00h]
0x14001375d  mov     rbx, [rbx]
0x140013760  test    rbx, rbx
0x140013763  jnz     short loc_14001373A
0x140013765  xor     edx, edx; freeCloneFlags
0x140013767  mov     rcx, rsi; netBufferList
0x14001376a  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x140013771  nop     dword ptr [rax+rax+00h]
0x140013776  jmp     short loc_1400137AE
0x140013778  mov     rax, [rbx+8]
0x14001377c  xor     r9d, r9d; FreeMdlHandler
0x14001377f  mov     r8b, 1; FreeMdl
0x140013782  mov     rcx, rbx; NetBuffer
0x140013785  mov     edx, [rax+28h]
0x140013788  sub     edx, [rbx+10h]; DataOffsetDelta
0x14001378b  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140013792  nop     dword ptr [rax+rax+00h]
0x140013797  mov     rbx, [rbx]
0x14001379a  test    rbx, rbx
0x14001379d  jnz     short loc_140013778
0x14001379f  mov     rcx, rsi; netBufferList
0x1400137a2  call    cs:__imp_FwpsFreeNetBufferList0
0x1400137a9  nop     dword ptr [rax+rax+00h]
0x1400137ae  test    rbp, rbp
0x1400137b1  jz      short loc_1400137B8
0x1400137b3  call    WinNatDereferenceGlobal
0x1400137b8  test    rdi, rdi
0x1400137bb  jnz     loc_14001370C
0x1400137c1  add     rsp, 20h
0x1400137c5  pop     r14
0x1400137c7  pop     rdi
0x1400137c8  pop     rsi
0x1400137c9  pop     rbp
0x1400137ca  pop     rbx
0x1400137cb  retn
```
