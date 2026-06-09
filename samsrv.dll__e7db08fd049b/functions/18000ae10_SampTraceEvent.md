# SampTraceEvent

- ea: `0x18000ae10`
- end: `0x18000b13f`
- name: `SampTraceEvent`
- size: `815`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `54`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001510`
- `0x1800024e0`
- `0x1800026e0`
- `0x1800031c0`
- `0x180009030`
- `0x18000a570`
- `0x18000b150`
- `0x180012160`
- `0x180012d60`
- `0x180013370`
- `0x180013710`
- `0x180014ea0`
- `0x180015430`
- `0x180015e90`
- `0x18001a0f0`
- `0x18001dc50`
- `0x180022db0`
- `0x180025dd0`
- `0x1800291c0`
- `0x180035920`
- `0x180035b60`
- `0x180035ec0`
- `0x1800362f0`
- `0x1800365c0`
- `0x180036700`
- `0x180036b00`
- `0x180036f40`
- `0x1800521c0`
- `0x180052640`
- `0x1800559a0`
- `0x180055cc0`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x180058a50`
- `0x180058bb0`
- `0x180058db0`
- `0x180058f40`
- `0x1800591b0`
- `0x1800641c0`
- `0x180064380`
- `0x1800647e0`
- `0x180064a20`
- `0x180064b60`
- `0x180064e80`
- `0x180065020`
- `0x180065490`
- `0x18008cd00`
- `0x1800952a0`
- `0x180095370`

## callees

- `0x18000ae10`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x180053030`
- `0x180073ce4`
- `0x18008ed40`
- `0x18008f330`

## import_xrefs

- `ntdll!EtwLogTraceEvent` at `0x18000b0a5`
- `ntdll!EtwLogTraceEvent` at `0x18000b0a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b106`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000afc1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000afc1`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000afd6`
- `RPCRT4!RpcBindingServerFromClient` at `0x18000afd6`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000afe8`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000afe8`
- `RPCRT4!RpcStringBindingParseW` at `0x18000b00c`
- `RPCRT4!RpcStringBindingParseW` at `0x18000b00c`
- `RPCRT4!RpcBindingFree` at `0x18000b018`
- `RPCRT4!RpcBindingFree` at `0x18000b018`
- `RPCRT4!RpcStringFreeW` at `0x18000b120`
- `RPCRT4!RpcStringFreeW` at `0x18000b134`
- `RPCRT4!RpcStringFreeW` at `0x18000b120`
- `RPCRT4!RpcStringFreeW` at `0x18000b134`

## pseudocode

```c
RPC_STATUS __fastcall SampTraceEvent(int a1, unsigned int a2, char a3)
{
  __int64 v3; // rsi
  PSID *v4; // rbx
  RPC_STATUS result; // eax
  int CurrentOwnerAndPrimaryGroup; // eax
  RPC_STATUS v8; // edi
  RPC_WSTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  unsigned int v13; // eax
  RPC_WSTR NetworkAddr; // [rsp+30h] [rbp-89h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-81h] BYREF
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-79h] BYREF
  int v17; // [rsp+48h] [rbp-71h] BYREF
  PSID *v18; // [rsp+50h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+58h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-59h] BYREF
  __int128 v21; // [rsp+70h] [rbp-49h] BYREF
  __int128 v22; // [rsp+80h] [rbp-39h]
  __int128 v23; // [rsp+90h] [rbp-29h]
  __int128 v24; // [rsp+A0h] [rbp-19h]
  __int128 v25; // [rsp+B0h] [rbp-9h]
  __int128 v26; // [rsp+C0h] [rbp+7h]
  __int128 v27; // [rsp+D0h] [rbp+17h]

  v3 = a2;
  ServerBinding = 0;
  hMem = 0;
  StringSid = 0;
  StringBinding = 0;
  v4 = 0;
  v18 = 0;
  NetworkAddr = 0;
  v17 = 1;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  result = a1 - 1;
  if ( a1 == 1 )
  {
    if ( (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 1) != 0 )
      result = WPP_SF_s(
                 *(_QWORD *)&WPP_GLOBAL_Control[1].Length,
                 14,
                 WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids,
                 (&off_1800C3458)[2 * a2]);
  }
  else if ( a1 == 2 && (BYTE4(WPP_GLOBAL_Control[1].Buffer) & 1) != 0 )
  {
    result = WPP_SF_sD(
               *(_QWORD *)&WPP_GLOBAL_Control[1].Length,
               15,
               (unsigned int)WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids,
               (unsigned int)(&off_1800C3458)[2 * a2],
               a3);
  }
  if ( SampEventTraceFlag )
  {
    memset_0(&v21, 0, 0x70u);
    BYTE4(v21) = a1;
    WORD3(v21) = 1;
    HIDWORD(v23) = 1703936;
    *((_QWORD *)&v22 + 1) = (&SampTraceGuids)[2 * v3];
    LOWORD(v21) = 48;
    if ( SampTraceLogEventInDetail && a1 == 1 )
    {
      if ( (SampQueryCapabilities(0, 0) & 5) == 1
        || (CurrentOwnerAndPrimaryGroup = SampGetCurrentOwnerAndPrimaryGroup((HLOCAL *)&v18, &hMem),
            v4 = v18,
            CurrentOwnerAndPrimaryGroup < 0)
        || !ConvertSidToStringSidW(*v18, &StringSid) )
      {
        StringSid = L"Not Available";
      }
      if ( RpcBindingServerFromClient(0, &ServerBinding) )
        goto LABEL_20;
      v8 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
      if ( !v8 )
        v8 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
      RpcBindingFree(&ServerBinding);
      if ( v8 )
      {
LABEL_20:
        v9 = L"Not Available";
        NetworkAddr = L"Not Available";
      }
      else
      {
        v9 = NetworkAddr;
      }
      *(_QWORD *)&v24 = L"SAM";
      v10 = -1;
      DWORD2(v24) = 8;
      *(_QWORD *)&v25 = &v17;
      v11 = -1;
      DWORD2(v25) = 4;
      do
        v12 = StringSid[++v11] == 0;
      while ( !v12 );
      *(_QWORD *)&v26 = StringSid;
      DWORD2(v26) = 2 * v11 + 2;
      do
        v12 = v9[++v10] == 0;
      while ( !v12 );
      LOWORD(v21) = v21 + 64;
      DWORD2(v27) = 2 * v10 + 2;
      *(_QWORD *)&v27 = v9;
    }
    v13 = EtwLogTraceEvent(SampTraceLoggerHandle, &v21);
    if ( v13
      && (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 16, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids, v13);
    }
    if ( v4 )
      LocalFree(v4);
    if ( hMem )
      LocalFree(hMem);
    if ( StringSid && L"Not Available" != StringSid )
      LocalFree(StringSid);
    result = (int)NetworkAddr;
    if ( NetworkAddr && L"Not Available" != NetworkAddr )
      result = RpcStringFreeW(&NetworkAddr);
    if ( StringBinding )
      return RpcStringFreeW(&StringBinding);
  }
  return result;
}

```

## disassembly

```asm
0x18000ae10  mov     [rsp-8+arg_10], rbx
0x18000ae15  mov     [rsp-8+arg_18], rsi
0x18000ae1a  push    rbp
0x18000ae1b  push    rdi
0x18000ae1c  push    r12
0x18000ae1e  push    r14
0x18000ae20  push    r15
0x18000ae22  lea     rbp, [rsp-37h]
0x18000ae27  sub     rsp, 0F0h
0x18000ae2e  mov     rax, cs:__security_cookie
0x18000ae35  xor     rax, rsp
0x18000ae38  mov     [rbp+57h+var_30], rax
0x18000ae3c  xor     r14d, r14d
0x18000ae3f  mov     esi, edx
0x18000ae41  xorps   xmm0, xmm0
0x18000ae44  mov     [rbp+57h+ServerBinding], r14
0x18000ae48  mov     r15d, 1
0x18000ae4e  mov     [rbp+57h+hMem], r14
0x18000ae52  mov     eax, ecx
0x18000ae54  mov     [rsp+110h+StringSid], r14
0x18000ae59  mov     [rbp+57h+StringBinding], r14
0x18000ae5d  mov     ebx, r14d
0x18000ae60  mov     [rbp+57h+var_C0], rbx
0x18000ae64  mov     edi, ecx
0x18000ae66  mov     [rsp+110h+NetworkAddr], r14
0x18000ae6b  lea     r12, __ImageBase
0x18000ae72  mov     [rbp+57h+var_C8], r15d
0x18000ae76  movups  [rbp+57h+var_A0], xmm0
0x18000ae7a  movups  [rbp+57h+var_90], xmm0
0x18000ae7e  movups  [rbp+57h+var_80], xmm0
0x18000ae82  movups  [rbp+57h+var_70], xmm0
0x18000ae86  movups  [rbp+57h+var_60], xmm0
0x18000ae8a  movups  [rbp+57h+var_50], xmm0
0x18000ae8e  movups  [rbp+57h+var_40], xmm0
0x18000ae92  sub     eax, r15d
0x18000ae95  jz      short loc_18000AED0
0x18000ae97  cmp     eax, r15d
0x18000ae9a  jz      short loc_18000AF02
0x18000ae9c  cmp     cs:?SampEventTraceFlag@@3KA, ebx; ulong SampEventTraceFlag
0x18000aea2  jnz     loc_18000AF3C
0x18000aea8  mov     rcx, [rbp+57h+var_30]
0x18000aeac  xor     rcx, rsp; StackCookie
0x18000aeaf  call    __security_check_cookie
0x18000aeb4  lea     r11, [rsp+110h+var_20]
0x18000aebc  mov     rbx, [r11+40h]
0x18000aec0  mov     rsi, [r11+48h]
0x18000aec4  mov     rsp, r11
0x18000aec7  pop     r15
0x18000aec9  pop     r14
0x18000aecb  pop     r12
0x18000aecd  pop     rdi
0x18000aece  pop     rbp
0x18000aecf  retn
0x18000aed0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aed7  test    [rcx+1Ch], r15b
0x18000aedb  jz      short loc_18000AE9C
0x18000aedd  mov     rcx, [rcx+10h]
0x18000aee1  lea     r8, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids
0x18000aee8  mov     r9, rsi
0x18000aeeb  mov     edx, 0Eh
0x18000aef0  add     r9, r9
0x18000aef3  mov     r9, ds:rva off_1800C3458[r12+r9*8]; "SampConnect" ...
0x18000aefb  call    WPP_SF_s
0x18000af00  jmp     short loc_18000AE9C
0x18000af02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af09  test    [rcx+1Ch], r15b
0x18000af0d  jz      short loc_18000AE9C
0x18000af0f  mov     rcx, [rcx+10h]
0x18000af13  mov     r9, rsi
0x18000af16  add     r9, r9
0x18000af19  mov     dword ptr [rsp+110h+Endpoint], r8d
0x18000af1e  mov     edx, 0Fh
0x18000af23  lea     r8, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids
0x18000af2a  mov     r9, ds:rva off_1800C3458[r12+r9*8]; "SampConnect" ...
0x18000af32  call    WPP_SF_sD
0x18000af37  jmp     loc_18000AE9C
0x18000af3c  xor     edx, edx; Val
0x18000af3e  lea     rcx, [rbp+57h+var_A0]; void *
0x18000af42  mov     r8d, 70h ; 'p'; Size
0x18000af48  call    memset_0
0x18000af4d  mov     rax, rsi
0x18000af50  mov     byte ptr [rbp+57h+var_A0+4], dil
0x18000af54  add     rax, rax
0x18000af57  mov     word ptr [rbp+57h+var_A0+6], r15w
0x18000af5c  cmp     cs:?SampTraceLogEventInDetail@@3EA, bl; uchar SampTraceLogEventInDetail
0x18000af62  lea     rsi, aNotAvailable; "Not Available"
0x18000af69  mov     dword ptr [rbp+57h+var_80+0Ch], 1A0000h
0x18000af70  mov     rax, rva ?SampTraceGuids@@3PAU_TRACE_GUID_REGISTRATION@@A[r12+rax*8]; _TRACE_GUID_REGISTRATION near * SampTraceGuids ...
0x18000af78  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000af7c  mov     eax, 30h ; '0'
0x18000af81  mov     word ptr [rbp+57h+var_A0], ax
0x18000af85  jz      loc_18000B09A
0x18000af8b  cmp     edi, r15d
0x18000af8e  jnz     loc_18000B09A
0x18000af94  xor     edx, edx
0x18000af96  xor     ecx, ecx
0x18000af98  call    SampQueryCapabilities
0x18000af9d  and     al, 5
0x18000af9f  cmp     al, r15b
0x18000afa2  jz      short loc_18000AFCB
0x18000afa4  lea     rdx, [rbp+57h+hMem]
0x18000afa8  lea     rcx, [rbp+57h+var_C0]
0x18000afac  call    SampGetCurrentOwnerAndPrimaryGroup
0x18000afb1  mov     rbx, [rbp+57h+var_C0]
0x18000afb5  test    eax, eax
0x18000afb7  js      short loc_18000AFCB
0x18000afb9  mov     rcx, [rbx]; Sid
0x18000afbc  lea     rdx, [rsp+110h+StringSid]; StringSid
0x18000afc1  call    cs:__imp_ConvertSidToStringSidW
0x18000afc7  test    eax, eax
0x18000afc9  jnz     short loc_18000AFD0
0x18000afcb  mov     [rsp+110h+StringSid], rsi
0x18000afd0  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x18000afd4  xor     ecx, ecx; ClientBinding
0x18000afd6  call    cs:__imp_RpcBindingServerFromClient
0x18000afdc  test    eax, eax
0x18000afde  jnz     short loc_18000B029
0x18000afe0  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x18000afe4  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18000afe8  call    cs:__imp_RpcBindingToStringBindingW
0x18000afee  mov     edi, eax
0x18000aff0  test    eax, eax
0x18000aff2  jnz     short loc_18000B014
0x18000aff4  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18000aff8  lea     r9, [rsp+110h+NetworkAddr]; NetworkAddr
0x18000affd  mov     [rsp+110h+NetworkOptions], r14; NetworkOptions
0x18000b002  xor     r8d, r8d; Protseq
0x18000b005  xor     edx, edx; ObjUuid
0x18000b007  mov     [rsp+110h+Endpoint], r14; Endpoint
0x18000b00c  call    cs:__imp_RpcStringBindingParseW
0x18000b012  mov     edi, eax
0x18000b014  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x18000b018  call    cs:__imp_RpcBindingFree
0x18000b01e  test    edi, edi
0x18000b020  jnz     short loc_18000B029
0x18000b022  mov     rcx, [rsp+110h+NetworkAddr]
0x18000b027  jmp     short loc_18000B031
0x18000b029  mov     rcx, rsi
0x18000b02c  mov     [rsp+110h+NetworkAddr], rcx
0x18000b031  mov     r8, [rsp+110h+StringSid]
0x18000b036  lea     rax, aSam; "SAM"
0x18000b03d  mov     qword ptr [rbp+57h+var_70], rax
0x18000b041  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000b048  lea     rax, [rbp+57h+var_C8]
0x18000b04c  mov     dword ptr [rbp+57h+var_70+8], 8
0x18000b053  mov     qword ptr [rbp+57h+var_60], rax
0x18000b057  mov     rax, rdx
0x18000b05a  mov     dword ptr [rbp+57h+var_60+8], 4
0x18000b061  cmp     [r8+rax*2+2], r14w
0x18000b067  lea     rax, [rax+1]
0x18000b06b  jnz     short loc_18000B061
0x18000b06d  lea     eax, ds:2[rax*2]
0x18000b074  mov     qword ptr [rbp+57h+var_50], r8
0x18000b078  mov     dword ptr [rbp+57h+var_50+8], eax
0x18000b07b  cmp     [rcx+rdx*2+2], r14w
0x18000b081  lea     rdx, [rdx+1]
0x18000b085  jnz     short loc_18000B07B
0x18000b087  add     word ptr [rbp+57h+var_A0], 40h ; '@'
0x18000b08c  lea     eax, ds:2[rdx*2]
0x18000b093  mov     dword ptr [rbp+57h+var_40+8], eax
0x18000b096  mov     qword ptr [rbp+57h+var_40], rcx
0x18000b09a  mov     rcx, cs:?SampTraceLoggerHandle@@3_KA; unsigned __int64 SampTraceLoggerHandle
0x18000b0a1  lea     rdx, [rbp+57h+var_A0]
0x18000b0a5  call    cs:__imp_EtwLogTraceEvent
0x18000b0ab  test    eax, eax
0x18000b0ad  jz      short loc_18000B0DA
0x18000b0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0b6  test    [rcx+44h], r15b
0x18000b0ba  jz      short loc_18000B0DA
0x18000b0bc  cmp     byte ptr [rcx+41h], 2
0x18000b0c0  jb      short loc_18000B0DA
0x18000b0c2  mov     rcx, [rcx+38h]
0x18000b0c6  lea     r8, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids
0x18000b0cd  mov     edx, 10h
0x18000b0d2  mov     r9d, eax
0x18000b0d5  call    WPP_SF_d
0x18000b0da  test    rbx, rbx
0x18000b0dd  jz      short loc_18000B0E8
0x18000b0df  mov     rcx, rbx; hMem
0x18000b0e2  call    cs:__imp_LocalFree
0x18000b0e8  mov     rcx, [rbp+57h+hMem]; hMem
0x18000b0ec  test    rcx, rcx
0x18000b0ef  jz      short loc_18000B0F7
0x18000b0f1  call    cs:__imp_LocalFree
0x18000b0f7  mov     rcx, [rsp+110h+StringSid]; hMem
0x18000b0fc  test    rcx, rcx
0x18000b0ff  jz      short loc_18000B10C
0x18000b101  cmp     rsi, rcx
0x18000b104  jz      short loc_18000B10C
0x18000b106  call    cs:__imp_LocalFree
0x18000b10c  mov     rax, [rsp+110h+NetworkAddr]
0x18000b111  test    rax, rax
0x18000b114  jz      short loc_18000B126
0x18000b116  cmp     rsi, rax
0x18000b119  jz      short loc_18000B126
0x18000b11b  lea     rcx, [rsp+110h+NetworkAddr]; String
0x18000b120  call    cs:__imp_RpcStringFreeW
0x18000b126  cmp     [rbp+57h+StringBinding], r14
0x18000b12a  jz      loc_18000AEA8
0x18000b130  lea     rcx, [rbp+57h+StringBinding]; String
0x18000b134  call    cs:__imp_RpcStringFreeW
0x18000b13a  jmp     loc_18000AEA8
```
