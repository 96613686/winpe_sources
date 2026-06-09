# DavServiceStop

- ea: `0x180025bf8`
- end: `0x180025eb4`
- name: `DavServiceStop`
- size: `700`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180025ec0`
- `0x180025f10`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000c2b8`
- `0x18000c628`
- `0x18000c730`
- `0x18000cc84`
- `0x18000fb90`
- `0x180025bf8`
- `0x180026980`
- `0x180028eb4`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180025d8b`
- `ntdll!NtFsControlFile` at `0x180025d8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025ddc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025e6e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025e6e`
- `RPCRT4!RpcServerUnregisterIf` at `0x180025ca4`
- `RPCRT4!RpcServerUnregisterIf` at `0x180025ca4`
- `WS2_32!__imp_WSAGetLastError` at `0x180025cc9`
- `WS2_32!__imp_WSAGetLastError` at `0x180025cc9`
- `WS2_32!__imp_WSACleanup` at `0x180025cbe`
- `WS2_32!__imp_WSACleanup` at `0x180025cbe`

## pseudocode

```c
__int64 DavServiceStop()
{
  unsigned int v0; // eax
  unsigned int v1; // eax
  unsigned int Error; // eax
  unsigned int v3; // ebx
  _BYTE *v4; // rcx
  bool v5; // zf
  unsigned int v6; // eax
  HLOCAL v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  unsigned int v9; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF

  if ( g_WorkersActive )
  {
    v0 = DavTerminateWorkerThreads();
    if ( v0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v0);
    g_WorkersActive = 0;
  }
  if ( g_ThreadPoolActive )
  {
    v1 = DavCleanupThreadPool();
    if ( v1 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v1);
    g_ThreadPoolActive = 0;
  }
  if ( g_RpcActive )
  {
    RpcServerUnregisterIf(qword_18002F6B0, 0, 1u);
    g_RpcActive = 0;
  }
  DavClose();
  if ( g_socketinit )
  {
    if ( WSACleanup() == -1 )
    {
      Error = WSAGetLastError();
      v3 = Error;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids, Error);
        v4 = WPP_GLOBAL_Control;
      }
      if ( !v3 || v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
        goto LABEL_25;
      WPP_SF_d(*((_QWORD *)v4 + 2), 15, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v3);
    }
    v4 = WPP_GLOBAL_Control;
LABEL_25:
    g_socketinit = 0;
    goto LABEL_27;
  }
  v4 = WPP_GLOBAL_Control;
LABEL_27:
  if ( !DavReflectorHandle )
    goto LABEL_42;
  v5 = *((_QWORD *)DavReflectorHandle + 1) == -1;
  IoStatusBlock = 0;
  if ( v5 )
  {
    v6 = 110;
  }
  else
  {
    v6 = NtFsControlFile(*((HANDLE *)DavReflectorHandle + 1), 0, 0, 0, &IoStatusBlock, 0x140390u, 0, 0, 0, 0);
    v4 = WPP_GLOBAL_Control;
    if ( !v6 )
      goto LABEL_35;
  }
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 2), 16, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v6);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_35:
  v7 = DavReflectorHandle;
  if ( DavReflectorHandle )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)DavReflectorHandle + 16);
    *((_DWORD *)DavReflectorHandle + 16) = 1;
    EnterCriticalSection(v8);
    DereferenceReflectorBlock(v7);
  }
  else
  {
    if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 1) == 0 )
      goto LABEL_41;
    WPP_SF_d(*((_QWORD *)v4 + 2), 17, WPP_3c901703a5983ce609c0997329a96280_Traceguids, 87);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_41:
  DavReflectorHandle = 0;
LABEL_42:
  if ( !g_RedirLoaded )
    goto LABEL_49;
  v9 = WsUnloadRedir();
  if ( v9 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_48;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v9);
  }
  v4 = WPP_GLOBAL_Control;
LABEL_48:
  g_RedirLoaded = 0;
LABEL_49:
  if ( g_DavServiceLockSet )
  {
    DeleteCriticalSection(&g_DavServiceLock);
    v4 = WPP_GLOBAL_Control;
    g_DavServiceLockSet = 0;
  }
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)v4 + 2), 19, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
  UpdateServiceStatus(1);
  return WppCleanupUm();
}

```

## disassembly

```asm
0x180025bf8  push    rbx
0x180025bfa  push    rbp
0x180025bfb  push    rsi
0x180025bfc  push    rdi
0x180025bfd  push    r14
0x180025bff  sub     rsp, 60h
0x180025c03  xor     edi, edi
0x180025c05  lea     rbp, WPP_GLOBAL_Control
0x180025c0c  cmp     cs:g_WorkersActive, edi
0x180025c12  lea     r14, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x180025c19  mov     esi, 1
0x180025c1e  jz      short loc_180025C53
0x180025c20  call    DavTerminateWorkerThreads
0x180025c25  test    eax, eax
0x180025c27  jz      short loc_180025C4D
0x180025c29  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c30  cmp     rcx, rbp
0x180025c33  jz      short loc_180025C4D
0x180025c35  test    [rcx+1Ch], sil
0x180025c39  jz      short loc_180025C4D
0x180025c3b  mov     rcx, [rcx+10h]
0x180025c3f  lea     edx, [rsi+0Ch]
0x180025c42  mov     r9d, eax
0x180025c45  mov     r8, r14
0x180025c48  call    WPP_SF_d
0x180025c4d  mov     cs:g_WorkersActive, edi
0x180025c53  cmp     cs:g_ThreadPoolActive, edi
0x180025c59  jz      short loc_180025C90
0x180025c5b  call    DavCleanupThreadPool
0x180025c60  test    eax, eax
0x180025c62  jz      short loc_180025C8A
0x180025c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c6b  cmp     rcx, rbp
0x180025c6e  jz      short loc_180025C8A
0x180025c70  test    [rcx+1Ch], sil
0x180025c74  jz      short loc_180025C8A
0x180025c76  mov     rcx, [rcx+10h]
0x180025c7a  mov     edx, 0Eh
0x180025c7f  mov     r9d, eax
0x180025c82  mov     r8, r14
0x180025c85  call    WPP_SF_d
0x180025c8a  mov     cs:g_ThreadPoolActive, edi
0x180025c90  cmp     cs:g_RpcActive, edi
0x180025c96  jz      short loc_180025CB0
0x180025c98  mov     r8d, esi; WaitForCallsToComplete
0x180025c9b  lea     rcx, qword_18002F6B0; IfSpec
0x180025ca2  xor     edx, edx; MgrTypeUuid
0x180025ca4  call    cs:__imp_RpcServerUnregisterIf
0x180025caa  mov     cs:g_RpcActive, edi
0x180025cb0  call    DavClose
0x180025cb5  cmp     cs:g_socketinit, dil
0x180025cbc  jz      short loc_180025D35
0x180025cbe  call    cs:__imp_WSACleanup
0x180025cc4  cmp     eax, 0FFFFFFFFh
0x180025cc7  jnz     short loc_180025D25
0x180025cc9  call    cs:__imp_WSAGetLastError
0x180025ccf  mov     ebx, eax
0x180025cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cd8  cmp     rcx, rbp
0x180025cdb  jz      short loc_180025D02
0x180025cdd  test    [rcx+1Ch], sil
0x180025ce1  jz      short loc_180025D02
0x180025ce3  mov     rcx, [rcx+10h]
0x180025ce7  lea     r8, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids
0x180025cee  mov     edx, 0Dh
0x180025cf3  mov     r9d, eax
0x180025cf6  call    WPP_SF_d
0x180025cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d02  test    ebx, ebx
0x180025d04  jz      short loc_180025D2C
0x180025d06  cmp     rcx, rbp
0x180025d09  jz      short loc_180025D2C
0x180025d0b  test    [rcx+1Ch], sil
0x180025d0f  jz      short loc_180025D2C
0x180025d11  mov     rcx, [rcx+10h]
0x180025d15  mov     edx, 0Fh
0x180025d1a  mov     r9d, ebx
0x180025d1d  mov     r8, r14
0x180025d20  call    WPP_SF_d
0x180025d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d2c  mov     cs:g_socketinit, dil
0x180025d33  jmp     short loc_180025D3C
0x180025d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d3c  mov     rax, cs:DavReflectorHandle
0x180025d43  test    rax, rax
0x180025d46  jz      loc_180025E1A
0x180025d4c  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180025d51  xorps   xmm0, xmm0
0x180025d54  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x180025d59  jz      short loc_180025D9E
0x180025d5b  mov     [rsp+88h+OutputBufferLength], edi; OutputBufferLength
0x180025d5f  lea     rcx, [rsp+88h+var_38]
0x180025d64  mov     [rsp+88h+OutputBuffer], rdi; OutputBuffer
0x180025d69  xor     r9d, r9d; ApcContext
0x180025d6c  mov     [rsp+88h+InputBufferLength], edi; InputBufferLength
0x180025d70  xor     r8d, r8d; ApcRoutine
0x180025d73  mov     [rsp+88h+InputBuffer], rdi; InputBuffer
0x180025d78  xor     edx, edx; Event
0x180025d7a  mov     [rsp+88h+FsControlCode], 140390h; FsControlCode
0x180025d82  mov     [rsp+88h+IoStatusBlock], rcx; IoStatusBlock
0x180025d87  mov     rcx, [rax+8]; FileHandle
0x180025d8b  call    cs:__imp_NtFsControlFile
0x180025d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d98  test    eax, eax
0x180025d9a  jnz     short loc_180025DA3
0x180025d9c  jmp     short loc_180025DC9
0x180025d9e  mov     eax, 6Eh ; 'n'
0x180025da3  cmp     rcx, rbp
0x180025da6  jz      short loc_180025DC9
0x180025da8  test    [rcx+1Ch], sil
0x180025dac  jz      short loc_180025DC9
0x180025dae  mov     rcx, [rcx+10h]
0x180025db2  mov     edx, 10h
0x180025db7  mov     r9d, eax
0x180025dba  mov     r8, r14
0x180025dbd  call    WPP_SF_d
0x180025dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dc9  mov     rbx, cs:DavReflectorHandle
0x180025dd0  test    rbx, rbx
0x180025dd3  jz      short loc_180025DEC
0x180025dd5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180025dd9  mov     [rbx+40h], esi
0x180025ddc  call    cs:__imp_EnterCriticalSection
0x180025de2  mov     rcx, rbx; hMem
0x180025de5  call    DereferenceReflectorBlock
0x180025dea  jmp     short loc_180025E0C
0x180025dec  cmp     rcx, rbp
0x180025def  jz      short loc_180025E13
0x180025df1  test    [rcx+1Ch], sil
0x180025df5  jz      short loc_180025E13
0x180025df7  mov     rcx, [rcx+10h]
0x180025dfb  mov     edx, 11h
0x180025e00  mov     r8, r14
0x180025e03  lea     r9d, [rdx+46h]
0x180025e07  call    WPP_SF_d
0x180025e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e13  mov     cs:DavReflectorHandle, rdi
0x180025e1a  cmp     cs:g_RedirLoaded, edi
0x180025e20  jz      short loc_180025E5E
0x180025e22  call    WsUnloadRedir
0x180025e27  test    eax, eax
0x180025e29  jz      short loc_180025E51
0x180025e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e32  cmp     rcx, rbp
0x180025e35  jz      short loc_180025E58
0x180025e37  test    [rcx+1Ch], sil
0x180025e3b  jz      short loc_180025E58
0x180025e3d  mov     rcx, [rcx+10h]
0x180025e41  mov     edx, 12h
0x180025e46  mov     r9d, eax
0x180025e49  mov     r8, r14
0x180025e4c  call    WPP_SF_d
0x180025e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e58  mov     cs:g_RedirLoaded, edi
0x180025e5e  cmp     cs:g_DavServiceLockSet, dil
0x180025e65  jz      short loc_180025E82
0x180025e67  lea     rcx, g_DavServiceLock; lpCriticalSection
0x180025e6e  call    cs:__imp_DeleteCriticalSection
0x180025e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e7b  mov     cs:g_DavServiceLockSet, dil
0x180025e82  cmp     rcx, rbp
0x180025e85  jz      short loc_180025E9E
0x180025e87  test    byte ptr [rcx+1Ch], 10h
0x180025e8b  jz      short loc_180025E9E
0x180025e8d  mov     rcx, [rcx+10h]
0x180025e91  mov     edx, 13h
0x180025e96  mov     r8, r14
0x180025e99  call    WPP_SF_
0x180025e9e  mov     ecx, esi
0x180025ea0  call    UpdateServiceStatus
0x180025ea5  add     rsp, 60h
0x180025ea9  pop     r14
0x180025eab  pop     rdi
0x180025eac  pop     rsi
0x180025ead  pop     rbp
0x180025eae  pop     rbx
0x180025eaf  jmp     WppCleanupUm
```
