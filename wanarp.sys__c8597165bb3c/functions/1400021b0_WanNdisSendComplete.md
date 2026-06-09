# WanNdisSendComplete

- ea: `0x1400021b0`
- end: `0x1400022b3`
- name: `WanNdisSendComplete`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400021b0`
- `0x14000f728`

## import_xrefs

- `NETIO!NetioAdvanceNetBufferList` at `0x14000220c`
- `NETIO!NetioAdvanceNetBufferList` at `0x14000220c`
- `NETIO!NetioDereferenceNetBufferList` at `0x14000224d`
- `NETIO!NetioDereferenceNetBufferList` at `0x140002291`
- `NETIO!NetioDereferenceNetBufferList` at `0x14000224d`
- `NETIO!NetioDereferenceNetBufferList` at `0x140002291`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400021f8`
- `NDIS!NdisFreeNetBufferListContext` at `0x1400021f8`

## pseudocode

```c
void __fastcall WanNdisSendComplete(__int64 a1, struct _NET_BUFFER_LIST *a2, char a3)
{
  unsigned __int8 v3; // bp
  struct _NET_BUFFER_LIST *v4; // rbx
  struct _NET_BUFFER_LIST *Alignment; // rdi
  __int64 v6; // rsi
  PNET_BUFFER i; // rdx
  __int64 v8; // rax

  if ( a2 )
  {
    v3 = a3 & 1;
    v4 = a2;
    do
    {
      Alignment = (struct _NET_BUFFER_LIST *)v4->Link.Alignment;
      v6 = *(_QWORD *)&v4->Context->ContextData[v4->Context->Offset];
      NdisFreeNetBufferListContext(v4, 8u);
      NetioAdvanceNetBufferList(v4, 14);
      if ( v6 )
      {
        for ( i = v4->FirstNetBuffer; i; i = (PNET_BUFFER)i->Link.Alignment )
        {
          v8 = *(_QWORD *)(v6 + 8);
          if ( v4->Status )
            _InterlockedIncrement64((volatile signed __int64 *)(v8 + 312));
          else
            _InterlockedAdd64((volatile signed __int64 *)(v8 + 272), i->DataLength);
        }
        NetioDereferenceNetBufferList(v4, v3);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 96), 0xFFFFFFFF) == 1 )
          WanpDeleteConnEntry((char *)v6);
      }
      else
      {
        NetioDereferenceNetBufferList(v4, v3);
      }
      v4 = Alignment;
    }
    while ( Alignment );
  }
}

```

## disassembly

```asm
0x1400021b0  test    rdx, rdx
0x1400021b3  jz      locret_140002288
0x1400021b9  mov     [rsp+arg_10], rbx
0x1400021be  push    rbp
0x1400021bf  sub     rsp, 20h
0x1400021c3  mov     ebp, r8d
0x1400021c6  mov     [rsp+28h+arg_0], rsi
0x1400021cb  and     bpl, 1
0x1400021cf  mov     [rsp+28h+arg_8], rdi
0x1400021d4  mov     rbx, rdx
0x1400021d7  nop     word ptr [rax+rax+00000000h]
0x1400021e0  mov     rcx, [rbx+10h]
0x1400021e4  mov     edx, 8; ContextSize
0x1400021e9  mov     rdi, [rbx]
0x1400021ec  movzx   eax, word ptr [rcx+0Ah]
0x1400021f0  mov     rsi, [rax+rcx+10h]
0x1400021f5  mov     rcx, rbx; NetBufferList
0x1400021f8  call    cs:__imp_NdisFreeNetBufferListContext
0x1400021ff  nop     dword ptr [rax+rax+00h]
0x140002204  mov     edx, 0Eh
0x140002209  mov     rcx, rbx
0x14000220c  call    cs:__imp_NetioAdvanceNetBufferList
0x140002213  nop     dword ptr [rax+rax+00h]
0x140002218  test    rsi, rsi
0x14000221b  jz      short loc_14000228A
0x14000221d  mov     rdx, [rbx+8]
0x140002221  test    rdx, rdx
0x140002224  jz      short loc_140002246
0x140002226  cmp     dword ptr [rbx+8Ch], 0
0x14000222d  mov     rax, [rsi+8]
0x140002231  jnz     short loc_14000229F
0x140002233  mov     ecx, [rdx+18h]
0x140002236  lock add [rax+110h], rcx
0x14000223e  mov     rdx, [rdx]
0x140002241  test    rdx, rdx
0x140002244  jnz     short loc_140002226
0x140002246  movzx   edx, bpl
0x14000224a  mov     rcx, rbx
0x14000224d  call    cs:__imp_NetioDereferenceNetBufferList
0x140002254  nop     dword ptr [rax+rax+00h]
0x140002259  mov     eax, 0FFFFFFFFh
0x14000225e  lock xadd [rsi+60h], eax
0x140002263  cmp     eax, 1
0x140002266  jz      short loc_1400022A9
0x140002268  mov     rbx, rdi
0x14000226b  test    rdi, rdi
0x14000226e  jnz     loc_1400021E0
0x140002274  mov     rdi, [rsp+28h+arg_8]
0x140002279  mov     rsi, [rsp+28h+arg_0]
0x14000227e  mov     rbx, [rsp+28h+arg_10]
0x140002283  add     rsp, 20h
0x140002287  pop     rbp
0x140002288  retn
0x14000228a  movzx   edx, bpl
0x14000228e  mov     rcx, rbx
0x140002291  call    cs:__imp_NetioDereferenceNetBufferList
0x140002298  nop     dword ptr [rax+rax+00h]
0x14000229d  jmp     short loc_140002268
0x14000229f  lock inc qword ptr [rax+138h]
0x1400022a7  jmp     short loc_14000223E
0x1400022a9  mov     rcx, rsi; Entry
0x1400022ac  call    WanpDeleteConnEntry
0x1400022b1  jmp     short loc_140002268
```
