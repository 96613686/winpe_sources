# wWinMain

- ea: `0x140012f54`
- end: `0x140013522`
- name: `wWinMain`
- size: `1486`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000d75c`
- `0x14000dd50`
- `0x14000dea0`
- `0x14000e2a0`
- `0x14000e3cc`
- `0x14000e550`
- `0x14000e624`
- `0x14000e6e4`
- `0x14000e72c`
- `0x14000ea8c`
- `0x14000eb0c`
- `0x14000f2d0`
- `0x14000f55c`
- `0x14000f5b8`
- `0x14000f5f4`
- `0x140012b08`
- `0x140012b48`
- `0x140012b80`
- `0x140012d8c`
- `0x140012e8c`
- `0x140012f54`
- `0x14001355c`
- `0x1400135a4`
- `0x1400135f0`
- `0x140017290`
- `0x140017698`
- `0x140018ac8`
- `0x14001cd1c`
- `0x14001cfa0`
- `0x140026a44`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x1400131b4`
- `ADVAPI32!RegDeleteValueW` at `0x1400131b4`
- `ADVAPI32!RegEnumValueW` at `0x1400133b0`
- `ADVAPI32!RegEnumValueW` at `0x140013467`
- `ADVAPI32!RegEnumValueW` at `0x1400133b0`
- `ADVAPI32!RegEnumValueW` at `0x140013467`
- `KERNEL32!HeapSetInformation` at `0x140012f92`
- `KERNEL32!HeapSetInformation` at `0x140012f92`
- `KERNEL32!SetThreadUILanguage` at `0x140012fb7`
- `KERNEL32!SetThreadUILanguage` at `0x140012fb7`
- `USER32!SystemParametersInfoW` at `0x14001321f`
- `USER32!SystemParametersInfoW` at `0x14001321f`
- `ole32!CoInitialize` at `0x1400131fc`
- `ole32!CoInitialize` at `0x1400131fc`
- `ole32!CoUninitialize` at `0x14001327c`
- `ole32!CoUninitialize` at `0x14001347f`
- `ole32!CoUninitialize` at `0x1400134d9`
- `ole32!CoUninitialize` at `0x14001327c`
- `ole32!CoUninitialize` at `0x14001347f`
- `ole32!CoUninitialize` at `0x1400134d9`

## string_xrefs

- `0x14001307e`: `Configuration`
- `0x1400130da`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x140013156`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`
- `0x140013307`: `Software\Microsoft\Windows NT\CurrentVersion\AccessibilityTemp`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LANGID SessionLangID; // ax
  void *v7; // rcx
  unsigned int v8; // edx
  unsigned int v9; // r9d
  bool v10; // bl
  bool v11; // dl
  int v12; // eax
  unsigned __int8 v13; // bl
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  bool v18; // dl
  int v19; // ebx
  int v20; // edi
  struct Accommodation *v21; // rax
  int v22; // r8d
  int v23; // r9d
  DWORD v24; // edx
  unsigned __int8 v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  int pvParam; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v33[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[352]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR hKey; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v36; // [rsp+1F0h] [rbp+F0h]
  WCHAR ValueName[1024]; // [rsp+200h] [rbp+100h] BYREF

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  if ( IsLogonUI() )
  {
    SessionLangID = GetSessionLangID();
    if ( SessionLangID )
      SetThreadUILanguage(SessionLangID);
  }
  v28 = 0;
  memset(v33, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, HKEY_LOCAL_MACHINE, L"System\\Setup", 0x20019u)
    && (unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v33, L"OOBEInProgress", &v28) )
  {
    v28 = 0;
  }
  if ( (unsigned int)CATUtils::IsProcessInATJob(v7) )
  {
    if ( v28 )
    {
      hKey.Ptr = 0;
      *(_QWORD *)&hKey.Size = 0;
      v36 = 0;
      cchValueName = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&hKey,
                            HKEY_LOCAL_MACHINE,
                            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
                            0x2001Fu)
        && !(unsigned int)ATL::CRegKey::QueryDWORDValue(
                            (ATL::CRegKey *)&hKey,
                            L"StartSecureDesktopToolsForOOBE",
                            &cchValueName)
        && cchValueName == 1 )
      {
        RegDeleteValueW((HKEY)hKey.Ptr, L"StartSecureDesktopToolsForOOBE");
        ATManager::ATManager((ATManager *)v34, 0);
        StartList::StartAll((StartList *)v34, v11);
        ATManager::~ATManager((ATManager *)v34);
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        goto LABEL_51;
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
    }
    if ( CoInitialize(0) >= 0 )
    {
      if ( !SystemParametersInfoW(0xAAu, 0, &pvParam, 0) || (v12 = 1, !pvParam) )
        v12 = 0;
      pvParam = v12;
      v26[0] = 0;
      if ( (int)IsCandidateUser(v26) < 0 || (v13 = 1, !v26[0]) )
        v13 = 0;
      if ( IsInteractiveUser() && (!pvParam || v13) )
      {
        HandleInteractiveUser(v13);
      }
      else if ( !IsUtilmanRunning() )
      {
        SetAsRunning(1);
        McGenEventRegister_EventRegister();
        if ( (Microsoft_Windows_EaseOfAccessEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v15, v14, v16, v17, &hKey);
        qword_1400472A0 = 0;
        WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_EASE_OF_ACCESS;
        WPP_GLOBAL_Control = &WPP_MAIN_CB;
        WPP_MAIN_CB = 0;
        qword_1400472A8 = 1;
        WppInitUm();
        if ( v28 )
        {
          ATManager::ATManager((ATManager *)v34);
          hKey.Ptr = 0;
          *(_QWORD *)&hKey.Size = 0;
          v36 = 0;
          if ( !(unsigned int)ATL::CRegKey::Open(
                                (ATL::CRegKey *)&hKey,
                                HKEY_CURRENT_USER,
                                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AccessibilityTemp",
                                0x2001Fu) )
          {
            v19 = 0;
            memset_0(ValueName, 0, 0x208u);
            cchValueName = 260;
            Type = 0;
            v20 = 1;
            *(_DWORD *)Data = 0;
            cbData = 4;
            if ( !RegEnumValueW((HKEY)hKey.Ptr, 0, ValueName, &cchValueName, 0, &Type, Data, &cbData) )
            {
              do
              {
                if ( (Data[0] & 1) != 0 )
                {
                  v21 = Accommodation::Open(ValueName);
                  if ( v21 )
                    StartList::Start((StartList *)v34, v21, v22, v23);
                }
                if ( *(_DWORD *)Data )
                {
                  v19 = 1;
                  ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)&hKey, ValueName, 0);
                }
                memset_0(ValueName, 0, 0x208u);
                cchValueName = 260;
                cbData = 4;
                v24 = v20++;
              }
              while ( !RegEnumValueW((HKEY)hKey.Ptr, v24, ValueName, &cchValueName, 0, &Type, Data, &cbData) );
              if ( v19 )
              {
                CoUninitialize();
                WppCleanupUm();
                McGenEventUnregister_EventUnregister();
                SetAsRunning(0);
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
                ATManager::~ATManager((ATManager *)v34);
                goto LABEL_51;
              }
            }
          }
          StartList::StartAll((StartList *)v34, v18);
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          ATManager::~ATManager((ATManager *)v34);
        }
        LaunchEaseOfAccessDialog(hInstance);
        CoUninitialize();
        WppCleanupUm();
        McGenEventUnregister_EventUnregister();
        SetAsRunning(0);
        goto LABEL_51;
      }
      CoUninitialize();
    }
  }
  else
  {
    if ( !wcscmp_0(lpCmdLine, L"/restart") )
    {
      hKey.Ptr = 0;
      *(_QWORD *)&hKey.Size = 0;
      v36 = 0;
      memset_0(ValueName, 0, sizeof(ValueName));
      GetSessionValue(ValueName, v8, (struct ATL::CRegKey *)&hKey);
      ATL::CRegKey::SetStringValue((ATL::CRegKey *)&hKey, L"Configuration", &qword_14002C590, v9);
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
      SendWinkeyPlusU();
      goto LABEL_51;
    }
    if ( !v28 || wcscmp_0(lpCmdLine, L"/startSecureDesktopToolsForOOBE") )
      goto LABEL_16;
    if ( CEaseOfAccessDialog::CopySecureDesktopToolsToOOBEConfig() )
    {
      hKey.Ptr = 0;
      *(_QWORD *)&hKey.Size = 0;
      v36 = 0;
      v10 = 0;
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)&hKey,
                            HKEY_LOCAL_MACHINE,
                            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\OOBE",
                            0x20006u) )
        v10 = (unsigned int)ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)&hKey, L"StartSecureDesktopToolsForOOBE", 1u) == 0;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      if ( v10 )
        goto LABEL_16;
    }
  }
LABEL_51:
  ATL::CRegKey::Close((ATL::CRegKey *)v33);
  return 0;
}

```

## disassembly

```asm
0x140012f54  push    rbp
0x140012f56  push    rbx
0x140012f57  push    rsi
0x140012f58  push    rdi
0x140012f59  push    r14
0x140012f5b  push    r15
0x140012f5d  lea     rbp, [rsp-918h]
0x140012f65  sub     rsp, 0A18h
0x140012f6c  mov     rax, cs:__security_cookie
0x140012f73  xor     rax, rsp
0x140012f76  mov     [rbp+940h+var_40], rax
0x140012f7d  xor     r9d, r9d; HeapInformationLength
0x140012f80  mov     rbx, r8
0x140012f83  mov     rsi, rcx
0x140012f86  xor     r8d, r8d; HeapInformation
0x140012f89  xor     ecx, ecx; HeapHandle
0x140012f8b  lea     r15d, [r9+1]
0x140012f8f  mov     edx, r15d; HeapInformationClass
0x140012f92  call    cs:__imp_HeapSetInformation
0x140012f99  nop     dword ptr [rax+rax+00h]
0x140012f9e  call    ?IsLogonUI@@YA_NXZ; IsLogonUI(void)
0x140012fa3  xor     r14d, r14d
0x140012fa6  test    al, al
0x140012fa8  jz      short loc_140012FC3
0x140012faa  call    ?GetSessionLangID@@YAGXZ; GetSessionLangID(void)
0x140012faf  test    ax, ax
0x140012fb2  jz      short loc_140012FC3
0x140012fb4  movzx   ecx, ax; LangId
0x140012fb7  call    cs:__imp_SetThreadUILanguage
0x140012fbe  nop     dword ptr [rax+rax+00h]
0x140012fc3  mov     rdi, 0FFFFFFFF80000002h
0x140012fca  mov     [rsp+0A40h+var_9F8], r14d
0x140012fcf  mov     rdx, rdi; hKey
0x140012fd2  mov     [rsp+0A40h+var_9E0], r14
0x140012fd7  mov     r9d, 20019h; unsigned int
0x140012fdd  mov     [rsp+0A40h+var_9D8], r14
0x140012fe2  lea     r8, aSystemSetup; "System\\Setup"
0x140012fe9  mov     [rsp+0A40h+var_9D0], r14
0x140012fee  lea     rcx, [rsp+0A40h+var_9E0]; this
0x140012ff3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140012ff8  test    eax, eax
0x140012ffa  jnz     short loc_14001301B
0x140012ffc  lea     r8, [rsp+0A40h+var_9F8]; unsigned int *
0x140013001  lea     rdx, aOobeinprogress; "OOBEInProgress"
0x140013008  lea     rcx, [rsp+0A40h+var_9E0]; this
0x14001300d  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140013012  test    eax, eax
0x140013014  jz      short loc_14001301B
0x140013016  mov     [rsp+0A40h+var_9F8], r14d
0x14001301b  call    ?IsProcessInATJob@CATUtils@@SAHPEAX@Z; CATUtils::IsProcessInATJob(void *)
0x140013020  test    eax, eax
0x140013022  jnz     loc_14001313E
0x140013028  lea     rdx, aRestart; "/restart"
0x14001302f  mov     rcx, rbx; String1
0x140013032  call    wcscmp_0
0x140013037  test    eax, eax
0x140013039  jnz     short loc_1400130A2
0x14001303b  xor     edx, edx; Val
0x14001303d  mov     [rbp+940h+hKey], r14
0x140013044  mov     r8d, 800h; Size
0x14001304a  mov     [rbp+940h+var_858], r14
0x140013051  lea     rcx, [rbp+940h+ValueName]; void *
0x140013058  mov     [rbp+940h+var_850], r14
0x14001305f  call    memset_0
0x140013064  lea     r8, [rbp+940h+hKey]; struct ATL::CRegKey *
0x14001306b  lea     rcx, [rbp+940h+ValueName]; unsigned __int16 *
0x140013072  call    ?GetSessionValue@@YAXPEAGIAEAVCRegKey@ATL@@@Z; GetSessionValue(ushort *,uint,ATL::CRegKey &)
0x140013077  lea     r8, qword_14002C590; unsigned __int16 *
0x14001307e  lea     rdx, aConfiguration; "Configuration"
0x140013085  lea     rcx, [rbp+940h+hKey]; this
0x14001308c  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x140013091  lea     rcx, [rbp+940h+hKey]; this
0x140013098  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001309d  jmp     loc_140013134
0x1400130a2  cmp     [rsp+0A40h+var_9F8], r14d
0x1400130a7  jz      loc_140013134
0x1400130ad  lea     rdx, aStartsecuredes; "/startSecureDesktopToolsForOOBE"
0x1400130b4  mov     rcx, rbx; String1
0x1400130b7  call    wcscmp_0
0x1400130bc  test    eax, eax
0x1400130be  jnz     short loc_140013134
0x1400130c0  call    ?CopySecureDesktopToolsToOOBEConfig@CEaseOfAccessDialog@@SA_NXZ; CEaseOfAccessDialog::CopySecureDesktopToolsToOOBEConfig(void)
0x1400130c5  test    al, al
0x1400130c7  jz      loc_1400134F6
0x1400130cd  mov     r9d, 20006h; unsigned int
0x1400130d3  mov     [rbp+940h+hKey], r14
0x1400130da  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400130e1  mov     [rbp+940h+var_858], r14
0x1400130e8  mov     rdx, rdi; hKey
0x1400130eb  mov     [rbp+940h+var_850], r14
0x1400130f2  lea     rcx, [rbp+940h+hKey]; this
0x1400130f9  mov     bl, r14b
0x1400130fc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140013101  test    eax, eax
0x140013103  jnz     short loc_140013120
0x140013105  mov     r8d, r15d; unsigned int
0x140013108  lea     rdx, ValueName; "StartSecureDesktopToolsForOOBE"
0x14001310f  lea     rcx, [rbp+940h+hKey]; this
0x140013116  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14001311b  test    eax, eax
0x14001311d  setz    bl
0x140013120  lea     rcx, [rbp+940h+hKey]; this
0x140013127  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001312c  test    bl, bl
0x14001312e  jz      loc_1400134F6
0x140013134  call    ?SendWinkeyPlusU@@YAXXZ; SendWinkeyPlusU(void)
0x140013139  jmp     loc_1400134F6
0x14001313e  cmp     [rsp+0A40h+var_9F8], r14d
0x140013143  jz      loc_1400131FA
0x140013149  mov     r9d, 2001Fh; unsigned int
0x14001314f  mov     [rbp+940h+hKey], r14
0x140013156  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001315d  mov     [rbp+940h+var_858], r14
0x140013164  mov     rdx, rdi; hKey
0x140013167  mov     [rbp+940h+var_850], r14
0x14001316e  lea     rcx, [rbp+940h+hKey]; this
0x140013175  mov     [rsp+0A40h+cchValueName], r14d
0x14001317a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001317f  test    eax, eax
0x140013181  jnz     short loc_1400131EE
0x140013183  lea     r8, [rsp+0A40h+cchValueName]; unsigned int *
0x140013188  lea     rdx, ValueName; "StartSecureDesktopToolsForOOBE"
0x14001318f  lea     rcx, [rbp+940h+hKey]; this
0x140013196  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x14001319b  test    eax, eax
0x14001319d  jnz     short loc_1400131EE
0x14001319f  cmp     [rsp+0A40h+cchValueName], r15d
0x1400131a4  jnz     short loc_1400131EE
0x1400131a6  mov     rcx, [rbp+940h+hKey]; hKey
0x1400131ad  lea     rdx, ValueName; "StartSecureDesktopToolsForOOBE"
0x1400131b4  call    cs:__imp_RegDeleteValueW
0x1400131bb  nop     dword ptr [rax+rax+00h]
0x1400131c0  xor     edx, edx; int
0x1400131c2  lea     rcx, [rbp+940h+var_9C0]; this
0x1400131c6  call    ??0ATManager@@QEAA@H@Z; ATManager::ATManager(int)
0x1400131cb  lea     rcx, [rbp+940h+var_9C0]; this
0x1400131cf  call    ?StartAll@StartList@@QEAAJ_N@Z; StartList::StartAll(bool)
0x1400131d4  lea     rcx, [rbp+940h+var_9C0]; this
0x1400131d8  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x1400131dd  lea     rcx, [rbp+940h+hKey]; this
0x1400131e4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400131e9  jmp     loc_1400134F6
0x1400131ee  lea     rcx, [rbp+940h+hKey]; this
0x1400131f5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400131fa  xor     ecx, ecx; pvReserved
0x1400131fc  call    cs:__imp_CoInitialize
0x140013203  nop     dword ptr [rax+rax+00h]
0x140013208  test    eax, eax
0x14001320a  js      loc_1400134F6
0x140013210  xor     r9d, r9d; fWinIni
0x140013213  lea     r8, [rsp+0A40h+pvParam]; pvParam
0x140013218  xor     edx, edx; uiParam
0x14001321a  mov     ecx, 0AAh; uiAction
0x14001321f  call    cs:__imp_SystemParametersInfoW
0x140013226  nop     dword ptr [rax+rax+00h]
0x14001322b  test    eax, eax
0x14001322d  jz      short loc_140013239
0x14001322f  mov     eax, r15d
0x140013232  cmp     [rsp+0A40h+pvParam], r14d
0x140013237  jnz     short loc_14001323C
0x140013239  mov     eax, r14d
0x14001323c  lea     rcx, [rsp+0A40h+var_A00]; unsigned __int8 *
0x140013241  mov     [rsp+0A40h+pvParam], eax
0x140013245  mov     [rsp+0A40h+var_A00], r14b
0x14001324a  call    ?IsCandidateUser@@YAJPEAE@Z; IsCandidateUser(uchar *)
0x14001324f  test    eax, eax
0x140013251  js      short loc_14001325D
0x140013253  mov     bl, r15b
0x140013256  cmp     [rsp+0A40h+var_A00], r14b
0x14001325b  jnz     short loc_140013260
0x14001325d  mov     bl, r14b
0x140013260  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140013265  test    eax, eax
0x140013267  jz      short loc_14001328D
0x140013269  cmp     [rsp+0A40h+pvParam], r14d
0x14001326e  jz      short loc_140013274
0x140013270  test    bl, bl
0x140013272  jz      short loc_14001328D
0x140013274  movzx   ecx, bl
0x140013277  call    ?HandleInteractiveUser@@YAXW4InteractiveUserType@@@Z; HandleInteractiveUser(InteractiveUserType)
0x14001327c  call    cs:__imp_CoUninitialize
0x140013283  nop     dword ptr [rax+rax+00h]
0x140013288  jmp     loc_1400134F6
0x14001328d  call    ?IsUtilmanRunning@@YA_NXZ; IsUtilmanRunning(void)
0x140013292  test    al, al
0x140013294  jnz     short loc_14001327C
0x140013296  mov     cl, r15b; bool
0x140013299  call    ?SetAsRunning@@YAX_N@Z; SetAsRunning(bool)
0x14001329e  call    McGenEventRegister_EventRegister
0x1400132a3  test    cs:Microsoft_Windows_EaseOfAccessEnableBits, r15b
0x1400132aa  jz      short loc_1400132BD
0x1400132ac  lea     rax, [rbp+940h+hKey]
0x1400132b3  mov     [rsp+0A40h+lpReserved], rax; PEVENT_DATA_DESCRIPTOR
0x1400132b8  call    McGenEventWrite_EventWriteTransfer
0x1400132bd  lea     rax, WPP_ThisDir_CTLGUID_EASE_OF_ACCESS
0x1400132c4  mov     cs:qword_1400472A0, r14
0x1400132cb  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1400132d2  lea     rax, WPP_MAIN_CB
0x1400132d9  mov     cs:WPP_GLOBAL_Control, rax
0x1400132e0  mov     cs:WPP_MAIN_CB, r14
0x1400132e7  mov     cs:qword_1400472A8, r15
0x1400132ee  call    WppInitUm
0x1400132f3  cmp     [rsp+0A40h+var_9F8], r14d
0x1400132f8  jz      loc_1400134D1
0x1400132fe  lea     rcx, [rbp+940h+var_9C0]; this
0x140013302  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x140013307  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001330e  mov     [rbp+940h+hKey], r14
0x140013315  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001331c  mov     [rbp+940h+var_858], r14
0x140013323  mov     r9d, 2001Fh; unsigned int
0x140013329  mov     [rbp+940h+var_850], r14
0x140013330  lea     rcx, [rbp+940h+hKey]; this
0x140013337  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001333c  test    eax, eax
0x14001333e  jnz     loc_1400134B3
0x140013344  xor     edx, edx; Val
0x140013346  lea     rcx, [rbp+940h+ValueName]; void *
0x14001334d  mov     r8d, 208h; Size
0x140013353  mov     ebx, r14d
0x140013356  call    memset_0
0x14001335b  mov     rcx, [rbp+940h+hKey]; hKey
0x140013362  lea     rax, [rsp+0A40h+cbData]
0x140013367  mov     [rsp+0A40h+lpcbData], rax; lpcbData
0x14001336c  lea     r9, [rsp+0A40h+cchValueName]; lpcchValueName
0x140013371  lea     rax, [rsp+0A40h+Data]
0x140013376  mov     [rsp+0A40h+cchValueName], 104h
0x14001337e  mov     [rsp+0A40h+lpData], rax; lpData
0x140013383  lea     r8, [rbp+940h+ValueName]; lpValueName
0x14001338a  lea     rax, [rsp+0A40h+Type]
0x14001338f  mov     [rsp+0A40h+Type], r14d
0x140013394  mov     [rsp+0A40h+lpType], rax; lpType
0x140013399  xor     edx, edx; dwIndex
0x14001339b  mov     [rsp+0A40h+lpReserved], r14; lpReserved
0x1400133a0  mov     edi, r15d
0x1400133a3  mov     dword ptr [rsp+0A40h+Data], r14d
0x1400133a8  mov     [rsp+0A40h+cbData], 4
0x1400133b0  call    cs:__imp_RegEnumValueW
0x1400133b7  nop     dword ptr [rax+rax+00h]
0x1400133bc  test    eax, eax
0x1400133be  jnz     loc_1400134B3
0x1400133c4  test    [rsp+0A40h+Data], r15b
0x1400133c9  jz      short loc_1400133E8
0x1400133cb  lea     rcx, [rbp+940h+ValueName]; unsigned __int16 *
0x1400133d2  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1400133d7  test    rax, rax
0x1400133da  jz      short loc_1400133E8
0x1400133dc  mov     rdx, rax; struct Accommodation *
0x1400133df  lea     rcx, [rbp+940h+var_9C0]; this
0x1400133e3  call    ?Start@StartList@@QEAAJPEAVAccommodation@@HH@Z; StartList::Start(Accommodation *,int,int)
0x1400133e8  cmp     dword ptr [rsp+0A40h+Data], r14d
0x1400133ed  jz      short loc_140013408
0x1400133ef  xor     r8d, r8d; unsigned int
0x1400133f2  lea     rdx, [rbp+940h+ValueName]; unsigned __int16 *
0x1400133f9  lea     rcx, [rbp+940h+hKey]; this
0x140013400  mov     ebx, r15d
0x140013403  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x140013408  xor     edx, edx; Val
0x14001340a  lea     rcx, [rbp+940h+ValueName]; void *
0x140013411  mov     r8d, 208h; Size
0x140013417  call    memset_0
0x14001341c  mov     rcx, [rbp+940h+hKey]; hKey
0x140013423  lea     rax, [rsp+0A40h+cbData]
0x140013428  mov     [rsp+0A40h+lpcbData], rax; lpcbData
0x14001342d  lea     r9, [rsp+0A40h+cchValueName]; lpcchValueName
0x140013432  lea     rax, [rsp+0A40h+Data]
0x140013437  mov     [rsp+0A40h+cchValueName], 104h
0x14001343f  mov     [rsp+0A40h+lpData], rax; lpData
0x140013444  lea     r8, [rbp+940h+ValueName]; lpValueName
0x14001344b  lea     rax, [rsp+0A40h+Type]
0x140013450  mov     [rsp+0A40h+cbData], 4
0x140013458  mov     [rsp+0A40h+lpType], rax; lpType
0x14001345d  mov     edx, edi; dwIndex
0x14001345f  mov     [rsp+0A40h+lpReserved], r14; lpReserved
0x140013464  add     edi, r15d
0x140013467  call    cs:__imp_RegEnumValueW
0x14001346e  nop     dword ptr [rax+rax+00h]
0x140013473  test    eax, eax
0x140013475  jz      loc_1400133C4
0x14001347b  test    ebx, ebx
0x14001347d  jz      short loc_1400134B3
0x14001347f  call    cs:__imp_CoUninitialize
0x140013486  nop     dword ptr [rax+rax+00h]
0x14001348b  call    WppCleanupUm
0x140013490  call    McGenEventUnregister_EventUnregister
0x140013495  xor     ecx, ecx; bool
0x140013497  call    ?SetAsRunning@@YAX_N@Z; SetAsRunning(bool)
0x14001349c  lea     rcx, [rbp+940h+hKey]; this
0x1400134a3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400134a8  lea     rcx, [rbp+940h+var_9C0]; this
0x1400134ac  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x1400134b1  jmp     short loc_1400134F6
0x1400134b3  lea     rcx, [rbp+940h+var_9C0]; this
0x1400134b7  call    ?StartAll@StartList@@QEAAJ_N@Z; StartList::StartAll(bool)
0x1400134bc  lea     rcx, [rbp+940h+hKey]; this
0x1400134c3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400134c8  lea     rcx, [rbp+940h+var_9C0]; this
0x1400134cc  call    ??1ATManager@@QEAA@XZ; ATManager::~ATManager(void)
0x1400134d1  mov     rcx, rsi; HINSTANCE
0x1400134d4  call    ?LaunchEaseOfAccessDialog@@YAXPEAUHINSTANCE__@@@Z; LaunchEaseOfAccessDialog(HINSTANCE__ *)
  ... truncated ...
```
