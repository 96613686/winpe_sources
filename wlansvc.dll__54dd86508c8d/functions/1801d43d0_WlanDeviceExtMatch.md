# WlanDeviceExtMatch

- ea: `0x1801d43d0`
- end: `0x1801d47aa`
- name: `WlanDeviceExtMatch`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801d47b0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18003fda0`
- `0x180106340`
- `0x1801d3ff8`
- `0x1801d4144`
- `0x1801d43d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d4479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d45a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d45a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d46ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d4720`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d46ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d4720`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1801d446a`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1801d446a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d4519`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d4659`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d46b3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d4519`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d4659`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d46b3`

## string_xrefs

- `0x1801d45fb`: `ExtensibilityDLL`
- `0x1801d459c`: `Ndi\IHVExtensions`
- `0x1801d468d`: `DiagnosticsID`
- `0x1801d463c`: `UIExtensibilityCLSID`

## pseudocode

```c
__int64 __fastcall WlanDeviceExtMatch(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, _DWORD *a5)
{
  HKEY v9; // rsi
  DWORD LastError; // eax
  unsigned int RegistryString; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  _BYTE *v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rax
  char v19; // al
  HKEY v20; // rcx
  _BYTE *v21; // rbx
  unsigned int v22; // eax
  HKEY hKey; // [rsp+30h] [rbp-61h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-41h] BYREF

  pclsid = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids);
  }
  v9 = (HKEY)DevObjOpenDevRegKey(a1, a2, 1);
  if ( v9 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (LastError = GetLastError(), (RegistryString = LastError) == 0) )
  {
    RegistryString = ReadRegistryString(v9, L"NetCfgInstanceId", 0x4Eu, sz);
    if ( !RegistryString )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, sz);
      }
      RegistryString = CLSIDFromString(sz, &pclsid);
      if ( RegistryString )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids,
            RegistryString);
        }
      }
      else
      {
        v14 = *(_QWORD *)&pclsid.Data1 - *a3;
        if ( *(_QWORD *)&pclsid.Data1 == *a3 )
          v14 = *(_QWORD *)pclsid.Data4 - a3[1];
        if ( v14 )
        {
          *a5 = 0;
        }
        else
        {
          *a5 = 1;
          v15 = RegOpenKeyExW(v9, L"Ndi\\IHVExtensions", 0, 0x20019u, &hKey);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v15);
            }
            RegistryString = 0;
          }
          else
          {
            *(_DWORD *)a4 = ReadRegistryString(hKey, L"ExtensibilityDLL", 0x208u, (LPWSTR)(a4 + 8)) == 0;
            ReadRegistryString(hKey, L"GroupName", 0x208u, (LPWSTR)(a4 + 528));
            ReadRegistryString(hKey, L"UIExtensibilityCLSID", 0x4Eu, sz);
            v16 = (_BYTE *)(a4 + 1048);
            v17 = 16;
            if ( CLSIDFromString(sz, (LPCLSID)(a4 + 1048)) )
            {
              v18 = 16;
              do
              {
                *v16++ = 0;
                --v18;
              }
              while ( v18 );
            }
            ReadRegistryNumber(hKey);
            v19 = *(_BYTE *)(a4 + 6);
            *(_BYTE *)(a4 + 6) = *(_BYTE *)(a4 + 4);
            v20 = hKey;
            *(_BYTE *)(a4 + 4) = v19;
            ReadRegistryString(v20, L"DiagnosticsID", 0x4Eu, sz);
            v21 = (_BYTE *)(a4 + 1064);
            if ( CLSIDFromString(sz, (LPCLSID)(a4 + 1064)) )
            {
              do
              {
                *v21++ = 0;
                --v17;
              }
              while ( v17 );
            }
            RegistryString = 0;
            v22 = RegCloseKey(hKey);
            if ( v22
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v22);
            }
          }
        }
      }
    }
    LastError = RegCloseKey(v9);
    if ( !LastError )
      goto LABEL_47;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return RegistryString;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_48;
    v13 = 26;
LABEL_46:
    WPP_SF_d(v12[2], v13, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, LastError);
LABEL_47:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return RegistryString;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 21;
    goto LABEL_46;
  }
LABEL_48:
  if ( v12 != &WPP_GLOBAL_Control && *((_BYTE *)v12 + 25) >= 4u && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_d(v12[2], 27, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, RegistryString);
  return RegistryString;
}

```

## disassembly

```asm
0x1801d43d0  push    rbp
0x1801d43d2  push    rbx
0x1801d43d3  push    rsi
0x1801d43d4  push    rdi
0x1801d43d5  push    r12
0x1801d43d7  push    r14
0x1801d43d9  push    r15
0x1801d43db  lea     rbp, [rsp-1Fh]
0x1801d43e0  sub     rsp, 0B0h
0x1801d43e7  mov     rax, cs:__security_cookie
0x1801d43ee  xor     rax, rsp
0x1801d43f1  mov     [rbp+4Fh+var_40], rax
0x1801d43f5  mov     r14, [rbp+4Fh+arg_20]
0x1801d43f9  xorps   xmm0, xmm0
0x1801d43fc  movups  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x1801d4400  mov     r15, r9
0x1801d4403  mov     [rbp+4Fh+hKey], 0FFFFFFFFFFFFFFFFh
0x1801d440b  mov     rdi, r8
0x1801d440e  mov     rsi, rdx
0x1801d4411  mov     rbx, rcx
0x1801d4414  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d441b  lea     rax, WPP_GLOBAL_Control
0x1801d4422  mov     r12d, 1
0x1801d4428  cmp     rcx, rax
0x1801d442b  jz      short loc_1801D444E
0x1801d442d  cmp     byte ptr [rcx+19h], 4
0x1801d4431  jb      short loc_1801D444E
0x1801d4433  test    [rcx+1Ch], r12b
0x1801d4437  jz      short loc_1801D444E
0x1801d4439  mov     rcx, [rcx+10h]
0x1801d443d  lea     edx, [r12+13h]
0x1801d4442  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d4449  call    WPP_SF_
0x1801d444e  mov     [rsp+0E0h+var_B8], 20019h
0x1801d4456  xor     r9d, r9d
0x1801d4459  mov     r8d, r12d
0x1801d445c  mov     dword ptr [rsp+0E0h+phkResult], 2
0x1801d4464  mov     rdx, rsi
0x1801d4467  mov     rcx, rbx
0x1801d446a  call    cs:__imp_DevObjOpenDevRegKey
0x1801d4470  mov     rsi, rax
0x1801d4473  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d4477  jnz     short loc_1801D44B8
0x1801d4479  call    cs:__imp_GetLastError
0x1801d447f  mov     ebx, eax
0x1801d4481  test    eax, eax
0x1801d4483  jz      short loc_1801D44B8
0x1801d4485  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d448c  lea     rdi, WPP_GLOBAL_Control
0x1801d4493  cmp     rcx, rdi
0x1801d4496  jz      loc_1801D478A
0x1801d449c  cmp     [rcx+19h], r12b
0x1801d44a0  jb      loc_1801D4761
0x1801d44a6  test    [rcx+1Ch], r12b
0x1801d44aa  jz      loc_1801D4761
0x1801d44b0  lea     edx, [rsi+16h]
0x1801d44b3  jmp     loc_1801D4747
0x1801d44b8  lea     r9, [rbp+4Fh+sz]; lpDst
0x1801d44bc  mov     r8d, 4Eh ; 'N'; dwBytes
0x1801d44c2  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x1801d44c9  mov     rcx, rsi; hKey
0x1801d44cc  call    ReadRegistryString
0x1801d44d1  mov     ebx, eax
0x1801d44d3  test    eax, eax
0x1801d44d5  jnz     loc_1801D4716
0x1801d44db  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d44e2  lea     rax, WPP_GLOBAL_Control
0x1801d44e9  cmp     rcx, rax
0x1801d44ec  jz      short loc_1801D4511
0x1801d44ee  cmp     byte ptr [rcx+19h], 4
0x1801d44f2  jb      short loc_1801D4511
0x1801d44f4  test    [rcx+1Ch], r12b
0x1801d44f8  jz      short loc_1801D4511
0x1801d44fa  mov     rcx, [rcx+10h]
0x1801d44fe  lea     edx, [rbx+16h]
0x1801d4501  lea     r9, [rbp+4Fh+sz]
0x1801d4505  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d450c  call    WPP_SF_S
0x1801d4511  lea     rdx, [rbp+4Fh+pclsid]; pclsid
0x1801d4515  lea     rcx, [rbp+4Fh+sz]; lpsz
0x1801d4519  call    cs:__imp_CLSIDFromString
0x1801d451f  mov     ebx, eax
0x1801d4521  test    eax, eax
0x1801d4523  jz      short loc_1801D456D
0x1801d4525  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d452c  lea     rax, WPP_GLOBAL_Control
0x1801d4533  cmp     rcx, rax
0x1801d4536  jz      loc_1801D4716
0x1801d453c  cmp     [rcx+19h], r12b
0x1801d4540  jb      loc_1801D4716
0x1801d4546  test    [rcx+1Ch], r12b
0x1801d454a  jz      loc_1801D4716
0x1801d4550  mov     rcx, [rcx+10h]
0x1801d4554  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d455b  mov     edx, 17h
0x1801d4560  mov     r9d, ebx
0x1801d4563  call    WPP_SF_d
0x1801d4568  jmp     loc_1801D4716
0x1801d456d  mov     rax, qword ptr [rbp+4Fh+pclsid.Data1]
0x1801d4571  sub     rax, [rdi]
0x1801d4574  jnz     short loc_1801D457E
0x1801d4576  mov     rax, qword ptr [rbp+4Fh+pclsid.Data4]
0x1801d457a  sub     rax, [rdi+8]
0x1801d457e  test    rax, rax
0x1801d4581  jnz     loc_1801D470F
0x1801d4587  lea     rax, [rbp+4Fh+hKey]
0x1801d458b  mov     [r14], r12d
0x1801d458e  mov     r9d, 20019h; samDesired
0x1801d4594  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1801d4599  xor     r8d, r8d; ulOptions
0x1801d459c  lea     rdx, aNdiIhvextensio; "Ndi\\IHVExtensions"
0x1801d45a3  mov     rcx, rsi; hKey
0x1801d45a6  call    cs:__imp_RegOpenKeyExW
0x1801d45ac  test    eax, eax
0x1801d45ae  jz      short loc_1801D45EE
0x1801d45b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d45b7  lea     rdi, WPP_GLOBAL_Control
0x1801d45be  cmp     rcx, rdi
0x1801d45c1  jz      short loc_1801D45E7
0x1801d45c3  cmp     byte ptr [rcx+19h], 4
0x1801d45c7  jb      short loc_1801D45E7
0x1801d45c9  test    [rcx+1Ch], r12b
0x1801d45cd  jz      short loc_1801D45E7
0x1801d45cf  mov     rcx, [rcx+10h]
0x1801d45d3  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d45da  mov     edx, 18h
0x1801d45df  mov     r9d, eax
0x1801d45e2  call    WPP_SF_d
0x1801d45e7  xor     ebx, ebx
0x1801d45e9  jmp     loc_1801D471D
0x1801d45ee  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d45f2  lea     r9, [r15+8]; lpDst
0x1801d45f6  mov     ebx, 208h
0x1801d45fb  lea     rdx, aExtensibilityd; "ExtensibilityDLL"
0x1801d4602  mov     r8d, ebx; dwBytes
0x1801d4605  call    ReadRegistryString
0x1801d460a  xor     ecx, ecx
0x1801d460c  lea     r9, [r15+210h]; lpDst
0x1801d4613  test    eax, eax
0x1801d4615  lea     rdx, aGroupname; "GroupName"
0x1801d461c  mov     r8d, ebx; dwBytes
0x1801d461f  setz    cl
0x1801d4622  mov     [r15], ecx
0x1801d4625  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d4629  call    ReadRegistryString
0x1801d462e  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d4632  lea     r9, [rbp+4Fh+sz]; lpDst
0x1801d4636  mov     r14d, 4Eh ; 'N'
0x1801d463c  lea     rdx, aUiextensibilit; "UIExtensibilityCLSID"
0x1801d4643  mov     r8d, r14d; dwBytes
0x1801d4646  call    ReadRegistryString
0x1801d464b  lea     rbx, [r15+418h]
0x1801d4652  mov     rdx, rbx; pclsid
0x1801d4655  lea     rcx, [rbp+4Fh+sz]; lpsz
0x1801d4659  call    cs:__imp_CLSIDFromString
0x1801d465f  lea     edi, [r14-3Eh]
0x1801d4663  test    eax, eax
0x1801d4665  jz      short loc_1801D4674
0x1801d4667  mov     eax, edi
0x1801d4669  mov     byte ptr [rbx], 0
0x1801d466c  add     rbx, r12
0x1801d466f  sub     rax, r12
0x1801d4672  jnz     short loc_1801D4669
0x1801d4674  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d4678  lea     rbx, [r15+4]
0x1801d467c  mov     r8, rbx
0x1801d467f  call    ReadRegistryNumber
0x1801d4684  mov     cl, [rbx]
0x1801d4686  lea     r9, [rbp+4Fh+sz]; lpDst
0x1801d468a  mov     al, [rbx+2]
0x1801d468d  lea     rdx, aDiagnosticsid; "DiagnosticsID"
0x1801d4694  mov     [rbx+2], cl
0x1801d4697  mov     r8d, r14d; dwBytes
0x1801d469a  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d469e  mov     [rbx], al
0x1801d46a0  call    ReadRegistryString
0x1801d46a5  lea     rbx, [r15+428h]
0x1801d46ac  mov     rdx, rbx; pclsid
0x1801d46af  lea     rcx, [rbp+4Fh+sz]; lpsz
0x1801d46b3  call    cs:__imp_CLSIDFromString
0x1801d46b9  test    eax, eax
0x1801d46bb  jz      short loc_1801D46C8
0x1801d46bd  mov     byte ptr [rbx], 0
0x1801d46c0  add     rbx, r12
0x1801d46c3  sub     rdi, r12
0x1801d46c6  jnz     short loc_1801D46BD
0x1801d46c8  xor     ebx, ebx
0x1801d46ca  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1801d46ce  call    cs:__imp_RegCloseKey
0x1801d46d4  test    eax, eax
0x1801d46d6  jz      short loc_1801D4716
0x1801d46d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d46df  lea     rdi, WPP_GLOBAL_Control
0x1801d46e6  cmp     rcx, rdi
0x1801d46e9  jz      short loc_1801D471D
0x1801d46eb  cmp     byte ptr [rcx+19h], 3
0x1801d46ef  jb      short loc_1801D471D
0x1801d46f1  test    [rcx+1Ch], r12b
0x1801d46f5  jz      short loc_1801D471D
0x1801d46f7  mov     rcx, [rcx+10h]
0x1801d46fb  lea     edx, [rbx+19h]
0x1801d46fe  mov     r9d, eax
0x1801d4701  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d4708  call    WPP_SF_d
0x1801d470d  jmp     short loc_1801D471D
0x1801d470f  mov     dword ptr [r14], 0
0x1801d4716  lea     rdi, WPP_GLOBAL_Control
0x1801d471d  mov     rcx, rsi; hKey
0x1801d4720  call    cs:__imp_RegCloseKey
0x1801d4726  test    eax, eax
0x1801d4728  jz      short loc_1801D475A
0x1801d472a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4731  cmp     rcx, rdi
0x1801d4734  jz      short loc_1801D478A
0x1801d4736  cmp     byte ptr [rcx+19h], 3
0x1801d473a  jb      short loc_1801D4761
0x1801d473c  test    [rcx+1Ch], r12b
0x1801d4740  jz      short loc_1801D4761
0x1801d4742  mov     edx, 1Ah
0x1801d4747  mov     rcx, [rcx+10h]
0x1801d474b  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d4752  mov     r9d, eax
0x1801d4755  call    WPP_SF_d
0x1801d475a  mov     rcx, cs:WPP_GLOBAL_Control
0x1801d4761  cmp     rcx, rdi
0x1801d4764  jz      short loc_1801D478A
0x1801d4766  cmp     byte ptr [rcx+19h], 4
0x1801d476a  jb      short loc_1801D478A
0x1801d476c  test    [rcx+1Ch], r12b
0x1801d4770  jz      short loc_1801D478A
0x1801d4772  mov     rcx, [rcx+10h]
0x1801d4776  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x1801d477d  mov     edx, 1Bh
0x1801d4782  mov     r9d, ebx
0x1801d4785  call    WPP_SF_d
0x1801d478a  mov     eax, ebx
0x1801d478c  mov     rcx, [rbp+4Fh+var_40]
0x1801d4790  xor     rcx, rsp; StackCookie
0x1801d4793  call    __security_check_cookie
0x1801d4798  add     rsp, 0B0h
0x1801d479f  pop     r15
0x1801d47a1  pop     r14
0x1801d47a3  pop     r12
0x1801d47a5  pop     rdi
0x1801d47a6  pop     rsi
0x1801d47a7  pop     rbx
0x1801d47a8  pop     rbp
0x1801d47a9  retn
```
