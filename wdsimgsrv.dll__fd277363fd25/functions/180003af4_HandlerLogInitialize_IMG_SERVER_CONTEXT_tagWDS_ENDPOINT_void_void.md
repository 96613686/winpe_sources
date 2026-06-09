# HandlerLogInitialize(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,void *)

- ea: `0x180003af4`
- end: `0x180003dbc`
- name: `?HandlerLogInitialize@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAX2@Z`
- size: `712`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, struct tagWDS_ENDPOINT *, void *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006e50`

## callees

- `0x1800036b0`
- `0x180003af4`
- `0x180007eb4`
- `0x180007fd8`
- `0x18000b370`
- `0x18000b5b0`
- `0x18000fdf8`
- `0x18000fe8c`
- `0x180016020`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180003bf1`
- `RPCRT4!UuidToStringW` at `0x180003bf1`
- `RPCRT4!RpcStringFreeW` at `0x180003d7f`
- `RPCRT4!RpcStringFreeW` at `0x180003d7f`
- `RPCRT4!UuidCreate` at `0x180003bb9`
- `RPCRT4!UuidCreate` at `0x180003bb9`
- `WDSSRV!WdsSendReply` at `0x180003cd8`
- `WDSSRV!WdsSendReply` at `0x180003cd8`
- `WDSSRV!WdsPacketFree` at `0x180003d53`
- `WDSSRV!WdsPacketFree` at `0x180003d53`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x180003ca7`
- `WDSCSL!WdsCpPacketGetBuffer` at `0x180003ca7`
- `WDSCSL!WdsCpPacketRelease` at `0x180003d68`
- `WDSCSL!WdsCpPacketRelease` at `0x180003d68`
- `WDSCSL!WdsCpPacketInitialize` at `0x180003b6f`
- `WDSCSL!WdsCpPacketInitialize` at `0x180003b6f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180003c3d`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x180003c3d`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180003d25`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180003d25`

## pseudocode

```c
__int64 __fastcall HandlerLogInitialize(struct _IMG_SERVER_CONTEXT *a1, struct tagWDS_ENDPOINT *a2, void *a3, void *a4)
{
  __int64 ClientLoggingLevel; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  RPC_STATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // eax
  struct tagWDS_ENDPOINT *v26; // rdx
  struct _IMG_SERVER_CONTEXT *v27; // rcx
  unsigned int v28; // ebx
  void *v30; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v32; // [rsp+4Ch] [rbp-Dh] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-9h] BYREF
  __int64 v34; // [rsp+58h] [rbp-1h] BYREF
  __int64 v35; // [rsp+60h] [rbp+7h] BYREF
  int v36; // [rsp+68h] [rbp+Fh]
  UUID Uuid; // [rsp+70h] [rbp+17h] BYREF

  v30 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  StringUuid = 0;
  v35 = 0;
  v36 = 0;
  Uuid = 0;
  WdsImgTrace(0x10000u, L"-> HandlerLogInitialize", a3, a4);
  v36 = 0;
  LODWORD(v35) = 12;
  BYTE4(v35) = 2;
  ClientLoggingLevel = (unsigned int)WdsCpPacketInitialize(g_hProvider, &v35, &v30);
  if ( !(unsigned int)ElValidateWin32(ClientLoggingLevel, v7, v8, 1069) )
  {
    ClientLoggingLevel = (unsigned int)pGetClientLoggingLevel(a1, &v31);
    if ( !(unsigned int)ElValidateWin32(ClientLoggingLevel, v9, v10, 1074) )
    {
      v11 = UuidCreate(&Uuid);
      LODWORD(ClientLoggingLevel) = v11;
      if ( !v11 || v11 == 1824 )
        LODWORD(ClientLoggingLevel) = 0;
      if ( !(unsigned int)ElValidateWin32((unsigned int)ClientLoggingLevel, v12, v13, 1084) )
      {
        ClientLoggingLevel = (unsigned int)UuidToStringW(&Uuid, &StringUuid);
        if ( !(unsigned int)ElValidateWin32(ClientLoggingLevel, v14, v15, 1087) )
        {
          v16 = WdsCliAddVarUlong(v30, L"VERSION", 1);
          if ( (int)ElValidateHr(v16, v17, v18, 1093) < 0
            || (v16 = WdsCliAddVarUlong(v30, L"LOGLEVEL", v31), (int)ElValidateHr(v16, v19, v20, 1096) < 0)
            || (v16 = WdsCliAddVarWstr(v30, L"TRANSACTION_ID", StringUuid), (int)ElValidateHr(v16, v21, v22, 1099) < 0) )
          {
            LODWORD(ClientLoggingLevel) = WIN32_FROM_HRESULT(v16);
          }
          else
          {
            ClientLoggingLevel = (unsigned int)WdsCpPacketGetBuffer(v30, &v34, &v32);
            ElValidateWin32(ClientLoggingLevel, v23, v24, 1104);
          }
        }
      }
    }
  }
  if ( (_DWORD)ClientLoggingLevel )
  {
    WdsImgTrace(0x80000u, L"Error initializing client->server logging. Error [%u].", (unsigned int)ClientLoggingLevel);
    CEventLog::Log((CEventLog *)g_EventLog, 0xC1060107, 2);
    v25 = HandlerError(v27, v26, a3, 7u);
  }
  else
  {
    v25 = WdsSendReply(a3, v34, v32, 0, 0);
  }
  v28 = v25;
  if ( v34 )
    WdsPacketFree(g_hProvider, 0);
  if ( v30 )
    WdsCpPacketRelease();
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  WdsImgTrace(0x10000u, L"<- HandlerLogInitialize=%x", v28);
  return v28;
}

```

## disassembly

```asm
0x180003af4  push    rbp
0x180003af6  push    rbx
0x180003af7  push    rsi
0x180003af8  push    rdi
0x180003af9  push    r14
0x180003afb  lea     rbp, [rsp-37h]
0x180003b00  sub     rsp, 90h
0x180003b07  mov     rax, cs:__security_cookie
0x180003b0e  xor     rax, rsp
0x180003b11  mov     [rbp+57h+var_30], rax
0x180003b15  xor     eax, eax
0x180003b17  mov     r14, rdx
0x180003b1a  and     [rbp+57h+var_70], rax
0x180003b1e  lea     rdx, aHandlerloginit_0; "-> HandlerLogInitialize"
0x180003b25  and     [rbp+57h+var_58], rax
0x180003b29  mov     rdi, rcx
0x180003b2c  and     [rbp+57h+var_68], eax
0x180003b2f  xorps   xmm0, xmm0
0x180003b32  and     [rbp+57h+var_64], eax
0x180003b35  mov     ecx, 10000h; unsigned int
0x180003b3a  and     [rbp+57h+StringUuid], rax
0x180003b3e  mov     rsi, r8
0x180003b41  mov     [rbp+57h+var_50], rax
0x180003b45  mov     [rbp+57h+var_48], eax
0x180003b48  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180003b4c  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003b51  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x180003b58  lea     r8, [rbp+57h+var_70]
0x180003b5c  and     [rbp+57h+var_48], 0
0x180003b60  lea     rdx, [rbp+57h+var_50]
0x180003b64  mov     dword ptr [rbp+57h+var_50], 0Ch
0x180003b6b  mov     byte ptr [rbp+57h+var_50+4], 2
0x180003b6f  call    cs:__imp_WdsCpPacketInitialize
0x180003b76  nop     dword ptr [rax+rax+00h]
0x180003b7b  mov     ecx, eax
0x180003b7d  mov     r9d, 42Dh
0x180003b83  mov     ebx, eax
0x180003b85  call    ElValidateWin32
0x180003b8a  test    eax, eax
0x180003b8c  jnz     loc_180003CC2
0x180003b92  lea     rdx, [rbp+57h+var_68]; unsigned int *
0x180003b96  mov     rcx, rdi; struct _IMG_SERVER_CONTEXT *
0x180003b99  call    ?pGetClientLoggingLevel@@YAJPEAU_IMG_SERVER_CONTEXT@@PEAK@Z; pGetClientLoggingLevel(_IMG_SERVER_CONTEXT *,ulong *)
0x180003b9e  mov     r9d, 432h
0x180003ba4  mov     ecx, eax
0x180003ba6  mov     ebx, eax
0x180003ba8  call    ElValidateWin32
0x180003bad  test    eax, eax
0x180003baf  jnz     loc_180003CC2
0x180003bb5  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180003bb9  call    cs:__imp_UuidCreate
0x180003bc0  nop     dword ptr [rax+rax+00h]
0x180003bc5  mov     ebx, eax
0x180003bc7  test    eax, eax
0x180003bc9  jz      short loc_180003BD2
0x180003bcb  cmp     eax, 720h
0x180003bd0  jnz     short loc_180003BD4
0x180003bd2  xor     ebx, ebx
0x180003bd4  mov     r9d, 43Ch
0x180003bda  mov     ecx, ebx
0x180003bdc  call    ElValidateWin32
0x180003be1  test    eax, eax
0x180003be3  jnz     loc_180003CC2
0x180003be9  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180003bed  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180003bf1  call    cs:__imp_UuidToStringW
0x180003bf8  nop     dword ptr [rax+rax+00h]
0x180003bfd  mov     ecx, eax
0x180003bff  mov     r9d, 43Fh
0x180003c05  mov     ebx, eax
0x180003c07  call    ElValidateWin32
0x180003c0c  test    eax, eax
0x180003c0e  jnz     loc_180003CC2
0x180003c14  mov     rcx, [rbp+57h+var_70]; void *
0x180003c18  lea     r8d, [rax+1]; unsigned int
0x180003c1c  lea     rdx, aVersion_0; "VERSION"
0x180003c23  call    ?WdsCliAddVarUlong@@YAJPEAXPEAGK@Z; WdsCliAddVarUlong(void *,ushort *,ulong)
0x180003c28  mov     r9d, 445h
0x180003c2e  mov     ecx, eax
0x180003c30  mov     ebx, eax
0x180003c32  call    ElValidateHr
0x180003c37  test    eax, eax
0x180003c39  jns     short loc_180003C4D
0x180003c3b  mov     ecx, ebx
0x180003c3d  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180003c44  nop     dword ptr [rax+rax+00h]
0x180003c49  mov     ebx, eax
0x180003c4b  jmp     short loc_180003CC2
0x180003c4d  mov     r8d, [rbp+57h+var_68]; unsigned int
0x180003c51  lea     rdx, aLoglevel; "LOGLEVEL"
0x180003c58  mov     rcx, [rbp+57h+var_70]; void *
0x180003c5c  call    ?WdsCliAddVarUlong@@YAJPEAXPEAGK@Z; WdsCliAddVarUlong(void *,ushort *,ulong)
0x180003c61  mov     r9d, 448h
0x180003c67  mov     ecx, eax
0x180003c69  mov     ebx, eax
0x180003c6b  call    ElValidateHr
0x180003c70  test    eax, eax
0x180003c72  js      short loc_180003C3B
0x180003c74  mov     r8, [rbp+57h+StringUuid]; unsigned __int16 *
0x180003c78  lea     rdx, aTransactionId; "TRANSACTION_ID"
0x180003c7f  mov     rcx, [rbp+57h+var_70]; void *
0x180003c83  call    ?WdsCliAddVarWstr@@YAJPEAXPEAG1@Z; WdsCliAddVarWstr(void *,ushort *,ushort *)
0x180003c88  mov     r9d, 44Bh
0x180003c8e  mov     ecx, eax
0x180003c90  mov     ebx, eax
0x180003c92  call    ElValidateHr
0x180003c97  test    eax, eax
0x180003c99  js      short loc_180003C3B
0x180003c9b  mov     rcx, [rbp+57h+var_70]
0x180003c9f  lea     r8, [rbp+57h+var_64]
0x180003ca3  lea     rdx, [rbp+57h+var_58]
0x180003ca7  call    cs:__imp_WdsCpPacketGetBuffer
0x180003cae  nop     dword ptr [rax+rax+00h]
0x180003cb3  mov     ecx, eax
0x180003cb5  mov     r9d, 450h
0x180003cbb  mov     ebx, eax
0x180003cbd  call    ElValidateWin32
0x180003cc2  test    ebx, ebx
0x180003cc4  jnz     short loc_180003CE6
0x180003cc6  and     dword ptr [rsp+0B0h+var_90], ebx
0x180003cca  xor     r9d, r9d
0x180003ccd  mov     r8d, [rbp+57h+var_64]
0x180003cd1  mov     rcx, rsi
0x180003cd4  mov     rdx, [rbp+57h+var_58]
0x180003cd8  call    cs:__imp_WdsSendReply
0x180003cdf  nop     dword ptr [rax+rax+00h]
0x180003ce4  jmp     short loc_180003D3F
0x180003ce6  mov     r8d, ebx
0x180003ce9  lea     rdx, aErrorInitializ; "Error initializing client->server loggi"...
0x180003cf0  mov     ecx, 80000h; unsigned int
0x180003cf5  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003cfa  mov     r9d, 1
0x180003d00  mov     [rsp+0B0h+var_80], ebx
0x180003d04  lea     rax, [r14+1Ch]
0x180003d08  mov     [rsp+0B0h+var_88], 5
0x180003d10  mov     edx, 0C1060107h
0x180003d15  mov     [rsp+0B0h+var_90], rax
0x180003d1a  lea     rcx, ?g_EventLog@@3VCEventLog@@A; CEventLog g_EventLog
0x180003d21  lea     r8d, [r9+1]
0x180003d25  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180003d2c  nop     dword ptr [rax+rax+00h]
0x180003d31  mov     r9d, 7; unsigned int
0x180003d37  mov     r8, rsi; void *
0x180003d3a  call    ?HandlerError@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAUtagWDS_ENDPOINT@@PEAXK@Z; HandlerError(_IMG_SERVER_CONTEXT *,tagWDS_ENDPOINT *,void *,ulong)
0x180003d3f  mov     r8, [rbp+57h+var_58]
0x180003d43  mov     ebx, eax
0x180003d45  test    r8, r8
0x180003d48  jz      short loc_180003D5F
0x180003d4a  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x180003d51  xor     edx, edx
0x180003d53  call    cs:__imp_WdsPacketFree
0x180003d5a  nop     dword ptr [rax+rax+00h]
0x180003d5f  mov     rcx, [rbp+57h+var_70]
0x180003d63  test    rcx, rcx
0x180003d66  jz      short loc_180003D74
0x180003d68  call    cs:__imp_WdsCpPacketRelease
0x180003d6f  nop     dword ptr [rax+rax+00h]
0x180003d74  cmp     [rbp+57h+StringUuid], 0
0x180003d79  jz      short loc_180003D8B
0x180003d7b  lea     rcx, [rbp+57h+StringUuid]; String
0x180003d7f  call    cs:__imp_RpcStringFreeW
0x180003d86  nop     dword ptr [rax+rax+00h]
0x180003d8b  mov     r8d, ebx
0x180003d8e  lea     rdx, aHandlerloginit; "<- HandlerLogInitialize=%x"
0x180003d95  mov     ecx, 10000h; unsigned int
0x180003d9a  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180003d9f  mov     eax, ebx
0x180003da1  mov     rcx, [rbp+57h+var_30]
0x180003da5  xor     rcx, rsp; StackCookie
0x180003da8  call    __security_check_cookie
0x180003dad  add     rsp, 90h
0x180003db4  pop     r14
0x180003db6  pop     rdi
0x180003db7  pop     rsi
0x180003db8  pop     rbx
0x180003db9  pop     rbp
0x180003dba  retn
```
