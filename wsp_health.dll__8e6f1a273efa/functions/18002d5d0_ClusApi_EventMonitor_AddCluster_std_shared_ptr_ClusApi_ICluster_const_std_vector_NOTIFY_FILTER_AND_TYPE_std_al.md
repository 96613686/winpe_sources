# ClusApi::EventMonitor::AddCluster(std::shared_ptr<ClusApi::ICluster> const &,std::vector<_NOTIFY_FILTER_AND_TYPE,std::allocator<_NOTIFY_FILTER_AND_TYPE>> const &)

- ea: `0x18002d5d0`
- end: `0x18002d66e`
- name: `?AddCluster@EventMonitor@ClusApi@@UEAAJAEBV?$shared_ptr@UICluster@ClusApi@@@std@@AEBV?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@4@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002cd88`
- `0x18002d5d0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d634`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x18002d623`
- `CLUSAPI!CreateClusterNotifyPortV2` at `0x18002d623`

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
0x18002d5d0  push    rbx
0x18002d5d2  push    rsi
0x18002d5d3  push    rdi
0x18002d5d4  push    r14
0x18002d5d6  sub     rsp, 38h
0x18002d5da  mov     rax, [rcx+18h]
0x18002d5de  mov     r14, rdx
0x18002d5e1  dec     rax
0x18002d5e4  mov     rsi, rcx
0x18002d5e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d5eb  ja      short loc_18002D65E
0x18002d5ed  mov     rcx, [rdx]
0x18002d5f0  mov     rdi, [r8]
0x18002d5f3  mov     rbx, [r8+8]
0x18002d5f7  sub     rbx, rdi
0x18002d5fa  mov     rax, [rcx]
0x18002d5fd  sar     rbx, 4
0x18002d601  mov     rax, [rax+188h]
0x18002d608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d60d  mov     rcx, [rsi+18h]
0x18002d611  mov     r9d, ebx
0x18002d614  mov     r8, rdi
0x18002d617  mov     [rsp+58h+var_38], 1
0x18002d620  mov     rdx, rax
0x18002d623  call    cs:__imp_CreateClusterNotifyPortV2
0x18002d62a  nop     dword ptr [rax+rax+00h]
0x18002d62f  test    rax, rax
0x18002d632  jnz     short loc_18002D64E
0x18002d634  call    cs:__imp_GetLastError
0x18002d63b  nop     dword ptr [rax+rax+00h]
0x18002d640  test    eax, eax
0x18002d642  jle     short loc_18002D663
0x18002d644  movzx   eax, ax
0x18002d647  or      eax, 80070000h
0x18002d64c  jmp     short loc_18002D663
0x18002d64e  lea     rcx, [rsi+28h]
0x18002d652  mov     rdx, r14
0x18002d655  call    ??$emplace_back@AEBV?$shared_ptr@UICluster@ClusApi@@@std@@@?$vector@V?$shared_ptr@UICluster@ClusApi@@@std@@V?$allocator@V?$shared_ptr@UICluster@ClusApi@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@UICluster@ClusApi@@@1@AEBV21@@Z; std::vector<std::shared_ptr<ClusApi::ICluster>>::emplace_back<std::shared_ptr<ClusApi::ICluster> const &>(std::shared_ptr<ClusApi::ICluster> const &)
0x18002d65a  xor     eax, eax
0x18002d65c  jmp     short loc_18002D663
0x18002d65e  mov     eax, 8007139Fh
0x18002d663  add     rsp, 38h
0x18002d667  pop     r14
0x18002d669  pop     rdi
0x18002d66a  pop     rsi
0x18002d66b  pop     rbx
0x18002d66c  retn
```
