# CETWLogger::SetPropertyString(ushort const *,ushort const *)

- ea: `0x1800d9900`
- end: `0x1800d9c2d`
- name: `?SetPropertyString@CETWLogger@@UEAAJPEBG0@Z`
- size: `813`
- prototype: `int(CETWLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x180004306`
- `0x1800d98a4`
- `0x1800d9900`
- `0x1800d9c34`
- `0x180102010`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800d9b75`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800d9b75`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800d9a3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800d9a3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9a75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9a8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9a75`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800d9a8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9aa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9ac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9ade`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9aa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9ac2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d9ade`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d9982`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d9bde`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d9982`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800d9bde`

## string_xrefs

- `0x1800d9a6e`: `advapi32.dll`
- `0x1800d9a87`: `api-ms-win-eventing-provider-l1-1-0.dll`
- `0x1800d9a9c`: `EventWrite`

## pseudocode

```c
__int64 __fastcall CETWLogger::SetPropertyString(
        CETWLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  int v7; // ebx
  _OWORD *v8; // rdi
  int v9; // eax
  int v10; // esi
  HMODULE ModuleHandleW; // rbx
  ULONG v12; // eax
  bool v13; // sf
  __int64 v14; // rax
  bool v15; // dl
  CETWLogger *v16; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-C0h] BYREF
  IID iid; // [rsp+50h] [rbp-B0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF

  if ( !wcscmp_0(a2, L"ETWProviderGUID") )
  {
    v6 = -1;
    iid = GUID_NULL;
    do
      ++v6;
    while ( a3[v6] );
    if ( v6 != 38 )
      return (unsigned int)-2147024809;
    v7 = IIDFromString(a3, &iid);
    if ( v7 >= 0 )
    {
      v8 = (_OWORD *)((char *)this + 8);
      v9 = McGenEventTracingUnregister2((char *)this + 8);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      if ( v7 >= 0 )
      {
        *((_DWORD *)this + 28) = 0;
        *v8 = SYMBOL_PRIVATE_PROVIDER_Context;
        *(_OWORD *)((char *)this + 24) = xmmword_180108E50;
        *(_OWORD *)((char *)this + 40) = xmmword_180108E60;
        *(_OWORD *)((char *)this + 56) = *(_OWORD *)&off_180108E70;
        *((_QWORD *)this + 9) = Microsoft_Speech_SREngine_PrivateLevels;
        *((_QWORD *)this + 7) = (char *)this + 112;
        if ( this == (CETWLogger *)-8LL )
        {
          LOWORD(v7) = 87;
LABEL_34:
          v7 = (unsigned __int16)v7 | 0x80070000;
          v13 = v7 < 0;
LABEL_35:
          if ( !v13 )
            *((IID *)this + 6) = iid;
          return (unsigned int)v7;
        }
        v7 = 0;
        if ( *(_QWORD *)v8 )
        {
LABEL_33:
          v13 = v7 < 0;
          if ( v7 <= 0 )
            goto LABEL_35;
          goto LABEL_34;
        }
        memset_0(&VersionInformation, 0, sizeof(VersionInformation));
        if ( McGenTracingSupportInit )
        {
LABEL_29:
          if ( McGenPreVista )
          {
            TraceGuidReg.Guid = &iid;
            *(_QWORD *)v8 = v8;
            TraceGuidReg.RegHandle = 0;
            v12 = RegisterTraceGuidsW(
                    McGenControlCallback,
                    (char *)this + 8,
                    &iid,
                    1u,
                    &TraceGuidReg,
                    0,
                    0,
                    (PTRACEHANDLE)this + 1);
          }
          else
          {
            v12 = ((__int64 (__fastcall *)(IID *, __int64 (__fastcall *)(int, int, int, int, __int64, int, __int64), char *, char *))PfnEventRegister)(
                    &iid,
                    McGenControlCallbackV2,
                    (char *)this + 8,
                    (char *)this + 8);
          }
          v7 = v12;
          goto LABEL_33;
        }
        VersionInformation.dwOSVersionInfoSize = 276;
        v10 = 0;
        if ( !GetVersionExW(&VersionInformation) )
          goto LABEL_20;
        McGenPreVista = VersionInformation.dwMajorVersion < 6;
        if ( VersionInformation.dwMajorVersion > 6
          || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1 )
        {
          v10 = 1;
        }
        if ( VersionInformation.dwMajorVersion >= 6 )
        {
LABEL_20:
          ModuleHandleW = GetModuleHandleW(L"advapi32.dll");
          if ( ModuleHandleW
            || v10 && (ModuleHandleW = GetModuleHandleW(L"api-ms-win-eventing-provider-l1-1-0.dll")) != 0 )
          {
            PfnEventWrite = (__int64)GetProcAddress(ModuleHandleW, "EventWrite");
            if ( PfnEventWrite )
            {
              PfnEventRegister = (__int64 (__fastcall *)(LPCGUID, WMIDPREQUEST, PTRACEHANDLE))GetProcAddress(
                                                                                                ModuleHandleW,
                                                                                                "EventRegister");
              if ( PfnEventRegister )
              {
                PfnEventUnregister = (__int64)GetProcAddress(ModuleHandleW, "EventUnregister");
                if ( PfnEventUnregister )
                  goto LABEL_28;
              }
              PfnEventRegister = McGenEventTracingRegister;
            }
          }
          McGenPreVista = 1;
        }
LABEL_28:
        McGenTracingSupportInit = 1;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v7 = 0;
    if ( wcscmp_0(a2, L"ETWActivityID") )
      return (unsigned int)v7;
    v14 = -1;
    iid = GUID_NULL;
    do
      ++v14;
    while ( a3[v14] );
    if ( v14 != 38 )
      return (unsigned int)-2147024809;
    v7 = IIDFromString(a3, &iid);
    if ( v7 >= 0 )
    {
      v7 = CETWLogger::SetCurrentThreadActivityID(v16, v15, &iid);
      if ( v7 >= 0 )
        *((IID *)this + 5) = iid;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800d9900  mov     [rsp-8+arg_8], rbx
0x1800d9905  push    rbp
0x1800d9906  push    rsi
0x1800d9907  push    rdi
0x1800d9908  push    r14
0x1800d990a  push    r15
0x1800d990c  lea     rbp, [rsp-90h]
0x1800d9914  sub     rsp, 190h
0x1800d991b  mov     rax, cs:__security_cookie
0x1800d9922  xor     rax, rsp
0x1800d9925  mov     [rbp+0B0h+var_30], rax
0x1800d992c  mov     rsi, rdx
0x1800d992f  mov     r14, rcx
0x1800d9932  mov     rcx, rsi; String1
0x1800d9935  lea     rdx, aEtwprovidergui; "ETWProviderGUID"
0x1800d993c  mov     rdi, r8
0x1800d993f  call    wcscmp_0
0x1800d9944  xor     r15d, r15d
0x1800d9947  test    eax, eax
0x1800d9949  jnz     loc_1800D9B9B
0x1800d994f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d9956  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d995a  movdqu  xmmword ptr [rsp+1B0h+iid.Data1], xmm0
0x1800d9960  inc     rax
0x1800d9963  cmp     [rdi+rax*2], r15w
0x1800d9968  jnz     short loc_1800D9960
0x1800d996a  cmp     rax, 26h ; '&'
0x1800d996e  jz      short loc_1800D997A
0x1800d9970  mov     ebx, 80070057h
0x1800d9975  jmp     loc_1800D9C05
0x1800d997a  lea     rdx, [rsp+1B0h+iid]; lpiid
0x1800d997f  mov     rcx, rdi; lpsz
0x1800d9982  call    cs:__imp_IIDFromString
0x1800d9988  mov     ebx, eax
0x1800d998a  test    eax, eax
0x1800d998c  js      loc_1800D9C05
0x1800d9992  lea     rdi, [r14+8]
0x1800d9996  mov     rcx, rdi
0x1800d9999  call    McGenEventTracingUnregister2
0x1800d999e  mov     ebx, eax
0x1800d99a0  test    eax, eax
0x1800d99a2  jle     short loc_1800D99AD
0x1800d99a4  movzx   ebx, ax
0x1800d99a7  or      ebx, 80070000h
0x1800d99ad  test    ebx, ebx
0x1800d99af  js      loc_1800D9C05
0x1800d99b5  movaps  xmm0, cs:SYMBOL_PRIVATE_PROVIDER_Context
0x1800d99bc  lea     rax, [r14+70h]
0x1800d99c0  movaps  xmm1, cs:xmmword_180108E50
0x1800d99c7  mov     [rax], r15d
0x1800d99ca  movups  xmmword ptr [rdi], xmm0
0x1800d99cd  movaps  xmm0, cs:xmmword_180108E60
0x1800d99d4  movups  xmmword ptr [rdi+10h], xmm1
0x1800d99d8  movaps  xmm1, xmmword ptr cs:off_180108E70
0x1800d99df  movups  xmmword ptr [rdi+20h], xmm0
0x1800d99e3  movsd   xmm0, cs:off_180108E80
0x1800d99eb  movups  xmmword ptr [rdi+30h], xmm1
0x1800d99ef  movsd   qword ptr [rdi+40h], xmm0
0x1800d99f4  mov     [r14+38h], rax
0x1800d99f8  test    rdi, rdi
0x1800d99fb  jnz     short loc_1800D9A05
0x1800d99fd  lea     ebx, [rdi+57h]
0x1800d9a00  jmp     loc_1800D9B81
0x1800d9a05  mov     ebx, r15d
0x1800d9a08  cmp     [rdi], r15
0x1800d9a0b  jnz     loc_1800D9B7D
0x1800d9a11  mov     ebx, 114h
0x1800d9a16  lea     rcx, [rsp+1B0h+VersionInformation]; void *
0x1800d9a1b  mov     r8d, ebx; Size
0x1800d9a1e  xor     edx, edx; Val
0x1800d9a20  call    memset_0
0x1800d9a25  cmp     cs:McGenTracingSupportInit, r15b
0x1800d9a2c  jnz     loc_1800D9B0C
0x1800d9a32  lea     rcx, [rsp+1B0h+VersionInformation]; lpVersionInformation
0x1800d9a37  mov     [rsp+1B0h+VersionInformation.dwOSVersionInfoSize], ebx
0x1800d9a3b  mov     esi, r15d
0x1800d9a3e  call    cs:__imp_GetVersionExW
0x1800d9a44  test    eax, eax
0x1800d9a46  jz      short loc_1800D9A6E
0x1800d9a48  cmp     [rsp+1B0h+VersionInformation.dwMajorVersion], 6
0x1800d9a4d  setb    cl
0x1800d9a50  mov     cs:McGenPreVista, cl
0x1800d9a56  ja      short loc_1800D9A61
0x1800d9a58  jnz     short loc_1800D9A66
0x1800d9a5a  cmp     [rsp+1B0h+VersionInformation.dwMinorVersion], 1
0x1800d9a5f  jbe     short loc_1800D9A66
0x1800d9a61  mov     esi, 1
0x1800d9a66  test    cl, cl
0x1800d9a68  jnz     loc_1800D9B05
0x1800d9a6e  lea     rcx, LibFileName; "advapi32.dll"
0x1800d9a75  call    cs:__imp_GetModuleHandleW
0x1800d9a7b  mov     rbx, rax
0x1800d9a7e  test    rax, rax
0x1800d9a81  jnz     short loc_1800D9A9C
0x1800d9a83  test    esi, esi
0x1800d9a85  jz      short loc_1800D9AFE
0x1800d9a87  lea     rcx, aApiMsWinEventi_1; "api-ms-win-eventing-provider-l1-1-0.dll"
0x1800d9a8e  call    cs:__imp_GetModuleHandleW
0x1800d9a94  mov     rbx, rax
0x1800d9a97  test    rax, rax
0x1800d9a9a  jz      short loc_1800D9AFE
0x1800d9a9c  lea     rdx, ProcName; "EventWrite"
0x1800d9aa3  mov     rcx, rbx; hModule
0x1800d9aa6  call    cs:__imp_GetProcAddress
0x1800d9aac  mov     cs:PfnEventWrite, rax
0x1800d9ab3  test    rax, rax
0x1800d9ab6  jz      short loc_1800D9AFE
0x1800d9ab8  lea     rdx, aEventregister; "EventRegister"
0x1800d9abf  mov     rcx, rbx; hModule
0x1800d9ac2  call    cs:__imp_GetProcAddress
0x1800d9ac8  mov     cs:PfnEventRegister, rax
0x1800d9acf  test    rax, rax
0x1800d9ad2  jz      short loc_1800D9AF0
0x1800d9ad4  lea     rdx, aEventunregiste; "EventUnregister"
0x1800d9adb  mov     rcx, rbx; hModule
0x1800d9ade  call    cs:__imp_GetProcAddress
0x1800d9ae4  mov     cs:PfnEventUnregister, rax
0x1800d9aeb  test    rax, rax
0x1800d9aee  jnz     short loc_1800D9B05
0x1800d9af0  lea     rax, McGenEventTracingRegister
0x1800d9af7  mov     cs:PfnEventRegister, rax
0x1800d9afe  mov     cs:McGenPreVista, 1
0x1800d9b05  mov     cs:McGenTracingSupportInit, 1
0x1800d9b0c  cmp     cs:McGenPreVista, r15b
0x1800d9b13  jnz     short loc_1800D9B35
0x1800d9b15  mov     rax, cs:PfnEventRegister
0x1800d9b1c  lea     rdx, McGenControlCallbackV2
0x1800d9b23  mov     r9, rdi
0x1800d9b26  lea     rcx, [rsp+1B0h+iid]
0x1800d9b2b  mov     r8, rdi
0x1800d9b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9b33  jmp     short loc_1800D9B7B
0x1800d9b35  mov     [rsp+1B0h+RegistrationHandle], rdi; RegistrationHandle
0x1800d9b3a  lea     rax, [rsp+1B0h+iid]
0x1800d9b3f  mov     [rsp+1B0h+var_170.Guid], rax
0x1800d9b44  lea     r8, [rsp+1B0h+iid]; ControlGuid
0x1800d9b49  lea     rax, [rsp+1B0h+var_170]
0x1800d9b4e  mov     [rsp+1B0h+MofResourceName], r15; MofResourceName
0x1800d9b53  mov     [rsp+1B0h+MofImagePath], r15; MofImagePath
0x1800d9b58  lea     rcx, McGenControlCallback; RequestAddress
0x1800d9b5f  mov     r9d, 1; GuidCount
0x1800d9b65  mov     [rsp+1B0h+TraceGuidReg], rax; TraceGuidReg
0x1800d9b6a  mov     rdx, rdi; RequestContext
0x1800d9b6d  mov     [rdi], rdi
0x1800d9b70  mov     [rsp+1B0h+var_170.RegHandle], r15
0x1800d9b75  call    cs:__imp_RegisterTraceGuidsW
0x1800d9b7b  mov     ebx, eax
0x1800d9b7d  test    ebx, ebx
0x1800d9b7f  jle     short loc_1800D9B8C
0x1800d9b81  movzx   ebx, bx
0x1800d9b84  or      ebx, 80070000h
0x1800d9b8a  test    ebx, ebx
0x1800d9b8c  js      short loc_1800D9C05
0x1800d9b8e  movups  xmm0, xmmword ptr [rsp+1B0h+iid.Data1]
0x1800d9b93  movdqu  xmmword ptr [r14+60h], xmm0
0x1800d9b99  jmp     short loc_1800D9C05
0x1800d9b9b  lea     rdx, aEtwactivityid; "ETWActivityID"
0x1800d9ba2  mov     rcx, rsi; String1
0x1800d9ba5  mov     ebx, r15d
0x1800d9ba8  call    wcscmp_0
0x1800d9bad  test    eax, eax
0x1800d9baf  jnz     short loc_1800D9C05
0x1800d9bb1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d9bb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d9bbc  movdqu  xmmword ptr [rsp+1B0h+iid.Data1], xmm0
0x1800d9bc2  inc     rax
0x1800d9bc5  cmp     [rdi+rax*2], r15w
0x1800d9bca  jnz     short loc_1800D9BC2
0x1800d9bcc  cmp     rax, 26h ; '&'
0x1800d9bd0  jnz     loc_1800D9970
0x1800d9bd6  lea     rdx, [rsp+1B0h+iid]; lpiid
0x1800d9bdb  mov     rcx, rdi; lpsz
0x1800d9bde  call    cs:__imp_IIDFromString
0x1800d9be4  mov     ebx, eax
0x1800d9be6  test    eax, eax
0x1800d9be8  js      short loc_1800D9C05
0x1800d9bea  lea     r8, [rsp+1B0h+iid]; struct _GUID *
0x1800d9bef  call    ?SetCurrentThreadActivityID@CETWLogger@@QEAAJ_NPEAU_GUID@@@Z; CETWLogger::SetCurrentThreadActivityID(bool,_GUID *)
0x1800d9bf4  mov     ebx, eax
0x1800d9bf6  test    eax, eax
0x1800d9bf8  js      short loc_1800D9C05
0x1800d9bfa  movups  xmm0, xmmword ptr [rsp+1B0h+iid.Data1]
0x1800d9bff  movdqu  xmmword ptr [r14+50h], xmm0
0x1800d9c05  mov     eax, ebx
0x1800d9c07  mov     rcx, [rbp+0B0h+var_30]
0x1800d9c0e  xor     rcx, rsp; StackCookie
0x1800d9c11  call    __security_check_cookie
0x1800d9c16  mov     rbx, [rsp+1B0h+arg_8]
0x1800d9c1e  add     rsp, 190h
0x1800d9c25  pop     r15
0x1800d9c27  pop     r14
0x1800d9c29  pop     rdi
0x1800d9c2a  pop     rsi
0x1800d9c2b  pop     rbp
0x1800d9c2c  retn
```
