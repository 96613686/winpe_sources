# EnsurePreviousWallpaper(ushort *,unsigned __int64,_tagWALLPAPEROPT *)

- ea: `0x180040c5c`
- end: `0x180040f08`
- name: `?EnsurePreviousWallpaper@@YAJPEAG_KPEAU_tagWALLPAPEROPT@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, struct _tagWALLPAPEROPT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800217fc`

## callees

- `0x18000ab10`
- `0x180014e40`
- `0x1800358c0`
- `0x180040c5c`
- `0x1800427dc`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180040d7d`
- `SHLWAPI!PathFindFileNameW` at `0x180040d7d`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180040e21`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180040e21`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180040d47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180040d47`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040d6b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040dac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040d6b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180040dac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040cbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040cbc`

## pseudocode

```c
__int64 __fastcall EnsurePreviousWallpaper(unsigned __int16 *a1, __int64 a2, struct _tagWALLPAPEROPT *a3)
{
  HRESULT v5; // r15d
  __int64 v6; // r14
  const WCHAR *FileNameW; // rax
  LPVOID v8; // rcx
  LPVOID v9; // rcx
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v12; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v14[264]; // [rsp+250h] [rbp+150h] BYREF

  v12 = 0;
  v5 = CoCreateInstance(&CLSID_ActiveDesktop, 0, 1u, &GUID_f490eb00_1240_11d1_9888_006097deacf9, &v12);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)v12 + 32LL))(
           v12,
           a1,
           260,
           0);
    if ( v5 < 0 || !*a1 )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids, a1);
    v6 = -1;
    if ( LoadStringW(g_hinst, 0x7E6u, Buffer, 260) && CompareStringOrdinal(Buffer, -1, a1, -1, 1) == 2 )
    {
LABEL_26:
      *a1 = 0;
      *((_DWORD *)a3 + 1) = 4;
      *(_DWORD *)a3 = 8;
    }
    else
    {
      FileNameW = PathFindFileNameW(a1);
      do
        ++v6;
      while ( FileNameW[v6] );
      if ( v6 == 14
        && CompareStringOrdinal(FileNameW, 9, L"Wallpaper", 9, 1) == 2
        && (int)HrRegGetPath(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"ConvertedWallpaper", v14, ppv) >= 0 )
      {
        StringCchCopyW(a1, 0x104u, v14);
      }
      v8 = v12;
      *(_DWORD *)a3 = 8;
      if ( (*(int (__fastcall **)(LPVOID, struct _tagWALLPAPEROPT *, _QWORD))(*(_QWORD *)v8 + 48LL))(v8, a3, 0) < 0 )
        *((_DWORD *)a3 + 1) = 4;
      if ( (unsigned int)SHExpandEnvironmentStringsW(a1, Buffer, 260) )
        v5 = StringCchCopyW(a1, 0x104u, Buffer);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids, a1);
      if ( v5 >= 0
        && *a1
        && (*(int (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)v12 + 40LL))(v12, a1, 0) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v12 + 24LL))(v12, 7);
      }
    }
    v9 = v12;
    v12 = 0;
    if ( v9 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180040c5c  mov     [rsp-8+arg_8], rbx
0x180040c61  mov     [rsp-8+arg_18], rdi
0x180040c66  push    rbp
0x180040c67  push    r12
0x180040c69  push    r13
0x180040c6b  push    r14
0x180040c6d  push    r15
0x180040c6f  lea     rbp, [rsp-370h]
0x180040c77  sub     rsp, 470h
0x180040c7e  mov     rax, cs:__security_cookie
0x180040c85  xor     rax, rsp
0x180040c88  mov     [rbp+390h+var_30], rax
0x180040c8f  xor     r12d, r12d
0x180040c92  lea     rax, [rsp+490h+var_460]
0x180040c97  mov     rdi, r8
0x180040c9a  mov     [rsp+490h+var_460], r12
0x180040c9f  mov     rbx, rcx
0x180040ca2  mov     qword ptr [rsp+490h+ppv], rax; ppv
0x180040ca7  lea     r9, _GUID_f490eb00_1240_11d1_9888_006097deacf9; riid
0x180040cae  xor     edx, edx; pUnkOuter
0x180040cb0  lea     r8d, [r12+1]; dwClsContext
0x180040cb5  lea     rcx, CLSID_ActiveDesktop; rclsid
0x180040cbc  call    cs:__imp_CoCreateInstance
0x180040cc2  mov     r15d, eax
0x180040cc5  test    eax, eax
0x180040cc7  js      loc_180040ED9
0x180040ccd  mov     rcx, [rsp+490h+var_460]
0x180040cd2  mov     r13d, 104h
0x180040cd8  xor     r9d, r9d
0x180040cdb  mov     r8d, r13d
0x180040cde  mov     rdx, rbx
0x180040ce1  mov     rax, [rcx]
0x180040ce4  mov     rax, [rax+20h]
0x180040ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ced  mov     r15d, eax
0x180040cf0  test    eax, eax
0x180040cf2  js      loc_180040EAD
0x180040cf8  cmp     [rbx], r12w
0x180040cfc  jz      loc_180040EAD
0x180040d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d09  lea     rax, WPP_GLOBAL_Control
0x180040d10  cmp     rcx, rax
0x180040d13  jz      short loc_180040D33
0x180040d15  test    byte ptr [rcx+1Ch], 8
0x180040d19  jz      short loc_180040D33
0x180040d1b  mov     rcx, [rcx+10h]
0x180040d1f  lea     edx, [r12+0Ah]
0x180040d24  mov     r9, rbx
0x180040d27  lea     r8, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids
0x180040d2e  call    WPP_SF_S
0x180040d33  mov     rcx, cs:g_hinst; hInstance
0x180040d3a  lea     r8, [rsp+490h+Buffer]; lpBuffer
0x180040d3f  mov     r9d, r13d; cchBufferMax
0x180040d42  mov     edx, 7E6h; uID
0x180040d47  call    cs:__imp_LoadStringW
0x180040d4d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180040d51  test    eax, eax
0x180040d53  jz      short loc_180040D7A
0x180040d55  mov     r9d, r14d; cchCount2
0x180040d58  mov     [rsp+490h+ppv], 1; bIgnoreCase
0x180040d60  mov     r8, rbx; lpString2
0x180040d63  lea     rcx, [rsp+490h+Buffer]; lpString1
0x180040d68  mov     edx, r14d; cchCount1
0x180040d6b  call    cs:__imp_CompareStringOrdinal
0x180040d71  cmp     eax, 2
0x180040d74  jz      loc_180040EAD
0x180040d7a  mov     rcx, rbx; pszPath
0x180040d7d  call    cs:__imp_PathFindFileNameW
0x180040d83  inc     r14
0x180040d86  cmp     [rax+r14*2], r12w
0x180040d8b  jnz     short loc_180040D83
0x180040d8d  cmp     r14, 0Eh
0x180040d91  jnz     short loc_180040DEE
0x180040d93  lea     edx, [r14-5]; cchCount1
0x180040d97  mov     [rsp+490h+ppv], 1; unsigned int
0x180040d9f  mov     r9d, edx; cchCount2
0x180040da2  lea     r8, aWallpaper; "Wallpaper"
0x180040da9  mov     rcx, rax; lpString1
0x180040dac  call    cs:__imp_CompareStringOrdinal
0x180040db2  cmp     eax, 2
0x180040db5  jnz     short loc_180040DEE
0x180040db7  lea     r9, [rbp+390h+var_240]; unsigned __int16 *
0x180040dbe  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180040dc5  lea     r8, aConvertedwallp; "ConvertedWallpaper"
0x180040dcc  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x180040dd3  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180040dd8  test    eax, eax
0x180040dda  js      short loc_180040DEE
0x180040ddc  lea     r8, [rbp+390h+var_240]; unsigned __int16 *
0x180040de3  mov     rdx, r13; unsigned __int64
0x180040de6  mov     rcx, rbx; unsigned __int16 *
0x180040de9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040dee  mov     rcx, [rsp+490h+var_460]
0x180040df3  xor     r8d, r8d
0x180040df6  mov     dword ptr [rdi], 8
0x180040dfc  mov     rdx, rdi
0x180040dff  mov     rax, [rcx]
0x180040e02  mov     rax, [rax+30h]
0x180040e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e0b  test    eax, eax
0x180040e0d  jns     short loc_180040E16
0x180040e0f  mov     dword ptr [rdi+4], 4
0x180040e16  mov     r8d, r13d
0x180040e19  lea     rdx, [rsp+490h+Buffer]
0x180040e1e  mov     rcx, rbx
0x180040e21  call    cs:__imp_SHExpandEnvironmentStringsW
0x180040e27  test    eax, eax
0x180040e29  jz      short loc_180040E3E
0x180040e2b  lea     r8, [rsp+490h+Buffer]; unsigned __int16 *
0x180040e30  mov     rdx, r13; unsigned __int64
0x180040e33  mov     rcx, rbx; unsigned __int16 *
0x180040e36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180040e3b  mov     r15d, eax
0x180040e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e45  lea     rax, WPP_GLOBAL_Control
0x180040e4c  cmp     rcx, rax
0x180040e4f  jz      short loc_180040E6F
0x180040e51  test    byte ptr [rcx+1Ch], 8
0x180040e55  jz      short loc_180040E6F
0x180040e57  mov     rcx, [rcx+10h]
0x180040e5b  lea     r8, WPP_db16c1876f9a307062c8a47e08f10cfd_Traceguids
0x180040e62  mov     edx, 0Bh
0x180040e67  mov     r9, rbx
0x180040e6a  call    WPP_SF_S
0x180040e6f  test    r15d, r15d
0x180040e72  js      short loc_180040EBE
0x180040e74  cmp     [rbx], r12w
0x180040e78  jz      short loc_180040EBE
0x180040e7a  mov     rcx, [rsp+490h+var_460]
0x180040e7f  xor     r8d, r8d
0x180040e82  mov     rdx, rbx
0x180040e85  mov     rax, [rcx]
0x180040e88  mov     rax, [rax+28h]
0x180040e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e91  test    eax, eax
0x180040e93  js      short loc_180040EBE
0x180040e95  mov     rcx, [rsp+490h+var_460]
0x180040e9a  mov     edx, 7
0x180040e9f  mov     rax, [rcx]
0x180040ea2  mov     rax, [rax+18h]
0x180040ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040eab  jmp     short loc_180040EBE
0x180040ead  mov     [rbx], r12w
0x180040eb1  mov     dword ptr [rdi+4], 4
0x180040eb8  mov     dword ptr [rdi], 8
0x180040ebe  mov     rcx, [rsp+490h+var_460]
0x180040ec3  mov     [rsp+490h+var_460], r12
0x180040ec8  test    rcx, rcx
0x180040ecb  jz      short loc_180040ED9
0x180040ecd  mov     rax, [rcx]
0x180040ed0  mov     rax, [rax+10h]
0x180040ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ed9  mov     eax, r15d
0x180040edc  mov     rcx, [rbp+390h+var_30]
0x180040ee3  xor     rcx, rsp; StackCookie
0x180040ee6  call    __security_check_cookie
0x180040eeb  lea     r11, [rsp+490h+var_20]
0x180040ef3  mov     rbx, [r11+38h]
0x180040ef7  mov     rdi, [r11+48h]
0x180040efb  mov     rsp, r11
0x180040efe  pop     r15
0x180040f00  pop     r14
0x180040f02  pop     r13
0x180040f04  pop     r12
0x180040f06  pop     rbp
0x180040f07  retn
```
