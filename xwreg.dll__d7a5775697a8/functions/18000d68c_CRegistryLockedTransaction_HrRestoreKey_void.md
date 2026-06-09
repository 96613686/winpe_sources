# CRegistryLockedTransaction::HrRestoreKey(void)

- ea: `0x18000d68c`
- end: `0x18000d762`
- name: `?HrRestoreKey@CRegistryLockedTransaction@@QEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(CRegistryLockedTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009994`

## callees

- `0x180007820`
- `0x18000d68c`
- `0x18000d768`

## pseudocode

```c
__int64 __fastcall CRegistryLockedTransaction::HrRestoreKey(CRegistryLockedTransaction *this)
{
  __int64 v1; // r9
  unsigned int v4; // ebx

  v1 = *((unsigned int *)this + 143);
  if ( (int)v1 >= 0 )
  {
    if ( *((_DWORD *)this + 142) )
    {
      v4 = CRegistryTransaction::HrRestoreKey((CRegistryLockedTransaction *)((char *)this + 8));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_b6864e106af034a19631ace060353c02_Traceguids, v4);
      return v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_b6864e106af034a19631ace060353c02_Traceguids, 2147483658LL);
      return 2147483658LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b6864e106af034a19631ace060353c02_Traceguids, v1);
    return *((unsigned int *)this + 143);
  }
}

```

## disassembly

```asm
0x18000d68c  push    rbx
0x18000d68e  sub     rsp, 20h
0x18000d692  mov     r9d, [rcx+23Ch]
0x18000d699  mov     rbx, rcx
0x18000d69c  test    r9d, r9d
0x18000d69f  jns     short loc_18000D6DA
0x18000d6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6a8  lea     rax, WPP_GLOBAL_Control
0x18000d6af  cmp     rcx, rax
0x18000d6b2  jz      short loc_18000D6CF
0x18000d6b4  test    byte ptr [rcx+1Ch], 4
0x18000d6b8  jz      short loc_18000D6CF
0x18000d6ba  mov     rcx, [rcx+10h]
0x18000d6be  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d6c5  mov     edx, 20h ; ' '
0x18000d6ca  call    WPP_SF_D
0x18000d6cf  mov     eax, [rbx+23Ch]
0x18000d6d5  jmp     loc_18000D75C
0x18000d6da  cmp     dword ptr [rcx+238h], 0
0x18000d6e1  jnz     short loc_18000D71E
0x18000d6e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6ea  lea     rax, WPP_GLOBAL_Control
0x18000d6f1  cmp     rcx, rax
0x18000d6f4  jz      short loc_18000D717
0x18000d6f6  test    byte ptr [rcx+1Ch], 4
0x18000d6fa  jz      short loc_18000D717
0x18000d6fc  mov     rcx, [rcx+10h]
0x18000d700  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d707  mov     edx, 21h ; '!'
0x18000d70c  mov     r9d, 8000000Ah
0x18000d712  call    WPP_SF_D
0x18000d717  mov     eax, 8000000Ah
0x18000d71c  jmp     short loc_18000D75C
0x18000d71e  add     rcx, 8; this
0x18000d722  call    ?HrRestoreKey@CRegistryTransaction@@QEAAJXZ; CRegistryTransaction::HrRestoreKey(void)
0x18000d727  mov     ebx, eax
0x18000d729  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d730  lea     rax, WPP_GLOBAL_Control
0x18000d737  cmp     rcx, rax
0x18000d73a  jz      short loc_18000D75A
0x18000d73c  test    byte ptr [rcx+1Ch], 10h
0x18000d740  jz      short loc_18000D75A
0x18000d742  mov     rcx, [rcx+10h]
0x18000d746  lea     r8, WPP_b6864e106af034a19631ace060353c02_Traceguids
0x18000d74d  mov     edx, 22h ; '"'
0x18000d752  mov     r9d, ebx
0x18000d755  call    WPP_SF_D
0x18000d75a  mov     eax, ebx
0x18000d75c  add     rsp, 20h
0x18000d760  pop     rbx
0x18000d761  retn
```
