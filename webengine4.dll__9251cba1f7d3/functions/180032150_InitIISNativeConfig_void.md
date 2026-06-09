# InitIISNativeConfig(void)

- ea: `0x180032150`
- end: `0x1800327f9`
- name: `?InitIISNativeConfig@@YAJXZ`
- size: `1705`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031974`
- `0x180031ae0`
- `0x180031b34`
- `0x180031c70`
- `0x180031e64`
- `0x180031fd8`

## callees

- `0x180007824`
- `0x18003166c`
- `0x180032150`
- `0x18004d030`
- `0x18004e5a8`
- `0x1800653c0`
- `0x180065b60`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180032215`
- `ole32!CoCreateInstance` at `0x180032238`
- `ole32!CoCreateInstance` at `0x180032215`
- `ole32!CoCreateInstance` at `0x180032238`
- `OLEAUT32!__imp_SysAllocString` at `0x1800321d4`
- `OLEAUT32!__imp_SysAllocString` at `0x180032274`
- `OLEAUT32!__imp_SysAllocString` at `0x18003228d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800322ea`
- `OLEAUT32!__imp_SysAllocString` at `0x180032303`
- `OLEAUT32!__imp_SysAllocString` at `0x18003231c`
- `OLEAUT32!__imp_SysAllocString` at `0x180032339`
- `OLEAUT32!__imp_SysAllocString` at `0x180032356`
- `OLEAUT32!__imp_SysAllocString` at `0x180032373`
- `OLEAUT32!__imp_SysAllocString` at `0x180032390`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323ca`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180032404`
- `OLEAUT32!__imp_SysAllocString` at `0x180032421`
- `OLEAUT32!__imp_SysAllocString` at `0x18003243e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003245b`
- `OLEAUT32!__imp_SysAllocString` at `0x180032478`
- `OLEAUT32!__imp_SysAllocString` at `0x180032498`
- `OLEAUT32!__imp_SysAllocString` at `0x1800324b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800324d2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003268f`
- `OLEAUT32!__imp_SysAllocString` at `0x180032717`
- `OLEAUT32!__imp_SysAllocString` at `0x180032797`
- `OLEAUT32!__imp_SysAllocString` at `0x1800321d4`
- `OLEAUT32!__imp_SysAllocString` at `0x180032274`
- `OLEAUT32!__imp_SysAllocString` at `0x18003228d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800322ea`
- `OLEAUT32!__imp_SysAllocString` at `0x180032303`
- `OLEAUT32!__imp_SysAllocString` at `0x18003231c`
- `OLEAUT32!__imp_SysAllocString` at `0x180032339`
- `OLEAUT32!__imp_SysAllocString` at `0x180032356`
- `OLEAUT32!__imp_SysAllocString` at `0x180032373`
- `OLEAUT32!__imp_SysAllocString` at `0x180032390`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323ca`
- `OLEAUT32!__imp_SysAllocString` at `0x1800323e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180032404`
- `OLEAUT32!__imp_SysAllocString` at `0x180032421`
- `OLEAUT32!__imp_SysAllocString` at `0x18003243e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003245b`
- `OLEAUT32!__imp_SysAllocString` at `0x180032478`
- `OLEAUT32!__imp_SysAllocString` at `0x180032498`
- `OLEAUT32!__imp_SysAllocString` at `0x1800324b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800324d2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003268f`
- `OLEAUT32!__imp_SysAllocString` at `0x180032717`
- `OLEAUT32!__imp_SysAllocString` at `0x180032797`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800327b6`
- `OLEAUT32!__imp_VariantInit` at `0x1800321a2`
- `OLEAUT32!__imp_VariantInit` at `0x1800321a2`
- `OLEAUT32!__imp_VariantClear` at `0x1800327c1`
- `OLEAUT32!__imp_VariantClear` at `0x1800327c1`

## string_xrefs

- `0x180032778`: `webengine4.dll`
- `0x1800326f4`: `aspnet_filter.dll`
- `0x18003266c`: `aspnet_isapi.dll`
- `0x180032437`: `extension`
- `0x180032471`: `physicalPath`

## pseudocode

```c
__int64 InitIISNativeConfig(void)
{
  unsigned int Instance; // ebx
  OLECHAR *v2; // rsi
  __int64 v3; // rax
  __int64 v4; // rdx
  OLECHAR *v5; // rcx
  OLECHAR v6; // ax
  OLECHAR *v7; // rax
  unsigned __int16 *v8; // rax
  const unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // rax
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  unsigned __int16 v13; // ax
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  signed __int64 v16; // rdi
  OLECHAR *v17; // rcx
  OLECHAR v18; // ax
  OLECHAR *v19; // rax
  __int64 v20; // rdx
  OLECHAR *v21; // rcx
  OLECHAR v22; // ax
  OLECHAR *v23; // rax
  __int64 v24; // r8
  OLECHAR *v25; // rcx
  OLECHAR v26; // ax
  OLECHAR *v27; // rax
  OLECHAR *v28; // rax
  int v29; // ecx
  VARIANTARG pvarg; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+48h] [rbp-C0h]
  _QWORD v32[5]; // [rsp+50h] [rbp-B8h] BYREF
  OLECHAR psz[264]; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int16 v34[264]; // [rsp+288h] [rbp+180h] BYREF

  if ( s_pAppHostWritableAdminManager )
    return 2147500035LL;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  memset_0(psz, 0, 0x20Au);
  memset_0(v34, 0, 0x20Au);
  s_bstrAppHostConfigPath = SysAllocString(L"MACHINE/WEBROOT/APPHOST");
  if ( s_bstrAppHostConfigPath )
  {
    GetRealProductVersion();
    if ( CoCreateInstance(
           &CLSID_AppHostWritableAdminManager,
           0,
           1u,
           &IID_IAppHostWritableAdminManager,
           &s_pAppHostWritableAdminManager) < 0 )
    {
      Instance = CoCreateInstance(
                   &CLSID_AppHostWritableAdminManager,
                   0,
                   0x15u,
                   &IID_IAppHostWritableAdminManager,
                   &s_pAppHostWritableAdminManager);
      if ( Instance )
        goto LABEL_77;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)s_pAppHostWritableAdminManager + 72LL))(
                 s_pAppHostWritableAdminManager,
                 s_bstrAppHostConfigPath);
    if ( Instance )
      goto LABEL_77;
    v2 = SysAllocString(L"defaultManagedRuntimeVersion");
    if ( v2 )
    {
      pvarg.pRecInfo = (IRecordInfo *)SysAllocString(L"4.0");
      if ( pvarg.pRecInfo )
      {
        pvarg.iVal = 8;
        v3 = *(_QWORD *)s_pAppHostWritableAdminManager;
        v32[3] = v31;
        *(_OWORD *)&v32[1] = *(_OWORD *)&pvarg.decVal.Lo32;
        (*(void (__fastcall **)(LPVOID, OLECHAR *, _QWORD *))(v3 + 40))(s_pAppHostWritableAdminManager, v2, &v32[1]);
        s_bstrPropNameIsapi = SysAllocString(L"scriptProcessor");
        if ( s_bstrPropNameIsapi )
        {
          s_bstrPropNamePreCond = SysAllocString(L"preCondition");
          if ( s_bstrPropNamePreCond )
          {
            s_bstrPropNameType = SysAllocString(L"type");
            if ( s_bstrPropNameType )
            {
              s_bstrPropNameManagedVer = SysAllocString(L"managedRuntimeVersion");
              if ( s_bstrPropNameManagedVer )
              {
                s_bstrPropNamePath = SysAllocString(L"path");
                if ( s_bstrPropNamePath )
                {
                  s_bstrPropNameAppPool = SysAllocString(L"applicationPool");
                  if ( s_bstrPropNameAppPool )
                  {
                    s_bstrPropNameName = SysAllocString(L"name");
                    if ( s_bstrPropNameName )
                    {
                      s_bstrPropNameVerb = SysAllocString(L"verb");
                      if ( s_bstrPropNameVerb )
                      {
                        s_bstrPropNameAdd = SysAllocString(L"add");
                        if ( s_bstrPropNameAdd )
                        {
                          s_bstrPropNameParentElement = SysAllocString(L"parentElement");
                          if ( s_bstrPropNameParentElement )
                          {
                            s_bstrPropNameFilter = SysAllocString(L"filter");
                            if ( s_bstrPropNameFilter )
                            {
                              s_bstrPropNameIsDefaultValue = SysAllocString(L"isDefaultValue");
                              if ( s_bstrPropNameIsDefaultValue )
                              {
                                s_bstrPropNameExtension = SysAllocString(L"extension");
                                if ( s_bstrPropNameExtension )
                                {
                                  s_bstrPropNameIsPresent = SysAllocString(L"isPresent");
                                  if ( s_bstrPropNameIsPresent )
                                  {
                                    s_bstrPropNamePhyPath = SysAllocString(L"physicalPath");
                                    if ( s_bstrPropNamePhyPath )
                                    {
                                      s_bstr64BitIsapiFullPath = SysAllocString(&Names::s_wszIsapiFullPath);
                                      if ( s_bstr64BitIsapiFullPath )
                                      {
                                        s_bstr64BitFilterFullPath = SysAllocString(&Names::s_wszFilterFullPath);
                                        if ( s_bstr64BitFilterFullPath )
                                        {
                                          s_bstr64BitEngineFullPath = SysAllocString(&Names::s_wszEngineFullPath);
                                          if ( s_bstr64BitFilterFullPath )
                                          {
                                            v4 = 261;
                                            v5 = psz;
                                            do
                                            {
                                              if ( v4 == -2147483385 )
                                                break;
                                              v6 = *(OLECHAR *)((char *)v5
                                                              + (char *)&Names::s_wszIsapiFullPath
                                                              - (char *)psz);
                                              if ( !v6 )
                                                break;
                                              *v5++ = v6;
                                              --v4;
                                            }
                                            while ( v4 );
                                            v7 = v5 - 1;
                                            if ( v4 )
                                              v7 = v5;
                                            *v7 = 0;
                                            Instance = v4 == 0 ? 0x8007007A : 0;
                                            if ( !v4 )
                                              goto LABEL_76;
                                            v8 = wcsistr(psz, L"64\\v4.0");
                                            if ( !v8 || (v9 = v8 + 2, *v8 = 0, (v10 = wcsistr(v8 + 3, L"\\")) == 0) )
                                            {
                                              Instance = -2147467259;
                                              goto LABEL_76;
                                            }
                                            v10[1] = 0;
                                            v11 = 261;
                                            v12 = v34;
                                            do
                                            {
                                              if ( v11 == -2147483385 )
                                                break;
                                              v13 = *(unsigned __int16 *)((char *)v12 + (char *)psz - (char *)v34);
                                              if ( !v13 )
                                                break;
                                              *v12++ = v13;
                                              --v11;
                                            }
                                            while ( v11 );
                                            v14 = v12 - 1;
                                            if ( v11 )
                                              v14 = v12;
                                            *v14 = 0;
                                            Instance = v11 == 0 ? 0x8007007A : 0;
                                            if ( !v11 )
                                              goto LABEL_76;
                                            Instance = StringCchCatW(v34, 0x105u, v9);
                                            if ( Instance )
                                              goto LABEL_76;
                                            v15 = 261;
                                            v16 = (char *)v34 - (char *)psz;
                                            v17 = psz;
                                            do
                                            {
                                              if ( v15 == -2147483385 )
                                                break;
                                              v18 = *(OLECHAR *)((char *)v17 + v16);
                                              if ( !v18 )
                                                break;
                                              *v17++ = v18;
                                              --v15;
                                            }
                                            while ( v15 );
                                            v19 = v17 - 1;
                                            if ( v15 )
                                              v19 = v17;
                                            *v19 = 0;
                                            Instance = v15 == 0 ? 0x8007007A : 0;
                                            if ( !v15 )
                                              goto LABEL_76;
                                            Instance = StringCchCatW(psz, 0x105u, L"aspnet_isapi.dll");
                                            if ( Instance )
                                              goto LABEL_76;
                                            s_bstr32BitIsapiFullPath = SysAllocString(psz);
                                            if ( s_bstr32BitIsapiFullPath )
                                            {
                                              v20 = 261;
                                              v21 = psz;
                                              do
                                              {
                                                if ( v20 == -2147483385 )
                                                  break;
                                                v22 = *(OLECHAR *)((char *)v21 + v16);
                                                if ( !v22 )
                                                  break;
                                                *v21++ = v22;
                                                --v20;
                                              }
                                              while ( v20 );
                                              v23 = v21 - 1;
                                              if ( v20 )
                                                v23 = v21;
                                              *v23 = 0;
                                              Instance = v20 == 0 ? 0x8007007A : 0;
                                              if ( !v20 )
                                                goto LABEL_76;
                                              Instance = StringCchCatW(psz, 0x105u, L"aspnet_filter.dll");
                                              if ( Instance )
                                                goto LABEL_76;
                                              s_bstr32BitFilterFullPath = SysAllocString(psz);
                                              if ( s_bstr32BitFilterFullPath )
                                              {
                                                v24 = 261;
                                                v25 = psz;
                                                do
                                                {
                                                  if ( v24 == -2147483385 )
                                                    break;
                                                  v26 = *(OLECHAR *)((char *)v25 + v16);
                                                  if ( !v26 )
                                                    break;
                                                  *v25++ = v26;
                                                  --v24;
                                                }
                                                while ( v24 );
                                                v27 = v25 - 1;
                                                if ( v24 )
                                                  v27 = v25;
                                                *v27 = 0;
                                                Instance = v24 == 0 ? 0x8007007A : 0;
                                                if ( v24 )
                                                {
                                                  Instance = StringCchCatW(psz, 0x105u, L"webengine4.dll");
                                                  if ( !Instance )
                                                  {
                                                    v28 = SysAllocString(psz);
                                                    v29 = 0;
                                                    s_bstr32BitEngineFullPath = v28;
                                                    if ( !v28 )
                                                      v29 = -2147024882;
                                                    Instance = v29;
                                                  }
                                                }
                                                goto LABEL_76;
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      Instance = -2147024882;
LABEL_76:
      SysFreeString(v2);
      goto LABEL_77;
    }
  }
  Instance = -2147024882;
LABEL_77:
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  return Instance;
}

```

## disassembly

```asm
0x180032150  mov     rax, rsp
0x180032153  mov     [rax+8], rbx
0x180032157  mov     [rax+10h], rsi
0x18003215b  mov     [rax+18h], rdi
0x18003215f  mov     [rax+20h], r12
0x180032163  push    rbp
0x180032164  push    r14
0x180032166  push    r15
0x180032168  lea     rbp, [rax-3B8h]
0x18003216f  sub     rsp, 4A0h
0x180032176  mov     rax, cs:__security_cookie
0x18003217d  xor     rax, rsp
0x180032180  mov     [rbp+3B0h+var_20], rax
0x180032187  xor     r14d, r14d
0x18003218a  cmp     cs:?s_pAppHostWritableAdminManager@@3PEAUIAppHostWritableAdminManager@@EA, r14; IAppHostWritableAdminManager * s_pAppHostWritableAdminManager
0x180032191  jz      short loc_18003219D
0x180032193  mov     eax, 80004003h
0x180032198  jmp     loc_1800327C9
0x18003219d  lea     rcx, [rsp+4B0h+pvarg+8]; pvarg
0x1800321a2  call    cs:__imp_VariantInit
0x1800321a8  mov     ebx, 20Ah
0x1800321ad  lea     rcx, [rsp+4B0h+psz]; void *
0x1800321b2  mov     r8d, ebx; Size
0x1800321b5  xor     edx, edx; Val
0x1800321b7  call    memset_0
0x1800321bc  mov     r8d, ebx; Size
0x1800321bf  lea     rcx, [rbp+3B0h+var_230]; void *
0x1800321c6  xor     edx, edx; Val
0x1800321c8  call    memset_0
0x1800321cd  lea     rcx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800321d4  call    cs:__imp_SysAllocString
0x1800321da  mov     cs:?s_bstrAppHostConfigPath@@3PEAGEA, rax; ushort * s_bstrAppHostConfigPath
0x1800321e1  test    rax, rax
0x1800321e4  jnz     short loc_1800321F0
0x1800321e6  mov     ebx, 8007000Eh
0x1800321eb  jmp     loc_1800327BC
0x1800321f0  call    ?GetRealProductVersion@@YAXXZ; GetRealProductVersion(void)
0x1800321f5  xor     edx, edx; pUnkOuter
0x1800321f7  lea     rbx, ?s_pAppHostWritableAdminManager@@3PEAUIAppHostWritableAdminManager@@EA; IAppHostWritableAdminManager * s_pAppHostWritableAdminManager
0x1800321fe  lea     r9, IID_IAppHostWritableAdminManager; riid
0x180032205  mov     [rsp+4B0h+ppv], rbx; ppv
0x18003220a  lea     rcx, CLSID_AppHostWritableAdminManager; rclsid
0x180032211  lea     r8d, [rdx+1]; dwClsContext
0x180032215  call    cs:__imp_CoCreateInstance
0x18003221b  test    eax, eax
0x18003221d  jns     short loc_180032248
0x18003221f  xor     edx, edx; pUnkOuter
0x180032221  mov     [rsp+4B0h+ppv], rbx; ppv
0x180032226  lea     r9, IID_IAppHostWritableAdminManager; riid
0x18003222d  lea     rcx, CLSID_AppHostWritableAdminManager; rclsid
0x180032234  lea     r8d, [rdx+15h]; dwClsContext
0x180032238  call    cs:__imp_CoCreateInstance
0x18003223e  mov     ebx, eax
0x180032240  test    eax, eax
0x180032242  jnz     loc_1800327BC
0x180032248  mov     rcx, cs:?s_pAppHostWritableAdminManager@@3PEAUIAppHostWritableAdminManager@@EA; IAppHostWritableAdminManager * s_pAppHostWritableAdminManager
0x18003224f  mov     rdx, cs:?s_bstrAppHostConfigPath@@3PEAGEA; ushort * s_bstrAppHostConfigPath
0x180032256  mov     rax, [rcx]
0x180032259  mov     rax, [rax+48h]
0x18003225d  call    cs:__guard_dispatch_icall_fptr
0x180032263  mov     ebx, eax
0x180032265  test    eax, eax
0x180032267  jnz     loc_1800327BC
0x18003226d  lea     rcx, aDefaultmanaged; "defaultManagedRuntimeVersion"
0x180032274  call    cs:__imp_SysAllocString
0x18003227a  mov     rsi, rax
0x18003227d  test    rax, rax
0x180032280  jz      loc_1800321E6
0x180032286  lea     rcx, a40; "4.0"
0x18003228d  call    cs:__imp_SysAllocString
0x180032293  mov     qword ptr [rsp+4B0h+pvarg+10h], rax
0x180032298  test    rax, rax
0x18003229b  jnz     short loc_1800322A7
0x18003229d  mov     ebx, 8007000Eh
0x1800322a2  jmp     loc_1800327B3
0x1800322a7  mov     rcx, cs:?s_pAppHostWritableAdminManager@@3PEAUIAppHostWritableAdminManager@@EA; IAppHostWritableAdminManager * s_pAppHostWritableAdminManager
0x1800322ae  lea     r8, [rsp+4B0h+var_468+8]
0x1800322b3  movsd   xmm1, [rsp+4B0h+var_470]
0x1800322b9  mov     eax, 8
0x1800322be  mov     word ptr [rsp+4B0h+pvarg+8], ax
0x1800322c3  mov     rdx, rsi
0x1800322c6  movups  xmm0, xmmword ptr [rsp+4B0h+pvarg+8]
0x1800322cb  mov     rax, [rcx]
0x1800322ce  movsd   [rsp+4B0h+var_450], xmm1
0x1800322d4  movaps  xmmword ptr [rsp+4B0h+var_468+8], xmm0
0x1800322d9  mov     rax, [rax+28h]
0x1800322dd  call    cs:__guard_dispatch_icall_fptr
0x1800322e3  lea     rcx, aScriptprocesso; "scriptProcessor"
0x1800322ea  call    cs:__imp_SysAllocString
0x1800322f0  mov     cs:?s_bstrPropNameIsapi@@3PEAGEA, rax; ushort * s_bstrPropNameIsapi
0x1800322f7  test    rax, rax
0x1800322fa  jz      short loc_18003229D
0x1800322fc  lea     rcx, aPrecondition; "preCondition"
0x180032303  call    cs:__imp_SysAllocString
0x180032309  mov     cs:?s_bstrPropNamePreCond@@3PEAGEA, rax; ushort * s_bstrPropNamePreCond
0x180032310  test    rax, rax
0x180032313  jz      short loc_18003229D
0x180032315  lea     rcx, aType; "type"
0x18003231c  call    cs:__imp_SysAllocString
0x180032322  mov     cs:?s_bstrPropNameType@@3PEAGEA, rax; ushort * s_bstrPropNameType
0x180032329  test    rax, rax
0x18003232c  jz      loc_18003229D
0x180032332  lea     rcx, aManagedruntime; "managedRuntimeVersion"
0x180032339  call    cs:__imp_SysAllocString
0x18003233f  mov     cs:?s_bstrPropNameManagedVer@@3PEAGEA, rax; ushort * s_bstrPropNameManagedVer
0x180032346  test    rax, rax
0x180032349  jz      loc_18003229D
0x18003234f  lea     rcx, aPath_0; "path"
0x180032356  call    cs:__imp_SysAllocString
0x18003235c  mov     cs:?s_bstrPropNamePath@@3PEAGEA, rax; ushort * s_bstrPropNamePath
0x180032363  test    rax, rax
0x180032366  jz      loc_18003229D
0x18003236c  lea     rcx, aApplicationpoo; "applicationPool"
0x180032373  call    cs:__imp_SysAllocString
0x180032379  mov     cs:?s_bstrPropNameAppPool@@3PEAGEA, rax; ushort * s_bstrPropNameAppPool
0x180032380  test    rax, rax
0x180032383  jz      loc_18003229D
0x180032389  lea     rcx, aName; "name"
0x180032390  call    cs:__imp_SysAllocString
0x180032396  mov     cs:?s_bstrPropNameName@@3PEAGEA, rax; ushort * s_bstrPropNameName
0x18003239d  test    rax, rax
0x1800323a0  jz      loc_18003229D
0x1800323a6  lea     rcx, aVerb; "verb"
0x1800323ad  call    cs:__imp_SysAllocString
0x1800323b3  mov     cs:?s_bstrPropNameVerb@@3PEAGEA, rax; ushort * s_bstrPropNameVerb
0x1800323ba  test    rax, rax
0x1800323bd  jz      loc_18003229D
0x1800323c3  lea     rcx, aAdd; "add"
0x1800323ca  call    cs:__imp_SysAllocString
0x1800323d0  mov     cs:?s_bstrPropNameAdd@@3PEAGEA, rax; ushort * s_bstrPropNameAdd
0x1800323d7  test    rax, rax
0x1800323da  jz      loc_18003229D
0x1800323e0  lea     rcx, aParentelement; "parentElement"
0x1800323e7  call    cs:__imp_SysAllocString
0x1800323ed  mov     cs:?s_bstrPropNameParentElement@@3PEAGEA, rax; ushort * s_bstrPropNameParentElement
0x1800323f4  test    rax, rax
0x1800323f7  jz      loc_18003229D
0x1800323fd  lea     rcx, aFilter; "filter"
0x180032404  call    cs:__imp_SysAllocString
0x18003240a  mov     cs:?s_bstrPropNameFilter@@3PEAGEA, rax; ushort * s_bstrPropNameFilter
0x180032411  test    rax, rax
0x180032414  jz      loc_18003229D
0x18003241a  lea     rcx, aIsdefaultvalue; "isDefaultValue"
0x180032421  call    cs:__imp_SysAllocString
0x180032427  mov     cs:?s_bstrPropNameIsDefaultValue@@3PEAGEA, rax; ushort * s_bstrPropNameIsDefaultValue
0x18003242e  test    rax, rax
0x180032431  jz      loc_18003229D
0x180032437  lea     rcx, aExtension; "extension"
0x18003243e  call    cs:__imp_SysAllocString
0x180032444  mov     cs:?s_bstrPropNameExtension@@3PEAGEA, rax; ushort * s_bstrPropNameExtension
0x18003244b  test    rax, rax
0x18003244e  jz      loc_18003229D
0x180032454  lea     rcx, aIspresent; "isPresent"
0x18003245b  call    cs:__imp_SysAllocString
0x180032461  mov     cs:?s_bstrPropNameIsPresent@@3PEAGEA, rax; ushort * s_bstrPropNameIsPresent
0x180032468  test    rax, rax
0x18003246b  jz      loc_18003229D
0x180032471  lea     rcx, aPhysicalpath; "physicalPath"
0x180032478  call    cs:__imp_SysAllocString
0x18003247e  mov     cs:?s_bstrPropNamePhyPath@@3PEAGEA, rax; ushort * s_bstrPropNamePhyPath
0x180032485  test    rax, rax
0x180032488  jz      loc_18003229D
0x18003248e  lea     rbx, ?s_wszIsapiFullPath@Names@@0PAGA; ushort near * Names::s_wszIsapiFullPath
0x180032495  mov     rcx, rbx; psz
0x180032498  call    cs:__imp_SysAllocString
0x18003249e  mov     cs:?s_bstr64BitIsapiFullPath@@3PEAGEA, rax; ushort * s_bstr64BitIsapiFullPath
0x1800324a5  test    rax, rax
0x1800324a8  jz      loc_18003229D
0x1800324ae  lea     rcx, ?s_wszFilterFullPath@Names@@0PAGA; psz
0x1800324b5  call    cs:__imp_SysAllocString
0x1800324bb  mov     cs:?s_bstr64BitFilterFullPath@@3PEAGEA, rax; ushort * s_bstr64BitFilterFullPath
0x1800324c2  test    rax, rax
0x1800324c5  jz      loc_18003229D
0x1800324cb  lea     rcx, ?s_wszEngineFullPath@Names@@0PAGA; psz
0x1800324d2  call    cs:__imp_SysAllocString
0x1800324d8  cmp     cs:?s_bstr64BitFilterFullPath@@3PEAGEA, r14; ushort * s_bstr64BitFilterFullPath
0x1800324df  mov     cs:?s_bstr64BitEngineFullPath@@3PEAGEA, rax; ushort * s_bstr64BitEngineFullPath
0x1800324e6  jz      loc_18003229D
0x1800324ec  mov     r15d, 105h
0x1800324f2  lea     rax, [rsp+4B0h+psz]
0x1800324f7  mov     edx, r15d
0x1800324fa  lea     rcx, [rsp+4B0h+psz]
0x1800324ff  sub     rbx, rax
0x180032502  lea     rax, [rdx+7FFFFEF9h]
0x180032509  test    rax, rax
0x18003250c  jz      short loc_180032524
0x18003250e  movzx   eax, word ptr [rbx+rcx]
0x180032512  test    ax, ax
0x180032515  jz      short loc_180032524
0x180032517  mov     [rcx], ax
0x18003251a  add     rcx, 2
0x18003251e  sub     rdx, 1
0x180032522  jnz     short loc_180032502
0x180032524  test    rdx, rdx
0x180032527  lea     rax, [rcx-2]
0x18003252b  mov     r12d, 8007007Ah
0x180032531  cmovnz  rax, rcx
0x180032535  mov     [rax], r14w
0x180032539  mov     rax, rdx
0x18003253c  neg     rax
0x18003253f  sbb     ebx, ebx
0x180032541  not     ebx
0x180032543  and     ebx, r12d
0x180032546  test    rdx, rdx
0x180032549  jz      loc_1800327B3
0x18003254f  lea     rdx, a64V40; "64\\v4.0"
0x180032556  lea     rcx, [rsp+4B0h+psz]; unsigned __int16 *
0x18003255b  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x180032560  test    rax, rax
0x180032563  jnz     short loc_18003256F
0x180032565  mov     ebx, 80004005h
0x18003256a  jmp     loc_1800327B3
0x18003256f  lea     rdi, [rax+4]
0x180032573  mov     [rax], r14w
0x180032577  lea     rcx, [rdi+2]; unsigned __int16 *
0x18003257b  lea     rdx, SubBlock; "\\"
0x180032582  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x180032587  test    rax, rax
0x18003258a  jz      short loc_180032565
0x18003258c  mov     [rax+2], r14w
0x180032591  lea     r8, [rsp+4B0h+psz]
0x180032596  lea     rax, [rbp+3B0h+var_230]
0x18003259d  mov     rdx, r15
0x1800325a0  sub     r8, rax
0x1800325a3  lea     rcx, [rbp+3B0h+var_230]
0x1800325aa  lea     rax, [rdx+7FFFFEF9h]
0x1800325b1  test    rax, rax
0x1800325b4  jz      short loc_1800325CD
0x1800325b6  movzx   eax, word ptr [rcx+r8]
0x1800325bb  test    ax, ax
0x1800325be  jz      short loc_1800325CD
0x1800325c0  mov     [rcx], ax
0x1800325c3  add     rcx, 2
0x1800325c7  sub     rdx, 1
0x1800325cb  jnz     short loc_1800325AA
0x1800325cd  test    rdx, rdx
0x1800325d0  lea     rax, [rcx-2]
0x1800325d4  cmovnz  rax, rcx
0x1800325d8  mov     [rax], r14w
0x1800325dc  mov     rax, rdx
0x1800325df  neg     rax
0x1800325e2  sbb     ebx, ebx
0x1800325e4  not     ebx
0x1800325e6  and     ebx, r12d
0x1800325e9  test    rdx, rdx
0x1800325ec  jz      loc_1800327B3
0x1800325f2  mov     r8, rdi; unsigned __int16 *
0x1800325f5  lea     rcx, [rbp+3B0h+var_230]; unsigned __int16 *
0x1800325fc  mov     rdx, r15; unsigned __int64
0x1800325ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032604  mov     ebx, eax
0x180032606  test    eax, eax
0x180032608  jnz     loc_1800327B3
0x18003260e  lea     rdi, [rbp+3B0h+var_230]
0x180032615  mov     rdx, r15
0x180032618  lea     rax, [rsp+4B0h+psz]
0x18003261d  sub     rdi, rax
0x180032620  lea     rcx, [rsp+4B0h+psz]
0x180032625  lea     rax, [rdx+7FFFFEF9h]
0x18003262c  test    rax, rax
0x18003262f  jz      short loc_180032647
0x180032631  movzx   eax, word ptr [rcx+rdi]
0x180032635  test    ax, ax
0x180032638  jz      short loc_180032647
0x18003263a  mov     [rcx], ax
0x18003263d  add     rcx, 2
0x180032641  sub     rdx, 1
0x180032645  jnz     short loc_180032625
0x180032647  test    rdx, rdx
0x18003264a  lea     rax, [rcx-2]
0x18003264e  cmovnz  rax, rcx
0x180032652  mov     [rax], r14w
0x180032656  mov     rax, rdx
0x180032659  neg     rax
0x18003265c  sbb     ebx, ebx
0x18003265e  not     ebx
0x180032660  and     ebx, r12d
0x180032663  test    rdx, rdx
0x180032666  jz      loc_1800327B3
0x18003266c  lea     r8, aAspnetIsapiDll_0; "aspnet_isapi.dll"
0x180032673  mov     rdx, r15; unsigned __int64
0x180032676  lea     rcx, [rsp+4B0h+psz]; unsigned __int16 *
0x18003267b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032680  mov     ebx, eax
0x180032682  test    eax, eax
0x180032684  jnz     loc_1800327B3
0x18003268a  lea     rcx, [rsp+4B0h+psz]; psz
0x18003268f  call    cs:__imp_SysAllocString
0x180032695  mov     cs:?s_bstr32BitIsapiFullPath@@3PEAGEA, rax; ushort * s_bstr32BitIsapiFullPath
0x18003269c  test    rax, rax
0x18003269f  jz      loc_18003229D
0x1800326a5  mov     rdx, r15
0x1800326a8  lea     rcx, [rsp+4B0h+psz]
0x1800326ad  lea     rax, [rdx+7FFFFEF9h]
0x1800326b4  test    rax, rax
0x1800326b7  jz      short loc_1800326CF
0x1800326b9  movzx   eax, word ptr [rcx+rdi]
0x1800326bd  test    ax, ax
0x1800326c0  jz      short loc_1800326CF
0x1800326c2  mov     [rcx], ax
  ... truncated ...
```
