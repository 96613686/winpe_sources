# WsImpersonateAndGetLogonId

- ea: `0x180002c20`
- end: `0x1800033b6`
- name: `WsImpersonateAndGetLogonId`
- size: `1942`
- prototype: `__int64 __fastcall(PLUID DestinationLuid)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x180002640`
- `0x180002890`
- `0x180003b00`
- `0x18002c5a8`

## callees

- `0x180002c20`
- `0x18001fbd0`
- `0x180031878`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180002d4e`
- `ntdll!RtlCopyLuid` at `0x180002d4e`
- `ntdll!NtOpenThreadToken` at `0x180002c9b`
- `ntdll!NtOpenThreadToken` at `0x180002c9b`
- `ntdll!RtlNtStatusToDosError` at `0x180002f2e`
- `ntdll!RtlNtStatusToDosError` at `0x1800030cf`
- `ntdll!RtlNtStatusToDosError` at `0x180002f2e`
- `ntdll!RtlNtStatusToDosError` at `0x1800030cf`
- `ntdll!NtClose` at `0x180002d5f`
- `ntdll!NtClose` at `0x180002d5f`
- `ntdll!NtQueryInformationToken` at `0x180002d23`
- `ntdll!NtQueryInformationToken` at `0x180002d23`
- `RPCRT4!RpcImpersonateClient` at `0x180002c63`
- `RPCRT4!RpcImpersonateClient` at `0x180002c63`
- `RPCRT4!RpcRevertToSelf` at `0x180002cc1`
- `RPCRT4!RpcRevertToSelf` at `0x180002cc1`

## pseudocode

```c
__int64 __fastcall WsImpersonateAndGetLogonId(PLUID DestinationLuid)
{
  RPC_STATUS v2; // eax
  int v3; // r8d
  int v4; // eax
  int v5; // edi
  unsigned int v6; // ebx
  RPC_STATUS v7; // eax
  int v8; // r8d
  int v10; // eax
  int v11; // edi
  ULONG v12; // eax
  ULONG v13; // eax
  void *TokenHandle; // [rsp+30h] [rbp-68h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-60h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17; // [rsp+70h] [rbp-28h]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v17 = 0;
  ReturnLength = 0;
  v2 = RpcImpersonateClient(0);
  if ( !v2 )
  {
    v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    v5 = v4;
    if ( !v4 )
      goto LABEL_8;
    if ( v4 == -2147483611 )
    {
      v6 = 0;
LABEL_5:
      v7 = RpcRevertToSelf();
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
            WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v8, (unsigned int)"unknown", 0, v7);
        }
        __fastfail(7u);
      }
      return v6;
    }
    if ( v4 <= -1073741531 )
    {
      if ( v4 != -1073741531 )
      {
        switch ( v4 )
        {
          case -1073741789:
            v6 = 2123;
            break;
          case -1073741727:
            v6 = 5;
            break;
          case -1073741726:
            v6 = 2202;
            break;
          case -1073741725:
            v6 = 2224;
            break;
          case -1073741724:
            v6 = 2221;
            break;
          case -1073741723:
            v6 = 2223;
            break;
          case -1073741722:
          case -1073741709:
            v6 = 2220;
            break;
          case -1073741721:
            v6 = 2236;
            break;
          case -1073741720:
            v6 = 2237;
            break;
          case -1073741716:
            v6 = 2245;
            break;
          case -1073741713:
            v6 = 2241;
            break;
          case -1073741712:
            v6 = 2240;
            break;
          case -1073741711:
            v6 = 2242;
            break;
          case -1073741604:
          case -1073741602:
            goto LABEL_61;
          case -1073741603:
            v6 = 2227;
            break;
          case -1073741596:
            v6 = 2247;
            break;
          case -1073741573:
            v6 = 2102;
            break;
          case -1073741561:
            v6 = 2401;
            break;
          case -1073741560:
            v6 = 2404;
            break;
          default:
            goto LABEL_57;
        }
        goto LABEL_5;
      }
LABEL_51:
      v6 = 2234;
      goto LABEL_7;
    }
    if ( v4 > -1073741495 )
    {
      switch ( v4 )
      {
        case -1073741433:
LABEL_61:
          v6 = 2226;
          goto LABEL_7;
        case -1073741421:
          v6 = 2239;
          goto LABEL_5;
        case -1073741261:
          v6 = 2453;
          goto LABEL_5;
      }
    }
    else
    {
      switch ( v4 )
      {
        case -1073741495:
          v6 = 2403;
          goto LABEL_5;
        case -1073741529:
          goto LABEL_51;
        case -1073741518:
          v6 = 2210;
          goto LABEL_5;
        case -1073741517:
          v6 = 2457;
          goto LABEL_5;
        case -1073741516:
          v6 = 2249;
          goto LABEL_5;
      }
    }
LABEL_57:
    v12 = RtlNtStatusToDosError(v4);
    v6 = 2140;
    if ( v12 != v5 )
      v6 = v12;
LABEL_7:
    if ( v5 < 0 )
      goto LABEL_5;
LABEL_8:
    v10 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    v11 = v10;
    if ( !v10 )
    {
      v6 = 0;
LABEL_12:
      RtlCopyLuid(DestinationLuid, (PLUID)TokenInformation + 1);
      goto LABEL_13;
    }
    if ( v10 == -2147483611 )
    {
      v6 = 0;
LABEL_13:
      NtClose(TokenHandle);
      goto LABEL_5;
    }
    if ( v10 <= -1073741531 )
    {
      if ( v10 != -1073741531 )
      {
        switch ( v10 )
        {
          case -1073741789:
            v6 = 2123;
            break;
          case -1073741727:
            v6 = 5;
            break;
          case -1073741726:
            v6 = 2202;
            break;
          case -1073741725:
            v6 = 2224;
            break;
          case -1073741724:
            v6 = 2221;
            break;
          case -1073741723:
            v6 = 2223;
            break;
          case -1073741722:
          case -1073741709:
            v6 = 2220;
            break;
          case -1073741721:
            v6 = 2236;
            break;
          case -1073741720:
            v6 = 2237;
            break;
          case -1073741716:
            v6 = 2245;
            break;
          case -1073741713:
            v6 = 2241;
            break;
          case -1073741712:
            v6 = 2240;
            break;
          case -1073741711:
            v6 = 2242;
            break;
          case -1073741604:
          case -1073741602:
            goto LABEL_102;
          case -1073741603:
            v6 = 2227;
            break;
          case -1073741596:
            v6 = 2247;
            break;
          case -1073741573:
            v6 = 2102;
            break;
          case -1073741561:
            v6 = 2401;
            break;
          case -1073741560:
            v6 = 2404;
            break;
          default:
            goto LABEL_98;
        }
        goto LABEL_13;
      }
LABEL_92:
      v6 = 2234;
      goto LABEL_14;
    }
    if ( v10 > -1073741495 )
    {
      switch ( v10 )
      {
        case -1073741433:
LABEL_102:
          v6 = 2226;
          goto LABEL_14;
        case -1073741421:
          v6 = 2239;
          goto LABEL_13;
        case -1073741261:
          v6 = 2453;
          goto LABEL_13;
      }
    }
    else
    {
      switch ( v10 )
      {
        case -1073741495:
          v6 = 2403;
          goto LABEL_13;
        case -1073741529:
          goto LABEL_92;
        case -1073741518:
          v6 = 2210;
          goto LABEL_13;
        case -1073741517:
          v6 = 2457;
          goto LABEL_13;
        case -1073741516:
          v6 = 2249;
          goto LABEL_13;
      }
    }
LABEL_98:
    v13 = RtlNtStatusToDosError(v10);
    v6 = 2140;
    if ( v13 != v11 )
      v6 = v13;
LABEL_14:
    if ( v11 < 0 )
      goto LABEL_13;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, (unsigned int)"unknown", 0, v2);
  }
  return 5;
}

```

## disassembly

```asm
0x180002c20  push    rbx
0x180002c22  push    rbp
0x180002c23  push    rsi
0x180002c24  sub     rsp, 80h
0x180002c2b  mov     rax, cs:__security_cookie
0x180002c32  xor     rax, rsp
0x180002c35  mov     [rsp+98h+var_20], rax
0x180002c3a  xorps   xmm0, xmm0
0x180002c3d  mov     rsi, rcx
0x180002c40  xor     ebp, ebp
0x180002c42  xor     eax, eax
0x180002c44  xor     ecx, ecx; BindingHandle
0x180002c46  mov     [rsp+98h+TokenHandle], rbp
0x180002c4b  movups  [rsp+98h+TokenInformation], xmm0
0x180002c50  mov     [rsp+98h+var_28], rax
0x180002c55  movups  [rsp+98h+var_48], xmm0
0x180002c5a  mov     [rsp+98h+var_60], ebp
0x180002c5e  movups  [rsp+98h+var_38], xmm0
0x180002c63  call    cs:__imp_RpcImpersonateClient
0x180002c6a  nop     dword ptr [rax+rax+00h]
0x180002c6f  test    eax, eax
0x180002c71  jnz     loc_180002D76
0x180002c77  mov     [rsp+98h+arg_8], rdi
0x180002c7f  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x180002c84  mov     r8b, 1; OpenAsSelf
0x180002c87  mov     [rsp+98h+arg_10], r14
0x180002c8f  mov     edx, 8; DesiredAccess
0x180002c94  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180002c9b  call    cs:__imp_NtOpenThreadToken
0x180002ca2  nop     dword ptr [rax+rax+00h]
0x180002ca7  lea     r14, __ImageBase
0x180002cae  mov     edi, eax
0x180002cb0  test    eax, eax
0x180002cb2  jz      short loc_180002D04
0x180002cb4  cmp     eax, 80000025h
0x180002cb9  jnz     loc_180002DBC
0x180002cbf  mov     ebx, ebp
0x180002cc1  call    cs:__imp_RpcRevertToSelf
0x180002cc8  nop     dword ptr [rax+rax+00h]
0x180002ccd  mov     r14, [rsp+98h+arg_10]
0x180002cd5  mov     rdi, [rsp+98h+arg_8]
0x180002cdd  test    eax, eax
0x180002cdf  jnz     loc_1800030FE
0x180002ce5  mov     eax, ebx
0x180002ce7  mov     rcx, [rsp+98h+var_20]
0x180002cec  xor     rcx, rsp; StackCookie
0x180002cef  call    __security_check_cookie
0x180002cf4  add     rsp, 80h
0x180002cfb  pop     rsi
0x180002cfc  pop     rbp
0x180002cfd  pop     rbx
0x180002cfe  retn
0x180002d00  test    edi, edi
0x180002d02  js      short loc_180002CC1
0x180002d04  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x180002d09  lea     rax, [rsp+98h+var_60]
0x180002d0e  mov     r9d, 38h ; '8'; TokenInformationLength
0x180002d14  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x180002d19  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180002d1e  mov     edx, 0Ah; TokenInformationClass
0x180002d23  call    cs:__imp_NtQueryInformationToken
0x180002d2a  nop     dword ptr [rax+rax+00h]
0x180002d2f  mov     edi, eax
0x180002d31  test    eax, eax
0x180002d33  jz      short loc_180002D44
0x180002d35  cmp     eax, 80000025h
0x180002d3a  jnz     loc_180002F5D
0x180002d40  mov     ebx, ebp
0x180002d42  jmp     short loc_180002D5A
0x180002d44  mov     ebx, ebp
0x180002d46  lea     rdx, [rsp+98h+TokenInformation+8]; SourceLuid
0x180002d4b  mov     rcx, rsi; DestinationLuid
0x180002d4e  call    cs:__imp_RtlCopyLuid
0x180002d55  nop     dword ptr [rax+rax+00h]
0x180002d5a  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x180002d5f  call    cs:__imp_NtClose
0x180002d66  nop     dword ptr [rax+rax+00h]
0x180002d6b  jmp     loc_180002CC1
0x180002d70  test    edi, edi
0x180002d72  js      short loc_180002D5A
0x180002d74  jmp     short loc_180002D46
0x180002d76  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180002d7d  lea     rdx, WPP_GLOBAL_Control
0x180002d84  cmp     rcx, rdx
0x180002d87  jz      short loc_180002DB2
0x180002d89  test    byte ptr [rcx+1Ch], 4
0x180002d8d  jz      short loc_180002DB2
0x180002d8f  cmp     byte ptr [rcx+19h], 1
0x180002d93  jb      short loc_180002DB2
0x180002d95  mov     rcx, [rcx+10h]
0x180002d99  lea     r9, aUnknown; "unknown"
0x180002da0  mov     [rsp+98h+var_70], eax
0x180002da4  mov     edx, 0Ah
0x180002da9  mov     dword ptr [rsp+98h+ReturnLength], ebp
0x180002dad  call    WPP_SF_sdL
0x180002db2  mov     eax, 5
0x180002db7  jmp     loc_180002CE7
0x180002dbc  cmp     edi, 0C0000125h
0x180002dc2  jg      loc_180002EAE
0x180002dc8  jz      loc_180002EF6
0x180002dce  add     eax, 3FFFFFDDh; switch 230 cases
0x180002dd3  cmp     eax, 0E5h
0x180002dd8  ja      def_180002DF4; jumptable 0000000180002DF4 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002dde  cdqe
0x180002de0  movzx   eax, ds:(byte_180003198 - 180000000h)[r14+rax]
0x180002de9  mov     ecx, ds:(jpt_180002DF4 - 180000000h)[r14+rax*4]
0x180002df1  add     rcx, r14
0x180002df4  jmp     rcx; switch jump
0x180002dfa  mov     ebx, 84Bh; jumptable 0000000180002DF4 case -1073741789
0x180002dff  jmp     loc_180002CC1
0x180002e04  mov     ebx, 961h; jumptable 0000000180002DF4 case -1073741561
0x180002e09  jmp     loc_180002CC1
0x180002e0e  mov     ebx, 964h; jumptable 0000000180002DF4 case -1073741560
0x180002e13  jmp     loc_180002CC1
0x180002e18  mov     ebx, 8C1h; jumptable 0000000180002DF4 case -1073741713
0x180002e1d  jmp     loc_180002CC1
0x180002e22  mov     ebx, 8C0h; jumptable 0000000180002DF4 case -1073741712
0x180002e27  jmp     loc_180002CC1
0x180002e2c  mov     ebx, 8C2h; jumptable 0000000180002DF4 case -1073741711
0x180002e31  jmp     loc_180002CC1
0x180002e36  mov     ebx, 836h; jumptable 0000000180002DF4 case -1073741573
0x180002e3b  jmp     loc_180002CC1
0x180002e40  mov     ebx, 8AFh; jumptable 0000000180002DF4 case -1073741723
0x180002e45  jmp     loc_180002CC1
0x180002e4a  mov     ebx, 8C7h; jumptable 0000000180002DF4 case -1073741596
0x180002e4f  jmp     loc_180002CC1
0x180002e54  mov     ebx, 89Ah; jumptable 0000000180002DF4 case -1073741726
0x180002e59  jmp     loc_180002CC1
0x180002e5e  mov     ebx, 8B3h; jumptable 0000000180002DF4 case -1073741603
0x180002e63  jmp     loc_180002CC1
0x180002e68  mov     ebx, 8BCh; jumptable 0000000180002DF4 case -1073741721
0x180002e6d  jmp     loc_180002CC1
0x180002e72  mov     ebx, 8BDh; jumptable 0000000180002DF4 case -1073741720
0x180002e77  jmp     loc_180002CC1
0x180002e7c  mov     ebx, 8ACh; jumptable 0000000180002DF4 cases -1073741722,-1073741709
0x180002e81  jmp     loc_180002CC1
0x180002e86  mov     ebx, 8B0h; jumptable 0000000180002DF4 case -1073741725
0x180002e8b  jmp     loc_180002CC1
0x180002e90  mov     ebx, 8ADh; jumptable 0000000180002DF4 case -1073741724
0x180002e95  jmp     loc_180002CC1
0x180002e9a  mov     ebx, 5; jumptable 0000000180002DF4 case -1073741727
0x180002e9f  jmp     loc_180002CC1
0x180002ea4  mov     ebx, 8C5h; jumptable 0000000180002DF4 case -1073741716
0x180002ea9  jmp     loc_180002CC1
0x180002eae  cmp     edi, 0C0000149h
0x180002eb4  jg      short loc_180002F0A
0x180002eb6  jz      short loc_180002F00
0x180002eb8  cmp     edi, 0C0000127h
0x180002ebe  jz      short loc_180002EF6
0x180002ec0  cmp     edi, 0C0000132h
0x180002ec6  jz      short loc_180002EEC
0x180002ec8  cmp     edi, 0C0000133h
0x180002ece  jz      short loc_180002EE2
0x180002ed0  cmp     edi, 0C0000134h
0x180002ed6  jnz     short def_180002DF4; jumptable 0000000180002DF4 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002ed8  mov     ebx, 8C9h
0x180002edd  jmp     loc_180002CC1
0x180002ee2  mov     ebx, 999h
0x180002ee7  jmp     loc_180002CC1
0x180002eec  mov     ebx, 8A2h
0x180002ef1  jmp     loc_180002CC1
0x180002ef6  mov     ebx, 8BAh
0x180002efb  jmp     loc_180002D00
0x180002f00  mov     ebx, 963h
0x180002f05  jmp     loc_180002CC1
0x180002f0a  cmp     edi, 0C0000187h
0x180002f10  jz      short loc_180002F53; jumptable 0000000180002DF4 cases -1073741604,-1073741602
0x180002f12  cmp     edi, 0C0000193h
0x180002f18  jz      short loc_180002F49
0x180002f1a  cmp     edi, 0C0000233h
0x180002f20  jnz     short def_180002DF4; jumptable 0000000180002DF4 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002f22  mov     ebx, 995h
0x180002f27  jmp     loc_180002CC1
0x180002f2c  mov     ecx, edi; jumptable 0000000180002DF4 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002f2e  call    cs:__imp_RtlNtStatusToDosError
0x180002f35  nop     dword ptr [rax+rax+00h]
0x180002f3a  cmp     eax, edi
0x180002f3c  mov     ebx, 85Ch
0x180002f41  cmovnz  ebx, eax
0x180002f44  jmp     loc_180002D00
0x180002f49  mov     ebx, 8BFh
0x180002f4e  jmp     loc_180002CC1
0x180002f53  mov     ebx, 8B2h; jumptable 0000000180002DF4 cases -1073741604,-1073741602
0x180002f58  jmp     loc_180002D00
0x180002f5d  cmp     edi, 0C0000125h
0x180002f63  jg      loc_18000304F
0x180002f69  jz      loc_180003097
0x180002f6f  add     eax, 3FFFFFDDh; switch 230 cases
0x180002f74  cmp     eax, 0E5h
0x180002f79  ja      def_180002F95; jumptable 0000000180002F95 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180002f7f  cdqe
0x180002f81  movzx   eax, ds:(byte_1800032D0 - 180000000h)[r14+rax]
0x180002f8a  mov     ecx, ds:(jpt_180002F95 - 180000000h)[r14+rax*4]
0x180002f92  add     rcx, r14
0x180002f95  jmp     rcx; switch jump
0x180002f9b  mov     ebx, 84Bh; jumptable 0000000180002F95 case -1073741789
0x180002fa0  jmp     loc_180002D5A
0x180002fa5  mov     ebx, 961h; jumptable 0000000180002F95 case -1073741561
0x180002faa  jmp     loc_180002D5A
0x180002faf  mov     ebx, 964h; jumptable 0000000180002F95 case -1073741560
0x180002fb4  jmp     loc_180002D5A
0x180002fb9  mov     ebx, 8C1h; jumptable 0000000180002F95 case -1073741713
0x180002fbe  jmp     loc_180002D5A
0x180002fc3  mov     ebx, 8C0h; jumptable 0000000180002F95 case -1073741712
0x180002fc8  jmp     loc_180002D5A
0x180002fcd  mov     ebx, 8C2h; jumptable 0000000180002F95 case -1073741711
0x180002fd2  jmp     loc_180002D5A
0x180002fd7  mov     ebx, 836h; jumptable 0000000180002F95 case -1073741573
0x180002fdc  jmp     loc_180002D5A
0x180002fe1  mov     ebx, 8AFh; jumptable 0000000180002F95 case -1073741723
0x180002fe6  jmp     loc_180002D5A
0x180002feb  mov     ebx, 8C7h; jumptable 0000000180002F95 case -1073741596
0x180002ff0  jmp     loc_180002D5A
0x180002ff5  mov     ebx, 89Ah; jumptable 0000000180002F95 case -1073741726
0x180002ffa  jmp     loc_180002D5A
0x180002fff  mov     ebx, 8B3h; jumptable 0000000180002F95 case -1073741603
0x180003004  jmp     loc_180002D5A
0x180003009  mov     ebx, 8BCh; jumptable 0000000180002F95 case -1073741721
0x18000300e  jmp     loc_180002D5A
0x180003013  mov     ebx, 8BDh; jumptable 0000000180002F95 case -1073741720
0x180003018  jmp     loc_180002D5A
0x18000301d  mov     ebx, 8ACh; jumptable 0000000180002F95 cases -1073741722,-1073741709
0x180003022  jmp     loc_180002D5A
0x180003027  mov     ebx, 8B0h; jumptable 0000000180002F95 case -1073741725
0x18000302c  jmp     loc_180002D5A
0x180003031  mov     ebx, 8ADh; jumptable 0000000180002F95 case -1073741724
0x180003036  jmp     loc_180002D5A
0x18000303b  mov     ebx, 5; jumptable 0000000180002F95 case -1073741727
0x180003040  jmp     loc_180002D5A
0x180003045  mov     ebx, 8C5h; jumptable 0000000180002F95 case -1073741716
0x18000304a  jmp     loc_180002D5A
0x18000304f  cmp     edi, 0C0000149h
0x180003055  jg      short loc_1800030AB
0x180003057  jz      short loc_1800030A1
0x180003059  cmp     edi, 0C0000127h
0x18000305f  jz      short loc_180003097
0x180003061  cmp     edi, 0C0000132h
0x180003067  jz      short loc_18000308D
0x180003069  cmp     edi, 0C0000133h
0x18000306f  jz      short loc_180003083
0x180003071  cmp     edi, 0C0000134h
0x180003077  jnz     short def_180002F95; jumptable 0000000180002F95 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x180003079  mov     ebx, 8C9h
0x18000307e  jmp     loc_180002D5A
0x180003083  mov     ebx, 999h
0x180003088  jmp     loc_180002D5A
0x18000308d  mov     ebx, 8A2h
0x180003092  jmp     loc_180002D5A
0x180003097  mov     ebx, 8BAh
0x18000309c  jmp     loc_180002D70
0x1800030a1  mov     ebx, 963h
0x1800030a6  jmp     loc_180002D5A
0x1800030ab  cmp     edi, 0C0000187h
0x1800030b1  jz      short loc_1800030F4; jumptable 0000000180002F95 cases -1073741604,-1073741602
0x1800030b3  cmp     edi, 0C0000193h
0x1800030b9  jz      short loc_1800030EA
0x1800030bb  cmp     edi, 0C0000233h
0x1800030c1  jnz     short def_180002F95; jumptable 0000000180002F95 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x1800030c3  mov     ebx, 995h
0x1800030c8  jmp     loc_180002D5A
0x1800030cd  mov     ecx, edi; jumptable 0000000180002F95 default case, cases -1073741788--1073741728,-1073741719--1073741717,-1073741715,-1073741714,-1073741710,-1073741708--1073741605,-1073741601--1073741597,-1073741595--1073741574,-1073741572--1073741562
0x1800030cf  call    cs:__imp_RtlNtStatusToDosError
0x1800030d6  nop     dword ptr [rax+rax+00h]
0x1800030db  cmp     eax, edi
0x1800030dd  mov     ebx, 85Ch
0x1800030e2  cmovnz  ebx, eax
0x1800030e5  jmp     loc_180002D70
0x1800030ea  mov     ebx, 8BFh
0x1800030ef  jmp     loc_180002D5A
0x1800030f4  mov     ebx, 8B2h; jumptable 0000000180002F95 cases -1073741604,-1073741602
0x1800030f9  jmp     loc_180002D70
0x1800030fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180003105  lea     rdx, WPP_GLOBAL_Control
0x18000310c  cmp     rcx, rdx
0x18000310f  jz      short loc_18000313A
0x180003111  test    byte ptr [rcx+1Ch], 4
0x180003115  jz      short loc_18000313A
0x180003117  cmp     byte ptr [rcx+19h], 1
0x18000311b  jb      short loc_18000313A
0x18000311d  mov     rcx, [rcx+10h]
0x180003121  lea     r9, aUnknown; "unknown"
0x180003128  mov     [rsp+98h+var_70], eax
0x18000312c  mov     edx, 0Bh
0x180003131  mov     dword ptr [rsp+98h+ReturnLength], ebp
0x180003135  call    WPP_SF_sdL
0x18000313a  mov     ecx, 7
0x18000313f  int     29h; Win8: RtlFailFast(ecx)
0x180003141  jmp     loc_180002CE5
```
