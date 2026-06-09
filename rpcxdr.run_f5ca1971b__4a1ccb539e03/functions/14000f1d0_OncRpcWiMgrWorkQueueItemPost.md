# OncRpcWiMgrWorkQueueItemPost

- ea: `0x14000f1d0`
- end: `0x14000f30f`
- name: `OncRpcWiMgrWorkQueueItemPost`
- size: `319`
- prototype: `__int64 __fastcall(PLIST_ENTRY Entry)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fa0c`
- `0x1400104e0`
- `0x1400202f8`
- `0x1400204c0`

## callees

- `0x14000d04c`
- `0x14000f1d0`

## import_xrefs

- `ntoskrnl!KeInsertHeadQueue` at `0x14000f2e4`
- `ntoskrnl!KeInsertHeadQueue` at `0x14000f2e4`
- `ntoskrnl!KeInsertQueue` at `0x14000f2f2`
- `ntoskrnl!KeInsertQueue` at `0x14000f2f2`

## pseudocode

```c
LONG __fastcall OncRpcWiMgrWorkQueueItemPost(PLIST_ENTRY Entry)
{
  struct _LIST_ENTRY *Flink; // rsi
  int Blink; // ecx
  struct _LIST_ENTRY *v4; // rax
  __int64 v5; // rdx
  bool v6; // zf
  __int64 v7; // rbx
  struct _KQUEUE *v8; // rcx

  LODWORD(Entry[2].Blink) |= 4u;
  Flink = Entry[1].Flink;
  Blink = (int)Entry[2].Blink;
  if ( (dword_14001A498 & 2) != 0 && (Blink & 8) == 0 && LODWORD(Flink[8].Flink) >= dword_14001A438 )
  {
    _InterlockedIncrement((_DWORD *)&qword_14001A440 + 1);
    v4 = Flink + 14;
    v5 = OncRpcWiMgrGlobals + 224LL * (unsigned int)(dword_14001A428 - 1);
    v6 = Flink == (struct _LIST_ENTRY *)v5;
    while ( 1 )
    {
      v7 = OncRpcWiMgrGlobals;
      if ( !v6 )
        v7 = (__int64)v4;
      if ( (struct _LIST_ENTRY *)v7 == Flink || *(_DWORD *)(v7 + 128) < (unsigned int)dword_14001A43C )
        break;
      v6 = v7 == v5;
      v4 = (struct _LIST_ENTRY *)(v7 + 224);
    }
    Flink = (struct _LIST_ENTRY *)v7;
    if ( (struct _LIST_ENTRY *)v7 != Entry[1].Flink )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        WPP_SF_dddd(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids,
          LODWORD(Entry[1].Flink[7].Flink),
          Entry[1].Flink[8].Flink,
          *(_DWORD *)(v7 + 112),
          *(_DWORD *)(v7 + 128));
      }
      _InterlockedIncrement((volatile signed __int32 *)&qword_14001A440);
      Entry[1].Flink = (struct _LIST_ENTRY *)v7;
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)&Flink[8]);
  v8 = (struct _KQUEUE *)&Flink[2];
  if ( ((__int64)Entry[2].Blink & 2) != 0 )
    return KeInsertHeadQueue(v8, Entry);
  else
    return KeInsertQueue(v8, Entry);
}

```

## disassembly

```asm
0x14000f1d0  mov     [rsp+arg_0], rbx
0x14000f1d5  mov     [rsp+arg_8], rsi
0x14000f1da  push    rdi
0x14000f1db  sub     rsp, 40h
0x14000f1df  or      dword ptr [rcx+28h], 4
0x14000f1e3  mov     rdi, rcx
0x14000f1e6  mov     eax, cs:dword_14001A498
0x14000f1ec  mov     rsi, [rcx+10h]
0x14000f1f0  mov     ecx, [rcx+28h]
0x14000f1f3  test    al, 2
0x14000f1f5  jz      loc_14000F2CF
0x14000f1fb  test    cl, 8
0x14000f1fe  jnz     loc_14000F2CF
0x14000f204  mov     eax, [rsi+80h]
0x14000f20a  cmp     eax, cs:dword_14001A438
0x14000f210  jb      loc_14000F2CF
0x14000f216  lock inc dword ptr cs:qword_14001A440+4
0x14000f21d  mov     ecx, cs:dword_14001A428
0x14000f223  lea     rax, [rsi+0E0h]
0x14000f22a  mov     r8, cs:OncRpcWiMgrGlobals
0x14000f231  dec     ecx
0x14000f233  imul    rdx, rcx, 0E0h
0x14000f23a  add     rdx, r8
0x14000f23d  cmp     rsi, rdx
0x14000f240  jmp     short loc_14000F25A
0x14000f242  mov     eax, [rbx+80h]
0x14000f248  cmp     eax, cs:dword_14001A43C
0x14000f24e  jb      short loc_14000F266
0x14000f250  cmp     rbx, rdx
0x14000f253  lea     rax, [rbx+0E0h]
0x14000f25a  mov     rbx, r8
0x14000f25d  cmovnz  rbx, rax
0x14000f261  cmp     rbx, rsi
0x14000f264  jnz     short loc_14000F242
0x14000f266  mov     rsi, rbx
0x14000f269  cmp     rbx, [rdi+10h]
0x14000f26d  jz      short loc_14000F2CF
0x14000f26f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f276  lea     rax, WPP_GLOBAL_Control
0x14000f27d  cmp     rcx, rax
0x14000f280  jz      short loc_14000F2C4
0x14000f282  mov     eax, [rcx+2Ch]
0x14000f285  test    al, al
0x14000f287  jns     short loc_14000F2C4
0x14000f289  mov     r10, [rdi+10h]
0x14000f28d  mov     edx, 11h
0x14000f292  mov     eax, [rbx+80h]
0x14000f298  mov     r8d, [rbx+70h]
0x14000f29c  mov     rcx, [rcx+18h]
0x14000f2a0  mov     r9d, [r10+70h]
0x14000f2a4  mov     [rsp+48h+var_18], eax
0x14000f2a8  mov     eax, [r10+80h]
0x14000f2af  mov     [rsp+48h+var_20], r8d
0x14000f2b4  lea     r8, WPP_c0dfc1f2c0fb36cb10e73f8368ba7cc0_Traceguids
0x14000f2bb  mov     [rsp+48h+var_28], eax
0x14000f2bf  call    WPP_SF_dddd
0x14000f2c4  lock inc dword ptr cs:qword_14001A440
0x14000f2cb  mov     [rdi+10h], rbx
0x14000f2cf  lock inc dword ptr [rsi+80h]
0x14000f2d6  mov     eax, [rdi+28h]
0x14000f2d9  lea     rcx, [rsi+20h]; Queue
0x14000f2dd  mov     rdx, rdi; Entry
0x14000f2e0  test    al, 2
0x14000f2e2  jz      short loc_14000F2F2
0x14000f2e4  call    cs:__imp_KeInsertHeadQueue
0x14000f2eb  nop     dword ptr [rax+rax+00h]
0x14000f2f0  jmp     short loc_14000F2FE
0x14000f2f2  call    cs:__imp_KeInsertQueue
0x14000f2f9  nop     dword ptr [rax+rax+00h]
0x14000f2fe  mov     rbx, [rsp+48h+arg_0]
0x14000f303  mov     rsi, [rsp+48h+arg_8]
0x14000f308  add     rsp, 40h
0x14000f30c  pop     rdi
0x14000f30d  retn
```
