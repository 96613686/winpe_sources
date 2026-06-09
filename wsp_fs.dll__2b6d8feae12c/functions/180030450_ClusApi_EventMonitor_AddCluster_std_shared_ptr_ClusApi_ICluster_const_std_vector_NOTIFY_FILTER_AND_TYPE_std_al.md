# ClusApi::EventMonitor::AddCluster(std::shared_ptr<ClusApi::ICluster> const &,std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x180030450`
- end: `0x1800304e1`
- name: `?AddCluster@EventMonitor@ClusApi@@UEAAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@AEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@4@@Z`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002fc20`
- `0x180030450`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304ae`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800304a3`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x1800304a3`

## pseudocode

```c
signed int __fastcall ClusApi::EventMonitor::AddCluster(__int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  signed int result; // eax

  if ( (unsigned __int64)(*(_QWORD *)(a1 + 24) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    return -2147019873;
  v5 = *a3;
  v6 = (a3[1] - *a3) >> 4;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 392LL))(*a2);
  if ( CreateClusterNotifyPortV2(*(_QWORD *)(a1 + 24), v7, v5, (unsigned int)v6, 1) )
  {
    std::vector<std::shared_ptr<ClusApi::ICluster>>::emplace_back<std::shared_ptr<ClusApi::ICluster> const &>(
      a1 + 40,
      a2);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180030450  push    rbx
0x180030452  push    rsi
0x180030453  push    rdi
0x180030454  push    r14
0x180030456  sub     rsp, 38h
0x18003045a  mov     rax, [rcx+18h]
0x18003045e  mov     r14, rdx
0x180030461  dec     rax
0x180030464  mov     rsi, rcx
0x180030467  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003046b  ja      short loc_1800304D2
0x18003046d  mov     rcx, [rdx]
0x180030470  mov     rdi, [r8]
0x180030473  mov     rbx, [r8+8]
0x180030477  sub     rbx, rdi
0x18003047a  mov     rax, [rcx]
0x18003047d  sar     rbx, 4
0x180030481  mov     rax, [rax+188h]
0x180030488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003048d  mov     rcx, [rsi+18h]
0x180030491  mov     r9d, ebx
0x180030494  mov     r8, rdi
0x180030497  mov     [rsp+58h+var_38], 1
0x1800304a0  mov     rdx, rax
0x1800304a3  call    cs:__imp_CreateClusterNotifyPortV2
0x1800304a9  test    rax, rax
0x1800304ac  jnz     short loc_1800304C2
0x1800304ae  call    cs:__imp_GetLastError
0x1800304b4  test    eax, eax
0x1800304b6  jle     short loc_1800304D7
0x1800304b8  movzx   eax, ax
0x1800304bb  or      eax, 80070000h
0x1800304c0  jmp     short loc_1800304D7
0x1800304c2  lea     rcx, [rsi+28h]
0x1800304c6  mov     rdx, r14
0x1800304c9  call    ??$emplace_back@AEBV?$shared_ptr@UICluster@ClusApi@@@std@@@?$vector@V?$shared_ptr@UICluster@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UICluster@ClusApi@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UICluster@ClusApi@@@1@AEBV21@@Z; std::vector<std::shared_ptr<ClusApi::ICluster>>::emplace_back<std::shared_ptr<ClusApi::ICluster> const &>(std::shared_ptr<ClusApi::ICluster> const &)
0x1800304ce  xor     eax, eax
0x1800304d0  jmp     short loc_1800304D7
0x1800304d2  mov     eax, 8007139Fh
0x1800304d7  add     rsp, 38h
0x1800304db  pop     r14
0x1800304dd  pop     rdi
0x1800304de  pop     rsi
0x1800304df  pop     rbx
0x1800304e0  retn
```
