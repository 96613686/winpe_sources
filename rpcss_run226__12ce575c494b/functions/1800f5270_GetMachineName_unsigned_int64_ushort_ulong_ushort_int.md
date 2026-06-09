# GetMachineName(unsigned __int64,ushort *,ulong,ushort *,int)

- ea: `0x1800f5270`
- end: `0x1800f578a`
- name: `?GetMachineName@@YAJ_KPEAGK1H@Z`
- size: `1306`
- prototype: `int(unsigned __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800668cc`

## callees

- `0x18000adbc`
- `0x18000bbe8`
- `0x180034540`
- `0x180070740`
- `0x180081210`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800f5270`
- `0x1800f5790`

## import_xrefs

- `ntdll!NtClose` at `0x1800f5741`
- `ntdll!NtClose` at `0x1800f5741`
- `ntdll!RtlCreateUnicodeString` at `0x1800f553d`
- `ntdll!RtlCreateUnicodeString` at `0x1800f553d`
- `ntdll!RtlFreeUnicodeString` at `0x1800f5587`
- `ntdll!RtlFreeUnicodeString` at `0x1800f566d`
- `ntdll!RtlFreeUnicodeString` at `0x1800f5587`
- `ntdll!RtlFreeUnicodeString` at `0x1800f566d`
- `ntdll!NtOpenFile` at `0x1800f5612`
- `ntdll!NtOpenFile` at `0x1800f5612`
- `ntdll!NtQueryInformationFile` at `0x1800f5697`
- `ntdll!NtQueryInformationFile` at `0x1800f5697`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5331`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5578`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5331`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5578`
- `RPCRT4!RpcRevertToSelf` at `0x1800f53ab`
- `RPCRT4!RpcRevertToSelf` at `0x1800f53f4`
- `RPCRT4!RpcRevertToSelf` at `0x1800f5662`
- `RPCRT4!RpcRevertToSelf` at `0x1800f53ab`
- `RPCRT4!RpcRevertToSelf` at `0x1800f53f4`
- `RPCRT4!RpcRevertToSelf` at `0x1800f5662`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f53a0`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f53a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f5758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f5758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f54b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f54b9`
- `MPR!WNetGetUniversalNameW` at `0x1800f53ec`
- `MPR!WNetGetUniversalNameW` at `0x1800f53ec`

## string_xrefs

- `0x1800f538b`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f543f`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f550e`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f55dd`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f5656`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f56e0`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`

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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
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
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x1800f5270  mov     [rsp-8+arg_10], rbx
0x1800f5275  push    rbp
0x1800f5276  push    rsi
0x1800f5277  push    rdi
0x1800f5278  push    r12
0x1800f527a  push    r13
0x1800f527c  push    r14
0x1800f527e  push    r15
0x1800f5280  lea     rbp, [rsp-3F0h]
0x1800f5288  sub     rsp, 4F0h
0x1800f528f  mov     rax, cs:__security_cookie
0x1800f5296  xor     rax, rsp
0x1800f5299  mov     [rbp+420h+var_40], rax
0x1800f52a0  xor     r15d, r15d
0x1800f52a3  mov     [rsp+520h+BufferSize], 220h
0x1800f52ab  mov     rdi, rdx
0x1800f52ae  mov     [rsp+520h+FileHandle], r15
0x1800f52b3  mov     r12, rcx
0x1800f52b6  xor     edx, edx; Val
0x1800f52b8  lea     rcx, [rbp+420h+SourceString]; void *
0x1800f52bc  mov     r8d, 208h; Size
0x1800f52c2  mov     ebx, r15d
0x1800f52c5  mov     esi, r15d
0x1800f52c8  mov     r13, r9
0x1800f52cb  call    memset_0
0x1800f52d0  xorps   xmm1, xmm1
0x1800f52d3  xorps   xmm0, xmm0
0x1800f52d6  movups  xmmword ptr [rsp+520h+IoStatusBlock], xmm0
0x1800f52db  movups  xmmword ptr [rsp+520h+ObjectAttributes.Length], xmm1
0x1800f52e0  movups  xmmword ptr [rbp+420h+ObjectAttributes.ObjectName], xmm1
0x1800f52e4  movups  xmmword ptr [rbp+420h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800f52e8  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x1800f52ed  cmp     r12, 3
0x1800f52f1  jbe     loc_1800F547C
0x1800f52f7  lea     r14d, [r15+5Ch]
0x1800f52fb  cmp     [rdi], r14w
0x1800f52ff  jnz     short loc_1800F530C
0x1800f5301  cmp     [rdi+2], r14w
0x1800f5306  jz      loc_1800F547C
0x1800f530c  mov     esi, 3
0x1800f5311  lea     rcx, [rbp+420h+RootPathName]; unsigned __int16 *
0x1800f5315  mov     r9d, esi; unsigned __int64
0x1800f5318  mov     r8, rdi; unsigned __int16 *
0x1800f531b  lea     edx, [rsi+1]; unsigned __int64
0x1800f531e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800f5323  test    eax, eax
0x1800f5325  js      loc_1800F544B
0x1800f532b  xor     ecx, ecx; BindingHandle
0x1800f532d  mov     [rbp+420h+var_47C], r14d
0x1800f5331  call    cs:__imp_RpcImpersonateClient
0x1800f5337  test    eax, eax
0x1800f5339  jz      short loc_1800F539C
0x1800f533b  mov     eax, cs:dword_18014E4B8
0x1800f5341  mov     ebx, 80080003h
0x1800f5346  test    eax, eax
0x1800f5348  jnz     short loc_1800F5366
0x1800f534a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f5351  jz      loc_1800F575E
0x1800f5357  xor     ecx, ecx
0x1800f5359  call    IsWppLevelEnabled
0x1800f535e  test    al, al
0x1800f5360  jz      loc_1800F575E
0x1800f5366  mov     [rsp+520h+var_4F0], ebx
0x1800f536a  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f5371  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800f5376  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f537d  xor     r9d, r9d
0x1800f5380  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f5385  mov     r8d, 83h
0x1800f538b  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5392  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f5397  jmp     loc_1800F575E
0x1800f539c  lea     rcx, [rbp+420h+RootPathName]; lpRootPathName
0x1800f53a0  call    cs:__imp_GetDriveTypeW
0x1800f53a6  cmp     eax, 4
0x1800f53a9  jz      short loc_1800F53D8
0x1800f53ab  call    cs:__imp_RpcRevertToSelf
0x1800f53b1  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f53b8  jz      loc_1800F551A
0x1800f53be  mov     ecx, esi
0x1800f53c0  call    IsWppLevelEnabled
0x1800f53c5  test    al, al
0x1800f53c7  jz      loc_1800F551A
0x1800f53cd  mov     r8d, 8Ah
0x1800f53d3  jmp     loc_1800F54EB
0x1800f53d8  lea     r9, [rsp+520h+BufferSize]; lpBufferSize
0x1800f53dd  mov     edx, 1; dwInfoLevel
0x1800f53e2  lea     r8, [rbp+420h+Buffer]; lpBuffer
0x1800f53e9  mov     rcx, rdi; lpLocalPath
0x1800f53ec  call    cs:__imp_WNetGetUniversalNameW
0x1800f53f2  mov     ebx, eax
0x1800f53f4  call    cs:__imp_RpcRevertToSelf
0x1800f53fa  test    ebx, ebx
0x1800f53fc  jz      short loc_1800F5455
0x1800f53fe  mov     ecx, cs:dword_18014E4B8
0x1800f5404  test    ecx, ecx
0x1800f5406  jnz     short loc_1800F541A
0x1800f5408  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f540f  jz      short loc_1800F544B
0x1800f5411  call    IsWppLevelEnabled
0x1800f5416  test    al, al
0x1800f5418  jz      short loc_1800F544B
0x1800f541a  mov     [rsp+520h+var_4F0], ebx
0x1800f541e  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x1800f5425  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800f542a  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f5431  xor     r9d, r9d
0x1800f5434  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f5439  mov     r8d, 96h
0x1800f543f  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5446  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800f544b  mov     eax, 80080004h
0x1800f5450  jmp     loc_1800F5760
0x1800f5455  mov     rbx, [rbp+420h+Buffer]
0x1800f545c  test    rbx, rbx
0x1800f545f  jz      short loc_1800F54D1
0x1800f5461  cmp     [rbx], r14w
0x1800f5465  jnz     short loc_1800F54D1
0x1800f5467  cmp     [rbx+2], r14w
0x1800f546c  jnz     short loc_1800F54D1
0x1800f546e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f5472  inc     rsi
0x1800f5475  cmp     [rbx+rsi*2], r15w
0x1800f547a  jnz     short loc_1800F5472
0x1800f547c  mov     r14, r15
0x1800f547f  cmp     rsi, 1
0x1800f5483  jbe     loc_1800F571B
0x1800f5489  lea     r9, [rbx+2]
0x1800f548d  mov     edx, 104h; unsigned __int64
0x1800f5492  lea     r8, aUncS; "\\??\\unc%s"
0x1800f5499  lea     rcx, [rbp+420h+SourceString]; unsigned __int16 *
0x1800f549d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f54a2  test    eax, eax
0x1800f54a4  js      loc_1800F5760
0x1800f54aa  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f54b1  xor     edx, edx; dwFlags
0x1800f54b3  mov     r8d, 210h; dwBytes
0x1800f54b9  call    cs:__imp_HeapAlloc
0x1800f54bf  mov     r14, rax
0x1800f54c2  test    rax, rax
0x1800f54c5  jnz     short loc_1800F5524
0x1800f54c7  mov     eax, 8007000Eh
0x1800f54cc  jmp     loc_1800F5760
0x1800f54d1  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f54d8  jz      short loc_1800F551A
0x1800f54da  mov     ecx, esi
0x1800f54dc  call    IsWppLevelEnabled
0x1800f54e1  test    al, al
0x1800f54e3  jz      short loc_1800F551A
0x1800f54e5  mov     r8d, 9Fh
0x1800f54eb  mov     [rsp+520h+var_4F0], 1
0x1800f54f3  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f54fa  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800f54ff  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f5506  mov     r9d, esi
0x1800f5509  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f550e  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5515  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f551a  mov     eax, 1
0x1800f551f  jmp     loc_1800F5760
0x1800f5524  xor     edx, edx; Val
0x1800f5526  mov     r8d, 210h; Size
0x1800f552c  mov     rcx, r14; void *
0x1800f552f  call    memset_0
0x1800f5534  lea     rdx, [rbp+420h+SourceString]; SourceString
0x1800f5538  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x1800f553d  call    cs:__imp_RtlCreateUnicodeString
0x1800f5543  test    al, al
0x1800f5545  jnz     short loc_1800F5551
0x1800f5547  mov     ebx, 8007000Eh
0x1800f554c  jmp     loc_1800F5737
0x1800f5551  lea     rax, [rsp+520h+DestinationString]
0x1800f5556  mov     [rsp+520h+ObjectAttributes.Length], 30h ; '0'
0x1800f555e  xorps   xmm0, xmm0
0x1800f5561  mov     [rbp+420h+ObjectAttributes.ObjectName], rax
0x1800f5565  xor     ecx, ecx; BindingHandle
0x1800f5567  mov     [rsp+520h+ObjectAttributes.RootDirectory], r15
0x1800f556c  movdqu  xmmword ptr [rbp+420h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f5571  mov     [rbp+420h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f5578  call    cs:__imp_RpcImpersonateClient
0x1800f557e  test    eax, eax
0x1800f5580  jz      short loc_1800F55EE
0x1800f5582  lea     rcx, [rsp+520h+DestinationString]; UnicodeString
0x1800f5587  call    cs:__imp_RtlFreeUnicodeString
0x1800f558d  mov     eax, cs:dword_18014E4B8
0x1800f5593  mov     ebx, 80080003h
0x1800f5598  test    eax, eax
0x1800f559a  jnz     short loc_1800F55B8
0x1800f559c  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800f55a3  jz      loc_1800F5737
0x1800f55a9  xor     ecx, ecx
0x1800f55ab  call    IsWppLevelEnabled
0x1800f55b0  test    al, al
0x1800f55b2  jz      loc_1800F5737
0x1800f55b8  mov     [rsp+520h+var_4F0], ebx
0x1800f55bc  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f55c3  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800f55c8  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f55cf  xor     r9d, r9d
0x1800f55d2  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f55d7  mov     r8d, 0CFh
0x1800f55dd  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f55e4  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f55e9  jmp     loc_1800F5737
0x1800f55ee  mov     [rsp+520h+OpenOptions], 20h ; ' '; OpenOptions
0x1800f55f6  lea     r9, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x1800f55fb  lea     r8, [rsp+520h+ObjectAttributes]; ObjectAttributes
0x1800f5600  mov     [rsp+520h+ShareAccess], 7; ShareAccess
0x1800f5608  mov     edx, 100088h; DesiredAccess
0x1800f560d  lea     rcx, [rsp+520h+FileHandle]; FileHandle
0x1800f5612  call    cs:__imp_NtOpenFile
0x1800f5618  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800f561f  mov     r15d, eax
0x1800f5622  jz      short loc_1800F5662
0x1800f5624  mov     ecx, 3
0x1800f5629  call    IsWppLevelEnabled
0x1800f562e  test    al, al
0x1800f5630  jz      short loc_1800F5662
0x1800f5632  lea     rax, aStatus; "%!STATUS!"
0x1800f5639  mov     [rsp+520h+OpenOptions], r15d
0x1800f563e  mov     r9d, 3
0x1800f5644  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f5649  mov     r8d, 0DCh
0x1800f564f  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f5656  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f565d  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800f5662  call    cs:__imp_RpcRevertToSelf
0x1800f5668  lea     rcx, [rsp+520h+DestinationString]; UnicodeString
0x1800f566d  call    cs:__imp_RtlFreeUnicodeString
0x1800f5673  test    r15d, r15d
0x1800f5676  jnz     loc_1800F571B
0x1800f567c  mov     rcx, [rsp+520h+FileHandle]; FileHandle
0x1800f5681  lea     rdx, [rsp+520h+IoStatusBlock]; IoStatusBlock
0x1800f5686  mov     r9d, 210h; Length
0x1800f568c  mov     [rsp+520h+ShareAccess], 31h ; '1'; FileInformationClass
0x1800f5694  mov     r8, r14; FileInformation
0x1800f5697  call    cs:__imp_NtQueryInformationFile
0x1800f569d  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x1800f56a4  mov     r15d, eax
0x1800f56a7  jz      short loc_1800F56EC
0x1800f56a9  mov     ecx, 3
0x1800f56ae  call    IsWppLevelEnabled
0x1800f56b3  test    al, al
0x1800f56b5  jz      short loc_1800F56EC
0x1800f56b7  mov     [rsp+520h+var_4F0], r15d
0x1800f56bc  lea     rax, aWsStatus; "%ws %!STATUS!"
0x1800f56c3  mov     qword ptr [rsp+520h+OpenOptions], rdi
0x1800f56c8  lea     rdx, aGetmachinename_0; "GetMachineName"
0x1800f56cf  mov     r9d, 3
0x1800f56d5  mov     qword ptr [rsp+520h+ShareAccess], rax
0x1800f56da  mov     r8d, 0EEh
0x1800f56e0  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f56e7  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800f56ec  test    r15d, r15d
0x1800f56ef  jnz     short loc_1800F571B
0x1800f56f1  lea     r9, [r14+4]
0x1800f56f5  mov     edx, 104h; unsigned __int64
0x1800f56fa  lea     r8, aS_2; "\\%s"
0x1800f5701  lea     rcx, [rbp+420h+SourceString]; unsigned __int16 *
0x1800f5705  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f570a  mov     ebx, eax
0x1800f570c  test    eax, eax
0x1800f570e  js      short loc_1800F5737
0x1800f5710  mov     esi, [r14]
0x1800f5713  lea     rbx, [rbp+420h+SourceString]
0x1800f5717  inc     esi
0x1800f5719  jmp     short loc_1800F5726
0x1800f571b  test    rbx, rbx
0x1800f571e  jnz     short loc_1800F5726
0x1800f5720  mov     rsi, r12
0x1800f5723  mov     rbx, rdi
0x1800f5726  lea     rcx, [rsi-1]; unsigned __int64
0x1800f572a  mov     r9, r13; unsigned __int16 *
0x1800f572d  mov     rdx, rbx; unsigned __int16 *
0x1800f5730  call    ?GetMachineNameFromUNC@@YAJ_KPEAGK1@Z; GetMachineNameFromUNC(unsigned __int64,ushort *,ulong,ushort *)
0x1800f5735  mov     ebx, eax
0x1800f5737  mov     rcx, [rsp+520h+FileHandle]; Handle
0x1800f573c  test    rcx, rcx
0x1800f573f  jz      short loc_1800F5747
0x1800f5741  call    cs:__imp_NtClose
0x1800f5747  test    r14, r14
0x1800f574a  jz      short loc_1800F575E
0x1800f574c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f5753  mov     r8, r14; lpMem
0x1800f5756  xor     edx, edx; dwFlags
0x1800f5758  call    cs:__imp_HeapFree
0x1800f575e  mov     eax, ebx
0x1800f5760  mov     rcx, [rbp+420h+var_40]
0x1800f5767  xor     rcx, rsp; StackCookie
0x1800f576a  call    __security_check_cookie
0x1800f576f  mov     rbx, [rsp+520h+arg_10]
0x1800f5777  add     rsp, 4F0h
0x1800f577e  pop     r15
0x1800f5780  pop     r14
0x1800f5782  pop     r13
0x1800f5784  pop     r12
0x1800f5786  pop     rdi
0x1800f5787  pop     rsi
0x1800f5788  pop     rbp
0x1800f5789  retn
  ... truncated ...
```
