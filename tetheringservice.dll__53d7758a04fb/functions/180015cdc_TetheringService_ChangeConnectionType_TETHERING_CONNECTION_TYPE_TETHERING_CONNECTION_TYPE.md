# TetheringService::ChangeConnectionType(_TETHERING_CONNECTION_TYPE,_TETHERING_CONNECTION_TYPE)

- ea: `0x180015cdc`
- end: `0x180015e28`
- name: `?ChangeConnectionType@TetheringService@@AEAAHW4_TETHERING_CONNECTION_TYPE@@0@Z`
- size: `332`
- prototype: `__int64 __fastcall(TetheringService *, unsigned int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180019b4c`
- `0x18001f740`

## callees

- `0x180002590`
- `0x180003088`
- `0x18000bfb4`
- `0x18000d8e4`
- `0x180015cdc`
- `0x180017adc`
- `0x18001c75c`
- `0x180021920`

## pseudocode

```c
__int64 __fastcall TetheringService::ChangeConnectionType(TetheringService *a1, unsigned int a2, int a3)
{
  unsigned int v6; // edi
  int Configuration; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  TetheringServiceTelemetry *v11; // rcx
  int v13; // [rsp+20h] [rbp-128h]
  int v14[4]; // [rsp+30h] [rbp-118h] BYREF
  _DWORD v15[52]; // [rsp+40h] [rbp-108h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v13 = a3;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  v6 = 0;
  memset_0(v15, 0, sizeof(v15));
  Configuration = TetheringService::GetConfiguration(a1, 0, (struct _TETHERING_CONNECTION_SETTINGS *)v15, v14);
  if ( Configuration < 0 )
    goto LABEL_10;
  if ( v15[0] != a2 )
  {
LABEL_13:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v15[0] = a3;
  Configuration = TetheringService::SetConfiguration(a1, 0, (struct _TETHERING_CONNECTION_SETTINGS *const)v15);
  if ( Configuration < 0 )
  {
LABEL_10:
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    WPP_SF_LLd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, a2, a3, Configuration);
    goto LABEL_13;
  }
  v6 = 1;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = a3;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_13;
  }
LABEL_14:
  if ( v11 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
  {
    LOBYTE(v10) = v6;
    WPP_SF_c(*((_QWORD *)v11 + 2), 259, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v10, v13);
  }
  return v6;
}

```

## disassembly

```asm
0x180015cdc  push    rbx
0x180015cde  push    rbp
0x180015cdf  push    rsi
0x180015ce0  push    rdi
0x180015ce1  push    r14
0x180015ce3  sub     rsp, 120h
0x180015cea  mov     rax, cs:__security_cookie
0x180015cf1  xor     rax, rsp
0x180015cf4  mov     [rsp+148h+var_38], rax
0x180015cfc  mov     esi, r8d
0x180015cff  mov     ebx, edx
0x180015d01  mov     rbp, rcx
0x180015d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d0b  lea     r14, WPP_GLOBAL_Control
0x180015d12  cmp     rcx, r14
0x180015d15  jz      short loc_180015D3A
0x180015d17  test    byte ptr [rcx+1Ch], 8
0x180015d1b  jz      short loc_180015D3A
0x180015d1d  mov     rcx, [rcx+10h]
0x180015d21  mov     edx, 100h
0x180015d26  mov     [rsp+148h+var_128], r8d
0x180015d2b  mov     r9d, ebx
0x180015d2e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015d35  call    WPP_SF_dd
0x180015d3a  xor     edx, edx; Val
0x180015d3c  lea     rcx, [rsp+148h+var_108]; void *
0x180015d41  mov     r8d, 0D0h; Size
0x180015d47  xor     edi, edi
0x180015d49  call    memset_0
0x180015d4e  lea     r9, [rsp+148h+var_118]; int *
0x180015d53  xor     edx, edx; struct _TETHERING_CONNECTION_SETTINGS *
0x180015d55  lea     r8, [rsp+148h+var_108]; struct _TETHERING_CONNECTION_SETTINGS *
0x180015d5a  mov     rcx, rbp; this
0x180015d5d  call    ?GetConfiguration@TetheringService@@QEAAJPEAU_TETHERING_CONNECTION_SETTINGS@@0PEAH@Z; TetheringService::GetConfiguration(_TETHERING_CONNECTION_SETTINGS *,_TETHERING_CONNECTION_SETTINGS *,int *)
0x180015d62  test    eax, eax
0x180015d64  js      short loc_180015DB8
0x180015d66  cmp     [rsp+148h+var_108], ebx
0x180015d6a  jnz     short loc_180015DDE
0x180015d6c  lea     r8, [rsp+148h+var_108]; struct _TETHERING_CONNECTION_SETTINGS *
0x180015d71  mov     [rsp+148h+var_108], esi
0x180015d75  xor     edx, edx; struct _TETHERING_CONNECTION_SETTINGS *
0x180015d77  mov     rcx, rbp; this
0x180015d7a  call    ?SetConfiguration@TetheringService@@QEAAJQEAU_TETHERING_CONNECTION_SETTINGS@@0@Z; TetheringService::SetConfiguration(_TETHERING_CONNECTION_SETTINGS * const,_TETHERING_CONNECTION_SETTINGS * const)
0x180015d7f  test    eax, eax
0x180015d81  js      short loc_180015DB8
0x180015d83  mov     edi, 1
0x180015d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d8f  cmp     rcx, r14
0x180015d92  jz      short loc_180015E08
0x180015d94  test    [rcx+1Ch], dil
0x180015d98  jz      short loc_180015DE5
0x180015d9a  mov     rcx, [rcx+10h]
0x180015d9e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015da5  mov     edx, 101h
0x180015daa  mov     [rsp+148h+var_128], esi
0x180015dae  mov     r9d, ebx
0x180015db1  call    WPP_SF_dd
0x180015db6  jmp     short loc_180015DDE
0x180015db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dbf  cmp     rcx, r14
0x180015dc2  jz      short loc_180015E08
0x180015dc4  test    byte ptr [rcx+1Ch], 1
0x180015dc8  jz      short loc_180015DE5
0x180015dca  mov     rcx, [rcx+10h]
0x180015dce  mov     r9d, ebx
0x180015dd1  mov     [rsp+148h+var_120], eax
0x180015dd5  mov     [rsp+148h+var_128], esi
0x180015dd9  call    WPP_SF_LLd
0x180015dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180015de5  cmp     rcx, r14
0x180015de8  jz      short loc_180015E08
0x180015dea  test    byte ptr [rcx+1Ch], 8
0x180015dee  jz      short loc_180015E08
0x180015df0  mov     rcx, [rcx+10h]
0x180015df4  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180015dfb  mov     r9b, dil
0x180015dfe  mov     edx, 103h
0x180015e03  call    WPP_SF_c
0x180015e08  mov     eax, edi
0x180015e0a  mov     rcx, [rsp+148h+var_38]
0x180015e12  xor     rcx, rsp; StackCookie
0x180015e15  call    __security_check_cookie
0x180015e1a  add     rsp, 120h
0x180015e21  pop     r14
0x180015e23  pop     rdi
0x180015e24  pop     rsi
0x180015e25  pop     rbp
0x180015e26  pop     rbx
0x180015e27  retn
```
