# CThemeManager2::CreateThemePack(HWND__ *,ushort const *,THEMEPACK_FLAGS)

- ea: `0x180053d50`
- end: `0x180053e8d`
- name: `?CreateThemePack@CThemeManager2@@UEAAJPEAUHWND__@@PEBGW4THEMEPACK_FLAGS@@@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800358c0`
- `0x180053d50`
- `0x1800628c4`
- `0x180062a50`
- `0x180062c40`
- `0x18006ad80`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180053d96`
- `SHLWAPI!PathFindExtensionW` at `0x180053d96`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180053db4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180053db4`
- `ntdll!WinSqmIncrementDWORD` at `0x180053dce`
- `ntdll!WinSqmIncrementDWORD` at `0x180053dce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThemeManager2::CreateThemePack(__int64 a1, __int64 a2, const WCHAR *a3, unsigned int a4)
{
  unsigned int v8; // edi
  const WCHAR *ExtensionW; // rax
  unsigned int v11; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v12; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v13[622]; // [rsp+40h] [rbp-C0h] BYREF

  v8 = -2147024809;
  ExtensionW = PathFindExtensionW(a3);
  if ( CompareStringOrdinal(ExtensionW, -1, L".deskthemepack", -1, 1) == 2 )
  {
    WinSqmIncrementDWORD(0, 3896, 1);
    CThemePackManager::CThemePackManager((CThemePackManager *)v13);
    v13[0] = a2;
    v13[1] = g_hinst;
    v8 = 0;
    if ( g_hinst )
    {
      v11 = 0;
      if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 88LL))(a1, &v11) >= 0 )
      {
        v12 = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD, OLECHAR **))(*(_QWORD *)a1 + 72LL))(a1, v11, &v12) >= 0 )
        {
          CThemePackManager::CreateThemePack((__int64)v13, v12, a3, a4);
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
    CThemePackManager::~CThemePackManager((CThemePackManager *)v13);
  }
  return v8;
}

```

## disassembly

```asm
0x180053d50  mov     [rsp-8+arg_8], rbx
0x180053d55  push    rbp
0x180053d56  push    rsi
0x180053d57  push    rdi
0x180053d58  push    r14
0x180053d5a  push    r15
0x180053d5c  lea     rbp, [rsp-12C0h]
0x180053d64  mov     eax, 13C0h
0x180053d69  call    _alloca_probe
0x180053d6e  sub     rsp, rax
0x180053d71  mov     rax, cs:__security_cookie
0x180053d78  xor     rax, rsp
0x180053d7b  mov     [rbp+12E0h+var_30], rax
0x180053d82  mov     r15d, r9d
0x180053d85  mov     r14, r8
0x180053d88  mov     rsi, rdx
0x180053d8b  mov     rbx, rcx
0x180053d8e  mov     edi, 80070057h
0x180053d93  mov     rcx, r8; pszPath
0x180053d96  call    cs:__imp_PathFindExtensionW
0x180053d9c  mov     [rsp+13E0h+bIgnoreCase], 1; bIgnoreCase
0x180053da4  or      edx, 0FFFFFFFFh; cchCount1
0x180053da7  mov     r9d, edx; cchCount2
0x180053daa  lea     r8, pszExt; ".deskthemepack"
0x180053db1  mov     rcx, rax; lpString1
0x180053db4  call    cs:__imp_CompareStringOrdinal
0x180053dba  cmp     eax, 2
0x180053dbd  jnz     loc_180053E65
0x180053dc3  mov     edx, 0F38h
0x180053dc8  xor     ecx, ecx
0x180053dca  lea     r8d, [rax-1]
0x180053dce  call    cs:__imp_WinSqmIncrementDWORD
0x180053dd4  lea     rcx, [rsp+13E0h+var_13A0]; this
0x180053dd9  call    ??0CThemePackManager@@QEAA@XZ; CThemePackManager::CThemePackManager(void)
0x180053dde  nop
0x180053ddf  mov     [rsp+13E0h+var_13A0], rsi
0x180053de4  mov     rax, cs:g_hinst
0x180053deb  mov     [rsp+13E0h+var_1398], rax
0x180053df0  xor     edi, edi
0x180053df2  test    rax, rax
0x180053df5  jz      short loc_180053E5B
0x180053df7  mov     [rsp+13E0h+var_13B0], edi
0x180053dfb  mov     rax, [rbx]
0x180053dfe  lea     rdx, [rsp+13E0h+var_13B0]
0x180053e03  mov     rcx, rbx
0x180053e06  mov     rax, [rax+58h]
0x180053e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e0f  test    eax, eax
0x180053e11  js      short loc_180053E5B
0x180053e13  mov     [rsp+13E0h+var_13A8], rdi
0x180053e18  mov     rax, [rbx]
0x180053e1b  lea     r8, [rsp+13E0h+var_13A8]
0x180053e20  mov     edx, [rsp+13E0h+var_13B0]
0x180053e24  mov     rcx, rbx
0x180053e27  mov     rax, [rax+48h]
0x180053e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e30  test    eax, eax
0x180053e32  js      short loc_180053E5B
0x180053e34  mov     r9d, r15d
0x180053e37  mov     r8, r14
0x180053e3a  mov     rdx, [rsp+13E0h+var_13A8]
0x180053e3f  lea     rcx, [rsp+13E0h+var_13A0]
0x180053e44  call    ?CreateThemePack@CThemePackManager@@QEAAJPEAUITheme@@PEBGW4THEMEPACK_FLAGS@@@Z; CThemePackManager::CreateThemePack(ITheme *,ushort const *,THEMEPACK_FLAGS)
0x180053e49  mov     rcx, [rsp+13E0h+var_13A8]
0x180053e4e  mov     rax, [rcx]
0x180053e51  mov     rax, [rax+10h]
0x180053e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e5a  nop
0x180053e5b  lea     rcx, [rsp+13E0h+var_13A0]; this
0x180053e60  call    ??1CThemePackManager@@QEAA@XZ; CThemePackManager::~CThemePackManager(void)
0x180053e65  mov     eax, edi
0x180053e67  mov     rcx, [rbp+12E0h+var_30]
0x180053e6e  xor     rcx, rsp; StackCookie
0x180053e71  call    __security_check_cookie
0x180053e76  mov     rbx, [rsp+13E0h+arg_8]
0x180053e7e  add     rsp, 13C0h
0x180053e85  pop     r15
0x180053e87  pop     r14
0x180053e89  pop     rdi
0x180053e8a  pop     rsi
0x180053e8b  pop     rbp
0x180053e8c  retn
```
