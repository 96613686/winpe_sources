# WlanInternalMiracastIsActive(void)

- ea: `0x1800122a4`
- end: `0x18001233f`
- name: `?WlanInternalMiracastIsActive@@YAHXZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015c00`

## callees

- `0x180006934`
- `0x1800122a4`

## import_xrefs

- `WFDSConMgr!WFDSConMgrFreeMemory` at `0x1800122e2`
- `WFDSConMgr!WFDSConMgrFreeMemory` at `0x1800122e2`
- `WFDSConMgr!WFDSConMgrGetOpenSessionList` at `0x1800122ba`
- `WFDSConMgr!WFDSConMgrGetOpenSessionList` at `0x1800122ba`

## pseudocode

```c
__int64 WlanInternalMiracastIsActive(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  unsigned int i; // r8d
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  v0 = 0;
  if ( !(unsigned int)WFDSConMgrGetOpenSessionList(&v4) )
  {
    v1 = v4;
    for ( i = 0; i < *(_DWORD *)(v4 + 8); ++i )
    {
      if ( (unsigned int)(*(_DWORD *)(28LL * i + v4 + 20) - 1) <= 2 )
      {
        v0 = 1;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 119, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
          v1 = v4;
        }
        break;
      }
    }
    if ( v1 )
      WFDSConMgrFreeMemory(v1);
  }
  return v0;
}

```

## disassembly

```asm
0x1800122a4  push    rbx
0x1800122a6  sub     rsp, 20h
0x1800122aa  lea     rcx, [rsp+28h+arg_0]
0x1800122af  mov     [rsp+28h+arg_0], 0
0x1800122b8  xor     ebx, ebx
0x1800122ba  call    cs:__imp_WFDSConMgrGetOpenSessionList
0x1800122c0  test    eax, eax
0x1800122c2  jnz     short loc_1800122D7
0x1800122c4  mov     rdx, [rsp+28h+arg_0]
0x1800122c9  xor     r8d, r8d
0x1800122cc  cmp     r8d, [rdx+8]
0x1800122d0  jb      short loc_1800122EA
0x1800122d2  test    rdx, rdx
0x1800122d5  jnz     short loc_1800122DF
0x1800122d7  mov     eax, ebx
0x1800122d9  add     rsp, 20h
0x1800122dd  pop     rbx
0x1800122de  retn
0x1800122df  mov     rcx, rdx
0x1800122e2  call    cs:__imp_WFDSConMgrFreeMemory
0x1800122e8  jmp     short loc_1800122D7
0x1800122ea  mov     eax, r8d
0x1800122ed  imul    rcx, rax, 1Ch
0x1800122f1  mov     eax, [rcx+rdx+14h]
0x1800122f5  dec     eax
0x1800122f7  cmp     eax, 2
0x1800122fa  jbe     short loc_180012301
0x1800122fc  inc     r8d
0x1800122ff  jmp     short loc_1800122CC
0x180012301  mov     ebx, 1
0x180012306  mov     rcx, cs:WPP_GLOBAL_Control
0x18001230d  lea     rax, WPP_GLOBAL_Control
0x180012314  cmp     rcx, rax
0x180012317  jz      short loc_1800122D2
0x180012319  cmp     byte ptr [rcx+69h], 4
0x18001231d  jb      short loc_1800122D2
0x18001231f  test    byte ptr [rcx+6Ch], 2
0x180012323  jz      short loc_1800122D2
0x180012325  mov     rcx, [rcx+60h]
0x180012329  lea     edx, [rbx+76h]
0x18001232c  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x180012333  call    WPP_SF_
0x180012338  mov     rdx, [rsp+28h+arg_0]
0x18001233d  jmp     short loc_1800122D2
```
