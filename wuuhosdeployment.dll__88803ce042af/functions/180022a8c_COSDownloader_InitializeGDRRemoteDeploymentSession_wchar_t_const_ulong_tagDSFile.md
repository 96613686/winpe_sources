# COSDownloader::InitializeGDRRemoteDeploymentSession(wchar_t const *,ulong,tagDSFile * *)

- ea: `0x180022a8c`
- end: `0x180022e41`
- name: `?InitializeGDRRemoteDeploymentSession@COSDownloader@@AEAAJPEB_WKPEAPEAUtagDSFile@@@Z`
- size: `949`
- prototype: `__int64 __fastcall(struct tagDSFile **this, const wchar_t *, int, struct tagDSFile **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021730`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000fba8`
- `0x180010f54`
- `0x18001a094`
- `0x18001a688`
- `0x180020e94`
- `0x180022a8c`
- `0x1800236c4`
- `0x18002e554`
- `0x18002e66c`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022d39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d47`

## string_xrefs

- `0x180022b5d`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180022d79`: `UpdatePriority`

## pseudocode

```c
__int64 __fastcall COSDownloader::InitializeGDRRemoteDeploymentSession(
        struct tagDSFile **this,
        const wchar_t *a2,
        int a3,
        struct tagDSFile **a4)
{
  __int64 DownloadProperties; // rax
  bool v7; // cl
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ecx
  wchar_t **v11; // rsi
  struct tagDSFile *v12; // rcx
  wchar_t *v13; // r14
  const wchar_t *v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rdx
  int started; // eax
  struct tagOptionalSessionInfo6 *v19; // r9
  int v20; // eax
  int v21; // eax
  int RemoteDeploymentSession; // eax
  void *v23; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v25; // rdx
  void *v27; // rbx
  HANDLE v28; // rax
  int v29; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  wchar_t **v34[5]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v35[2]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v36[14]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v38; // [rsp+E8h] [rbp-18h] BYREF
  struct tagDSFile *v39[14]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_QWORD *)v35 = a4;
  LODWORD(v38) = a3;
  memset(v39, 0, sizeof(v39));
  v39[1] = this[41];
  v39[4] = this[48];
  v39[0] = this[44];
  v39[2] = this[45];
  v39[3] = this[46];
  v39[7] = this[47];
  DownloadProperties = COSDownloader::GetDownloadProperties(this, v34);
  *(_OWORD *)((char *)&v39[8] + 4) = *(_OWORD *)DownloadProperties;
  *(_OWORD *)((char *)&v39[10] + 4) = *(_OWORD *)(DownloadProperties + 16);
  HIDWORD(v39[12]) = *(_DWORD *)(DownloadProperties + 32);
  LODWORD(v39[13]) = *((_DWORD *)this + 118) == 1;
  if ( (unsigned int)AreTestKeysAllowed(v7) )
  {
    LODWORD(lpMem) = 0;
    v9 = RegQueryDwordValue(
           v8,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
           L"UHOSSessionInfoFlagsOverride",
           &lpMem);
    v10 = (int)v39[8];
    if ( v9 >= 0 )
      v10 = (int)lpMem;
    LODWORD(v39[8]) = v10;
  }
  v11 = (wchar_t **)(this + 17);
  v12 = this[17];
  if ( v12 )
  {
    (*(void (__fastcall **)(struct tagDSFile *))(*(_QWORD *)v12 + 16LL))(v12);
    *v11 = 0;
  }
  v13 = (wchar_t *)this[35];
  v14 = (const wchar_t *)this[43];
  if ( this == (struct tagDSFile **)-136LL )
  {
    v15 = -2147467261;
    v16 = 2147500035LL;
    v17 = 85;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
      (const char *)v16,
      v30);
LABEL_23:
    v25 = 2006;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)v15,
      v31);
    return v15;
  }
  started = OSDeploymentRemote::RemoteDeploymentSessionWrapper::StartRemoteProcess(
              (OSDeploymentRemote::RemoteDeploymentSessionWrapper *)(this + 60),
              HIDWORD(v39[8]) != 0);
  v15 = started;
  if ( started < 0 )
  {
    v16 = (unsigned int)started;
    v17 = 88;
    goto LABEL_9;
  }
  memset(v36, 0, sizeof(v36));
  v20 = OSDeploymentHelper::BuildOptionalSessionInfo((OSDeploymentHelper *)6, (unsigned int)v39, v36, v19);
  v15 = v20;
  if ( v20 < 0 )
  {
    v16 = (unsigned int)v20;
    v17 = 93;
    goto LABEL_9;
  }
  if ( v36[6] )
    v13 = v36[6];
  lpMem = 0;
  v21 = OSDeploymentHelper::PrepareSandboxForSessionCreation_Legacy(
          v13,
          a2,
          v14,
          (const wchar_t *)(unsigned int)v38,
          v35[0],
          v39,
          v36,
          (const struct tagOptionalSessionInfo6 *)&lpMem,
          v34[0]);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)v21,
      v32);
LABEL_21:
    v23 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
    }
    goto LABEL_23;
  }
  v38 = 0;
  RemoteDeploymentSession = OSDeploymentRemote::RemoteDeploymentSessionWrapper::CreateRemoteDeploymentSession(
                              (OSDeploymentRemote::RemoteDeploymentSessionWrapper *)(this + 60),
                              (const wchar_t *)lpMem,
                              v13,
                              (struct tagOptionalSessionInfo6 *)v39,
                              (struct IRemoteDeploymentSession **)&v38);
  v15 = RemoteDeploymentSession;
  if ( RemoteDeploymentSession < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Remote\\RemoteDeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)RemoteDeploymentSession,
      v33);
    if ( v38 )
      (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_21;
  }
  *v11 = v38;
  v27 = lpMem;
  if ( lpMem )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
  }
  if ( !*v11 )
  {
    v15 = -2145124348;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x735,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80240004LL,
      v33);
    v25 = 2009;
    goto LABEL_24;
  }
  *(_QWORD *)v35 = L"UpdatePriority";
  v38 = (wchar_t *)(*((_DWORD *)this + 115) == 1);
  WUTrace(0, 0, 4096, 5);
  v34[0] = (wchar_t **)this;
  v34[1] = (wchar_t **)v35;
  v34[2] = &v38;
  v29 = WUComTimeout::ComTimeout::MakeComCall__lambda_bd7de044fd6607a1d7e3b3c9840c6c74___(v34);
  if ( v29 < 0 )
    WUTrace(0, 0, 4096, 5);
  return 0;
}

```

## disassembly

```asm
0x180022a8c  push    rbp
0x180022a8e  push    rbx
0x180022a8f  push    rsi
0x180022a90  push    rdi
0x180022a91  push    r12
0x180022a93  push    r13
0x180022a95  push    r14
0x180022a97  push    r15
0x180022a99  lea     rbp, [rsp-78h]
0x180022a9e  sub     rsp, 178h
0x180022aa5  mov     rax, cs:__security_cookie
0x180022aac  xor     rax, rsp
0x180022aaf  mov     [rbp+0B0h+var_50], rax
0x180022ab3  mov     qword ptr [rsp+1B0h+var_148], r9
0x180022ab8  mov     dword ptr [rbp+0B0h+var_C8], r8d
0x180022abc  mov     r13, rdx
0x180022abf  mov     rdi, rcx
0x180022ac2  xor     edx, edx; Val
0x180022ac4  lea     r8d, [rdx+70h]; Size
0x180022ac8  lea     rcx, [rbp+0B0h+var_C0]; void *
0x180022acc  call    memset
0x180022ad1  mov     rax, [rdi+148h]
0x180022ad8  mov     [rbp+0B0h+var_B8], rax
0x180022adc  mov     rax, [rdi+180h]
0x180022ae3  mov     [rbp+0B0h+var_A0], rax
0x180022ae7  mov     rax, [rdi+160h]
0x180022aee  mov     [rbp+0B0h+var_C0], rax
0x180022af2  mov     rax, [rdi+168h]
0x180022af9  mov     [rbp+0B0h+var_B0], rax
0x180022afd  mov     rax, [rdi+170h]
0x180022b04  mov     [rbp+0B0h+var_A8], rax
0x180022b08  mov     rax, [rdi+178h]
0x180022b0f  mov     [rbp+0B0h+var_88], rax
0x180022b13  lea     rdx, [rsp+1B0h+var_170]
0x180022b18  mov     rcx, rdi
0x180022b1b  call    ?GetDownloadProperties@COSDownloader@@QEAA?BUtagSessionDownloadProperties@@XZ; COSDownloader::GetDownloadProperties(void)
0x180022b20  movups  xmm0, xmmword ptr [rax]
0x180022b23  movups  [rbp+0B0h+var_7C], xmm0
0x180022b27  movups  xmm1, xmmword ptr [rax+10h]
0x180022b2b  movups  [rbp+0B0h+var_6C], xmm1
0x180022b2f  mov     eax, [rax+20h]
0x180022b32  mov     [rbp+0B0h+var_5C], eax
0x180022b35  xor     ebx, ebx
0x180022b37  mov     eax, ebx
0x180022b39  cmp     dword ptr [rdi+1D8h], 1
0x180022b40  setz    al
0x180022b43  mov     [rbp+0B0h+var_58], eax
0x180022b46  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180022b4b  test    eax, eax
0x180022b4d  jz      short loc_180022B75
0x180022b4f  mov     dword ptr [rbp+0B0h+lpMem], ebx
0x180022b52  lea     r9, [rbp+0B0h+lpMem]
0x180022b56  lea     r8, ?c_szRegUHOSSessionInfoFlagsOverride@@3QB_WB; "UHOSSessionInfoFlagsOverride"
0x180022b5d  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022b64  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x180022b69  mov     ecx, [rbp+0B0h+var_80]
0x180022b6c  test    eax, eax
0x180022b6e  cmovns  ecx, dword ptr [rbp+0B0h+lpMem]
0x180022b72  mov     [rbp+0B0h+var_80], ecx
0x180022b75  lea     r15, [rdi+1E0h]
0x180022b7c  lea     rsi, [rdi+88h]
0x180022b83  mov     rcx, [rsi]
0x180022b86  test    rcx, rcx
0x180022b89  jz      short loc_180022B9A
0x180022b8b  mov     rax, [rcx]
0x180022b8e  mov     rax, [rax+10h]
0x180022b92  call    _guard_dispatch_icall
0x180022b97  mov     [rsi], rbx
0x180022b9a  mov     r14, [rdi+118h]
0x180022ba1  mov     r12, [rdi+158h]
0x180022ba8  test    rsi, rsi
0x180022bab  jnz     short loc_180022BD0
0x180022bad  mov     ebx, 80004003h
0x180022bb2  mov     r9d, ebx; char *
0x180022bb5  lea     edx, [rsi+55h]; void *
0x180022bb8  mov     rcx, [rbp+0B8h]; this
0x180022bbf  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180022bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022bcb  jmp     loc_180022D07
0x180022bd0  cmp     dword ptr [rbp+0B0h+var_7C], ebx
0x180022bd3  setnz   dl; bool
0x180022bd6  mov     rcx, r15; this
0x180022bd9  call    ?StartRemoteProcess@RemoteDeploymentSessionWrapper@OSDeploymentRemote@@AEAAJ_N@Z; OSDeploymentRemote::RemoteDeploymentSessionWrapper::StartRemoteProcess(bool)
0x180022bde  mov     ebx, eax
0x180022be0  test    eax, eax
0x180022be2  jns     short loc_180022BEE
0x180022be4  mov     r9d, eax
0x180022be7  mov     edx, 58h ; 'X'
0x180022bec  jmp     short loc_180022BB8
0x180022bee  xor     edx, edx; Val
0x180022bf0  lea     r8d, [rdx+70h]; Size
0x180022bf4  lea     rcx, [rsp+1B0h+var_140]; void *
0x180022bf9  call    memset
0x180022bfe  lea     r8, [rsp+1B0h+var_140]; void *
0x180022c03  lea     rdx, [rbp+0B0h+var_C0]; unsigned int
0x180022c07  mov     ecx, 6; this
0x180022c0c  call    ?BuildOptionalSessionInfo@OSDeploymentHelper@@YAJKPEAXAEAUtagOptionalSessionInfo6@@@Z; OSDeploymentHelper::BuildOptionalSessionInfo(ulong,void *,tagOptionalSessionInfo6 &)
0x180022c11  mov     ebx, eax
0x180022c13  test    eax, eax
0x180022c15  jns     short loc_180022C21
0x180022c17  mov     r9d, eax
0x180022c1a  mov     edx, 5Dh ; ']'
0x180022c1f  jmp     short loc_180022BB8
0x180022c21  mov     rax, [rbp+0B0h+var_110]
0x180022c25  test    rax, rax
0x180022c28  cmovnz  r14, rax
0x180022c2c  mov     [rbp+0B0h+lpMem], 0
0x180022c34  lea     rax, [rbp+0B0h+lpMem]
0x180022c38  mov     [rsp+1B0h+var_178], rax; struct tagOptionalSessionInfo6 *
0x180022c3d  lea     rax, [rsp+1B0h+var_140]
0x180022c42  mov     [rsp+1B0h+var_180], rax; void *
0x180022c47  lea     rax, [rbp+0B0h+var_C0]
0x180022c4b  mov     [rsp+1B0h+var_188], rax; struct tagDSFile **
0x180022c50  mov     rax, qword ptr [rsp+1B0h+var_148]
0x180022c55  mov     [rsp+1B0h+var_190], rax; int
0x180022c5a  mov     r9d, dword ptr [rbp+0B0h+var_C8]; wchar_t *
0x180022c5e  mov     r8, r12; wchar_t *
0x180022c61  mov     rdx, r13; wchar_t *
0x180022c64  mov     rcx, r14; this
0x180022c67  call    ?PrepareSandboxForSessionCreation_Legacy@OSDeploymentHelper@@YAJPEB_W00KPEAPEAUtagDSFile@@PEAXAEBUtagOptionalSessionInfo6@@PEAPEA_W@Z; OSDeploymentHelper::PrepareSandboxForSessionCreation_Legacy(wchar_t const *,wchar_t const *,wchar_t const *,ulong,tagDSFile * *,void *,tagOptionalSessionInfo6 const &,wchar_t * *)
0x180022c6c  mov     ebx, eax
0x180022c6e  xor     r12d, r12d
0x180022c71  test    eax, eax
0x180022c73  jns     short loc_180022C92
0x180022c75  mov     rcx, [rbp+0B8h]; this
0x180022c7c  mov     r9d, eax; char *
0x180022c7f  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180022c86  lea     edx, [r12+6Bh]; void *
0x180022c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022c90  jmp     short loc_180022CEA
0x180022c92  mov     [rbp+0B0h+var_C8], r12
0x180022c96  lea     rax, [rbp+0B0h+var_C8]
0x180022c9a  mov     [rsp+1B0h+var_190], rax; int
0x180022c9f  lea     r9, [rbp+0B0h+var_C0]; struct tagOptionalSessionInfo6 *
0x180022ca3  mov     r8, r14; wchar_t *
0x180022ca6  mov     rdx, [rbp+0B0h+lpMem]; wchar_t *
0x180022caa  mov     rcx, r15; this
0x180022cad  call    ?CreateRemoteDeploymentSession@RemoteDeploymentSessionWrapper@OSDeploymentRemote@@AEAAJPEB_W0AEAUtagOptionalSessionInfo6@@PEAPEAUIRemoteDeploymentSession@@@Z; OSDeploymentRemote::RemoteDeploymentSessionWrapper::CreateRemoteDeploymentSession(wchar_t const *,wchar_t const *,tagOptionalSessionInfo6 &,IRemoteDeploymentSession * *)
0x180022cb2  mov     ebx, eax
0x180022cb4  test    eax, eax
0x180022cb6  jns     short loc_180022D29
0x180022cb8  mov     rcx, [rbp+0B8h]; this
0x180022cbf  mov     r9d, eax; char *
0x180022cc2  lea     r8, aCW1SSrcClientE; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180022cc9  mov     edx, 6Fh ; 'o'; void *
0x180022cce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022cd3  nop
0x180022cd4  mov     rcx, [rbp+0B0h+var_C8]
0x180022cd8  test    rcx, rcx
0x180022cdb  jz      short loc_180022CEA
0x180022cdd  mov     rax, [rcx]
0x180022ce0  mov     rax, [rax+10h]
0x180022ce4  call    _guard_dispatch_icall
0x180022ce9  nop
0x180022cea  mov     rdi, [rbp+0B0h+lpMem]
0x180022cee  test    rdi, rdi
0x180022cf1  jz      short loc_180022D07
0x180022cf3  call    cs:__imp_GetProcessHeap
0x180022cf9  mov     r8, rdi; lpMem
0x180022cfc  xor     edx, edx; dwFlags
0x180022cfe  mov     rcx, rax; hHeap
0x180022d01  call    cs:__imp_HeapFree
0x180022d07  mov     edx, 7D6h; void *
0x180022d0c  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180022d13  mov     r9d, ebx; char *
0x180022d16  mov     rcx, [rbp+0B8h]; this
0x180022d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d22  mov     eax, ebx
0x180022d24  jmp     loc_180022E21
0x180022d29  mov     rax, [rbp+0B0h+var_C8]
0x180022d2d  mov     [rsi], rax
0x180022d30  mov     rbx, [rbp+0B0h+lpMem]
0x180022d34  test    rbx, rbx
0x180022d37  jz      short loc_180022D4D
0x180022d39  call    cs:__imp_GetProcessHeap
0x180022d3f  mov     rcx, rax; hHeap
0x180022d42  mov     r8, rbx; lpMem
0x180022d45  xor     edx, edx; dwFlags
0x180022d47  call    cs:__imp_HeapFree
0x180022d4d  cmp     [rsi], r12
0x180022d50  jnz     short loc_180022D79
0x180022d52  mov     rcx, [rbp+0B8h]; this
0x180022d59  mov     ebx, 80240004h
0x180022d5e  mov     r9d, ebx; char *
0x180022d61  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180022d68  mov     edx, 735h; void *
0x180022d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d72  mov     edx, 7D9h
0x180022d77  jmp     short loc_180022D0C
0x180022d79  lea     rcx, aUpdatepriority; "UpdatePriority"
0x180022d80  mov     qword ptr [rsp+1B0h+var_148], rcx
0x180022d85  mov     rax, r12
0x180022d88  cmp     dword ptr [rdi+1CCh], 1
0x180022d8f  setz    al
0x180022d92  mov     [rbp+0B0h+var_C8], rax
0x180022d96  mov     [rsp+1B0h+var_178], rax
0x180022d9b  mov     [rsp+1B0h+var_180], rcx
0x180022da0  lea     rax, aCallingSetattr; "Calling SetAttributeInt [%ws, %lld]"
0x180022da7  mov     [rsp+1B0h+var_188], rax
0x180022dac  mov     [rsp+1B0h+var_190], r12
0x180022db1  mov     ebx, 5
0x180022db6  mov     r9d, ebx
0x180022db9  mov     esi, 1000h
0x180022dbe  mov     r8d, esi
0x180022dc1  xor     edx, edx
0x180022dc3  xor     ecx, ecx
0x180022dc5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180022dca  mov     [rsp+1B0h+var_170], rdi
0x180022dcf  lea     rax, [rsp+1B0h+var_148]
0x180022dd4  mov     [rsp+1B0h+var_168], rax
0x180022dd9  lea     rax, [rbp+0B0h+var_C8]
0x180022ddd  mov     [rsp+1B0h+var_160], rax
0x180022de2  lea     rcx, [rsp+1B0h+var_170]
0x180022de7  call    WUComTimeout__ComTimeout__MakeComCall__lambda_bd7de044fd6607a1d7e3b3c9840c6c74___
0x180022dec  test    eax, eax
0x180022dee  jns     short loc_180022E1F
0x180022df0  lea     rdx, aSetattributein; "SetAttributeInt API not available"
0x180022df7  lea     rcx, aFailedToSetAtt_0; "Failed to set Attribute"
0x180022dfe  cmp     eax, 80004002h
0x180022e03  cmovz   rcx, rdx
0x180022e07  mov     [rsp+1B0h+var_188], rcx
0x180022e0c  mov     dword ptr [rsp+1B0h+var_190], eax
0x180022e10  mov     r9d, ebx
0x180022e13  mov     r8d, esi
0x180022e16  xor     edx, edx
0x180022e18  xor     ecx, ecx
0x180022e1a  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180022e1f  xor     eax, eax
0x180022e21  mov     rcx, [rbp+0B0h+var_50]
0x180022e25  xor     rcx, rsp; StackCookie
0x180022e28  call    __security_check_cookie
0x180022e2d  add     rsp, 178h
0x180022e34  pop     r15
0x180022e36  pop     r14
0x180022e38  pop     r13
0x180022e3a  pop     r12
0x180022e3c  pop     rdi
0x180022e3d  pop     rsi
0x180022e3e  pop     rbx
0x180022e3f  pop     rbp
0x180022e40  retn
```
