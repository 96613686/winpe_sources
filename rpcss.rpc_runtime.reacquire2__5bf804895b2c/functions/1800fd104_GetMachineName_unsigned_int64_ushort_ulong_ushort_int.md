# GetMachineName(unsigned __int64,ushort *,ulong,ushort *,int)

- ea: `0x1800fd104`
- end: `0x1800fd679`
- name: `?GetMachineName@@YAJ_KPEAGK1H@Z`
- size: `1397`
- prototype: `int(unsigned __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b520`

## callees

- `0x18001037c`
- `0x1800117e8`
- `0x180034260`
- `0x180074d98`
- `0x1800855d8`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800fd104`
- `0x1800fd680`

## import_xrefs

- `ntdll!NtClose` at `0x1800fd623`
- `ntdll!NtClose` at `0x1800fd623`
- `ntdll!RtlCreateUnicodeString` at `0x1800fd3f5`
- `ntdll!RtlCreateUnicodeString` at `0x1800fd3f5`
- `ntdll!RtlFreeUnicodeString` at `0x1800fd44b`
- `ntdll!RtlFreeUnicodeString` at `0x1800fd543`
- `ntdll!RtlFreeUnicodeString` at `0x1800fd44b`
- `ntdll!RtlFreeUnicodeString` at `0x1800fd543`
- `ntdll!NtOpenFile` at `0x1800fd4dc`
- `ntdll!NtOpenFile` at `0x1800fd4dc`
- `ntdll!NtQueryInformationFile` at `0x1800fd573`
- `ntdll!NtQueryInformationFile` at `0x1800fd573`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd1c5`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd436`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd1c5`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd436`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd24b`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd2a0`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd532`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd24b`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd2a0`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd532`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800fd23a`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800fd23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fd640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fd640`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fd36b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fd36b`
- `MPR!WNetGetUniversalNameW` at `0x1800fd292`
- `MPR!WNetGetUniversalNameW` at `0x1800fd292`

## string_xrefs

- `0x1800fd225`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd2f1`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd3c6`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd4a7`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd526`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd5c2`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`

## pseudocode

```c
__int64 __fastcall GetMachineName(unsigned __int64 a1, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned __int16 *v6; // rbx
  unsigned __int64 v7; // rsi
  unsigned int v9; // r8d
  int MachineNameFromUNC; // ebx
  int v11; // r8d
  DWORD UniversalNameW; // ebx
  __int64 result; // rax
  _DWORD *v14; // r14
  _DWORD *v15; // rax
  NTSTATUS v16; // r15d
  NTSTATUS v17; // r15d
  ULONG OpenOptions[2]; // [rsp+28h] [rbp-D8h]
  DWORD BufferSize; // [rsp+40h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR RootPathName[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v25; // [rsp+A4h] [rbp-5Ch]
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *Buffer; // [rsp+2C0h] [rbp+1C0h] BYREF

  BufferSize = 544;
  FileHandle = 0;
  v6 = 0;
  v7 = 0;
  memset_0(SourceString, 0, 0x208u);
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( a1 <= 3 || *(_DWORD *)a2 == 6029404 )
  {
LABEL_23:
    v14 = 0;
    if ( v7 <= 1 )
      goto LABEL_49;
    result = StringCchPrintfW(SourceString, 0x104u, L"\\??\\unc%s", v6 + 1);
    if ( (int)result < 0 )
      return result;
    v15 = HeapAlloc(g_hHeap, 0, 0x210u);
    v14 = v15;
    if ( !v15 )
      return 2147942414LL;
    memset_0(v15, 0, 0x210u);
    if ( !RtlCreateUnicodeString(&DestinationString, SourceString) )
    {
      MachineNameFromUNC = -2147024882;
LABEL_52:
      if ( FileHandle )
        NtClose(FileHandle);
      if ( v14 )
        HeapFree(g_hHeap, 0, v14);
      return (unsigned int)MachineNameFromUNC;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Attributes = 64;
    if ( RpcImpersonateClient(0) )
    {
      RtlFreeUnicodeString(&DestinationString);
      MachineNameFromUNC = -2146959357;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
          (unsigned int)"GetMachineName",
          207,
          0,
          (__int64)L"%ws %!HRESULT!",
          a2,
          -2146959357);
      goto LABEL_52;
    }
    v16 = NtOpenFile(&FileHandle, 0x100088u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
    {
      OpenOptions[0] = v16;
      ComTraceMessageT<int>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
        (unsigned int)"GetMachineName",
        220,
        3,
        (__int64)L"%!STATUS!",
        *(_QWORD *)OpenOptions);
    }
    RpcRevertToSelf();
    RtlFreeUnicodeString(&DestinationString);
    if ( v16 )
      goto LABEL_49;
    v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v14, 0x210u, FileNetworkPhysicalNameInformation);
    if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned __int64,unsigned long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
        (unsigned int)"GetMachineName",
        238,
        3,
        (__int64)L"%ws %!STATUS!",
        a2,
        v17);
    if ( v17 )
    {
LABEL_49:
      if ( !v6 )
      {
        v7 = a1;
        v6 = a2;
      }
    }
    else
    {
      MachineNameFromUNC = StringCchPrintfW(SourceString, 0x104u, L"\\%s", v14 + 1);
      if ( MachineNameFromUNC < 0 )
        goto LABEL_52;
      v6 = SourceString;
      v7 = (unsigned int)(*v14 + 1);
    }
    MachineNameFromUNC = GetMachineNameFromUNC(v7 - 1, v6, v9, a4);
    goto LABEL_52;
  }
  if ( (int)StringCchCopyNW(RootPathName, 4u, a2, 3u) < 0 )
    return 2148007940LL;
  v25 = 92;
  if ( !RpcImpersonateClient(0) )
  {
    if ( GetDriveTypeW(RootPathName) != 4 )
    {
      RpcRevertToSelf();
      if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(3) )
        return 1;
      v11 = 138;
LABEL_30:
      ComTraceMessageT<unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
        (unsigned int)"GetMachineName",
        v11,
        3,
        (__int64)L"%ws %!HRESULT!",
        a2,
        1);
      return 1;
    }
    UniversalNameW = WNetGetUniversalNameW(a2, 1u, &Buffer, &BufferSize);
    RpcRevertToSelf();
    if ( UniversalNameW )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
        ComTraceMessageT<unsigned __int64,unsigned long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
          (unsigned int)"GetMachineName",
          150,
          0,
          (__int64)L"%ws %!WINERROR!",
          a2,
          UniversalNameW);
      return 2148007940LL;
    }
    v6 = Buffer;
    if ( !Buffer || *(_DWORD *)Buffer != 6029404 )
    {
      if ( !gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(3) )
        return 1;
      v11 = 159;
      goto LABEL_30;
    }
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    goto LABEL_23;
  }
  MachineNameFromUNC = -2146959357;
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
      (unsigned int)"GetMachineName",
      131,
      0,
      (__int64)L"%ws %!HRESULT!",
      a2,
      -2146959357);
  return (unsigned int)MachineNameFromUNC;
}

```

## disassembly

```asm
0x1800fd104  mov     [rsp-8+arg_10], rbx
0x1800fd109  push    rbp
0x1800fd10a  push    rsi
0x1800fd10b  push    rdi
0x1800fd10c  push    r12
0x1800fd10e  push    r13
0x1800fd110  push    r14
0x1800fd112  push    r15
0x1800fd114  lea     rbp, [rsp-3F0h]
0x1800fd11c  sub     rsp, 4F0h
0x1800fd123  mov     rax, cs:__security_cookie
0x1800fd12a  xor     rax, rsp
0x1800fd12d  mov     [rbp+420h+var_40], rax
0x1800fd134  xor     r15d, r15d
0x1800fd137  mov     [rsp+520h+BufferSize], 220h
0x1800fd13f  mov     rdi, rdx
0x1800fd142  mov     [rsp+520h+FileHandle], r15
0x1800fd147  mov     r12, rcx
0x1800fd14a  xor     edx, edx; Val
0x1800fd14c  lea     rcx, [rbp+420h+SourceString]; void *
0x1800fd150  mov     r8d, 208h; Size
0x1800fd156  mov     ebx, r15d
0x1800fd159  mov     esi, r15d
0x1800fd15c  mov     r13, r9
0x1800fd15f  call    memset_0
0x1800fd164  xorps   xmm1, xmm1
0x1800fd167  xorps   xmm0, xmm0
0x1800fd16a  movups  xmmword ptr [rsp+520h+IoStatusBlock], xmm0
0x1800fd16f  movups  xmmword ptr [rsp+520h+ObjectAttributes.Length], xmm1
0x1800fd174  movups  xmmword ptr [rbp+420h+ObjectAttributes.ObjectName], xmm1
0x1800fd178  movups  xmmword ptr [rbp+420h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800fd17c  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x1800fd181  cmp     r12, 3
0x1800fd185  jbe     loc_1800FD32E
0x1800fd18b  lea     r14d, [r15+5Ch]
0x1800fd18f  cmp     [rdi], r14w
0x1800fd193  jnz     short loc_1800FD1A0
0x1800fd195  cmp     [rdi+2], r14w
0x1800fd19a  jz      loc_1800FD32E
0x1800fd1a0  mov     esi, 3
0x1800fd1a5  lea     rcx, [rbp+420h+RootPathName]; unsigned __int16 *
0x1800fd1a9  mov     r9d, esi; unsigned __int64
0x1800fd1ac  mov     r8, rdi; unsigned __int16 *
0x1800fd1af  lea     edx, [rsi+1]; unsigned __int64
0x1800fd1b2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800fd1b7  test    eax, eax
0x1800fd1b9  js      loc_1800FD2FD
0x1800fd1bf  xor     ecx, ecx; BindingHandle
0x1800fd1c1  mov     [rbp+420h+var_47C], r14d
0x1800fd1c5  call    cs:__imp_RpcImpersonateClient
0x1800fd1cc  nop     dword ptr [rax+rax+00h]
0x1800fd1d1  test    eax, eax
0x1800fd1d3  jz      short loc_1800FD236
0x1800fd1d5  mov     eax, cs:dword_1801574B8
0x1800fd1db  mov     ebx, 80080003h
0x1800fd1e0  test    eax, eax
0x1800fd1e2  jnz     short loc_1800FD200
0x1800fd1e4  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800fd1eb  jz      loc_1800FD64C
0x1800fd1f1  xor     ecx, ecx
0x1800fd1f3  call    IsWppLevelEnabled
0x1800fd1f8  test    al, al
0x1800fd1fa  jz      loc_1800FD64C
0x1800fd200  mov     [rsp+520h+var_4F0], ebx
0x1800fd204  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800fd20b  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800fd210  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd217  xor     r9d, r9d
0x1800fd21a  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd21f  mov     r8d, 83h
0x1800fd225  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd22c  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800fd231  jmp     loc_1800FD64C
0x1800fd236  lea     rcx, [rbp+420h+RootPathName]; lpRootPathName
0x1800fd23a  call    cs:__imp_GetDriveTypeW
0x1800fd241  nop     dword ptr [rax+rax+00h]
0x1800fd246  cmp     eax, 4
0x1800fd249  jz      short loc_1800FD27E
0x1800fd24b  call    cs:__imp_RpcRevertToSelf
0x1800fd252  nop     dword ptr [rax+rax+00h]
0x1800fd257  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800fd25e  jz      loc_1800FD3D2
0x1800fd264  mov     ecx, esi
0x1800fd266  call    IsWppLevelEnabled
0x1800fd26b  test    al, al
0x1800fd26d  jz      loc_1800FD3D2
0x1800fd273  mov     r8d, 8Ah
0x1800fd279  jmp     loc_1800FD3A3
0x1800fd27e  lea     r9, [rsp+520h+BufferSize]; lpBufferSize
0x1800fd283  mov     edx, 1; dwInfoLevel
0x1800fd288  lea     r8, [rbp+420h+Buffer]; lpBuffer
0x1800fd28f  mov     rcx, rdi; lpLocalPath
0x1800fd292  call    cs:__imp_WNetGetUniversalNameW
0x1800fd299  nop     dword ptr [rax+rax+00h]
0x1800fd29e  mov     ebx, eax
0x1800fd2a0  call    cs:__imp_RpcRevertToSelf
0x1800fd2a7  nop     dword ptr [rax+rax+00h]
0x1800fd2ac  test    ebx, ebx
0x1800fd2ae  jz      short loc_1800FD307
0x1800fd2b0  mov     ecx, cs:dword_1801574B8
0x1800fd2b6  test    ecx, ecx
0x1800fd2b8  jnz     short loc_1800FD2CC
0x1800fd2ba  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800fd2c1  jz      short loc_1800FD2FD
0x1800fd2c3  call    IsWppLevelEnabled
0x1800fd2c8  test    al, al
0x1800fd2ca  jz      short loc_1800FD2FD
0x1800fd2cc  mov     [rsp+520h+var_4F0], ebx
0x1800fd2d0  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x1800fd2d7  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800fd2dc  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd2e3  xor     r9d, r9d
0x1800fd2e6  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd2eb  mov     r8d, 96h
0x1800fd2f1  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd2f8  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800fd2fd  mov     eax, 80080004h
0x1800fd302  jmp     loc_1800FD64E
0x1800fd307  mov     rbx, [rbp+420h+Buffer]
0x1800fd30e  test    rbx, rbx
0x1800fd311  jz      short loc_1800FD389
0x1800fd313  cmp     [rbx], r14w
0x1800fd317  jnz     short loc_1800FD389
0x1800fd319  cmp     [rbx+2], r14w
0x1800fd31e  jnz     short loc_1800FD389
0x1800fd320  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800fd324  inc     rsi
0x1800fd327  cmp     [rbx+rsi*2], r15w
0x1800fd32c  jnz     short loc_1800FD324
0x1800fd32e  mov     r14, r15
0x1800fd331  cmp     rsi, 1
0x1800fd335  jbe     loc_1800FD5FD
0x1800fd33b  lea     r9, [rbx+2]
0x1800fd33f  mov     edx, 104h; unsigned __int64
0x1800fd344  lea     r8, aUncS; "\\??\\unc%s"
0x1800fd34b  lea     rcx, [rbp+420h+SourceString]; unsigned __int16 *
0x1800fd34f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fd354  test    eax, eax
0x1800fd356  js      loc_1800FD64E
0x1800fd35c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800fd363  xor     edx, edx; dwFlags
0x1800fd365  mov     r8d, 210h; dwBytes
0x1800fd36b  call    cs:__imp_HeapAlloc
0x1800fd372  nop     dword ptr [rax+rax+00h]
0x1800fd377  mov     r14, rax
0x1800fd37a  test    rax, rax
0x1800fd37d  jnz     short loc_1800FD3DC
0x1800fd37f  mov     eax, 8007000Eh
0x1800fd384  jmp     loc_1800FD64E
0x1800fd389  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800fd390  jz      short loc_1800FD3D2
0x1800fd392  mov     ecx, esi
0x1800fd394  call    IsWppLevelEnabled
0x1800fd399  test    al, al
0x1800fd39b  jz      short loc_1800FD3D2
0x1800fd39d  mov     r8d, 9Fh
0x1800fd3a3  mov     [rsp+520h+var_4F0], 1
0x1800fd3ab  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800fd3b2  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800fd3b7  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd3be  mov     r9d, esi
0x1800fd3c1  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd3c6  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd3cd  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800fd3d2  mov     eax, 1
0x1800fd3d7  jmp     loc_1800FD64E
0x1800fd3dc  xor     edx, edx; Val
0x1800fd3de  mov     r8d, 210h; Size
0x1800fd3e4  mov     rcx, r14; void *
0x1800fd3e7  call    memset_0
0x1800fd3ec  lea     rdx, [rbp+420h+SourceString]; SourceString
0x1800fd3f0  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x1800fd3f5  call    cs:__imp_RtlCreateUnicodeString
0x1800fd3fc  nop     dword ptr [rax+rax+00h]
0x1800fd401  test    al, al
0x1800fd403  jnz     short loc_1800FD40F
0x1800fd405  mov     ebx, 8007000Eh
0x1800fd40a  jmp     loc_1800FD619
0x1800fd40f  lea     rax, [rsp+520h+DestinationString]
0x1800fd414  mov     [rsp+520h+ObjectAttributes.Length], 30h ; '0'
0x1800fd41c  xorps   xmm0, xmm0
0x1800fd41f  mov     [rbp+420h+ObjectAttributes.ObjectName], rax
0x1800fd423  xor     ecx, ecx; BindingHandle
0x1800fd425  mov     [rsp+520h+ObjectAttributes.RootDirectory], r15
0x1800fd42a  movdqu  xmmword ptr [rbp+420h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fd42f  mov     [rbp+420h+ObjectAttributes.Attributes], 40h ; '@'
0x1800fd436  call    cs:__imp_RpcImpersonateClient
0x1800fd43d  nop     dword ptr [rax+rax+00h]
0x1800fd442  test    eax, eax
0x1800fd444  jz      short loc_1800FD4B8
0x1800fd446  lea     rcx, [rsp+520h+DestinationString]; UnicodeString
0x1800fd44b  call    cs:__imp_RtlFreeUnicodeString
0x1800fd452  nop     dword ptr [rax+rax+00h]
0x1800fd457  mov     eax, cs:dword_1801574B8
0x1800fd45d  mov     ebx, 80080003h
0x1800fd462  test    eax, eax
0x1800fd464  jnz     short loc_1800FD482
0x1800fd466  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800fd46d  jz      loc_1800FD619
0x1800fd473  xor     ecx, ecx
0x1800fd475  call    IsWppLevelEnabled
0x1800fd47a  test    al, al
0x1800fd47c  jz      loc_1800FD619
0x1800fd482  mov     [rsp+520h+var_4F0], ebx
0x1800fd486  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800fd48d  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800fd492  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd499  xor     r9d, r9d
0x1800fd49c  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd4a1  mov     r8d, 0CFh
0x1800fd4a7  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd4ae  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800fd4b3  jmp     loc_1800FD619
0x1800fd4b8  mov     [rsp+520h+OpenOptions], 20h ; ' '; OpenOptions
0x1800fd4c0  lea     r9, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x1800fd4c5  lea     r8, [rsp+520h+ObjectAttributes]; ObjectAttributes
0x1800fd4ca  mov     [rsp+520h+ShareAccess], 7; ShareAccess
0x1800fd4d2  mov     edx, 100088h; DesiredAccess
0x1800fd4d7  lea     rcx, [rsp+520h+FileHandle]; FileHandle
0x1800fd4dc  call    cs:__imp_NtOpenFile
0x1800fd4e3  nop     dword ptr [rax+rax+00h]
0x1800fd4e8  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800fd4ef  mov     r15d, eax
0x1800fd4f2  jz      short loc_1800FD532
0x1800fd4f4  mov     ecx, 3
0x1800fd4f9  call    IsWppLevelEnabled
0x1800fd4fe  test    al, al
0x1800fd500  jz      short loc_1800FD532
0x1800fd502  lea     rax, aStatus; "%!STATUS!"
0x1800fd509  mov     [rsp+520h+OpenOptions], r15d
0x1800fd50e  mov     r9d, 3
0x1800fd514  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd519  mov     r8d, 0DCh
0x1800fd51f  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd526  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd52d  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800fd532  call    cs:__imp_RpcRevertToSelf
0x1800fd539  nop     dword ptr [rax+rax+00h]
0x1800fd53e  lea     rcx, [rsp+520h+DestinationString]; UnicodeString
0x1800fd543  call    cs:__imp_RtlFreeUnicodeString
0x1800fd54a  nop     dword ptr [rax+rax+00h]
0x1800fd54f  test    r15d, r15d
0x1800fd552  jnz     loc_1800FD5FD
0x1800fd558  mov     rcx, [rsp+520h+FileHandle]; FileHandle
0x1800fd55d  lea     rdx, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x1800fd562  mov     r9d, 210h; Length
0x1800fd568  mov     [rsp+520h+ShareAccess], 31h ; '1'; FileInformationClass
0x1800fd570  mov     r8, r14; FileInformation
0x1800fd573  call    cs:__imp_NtQueryInformationFile
0x1800fd57a  nop     dword ptr [rax+rax+00h]
0x1800fd57f  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800fd586  mov     r15d, eax
0x1800fd589  jz      short loc_1800FD5CE
0x1800fd58b  mov     ecx, 3
0x1800fd590  call    IsWppLevelEnabled
0x1800fd595  test    al, al
0x1800fd597  jz      short loc_1800FD5CE
0x1800fd599  mov     [rsp+520h+var_4F0], r15d
0x1800fd59e  lea     rax, aWsStatus; "%ws %!STATUS!"
0x1800fd5a5  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800fd5aa  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800fd5b1  mov     r9d, 3
0x1800fd5b7  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800fd5bc  mov     r8d, 0EEh
0x1800fd5c2  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd5c9  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800fd5ce  test    r15d, r15d
0x1800fd5d1  jnz     short loc_1800FD5FD
0x1800fd5d3  lea     r9, [r14+4]
0x1800fd5d7  mov     edx, 104h; unsigned __int64
0x1800fd5dc  lea     r8, aS_2; "\\%s"
0x1800fd5e3  lea     rcx, [rbp+420h+SourceString]; unsigned __int16 *
0x1800fd5e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fd5ec  mov     ebx, eax
0x1800fd5ee  test    eax, eax
0x1800fd5f0  js      short loc_1800FD619
0x1800fd5f2  mov     esi, [r14]
0x1800fd5f5  lea     rbx, [rbp+420h+SourceString]
0x1800fd5f9  inc     esi
0x1800fd5fb  jmp     short loc_1800FD608
0x1800fd5fd  test    rbx, rbx
0x1800fd600  jnz     short loc_1800FD608
0x1800fd602  mov     rsi, r12
0x1800fd605  mov     rbx, rdi
0x1800fd608  lea     rcx, [rsi-1]; unsigned __int64
0x1800fd60c  mov     r9, r13; unsigned __int16 *
0x1800fd60f  mov     rdx, rbx; unsigned __int16 *
0x1800fd612  call    ?GetMachineNameFromUNC@@YAJ_KPEAGK1@Z; GetMachineNameFromUNC(unsigned __int64,ushort *,ulong,ushort *)
0x1800fd617  mov     ebx, eax
0x1800fd619  mov     rcx, [rsp+520h+FileHandle]; Handle
0x1800fd61e  test    rcx, rcx
0x1800fd621  jz      short loc_1800FD62F
0x1800fd623  call    cs:__imp_NtClose
0x1800fd62a  nop     dword ptr [rax+rax+00h]
0x1800fd62f  test    r14, r14
0x1800fd632  jz      short loc_1800FD64C
0x1800fd634  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800fd63b  mov     r8, r14; lpMem
0x1800fd63e  xor     edx, edx; dwFlags
0x1800fd640  call    cs:__imp_HeapFree
  ... truncated ...
```
