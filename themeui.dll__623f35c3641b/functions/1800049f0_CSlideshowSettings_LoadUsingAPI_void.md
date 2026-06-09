# CSlideshowSettings::LoadUsingAPI(void)

- ea: `0x1800049f0`
- end: `0x180004c6f`
- name: `?LoadUsingAPI@CSlideshowSettings@@QEAAJXZ`
- size: `639`
- prototype: `__int64 __fastcall(CSlideshowSettings *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010b20`

## callees

- `0x180004768`
- `0x1800047ac`
- `0x18000491c`
- `0x1800049f0`
- `0x180004d70`
- `0x180004da0`
- `0x180005410`
- `0x1800054f8`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a64`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004a64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004b74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004a2b`

## pseudocode

```c
__int64 __fastcall CSlideshowSettings::LoadUsingAPI(CSlideshowSettings *this)
{
  int v2; // esi
  CFileSource *v3; // rdi
  int v4; // eax
  CFileSource *v5; // rcx
  unsigned int v6; // ecx
  CFileSource *v7; // rcx
  unsigned int v8; // edx
  __int64 v9; // rcx
  __int64 result; // rax
  int v11; // r9d
  LPVOID v12; // rcx
  unsigned int USDWORDW; // eax
  __int64 v14; // rcx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  struct CFileSource *v16; // [rsp+70h] [rbp+8h] BYREF
  int v17; // [rsp+78h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+18h] BYREF
  struct IShellItemArray *v19; // [rsp+88h] [rbp+20h] BYREF

  *((_DWORD *)this + 6) = 0;
  hKey = 0;
  v2 = -2147467259;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Personalization\\Desktop Slideshow", 0, 1u, &hKey) )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b, &ppv) < 0 )
      goto LABEL_26;
    v19 = 0;
    v3 = 0;
    v16 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray **))(*(_QWORD *)ppv + 104LL))(ppv, &v19);
    if ( v4 >= 0 )
    {
      if ( !v4 )
      {
        CFileSource::s_CreateFromShellItemArray(v19, &v16);
        v3 = v16;
        v2 = 0;
      }
      ((void (__fastcall *)(struct IShellItemArray *))v19->lpVtbl->Release)(v19);
    }
    v5 = (CFileSource *)*((_QWORD *)this + 2);
    if ( (v5 != 0) == (v3 != 0) )
    {
      if ( !v5 || !v3 )
        goto LABEL_19;
      if ( CFileSource::IsEqual(v5, v3) )
      {
        v6 = *((_DWORD *)this + 6) | 4;
        if ( !*((_QWORD *)this + 2) )
          v6 = *((_DWORD *)this + 6) & 0xFFFFFFFB;
        *((_DWORD *)this + 6) = v6;
LABEL_22:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
        {
          CFileSource::~CFileSource(v3);
          operator delete(v3);
        }
LABEL_24:
        if ( v2 >= 0 )
        {
          v17 = 0;
          LODWORD(v16) = 0;
          if ( (*(int (__fastcall **)(LPVOID, int *, struct CFileSource **))(*(_QWORD *)ppv + 120LL))(ppv, &v17, &v16) >= 0 )
          {
            CSlideshowSettings::SetInterval(this, (unsigned int)v16);
            v11 = v17 & 1;
            if ( v11 != *((_DWORD *)this + 1) || (*((_BYTE *)this + 24) & 2) == 0 )
            {
              *((_DWORD *)this + 7) |= 2u;
              *((_DWORD *)this + 1) = v11;
            }
            v12 = ppv;
            *((_DWORD *)this + 6) |= 2u;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
            goto LABEL_33;
          }
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v2 >= 0 )
        {
LABEL_33:
          USDWORDW = SHRegGetUSDWORDW(v9, L"AnimationDuration", 1000);
          *((_DWORD *)this + 2) = USDWORDW;
          if ( USDWORDW )
          {
            v14 = 250;
            if ( USDWORDW < 0xFA )
              USDWORDW = 250;
            *((_DWORD *)this + 2) = USDWORDW;
          }
          *((_DWORD *)this + 8) = SHRegGetUSDWORDW(v14, L"Flags", 0);
        }
LABEL_26:
        RegCloseKey(hKey);
        goto LABEL_27;
      }
    }
    v7 = (CFileSource *)*((_QWORD *)this + 2);
    if ( v7 )
      CFileSource::Release(v7);
    if ( v3 )
      _InterlockedIncrement((volatile signed __int32 *)v3);
    *((_DWORD *)this + 7) |= 4u;
    *((_QWORD *)this + 2) = v3;
LABEL_19:
    v8 = *((_DWORD *)this + 6) | 4;
    if ( !*((_QWORD *)this + 2) )
      v8 = *((_DWORD *)this + 6) & 0xFFFFFFFB;
    *((_DWORD *)this + 6) = v8;
    if ( !v3 )
      goto LABEL_24;
    goto LABEL_22;
  }
LABEL_27:
  result = (unsigned int)v2;
  *((_DWORD *)this + 7) = 0;
  return result;
}

```

## disassembly

```asm
0x1800049f0  push    rbx
0x1800049f2  push    rbp
0x1800049f3  push    rsi
0x1800049f4  sub     rsp, 50h
0x1800049f8  xor     ebp, ebp
0x1800049fa  lea     rax, [rsp+68h+hKey]
0x1800049ff  mov     [rcx+18h], ebp
0x180004a02  lea     rdx, SubKey; "Control Panel\\Personalization\\Desktop"...
0x180004a09  mov     rbx, rcx
0x180004a0c  mov     [rsp+68h+hKey], rbp
0x180004a11  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004a18  mov     [rsp+68h+phkResult], rax; phkResult
0x180004a1d  mov     r9d, 1; samDesired
0x180004a23  xor     r8d, r8d; ulOptions
0x180004a26  mov     esi, 80004005h
0x180004a2b  call    cs:__imp_RegOpenKeyExW
0x180004a31  test    eax, eax
0x180004a33  jnz     loc_180004B7A
0x180004a39  lea     rax, [rsp+68h+ppv]
0x180004a41  mov     [rsp+68h+ppv], rbp
0x180004a49  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x180004a50  mov     [rsp+68h+phkResult], rax; ppv
0x180004a55  xor     edx, edx; pUnkOuter
0x180004a57  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x180004a5e  mov     r8d, 4; dwClsContext
0x180004a64  call    cs:__imp_CoCreateInstance
0x180004a6a  test    eax, eax
0x180004a6c  js      loc_180004B6F
0x180004a72  mov     rcx, [rsp+68h+ppv]
0x180004a7a  lea     rdx, [rsp+68h+arg_18]
0x180004a82  mov     [rsp+68h+arg_18], rbp
0x180004a8a  mov     [rsp+68h+var_20], rdi
0x180004a8f  mov     edi, ebp
0x180004a91  mov     [rsp+68h+arg_0], rbp
0x180004a96  mov     rax, [rcx]
0x180004a99  mov     rax, [rax+68h]
0x180004a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa2  test    eax, eax
0x180004aa4  js      short loc_180004AC0
0x180004aa6  jz      loc_180004B99
0x180004aac  mov     rcx, [rsp+68h+arg_18]
0x180004ab4  mov     rax, [rcx]
0x180004ab7  mov     rax, [rax+10h]
0x180004abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac0  mov     rcx, [rbx+10h]; this
0x180004ac4  mov     edx, ebp
0x180004ac6  test    rcx, rcx
0x180004ac9  mov     eax, ebp
0x180004acb  setnz   dl
0x180004ace  test    rdi, rdi
0x180004ad1  setnz   al
0x180004ad4  cmp     edx, eax
0x180004ad6  jnz     short loc_180004B05
0x180004ad8  test    rcx, rcx
0x180004adb  jz      short loc_180004B22
0x180004add  test    rdi, rdi
0x180004ae0  jz      short loc_180004B22
0x180004ae2  mov     rdx, rdi; struct CFileSource *
0x180004ae5  call    ?IsEqual@CFileSource@@QEAA_NPEAV1@@Z; CFileSource::IsEqual(CFileSource *)
0x180004aea  test    al, al
0x180004aec  jz      short loc_180004B05
0x180004aee  mov     ecx, [rbx+18h]
0x180004af1  mov     eax, ecx
0x180004af3  and     eax, 0FFFFFFFBh
0x180004af6  or      ecx, 4
0x180004af9  cmp     [rbx+10h], rbp
0x180004afd  cmovz   ecx, eax
0x180004b00  mov     [rbx+18h], ecx
0x180004b03  jmp     short loc_180004B3C
0x180004b05  mov     rcx, [rbx+10h]; this
0x180004b09  test    rcx, rcx
0x180004b0c  jnz     loc_180004C56
0x180004b12  test    rdi, rdi
0x180004b15  jz      short loc_180004B1A
0x180004b17  lock inc dword ptr [rdi]
0x180004b1a  or      dword ptr [rbx+1Ch], 4
0x180004b1e  mov     [rbx+10h], rdi
0x180004b22  mov     edx, [rbx+18h]
0x180004b25  mov     eax, edx
0x180004b27  and     eax, 0FFFFFFFBh
0x180004b2a  or      edx, 4
0x180004b2d  cmp     [rbx+10h], rbp
0x180004b31  cmovz   edx, eax
0x180004b34  mov     [rbx+18h], edx
0x180004b37  test    rdi, rdi
0x180004b3a  jz      short loc_180004B4A
0x180004b3c  mov     eax, 0FFFFFFFFh
0x180004b41  lock xadd [rdi], eax
0x180004b45  cmp     eax, 1
0x180004b48  jz      short loc_180004B87
0x180004b4a  mov     rdi, [rsp+68h+var_20]
0x180004b4f  test    esi, esi
0x180004b51  jns     short loc_180004BB7
0x180004b53  mov     rcx, [rsp+68h+ppv]
0x180004b5b  mov     rax, [rcx]
0x180004b5e  mov     rax, [rax+10h]
0x180004b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b67  test    esi, esi
0x180004b69  jns     loc_180004C26
0x180004b6f  mov     rcx, [rsp+68h+hKey]; hKey
0x180004b74  call    cs:__imp_RegCloseKey
0x180004b7a  mov     eax, esi
0x180004b7c  mov     [rbx+1Ch], ebp
0x180004b7f  add     rsp, 50h
0x180004b83  pop     rsi
0x180004b84  pop     rbp
0x180004b85  pop     rbx
0x180004b86  retn
0x180004b87  mov     rcx, rdi; this
0x180004b8a  call    ??1CFileSource@@AEAA@XZ; CFileSource::~CFileSource(void)
0x180004b8f  mov     rcx, rdi; lpMem
0x180004b92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004b97  jmp     short loc_180004B4A
0x180004b99  mov     rcx, [rsp+68h+arg_18]; struct IShellItemArray *
0x180004ba1  lea     rdx, [rsp+68h+arg_0]; struct CFileSource **
0x180004ba6  call    ?s_CreateFromShellItemArray@CFileSource@@SAJPEAUIShellItemArray@@PEAPEAV1@@Z; CFileSource::s_CreateFromShellItemArray(IShellItemArray *,CFileSource * *)
0x180004bab  mov     rdi, [rsp+68h+arg_0]
0x180004bb0  mov     esi, ebp
0x180004bb2  jmp     loc_180004AAC
0x180004bb7  mov     rcx, [rsp+68h+ppv]
0x180004bbf  lea     r8, [rsp+68h+arg_0]
0x180004bc4  mov     [rsp+68h+arg_8], ebp
0x180004bc8  lea     rdx, [rsp+68h+arg_8]
0x180004bcd  mov     dword ptr [rsp+68h+arg_0], ebp
0x180004bd1  mov     rax, [rcx]
0x180004bd4  mov     rax, [rax+78h]
0x180004bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bdd  test    eax, eax
0x180004bdf  js      loc_180004B53
0x180004be5  mov     edx, dword ptr [rsp+68h+arg_0]; unsigned int
0x180004be9  mov     rcx, rbx; this
0x180004bec  call    ?SetInterval@CSlideshowSettings@@QEAAJK@Z; CSlideshowSettings::SetInterval(ulong)
0x180004bf1  mov     r9d, [rsp+68h+arg_8]
0x180004bf6  and     r9d, 1
0x180004bfa  cmp     r9d, [rbx+4]
0x180004bfe  jnz     short loc_180004C06
0x180004c00  test    byte ptr [rbx+18h], 2
0x180004c04  jnz     short loc_180004C0E
0x180004c06  or      dword ptr [rbx+1Ch], 2
0x180004c0a  mov     [rbx+4], r9d
0x180004c0e  mov     rcx, [rsp+68h+ppv]
0x180004c16  or      dword ptr [rbx+18h], 2
0x180004c1a  mov     rax, [rcx]
0x180004c1d  mov     rax, [rax+10h]
0x180004c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c26  mov     r8d, 3E8h
0x180004c2c  lea     rdx, aAnimationdurat; "AnimationDuration"
0x180004c33  call    SHRegGetUSDWORDW
0x180004c38  mov     [rbx+8], eax
0x180004c3b  test    eax, eax
0x180004c3d  jnz     short loc_180004C60
0x180004c3f  xor     r8d, r8d
0x180004c42  lea     rdx, aFlags; "Flags"
0x180004c49  call    SHRegGetUSDWORDW
0x180004c4e  mov     [rbx+20h], eax
0x180004c51  jmp     loc_180004B6F
0x180004c56  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x180004c5b  jmp     loc_180004B12
0x180004c60  mov     ecx, 0FAh
0x180004c65  cmp     eax, ecx
0x180004c67  cmovb   eax, ecx
0x180004c6a  mov     [rbx+8], eax
0x180004c6d  jmp     short loc_180004C3F
```
