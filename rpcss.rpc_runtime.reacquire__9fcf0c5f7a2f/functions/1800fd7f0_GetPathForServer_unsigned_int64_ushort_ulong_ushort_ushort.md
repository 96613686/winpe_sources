# GetPathForServer(unsigned __int64,ushort *,ulong,ushort *,ushort * *)

- ea: `0x1800fd7f0`
- end: `0x1800fdae2`
- name: `?GetPathForServer@@YAJ_KPEAGK1PEAPEAG@Z`
- size: `754`
- prototype: `int(unsigned __int64, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fab44`

## callees

- `0x18001037c`
- `0x1800117e8`
- `0x180011db0`
- `0x180034260`
- `0x180074d98`
- `0x1800855d8`
- `0x1800b7ac0`
- `0x1800f8410`
- `0x1800fd7f0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800fd87d`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd964`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd87d`
- `RPCRT4!RpcImpersonateClient` at `0x1800fd964`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd8d0`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd9f0`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd8d0`
- `RPCRT4!RpcRevertToSelf` at `0x1800fd9f0`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800fd8c2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800fd8c2`
- `MPR!WNetGetUniversalNameW` at `0x1800fd9e2`
- `MPR!WNetGetUniversalNameW` at `0x1800fd9e2`

## string_xrefs

- `0x1800fd94c`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd9ba`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fda48`: `onecore\com\combase\rpcss\olescm\actmisc.cxx`
- `0x1800fd937`: `GetPathForServer`
- `0x1800fd9ab`: `GetPathForServer`
- `0x1800fda33`: `GetPathForServer`

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
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
          if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          return 2148007939LL;
        v7 = 338;
        goto LABEL_27;
      }
      UniversalNameW = WNetGetUniversalNameW(a2, 1u, &Buffer, &BufferSize);
      RpcRevertToSelf();
      if ( UniversalNameW )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
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
0x1800fd7f0  mov     [rsp+arg_0], rbx
0x1800fd7f5  push    rbp
0x1800fd7f6  push    rsi
0x1800fd7f7  push    rdi
0x1800fd7f8  sub     rsp, 280h
0x1800fd7ff  mov     rax, cs:__security_cookie
0x1800fd806  xor     rax, rsp
0x1800fd809  mov     [rsp+298h+var_28], rax
0x1800fd811  mov     rsi, [rsp+298h+arg_20]
0x1800fd819  mov     rbp, r9
0x1800fd81c  mov     [rsp+298h+BufferSize], 220h
0x1800fd824  mov     rdi, rdx
0x1800fd827  mov     qword ptr [rsi], 0
0x1800fd82e  test    rdx, rdx
0x1800fd831  jz      loc_1800FDAB9
0x1800fd837  mov     r9d, 3; unsigned __int64
0x1800fd83d  cmp     rcx, r9
0x1800fd840  jbe     loc_1800FDAB9
0x1800fd846  cmp     word ptr [rdx+2], 3Ah ; ':'
0x1800fd84b  jnz     loc_1800FDAB9
0x1800fd851  lea     ebx, [r9+59h]
0x1800fd855  cmp     [rdx+4], bx
0x1800fd859  jnz     loc_1800FDAB9
0x1800fd85f  mov     r8, rdx; unsigned __int16 *
0x1800fd862  lea     rcx, [rsp+298h+RootPathName]; unsigned __int16 *
0x1800fd867  lea     edx, [rbx-58h]; unsigned __int64
0x1800fd86a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800fd86f  test    eax, eax
0x1800fd871  js      loc_1800FD958
0x1800fd877  xor     ecx, ecx; BindingHandle
0x1800fd879  mov     [rsp+298h+var_24C], ebx
0x1800fd87d  call    cs:__imp_RpcImpersonateClient
0x1800fd884  nop     dword ptr [rax+rax+00h]
0x1800fd889  test    eax, eax
0x1800fd88b  jz      short loc_1800FD8BD
0x1800fd88d  mov     eax, cs:dword_1801574B8
0x1800fd893  test    eax, eax
0x1800fd895  jnz     short loc_1800FD8B2
0x1800fd897  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800fd89d  jz      loc_1800FD9C6
0x1800fd8a3  xor     ecx, ecx
0x1800fd8a5  call    IsWppLevelEnabled
0x1800fd8aa  test    al, al
0x1800fd8ac  jz      loc_1800FD9C6
0x1800fd8b2  mov     r8d, 12Eh
0x1800fd8b8  jmp     loc_1800FD997
0x1800fd8bd  lea     rcx, [rsp+298h+RootPathName]; lpRootPathName
0x1800fd8c2  call    cs:__imp_GetDriveTypeW
0x1800fd8c9  nop     dword ptr [rax+rax+00h]
0x1800fd8ce  mov     ebx, eax
0x1800fd8d0  call    cs:__imp_RpcRevertToSelf
0x1800fd8d7  nop     dword ptr [rax+rax+00h]
0x1800fd8dc  test    ebx, ebx
0x1800fd8de  jz      short loc_1800FD906
0x1800fd8e0  sub     ebx, 1
0x1800fd8e3  jz      short loc_1800FD906
0x1800fd8e5  sub     ebx, 1
0x1800fd8e8  jz      short loc_1800FD906
0x1800fd8ea  sub     ebx, 1
0x1800fd8ed  jz      loc_1800FDA6D
0x1800fd8f3  sub     ebx, 1
0x1800fd8f6  jz      short loc_1800FD962
0x1800fd8f8  sub     ebx, 1
0x1800fd8fb  jz      short loc_1800FD906
0x1800fd8fd  cmp     ebx, 1
0x1800fd900  jnz     loc_1800FDABC
0x1800fd906  mov     eax, cs:dword_1801574B8
0x1800fd90c  test    eax, eax
0x1800fd90e  jnz     short loc_1800FD923
0x1800fd910  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800fd916  jz      short loc_1800FD958
0x1800fd918  xor     ecx, ecx
0x1800fd91a  call    IsWppLevelEnabled
0x1800fd91f  test    al, al
0x1800fd921  jz      short loc_1800FD958
0x1800fd923  mov     [rsp+298h+var_268], 80080004h
0x1800fd92b  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800fd932  mov     [rsp+298h+var_270], rdi
0x1800fd937  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800fd93e  xor     r9d, r9d
0x1800fd941  mov     [rsp+298h+var_278], rax
0x1800fd946  mov     r8d, 141h
0x1800fd94c  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd953  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800fd958  mov     eax, 80080004h
0x1800fd95d  jmp     loc_1800FDABE
0x1800fd962  xor     ecx, ecx; BindingHandle
0x1800fd964  call    cs:__imp_RpcImpersonateClient
0x1800fd96b  nop     dword ptr [rax+rax+00h]
0x1800fd970  test    eax, eax
0x1800fd972  jz      short loc_1800FD9D0
0x1800fd974  mov     eax, cs:dword_1801574B8
0x1800fd97a  test    eax, eax
0x1800fd97c  jnz     short loc_1800FD991
0x1800fd97e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800fd984  jz      short loc_1800FD9C6
0x1800fd986  xor     ecx, ecx
0x1800fd988  call    IsWppLevelEnabled
0x1800fd98d  test    al, al
0x1800fd98f  jz      short loc_1800FD9C6
0x1800fd991  mov     r8d, 152h
0x1800fd997  mov     [rsp+298h+var_268], 80080003h
0x1800fd99f  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800fd9a6  mov     [rsp+298h+var_270], rdi
0x1800fd9ab  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800fd9b2  xor     r9d, r9d
0x1800fd9b5  mov     [rsp+298h+var_278], rax
0x1800fd9ba  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fd9c1  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800fd9c6  mov     eax, 80080003h
0x1800fd9cb  jmp     loc_1800FDABE
0x1800fd9d0  lea     r9, [rsp+298h+BufferSize]; lpBufferSize
0x1800fd9d5  mov     edx, 1; dwInfoLevel
0x1800fd9da  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x1800fd9df  mov     rcx, rdi; lpLocalPath
0x1800fd9e2  call    cs:__imp_WNetGetUniversalNameW
0x1800fd9e9  nop     dword ptr [rax+rax+00h]
0x1800fd9ee  mov     ebx, eax
0x1800fd9f0  call    cs:__imp_RpcRevertToSelf
0x1800fd9f7  nop     dword ptr [rax+rax+00h]
0x1800fd9fc  test    ebx, ebx
0x1800fd9fe  jz      short loc_1800FDA59
0x1800fda00  mov     ecx, cs:dword_1801574B8
0x1800fda06  test    ecx, ecx
0x1800fda08  jnz     short loc_1800FDA23
0x1800fda0a  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x1800fda10  jz      loc_1800FD958
0x1800fda16  call    IsWppLevelEnabled
0x1800fda1b  test    al, al
0x1800fda1d  jz      loc_1800FD958
0x1800fda23  mov     [rsp+298h+var_268], ebx
0x1800fda27  lea     rax, aWsStatus; "%ws %!STATUS!"
0x1800fda2e  mov     [rsp+298h+var_270], rdi
0x1800fda33  lea     rdx, aGetpathforserv; "GetPathForServer"
0x1800fda3a  xor     r9d, r9d
0x1800fda3d  mov     [rsp+298h+var_278], rax
0x1800fda42  mov     r8d, 15Eh
0x1800fda48  lea     rcx, aOnecoreComComb_16; "onecore\\com\\combase\\rpcss\\olescm\\a"...
0x1800fda4f  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x1800fda54  jmp     loc_1800FD958
0x1800fda59  mov     r8, [rsp+298h+Buffer]; unsigned __int16 *
0x1800fda5e  mov     edx, 105h; unsigned __int64
0x1800fda63  mov     rcx, rbp; unsigned __int16 *
0x1800fda66  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800fda6b  jmp     short loc_1800FDAA5
0x1800fda6d  call    ?NetBiosName@CMachineName@@QEAAPEAGXZ; CMachineName::NetBiosName(void)
0x1800fda72  test    rax, rax
0x1800fda75  jz      short loc_1800FDAB2
0x1800fda77  movzx   ebx, [rsp+298h+RootPathName]
0x1800fda7c  call    ?NetBiosName@CMachineName@@QEAAPEAGXZ; CMachineName::NetBiosName(void)
0x1800fda81  lea     rcx, [rdi+6]
0x1800fda85  mov     r9, rax
0x1800fda88  mov     [rsp+298h+var_270], rcx
0x1800fda8d  lea     r8, aLsLcLs; "\\\\%Ls\\%Lc$\\%Ls"
0x1800fda94  mov     rcx, rbp; unsigned __int16 *
0x1800fda97  mov     dword ptr [rsp+298h+var_278], ebx
0x1800fda9b  mov     edx, 105h; unsigned __int64
0x1800fdaa0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fdaa5  test    eax, eax
0x1800fdaa7  js      loc_1800FD958
0x1800fdaad  mov     [rsi], rbp
0x1800fdab0  jmp     short loc_1800FDABC
0x1800fdab2  mov     eax, 8007000Eh
0x1800fdab7  jmp     short loc_1800FDABE
0x1800fdab9  mov     [rsi], rdi
0x1800fdabc  xor     eax, eax
0x1800fdabe  mov     rcx, [rsp+298h+var_28]
0x1800fdac6  xor     rcx, rsp; StackCookie
0x1800fdac9  call    __security_check_cookie
0x1800fdace  mov     rbx, [rsp+298h+arg_0]
0x1800fdad6  add     rsp, 280h
0x1800fdadd  pop     rdi
0x1800fdade  pop     rsi
0x1800fdadf  pop     rbp
0x1800fdae0  retn
```
