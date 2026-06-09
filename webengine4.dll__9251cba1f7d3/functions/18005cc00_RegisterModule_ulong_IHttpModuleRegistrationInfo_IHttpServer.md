# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x18005cc00`
- end: `0x18005ce82`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180001898`
- `0x180007824`
- `0x18004d030`
- `0x18004dddc`
- `0x18005bbb4`
- `0x18005cc00`
- `0x18005e8f4`
- `0x180064810`
- `0x1800653c0`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005cd59`
- `KERNEL32!GetLastError` at `0x18005cd59`
- `KERNEL32!CreateEventW` at `0x18005cd47`
- `KERNEL32!CreateEventW` at `0x18005cd47`
- `KERNEL32!GetFileAttributesW` at `0x18005cdf8`
- `KERNEL32!GetFileAttributesW` at `0x18005cdf8`

## string_xrefs

- `0x18005ce18`: `\aspnet.config`

## pseudocode

```c
__int64 __fastcall RegisterModule(unsigned int a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  const unsigned __int16 *v6; // rax
  signed int InstallDirectory; // ebx
  signed int LastError; // eax
  _QWORD *v9; // rax
  void *v10; // rdi
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v13 = 0;
  v12 = 0;
  v14 = 260;
  memset_0(FileName, 0, 0x208u);
  g_MgdModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(struct IHttpModuleRegistrationInfo *))a2)(a2);
  g_pHttpServer = a3;
  g_MgdModuleName = v6;
  InstallDirectory = (*(__int64 (__fastcall **)(struct IHttpServer *, __int64 *))(*(_QWORD *)a3 + 160LL))(a3, &v13);
  if ( InstallDirectory >= 0 )
  {
    InstallDirectory = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v13 + 16LL))(v13, 4, &v12);
    if ( InstallDirectory >= 0 && !v12 )
    {
      if ( (*(int (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v13 + 24LL))(v13, 1, &v15) >= 0 )
        g_MemoryLimitKB = v15 >> 10;
      g_IsAppPoolInIntegratedMode = 1;
      if ( !g_dwIISVersion )
      {
        if ( a1 == 7 )
        {
          a1 = 458752;
        }
        else if ( a1 == 327687 )
        {
          a1 = 458757;
        }
        g_dwIISVersion = a1;
      }
      g_hStopListeningFired = CreateEventW(0, 1, 0, 0);
      if ( g_hStopListeningFired )
      {
        v9 = operator new(8u);
        v10 = v9;
        if ( v9 )
        {
          *v9 = &CMgdEngGlobalModule::`vftable';
          InstallDirectory = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
                               a2,
                               v9,
                               134146);
          if ( InstallDirectory >= 0 )
          {
            InstallDirectory = W3_MGD_APP_CONTEXT::Initialize();
            if ( InstallDirectory >= 0 )
            {
              if ( (*(int (__fastcall **)(__int64, __int64, WCHAR *, int *))(*(_QWORD *)v13 + 32LL))(
                     v13,
                     4,
                     FileName,
                     &v14) >= 0
                && GetFileAttributesW(FileName) != -1
                || (InstallDirectory = GetInstallDirectory(FileName, 0x104u), InstallDirectory >= 0)
                && (InstallDirectory = StringCchCatW(FileName, 0x104u, L"\\aspnet.config"), InstallDirectory >= 0) )
              {
                InstallDirectory = InitializeMgdEng(FileName);
              }
            }
          }
          else
          {
            operator delete(v10, 8u);
          }
        }
        else
        {
          InstallDirectory = -2147024888;
        }
      }
      else
      {
        LastError = GetLastError();
        InstallDirectory = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          InstallDirectory = LastError;
      }
    }
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  return (unsigned int)InstallDirectory;
}

```

## disassembly

```asm
0x18005cc00  mov     [rsp-8+arg_0], rbx
0x18005cc05  push    rbp
0x18005cc06  push    rsi
0x18005cc07  push    rdi
0x18005cc08  lea     rbp, [rsp-170h]
0x18005cc10  sub     rsp, 270h
0x18005cc17  mov     rax, cs:__security_cookie
0x18005cc1e  xor     rax, rsp
0x18005cc21  mov     [rbp+180h+var_20], rax
0x18005cc28  and     [rsp+280h+var_248], 0
0x18005cc2e  mov     rbx, r8
0x18005cc31  and     [rsp+280h+var_250], 0
0x18005cc36  mov     rsi, rdx
0x18005cc39  mov     edi, ecx
0x18005cc3b  mov     [rsp+280h+var_240], 104h
0x18005cc43  xor     edx, edx; Val
0x18005cc45  lea     rcx, [rsp+280h+FileName]; void *
0x18005cc4a  mov     r8d, 208h; Size
0x18005cc50  call    memset_0
0x18005cc55  mov     rax, [rsi]
0x18005cc58  mov     rcx, rsi
0x18005cc5b  mov     rax, [rax+8]
0x18005cc5f  call    cs:__guard_dispatch_icall_fptr
0x18005cc65  mov     cs:?g_MgdModuleContext@@3PEAXEA, rax; void * g_MgdModuleContext
0x18005cc6c  mov     rcx, rsi
0x18005cc6f  mov     rax, [rsi]
0x18005cc72  mov     rax, [rax]
0x18005cc75  call    cs:__guard_dispatch_icall_fptr
0x18005cc7b  mov     cs:?g_pHttpServer@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pHttpServer
0x18005cc82  lea     rdx, [rsp+280h+var_248]
0x18005cc87  mov     cs:?g_MgdModuleName@@3PEBGEB, rax; ushort const * const g_MgdModuleName
0x18005cc8e  mov     rcx, rbx
0x18005cc91  mov     rax, [rbx]
0x18005cc94  mov     rax, [rax+0A0h]
0x18005cc9b  call    cs:__guard_dispatch_icall_fptr
0x18005cca1  mov     ebx, eax
0x18005cca3  test    eax, eax
0x18005cca5  js      loc_18005CE47
0x18005ccab  mov     rcx, [rsp+280h+var_248]
0x18005ccb0  lea     r8, [rsp+280h+var_250]
0x18005ccb5  mov     edx, 4
0x18005ccba  mov     rax, [rcx]
0x18005ccbd  mov     rax, [rax+10h]
0x18005ccc1  call    cs:__guard_dispatch_icall_fptr
0x18005ccc7  mov     ebx, eax
0x18005ccc9  test    eax, eax
0x18005cccb  js      loc_18005CE47
0x18005ccd1  cmp     [rsp+280h+var_250], 0
0x18005ccd6  jnz     loc_18005CE47
0x18005ccdc  mov     rcx, [rsp+280h+var_248]
0x18005cce1  lea     r8, [rsp+280h+var_238]
0x18005cce6  mov     ebx, 1
0x18005cceb  mov     edx, ebx
0x18005cced  mov     rax, [rcx]
0x18005ccf0  mov     rax, [rax+18h]
0x18005ccf4  call    cs:__guard_dispatch_icall_fptr
0x18005ccfa  test    eax, eax
0x18005ccfc  js      short loc_18005CD0E
0x18005ccfe  mov     rax, [rsp+280h+var_238]
0x18005cd03  shr     rax, 0Ah
0x18005cd07  mov     cs:?g_MemoryLimitKB@@3_KA, rax; unsigned __int64 g_MemoryLimitKB
0x18005cd0e  cmp     cs:?g_dwIISVersion@@3KA, 0; ulong g_dwIISVersion
0x18005cd15  mov     cs:?g_IsAppPoolInIntegratedMode@@3HA, ebx; int g_IsAppPoolInIntegratedMode
0x18005cd1b  jnz     short loc_18005CD3D
0x18005cd1d  cmp     edi, 7
0x18005cd20  jnz     short loc_18005CD29
0x18005cd22  mov     edi, 70000h
0x18005cd27  jmp     short loc_18005CD37
0x18005cd29  cmp     edi, 50007h
0x18005cd2f  mov     eax, 70005h
0x18005cd34  cmovz   edi, eax
0x18005cd37  mov     cs:?g_dwIISVersion@@3KA, edi; ulong g_dwIISVersion
0x18005cd3d  xor     r9d, r9d; lpName
0x18005cd40  xor     r8d, r8d; bInitialState
0x18005cd43  mov     edx, ebx; bManualReset
0x18005cd45  xor     ecx, ecx; lpEventAttributes
0x18005cd47  call    cs:__imp_CreateEventW
0x18005cd4d  mov     cs:?g_hStopListeningFired@@3PEAXEA, rax; void * g_hStopListeningFired
0x18005cd54  test    rax, rax
0x18005cd57  jnz     short loc_18005CD72
0x18005cd59  call    cs:__imp_GetLastError
0x18005cd5f  movzx   ebx, ax
0x18005cd62  or      ebx, 80070000h
0x18005cd68  test    eax, eax
0x18005cd6a  cmovle  ebx, eax
0x18005cd6d  jmp     loc_18005CE47
0x18005cd72  mov     ecx, 8; unsigned __int64
0x18005cd77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005cd7c  mov     rdi, rax
0x18005cd7f  test    rax, rax
0x18005cd82  jz      loc_18005CE42
0x18005cd88  lea     rax, ??_7CMgdEngGlobalModule@@6B@; const CMgdEngGlobalModule::`vftable'
0x18005cd8f  mov     r8d, 20C02h
0x18005cd95  mov     [rdi], rax
0x18005cd98  mov     rcx, rsi
0x18005cd9b  mov     rdx, [rsi]
0x18005cd9e  mov     rax, [rdx+18h]
0x18005cda2  mov     rdx, rdi
0x18005cda5  call    cs:__guard_dispatch_icall_fptr
0x18005cdab  mov     ebx, eax
0x18005cdad  test    eax, eax
0x18005cdaf  jns     short loc_18005CDC3
0x18005cdb1  mov     edx, 8; unsigned __int64
0x18005cdb6  mov     rcx, rdi; void *
0x18005cdb9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005cdbe  jmp     loc_18005CE47
0x18005cdc3  call    ?Initialize@W3_MGD_APP_CONTEXT@@SAJXZ; W3_MGD_APP_CONTEXT::Initialize(void)
0x18005cdc8  mov     ebx, eax
0x18005cdca  test    eax, eax
0x18005cdcc  js      short loc_18005CE47
0x18005cdce  mov     rcx, [rsp+280h+var_248]
0x18005cdd3  lea     r9, [rsp+280h+var_240]
0x18005cdd8  lea     r8, [rsp+280h+FileName]
0x18005cddd  mov     edx, 4
0x18005cde2  mov     rax, [rcx]
0x18005cde5  mov     rax, [rax+20h]
0x18005cde9  call    cs:__guard_dispatch_icall_fptr
0x18005cdef  test    eax, eax
0x18005cdf1  js      short loc_18005CE03
0x18005cdf3  lea     rcx, [rsp+280h+FileName]; lpFileName
0x18005cdf8  call    cs:__imp_GetFileAttributesW
0x18005cdfe  cmp     eax, 0FFFFFFFFh
0x18005ce01  jnz     short loc_18005CE34
0x18005ce03  mov     edx, 104h; unsigned __int64
0x18005ce08  lea     rcx, [rsp+280h+FileName]; unsigned __int16 *
0x18005ce0d  call    ?GetInstallDirectory@@YAJPEAG_K@Z; GetInstallDirectory(ushort *,unsigned __int64)
0x18005ce12  mov     ebx, eax
0x18005ce14  test    eax, eax
0x18005ce16  js      short loc_18005CE47
0x18005ce18  lea     r8, aAspnetConfig; "\\aspnet.config"
0x18005ce1f  mov     edx, 104h; unsigned __int64
0x18005ce24  lea     rcx, [rsp+280h+FileName]; unsigned __int16 *
0x18005ce29  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005ce2e  mov     ebx, eax
0x18005ce30  test    eax, eax
0x18005ce32  js      short loc_18005CE47
0x18005ce34  lea     rcx, [rsp+280h+FileName]; pszFile
0x18005ce39  call    ?InitializeMgdEng@@YAJPEBG@Z; InitializeMgdEng(ushort const *)
0x18005ce3e  mov     ebx, eax
0x18005ce40  jmp     short loc_18005CE47
0x18005ce42  mov     ebx, 80070008h
0x18005ce47  mov     rcx, [rsp+280h+var_248]
0x18005ce4c  test    rcx, rcx
0x18005ce4f  jz      short loc_18005CE5E
0x18005ce51  mov     rax, [rcx]
0x18005ce54  mov     rax, [rax+8]
0x18005ce58  call    cs:__guard_dispatch_icall_fptr
0x18005ce5e  mov     eax, ebx
0x18005ce60  mov     rcx, [rbp+180h+var_20]
0x18005ce67  xor     rcx, rsp; StackCookie
0x18005ce6a  call    __security_check_cookie
0x18005ce6f  mov     rbx, [rsp+280h+arg_0]
0x18005ce77  add     rsp, 270h
0x18005ce7e  pop     rdi
0x18005ce7f  pop     rsi
0x18005ce80  pop     rbp
0x18005ce81  retn
```
