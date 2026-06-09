# InterfaceMgr::UpdatePrivateBluetoothInterface(void)

- ea: `0x180013ca0`
- end: `0x180013d90`
- name: `?UpdatePrivateBluetoothInterface@InterfaceMgr@@QEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(InterfaceMgr *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18001e4a4`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x180012818`
- `0x180013ca0`
- `0x1800140f4`

## pseudocode

```c
__int64 __fastcall InterfaceMgr::UpdatePrivateBluetoothInterface(struct _GUID *this)
{
  int BTPANInterfaceGuid; // eax
  int v3; // r8d
  unsigned int v4; // ebx
  TetheringServiceTelemetry *v5; // rcx
  struct _GUID v6; // xmm0
  struct _GUID v8; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
  }
  v8 = 0;
  BTPANInterfaceGuid = InterfaceMgr::GetBTPANInterfaceGuid(&v8);
  v4 = BTPANInterfaceGuid;
  if ( BTPANInterfaceGuid >= 0 )
  {
    v6 = v8;
    *(_DWORD *)&this[7].Data4[4] = 10;
    this[5] = v6;
    goto LABEL_9;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      138,
      &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids,
      (unsigned int)BTPANInterfaceGuid);
LABEL_9:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d_guid_(*((_QWORD *)v5 + 2), 139, v3, v4, (__int64)&v8);
  return v4;
}

```

## disassembly

```asm
0x180013ca0  mov     [rsp+arg_8], rbx
0x180013ca5  mov     [rsp+arg_10], rsi
0x180013caa  push    rdi
0x180013cab  sub     rsp, 50h
0x180013caf  mov     rax, cs:__security_cookie
0x180013cb6  xor     rax, rsp
0x180013cb9  mov     [rsp+58h+var_18], rax
0x180013cbe  mov     rdi, rcx
0x180013cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cc8  lea     rsi, WPP_GLOBAL_Control
0x180013ccf  cmp     rcx, rsi
0x180013cd2  jz      short loc_180013CEF
0x180013cd4  test    byte ptr [rcx+1Ch], 8
0x180013cd8  jz      short loc_180013CEF
0x180013cda  mov     rcx, [rcx+10h]
0x180013cde  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013ce5  mov     edx, 89h
0x180013cea  call    WPP_SF_
0x180013cef  xorps   xmm0, xmm0
0x180013cf2  lea     rcx, [rsp+58h+var_28]; struct _GUID *
0x180013cf7  movups  xmmword ptr [rsp+58h+var_28.Data1], xmm0
0x180013cfc  call    ?GetBTPANInterfaceGuid@InterfaceMgr@@CAJPEAU_GUID@@@Z; InterfaceMgr::GetBTPANInterfaceGuid(_GUID *)
0x180013d01  mov     ebx, eax
0x180013d03  test    eax, eax
0x180013d05  jns     short loc_180013D33
0x180013d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d0e  cmp     rcx, rsi
0x180013d11  jz      short loc_180013D71
0x180013d13  test    byte ptr [rcx+1Ch], 1
0x180013d17  jz      short loc_180013D4B
0x180013d19  mov     rcx, [rcx+10h]
0x180013d1d  lea     r8, WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids
0x180013d24  mov     edx, 8Ah
0x180013d29  mov     r9d, eax
0x180013d2c  call    WPP_SF_d
0x180013d31  jmp     short loc_180013D44
0x180013d33  movups  xmm0, xmmword ptr [rsp+58h+var_28.Data1]
0x180013d38  mov     dword ptr [rdi+7Ch], 0Ah
0x180013d3f  movdqu  xmmword ptr [rdi+50h], xmm0
0x180013d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d4b  cmp     rcx, rsi
0x180013d4e  jz      short loc_180013D71
0x180013d50  test    byte ptr [rcx+1Ch], 8
0x180013d54  jz      short loc_180013D71
0x180013d56  mov     rcx, [rcx+10h]
0x180013d5a  lea     rax, [rsp+58h+var_28]
0x180013d5f  mov     edx, 8Bh
0x180013d64  mov     [rsp+58h+var_38], rax
0x180013d69  mov     r9d, ebx
0x180013d6c  call    WPP_SF_d_guid_
0x180013d71  mov     eax, ebx
0x180013d73  mov     rcx, [rsp+58h+var_18]
0x180013d78  xor     rcx, rsp; StackCookie
0x180013d7b  call    __security_check_cookie
0x180013d80  mov     rbx, [rsp+58h+arg_8]
0x180013d85  mov     rsi, [rsp+58h+arg_10]
0x180013d8a  add     rsp, 50h
0x180013d8e  pop     rdi
0x180013d8f  retn
```
