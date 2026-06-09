# UbpmSystemInterfaceStart(void)

- ea: `0x180036484`
- end: `0x1800367aa`
- name: `?UbpmSystemInterfaceStart@@YAKXZ`
- size: `806`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002bb88`

## callees

- `0x18001af64`
- `0x18002a380`
- `0x18002d654`
- `0x1800351ec`
- `0x180036484`
- `0x180036810`
- `0x180036c60`
- `0x180036c90`
- `0x180036cf8`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180036530`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180036530`
- `ntdll!RtlNtStatusToDosError` at `0x180036546`
- `ntdll!RtlNtStatusToDosError` at `0x180036546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003671b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003671b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800366a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800366a7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800365e3`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x1800365e3`

## pseudocode

```c
__int64 __fastcall UbpmSystemInterfaceStart(struct _UBPM_UTILS_SETUP_PARAMS *a1)
{
  unsigned int v1; // eax
  ULONG v2; // ebx
  __int64 i; // rbx
  __int64 v4; // rbp
  NTSTATUS v5; // eax
  ULONG v6; // eax
  __int64 v7; // r8
  __int64 j; // rsi
  const GUID *v9; // rcx
  DWORD v10; // eax
  PVOID *v11; // rcx
  int k; // ebp
  DWORD LastError; // eax
  _QWORD Recipient[7]; // [rsp+40h] [rbp-38h] BYREF

  v1 = UbpmpOobeStateStart(a1);
  v2 = v1;
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids, v1);
    return v2;
  }
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    v4 = 3 * i;
    v5 = RtlSubscribeWnfStateChangeNotification(
           &g_WnfSubscriptions + 3 * i,
           qword_18004F188[3 * i],
           0,
           *(&off_18004F190 + 3 * i),
           0,
           0,
           0,
           0);
    if ( v5 < 0 )
    {
      v6 = RtlNtStatusToDosError(v5);
      v2 = v6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          v7,
          LODWORD(qword_18004F188[v4]),
          HIDWORD(qword_18004F188[v4]),
          v6);
      return v2;
    }
  }
  for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
  {
    Recipient[1] = 0;
    v9 = (const GUID *)*((_QWORD *)&off_18004F048 + 3 * j);
    Recipient[0] = *(&off_18004F050 + 3 * j);
    v10 = PowerSettingRegisterNotification(v9, 2u, Recipient, (PHPOWERNOTIFY)&g_PoSubscriptions + 3 * j);
    v2 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__guid_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
          *((_QWORD *)&off_18004F048 + 3 * j),
          v10);
      return v2;
    }
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  for ( k = 0; !k; k = 1 )
  {
    v2 = UbpmUtilsRegOpenKey(
           *((PCWSTR *)&_ImageBase + 40454),
           *((_DWORD *)&_ImageBase + 80906) | 0x10,
           &qword_18004F008);
    if ( v2 - 2 > 1 && v2 != 1168 )
    {
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
            (_DWORD)off_18004F030,
            v2);
        return v2;
      }
      hObject = CreateEventW(0, 0, 0, 0);
      if ( !hObject )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)&WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
            (_DWORD)off_18004F030,
            LastError);
        return v2;
      }
      LOBYTE(g_RegSubscriptions) = 1;
      UbpmpRegistryChangeCallback(&g_RegSubscriptions, 0, 0);
      goto LABEL_29;
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
        (_DWORD)off_18004F030,
        v2);
LABEL_29:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
  }
  v2 = 0;
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    WPP_SF_(v11[2], 16, &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x180036484  push    rbx
0x180036486  push    rbp
0x180036487  push    rsi
0x180036488  push    r12
0x18003648a  push    r14
0x18003648c  sub     rsp, 50h
0x180036490  call    ?UbpmpOobeStateStart@@YAKPEAU_UBPM_UTILS_SETUP_PARAMS@@@Z; UbpmpOobeStateStart(_UBPM_UTILS_SETUP_PARAMS *)
0x180036495  mov     ebx, eax
0x180036497  test    eax, eax
0x180036499  jz      short loc_1800364D9
0x18003649b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364a2  lea     rsi, WPP_GLOBAL_Control
0x1800364a9  cmp     rcx, rsi
0x1800364ac  jz      loc_18003679B
0x1800364b2  test    byte ptr [rcx+1Ch], 1
0x1800364b6  jz      loc_18003679B
0x1800364bc  mov     rcx, [rcx+10h]
0x1800364c0  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x1800364c7  mov     edx, 0Ah
0x1800364cc  mov     r9d, eax
0x1800364cf  call    WPP_SF_d
0x1800364d4  jmp     loc_18003679B
0x1800364d9  xor     ebx, ebx
0x1800364db  lea     r12, __ImageBase
0x1800364e2  cmp     ebx, 3
0x1800364e5  jnb     loc_1800365A0
0x1800364eb  lea     rbp, [rbx+rbx*2]
0x1800364ef  mov     [rsp+78h+var_40], 0
0x1800364f7  mov     r9, rva off_18004F190[r12+rbp*8]
0x1800364ff  lea     rcx, rva ?g_WnfSubscriptions@@3PAU_UBPM_WNF_SUBSCRIPTION@@A[r12]; _UBPM_WNF_SUBSCRIPTION near * g_WnfSubscriptions ...
0x180036507  mov     rdx, rva qword_18004F188[r12+rbp*8]
0x18003650f  lea     rcx, [rcx+rbp*8]
0x180036513  mov     [rsp+78h+var_48], 0
0x18003651b  xor     r8d, r8d
0x18003651e  mov     [rsp+78h+var_50], 0
0x180036527  mov     [rsp+78h+var_58], 0
0x180036530  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180036537  nop     dword ptr [rax+rax+00h]
0x18003653c  test    eax, eax
0x18003653e  js      short loc_180036544
0x180036540  inc     ebx
0x180036542  jmp     short loc_1800364E2
0x180036544  mov     ecx, eax; Status
0x180036546  call    cs:__imp_RtlNtStatusToDosError
0x18003654d  nop     dword ptr [rax+rax+00h]
0x180036552  mov     ebx, eax
0x180036554  mov     rcx, cs:WPP_GLOBAL_Control
0x18003655b  lea     rsi, WPP_GLOBAL_Control
0x180036562  cmp     rcx, rsi
0x180036565  jz      loc_18003679B
0x18003656b  test    byte ptr [rcx+1Ch], 1
0x18003656f  jz      loc_18003679B
0x180036575  mov     r9d, dword ptr rva qword_18004F188[r12+rbp*8]
0x18003657d  mov     edx, 0Bh
0x180036582  mov     rcx, [rcx+10h]
0x180036586  mov     dword ptr [rsp+78h+var_50], eax
0x18003658a  mov     eax, dword ptr (rva qword_18004F188+4)[r12+rbp*8]
0x180036592  mov     dword ptr [rsp+78h+var_58], eax
0x180036596  call    WPP_SF_DDd
0x18003659b  jmp     loc_18003679B
0x1800365a0  xor     esi, esi
0x1800365a2  cmp     esi, 2
0x1800365a5  jnb     loc_180036640
0x1800365ab  lea     rbp, [rsi+rsi*2]
0x1800365af  mov     [rsp+78h+var_30], 0
0x1800365b8  mov     rax, rva off_18004F050[r12+rbp*8]
0x1800365c0  lea     r9, rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r12]; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x1800365c8  mov     rcx, rva off_18004F048[r12+rbp*8]; SettingGuid
0x1800365d0  lea     r9, [r9+rbp*8]; RegistrationHandle
0x1800365d4  lea     r8, [rsp+78h+Recipient]; Recipient
0x1800365d9  mov     [rsp+78h+Recipient], rax
0x1800365de  mov     edx, 2; Flags
0x1800365e3  call    cs:__imp_PowerSettingRegisterNotification
0x1800365ea  nop     dword ptr [rax+rax+00h]
0x1800365ef  mov     ebx, eax
0x1800365f1  test    eax, eax
0x1800365f3  jnz     short loc_1800365F9
0x1800365f5  inc     esi
0x1800365f7  jmp     short loc_1800365A2
0x1800365f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180036600  lea     rsi, WPP_GLOBAL_Control
0x180036607  cmp     rcx, rsi
0x18003660a  jz      loc_18003679B
0x180036610  test    byte ptr [rcx+1Ch], 1
0x180036614  jz      loc_18003679B
0x18003661a  mov     r9, rva off_18004F048[r12+rbp*8]
0x180036622  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180036629  mov     rcx, [rcx+10h]
0x18003662d  mov     edx, 0Ch
0x180036632  mov     dword ptr [rsp+78h+var_58], eax
0x180036636  call    WPP_SF__guid_d
0x18003663b  jmp     loc_18003679B
0x180036640  mov     rcx, cs:WPP_GLOBAL_Control
0x180036647  lea     rsi, WPP_GLOBAL_Control
0x18003664e  xor     ebp, ebp
0x180036650  cmp     ebp, 1
0x180036653  jnb     loc_18003677B
0x180036659  mov     r14d, ebp
0x18003665c  lea     r8, rva qword_18004F008[r12]
0x180036664  shl     r14, 6
0x180036668  add     r8, r14; KeyHandle
0x18003666b  mov     edx, [r14+r12+4F028h]
0x180036673  mov     rcx, [r14+r12+4F030h]; SourceString
0x18003667b  or      edx, 10h; DesiredAccess
0x18003667e  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180036683  mov     ebx, eax
0x180036685  add     eax, 0FFFFFFFEh
0x180036688  cmp     eax, 1
0x18003668b  jbe     short loc_1800366DA
0x18003668d  cmp     ebx, 490h
0x180036693  jz      short loc_1800366DA
0x180036695  test    ebx, ebx
0x180036697  jnz     loc_180036746
0x18003669d  xor     r9d, r9d; lpName
0x1800366a0  xor     r8d, r8d; bInitialState
0x1800366a3  xor     edx, edx; bManualReset
0x1800366a5  xor     ecx, ecx; lpEventAttributes
0x1800366a7  call    cs:__imp_CreateEventW
0x1800366ae  nop     dword ptr [rax+rax+00h]
0x1800366b3  mov     [r14+r12+4F010h], rax
0x1800366bb  test    rax, rax
0x1800366be  jz      short loc_18003671B
0x1800366c0  lea     rcx, rva ?g_RegSubscriptions@@3PAU_UBPM_REGISTRY_SUBSCRIPTION@@A[r12]; _UBPM_REGISTRY_SUBSCRIPTION near * g_RegSubscriptions ...
0x1800366c8  xor     r8d, r8d; void *
0x1800366cb  add     rcx, r14; void *
0x1800366ce  xor     edx, edx; unsigned __int8
0x1800366d0  mov     byte ptr [rcx], 1
0x1800366d3  call    ?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z; UbpmpRegistryChangeCallback(void *,uchar,void *)
0x1800366d8  jmp     short loc_18003670D
0x1800366da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366e1  cmp     rcx, rsi
0x1800366e4  jz      short loc_180036714
0x1800366e6  test    byte ptr [rcx+1Ch], 1
0x1800366ea  jz      short loc_180036714
0x1800366ec  mov     r9, [r14+r12+4F030h]
0x1800366f4  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x1800366fb  mov     rcx, [rcx+10h]
0x1800366ff  mov     edx, 0Dh
0x180036704  mov     dword ptr [rsp+78h+var_58], ebx
0x180036708  call    WPP_SF_Sd
0x18003670d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036714  inc     ebp
0x180036716  jmp     loc_180036650
0x18003671b  call    cs:__imp_GetLastError
0x180036722  nop     dword ptr [rax+rax+00h]
0x180036727  mov     ebx, eax
0x180036729  mov     rcx, cs:WPP_GLOBAL_Control
0x180036730  cmp     rcx, rsi
0x180036733  jz      short loc_18003679B
0x180036735  test    byte ptr [rcx+1Ch], 1
0x180036739  jz      short loc_18003679B
0x18003673b  mov     edx, 0Fh
0x180036740  mov     dword ptr [rsp+78h+var_58], eax
0x180036744  jmp     short loc_180036761
0x180036746  mov     rcx, cs:WPP_GLOBAL_Control
0x18003674d  cmp     rcx, rsi
0x180036750  jz      short loc_18003679B
0x180036752  test    byte ptr [rcx+1Ch], 1
0x180036756  jz      short loc_18003679B
0x180036758  mov     edx, 0Eh
0x18003675d  mov     dword ptr [rsp+78h+var_58], ebx
0x180036761  mov     r9, [r14+r12+4F030h]
0x180036769  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180036770  mov     rcx, [rcx+10h]
0x180036774  call    WPP_SF_Sd
0x180036779  jmp     short loc_18003679B
0x18003677b  xor     ebx, ebx
0x18003677d  cmp     rcx, rsi
0x180036780  jz      short loc_18003679B
0x180036782  test    byte ptr [rcx+1Ch], 4
0x180036786  jz      short loc_18003679B
0x180036788  mov     rcx, [rcx+10h]
0x18003678c  lea     edx, [rbx+10h]
0x18003678f  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180036796  call    WPP_SF_
0x18003679b  mov     eax, ebx
0x18003679d  add     rsp, 50h
0x1800367a1  pop     r14
0x1800367a3  pop     r12
0x1800367a5  pop     rsi
0x1800367a6  pop     rbp
0x1800367a7  pop     rbx
0x1800367a8  retn
```
