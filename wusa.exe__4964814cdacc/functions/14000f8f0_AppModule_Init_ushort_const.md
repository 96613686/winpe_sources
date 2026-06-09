# AppModule::Init(ushort const *)

- ea: `0x14000f8f0`
- end: `0x14000fdf1`
- name: `?Init@AppModule@@QEAAJPEBG@Z`
- size: `1281`
- prototype: `__int64 __fastcall(AppModule *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x14000d44c`
- `0x14000e280`
- `0x14000e9ac`
- `0x14000eb0c`
- `0x14000ec58`
- `0x14000f45c`
- `0x14000f8f0`
- `0x14000fdf8`
- `0x140010800`
- `0x140013020`
- `0x140013490`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x14000f931`
- `ADVAPI32!EventRegister` at `0x14000f931`
- `KERNEL32!LocalFree` at `0x14000fd8b`
- `KERNEL32!LocalFree` at `0x14000fdd0`
- `KERNEL32!LocalFree` at `0x14000fd8b`
- `KERNEL32!LocalFree` at `0x14000fdd0`
- `KERNEL32!CreateEventW` at `0x14000f95f`
- `KERNEL32!CreateEventW` at `0x14000f95f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000fa1e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000fa1e`
- `KERNEL32!GetLastError` at `0x14000f96e`
- `KERNEL32!GetLastError` at `0x14000fa28`
- `KERNEL32!GetLastError` at `0x14000fbdb`
- `KERNEL32!GetLastError` at `0x14000f96e`
- `KERNEL32!GetLastError` at `0x14000fa28`
- `KERNEL32!GetLastError` at `0x14000fbdb`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fb85`
- `OLEAUT32!__imp_SysAllocString` at `0x14000fb85`
- `COMCTL32!InitCommonControlsEx` at `0x14000fbd1`
- `COMCTL32!InitCommonControlsEx` at `0x14000fbd1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000f9a5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000f9a5`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000f9f4`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14000f9f4`

## string_xrefs

- `0x14000f9b5`: `Failed to initialize COM`
- `0x14000f985`: `Failed to create event`
- `0x14000f9fe`: `Failed to initialize COM security`
- `0x14000fd6e`: `Failed to show welcome dialog`
- `0x14000fb0a`: `Failed to create sandbox`
- `0x14000fb1e`: `Created sandbox %ls`
- `0x14000fb3d`: `Failed: AppModule::SetScanCabPath()`
- `0x14000fbf2`: `Failure returned by InitCommonControlsEx()`
- `0x14000fc19`: `Failure returned by CreateFont()`
- `0x14000fc88`: `Failed to get STR_EXPAND_START_UNINSTALL text`
- `0x14000fcd2`: `Failed to get STR_COPY_START text`
- `0x14000fcfb`: `Failed to get STR_UNINSTALL_START text`

## pseudocode

```c
__int64 __fastcall AppModule::Init(AppModule *this, const unsigned __int16 *a2)
{
  signed int FontW; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  const char *v7; // r8
  __int64 v8; // rdx
  HRESULT v9; // eax
  signed int v10; // eax
  BSTR v11; // rax
  signed int v12; // eax
  HLOCAL v13; // rdi
  INITCOMMONCONTROLSEX picce; // [rsp+50h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp+40h] BYREF
  OLECHAR *psz; // [rsp+A8h] [rbp+48h] BYREF

  LODWORD(hMem) = 0;
  picce = 0;
  psz = 0;
  FontW = EventRegister(&WUSA_PROVIDER, 0, 0, &RegHandle);
  if ( FontW < 0 )
  {
    RegHandle = 0;
    goto LABEL_62;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    FontW = LastError;
    if ( LastError > 0 )
      FontW = (unsigned __int16)LastError | 0x80070000;
    v7 = "Failed to create event";
    v8 = 89;
    if ( FontW >= 0 )
      FontW = -2147467259;
    goto LABEL_61;
  }
  v9 = CoInitializeEx(0, 2u);
  *((_DWORD *)this + 59) = v9;
  if ( v9 < 0 )
  {
    v7 = "Failed to initialize COM";
    v8 = 92;
LABEL_61:
    WusaLogDebugEventA(L"AppModule::Init", v8, v7);
    goto LABEL_62;
  }
  *((_DWORD *)this + 59) = 0;
  if ( CoInitializeSecurity(0, -1, 0, 0, 3u, 3u, 0, 0, 0) < 0 )
    WusaLogDebugEventA(L"AppModule::Init", 98, "Failed to initialize COM security");
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 256), 0x64u) )
  {
    v10 = GetLastError();
    FontW = v10;
    if ( v10 > 0 )
      FontW = (unsigned __int16)v10 | 0x80070000;
    v7 = "Failed to initialize critical section";
    v8 = 104;
    if ( FontW >= 0 )
      FontW = -2147467259;
    goto LABEL_61;
  }
  *((_DWORD *)this + 74) = 1;
  FontW = AppModule::ParseCommandLine(this, a2);
  if ( FontW < 0 || *((_DWORD *)this + 22) )
  {
    if ( (int)WusaMessageBox(0xEA61u, 0xEA60u, 1, (PCWSTR)0xFFFD, 0) >= 0 )
      goto LABEL_62;
    v7 = "Failed to show welcome dialog";
    v8 = 114;
    goto LABEL_61;
  }
  if ( (int)WusaIsUserAdmin((int *)&hMem) < 0 || !(_DWORD)hMem )
  {
    if ( (int)WusaMessageBox(0xEA65u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
      WusaLogDebugEventA(L"AppModule::Init", 126, "Failed to show non administrator dialog");
    FontW = -2147024891;
    v7 = "User is not a member of the Administrators group.";
    v8 = 130;
    goto LABEL_61;
  }
  if ( (int)WusaCreateLockFile((void **)this + 30) < 0 )
  {
    if ( (int)WusaMessageBox(0xEA63u, 0xEA60u, 1, (PCWSTR)0xFFFD, 0) < 0 )
      WusaLogDebugEventA(L"AppModule::Init", 143, "Failed to show multiple instance dialog");
    FontW = -2147023278;
    v7 = "Error: Another instance of wusa.exe is running.";
    v8 = 147;
    goto LABEL_61;
  }
  FontW = WusaSandBoxCreate((unsigned __int16 **)this + 22);
  if ( FontW < 0 )
  {
    WusaLogDebugEventA(L"AppModule::Init", 154, "Failed to create sandbox");
    goto LABEL_62;
  }
  WusaLogDebugEventA(L"AppModule::Init", 156, "Created sandbox %ls", *((const wchar_t **)this + 22));
  FontW = AppModule::SetScanCabPath(this);
  if ( FontW < 0 )
  {
    v7 = "Failed: AppModule::SetScanCabPath()";
    v8 = 159;
    goto LABEL_61;
  }
  FontW = WusaLoadMessage(0xEA60u, &psz);
  if ( FontW < 0 )
  {
    WusaLogDebugEventA(L"AppModule::Init", 165, "Failed to get application title text, id %u", 60000);
    goto LABEL_62;
  }
  v11 = SysAllocString(psz);
  *((_QWORD *)this + 20) = v11;
  if ( !v11 )
  {
    WusaLogDebugEventA(L"AppModule::Init", 168, "Failed to allocate BSTR for application title");
    FontW = -2147024882;
    goto LABEL_62;
  }
  if ( !*((_DWORD *)this + 26) )
  {
    picce.dwSize = 8;
    picce.dwICC = 32;
    if ( InitCommonControlsEx(&picce) )
    {
      FontW = AppModule::CreateFontW(this);
      if ( FontW >= 0 )
      {
        FontW = WusaLoadMessage(0xEA6Au, (unsigned __int16 **)this + 5);
        if ( FontW >= 0 )
        {
          FontW = WusaLoadMessage(0xEA6Cu, (unsigned __int16 **)this + 6);
          if ( FontW >= 0 )
          {
            FontW = WusaLoadMessage(0xEA6Du, (unsigned __int16 **)this + 7);
            if ( FontW >= 0 )
            {
              FontW = WusaLoadMessage(0xEA67u, (unsigned __int16 **)this + 8);
              if ( FontW >= 0 )
              {
                FontW = WusaLoadMessage(0xEA69u, (unsigned __int16 **)this + 9);
                if ( FontW >= 0 )
                {
                  FontW = WusaLoadMessage(0xEA72u, (unsigned __int16 **)this + 10);
                  if ( FontW >= 0 )
                    goto LABEL_62;
                  v7 = "Failed to get STR_UNINSTALL_START text";
                  v8 = 203;
                }
                else
                {
                  v7 = "Failed to get STR_COPY_START text";
                  v8 = 200;
                }
              }
              else
              {
                v7 = "Failed to get STR_SEARCH_START text";
                v8 = 197;
              }
            }
            else
            {
              v7 = "Failed to get STR_EXPAND_START_UNINSTALL text";
              v8 = 194;
            }
          }
          else
          {
            v7 = "Failed to get STR_EXPAND_START text";
            v8 = 191;
          }
        }
        else
        {
          v7 = "Failed to get STR_EXPAND_START text";
          v8 = 188;
        }
      }
      else
      {
        v7 = "Failure returned by CreateFont()";
        v8 = 185;
      }
    }
    else
    {
      v12 = GetLastError();
      FontW = v12;
      if ( v12 > 0 )
        FontW = (unsigned __int16)v12 | 0x80070000;
      v7 = "Failure returned by InitCommonControlsEx()";
      v8 = 180;
      if ( FontW >= 0 )
        FontW = -2147467259;
    }
    goto LABEL_61;
  }
LABEL_62:
  if ( psz )
  {
    LocalFree(psz);
    psz = 0;
  }
  if ( FontW < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(FontW, (unsigned __int16 **)&hMem);
    v13 = hMem;
    WusaLogDebugEventA(L"AppModule::Init", 210, "Exit with error code 0X%x (%ls)", FontW, (const wchar_t *)hMem);
    if ( v13 )
      LocalFree(v13);
  }
  return (unsigned int)FontW;
}

```

## disassembly

```asm
0x14000f8f0  mov     [rsp-28h+arg_0], rbx
0x14000f8f5  mov     [rsp-28h+arg_8], rsi
0x14000f8fa  push    rbp
0x14000f8fb  push    rdi
0x14000f8fc  push    r12
0x14000f8fe  push    r14
0x14000f900  push    r15
0x14000f902  mov     rbp, rsp
0x14000f905  sub     rsp, 60h
0x14000f909  xor     r14d, r14d
0x14000f90c  lea     r9, RegHandle; RegHandle
0x14000f913  mov     rsi, rdx
0x14000f916  mov     dword ptr [rbp+hMem], r14d
0x14000f91a  mov     rdi, rcx
0x14000f91d  mov     qword ptr [rbp+picce.dwSize], r14
0x14000f921  xor     edx, edx; EnableCallback
0x14000f923  mov     [rbp+psz], r14
0x14000f927  lea     rcx, WUSA_PROVIDER; ProviderId
0x14000f92e  xor     r8d, r8d; CallbackContext
0x14000f931  call    cs:__imp_EventRegister
0x14000f937  lea     r15, aAppmoduleInit; "AppModule::Init"
0x14000f93e  mov     ebx, eax
0x14000f940  test    eax, eax
0x14000f942  jns     short loc_14000F950
0x14000f944  mov     cs:RegHandle, r14
0x14000f94b  jmp     loc_14000FD82
0x14000f950  xor     r9d, r9d; lpName
0x14000f953  xor     r8d, r8d; bInitialState
0x14000f956  xor     ecx, ecx; lpEventAttributes
0x14000f958  lea     r12d, [r9+1]
0x14000f95c  mov     edx, r12d; bManualReset
0x14000f95f  call    cs:__imp_CreateEventW
0x14000f965  mov     [rdi+18h], rax
0x14000f969  test    rax, rax
0x14000f96c  jnz     short loc_14000F99E
0x14000f96e  call    cs:__imp_GetLastError
0x14000f974  mov     ebx, eax
0x14000f976  test    eax, eax
0x14000f978  jle     short loc_14000F983
0x14000f97a  movzx   ebx, ax
0x14000f97d  or      ebx, 80070000h
0x14000f983  test    ebx, ebx
0x14000f985  lea     r8, aFailedToCreate_13; "Failed to create event"
0x14000f98c  mov     eax, 80004005h
0x14000f991  mov     edx, 59h ; 'Y'
0x14000f996  cmovns  ebx, eax
0x14000f999  jmp     loc_14000FD7A
0x14000f99e  mov     edx, 2; dwCoInit
0x14000f9a3  xor     ecx, ecx; pvReserved
0x14000f9a5  call    cs:__imp_CoInitializeEx
0x14000f9ab  mov     [rdi+0ECh], eax
0x14000f9b1  test    eax, eax
0x14000f9b3  jns     short loc_14000F9C6
0x14000f9b5  lea     r8, aFailedToInitia_2; "Failed to initialize COM"
0x14000f9bc  mov     edx, 5Ch ; '\'
0x14000f9c1  jmp     loc_14000FD7A
0x14000f9c6  mov     [rsp+60h+pReserved3], r14; pReserved3
0x14000f9cb  mov     eax, 3
0x14000f9d0  mov     [rsp+60h+dwCapabilities], r14d; dwCapabilities
0x14000f9d5  xor     r9d, r9d; pReserved1
0x14000f9d8  mov     [rsp+60h+pAuthList], r14; pAuthList
0x14000f9dd  xor     r8d, r8d; asAuthSvc
0x14000f9e0  mov     [rsp+60h+dwImpLevel], eax; dwImpLevel
0x14000f9e4  or      edx, 0FFFFFFFFh; cAuthSvc
0x14000f9e7  xor     ecx, ecx; pSecDesc
0x14000f9e9  mov     [rsp+60h+dwAuthnLevel], eax; dwAuthnLevel
0x14000f9ed  mov     [rdi+0ECh], r14d
0x14000f9f4  call    cs:__imp_CoInitializeSecurity
0x14000f9fa  test    eax, eax
0x14000f9fc  jns     short loc_14000FA12
0x14000f9fe  lea     r8, aFailedToInitia_4; "Failed to initialize COM security"
0x14000fa05  mov     edx, 62h ; 'b'
0x14000fa0a  mov     rcx, r15
0x14000fa0d  call    WusaLogDebugEventA
0x14000fa12  lea     rcx, [rdi+100h]; lpCriticalSection
0x14000fa19  mov     edx, 64h ; 'd'; dwSpinCount
0x14000fa1e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000fa24  test    eax, eax
0x14000fa26  jnz     short loc_14000FA58
0x14000fa28  call    cs:__imp_GetLastError
0x14000fa2e  mov     ebx, eax
0x14000fa30  test    eax, eax
0x14000fa32  jle     short loc_14000FA3D
0x14000fa34  movzx   ebx, ax
0x14000fa37  or      ebx, 80070000h
0x14000fa3d  test    ebx, ebx
0x14000fa3f  lea     r8, aFailedToInitia_3; "Failed to initialize critical section"
0x14000fa46  mov     eax, 80004005h
0x14000fa4b  mov     edx, 68h ; 'h'
0x14000fa50  cmovns  ebx, eax
0x14000fa53  jmp     loc_14000FD7A
0x14000fa58  mov     rdx, rsi; unsigned __int16 *
0x14000fa5b  mov     [rdi+128h], r12d
0x14000fa62  mov     rcx, rdi; this
0x14000fa65  call    ?ParseCommandLine@AppModule@@QEAAJPEBG@Z; AppModule::ParseCommandLine(ushort const *)
0x14000fa6a  mov     ebx, eax
0x14000fa6c  test    eax, eax
0x14000fa6e  js      loc_14000FD4F
0x14000fa74  cmp     [rdi+58h], r14d
0x14000fa78  jnz     loc_14000FD4F
0x14000fa7e  lea     rcx, [rbp+hMem]; int *
0x14000fa82  call    ?WusaIsUserAdmin@@YAJPEAH@Z; WusaIsUserAdmin(int *)
0x14000fa87  test    eax, eax
0x14000fa89  js      loc_14000FD09
0x14000fa8f  cmp     dword ptr [rbp+hMem], r14d
0x14000fa93  jz      loc_14000FD09
0x14000fa99  lea     rcx, [rdi+0F0h]; void **
0x14000faa0  call    ?WusaCreateLockFile@@YAJPEAPEAX@Z; WusaCreateLockFile(void * *)
0x14000faa5  test    eax, eax
0x14000faa7  jns     short loc_14000FAF2
0x14000faa9  mov     edx, 0EA60h; DWORD
0x14000faae  mov     qword ptr [rsp+60h+dwAuthnLevel], r14; int *
0x14000fab3  mov     r9d, 0FFFDh; pszIcon
0x14000fab9  mov     r8d, r12d; dwCommonButtons
0x14000fabc  lea     ecx, [rdx+3]; dwMessageId
0x14000fabf  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000fac4  test    eax, eax
0x14000fac6  jns     short loc_14000FADC
0x14000fac8  lea     r8, aFailedToShowMu; "Failed to show multiple instance dialog"
0x14000facf  mov     edx, 8Fh
0x14000fad4  mov     rcx, r15
0x14000fad7  call    WusaLogDebugEventA
0x14000fadc  mov     ebx, 80070652h
0x14000fae1  lea     r8, aErrorAnotherIn; "Error: Another instance of wusa.exe is "...
0x14000fae8  mov     edx, 93h
0x14000faed  jmp     loc_14000FD7A
0x14000faf2  lea     rsi, [rdi+0B0h]
0x14000faf9  mov     rcx, rsi; unsigned __int16 **
0x14000fafc  call    ?WusaSandBoxCreate@@YAJPEAPEAG@Z; WusaSandBoxCreate(ushort * *)
0x14000fb01  mov     ebx, eax
0x14000fb03  mov     rcx, r15
0x14000fb06  test    eax, eax
0x14000fb08  jns     short loc_14000FB1B
0x14000fb0a  lea     r8, aFailedToCreate_14; "Failed to create sandbox"
0x14000fb11  mov     edx, 9Ah
0x14000fb16  jmp     loc_14000FD7D
0x14000fb1b  mov     r9, [rsi]
0x14000fb1e  lea     r8, aCreatedSandbox; "Created sandbox %ls"
0x14000fb25  mov     edx, 9Ch
0x14000fb2a  call    WusaLogDebugEventA
0x14000fb2f  mov     rcx, rdi; this
0x14000fb32  call    ?SetScanCabPath@AppModule@@AEAAJXZ; AppModule::SetScanCabPath(void)
0x14000fb37  mov     ebx, eax
0x14000fb39  test    eax, eax
0x14000fb3b  jns     short loc_14000FB4E
0x14000fb3d  lea     r8, aFailedAppmodul; "Failed: AppModule::SetScanCabPath()"
0x14000fb44  mov     edx, 9Fh
0x14000fb49  jmp     loc_14000FD7A
0x14000fb4e  lea     rdx, [rbp+psz]; unsigned __int16 **
0x14000fb52  mov     ecx, 0EA60h; dwMessageId
0x14000fb57  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fb5c  mov     ebx, eax
0x14000fb5e  test    eax, eax
0x14000fb60  jns     short loc_14000FB81
0x14000fb62  mov     r9d, 0EA60h
0x14000fb68  lea     r8, aFailedToGetApp; "Failed to get application title text, i"...
0x14000fb6f  mov     edx, 0A5h
0x14000fb74  mov     rcx, r15
0x14000fb77  call    WusaLogDebugEventA
0x14000fb7c  jmp     loc_14000FD82
0x14000fb81  mov     rcx, [rbp+psz]; psz
0x14000fb85  call    cs:__imp_SysAllocString
0x14000fb8b  mov     [rdi+0A0h], rax
0x14000fb92  test    rax, rax
0x14000fb95  jnz     short loc_14000FBB5
0x14000fb97  lea     r8, aFailedToAlloca_6; "Failed to allocate BSTR for application"...
0x14000fb9e  mov     edx, 0A8h
0x14000fba3  mov     rcx, r15
0x14000fba6  call    WusaLogDebugEventA
0x14000fbab  mov     ebx, 8007000Eh
0x14000fbb0  jmp     loc_14000FD82
0x14000fbb5  cmp     [rdi+68h], r14d
0x14000fbb9  jnz     loc_14000FD82
0x14000fbbf  lea     rcx, [rbp+picce]; picce
0x14000fbc3  mov     [rbp+picce.dwSize], 8
0x14000fbca  mov     [rbp+picce.dwICC], 20h ; ' '
0x14000fbd1  call    cs:__imp_InitCommonControlsEx
0x14000fbd7  test    eax, eax
0x14000fbd9  jnz     short loc_14000FC0B
0x14000fbdb  call    cs:__imp_GetLastError
0x14000fbe1  mov     ebx, eax
0x14000fbe3  test    eax, eax
0x14000fbe5  jle     short loc_14000FBF0
0x14000fbe7  movzx   ebx, ax
0x14000fbea  or      ebx, 80070000h
0x14000fbf0  test    ebx, ebx
0x14000fbf2  lea     r8, aFailureReturne_15; "Failure returned by InitCommonControlsE"...
0x14000fbf9  mov     eax, 80004005h
0x14000fbfe  mov     edx, 0B4h
0x14000fc03  cmovns  ebx, eax
0x14000fc06  jmp     loc_14000FD7A
0x14000fc0b  mov     rcx, rdi; this
0x14000fc0e  call    ?CreateFontW@AppModule@@AEAAJXZ; AppModule::CreateFontW(void)
0x14000fc13  mov     ebx, eax
0x14000fc15  test    eax, eax
0x14000fc17  jns     short loc_14000FC2A
0x14000fc19  lea     r8, aFailureReturne_3; "Failure returned by CreateFont()"
0x14000fc20  mov     edx, 0B9h
0x14000fc25  jmp     loc_14000FD7A
0x14000fc2a  lea     rdx, [rdi+28h]; unsigned __int16 **
0x14000fc2e  mov     ecx, 0EA6Ah; dwMessageId
0x14000fc33  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fc38  mov     ebx, eax
0x14000fc3a  test    eax, eax
0x14000fc3c  jns     short loc_14000FC4F
0x14000fc3e  lea     r8, aFailedToGetStr_1; "Failed to get STR_EXPAND_START text"
0x14000fc45  mov     edx, 0BCh
0x14000fc4a  jmp     loc_14000FD7A
0x14000fc4f  lea     rdx, [rdi+30h]; unsigned __int16 **
0x14000fc53  mov     ecx, 0EA6Ch; dwMessageId
0x14000fc58  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fc5d  mov     ebx, eax
0x14000fc5f  test    eax, eax
0x14000fc61  jns     short loc_14000FC74
0x14000fc63  lea     r8, aFailedToGetStr_1; "Failed to get STR_EXPAND_START text"
0x14000fc6a  mov     edx, 0BFh
0x14000fc6f  jmp     loc_14000FD7A
0x14000fc74  lea     rdx, [rdi+38h]; unsigned __int16 **
0x14000fc78  mov     ecx, 0EA6Dh; dwMessageId
0x14000fc7d  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fc82  mov     ebx, eax
0x14000fc84  test    eax, eax
0x14000fc86  jns     short loc_14000FC99
0x14000fc88  lea     r8, aFailedToGetStr_3; "Failed to get STR_EXPAND_START_UNINSTAL"...
0x14000fc8f  mov     edx, 0C2h
0x14000fc94  jmp     loc_14000FD7A
0x14000fc99  lea     rdx, [rdi+40h]; unsigned __int16 **
0x14000fc9d  mov     ecx, 0EA67h; dwMessageId
0x14000fca2  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fca7  mov     ebx, eax
0x14000fca9  test    eax, eax
0x14000fcab  jns     short loc_14000FCBE
0x14000fcad  lea     r8, aFailedToGetStr_0; "Failed to get STR_SEARCH_START text"
0x14000fcb4  mov     edx, 0C5h
0x14000fcb9  jmp     loc_14000FD7A
0x14000fcbe  lea     rdx, [rdi+48h]; unsigned __int16 **
0x14000fcc2  mov     ecx, 0EA69h; dwMessageId
0x14000fcc7  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fccc  mov     ebx, eax
0x14000fcce  test    eax, eax
0x14000fcd0  jns     short loc_14000FCE3
0x14000fcd2  lea     r8, aFailedToGetStr_5; "Failed to get STR_COPY_START text"
0x14000fcd9  mov     edx, 0C8h
0x14000fcde  jmp     loc_14000FD7A
0x14000fce3  lea     rdx, [rdi+50h]; unsigned __int16 **
0x14000fce7  mov     ecx, 0EA72h; dwMessageId
0x14000fcec  call    ?WusaLoadMessage@@YAJHPEAPEAGZZ; WusaLoadMessage(int,ushort * *,...)
0x14000fcf1  mov     ebx, eax
0x14000fcf3  test    eax, eax
0x14000fcf5  jns     loc_14000FD82
0x14000fcfb  lea     r8, aFailedToGetStr_4; "Failed to get STR_UNINSTALL_START text"
0x14000fd02  mov     edx, 0CBh
0x14000fd07  jmp     short loc_14000FD7A
0x14000fd09  mov     edx, 0EA60h; DWORD
0x14000fd0e  mov     qword ptr [rsp+60h+dwAuthnLevel], r14; int *
0x14000fd13  mov     r9d, 0FFFEh; pszIcon
0x14000fd19  mov     r8d, r12d; dwCommonButtons
0x14000fd1c  lea     ecx, [rdx+5]; dwMessageId
0x14000fd1f  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000fd24  test    eax, eax
0x14000fd26  jns     short loc_14000FD3C
0x14000fd28  lea     r8, aFailedToShowNo; "Failed to show non administrator dialog"
0x14000fd2f  mov     edx, 7Eh ; '~'
0x14000fd34  mov     rcx, r15
0x14000fd37  call    WusaLogDebugEventA
0x14000fd3c  mov     ebx, 80070005h
0x14000fd41  lea     r8, aUserIsNotAMemb; "User is not a member of the Administrat"...
0x14000fd48  mov     edx, 82h
0x14000fd4d  jmp     short loc_14000FD7A
0x14000fd4f  mov     edx, 0EA60h; DWORD
0x14000fd54  mov     qword ptr [rsp+60h+dwAuthnLevel], r14; int *
0x14000fd59  mov     r9d, 0FFFDh; pszIcon
0x14000fd5f  mov     r8d, r12d; dwCommonButtons
0x14000fd62  lea     ecx, [rdx+1]; dwMessageId
0x14000fd65  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000fd6a  test    eax, eax
0x14000fd6c  jns     short loc_14000FD82
0x14000fd6e  lea     r8, aFailedToShowWe; "Failed to show welcome dialog"
0x14000fd75  mov     edx, 72h ; 'r'
0x14000fd7a  mov     rcx, r15
0x14000fd7d  call    WusaLogDebugEventA
0x14000fd82  mov     rcx, [rbp+psz]; hMem
0x14000fd86  test    rcx, rcx
0x14000fd89  jz      short loc_14000FD95
0x14000fd8b  call    cs:__imp_LocalFree
0x14000fd91  mov     [rbp+psz], r14
0x14000fd95  test    ebx, ebx
0x14000fd97  jns     short loc_14000FDD6
0x14000fd99  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000fd9d  mov     [rbp+hMem], r14
0x14000fda1  mov     ecx, ebx; dwMessageId
0x14000fda3  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000fda8  mov     rdi, [rbp+hMem]
0x14000fdac  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000fdb3  mov     r9d, ebx
0x14000fdb6  mov     qword ptr [rsp+60h+dwAuthnLevel], rdi
0x14000fdbb  mov     edx, 0D2h
0x14000fdc0  mov     rcx, r15
0x14000fdc3  call    WusaLogDebugEventA
0x14000fdc8  test    rdi, rdi
  ... truncated ...
```
