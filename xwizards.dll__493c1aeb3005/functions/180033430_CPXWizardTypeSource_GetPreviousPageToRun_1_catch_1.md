# _CPXWizardTypeSource::GetPreviousPageToRun_::_1_::catch$1

- ea: `0x180033430`
- end: `0x180033497`
- name: `_CPXWizardTypeSource::GetPreviousPageToRun_::_1_::catch$1`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x180033430`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003347f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003347f`

## pseudocode

```c
__int64 __fastcall CPXWizardTypeSource::GetPreviousPageToRun_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids, 2147942414LL);
  CoTaskMemFree(*(LPVOID *)(a2 + 136));
  return 0;
}

```

## disassembly

```asm
0x180033430  mov     [rsp+arg_8], rdx
0x180033435  push    rbp
0x180033436  sub     rsp, 20h
0x18003343a  mov     rbp, rdx
0x18003343d  mov     dword ptr [rbp+70h], 8007000Eh
0x180033444  lea     rax, WPP_GLOBAL_Control
0x18003344b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033452  cmp     rcx, rax
0x180033455  jz      short loc_180033478
0x180033457  test    byte ptr [rcx+1Ch], 4
0x18003345b  jz      short loc_180033478
0x18003345d  mov     edx, 20h ; ' '
0x180033462  mov     r9d, 8007000Eh
0x180033468  lea     r8, WPP_fa339ca505f03532a01d2a69d711b092_Traceguids
0x18003346f  mov     rcx, [rcx+10h]
0x180033473  call    WPP_SF_d
0x180033478  mov     rcx, [rbp+88h]; pv
0x18003347f  call    cs:__imp_CoTaskMemFree
0x180033485  nop
0x180033486  mov     rax, 0
0x180033490  add     rsp, 20h
0x180033494  pop     rbp
0x180033495  retn
```
