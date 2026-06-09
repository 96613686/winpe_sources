# SrvNetListenerRuleEntryUpdate

- ea: `0x14001f244`
- end: `0x14001f637`
- name: `SrvNetListenerRuleEntryUpdate`
- size: `1011`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size, void *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x140011cb8`

## callees

- `0x140007c60`
- `0x140014190`
- `0x140015790`
- `0x140016384`
- `0x14001e918`
- `0x14001ea1c`
- `0x14001edfc`
- `0x14001f244`
- `0x14001f740`
- `0x14001f888`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f503`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f5b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f503`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f5b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f32b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f32b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f30f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f30f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f4f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f5a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f4f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f5a4`

## pseudocode

```c
__int64 __fastcall SrvNetListenerRuleEntryUpdate(
        unsigned __int16 a1,
        unsigned int a2,
        char a3,
        char a4,
        size_t Size,
        void *a6,
        __int64 a7)
{
  __int64 v7; // rsi
  unsigned int ListenersBasedOnListenerRuleEntry; // edi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *ListenerRuleEntry; // rax
  int v15; // r14d
  int v16; // ebp
  unsigned __int16 *v17; // rbx
  int v18; // r8d
  int v19; // edx
  char v20; // si
  __int64 v21; // rcx
  unsigned __int16 **v22; // rdx
  int v23; // r8d
  char v24; // bp
  int v25; // ebp
  __int64 PoolWithTag; // rax
  PERESOURCE v27; // r8
  __int64 *v28; // rdx
  __int64 v29; // r8
  __int64 **v30; // rax

  v7 = (int)a2;
  if ( a2 - 1 <= 1 )
  {
    ListenersBasedOnListenerRuleEntry = -1073741637;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids);
    }
    return ListenersBasedOnListenerRuleEntry;
  }
  if ( !(unsigned __int8)SrvNetTransportTypeSupportsMultiplePorts(a2) )
  {
    ListenersBasedOnListenerRuleEntry = -1073741637;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v13 = 17;
LABEL_7:
      WPP_SF_Dd(
        v12->AttachedDevice,
        v13,
        WPP_4b4512c1b54e30e269f755586e080b68_Traceguids,
        (unsigned int)v7,
        -1073741637);
      return ListenersBasedOnListenerRuleEntry;
    }
    return ListenersBasedOnListenerRuleEntry;
  }
  if ( a6 && (_DWORD)Size )
    memset(a6, 0, (unsigned int)Size);
  if ( ((a1 - 443) & 0xFFFD) != 0 )
  {
    ListenersBasedOnListenerRuleEntry = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 944), 1u);
    ListenerRuleEntry = (unsigned __int16 *)SrvNetFindListenerRuleEntry(a1, (unsigned int)v7);
    v15 = a3 & 0x3F;
    v16 = a4 & 0x3F;
    v17 = ListenerRuleEntry;
    if ( ListenerRuleEntry )
    {
      v18 = *((_DWORD *)ListenerRuleEntry + 1);
      v19 = (v15 | v18) & ~v16;
      *((_DWORD *)ListenerRuleEntry + 1) = v19;
      if ( (((v15 | v18) ^ v19) & v16) != 0 )
      {
        v20 = 1;
      }
      else
      {
        v20 = 0;
        if ( v18 != v19 && (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 1) != 0 )
          McTemplateK0hqq_EtwWriteTransfer(
            v15 | v18,
            (unsigned int)SrvNetAddListenerRuleUpdate,
            v18,
            *ListenerRuleEntry,
            *((_BYTE *)ListenerRuleEntry + 2),
            v19);
      }
      if ( *((_DWORD *)v17 + 1) )
        goto LABEL_23;
      v21 = *((_QWORD *)v17 + 1);
      if ( *(unsigned __int16 **)(v21 + 8) == v17 + 4 )
      {
        v22 = (unsigned __int16 **)*((_QWORD *)v17 + 2);
        if ( *v22 == v17 + 4 )
        {
          *v22 = (unsigned __int16 *)v21;
          *(_QWORD *)(v21 + 8) = v22;
          *((_BYTE *)v17 + 28) = 1;
          SrvNetDereferenceListenerRuleEntry(v17);
          if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 1) != 0 )
            McTemplateK0hqq_EtwWriteTransfer(
              *((unsigned __int8 *)v17 + 2),
              (unsigned int)SrvNetAddListenerRuleRemove,
              v23,
              *v17,
              *((_BYTE *)v17 + 2),
              *((_DWORD *)v17 + 1));
LABEL_23:
          v24 = 1;
          if ( v20 )
            SrvNetRestrictConnectionsBasedOnListenerRuleEntry(v17);
LABEL_33:
          ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 944));
          KeLeaveCriticalRegion();
          if ( v24 )
            SrvNetDereferenceListenerRuleEntry(v17);
          return ListenersBasedOnListenerRuleEntry;
        }
      }
LABEL_29:
      __fastfail(3u);
    }
    v25 = v15 ^ v16;
    if ( v25 && v15 )
    {
      PoolWithTag = SrvNetAllocatePoolWithTag(64, 32, 1852592972);
      v17 = (unsigned __int16 *)PoolWithTag;
      if ( PoolWithTag )
      {
        v27 = SrvNetDeviceExtension;
        v28 = (__int64 *)(PoolWithTag + 8);
        *(_DWORD *)(PoolWithTag + 24) = 1;
        *(_WORD *)PoolWithTag = a1;
        v29 = (__int64)(&v27[10].ActiveCount + 8 * v7);
        *(_BYTE *)(PoolWithTag + 2) = v7;
        *(_DWORD *)(PoolWithTag + 4) = v25;
        *(_QWORD *)(PoolWithTag + 16) = PoolWithTag + 8;
        *(_QWORD *)(PoolWithTag + 8) = PoolWithTag + 8;
        v30 = *(__int64 ***)(v29 + 8);
        if ( *v30 == (__int64 *)v29 )
        {
          *v28 = v29;
          v24 = 0;
          v28[1] = (__int64)v30;
          *v30 = v28;
          *(_QWORD *)(v29 + 8) = v28;
          if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 1) != 0 )
            McTemplateK0hqq_EtwWriteTransfer(
              *((unsigned __int8 *)v17 + 2),
              (unsigned int)SrvNetAddListenerRuleNew,
              v29,
              *v17,
              *((_BYTE *)v17 + 2),
              *((_DWORD *)v17 + 1));
          ListenersBasedOnListenerRuleEntry = SrvNetCreateListenersBasedOnListenerRuleEntry(
                                                v17,
                                                (unsigned int)Size,
                                                a6,
                                                a7);
          goto LABEL_33;
        }
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids);
      }
      ListenersBasedOnListenerRuleEntry = -1073741670;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids);
    }
    ExReleaseResourceLite((PERESOURCE)((char *)SrvNetDeviceExtension + 944));
    KeLeaveCriticalRegion();
    return ListenersBasedOnListenerRuleEntry;
  }
  ListenersBasedOnListenerRuleEntry = -1073741637;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v13 = 18;
    goto LABEL_7;
  }
  return ListenersBasedOnListenerRuleEntry;
}

```

## disassembly

```asm
0x14001f244  push    rbx
0x14001f246  push    rbp
0x14001f247  push    rsi
0x14001f248  push    rdi
0x14001f249  push    r13
0x14001f24b  push    r14
0x14001f24d  sub     rsp, 38h
0x14001f251  movsxd  rsi, edx
0x14001f254  mov     ebp, r9d
0x14001f257  mov     r14d, r8d
0x14001f25a  movzx   r13d, cx
0x14001f25e  lea     eax, [rsi-1]
0x14001f261  cmp     eax, 1
0x14001f264  jbe     loc_14001F5ED
0x14001f26a  mov     ecx, esi
0x14001f26c  call    SrvNetTransportTypeSupportsMultiplePorts
0x14001f271  test    al, al
0x14001f273  jnz     short loc_14001F2C7
0x14001f275  mov     edi, 0C00000BBh
0x14001f27a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f281  lea     rax, WPP_GLOBAL_Control
0x14001f288  cmp     rcx, rax
0x14001f28b  jz      loc_14001F627
0x14001f291  mov     eax, [rcx+2Ch]
0x14001f294  test    al, 10h
0x14001f296  jz      loc_14001F627
0x14001f29c  cmp     byte ptr [rcx+29h], 1
0x14001f2a0  jb      loc_14001F627
0x14001f2a6  mov     edx, 11h
0x14001f2ab  mov     rcx, [rcx+18h]
0x14001f2af  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001f2b6  mov     r9d, esi
0x14001f2b9  mov     [rsp+68h+var_48], edi
0x14001f2bd  call    WPP_SF_Dd
0x14001f2c2  jmp     loc_14001F627
0x14001f2c7  cmp     [rsp+68h+arg_28], 0
0x14001f2d0  jz      short loc_14001F2F3
0x14001f2d2  cmp     dword ptr [rsp+68h+Size], 0
0x14001f2da  jz      short loc_14001F2F3
0x14001f2dc  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x14001f2e4  xor     edx, edx; Val
0x14001f2e6  mov     rcx, [rsp+68h+arg_28]; void *
0x14001f2ee  call    memset
0x14001f2f3  mov     ecx, 1BBh
0x14001f2f8  movzx   eax, r13w
0x14001f2fc  sub     ax, cx
0x14001f2ff  mov     ecx, 0FFFDh
0x14001f304  test    cx, ax
0x14001f307  jz      loc_14001F5BE
0x14001f30d  xor     edi, edi
0x14001f30f  call    cs:__imp_KeEnterCriticalRegion
0x14001f316  nop     dword ptr [rax+rax+00h]
0x14001f31b  mov     rcx, cs:SrvNetDeviceExtension
0x14001f322  mov     dl, 1; Wait
0x14001f324  add     rcx, 3B0h; Resource
0x14001f32b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001f332  nop     dword ptr [rax+rax+00h]
0x14001f337  mov     edx, esi
0x14001f339  movzx   ecx, r13w
0x14001f33d  call    SrvNetFindListenerRuleEntry
0x14001f342  and     r14d, 3Fh
0x14001f346  and     ebp, 3Fh
0x14001f349  mov     rbx, rax
0x14001f34c  test    rax, rax
0x14001f34f  jz      loc_14001F419
0x14001f355  mov     r8d, [rax+4]
0x14001f359  mov     edx, ebp
0x14001f35b  mov     ecx, r8d
0x14001f35e  not     edx
0x14001f360  or      ecx, r14d
0x14001f363  and     edx, ecx
0x14001f365  mov     [rax+4], edx
0x14001f368  mov     eax, edx
0x14001f36a  xor     eax, ecx
0x14001f36c  test    ebp, eax
0x14001f36e  jz      short loc_14001F375
0x14001f370  mov     sil, 1
0x14001f373  jmp     short loc_14001F3A2
0x14001f375  xor     sil, sil
0x14001f378  cmp     r8d, edx
0x14001f37b  jz      short loc_14001F3A2
0x14001f37d  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 1
0x14001f384  jz      short loc_14001F3A2
0x14001f386  movzx   eax, byte ptr [rbx+2]
0x14001f38a  movzx   r9d, word ptr [rbx]
0x14001f38e  mov     [rsp+68h+var_40], edx
0x14001f392  lea     rdx, SrvNetAddListenerRuleUpdate
0x14001f399  mov     [rsp+68h+var_48], eax
0x14001f39d  call    McTemplateK0hqq_EtwWriteTransfer
0x14001f3a2  cmp     [rbx+4], edi
0x14001f3a5  jnz     short loc_14001F400
0x14001f3a7  lea     rax, [rbx+8]
0x14001f3ab  mov     rcx, [rax]
0x14001f3ae  cmp     [rcx+8], rax
0x14001f3b2  jnz     loc_14001F488
0x14001f3b8  mov     rdx, [rax+8]
0x14001f3bc  cmp     [rdx], rax
0x14001f3bf  jnz     loc_14001F488
0x14001f3c5  mov     [rdx], rcx
0x14001f3c8  mov     [rcx+8], rdx
0x14001f3cc  mov     rcx, rbx
0x14001f3cf  mov     byte ptr [rbx+1Ch], 1
0x14001f3d3  call    SrvNetDereferenceListenerRuleEntry
0x14001f3d8  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 1
0x14001f3df  jz      short loc_14001F400
0x14001f3e1  movzx   ecx, byte ptr [rbx+2]
0x14001f3e5  lea     rdx, SrvNetAddListenerRuleRemove
0x14001f3ec  mov     eax, [rbx+4]
0x14001f3ef  movzx   r9d, word ptr [rbx]
0x14001f3f3  mov     [rsp+68h+var_40], eax
0x14001f3f7  mov     [rsp+68h+var_48], ecx
0x14001f3fb  call    McTemplateK0hqq_EtwWriteTransfer
0x14001f400  mov     bpl, 1
0x14001f403  test    sil, sil
0x14001f406  jz      loc_14001F4E9
0x14001f40c  mov     rcx, rbx
0x14001f40f  call    SrvNetRestrictConnectionsBasedOnListenerRuleEntry
0x14001f414  jmp     loc_14001F4E9
0x14001f419  xor     ebp, r14d
0x14001f41c  jz      loc_14001F561
0x14001f422  test    r14d, r14d
0x14001f425  jz      loc_14001F561
0x14001f42b  mov     edx, 20h ; ' '
0x14001f430  mov     r8d, 6E6C534Ch
0x14001f436  lea     ecx, [rdx+20h]
0x14001f439  call    SrvNetAllocatePoolWithTag
0x14001f43e  mov     rbx, rax
0x14001f441  test    rax, rax
0x14001f444  jz      loc_14001F525
0x14001f44a  mov     r8, cs:SrvNetDeviceExtension
0x14001f451  lea     rdx, [rax+8]
0x14001f455  mov     dword ptr [rax+18h], 1
0x14001f45c  add     r8, 428h
0x14001f463  mov     [rax], r13w
0x14001f467  mov     rcx, rsi
0x14001f46a  shl     rcx, 4
0x14001f46e  add     r8, rcx
0x14001f471  mov     [rax+2], sil
0x14001f475  mov     [rax+4], ebp
0x14001f478  mov     [rdx+8], rdx
0x14001f47c  mov     [rdx], rdx
0x14001f47f  mov     rax, [r8+8]
0x14001f483  cmp     [rax], r8
0x14001f486  jz      short loc_14001F48F
0x14001f488  mov     ecx, 3
0x14001f48d  int     29h; Win8: RtlFailFast(ecx)
0x14001f48f  mov     [rdx], r8
0x14001f492  xor     bpl, bpl
0x14001f495  mov     [rdx+8], rax
0x14001f499  mov     [rax], rdx
0x14001f49c  mov     [r8+8], rdx
0x14001f4a0  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 1
0x14001f4a7  jz      short loc_14001F4C8
0x14001f4a9  movzx   ecx, byte ptr [rbx+2]
0x14001f4ad  lea     rdx, SrvNetAddListenerRuleNew
0x14001f4b4  mov     eax, [rbx+4]
0x14001f4b7  movzx   r9d, word ptr [rbx]
0x14001f4bb  mov     [rsp+68h+var_40], eax
0x14001f4bf  mov     [rsp+68h+var_48], ecx
0x14001f4c3  call    McTemplateK0hqq_EtwWriteTransfer
0x14001f4c8  mov     r9, [rsp+68h+arg_30]
0x14001f4d0  mov     rcx, rbx
0x14001f4d3  mov     r8, [rsp+68h+arg_28]
0x14001f4db  mov     edx, dword ptr [rsp+68h+Size]
0x14001f4e2  call    SrvNetCreateListenersBasedOnListenerRuleEntry
0x14001f4e7  mov     edi, eax
0x14001f4e9  mov     rcx, cs:SrvNetDeviceExtension
0x14001f4f0  add     rcx, 3B0h; Resource
0x14001f4f7  call    cs:__imp_ExReleaseResourceLite
0x14001f4fe  nop     dword ptr [rax+rax+00h]
0x14001f503  call    cs:__imp_KeLeaveCriticalRegion
0x14001f50a  nop     dword ptr [rax+rax+00h]
0x14001f50f  test    bpl, bpl
0x14001f512  jz      loc_14001F627
0x14001f518  mov     rcx, rbx
0x14001f51b  call    SrvNetDereferenceListenerRuleEntry
0x14001f520  jmp     loc_14001F627
0x14001f525  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f52c  lea     rax, WPP_GLOBAL_Control
0x14001f533  cmp     rcx, rax
0x14001f536  jz      short loc_14001F55A
0x14001f538  mov     eax, [rcx+2Ch]
0x14001f53b  test    al, 10h
0x14001f53d  jz      short loc_14001F55A
0x14001f53f  cmp     byte ptr [rcx+29h], 2
0x14001f543  jb      short loc_14001F55A
0x14001f545  mov     rcx, [rcx+18h]
0x14001f549  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001f550  mov     edx, 14h
0x14001f555  call    WPP_SF_
0x14001f55a  mov     edi, 0C000009Ah
0x14001f55f  jmp     short loc_14001F596
0x14001f561  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f568  lea     rax, WPP_GLOBAL_Control
0x14001f56f  cmp     rcx, rax
0x14001f572  jz      short loc_14001F596
0x14001f574  mov     eax, [rcx+2Ch]
0x14001f577  test    al, 10h
0x14001f579  jz      short loc_14001F596
0x14001f57b  cmp     byte ptr [rcx+29h], 2
0x14001f57f  jb      short loc_14001F596
0x14001f581  mov     rcx, [rcx+18h]
0x14001f585  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001f58c  mov     edx, 13h
0x14001f591  call    WPP_SF_
0x14001f596  mov     rcx, cs:SrvNetDeviceExtension
0x14001f59d  add     rcx, 3B0h; Resource
0x14001f5a4  call    cs:__imp_ExReleaseResourceLite
0x14001f5ab  nop     dword ptr [rax+rax+00h]
0x14001f5b0  call    cs:__imp_KeLeaveCriticalRegion
0x14001f5b7  nop     dword ptr [rax+rax+00h]
0x14001f5bc  jmp     short loc_14001F627
0x14001f5be  mov     edi, 0C00000BBh
0x14001f5c3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f5ca  lea     rax, WPP_GLOBAL_Control
0x14001f5d1  cmp     rcx, rax
0x14001f5d4  jz      short loc_14001F627
0x14001f5d6  mov     eax, [rcx+2Ch]
0x14001f5d9  test    al, 10h
0x14001f5db  jz      short loc_14001F627
0x14001f5dd  cmp     byte ptr [rcx+29h], 1
0x14001f5e1  jb      short loc_14001F627
0x14001f5e3  mov     edx, 12h
0x14001f5e8  jmp     loc_14001F2AB
0x14001f5ed  mov     edi, 0C00000BBh
0x14001f5f2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001f5f9  lea     rax, WPP_GLOBAL_Control
0x14001f600  cmp     rcx, rax
0x14001f603  jz      short loc_14001F627
0x14001f605  mov     eax, [rcx+2Ch]
0x14001f608  test    al, 10h
0x14001f60a  jz      short loc_14001F627
0x14001f60c  cmp     byte ptr [rcx+29h], 1
0x14001f610  jb      short loc_14001F627
0x14001f612  mov     rcx, [rcx+18h]
0x14001f616  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001f61d  mov     edx, 10h
0x14001f622  call    WPP_SF_
0x14001f627  mov     eax, edi
0x14001f629  add     rsp, 38h
0x14001f62d  pop     r14
0x14001f62f  pop     r13
0x14001f631  pop     rdi
0x14001f632  pop     rsi
0x14001f633  pop     rbp
0x14001f634  pop     rbx
0x14001f635  retn
```
