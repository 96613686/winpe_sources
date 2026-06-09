# SrvNetUpdateIPAddressList

- ea: `0x14000d560`
- end: `0x14000d6d1`
- name: `SrvNetUpdateIPAddressList`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140010d94`
- `0x14001111c`
- `0x140053100`
- `0x140053940`

## callees

- `0x140007c60`
- `0x14000d560`
- `0x140015790`

## import_xrefs

- `ntoskrnl!IoSizeofWorkItem` at `0x14000d577`
- `ntoskrnl!IoSizeofWorkItem` at `0x14000d577`
- `ntoskrnl!IoInitializeWorkItem` at `0x14000d61d`
- `ntoskrnl!IoInitializeWorkItem` at `0x14000d61d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000d63c`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14000d63c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d6ba`

## pseudocode

```c
void SrvNetUpdateIPAddressList()
{
  ULONG v0; // eax
  struct _IO_WORKITEM *PoolWithTag; // rbx
  signed int v2; // r8d
  signed __int32 v3; // ecx
  int v4; // eax
  signed __int32 v5; // edx
  int v6; // eax

  if ( (SrvNetIpAddressUpdateWorkerState & 1) == 0 )
  {
    v0 = IoSizeofWorkItem();
    PoolWithTag = (struct _IO_WORKITEM *)SrvNetAllocatePoolWithTag(66, v0, 1717719884);
    if ( PoolWithTag )
    {
      _m_prefetchw(&SrvNetIpAddressUpdateWorkerState);
      if ( _InterlockedOr(&SrvNetIpAddressUpdateWorkerState, 1u) )
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
        IoQueueWorkItemEx(
          PoolWithTag,
          (PIO_WORKITEM_ROUTINE_EX)SrvNetUpdateIPAddressListWorkerRoutine,
          DelayedWorkQueue,
          0);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14000d560  sub     rsp, 28h
0x14000d564  mov     eax, cs:SrvNetIpAddressUpdateWorkerState
0x14000d56a  test    al, 1
0x14000d56c  jnz     loc_14000D6CB
0x14000d572  mov     [rsp+28h+var_8], rbx
0x14000d577  call    cs:__imp_IoSizeofWorkItem
0x14000d57e  nop     dword ptr [rax+rax+00h]
0x14000d583  mov     edx, eax
0x14000d585  mov     ecx, 42h ; 'B'
0x14000d58a  mov     r8d, 6662534Ch
0x14000d590  call    SrvNetAllocatePoolWithTag
0x14000d595  mov     rbx, rax
0x14000d598  test    rax, rax
0x14000d59b  jnz     short loc_14000D5EB
0x14000d59d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d5a4  lea     rax, WPP_GLOBAL_Control
0x14000d5ab  cmp     rcx, rax
0x14000d5ae  jz      loc_14000D6C6
0x14000d5b4  test    dword ptr [rcx+2Ch], 2000h
0x14000d5bb  jz      loc_14000D6C6
0x14000d5c1  cmp     byte ptr [rcx+29h], 1
0x14000d5c5  jb      loc_14000D6C6
0x14000d5cb  mov     rcx, [rcx+18h]
0x14000d5cf  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x14000d5d6  mov     edx, 3Ah ; ':'
0x14000d5db  call    WPP_SF_
0x14000d5e0  mov     rbx, [rsp+28h+var_8]
0x14000d5e5  add     rsp, 28h
0x14000d5e9  retn
0x14000d5eb  prefetchw byte ptr cs:SrvNetIpAddressUpdateWorkerState
0x14000d5f2  mov     eax, cs:SrvNetIpAddressUpdateWorkerState
0x14000d5f8  nop     dword ptr [rax+rax+00000000h]
0x14000d600  mov     ecx, eax
0x14000d602  or      ecx, 1
0x14000d605  lock cmpxchg cs:SrvNetIpAddressUpdateWorkerState, ecx
0x14000d60d  jnz     short loc_14000D600
0x14000d60f  test    eax, eax
0x14000d611  jnz     short loc_14000D653
0x14000d613  mov     rcx, cs:SrvNetDeviceObject; IoObject
0x14000d61a  mov     rdx, rbx; IoWorkItem
0x14000d61d  call    cs:__imp_IoInitializeWorkItem
0x14000d624  nop     dword ptr [rax+rax+00h]
0x14000d629  xor     r9d, r9d; Context
0x14000d62c  lea     rdx, SrvNetUpdateIPAddressListWorkerRoutine; WorkerRoutine
0x14000d633  mov     r8d, 1; QueueType
0x14000d639  mov     rcx, rbx; IoWorkItem
0x14000d63c  call    cs:__imp_IoQueueWorkItemEx
0x14000d643  nop     dword ptr [rax+rax+00h]
0x14000d648  mov     rbx, [rsp+28h+var_8]
0x14000d64d  add     rsp, 28h
0x14000d651  retn
0x14000d653  mov     r8d, [rbx-10h]
0x14000d657  neg     r8d
0x14000d65a  test    dword ptr [rbx-0Ch], 100h
0x14000d661  jnz     short loc_14000D68C
0x14000d663  mov     ecx, r8d
0x14000d666  lock xadd cs:dword_1400365E4, ecx
0x14000d66e  add     ecx, r8d
0x14000d671  test    r8d, r8d
0x14000d674  jle     short loc_14000D6B4
0x14000d676  mov     eax, cs:dword_1400365EC
0x14000d67c  cmp     ecx, eax
0x14000d67e  jle     short loc_14000D6B4
0x14000d680  lock cmpxchg cs:dword_1400365EC, ecx
0x14000d688  jnz     short loc_14000D676
0x14000d68a  jmp     short loc_14000D6B4
0x14000d68c  mov     edx, r8d
0x14000d68f  lock xadd dword ptr cs:xmmword_1400365F0, edx
0x14000d697  add     edx, r8d
0x14000d69a  test    r8d, r8d
0x14000d69d  jle     short loc_14000D6B4
0x14000d69f  nop
0x14000d6a0  mov     eax, dword ptr cs:xmmword_1400365F0+8
0x14000d6a6  cmp     edx, eax
0x14000d6a8  jle     short loc_14000D6B4
0x14000d6aa  lock cmpxchg dword ptr cs:xmmword_1400365F0+8, edx
0x14000d6b2  jnz     short loc_14000D6A0
0x14000d6b4  xor     edx, edx; Tag
0x14000d6b6  lea     rcx, [rbx-10h]; P
0x14000d6ba  call    cs:__imp_ExFreePoolWithTag
0x14000d6c1  nop     dword ptr [rax+rax+00h]
0x14000d6c6  mov     rbx, [rsp+28h+var_8]
0x14000d6cb  add     rsp, 28h
0x14000d6cf  retn
```
