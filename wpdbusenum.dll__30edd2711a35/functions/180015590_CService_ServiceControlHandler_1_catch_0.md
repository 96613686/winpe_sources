# _CService::ServiceControlHandler_::_1_::catch$0

- ea: `0x180015590`
- end: `0x1800155e4`
- name: `_CService::ServiceControlHandler_::_1_::catch$0`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000ec30`
- `0x180015590`

## pseudocode

```c
__int64 __fastcall CService::ServiceControlHandler_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9

  v3 = *(unsigned int *)(a2 + 68);
  if ( (int)v3 < 0
    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, a3, v3, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180015590  mov     [rsp+arg_8], rdx
0x180015595  push    rbp
0x180015596  sub     rsp, 40h
0x18001559a  mov     rbp, rdx
0x18001559d  mov     r9d, [rbp+44h]
0x1800155a1  test    r9d, r9d
0x1800155a4  jns     short loc_1800155D3
0x1800155a6  lea     rax, WPP_GLOBAL_Control
0x1800155ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155b4  cmp     rcx, rax
0x1800155b7  jz      short loc_1800155D3
0x1800155b9  test    byte ptr [rcx+1Ch], 2
0x1800155bd  jz      short loc_1800155D3
0x1800155bf  mov     edx, 32h ; '2'
0x1800155c4  mov     [rsp+48h+var_28], r9d
0x1800155c9  mov     rcx, [rcx+10h]
0x1800155cd  call    WPP_SF_Dd
0x1800155d2  nop
0x1800155d3  mov     rax, 0
0x1800155dd  add     rsp, 40h
0x1800155e1  pop     rbp
0x1800155e2  retn
```
