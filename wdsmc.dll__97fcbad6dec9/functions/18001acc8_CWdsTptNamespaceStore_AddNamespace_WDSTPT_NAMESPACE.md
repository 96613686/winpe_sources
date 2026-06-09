# CWdsTptNamespaceStore::AddNamespace(_WDSTPT_NAMESPACE *)

- ea: `0x18001acc8`
- end: `0x18001b0a3`
- name: `?AddNamespace@CWdsTptNamespaceStore@@QEAAKPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `987`
- prototype: `unsigned int __fastcall(CWdsTptNamespaceStore *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006488`

## callees

- `0x18001aab4`
- `0x18001acc8`
- `0x18001b0ac`
- `0x18001b990`
- `0x180022634`
- `0x180025850`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001b083`
- `KERNEL32!LeaveCriticalSection` at `0x18001b083`
- `KERNEL32!EnterCriticalSection` at `0x18001ace9`
- `KERNEL32!EnterCriticalSection` at `0x18001ace9`
- `ADVAPI32!RegCreateKeyExW` at `0x18001ad73`
- `ADVAPI32!RegCreateKeyExW` at `0x18001ad73`
- `ADVAPI32!RegSetValueExW` at `0x18001adeb`
- `ADVAPI32!RegSetValueExW` at `0x18001af20`
- `ADVAPI32!RegSetValueExW` at `0x18001af69`
- `ADVAPI32!RegSetValueExW` at `0x18001afb2`
- `ADVAPI32!RegSetValueExW` at `0x18001b03e`
- `ADVAPI32!RegSetValueExW` at `0x18001adeb`
- `ADVAPI32!RegSetValueExW` at `0x18001af20`
- `ADVAPI32!RegSetValueExW` at `0x18001af69`
- `ADVAPI32!RegSetValueExW` at `0x18001afb2`
- `ADVAPI32!RegSetValueExW` at `0x18001b03e`
- `ADVAPI32!RegCloseKey` at `0x18001ad39`
- `ADVAPI32!RegCloseKey` at `0x18001ada6`
- `ADVAPI32!RegCloseKey` at `0x18001b074`
- `ADVAPI32!RegCloseKey` at `0x18001ad39`
- `ADVAPI32!RegCloseKey` at `0x18001ada6`
- `ADVAPI32!RegCloseKey` at `0x18001b074`

## string_xrefs

- `0x18001aec0`: `Configuration`

## pseudocode

```c
__int64 __fastcall CWdsTptNamespaceStore::AddNamespace(CWdsTptNamespaceStore *this, struct _WDSTPT_NAMESPACE *a2)
{
  unsigned __int64 v4; // r15
  int v5; // r12d
  unsigned int v6; // ebx
  const char *v7; // rdx
  const WCHAR *v8; // rbx
  HKEY v9; // rsi
  const char *v10; // rdx
  HKEY v11; // rcx
  const char *v12; // rdx
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v14; // r8
  const char *v15; // rdx
  const unsigned __int16 *v16; // r8
  const char *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  const char *v23; // rdx
  unsigned int v24; // eax
  const char *v25; // rdx
  unsigned __int64 v27; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int64 Data; // [rsp+B0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+58h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  hKey = 0;
  v4 = 0;
  dwDisposition = 0;
  v27 = 0;
  v5 = 0;
  v6 = CWdsTptNamespaceStore::ValidateNamespace(a2);
  if ( !ElValidateWin32(v6, v7, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x518u) )
  {
    v8 = (const WCHAR *)*((_QWORD *)a2 + 2);
    v9 = (HKEY)*((_QWORD *)this + 6);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v6 = RegCreateKeyExW(v9, v8, 0, 0, 0, 0x20106u, 0, &hKey, &dwDisposition);
    if ( !ElValidateWin32(v6, v10, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x523u) )
    {
      if ( dwDisposition == 2 )
      {
        v11 = hKey;
        if ( hKey )
        {
          RegCloseKey(hKey);
          v11 = 0;
          hKey = 0;
        }
        v6 = 183;
        goto LABEL_33;
      }
      LODWORD(Data) = *((_DWORD *)a2 + 2);
      v5 = 1;
      v6 = RegSetValueExW(hKey, L"Type", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !ElValidateWin32(v6, v12, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x545u) )
      {
        v13 = (const unsigned __int16 *)&qword_18002DA18;
        v14 = (const unsigned __int16 *)&qword_18002DA18;
        if ( *((_QWORD *)a2 + 3) )
          v14 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v6 = CRegKey::SetValueSz((CRegKey *)&hKey, L"FriendlyName", v14);
        if ( !ElValidateWin32(v6, v15, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x549u) )
        {
          v16 = (const unsigned __int16 *)&qword_18002DA18;
          if ( *((_QWORD *)a2 + 4) )
            v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
          v6 = CRegKey::SetValueSz((CRegKey *)&hKey, L"Description", v16);
          if ( !ElValidateWin32(v6, v17, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x54Du) )
          {
            v6 = CRegKey::SetValueSz((CRegKey *)&hKey, L"ContentProvider", *((const unsigned __int16 **)a2 + 5));
            if ( !ElValidateWin32(v6, v18, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x551u) )
            {
              if ( *((_QWORD *)a2 + 6) )
                v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
              v6 = CRegKey::SetValueSz((CRegKey *)&hKey, L"Configuration", v13);
              if ( !ElValidateWin32(v6, v19, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x555u) )
              {
                LODWORD(Data) = *((_DWORD *)a2 + 20);
                v6 = RegSetValueExW(hKey, L"SessionStartType", 0, 4u, (const BYTE *)&Data, 4u);
                if ( !ElValidateWin32(v6, v20, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x55Cu) )
                {
                  LODWORD(Data) = *((_DWORD *)a2 + 21);
                  v6 = RegSetValueExW(hKey, L"SessionFlags", 0, 4u, (const BYTE *)&Data, 4u);
                  if ( !ElValidateWin32(v6, v21, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x560u) )
                  {
                    LODWORD(Data) = *((_DWORD *)a2 + 22);
                    v6 = RegSetValueExW(hKey, L"MinClients", 0, 4u, (const BYTE *)&Data, 4u);
                    if ( !ElValidateWin32(v6, v22, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x564u)
                      && (*((_BYTE *)a2 + 84) & 2) != 0 )
                    {
                      Data = 0;
                      if ( a2 == (struct _WDSTPT_NAMESPACE *)-92LL )
                      {
                        v6 = 87;
                      }
                      else
                      {
                        v24 = CWdsTptNamespaceStore::SystemTimeToUint64Time(
                                (struct _SYSTEMTIME *)((char *)a2 + 92),
                                &v27);
                        v4 = v27;
                        v6 = v24;
                      }
                      if ( !ElValidateWin32(
                              v6,
                              v23,
                              "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp",
                              0x570u) )
                      {
                        Data = v4;
                        v6 = RegSetValueExW(hKey, L"StartTime", 0, 0xBu, (const BYTE *)&Data, 8u);
                        ElValidateWin32(v6, v25, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x574u);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v6 && v5 )
    CWdsTptNamespaceStore::RemoveNamespace(this, *((const unsigned __int16 **)a2 + 2));
  v11 = hKey;
LABEL_33:
  if ( v11 )
  {
    RegCloseKey(v11);
    hKey = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v6;
}

```

## disassembly

```asm
0x18001acc8  mov     [rsp-38h+arg_8], rbx
0x18001accd  push    rbp
0x18001acce  push    rsi
0x18001accf  push    rdi
0x18001acd0  push    r12
0x18001acd2  push    r13
0x18001acd4  push    r14
0x18001acd6  push    r15
0x18001acd8  mov     rbp, rsp
0x18001acdb  sub     rsp, 60h
0x18001acdf  mov     r14, rcx
0x18001ace2  mov     rdi, rdx
0x18001ace5  add     rcx, 8; lpCriticalSection
0x18001ace9  call    cs:__imp_EnterCriticalSection
0x18001acef  and     [rbp+hKey], 0
0x18001acf4  xor     r15d, r15d
0x18001acf7  and     [rbp+dwDisposition], 0
0x18001acfb  mov     rcx, rdi; struct _WDSTPT_NAMESPACE *
0x18001acfe  mov     [rbp+var_10], r15
0x18001ad02  xor     r12d, r12d
0x18001ad05  call    ?ValidateNamespace@CWdsTptNamespaceStore@@SAKPEAU_WDSTPT_NAMESPACE@@@Z; CWdsTptNamespaceStore::ValidateNamespace(_WDSTPT_NAMESPACE *)
0x18001ad0a  mov     r9d, 518h; unsigned int
0x18001ad10  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001ad17  mov     ecx, eax; unsigned int
0x18001ad19  mov     ebx, eax
0x18001ad1b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ad20  test    eax, eax
0x18001ad22  jnz     loc_18001B056
0x18001ad28  mov     rcx, [rbp+hKey]; hKey
0x18001ad2c  mov     rbx, [rdi+10h]
0x18001ad30  mov     rsi, [r14+30h]
0x18001ad34  test    rcx, rcx
0x18001ad37  jz      short loc_18001AD43
0x18001ad39  call    cs:__imp_RegCloseKey
0x18001ad3f  and     [rbp+hKey], r12
0x18001ad43  lea     rax, [rbp+dwDisposition]
0x18001ad47  xor     r9d, r9d; lpClass
0x18001ad4a  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18001ad4f  xor     r8d, r8d; Reserved
0x18001ad52  lea     rax, [rbp+hKey]
0x18001ad56  mov     rdx, rbx; lpSubKey
0x18001ad59  mov     [rsp+60h+phkResult], rax; phkResult
0x18001ad5e  mov     rcx, rsi; hKey
0x18001ad61  and     [rsp+60h+var_30], r12
0x18001ad66  mov     [rsp+60h+samDesired], 20106h; samDesired
0x18001ad6e  and     dword ptr [rsp+60h+lpData], r12d
0x18001ad73  call    cs:__imp_RegCreateKeyExW
0x18001ad79  mov     r9d, 523h; unsigned int
0x18001ad7f  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001ad86  mov     ecx, eax; unsigned int
0x18001ad88  mov     ebx, eax
0x18001ad8a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ad8f  test    eax, eax
0x18001ad91  jnz     loc_18001B056
0x18001ad97  cmp     [rbp+dwDisposition], 2
0x18001ad9b  jnz     short loc_18001ADBC
0x18001ad9d  mov     rcx, [rbp+hKey]; hKey
0x18001ada1  test    rcx, rcx
0x18001ada4  jz      short loc_18001ADB2
0x18001ada6  call    cs:__imp_RegCloseKey
0x18001adac  xor     ecx, ecx
0x18001adae  mov     [rbp+hKey], rcx
0x18001adb2  mov     ebx, 0B7h
0x18001adb7  jmp     loc_18001B06F
0x18001adbc  mov     eax, [rdi+8]
0x18001adbf  lea     rdx, aType; "Type"
0x18001adc6  mov     dword ptr [rbp+Data], eax
0x18001adc9  mov     r12d, 1
0x18001adcf  lea     rax, [rbp+Data]
0x18001add3  xor     r8d, r8d; Reserved
0x18001add6  lea     ecx, [r12+3]
0x18001addb  mov     [rsp+60h+samDesired], ecx; cbData
0x18001addf  mov     r9d, ecx; dwType
0x18001ade2  mov     rcx, [rbp+hKey]; hKey
0x18001ade6  mov     [rsp+60h+lpData], rax; lpData
0x18001adeb  call    cs:__imp_RegSetValueExW
0x18001adf1  mov     r9d, 545h; unsigned int
0x18001adf7  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001adfe  mov     ecx, eax; unsigned int
0x18001ae00  mov     ebx, eax
0x18001ae02  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ae07  test    eax, eax
0x18001ae09  jnz     loc_18001B056
0x18001ae0f  cmp     [rdi+18h], r15
0x18001ae13  lea     rsi, qword_18002DA18
0x18001ae1a  mov     r8, rsi
0x18001ae1d  lea     rdx, aFriendlyname; "FriendlyName"
0x18001ae24  cmovnz  r8, [rdi+18h]; unsigned __int16 *
0x18001ae29  lea     rcx, [rbp+hKey]; this
0x18001ae2d  call    ?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18001ae32  mov     r9d, 549h; unsigned int
0x18001ae38  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001ae3f  mov     ecx, eax; unsigned int
0x18001ae41  mov     ebx, eax
0x18001ae43  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ae48  test    eax, eax
0x18001ae4a  jnz     loc_18001B056
0x18001ae50  cmp     [rdi+20h], r15
0x18001ae54  lea     rdx, aDescription; "Description"
0x18001ae5b  mov     r8, rsi
0x18001ae5e  lea     rcx, [rbp+hKey]; this
0x18001ae62  cmovnz  r8, [rdi+20h]; unsigned __int16 *
0x18001ae67  call    ?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18001ae6c  mov     r9d, 54Dh; unsigned int
0x18001ae72  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001ae79  mov     ecx, eax; unsigned int
0x18001ae7b  mov     ebx, eax
0x18001ae7d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ae82  test    eax, eax
0x18001ae84  jnz     loc_18001B056
0x18001ae8a  mov     r8, [rdi+28h]; unsigned __int16 *
0x18001ae8e  lea     rdx, aContentprovide; "ContentProvider"
0x18001ae95  lea     rcx, [rbp+hKey]; this
0x18001ae99  call    ?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18001ae9e  mov     r9d, 551h; unsigned int
0x18001aea4  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001aeab  mov     ecx, eax; unsigned int
0x18001aead  mov     ebx, eax
0x18001aeaf  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001aeb4  test    eax, eax
0x18001aeb6  jnz     loc_18001B056
0x18001aebc  cmp     [rdi+30h], r15
0x18001aec0  lea     rdx, aConfiguration; "Configuration"
0x18001aec7  lea     rcx, [rbp+hKey]; this
0x18001aecb  cmovnz  rsi, [rdi+30h]
0x18001aed0  mov     r8, rsi; unsigned __int16 *
0x18001aed3  call    ?SetValueSz@CRegKey@@QEAAKPEBG0@Z; CRegKey::SetValueSz(ushort const *,ushort const *)
0x18001aed8  lea     rsi, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001aedf  mov     r9d, 555h; unsigned int
0x18001aee5  mov     r8, rsi; char *
0x18001aee8  mov     ecx, eax; unsigned int
0x18001aeea  mov     ebx, eax
0x18001aeec  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001aef1  test    eax, eax
0x18001aef3  jnz     loc_18001B056
0x18001aef9  mov     eax, [rdi+50h]
0x18001aefc  lea     r9d, [r12+3]; dwType
0x18001af01  mov     rcx, [rbp+hKey]; hKey
0x18001af05  lea     rdx, aSessionstartty; "SessionStartType"
0x18001af0c  mov     dword ptr [rbp+Data], eax
0x18001af0f  xor     r8d, r8d; Reserved
0x18001af12  lea     rax, [rbp+Data]
0x18001af16  mov     [rsp+60h+samDesired], r9d; cbData
0x18001af1b  mov     [rsp+60h+lpData], rax; lpData
0x18001af20  call    cs:__imp_RegSetValueExW
0x18001af26  mov     r9d, 55Ch; unsigned int
0x18001af2c  mov     r8, rsi; char *
0x18001af2f  mov     ecx, eax; unsigned int
0x18001af31  mov     ebx, eax
0x18001af33  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001af38  test    eax, eax
0x18001af3a  jnz     loc_18001B056
0x18001af40  mov     eax, [rdi+54h]
0x18001af43  lea     ecx, [r12+3]
0x18001af48  mov     [rsp+60h+samDesired], ecx; cbData
0x18001af4c  lea     rdx, aSessionflags; "SessionFlags"
0x18001af53  mov     dword ptr [rbp+Data], eax
0x18001af56  mov     r9d, ecx; dwType
0x18001af59  mov     rcx, [rbp+hKey]; hKey
0x18001af5d  lea     rax, [rbp+Data]
0x18001af61  xor     r8d, r8d; Reserved
0x18001af64  mov     [rsp+60h+lpData], rax; lpData
0x18001af69  call    cs:__imp_RegSetValueExW
0x18001af6f  mov     r9d, 560h; unsigned int
0x18001af75  mov     r8, rsi; char *
0x18001af78  mov     ecx, eax; unsigned int
0x18001af7a  mov     ebx, eax
0x18001af7c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001af81  test    eax, eax
0x18001af83  jnz     loc_18001B056
0x18001af89  mov     eax, [rdi+58h]
0x18001af8c  lea     ecx, [r12+3]
0x18001af91  mov     [rsp+60h+samDesired], ecx; cbData
0x18001af95  lea     rdx, aMinclients; "MinClients"
0x18001af9c  mov     dword ptr [rbp+Data], eax
0x18001af9f  mov     r9d, ecx; dwType
0x18001afa2  mov     rcx, [rbp+hKey]; hKey
0x18001afa6  lea     rax, [rbp+Data]
0x18001afaa  xor     r8d, r8d; Reserved
0x18001afad  mov     [rsp+60h+lpData], rax; lpData
0x18001afb2  call    cs:__imp_RegSetValueExW
0x18001afb8  mov     r9d, 564h; unsigned int
0x18001afbe  mov     r8, rsi; char *
0x18001afc1  mov     ecx, eax; unsigned int
0x18001afc3  mov     ebx, eax
0x18001afc5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001afca  test    eax, eax
0x18001afcc  jnz     loc_18001B056
0x18001afd2  test    byte ptr [rdi+54h], 2
0x18001afd6  jz      short loc_18001B056
0x18001afd8  xor     eax, eax
0x18001afda  lea     rcx, [rdi+5Ch]; struct _SYSTEMTIME *
0x18001afde  mov     [rbp+Data], rax
0x18001afe2  test    rcx, rcx
0x18001afe5  jz      short loc_18001AFFC
0x18001afe7  lea     r8, [rbp+Data]
0x18001afeb  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x18001afef  call    ?SystemTimeToUint64Time@CWdsTptNamespaceStore@@CAKPEAU_SYSTEMTIME@@PEA_K@Z; CWdsTptNamespaceStore::SystemTimeToUint64Time(_SYSTEMTIME *,unsigned __int64 *)
0x18001aff4  mov     r15, [rbp+var_10]
0x18001aff8  mov     ebx, eax
0x18001affa  jmp     short loc_18001B001
0x18001affc  mov     ebx, 57h ; 'W'
0x18001b001  mov     r9d, 570h; unsigned int
0x18001b007  mov     r8, rsi; char *
0x18001b00a  mov     ecx, ebx; unsigned int
0x18001b00c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b011  test    eax, eax
0x18001b013  jnz     short loc_18001B056
0x18001b015  mov     rcx, [rbp+hKey]; hKey
0x18001b019  lea     rax, [rbp+Data]
0x18001b01d  mov     [rsp+60h+samDesired], 8; cbData
0x18001b025  lea     rdx, aStarttime; "StartTime"
0x18001b02c  mov     r9d, 0Bh; dwType
0x18001b032  mov     [rsp+60h+lpData], rax; lpData
0x18001b037  xor     r8d, r8d; Reserved
0x18001b03a  mov     [rbp+Data], r15
0x18001b03e  call    cs:__imp_RegSetValueExW
0x18001b044  mov     r9d, 574h; unsigned int
0x18001b04a  mov     r8, rsi; char *
0x18001b04d  mov     ecx, eax; unsigned int
0x18001b04f  mov     ebx, eax
0x18001b051  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b056  test    ebx, ebx
0x18001b058  jz      short loc_18001B06B
0x18001b05a  test    r12d, r12d
0x18001b05d  jz      short loc_18001B06B
0x18001b05f  mov     rdx, [rdi+10h]; unsigned __int16 *
0x18001b063  mov     rcx, r14; this
0x18001b066  call    ?RemoveNamespace@CWdsTptNamespaceStore@@QEAAKPEBG@Z; CWdsTptNamespaceStore::RemoveNamespace(ushort const *)
0x18001b06b  mov     rcx, [rbp+hKey]; hKey
0x18001b06f  test    rcx, rcx
0x18001b072  jz      short loc_18001B07F
0x18001b074  call    cs:__imp_RegCloseKey
0x18001b07a  and     [rbp+hKey], 0
0x18001b07f  lea     rcx, [r14+8]; lpCriticalSection
0x18001b083  call    cs:__imp_LeaveCriticalSection
0x18001b089  mov     eax, ebx
0x18001b08b  mov     rbx, [rsp+60h+arg_8]
0x18001b093  add     rsp, 60h
0x18001b097  pop     r15
0x18001b099  pop     r14
0x18001b09b  pop     r13
0x18001b09d  pop     r12
0x18001b09f  pop     rdi
0x18001b0a0  pop     rsi
0x18001b0a1  pop     rbp
0x18001b0a2  retn
```
