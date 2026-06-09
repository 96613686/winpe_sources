# FrameRenderCompleteCallbackIsoch

- ea: `0x14001c1d0`
- end: `0x14001c4e2`
- name: `FrameRenderCompleteCallbackIsoch`
- size: `786`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140001544`
- `0x140019cd4`
- `0x140019d34`
- `0x14001b118`
- `0x14001baac`
- `0x14001c1d0`
- `0x14001c5b4`
- `0x14001d180`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001c351`
- `ntoskrnl!KeSetEvent` at `0x14001c4c1`
- `ntoskrnl!KeSetEvent` at `0x14001c351`
- `ntoskrnl!KeSetEvent` at `0x14001c4c1`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c3d9`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c441`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c476`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c4a0`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c3d9`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c441`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c476`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001c4a0`
- `ks!KsIncrementCountedWorker` at `0x14001c457`
- `ks!KsIncrementCountedWorker` at `0x14001c457`

## pseudocode

```c
__int64 __fastcall FrameRenderCompleteCallbackIsoch(__int64 a1, __int64 a2, __int64 a3)
{
  struct _KSPIN *v3; // r14
  int v5; // ebp
  char *Context; // rsi
  __int64 v7; // rbx
  __int64 v8; // r8
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  int v12; // edx

  v3 = *(struct _KSPIN **)(a3 + 16);
  v5 = *(_DWORD *)(a2 + 48);
  Context = (char *)v3->Context;
  v7 = *((_QWORD *)Context + 12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qqqd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
      v3->Context,
      a3,
      *(_QWORD *)(a3 + 32),
      v5);
  _InterlockedDecrement((volatile signed __int32 *)Context + 9);
  v8 = *(_QWORD *)(a3 + 32);
  if ( *(_DWORD *)(v8 + 4) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
        Context,
        a3,
        *(_DWORD *)(v8 + 4));
      v8 = *(_QWORD *)(a3 + 32);
    }
    v5 = -1073741668;
  }
  if ( *(_DWORD *)(v8 + 136)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids);
  }
  if ( *(_DWORD *)(v7 + 8) )
  {
    v9 = *(_DWORD *)(a3 + 48);
    v10 = *(_DWORD *)(*(_QWORD *)(a3 + 32) + 128LL);
    if ( v10 != v9 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
          Context,
          v10,
          v9);
      v11 = *(_DWORD *)(v7 + 40);
      v12 = *(_DWORD *)(*(_QWORD *)(a3 + 32) + 128LL) - *(_DWORD *)(a3 + 48);
      if ( (unsigned int)(v11 - *(_DWORD *)(v7 + 76)) >= 4 || v12 != *(_DWORD *)(v7 + 80) )
      {
        *(_DWORD *)(v7 + 72) += v12;
        *(_DWORD *)(v7 + 76) = v11;
        *(_DWORD *)(v7 + 80) = v12;
      }
    }
    FrameRenderInitializeIsochUrb(a3);
    if ( !*((_DWORD *)Context + 9) )
    {
      KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
      if ( !*(_DWORD *)(v7 + 12)
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
          (unsigned int)v5);
      }
    }
    if ( *((_DWORD *)Context + 13) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
          Context,
          a3,
          *(_QWORD *)(a3 + 32),
          v5);
      ExInterlockedInsertTailList((PLIST_ENTRY)(v7 + 288), (PLIST_ENTRY)a3, (PKSPIN_LOCK)(v7 + 280));
      ++*(_DWORD *)(v7 + 64);
    }
    else if ( v5 >= 0 )
    {
      ExInterlockedInsertTailList((PLIST_ENTRY)(v7 + 304), (PLIST_ENTRY)a3, (PKSPIN_LOCK)(v7 + 272));
      ++*(_DWORD *)(v7 + 60);
      FrameRenderTransmitData(v3);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids,
          Context,
          a3,
          *(_QWORD *)(a3 + 32),
          v5);
      *((_DWORD *)Context + 13) = 1;
      ExInterlockedInsertTailList((PLIST_ENTRY)(v7 + 288), (PLIST_ENTRY)a3, (PKSPIN_LOCK)(v7 + 280));
      ++*(_DWORD *)(v7 + 64);
      KsIncrementCountedWorker(*(PKSWORKER *)(v7 + 168));
    }
  }
  else
  {
    ExInterlockedInsertTailList((PLIST_ENTRY)(v7 + 304), (PLIST_ENTRY)a3, (PKSPIN_LOCK)(v7 + 272));
    if ( ++*(_DWORD *)(v7 + 60) == 4 )
      KeSetEvent((PRKEVENT)(Context + 128), 0, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001c1d0  push    rbx
0x14001c1d2  push    rbp
0x14001c1d3  push    rsi
0x14001c1d4  push    rdi
0x14001c1d5  push    r12
0x14001c1d7  push    r13
0x14001c1d9  push    r14
0x14001c1db  sub     rsp, 40h
0x14001c1df  mov     r14, [r8+10h]
0x14001c1e3  mov     rdi, r8
0x14001c1e6  mov     ebp, [rdx+30h]
0x14001c1e9  mov     rsi, [r14+10h]
0x14001c1ed  mov     rbx, [rsi+60h]
0x14001c1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1f8  lea     r12, WPP_GLOBAL_Control
0x14001c1ff  lea     r13, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001c206  cmp     rcx, r12
0x14001c209  jz      short loc_14001C237
0x14001c20b  cmp     byte ptr [rcx+29h], 4
0x14001c20f  jb      short loc_14001C237
0x14001c211  mov     rax, [r8+20h]
0x14001c215  mov     edx, 0Dh
0x14001c21a  mov     rcx, [rcx+18h]
0x14001c21e  mov     r9, rsi
0x14001c221  mov     [rsp+78h+var_48], ebp
0x14001c225  mov     [rsp+78h+var_50], rax
0x14001c22a  mov     [rsp+78h+var_58], r8
0x14001c22f  mov     r8, r13
0x14001c232  call    WPP_SF_qqqd
0x14001c237  lock dec dword ptr [rsi+24h]
0x14001c23b  mov     r8, [rdi+20h]
0x14001c23f  mov     eax, [r8+4]
0x14001c243  test    eax, eax
0x14001c245  jz      short loc_14001C27F
0x14001c247  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c24e  cmp     rcx, r12
0x14001c251  jz      short loc_14001C27A
0x14001c253  cmp     byte ptr [rcx+29h], 3
0x14001c257  jb      short loc_14001C27A
0x14001c259  mov     rcx, [rcx+18h]
0x14001c25d  mov     edx, 0Eh
0x14001c262  mov     dword ptr [rsp+78h+var_50], eax
0x14001c266  mov     r9, rsi
0x14001c269  mov     r8, r13
0x14001c26c  mov     [rsp+78h+var_58], rdi
0x14001c271  call    WPP_SF_qqD
0x14001c276  mov     r8, [rdi+20h]
0x14001c27a  mov     ebp, 0C000009Ch
0x14001c27f  mov     r9d, [r8+88h]
0x14001c286  test    r9d, r9d
0x14001c289  jz      short loc_14001C2C1
0x14001c28b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c292  cmp     rcx, r12
0x14001c295  jz      short loc_14001C2C1
0x14001c297  mov     eax, [rcx+2Ch]
0x14001c29a  test    al, 2
0x14001c29c  jz      short loc_14001C2C1
0x14001c29e  mov     eax, [r8+80h]
0x14001c2a5  mov     edx, 0Fh
0x14001c2aa  mov     rcx, [rcx+18h]
0x14001c2ae  mov     r8, r13
0x14001c2b1  mov     dword ptr [rsp+78h+var_50], eax
0x14001c2b5  mov     eax, [rbx+28h]
0x14001c2b8  mov     dword ptr [rsp+78h+var_58], eax
0x14001c2bc  call    WPP_SF_ddD
0x14001c2c1  cmp     dword ptr [rbx+8], 0
0x14001c2c5  jz      loc_14001C48F
0x14001c2cb  mov     rax, [rdi+20h]
0x14001c2cf  mov     r8d, [rdi+30h]
0x14001c2d3  mov     r9d, [rax+80h]
0x14001c2da  cmp     r9d, r8d
0x14001c2dd  jz      short loc_14001C337
0x14001c2df  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2e6  cmp     rcx, r12
0x14001c2e9  jz      short loc_14001C30F
0x14001c2eb  cmp     byte ptr [rcx+29h], 3
0x14001c2ef  jb      short loc_14001C30F
0x14001c2f1  mov     rcx, [rcx+18h]
0x14001c2f5  mov     edx, 10h
0x14001c2fa  mov     dword ptr [rsp+78h+var_50], r8d
0x14001c2ff  mov     r8, r13
0x14001c302  mov     dword ptr [rsp+78h+var_58], r9d
0x14001c307  mov     r9, rsi
0x14001c30a  call    WPP_SF_qDD
0x14001c30f  mov     rax, [rdi+20h]
0x14001c313  mov     ecx, [rbx+28h]
0x14001c316  mov     edx, [rax+80h]
0x14001c31c  mov     eax, ecx
0x14001c31e  sub     eax, [rbx+4Ch]
0x14001c321  sub     edx, [rdi+30h]
0x14001c324  cmp     eax, 4
0x14001c327  jnb     short loc_14001C32E
0x14001c329  cmp     edx, [rbx+50h]
0x14001c32c  jz      short loc_14001C337
0x14001c32e  add     [rbx+48h], edx
0x14001c331  mov     [rbx+4Ch], ecx
0x14001c334  mov     [rbx+50h], edx
0x14001c337  mov     rcx, rdi
0x14001c33a  call    FrameRenderInitializeIsochUrb
0x14001c33f  cmp     dword ptr [rsi+24h], 0
0x14001c343  jnz     short loc_14001C38A
0x14001c345  lea     rcx, [rsi+80h]; Event
0x14001c34c  xor     r8d, r8d; Wait
0x14001c34f  xor     edx, edx; Increment
0x14001c351  call    cs:__imp_KeSetEvent
0x14001c358  nop     dword ptr [rax+rax+00h]
0x14001c35d  cmp     dword ptr [rbx+0Ch], 0
0x14001c361  jnz     short loc_14001C38A
0x14001c363  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c36a  cmp     rcx, r12
0x14001c36d  jz      short loc_14001C38A
0x14001c36f  mov     eax, [rcx+2Ch]
0x14001c372  test    al, 2
0x14001c374  jz      short loc_14001C38A
0x14001c376  mov     rcx, [rcx+18h]
0x14001c37a  mov     edx, 11h
0x14001c37f  mov     r9d, ebp
0x14001c382  mov     r8, r13
0x14001c385  call    WPP_SF_d
0x14001c38a  cmp     dword ptr [rsi+34h], 0
0x14001c38e  jz      short loc_14001C3ED
0x14001c390  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c397  cmp     rcx, r12
0x14001c39a  jz      short loc_14001C3C8
0x14001c39c  cmp     byte ptr [rcx+29h], 3
0x14001c3a0  jb      short loc_14001C3C8
0x14001c3a2  mov     rax, [rdi+20h]
0x14001c3a6  mov     edx, 12h
0x14001c3ab  mov     rcx, [rcx+18h]
0x14001c3af  mov     r9, rsi
0x14001c3b2  mov     [rsp+78h+var_48], ebp
0x14001c3b6  mov     r8, r13
0x14001c3b9  mov     [rsp+78h+var_50], rax
0x14001c3be  mov     [rsp+78h+var_58], rdi
0x14001c3c3  call    WPP_SF_qqqd
0x14001c3c8  lea     r8, [rbx+118h]; Lock
0x14001c3cf  mov     rdx, rdi; ListEntry
0x14001c3d2  lea     rcx, [rbx+120h]; ListHead
0x14001c3d9  call    cs:__imp_ExInterlockedInsertTailList
0x14001c3e0  nop     dword ptr [rax+rax+00h]
0x14001c3e5  inc     dword ptr [rbx+40h]
0x14001c3e8  jmp     loc_14001C4CD
0x14001c3ed  test    ebp, ebp
0x14001c3ef  jns     short loc_14001C465
0x14001c3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3f8  cmp     rcx, r12
0x14001c3fb  jz      short loc_14001C429
0x14001c3fd  cmp     byte ptr [rcx+29h], 3
0x14001c401  jb      short loc_14001C429
0x14001c403  mov     rax, [rdi+20h]
0x14001c407  mov     edx, 13h
0x14001c40c  mov     rcx, [rcx+18h]
0x14001c410  mov     r9, rsi
0x14001c413  mov     [rsp+78h+var_48], ebp
0x14001c417  mov     r8, r13
0x14001c41a  mov     [rsp+78h+var_50], rax
0x14001c41f  mov     [rsp+78h+var_58], rdi
0x14001c424  call    WPP_SF_qqqd
0x14001c429  lea     r8, [rbx+118h]; Lock
0x14001c430  mov     dword ptr [rsi+34h], 1
0x14001c437  lea     rcx, [rbx+120h]; ListHead
0x14001c43e  mov     rdx, rdi; ListEntry
0x14001c441  call    cs:__imp_ExInterlockedInsertTailList
0x14001c448  nop     dword ptr [rax+rax+00h]
0x14001c44d  inc     dword ptr [rbx+40h]
0x14001c450  mov     rcx, [rbx+0A8h]; Worker
0x14001c457  call    cs:__imp_KsIncrementCountedWorker
0x14001c45e  nop     dword ptr [rax+rax+00h]
0x14001c463  jmp     short loc_14001C4CD
0x14001c465  lea     r8, [rbx+110h]; Lock
0x14001c46c  mov     rdx, rdi; ListEntry
0x14001c46f  lea     rcx, [rbx+130h]; ListHead
0x14001c476  call    cs:__imp_ExInterlockedInsertTailList
0x14001c47d  nop     dword ptr [rax+rax+00h]
0x14001c482  inc     dword ptr [rbx+3Ch]
0x14001c485  mov     rcx, r14; Pin
0x14001c488  call    FrameRenderTransmitData
0x14001c48d  jmp     short loc_14001C4CD
0x14001c48f  lea     r8, [rbx+110h]; Lock
0x14001c496  mov     rdx, rdi; ListEntry
0x14001c499  lea     rcx, [rbx+130h]; ListHead
0x14001c4a0  call    cs:__imp_ExInterlockedInsertTailList
0x14001c4a7  nop     dword ptr [rax+rax+00h]
0x14001c4ac  inc     dword ptr [rbx+3Ch]
0x14001c4af  cmp     dword ptr [rbx+3Ch], 4
0x14001c4b3  jnz     short loc_14001C4CD
0x14001c4b5  lea     rcx, [rsi+80h]; Event
0x14001c4bc  xor     r8d, r8d; Wait
0x14001c4bf  xor     edx, edx; Increment
0x14001c4c1  call    cs:__imp_KeSetEvent
0x14001c4c8  nop     dword ptr [rax+rax+00h]
0x14001c4cd  mov     eax, 0C0000016h
0x14001c4d2  add     rsp, 40h
0x14001c4d6  pop     r14
0x14001c4d8  pop     r13
0x14001c4da  pop     r12
0x14001c4dc  pop     rdi
0x14001c4dd  pop     rsi
0x14001c4de  pop     rbp
0x14001c4df  pop     rbx
0x14001c4e0  retn
```
