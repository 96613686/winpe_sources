# CWdsTransportServicePolicy::ValidateMulticastIpAddress(ulong,ushort const *)

- ea: `0x18000d9e8`
- end: `0x18000dbc2`
- name: `?ValidateMulticastIpAddress@CWdsTransportServicePolicy@@CAJKPEBG@Z`
- size: `474`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e4f0`
- `0x18000e850`

## callees

- `0x18000d9e8`
- `0x18000eb74`
- `0x18000ec98`
- `0x18001e9f0`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18000db4e`
- `WS2_32!__imp_ntohl` at `0x18000db5f`
- `WS2_32!__imp_ntohl` at `0x18000db72`
- `WS2_32!__imp_ntohl` at `0x18000db83`
- `WS2_32!__imp_ntohl` at `0x18000db4e`
- `WS2_32!__imp_ntohl` at `0x18000db5f`
- `WS2_32!__imp_ntohl` at `0x18000db72`
- `WS2_32!__imp_ntohl` at `0x18000db83`
- `WdsCommonLib!?IsValidIpAddress@CNetworkAddress@@SAKKPEBG@Z` at `0x18000da44`
- `WdsCommonLib!?IsValidIpAddress@CNetworkAddress@@SAKKPEBG@Z` at `0x18000da44`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000da92`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000dafc`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000db28`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000da92`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000dafc`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000db28`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::ValidateMulticastIpAddress(unsigned int a1, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  int IsValidIpAddress; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  signed int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  u_long v15; // ebx
  u_long v16; // ebx
  u_long v18[4]; // [rsp+20h] [rbp-50h] BYREF
  int v19; // [rsp+30h] [rbp-40h]
  u_long netlong[4]; // [rsp+38h] [rbp-38h] BYREF
  int v21; // [rsp+48h] [rbp-28h]
  u_long v22[4]; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+60h] [rbp-10h]

  v19 = 0;
  v21 = 0;
  v23 = 0;
  *(_OWORD *)v18 = 0;
  *(_OWORD *)netlong = 0;
  *(_OWORD *)v22 = 0;
  if ( !a2 || !*a2 )
    return (unsigned int)-2147024809;
  v4 = 0;
  IsValidIpAddress = CNetworkAddress::IsValidIpAddress(a1, a2);
  if ( IsValidIpAddress )
  {
    if ( IsValidIpAddress == 13 )
    {
      v4 = -1055915754;
    }
    else if ( IsValidIpAddress > 0 )
    {
      v4 = (unsigned __int16)IsValidIpAddress | 0x80070000;
    }
    else
    {
      v4 = IsValidIpAddress;
    }
  }
  if ( (int)ElValidateHr_4(v4, v6, v7, 627) >= 0 )
  {
    v8 = CNetworkAddress::StringToIpAddress(a1, a2, (struct tagWDS_IP_ADDRESS6 *)v18);
    if ( (unsigned int)ElValidateWin32_4(v8, v9, v10, 0x27Bu) )
    {
LABEL_11:
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
      else
        return (unsigned int)v8;
    }
    if ( a1 == 2 )
    {
      v8 = CNetworkAddress::StringToIpAddress(2u, L"224.0.1.0", (struct tagWDS_IP_ADDRESS6 *)netlong);
      if ( (unsigned int)ElValidateWin32_4(v8, v11, v12, 0x28Cu) )
        goto LABEL_11;
      v8 = CNetworkAddress::StringToIpAddress(2u, L"239.255.255.255", (struct tagWDS_IP_ADDRESS6 *)v22);
      if ( (unsigned int)ElValidateWin32_4(v8, v13, v14, 0x291u) )
        goto LABEL_11;
      v15 = ntohl(netlong[0]);
      if ( ntohl(v18[0]) < v15 )
        return (unsigned int)-1055915753;
      v16 = ntohl(v22[0]);
      if ( ntohl(v18[0]) > v16 )
        return (unsigned int)-1055915753;
    }
    else if ( a1 == 23 )
    {
      if ( LOBYTE(v18[0]) != 0xFF )
        return (unsigned int)-1055915752;
    }
    else
    {
      return (unsigned int)-2147467263;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000d9e8  mov     [rsp-28h+arg_10], rbx
0x18000d9ed  push    rbp
0x18000d9ee  push    rsi
0x18000d9ef  push    rdi
0x18000d9f0  push    r14
0x18000d9f2  push    r15
0x18000d9f4  mov     rbp, rsp
0x18000d9f7  sub     rsp, 70h
0x18000d9fb  mov     rax, cs:__security_cookie
0x18000da02  xor     rax, rsp
0x18000da05  mov     [rbp+var_8], rax
0x18000da09  xor     eax, eax
0x18000da0b  xorps   xmm0, xmm0
0x18000da0e  xor     r14d, r14d
0x18000da11  mov     [rbp+var_40], eax
0x18000da14  mov     [rbp+var_28], eax
0x18000da17  xorps   xmm1, xmm1
0x18000da1a  mov     [rbp+var_10], eax
0x18000da1d  mov     rbx, rdx
0x18000da20  mov     esi, ecx
0x18000da22  movups  xmmword ptr [rbp+var_50], xmm0
0x18000da26  movups  xmmword ptr [rbp+netlong], xmm1
0x18000da2a  movups  xmmword ptr [rbp+var_20], xmm0
0x18000da2e  test    rdx, rdx
0x18000da31  jz      loc_18000DB9A
0x18000da37  cmp     [rdx], r14w
0x18000da3b  jz      loc_18000DB9A
0x18000da41  mov     edi, r14d
0x18000da44  call    cs:__imp_?IsValidIpAddress@CNetworkAddress@@SAKKPEBG@Z; CNetworkAddress::IsValidIpAddress(ulong,ushort const *)
0x18000da4b  nop     dword ptr [rax+rax+00h]
0x18000da50  mov     r15d, 80070000h
0x18000da56  test    eax, eax
0x18000da58  jz      short loc_18000DA74
0x18000da5a  cmp     eax, 0Dh
0x18000da5d  jnz     short loc_18000DA66
0x18000da5f  mov     edi, 0C1100116h
0x18000da64  jmp     short loc_18000DA74
0x18000da66  test    eax, eax
0x18000da68  jg      short loc_18000DA6E
0x18000da6a  mov     edi, eax
0x18000da6c  jmp     short loc_18000DA74
0x18000da6e  movzx   edi, ax
0x18000da71  or      edi, r15d
0x18000da74  mov     r9d, 273h
0x18000da7a  mov     ecx, edi
0x18000da7c  call    ElValidateHr_4
0x18000da81  test    eax, eax
0x18000da83  js      loc_18000DB9F
0x18000da89  lea     r8, [rbp+var_50]
0x18000da8d  mov     rdx, rbx
0x18000da90  mov     ecx, esi
0x18000da92  call    cs:__imp_?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)
0x18000da99  nop     dword ptr [rax+rax+00h]
0x18000da9e  mov     ecx, eax
0x18000daa0  mov     r9d, 27Bh
0x18000daa6  mov     ebx, eax
0x18000daa8  call    ElValidateWin32_4
0x18000daad  test    eax, eax
0x18000daaf  jz      short loc_18000DAC7
0x18000dab1  test    ebx, ebx
0x18000dab3  jg      short loc_18000DABC
0x18000dab5  mov     edi, ebx
0x18000dab7  jmp     loc_18000DB9F
0x18000dabc  movzx   edi, bx
0x18000dabf  or      edi, r15d
0x18000dac2  jmp     loc_18000DB9F
0x18000dac7  cmp     esi, 2
0x18000daca  jz      short loc_18000DAEF
0x18000dacc  cmp     esi, 17h
0x18000dacf  jz      short loc_18000DADB
0x18000dad1  mov     edi, 80004001h
0x18000dad6  jmp     loc_18000DB9F
0x18000dadb  cmp     byte ptr [rbp+var_50], 0FFh
0x18000dadf  jz      loc_18000DB9F
0x18000dae5  mov     edi, 0C1100118h
0x18000daea  jmp     loc_18000DB9F
0x18000daef  lea     r8, [rbp+netlong]
0x18000daf3  mov     ecx, esi
0x18000daf5  lea     rdx, a224010; "224.0.1.0"
0x18000dafc  call    cs:__imp_?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)
0x18000db03  nop     dword ptr [rax+rax+00h]
0x18000db08  mov     ecx, eax
0x18000db0a  mov     r9d, 28Ch
0x18000db10  mov     ebx, eax
0x18000db12  call    ElValidateWin32_4
0x18000db17  test    eax, eax
0x18000db19  jnz     short loc_18000DAB1
0x18000db1b  lea     r8, [rbp+var_20]
0x18000db1f  mov     ecx, esi
0x18000db21  lea     rdx, a239255255255; "239.255.255.255"
0x18000db28  call    cs:__imp_?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)
0x18000db2f  nop     dword ptr [rax+rax+00h]
0x18000db34  mov     ecx, eax
0x18000db36  mov     r9d, 291h
0x18000db3c  mov     ebx, eax
0x18000db3e  call    ElValidateWin32_4
0x18000db43  test    eax, eax
0x18000db45  jnz     loc_18000DAB1
0x18000db4b  mov     ecx, [rbp+netlong]; netlong
0x18000db4e  call    cs:__imp_ntohl
0x18000db55  nop     dword ptr [rax+rax+00h]
0x18000db5a  mov     ecx, [rbp+var_50]; netlong
0x18000db5d  mov     ebx, eax
0x18000db5f  call    cs:__imp_ntohl
0x18000db66  nop     dword ptr [rax+rax+00h]
0x18000db6b  cmp     eax, ebx
0x18000db6d  jb      short loc_18000DB93
0x18000db6f  mov     ecx, [rbp+var_20]; netlong
0x18000db72  call    cs:__imp_ntohl
0x18000db79  nop     dword ptr [rax+rax+00h]
0x18000db7e  mov     ecx, [rbp+var_50]; netlong
0x18000db81  mov     ebx, eax
0x18000db83  call    cs:__imp_ntohl
0x18000db8a  nop     dword ptr [rax+rax+00h]
0x18000db8f  cmp     eax, ebx
0x18000db91  jbe     short loc_18000DB9F
0x18000db93  mov     edi, 0C1100117h
0x18000db98  jmp     short loc_18000DB9F
0x18000db9a  mov     edi, 80070057h
0x18000db9f  mov     eax, edi
0x18000dba1  mov     rcx, [rbp+var_8]
0x18000dba5  xor     rcx, rsp; StackCookie
0x18000dba8  call    __security_check_cookie
0x18000dbad  mov     rbx, [rsp+70h+arg_10]
0x18000dbb5  add     rsp, 70h
0x18000dbb9  pop     r15
0x18000dbbb  pop     r14
0x18000dbbd  pop     rdi
0x18000dbbe  pop     rsi
0x18000dbbf  pop     rbp
0x18000dbc0  retn
```
