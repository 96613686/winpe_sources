# ShellMRTHelper::MRTHelperBase::InitializeMRTObjects(void)

- ea: `0x180048424`
- end: `0x18004880a`
- name: `?InitializeMRTObjects@MRTHelperBase@ShellMRTHelper@@AEAAJXZ`
- size: `998`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047c60`

## callees

- `0x180044668`
- `0x180048424`
- `0x18006c944`
- `0x1800e2d14`
- `0x1800e34bc`
- `0x1800e3810`
- `0x18011d690`
- `0x18015cb00`
- `0x1804684f0`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004860c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004860c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180048667`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180048667`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048490`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180048490`

## string_xrefs

- `0x180048584`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1800485a2`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x18004867a`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180048764`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1800487c7`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellMRTHelper::MRTHelperBase::InitializeMRTObjects(
        LPVOID *ppv,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  LPVOID *v5; // r15
  HRESULT Instance; // ebx
  __int64 result; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, GUID *, LPVOID *); // rbx
  LPVOID *v11; // r14
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, GUID *, LPVOID *); // rbx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rdx
  PCWSTR *v18; // rbx
  unsigned __int64 v19; // rcx
  HRESULT v20; // eax
  int v21; // eax
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // r8
  int v26; // ecx
  const wchar_t *v27; // r8
  int v28; // ecx
  const wchar_t *v29; // rdx
  int ppva; // [rsp+20h] [rbp-48h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-38h] BYREF
  __int64 v32; // [rsp+38h] [rbp-30h]
  __int64 v33; // [rsp+40h] [rbp-28h]
  WCHAR String2[8]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v5 = ppv + 1;
  if ( !ppv[1] )
  {
    if ( !*((_BYTE *)ppv + 45) && !*((_BYTE *)ppv + 46) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x8E,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
        a4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv);
    Instance = CoCreateInstance(
                 &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                 0,
                 1u,
                 &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                 ppv);
    if ( Instance < 0 )
    {
      v17 = 144;
      goto LABEL_21;
    }
    if ( *((_BYTE *)ppv + 45) )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(*(_QWORD *)*ppv + 40LL))(*ppv, ppv[6]);
    }
    else
    {
      wcscpy(String2, L".pri");
      v18 = (PCWSTR *)(ppv + 9);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_EnsureCount(ppv + 9);
      v19 = (unsigned __int64)ppv[10];
      if ( v19 <= 4 || CompareStringOrdinal(&(*v18)[v19 - 4], 4, String2, 4, 1) != 2 )
      {
        ppszPathOut = 0;
        v32 = 0;
        v33 = 0;
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(&ppszPathOut);
        v32 = -1;
        v33 = -1;
        v20 = PathAllocCombine(*v18, L"resources.pri", 0, &ppszPathOut);
        Instance = v20;
        if ( v20 >= 0 )
        {
          v21 = (*(__int64 (__fastcall **)(_QWORD, PWSTR))(*(_QWORD *)*ppv + 48LL))(*ppv, ppszPathOut);
          if ( v21 >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(&ppszPathOut);
            goto LABEL_9;
          }
          Instance = v21;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA5,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v20,
            ppva);
        }
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(&ppszPathOut);
        return (unsigned int)Instance;
      }
      result = (*(__int64 (__fastcall **)(_QWORD, PCWSTR))(*(_QWORD *)*ppv + 48LL))(*ppv, *v18);
    }
    if ( (int)result < 0 )
      return result;
LABEL_9:
    v9 = (__int64)*ppv;
    v10 = *(__int64 (__fastcall **)(__int64, GUID *, LPVOID *))(*(_QWORD *)*ppv + 72LL);
    v11 = ppv + 2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv + 2);
    Instance = v10(v9, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, ppv + 2);
    if ( Instance < 0 )
    {
      v17 = 169;
    }
    else
    {
      v12 = (__int64)*ppv;
      v13 = *(__int64 (__fastcall **)(__int64, GUID *, LPVOID *))(*(_QWORD *)*ppv + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5);
      Instance = v13(v12, &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, v5);
      if ( Instance >= 0 )
      {
        if ( !*((_WORD *)ppv + 21) )
          goto LABEL_12;
        v22 = *(_QWORD *)*v11;
        if ( *((_BYTE *)ppv + 43) )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(v22 + 112))(*v11, *((unsigned __int16 *)ppv + 20));
          if ( Instance < 0 )
          {
            v17 = 176;
            goto LABEL_21;
          }
        }
        else
        {
          v23 = ShellMRTHelper::Common::ScaleFactorToResourceScale(*((unsigned int *)ppv + 6), v14, *v11, v22);
          Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(v24 + 120))(v25, v23);
          if ( Instance < 0 )
          {
            v17 = 180;
            goto LABEL_21;
          }
        }
LABEL_12:
        if ( *((_BYTE *)ppv + 44) )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*v11 + 128LL))(
                       *v11,
                       *((unsigned int *)ppv + 7));
          if ( Instance < 0 )
          {
            v17 = 186;
            goto LABEL_21;
          }
        }
        v15 = *((_DWORD *)ppv + 8);
        if ( v15 )
        {
          v26 = v15 - 1;
          if ( v26 )
          {
            if ( v26 != 1 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xCA,
                (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
                (const char *)0x8000FFFFLL,
                ppva);
            v27 = L"light";
          }
          else
          {
            v27 = L"dark";
          }
          Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *))(*(_QWORD *)*v11 + 144LL))(
                       *v11,
                       L"Theme",
                       v27);
          if ( Instance < 0 )
          {
            v17 = 207;
            goto LABEL_21;
          }
        }
        v16 = *((_DWORD *)ppv + 9);
        if ( v16 )
        {
          v28 = v16 - 1;
          if ( v28 )
          {
            if ( v28 != 1 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xE0,
                (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
                (const char *)0x8000FFFFLL,
                ppva);
            v29 = L"lightunplated";
          }
          else
          {
            v29 = L"unplated";
          }
          Instance = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)*v11 + 136LL))(*v11, v29);
          if ( Instance < 0 )
          {
            v17 = 229;
            goto LABEL_21;
          }
        }
        return 0;
      }
      v17 = 170;
    }
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    return (unsigned int)Instance;
  }
  return 0;
}

```

## disassembly

```asm
0x180048424  push    rbp
0x180048426  push    rbx
0x180048427  push    rsi
0x180048428  push    rdi
0x180048429  push    r14
0x18004842b  push    r15
0x18004842d  mov     rbp, rsp
0x180048430  sub     rsp, 68h
0x180048434  mov     rax, cs:__security_cookie
0x18004843b  xor     rax, rsp
0x18004843e  mov     [rbp+var_10], rax
0x180048442  mov     rsi, rcx
0x180048445  lea     r15, [rcx+8]
0x180048449  cmp     qword ptr [r15], 0
0x18004844d  jnz     loc_180048557
0x180048453  mov     edi, 1
0x180048458  cmp     byte ptr [rcx+2Dh], 0
0x18004845c  jz      loc_180048572
0x180048462  xor     al, al
0x180048464  mov     rcx, [rbp+30h]; this
0x180048468  test    al, al
0x18004846a  jnz     loc_180048584
0x180048470  mov     rcx, rsi
0x180048473  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048478  mov     qword ptr [rsp+68h+ppv], rsi; int
0x18004847d  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180048484  mov     r8d, edi; dwClsContext
0x180048487  xor     edx, edx; pUnkOuter
0x180048489  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x180048490  call    cs:__imp_CoCreateInstance
0x180048496  mov     ebx, eax
0x180048498  test    eax, eax
0x18004849a  js      loc_180048596
0x1800484a0  cmp     byte ptr [rsi+2Dh], 0
0x1800484a4  jz      loc_1800485C6
0x1800484aa  mov     rcx, [rsi]
0x1800484ad  mov     rax, [rcx]
0x1800484b0  mov     rdx, [rsi+30h]
0x1800484b4  mov     rax, [rax+28h]
0x1800484b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484bd  test    eax, eax
0x1800484bf  js      loc_180048559
0x1800484c5  mov     rdi, [rsi]
0x1800484c8  mov     rax, [rdi]
0x1800484cb  mov     rbx, [rax+48h]
0x1800484cf  lea     r14, [rsi+10h]
0x1800484d3  mov     rcx, r14
0x1800484d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800484db  mov     r8, r14
0x1800484de  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x1800484e5  mov     rcx, rdi
0x1800484e8  mov     rax, rbx
0x1800484eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484f0  mov     ebx, eax
0x1800484f2  test    eax, eax
0x1800484f4  js      loc_1800486B9
0x1800484fa  mov     rdi, [rsi]
0x1800484fd  mov     rax, [rdi]
0x180048500  mov     rbx, [rax+38h]
0x180048504  mov     rcx, r15
0x180048507  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004850c  mov     r8, r15
0x18004850f  lea     rdx, _GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd
0x180048516  mov     rcx, rdi
0x180048519  mov     rax, rbx
0x18004851c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048521  mov     ebx, eax
0x180048523  test    eax, eax
0x180048525  js      loc_1800486C3
0x18004852b  mov     al, [rsi+2Bh]
0x18004852e  or      al, [rsi+2Ah]
0x180048531  jnz     loc_1800486CD
0x180048537  cmp     byte ptr [rsi+2Ch], 0
0x18004853b  jnz     loc_180048727
0x180048541  mov     ecx, [rsi+20h]
0x180048544  test    ecx, ecx
0x180048546  jnz     loc_180048750
0x18004854c  mov     ecx, [rsi+24h]
0x18004854f  test    ecx, ecx
0x180048551  jnz     loc_1800487B3
0x180048557  xor     eax, eax
0x180048559  mov     rcx, [rbp+var_10]
0x18004855d  xor     rcx, rsp; StackCookie
0x180048560  call    __security_check_cookie
0x180048565  add     rsp, 68h
0x180048569  pop     r15
0x18004856b  pop     r14
0x18004856d  pop     rdi
0x18004856e  pop     rsi
0x18004856f  pop     rbx
0x180048570  pop     rbp
0x180048571  retn
0x180048572  cmp     byte ptr [rcx+2Eh], 0
0x180048576  jnz     loc_180048462
0x18004857c  mov     al, dil
0x18004857f  jmp     loc_180048464
0x180048584  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18004858b  mov     edx, 8Eh; void *
0x180048590  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180048596  mov     edx, 90h
0x18004859b  jmp     short loc_1800485A2
0x18004859d  mov     edx, 0E5h; void *
0x1800485a2  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800485a9  mov     r9d, ebx; char *
0x1800485ac  mov     rcx, [rbp+30h]; this
0x1800485b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800485b5  jmp     short loc_1800485C2
0x1800485b7  mov     ebx, eax
0x1800485b9  lea     rcx, [rbp+ppszPathOut]
0x1800485bd  call    ?_Free@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(void)
0x1800485c2  mov     eax, ebx
0x1800485c4  jmp     short loc_180048559
0x1800485c6  mov     dword ptr [rbp+String2], 70002Eh
0x1800485cd  mov     [rbp+var_1C], 690072h
0x1800485d4  xor     eax, eax
0x1800485d6  mov     [rbp+var_18], ax
0x1800485da  lea     rbx, [rsi+48h]
0x1800485de  mov     rcx, rbx
0x1800485e1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<wchar_t>>::_EnsureCount(void)
0x1800485e6  mov     rcx, [rbx+8]
0x1800485ea  cmp     rcx, 4
0x1800485ee  jbe     short loc_180048629
0x1800485f0  mov     rax, [rbx]
0x1800485f3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800485f7  lea     rcx, [rax+rcx*2]; lpString1
0x1800485fb  mov     [rsp+68h+ppv], edi; bIgnoreCase
0x1800485ff  mov     r9d, 4; cchCount2
0x180048605  lea     r8, [rbp+String2]; lpString2
0x180048609  mov     edx, r9d; cchCount1
0x18004860c  call    cs:__imp_CompareStringOrdinal
0x180048612  cmp     eax, 2
0x180048615  jnz     short loc_180048629
0x180048617  mov     rcx, [rsi]
0x18004861a  mov     rax, [rcx]
0x18004861d  mov     rdx, [rbx]
0x180048620  mov     rax, [rax+30h]
0x180048624  jmp     loc_1800484B8
0x180048629  mov     [rbp+ppszPathOut], 0
0x180048631  mov     [rbp+var_30], 0
0x180048639  mov     [rbp+var_28], 0
0x180048641  lea     rcx, [rbp+ppszPathOut]
0x180048645  call    ?_Free@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(void)
0x18004864a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004864e  mov     [rbp+var_30], rax
0x180048652  mov     [rbp+var_28], rax
0x180048656  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18004865a  xor     r8d, r8d; dwFlags
0x18004865d  lea     rdx, pszMore; "resources.pri"
0x180048664  mov     rcx, [rbx]; pszPathIn
0x180048667  call    cs:__imp_PathAllocCombine
0x18004866d  mov     ebx, eax
0x18004866f  test    eax, eax
0x180048671  jns     short loc_180048690
0x180048673  mov     rcx, [rbp+30h]; this
0x180048677  mov     r9d, eax; char *
0x18004867a  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x180048681  mov     edx, 0A5h; void *
0x180048686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004868b  jmp     loc_1800485B9
0x180048690  mov     rcx, [rsi]
0x180048693  mov     rax, [rcx]
0x180048696  mov     rdx, [rbp+ppszPathOut]
0x18004869a  mov     rax, [rax+30h]
0x18004869e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486a3  test    eax, eax
0x1800486a5  js      loc_1800485B7
0x1800486ab  lea     rcx, [rbp+ppszPathOut]
0x1800486af  call    ?_Free@?$NativeString@V?$LocalMemPolicy@_W@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<wchar_t>>::_Free(void)
0x1800486b4  jmp     loc_1800484C5
0x1800486b9  mov     edx, 0A9h
0x1800486be  jmp     loc_1800485A2
0x1800486c3  mov     edx, 0AAh
0x1800486c8  jmp     loc_1800485A2
0x1800486cd  mov     r8, [r14]
0x1800486d0  mov     r9, [r8]
0x1800486d3  cmp     byte ptr [rsi+2Bh], 0
0x1800486d7  jz      short loc_1800486FD
0x1800486d9  movzx   edx, word ptr [rsi+28h]
0x1800486dd  mov     rcx, r8
0x1800486e0  mov     rax, [r9+70h]
0x1800486e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486e9  mov     ebx, eax
0x1800486eb  test    eax, eax
0x1800486ed  jns     loc_180048537
0x1800486f3  mov     edx, 0B0h
0x1800486f8  jmp     loc_1800485A2
0x1800486fd  mov     ecx, [rsi+18h]
0x180048700  call    ?ScaleFactorToResourceScale@Common@ShellMRTHelper@@YA?AW4RESOURCE_SCALE@@W4DEVICE_SCALE_FACTOR@@@Z; ShellMRTHelper::Common::ScaleFactorToResourceScale(DEVICE_SCALE_FACTOR)
0x180048705  mov     edx, eax
0x180048707  mov     rcx, r8
0x18004870a  mov     rax, [r9+78h]
0x18004870e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048713  mov     ebx, eax
0x180048715  test    eax, eax
0x180048717  jns     loc_180048537
0x18004871d  mov     edx, 0B4h
0x180048722  jmp     loc_1800485A2
0x180048727  mov     rcx, [r14]
0x18004872a  mov     rax, [rcx]
0x18004872d  mov     edx, [rsi+1Ch]
0x180048730  mov     rax, [rax+80h]
0x180048737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004873c  mov     ebx, eax
0x18004873e  test    eax, eax
0x180048740  jns     loc_180048541
0x180048746  mov     edx, 0BAh
0x18004874b  jmp     loc_1800485A2
0x180048750  sub     ecx, 1
0x180048753  jz      short loc_18004877F
0x180048755  cmp     ecx, 1
0x180048758  jz      short loc_180048776
0x18004875a  mov     rcx, [rbp+30h]; this
0x18004875e  mov     r9d, 8000FFFFh; char *
0x180048764  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18004876b  mov     edx, 0CAh; void *
0x180048770  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180048776  lea     r8, aLight; "light"
0x18004877d  jmp     short loc_180048786
0x18004877f  lea     r8, aDark; "dark"
0x180048786  mov     rcx, [r14]
0x180048789  mov     rax, [rcx]
0x18004878c  lea     rdx, aTheme; "Theme"
0x180048793  mov     rax, [rax+90h]
0x18004879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004879f  mov     ebx, eax
0x1800487a1  test    eax, eax
0x1800487a3  jns     loc_18004854C
0x1800487a9  mov     edx, 0CFh
0x1800487ae  jmp     loc_1800485A2
0x1800487b3  sub     ecx, 1
0x1800487b6  jz      short loc_1800487E2
0x1800487b8  cmp     ecx, 1
0x1800487bb  jz      short loc_1800487D9
0x1800487bd  mov     rcx, [rbp+30h]; this
0x1800487c1  mov     r9d, 8000FFFFh; char *
0x1800487c7  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1800487ce  mov     edx, 0E0h; void *
0x1800487d3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800487d9  lea     rdx, aLightunplated; "lightunplated"
0x1800487e0  jmp     short loc_1800487E9
0x1800487e2  lea     rdx, aUnplated; "unplated"
0x1800487e9  mov     rcx, [r14]
0x1800487ec  mov     rax, [rcx]
0x1800487ef  mov     rax, [rax+88h]
0x1800487f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487fb  mov     ebx, eax
0x1800487fd  test    eax, eax
0x1800487ff  jns     loc_180048557
0x180048805  jmp     loc_18004859D
```
