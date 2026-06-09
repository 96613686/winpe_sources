# WinNatInjectionComplete

- ea: `0x140012db0`
- end: `0x140012e8d`
- name: `WinNatInjectionComplete`
- size: `221`
- prototype: `void __stdcall(void *context, NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140012980`
- `0x140012cc8`
- `0x140012ea0`
- `0x140017190`
- `0x1400172d0`
- `0x140017720`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x140012db0`

## import_xrefs

- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012e11`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012e4b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012e11`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140012e4b`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x140012e2a`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x140012e2a`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012e62`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x140012e62`

## pseudocode

```c
void __fastcall WinNatInjectionComplete(
        void *context,
        NET_BUFFER_LIST *netBufferList,
        __int64 dispatchLevel,
        __int64 a4)
{
  NET_BUFFER_LIST *Alignment; // rdi
  NET_BUFFER_LIST *v6; // rbx
  NET_BUFFER_LIST *v7; // rsi
  struct _NET_BUFFER *FirstNetBuffer; // rbx

  if ( netBufferList )
  {
    Alignment = netBufferList;
    do
    {
      v6 = Alignment;
      v7 = Alignment;
      Alignment = (NET_BUFFER_LIST *)Alignment->Link.Alignment;
      if ( !v6->Context->Size )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(context, netBufferList, dispatchLevel, a4);
      FirstNetBuffer = v6->FirstNetBuffer;
      if ( (v7->Context->ContextData[v7->Context->Offset] & 1) != 0 )
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
        FwpsFreeNetBufferList0(v7);
      }
      else
      {
        while ( FirstNetBuffer )
        {
          NdisAdvanceNetBufferDataStart(
            FirstNetBuffer,
            *(_DWORD *)(FirstNetBuffer->Link.Region + 40) - FirstNetBuffer->CurrentMdlOffset,
            1u,
            WinNatFreeMdl);
          FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        }
        FwpsFreeCloneNetBufferList0(v7, 0);
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
0x140012db0  test    rdx, rdx
0x140012db3  jz      locret_140012E8B
0x140012db9  push    rbx
0x140012dba  push    rbp
0x140012dbb  push    rsi
0x140012dbc  push    rdi
0x140012dbd  push    r14
0x140012dbf  sub     rsp, 20h
0x140012dc3  mov     rdi, rdx
0x140012dc6  mov     rbp, rcx
0x140012dc9  xor     r14d, r14d
0x140012dcc  mov     rbx, rdi
0x140012dcf  mov     rsi, rdi
0x140012dd2  mov     rdi, [rdi]
0x140012dd5  mov     rax, [rbx+10h]
0x140012dd9  cmp     [rax+8], r14w
0x140012dde  jnz     short loc_140012DE5
0x140012de0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140012de5  mov     rcx, [rsi+10h]
0x140012de9  mov     rbx, [rbx+8]
0x140012ded  movzx   eax, word ptr [rcx+0Ah]
0x140012df1  test    byte ptr [rax+rcx+10h], 1
0x140012df6  jnz     short loc_140012E5A
0x140012df8  jmp     short loc_140012E20
0x140012dfa  mov     rax, [rbx+8]
0x140012dfe  lea     r9, WinNatFreeMdl; FreeMdlHandler
0x140012e05  mov     r8b, 1; FreeMdl
0x140012e08  mov     rcx, rbx; NetBuffer
0x140012e0b  mov     edx, [rax+28h]
0x140012e0e  sub     edx, [rbx+10h]; DataOffsetDelta
0x140012e11  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140012e18  nop     dword ptr [rax+rax+00h]
0x140012e1d  mov     rbx, [rbx]
0x140012e20  test    rbx, rbx
0x140012e23  jnz     short loc_140012DFA
0x140012e25  xor     edx, edx; freeCloneFlags
0x140012e27  mov     rcx, rsi; netBufferList
0x140012e2a  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x140012e31  nop     dword ptr [rax+rax+00h]
0x140012e36  jmp     short loc_140012E6E
0x140012e38  mov     rax, [rbx+8]
0x140012e3c  xor     r9d, r9d; FreeMdlHandler
0x140012e3f  mov     r8b, 1; FreeMdl
0x140012e42  mov     rcx, rbx; NetBuffer
0x140012e45  mov     edx, [rax+28h]
0x140012e48  sub     edx, [rbx+10h]; DataOffsetDelta
0x140012e4b  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140012e52  nop     dword ptr [rax+rax+00h]
0x140012e57  mov     rbx, [rbx]
0x140012e5a  test    rbx, rbx
0x140012e5d  jnz     short loc_140012E38
0x140012e5f  mov     rcx, rsi; netBufferList
0x140012e62  call    cs:__imp_FwpsFreeNetBufferList0
0x140012e69  nop     dword ptr [rax+rax+00h]
0x140012e6e  test    rbp, rbp
0x140012e71  jz      short loc_140012E78
0x140012e73  call    WinNatDereferenceGlobal
0x140012e78  test    rdi, rdi
0x140012e7b  jnz     loc_140012DCC
0x140012e81  add     rsp, 20h
0x140012e85  pop     r14
0x140012e87  pop     rdi
0x140012e88  pop     rsi
0x140012e89  pop     rbp
0x140012e8a  pop     rbx
0x140012e8b  retn
```
