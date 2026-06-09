# UbpmSystemInterfaceStart(void)

- ea: `0x180034034`
- end: `0x18003433b`
- name: `?UbpmSystemInterfaceStart@@YAKXZ`
- size: `775`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002a0cc`

## callees

- `0x18001e9f4`
- `0x180028424`
- `0x18002b670`
- `0x180032e38`
- `0x180034034`
- `0x1800343b0`
- `0x1800347bc`
- `0x1800347e4`
- `0x180034844`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800340e0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800340e0`
- `ntdll!RtlNtStatusToDosError` at `0x1800340f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800340f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034245`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180034245`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180034187`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180034187`

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
           qword_18004C188[3 * i],
           0,
           *(&off_18004C190 + 3 * i),
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
          LODWORD(qword_18004C188[v4]),
          HIDWORD(qword_18004C188[v4]),
          v6);
      return v2;
    }
  }
  for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
  {
    Recipient[1] = 0;
    v9 = (const GUID *)*((_QWORD *)&off_18004C048 + 3 * j);
    Recipient[0] = *(&off_18004C050 + 3 * j);
    v10 = PowerSettingRegisterNotification(v9, 2u, Recipient, (PHPOWERNOTIFY)&g_PoSubscriptions + 3 * j);
    v2 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF__guid_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
          *((_QWORD *)&off_18004C048 + 3 * j),
          v10);
      return v2;
    }
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  for ( k = 0; !k; k = 1 )
  {
    v2 = UbpmUtilsRegOpenKey(
           *((PCWSTR *)&_ImageBase + 38918),
           *((_DWORD *)&_ImageBase + 77834) | 0x10,
           &qword_18004C008);
    if ( v2 - 2 > 1 && v2 != 1168 )
    {
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids,
            (_DWORD)off_18004C030,
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
            (_DWORD)off_18004C030,
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
        (_DWORD)off_18004C030,
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
0x180034034  push    rbx
0x180034036  push    rbp
0x180034037  push    rsi
0x180034038  push    r12
0x18003403a  push    r14
0x18003403c  sub     rsp, 50h
0x180034040  call    ?UbpmpOobeStateStart@@YAKPEAU_UBPM_UTILS_SETUP_PARAMS@@@Z; UbpmpOobeStateStart(_UBPM_UTILS_SETUP_PARAMS *)
0x180034045  mov     ebx, eax
0x180034047  test    eax, eax
0x180034049  jz      short loc_180034089
0x18003404b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034052  lea     rsi, WPP_GLOBAL_Control
0x180034059  cmp     rcx, rsi
0x18003405c  jz      loc_18003432D
0x180034062  test    byte ptr [rcx+1Ch], 1
0x180034066  jz      loc_18003432D
0x18003406c  mov     rcx, [rcx+10h]
0x180034070  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180034077  mov     edx, 0Ah
0x18003407c  mov     r9d, eax
0x18003407f  call    WPP_SF_d
0x180034084  jmp     loc_18003432D
0x180034089  xor     ebx, ebx
0x18003408b  lea     r12, __ImageBase
0x180034092  cmp     ebx, 3
0x180034095  jnb     loc_180034144
0x18003409b  lea     rbp, [rbx+rbx*2]
0x18003409f  mov     [rsp+78h+var_40], 0
0x1800340a7  mov     r9, rva off_18004C190[r12+rbp*8]
0x1800340af  lea     rcx, rva ?g_WnfSubscriptions@@3PAU_UBPM_WNF_SUBSCRIPTION@@A[r12]; _UBPM_WNF_SUBSCRIPTION near * g_WnfSubscriptions ...
0x1800340b7  mov     rdx, rva qword_18004C188[r12+rbp*8]
0x1800340bf  lea     rcx, [rcx+rbp*8]
0x1800340c3  mov     [rsp+78h+var_48], 0
0x1800340cb  xor     r8d, r8d
0x1800340ce  mov     [rsp+78h+var_50], 0
0x1800340d7  mov     [rsp+78h+var_58], 0
0x1800340e0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800340e6  test    eax, eax
0x1800340e8  js      short loc_1800340EE
0x1800340ea  inc     ebx
0x1800340ec  jmp     short loc_180034092
0x1800340ee  mov     ecx, eax; Status
0x1800340f0  call    cs:__imp_RtlNtStatusToDosError
0x1800340f6  mov     ebx, eax
0x1800340f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340ff  lea     rsi, WPP_GLOBAL_Control
0x180034106  cmp     rcx, rsi
0x180034109  jz      loc_18003432D
0x18003410f  test    byte ptr [rcx+1Ch], 1
0x180034113  jz      loc_18003432D
0x180034119  mov     r9d, dword ptr rva qword_18004C188[r12+rbp*8]
0x180034121  mov     edx, 0Bh
0x180034126  mov     rcx, [rcx+10h]
0x18003412a  mov     dword ptr [rsp+78h+var_50], eax
0x18003412e  mov     eax, dword ptr (rva qword_18004C188+4)[r12+rbp*8]
0x180034136  mov     dword ptr [rsp+78h+var_58], eax
0x18003413a  call    WPP_SF_DDd
0x18003413f  jmp     loc_18003432D
0x180034144  xor     esi, esi
0x180034146  cmp     esi, 2
0x180034149  jnb     loc_1800341DE
0x18003414f  lea     rbp, [rsi+rsi*2]
0x180034153  mov     [rsp+78h+var_30], 0
0x18003415c  mov     rax, rva off_18004C050[r12+rbp*8]
0x180034164  lea     r9, rva ?g_PoSubscriptions@@3PAU_UBPM_POWER_SUBSCRIPTION@@A[r12]; _UBPM_POWER_SUBSCRIPTION near * g_PoSubscriptions ...
0x18003416c  mov     rcx, rva off_18004C048[r12+rbp*8]; SettingGuid
0x180034174  lea     r9, [r9+rbp*8]; RegistrationHandle
0x180034178  lea     r8, [rsp+78h+Recipient]; Recipient
0x18003417d  mov     [rsp+78h+Recipient], rax
0x180034182  mov     edx, 2; Flags
0x180034187  call    cs:__imp_PowerSettingRegisterNotification
0x18003418d  mov     ebx, eax
0x18003418f  test    eax, eax
0x180034191  jnz     short loc_180034197
0x180034193  inc     esi
0x180034195  jmp     short loc_180034146
0x180034197  mov     rcx, cs:WPP_GLOBAL_Control
0x18003419e  lea     rsi, WPP_GLOBAL_Control
0x1800341a5  cmp     rcx, rsi
0x1800341a8  jz      loc_18003432D
0x1800341ae  test    byte ptr [rcx+1Ch], 1
0x1800341b2  jz      loc_18003432D
0x1800341b8  mov     r9, rva off_18004C048[r12+rbp*8]
0x1800341c0  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x1800341c7  mov     rcx, [rcx+10h]
0x1800341cb  mov     edx, 0Ch
0x1800341d0  mov     dword ptr [rsp+78h+var_58], eax
0x1800341d4  call    WPP_SF__guid_d
0x1800341d9  jmp     loc_18003432D
0x1800341de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341e5  lea     rsi, WPP_GLOBAL_Control
0x1800341ec  xor     ebp, ebp
0x1800341ee  cmp     ebp, 1
0x1800341f1  jnb     loc_18003430D
0x1800341f7  mov     r14d, ebp
0x1800341fa  lea     r8, rva qword_18004C008[r12]
0x180034202  shl     r14, 6
0x180034206  add     r8, r14; KeyHandle
0x180034209  mov     edx, [r14+r12+4C028h]
0x180034211  mov     rcx, [r14+r12+4C030h]; SourceString
0x180034219  or      edx, 10h; DesiredAccess
0x18003421c  call    ?UbpmUtilsRegOpenKey@@YAKPEBGKPEAPEAX@Z; UbpmUtilsRegOpenKey(ushort const *,ulong,void * *)
0x180034221  mov     ebx, eax
0x180034223  add     eax, 0FFFFFFFEh
0x180034226  cmp     eax, 1
0x180034229  jbe     short loc_180034272
0x18003422b  cmp     ebx, 490h
0x180034231  jz      short loc_180034272
0x180034233  test    ebx, ebx
0x180034235  jnz     loc_1800342D8
0x18003423b  xor     r9d, r9d; lpName
0x18003423e  xor     r8d, r8d; bInitialState
0x180034241  xor     edx, edx; bManualReset
0x180034243  xor     ecx, ecx; lpEventAttributes
0x180034245  call    cs:__imp_CreateEventW
0x18003424b  mov     [r14+r12+4C010h], rax
0x180034253  test    rax, rax
0x180034256  jz      short loc_1800342B3
0x180034258  lea     rcx, rva ?g_RegSubscriptions@@3PAU_UBPM_REGISTRY_SUBSCRIPTION@@A[r12]; _UBPM_REGISTRY_SUBSCRIPTION near * g_RegSubscriptions ...
0x180034260  xor     r8d, r8d; void *
0x180034263  add     rcx, r14; void *
0x180034266  xor     edx, edx; unsigned __int8
0x180034268  mov     byte ptr [rcx], 1
0x18003426b  call    ?UbpmpRegistryChangeCallback@@YAXPEAXE0@Z; UbpmpRegistryChangeCallback(void *,uchar,void *)
0x180034270  jmp     short loc_1800342A5
0x180034272  mov     rcx, cs:WPP_GLOBAL_Control
0x180034279  cmp     rcx, rsi
0x18003427c  jz      short loc_1800342AC
0x18003427e  test    byte ptr [rcx+1Ch], 1
0x180034282  jz      short loc_1800342AC
0x180034284  mov     r9, [r14+r12+4C030h]
0x18003428c  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180034293  mov     rcx, [rcx+10h]
0x180034297  mov     edx, 0Dh
0x18003429c  mov     dword ptr [rsp+78h+var_58], ebx
0x1800342a0  call    WPP_SF_Sd
0x1800342a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342ac  inc     ebp
0x1800342ae  jmp     loc_1800341EE
0x1800342b3  call    cs:__imp_GetLastError
0x1800342b9  mov     ebx, eax
0x1800342bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342c2  cmp     rcx, rsi
0x1800342c5  jz      short loc_18003432D
0x1800342c7  test    byte ptr [rcx+1Ch], 1
0x1800342cb  jz      short loc_18003432D
0x1800342cd  mov     edx, 0Fh
0x1800342d2  mov     dword ptr [rsp+78h+var_58], eax
0x1800342d6  jmp     short loc_1800342F3
0x1800342d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342df  cmp     rcx, rsi
0x1800342e2  jz      short loc_18003432D
0x1800342e4  test    byte ptr [rcx+1Ch], 1
0x1800342e8  jz      short loc_18003432D
0x1800342ea  mov     edx, 0Eh
0x1800342ef  mov     dword ptr [rsp+78h+var_58], ebx
0x1800342f3  mov     r9, [r14+r12+4C030h]
0x1800342fb  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180034302  mov     rcx, [rcx+10h]
0x180034306  call    WPP_SF_Sd
0x18003430b  jmp     short loc_18003432D
0x18003430d  xor     ebx, ebx
0x18003430f  cmp     rcx, rsi
0x180034312  jz      short loc_18003432D
0x180034314  test    byte ptr [rcx+1Ch], 4
0x180034318  jz      short loc_18003432D
0x18003431a  mov     rcx, [rcx+10h]
0x18003431e  lea     edx, [rbx+10h]
0x180034321  lea     r8, WPP_f04dccc07b3a38008afab32bdc0c36f6_Traceguids
0x180034328  call    WPP_SF_
0x18003432d  mov     eax, ebx
0x18003432f  add     rsp, 50h
0x180034333  pop     r14
0x180034335  pop     r12
0x180034337  pop     rsi
0x180034338  pop     rbp
0x180034339  pop     rbx
0x18003433a  retn
```
