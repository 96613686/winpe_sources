# CUrlDownload::CUrlDownload(CUrlDownloadSink *,uint)

- ea: `0x18000597c`
- end: `0x180005b9d`
- name: `??0CUrlDownload@@QEAA@PEAVCUrlDownloadSink@@I@Z`
- size: `545`
- prototype: `CUrlDownload *__fastcall(CUrlDownload *__hidden this, struct CUrlDownloadSink *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021e40`

## callees

- `0x18000597c`
- `0x18002924e`

## import_xrefs

- `USER32!RegisterClassW` at `0x180005b81`
- `USER32!RegisterClassW` at `0x180005b81`
- `USER32!RegisterClipboardFormatW` at `0x180005ab3`
- `USER32!RegisterClipboardFormatW` at `0x180005ab3`
- `SHLWAPI!SHGetValueW` at `0x180005a93`
- `SHLWAPI!SHGetValueW` at `0x180005a93`
- `WININET!GetUrlCacheConfigInfoW` at `0x180005af0`
- `WININET!GetUrlCacheConfigInfoW` at `0x180005af0`

## pseudocode

```c
CUrlDownload *__fastcall CUrlDownload::CUrlDownload(CUrlDownload *this, struct CUrlDownloadSink *a2)
{
  _DWORD *v3; // rdi
  WNDCLASSW WndClass; // [rsp+30h] [rbp-D0h] BYREF
  _INTERNET_CACHE_CONFIG_INFOW CacheConfigInfo; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbCacheConfigInfo; // [rsp+2D0h] [rbp+1D0h] BYREF
  DWORD pcbData; // [rsp+2E0h] [rbp+1E0h] BYREF

  *(_QWORD *)this = &CUrlDownload::`vftable'{for `IOleClientSite'};
  *((_QWORD *)this + 1) = &CUrlDownload::`vftable'{for `IPropertyNotifySink'};
  *((_QWORD *)this + 2) = &CUrlDownload::`vftable'{for `IOleCommandTarget'};
  *((_QWORD *)this + 3) = &CUrlDownload::`vftable'{for `IDispatch'};
  *((_QWORD *)this + 4) = &CUrlDownload::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 5) = &CUrlDownload::`vftable'{for `IAuthenticate'};
  *((_QWORD *)this + 6) = &CUrlDownload::`vftable'{for `IHlinkFrame'};
  *((_QWORD *)this + 7) = &CUrlDownload::`vftable'{for `IInternetSecurityManager'};
  *((_QWORD *)this + 8) = &CUrlDownload::`vftable'{for `IHttpSecurity'};
  _InterlockedIncrement((volatile signed __int32 *)&g_cObj);
  *((_QWORD *)this + 10) = a2;
  v3 = (_DWORD *)((char *)this + 96);
  *((_QWORD *)this + 9) = 1;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  pcbData = 4;
  if ( SHGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Webcheck",
         L"Timeout",
         0,
         (char *)this + 96,
         &pcbData) )
  {
    *v3 = 120;
  }
  if ( !g_cfHTML )
    g_cfHTML = RegisterClipboardFormatW(L"text/html");
  memset_0(&CacheConfigInfo.dwContainer, 0, 0x22Cu);
  cbCacheConfigInfo = 560;
  CacheConfigInfo.dwStructSize = 560;
  if ( GetUrlCacheConfigInfoW(&CacheConfigInfo, &cbCacheConfigInfo, 0x80u) )
    *((_DWORD *)this + 186) = CacheConfigInfo.dwSyncMode - 2 > 2;
  *((_DWORD *)this + 190) = 1073776512;
  if ( *((_DWORD *)this + 186) )
    *((_DWORD *)this + 190) = 1073784704;
  if ( !g_lRegisteredWnd )
  {
    g_lRegisteredWnd = 1;
    WndClass.lpfnWndProc = (WNDPROC)UrlDownloadWndProc;
    WndClass.hInstance = g_hInst;
    *(_QWORD *)&WndClass.style = 0;
    WndClass.lpszClassName = L"WCUrlDlClass";
    *(_QWORD *)&WndClass.cbClsExtra = 0;
    memset(&WndClass.hIcon, 0, 32);
    RegisterClassW(&WndClass);
  }
  return this;
}

```

## disassembly

```asm
0x18000597c  mov     [rsp-8+arg_8], rbx
0x180005981  mov     [rsp-8+arg_10], r8d
0x180005986  push    rbp
0x180005987  push    rsi
0x180005988  push    rdi
0x180005989  lea     rbp, [rsp-1B0h]
0x180005991  sub     rsp, 2B0h
0x180005998  lea     rax, ??_7CUrlDownload@@6BIOleClientSite@@@; const CUrlDownload::`vftable'{for `IOleClientSite'}
0x18000599f  xor     esi, esi
0x1800059a1  mov     [rcx], rax
0x1800059a4  mov     rbx, rcx
0x1800059a7  lea     rax, ??_7CUrlDownload@@6BIPropertyNotifySink@@@; const CUrlDownload::`vftable'{for `IPropertyNotifySink'}
0x1800059ae  mov     [rbp+1C0h+arg_10], esi
0x1800059b4  mov     [rcx+8], rax
0x1800059b8  lea     rax, ??_7CUrlDownload@@6BIOleCommandTarget@@@; const CUrlDownload::`vftable'{for `IOleCommandTarget'}
0x1800059bf  mov     [rcx+10h], rax
0x1800059c3  lea     rax, ??_7CUrlDownload@@6BIDispatch@@@; const CUrlDownload::`vftable'{for `IDispatch'}
0x1800059ca  mov     [rcx+18h], rax
0x1800059ce  lea     rax, ??_7CUrlDownload@@6BIServiceProvider@@@; const CUrlDownload::`vftable'{for `IServiceProvider'}
0x1800059d5  mov     [rcx+20h], rax
0x1800059d9  lea     rax, ??_7CUrlDownload@@6BIAuthenticate@@@; const CUrlDownload::`vftable'{for `IAuthenticate'}
0x1800059e0  mov     [rcx+28h], rax
0x1800059e4  lea     rax, ??_7CUrlDownload@@6BIHlinkFrame@@@; const CUrlDownload::`vftable'{for `IHlinkFrame'}
0x1800059eb  mov     [rcx+30h], rax
0x1800059ef  lea     rax, ??_7CUrlDownload@@6BIInternetSecurityManager@@@; const CUrlDownload::`vftable'{for `IInternetSecurityManager'}
0x1800059f6  mov     [rcx+38h], rax
0x1800059fa  lea     rax, ??_7CUrlDownload@@6BIHttpSecurity@@@; const CUrlDownload::`vftable'{for `IHttpSecurity'}
0x180005a01  mov     [rcx+40h], rax
0x180005a05  lock inc cs:?g_cObj@@3KA; ulong g_cObj
0x180005a0c  mov     [rcx+50h], rdx
0x180005a10  lea     rdi, [rcx+60h]
0x180005a14  lea     rax, [rbp+1C0h+arg_10]
0x180005a1b  mov     qword ptr [rcx+48h], 1
0x180005a23  mov     [rcx+68h], rsi
0x180005a27  lea     r8, pszValue; "Timeout"
0x180005a2e  mov     [rcx+70h], rsi
0x180005a32  lea     rdx, ?c_szRegKey@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180005a39  mov     [rcx+78h], rsi
0x180005a3d  xor     r9d, r9d; pdwType
0x180005a40  mov     [rcx+88h], rsi
0x180005a47  mov     [rcx+0A0h], rsi
0x180005a4e  mov     [rcx+0B0h], rsi
0x180005a55  mov     [rcx+0B8h], rsi
0x180005a5c  mov     [rcx+2E0h], rsi
0x180005a63  mov     [rcx+2F0h], rsi
0x180005a6a  mov     [rcx+300h], rsi
0x180005a71  mov     [rcx+308h], rsi
0x180005a78  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180005a7f  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180005a84  mov     [rsp+2C0h+pvData], rdi; pvData
0x180005a89  mov     [rbp+1C0h+arg_10], 4
0x180005a93  call    cs:__imp_SHGetValueW
0x180005a99  test    eax, eax
0x180005a9b  jz      short loc_180005AA3
0x180005a9d  mov     dword ptr [rdi], 78h ; 'x'
0x180005aa3  cmp     cs:?g_cfHTML@@3GA, si; ushort g_cfHTML
0x180005aaa  jnz     short loc_180005AC0
0x180005aac  lea     rcx, szFormat; "text/html"
0x180005ab3  call    cs:__imp_RegisterClipboardFormatW
0x180005ab9  mov     cs:?g_cfHTML@@3GA, ax; ushort g_cfHTML
0x180005ac0  xor     edx, edx; Val
0x180005ac2  lea     rcx, [rbp+1C0h+CacheConfigInfo.dwContainer]; void *
0x180005ac6  mov     r8d, 22Ch; Size
0x180005acc  call    memset_0
0x180005ad1  mov     eax, 230h
0x180005ad6  lea     rdx, [rbp+1C0h+cbCacheConfigInfo]; lpcbCacheConfigInfo
0x180005add  mov     r8d, 80h; dwFieldControl
0x180005ae3  mov     [rbp+1C0h+cbCacheConfigInfo], eax
0x180005ae9  lea     rcx, [rbp+1C0h+CacheConfigInfo]; lpCacheConfigInfo
0x180005aed  mov     [rbp+1C0h+CacheConfigInfo.dwStructSize], eax
0x180005af0  call    cs:__imp_GetUrlCacheConfigInfoW
0x180005af6  test    eax, eax
0x180005af8  jz      short loc_180005B0E
0x180005afa  mov     eax, [rbp+1C0h+CacheConfigInfo.dwSyncMode]
0x180005afd  mov     ecx, esi
0x180005aff  add     eax, 0FFFFFFFEh
0x180005b02  cmp     eax, 2
0x180005b05  setnbe  cl
0x180005b08  mov     [rbx+2E8h], ecx
0x180005b0e  mov     dword ptr [rbx+2F8h], 40008780h
0x180005b18  cmp     [rbx+2E8h], esi
0x180005b1e  jz      short loc_180005B2A
0x180005b20  mov     dword ptr [rbx+2F8h], 4000A780h
0x180005b2a  cmp     cs:?g_lRegisteredWnd@@3JA, esi; long g_lRegisteredWnd
0x180005b30  jnz     short loc_180005B87
0x180005b32  lea     rax, ?UrlDownloadWndProc@@YA_JPEAUHWND__@@I_K_J@Z; UrlDownloadWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180005b39  mov     cs:?g_lRegisteredWnd@@3JA, 1; long g_lRegisteredWnd
0x180005b43  mov     [rsp+2C0h+WndClass.lpfnWndProc], rax
0x180005b48  lea     rcx, [rsp+2C0h+WndClass]; lpWndClass
0x180005b4d  mov     rax, cs:g_hInst
0x180005b54  xorps   xmm0, xmm0
0x180005b57  mov     [rsp+2C0h+WndClass.hInstance], rax
0x180005b5c  xorps   xmm1, xmm1
0x180005b5f  lea     rax, ClassName; "WCUrlDlClass"
0x180005b66  mov     qword ptr [rsp+2C0h+WndClass.style], rsi
0x180005b6b  mov     [rsp+2C0h+WndClass.lpszClassName], rax
0x180005b70  mov     qword ptr [rsp+2C0h+WndClass.cbClsExtra], rsi
0x180005b75  movdqa  xmmword ptr [rsp+2C0h+WndClass.hIcon], xmm0
0x180005b7b  movdqa  xmmword ptr [rsp+2C0h+WndClass.hbrBackground], xmm1
0x180005b81  call    cs:__imp_RegisterClassW
0x180005b87  mov     rax, rbx
0x180005b8a  mov     rbx, [rsp+2C0h+arg_8]
0x180005b92  add     rsp, 2B0h
0x180005b99  pop     rdi
0x180005b9a  pop     rsi
0x180005b9b  pop     rbp
0x180005b9c  retn
```
