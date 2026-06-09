# _CPropertyBag::HrSetProperty_::_1_::catch$0

- ea: `0x1800335a2`
- end: `0x180033609`
- name: `_CPropertyBag::HrSetProperty_::_1_::catch$0`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x1800335a2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800335f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800335f1`

## pseudocode

```c
__int64 __fastcall CPropertyBag::HrSetProperty_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 176) = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids, 2147942414LL);
  CoTaskMemFree(*(LPVOID *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x1800335a2  mov     [rsp+arg_8], rdx
0x1800335a7  push    rbp
0x1800335a8  sub     rsp, 30h
0x1800335ac  mov     rbp, rdx
0x1800335af  mov     dword ptr [rbp+0B0h], 8007000Eh
0x1800335b9  lea     rax, WPP_GLOBAL_Control
0x1800335c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335c7  cmp     rcx, rax
0x1800335ca  jz      short loc_1800335ED
0x1800335cc  test    byte ptr [rcx+1Ch], 4
0x1800335d0  jz      short loc_1800335ED
0x1800335d2  mov     edx, 10h
0x1800335d7  mov     r9d, 8007000Eh
0x1800335dd  lea     r8, WPP_68d45ddfb6663f942b433d9c5d20cdd0_Traceguids
0x1800335e4  mov     rcx, [rcx+10h]
0x1800335e8  call    WPP_SF_d
0x1800335ed  mov     rcx, [rbp+30h]; pv
0x1800335f1  call    cs:__imp_CoTaskMemFree
0x1800335f7  nop
0x1800335f8  mov     rax, 0
0x180033602  add     rsp, 30h
0x180033606  pop     rbp
0x180033607  retn
```
