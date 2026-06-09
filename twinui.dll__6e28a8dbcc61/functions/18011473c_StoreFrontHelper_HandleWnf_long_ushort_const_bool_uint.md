# StoreFrontHelper::HandleWnf(long,ushort const *,bool,uint)

- ea: `0x18011473c`
- end: `0x180114a29`
- name: `?HandleWnf@StoreFrontHelper@@AEAAJJPEBG_NI@Z`
- size: `749`
- prototype: `int(StoreFrontHelper *__hidden this, int, const unsigned __int16 *, bool, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180114598`
- `0x180124d54`

## callees

- `0x18000b7e8`
- `0x180030470`
- `0x18003c5e4`
- `0x180078490`
- `0x18011473c`
- `0x180334a3c`
- `0x180334d60`
- `0x180335000`
- `0x180335308`
- `0x180336304`
- `0x18033663c`
- `0x180336744`
- `0x1803367d0`
- `0x18036e038`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801149b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801149c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801149b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801149c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801148da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801147e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801148da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114953`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801147a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801147a2`

## pseudocode

```c
__int64 __fastcall StoreFrontHelper::HandleWnf(
        StoreFrontHelper *this,
        int a2,
        CallerIdentity *a3,
        char a4,
        unsigned int a5)
{
  int PackageInfoFromPackageFullName; // eax
  void *v9; // r14
  int v10; // ebx
  StoreFrontHelperUtils *StringRawBuffer; // rax
  struct Microsoft::WRL::Wrappers::HString *v12; // r8
  int AppDisplayNameFromPackageFamilyName; // eax
  StoreFrontHelper *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  StorePopup *v17; // rax
  bool *v18; // r8
  StoreFrontHelper *v19; // rcx
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // rbx
  StorePopup *v22; // rax
  const unsigned __int16 *v23; // r8
  StorePopup *v25; // rax
  const unsigned __int16 *v26; // rdx
  struct PACKAGE_INFO **v27; // [rsp+20h] [rbp-30h]
  int v28; // [rsp+20h] [rbp-30h]
  HSTRING v29; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v33; // [rsp+80h] [rbp+30h] BYREF
  int v34; // [rsp+84h] [rbp+34h]

  v34 = HIDWORD(this);
  string = 0;
  v33 = 0;
  pv = 0;
  PackageInfoFromPackageFullName = CallerIdentity::GetPackageInfoFromPackageFullName(
                                     a3,
                                     (const unsigned __int16 *)0x100,
                                     (unsigned int)&v33,
                                     (unsigned int *)&pv,
                                     v27);
  v9 = pv;
  v10 = PackageInfoFromPackageFullName;
  if ( PackageInfoFromPackageFullName >= 0 )
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string);
  CoTaskMemFree(v9);
  if ( v10 >= 0 )
  {
    v29 = 0;
    StringRawBuffer = (StoreFrontHelperUtils *)WindowsGetStringRawBuffer(string, 0);
    AppDisplayNameFromPackageFamilyName = StoreFrontHelperUtils::GetAppDisplayNameFromPackageFamilyName(
                                            StringRawBuffer,
                                            (const unsigned __int16 *)&v29,
                                            v12);
    v10 = AppDisplayNameFromPackageFamilyName;
    if ( AppDisplayNameFromPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
        (const char *)(unsigned int)AppDisplayNameFromPackageFamilyName,
        v28);
LABEL_7:
      WindowsDeleteString(v29);
LABEL_32:
      v29 = 0;
      goto LABEL_33;
    }
    pv = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
    Microsoft::WRL::Details::MakeAndInitialize<StoreFrontNotificationHelper,StoreFrontNotificationHelper,>(&pv);
    switch ( a2 )
    {
      case -2143326196:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 98;
          goto LABEL_17;
        }
        v25 = (StorePopup *)WindowsGetStringRawBuffer(string, 0);
        v15 = StorePopup::ShowOfflineWarningDialog(v25, v26);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 99;
          goto LABEL_17;
        }
        break;
      case -2143326195:
        StoreFrontNotificationHelper::ShowNotification(v14, 0, string, v29, 0);
        break;
      case -2143326194:
        StoreFrontNotificationHelper::ShowNotification(v14, 1, string, v29, a5);
        break;
      case -2143322105:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 102;
          goto LABEL_17;
        }
        break;
      case -2143322103:
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 88;
          goto LABEL_17;
        }
        v21 = WindowsGetStringRawBuffer(string, 0);
        v22 = (StorePopup *)WindowsGetStringRawBuffer(v29, 0);
        v15 = StorePopup::ShowTrialExpiredDialog(v22, v21, v23);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 89;
          goto LABEL_17;
        }
        break;
      case -2143322008:
        LOBYTE(v33) = 0;
        v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
        v10 = v15;
        if ( v15 < 0 )
        {
          v16 = 107;
          goto LABEL_17;
        }
        v17 = (StorePopup *)WindowsGetStringRawBuffer(v29, 0);
        if ( (int)StorePopup::ShowConcurrencyLimitDialog(v17, (const unsigned __int16 *)&v33, v18) >= 0 )
        {
          if ( (_BYTE)v33 )
          {
            WindowsGetStringRawBuffer(string, 0);
            v15 = StoreFrontHelper::ResumeApp(v19, (const unsigned __int16 *)a3, v20);
            v10 = v15;
            if ( v15 < 0 )
            {
              v16 = 111;
              goto LABEL_17;
            }
          }
        }
        break;
      default:
        if ( a4 )
        {
          v15 = StoreFrontHelper::ForceAppShutdown(v14, (const unsigned __int16 *)a3);
          v10 = v15;
          if ( v15 < 0 )
          {
            v16 = 118;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
              (const char *)(unsigned int)v15,
              v28);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
            goto LABEL_7;
          }
        }
        break;
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pv);
    WindowsDeleteString(v29);
    v10 = 0;
    goto LABEL_32;
  }
  StoreFrontHelperTelemetry::TraceLoggingInfo("GetFamilyNameFromPackageFullName failed with 0x%x", v10);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D,
    (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
    (const char *)(unsigned int)v10,
    v28);
LABEL_33:
  WindowsDeleteString(string);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18011473c  mov     [rsp-28h+arg_8], rbx
0x180114741  mov     [rsp-28h+arg_10], rsi
0x180114746  mov     qword ptr [rsp-28h+arg_0], rcx
0x18011474b  push    rbp
0x18011474c  push    rdi
0x18011474d  push    r12
0x18011474f  push    r14
0x180114751  push    r15
0x180114753  mov     rbp, rsp
0x180114756  sub     rsp, 50h
0x18011475a  mov     rsi, r8
0x18011475d  xor     r12d, r12d
0x180114760  mov     r15b, r9b
0x180114763  mov     [rbp+string], r12
0x180114767  mov     edi, edx
0x180114769  mov     [rbp+arg_0], r12d
0x18011476d  mov     rcx, rsi; this
0x180114770  mov     [rbp+pv], r12
0x180114774  lea     r9, [rbp+pv]; unsigned int *
0x180114778  mov     edx, 100h; unsigned __int16 *
0x18011477d  lea     r8, [rbp+arg_0]; unsigned int
0x180114781  call    ?GetPackageInfoFromPackageFullName@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z; CallerIdentity::GetPackageInfoFromPackageFullName(ushort const *,uint,uint *,PACKAGE_INFO * *)
0x180114786  mov     r14, [rbp+pv]
0x18011478a  mov     ebx, eax
0x18011478c  test    eax, eax
0x18011478e  js      short loc_18011479F
0x180114790  lea     rdx, [r14+18h]
0x180114794  lea     rcx, [rbp+string]; string
0x180114798  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18011479d  mov     ebx, eax
0x18011479f  mov     rcx, r14; pv
0x1801147a2  call    cs:__imp_CoTaskMemFree
0x1801147a8  test    ebx, ebx
0x1801147aa  jns     short loc_1801147D7
0x1801147ac  mov     edx, ebx
0x1801147ae  lea     rcx, aGetfamilynamef; "GetFamilyNameFromPackageFullName failed"...
0x1801147b5  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x1801147ba  mov     rcx, [rbp+28h]; this
0x1801147be  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x1801147c5  mov     r9d, ebx; char *
0x1801147c8  mov     edx, 4Dh ; 'M'; void *
0x1801147cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801147d2  jmp     loc_1801149BF
0x1801147d7  mov     rcx, [rbp+string]; string
0x1801147db  xor     edx, edx; length
0x1801147dd  mov     [rbp+var_20], r12
0x1801147e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1801147e7  mov     rcx, rax; this
0x1801147ea  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x1801147ee  call    ?GetAppDisplayNameFromPackageFamilyName@StoreFrontHelperUtils@@YAJPEBGAEAVHString@Wrappers@WRL@Microsoft@@@Z; StoreFrontHelperUtils::GetAppDisplayNameFromPackageFamilyName(ushort const *,Microsoft::WRL::Wrappers::HString &)
0x1801147f3  mov     ebx, eax
0x1801147f5  test    eax, eax
0x1801147f7  jns     short loc_180114820
0x1801147f9  mov     rcx, [rbp+28h]; this
0x1801147fd  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x180114804  mov     r9d, eax; char *
0x180114807  mov     edx, 50h ; 'P'; void *
0x18011480c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114811  mov     rcx, [rbp+var_20]; string
0x180114815  call    cs:__imp_WindowsDeleteString
0x18011481b  jmp     loc_1801149BB
0x180114820  lea     rcx, [rbp+pv]
0x180114824  mov     [rbp+pv], r12
0x180114828  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011482d  lea     rcx, [rbp+pv]
0x180114831  call    ??$MakeAndInitialize@VStoreFrontNotificationHelper@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVStoreFrontNotificationHelper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<StoreFrontNotificationHelper,StoreFrontNotificationHelper,>(StoreFrontNotificationHelper * *)
0x180114836  cmp     edi, 803F700Ch
0x18011483c  jz      loc_1801149ED
0x180114842  cmp     edi, 803F700Dh
0x180114848  jz      loc_1801149E4
0x18011484e  cmp     edi, 803F700Eh
0x180114854  jz      loc_18011498C
0x18011485a  cmp     edi, 803F8007h
0x180114860  jz      loc_180114974
0x180114866  cmp     edi, 803F8009h
0x18011486c  jz      loc_180114926
0x180114872  cmp     edi, 803F8068h
0x180114878  jz      short loc_1801148BB
0x18011487a  test    r15b, r15b
0x18011487d  jz      loc_1801149A5
0x180114883  mov     rdx, rsi; unsigned __int16 *
0x180114886  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011488b  mov     ebx, eax
0x18011488d  test    eax, eax
0x18011488f  jns     loc_1801149A5
0x180114895  mov     edx, 76h ; 'v'; void *
0x18011489a  mov     rcx, [rbp+28h]; this
0x18011489e  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x1801148a5  mov     r9d, eax; char *
0x1801148a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801148ad  lea     rcx, [rbp+pv]
0x1801148b1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801148b6  jmp     loc_180114811
0x1801148bb  mov     rdx, rsi; unsigned __int16 *
0x1801148be  mov     byte ptr [rbp+arg_0], r12b
0x1801148c2  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x1801148c7  mov     ebx, eax
0x1801148c9  test    eax, eax
0x1801148cb  jns     short loc_1801148D4
0x1801148cd  mov     edx, 6Bh ; 'k'
0x1801148d2  jmp     short loc_18011489A
0x1801148d4  mov     rcx, [rbp+var_20]; string
0x1801148d8  xor     edx, edx; length
0x1801148da  call    cs:__imp_WindowsGetStringRawBuffer
0x1801148e0  mov     rcx, rax; this
0x1801148e3  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x1801148e7  call    ?ShowConcurrencyLimitDialog@StorePopup@@YAJPEBGAEA_N@Z; StorePopup::ShowConcurrencyLimitDialog(ushort const *,bool &)
0x1801148ec  test    eax, eax
0x1801148ee  js      loc_1801149A5
0x1801148f4  cmp     byte ptr [rbp+arg_0], r12b
0x1801148f8  jz      loc_1801149A5
0x1801148fe  mov     rcx, [rbp+string]; string
0x180114902  xor     edx, edx; length
0x180114904  call    cs:__imp_WindowsGetStringRawBuffer
0x18011490a  mov     rdx, rsi; unsigned __int16 *
0x18011490d  call    ?ResumeApp@StoreFrontHelper@@AEAAJPEBG0@Z; StoreFrontHelper::ResumeApp(ushort const *,ushort const *)
0x180114912  mov     ebx, eax
0x180114914  test    eax, eax
0x180114916  jns     loc_1801149A5
0x18011491c  mov     edx, 6Fh ; 'o'
0x180114921  jmp     loc_18011489A
0x180114926  mov     rdx, rsi; unsigned __int16 *
0x180114929  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011492e  mov     ebx, eax
0x180114930  test    eax, eax
0x180114932  jns     short loc_18011493E
0x180114934  mov     edx, 58h ; 'X'
0x180114939  jmp     loc_18011489A
0x18011493e  mov     rcx, [rbp+string]; string
0x180114942  xor     edx, edx; length
0x180114944  call    cs:__imp_WindowsGetStringRawBuffer
0x18011494a  mov     rcx, [rbp+var_20]; string
0x18011494e  xor     edx, edx; length
0x180114950  mov     rbx, rax
0x180114953  call    cs:__imp_WindowsGetStringRawBuffer
0x180114959  mov     rcx, rax; this
0x18011495c  mov     rdx, rbx; unsigned __int16 *
0x18011495f  call    ?ShowTrialExpiredDialog@StorePopup@@YAJPEBG0@Z; StorePopup::ShowTrialExpiredDialog(ushort const *,ushort const *)
0x180114964  mov     ebx, eax
0x180114966  test    eax, eax
0x180114968  jns     short loc_1801149A5
0x18011496a  mov     edx, 59h ; 'Y'
0x18011496f  jmp     loc_18011489A
0x180114974  mov     rdx, rsi; unsigned __int16 *
0x180114977  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x18011497c  mov     ebx, eax
0x18011497e  test    eax, eax
0x180114980  jns     short loc_1801149A5
0x180114982  mov     edx, 66h ; 'f'
0x180114987  jmp     loc_18011489A
0x18011498c  mov     eax, [rbp+arg_20]
0x18011498f  mov     edx, 1
0x180114994  mov     [rsp+50h+var_30], eax
0x180114998  mov     r8, [rbp+string]
0x18011499c  mov     r9, [rbp+var_20]
0x1801149a0  call    ?ShowNotification@StoreFrontNotificationHelper@@QEAAJW4NotificationType@@PEAUHSTRING__@@1I@Z; StoreFrontNotificationHelper::ShowNotification(NotificationType,HSTRING__ *,HSTRING__ *,uint)
0x1801149a5  lea     rcx, [rbp+pv]
0x1801149a9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801149ae  mov     rcx, [rbp+var_20]; string
0x1801149b2  call    cs:__imp_WindowsDeleteString
0x1801149b8  mov     ebx, r12d
0x1801149bb  mov     [rbp+var_20], r12
0x1801149bf  mov     rcx, [rbp+string]; string
0x1801149c3  call    cs:__imp_WindowsDeleteString
0x1801149c9  lea     r11, [rsp+50h+var_s0]
0x1801149ce  mov     eax, ebx
0x1801149d0  mov     rbx, [r11+38h]
0x1801149d4  mov     rsi, [r11+40h]
0x1801149d8  mov     rsp, r11
0x1801149db  pop     r15
0x1801149dd  pop     r14
0x1801149df  pop     r12
0x1801149e1  pop     rdi
0x1801149e2  pop     rbp
0x1801149e3  retn
0x1801149e4  mov     [rsp+50h+var_30], r12d
0x1801149e9  xor     edx, edx
0x1801149eb  jmp     short loc_180114998
0x1801149ed  mov     rdx, rsi; unsigned __int16 *
0x1801149f0  call    ?ForceAppShutdown@StoreFrontHelper@@AEAAJPEBG@Z; StoreFrontHelper::ForceAppShutdown(ushort const *)
0x1801149f5  mov     ebx, eax
0x1801149f7  test    eax, eax
0x1801149f9  jns     short loc_180114A05
0x1801149fb  mov     edx, 62h ; 'b'
0x180114a00  jmp     loc_18011489A
0x180114a05  mov     rcx, [rbp+string]; string
0x180114a09  xor     edx, edx; length
0x180114a0b  call    cs:__imp_WindowsGetStringRawBuffer
0x180114a11  mov     rcx, rax; this
0x180114a14  call    ?ShowOfflineWarningDialog@StorePopup@@YAJPEBG@Z; StorePopup::ShowOfflineWarningDialog(ushort const *)
0x180114a19  mov     ebx, eax
0x180114a1b  test    eax, eax
0x180114a1d  jns     short loc_1801149A5
0x180114a1f  mov     edx, 63h ; 'c'
0x180114a24  jmp     loc_18011489A
```
