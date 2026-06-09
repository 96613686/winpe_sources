# CWallpaperCore::~CWallpaperCore(void)

- ea: `0x18003a7a8`
- end: `0x18003aa34`
- name: `??1CWallpaperCore@@AEAA@XZ`
- size: `652`
- prototype: `void __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e020`

## callees

- `0x180008c98`
- `0x18003a7a8`
- `0x1800429c4`
- `0x18004f490`
- `0x180054f64`
- `0x180054fb4`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18003a8e6`
- `SHELL32!__imp_ILFree` at `0x18003a974`
- `SHELL32!__imp_ILFree` at `0x18003a8e6`
- `SHELL32!__imp_ILFree` at `0x18003a974`
- `SHELL32!__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z` at `0x18003a8ce`
- `SHELL32!__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z` at `0x18003a8ce`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a802`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003a802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a957`
- `USER32!DestroyWindow` at `0x18003a89d`
- `USER32!DestroyWindow` at `0x18003a89d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWallpaperCore::~CWallpaperCore(CWallpaperCore *this)
{
  struct _DPA *v2; // rcx
  struct _DPA *v3; // rcx
  struct _DPA *v4; // rcx
  HWND v5; // rcx
  ITEMIDLIST *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int i; // edi
  struct _DPA *v10; // rcx
  struct _DPA *v11; // rcx
  struct _DPA *v12; // rcx

  *(_QWORD *)this = &CWallpaperCore::`vftable'{for `IBrowserFrameSite'};
  *((_QWORD *)this + 1) = &CWallpaperCore::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 2) = &CWallpaperCore::`vftable'{for `IWallpaperTasksCallback'};
  RegSetKeyValueW(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers\\Colors",
    0,
    3u,
    (char *)this + 104,
    0x40u);
  CWallpaperCore::_SaveUserPaths(this);
  v2 = (struct _DPA *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    DPA_DestroyCallback(
      v2,
      CDPA_Base<CWallpaperCore::REGISTRY_WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB,
      0);
    *((_QWORD *)this + 12) = 0;
    DPA_Destroy(0);
    *((_QWORD *)this + 12) = 0;
  }
  v3 = (struct _DPA *)*((_QWORD *)this + 11);
  if ( v3 )
  {
    DPA_DestroyCallback(v3, CDPA_Base<CWallpaperCore::WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB, 0);
    *((_QWORD *)this + 11) = 0;
    DPA_Destroy(0);
    *((_QWORD *)this + 11) = 0;
  }
  v4 = (struct _DPA *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    DPA_DestroyCallback(v4, CDPA_Base<CWallpaperCore::WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB, 0);
    *((_QWORD *)this + 10) = 0;
    DPA_Destroy(0);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = (HWND)*((_QWORD *)this + 7);
  if ( v5 )
  {
    *((_DWORD *)this + 6) = 1000;
    DestroyWindow(v5);
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 6) = 0;
  }
  *((_QWORD *)this + 21) = 0;
  SafeRelease<IUnknown>((char *)this + 64);
  if ( *((_BYTE *)this + 182) )
    UpdateWallpaperTransition(1, 0);
  v6 = (ITEMIDLIST *)*((_QWORD *)this + 24);
  if ( v6 )
    ILFree(v6);
  CoTaskMemFree(*((LPVOID *)this + 25));
  v7 = *((_QWORD *)this + 53);
  *((_QWORD *)this + 53) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 52);
  *((_QWORD *)this + 52) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  for ( i = 0; i < *((_DWORD *)this + 55); ++i )
    CoTaskMemFree(*((LPVOID *)this + i + 28));
  ILFree(*((LPITEMIDLIST *)this + 55));
  if ( *((_QWORD *)this + 12) )
  {
    if ( !IsProcessShutdownInProgress() )
    {
      v10 = (struct _DPA *)*((_QWORD *)this + 12);
      if ( v10 )
      {
        DPA_DestroyCallback(
          v10,
          CDPA_Base<CWallpaperCore::REGISTRY_WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB,
          0);
        *((_QWORD *)this + 12) = 0;
        DPA_Destroy(0);
        *((_QWORD *)this + 12) = 0;
      }
    }
  }
  if ( *((_QWORD *)this + 11) )
  {
    if ( !IsProcessShutdownInProgress() )
    {
      v11 = (struct _DPA *)*((_QWORD *)this + 11);
      if ( v11 )
      {
        DPA_DestroyCallback(
          v11,
          CDPA_Base<CWallpaperCore::WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB,
          0);
        *((_QWORD *)this + 11) = 0;
        DPA_Destroy(0);
        *((_QWORD *)this + 11) = 0;
      }
    }
  }
  if ( *((_QWORD *)this + 10) && !IsProcessShutdownInProgress() )
  {
    v12 = (struct _DPA *)*((_QWORD *)this + 10);
    if ( v12 )
    {
      DPA_DestroyCallback(
        v12,
        CDPA_Base<CWallpaperCore::WALLPAPER_PATH,CTContainer_PolicyNewMem>::_StandardDestroyCB,
        0);
      *((_QWORD *)this + 10) = 0;
      DPA_Destroy(0);
      *((_QWORD *)this + 10) = 0;
    }
  }
}

```

## disassembly

```asm
0x18003a7a8  mov     [rsp+arg_0], rbx
0x18003a7ad  mov     [rsp+arg_8], rsi
0x18003a7b2  push    rdi
0x18003a7b3  sub     rsp, 30h
0x18003a7b7  mov     rbx, rcx
0x18003a7ba  lea     rax, ??_7CWallpaperCore@@6BIBrowserFrameSite@@@; const CWallpaperCore::`vftable'{for `IBrowserFrameSite'}
0x18003a7c1  mov     [rcx], rax
0x18003a7c4  lea     rax, ??_7CWallpaperCore@@6BIServiceProvider@@@; const CWallpaperCore::`vftable'{for `IServiceProvider'}
0x18003a7cb  mov     [rcx+8], rax
0x18003a7cf  lea     rax, ??_7CWallpaperCore@@6BIWallpaperTasksCallback@@@; const CWallpaperCore::`vftable'{for `IWallpaperTasksCallback'}
0x18003a7d6  mov     [rcx+10h], rax
0x18003a7da  lea     rax, [rcx+68h]
0x18003a7de  mov     [rsp+38h+cbData], 40h ; '@'; cbData
0x18003a7e6  mov     [rsp+38h+lpData], rax; lpData
0x18003a7eb  mov     r9d, 3; dwType
0x18003a7f1  xor     r8d, r8d; lpValueName
0x18003a7f4  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003a7fb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003a802  call    cs:__imp_RegSetKeyValueW
0x18003a809  nop     dword ptr [rax+rax+00h]
0x18003a80e  mov     rcx, rbx; this
0x18003a811  call    ?_SaveUserPaths@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_SaveUserPaths(void)
0x18003a816  mov     rcx, [rbx+60h]; hdpa
0x18003a81a  xor     esi, esi
0x18003a81c  test    rcx, rcx
0x18003a81f  jz      short loc_18003A83F
0x18003a821  xor     r8d, r8d; pData
0x18003a824  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UREGISTRY_WALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUREGISTRY_WALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003a82b  call    DPA_DestroyCallback
0x18003a830  mov     [rbx+60h], rsi
0x18003a834  xor     ecx, ecx; hdpa
0x18003a836  call    DPA_Destroy
0x18003a83b  mov     [rbx+60h], rsi
0x18003a83f  mov     rcx, [rbx+58h]; hdpa
0x18003a843  test    rcx, rcx
0x18003a846  jz      short loc_18003A866
0x18003a848  xor     r8d, r8d; pData
0x18003a84b  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UWALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUWALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003a852  call    DPA_DestroyCallback
0x18003a857  mov     [rbx+58h], rsi
0x18003a85b  xor     ecx, ecx; hdpa
0x18003a85d  call    DPA_Destroy
0x18003a862  mov     [rbx+58h], rsi
0x18003a866  mov     rcx, [rbx+50h]; hdpa
0x18003a86a  test    rcx, rcx
0x18003a86d  jz      short loc_18003A88D
0x18003a86f  xor     r8d, r8d; pData
0x18003a872  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UWALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUWALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003a879  call    DPA_DestroyCallback
0x18003a87e  mov     [rbx+50h], rsi
0x18003a882  xor     ecx, ecx; hdpa
0x18003a884  call    DPA_Destroy
0x18003a889  mov     [rbx+50h], rsi
0x18003a88d  mov     rcx, [rbx+38h]; hWnd
0x18003a891  test    rcx, rcx
0x18003a894  jz      short loc_18003A8B0
0x18003a896  mov     dword ptr [rbx+18h], 3E8h
0x18003a89d  call    cs:__imp_DestroyWindow
0x18003a8a4  nop     dword ptr [rax+rax+00h]
0x18003a8a9  mov     [rbx+38h], rsi
0x18003a8ad  mov     [rbx+18h], esi
0x18003a8b0  mov     [rbx+0A8h], rsi
0x18003a8b7  lea     rcx, [rbx+40h]
0x18003a8bb  call    ??$SafeRelease@UIUnknown@@@@YAXPEAPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown * *)
0x18003a8c0  cmp     [rbx+0B6h], sil
0x18003a8c7  jz      short loc_18003A8DA
0x18003a8c9  xor     edx, edx
0x18003a8cb  lea     ecx, [rdx+1]
0x18003a8ce  call    cs:__imp_?UpdateWallpaperTransition@@YAJW4WALLPAPER_TRANSITION_TYPE@@_J@Z; UpdateWallpaperTransition(WALLPAPER_TRANSITION_TYPE,__int64)
0x18003a8d5  nop     dword ptr [rax+rax+00h]
0x18003a8da  mov     rcx, [rbx+0C0h]; pidl
0x18003a8e1  test    rcx, rcx
0x18003a8e4  jz      short loc_18003A8F2
0x18003a8e6  call    cs:__imp_ILFree
0x18003a8ed  nop     dword ptr [rax+rax+00h]
0x18003a8f2  mov     rcx, [rbx+0C8h]; pv
0x18003a8f9  call    cs:__imp_CoTaskMemFree
0x18003a900  nop     dword ptr [rax+rax+00h]
0x18003a905  mov     rcx, [rbx+1A8h]
0x18003a90c  mov     [rbx+1A8h], rsi
0x18003a913  test    rcx, rcx
0x18003a916  jz      short loc_18003A924
0x18003a918  mov     rax, [rcx]
0x18003a91b  mov     rax, [rax+10h]
0x18003a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a924  mov     rcx, [rbx+1A0h]
0x18003a92b  mov     [rbx+1A0h], rsi
0x18003a932  test    rcx, rcx
0x18003a935  jz      short loc_18003A943
0x18003a937  mov     rax, [rcx]
0x18003a93a  mov     rax, [rax+10h]
0x18003a93e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a943  mov     edi, esi
0x18003a945  cmp     [rbx+0DCh], esi
0x18003a94b  jbe     short loc_18003A96D
0x18003a94d  mov     ecx, edi
0x18003a94f  mov     rcx, [rbx+rcx*8+0E0h]; pv
0x18003a957  call    cs:__imp_CoTaskMemFree
0x18003a95e  nop     dword ptr [rax+rax+00h]
0x18003a963  inc     edi
0x18003a965  cmp     edi, [rbx+0DCh]
0x18003a96b  jb      short loc_18003A94D
0x18003a96d  mov     rcx, [rbx+1B8h]; pidl
0x18003a974  call    cs:__imp_ILFree
0x18003a97b  nop     dword ptr [rax+rax+00h]
0x18003a980  nop
0x18003a981  cmp     [rbx+60h], rsi
0x18003a985  jz      short loc_18003A9B7
0x18003a987  call    ?IsProcessShutdownInProgress@@YA_NXZ; IsProcessShutdownInProgress(void)
0x18003a98c  test    al, al
0x18003a98e  jnz     short loc_18003A9B7
0x18003a990  mov     rcx, [rbx+60h]; hdpa
0x18003a994  test    rcx, rcx
0x18003a997  jz      short loc_18003A9B7
0x18003a999  xor     r8d, r8d; pData
0x18003a99c  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UREGISTRY_WALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUREGISTRY_WALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003a9a3  call    DPA_DestroyCallback
0x18003a9a8  mov     [rbx+60h], rsi
0x18003a9ac  xor     ecx, ecx; hdpa
0x18003a9ae  call    DPA_Destroy
0x18003a9b3  mov     [rbx+60h], rsi
0x18003a9b7  cmp     [rbx+58h], rsi
0x18003a9bb  jz      short loc_18003A9ED
0x18003a9bd  call    ?IsProcessShutdownInProgress@@YA_NXZ; IsProcessShutdownInProgress(void)
0x18003a9c2  test    al, al
0x18003a9c4  jnz     short loc_18003A9ED
0x18003a9c6  mov     rcx, [rbx+58h]; hdpa
0x18003a9ca  test    rcx, rcx
0x18003a9cd  jz      short loc_18003A9ED
0x18003a9cf  xor     r8d, r8d; pData
0x18003a9d2  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UWALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUWALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003a9d9  call    DPA_DestroyCallback
0x18003a9de  mov     [rbx+58h], rsi
0x18003a9e2  xor     ecx, ecx; hdpa
0x18003a9e4  call    DPA_Destroy
0x18003a9e9  mov     [rbx+58h], rsi
0x18003a9ed  cmp     [rbx+50h], rsi
0x18003a9f1  jz      short loc_18003AA23
0x18003a9f3  call    ?IsProcessShutdownInProgress@@YA_NXZ; IsProcessShutdownInProgress(void)
0x18003a9f8  test    al, al
0x18003a9fa  jnz     short loc_18003AA23
0x18003a9fc  mov     rcx, [rbx+50h]; hdpa
0x18003aa00  test    rcx, rcx
0x18003aa03  jz      short loc_18003AA23
0x18003aa05  xor     r8d, r8d; pData
0x18003aa08  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@UWALLPAPER_PATH@CWallpaperCore@@VCTContainer_PolicyNewMem@@@@CAHPEAUWALLPAPER_PATH@CWallpaperCore@@PEAX@Z; pfnCB
0x18003aa0f  call    DPA_DestroyCallback
0x18003aa14  mov     [rbx+50h], rsi
0x18003aa18  xor     ecx, ecx; hdpa
0x18003aa1a  call    DPA_Destroy
0x18003aa1f  mov     [rbx+50h], rsi
0x18003aa23  mov     rbx, [rsp+38h+arg_0]
0x18003aa28  mov     rsi, [rsp+38h+arg_8]
0x18003aa2d  add     rsp, 30h
0x18003aa31  pop     rdi
0x18003aa32  retn
```
