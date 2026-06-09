# HrRenumberComponentOrdinalNumbers(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong)

- ea: `0x1800095c0`
- end: `0x18000998c`
- name: `?HrRenumberComponentOrdinalNumbers@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@K@Z`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a168`

## callees

- `0x180007820`
- `0x1800095c0`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ace0`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000974c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800096b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000974c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009718`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009840`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009840`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800098e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000978a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000978a`

## string_xrefs

- `0x18000963d`: `Components`

## pseudocode

```c
__int64 __fastcall HrRenumberComponentOrdinalNumbers(const unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  DWORD v7; // r15d
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  PVOID *v14; // rcx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[120]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(Name, 0, sizeof(Name));
  cchName = 0;
  hKey = 0;
  ftLastWriteTime = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x74u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x74u, L"Components");
  if ( a1 )
  {
    StringCchCatW(SubKey, 0x74u, L"\\");
    StringCchCatW(SubKey, 0x74u, a1);
    StringCchCatW(SubKey, 0x74u, L"\\");
    StringCchCatW(SubKey, 0x74u, L"Children");
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( !v5 )
  {
    v7 = 0;
    while ( 1 )
    {
      cchName = 40;
      v8 = RegEnumKeyExW(hKey, v7, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v8 )
      {
        if ( v8 != 259 )
        {
          v6 = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (unsigned int)SubKey,
              (__int64)Name,
              v6);
        }
LABEL_36:
        RegCloseKey(hKey);
LABEL_42:
        v14 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_43;
      }
      phkResult = 0;
      v9 = RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, &phkResult);
      v6 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            (unsigned int)SubKey,
            (__int64)Name,
            v6);
        goto LABEL_27;
      }
      *(_DWORD *)Data = 0;
      cbData = 4;
      v10 = RegQueryValueExW(phkResult, L"Ordinal", 0, 0, Data, &cbData);
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( v6 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_21;
        v13 = 14;
      }
      else
      {
        if ( *(_DWORD *)Data <= a3 )
          goto LABEL_21;
        --*(_DWORD *)Data;
        v11 = RegSetValueExW(phkResult, L"Ordinal", 0, 4u, Data, 4u);
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        if ( v6 >= 0 )
          goto LABEL_21;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_21;
        v13 = 12;
      }
      WPP_SF_SSD(
        v12[2],
        v13,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        (__int64)Name,
        v6);
LABEL_21:
      RegCloseKey(phkResult);
LABEL_27:
      ++v7;
      if ( v6 )
        goto LABEL_36;
    }
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)SubKey,
        v6);
      goto LABEL_42;
    }
LABEL_43:
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
      WPP_SF_D(v14[2], 18, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800095c0  mov     [rsp-8+arg_8], rbx
0x1800095c5  mov     [rsp-8+arg_10], rsi
0x1800095ca  push    rbp
0x1800095cb  push    rdi
0x1800095cc  push    r12
0x1800095ce  push    r14
0x1800095d0  push    r15
0x1800095d2  lea     rbp, [rsp-0C0h]
0x1800095da  sub     rsp, 1C0h
0x1800095e1  mov     rax, cs:__security_cookie
0x1800095e8  xor     rax, rsp
0x1800095eb  mov     [rbp+0E0h+var_30], rax
0x1800095f2  xor     edx, edx; Val
0x1800095f4  mov     r12d, r8d
0x1800095f7  mov     rbx, rcx
0x1800095fa  lea     rcx, [rsp+1E0h+Name]; void *
0x1800095ff  lea     r8d, [rdx+50h]; Size
0x180009603  call    memset_0
0x180009608  xor     eax, eax
0x18000960a  mov     [rsp+1E0h+cchName], 0
0x180009612  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009619  mov     [rsp+1E0h+hKey], 0
0x180009622  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x180009626  mov     qword ptr [rsp+1E0h+ftLastWriteTime.dwLowDateTime], 0
0x18000962f  mov     [rbp+0E0h+SubKey], ax
0x180009633  lea     edi, [rax+74h]
0x180009636  mov     edx, edi; unsigned __int64
0x180009638  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000963d  lea     r8, aComponents; "Components"
0x180009644  mov     edx, edi; unsigned __int64
0x180009646  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x18000964a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000964f  test    rbx, rbx
0x180009652  jz      short loc_180009698
0x180009654  lea     r8, asc_180016A5C; "\\"
0x18000965b  mov     edx, edi; unsigned __int64
0x18000965d  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x180009661  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009666  mov     r8, rbx; unsigned __int16 *
0x180009669  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x18000966d  mov     edx, edi; unsigned __int64
0x18000966f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009674  lea     r8, asc_180016A5C; "\\"
0x18000967b  mov     edx, edi; unsigned __int64
0x18000967d  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x180009681  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009686  lea     r8, aChildren; "Children"
0x18000968d  mov     edx, edi; unsigned __int64
0x18000968f  lea     rcx, [rbp+0E0h+SubKey]; unsigned __int16 *
0x180009693  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009698  lea     rax, [rsp+1E0h+hKey]
0x18000969d  mov     r9d, 20019h; samDesired
0x1800096a3  xor     r8d, r8d; ulOptions
0x1800096a6  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800096ab  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x1800096af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800096b6  call    cs:__imp_RegOpenKeyExW
0x1800096bc  mov     ebx, eax
0x1800096be  test    eax, eax
0x1800096c0  jnz     loc_1800098F1
0x1800096c6  xor     r15d, r15d
0x1800096c9  lea     edi, [rax+4]
0x1800096cc  mov     r14d, 80070000h
0x1800096d2  lea     rsi, WPP_GLOBAL_Control
0x1800096d9  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800096de  lea     rax, [rsp+1E0h+ftLastWriteTime]
0x1800096e3  mov     [rsp+1E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800096e8  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x1800096ed  mov     [rsp+1E0h+lpcchClass], 0; lpcchClass
0x1800096f6  lea     r8, [rsp+1E0h+Name]; lpName
0x1800096fb  mov     [rsp+1E0h+lpClass], 0; lpClass
0x180009704  mov     edx, r15d; dwIndex
0x180009707  mov     [rsp+1E0h+phkResult], 0; lpReserved
0x180009710  mov     [rsp+1E0h+cchName], 28h ; '('
0x180009718  call    cs:__imp_RegEnumKeyExW
0x18000971e  test    eax, eax
0x180009720  jnz     loc_180009896
0x180009726  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18000972b  lea     rax, [rsp+1E0h+var_198]
0x180009730  mov     r9d, 2001Fh; samDesired
0x180009736  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18000973b  xor     r8d, r8d; ulOptions
0x18000973e  mov     [rsp+1E0h+var_198], 0
0x180009747  lea     rdx, [rsp+1E0h+Name]; lpSubKey
0x18000974c  call    cs:__imp_RegOpenKeyExW
0x180009752  mov     ebx, eax
0x180009754  test    eax, eax
0x180009756  jnz     loc_180009848
0x18000975c  mov     rcx, [rsp+1E0h+var_198]; hKey
0x180009761  lea     rdx, aOrdinal; "Ordinal"
0x180009768  mov     dword ptr [rsp+1E0h+Data], eax
0x18000976c  xor     r9d, r9d; lpType
0x18000976f  lea     rax, [rsp+1E0h+cbData]
0x180009774  mov     [rsp+1E0h+cbData], edi
0x180009778  mov     [rsp+1E0h+lpClass], rax; lpcbData
0x18000977d  xor     r8d, r8d; lpReserved
0x180009780  lea     rax, [rsp+1E0h+Data]
0x180009785  mov     [rsp+1E0h+phkResult], rax; lpData
0x18000978a  call    cs:__imp_RegQueryValueExW
0x180009790  mov     ebx, eax
0x180009792  test    eax, eax
0x180009794  jle     short loc_18000979C
0x180009796  movzx   ebx, ax
0x180009799  or      ebx, r14d
0x18000979c  test    ebx, ebx
0x18000979e  js      short loc_180009802
0x1800097a0  mov     eax, dword ptr [rsp+1E0h+Data]
0x1800097a4  cmp     eax, r12d
0x1800097a7  jbe     loc_18000983B
0x1800097ad  mov     rcx, [rsp+1E0h+var_198]; hKey
0x1800097b2  lea     rdx, aOrdinal; "Ordinal"
0x1800097b9  dec     eax
0x1800097bb  mov     dword ptr [rsp+1E0h+lpClass], edi; cbData
0x1800097bf  mov     dword ptr [rsp+1E0h+Data], eax
0x1800097c3  mov     r9d, edi; dwType
0x1800097c6  lea     rax, [rsp+1E0h+Data]
0x1800097cb  xor     r8d, r8d; Reserved
0x1800097ce  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800097d3  call    cs:__imp_RegSetValueExW
0x1800097d9  mov     ebx, eax
0x1800097db  test    eax, eax
0x1800097dd  jle     short loc_1800097E5
0x1800097df  movzx   ebx, ax
0x1800097e2  or      ebx, r14d
0x1800097e5  test    ebx, ebx
0x1800097e7  jns     short loc_18000983B
0x1800097e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097f0  cmp     rcx, rsi
0x1800097f3  jz      short loc_18000983B
0x1800097f5  test    [rcx+1Ch], dil
0x1800097f9  jz      short loc_18000983B
0x1800097fb  mov     edx, 0Ch
0x180009800  jmp     short loc_180009819
0x180009802  mov     rcx, cs:WPP_GLOBAL_Control
0x180009809  cmp     rcx, rsi
0x18000980c  jz      short loc_18000983B
0x18000980e  test    [rcx+1Ch], dil
0x180009812  jz      short loc_18000983B
0x180009814  mov     edx, 0Eh
0x180009819  mov     rcx, [rcx+10h]
0x18000981d  lea     rax, [rsp+1E0h+Name]
0x180009822  mov     dword ptr [rsp+1E0h+lpClass], ebx
0x180009826  lea     r9, [rbp+0E0h+SubKey]
0x18000982a  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009831  mov     [rsp+1E0h+phkResult], rax
0x180009836  call    WPP_SF_SSD
0x18000983b  mov     rcx, [rsp+1E0h+var_198]; hKey
0x180009840  call    cs:__imp_RegCloseKey
0x180009846  jmp     short loc_180009889
0x180009848  jle     short loc_180009850
0x18000984a  movzx   ebx, ax
0x18000984d  or      ebx, r14d
0x180009850  mov     rcx, cs:WPP_GLOBAL_Control
0x180009857  cmp     rcx, rsi
0x18000985a  jz      short loc_180009889
0x18000985c  test    [rcx+1Ch], dil
0x180009860  jz      short loc_180009889
0x180009862  mov     rcx, [rcx+10h]
0x180009866  lea     rax, [rsp+1E0h+Name]
0x18000986b  mov     edx, 0Fh
0x180009870  mov     dword ptr [rsp+1E0h+lpClass], ebx
0x180009874  lea     r9, [rbp+0E0h+SubKey]
0x180009878  mov     [rsp+1E0h+phkResult], rax
0x18000987d  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009884  call    WPP_SF_SSD
0x180009889  inc     r15d
0x18000988c  test    ebx, ebx
0x18000988e  jz      loc_1800096D9
0x180009894  jmp     short loc_1800098E4
0x180009896  cmp     eax, 103h
0x18000989b  jz      short loc_1800098E4
0x18000989d  test    eax, eax
0x18000989f  jg      short loc_1800098A5
0x1800098a1  mov     ebx, eax
0x1800098a3  jmp     short loc_1800098AB
0x1800098a5  movzx   ebx, ax
0x1800098a8  or      ebx, r14d
0x1800098ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098b2  cmp     rcx, rsi
0x1800098b5  jz      short loc_1800098E4
0x1800098b7  test    [rcx+1Ch], dil
0x1800098bb  jz      short loc_1800098E4
0x1800098bd  mov     rcx, [rcx+10h]
0x1800098c1  lea     rax, [rsp+1E0h+Name]
0x1800098c6  mov     edx, 10h
0x1800098cb  mov     dword ptr [rsp+1E0h+lpClass], ebx
0x1800098cf  lea     r9, [rbp+0E0h+SubKey]
0x1800098d3  mov     [rsp+1E0h+phkResult], rax
0x1800098d8  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x1800098df  call    WPP_SF_SSD
0x1800098e4  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800098e9  call    cs:__imp_RegCloseKey
0x1800098ef  jmp     short loc_180009935
0x1800098f1  jle     short loc_1800098FC
0x1800098f3  movzx   ebx, ax
0x1800098f6  or      ebx, 80070000h
0x1800098fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009903  lea     rsi, WPP_GLOBAL_Control
0x18000990a  cmp     rcx, rsi
0x18000990d  jz      short loc_18000995F
0x18000990f  mov     edi, 4
0x180009914  test    [rcx+1Ch], dil
0x180009918  jz      short loc_18000993C
0x18000991a  mov     rcx, [rcx+10h]
0x18000991e  lea     edx, [rdi+0Dh]
0x180009921  lea     r9, [rbp+0E0h+SubKey]
0x180009925  mov     dword ptr [rsp+1E0h+phkResult], ebx
0x180009929  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009930  call    WPP_SF_SD
0x180009935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000993c  cmp     rcx, rsi
0x18000993f  jz      short loc_18000995F
0x180009941  test    byte ptr [rcx+1Ch], 10h
0x180009945  jz      short loc_18000995F
0x180009947  mov     rcx, [rcx+10h]
0x18000994b  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009952  mov     edx, 12h
0x180009957  mov     r9d, ebx
0x18000995a  call    WPP_SF_D
0x18000995f  mov     eax, ebx
0x180009961  mov     rcx, [rbp+0E0h+var_30]
0x180009968  xor     rcx, rsp; StackCookie
0x18000996b  call    __security_check_cookie
0x180009970  lea     r11, [rsp+1E0h+var_20]
0x180009978  mov     rbx, [r11+38h]
0x18000997c  mov     rsi, [r11+40h]
0x180009980  mov     rsp, r11
0x180009983  pop     r15
0x180009985  pop     r14
0x180009987  pop     r12
0x180009989  pop     rdi
0x18000998a  pop     rbp
0x18000998b  retn
```
