# HandlerImageEnumeration(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,CImgSrvPacket *)

- ea: `0x180003838`
- end: `0x180003aec`
- name: `?HandlerImageEnumeration@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXPEAVCImgSrvPacket@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, struct tagWDS_ENDPOINT *, void *, struct CImgSrvPacket *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006e50`

## callees

- `0x180003838`
- `0x180007b18`
- `0x180007c28`
- `0x180007fd8`
- `0x18000b370`
- `0x1800119d4`
- `0x1800121ac`
- `0x180012214`
- `0x180016020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003905`
- `KERNEL32!GetLastError` at `0x180003905`
- `KERNEL32!CloseHandle` at `0x180003a9f`
- `KERNEL32!CloseHandle` at `0x180003a9f`
- `KERNEL32!GetCurrentThread` at `0x1800038d9`
- `KERNEL32!GetCurrentThread` at `0x1800038d9`
- `ADVAPI32!OpenThreadToken` at `0x1800038f5`
- `ADVAPI32!OpenThreadToken` at `0x1800038f5`
- `WDSSRV!WdsSendReply` at `0x180003a22`
- `WDSSRV!WdsSendReply` at `0x180003a22`
- `WDSSRV!WdsImpersonateClient` at `0x1800038c7`
- `WDSSRV!WdsImpersonateClient` at `0x1800038c7`
- `WDSSRV!WdsPacketFree` at `0x180003a8a`
- `WDSSRV!WdsPacketFree` at `0x180003a8a`
- `WDSSRV!WdsRevertToSelf` at `0x180003916`
- `WDSSRV!WdsRevertToSelf` at `0x180003916`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x1800039f1`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x1800039f1`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180003a6c`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180003a6c`

## pseudocode

```c
__int64 __fastcall HandlerImageEnumeration(
        struct _IMG_SERVER_CONTEXT *a1,
        struct tagWDS_ENDPOINT *a2,
        void *a3,
        struct CImgSrvPacket *a4)
{
  __int64 Buffer; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  HANDLE CurrentThread; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  struct _IMG_SERVER_CONTEXT *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v27; // [rsp+40h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-11h] BYREF
  __int64 v29; // [rsp+50h] [rbp-9h] BYREF
  __int128 v30; // [rsp+58h] [rbp-1h] BYREF
  __int64 v31; // [rsp+68h] [rbp+Fh]
  int v32; // [rsp+70h] [rbp+17h]

  TokenHandle = 0;
  v29 = 0;
  v27 = 0;
  v31 = 0;
  v32 = 0;
  v30 = 0;
  WdsImgTrace(0x10000u, L"-> HandlerImageEnumeration");
  Buffer = CControlPacket::SendInitialize((CControlPacket *)&v30, g_hProvider, 0, 2u);
  if ( !(unsigned int)ElValidateWin32(Buffer, v8, v9, 444) )
  {
    LODWORD(Buffer) = WdsImpersonateClient(a3);
    if ( !(_DWORD)Buffer )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
        LODWORD(Buffer) = GetLastError();
      WdsRevertToSelf(a3);
    }
    if ( !(unsigned int)ElValidateWin32((unsigned int)Buffer, v10, v11, 453) )
    {
      Buffer = (unsigned int)CControlPacket::AddVariable<unsigned long>(
                               (unsigned int)&v30,
                               (unsigned int)L"VERSION",
                               0,
                               -1);
      if ( !(unsigned int)ElValidateWin32(Buffer, v13, v14, 461) )
      {
        Buffer = (unsigned int)CControlPacket::AddVariable<unsigned long>(
                                 (unsigned int)&v30,
                                 (unsigned int)L"SC",
                                 0,
                                 -1);
        if ( !(unsigned int)ElValidateWin32(Buffer, v15, v16, 469) )
        {
          Buffer = pAddImagesToReply(a1, a4, (struct CImgSrvPacket *)&v30, TokenHandle);
          if ( !(unsigned int)ElValidateWin32(Buffer, v17, v18, 479) )
          {
            Buffer = pAddImageEnumFlags(v19, (struct CImgSrvPacket *)&v30);
            if ( !(unsigned int)ElValidateWin32(Buffer, v20, v21, 486) )
            {
              Buffer = (unsigned int)WdsCpPacketGetBuffer(*((_QWORD *)&v30 + 1), &v29, &v27);
              if ( !(unsigned int)ElValidateWin32(Buffer, v22, v23, 493) )
              {
                Buffer = (unsigned int)WdsSendReply(a3, v29, v27, 0, 0);
                ElValidateWin32(Buffer, v24, v25, 500);
              }
            }
          }
        }
      }
    }
  }
  if ( (_DWORD)Buffer )
    CEventLog::Log((CEventLog *)g_EventLog, 0xC1060104, 2);
  if ( v29 )
    WdsPacketFree(g_hProvider, 0);
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  WdsImgTrace(0x10000u, L"<- HandlerImageEnumeration=%x", (unsigned int)Buffer);
  CControlPacket::Shutdown((CControlPacket *)&v30);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x180003838  push    rbp
0x18000383a  push    rbx
0x18000383b  push    rsi
0x18000383c  push    rdi
0x18000383d  push    r14
0x18000383f  push    r15
0x180003841  lea     rbp, [rsp-2Fh]
0x180003846  sub     rsp, 88h
0x18000384d  mov     rax, cs:__security_cookie
0x180003854  xor     rax, rsp
0x180003857  mov     [rbp+57h+var_38], rax
0x18000385b  and     [rbp+57h+TokenHandle], 0
0x180003860  xor     eax, eax
0x180003862  and     [rbp+57h+var_60], 0
0x180003867  mov     r15, rdx
0x18000386a  and     [rbp+57h+var_70], 0
0x18000386e  lea     rdx, aHandlerimageen; "-> HandlerImageEnumeration"
0x180003875  mov     rsi, rcx
0x180003878  mov     [rbp+57h+var_48], rax
0x18000387c  xorps   xmm0, xmm0
0x18000387f  mov     [rbp+57h+var_40], eax
0x180003882  mov     ecx, 10000h; unsigned int
0x180003887  mov     r14, r9
0x18000388a  movdqu  [rbp+57h+var_58], xmm0
0x18000388f  mov     rdi, r8
0x180003892  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003897  mov     rdx, cs:?g_hProvider@@3PEAXEA; void *
0x18000389e  lea     rcx, [rbp+57h+var_58]; this
0x1800038a2  mov     r9b, 2; unsigned __int8
0x1800038a5  xor     r8d, r8d; unsigned int
0x1800038a8  call    ?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z; CControlPacket::SendInitialize(void *,ulong,uchar)
0x1800038ad  mov     r9d, 1BCh
0x1800038b3  mov     ecx, eax
0x1800038b5  mov     ebx, eax
0x1800038b7  call    ElValidateWin32
0x1800038bc  test    eax, eax
0x1800038be  jnz     loc_180003A3D
0x1800038c4  mov     rcx, rdi
0x1800038c7  call    cs:__imp_WdsImpersonateClient
0x1800038ce  nop     dword ptr [rax+rax+00h]
0x1800038d3  mov     ebx, eax
0x1800038d5  test    eax, eax
0x1800038d7  jnz     short loc_180003922
0x1800038d9  call    cs:__imp_GetCurrentThread
0x1800038e0  nop     dword ptr [rax+rax+00h]
0x1800038e5  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800038e9  mov     edx, 20008h; DesiredAccess
0x1800038ee  mov     rcx, rax; ThreadHandle
0x1800038f1  lea     r8d, [rbx+1]; OpenAsSelf
0x1800038f5  call    cs:__imp_OpenThreadToken
0x1800038fc  nop     dword ptr [rax+rax+00h]
0x180003901  test    eax, eax
0x180003903  jnz     short loc_180003913
0x180003905  call    cs:__imp_GetLastError
0x18000390c  nop     dword ptr [rax+rax+00h]
0x180003911  mov     ebx, eax
0x180003913  mov     rcx, rdi
0x180003916  call    cs:__imp_WdsRevertToSelf
0x18000391d  nop     dword ptr [rax+rax+00h]
0x180003922  mov     r9d, 1C5h
0x180003928  mov     ecx, ebx
0x18000392a  call    ElValidateWin32
0x18000392f  test    eax, eax
0x180003931  jnz     loc_180003A3D
0x180003937  or      r9d, 0FFFFFFFFh
0x18000393b  mov     [rsp+0B0h+var_88], 1
0x180003943  xor     r8d, r8d
0x180003946  lea     rdx, aVersion_0; "VERSION"
0x18000394d  lea     rcx, [rbp+57h+var_58]
0x180003951  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x180003956  mov     r9d, 1CDh
0x18000395c  mov     ecx, eax
0x18000395e  mov     ebx, eax
0x180003960  call    ElValidateWin32
0x180003965  test    eax, eax
0x180003967  jnz     loc_180003A3D
0x18000396d  or      r9d, 0FFFFFFFFh
0x180003971  mov     [rsp+0B0h+var_88], 3
0x180003979  xor     r8d, r8d
0x18000397c  lea     rdx, aSc; "SC"
0x180003983  lea     rcx, [rbp+57h+var_58]
0x180003987  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18000398c  mov     r9d, 1D5h
0x180003992  mov     ecx, eax
0x180003994  mov     ebx, eax
0x180003996  call    ElValidateWin32
0x18000399b  test    eax, eax
0x18000399d  jnz     loc_180003A3D
0x1800039a3  mov     r9, [rbp+57h+TokenHandle]; void *
0x1800039a7  lea     r8, [rbp+57h+var_58]; struct CImgSrvPacket *
0x1800039ab  mov     rdx, r14; struct CImgSrvPacket *
0x1800039ae  mov     rcx, rsi; struct _IMG_SERVER_CONTEXT *
0x1800039b1  call    ?pAddImagesToReply@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAVCImgSrvPacket@@1PEAX@Z; pAddImagesToReply(_IMG_SERVER_CONTEXT *,CImgSrvPacket *,CImgSrvPacket *,void *)
0x1800039b6  mov     r9d, 1DFh
0x1800039bc  mov     ecx, eax
0x1800039be  mov     ebx, eax
0x1800039c0  call    ElValidateWin32
0x1800039c5  test    eax, eax
0x1800039c7  jnz     short loc_180003A3D
0x1800039c9  lea     rdx, [rbp+57h+var_58]; struct CImgSrvPacket *
0x1800039cd  call    ?pAddImageEnumFlags@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAVCImgSrvPacket@@@Z; pAddImageEnumFlags(_IMG_SERVER_CONTEXT *,CImgSrvPacket *)
0x1800039d2  mov     r9d, 1E6h
0x1800039d8  mov     ecx, eax
0x1800039da  mov     ebx, eax
0x1800039dc  call    ElValidateWin32
0x1800039e1  test    eax, eax
0x1800039e3  jnz     short loc_180003A3D
0x1800039e5  mov     rcx, qword ptr [rbp+57h+var_58+8]
0x1800039e9  lea     r8, [rbp+57h+var_70]
0x1800039ed  lea     rdx, [rbp+57h+var_60]
0x1800039f1  call    cs:__imp_WdsCpPacketGetBuffer
0x1800039f8  nop     dword ptr [rax+rax+00h]
0x1800039fd  mov     ecx, eax
0x1800039ff  mov     r9d, 1EDh
0x180003a05  mov     ebx, eax
0x180003a07  call    ElValidateWin32
0x180003a0c  test    eax, eax
0x180003a0e  jnz     short loc_180003A3D
0x180003a10  mov     r8d, [rbp+57h+var_70]
0x180003a14  xor     r9d, r9d
0x180003a17  mov     rdx, [rbp+57h+var_60]
0x180003a1b  mov     rcx, rdi
0x180003a1e  and     dword ptr [rsp+0B0h+var_90], eax
0x180003a22  call    cs:__imp_WdsSendReply
0x180003a29  nop     dword ptr [rax+rax+00h]
0x180003a2e  mov     ecx, eax
0x180003a30  mov     r9d, 1F4h
0x180003a36  mov     ebx, eax
0x180003a38  call    ElValidateWin32
0x180003a3d  test    ebx, ebx
0x180003a3f  jz      short loc_180003A78
0x180003a41  mov     r9d, 1
0x180003a47  mov     [rsp+0B0h+var_80], ebx
0x180003a4b  lea     rax, [r15+1Ch]
0x180003a4f  mov     [rsp+0B0h+var_88], 5
0x180003a57  mov     edx, 0C1060104h
0x180003a5c  mov     [rsp+0B0h+var_90], rax
0x180003a61  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x180003a68  lea     r8d, [r9+1]
0x180003a6c  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180003a73  nop     dword ptr [rax+rax+00h]
0x180003a78  mov     r8, [rbp+57h+var_60]
0x180003a7c  test    r8, r8
0x180003a7f  jz      short loc_180003A96
0x180003a81  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x180003a88  xor     edx, edx
0x180003a8a  call    cs:__imp_WdsPacketFree
0x180003a91  nop     dword ptr [rax+rax+00h]
0x180003a96  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180003a9a  test    rcx, rcx
0x180003a9d  jz      short loc_180003AB0
0x180003a9f  call    cs:__imp_CloseHandle
0x180003aa6  nop     dword ptr [rax+rax+00h]
0x180003aab  and     [rbp+57h+TokenHandle], 0
0x180003ab0  mov     r8d, ebx
0x180003ab3  lea     rdx, aHandlerimageen_0; "<- HandlerImageEnumeration=%x"
0x180003aba  mov     ecx, 10000h; unsigned int
0x180003abf  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003ac4  lea     rcx, [rbp+57h+var_58]; this
0x180003ac8  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x180003acd  mov     eax, ebx
0x180003acf  mov     rcx, [rbp+57h+var_38]
0x180003ad3  xor     rcx, rsp; StackCookie
0x180003ad6  call    __security_check_cookie
0x180003adb  add     rsp, 88h
0x180003ae2  pop     r15
0x180003ae4  pop     r14
0x180003ae6  pop     rdi
0x180003ae7  pop     rsi
0x180003ae8  pop     rbx
0x180003ae9  pop     rbp
0x180003aea  retn
```
