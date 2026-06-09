# VPNIKEIOCTLHelper::UpdateVPNTrafficSelectorsHelper(_CONNECTION_ID_,unsigned __int64,ulong,_VPN_TRAFFIC_SELECTOR_ *,ulong,_VPN_TRAFFIC_SELECTOR_ *,uchar,uchar)

- ea: `0x18000bc98`
- end: `0x18000bf91`
- name: `?UpdateVPNTrafficSelectorsHelper@VPNIKEIOCTLHelper@@IEAAKT_CONNECTION_ID_@@_KKPEAU_VPN_TRAFFIC_SELECTOR_@@K2EE@Z`
- size: `761`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned int, __int64, char, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b430`
- `0x18000bb80`

## callees

- `0x180007590`
- `0x1800077bc`
- `0x18000a9f0`
- `0x18000bc98`
- `0x18000c020`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bf2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bd83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000bd83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf21`

## string_xrefs

- `0x18000bebf`: `IOCTL_AGILEVPN_UPDATE_TUNNEL_TS failed %d`
- `0x18000beea`: `IOCTL_AGILEVPN_UPDATE_CONFIGURED_TS failed %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VPNIKEIOCTLHelper::UpdateVPNTrafficSelectorsHelper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        char a8,
        char a9)
{
  PVOID *v11; // rdx
  unsigned int v12; // r15d
  unsigned int v13; // r12d
  HANDLE ProcessHeap; // rax
  unsigned int v15; // edi
  _DWORD *v16; // rax
  VPNIKEIOCTLHelper *v17; // rcx
  _DWORD *v18; // rsi
  unsigned int v19; // ebx
  unsigned int v20; // edi
  _DWORD *v21; // rdi
  unsigned int v22; // ebx
  __int64 (__fastcall *v23)(__int64, __int64, _DWORD *, _QWORD); // rax
  unsigned int v24; // eax
  HANDLE v25; // rax
  _DWORD *v28; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v11 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v11) = a9;
    WPP_SF_IIddcc(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, a3, a3, a2, a4, a4, a8, a9);
  }
  v30 = 0;
  v12 = 48;
  memset_0(v31, 0, sizeof(v31));
  v13 = a6;
  if ( !a8 )
    v12 = 44 * (a4 + a6) + 48;
  ProcessHeap = GetProcessHeap();
  v15 = 8;
  v16 = HeapAlloc(ProcessHeap, 8u, v12);
  v28 = v16;
  v18 = v16;
  if ( v16 )
  {
    *(_QWORD *)v16 = a2;
    v19 = 8;
    *((_BYTE *)v16 + 8) = a8;
    v16[4] = v12 - 16;
    *((_QWORD *)v16 + 3) = a3;
    v16[8] = a4;
    v16[10] = a6;
    if ( a5 )
    {
      v20 = 0;
      v16[9] = 32;
      if ( a4 )
      {
        do
        {
          VPNIKEIOCTLHelper::ConvertVPNTSToAgileVPNTS(
            v17,
            (struct _AGILEVPN_TRAFFIC_SELECTOR *)&v18[11 * v20 + 12],
            (struct _VPN_TRAFFIC_SELECTOR_ *)(a5 + 52LL * v20));
          v19 += 11;
          ++v20;
        }
        while ( v20 < a4 );
        v13 = a6;
      }
    }
    if ( a7 )
    {
      v18[11] = v19 * 4;
      v21 = &v18[v19 + 4];
      v22 = 0;
      if ( v13 )
      {
        do
        {
          VPNIKEIOCTLHelper::ConvertVPNTSToAgileVPNTS(
            v17,
            (struct _AGILEVPN_TRAFFIC_SELECTOR *)&v21[11 * v22],
            (struct _VPN_TRAFFIC_SELECTOR_ *)(a7 + 52LL * v22));
          ++v22;
        }
        while ( v22 < v13 );
        v18 = v28;
      }
    }
    v23 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *, _QWORD))(*(_QWORD *)a1 + 72LL);
    if ( a9 )
    {
      v24 = v23(a1, 1212440, v18, v12);
      v15 = v24;
      if ( v24 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v30, L"IOCTL_AGILEVPN_UPDATE_TUNNEL_TS failed %d", v24);
        goto LABEL_26;
      }
    }
    else
    {
      v15 = v23(a1, 1212444, v18, v12);
      if ( v15 && (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v30) = 0;
        FormatRRASErrorString(&v30, L"IOCTL_AGILEVPN_UPDATE_CONFIGURED_TS failed %d", v15);
LABEL_26:
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v30);
      }
    }
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v18);
    goto LABEL_29;
  }
  if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(&v30, L"VPNIKE_MALLOC failed with error %d", 8);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v30);
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids, v15);
  }
  return v15;
}

```

## disassembly

```asm
0x18000bc98  push    rbp
0x18000bc9a  push    rbx
0x18000bc9b  push    rsi
0x18000bc9c  push    rdi
0x18000bc9d  push    r12
0x18000bc9f  push    r13
0x18000bca1  push    r14
0x18000bca3  push    r15
0x18000bca5  lea     rbp, [rsp-798h]
0x18000bcad  sub     rsp, 898h
0x18000bcb4  mov     rax, cs:__security_cookie
0x18000bcbb  xor     rax, rsp
0x18000bcbe  mov     [rbp+7D0h+var_50], rax
0x18000bcc5  mov     [rsp+8D0h+var_860], rcx
0x18000bcca  mov     rax, r8
0x18000bccd  mov     rcx, [rbp+7D0h+arg_20]
0x18000bcd4  mov     r14d, r9d
0x18000bcd7  mov     [rsp+8D0h+var_880], rcx
0x18000bcdc  mov     rbx, rdx
0x18000bcdf  mov     rcx, [rbp+7D0h+arg_30]
0x18000bce6  mov     [rsp+8D0h+var_878], rcx
0x18000bceb  mov     [rsp+8D0h+var_870], rax
0x18000bcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcf7  lea     rdx, WPP_GLOBAL_Control
0x18000bcfe  mov     r13b, [rbp+7D0h+arg_38]
0x18000bd05  cmp     rcx, rdx
0x18000bd08  jz      short loc_18000BD40
0x18000bd0a  test    byte ptr [rcx+1Ch], 1
0x18000bd0e  jz      short loc_18000BD40
0x18000bd10  cmp     byte ptr [rcx+19h], 6
0x18000bd14  jb      short loc_18000BD40
0x18000bd16  mov     dl, [rbp+7D0h+arg_40]
0x18000bd1c  mov     rcx, [rcx+10h]
0x18000bd20  mov     [rsp+8D0h+var_890], dl
0x18000bd24  mov     [rsp+8D0h+var_898], r13b
0x18000bd29  mov     [rsp+8D0h+var_8A0], r9d
0x18000bd2e  mov     [rsp+8D0h+var_8A8], r9d
0x18000bd33  mov     r9, rax
0x18000bd36  mov     [rsp+8D0h+var_8B0], rbx
0x18000bd3b  call    WPP_SF_IIddcc
0x18000bd40  xor     eax, eax
0x18000bd42  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18000bd46  xor     edx, edx; Val
0x18000bd48  mov     [rbp+7D0h+var_850], eax
0x18000bd4b  mov     r8d, 7FCh; Size
0x18000bd51  lea     r15d, [rax+30h]
0x18000bd55  call    memset_0
0x18000bd5a  mov     r12d, [rbp+7D0h+arg_28]
0x18000bd61  test    r13b, r13b
0x18000bd64  jnz     short loc_18000BD70
0x18000bd66  lea     eax, [r14+r12]
0x18000bd6a  imul    ecx, eax, 2Ch ; ','
0x18000bd6d  add     r15d, ecx
0x18000bd70  call    cs:__imp_GetProcessHeap
0x18000bd76  mov     edi, 8
0x18000bd7b  mov     r8d, r15d; dwBytes
0x18000bd7e  mov     rcx, rax; hHeap
0x18000bd81  mov     edx, edi; dwFlags
0x18000bd83  call    cs:__imp_HeapAlloc
0x18000bd89  mov     [rsp+8D0h+var_868], rax
0x18000bd8e  mov     rsi, rax
0x18000bd91  test    rax, rax
0x18000bd94  jnz     short loc_18000BDE3
0x18000bd96  test    cs:byte_1800AA941, 4
0x18000bd9d  jz      loc_18000BF35
0x18000bda3  mov     r8d, edi
0x18000bda6  mov     word ptr [rbp+7D0h+var_850], ax
0x18000bdaa  lea     rdx, aVpnikeMallocFa; "VPNIKE_MALLOC failed with error %d"
0x18000bdb1  lea     rcx, [rbp+7D0h+var_850]
0x18000bdb5  call    FormatRRASErrorString
0x18000bdba  test    cs:byte_1800AA941, 4
0x18000bdc1  jz      loc_18000BF35
0x18000bdc7  lea     r8, [rbp+7D0h+var_850]
0x18000bdcb  lea     rdx, RasVpnIkeTraceError
0x18000bdd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bdd9  call    McTemplateU0z_EventWriteTransfer
0x18000bdde  jmp     loc_18000BF35
0x18000bde3  cmp     [rsp+8D0h+var_880], 0
0x18000bde9  mov     [rax], rbx
0x18000bdec  mov     ebx, 20h ; ' '
0x18000bdf1  mov     [rax+8], r13b
0x18000bdf5  lea     eax, [r15-10h]
0x18000bdf9  mov     [rsi+10h], eax
0x18000bdfc  mov     rax, [rsp+8D0h+var_870]
0x18000be01  mov     [rsi+18h], rax
0x18000be05  mov     [rsi+20h], r14d
0x18000be09  mov     [rsi+28h], r12d
0x18000be0d  jz      short loc_18000BE48
0x18000be0f  xor     edi, edi
0x18000be11  mov     [rsi+24h], ebx
0x18000be14  lea     r13, [rsi+30h]
0x18000be18  test    r14d, r14d
0x18000be1b  jz      short loc_18000BE48
0x18000be1d  mov     r12, [rsp+8D0h+var_880]
0x18000be22  mov     eax, edi
0x18000be24  imul    r8, rax, 34h ; '4'
0x18000be28  imul    rdx, rax, 2Ch ; ','
0x18000be2c  add     r8, r12; struct _VPN_TRAFFIC_SELECTOR_ *
0x18000be2f  add     rdx, r13; struct _AGILEVPN_TRAFFIC_SELECTOR *
0x18000be32  call    ?ConvertVPNTSToAgileVPNTS@VPNIKEIOCTLHelper@@IEAAXAEAU_AGILEVPN_TRAFFIC_SELECTOR@@AEAU_VPN_TRAFFIC_SELECTOR_@@@Z; VPNIKEIOCTLHelper::ConvertVPNTSToAgileVPNTS(_AGILEVPN_TRAFFIC_SELECTOR &,_VPN_TRAFFIC_SELECTOR_ &)
0x18000be37  add     ebx, 2Ch ; ','
0x18000be3a  inc     edi
0x18000be3c  cmp     edi, r14d
0x18000be3f  jb      short loc_18000BE22
0x18000be41  mov     r12d, [rbp+7D0h+arg_28]
0x18000be48  cmp     [rsp+8D0h+var_878], 0
0x18000be4e  jz      short loc_18000BE89
0x18000be50  mov     edi, ebx
0x18000be52  add     rdi, 10h
0x18000be56  mov     [rsi+2Ch], ebx
0x18000be59  add     rdi, rsi
0x18000be5c  xor     ebx, ebx
0x18000be5e  test    r12d, r12d
0x18000be61  jz      short loc_18000BE89
0x18000be63  mov     rsi, [rsp+8D0h+var_878]
0x18000be68  mov     eax, ebx
0x18000be6a  imul    r8, rax, 34h ; '4'
0x18000be6e  imul    rdx, rax, 2Ch ; ','
0x18000be72  add     r8, rsi; struct _VPN_TRAFFIC_SELECTOR_ *
0x18000be75  add     rdx, rdi; struct _AGILEVPN_TRAFFIC_SELECTOR *
0x18000be78  call    ?ConvertVPNTSToAgileVPNTS@VPNIKEIOCTLHelper@@IEAAXAEAU_AGILEVPN_TRAFFIC_SELECTOR@@AEAU_VPN_TRAFFIC_SELECTOR_@@@Z; VPNIKEIOCTLHelper::ConvertVPNTSToAgileVPNTS(_AGILEVPN_TRAFFIC_SELECTOR &,_VPN_TRAFFIC_SELECTOR_ &)
0x18000be7d  inc     ebx
0x18000be7f  cmp     ebx, r12d
0x18000be82  jb      short loc_18000BE68
0x18000be84  mov     rsi, [rsp+8D0h+var_868]
0x18000be89  cmp     [rbp+7D0h+arg_40], 0
0x18000be90  mov     r9d, r15d
0x18000be93  mov     rcx, [rsp+8D0h+var_860]
0x18000be98  mov     r8, rsi
0x18000be9b  mov     rax, [rcx]
0x18000be9e  mov     rax, [rax+48h]
0x18000bea2  jz      short loc_18000BECF
0x18000bea4  mov     edx, 128018h
0x18000bea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beae  mov     edi, eax
0x18000beb0  test    eax, eax
0x18000beb2  jz      short loc_18000BF21
0x18000beb4  test    cs:byte_1800AA941, 4
0x18000bebb  jz      short loc_18000BF21
0x18000bebd  xor     ecx, ecx
0x18000bebf  lea     rdx, aIoctlAgilevpnU_1; "IOCTL_AGILEVPN_UPDATE_TUNNEL_TS failed "...
0x18000bec6  mov     word ptr [rbp+7D0h+var_850], cx
0x18000beca  mov     r8d, eax
0x18000becd  jmp     short loc_18000BEF8
0x18000becf  mov     edx, 12801Ch
0x18000bed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bed9  mov     edi, eax
0x18000bedb  test    eax, eax
0x18000bedd  jz      short loc_18000BF21
0x18000bedf  test    cs:byte_1800AA941, 4
0x18000bee6  jz      short loc_18000BF21
0x18000bee8  xor     eax, eax
0x18000beea  lea     rdx, aIoctlAgilevpnU; "IOCTL_AGILEVPN_UPDATE_CONFIGURED_TS fai"...
0x18000bef1  mov     word ptr [rbp+7D0h+var_850], ax
0x18000bef5  mov     r8d, edi
0x18000bef8  lea     rcx, [rbp+7D0h+var_850]
0x18000befc  call    FormatRRASErrorString
0x18000bf01  test    cs:byte_1800AA941, 4
0x18000bf08  jz      short loc_18000BF21
0x18000bf0a  lea     r8, [rbp+7D0h+var_850]
0x18000bf0e  lea     rdx, RasVpnIkeTraceError
0x18000bf15  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bf1c  call    McTemplateU0z_EventWriteTransfer
0x18000bf21  call    cs:__imp_GetProcessHeap
0x18000bf27  mov     r8, rsi; lpMem
0x18000bf2a  xor     edx, edx; dwFlags
0x18000bf2c  mov     rcx, rax; hHeap
0x18000bf2f  call    cs:__imp_HeapFree
0x18000bf35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf3c  lea     rax, WPP_GLOBAL_Control
0x18000bf43  cmp     rcx, rax
0x18000bf46  jz      short loc_18000BF6C
0x18000bf48  test    byte ptr [rcx+1Ch], 1
0x18000bf4c  jz      short loc_18000BF6C
0x18000bf4e  cmp     byte ptr [rcx+19h], 6
0x18000bf52  jb      short loc_18000BF6C
0x18000bf54  mov     rcx, [rcx+10h]
0x18000bf58  lea     r8, WPP_45d935e7e0d7382daf50f1a345cf85df_Traceguids
0x18000bf5f  mov     edx, 19h
0x18000bf64  mov     r9d, edi
0x18000bf67  call    WPP_SF_d
0x18000bf6c  mov     eax, edi
0x18000bf6e  mov     rcx, [rbp+7D0h+var_50]
0x18000bf75  xor     rcx, rsp; StackCookie
0x18000bf78  call    __security_check_cookie
0x18000bf7d  add     rsp, 898h
0x18000bf84  pop     r15
0x18000bf86  pop     r14
0x18000bf88  pop     r13
0x18000bf8a  pop     r12
0x18000bf8c  pop     rdi
0x18000bf8d  pop     rsi
0x18000bf8e  pop     rbx
0x18000bf8f  pop     rbp
0x18000bf90  retn
```
