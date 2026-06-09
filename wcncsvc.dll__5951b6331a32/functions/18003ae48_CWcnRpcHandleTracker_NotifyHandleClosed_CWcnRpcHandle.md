# CWcnRpcHandleTracker::NotifyHandleClosed(CWcnRpcHandle *)

- ea: `0x18003ae48`
- end: `0x18003af36`
- name: `?NotifyHandleClosed@CWcnRpcHandleTracker@@QEAAXPEAVCWcnRpcHandle@@@Z`
- size: `238`
- prototype: `void __fastcall(CWcnRpcHandleTracker *__hidden this, struct CWcnRpcHandle *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003bdb0`

## callees

- `0x18003ad10`
- `0x18003ae48`
- `0x18003afc8`
- `0x1800504cc`
- `0x180056dcf`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ae6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aeaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aeaa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003af20`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003af20`

## pseudocode

```c
void __fastcall CWcnRpcHandleTracker::NotifyHandleClosed(CWcnRpcHandleTracker *this, struct CWcnRpcHandle *a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rcx
  struct _TP_TIMER *v9; // rcx
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  struct CWcnRpcHandleTracker::tagPER_SESSION_DATA *v11; // [rsp+48h] [rbp+10h] BYREF

  v10 = *((_DWORD *)a2 + 6);
  v2 = v10;
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (int)CWcnRpcHandleTracker::GetPerSessionData(this, v2, &v11) >= 0 && (*(_DWORD *)v11)-- == 1 )
    std::_Tree<std::_Tmap_traits<unsigned long,CWcnRpcHandleTracker::tagPER_SESSION_DATA,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CWcnRpcHandleTracker::tagPER_SESSION_DATA>>,0>>::erase(
      *((_QWORD *)this + 7),
      &v10);
  v5 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !v5 )
  {
    v6 = _RTDynamicCast_0(
           *(_QWORD *)(*((_QWORD *)g_pWcnService + 7) + 48LL),
           0,
           &IWcnTransport `RTTI Type Descriptor',
           &CWcnEapTransport `RTTI Type Descriptor',
           0);
    v7 = (_QWORD *)v6;
    if ( v6 )
    {
      v8 = *(void **)(v6 + 168);
      if ( v8 )
      {
        WcnWlanCloseHandle(v8);
        v7[21] = 0;
      }
      v9 = (struct _TP_TIMER *)v7[22];
      v7[34] = 0;
      if ( v9 )
        SetThreadpoolTimer(v9, 0, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x18003ae48  mov     rax, rsp
0x18003ae4b  mov     [rax+18h], rbx
0x18003ae4f  mov     [rax+20h], rsi
0x18003ae53  push    rdi
0x18003ae54  sub     rsp, 30h
0x18003ae58  mov     ebx, [rdx+18h]
0x18003ae5b  mov     rdi, rcx
0x18003ae5e  add     rcx, 10h; lpCriticalSection
0x18003ae62  mov     [rax+8], ebx
0x18003ae65  mov     qword ptr [rax+10h], 0
0x18003ae6d  call    cs:__imp_EnterCriticalSection
0x18003ae73  lea     r8, [rsp+38h+arg_8]; struct CWcnRpcHandleTracker::tagPER_SESSION_DATA **
0x18003ae78  mov     edx, ebx; unsigned int
0x18003ae7a  mov     rcx, rdi; this
0x18003ae7d  call    ?GetPerSessionData@CWcnRpcHandleTracker@@AEAAJKPEAPEAUtagPER_SESSION_DATA@1@@Z; CWcnRpcHandleTracker::GetPerSessionData(ulong,CWcnRpcHandleTracker::tagPER_SESSION_DATA * *)
0x18003ae82  test    eax, eax
0x18003ae84  js      short loc_18003AE9E
0x18003ae86  mov     rax, [rsp+38h+arg_8]
0x18003ae8b  add     dword ptr [rax], 0FFFFFFFFh
0x18003ae8e  jnz     short loc_18003AE9E
0x18003ae90  mov     rcx, [rdi+38h]
0x18003ae94  lea     rdx, [rsp+38h+arg_0]
0x18003ae99  call    ?erase@?$_Tree@V?$_Tmap_traits@KUtagPER_SESSION_DATA@CWcnRpcHandleTracker@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUtagPER_SESSION_DATA@CWcnRpcHandleTracker@@@std@@@4@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CWcnRpcHandleTracker::tagPER_SESSION_DATA,std::less<ulong>,std::allocator<std::pair<ulong const,CWcnRpcHandleTracker::tagPER_SESSION_DATA>>,0>>::erase(ulong const &)
0x18003ae9e  mov     rax, [rdi+38h]
0x18003aea2  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003aea6  mov     rbx, [rax+8]
0x18003aeaa  call    cs:__imp_LeaveCriticalSection
0x18003aeb0  test    rbx, rbx
0x18003aeb3  jnz     short loc_18003AF26
0x18003aeb5  mov     rax, cs:?g_pWcnService@@3PEAVCWcnService@@EA; CWcnService * g_pWcnService
0x18003aebc  lea     r9, ??_R0?AVCWcnEapTransport@@@8; CWcnEapTransport `RTTI Type Descriptor'
0x18003aec3  lea     r8, ??_R0?AVIWcnTransport@@@8; IWcnTransport `RTTI Type Descriptor'
0x18003aeca  mov     [rsp+38h+var_18], ebx
0x18003aece  xor     edx, edx
0x18003aed0  mov     rcx, [rax+38h]
0x18003aed4  mov     rcx, [rcx+30h]
0x18003aed8  call    __RTDynamicCast_0
0x18003aedd  mov     rbx, rax
0x18003aee0  test    rax, rax
0x18003aee3  jz      short loc_18003AF26
0x18003aee5  mov     rcx, [rax+0A8h]; hClientHandle
0x18003aeec  test    rcx, rcx
0x18003aeef  jz      short loc_18003AF01
0x18003aef1  call    ?WcnWlanCloseHandle@@YAJPEAX@Z; WcnWlanCloseHandle(void *)
0x18003aef6  mov     qword ptr [rbx+0A8h], 0
0x18003af01  mov     rcx, [rbx+0B0h]; pti
0x18003af08  mov     qword ptr [rbx+110h], 0
0x18003af13  test    rcx, rcx
0x18003af16  jz      short loc_18003AF26
0x18003af18  xor     r9d, r9d; msWindowLength
0x18003af1b  xor     r8d, r8d; msPeriod
0x18003af1e  xor     edx, edx; pftDueTime
0x18003af20  call    cs:__imp_SetThreadpoolTimer
0x18003af26  mov     rbx, [rsp+38h+arg_10]
0x18003af2b  mov     rsi, [rsp+38h+arg_18]
0x18003af30  add     rsp, 30h
0x18003af34  pop     rdi
0x18003af35  retn
```
