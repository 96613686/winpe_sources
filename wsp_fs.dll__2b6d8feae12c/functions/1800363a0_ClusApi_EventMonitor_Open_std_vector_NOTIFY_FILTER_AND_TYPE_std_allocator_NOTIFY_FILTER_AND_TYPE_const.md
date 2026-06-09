# ClusApi::EventMonitor::Open(std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x1800363a0`
- end: `0x18003645b`
- name: `?Open@EventMonitor@ClusApi@@UEAAJAEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800309c4`
- `0x1800309f4`
- `0x1800363a0`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036419`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800363f9`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800363f9`
- `CLUSAPI!GetNotifyEventHandle` at `0x18003644b`
- `CLUSAPI!GetNotifyEventHandle` at `0x18003644b`

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
0x1800363a0  push    rbx
0x1800363a2  push    rbp
0x1800363a3  push    rsi
0x1800363a4  push    rdi
0x1800363a5  push    r14
0x1800363a7  sub     rsp, 30h
0x1800363ab  lea     r14, [rcx+18h]
0x1800363af  xor     esi, esi
0x1800363b1  mov     rax, [r14]
0x1800363b4  mov     rbp, rcx
0x1800363b7  inc     rax
0x1800363ba  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800363c0  jnz     short loc_18003642E
0x1800363c2  mov     rcx, [rcx+8]
0x1800363c6  mov     rdi, [rdx]
0x1800363c9  mov     rbx, [rdx+8]
0x1800363cd  sub     rbx, rdi
0x1800363d0  mov     rax, [rcx]
0x1800363d3  sar     rbx, 4
0x1800363d7  mov     rax, [rax+188h]
0x1800363de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363e3  mov     r9d, ebx
0x1800363e6  mov     [rsp+58h+var_38], 1
0x1800363ef  mov     r8, rdi
0x1800363f2  mov     rdx, rax
0x1800363f5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800363f9  call    cs:__imp_CreateClusterNotifyPortV2
0x1800363ff  mov     rcx, r14
0x180036402  mov     rbx, rax
0x180036405  call    ?Close@?$AutoHandle@PEAU_HCHANGE@@H$1?CloseClusterNotifyPort@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCHANGE *,int,&CloseClusterNotifyPort(_HCHANGE *),0>::Close(void)
0x18003640a  lea     rax, [rbx+1]
0x18003640e  mov     [r14], rbx
0x180036411  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036417  jnz     short loc_18003643B
0x180036419  call    cs:__imp_GetLastError
0x18003641f  mov     esi, eax
0x180036421  test    eax, eax
0x180036423  jle     short loc_18003642E
0x180036425  movzx   esi, ax
0x180036428  or      esi, 80070000h
0x18003642e  mov     eax, esi
0x180036430  add     rsp, 30h
0x180036434  pop     r14
0x180036436  pop     rdi
0x180036437  pop     rsi
0x180036438  pop     rbp
0x180036439  pop     rbx
0x18003643a  retn
0x18003643b  lea     rcx, [rbp+20h]
0x18003643f  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),0>::Close(void)
0x180036444  mov     rcx, [r14]
0x180036447  lea     rdx, [rbp+20h]
0x18003644b  call    cs:__imp_GetNotifyEventHandle
0x180036451  test    eax, eax
0x180036453  jz      short loc_18003642E
0x180036455  jg      short loc_180036425
0x180036457  mov     esi, eax
0x180036459  jmp     short loc_18003642E
```
