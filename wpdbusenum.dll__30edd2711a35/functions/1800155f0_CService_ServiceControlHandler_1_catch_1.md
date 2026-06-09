# _CService::ServiceControlHandler_::_1_::catch$1

- ea: `0x1800155f0`
- end: `0x180015644`
- name: `_CService::ServiceControlHandler_::_1_::catch$1`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000ec30`
- `0x1800155f0`

## pseudocode

```c
__int64 __fastcall CService::ServiceControlHandler_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9

  v3 = *(unsigned int *)(a2 + 72);
  if ( (int)v3 < 0
    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, a3, v3, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800155f0  mov     [rsp+arg_8], rdx
0x1800155f5  push    rbp
0x1800155f6  sub     rsp, 40h
0x1800155fa  mov     rbp, rdx
0x1800155fd  mov     r9d, [rbp+48h]
0x180015601  test    r9d, r9d
0x180015604  jns     short loc_180015633
0x180015606  lea     rax, WPP_GLOBAL_Control
0x18001560d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015614  cmp     rcx, rax
0x180015617  jz      short loc_180015633
0x180015619  test    byte ptr [rcx+1Ch], 2
0x18001561d  jz      short loc_180015633
0x18001561f  mov     edx, 37h ; '7'
0x180015624  mov     [rsp+48h+var_28], r9d
0x180015629  mov     rcx, [rcx+10h]
0x18001562d  call    WPP_SF_Dd
0x180015632  nop
0x180015633  mov     rax, 0
0x18001563d  add     rsp, 40h
0x180015641  pop     rbp
0x180015642  retn
```
