# _CPXWizardTypeSource::DoWizardTransaction_::_1_::catch$0

- ea: `0x180033284`
- end: `0x1800332eb`
- name: `_CPXWizardTypeSource::DoWizardTransaction_::_1_::catch$0`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x180033284`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800332d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800332d3`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::DoWizardTransaction_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 128) = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
  CoTaskMemFree(*(LPVOID *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x180033284  mov     [rsp+arg_8], rdx
0x180033289  push    rbp
0x18003328a  sub     rsp, 30h
0x18003328e  mov     rbp, rdx
0x180033291  mov     dword ptr [rbp+80h], 8007000Eh
0x18003329b  lea     rax, WPP_GLOBAL_Control
0x1800332a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332a9  cmp     rcx, rax
0x1800332ac  jz      short loc_1800332CF
0x1800332ae  test    byte ptr [rcx+1Ch], 4
0x1800332b2  jz      short loc_1800332CF
0x1800332b4  mov     edx, 26h ; '&'
0x1800332b9  mov     r9d, 8007000Eh
0x1800332bf  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x1800332c6  mov     rcx, [rcx+10h]
0x1800332ca  call    WPP_SF_d
0x1800332cf  mov     rcx, [rbp+30h]; pv
0x1800332d3  call    cs:__imp_CoTaskMemFree
0x1800332d9  nop
0x1800332da  mov     rax, 0
0x1800332e4  add     rsp, 30h
0x1800332e8  pop     rbp
0x1800332e9  retn
```
