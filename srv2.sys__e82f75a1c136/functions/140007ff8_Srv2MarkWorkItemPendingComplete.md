# Srv2MarkWorkItemPendingComplete

- ea: `0x140007ff8`
- end: `0x140008184`
- name: `Srv2MarkWorkItemPendingComplete`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140007090`

## callees

- `0x140004960`
- `0x140005070`
- `0x140007ff8`
- `0x1400222ec`
- `0x140022690`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14003aa12`
- `ntoskrnl!KeBugCheckEx` at `0x14003aa12`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400080c4`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400080c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000800a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000800a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000806f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000806f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400080e0`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400080e0`

## string_xrefs

- `0x1400080a5`: `Srv2PostToThreadPool`

## pseudocode

```c
void __fastcall Srv2MarkWorkItemPendingComplete(__int64 a1)
{
  KIRQL v2; // r14
  __int64 v3; // rbx
  __int64 v4; // rdx
  bool v5; // zf
  __int64 v6; // rbx
  __int64 v7; // rbx
  ULONG_PTR BugCheckParameter4; // [rsp+20h] [rbp-38h]

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 80));
  if ( *(_DWORD *)(a1 + 12) != 222 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_1f56813514af312e5a39176f5ad11993_Traceguids, a1);
    }
    KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\workitem.c", 0x874u, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    BugCheckParameter4 = *(_QWORD *)(a1 + 520);
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_1f56813514af312e5a39176f5ad11993_Traceguids);
  }
  v3 = *(_QWORD *)(a1 + 520);
  *(_DWORD *)(a1 + 12) = 220;
  *(_QWORD *)(a1 + 520) = 0;
  if ( v3 )
    *(_DWORD *)(a1 + 12) = 223;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 80), v2);
  if ( v3 )
  {
    v5 = *(_DWORD *)(a1 + 8) == 5;
    *(_QWORD *)(a1 + 48) = v3;
    *(_DWORD *)(a1 + 72) = 0;
    if ( v5 )
    {
      LOBYTE(BugCheckParameter4) = 1;
      LOBYTE(v4) = 1;
      SRV2_PERF_ENTER_EX(a1 + 584, v4, 391, "Srv2PostToThreadPool", BugCheckParameter4);
    }
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 136LL);
    v7 = *(_QWORD *)(v6 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v7 + 16), (PSLIST_ENTRY)(a1 + 32)) )
    {
      if ( *(_WORD *)(v7 + 66) )
        RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v7);
    }
  }
}

```

## disassembly

```asm
0x140007ff8  push    rbx
0x140007ffa  push    rbp
0x140007ffb  push    rsi
0x140007ffc  push    rdi
0x140007ffd  push    r14
0x140007fff  sub     rsp, 30h
0x140008003  mov     rdi, rcx
0x140008006  add     rcx, 50h ; 'P'; SpinLock
0x14000800a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008011  nop     dword ptr [rax+rax+00h]
0x140008016  cmp     dword ptr [rdi+0Ch], 0DEh
0x14000801d  mov     r14b, al
0x140008020  jnz     loc_14000813A
0x140008026  mov     rcx, cs:WPP_GLOBAL_Control
0x14000802d  lea     rdx, WPP_GLOBAL_Control
0x140008034  cmp     rcx, rdx
0x140008037  jz      short loc_140008045
0x140008039  mov     edx, [rcx+2Ch]
0x14000803c  test    dl, 1
0x14000803f  jnz     loc_140008107
0x140008045  mov     rbx, [rdi+208h]
0x14000804c  xor     esi, esi
0x14000804e  mov     dword ptr [rdi+0Ch], 0DCh
0x140008055  mov     [rdi+208h], rsi
0x14000805c  test    rbx, rbx
0x14000805f  jz      short loc_140008068
0x140008061  mov     dword ptr [rdi+0Ch], 0DFh
0x140008068  mov     dl, r14b; NewIrql
0x14000806b  lea     rcx, [rdi+50h]; SpinLock
0x14000806f  call    cs:__imp_KeReleaseSpinLock
0x140008076  nop     dword ptr [rax+rax+00h]
0x14000807b  test    rbx, rbx
0x14000807e  jnz     short loc_14000808C
0x140008080  add     rsp, 30h
0x140008084  pop     r14
0x140008086  pop     rdi
0x140008087  pop     rsi
0x140008088  pop     rbp
0x140008089  pop     rbx
0x14000808a  retn
0x14000808c  cmp     dword ptr [rdi+8], 5
0x140008090  mov     [rdi+30h], rbx
0x140008094  mov     [rdi+48h], esi
0x140008097  jnz     short loc_1400080B9
0x140008099  lea     rcx, [rdi+248h]
0x1400080a0  mov     byte ptr [rsp+58h+BugCheckParameter4], 1
0x1400080a5  lea     r9, SourceString; "Srv2PostToThreadPool"
0x1400080ac  mov     r8d, 187h
0x1400080b2  mov     dl, 1
0x1400080b4  call    SRV2_PERF_ENTER_EX
0x1400080b9  mov     rax, [rdi+40h]
0x1400080bd  mov     rbx, [rax+88h]
0x1400080c4  call    cs:__imp_KeGetCurrentNodeNumber
0x1400080cb  nop     dword ptr [rax+rax+00h]
0x1400080d0  movzx   eax, ax
0x1400080d3  lea     rdx, [rdi+20h]; ListEntry
0x1400080d7  mov     rbx, [rbx+rax*8+8]
0x1400080dc  lea     rcx, [rbx+10h]; ListHead
0x1400080e0  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400080e7  nop     dword ptr [rax+rax+00h]
0x1400080ec  test    rax, rax
0x1400080ef  jnz     short loc_140008080
0x1400080f1  movzx   eax, word ptr [rbx+42h]
0x1400080f5  cmp     si, ax
0x1400080f8  jz      short loc_140008080
0x1400080fa  mov     rcx, rbx
0x1400080fd  call    RfspThreadPoolNodeWakeIdleWorker
0x140008102  jmp     loc_140008080
0x140008107  cmp     byte ptr [rcx+29h], 2
0x14000810b  jb      loc_140008045
0x140008111  mov     rax, [rdi+208h]
0x140008118  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x14000811f  mov     rcx, [rcx+18h]
0x140008123  mov     edx, 25h ; '%'
0x140008128  mov     r9, rdi
0x14000812b  mov     [rsp+58h+BugCheckParameter4], rax
0x140008130  call    WPP_SF_qq
0x140008135  jmp     loc_140008045
0x14000813a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008141  lea     rdx, WPP_GLOBAL_Control
0x140008148  cmp     rcx, rdx
0x14000814b  jz      loc_14003A9F8
0x140008151  mov     eax, [rcx+2Ch]
0x140008154  test    al, 1
0x140008156  jz      loc_14003A9F8
0x14000815c  cmp     byte ptr [rcx+29h], 1
0x140008160  jb      loc_14003A9F8
0x140008166  mov     rcx, [rcx+18h]
0x14000816a  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x140008171  mov     edx, 26h ; '&'
0x140008176  mov     r9, rdi
0x140008179  call    WPP_SF_q
0x14000817e  nop
0x14000817f  jmp     loc_14003A9F8
0x14003a9f8  xor     esi, esi
0x14003a9fa  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14003aa01  xor     r9d, r9d; BugCheckParameter3
0x14003aa04  mov     [rsp+58h+BugCheckParameter4], rsi; BugCheckParameter4
0x14003aa09  mov     r8d, 874h; BugCheckParameter2
0x14003aa0f  lea     ecx, [rsi+54h]; BugCheckCode
0x14003aa12  call    cs:__imp_KeBugCheckEx
```
