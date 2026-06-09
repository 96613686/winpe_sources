# RPCSplWOW64DocumentEvent

- ea: `0x14000d9e0`
- end: `0x14000dc09`
- name: `RPCSplWOW64DocumentEvent`
- size: `553`
- prototype: `__int64 __usercall@<rax>(LPVOID lpTlsValue@<rcx>, int, struct _DOCUMENT_EVENT_CONTAINER *, unsigned int *, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001b90`
- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000d17c`
- `0x14000d9e0`
- `0x14000e89c`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000da13`
- `KERNEL32!TlsSetValue` at `0x14000dbec`
- `KERNEL32!TlsSetValue` at `0x14000da13`
- `KERNEL32!TlsSetValue` at `0x14000dbec`
- `RPCRT4!RpcRevertToSelf` at `0x14000dbab`
- `RPCRT4!RpcRevertToSelf` at `0x14000dbab`
- `RPCRT4!RpcImpersonateClient` at `0x14000da4e`
- `RPCRT4!RpcImpersonateClient` at `0x14000da4e`

## string_xrefs

- `0x14000da1c`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
__int64 __fastcall RPCSplWOW64DocumentEvent(
        LPVOID lpTlsValue,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        int a4,
        int a5,
        struct _DOCUMENT_EVENT_CONTAINER *a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        unsigned __int8 *a9)
{
  unsigned int v10; // r12d
  unsigned __int64 v12; // rsi
  TPrinterEventMgr *v13; // rbx
  char v14; // r13
  unsigned int v15; // r14d
  RPC_STATUS v16; // eax
  NSecurityLibrary *v17; // rcx
  unsigned int *v18; // rdi
  unsigned int v19; // ecx
  int Interface; // eax
  unsigned int v21; // eax
  void *Block[2]; // [rsp+50h] [rbp-61h] BYREF
  _DOCEVENT_CREATEDCPRE v24; // [rsp+60h] [rbp-51h] BYREF
  _DOCINFOW v25; // [rsp+80h] [rbp-31h] BYREF
  unsigned int v26; // [rsp+100h] [rbp+4Fh] BYREF
  unsigned __int16 *v27; // [rsp+108h] [rbp+57h]
  TPrinterEventMgr *v28; // [rsp+110h] [rbp+5Fh] BYREF
  int v29; // [rsp+118h] [rbp+67h]

  v29 = a4;
  v27 = a2;
  v10 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo("RPCSplWOW64DocumentEvent", L"clientProcessID %u pszPrinterName %ws", v10, a2);
  v12 = -1;
  v13 = 0;
  v14 = 0;
  v28 = 0;
  v15 = -1;
  *a7 = 0;
  v16 = RpcImpersonateClient(0);
  v18 = (unsigned int *)a9;
  *(_DWORD *)a9 = v16;
  if ( !v16 )
  {
    v14 = 1;
    if ( NSecurityLibrary::IsClientAppContainer(v17) )
    {
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64DocumentEvent",
        L"Cannot call DocumentEvent from AppContainer, PID=%u",
        v10);
      *v18 = 5;
    }
  }
  v19 = *v18;
  if ( *v18 )
  {
    v12 = a3;
  }
  else
  {
    if ( !v29 )
      v12 = a3;
    Interface = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTEREVENT, (void **)&v28);
    v19 = Interface;
    if ( Interface < 0 )
    {
      if ( (Interface & 0x1FFF0000) == 0x70000 )
        v19 = (unsigned __int16)Interface;
    }
    else
    {
      v19 = 0;
    }
    v13 = v28;
    *v18 = v19;
  }
  v26 = 0;
  a9 = 0;
  *(_OWORD *)Block = 0;
  if ( !v19 )
  {
    memset(&v24, 0, sizeof(v24));
    memset(&v25, 0, sizeof(v25));
    v21 = DocEventContainer2Buffer(v29, a5, a6, &v24, &v25, &v26, &a9, (struct PrintPropertiesCollection *)Block);
    *v18 = v21;
    if ( !v21 )
      v15 = TPrinterEventMgr::DocumentEvent(v13, v27, v12, a5, v26, a9, a7, a8, v18);
  }
  operator delete(Block[1]);
  Block[1] = 0;
  LODWORD(Block[0]) = 0;
  if ( v14 )
    RpcRevertToSelf();
  if ( v15 == -1 )
    SplWow64Telemetry::WriteDbgTraceError("RPCSplWOW64DocumentEvent", L"DocumentEvent failed, PID=%u: %d", v10, *v18);
  if ( v13 )
    (*(void (__fastcall **)(TPrinterEventMgr *))(*(_QWORD *)v13 + 16LL))(v13);
  TlsSetValue(g_GlobalTlsIndex, 0);
  return v15;
}

```

## disassembly

```asm
0x14000d9e0  mov     [rsp-8+arg_18], r9d
0x14000d9e5  mov     [rsp-8+arg_8], rdx
0x14000d9ea  push    rbp
0x14000d9eb  push    rbx
0x14000d9ec  push    rsi
0x14000d9ed  push    rdi
0x14000d9ee  push    r12
0x14000d9f0  push    r13
0x14000d9f2  push    r14
0x14000d9f4  push    r15
0x14000d9f6  lea     rbp, [rsp-7]
0x14000d9fb  sub     rsp, 0B8h
0x14000da02  mov     rbx, rdx
0x14000da05  mov     r12d, ecx
0x14000da08  mov     edx, ecx; lpTlsValue
0x14000da0a  mov     r15, r8
0x14000da0d  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000da13  call    cs:__imp_TlsSetValue
0x14000da19  mov     r9, rbx
0x14000da1c  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000da23  mov     r8d, r12d
0x14000da26  lea     rcx, aRpcsplwow64doc; "RPCSplWOW64DocumentEvent"
0x14000da2d  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000da32  mov     rax, [rbp+3Fh+arg_30]
0x14000da36  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000da3a  xor     ebx, ebx
0x14000da3c  xor     ecx, ecx; BindingHandle
0x14000da3e  xor     r13b, r13b
0x14000da41  mov     [rbp+3Fh+arg_10], rbx
0x14000da45  mov     r14d, esi
0x14000da48  mov     dword ptr [rax], 0
0x14000da4e  call    cs:__imp_RpcImpersonateClient
0x14000da54  mov     rdi, [rbp+3Fh+arg_40]
0x14000da5b  mov     [rdi], eax
0x14000da5d  test    eax, eax
0x14000da5f  jnz     short loc_14000DA89
0x14000da61  mov     r13b, 1
0x14000da64  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x14000da69  test    al, al
0x14000da6b  jz      short loc_14000DA89
0x14000da6d  mov     r8d, r12d
0x14000da70  lea     rdx, aCannotCallDocu; "Cannot call DocumentEvent from AppConta"...
0x14000da77  lea     rcx, aRpcsplwow64doc; "RPCSplWOW64DocumentEvent"
0x14000da7e  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000da83  mov     dword ptr [rdi], 5
0x14000da89  mov     ecx, [rdi]
0x14000da8b  test    ecx, ecx
0x14000da8d  jnz     short loc_14000DACE
0x14000da8f  cmp     [rbp+3Fh+arg_18], ebx
0x14000da92  lea     r8, [rbp+3Fh+arg_10]; void **
0x14000da96  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000da9d  lea     rdx, ?IID_PRINTEREVENT@@3U_GUID@@A; struct _GUID *
0x14000daa4  cmovz   rsi, r15
0x14000daa8  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000daad  mov     ecx, eax
0x14000daaf  test    eax, eax
0x14000dab1  js      short loc_14000DAB7
0x14000dab3  xor     ecx, ecx
0x14000dab5  jmp     short loc_14000DAC6
0x14000dab7  and     eax, 1FFF0000h
0x14000dabc  cmp     eax, 70000h
0x14000dac1  jnz     short loc_14000DAC6
0x14000dac3  movzx   ecx, cx
0x14000dac6  mov     rbx, [rbp+3Fh+arg_10]
0x14000daca  mov     [rdi], ecx
0x14000dacc  jmp     short loc_14000DAD1
0x14000dace  mov     rsi, r15
0x14000dad1  mov     [rbp+3Fh+arg_0], 0
0x14000dad8  xorps   xmm0, xmm0
0x14000dadb  mov     [rbp+3Fh+arg_40], 0
0x14000dae6  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x14000daea  test    ecx, ecx
0x14000daec  jnz     loc_14000DB8E
0x14000daf2  mov     r8, [rbp+3Fh+arg_28]; struct _DOCUMENT_EVENT_CONTAINER *
0x14000daf6  lea     r9, [rbp+3Fh+var_90]; struct _DOCEVENT_CREATEDCPRE *
0x14000dafa  mov     edx, [rbp+3Fh+arg_20]; int
0x14000dafd  xor     eax, eax
0x14000daff  mov     ecx, [rbp+3Fh+arg_18]; int
0x14000db02  xorps   xmm1, xmm1
0x14000db05  mov     qword ptr [rbp+3Fh+var_70.fwType], rax
0x14000db09  lea     rax, [rbp+3Fh+Block]
0x14000db0d  mov     [rsp+0F0h+var_B8], rax; struct PrintPropertiesCollection *
0x14000db12  lea     rax, [rbp+3Fh+arg_40]
0x14000db19  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 **
0x14000db1e  lea     rax, [rbp+3Fh+arg_0]
0x14000db22  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x14000db27  lea     rax, [rbp+3Fh+var_70]
0x14000db2b  mov     [rsp+0F0h+var_D0], rax; struct _DOCINFOW *
0x14000db30  movups  xmmword ptr [rbp+3Fh+var_90.pszDriver], xmm0
0x14000db34  movups  xmmword ptr [rbp+3Fh+var_90.pdm], xmm0
0x14000db38  movups  xmmword ptr [rbp+3Fh+var_70.cbSize], xmm1
0x14000db3c  movups  xmmword ptr [rbp+3Fh+var_70.lpszOutput], xmm1
0x14000db40  call    ?DocEventContainer2Buffer@@YAKHHPEAU_DOCUMENT_EVENT_CONTAINER@@PEAU_DOCEVENT_CREATEDCPRE@@PEAU_DOCINFOW@@PEAKPEAPEAEPEAUPrintPropertiesCollection@@@Z; DocEventContainer2Buffer(int,int,_DOCUMENT_EVENT_CONTAINER *,_DOCEVENT_CREATEDCPRE *,_DOCINFOW *,ulong *,uchar * *,PrintPropertiesCollection *)
0x14000db45  mov     [rdi], eax
0x14000db47  test    eax, eax
0x14000db49  jnz     short loc_14000DB8E
0x14000db4b  mov     rax, [rbp+3Fh+arg_38]
0x14000db52  mov     r8, rsi; unsigned __int64
0x14000db55  mov     r9d, [rbp+3Fh+arg_20]; int
0x14000db59  mov     rcx, rbx; this
0x14000db5c  mov     rdx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x14000db60  mov     [rsp+0F0h+var_B0], rdi; unsigned int *
0x14000db65  mov     [rsp+0F0h+var_B8], rax; unsigned __int8 **
0x14000db6a  mov     rax, [rbp+3Fh+arg_30]
0x14000db6e  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x14000db73  mov     rax, [rbp+3Fh+arg_40]
0x14000db7a  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x14000db7f  mov     eax, [rbp+3Fh+arg_0]
0x14000db82  mov     dword ptr [rsp+0F0h+var_D0], eax; unsigned int
0x14000db86  call    ?DocumentEvent@TPrinterEventMgr@@QEAAHPEAG_KHKPEAEPEAKPEAPEAE3@Z; TPrinterEventMgr::DocumentEvent(ushort *,unsigned __int64,int,ulong,uchar *,ulong *,uchar * *,ulong *)
0x14000db8b  mov     r14d, eax
0x14000db8e  mov     rcx, [rbp+3Fh+Block+8]; Block
0x14000db92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000db97  mov     [rbp+3Fh+Block+8], 0
0x14000db9f  mov     dword ptr [rbp+3Fh+Block], 0
0x14000dba6  test    r13b, r13b
0x14000dba9  jz      short loc_14000DBB1
0x14000dbab  call    cs:__imp_RpcRevertToSelf
0x14000dbb1  cmp     r14d, 0FFFFFFFFh
0x14000dbb5  jnz     short loc_14000DBD0
0x14000dbb7  mov     r9d, [rdi]
0x14000dbba  lea     rdx, aDocumenteventF; "DocumentEvent failed, PID=%u: %d"
0x14000dbc1  mov     r8d, r12d
0x14000dbc4  lea     rcx, aRpcsplwow64doc; "RPCSplWOW64DocumentEvent"
0x14000dbcb  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000dbd0  test    rbx, rbx
0x14000dbd3  jz      short loc_14000DBE4
0x14000dbd5  mov     rax, [rbx]
0x14000dbd8  mov     rcx, rbx
0x14000dbdb  mov     rax, [rax+10h]
0x14000dbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dbe4  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dbea  xor     edx, edx; lpTlsValue
0x14000dbec  call    cs:__imp_TlsSetValue
0x14000dbf2  mov     eax, r14d
0x14000dbf5  add     rsp, 0B8h
0x14000dbfc  pop     r15
0x14000dbfe  pop     r14
0x14000dc00  pop     r13
0x14000dc02  pop     r12
0x14000dc04  pop     rdi
0x14000dc05  pop     rsi
0x14000dc06  pop     rbx
0x14000dc07  pop     rbp
0x14000dc08  retn
```
