# StorageService::ExecuteDehydrateUserFiles(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x180021e80`
- end: `0x180022228`
- name: `?ExecuteDehydrateUserFiles@StorageService@@QEAAJPEAUtagSAFEARRAY@@0@Z`
- size: `936`
- prototype: `int(StorageService *__hidden this, struct tagSAFEARRAY *, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x1800373e0`

## callees

- `0x180012734`
- `0x180019d4c`
- `0x18001dcf4`
- `0x18001fcac`
- `0x180021e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021ff8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021ff8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022139`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022139`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021fc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002204e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002217f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002204e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002217f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022154`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022154`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022032`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022032`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800220ef`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800220ef`
- `RPCRT4!RpcRevertToSelf` at `0x180021eee`
- `RPCRT4!RpcRevertToSelf` at `0x1800221ed`
- `RPCRT4!RpcRevertToSelf` at `0x180022202`
- `RPCRT4!RpcRevertToSelf` at `0x180021eee`
- `RPCRT4!RpcRevertToSelf` at `0x1800221ed`
- `RPCRT4!RpcRevertToSelf` at `0x180022202`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180021f49`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180021f8d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180021f49`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180021f8d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180021f2d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180021f6e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180021f2d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180021f6e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021ebe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021f06`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021ebe`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180021f06`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221b3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221cc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221b3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800221cc`
- `cldapi!CfDehydratePlaceholderEx` at `0x18002207c`
- `cldapi!CfDehydratePlaceholderEx` at `0x1800220cc`
- `cldapi!CfDehydratePlaceholderEx` at `0x18002207c`
- `cldapi!CfDehydratePlaceholderEx` at `0x1800220cc`
- `cldapi!CfSetPinState` at `0x180022096`
- `cldapi!CfSetPinState` at `0x180022096`

## string_xrefs

- `0x180021ecf`: `onecore\drivers\storage\storsvc\service\storageservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall StorageService::ExecuteDehydrateUserFiles(
        StorageService *this,
        struct tagSAFEARRAY *a2,
        struct tagSAFEARRAY *a3)
{
  HRESULT LBound; // ebx
  __int64 v6; // rdx
  char v7; // cl
  HANDLE EventW; // r13
  LONG i; // r14d
  HANDLE FileW; // rax
  HANDLE v12; // rbx
  int v13; // ecx
  DWORD v14; // edx
  DWORD v15; // eax
  char v16; // al
  char v17; // al
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-49h]
  _BYTE v19[4]; // [rsp+40h] [rbp-29h] BYREF
  LONG plUbound; // [rsp+44h] [rbp-25h] BYREF
  void *v21; // [rsp+48h] [rbp-21h] BYREF
  LONG plLbound; // [rsp+50h] [rbp-19h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-11h] BYREF
  LONG v24; // [rsp+60h] [rbp-9h] BYREF
  LONG v25; // [rsp+64h] [rbp-5h] BYREF
  void *ppvData; // [rsp+68h] [rbp-1h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  StorageService *NumberOfBytesTransferred; // [rsp+D0h] [rbp+67h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+E8h] [rbp+7Fh] BYREF

  NumberOfBytesTransferred = this;
  AutoRpcImpersonateClient(v19);
  ppvData = 0;
  LBound = SafeArrayAccessData(a2, &ppvData);
  if ( LBound < 0 )
  {
    v6 = 1897;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageservice.cpp",
      (const char *)(unsigned int)LBound,
      dwCreationDisposition);
    v7 = v19[0];
    v19[0] = 0;
    if ( v7 )
      RpcRevertToSelf();
    return (unsigned int)LBound;
  }
  v21 = 0;
  LBound = SafeArrayAccessData(a3, &v21);
  if ( LBound < 0 )
  {
    v6 = 1901;
    goto LABEL_3;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(a2, 1u, &plLbound);
  if ( LBound < 0 )
  {
    v6 = 1904;
    goto LABEL_3;
  }
  LBound = SafeArrayGetUBound(a2, 1u, &plUbound);
  if ( LBound < 0 )
  {
    v6 = 1905;
    goto LABEL_3;
  }
  v24 = 0;
  v25 = 0;
  LBound = SafeArrayGetLBound(a3, 1u, &v24);
  if ( LBound < 0 )
  {
    v6 = 1908;
    goto LABEL_3;
  }
  LBound = SafeArrayGetUBound(a3, 1u, &v25);
  if ( LBound < 0 )
  {
    v6 = 1909;
    goto LABEL_3;
  }
  if ( v24 == plLbound && v25 == plUbound )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    for ( i = plLbound; i <= plUbound; ++i )
    {
      hFile = 0;
      memset(&Overlapped, 0, sizeof(Overlapped));
      ResetEvent(EventW);
      Overlapped.hEvent = EventW;
      FileW = CreateFileW(*((LPCWSTR *)ppvData + i), 0x80u, 1u, 0, 3u, 0x40000000u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        FileW);
      v12 = hFile;
      if ( hFile != (HANDLE)-1LL )
      {
        dwCreationDisposition = 1;
        v13 = CfDehydratePlaceholderEx(hFile, 0, 0x7FFFFFFFFFFFFFFFLL, 0);
        if ( v13 == -2147024504 )
        {
          if ( (int)CfSetPinState(v12, 0, 0, 0) < 0 )
          {
            *((_DWORD *)v21 + i) = -2147024504;
            goto LABEL_36;
          }
          dwCreationDisposition = 1;
          v13 = CfDehydratePlaceholderEx(v12, 0, 0x7FFFFFFFFFFFFFFFLL, 0);
        }
        if ( v13 != -2147023899 )
        {
          *((_DWORD *)v21 + i) = v13;
          goto LABEL_36;
        }
        FileSize.QuadPart = 0;
        if ( GetFileSizeEx(v12, &FileSize) )
        {
          v14 = 10000;
          if ( (unsigned int)(FileSize.QuadPart / 5000) > 0x2710 )
            v14 = FileSize.QuadPart / 5000;
          v15 = WaitForSingleObject(EventW, v14);
          if ( v15 )
          {
            if ( v15 == 258 )
            {
              *((_DWORD *)v21 + i) = 1460;
              goto LABEL_36;
            }
          }
          else
          {
            LODWORD(NumberOfBytesTransferred) = 0;
            if ( GetOverlappedResult(v12, &Overlapped, (LPDWORD)&NumberOfBytesTransferred, 0) )
            {
              *((_DWORD *)v21 + i) = 0;
              goto LABEL_36;
            }
          }
        }
      }
      *((_DWORD *)v21 + i) = GetLastError();
LABEL_36:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    }
    LBound = SafeArrayUnaccessData(a2);
    if ( LBound < 0 )
    {
      v6 = 2006;
      goto LABEL_3;
    }
    LBound = SafeArrayUnaccessData(a3);
    if ( LBound < 0 )
    {
      v6 = 2007;
      goto LABEL_3;
    }
    v16 = v19[0];
    v19[0] = 0;
    if ( v16 )
      RpcRevertToSelf();
    return 0;
  }
  else
  {
    v17 = v19[0];
    v19[0] = 0;
    if ( v17 )
      RpcRevertToSelf();
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180021e80  mov     [rsp-8+arg_8], rbx
0x180021e85  mov     [rsp-8+NumberOfBytesTransferred], rcx
0x180021e8a  push    rbp
0x180021e8b  push    rsi
0x180021e8c  push    rdi
0x180021e8d  push    r12
0x180021e8f  push    r13
0x180021e91  push    r14
0x180021e93  push    r15
0x180021e95  lea     rbp, [rsp-27h]
0x180021e9a  sub     rsp, 90h
0x180021ea1  mov     r15, r8
0x180021ea4  mov     r12, rdx
0x180021ea7  lea     rcx, [rbp+57h+var_80]
0x180021eab  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x180021eb0  nop
0x180021eb1  xor     esi, esi
0x180021eb3  mov     [rbp+57h+ppvData], rsi
0x180021eb7  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180021ebb  mov     rcx, r12; psa
0x180021ebe  call    cs:__imp_SafeArrayAccessData
0x180021ec4  mov     ebx, eax
0x180021ec6  test    eax, eax
0x180021ec8  jns     short loc_180021EFB
0x180021eca  mov     edx, 769h; void *
0x180021ecf  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180021ed6  mov     r9d, ebx; char *
0x180021ed9  mov     rcx, [rbp+5Fh]; this
0x180021edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ee2  nop
0x180021ee3  mov     cl, [rbp+57h+var_80]
0x180021ee6  mov     [rbp+57h+var_80], sil
0x180021eea  test    cl, cl
0x180021eec  jz      short loc_180021EF4
0x180021eee  call    cs:__imp_RpcRevertToSelf
0x180021ef4  mov     eax, ebx
0x180021ef6  jmp     loc_18002220D
0x180021efb  mov     [rbp+57h+var_78], rsi
0x180021eff  lea     rdx, [rbp+57h+var_78]; ppvData
0x180021f03  mov     rcx, r15; psa
0x180021f06  call    cs:__imp_SafeArrayAccessData
0x180021f0c  mov     ebx, eax
0x180021f0e  test    eax, eax
0x180021f10  jns     short loc_180021F19
0x180021f12  mov     edx, 76Dh
0x180021f17  jmp     short loc_180021ECF
0x180021f19  mov     [rbp+57h+plLbound], esi
0x180021f1c  mov     [rbp+57h+plUbound], esi
0x180021f1f  lea     r8, [rbp+57h+plLbound]; plLbound
0x180021f23  mov     edi, 1
0x180021f28  mov     edx, edi; nDim
0x180021f2a  mov     rcx, r12; psa
0x180021f2d  call    cs:__imp_SafeArrayGetLBound
0x180021f33  mov     ebx, eax
0x180021f35  test    eax, eax
0x180021f37  jns     short loc_180021F40
0x180021f39  mov     edx, 770h
0x180021f3e  jmp     short loc_180021ECF
0x180021f40  lea     r8, [rbp+57h+plUbound]; plUbound
0x180021f44  mov     edx, edi; nDim
0x180021f46  mov     rcx, r12; psa
0x180021f49  call    cs:__imp_SafeArrayGetUBound
0x180021f4f  mov     ebx, eax
0x180021f51  test    eax, eax
0x180021f53  jns     short loc_180021F5F
0x180021f55  mov     edx, 771h
0x180021f5a  jmp     loc_180021ECF
0x180021f5f  mov     [rbp+57h+var_60], esi
0x180021f62  mov     [rbp+57h+var_5C], esi
0x180021f65  lea     r8, [rbp+57h+var_60]; plLbound
0x180021f69  mov     edx, edi; nDim
0x180021f6b  mov     rcx, r15; psa
0x180021f6e  call    cs:__imp_SafeArrayGetLBound
0x180021f74  mov     ebx, eax
0x180021f76  test    eax, eax
0x180021f78  jns     short loc_180021F84
0x180021f7a  mov     edx, 774h
0x180021f7f  jmp     loc_180021ECF
0x180021f84  lea     r8, [rbp+57h+var_5C]; plUbound
0x180021f88  mov     edx, edi; nDim
0x180021f8a  mov     rcx, r15; psa
0x180021f8d  call    cs:__imp_SafeArrayGetUBound
0x180021f93  mov     ebx, eax
0x180021f95  test    eax, eax
0x180021f97  jns     short loc_180021FA3
0x180021f99  mov     edx, 775h
0x180021f9e  jmp     loc_180021ECF
0x180021fa3  mov     eax, [rbp+57h+plLbound]
0x180021fa6  cmp     [rbp+57h+var_60], eax
0x180021fa9  jnz     loc_1800221F7
0x180021faf  mov     eax, [rbp+57h+plUbound]
0x180021fb2  cmp     [rbp+57h+var_5C], eax
0x180021fb5  jnz     loc_1800221F7
0x180021fbb  xor     r9d, r9d; lpName
0x180021fbe  xor     r8d, r8d; bInitialState
0x180021fc1  xor     edx, edx; bManualReset
0x180021fc3  xor     ecx, ecx; lpEventAttributes
0x180021fc5  call    cs:__imp_CreateEventW
0x180021fcb  mov     r13, rax
0x180021fce  mov     r14d, [rbp+57h+plLbound]
0x180021fd2  cmp     r14d, [rbp+57h+plUbound]
0x180021fd6  jg      loc_1800221B0
0x180021fdc  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180021fe6  mov     [rbp+57h+hFile], rsi
0x180021fea  xorps   xmm0, xmm0
0x180021fed  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180021ff1  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180021ff5  mov     rcx, r13; hEvent
0x180021ff8  call    cs:__imp_ResetEvent
0x180021ffe  mov     [rbp+57h+Overlapped.hEvent], r13
0x180022002  movsxd  rsi, r14d
0x180022005  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18002200e  mov     [rsp+0C0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180022016  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002201e  xor     r9d, r9d; lpSecurityAttributes
0x180022021  mov     edx, 80h; dwDesiredAccess
0x180022026  lea     r8d, [r9+1]; dwShareMode
0x18002202a  mov     rcx, [rbp+57h+ppvData]
0x18002202e  mov     rcx, [rcx+rsi*8]; lpFileName
0x180022032  call    cs:__imp_CreateFileW
0x180022038  mov     rdx, rax
0x18002203b  lea     rcx, [rbp+57h+hFile]
0x18002203f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180022044  mov     rbx, [rbp+57h+hFile]
0x180022048  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002204c  jnz     short loc_180022060
0x18002204e  call    cs:__imp_GetLastError
0x180022054  mov     rcx, [rbp+57h+var_78]
0x180022058  mov     [rcx+rsi*4], eax
0x18002205b  jmp     loc_180022195
0x180022060  xor     edx, edx
0x180022062  lea     rax, [rbp+57h+Overlapped]
0x180022066  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax
0x18002206b  mov     [rsp+0C0h+dwCreationDisposition], 1
0x180022073  xor     r9d, r9d
0x180022076  mov     r8, rdi
0x180022079  mov     rcx, rbx
0x18002207c  call    cs:__imp_CfDehydratePlaceholderEx
0x180022082  mov     ecx, eax
0x180022084  cmp     eax, 80070188h
0x180022089  jnz     short loc_1800220D4
0x18002208b  xor     r9d, r9d
0x18002208e  xor     r8d, r8d
0x180022091  xor     edx, edx
0x180022093  mov     rcx, rbx
0x180022096  call    cs:__imp_CfSetPinState
0x18002209c  test    eax, eax
0x18002209e  jns     short loc_1800220B0
0x1800220a0  mov     rax, [rbp+57h+var_78]
0x1800220a4  mov     dword ptr [rax+rsi*4], 80070188h
0x1800220ab  jmp     loc_180022195
0x1800220b0  xor     edx, edx
0x1800220b2  lea     rax, [rbp+57h+Overlapped]
0x1800220b6  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rax
0x1800220bb  mov     [rsp+0C0h+dwCreationDisposition], 1
0x1800220c3  xor     r9d, r9d
0x1800220c6  mov     r8, rdi
0x1800220c9  mov     rcx, rbx
0x1800220cc  call    cs:__imp_CfDehydratePlaceholderEx
0x1800220d2  mov     ecx, eax
0x1800220d4  cmp     ecx, 800703E5h
0x1800220da  jnz     loc_18002218E
0x1800220e0  mov     qword ptr [rbp+57h+FileSize], 0
0x1800220e8  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800220ec  mov     rcx, rbx; hFile
0x1800220ef  call    cs:__imp_GetFileSizeEx
0x1800220f5  test    eax, eax
0x1800220f7  jnz     short loc_18002210B
0x1800220f9  call    cs:__imp_GetLastError
0x1800220ff  mov     rcx, [rbp+57h+var_78]
0x180022103  mov     [rcx+rsi*4], eax
0x180022106  jmp     loc_180022195
0x18002210b  mov     rax, 346DC5D63886594Bh
0x180022115  imul    qword ptr [rbp+57h+FileSize]
0x180022119  mov     rcx, rdx
0x18002211c  sar     rcx, 0Ah
0x180022120  mov     rax, rcx
0x180022123  shr     rax, 3Fh
0x180022127  add     rcx, rax
0x18002212a  mov     eax, 2710h
0x18002212f  mov     edx, eax
0x180022131  cmp     ecx, eax
0x180022133  cmova   edx, ecx; dwMilliseconds
0x180022136  mov     rcx, r13; hHandle
0x180022139  call    cs:__imp_WaitForSingleObject
0x18002213f  test    eax, eax
0x180022141  jnz     short loc_18002216B
0x180022143  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], eax
0x180022146  xor     r9d, r9d; bWait
0x180022149  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002214d  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180022151  mov     rcx, rbx; hFile
0x180022154  call    cs:__imp_GetOverlappedResult
0x18002215a  test    eax, eax
0x18002215c  jz      short loc_18002217F
0x18002215e  mov     rax, [rbp+57h+var_78]
0x180022162  mov     dword ptr [rax+rsi*4], 0
0x180022169  jmp     short loc_180022195
0x18002216b  cmp     eax, 102h
0x180022170  jnz     short loc_18002217F
0x180022172  mov     rax, [rbp+57h+var_78]
0x180022176  mov     dword ptr [rax+rsi*4], 5B4h
0x18002217d  jmp     short loc_180022195
0x18002217f  call    cs:__imp_GetLastError
0x180022185  mov     rcx, [rbp+57h+var_78]
0x180022189  mov     [rcx+rsi*4], eax
0x18002218c  jmp     short loc_180022195
0x18002218e  mov     rax, [rbp+57h+var_78]
0x180022192  mov     [rax+rsi*4], ecx
0x180022195  lea     rcx, [rbp+57h+hFile]
0x180022199  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002219e  inc     r14d
0x1800221a1  cmp     r14d, [rbp+57h+plUbound]
0x1800221a5  mov     esi, 0
0x1800221aa  jle     loc_180021FE6
0x1800221b0  mov     rcx, r12; psa
0x1800221b3  call    cs:__imp_SafeArrayUnaccessData
0x1800221b9  mov     ebx, eax
0x1800221bb  test    eax, eax
0x1800221bd  jns     short loc_1800221C9
0x1800221bf  mov     edx, 7D6h
0x1800221c4  jmp     loc_180021ECF
0x1800221c9  mov     rcx, r15; psa
0x1800221cc  call    cs:__imp_SafeArrayUnaccessData
0x1800221d2  mov     ebx, eax
0x1800221d4  test    eax, eax
0x1800221d6  jns     short loc_1800221E2
0x1800221d8  mov     edx, 7D7h
0x1800221dd  jmp     loc_180021ECF
0x1800221e2  mov     al, [rbp+57h+var_80]
0x1800221e5  mov     [rbp+57h+var_80], sil
0x1800221e9  test    al, al
0x1800221eb  jz      short loc_1800221F3
0x1800221ed  call    cs:__imp_RpcRevertToSelf
0x1800221f3  xor     eax, eax
0x1800221f5  jmp     short loc_18002220D
0x1800221f7  mov     al, [rbp+57h+var_80]
0x1800221fa  mov     [rbp+57h+var_80], sil
0x1800221fe  test    al, al
0x180022200  jz      short loc_180022208
0x180022202  call    cs:__imp_RpcRevertToSelf
0x180022208  mov     eax, 80070057h
0x18002220d  mov     rbx, [rsp+0C0h+arg_8]
0x180022215  add     rsp, 90h
0x18002221c  pop     r15
0x18002221e  pop     r14
0x180022220  pop     r13
0x180022222  pop     r12
0x180022224  pop     rdi
0x180022225  pop     rsi
0x180022226  pop     rbp
0x180022227  retn
```
