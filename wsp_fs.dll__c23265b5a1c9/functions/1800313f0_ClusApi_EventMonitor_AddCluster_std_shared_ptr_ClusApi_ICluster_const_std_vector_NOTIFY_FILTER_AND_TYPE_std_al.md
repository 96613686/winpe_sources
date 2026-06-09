# ClusApi::EventMonitor::AddCluster(std::shared_ptr<ClusApi::ICluster> const &,std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x1800313f0`
- end: `0x18003148e`
- name: `?AddCluster@EventMonitor@ClusApi@@UEAAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@AEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@4@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180030b9c`
- `0x1800313f0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031454`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180031443`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x180031443`

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
0x1800313f0  push    rbx
0x1800313f2  push    rsi
0x1800313f3  push    rdi
0x1800313f4  push    r14
0x1800313f6  sub     rsp, 38h
0x1800313fa  mov     rax, [rcx+18h]
0x1800313fe  mov     r14, rdx
0x180031401  dec     rax
0x180031404  mov     rsi, rcx
0x180031407  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003140b  ja      short loc_18003147E
0x18003140d  mov     rcx, [rdx]
0x180031410  mov     rdi, [r8]
0x180031413  mov     rbx, [r8+8]
0x180031417  sub     rbx, rdi
0x18003141a  mov     rax, [rcx]
0x18003141d  sar     rbx, 4
0x180031421  mov     rax, [rax+188h]
0x180031428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003142d  mov     rcx, [rsi+18h]
0x180031431  mov     r9d, ebx
0x180031434  mov     r8, rdi
0x180031437  mov     [rsp+58h+var_38], 1
0x180031440  mov     rdx, rax
0x180031443  call    cs:__imp_CreateClusterNotifyPortV2
0x18003144a  nop     dword ptr [rax+rax+00h]
0x18003144f  test    rax, rax
0x180031452  jnz     short loc_18003146E
0x180031454  call    cs:__imp_GetLastError
0x18003145b  nop     dword ptr [rax+rax+00h]
0x180031460  test    eax, eax
0x180031462  jle     short loc_180031483
0x180031464  movzx   eax, ax
0x180031467  or      eax, 80070000h
0x18003146c  jmp     short loc_180031483
0x18003146e  lea     rcx, [rsi+28h]
0x180031472  mov     rdx, r14
0x180031475  call    ??$emplace_back@AEBV?$shared_ptr@UICluster@ClusApi@@@std@@@?$vector@V?$shared_ptr@UICluster@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UICluster@ClusApi@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UICluster@ClusApi@@@1@AEBV21@@Z; std::vector<std::shared_ptr<ClusApi::ICluster>>::emplace_back<std::shared_ptr<ClusApi::ICluster> const &>(std::shared_ptr<ClusApi::ICluster> const &)
0x18003147a  xor     eax, eax
0x18003147c  jmp     short loc_180031483
0x18003147e  mov     eax, 8007139Fh
0x180031483  add     rsp, 38h
0x180031487  pop     r14
0x180031489  pop     rdi
0x18003148a  pop     rsi
0x18003148b  pop     rbx
0x18003148c  retn
```
