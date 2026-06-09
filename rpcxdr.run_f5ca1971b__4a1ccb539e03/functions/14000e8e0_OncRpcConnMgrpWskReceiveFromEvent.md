# OncRpcConnMgrpWskReceiveFromEvent

- ea: `0x14000e8e0`
- end: `0x14000ebaf`
- name: `OncRpcConnMgrpWskReceiveFromEvent`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140001020`
- `0x1400020c0`
- `0x140002104`
- `0x1400059a4`
- `0x140006720`
- `0x140006798`
- `0x14000e8e0`
- `0x14000f770`
- `0x14000fabc`
- `0x14000fce4`
- `0x140015840`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000eaae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000eaae`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskReceiveFromEvent(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rsi
  unsigned int v6; // eax
  bool v7; // zf
  int v8; // eax
  __int64 v9; // rbp
  int v10; // ebx
  const GUID *v11; // r15
  int v12; // edx
  struct _MDL *v13; // r14
  unsigned int v14; // r12d
  __int64 v15; // rbp
  int v16; // esi
  char *MappedSystemVa; // rax
  _QWORD *v18; // r15
  __int64 v19; // r13
  char *v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+38h] [rbp-50h]
  const GUID *v24; // [rsp+40h] [rbp-48h]
  __int64 v26; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, a1);
  if ( !a3 )
    return 3221226011LL;
  v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 232), 0, 0);
  if ( v6 <= dword_14001A434 )
  {
    do
    {
      v7 = a3[3] == 0;
      v22 = 0;
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_qd(
            WPP_GLOBAL_Control->AttachedDevice,
            43,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            v4,
            -1073739509);
        }
      }
      else
      {
        v8 = OncRpcWiMgrpSrvWorkItemAlloc(v4, 0, &v22);
        v9 = v22;
        v10 = v8;
        if ( v8 < 0 )
          goto LABEL_30;
        v11 = (const GUID *)(v22 + 2444);
        v24 = (const GUID *)(v22 + 2444);
        LogOncrpcEvent(&ONCRPC_EVENT_WSK_INDICATION, (LPCGUID)(v22 + 2444));
        v12 = *((_DWORD *)a3 + 6);
        v26 = v9 + 128;
        v10 = OncRpcBufMgrAllocate((unsigned int)&v26, v12, 4, 0, 0);
        if ( v10 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, v4, v10);
        }
        if ( v10 < 0 )
        {
LABEL_30:
          if ( v9 )
          {
            if ( v10 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                46,
                WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
                (unsigned int)v10);
            }
            OncRpcWiMgrSrvWorkItemFree(v9);
          }
        }
        else
        {
          v13 = (struct _MDL *)a3[1];
          v14 = *((_DWORD *)a3 + 6);
          v23 = *(_QWORD *)(v26 + 40);
          if ( v13 )
          {
            v15 = v26;
            v16 = *((_DWORD *)a3 + 4);
            do
            {
              if ( !v14 )
                break;
              if ( (v13->MdlFlags & 5) != 0 )
                MappedSystemVa = (char *)v13->MappedSystemVa;
              else
                MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v13, 0, MmCached, 0, 0, 0x40000000u);
              v18 = *(_QWORD **)(v15 + 40);
              v19 = v14;
              v20 = &MappedSystemVa[v16];
              v21 = v13->ByteCount - v16;
              if ( v14 >= v21 )
                v19 = v21;
              v16 = 0;
              if ( v18 )
                v18 = (_QWORD *)v18[8];
              memmove(v18, v20, (unsigned int)v19);
              v14 -= v19;
              *(_QWORD *)(v23 + 64) = (char *)v18 + v19;
              v13 = v13->Next;
            }
            while ( v13 );
            v4 = a1;
            v9 = v22;
            v11 = v24;
          }
          LogOncrpcEvent(&ONCRPC_EVENT_PKT_RECEIVE_COMPLETION, v11);
          OncRpcCopyAddress(v9 + 316, a3[6]);
          OncRpcWiMgrProcessSrvWorkItem(v9, 0, v4);
        }
      }
      a3 = (__int64 *)*a3;
    }
    while ( a3 );
  }
  return 0;
}

```

## disassembly

```asm
0x14000e8e0  mov     [rsp+arg_8], rbx
0x14000e8e5  mov     [rsp+arg_0], rcx
0x14000e8ea  push    rbp
0x14000e8eb  push    rsi
0x14000e8ec  push    rdi
0x14000e8ed  push    r12
0x14000e8ef  push    r13
0x14000e8f1  push    r14
0x14000e8f3  push    r15
0x14000e8f5  sub     rsp, 50h
0x14000e8f9  mov     rdi, r8
0x14000e8fc  mov     rsi, rcx
0x14000e8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e906  lea     r14, WPP_GLOBAL_Control
0x14000e90d  cmp     rcx, r14
0x14000e910  jz      short loc_14000E931
0x14000e912  mov     eax, [rcx+2Ch]
0x14000e915  test    al, 1
0x14000e917  jz      short loc_14000E931
0x14000e919  mov     rcx, [rcx+18h]
0x14000e91d  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e924  mov     edx, 2Ah ; '*'
0x14000e929  mov     r9, rsi
0x14000e92c  call    WPP_SF_q
0x14000e931  test    rdi, rdi
0x14000e934  jnz     short loc_14000E940
0x14000e936  mov     eax, 0C000021Bh
0x14000e93b  jmp     loc_14000EB96
0x14000e940  xor     ecx, ecx
0x14000e942  xor     eax, eax
0x14000e944  lock cmpxchg [rsi+0E8h], ecx
0x14000e94c  cmp     eax, cs:dword_14001A434
0x14000e952  ja      loc_14000EB94
0x14000e958  cmp     qword ptr [rdi+18h], 0
0x14000e95d  mov     [rsp+88h+var_58], 0
0x14000e966  jnz     short loc_14000E9A8
0x14000e968  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e96f  cmp     rcx, r14
0x14000e972  jz      loc_14000EB88
0x14000e978  mov     eax, [rcx+2Ch]
0x14000e97b  test    al, 10h
0x14000e97d  jz      loc_14000EB88
0x14000e983  mov     rcx, [rcx+18h]
0x14000e987  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e98e  mov     edx, 2Bh ; '+'
0x14000e993  mov     [rsp+88h+BugCheckOnFailure], 0C000090Bh
0x14000e99b  mov     r9, rsi
0x14000e99e  call    WPP_SF_qd
0x14000e9a3  jmp     loc_14000EB88
0x14000e9a8  lea     r8, [rsp+88h+var_58]
0x14000e9ad  xor     edx, edx
0x14000e9af  mov     rcx, rsi
0x14000e9b2  call    OncRpcWiMgrpSrvWorkItemAlloc
0x14000e9b7  mov     rbp, [rsp+88h+var_58]
0x14000e9bc  mov     ebx, eax
0x14000e9be  test    eax, eax
0x14000e9c0  js      loc_14000EB4C
0x14000e9c6  lea     r15, [rbp+98Ch]
0x14000e9cd  mov     rdx, r15; ActivityId
0x14000e9d0  mov     [rsp+88h+var_48], r15
0x14000e9d5  lea     rcx, ONCRPC_EVENT_WSK_INDICATION; EventDescriptor
0x14000e9dc  call    LogOncrpcEvent
0x14000e9e1  mov     edx, [rdi+18h]
0x14000e9e4  lea     rax, [rbp+80h]
0x14000e9eb  xor     r9d, r9d
0x14000e9ee  mov     [rsp+88h+arg_18], rax
0x14000e9f6  lea     rcx, [rsp+88h+arg_18]
0x14000e9fe  mov     qword ptr [rsp+88h+BugCheckOnFailure], 0
0x14000ea07  lea     r8d, [r9+4]
0x14000ea0b  call    OncRpcBufMgrAllocate
0x14000ea10  mov     ebx, eax
0x14000ea12  test    eax, eax
0x14000ea14  jns     short loc_14000EA45
0x14000ea16  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea1d  cmp     rcx, r14
0x14000ea20  jz      short loc_14000EA45
0x14000ea22  mov     eax, [rcx+2Ch]
0x14000ea25  test    al, 10h
0x14000ea27  jz      short loc_14000EA45
0x14000ea29  mov     rcx, [rcx+18h]
0x14000ea2d  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000ea34  mov     edx, 2Dh ; '-'
0x14000ea39  mov     [rsp+88h+BugCheckOnFailure], ebx
0x14000ea3d  mov     r9, rsi
0x14000ea40  call    WPP_SF_qd
0x14000ea45  test    ebx, ebx
0x14000ea47  js      loc_14000EB4C
0x14000ea4d  mov     rax, [rsp+88h+arg_18]
0x14000ea55  mov     r14, [rdi+8]
0x14000ea59  mov     r12d, [rdi+18h]
0x14000ea5d  mov     rax, [rax+28h]
0x14000ea61  mov     [rsp+88h+var_50], rax
0x14000ea66  mov     eax, [rdi+10h]
0x14000ea69  test    r14, r14
0x14000ea6c  jz      loc_14000EB17
0x14000ea72  mov     rbp, [rsp+88h+arg_18]
0x14000ea7a  mov     esi, eax
0x14000ea7c  test    r12d, r12d
0x14000ea7f  jz      loc_14000EB05
0x14000ea85  test    byte ptr [r14+0Ah], 5
0x14000ea8a  jz      short loc_14000EA92
0x14000ea8c  mov     rax, [r14+18h]
0x14000ea90  jmp     short loc_14000EABA
0x14000ea92  xor     r9d, r9d; RequestedAddress
0x14000ea95  mov     [rsp+88h+Priority], 40000000h; Priority
0x14000ea9d  xor     edx, edx; AccessMode
0x14000ea9f  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000eaa7  mov     rcx, r14; MemoryDescriptorList
0x14000eaaa  lea     r8d, [r9+1]; CacheType
0x14000eaae  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000eab5  nop     dword ptr [rax+rax+00h]
0x14000eaba  mov     r15, [rbp+28h]
0x14000eabe  mov     r13d, r12d
0x14000eac1  mov     edx, esi
0x14000eac3  add     rdx, rax; Src
0x14000eac6  mov     eax, [r14+28h]
0x14000eaca  sub     eax, esi
0x14000eacc  cmp     r12d, eax
0x14000eacf  cmovnb  r13d, eax
0x14000ead3  xor     esi, esi
0x14000ead5  test    r15, r15
0x14000ead8  jz      short loc_14000EADE
0x14000eada  mov     r15, [r15+40h]
0x14000eade  mov     r8d, r13d; Size
0x14000eae1  mov     rcx, r15; void *
0x14000eae4  call    memmove
0x14000eae9  mov     rcx, [rsp+88h+var_50]
0x14000eaee  lea     rax, [r15+r13]
0x14000eaf2  sub     r12d, r13d
0x14000eaf5  mov     [rcx+40h], rax
0x14000eaf9  mov     r14, [r14]
0x14000eafc  test    r14, r14
0x14000eaff  jnz     loc_14000EA7C
0x14000eb05  mov     rsi, [rsp+88h+arg_0]
0x14000eb0d  mov     rbp, [rsp+88h+var_58]
0x14000eb12  mov     r15, [rsp+88h+var_48]
0x14000eb17  mov     rdx, r15; ActivityId
0x14000eb1a  lea     rcx, ONCRPC_EVENT_PKT_RECEIVE_COMPLETION; EventDescriptor
0x14000eb21  call    LogOncrpcEvent
0x14000eb26  mov     rdx, [rdi+30h]
0x14000eb2a  lea     rcx, [rbp+13Ch]
0x14000eb31  call    OncRpcCopyAddress
0x14000eb36  mov     r8, rsi
0x14000eb39  xor     edx, edx
0x14000eb3b  mov     rcx, rbp
0x14000eb3e  call    OncRpcWiMgrProcessSrvWorkItem
0x14000eb43  lea     r14, WPP_GLOBAL_Control
0x14000eb4a  jmp     short loc_14000EB88
0x14000eb4c  test    rbp, rbp
0x14000eb4f  jz      short loc_14000EB88
0x14000eb51  test    ebx, ebx
0x14000eb53  jns     short loc_14000EB80
0x14000eb55  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb5c  cmp     rcx, r14
0x14000eb5f  jz      short loc_14000EB80
0x14000eb61  mov     eax, [rcx+2Ch]
0x14000eb64  test    al, 10h
0x14000eb66  jz      short loc_14000EB80
0x14000eb68  mov     rcx, [rcx+18h]
0x14000eb6c  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000eb73  mov     edx, 2Eh ; '.'
0x14000eb78  mov     r9d, ebx
0x14000eb7b  call    WPP_SF_d
0x14000eb80  mov     rcx, rbp
0x14000eb83  call    OncRpcWiMgrSrvWorkItemFree
0x14000eb88  mov     rdi, [rdi]
0x14000eb8b  test    rdi, rdi
0x14000eb8e  jnz     loc_14000E958
0x14000eb94  xor     eax, eax
0x14000eb96  mov     rbx, [rsp+88h+arg_8]
0x14000eb9e  add     rsp, 50h
0x14000eba2  pop     r15
0x14000eba4  pop     r14
0x14000eba6  pop     r13
0x14000eba8  pop     r12
0x14000ebaa  pop     rdi
0x14000ebab  pop     rsi
0x14000ebac  pop     rbp
0x14000ebad  retn
```
