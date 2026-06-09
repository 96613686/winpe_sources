# LoadGPProfileGuid(ushort *,_GUID *,ushort const *)

- ea: `0x1801be888`
- end: `0x1801bec2c`
- name: `?LoadGPProfileGuid@@YAJPEAGPEAU_GUID@@PEBG@Z`
- size: `932`
- prototype: `int(unsigned __int16 *, struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180105384`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180036110`
- `0x18003fda0`
- `0x180106340`
- `0x1801be888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801beaa5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801beaa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801be917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bea13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801be917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801bea13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801beb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bebcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801beb92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801bebcf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801be9dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801be9dd`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801beb6c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801beb6c`

## pseudocode

```c
__int64 __fastcall LoadGPProfileGuid(char *a1, struct _GUID *a2, const unsigned __int16 *a3)
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  int v8; // edi
  PVOID *v9; // rcx
  int v10; // esi
  DWORD v11; // r14d
  LSTATUS v12; // edi
  BYTE *v13; // rax
  int v14; // edx
  int v15; // r8d
  HRESULT v16; // eax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[528]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
        (unsigned int)L"Software\\Microsoft\\Wlansvc\\GroupPolicy\\Profiles",
        v7);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    else
      v6 = v8;
    if ( v6 < 0 )
      goto LABEL_49;
  }
  else
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = 0;
  v11 = 0;
  if ( v8 == 259 )
    goto LABEL_48;
  while ( !v10 )
  {
    cchName = 260;
    cbData = 260;
    v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, 0);
    if ( !v12 )
    {
      phkResult = 0;
      v12 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      if ( v12 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
            (unsigned int)Name,
            v12);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        else
          v6 = v12;
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 < 0 )
        goto LABEL_45;
      v12 = RegQueryValueExW(phkResult, L"Name", 0, 0, Data, &cbData);
      if ( v12 )
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            (unsigned int)&WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids,
            (unsigned int)L"Name",
            v12);
          v9 = (PVOID *)WPP_GLOBAL_Control;
        }
        v6 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        v13 = Data;
        do
        {
          v14 = *(unsigned __int16 *)&v13[a1 - (char *)Data];
          v15 = *(unsigned __int16 *)v13 - v14;
          if ( v15 )
            break;
          v13 += 2;
        }
        while ( v14 );
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, Data);
          v16 = IIDFromString(Name, a2);
          v9 = (PVOID *)WPP_GLOBAL_Control;
          v6 = v16;
          if ( v16 >= 0 )
            v10 = 1;
        }
      }
      if ( !phkResult )
        goto LABEL_45;
      RegCloseKey(phkResult);
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
    ++v11;
    if ( v12 == 259 )
      break;
  }
  if ( v6 >= 0 && !v10 )
LABEL_48:
    v6 = -2147023728;
LABEL_49:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    WPP_SF_d(v9[2], 87, &WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801be888  mov     [rsp-8+arg_0], rbx
0x1801be88d  mov     [rsp-8+arg_18], rsi
0x1801be892  push    rbp
0x1801be893  push    rdi
0x1801be894  push    r12
0x1801be896  push    r14
0x1801be898  push    r15
0x1801be89a  lea     rbp, [rsp-390h]
0x1801be8a2  sub     rsp, 490h
0x1801be8a9  mov     rax, cs:__security_cookie
0x1801be8b0  xor     rax, rsp
0x1801be8b3  mov     [rbp+3B0h+var_30], rax
0x1801be8ba  mov     rdi, r8
0x1801be8bd  mov     [rsp+4B0h+hKey], 0
0x1801be8c6  mov     r12, rdx
0x1801be8c9  mov     r15, rcx
0x1801be8cc  xor     ebx, ebx
0x1801be8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1801be8d5  lea     rsi, WPP_GLOBAL_Control
0x1801be8dc  cmp     rcx, rsi
0x1801be8df  jz      short loc_1801BE8FA
0x1801be8e1  test    byte ptr [rcx+1Ch], 10h
0x1801be8e5  jz      short loc_1801BE8FA
0x1801be8e7  mov     rcx, [rcx+10h]
0x1801be8eb  lea     edx, [rbx+52h]
0x1801be8ee  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801be8f5  call    WPP_SF_
0x1801be8fa  lea     rax, [rsp+4B0h+hKey]
0x1801be8ff  mov     r9d, 20019h; samDesired
0x1801be905  xor     r8d, r8d; ulOptions
0x1801be908  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1801be90d  mov     rdx, rdi; lpSubKey
0x1801be910  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801be917  call    cs:__imp_RegOpenKeyExW
0x1801be91d  mov     edi, eax
0x1801be91f  test    eax, eax
0x1801be921  jz      short loc_1801BE977
0x1801be923  mov     rcx, cs:WPP_GLOBAL_Control
0x1801be92a  cmp     rcx, rsi
0x1801be92d  jz      short loc_1801BE95C
0x1801be92f  test    byte ptr [rcx+1Ch], 2
0x1801be933  jz      short loc_1801BE95C
0x1801be935  mov     rcx, [rcx+10h]
0x1801be939  lea     r9, aSoftwareMicros_21; "Software\\Microsoft\\Wlansvc\\GroupPoli"...
0x1801be940  mov     edx, 53h ; 'S'
0x1801be945  mov     dword ptr [rsp+4B0h+phkResult], eax
0x1801be949  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801be950  call    WPP_SF_SD
0x1801be955  mov     rcx, cs:WPP_GLOBAL_Control
0x1801be95c  test    edi, edi
0x1801be95e  jg      short loc_1801BE964
0x1801be960  mov     ebx, edi
0x1801be962  jmp     short loc_1801BE96D
0x1801be964  movzx   ebx, di
0x1801be967  or      ebx, 80070000h
0x1801be96d  test    ebx, ebx
0x1801be96f  js      loc_1801BEBC2
0x1801be975  jmp     short loc_1801BE97E
0x1801be977  mov     rcx, cs:WPP_GLOBAL_Control
0x1801be97e  xor     esi, esi
0x1801be980  xor     r14d, r14d
0x1801be983  cmp     edi, 103h
0x1801be989  jz      loc_1801BEBB6
0x1801be98f  test    esi, esi
0x1801be991  jnz     loc_1801BEBAE
0x1801be997  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1801be99c  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x1801be9a1  mov     [rsp+4B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1801be9aa  lea     r8, [rsp+4B0h+Name]; lpName
0x1801be9af  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x1801be9b8  mov     edx, r14d; dwIndex
0x1801be9bb  mov     [rsp+4B0h+lpClass], 0; lpClass
0x1801be9c4  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x1801be9cd  mov     [rsp+4B0h+cchName], 104h
0x1801be9d5  mov     [rsp+4B0h+cbData], 104h
0x1801be9dd  call    cs:__imp_RegEnumKeyExW
0x1801be9e3  mov     edi, eax
0x1801be9e5  test    eax, eax
0x1801be9e7  jnz     loc_1801BEB98
0x1801be9ed  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1801be9f2  lea     rax, [rsp+4B0h+var_460]
0x1801be9f7  mov     r9d, 20019h; samDesired
0x1801be9fd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1801bea02  xor     r8d, r8d; ulOptions
0x1801bea05  mov     [rsp+4B0h+var_460], 0
0x1801bea0e  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x1801bea13  call    cs:__imp_RegOpenKeyExW
0x1801bea19  mov     edi, eax
0x1801bea1b  test    eax, eax
0x1801bea1d  jz      short loc_1801BEA6E
0x1801bea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bea26  lea     rax, WPP_GLOBAL_Control
0x1801bea2d  cmp     rcx, rax
0x1801bea30  jz      short loc_1801BEA5B
0x1801bea32  test    byte ptr [rcx+1Ch], 2
0x1801bea36  jz      short loc_1801BEA5B
0x1801bea38  mov     rcx, [rcx+10h]
0x1801bea3c  lea     edx, [rsi+54h]
0x1801bea3f  lea     r9, [rsp+4B0h+Name]
0x1801bea44  mov     dword ptr [rsp+4B0h+phkResult], edi
0x1801bea48  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bea4f  call    WPP_SF_SD
0x1801bea54  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bea5b  test    edi, edi
0x1801bea5d  jg      short loc_1801BEA63
0x1801bea5f  mov     ebx, edi
0x1801bea61  jmp     short loc_1801BEA75
0x1801bea63  movzx   ebx, di
0x1801bea66  or      ebx, 80070000h
0x1801bea6c  jmp     short loc_1801BEA75
0x1801bea6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bea75  test    ebx, ebx
0x1801bea77  js      loc_1801BEB9F
0x1801bea7d  mov     rcx, [rsp+4B0h+var_460]; hKey
0x1801bea82  lea     rax, [rsp+4B0h+cbData]
0x1801bea87  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x1801bea8c  lea     rdx, aName_2; "Name"
0x1801bea93  lea     rax, [rbp+3B0h+Data]
0x1801bea9a  xor     r9d, r9d; lpType
0x1801bea9d  xor     r8d, r8d; lpReserved
0x1801beaa0  mov     [rsp+4B0h+phkResult], rax; lpData
0x1801beaa5  call    cs:__imp_RegQueryValueExW
0x1801beaab  mov     edi, eax
0x1801beaad  test    eax, eax
0x1801beaaf  jz      short loc_1801BEB08
0x1801beab1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beab8  lea     rax, WPP_GLOBAL_Control
0x1801beabf  cmp     rcx, rax
0x1801beac2  jz      short loc_1801BEAF1
0x1801beac4  test    byte ptr [rcx+1Ch], 2
0x1801beac8  jz      short loc_1801BEAF1
0x1801beaca  mov     rcx, [rcx+10h]
0x1801beace  lea     r9, aName_2; "Name"
0x1801bead5  mov     edx, 55h ; 'U'
0x1801beada  mov     dword ptr [rsp+4B0h+phkResult], edi
0x1801beade  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801beae5  call    WPP_SF_SD
0x1801beaea  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beaf1  test    edi, edi
0x1801beaf3  jg      short loc_1801BEAF9
0x1801beaf5  mov     ebx, edi
0x1801beaf7  jmp     short loc_1801BEB02
0x1801beaf9  movzx   ebx, di
0x1801beafc  or      ebx, 80070000h
0x1801beb02  test    ebx, ebx
0x1801beb04  js      short loc_1801BEB85
0x1801beb06  jmp     short loc_1801BEB0F
0x1801beb08  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beb0f  lea     rax, [rbp+3B0h+Data]
0x1801beb16  mov     r9, r15
0x1801beb19  sub     r9, rax
0x1801beb1c  movzx   r8d, word ptr [rax]
0x1801beb20  movzx   edx, word ptr [rax+r9]
0x1801beb25  sub     r8d, edx
0x1801beb28  jnz     short loc_1801BEB32
0x1801beb2a  add     rax, 2
0x1801beb2e  test    edx, edx
0x1801beb30  jnz     short loc_1801BEB1C
0x1801beb32  test    r8d, r8d
0x1801beb35  jnz     short loc_1801BEB85
0x1801beb37  lea     rax, WPP_GLOBAL_Control
0x1801beb3e  cmp     rcx, rax
0x1801beb41  jz      short loc_1801BEB64
0x1801beb43  test    byte ptr [rcx+1Ch], 10h
0x1801beb47  jz      short loc_1801BEB64
0x1801beb49  mov     rcx, [rcx+10h]
0x1801beb4d  lea     edx, [r8+56h]
0x1801beb51  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801beb58  lea     r9, [rbp+3B0h+Data]
0x1801beb5f  call    WPP_SF_S
0x1801beb64  mov     rdx, r12; lpiid
0x1801beb67  lea     rcx, [rsp+4B0h+Name]; lpsz
0x1801beb6c  call    cs:__imp_IIDFromString
0x1801beb72  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beb79  test    eax, eax
0x1801beb7b  mov     ebx, eax
0x1801beb7d  mov     eax, 1
0x1801beb82  cmovns  esi, eax
0x1801beb85  mov     rax, [rsp+4B0h+var_460]
0x1801beb8a  test    rax, rax
0x1801beb8d  jz      short loc_1801BEB9F
0x1801beb8f  mov     rcx, rax; hKey
0x1801beb92  call    cs:__imp_RegCloseKey
0x1801beb98  mov     rcx, cs:WPP_GLOBAL_Control
0x1801beb9f  inc     r14d
0x1801beba2  cmp     edi, 103h
0x1801beba8  jnz     loc_1801BE98F
0x1801bebae  test    ebx, ebx
0x1801bebb0  js      short loc_1801BEBBB
0x1801bebb2  test    esi, esi
0x1801bebb4  jnz     short loc_1801BEBBB
0x1801bebb6  mov     ebx, 80070490h
0x1801bebbb  lea     rsi, WPP_GLOBAL_Control
0x1801bebc2  mov     rax, [rsp+4B0h+hKey]
0x1801bebc7  test    rax, rax
0x1801bebca  jz      short loc_1801BEBDC
0x1801bebcc  mov     rcx, rax; hKey
0x1801bebcf  call    cs:__imp_RegCloseKey
0x1801bebd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801bebdc  cmp     rcx, rsi
0x1801bebdf  jz      short loc_1801BEBFF
0x1801bebe1  test    byte ptr [rcx+1Ch], 10h
0x1801bebe5  jz      short loc_1801BEBFF
0x1801bebe7  mov     rcx, [rcx+10h]
0x1801bebeb  lea     r8, WPP_2d7ff833c87735b1b0f1fe148779aca4_Traceguids
0x1801bebf2  mov     edx, 57h ; 'W'
0x1801bebf7  mov     r9d, ebx
0x1801bebfa  call    WPP_SF_d
0x1801bebff  mov     eax, ebx
0x1801bec01  mov     rcx, [rbp+3B0h+var_30]
0x1801bec08  xor     rcx, rsp; StackCookie
0x1801bec0b  call    __security_check_cookie
0x1801bec10  lea     r11, [rsp+4B0h+var_20]
0x1801bec18  mov     rbx, [r11+30h]
0x1801bec1c  mov     rsi, [r11+48h]
0x1801bec20  mov     rsp, r11
0x1801bec23  pop     r15
0x1801bec25  pop     r14
0x1801bec27  pop     r12
0x1801bec29  pop     rdi
0x1801bec2a  pop     rbp
0x1801bec2b  retn
```
