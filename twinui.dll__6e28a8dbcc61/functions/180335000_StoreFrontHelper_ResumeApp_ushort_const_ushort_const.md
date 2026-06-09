# StoreFrontHelper::ResumeApp(ushort const *,ushort const *)

- ea: `0x180335000`
- end: `0x180335234`
- name: `?ResumeApp@StoreFrontHelper@@AEAAJPEBG0@Z`
- size: `564`
- prototype: `int(StoreFrontHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18011473c`

## callees

- `0x180008acc`
- `0x180030470`
- `0x18003c5e4`
- `0x180335000`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033520f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18033520f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18033514b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18033514b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180335045`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803351c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180335045`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1803351c4`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x180335101`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x180335101`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x180335219`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x180335219`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x180335139`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18033516c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x180335139`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18033516c`

## pseudocode

```c
__int64 __fastcall StoreFrontHelper::ResumeApp(
        StoreFrontHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  LONG v9; // eax
  bool v10; // sf
  BYTE *v11; // rax
  BYTE *v12; // rdi
  LONG PackageApplicationIds; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v16; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-10h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  StoreFrontHelper *count; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 *bufferLength; // [rsp+80h] [rbp+30h] BYREF
  int v22; // [rsp+88h] [rbp+38h] BYREF

  bufferLength = a3;
  count = this;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v4 = CoCreateInstance(&CLSID_PackageDebugSettings, 0, 1u, &GUID_f27c3930_8029_4ad1_94e3_3dba417810c1, &v16);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v22 = 0;
    v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, int *))(*(_QWORD *)v16 + 120LL))(v16, a2, &v22);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 196;
      goto LABEL_5;
    }
    if ( v22 )
    {
      if ( v22 == 2 || v22 == 3 )
      {
        StoreFrontHelperTelemetry::TraceLoggingInfo("ResumeApp - resuming %ws", a2);
        v4 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v16 + 48LL))(v16, a2);
        v5 = v4;
        if ( v4 < 0 )
        {
          v6 = 203;
          goto LABEL_5;
        }
LABEL_11:
        v5 = 0;
        goto LABEL_12;
      }
      if ( v22 != 4 )
        goto LABEL_11;
    }
    packageInfoReference = 0;
    v9 = OpenPackageInfoByFullName(a2, 0, &packageInfoReference);
    v10 = v9 < 0;
    if ( v9 > 0 )
      v10 = 1;
    if ( !v10 )
    {
      LODWORD(bufferLength) = 0;
      LODWORD(count) = 0;
      v5 = -2147418113;
      if ( GetPackageApplicationIds(packageInfoReference, (UINT32 *)&bufferLength, 0, (UINT32 *)&count) == 122 )
      {
        v11 = (BYTE *)CoTaskMemAlloc((unsigned int)bufferLength);
        v12 = v11;
        if ( v11 )
        {
          PackageApplicationIds = GetPackageApplicationIds(
                                    packageInfoReference,
                                    (UINT32 *)&bufferLength,
                                    v11,
                                    (UINT32 *)&count);
          v5 = PackageApplicationIds;
          if ( PackageApplicationIds > 0 )
            v5 = (unsigned __int16)PackageApplicationIds | 0x80070000;
          if ( v5 >= 0 && (_DWORD)count )
          {
            v15 = 0;
            v17 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
            v5 = CoCreateInstance(
                   &CLSID_ApplicationActivationManager,
                   0,
                   1u,
                   &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
                   &v17);
            if ( v5 >= 0 )
            {
              StoreFrontHelperTelemetry::TraceLoggingInfo("ResumeApp - launching %ws", *(_QWORD *)v12);
              ppv = (LPVOID *)&v15;
              v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
                     v17,
                     *(_QWORD *)v12,
                     0,
                     0);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
          }
          CoTaskMemFree(v12);
        }
      }
      ClosePackageInfo(packageInfoReference);
      if ( v5 < 0 )
      {
        v7 = (unsigned int)v5;
        v6 = 238;
        goto LABEL_6;
      }
    }
    goto LABEL_11;
  }
  v6 = 193;
LABEL_5:
  v7 = (unsigned int)v4;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\twinui\\storefronthelper\\lib\\storefronthelper.cpp",
    (const char *)v7,
    (int)ppv);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180335000  mov     [rsp-18h+bufferLength], r8
0x180335005  mov     [rsp-18h+count], rcx
0x18033500a  push    rbp
0x18033500b  push    rbx
0x18033500c  push    rdi
0x18033500d  mov     rbp, rsp
0x180335010  sub     rsp, 50h
0x180335014  lea     rcx, [rbp+var_18]
0x180335018  mov     [rbp+var_18], 0
0x180335020  mov     rdi, rdx
0x180335023  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180335028  xor     edx, edx; pUnkOuter
0x18033502a  lea     rax, [rbp+var_18]
0x18033502e  lea     r9, _GUID_f27c3930_8029_4ad1_94e3_3dba417810c1; riid
0x180335035  mov     [rsp+50h+ppv], rax; int
0x18033503a  lea     rcx, CLSID_PackageDebugSettings; rclsid
0x180335041  lea     r8d, [rdx+1]; dwClsContext
0x180335045  call    cs:__imp_CoCreateInstance
0x18033504b  mov     ebx, eax
0x18033504d  test    eax, eax
0x18033504f  jns     short loc_180335058
0x180335051  mov     edx, 0C1h
0x180335056  jmp     short loc_180335081
0x180335058  mov     rcx, [rbp+var_18]
0x18033505c  lea     r8, [rbp+arg_18]
0x180335060  mov     [rbp+arg_18], 0
0x180335067  mov     rdx, rdi
0x18033506a  mov     rax, [rcx]
0x18033506d  mov     rax, [rax+78h]
0x180335071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180335076  mov     ebx, eax
0x180335078  test    eax, eax
0x18033507a  jns     short loc_180335096
0x18033507c  mov     edx, 0C4h; void *
0x180335081  mov     r9d, eax; char *
0x180335084  mov     rcx, [rbp+18h]; this
0x180335088  lea     r8, aShellTwinuiSto_0; "shell\\twinui\\storefronthelper\\lib\\s"...
0x18033508f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180335094  jmp     short loc_1803350AE
0x180335096  mov     ecx, [rbp+arg_18]
0x180335099  test    ecx, ecx
0x18033509b  jz      short loc_1803350F0
0x18033509d  sub     ecx, 2
0x1803350a0  jz      short loc_1803350C1
0x1803350a2  sub     ecx, 1
0x1803350a5  jz      short loc_1803350C1
0x1803350a7  cmp     ecx, 1
0x1803350aa  jz      short loc_1803350F0
0x1803350ac  xor     ebx, ebx
0x1803350ae  lea     rcx, [rbp+var_18]
0x1803350b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803350b7  mov     eax, ebx
0x1803350b9  add     rsp, 50h
0x1803350bd  pop     rdi
0x1803350be  pop     rbx
0x1803350bf  pop     rbp
0x1803350c0  retn
0x1803350c1  mov     rdx, rdi
0x1803350c4  lea     rcx, aResumeappResum; "ResumeApp - resuming %ws"
0x1803350cb  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x1803350d0  mov     rcx, [rbp+var_18]
0x1803350d4  mov     rdx, rdi
0x1803350d7  mov     rax, [rcx]
0x1803350da  mov     rax, [rax+30h]
0x1803350de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803350e3  mov     ebx, eax
0x1803350e5  test    eax, eax
0x1803350e7  jns     short loc_1803350AC
0x1803350e9  mov     edx, 0CBh
0x1803350ee  jmp     short loc_180335081
0x1803350f0  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x1803350f4  mov     [rbp+packageInfoReference], 0
0x1803350fc  xor     edx, edx; reserved
0x1803350fe  mov     rcx, rdi; packageFullName
0x180335101  call    cs:__imp_OpenPackageInfoByFullName
0x180335107  test    eax, eax
0x180335109  jle     short loc_180335115
0x18033510b  movzx   eax, ax
0x18033510e  or      eax, 80070000h
0x180335113  test    eax, eax
0x180335115  js      short loc_1803350AC
0x180335117  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18033511b  lea     r9, [rbp+count]; count
0x18033511f  xor     r8d, r8d; buffer
0x180335122  mov     dword ptr [rbp+bufferLength], 0
0x180335129  lea     rdx, [rbp+bufferLength]; bufferLength
0x18033512d  mov     dword ptr [rbp+count], 0
0x180335134  mov     ebx, 8000FFFFh
0x180335139  call    cs:__imp_GetPackageApplicationIds
0x18033513f  cmp     eax, 7Ah ; 'z'
0x180335142  jnz     loc_180335215
0x180335148  mov     ecx, dword ptr [rbp+bufferLength]; cb
0x18033514b  call    cs:__imp_CoTaskMemAlloc
0x180335151  mov     rdi, rax
0x180335154  test    rax, rax
0x180335157  jz      loc_180335215
0x18033515d  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x180335161  lea     r9, [rbp+count]; count
0x180335165  mov     r8, rax; buffer
0x180335168  lea     rdx, [rbp+bufferLength]; bufferLength
0x18033516c  call    cs:__imp_GetPackageApplicationIds
0x180335172  mov     ebx, eax
0x180335174  test    eax, eax
0x180335176  jle     short loc_180335181
0x180335178  movzx   ebx, ax
0x18033517b  or      ebx, 80070000h
0x180335181  test    ebx, ebx
0x180335183  js      loc_18033520C
0x180335189  cmp     dword ptr [rbp+count], 0
0x18033518d  jz      short loc_18033520C
0x18033518f  lea     rcx, [rbp+var_10]
0x180335193  mov     [rbp+var_20], 0
0x18033519a  mov     [rbp+var_10], 0
0x1803351a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803351a7  xor     edx, edx; pUnkOuter
0x1803351a9  lea     rax, [rbp+var_10]
0x1803351ad  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x1803351b4  mov     [rsp+50h+ppv], rax; ppv
0x1803351b9  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x1803351c0  lea     r8d, [rdx+1]; dwClsContext
0x1803351c4  call    cs:__imp_CoCreateInstance
0x1803351ca  mov     ebx, eax
0x1803351cc  test    eax, eax
0x1803351ce  js      short loc_180335203
0x1803351d0  mov     rdx, [rdi]
0x1803351d3  lea     rcx, aResumeappLaunc; "ResumeApp - launching %ws"
0x1803351da  call    ?TraceLoggingInfo@StoreFrontHelperTelemetry@@SAXPEBDZZ; StoreFrontHelperTelemetry::TraceLoggingInfo(char const *,...)
0x1803351df  mov     rcx, [rbp+var_10]
0x1803351e3  lea     rdx, [rbp+var_20]
0x1803351e7  mov     [rsp+50h+ppv], rdx
0x1803351ec  xor     r9d, r9d
0x1803351ef  mov     rdx, [rdi]
0x1803351f2  xor     r8d, r8d
0x1803351f5  mov     rax, [rcx]
0x1803351f8  mov     rax, [rax+18h]
0x1803351fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180335201  mov     ebx, eax
0x180335203  lea     rcx, [rbp+var_10]
0x180335207  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033520c  mov     rcx, rdi; pv
0x18033520f  call    cs:__imp_CoTaskMemFree
0x180335215  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x180335219  call    cs:__imp_ClosePackageInfo
0x18033521f  test    ebx, ebx
0x180335221  jns     loc_1803350AC
0x180335227  mov     r9d, ebx
0x18033522a  mov     edx, 0EEh
0x18033522f  jmp     loc_180335084
```
