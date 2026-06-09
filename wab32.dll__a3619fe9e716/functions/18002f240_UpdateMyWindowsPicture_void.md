# UpdateMyWindowsPicture(void)

- ea: `0x18002f240`
- end: `0x18002f3e8`
- name: `?UpdateMyWindowsPicture@@YAJXZ`
- size: `424`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000eef0`
- `0x18002f0d8`
- `0x18003d2e8`

## callees

- `0x180002818`
- `0x18002eb4c`
- `0x18002f240`
- `0x18006b400`
- `0x18006b620`
- `0x18006bcac`
- `0x18006c19c`
- `0x18006c504`
- `0x180074bf4`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18002f32a`
- `SHLWAPI!PathAppendW` at `0x18002f32a`
- `SHLWAPI!SHRegSetUSValueW` at `0x18002f37f`
- `SHLWAPI!SHRegSetUSValueW` at `0x18002f37f`
- `SHELL32!SHGetFolderPathW` at `0x18002f30c`
- `SHELL32!SHGetFolderPathW` at `0x18002f30c`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x18002f394`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x18002f394`

## pseudocode

```c
__int64 UpdateMyWindowsPicture(void)
{
  HRESULT v0; // ebx
  int pvData; // [rsp+30h] [rbp-D0h] BYREF
  struct IContact *v3; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v5; // [rsp+50h] [rbp-B0h]
  __int64 v6; // [rsp+60h] [rbp-A0h]
  __int128 v7; // [rsp+68h] [rbp-98h]
  _BYTE v8[272]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPath[264]; // [rsp+190h] [rbp+90h] BYREF

  v3 = 0;
  memset_0(pszPath, 0, 0x208u);
  v4[1] = 0;
  v4[0] = &CUserTile::`vftable';
  v6 = 0;
  v5 = 0;
  v7 = 0;
  CComProtector::CComProtector((CComProtector *)v8);
  EnsureResourcesAreLoaded();
  if ( (int)GetMyContact(0, &v3) >= 0 )
  {
    v0 = CUserTile::InitFromContact((CUserTile *)v4, v3);
    if ( v0 >= 0 )
    {
      v0 = SHGetFolderPathW(0, 26, 0, 0, pszPath);
      if ( v0 >= 0 )
      {
        if ( PathAppendW(pszPath, L"UserTile.png") )
        {
          v0 = CUserTile::SaveImage((CUserTile *)v4, pszPath);
          if ( v0 >= 0 )
          {
            pvData = 1;
            if ( SHRegSetUSValueW(L"Software\\Microsoft\\WAB\\Me", L"Delay Picture Sync", 4u, &pvData, 4u, 2u) )
            {
              v0 = -2147467259;
            }
            else
            {
              v0 = SHSetUserPicturePath(0, 0, pszPath);
              if ( v0 >= 0 )
                v0 = 0;
            }
          }
        }
        else
        {
          v0 = -2147418113;
        }
      }
    }
  }
  else
  {
    v0 = 1;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v3);
  CComProtector::~CComProtector((CComProtector *)v8);
  CUserTile::~CUserTile((CUserTile *)v4);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002f240  mov     [rsp-8+arg_0], rbx
0x18002f245  push    rbp
0x18002f246  lea     rbp, [rsp-2B0h]
0x18002f24e  sub     rsp, 3B0h
0x18002f255  mov     rax, cs:__security_cookie
0x18002f25c  xor     rax, rsp
0x18002f25f  mov     [rbp+2B0h+var_10], rax
0x18002f266  xor     edx, edx; Val
0x18002f268  mov     [rsp+3B0h+var_378], 0
0x18002f271  mov     r8d, 208h; Size
0x18002f277  lea     rcx, [rbp+2B0h+var_220]; void *
0x18002f27e  call    memset_0
0x18002f283  lea     rax, ??_7CUserTile@@6B@; const CUserTile::`vftable'
0x18002f28a  mov     [rsp+3B0h+var_368], 0
0x18002f293  xorps   xmm0, xmm0
0x18002f296  mov     [rsp+3B0h+var_370], rax
0x18002f29b  xorps   xmm1, xmm1
0x18002f29e  mov     [rsp+3B0h+var_350], 0
0x18002f2a7  lea     rcx, [rbp+2B0h+var_330]; this
0x18002f2ab  movdqu  [rsp+3B0h+var_360], xmm0
0x18002f2b1  movdqu  [rsp+3B0h+var_348], xmm1
0x18002f2b7  call    ??0CComProtector@@QEAA@XZ; CComProtector::CComProtector(void)
0x18002f2bc  call    ?EnsureResourcesAreLoaded@@YAJXZ; EnsureResourcesAreLoaded(void)
0x18002f2c1  lea     rdx, [rsp+3B0h+var_378]; struct IContact **
0x18002f2c6  xor     ecx, ecx; struct IContactManager *
0x18002f2c8  call    ?GetMyContact@@YAJPEAUIContactManager@@PEAPEAUIContact@@@Z; GetMyContact(IContactManager *,IContact * *)
0x18002f2cd  test    eax, eax
0x18002f2cf  jns     short loc_18002F2DB
0x18002f2d1  mov     ebx, 1
0x18002f2d6  jmp     loc_18002F3A9
0x18002f2db  mov     rdx, [rsp+3B0h+var_378]; struct IContact *
0x18002f2e0  lea     rcx, [rsp+3B0h+var_370]; this
0x18002f2e5  call    ?InitFromContact@CUserTile@@QEAAJPEAUIContact@@@Z; CUserTile::InitFromContact(IContact *)
0x18002f2ea  mov     ebx, eax
0x18002f2ec  test    eax, eax
0x18002f2ee  js      loc_18002F3A9
0x18002f2f4  xor     r9d, r9d; dwFlags
0x18002f2f7  lea     rax, [rbp+2B0h+var_220]
0x18002f2fe  xor     r8d, r8d; hToken
0x18002f301  mov     [rsp+3B0h+pszPath], rax; pszPath
0x18002f306  xor     ecx, ecx; hwnd
0x18002f308  lea     edx, [r9+1Ah]; csidl
0x18002f30c  call    cs:__imp_SHGetFolderPathW
0x18002f312  mov     ebx, eax
0x18002f314  test    eax, eax
0x18002f316  js      loc_18002F3A9
0x18002f31c  lea     rdx, pszMore; "UserTile.png"
0x18002f323  lea     rcx, [rbp+2B0h+var_220]; pszPath
0x18002f32a  call    cs:__imp_PathAppendW
0x18002f330  test    eax, eax
0x18002f332  jnz     short loc_18002F33B
0x18002f334  mov     ebx, 8000FFFFh
0x18002f339  jmp     short loc_18002F3A9
0x18002f33b  lea     rdx, [rbp+2B0h+var_220]; unsigned __int16 *
0x18002f342  lea     rcx, [rsp+3B0h+var_370]; this
0x18002f347  call    ?SaveImage@CUserTile@@QEAAJPEBG@Z; CUserTile::SaveImage(ushort const *)
0x18002f34c  mov     ebx, eax
0x18002f34e  test    eax, eax
0x18002f350  js      short loc_18002F3A9
0x18002f352  mov     ebx, 1
0x18002f357  mov     [rsp+3B0h+dwFlags], 2; dwFlags
0x18002f35f  lea     r9, [rsp+3B0h+pvData]; pvData
0x18002f364  mov     [rsp+3B0h+pvData], ebx
0x18002f368  lea     rdx, pszValue; "Delay Picture Sync"
0x18002f36f  lea     rcx, pszSubKey; "Software\\Microsoft\\WAB\\Me"
0x18002f376  lea     r8d, [rbx+3]; dwType
0x18002f37a  mov     dword ptr [rsp+3B0h+pszPath], r8d; cbData
0x18002f37f  call    cs:__imp_SHRegSetUSValueW
0x18002f385  test    eax, eax
0x18002f387  jnz     short loc_18002F3A4
0x18002f389  lea     r8, [rbp+2B0h+var_220]
0x18002f390  xor     edx, edx
0x18002f392  xor     ecx, ecx
0x18002f394  call    cs:__imp_SHSetUserPicturePath
0x18002f39a  mov     ebx, eax
0x18002f39c  test    eax, eax
0x18002f39e  js      short loc_18002F3A9
0x18002f3a0  xor     ebx, ebx
0x18002f3a2  jmp     short loc_18002F3A9
0x18002f3a4  mov     ebx, 80004005h
0x18002f3a9  lea     rcx, [rsp+3B0h+var_378]
0x18002f3ae  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18002f3b3  lea     rcx, [rbp+2B0h+var_330]; this
0x18002f3b7  call    ??1CComProtector@@QEAA@XZ; CComProtector::~CComProtector(void)
0x18002f3bc  lea     rcx, [rsp+3B0h+var_370]; this
0x18002f3c1  call    ??1CUserTile@@UEAA@XZ; CUserTile::~CUserTile(void)
0x18002f3c6  mov     eax, ebx
0x18002f3c8  mov     rcx, [rbp+2B0h+var_10]
0x18002f3cf  xor     rcx, rsp; StackCookie
0x18002f3d2  call    __security_check_cookie
0x18002f3d7  mov     rbx, [rsp+3B0h+arg_0]
0x18002f3df  add     rsp, 3B0h
0x18002f3e6  pop     rbp
0x18002f3e7  retn
```
