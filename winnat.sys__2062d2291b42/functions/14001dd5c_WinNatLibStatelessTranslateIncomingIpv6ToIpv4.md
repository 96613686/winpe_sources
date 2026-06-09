# WinNatLibStatelessTranslateIncomingIpv6ToIpv4

- ea: `0x14001dd5c`
- end: `0x14001df66`
- name: `WinNatLibStatelessTranslateIncomingIpv6ToIpv4`
- size: `522`
- prototype: `__int64 __fastcall(NET_BUFFER_LIST *originalNetBufferList, NET_BUFFER_LIST **, _BYTE *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140018010`

## callees

- `0x140001190`
- `0x14000caa0`
- `0x140012b08`
- `0x140016e28`
- `0x14001dd04`
- `0x14001dd5c`
- `0x14001e4fc`
- `0x14001e7d8`
- `0x14001ecb4`
- `0x14001f320`
- `0x14001f980`

## import_xrefs

- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001deb4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001def0`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001deb4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001def0`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001de82`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001de82`

## pseudocode

```c
__int64 __fastcall WinNatLibStatelessTranslateIncomingIpv6ToIpv4(
        NET_BUFFER_LIST *originalNetBufferList,
        NET_BUFFER_LIST **a2,
        _BYTE *a3,
        __int64 a4,
        __int64 a5)
{
  NDIS_STATUS TranslatedIpForIncomingIpv6; // ebx
  __int64 v10; // r8
  NET_BUFFER_LIST *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // edx
  int v16; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v20[60]; // [rsp+50h] [rbp-B0h] BYREF

  v19[0] = 0;
  v18 = 0;
  memset(v20, 0, 0xE8u);
  if ( !originalNetBufferList || !a2 || !a3 || !a5 || !(unsigned __int8)IPxlatInstancePropertiesValid(a5) )
    return (unsigned int)-1073741811;
  *a2 = 0;
  if ( (unsigned int)Feature_TCPIP_Wave5_Winnat_XlatErrorCleanup__private_IsEnabledDeviceUsageNoInline() )
    *a3 = 0;
  if ( !(unsigned __int8)WinNatParseNbl(originalNetBufferList, v20, 0, 8) || BYTE1(v20[4]) != 6 )
    return (unsigned int)-1073741285;
  if ( (v20[53] & 1) != 0 )
  {
    TranslatedIpForIncomingIpv6 = 0;
    *a3 = 1;
  }
  else
  {
    BYTE1(v20[37]) = 20;
    if ( BYTE1(v20[53]) )
    {
      return (unsigned int)WinNatStatelessTranslateIcmpError((int)v20, 1);
    }
    else
    {
      TranslatedIpForIncomingIpv6 = WinNatStatelessGetTranslatedIpForIncomingIpv6(v20, a5, v19, &v18);
      if ( TranslatedIpForIncomingIpv6 < 0 )
        return (unsigned int)TranslatedIpForIncomingIpv6;
      NdisAdvanceNetBufferDataStart(originalNetBufferList->FirstNetBuffer, v20[35] + LOBYTE(v20[37]), 0, 0);
      v11 = WinNatCloneNblForTranslation(originalNetBufferList, BYTE1(v20[37]) + (unsigned int)LOBYTE(v20[37]), v10);
      TranslatedIpForIncomingIpv6 = NdisRetreatNetBufferDataStart(
                                      originalNetBufferList->FirstNetBuffer,
                                      v20[35] + LOBYTE(v20[37]),
                                      0,
                                      0);
      if ( TranslatedIpForIncomingIpv6 < 0 )
        goto LABEL_17;
      if ( !v11 )
        return (unsigned int)-1073741670;
      v15 = LOBYTE(v20[37]);
      v16 = BYTE1(v20[37]);
      *a2 = v11;
      TranslatedIpForIncomingIpv6 = NdisRetreatNetBufferDataStart(v11->FirstNetBuffer, v16 + v15, 0, 0);
      if ( TranslatedIpForIncomingIpv6 < 0 )
      {
LABEL_17:
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12, v14);
        return (unsigned int)TranslatedIpForIncomingIpv6;
      }
      return (unsigned int)WinNatStatelessTranslatePacket((int)v20, v11->FirstNetBuffer, (int)&v18, 1, 1, 0);
    }
  }
  return (unsigned int)TranslatedIpForIncomingIpv6;
}

```

## disassembly

```asm
0x14001dd5c  push    rbp
0x14001dd5e  push    rbx
0x14001dd5f  push    rsi
0x14001dd60  push    rdi
0x14001dd61  push    r14
0x14001dd63  lea     rbp, [rsp-50h]
0x14001dd68  sub     rsp, 150h
0x14001dd6f  mov     rax, cs:__security_cookie
0x14001dd76  xor     rax, rsp
0x14001dd79  mov     [rbp+70h+var_30], rax
0x14001dd7d  mov     rbx, [rbp+70h+arg_20]
0x14001dd84  mov     rsi, r8
0x14001dd87  mov     rdi, rdx
0x14001dd8a  mov     [rsp+170h+var_12C], 0
0x14001dd92  mov     r14, rcx
0x14001dd95  mov     [rsp+170h+var_130], 0
0x14001dd9d  xor     edx, edx; Val
0x14001dd9f  lea     rcx, [rsp+170h+var_120]; void *
0x14001dda4  mov     r8d, 0E8h; Size
0x14001ddaa  call    memset
0x14001ddaf  test    r14, r14
0x14001ddb2  jz      loc_14001DF44
0x14001ddb8  test    rdi, rdi
0x14001ddbb  jz      loc_14001DF44
0x14001ddc1  test    rsi, rsi
0x14001ddc4  jz      loc_14001DF44
0x14001ddca  test    rbx, rbx
0x14001ddcd  jz      loc_14001DF44
0x14001ddd3  mov     rcx, rbx
0x14001ddd6  call    IPxlatInstancePropertiesValid
0x14001dddb  test    al, al
0x14001dddd  jz      loc_14001DF44
0x14001dde3  mov     qword ptr [rdi], 0
0x14001ddea  call    Feature_TCPIP_Wave5_Winnat_XlatErrorCleanup__private_IsEnabledDeviceUsageNoInline
0x14001ddef  test    eax, eax
0x14001ddf1  jz      short loc_14001DDF6
0x14001ddf3  mov     byte ptr [rsi], 0
0x14001ddf6  mov     r9d, 8
0x14001ddfc  lea     rdx, [rsp+170h+var_120]
0x14001de01  xor     r8d, r8d
0x14001de04  mov     rcx, r14
0x14001de07  call    WinNatParseNbl
0x14001de0c  test    al, al
0x14001de0e  jz      loc_14001DF3D
0x14001de14  cmp     [rsp+170h+var_10F], 6
0x14001de19  jnz     loc_14001DF3D
0x14001de1f  test    [rbp+70h+var_4C], 1
0x14001de23  jz      short loc_14001DE2F
0x14001de25  xor     ebx, ebx
0x14001de27  mov     byte ptr [rsi], 1
0x14001de2a  jmp     loc_14001DF49
0x14001de2f  cmp     [rbp+70h+var_4B], 0
0x14001de33  lea     rcx, [rsp+170h+var_120]; int
0x14001de38  mov     [rbp+70h+var_8B], 14h
0x14001de3c  mov     rdx, rbx
0x14001de3f  jz      short loc_14001DE58
0x14001de41  mov     r9, rdi
0x14001de44  mov     [rsp+170h+var_150], 1; char
0x14001de49  mov     r8, r14
0x14001de4c  call    WinNatStatelessTranslateIcmpError
0x14001de51  mov     ebx, eax
0x14001de53  jmp     loc_14001DF49
0x14001de58  lea     r9, [rsp+170h+var_130]
0x14001de5d  lea     r8, [rsp+170h+var_12C]
0x14001de62  call    WinNatStatelessGetTranslatedIpForIncomingIpv6
0x14001de67  mov     ebx, eax
0x14001de69  test    eax, eax
0x14001de6b  js      loc_14001DF49
0x14001de71  movzx   edx, [rbp+70h+var_8C]
0x14001de75  xor     r9d, r9d; FreeMdlHandler
0x14001de78  add     edx, [rbp+70h+var_94]; DataOffsetDelta
0x14001de7b  xor     r8d, r8d; FreeMdl
0x14001de7e  mov     rcx, [r14+8]; NetBuffer
0x14001de82  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001de89  nop     dword ptr [rax+rax+00h]
0x14001de8e  movzx   edx, [rbp+70h+var_8C]
0x14001de92  mov     rcx, r14; originalNetBufferList
0x14001de95  movzx   eax, [rbp+70h+var_8B]
0x14001de99  add     edx, eax; DataOffsetDelta
0x14001de9b  call    WinNatCloneNblForTranslation
0x14001dea0  movzx   edx, [rbp+70h+var_8C]
0x14001dea4  xor     r9d, r9d; AllocateMdlHandler
0x14001dea7  add     edx, [rbp+70h+var_94]; DataOffsetDelta
0x14001deaa  xor     r8d, r8d; DataBackFill
0x14001dead  mov     rcx, [r14+8]; NetBuffer
0x14001deb1  mov     rsi, rax
0x14001deb4  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001debb  nop     dword ptr [rax+rax+00h]
0x14001dec0  mov     ebx, eax
0x14001dec2  test    eax, eax
0x14001dec4  jns     short loc_14001DECD
0x14001dec6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001decb  jmp     short loc_14001DF49
0x14001decd  test    rsi, rsi
0x14001ded0  jnz     short loc_14001DED9
0x14001ded2  mov     ebx, 0C000009Ah
0x14001ded7  jmp     short loc_14001DF49
0x14001ded9  movzx   edx, [rbp+70h+var_8C]
0x14001dedd  xor     r9d, r9d; AllocateMdlHandler
0x14001dee0  movzx   eax, [rbp+70h+var_8B]
0x14001dee4  xor     r8d, r8d; DataBackFill
0x14001dee7  mov     [rdi], rsi
0x14001deea  add     edx, eax; DataOffsetDelta
0x14001deec  mov     rcx, [rsi+8]; NetBuffer
0x14001def0  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001def7  nop     dword ptr [rax+rax+00h]
0x14001defc  mov     ebx, eax
0x14001defe  test    eax, eax
0x14001df00  jns     short loc_14001DF09
0x14001df02  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001df07  jmp     short loc_14001DF49
0x14001df09  mov     rdx, [rsi+8]; NetBuffer
0x14001df0d  lea     rax, [rsp+170h+var_130]
0x14001df12  mov     [rsp+170h+var_138], 0; char
0x14001df17  lea     r9, [rsp+170h+var_12C]
0x14001df1c  mov     [rsp+170h+var_140], 1; char
0x14001df21  lea     rcx, [rsp+170h+var_120]; int
0x14001df26  mov     [rsp+170h+var_148], 1; char
0x14001df2b  mov     r8, rdi
0x14001df2e  mov     qword ptr [rsp+170h+var_150], rax; int
0x14001df33  call    WinNatStatelessTranslatePacket
0x14001df38  jmp     loc_14001DE51
0x14001df3d  mov     ebx, 0C000021Bh
0x14001df42  jmp     short loc_14001DF49
0x14001df44  mov     ebx, 0C000000Dh
0x14001df49  mov     eax, ebx
0x14001df4b  mov     rcx, [rbp+70h+var_30]
0x14001df4f  xor     rcx, rsp; StackCookie
0x14001df52  call    __security_check_cookie
0x14001df57  add     rsp, 150h
0x14001df5e  pop     r14
0x14001df60  pop     rdi
0x14001df61  pop     rsi
0x14001df62  pop     rbx
0x14001df63  pop     rbp
0x14001df64  retn
```
