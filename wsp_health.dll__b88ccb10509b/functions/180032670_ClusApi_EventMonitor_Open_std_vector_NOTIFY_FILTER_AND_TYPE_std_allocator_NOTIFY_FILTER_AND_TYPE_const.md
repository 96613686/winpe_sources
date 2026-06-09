# ClusApi::EventMonitor::Open(std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x180032670`
- end: `0x18003272b`
- name: `?Open@EventMonitor@ClusApi@@UEAAJAEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002ccb4`
- `0x18002cce4`
- `0x180032670`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326e9`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800326c9`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800326c9`
- `CLUSAPI!GetNotifyEventHandle` at `0x18003271b`
- `CLUSAPI!GetNotifyEventHandle` at `0x18003271b`

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
0x180032670  push    rbx
0x180032672  push    rbp
0x180032673  push    rsi
0x180032674  push    rdi
0x180032675  push    r14
0x180032677  sub     rsp, 30h
0x18003267b  lea     r14, [rcx+18h]
0x18003267f  xor     esi, esi
0x180032681  mov     rax, [r14]
0x180032684  mov     rbp, rcx
0x180032687  inc     rax
0x18003268a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180032690  jnz     short loc_1800326FE
0x180032692  mov     rcx, [rcx+8]
0x180032696  mov     rdi, [rdx]
0x180032699  mov     rbx, [rdx+8]
0x18003269d  sub     rbx, rdi
0x1800326a0  mov     rax, [rcx]
0x1800326a3  sar     rbx, 4
0x1800326a7  mov     rax, [rax+188h]
0x1800326ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326b3  mov     r9d, ebx
0x1800326b6  mov     [rsp+58h+var_38], 1
0x1800326bf  mov     r8, rdi
0x1800326c2  mov     rdx, rax
0x1800326c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800326c9  call    cs:__imp_CreateClusterNotifyPortV2
0x1800326cf  mov     rcx, r14
0x1800326d2  mov     rbx, rax
0x1800326d5  call    ?Close@?$AutoHandle@PEAU_HCHANGE@@H$1?CloseClusterNotifyPort@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCHANGE *,int,&CloseClusterNotifyPort(_HCHANGE *),0>::Close(void)
0x1800326da  lea     rax, [rbx+1]
0x1800326de  mov     [r14], rbx
0x1800326e1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800326e7  jnz     short loc_18003270B
0x1800326e9  call    cs:__imp_GetLastError
0x1800326ef  mov     esi, eax
0x1800326f1  test    eax, eax
0x1800326f3  jle     short loc_1800326FE
0x1800326f5  movzx   esi, ax
0x1800326f8  or      esi, 80070000h
0x1800326fe  mov     eax, esi
0x180032700  add     rsp, 30h
0x180032704  pop     r14
0x180032706  pop     rdi
0x180032707  pop     rsi
0x180032708  pop     rbp
0x180032709  pop     rbx
0x18003270a  retn
0x18003270b  lea     rcx, [rbp+20h]
0x18003270f  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),0>::Close(void)
0x180032714  mov     rcx, [r14]
0x180032717  lea     rdx, [rbp+20h]
0x18003271b  call    cs:__imp_GetNotifyEventHandle
0x180032721  test    eax, eax
0x180032723  jz      short loc_1800326FE
0x180032725  jg      short loc_1800326F5
0x180032727  mov     esi, eax
0x180032729  jmp     short loc_1800326FE
```
