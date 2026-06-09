# CExtensionContextMenus::_LoadExtensionMenus(_DPA *,uint)

- ea: `0x180019280`
- end: `0x18001956d`
- name: `?_LoadExtensionMenus@CExtensionContextMenus@@AEAAJPEAU_DPA@@I@Z`
- size: `749`
- prototype: `__int64 __fastcall(CExtensionContextMenus *__hidden this, struct _DPA *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c2e0`

## callees

- `0x18000161c`
- `0x180002818`
- `0x180018f30`
- `0x180018fbc`
- `0x180019044`
- `0x180019280`
- `0x180091e86`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180019333`
- `ADVAPI32!RegOpenKeyExW` at `0x180019333`
- `ADVAPI32!RegEnumValueW` at `0x18001938f`
- `ADVAPI32!RegEnumValueW` at `0x18001938f`
- `ADVAPI32!RegCloseKey` at `0x180019510`
- `ADVAPI32!RegCloseKey` at `0x180019510`
- `ole32!CoCreateInstance` at `0x180019407`
- `ole32!CoCreateInstance` at `0x180019407`
- `ole32!CLSIDFromString` at `0x1800193be`
- `ole32!CLSIDFromString` at `0x1800193be`
- `iertutil!__imp_DPA_Create` at `0x1800192f5`
- `iertutil!__imp_DPA_Create` at `0x1800192f5`
- `iertutil!__imp_DPA_InsertPtr` at `0x1800194ca`
- `iertutil!__imp_DPA_InsertPtr` at `0x1800194ca`

## pseudocode

```c
__int64 __fastcall CExtensionContextMenus::_LoadExtensionMenus(struct _DPA **this, struct _DPA *a2, unsigned int a3)
{
  struct _DPA *v3; // rbx
  void (__fastcall ***v5)(_QWORD, __int64); // rdi
  _QWORD *v6; // r14
  CExtensionContextMenus *v7; // rcx
  struct _DPA *v8; // rsi
  int v9; // ebx
  DWORD v10; // r15d
  void (__fastcall ***v11)(_QWORD, __int64); // rax
  CExtensionContextMenus *v12; // rcx
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19; // [rsp+64h] [rbp-9Ch]
  struct _DPA *v20; // [rsp+68h] [rbp-98h] BYREF
  struct _DPA *v21; // [rsp+70h] [rbp-90h]
  GUID pclsid; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = a2;
  v21 = a2;
  v19 = a3;
  hKey = 0;
  ppv = 0;
  v5 = 0;
  v16 = 0;
  CExtensionContextMenus::_FreeExtensionMenus((CExtensionContextMenus *)this, this + 1);
  v6 = this + 2;
  CExtensionContextMenus::_DeInitializeContextDataStruct(v7, (struct _WABEXTDISPLAY **)this + 2);
  v20 = DPA_Create(5);
  v8 = v20;
  if ( v20 )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WAB\\WAB4\\ExtContext", 0, 0x20019u, &hKey) )
    {
      memset_0(ValueName, 0, 0x208u);
      v10 = 0;
      cchValueName = 260;
      Type = 0;
      while ( 1 )
      {
        v5 = 0;
        if ( RegEnumValueW(hKey, v10, ValueName, &cchValueName, 0, &Type, 0, 0) )
          break;
        cchValueName = 260;
        ++v10;
        pclsid = GUID_NULL;
        if ( CLSIDFromString(ValueName, &pclsid) >= 0 )
        {
          if ( memcmp_0(&pclsid, qword_1800AB318, 0x10u) )
          {
            OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
            if ( CoCreateInstance(&pclsid, 0, 1u, &IID_IContextMenu, &ppv) >= 0 )
            {
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
              if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IWABExtInit, &v16) >= 0 )
              {
                if ( !*v6 )
                {
                  v9 = CExtensionContextMenus::_InitializeContextDataStruct(
                         (CExtensionContextMenus *)this,
                         v3,
                         v19,
                         (struct _WABEXTDISPLAY **)this + 2);
                  if ( v9 < 0 )
                    goto LABEL_19;
                  v3 = v21;
                }
                if ( (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, *v6) >= 0 )
                {
                  v11 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x18u);
                  v5 = v11;
                  if ( !v11 )
                  {
                    v9 = -2147024882;
                    v5 = 0;
                    goto LABEL_19;
                  }
                  v11[1] = (void (__fastcall **)(_QWORD, __int64))ppv;
                  *v11 = (void (__fastcall **)(_QWORD, __int64))&ContextMenuExtData::`vftable';
                  *((_DWORD *)v11 + 4) = 0xFFFF;
                  *((_DWORD *)v11 + 5) = 0xFFFF;
                  ppv = 0;
                  if ( DPA_InsertPtr(v8, 0x7FFFFFFF, v11) == -1 )
                    goto LABEL_2;
                }
              }
            }
          }
        }
      }
    }
    v9 = 0;
    this[1] = v8;
    v20 = 0;
  }
  else
  {
LABEL_2:
    v9 = -2147024882;
  }
LABEL_19:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
  v12 = (CExtensionContextMenus *)hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CExtensionContextMenus::_FreeExtensionMenus(v12, &v20);
  if ( v5 )
    (**v5)(v5, 1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019280  mov     [rsp-8+arg_18], rbx
0x180019285  push    rbp
0x180019286  push    rsi
0x180019287  push    rdi
0x180019288  push    r12
0x18001928a  push    r13
0x18001928c  push    r14
0x18001928e  push    r15
0x180019290  lea     rbp, [rsp-1B0h]
0x180019298  sub     rsp, 2B0h
0x18001929f  mov     rax, cs:__security_cookie
0x1800192a6  xor     rax, rsp
0x1800192a9  mov     [rbp+1E0h+var_40], rax
0x1800192b0  mov     rbx, rdx
0x1800192b3  mov     [rsp+2E0h+var_270], rdx
0x1800192b8  lea     rdx, [rcx+8]; struct _DPA **
0x1800192bc  mov     [rsp+2E0h+var_27C], r8d
0x1800192c1  mov     r13, rcx
0x1800192c4  mov     [rsp+2E0h+hKey], 0
0x1800192cd  mov     [rsp+2E0h+ppv], 0
0x1800192d6  xor     edi, edi
0x1800192d8  mov     [rsp+2E0h+var_290], 0
0x1800192e1  call    ?_FreeExtensionMenus@CExtensionContextMenus@@AEAAXPEAPEAU_DPA@@@Z; CExtensionContextMenus::_FreeExtensionMenus(_DPA * *)
0x1800192e6  lea     r14, [r13+10h]
0x1800192ea  mov     rdx, r14; struct _WABEXTDISPLAY **
0x1800192ed  call    ?_DeInitializeContextDataStruct@CExtensionContextMenus@@AEAAXPEAPEAU_WABEXTDISPLAY@@@Z; CExtensionContextMenus::_DeInitializeContextDataStruct(_WABEXTDISPLAY * *)
0x1800192f2  lea     ecx, [rdi+5]; cItemGrow
0x1800192f5  call    cs:__imp_DPA_Create
0x1800192fb  mov     [rsp+2E0h+var_278], rax
0x180019300  mov     rsi, rax
0x180019303  test    rax, rax
0x180019306  jnz     short loc_180019312
0x180019308  mov     ebx, 8007000Eh
0x18001930d  jmp     loc_1800194F2
0x180019312  lea     rax, [rsp+2E0h+hKey]
0x180019317  mov     r9d, 20019h; samDesired
0x18001931d  xor     r8d, r8d; ulOptions
0x180019320  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180019325  lea     rdx, SubKey; "Software\\Microsoft\\WAB\\WAB4\\ExtCont"...
0x18001932c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019333  call    cs:__imp_RegOpenKeyExW
0x180019339  test    eax, eax
0x18001933b  jnz     loc_1800194E7
0x180019341  xor     edx, edx; Val
0x180019343  lea     rcx, [rbp+1E0h+ValueName]; void *
0x180019347  mov     r8d, 208h; Size
0x18001934d  call    memset_0
0x180019352  xor     r15d, r15d
0x180019355  mov     [rsp+2E0h+cchValueName], 104h
0x18001935d  mov     [rsp+2E0h+Type], edi
0x180019361  xor     ecx, ecx
0x180019363  lea     rax, [rsp+2E0h+Type]
0x180019368  mov     [rsp+2E0h+lpcbData], rcx; lpcbData
0x18001936d  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180019372  mov     [rsp+2E0h+lpData], rcx; lpData
0x180019377  lea     r8, [rbp+1E0h+ValueName]; lpValueName
0x18001937b  mov     [rsp+2E0h+lpType], rax; lpType
0x180019380  mov     edx, r15d; dwIndex
0x180019383  mov     [rsp+2E0h+phkResult], rcx; lpReserved
0x180019388  xor     edi, edi
0x18001938a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001938f  call    cs:__imp_RegEnumValueW
0x180019395  test    eax, eax
0x180019397  jnz     loc_1800194E7
0x18001939d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800193a4  lea     rdx, [rsp+2E0h+pclsid]; pclsid
0x1800193a9  mov     [rsp+2E0h+cchValueName], 104h
0x1800193b1  lea     rcx, [rbp+1E0h+ValueName]; lpsz
0x1800193b5  inc     r15d
0x1800193b8  movdqu  xmmword ptr [rsp+2E0h+pclsid.Data1], xmm0
0x1800193be  call    cs:__imp_CLSIDFromString
0x1800193c4  test    eax, eax
0x1800193c6  js      short loc_180019361
0x1800193c8  lea     r8d, [rdi+10h]; Size
0x1800193cc  lea     rdx, qword_1800AB318; Buf2
0x1800193d3  lea     rcx, [rsp+2E0h+pclsid]; Buf1
0x1800193d8  call    memcmp_0
0x1800193dd  test    eax, eax
0x1800193df  jz      short loc_180019361
0x1800193e1  lea     rcx, [rsp+2E0h+ppv]
0x1800193e6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800193eb  lea     rax, [rsp+2E0h+ppv]
0x1800193f0  xor     edx, edx; pUnkOuter
0x1800193f2  lea     r9, IID_IContextMenu; riid
0x1800193f9  mov     [rsp+2E0h+phkResult], rax; ppv
0x1800193fe  lea     r8d, [rdi+1]; dwClsContext
0x180019402  lea     rcx, [rsp+2E0h+pclsid]; rclsid
0x180019407  call    cs:__imp_CoCreateInstance
0x18001940d  test    eax, eax
0x18001940f  js      loc_180019361
0x180019415  lea     rcx, [rsp+2E0h+var_290]
0x18001941a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18001941f  mov     rcx, [rsp+2E0h+ppv]
0x180019424  lea     r8, [rsp+2E0h+var_290]
0x180019429  lea     rdx, IID_IWABExtInit
0x180019430  mov     rax, [rcx]
0x180019433  mov     rax, [rax]
0x180019436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001943b  test    eax, eax
0x18001943d  js      loc_180019361
0x180019443  cmp     [r14], rdi
0x180019446  jnz     short loc_18001946A
0x180019448  mov     r8d, [rsp+2E0h+var_27C]; unsigned int
0x18001944d  mov     r9, r14; struct _WABEXTDISPLAY **
0x180019450  mov     rdx, rbx; struct _DPA *
0x180019453  mov     rcx, r13; this
0x180019456  call    ?_InitializeContextDataStruct@CExtensionContextMenus@@AEAAJPEAU_DPA@@IPEAPEAU_WABEXTDISPLAY@@@Z; CExtensionContextMenus::_InitializeContextDataStruct(_DPA *,uint,_WABEXTDISPLAY * *)
0x18001945b  mov     ebx, eax
0x18001945d  test    eax, eax
0x18001945f  js      loc_1800194F2
0x180019465  mov     rbx, [rsp+2E0h+var_270]
0x18001946a  mov     rcx, [rsp+2E0h+var_290]
0x18001946f  mov     rdx, [r14]
0x180019472  mov     rax, [rcx]
0x180019475  mov     rax, [rax+18h]
0x180019479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001947e  test    eax, eax
0x180019480  js      loc_180019361
0x180019486  mov     ecx, 18h; Size
0x18001948b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019490  mov     rdi, rax
0x180019493  test    rax, rax
0x180019496  jz      short loc_1800194DE
0x180019498  mov     rax, [rsp+2E0h+ppv]
0x18001949d  lea     rcx, ??_7ContextMenuExtData@@6B@; const ContextMenuExtData::`vftable'
0x1800194a4  mov     [rdi+8], rax
0x1800194a8  mov     r8, rdi; p
0x1800194ab  mov     eax, 0FFFFh
0x1800194b0  mov     [rdi], rcx
0x1800194b3  mov     [rdi+10h], eax
0x1800194b6  mov     edx, 7FFFFFFFh; i
0x1800194bb  mov     [rdi+14h], eax
0x1800194be  mov     rcx, rsi; hdpa
0x1800194c1  mov     [rsp+2E0h+ppv], 0
0x1800194ca  call    cs:__imp_DPA_InsertPtr
0x1800194d0  cmp     eax, 0FFFFFFFFh
0x1800194d3  jnz     loc_180019361
0x1800194d9  jmp     loc_180019308
0x1800194de  mov     ebx, 8007000Eh
0x1800194e3  xor     edi, edi
0x1800194e5  jmp     short loc_1800194F2
0x1800194e7  xor     ebx, ebx
0x1800194e9  mov     [r13+8], rsi
0x1800194ed  mov     [rsp+2E0h+var_278], rbx
0x1800194f2  lea     rcx, [rsp+2E0h+ppv]
0x1800194f7  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800194fc  lea     rcx, [rsp+2E0h+var_290]
0x180019501  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180019506  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001950b  test    rcx, rcx
0x18001950e  jz      short loc_18001951F
0x180019510  call    cs:__imp_RegCloseKey
0x180019516  mov     [rsp+2E0h+hKey], 0
0x18001951f  lea     rdx, [rsp+2E0h+var_278]; struct _DPA **
0x180019524  call    ?_FreeExtensionMenus@CExtensionContextMenus@@AEAAXPEAPEAU_DPA@@@Z; CExtensionContextMenus::_FreeExtensionMenus(_DPA * *)
0x180019529  test    rdi, rdi
0x18001952c  jz      short loc_180019541
0x18001952e  mov     rax, [rdi]
0x180019531  mov     edx, 1
0x180019536  mov     rcx, rdi
0x180019539  mov     rax, [rax]
0x18001953c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019541  mov     eax, ebx
0x180019543  mov     rcx, [rbp+1E0h+var_40]
0x18001954a  xor     rcx, rsp; StackCookie
0x18001954d  call    __security_check_cookie
0x180019552  mov     rbx, [rsp+2E0h+arg_18]
0x18001955a  add     rsp, 2B0h
0x180019561  pop     r15
0x180019563  pop     r14
0x180019565  pop     r13
0x180019567  pop     r12
0x180019569  pop     rdi
0x18001956a  pop     rsi
0x18001956b  pop     rbp
0x18001956c  retn
```
