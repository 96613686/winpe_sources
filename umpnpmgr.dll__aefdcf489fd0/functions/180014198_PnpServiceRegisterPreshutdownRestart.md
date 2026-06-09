# PnpServiceRegisterPreshutdownRestart

- ea: `0x180014198`
- end: `0x180014242`
- name: `PnpServiceRegisterPreshutdownRestart`
- size: `170`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000e890`
- `0x1800140f0`

## callees

- `0x1800117d4`
- `0x180011964`
- `0x180014198`

## import_xrefs

- `api-ms-win-service-private-l1-1-1!I_ScRegisterPreshutdownRestart` at `0x1800141a7`
- `api-ms-win-service-private-l1-1-1!I_ScRegisterPreshutdownRestart` at `0x1800141a7`

## string_xrefs

- `0x1800141a0`: `DeviceInstall`

## pseudocode

```c
__int64 PnpServiceRegisterPreshutdownRestart()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx

  v0 = I_ScRegisterPreshutdownRestart(L"DeviceInstall", 0);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 == 1115 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v3 = 11;
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids, v0);
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v3 = 10;
LABEL_9:
      WPP_SF_(v2[2], v3, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180014198  push    rbx
0x18001419a  sub     rsp, 20h
0x18001419e  xor     edx, edx
0x1800141a0  lea     rcx, ServiceName; "DeviceInstall"
0x1800141a7  call    cs:__imp_I_ScRegisterPreshutdownRestart
0x1800141ad  mov     ebx, eax
0x1800141af  test    eax, eax
0x1800141b1  jnz     short loc_1800141D1
0x1800141b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141ba  lea     rdx, WPP_GLOBAL_Control
0x1800141c1  cmp     rcx, rdx
0x1800141c4  jz      short loc_18001423A
0x1800141c6  test    byte ptr [rcx+1Ch], 8
0x1800141ca  jz      short loc_18001423A
0x1800141cc  lea     edx, [rax+0Ah]
0x1800141cf  jmp     short loc_1800141F7
0x1800141d1  cmp     ebx, 45Bh
0x1800141d7  jnz     short loc_180014209
0x1800141d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141e0  lea     rdx, WPP_GLOBAL_Control
0x1800141e7  cmp     rcx, rdx
0x1800141ea  jz      short loc_18001423A
0x1800141ec  test    byte ptr [rcx+1Ch], 8
0x1800141f0  jz      short loc_18001423A
0x1800141f2  mov     edx, 0Bh
0x1800141f7  mov     rcx, [rcx+10h]
0x1800141fb  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x180014202  call    WPP_SF_
0x180014207  jmp     short loc_18001423A
0x180014209  mov     rcx, cs:WPP_GLOBAL_Control
0x180014210  lea     rdx, WPP_GLOBAL_Control
0x180014217  cmp     rcx, rdx
0x18001421a  jz      short loc_18001423A
0x18001421c  test    byte ptr [rcx+1Ch], 1
0x180014220  jz      short loc_18001423A
0x180014222  mov     rcx, [rcx+10h]
0x180014226  lea     r8, WPP_0e80b14c55a13f72cdcecc79ffb17787_Traceguids
0x18001422d  mov     edx, 0Ch
0x180014232  mov     r9d, ebx
0x180014235  call    WPP_SF_d
0x18001423a  mov     eax, ebx
0x18001423c  add     rsp, 20h
0x180014240  pop     rbx
0x180014241  retn
```
