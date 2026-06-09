# CRdrPnpSession::OnConnect(void)

- ea: `0x180002eb4`
- end: `0x1800030ec`
- name: `?OnConnect@CRdrPnpSession@@QEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(CRdrPnpSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002b60`

## callees

- `0x180002eb4`
- `0x180003100`
- `0x180009768`
- `0x18000abc0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18003fe48`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002f2a`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180002ef4`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180002ef4`
- `WTSAPI32!WTSFreeMemory` at `0x180002f0b`
- `WTSAPI32!WTSFreeMemory` at `0x180002f0b`

## string_xrefs

- `0x180002fbe`: `CreateServerSideVCManager failed`
- `0x18000303a`: `CreateServerProtocolHandler FAILED`
- `0x1800030a1`: `spServerProtocolHandler->OnConnect FAILED`

## pseudocode

```c
__int64 __fastcall CRdrPnpSession::OnConnect(CRdrPnpSession *this)
{
  DWORD v1; // edx
  LPWSTR v3; // rcx
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  struct IServerVCChannelManager *v8; // r14
  int Instance; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // edx
  const char *v12; // rcx
  _QWORD *v13; // rdi
  __int64 v14; // rcx
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+40h] [rbp-10h]
  DWORD pBytesReturned; // [rsp+80h] [rbp+30h] BYREF
  LPWSTR ppBuffer; // [rsp+88h] [rbp+38h] BYREF
  struct IServerVCChannelManager *v20; // [rsp+90h] [rbp+40h] BYREF

  v1 = *((_DWORD *)this + 19);
  v20 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  if ( WTSQuerySessionInformationW(0, v1, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    v3 = ppBuffer;
    *((_BYTE *)this + 72) = *(_DWORD *)ppBuffer == 0;
    WTSFreeMemory(v3);
    ppBuffer = 0;
  }
  v17 = 0;
  v16 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  CTSDevPlatExeMain::Initialize((CTSDevPlatExeMain *)&v16, ModuleHandleW);
  v5 = *((_QWORD *)&v16 + 1);
  if ( *((_QWORD *)&v16 + 1) )
  {
    *((_QWORD *)&v16 + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = v16;
  if ( (_QWORD)v16 )
  {
    *(_QWORD *)&v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = CServerVCChannelManager::CreateInstance(&v20);
  v8 = v20;
  Instance = v7;
  if ( v7 >= 0 )
  {
    v13 = (_QWORD *)((char *)this + 88);
    v14 = *((_QWORD *)this + 11);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14);
      if ( *v13 )
      {
        TCntPtr<IDispatch>::SafeRelease((char *)this + 88);
        *v13 = 0;
      }
    }
    Instance = CServerHandler::CreateInstance((struct IPNPServerHandler **)this + 11);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IServerVCChannelManager *, unsigned __int64))(*(_QWORD *)*v13 + 24LL))(
                   *v13,
                   *((unsigned int *)this + 19),
                   *((unsigned __int8 *)this + 72),
                   v8,
                   ((unsigned __int64)this + 48) & -(__int64)(this != 0));
      if ( Instance < 0
        && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 14;
        v12 = "spServerProtocolHandler->OnConnect FAILED";
        goto LABEL_25;
      }
    }
    else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
           && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 13;
      v12 = "CreateServerProtocolHandler FAILED";
      goto LABEL_25;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 12;
    v12 = "CreateServerSideVCManager failed";
LABEL_25:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v11,
      (unsigned int)WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v12,
      Instance);
  }
  if ( v8 )
    (*(void (__fastcall **)(struct IServerVCChannelManager *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180002eb4  push    rbp
0x180002eb6  push    rbx
0x180002eb7  push    rsi
0x180002eb8  push    rdi
0x180002eb9  push    r14
0x180002ebb  mov     rbp, rsp
0x180002ebe  sub     rsp, 50h
0x180002ec2  mov     edx, [rcx+4Ch]; SessionId
0x180002ec5  lea     rax, [rbp+arg_0]
0x180002ec9  mov     rsi, rcx
0x180002ecc  mov     [rsp+50h+pBytesReturned], rax; pBytesReturned
0x180002ed1  xor     ecx, ecx; hServer
0x180002ed3  mov     [rbp+arg_10], 0
0x180002edb  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180002edf  mov     [rbp+ppBuffer], 0
0x180002ee7  mov     r8d, 8; WTSInfoClass
0x180002eed  mov     [rbp+arg_0], 0
0x180002ef4  call    cs:__imp_WTSQuerySessionInformationW
0x180002efa  test    eax, eax
0x180002efc  jz      short loc_180002F19
0x180002efe  mov     rcx, [rbp+ppBuffer]; pMemory
0x180002f02  cmp     dword ptr [rcx], 0
0x180002f05  setz    al
0x180002f08  mov     [rsi+48h], al
0x180002f0b  call    cs:__imp_WTSFreeMemory
0x180002f11  mov     [rbp+ppBuffer], 0
0x180002f19  xorps   xmm0, xmm0
0x180002f1c  mov     [rbp+var_10], 0
0x180002f23  xor     ecx, ecx; lpModuleName
0x180002f25  movdqu  [rbp+var_20], xmm0
0x180002f2a  call    cs:__imp_GetModuleHandleW
0x180002f30  mov     rdx, rax; void *
0x180002f33  lea     rcx, [rbp+var_20]; this
0x180002f37  call    ?Initialize@CTSDevPlatExeMain@@QEAAJPEAX@Z; CTSDevPlatExeMain::Initialize(void *)
0x180002f3c  mov     rcx, qword ptr [rbp+var_20+8]
0x180002f40  test    rcx, rcx
0x180002f43  jz      short loc_180002F59
0x180002f45  mov     qword ptr [rbp+var_20+8], 0
0x180002f4d  mov     rax, [rcx]
0x180002f50  mov     rax, [rax+10h]
0x180002f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f59  mov     rcx, qword ptr [rbp+var_20]
0x180002f5d  test    rcx, rcx
0x180002f60  jz      short loc_180002F76
0x180002f62  mov     qword ptr [rbp+var_20], 0
0x180002f6a  mov     rax, [rcx]
0x180002f6d  mov     rax, [rax+10h]
0x180002f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f76  lea     rcx, [rbp+arg_10]; struct IServerVCChannelManager **
0x180002f7a  call    ?CreateInstance@CServerVCChannelManager@@SAJPEAPEAUIServerVCChannelManager@@@Z; CServerVCChannelManager::CreateInstance(IServerVCChannelManager * *)
0x180002f7f  mov     r14, [rbp+arg_10]
0x180002f83  mov     ebx, eax
0x180002f85  test    eax, eax
0x180002f87  jns     short loc_180002FCA
0x180002f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f90  lea     rax, WPP_GLOBAL_Control
0x180002f97  cmp     rcx, rax
0x180002f9a  jz      loc_1800030CB
0x180002fa0  test    byte ptr [rcx+1Ch], 8
0x180002fa4  jz      loc_1800030CB
0x180002faa  cmp     byte ptr [rcx+19h], 2
0x180002fae  jb      loc_1800030CB
0x180002fb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180002fb9  mov     edx, 0Ch
0x180002fbe  lea     rcx, aCreateserversi; "CreateServerSideVCManager failed"
0x180002fc5  jmp     loc_1800030A8
0x180002fca  lea     rdi, [rsi+58h]
0x180002fce  mov     rcx, [rdi]
0x180002fd1  test    rcx, rcx
0x180002fd4  jz      short loc_180002FF7
0x180002fd6  mov     rax, [rcx]
0x180002fd9  mov     rax, [rax+20h]
0x180002fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe2  cmp     qword ptr [rdi], 0
0x180002fe6  jz      short loc_180002FF7
0x180002fe8  mov     rcx, rdi
0x180002feb  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180002ff0  mov     qword ptr [rdi], 0
0x180002ff7  mov     rcx, rdi; struct IPNPServerHandler **
0x180002ffa  call    ?CreateInstance@CServerHandler@@SAJPEAPEAUIPNPServerHandler@@@Z; CServerHandler::CreateInstance(IPNPServerHandler * *)
0x180002fff  mov     ebx, eax
0x180003001  test    eax, eax
0x180003003  jns     short loc_180003043
0x180003005  mov     rcx, cs:WPP_GLOBAL_Control
0x18000300c  lea     rax, WPP_GLOBAL_Control
0x180003013  cmp     rcx, rax
0x180003016  jz      loc_1800030CB
0x18000301c  test    byte ptr [rcx+1Ch], 8
0x180003020  jz      loc_1800030CB
0x180003026  cmp     byte ptr [rcx+19h], 2
0x18000302a  jb      loc_1800030CB
0x180003030  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180003035  mov     edx, 0Dh
0x18000303a  lea     rcx, aCreateserverpr; "CreateServerProtocolHandler FAILED"
0x180003041  jmp     short loc_1800030A8
0x180003043  mov     rcx, [rdi]
0x180003046  lea     rdx, [rsi+30h]
0x18000304a  movzx   r8d, byte ptr [rsi+48h]
0x18000304f  mov     rax, rsi
0x180003052  neg     rax
0x180003055  mov     r10, [rcx]
0x180003058  sbb     r9, r9
0x18000305b  and     r9, rdx
0x18000305e  mov     edx, [rsi+4Ch]
0x180003061  mov     [rsp+50h+pBytesReturned], r9
0x180003066  mov     r9, r14
0x180003069  mov     rax, [r10+18h]
0x18000306d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003072  mov     ebx, eax
0x180003074  test    eax, eax
0x180003076  jns     short loc_1800030CB
0x180003078  mov     rcx, cs:WPP_GLOBAL_Control
0x18000307f  lea     rax, WPP_GLOBAL_Control
0x180003086  cmp     rcx, rax
0x180003089  jz      short loc_1800030CB
0x18000308b  test    byte ptr [rcx+1Ch], 8
0x18000308f  jz      short loc_1800030CB
0x180003091  cmp     byte ptr [rcx+19h], 2
0x180003095  jb      short loc_1800030CB
0x180003097  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000309c  mov     edx, 0Eh
0x1800030a1  lea     rcx, aSpserverprotoc; "spServerProtocolHandler->OnConnect FAIL"...
0x1800030a8  mov     [rsp+50h+var_28], ebx
0x1800030ac  lea     r8, WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids
0x1800030b3  mov     [rsp+50h+pBytesReturned], rcx
0x1800030b8  mov     r9d, eax
0x1800030bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030c2  mov     rcx, [rcx+10h]
0x1800030c6  call    WPP_SF_DsD
0x1800030cb  test    r14, r14
0x1800030ce  jz      short loc_1800030DF
0x1800030d0  mov     rax, [r14]
0x1800030d3  mov     rcx, r14
0x1800030d6  mov     rax, [rax+10h]
0x1800030da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030df  mov     eax, ebx
0x1800030e1  add     rsp, 50h
0x1800030e5  pop     r14
0x1800030e7  pop     rdi
0x1800030e8  pop     rsi
0x1800030e9  pop     rbx
0x1800030ea  pop     rbp
0x1800030eb  retn
```
