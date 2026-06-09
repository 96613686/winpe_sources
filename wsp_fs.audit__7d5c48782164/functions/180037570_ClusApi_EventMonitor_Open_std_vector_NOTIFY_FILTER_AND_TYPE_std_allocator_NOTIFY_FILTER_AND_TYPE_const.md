# ClusApi::EventMonitor::Open(std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x180037570`
- end: `0x18003763e`
- name: `?Open@EventMonitor@ClusApi@@UEAAJAEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@@Z`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800319b4`
- `0x1800319ec`
- `0x180037570`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375ef`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800375c9`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800375c9`
- `CLUSAPI!GetNotifyEventHandle` at `0x180037628`
- `CLUSAPI!GetNotifyEventHandle` at `0x180037628`

## pseudocode

```c
__int64 __fastcall ClusApi::EventMonitor::Open(__int64 a1, __int64 *a2)
{
  __int64 *v2; // r14
  unsigned int v3; // esi
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 ClusterNotifyPortV2; // rbx
  signed int NotifyEventHandle; // eax

  v2 = (__int64 *)(a1 + 24);
  v3 = 0;
  if ( ((*(_QWORD *)(a1 + 24) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = *a2;
    v6 = (a2[1] - *a2) >> 4;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 392LL))(*(_QWORD *)(a1 + 8));
    ClusterNotifyPortV2 = CreateClusterNotifyPortV2(-1, v7, v5, (unsigned int)v6, 1);
    cxl::AutoHandle<_HCHANGE *,int,&int CloseClusterNotifyPort(_HCHANGE *),0>::Close(v2);
    *v2 = ClusterNotifyPortV2;
    if ( ((ClusterNotifyPortV2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      cxl::AutoHandle<void *,int,&int CloseHandle(void *),0>::Close(a1 + 32);
      NotifyEventHandle = GetNotifyEventHandle(*v2, a1 + 32);
      if ( !NotifyEventHandle )
        return v3;
      if ( NotifyEventHandle <= 0 )
        return (unsigned int)NotifyEventHandle;
      return (unsigned __int16)NotifyEventHandle | 0x80070000;
    }
    NotifyEventHandle = GetLastError();
    v3 = NotifyEventHandle;
    if ( NotifyEventHandle > 0 )
      return (unsigned __int16)NotifyEventHandle | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180037570  push    rbx
0x180037572  push    rbp
0x180037573  push    rsi
0x180037574  push    rdi
0x180037575  push    r14
0x180037577  sub     rsp, 30h
0x18003757b  lea     r14, [rcx+18h]
0x18003757f  xor     esi, esi
0x180037581  mov     rax, [r14]
0x180037584  mov     rbp, rcx
0x180037587  inc     rax
0x18003758a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180037590  jnz     short loc_18003760A
0x180037592  mov     rcx, [rcx+8]
0x180037596  mov     rdi, [rdx]
0x180037599  mov     rbx, [rdx+8]
0x18003759d  sub     rbx, rdi
0x1800375a0  mov     rax, [rcx]
0x1800375a3  sar     rbx, 4
0x1800375a7  mov     rax, [rax+188h]
0x1800375ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375b3  mov     r9d, ebx
0x1800375b6  mov     [rsp+58h+var_38], 1
0x1800375bf  mov     r8, rdi
0x1800375c2  mov     rdx, rax
0x1800375c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800375c9  call    cs:__imp_CreateClusterNotifyPortV2
0x1800375d0  nop     dword ptr [rax+rax+00h]
0x1800375d5  mov     rcx, r14
0x1800375d8  mov     rbx, rax
0x1800375db  call    ?Close@?$AutoHandle@PEAU_HCHANGE@@H$1?CloseClusterNotifyPort@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCHANGE *,int,&CloseClusterNotifyPort(_HCHANGE *),0>::Close(void)
0x1800375e0  lea     rax, [rbx+1]
0x1800375e4  mov     [r14], rbx
0x1800375e7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800375ed  jnz     short loc_180037618
0x1800375ef  call    cs:__imp_GetLastError
0x1800375f6  nop     dword ptr [rax+rax+00h]
0x1800375fb  mov     esi, eax
0x1800375fd  test    eax, eax
0x1800375ff  jle     short loc_18003760A
0x180037601  movzx   esi, ax
0x180037604  or      esi, 80070000h
0x18003760a  mov     eax, esi
0x18003760c  add     rsp, 30h
0x180037610  pop     r14
0x180037612  pop     rdi
0x180037613  pop     rsi
0x180037614  pop     rbp
0x180037615  pop     rbx
0x180037616  retn
0x180037618  lea     rcx, [rbp+20h]
0x18003761c  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),0>::Close(void)
0x180037621  mov     rcx, [r14]
0x180037624  lea     rdx, [rbp+20h]
0x180037628  call    cs:__imp_GetNotifyEventHandle
0x18003762f  nop     dword ptr [rax+rax+00h]
0x180037634  test    eax, eax
0x180037636  jz      short loc_18003760A
0x180037638  jg      short loc_180037601
0x18003763a  mov     esi, eax
0x18003763c  jmp     short loc_18003760A
```
