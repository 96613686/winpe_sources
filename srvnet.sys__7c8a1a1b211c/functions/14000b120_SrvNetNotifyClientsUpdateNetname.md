# SrvNetNotifyClientsUpdateNetname

- ea: `0x14000b120`
- end: `0x14000b291`
- name: `SrvNetNotifyClientsUpdateNetname`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000ae00`
- `0x140025740`
- `0x140046d00`
- `0x1400475a0`
- `0x1400527c0`
- `0x140053100`
- `0x1400537b0`
- `0x140053940`

## callees

- `0x140007c60`
- `0x14000b120`
- `0x140015790`

## import_xrefs

- `ntoskrnl!IoSizeofWorkItem` at `0x14000b137`
- `ntoskrnl!IoSizeofWorkItem` at `0x14000b137`
- `ntoskrnl!IoInitializeWorkItem` at `0x14000b1dd`
- `ntoskrnl!IoInitializeWorkItem` at `0x14000b1dd`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000b1fc`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000b1fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b27a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b27a`

## pseudocode

```c
void SrvNetNotifyClientsUpdateNetname()
{
  ULONG v0; // eax
  struct _IO_WORKITEM *PoolWithTag; // rbx
  signed int v2; // r8d
  signed __int32 v3; // ecx
  int v4; // eax
  signed __int32 v5; // edx
  int v6; // eax

  if ( (SrvNetNetNameUpdateWorkerState & 1) == 0 )
  {
    v0 = IoSizeofWorkItem();
    PoolWithTag = (struct _IO_WORKITEM *)SrvNetAllocatePoolWithTag(66, v0, 1717719884);
    if ( PoolWithTag )
    {
      _m_prefetchw(&SrvNetNetNameUpdateWorkerState);
      if ( _InterlockedOr(&SrvNetNetNameUpdateWorkerState, 1u) )
      {
        v2 = -*((_DWORD *)PoolWithTag - 4);
        if ( (*((_DWORD *)PoolWithTag - 3) & 0x100) != 0 )
        {
          v5 = v2 + _InterlockedExchangeAdd((volatile signed __int32 *)&xmmword_1400365F0, v2);
          if ( v2 > 0 )
          {
            do
              v6 = DWORD2(xmmword_1400365F0);
            while ( v5 > SDWORD2(xmmword_1400365F0)
                 && v6 != _InterlockedCompareExchange((_DWORD *)&xmmword_1400365F0 + 2, v5, SDWORD2(xmmword_1400365F0)) );
          }
        }
        else
        {
          v3 = v2 + _InterlockedExchangeAdd(&dword_1400365E4, v2);
          if ( v2 > 0 )
          {
            do
              v4 = dword_1400365EC;
            while ( v3 > dword_1400365EC && v4 != _InterlockedCompareExchange(&dword_1400365EC, v3, dword_1400365EC) );
          }
        }
        ExFreePoolWithTag((char *)PoolWithTag - 16, 0);
      }
      else
      {
        IoInitializeWorkItem(SrvNetDeviceObject, PoolWithTag);
        IoQueueWorkItemEx(PoolWithTag, SrvNetUpdateNetNameWorkerRoutine, DelayedWorkQueue, 0);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14000b120  sub     rsp, 28h
0x14000b124  mov     eax, cs:SrvNetNetNameUpdateWorkerState
0x14000b12a  test    al, 1
0x14000b12c  jnz     loc_14000B28B
0x14000b132  mov     [rsp+28h+var_8], rbx
0x14000b137  call    cs:__imp_IoSizeofWorkItem
0x14000b13e  nop     dword ptr [rax+rax+00h]
0x14000b143  mov     edx, eax
0x14000b145  mov     ecx, 42h ; 'B'
0x14000b14a  mov     r8d, 6662534Ch
0x14000b150  call    SrvNetAllocatePoolWithTag
0x14000b155  mov     rbx, rax
0x14000b158  test    rax, rax
0x14000b15b  jnz     short loc_14000B1AB
0x14000b15d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b164  lea     rax, WPP_GLOBAL_Control
0x14000b16b  cmp     rcx, rax
0x14000b16e  jz      loc_14000B286
0x14000b174  test    dword ptr [rcx+2Ch], 2000h
0x14000b17b  jz      loc_14000B286
0x14000b181  cmp     byte ptr [rcx+29h], 1
0x14000b185  jb      loc_14000B286
0x14000b18b  mov     rcx, [rcx+18h]
0x14000b18f  lea     r8, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids
0x14000b196  mov     edx, 24h ; '$'
0x14000b19b  call    WPP_SF_
0x14000b1a0  mov     rbx, [rsp+28h+var_8]
0x14000b1a5  add     rsp, 28h
0x14000b1a9  retn
0x14000b1ab  prefetchw byte ptr cs:SrvNetNetNameUpdateWorkerState
0x14000b1b2  mov     eax, cs:SrvNetNetNameUpdateWorkerState
0x14000b1b8  nop     dword ptr [rax+rax+00000000h]
0x14000b1c0  mov     ecx, eax
0x14000b1c2  or      ecx, 1
0x14000b1c5  lock cmpxchg cs:SrvNetNetNameUpdateWorkerState, ecx
0x14000b1cd  jnz     short loc_14000B1C0
0x14000b1cf  test    eax, eax
0x14000b1d1  jnz     short loc_14000B213
0x14000b1d3  mov     rcx, cs:SrvNetDeviceObject; IoObject
0x14000b1da  mov     rdx, rbx; IoWorkItem
0x14000b1dd  call    cs:__imp_IoInitializeWorkItem
0x14000b1e4  nop     dword ptr [rax+rax+00h]
0x14000b1e9  xor     r9d, r9d; Context
0x14000b1ec  lea     rdx, SrvNetUpdateNetNameWorkerRoutine; WorkerRoutine
0x14000b1f3  mov     r8d, 1; QueueType
0x14000b1f9  mov     rcx, rbx; IoWorkItem
0x14000b1fc  call    cs:__imp_IoQueueWorkItemEx
0x14000b203  nop     dword ptr [rax+rax+00h]
0x14000b208  mov     rbx, [rsp+28h+var_8]
0x14000b20d  add     rsp, 28h
0x14000b211  retn
0x14000b213  mov     r8d, [rbx-10h]
0x14000b217  neg     r8d
0x14000b21a  test    dword ptr [rbx-0Ch], 100h
0x14000b221  jnz     short loc_14000B24C
0x14000b223  mov     ecx, r8d
0x14000b226  lock xadd cs:dword_1400365E4, ecx
0x14000b22e  add     ecx, r8d
0x14000b231  test    r8d, r8d
0x14000b234  jle     short loc_14000B274
0x14000b236  mov     eax, cs:dword_1400365EC
0x14000b23c  cmp     ecx, eax
0x14000b23e  jle     short loc_14000B274
0x14000b240  lock cmpxchg cs:dword_1400365EC, ecx
0x14000b248  jnz     short loc_14000B236
0x14000b24a  jmp     short loc_14000B274
0x14000b24c  mov     edx, r8d
0x14000b24f  lock xadd dword ptr cs:xmmword_1400365F0, edx
0x14000b257  add     edx, r8d
0x14000b25a  test    r8d, r8d
0x14000b25d  jle     short loc_14000B274
0x14000b25f  nop
0x14000b260  mov     eax, dword ptr cs:xmmword_1400365F0+8
0x14000b266  cmp     edx, eax
0x14000b268  jle     short loc_14000B274
0x14000b26a  lock cmpxchg dword ptr cs:xmmword_1400365F0+8, edx
0x14000b272  jnz     short loc_14000B260
0x14000b274  xor     edx, edx; Tag
0x14000b276  lea     rcx, [rbx-10h]; P
0x14000b27a  call    cs:__imp_ExFreePoolWithTag
0x14000b281  nop     dword ptr [rax+rax+00h]
0x14000b286  mov     rbx, [rsp+28h+var_8]
0x14000b28b  add     rsp, 28h
0x14000b28f  retn
```
