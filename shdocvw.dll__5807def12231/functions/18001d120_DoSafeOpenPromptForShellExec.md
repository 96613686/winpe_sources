# DoSafeOpenPromptForShellExec

- ea: `0x18001d120`
- end: `0x18001d3a8`
- name: `DoSafeOpenPromptForShellExec`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004d30`

## callees

- `0x180003660`
- `0x180003fc0`
- `0x180006750`
- `0x1800067a0`
- `0x180008320`
- `0x180009298`
- `0x18001794c`
- `0x18001d120`
- `0x180029010`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x18001d276`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001d276`
- `SHLWAPI!AssocIsDangerous` at `0x18001d190`
- `SHLWAPI!AssocIsDangerous` at `0x18001d190`
- `SHLWAPI!PathFindExtensionW` at `0x18001d179`
- `SHLWAPI!PathFindExtensionW` at `0x18001d179`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d2bf`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d2bf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d1f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d1f1`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18001d257`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18001d257`

## string_xrefs

- `0x18001d1c6`: `Windows.Internal.Security.SmartScreen.AppReputationService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DoSafeOpenPromptForShellExec(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        IUnknown *a6)
{
  int v7; // esi
  LPWSTR ExtensionW; // rax
  LPWSTR v9; // rdi
  char v10; // r14
  char v11; // r15
  __int64 v12; // rbx
  int v13; // r12d
  char v14; // bl
  __int64 v15; // r8
  char v16; // r15
  char v17; // r12
  unsigned int v18; // eax
  unsigned int v19; // ebx
  _BYTE v21[4]; // [rsp+70h] [rbp-59h] BYREF
  int v22; // [rsp+74h] [rbp-55h] BYREF
  int v23; // [rsp+78h] [rbp-51h] BYREF
  void *ppvOut; // [rsp+80h] [rbp-49h] BYREF
  void *v25; // [rsp+88h] [rbp-41h] BYREF
  int v26; // [rsp+90h] [rbp-39h] BYREF
  IUnknown *punk; // [rsp+98h] [rbp-31h]
  __int64 v28; // [rsp+A0h] [rbp-29h]
  __int64 v29; // [rsp+A8h] [rbp-21h]
  __int64 v30; // [rsp+B0h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v32; // [rsp+D0h] [rbp+7h]

  LODWORD(ppvOut) = a4;
  v30 = a3;
  v29 = a1;
  v28 = a5;
  punk = a6;
  v7 = 1;
  if ( a2 )
  {
    ExtensionW = PathFindExtensionW(a2);
    v9 = ExtensionW;
    if ( ExtensionW && *ExtensionW && AssocIsDangerous(ExtensionW) )
    {
      v10 = 1;
      goto LABEL_8;
    }
  }
  else
  {
    v9 = 0;
  }
  v10 = 0;
LABEL_8:
  v26 = 0;
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v11 = 0;
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.SmartScreen.AppReputationService",
    0x3Bu,
    0x3Au);
  v12 = v32;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  if ( (int)RoGetActivationFactory(v12, &GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34, &v25) >= 0 )
  {
    v21[0] = 0;
    if ( (*(int (__fastcall **)(void *, int *, _BYTE *))(*(_QWORD *)v25 + 48LL))(v25, &v23, v21) < 0 )
    {
      v23 = 0;
    }
    else if ( (*(int (__fastcall **)(void *, int *, _BYTE *))(*(_QWORD *)v25 + 64LL))(v25, &v22, v21) < 0 )
    {
      v22 = 0;
    }
    else
    {
      v11 = 1;
    }
  }
  v13 = IsNightsWatchVAILOn();
  v14 = (unsigned __int8)IsQueryWin32SubsystemHostPresent() && (unsigned int)QueryWin32SubsystemHost() - 1 <= 1;
  if ( !v10 )
  {
    v19 = 0;
    goto LABEL_34;
  }
  if ( !PathIsNetworkPathW(a2) && v11 && (v23 || v22) )
  {
    if ( (_DWORD)ppvOut )
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(
             punk,
             (const GUID *const)&SID_ShouldShowCreateProcessUIUnderShellExecute,
             &GUID_00000000_0000_0000_c000_000000000046,
             &ppvOut) < 0 )
      {
LABEL_28:
        v16 = v13 != 0;
        v17 = v22;
        ppvOut = v25;
        if ( v25 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
        v18 = InvokeSmartScreen(
                v29,
                (_DWORD)a2,
                v30,
                v7,
                (char)punk,
                (char)v9,
                v10,
                (__int64)&ppvOut,
                v17,
                v16,
                v14,
                v28,
                (__int64)&v26);
        goto LABEL_32;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    if ( !v14 )
      v7 = 0;
    goto LABEL_28;
  }
  LOBYTE(v15) = v10;
  v18 = DisplayLegacyBlockUX(v29, a2, v15, v9, v28);
LABEL_32:
  v19 = v18;
LABEL_34:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  return v19;
}

```

## disassembly

```asm
0x18001d120  mov     [rsp-8+arg_18], rbx
0x18001d125  push    rbp
0x18001d126  push    rsi
0x18001d127  push    rdi
0x18001d128  push    r12
0x18001d12a  push    r13
0x18001d12c  push    r14
0x18001d12e  push    r15
0x18001d130  lea     rbp, [rsp-17h]
0x18001d135  sub     rsp, 0E0h
0x18001d13c  mov     rax, cs:__security_cookie
0x18001d143  xor     rax, rsp
0x18001d146  mov     [rbp+47h+var_38], rax
0x18001d14a  mov     dword ptr [rbp+47h+ppvOut], r9d
0x18001d14e  mov     [rbp+47h+var_60], r8
0x18001d152  mov     r13, rdx
0x18001d155  mov     [rbp+47h+var_68], rcx
0x18001d159  mov     rax, [rbp+47h+arg_20]
0x18001d15d  mov     [rbp+47h+var_70], rax
0x18001d161  mov     rax, [rbp+47h+arg_28]
0x18001d165  mov     [rbp+47h+punk], rax
0x18001d169  mov     esi, 1
0x18001d16e  xor     r12d, r12d
0x18001d171  test    rdx, rdx
0x18001d174  jz      short loc_18001D19F
0x18001d176  mov     rcx, rdx; pszPath
0x18001d179  call    cs:__imp_PathFindExtensionW
0x18001d17f  mov     rdi, rax
0x18001d182  test    rax, rax
0x18001d185  jz      short loc_18001D1A2
0x18001d187  cmp     [rax], r12w
0x18001d18b  jz      short loc_18001D1A2
0x18001d18d  mov     rcx, rax; pszAssoc
0x18001d190  call    cs:__imp_AssocIsDangerous
0x18001d196  test    eax, eax
0x18001d198  jz      short loc_18001D1A2
0x18001d19a  mov     r14b, sil
0x18001d19d  jmp     short loc_18001D1A5
0x18001d19f  mov     rdi, r12
0x18001d1a2  mov     r14b, r12b
0x18001d1a5  mov     [rbp+47h+var_80], r12d
0x18001d1a9  mov     [rbp+47h+var_88], r12
0x18001d1ad  mov     [rbp+47h+var_9C], r12d
0x18001d1b1  mov     [rbp+47h+var_98], r12d
0x18001d1b5  mov     r15b, r12b
0x18001d1b8  mov     [rbp+47h+var_40], r12
0x18001d1bc  mov     r9d, 3Ah ; ':'; unsigned int
0x18001d1c2  lea     r8d, [r9+1]; unsigned int
0x18001d1c6  lea     rdx, ?RuntimeClass_Windows_Internal_Security_SmartScreen_AppReputationService@@3QBGB; "Windows.Internal.Security.SmartScreen.A"...
0x18001d1cd  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x18001d1d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001d1d6  mov     rbx, [rbp+47h+var_40]
0x18001d1da  lea     rcx, [rbp+47h+var_88]
0x18001d1de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1e3  lea     r8, [rbp+47h+var_88]
0x18001d1e7  lea     rdx, _GUID_343baa78_e34f_466c_9ffa_81af5ce4cd34
0x18001d1ee  mov     rcx, rbx
0x18001d1f1  call    cs:__imp_RoGetActivationFactory
0x18001d1f7  test    eax, eax
0x18001d1f9  js      short loc_18001D246
0x18001d1fb  mov     [rbp+47h+var_A0], r12b
0x18001d1ff  mov     rcx, [rbp+47h+var_88]
0x18001d203  mov     rax, [rcx]
0x18001d206  lea     r8, [rbp+47h+var_A0]
0x18001d20a  lea     rdx, [rbp+47h+var_98]
0x18001d20e  mov     rax, [rax+30h]
0x18001d212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d217  test    eax, eax
0x18001d219  js      short loc_18001D242
0x18001d21b  mov     rcx, [rbp+47h+var_88]
0x18001d21f  mov     rax, [rcx]
0x18001d222  lea     r8, [rbp+47h+var_A0]
0x18001d226  lea     rdx, [rbp+47h+var_9C]
0x18001d22a  mov     rax, [rax+40h]
0x18001d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d233  test    eax, eax
0x18001d235  js      short loc_18001D23C
0x18001d237  mov     r15b, sil
0x18001d23a  jmp     short loc_18001D246
0x18001d23c  mov     [rbp+47h+var_9C], r12d
0x18001d240  jmp     short loc_18001D246
0x18001d242  mov     [rbp+47h+var_98], r12d
0x18001d246  call    IsNightsWatchVAILOn
0x18001d24b  mov     r12d, eax
0x18001d24e  call    IsQueryWin32SubsystemHostPresent
0x18001d253  test    al, al
0x18001d255  jz      short loc_18001D268
0x18001d257  call    cs:__imp_QueryWin32SubsystemHost
0x18001d25d  dec     eax
0x18001d25f  cmp     eax, esi
0x18001d261  ja      short loc_18001D268
0x18001d263  mov     bl, sil
0x18001d266  jmp     short loc_18001D26A
0x18001d268  xor     bl, bl
0x18001d26a  test    r14b, r14b
0x18001d26d  jz      loc_18001D374
0x18001d273  mov     rcx, r13; pszPath
0x18001d276  call    cs:__imp_PathIsNetworkPathW
0x18001d27c  test    eax, eax
0x18001d27e  jnz     loc_18001D355
0x18001d284  test    r15b, r15b
0x18001d287  jz      loc_18001D355
0x18001d28d  cmp     [rbp+47h+var_98], eax
0x18001d290  jnz     short loc_18001D29B
0x18001d292  cmp     [rbp+47h+var_9C], eax
0x18001d295  jz      loc_18001D355
0x18001d29b  cmp     dword ptr [rbp+47h+ppvOut], 0
0x18001d29f  jz      short loc_18001D2D9
0x18001d2a1  mov     [rbp+47h+ppvOut], 0
0x18001d2a9  lea     r9, [rbp+47h+ppvOut]; ppvOut
0x18001d2ad  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001d2b4  lea     rdx, SID_ShouldShowCreateProcessUIUnderShellExecute; guidService
0x18001d2bb  mov     rcx, [rbp+47h+punk]; punk
0x18001d2bf  call    cs:__imp_IUnknown_QueryService
0x18001d2c5  test    eax, eax
0x18001d2c7  js      short loc_18001D2DF
0x18001d2c9  mov     rcx, [rbp+47h+ppvOut]
0x18001d2cd  mov     rax, [rcx]
0x18001d2d0  mov     rax, [rax+10h]
0x18001d2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2d9  test    bl, bl
0x18001d2db  jnz     short loc_18001D2DF
0x18001d2dd  xor     esi, esi
0x18001d2df  test    r12d, r12d
0x18001d2e2  setnz   r15b
0x18001d2e6  mov     r12d, [rbp+47h+var_9C]
0x18001d2ea  mov     rcx, [rbp+47h+var_88]
0x18001d2ee  mov     [rbp+47h+ppvOut], rcx
0x18001d2f2  test    rcx, rcx
0x18001d2f5  jz      short loc_18001D304
0x18001d2f7  mov     rax, [rcx]
0x18001d2fa  mov     rax, [rax+8]
0x18001d2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d303  nop
0x18001d304  lea     rax, [rbp+47h+var_80]
0x18001d308  mov     [rsp+110h+var_B0], rax
0x18001d30d  mov     rax, [rbp+47h+var_70]
0x18001d311  mov     [rsp+110h+var_B8], rax
0x18001d316  mov     [rsp+110h+var_C0], bl
0x18001d31a  mov     [rsp+110h+var_C8], r15b
0x18001d31f  mov     [rsp+110h+var_D0], r12d
0x18001d324  lea     rax, [rbp+47h+ppvOut]
0x18001d328  mov     [rsp+110h+var_D8], rax
0x18001d32d  mov     [rsp+110h+var_E0], r14b
0x18001d332  mov     [rsp+110h+var_E8], rdi
0x18001d337  mov     rax, [rbp+47h+punk]
0x18001d33b  mov     [rsp+110h+var_F0], rax
0x18001d340  mov     r9d, esi
0x18001d343  mov     r8, [rbp+47h+var_60]
0x18001d347  mov     rdx, r13
0x18001d34a  mov     rcx, [rbp+47h+var_68]
0x18001d34e  call    ?InvokeSmartScreen@@YAKQEAUHWND__@@QEBG1HPEAUIUnknown@@1_NV?$ComPtr@UIAppReputationServiceStatics@SmartScreen@Security@Internal@Windows@@@WRL@Microsoft@@W4AppControlEnforcementLevel@SmartScreen@Security@Internal@Windows@@33AEAW4SafeOpenPromptExperienceResults@@AEAK@Z; InvokeSmartScreen(HWND__ * const,ushort const * const,ushort const * const,int,IUnknown *,ushort const * const,bool,Microsoft::WRL::ComPtr<Windows::Internal::Security::SmartScreen::IAppReputationServiceStatics>,Windows::Internal::Security::SmartScreen::AppControlEnforcementLevel,bool,bool,SafeOpenPromptExperienceResults &,ulong &)
0x18001d353  jmp     short loc_18001D370
0x18001d355  mov     rax, [rbp+47h+var_70]
0x18001d359  mov     [rsp+110h+var_F0], rax
0x18001d35e  mov     r9, rdi
0x18001d361  mov     r8b, r14b
0x18001d364  mov     rdx, r13
0x18001d367  mov     rcx, [rbp+47h+var_68]
0x18001d36b  call    DisplayLegacyBlockUX
0x18001d370  mov     ebx, eax
0x18001d372  jmp     short loc_18001D376
0x18001d374  xor     ebx, ebx
0x18001d376  lea     rcx, [rbp+47h+var_88]
0x18001d37a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d37f  mov     eax, ebx
0x18001d381  mov     rcx, [rbp+47h+var_38]
0x18001d385  xor     rcx, rsp; StackCookie
0x18001d388  call    __security_check_cookie
0x18001d38d  mov     rbx, [rsp+110h+arg_18]
0x18001d395  add     rsp, 0E0h
0x18001d39c  pop     r15
0x18001d39e  pop     r14
0x18001d3a0  pop     r13
0x18001d3a2  pop     r12
0x18001d3a4  pop     rdi
0x18001d3a5  pop     rsi
0x18001d3a6  pop     rbp
0x18001d3a7  retn
```
