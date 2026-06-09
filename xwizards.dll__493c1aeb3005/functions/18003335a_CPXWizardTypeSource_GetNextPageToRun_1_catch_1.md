# _CPXWizardTypeSource::GetNextPageToRun_::_1_::catch$1

- ea: `0x18003335a`
- end: `0x1800333c1`
- name: `_CPXWizardTypeSource::GetNextPageToRun_::_1_::catch$1`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18003335a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800333a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800333a9`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::GetNextPageToRun_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
  CoTaskMemFree(*(LPVOID *)(a2 + 136));
  return 0;
}

```

## disassembly

```asm
0x18003335a  mov     [rsp+arg_8], rdx
0x18003335f  push    rbp
0x180033360  sub     rsp, 20h
0x180033364  mov     rbp, rdx
0x180033367  mov     dword ptr [rbp+70h], 8007000Eh
0x18003336e  lea     rax, WPP_GLOBAL_Control
0x180033375  mov     rcx, cs:WPP_GLOBAL_Control
0x18003337c  cmp     rcx, rax
0x18003337f  jz      short loc_1800333A2
0x180033381  test    byte ptr [rcx+1Ch], 4
0x180033385  jz      short loc_1800333A2
0x180033387  mov     edx, 18h
0x18003338c  mov     r9d, 8007000Eh
0x180033392  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x180033399  mov     rcx, [rcx+10h]
0x18003339d  call    WPP_SF_d
0x1800333a2  mov     rcx, [rbp+88h]; pv
0x1800333a9  call    cs:__imp_CoTaskMemFree
0x1800333af  nop
0x1800333b0  mov     rax, 0
0x1800333ba  add     rsp, 20h
0x1800333be  pop     rbp
0x1800333bf  retn
```
