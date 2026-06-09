# CAutoplayDialog::_UpdateConsent(IAutoplayHandler *)

- ea: `0x18010d400`
- end: `0x18010d731`
- name: `?_UpdateConsent@CAutoplayDialog@@AEAAJPEAUIAutoplayHandler@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(CAutoplayDialog *__hidden this, struct IAutoplayHandler *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18019078c`

## callees

- `0x18000b7e8`
- `0x1800150c0`
- `0x18010d400`
- `0x18013d330`
- `0x18013f43c`
- `0x18013f4a4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010d503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d6c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d6cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d6c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010d6cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d6da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010d6da`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18010d622`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18010d622`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010d658`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18010d658`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18010d4f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18010d4f9`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18010d6ba`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18010d6ba`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18010d5c2`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18010d5c2`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18010d4b2`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18010d4b2`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18010d4db`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x18010d4db`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::_UpdateConsent(CAutoplayDialog *this, struct IAutoplayHandler *a2, __int64 a3)
{
  __int64 v5; // rax
  int ObjectProperties; // ebx
  __int64 v7; // r8
  LONG v8; // eax
  signed int LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR packageFullName; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR *v20; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+84h] [rbp-7Ch]
  __int64 v24; // [rsp+88h] [rbp-78h]
  PSID Sid[2]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_TWINUI_PUBLISHER_Context, AutoPlay_Broker_Device_Start, a3, 1, Sid);
  v5 = *(_QWORD *)a2;
  packageFullName = 0;
  ObjectProperties = (*(__int64 (__fastcall **)(struct IAutoplayHandler *, PCWSTR *))(v5 + 200))(a2, &packageFullName);
  if ( ObjectProperties >= 0 && packageFullName && *packageFullName )
  {
    packageFamilyNameLength = 65;
    v8 = PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName);
    ObjectProperties = v8;
    if ( v8 > 0 )
      ObjectProperties = (unsigned __int16)v8 | 0x80070000;
    if ( ObjectProperties >= 0 )
    {
      Sid[0] = 0;
      ObjectProperties = AppContainerDeriveSidFromMoniker(packageFamilyName, Sid);
      if ( ObjectProperties >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          if ( dword_1804B6E18 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 4LL) )
          {
            Init_thread_header(&dword_1804B6E18);
            if ( dword_1804B6E18 == -1 )
            {
              *(DEVPROPKEY *)byte_1804B4F60 = DEVPKEY_DeviceInterface_ClassGuid;
              dword_1804B4F74 = 0;
              qword_1804B4F78 = 0;
              Init_thread_footer(&dword_1804B6E18);
            }
          }
          v10 = *((_QWORD *)this + 2);
          v14 = 0;
          v15 = 0;
          ObjectProperties = DevGetObjectProperties(1, v10, 0, 1, byte_1804B4F60, &v14, &v15);
          if ( ObjectProperties >= 0 )
          {
            v11 = v15;
            if ( v14 == 1 && *(_DWORD *)(v15 + 16) == 4 )
            {
              v12 = *(_QWORD *)v15 - *(_QWORD *)&DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1;
              if ( *(_QWORD *)v15 == *(_QWORD *)&DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1 )
                v12 = *(_QWORD *)(v15 + 8) - *(_QWORD *)DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data4;
              if ( !v12 && *(_DWORD *)(v15 + 32) == 13 )
              {
                if ( StringFromGUID2(*(const GUID *const *)(v15 + 40), sz, 39) )
                {
                  ppv = 0;
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
                  ObjectProperties = CoCreateInstance(
                                       &CLSID_DeviceAccessPolicyManager,
                                       0,
                                       1u,
                                       &GUID_02a175a2_f59b_4490_8008_da0592239633,
                                       &ppv);
                  if ( ObjectProperties >= 0 )
                  {
                    v20 = sz;
                    v22 = 0;
                    v23 = 0;
                    v24 = 1;
                    v21 = 0;
                    ObjectProperties = (*(__int64 (__fastcall **)(LPVOID, LPWSTR, OLECHAR **, __int64))(*(_QWORD *)ppv + 64LL))(
                                         ppv,
                                         StringSid,
                                         &v20,
                                         1);
                  }
                  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
                }
                else
                {
                  ObjectProperties = -2147418113;
                }
                v11 = v15;
              }
            }
            DevFreeObjectProperties(v14, v11);
          }
          LocalFree(StringSid);
        }
        else
        {
          LastError = GetLastError();
          ObjectProperties = LastError;
          if ( LastError > 0 )
            ObjectProperties = (unsigned __int16)LastError | 0x80070000;
        }
        LocalFree(Sid[0]);
      }
    }
    CoTaskMemFree((LPVOID)packageFullName);
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_TWINUI_PUBLISHER_Context, AutoPlay_Broker_Device_Stop, v7, 1, Sid);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x18010d400  mov     [rsp-8+arg_10], rbx
0x18010d405  mov     [rsp-8+arg_18], rsi
0x18010d40a  push    rbp
0x18010d40b  push    rdi
0x18010d40c  push    r14
0x18010d40e  lea     rbp, [rsp-90h]
0x18010d416  sub     rsp, 190h
0x18010d41d  mov     rax, cs:__security_cookie
0x18010d424  xor     rax, rsp
0x18010d427  mov     [rbp+0A0h+var_20], rax
0x18010d42e  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18010d435  mov     rbx, rdx
0x18010d438  mov     rdi, rcx
0x18010d43b  mov     r14d, 1
0x18010d441  jz      short loc_18010D462
0x18010d443  lea     rax, [rbp+0A0h+Sid]
0x18010d447  mov     r9d, r14d
0x18010d44a  lea     rdx, AutoPlay_Broker_Device_Start
0x18010d451  mov     [rsp+1A0h+ppv], rax
0x18010d456  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18010d45d  call    McGenEventWrite_EventWriteTransfer
0x18010d462  mov     rax, [rbx]
0x18010d465  lea     rdx, [rsp+1A0h+packageFullName]
0x18010d46a  xor     esi, esi
0x18010d46c  mov     rcx, rbx
0x18010d46f  mov     [rsp+1A0h+packageFullName], rsi
0x18010d474  mov     rax, [rax+0C8h]
0x18010d47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d480  mov     ebx, eax
0x18010d482  test    eax, eax
0x18010d484  js      loc_18010D6E0
0x18010d48a  mov     rcx, [rsp+1A0h+packageFullName]; packageFullName
0x18010d48f  test    rcx, rcx
0x18010d492  jz      loc_18010D6E0
0x18010d498  cmp     [rcx], si
0x18010d49b  jz      loc_18010D6E0
0x18010d4a1  lea     r8, [rbp+0A0h+packageFamilyName]; packageFamilyName
0x18010d4a5  mov     [rsp+1A0h+packageFamilyNameLength], 41h ; 'A'
0x18010d4ad  lea     rdx, [rsp+1A0h+packageFamilyNameLength]; packageFamilyNameLength
0x18010d4b2  call    cs:__imp_PackageFamilyNameFromFullName
0x18010d4b8  mov     ebx, eax
0x18010d4ba  test    eax, eax
0x18010d4bc  jle     short loc_18010D4C7
0x18010d4be  movzx   ebx, ax
0x18010d4c1  or      ebx, 80070000h
0x18010d4c7  test    ebx, ebx
0x18010d4c9  js      loc_18010D6D5
0x18010d4cf  lea     rdx, [rbp+0A0h+Sid]
0x18010d4d3  mov     [rbp+0A0h+Sid], rsi
0x18010d4d7  lea     rcx, [rbp+0A0h+packageFamilyName]
0x18010d4db  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x18010d4e1  mov     ebx, eax
0x18010d4e3  test    eax, eax
0x18010d4e5  js      loc_18010D6D5
0x18010d4eb  mov     rcx, [rbp+0A0h+Sid]; Sid
0x18010d4ef  lea     rdx, [rsp+1A0h+StringSid]; StringSid
0x18010d4f4  mov     [rsp+1A0h+StringSid], rsi
0x18010d4f9  call    cs:__imp_ConvertSidToStringSidW
0x18010d4ff  test    eax, eax
0x18010d501  jnz     short loc_18010D521
0x18010d503  call    cs:__imp_GetLastError
0x18010d509  mov     ebx, eax
0x18010d50b  test    eax, eax
0x18010d50d  jle     loc_18010D6CB
0x18010d513  movzx   ebx, ax
0x18010d516  or      ebx, 80070000h
0x18010d51c  jmp     loc_18010D6CB
0x18010d521  mov     ecx, cs:_tls_index
0x18010d527  mov     rax, gs:58h
0x18010d530  mov     edx, 4
0x18010d535  mov     rax, [rax+rcx*8]
0x18010d539  mov     ecx, [rdx+rax]
0x18010d53c  cmp     cs:dword_1804B6E18, ecx
0x18010d542  jle     short loc_18010D58C
0x18010d544  lea     rcx, dword_1804B6E18
0x18010d54b  call    _Init_thread_header
0x18010d550  cmp     cs:dword_1804B6E18, 0FFFFFFFFh
0x18010d557  jnz     short loc_18010D58C
0x18010d559  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18010d560  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18010d566  lea     rcx, dword_1804B6E18
0x18010d56d  mov     dword ptr cs:byte_1804B4F60+10h, eax
0x18010d573  movups  xmmword ptr cs:byte_1804B4F60, xmm0
0x18010d57a  mov     cs:dword_1804B4F74, esi
0x18010d580  mov     cs:qword_1804B4F78, rsi
0x18010d587  call    _Init_thread_footer
0x18010d58c  mov     rdx, [rdi+10h]
0x18010d590  lea     rax, [rsp+1A0h+var_158]
0x18010d595  mov     [rsp+1A0h+var_170], rax
0x18010d59a  mov     r9d, r14d
0x18010d59d  lea     rax, [rsp+1A0h+var_160]
0x18010d5a2  mov     [rsp+1A0h+var_160], esi
0x18010d5a6  mov     [rsp+1A0h+var_178], rax
0x18010d5ab  xor     r8d, r8d
0x18010d5ae  lea     rax, byte_1804B4F60
0x18010d5b5  mov     [rsp+1A0h+var_158], rsi
0x18010d5ba  mov     ecx, r14d
0x18010d5bd  mov     [rsp+1A0h+ppv], rax
0x18010d5c2  call    cs:__imp_DevGetObjectProperties
0x18010d5c8  mov     ebx, eax
0x18010d5ca  test    eax, eax
0x18010d5cc  js      loc_18010D6C0
0x18010d5d2  mov     rax, [rsp+1A0h+var_158]
0x18010d5d7  cmp     [rsp+1A0h+var_160], r14d
0x18010d5dc  jnz     loc_18010D6B3
0x18010d5e2  cmp     dword ptr [rax+10h], 4
0x18010d5e6  jnz     loc_18010D6B3
0x18010d5ec  mov     rcx, [rax]
0x18010d5ef  sub     rcx, qword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18010d5f6  jnz     short loc_18010D603
0x18010d5f8  mov     rcx, [rax+8]
0x18010d5fc  sub     rcx, qword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data4
0x18010d603  test    rcx, rcx
0x18010d606  jnz     loc_18010D6B3
0x18010d60c  cmp     dword ptr [rax+20h], 0Dh
0x18010d610  jnz     loc_18010D6B3
0x18010d616  lea     r8d, [rcx+27h]; cchMax
0x18010d61a  mov     rcx, [rax+28h]; rguid
0x18010d61e  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18010d622  call    cs:__imp_StringFromGUID2
0x18010d628  test    eax, eax
0x18010d62a  jz      short loc_18010D6A9
0x18010d62c  lea     rcx, [rsp+1A0h+var_150]
0x18010d631  mov     [rsp+1A0h+var_150], rsi
0x18010d636  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010d63b  lea     rax, [rsp+1A0h+var_150]
0x18010d640  mov     r8d, r14d; dwClsContext
0x18010d643  lea     r9, _GUID_02a175a2_f59b_4490_8008_da0592239633; riid
0x18010d64a  mov     [rsp+1A0h+ppv], rax; ppv
0x18010d64f  xor     edx, edx; pUnkOuter
0x18010d651  lea     rcx, CLSID_DeviceAccessPolicyManager; rclsid
0x18010d658  call    cs:__imp_CoCreateInstance
0x18010d65e  mov     ebx, eax
0x18010d660  test    eax, eax
0x18010d662  js      short loc_18010D69D
0x18010d664  mov     rcx, [rsp+1A0h+var_150]
0x18010d669  lea     rax, [rbp+0A0h+sz]
0x18010d66d  mov     rdx, [rsp+1A0h+StringSid]
0x18010d672  lea     r8, [rsp+1A0h+var_130]
0x18010d677  mov     [rsp+1A0h+var_130], rax
0x18010d67c  mov     r9d, r14d
0x18010d67f  mov     [rsp+1A0h+var_124], rsi
0x18010d684  mov     [rbp+0A0h+var_11C], esi
0x18010d687  mov     [rbp+0A0h+var_118], r14
0x18010d68b  mov     [rsp+1A0h+var_128], esi
0x18010d68f  mov     rax, [rcx]
0x18010d692  mov     rax, [rax+40h]
0x18010d696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d69b  mov     ebx, eax
0x18010d69d  lea     rcx, [rsp+1A0h+var_150]
0x18010d6a2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18010d6a7  jmp     short loc_18010D6AE
0x18010d6a9  mov     ebx, 8000FFFFh
0x18010d6ae  mov     rax, [rsp+1A0h+var_158]
0x18010d6b3  mov     ecx, [rsp+1A0h+var_160]
0x18010d6b7  mov     rdx, rax
0x18010d6ba  call    cs:__imp_DevFreeObjectProperties
0x18010d6c0  mov     rcx, [rsp+1A0h+StringSid]; hMem
0x18010d6c5  call    cs:__imp_LocalFree
0x18010d6cb  mov     rcx, [rbp+0A0h+Sid]; hMem
0x18010d6cf  call    cs:__imp_LocalFree
0x18010d6d5  mov     rcx, [rsp+1A0h+packageFullName]; pv
0x18010d6da  call    cs:__imp_CoTaskMemFree
0x18010d6e0  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18010d6e7  jz      short loc_18010D708
0x18010d6e9  lea     rax, [rbp+0A0h+Sid]
0x18010d6ed  mov     r9d, r14d
0x18010d6f0  lea     rdx, AutoPlay_Broker_Device_Stop
0x18010d6f7  mov     [rsp+1A0h+ppv], rax
0x18010d6fc  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18010d703  call    McGenEventWrite_EventWriteTransfer
0x18010d708  mov     eax, ebx
0x18010d70a  mov     rcx, [rbp+0A0h+var_20]
0x18010d711  xor     rcx, rsp; StackCookie
0x18010d714  call    __security_check_cookie
0x18010d719  lea     r11, [rsp+1A0h+var_10]
0x18010d721  mov     rbx, [r11+30h]
0x18010d725  mov     rsi, [r11+38h]
0x18010d729  mov     rsp, r11
0x18010d72c  pop     r14
0x18010d72e  pop     rdi
0x18010d72f  pop     rbp
0x18010d730  retn
```
