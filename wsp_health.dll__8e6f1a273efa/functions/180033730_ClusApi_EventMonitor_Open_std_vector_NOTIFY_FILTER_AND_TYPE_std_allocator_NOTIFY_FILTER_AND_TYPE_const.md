# ClusApi::EventMonitor::Open(std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x180033730`
- end: `0x1800337fe`
- name: `?Open@EventMonitor@ClusApi@@UEAAJAEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@@Z`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002db94`
- `0x18002dbcc`
- `0x180033730`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337af`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180033789`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180033789`
- `CLUSAPI!GetNotifyEventHandle` at `0x1800337e8`
- `CLUSAPI!GetNotifyEventHandle` at `0x1800337e8`

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
0x180033730  push    rbx
0x180033732  push    rbp
0x180033733  push    rsi
0x180033734  push    rdi
0x180033735  push    r14
0x180033737  sub     rsp, 30h
0x18003373b  lea     r14, [rcx+18h]
0x18003373f  xor     esi, esi
0x180033741  mov     rax, [r14]
0x180033744  mov     rbp, rcx
0x180033747  inc     rax
0x18003374a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180033750  jnz     short loc_1800337CA
0x180033752  mov     rcx, [rcx+8]
0x180033756  mov     rdi, [rdx]
0x180033759  mov     rbx, [rdx+8]
0x18003375d  sub     rbx, rdi
0x180033760  mov     rax, [rcx]
0x180033763  sar     rbx, 4
0x180033767  mov     rax, [rax+188h]
0x18003376e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033773  mov     r9d, ebx
0x180033776  mov     [rsp+58h+var_38], 1
0x18003377f  mov     r8, rdi
0x180033782  mov     rdx, rax
0x180033785  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180033789  call    cs:__imp_CreateClusterNotifyPortV2
0x180033790  nop     dword ptr [rax+rax+00h]
0x180033795  mov     rcx, r14
0x180033798  mov     rbx, rax
0x18003379b  call    ?Close@?$AutoHandle@PEAU_HCHANGE@@H$1?CloseClusterNotifyPort@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCHANGE *,int,&CloseClusterNotifyPort(_HCHANGE *),0>::Close(void)
0x1800337a0  lea     rax, [rbx+1]
0x1800337a4  mov     [r14], rbx
0x1800337a7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800337ad  jnz     short loc_1800337D8
0x1800337af  call    cs:__imp_GetLastError
0x1800337b6  nop     dword ptr [rax+rax+00h]
0x1800337bb  mov     esi, eax
0x1800337bd  test    eax, eax
0x1800337bf  jle     short loc_1800337CA
0x1800337c1  movzx   esi, ax
0x1800337c4  or      esi, 80070000h
0x1800337ca  mov     eax, esi
0x1800337cc  add     rsp, 30h
0x1800337d0  pop     r14
0x1800337d2  pop     rdi
0x1800337d3  pop     rsi
0x1800337d4  pop     rbp
0x1800337d5  pop     rbx
0x1800337d6  retn
0x1800337d8  lea     rcx, [rbp+20h]
0x1800337dc  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),0>::Close(void)
0x1800337e1  mov     rcx, [r14]
0x1800337e4  lea     rdx, [rbp+20h]
0x1800337e8  call    cs:__imp_GetNotifyEventHandle
0x1800337ef  nop     dword ptr [rax+rax+00h]
0x1800337f4  test    eax, eax
0x1800337f6  jz      short loc_1800337CA
0x1800337f8  jg      short loc_1800337C1
0x1800337fa  mov     esi, eax
0x1800337fc  jmp     short loc_1800337CA
```
