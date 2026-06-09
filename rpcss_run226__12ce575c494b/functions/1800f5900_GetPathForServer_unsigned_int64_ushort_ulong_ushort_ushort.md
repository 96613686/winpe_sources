# GetPathForServer(unsigned __int64,ushort *,ulong,ushort *,ushort * *)

- ea: `0x1800f5900`
- end: `0x1800f5bcd`
- name: `?GetPathForServer@@YAJ_KPEAGK1PEAPEAG@Z`
- size: `717`
- prototype: `int(unsigned __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f2da4`

## callees

- `0x18000adbc`
- `0x18000b310`
- `0x18000bbe8`
- `0x180034540`
- `0x180070740`
- `0x180081210`
- `0x1800b27e0`
- `0x1800f07c0`
- `0x1800f5900`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800f598d`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5a62`
- `RPCRT4!RpcImpersonateClient` at `0x1800f598d`
- `RPCRT4!RpcImpersonateClient` at `0x1800f5a62`
- `RPCRT4!RpcRevertToSelf` at `0x1800f59d4`
- `RPCRT4!RpcRevertToSelf` at `0x1800f5ae2`
- `RPCRT4!RpcRevertToSelf` at `0x1800f59d4`
- `RPCRT4!RpcRevertToSelf` at `0x1800f5ae2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f59cc`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f59cc`
- `MPR!WNetGetUniversalNameW` at `0x1800f5ada`
- `MPR!WNetGetUniversalNameW` at `0x1800f5ada`

## string_xrefs

- `0x1800f5a4a`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f5ab2`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f5b34`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800f5a35`: `GetPathForServer`
- `0x1800f5aa3`: `GetPathForServer`
- `0x1800f5b1f`: `GetPathForServer`

## pseudocode

```c
__int64 __fastcall GetPathForServer(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int v7; // r8d
  UINT DriveTypeW; // ebx
  CMachineName *v9; // rcx
  UINT v10; // ebx
  UINT v11; // ebx
  UINT v12; // ebx
  UINT v13; // ebx
  DWORD UniversalNameW; // ebx
  int v16; // eax
  CMachineName *v17; // rcx
  int v18; // ebx
  unsigned __int16 *v19; // rax
  DWORD BufferSize; // [rsp+40h] [rbp-258h] BYREF
  WCHAR RootPathName[2]; // [rsp+48h] [rbp-250h] BYREF
  int v22; // [rsp+4Ch] [rbp-24Ch]
  const unsigned __int16 *Buffer; // [rsp+50h] [rbp-248h] BYREF

  BufferSize = 544;
  *a5 = 0;
  if ( a2 && a1 > 3 && a2[1] == 58 && a2[2] == 92 )
  {
    if ( (int)StringCchCopyNW(RootPathName, 4u, a2, 3u) < 0 )
      return 2148007940LL;
    v22 = 92;
    if ( RpcImpersonateClient(0) )
    {
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
        return 2148007939LL;
      v7 = 302;
LABEL_27:
      ComTraceMessageT<unsigned short *,long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
        (unsigned int)"GetPathForServer",
        v7,
        0,
        (__int64)L"%ws %!HRESULT!",
        a2,
        -2146959357);
      return 2148007939LL;
    }
    DriveTypeW = GetDriveTypeW(RootPathName);
    RpcRevertToSelf();
    if ( !DriveTypeW )
      goto LABEL_17;
    v10 = DriveTypeW - 1;
    if ( !v10 )
      goto LABEL_17;
    v11 = v10 - 1;
    if ( !v11 )
      goto LABEL_17;
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 - 1 <= 1 )
        {
LABEL_17:
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
            ComTraceMessageT<unsigned short *,long>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
              (unsigned int)"GetPathForServer",
              321,
              0,
              (__int64)L"%ws %!HRESULT!",
              a2,
              -2146959356);
          return 2148007940LL;
        }
        return 0;
      }
      if ( RpcImpersonateClient(0) )
      {
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          return 2148007939LL;
        v7 = 338;
        goto LABEL_27;
      }
      UniversalNameW = WNetGetUniversalNameW(a2, 1u, &Buffer, &BufferSize);
      RpcRevertToSelf();
      if ( UniversalNameW )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
          ComTraceMessageT<unsigned __int64,unsigned long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\actmisc.cxx",
            (unsigned int)"GetPathForServer",
            350,
            0,
            (__int64)L"%ws %!STATUS!",
            a2,
            UniversalNameW);
        return 2148007940LL;
      }
      v16 = StringCchCopyW(a4, 0x105u, Buffer);
    }
    else
    {
      if ( !CMachineName::NetBiosName(v9) )
        return 2147942414LL;
      v18 = RootPathName[0];
      v19 = CMachineName::NetBiosName(v17);
      v16 = StringCchPrintfW(a4, 0x105u, L"\\\\%Ls\\%Lc$\\%Ls", v19, v18, a2 + 3);
    }
    if ( v16 < 0 )
      return 2148007940LL;
    *a5 = a4;
  }
  else
  {
    *a5 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f5900  mov     [rsp+arg_0], rbx
0x1800f5905  push    rbp
0x1800f5906  push    rsi
0x1800f5907  push    rdi
0x1800f5908  sub     rsp, 280h
0x1800f590f  mov     rax, cs:__security_cookie
0x1800f5916  xor     rax, rsp
0x1800f5919  mov     [rsp+298h+var_28], rax
0x1800f5921  mov     rsi, [rsp+298h+arg_20]
0x1800f5929  mov     rbp, r9
0x1800f592c  mov     [rsp+298h+BufferSize], 220h
0x1800f5934  mov     rdi, rdx
0x1800f5937  mov     qword ptr [rsi], 0
0x1800f593e  test    rdx, rdx
0x1800f5941  jz      loc_1800F5BA5
0x1800f5947  mov     r9d, 3; unsigned __int64
0x1800f594d  cmp     rcx, r9
0x1800f5950  jbe     loc_1800F5BA5
0x1800f5956  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1800f595b  jnz     loc_1800F5BA5
0x1800f5961  lea     ebx, [r9+59h]
0x1800f5965  cmp     [rdx+4], bx
0x1800f5969  jnz     loc_1800F5BA5
0x1800f596f  mov     r8, rdx; unsigned __int16 *
0x1800f5972  lea     rcx, [rsp+298h+RootPathName]; unsigned __int16 *
0x1800f5977  lea     edx, [rbx-58h]; unsigned __int64
0x1800f597a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800f597f  test    eax, eax
0x1800f5981  js      loc_1800F5A56
0x1800f5987  xor     ecx, ecx; BindingHandle
0x1800f5989  mov     [rsp+298h+var_24C], ebx
0x1800f598d  call    cs:__imp_RpcImpersonateClient
0x1800f5993  test    eax, eax
0x1800f5995  jz      short loc_1800F59C7
0x1800f5997  mov     eax, cs:dword_18014E4B8
0x1800f599d  test    eax, eax
0x1800f599f  jnz     short loc_1800F59BC
0x1800f59a1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f59a7  jz      loc_1800F5ABE
0x1800f59ad  xor     ecx, ecx
0x1800f59af  call    IsWppLevelEnabled
0x1800f59b4  test    al, al
0x1800f59b6  jz      loc_1800F5ABE
0x1800f59bc  mov     r8d, 12Eh
0x1800f59c2  jmp     loc_1800F5A8F
0x1800f59c7  lea     rcx, [rsp+298h+RootPathName]; lpRootPathName
0x1800f59cc  call    cs:__imp_GetDriveTypeW
0x1800f59d2  mov     ebx, eax
0x1800f59d4  call    cs:__imp_RpcRevertToSelf
0x1800f59da  test    ebx, ebx
0x1800f59dc  jz      short loc_1800F5A04
0x1800f59de  sub     ebx, 1
0x1800f59e1  jz      short loc_1800F5A04
0x1800f59e3  sub     ebx, 1
0x1800f59e6  jz      short loc_1800F5A04
0x1800f59e8  sub     ebx, 1
0x1800f59eb  jz      loc_1800F5B59
0x1800f59f1  sub     ebx, 1
0x1800f59f4  jz      short loc_1800F5A60
0x1800f59f6  sub     ebx, 1
0x1800f59f9  jz      short loc_1800F5A04
0x1800f59fb  cmp     ebx, 1
0x1800f59fe  jnz     loc_1800F5BA8
0x1800f5a04  mov     eax, cs:dword_18014E4B8
0x1800f5a0a  test    eax, eax
0x1800f5a0c  jnz     short loc_1800F5A21
0x1800f5a0e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f5a14  jz      short loc_1800F5A56
0x1800f5a16  xor     ecx, ecx
0x1800f5a18  call    IsWppLevelEnabled
0x1800f5a1d  test    al, al
0x1800f5a1f  jz      short loc_1800F5A56
0x1800f5a21  mov     [rsp+298h+var_268], 80080004h
0x1800f5a29  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f5a30  mov     [rsp+298h+var_270], rdi
0x1800f5a35  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800f5a3c  xor     r9d, r9d
0x1800f5a3f  mov     [rsp+298h+var_278], rax
0x1800f5a44  mov     r8d, 141h
0x1800f5a4a  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5a51  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f5a56  mov     eax, 80080004h
0x1800f5a5b  jmp     loc_1800F5BAA
0x1800f5a60  xor     ecx, ecx; BindingHandle
0x1800f5a62  call    cs:__imp_RpcImpersonateClient
0x1800f5a68  test    eax, eax
0x1800f5a6a  jz      short loc_1800F5AC8
0x1800f5a6c  mov     eax, cs:dword_18014E4B8
0x1800f5a72  test    eax, eax
0x1800f5a74  jnz     short loc_1800F5A89
0x1800f5a76  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f5a7c  jz      short loc_1800F5ABE
0x1800f5a7e  xor     ecx, ecx
0x1800f5a80  call    IsWppLevelEnabled
0x1800f5a85  test    al, al
0x1800f5a87  jz      short loc_1800F5ABE
0x1800f5a89  mov     r8d, 152h
0x1800f5a8f  mov     [rsp+298h+var_268], 80080003h
0x1800f5a97  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f5a9e  mov     [rsp+298h+var_270], rdi
0x1800f5aa3  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800f5aaa  xor     r9d, r9d
0x1800f5aad  mov     [rsp+298h+var_278], rax
0x1800f5ab2  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5ab9  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f5abe  mov     eax, 80080003h
0x1800f5ac3  jmp     loc_1800F5BAA
0x1800f5ac8  lea     r9, [rsp+298h+BufferSize]; lpBufferSize
0x1800f5acd  mov     edx, 1; dwInfoLevel
0x1800f5ad2  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x1800f5ad7  mov     rcx, rdi; lpLocalPath
0x1800f5ada  call    cs:__imp_WNetGetUniversalNameW
0x1800f5ae0  mov     ebx, eax
0x1800f5ae2  call    cs:__imp_RpcRevertToSelf
0x1800f5ae8  test    ebx, ebx
0x1800f5aea  jz      short loc_1800F5B45
0x1800f5aec  mov     ecx, cs:dword_18014E4B8
0x1800f5af2  test    ecx, ecx
0x1800f5af4  jnz     short loc_1800F5B0F
0x1800f5af6  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800f5afc  jz      loc_1800F5A56
0x1800f5b02  call    IsWppLevelEnabled
0x1800f5b07  test    al, al
0x1800f5b09  jz      loc_1800F5A56
0x1800f5b0f  mov     [rsp+298h+var_268], ebx
0x1800f5b13  lea     rax, aWsStatus; "%ws %!STATUS!"
0x1800f5b1a  mov     [rsp+298h+var_270], rdi
0x1800f5b1f  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800f5b26  xor     r9d, r9d
0x1800f5b29  mov     [rsp+298h+var_278], rax
0x1800f5b2e  mov     r8d, 15Eh
0x1800f5b34  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800f5b3b  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800f5b40  jmp     loc_1800F5A56
0x1800f5b45  mov     r8, [rsp+298h+Buffer]; unsigned __int16 *
0x1800f5b4a  mov     edx, 105h; unsigned __int64
0x1800f5b4f  mov     rcx, rbp; unsigned __int16 *
0x1800f5b52  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800f5b57  jmp     short loc_1800F5B91
0x1800f5b59  call    ?NetBiosName@CMachineName@@QEAAPEAGXZ; CMachineName::NetBiosName(void)
0x1800f5b5e  test    rax, rax
0x1800f5b61  jz      short loc_1800F5B9E
0x1800f5b63  movzx   ebx, [rsp+298h+RootPathName]
0x1800f5b68  call    ?NetBiosName@CMachineName@@QEAAPEAGXZ; CMachineName::NetBiosName(void)
0x1800f5b6d  lea     rcx, [rdi+6]
0x1800f5b71  mov     r9, rax
0x1800f5b74  mov     [rsp+298h+var_270], rcx
0x1800f5b79  lea     r8, aLsLcLs; "\\\\%Ls\\%Lc$\\%Ls"
0x1800f5b80  mov     rcx, rbp; unsigned __int16 *
0x1800f5b83  mov     dword ptr [rsp+298h+var_278], ebx
0x1800f5b87  mov     edx, 105h; unsigned __int64
0x1800f5b8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f5b91  test    eax, eax
0x1800f5b93  js      loc_1800F5A56
0x1800f5b99  mov     [rsi], rbp
0x1800f5b9c  jmp     short loc_1800F5BA8
0x1800f5b9e  mov     eax, 8007000Eh
0x1800f5ba3  jmp     short loc_1800F5BAA
0x1800f5ba5  mov     [rsi], rdi
0x1800f5ba8  xor     eax, eax
0x1800f5baa  mov     rcx, [rsp+298h+var_28]
0x1800f5bb2  xor     rcx, rsp; StackCookie
0x1800f5bb5  call    __security_check_cookie
0x1800f5bba  mov     rbx, [rsp+298h+arg_0]
0x1800f5bc2  add     rsp, 280h
0x1800f5bc9  pop     rdi
0x1800f5bca  pop     rsi
0x1800f5bcb  pop     rbp
0x1800f5bcc  retn
```
