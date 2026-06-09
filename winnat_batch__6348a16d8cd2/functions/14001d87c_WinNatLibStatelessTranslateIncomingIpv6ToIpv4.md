# WinNatLibStatelessTranslateIncomingIpv6ToIpv4

- ea: `0x14001d87c`
- end: `0x14001da86`
- name: `WinNatLibStatelessTranslateIncomingIpv6ToIpv4`
- size: `522`
- prototype: `__int64 __usercall@<rax>(NET_BUFFER_LIST *originalNetBufferList@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400172d0`

## callees

- `0x140001190`
- `0x14000caa0`
- `0x1400121c8`
- `0x1400161c0`
- `0x14001d824`
- `0x14001d87c`
- `0x14001e01c`
- `0x14001e2a0`
- `0x14001e77c`
- `0x14001ede0`
- `0x14001f440`

## import_xrefs

- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001d9d4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001da10`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001d9d4`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14001da10`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001d9a2`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14001d9a2`

## pseudocode

```c
__int64 __fastcall WinNatLibStatelessTranslateIncomingIpv6ToIpv4(
        NET_BUFFER_LIST *originalNetBufferList,
        __int64 *a2,
        _BYTE *a3,
        __int64 a4,
        const UCHAR *a5)
{
  NDIS_STATUS TranslatedIpForIncomingIpv6; // ebx
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // edx
  int v16; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[3]; // [rsp+44h] [rbp-BCh] BYREF
  int v20[60]; // [rsp+50h] [rbp-B0h] BYREF

  v19[0] = 0;
  v18 = 0;
  memset(v20, 0, 0xE8u);
  if ( !originalNetBufferList || !a2 || !a3 || !a5 || !IPxlatInstancePropertiesValid(a5) )
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
      v10 = WinNatCloneNblForTranslation(originalNetBufferList, BYTE1(v20[37]) + (unsigned int)LOBYTE(v20[37]));
      TranslatedIpForIncomingIpv6 = NdisRetreatNetBufferDataStart(
                                      originalNetBufferList->FirstNetBuffer,
                                      v20[35] + LOBYTE(v20[37]),
                                      0,
                                      0);
      if ( TranslatedIpForIncomingIpv6 < 0 )
        goto LABEL_17;
      if ( !v10 )
        return (unsigned int)-1073741670;
      v15 = LOBYTE(v20[37]);
      v16 = BYTE1(v20[37]);
      *a2 = v10;
      TranslatedIpForIncomingIpv6 = NdisRetreatNetBufferDataStart(*(PNET_BUFFER *)(v10 + 8), v16 + v15, 0, 0);
      if ( TranslatedIpForIncomingIpv6 < 0 )
      {
LABEL_17:
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11, v13, v14);
        return (unsigned int)TranslatedIpForIncomingIpv6;
      }
      return (unsigned int)WinNatStatelessTranslatePacket((int)v20, *(PNET_BUFFER *)(v10 + 8), (int)&v18, 1, 1, 0);
    }
  }
  return (unsigned int)TranslatedIpForIncomingIpv6;
}

```

## disassembly

```asm
0x14001d87c  push    rbp
0x14001d87e  push    rbx
0x14001d87f  push    rsi
0x14001d880  push    rdi
0x14001d881  push    r14
0x14001d883  lea     rbp, [rsp-50h]
0x14001d888  sub     rsp, 150h
0x14001d88f  mov     rax, cs:__security_cookie
0x14001d896  xor     rax, rsp
0x14001d899  mov     [rbp+70h+var_30], rax
0x14001d89d  mov     rbx, [rbp+70h+arg_20]
0x14001d8a4  mov     rsi, r8
0x14001d8a7  mov     rdi, rdx
0x14001d8aa  mov     [rsp+170h+var_12C], 0
0x14001d8b2  mov     r14, rcx
0x14001d8b5  mov     [rsp+170h+var_130], 0
0x14001d8bd  xor     edx, edx; Val
0x14001d8bf  lea     rcx, [rsp+170h+var_120]; void *
0x14001d8c4  mov     r8d, 0E8h; Size
0x14001d8ca  call    memset
0x14001d8cf  test    r14, r14
0x14001d8d2  jz      loc_14001DA64
0x14001d8d8  test    rdi, rdi
0x14001d8db  jz      loc_14001DA64
0x14001d8e1  test    rsi, rsi
0x14001d8e4  jz      loc_14001DA64
0x14001d8ea  test    rbx, rbx
0x14001d8ed  jz      loc_14001DA64
0x14001d8f3  mov     rcx, rbx
0x14001d8f6  call    IPxlatInstancePropertiesValid
0x14001d8fb  test    al, al
0x14001d8fd  jz      loc_14001DA64
0x14001d903  mov     qword ptr [rdi], 0
0x14001d90a  call    Feature_TCPIP_Wave5_Winnat_XlatErrorCleanup__private_IsEnabledDeviceUsageNoInline
0x14001d90f  test    eax, eax
0x14001d911  jz      short loc_14001D916
0x14001d913  mov     byte ptr [rsi], 0
0x14001d916  mov     r9d, 8
0x14001d91c  lea     rdx, [rsp+170h+var_120]
0x14001d921  xor     r8d, r8d
0x14001d924  mov     rcx, r14
0x14001d927  call    WinNatParseNbl
0x14001d92c  test    al, al
0x14001d92e  jz      loc_14001DA5D
0x14001d934  cmp     [rsp+170h+var_10F], 6
0x14001d939  jnz     loc_14001DA5D
0x14001d93f  test    [rbp+70h+var_4C], 1
0x14001d943  jz      short loc_14001D94F
0x14001d945  xor     ebx, ebx
0x14001d947  mov     byte ptr [rsi], 1
0x14001d94a  jmp     loc_14001DA69
0x14001d94f  cmp     [rbp+70h+var_4B], 0
0x14001d953  lea     rcx, [rsp+170h+var_120]; int
0x14001d958  mov     [rbp+70h+var_8B], 14h
0x14001d95c  mov     rdx, rbx
0x14001d95f  jz      short loc_14001D978
0x14001d961  mov     r9, rdi
0x14001d964  mov     [rsp+170h+var_150], 1; char
0x14001d969  mov     r8, r14
0x14001d96c  call    WinNatStatelessTranslateIcmpError
0x14001d971  mov     ebx, eax
0x14001d973  jmp     loc_14001DA69
0x14001d978  lea     r9, [rsp+170h+var_130]
0x14001d97d  lea     r8, [rsp+170h+var_12C]
0x14001d982  call    WinNatStatelessGetTranslatedIpForIncomingIpv6
0x14001d987  mov     ebx, eax
0x14001d989  test    eax, eax
0x14001d98b  js      loc_14001DA69
0x14001d991  movzx   edx, [rbp+70h+var_8C]
0x14001d995  xor     r9d, r9d; FreeMdlHandler
0x14001d998  add     edx, [rbp+70h+var_94]; DataOffsetDelta
0x14001d99b  xor     r8d, r8d; FreeMdl
0x14001d99e  mov     rcx, [r14+8]; NetBuffer
0x14001d9a2  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14001d9a9  nop     dword ptr [rax+rax+00h]
0x14001d9ae  movzx   edx, [rbp+70h+var_8C]
0x14001d9b2  mov     rcx, r14; originalNetBufferList
0x14001d9b5  movzx   eax, [rbp+70h+var_8B]
0x14001d9b9  add     edx, eax; DataOffsetDelta
0x14001d9bb  call    WinNatCloneNblForTranslation
0x14001d9c0  movzx   edx, [rbp+70h+var_8C]
0x14001d9c4  xor     r9d, r9d; AllocateMdlHandler
0x14001d9c7  add     edx, [rbp+70h+var_94]; DataOffsetDelta
0x14001d9ca  xor     r8d, r8d; DataBackFill
0x14001d9cd  mov     rcx, [r14+8]; NetBuffer
0x14001d9d1  mov     rsi, rax
0x14001d9d4  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001d9db  nop     dword ptr [rax+rax+00h]
0x14001d9e0  mov     ebx, eax
0x14001d9e2  test    eax, eax
0x14001d9e4  jns     short loc_14001D9ED
0x14001d9e6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001d9eb  jmp     short loc_14001DA69
0x14001d9ed  test    rsi, rsi
0x14001d9f0  jnz     short loc_14001D9F9
0x14001d9f2  mov     ebx, 0C000009Ah
0x14001d9f7  jmp     short loc_14001DA69
0x14001d9f9  movzx   edx, [rbp+70h+var_8C]
0x14001d9fd  xor     r9d, r9d; AllocateMdlHandler
0x14001da00  movzx   eax, [rbp+70h+var_8B]
0x14001da04  xor     r8d, r8d; DataBackFill
0x14001da07  mov     [rdi], rsi
0x14001da0a  add     edx, eax; DataOffsetDelta
0x14001da0c  mov     rcx, [rsi+8]; NetBuffer
0x14001da10  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14001da17  nop     dword ptr [rax+rax+00h]
0x14001da1c  mov     ebx, eax
0x14001da1e  test    eax, eax
0x14001da20  jns     short loc_14001DA29
0x14001da22  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14001da27  jmp     short loc_14001DA69
0x14001da29  mov     rdx, [rsi+8]; NetBuffer
0x14001da2d  lea     rax, [rsp+170h+var_130]
0x14001da32  mov     [rsp+170h+var_138], 0; char
0x14001da37  lea     r9, [rsp+170h+var_12C]
0x14001da3c  mov     [rsp+170h+var_140], 1; char
0x14001da41  lea     rcx, [rsp+170h+var_120]; int
0x14001da46  mov     [rsp+170h+var_148], 1; char
0x14001da4b  mov     r8, rdi
0x14001da4e  mov     qword ptr [rsp+170h+var_150], rax; int
0x14001da53  call    WinNatStatelessTranslatePacket
0x14001da58  jmp     loc_14001D971
0x14001da5d  mov     ebx, 0C000021Bh
0x14001da62  jmp     short loc_14001DA69
0x14001da64  mov     ebx, 0C000000Dh
0x14001da69  mov     eax, ebx
0x14001da6b  mov     rcx, [rbp+70h+var_30]
0x14001da6f  xor     rcx, rsp; StackCookie
0x14001da72  call    __security_check_cookie
0x14001da77  add     rsp, 150h
0x14001da7e  pop     r14
0x14001da80  pop     rdi
0x14001da81  pop     rsi
0x14001da82  pop     rbx
0x14001da83  pop     rbp
0x14001da84  retn
```
