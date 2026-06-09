# DisplayManagementSettings(ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x1800385e0`
- end: `0x180038807`
- name: `?DisplayManagementSettings@@YAJPEAG0000@Z`
- size: `551`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180037b08`
- `0x180038400`
- `0x1800385e0`
- `0x18003abe4`
- `0x18004d854`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800386fb`
- `KERNEL32!GetCurrentProcessId` at `0x1800386fb`
- `ole32!CoUninitialize` at `0x18003878d`
- `ole32!CoUninitialize` at `0x18003878d`
- `OLEAUT32!__imp_SysAllocString` at `0x180038624`
- `OLEAUT32!__imp_SysAllocString` at `0x180038641`
- `OLEAUT32!__imp_SysAllocString` at `0x18003865e`
- `OLEAUT32!__imp_SysAllocString` at `0x180038670`
- `OLEAUT32!__imp_SysAllocString` at `0x18003868d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800386ab`
- `OLEAUT32!__imp_SysAllocString` at `0x180038624`
- `OLEAUT32!__imp_SysAllocString` at `0x180038641`
- `OLEAUT32!__imp_SysAllocString` at `0x18003865e`
- `OLEAUT32!__imp_SysAllocString` at `0x180038670`
- `OLEAUT32!__imp_SysAllocString` at `0x18003868d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800386ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18003879c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003879c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800387e7`
- `OLEAUT32!__imp_SysStringLen` at `0x18003873f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003873f`

## string_xrefs

- `0x1800386c3`: `Display Management Configuration Settings user interface`
- `0x180038761`: `Display Management Configuration Settings user interface`

## pseudocode

```c
__int64 __fastcall DisplayManagementSettings(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  OLECHAR *v7; // r12
  OLECHAR *v8; // r14
  OLECHAR *v9; // r15
  OLECHAR *v10; // rsi
  OLECHAR *v11; // rdi
  unsigned int DisplayConfigUtilityManagedRuntime; // ebx
  const OLECHAR *v13; // rcx
  const OLECHAR *v14; // rcx
  const OLECHAR *v15; // rcx
  DWORD CurrentProcessId; // eax
  int v18; // [rsp+50h] [rbp-20h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp-18h] BYREF
  struct xspmrt::_RegiisUtility *v20; // [rsp+60h] [rbp-10h] BYREF

  v20 = 0;
  v18 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  pbstr = SysAllocString(&Class);
  if ( !pbstr )
    goto LABEL_2;
  v7 = SysAllocString(a1);
  if ( !v7 )
    goto LABEL_2;
  v13 = a2;
  if ( !a2 )
    v13 = &Class;
  v8 = SysAllocString(v13);
  if ( !v8 )
    goto LABEL_2;
  v9 = SysAllocString(a3);
  if ( !v9 )
    goto LABEL_2;
  v14 = a4;
  if ( !a4 )
    v14 = &Class;
  v10 = SysAllocString(v14);
  if ( !v10 )
    goto LABEL_2;
  v15 = a5;
  if ( !a5 )
    v15 = &Class;
  v11 = SysAllocString(v15);
  if ( v11 )
  {
    CSetupLogging::Log(1, "DisplayManagementSettings", 0, "Display Management Configuration Settings user interface", 0);
    DisplayConfigUtilityManagedRuntime = EnsureCoInitialized(&v18);
    if ( !DisplayConfigUtilityManagedRuntime )
    {
      DisplayConfigUtilityManagedRuntime = CreateDisplayConfigUtilityManagedRuntime((LPVOID *)&v20);
      if ( !DisplayConfigUtilityManagedRuntime )
      {
        CurrentProcessId = GetCurrentProcessId();
        DisplayConfigUtilityManagedRuntime = (*(__int64 (__fastcall **)(struct xspmrt::_RegiisUtility *, OLECHAR *, OLECHAR *, OLECHAR *, OLECHAR *, OLECHAR *, DWORD, BSTR *))(*(_QWORD *)v20 + 56LL))(
                                               v20,
                                               v7,
                                               v8,
                                               v9,
                                               v10,
                                               v11,
                                               CurrentProcessId,
                                               &pbstr);
        if ( !DisplayConfigUtilityManagedRuntime )
          goto LABEL_19;
      }
    }
  }
  else
  {
LABEL_2:
    DisplayConfigUtilityManagedRuntime = -2147024882;
  }
  if ( SysStringLen(pbstr) )
  {
    CSetupLogging::Log(
      DisplayConfigUtilityManagedRuntime,
      "DisplayManagementSettings",
      0,
      "DisplayManagementSettings with exception: ",
      pbstr);
    goto LABEL_20;
  }
LABEL_19:
  CSetupLogging::Log(
    DisplayConfigUtilityManagedRuntime,
    "DisplayManagementSettings",
    0,
    "Display Management Configuration Settings user interface",
    0);
LABEL_20:
  if ( v20 )
    DeleteRegiisUtilityManagedRuntime(v20);
  if ( v18 )
    CoUninitialize();
  if ( pbstr )
  {
    SysFreeString(pbstr);
    pbstr = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  if ( v8 )
    SysFreeString(v8);
  if ( v9 )
    SysFreeString(v9);
  if ( v10 )
    SysFreeString(v10);
  if ( v11 )
    SysFreeString(v11);
  return DisplayConfigUtilityManagedRuntime;
}

```

## disassembly

```asm
0x1800385e0  mov     [rsp-38h+arg_8], rbx
0x1800385e5  mov     [rsp-38h+arg_10], r8
0x1800385ea  mov     [rsp-38h+psz], rcx
0x1800385ef  push    rbp
0x1800385f0  push    rsi
0x1800385f1  push    rdi
0x1800385f2  push    r12
0x1800385f4  push    r13
0x1800385f6  push    r14
0x1800385f8  push    r15
0x1800385fa  mov     rbp, rsp
0x1800385fd  sub     rsp, 70h
0x180038601  and     [rbp+var_10], 0
0x180038606  lea     rcx, Class; psz
0x18003860d  and     [rbp+var_20], 0
0x180038611  mov     r13, r9
0x180038614  mov     rbx, rdx
0x180038617  xor     r12d, r12d
0x18003861a  xor     r14d, r14d
0x18003861d  xor     r15d, r15d
0x180038620  xor     esi, esi
0x180038622  xor     edi, edi
0x180038624  call    cs:__imp_SysAllocString
0x18003862a  mov     [rbp+pbstr], rax
0x18003862e  test    rax, rax
0x180038631  jnz     short loc_18003863D
0x180038633  mov     ebx, 8007000Eh
0x180038638  jmp     loc_18003873B
0x18003863d  mov     rcx, [rbp+psz]; psz
0x180038641  call    cs:__imp_SysAllocString
0x180038647  mov     r12, rax
0x18003864a  test    rax, rax
0x18003864d  jz      short loc_180038633
0x18003864f  mov     rcx, rbx
0x180038652  test    rbx, rbx
0x180038655  jnz     short loc_18003865E
0x180038657  lea     rcx, Class; psz
0x18003865e  call    cs:__imp_SysAllocString
0x180038664  mov     r14, rax
0x180038667  test    rax, rax
0x18003866a  jz      short loc_180038633
0x18003866c  mov     rcx, [rbp+arg_10]; psz
0x180038670  call    cs:__imp_SysAllocString
0x180038676  mov     r15, rax
0x180038679  test    rax, rax
0x18003867c  jz      short loc_180038633
0x18003867e  mov     rcx, r13
0x180038681  test    r13, r13
0x180038684  jnz     short loc_18003868D
0x180038686  lea     rcx, Class; psz
0x18003868d  call    cs:__imp_SysAllocString
0x180038693  mov     rsi, rax
0x180038696  test    rax, rax
0x180038699  jz      short loc_180038633
0x18003869b  mov     rcx, [rbp+arg_20]
0x18003869f  test    rcx, rcx
0x1800386a2  jnz     short loc_1800386AB
0x1800386a4  lea     rcx, Class; psz
0x1800386ab  call    cs:__imp_SysAllocString
0x1800386b1  mov     rdi, rax
0x1800386b4  test    rax, rax
0x1800386b7  jz      loc_180038633
0x1800386bd  and     [rsp+70h+var_50], 0
0x1800386c3  lea     r9, aDisplayManagem
0x1800386ca  xor     r8d, r8d; unsigned int
0x1800386cd  lea     rdx, aDisplaymanagem_0
0x1800386d4  lea     ecx, [r8+1]; int
0x1800386d8  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z
0x1800386dd  lea     rcx, [rbp+var_20]; int *
0x1800386e1  call    ?EnsureCoInitialized@@YAJPEAH@Z
0x1800386e6  mov     ebx, eax
0x1800386e8  test    eax, eax
0x1800386ea  jnz     short loc_18003873B
0x1800386ec  lea     rcx, [rbp+var_10]; struct xspmrt::_AspNetManagementUtility **
0x1800386f0  call    ?CreateDisplayConfigUtilityManagedRuntime@@YAJPEAPEAU_AspNetManagementUtility@xspmrt@@@Z
0x1800386f5  mov     ebx, eax
0x1800386f7  test    eax, eax
0x1800386f9  jnz     short loc_18003873B
0x1800386fb  call    cs:__imp_GetCurrentProcessId
0x180038701  mov     rcx, [rbp+var_10]
0x180038705  mov     r9, r15
0x180038708  mov     r8, r14
0x18003870b  mov     rdx, [rcx]
0x18003870e  mov     r10, [rdx+38h]
0x180038712  lea     rdx, [rbp+pbstr]
0x180038716  mov     [rsp+70h+var_38], rdx
0x18003871b  mov     rdx, r12
0x18003871e  mov     [rsp+70h+var_40], eax
0x180038722  mov     rax, r10
0x180038725  mov     [rsp+70h+var_48], rdi
0x18003872a  mov     [rsp+70h+var_50], rsi; unsigned __int16 *
0x18003872f  call    cs:__guard_dispatch_icall_fptr
0x180038735  mov     ebx, eax
0x180038737  test    eax, eax
0x180038739  jz      short loc_18003875B
0x18003873b  mov     rcx, [rbp+pbstr]; pbstr
0x18003873f  call    cs:__imp_SysStringLen
0x180038745  test    eax, eax
0x180038747  jz      short loc_18003875B
0x180038749  mov     rax, [rbp+pbstr]
0x18003874d  lea     r9, aDisplaymanagem_1
0x180038754  mov     [rsp+70h+var_50], rax
0x180038759  jmp     short loc_180038768
0x18003875b  and     [rsp+70h+var_50], 0
0x180038761  lea     r9, aDisplayManagem
0x180038768  xor     r8d, r8d; unsigned int
0x18003876b  lea     rdx, aDisplaymanagem_0
0x180038772  mov     ecx, ebx; int
0x180038774  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z
0x180038779  mov     rcx, [rbp+var_10]; struct xspmrt::_RegiisUtility *
0x18003877d  test    rcx, rcx
0x180038780  jz      short loc_180038787
0x180038782  call    ?DeleteRegiisUtilityManagedRuntime@@YAJPEAU_RegiisUtility@xspmrt@@@Z
0x180038787  cmp     [rbp+var_20], 0
0x18003878b  jz      short loc_180038793
0x18003878d  call    cs:__imp_CoUninitialize
0x180038793  mov     rcx, [rbp+pbstr]; bstrString
0x180038797  test    rcx, rcx
0x18003879a  jz      short loc_1800387A7
0x18003879c  call    cs:__imp_SysFreeString
0x1800387a2  and     [rbp+pbstr], 0
0x1800387a7  test    r12, r12
0x1800387aa  jz      short loc_1800387B5
0x1800387ac  mov     rcx, r12; bstrString
0x1800387af  call    cs:__imp_SysFreeString
0x1800387b5  test    r14, r14
0x1800387b8  jz      short loc_1800387C3
0x1800387ba  mov     rcx, r14; bstrString
0x1800387bd  call    cs:__imp_SysFreeString
0x1800387c3  test    r15, r15
0x1800387c6  jz      short loc_1800387D1
0x1800387c8  mov     rcx, r15; bstrString
0x1800387cb  call    cs:__imp_SysFreeString
0x1800387d1  test    rsi, rsi
0x1800387d4  jz      short loc_1800387DF
0x1800387d6  mov     rcx, rsi; bstrString
0x1800387d9  call    cs:__imp_SysFreeString
0x1800387df  test    rdi, rdi
0x1800387e2  jz      short loc_1800387ED
0x1800387e4  mov     rcx, rdi; bstrString
0x1800387e7  call    cs:__imp_SysFreeString
0x1800387ed  mov     eax, ebx
0x1800387ef  mov     rbx, [rsp+70h+arg_8]
0x1800387f7  add     rsp, 70h
0x1800387fb  pop     r15
0x1800387fd  pop     r14
0x1800387ff  pop     r13
0x180038801  pop     r12
0x180038803  pop     rdi
0x180038804  pop     rsi
0x180038805  pop     rbp
0x180038806  retn
```
