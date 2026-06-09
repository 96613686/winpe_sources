# CNodeFactory::BeginChildren(IXMLNodeSource *,_XML_NODE_INFO *)

- ea: `0x1800328b0`
- end: `0x180032d63`
- name: `?BeginChildren@CNodeFactory@@UEAAJPEAUIXMLNodeSource@@PEAU_XML_NODE_INFO@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, struct IXMLNodeSource *, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800075a0`
- `0x18000dffc`
- `0x18001c2c8`
- `0x18001e5c0`
- `0x18002e98c`
- `0x1800328b0`
- `0x180032d70`
- `0x18005b8a0`
- `0x18005bf78`
- `0x18005cc58`
- `0x180067170`
- `0x180067548`
- `0x180067680`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180032aa1`
- `ntdll!RtlPopFrame` at `0x180032c57`
- `ntdll!RtlPopFrame` at `0x180032cda`
- `ntdll!RtlPopFrame` at `0x180032d04`
- `ntdll!RtlPopFrame` at `0x180032aa1`
- `ntdll!RtlPopFrame` at `0x180032c57`
- `ntdll!RtlPopFrame` at `0x180032cda`
- `ntdll!RtlPopFrame` at `0x180032d04`
- `ntdll!RtlPushFrame` at `0x18003291d`
- `ntdll!RtlPushFrame` at `0x180032a53`
- `ntdll!RtlPushFrame` at `0x18003291d`
- `ntdll!RtlPushFrame` at `0x180032a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003299d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800329ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032a01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032a74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032d52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003299d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800329ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032a01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032a74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032bcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032d52`

## pseudocode

```c
__int64 __fastcall CNodeFactory::BeginChildren(
        CNodeFactory *this,
        struct IXMLNodeSource *a2,
        struct _XML_NODE_INFO *a3)
{
  int v5; // eax
  int v6; // ebx
  unsigned int i; // ebx
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // rdi
  int v11; // edi
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ebx
  DWORD LastError; // eax
  DWORD v18; // edi
  int v19; // ecx
  __int128 v20; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-D0h]
  __int128 v22; // [rsp+48h] [rbp-C0h]
  __int64 v23; // [rsp+58h] [rbp-B0h]
  __int64 v24; // [rsp+60h] [rbp-A8h]
  __int64 v25; // [rsp+68h] [rbp-A0h]
  _QWORD v26[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v27; // [rsp+88h] [rbp-80h]
  int v28; // [rsp+98h] [rbp-70h] BYREF
  int v29; // [rsp+9Ch] [rbp-6Ch] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-50h]
  int v32; // [rsp+C0h] [rbp-48h]
  int *v33; // [rsp+C8h] [rbp-40h]
  struct _TEB_ACTIVE_FRAME v34; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-20h]
  int v36; // [rsp+F0h] [rbp-18h]
  int *v37; // [rsp+F8h] [rbp-10h]
  _BYTE v38[8]; // [rsp+108h] [rbp+0h] BYREF
  void **v39; // [rsp+110h] [rbp+8h] BYREF
  int v40; // [rsp+118h] [rbp+10h]
  void *InlineBuffer; // [rsp+120h] [rbp+18h]
  __int128 v42; // [rsp+128h] [rbp+20h]
  __int16 v43; // [rsp+138h] [rbp+30h] BYREF

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006F730;
  v33 = &v28;
  v28 = -1;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v31 = 544438355;
  v32 = 1286;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v40 = 0;
  v42 = 0;
  v39 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  InlineBuffer = 0;
  v43 = 0;
  InlineBuffer = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v39);
  *(_QWORD *)&v42 = ((__int64 (__fastcall *)(void ***))v39[3])(&v39);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(InlineBuffer, 0, 2 * v42);
  SetLastError(0);
  SetLastError(0);
  v5 = CNodeFactory::ConvertXMLNodeInfoToSXSNodeInfo(this, a3, (struct _SXS_NODE_INFO *)v38);
  v6 = v5;
  if ( v5 < 0 )
  {
    FusionpTraceCOMFailure(v5, byte_18008517D);
    CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&Frame, v6);
    goto LABEL_23;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) )
    {
      *v33 = 0;
      goto LABEL_23;
    }
    SetLastError(0);
    v8 = *((_QWORD *)this + 2);
    v9 = *((_QWORD *)this + 49);
    v29 = 0;
    v34.Flags = 1;
    v34.Previous = 0;
    v34.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071730;
    v10 = *(_QWORD *)v8 + 48LL * i;
    v35 = 544438355;
    v36 = 340;
    v37 = &v29;
    RtlPushFrame(&v34);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    if ( *(_DWORD *)(v10 + 12) )
      goto LABEL_11;
    v12 = *(_DWORD *)(v8 + 1204);
    v13 = *(_QWORD *)(v10 + 16);
    v20 = 0;
    HIDWORD(v20) = v12;
    *(_QWORD *)((char *)&v20 + 4) = *(_QWORD *)(v8 + 1208);
    v23 = 0;
    v24 = v8 + 1216;
    memset(v26, 0, sizeof(v26));
    v25 = v8 + 1272;
    v21 = 0;
    LODWORD(v20) = 5;
    v22 = 0;
    v27 = 0;
    v14 = *(_BYTE *)(v13 + 61) ? v13 + 16 : 0LL;
    *(_QWORD *)&v21 = v14;
    DWORD2(v21) = *(_DWORD *)(v13 + 32);
    *(_QWORD *)&v22 = *(_QWORD *)(v13 + 40);
    v26[0] = v8;
    v23 = *(_DWORD *)(v10 + 8) ? *(_QWORD *)v10 : 0LL;
    *((_QWORD *)&v22 + 1) = *(_QWORD *)(v10 + 24);
    v26[2] = (char *)this + 400;
    *(_QWORD *)&v27 = v38;
    v26[1] = v9;
    DWORD2(v27) = 1;
    SetLastError(0);
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)(v10 + 16) + 48LL))(&v20);
    if ( DWORD2(v27) )
    {
LABEL_11:
      SetLastError(0);
      *v37 = 1;
    }
    else if ( !GetLastError() )
    {
      SetLastError(0x54Fu);
    }
    v11 = *v37;
    if ( g_FusionEnterExitTracingEnabled )
      break;
    RtlPopFrame(&v34);
    if ( !v11 )
      goto LABEL_33;
LABEL_14:
    ;
  }
  if ( v11 )
  {
    FusionpTraceCallSuccessfulExit(0);
    RtlPopFrame(&v34);
    goto LABEL_14;
  }
  LastError = GetLastError();
  FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
  RtlPopFrame(&v34);
LABEL_33:
  CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&Frame);
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800795C8);
LABEL_23:
  v15 = *v33;
  v39 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( InlineBuffer != &v43 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v39);
  InlineBuffer = 0;
  *(_QWORD *)&v42 = 0;
  v39 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( g_FusionEnterExitTracingEnabled )
  {
    v18 = GetLastError();
    v19 = *v33;
    if ( *v33 < 0 )
      FusionpTraceCOMFailure(v19, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v19, 0);
    SetLastError(v18);
  }
  RtlPopFrame(&Frame);
  return v15;
}

```

## disassembly

```asm
0x1800328b0  mov     r11, rsp
0x1800328b3  push    rbp
0x1800328b4  push    rbx
0x1800328b5  lea     rbp, [r11-108h]
0x1800328bc  sub     rsp, 1F8h
0x1800328c3  mov     rax, cs:__security_cookie
0x1800328ca  xor     rax, rsp
0x1800328cd  mov     [rbp+100h+var_40], rax
0x1800328d4  mov     [r11+10h], rsi
0x1800328d8  lea     rax, qword_18006F730
0x1800328df  mov     [rbp+100h+Frame.Context], rax
0x1800328e3  mov     rsi, rcx
0x1800328e6  mov     [r11-20h], r12
0x1800328ea  lea     rax, [rbp+100h+var_170]
0x1800328ee  xor     r12d, r12d
0x1800328f1  mov     [rbp+100h+var_140], rax
0x1800328f5  lea     rcx, [rbp+100h+Frame]; Frame
0x1800328f9  mov     [rbp+100h+var_170], 0FFFFFFFFh
0x180032900  mov     rbx, r8
0x180032903  mov     [rbp+100h+Frame.Flags], 1
0x18003290a  mov     [rbp+100h+Frame.Previous], r12
0x18003290e  mov     [rbp+100h+var_150], 20737853h
0x180032916  mov     [rbp+100h+var_148], 506h
0x18003291d  call    cs:__imp_RtlPushFrame
0x180032924  nop     dword ptr [rax+rax+00h]
0x180032929  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x180032930  jnz     loc_180032CA3
0x180032936  xorps   xmm0, xmm0
0x180032939  mov     [rbp+100h+var_F0], r12d
0x18003293d  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180032944  movdqa  [rbp+100h+var_E0], xmm0
0x180032949  lea     rcx, [rbp+100h+var_F8]
0x18003294d  mov     [rbp+100h+var_F8], rax
0x180032951  mov     [rbp+100h+var_E8], r12
0x180032955  mov     [rbp+100h+var_D0], r12w
0x18003295a  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x18003295f  mov     [rbp+100h+var_E8], rax
0x180032963  lea     rcx, [rbp+100h+var_F8]
0x180032967  mov     rax, [rbp+100h+var_F8]
0x18003296b  mov     rax, [rax+18h]
0x18003296f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032974  mov     qword ptr [rbp+100h+var_E0], rax
0x180032978  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x18003297d  test    eax, eax
0x18003297f  jz      short loc_180032993
0x180032981  mov     r8, qword ptr [rbp+100h+var_E0]
0x180032985  xor     edx, edx; Val
0x180032987  mov     rcx, [rbp+100h+var_E8]; void *
0x18003298b  add     r8, r8; Size
0x18003298e  call    memset_0
0x180032993  xor     ecx, ecx; dwErrCode
0x180032995  mov     [rsp+1F0h], rdi
0x18003299d  call    cs:__imp_SetLastError
0x1800329a4  nop     dword ptr [rax+rax+00h]
0x1800329a9  xor     ecx, ecx; dwErrCode
0x1800329ab  call    cs:__imp_SetLastError
0x1800329b2  nop     dword ptr [rax+rax+00h]
0x1800329b7  lea     r8, [rbp+100h+var_100]; struct _SXS_NODE_INFO *
0x1800329bb  mov     rdx, rbx; struct _XML_NODE_INFO *
0x1800329be  mov     rcx, rsi; this
0x1800329c1  call    ?ConvertXMLNodeInfoToSXSNodeInfo@CNodeFactory@@QEAAJPEBU_XML_NODE_INFO@@AEAU_SXS_NODE_INFO@@@Z; CNodeFactory::ConvertXMLNodeInfoToSXSNodeInfo(_XML_NODE_INFO const *,_SXS_NODE_INFO &)
0x1800329c6  mov     ebx, eax
0x1800329c8  test    eax, eax
0x1800329ca  js      loc_180032CAD
0x1800329d0  mov     [rsp+200h+var_20], r13
0x1800329d8  mov     ebx, r12d
0x1800329db  mov     [rsp+200h+var_28], r14
0x1800329e3  lea     r13, qword_180071730
0x1800329ea  mov     [rsp+200h+var_30], r15
0x1800329f2  mov     rax, [rsi+10h]
0x1800329f6  cmp     ebx, [rax+8]
0x1800329f9  jnb     loc_180032BDD
0x1800329ff  xor     ecx, ecx; dwErrCode
0x180032a01  call    cs:__imp_SetLastError
0x180032a08  nop     dword ptr [rax+rax+00h]
0x180032a0d  mov     r14, [rsi+10h]
0x180032a11  lea     rcx, [rbp+100h+var_138]; Frame
0x180032a15  mov     r15, [rsi+188h]
0x180032a1c  mov     eax, ebx
0x180032a1e  mov     [rbp+100h+var_16C], r12d
0x180032a22  mov     [rbp+100h+var_138.Flags], 1
0x180032a29  mov     [rbp+100h+var_138.Previous], r12
0x180032a2d  lea     rdi, [rax+rax*2]
0x180032a31  mov     [rbp+100h+var_138.Context], r13
0x180032a35  lea     rax, [rbp+100h+var_16C]
0x180032a39  shl     rdi, 4
0x180032a3d  add     rdi, [r14]
0x180032a40  mov     [rbp+100h+var_120], 20737853h
0x180032a48  mov     [rbp+100h+var_118], 154h
0x180032a4f  mov     [rbp+100h+var_110], rax
0x180032a53  call    cs:__imp_RtlPushFrame
0x180032a5a  nop     dword ptr [rax+rax+00h]
0x180032a5f  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x180032a66  jnz     loc_180032C87
0x180032a6c  cmp     [rdi+0Ch], r12d
0x180032a70  jz      short loc_180032ABC
0x180032a72  xor     ecx, ecx; dwErrCode
0x180032a74  call    cs:__imp_SetLastError
0x180032a7b  nop     dword ptr [rax+rax+00h]
0x180032a80  mov     rax, [rbp+100h+var_110]
0x180032a84  mov     dword ptr [rax], 1
0x180032a8a  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x180032a91  mov     rax, [rbp+100h+var_110]
0x180032a95  mov     edi, [rax]
0x180032a97  jnz     loc_180032CCB
0x180032a9d  lea     rcx, [rbp+100h+var_138]; Frame
0x180032aa1  call    cs:__imp_RtlPopFrame
0x180032aa8  nop     dword ptr [rax+rax+00h]
0x180032aad  test    edi, edi
0x180032aaf  jz      loc_180032D10
0x180032ab5  inc     ebx
0x180032ab7  jmp     loc_1800329F2
0x180032abc  mov     eax, [r14+4B4h]
0x180032ac3  xorps   xmm0, xmm0
0x180032ac6  mov     rcx, [rdi+10h]
0x180032aca  movups  [rsp+200h+var_1E8+8], xmm0
0x180032acf  mov     dword ptr [rsp+200h+var_1D8+4], eax
0x180032ad3  mov     eax, [r14+4B8h]
0x180032ada  mov     dword ptr [rsp+200h+var_1E8+0Ch], eax
0x180032ade  mov     eax, [r14+4BCh]
0x180032ae5  mov     dword ptr [rsp+200h+var_1D8], eax
0x180032ae9  lea     rax, [r14+4C0h]
0x180032af0  movups  [rsp+200h+var_1B8+8], xmm0
0x180032af5  mov     qword ptr [rsp+200h+var_1A8], rax
0x180032afa  lea     rax, [r14+4F8h]
0x180032b01  movups  [rsp+200h+var_1A8+8], xmm0
0x180032b06  mov     qword ptr [rsp+200h+var_1A8+8], rax
0x180032b0b  movups  [rsp+200h+var_1D8+8], xmm0
0x180032b10  mov     dword ptr [rsp+200h+var_1E8+8], 5
0x180032b18  movups  [rsp+200h+var_1C8+8], xmm0
0x180032b1d  movups  xmmword ptr [rsp+200h+var_198+8], xmm0
0x180032b22  movups  [rbp+100h+var_180], xmm0
0x180032b26  cmp     [rcx+3Dh], r12b
0x180032b2a  jz      loc_180032C9B
0x180032b30  lea     rax, [rcx+10h]
0x180032b34  mov     qword ptr [rsp+200h+var_1D8+8], rax
0x180032b39  mov     eax, [rcx+20h]
0x180032b3c  mov     dword ptr [rsp+200h+var_1C8], eax
0x180032b40  mov     rax, [rcx+28h]
0x180032b44  mov     qword ptr [rsp+200h+var_1C8+8], rax
0x180032b49  mov     qword ptr [rsp+200h+var_198], r14
0x180032b4e  cmp     [rdi+8], r12d
0x180032b52  jz      loc_180032C91
0x180032b58  mov     rax, [rdi]
0x180032b5b  mov     qword ptr [rsp+200h+var_1B8+8], rax
0x180032b60  mov     rax, [rdi+18h]
0x180032b64  xor     ecx, ecx; dwErrCode
0x180032b66  mov     qword ptr [rsp+200h+var_1B8], rax
0x180032b6b  lea     rax, [rsi+190h]
0x180032b72  mov     qword ptr [rsp+200h+var_198+10h], rax
0x180032b77  lea     rax, [rbp+100h+var_100]
0x180032b7b  mov     qword ptr [rbp+100h+var_180], rax
0x180032b7f  mov     qword ptr [rsp+200h+var_198+8], r15
0x180032b84  mov     dword ptr [rbp+100h+var_180+8], 1
0x180032b8b  call    cs:__imp_SetLastError
0x180032b92  nop     dword ptr [rax+rax+00h]
0x180032b97  mov     rax, [rdi+10h]
0x180032b9b  lea     rcx, [rsp+200h+var_1E8+8]
0x180032ba0  mov     rax, [rax+30h]
0x180032ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ba9  cmp     dword ptr [rbp+100h+var_180+8], r12d
0x180032bad  jnz     loc_180032A72
0x180032bb3  call    cs:__imp_GetLastError
0x180032bba  nop     dword ptr [rax+rax+00h]
0x180032bbf  test    eax, eax
0x180032bc1  jnz     loc_180032A8A
0x180032bc7  mov     ecx, 54Fh; dwErrCode
0x180032bcc  call    cs:__imp_SetLastError
0x180032bd3  nop     dword ptr [rax+rax+00h]
0x180032bd8  jmp     loc_180032A8A
0x180032bdd  mov     rax, [rbp+100h+var_140]
0x180032be1  mov     [rax], r12d
0x180032be4  mov     r14, [rsp+200h+var_28]
0x180032bec  mov     r15, [rsp+200h+var_30]
0x180032bf4  mov     r13, [rsp+200h+var_20]
0x180032bfc  mov     rax, [rbp+100h+var_140]
0x180032c00  mov     rdx, [rbp+100h+var_E8]
0x180032c04  mov     rsi, [rsp+200h+arg_8]
0x180032c0c  mov     ebx, [rax]
0x180032c0e  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180032c15  mov     [rbp+100h+var_F8], rax
0x180032c19  lea     rax, [rbp+100h+var_D0]
0x180032c1d  cmp     rdx, rax
0x180032c20  jz      short loc_180032C2B
0x180032c22  lea     rcx, [rbp+100h+var_F8]
0x180032c26  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180032c2b  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180032c32  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x180032c39  mov     [rbp+100h+var_E8], r12
0x180032c3d  mov     qword ptr [rbp+100h+var_E0], r12
0x180032c41  mov     r12, [rsp+200h+var_18]
0x180032c49  mov     [rbp+100h+var_F8], rax
0x180032c4d  jnz     loc_180032D2A
0x180032c53  lea     rcx, [rbp+100h+Frame]; Frame
0x180032c57  call    cs:__imp_RtlPopFrame
0x180032c5e  nop     dword ptr [rax+rax+00h]
0x180032c63  mov     rdi, [rsp+1F0h]
0x180032c6b  mov     eax, ebx
0x180032c6d  mov     rcx, [rbp+100h+var_40]
0x180032c74  xor     rcx, rsp; StackCookie
0x180032c77  call    __security_check_cookie
0x180032c7c  add     rsp, 1F8h
0x180032c83  pop     rbx
0x180032c84  pop     rbp
0x180032c85  retn
0x180032c87  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180032c8c  jmp     loc_180032A6C
0x180032c91  mov     qword ptr [rsp+200h+var_1B8+8], r12
0x180032c96  jmp     loc_180032B60
0x180032c9b  mov     rax, r12
0x180032c9e  jmp     loc_180032B34
0x180032ca3  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180032ca8  jmp     loc_180032936
0x180032cad  lea     rdx, byte_18008517D; char *
0x180032cb4  mov     ecx, ebx; int
0x180032cb6  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180032cbb  mov     edx, ebx; int
0x180032cbd  lea     rcx, [rbp+100h+Frame]; this
0x180032cc1  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x180032cc6  jmp     loc_180032BFC
0x180032ccb  test    edi, edi
0x180032ccd  jz      short loc_180032CEB
0x180032ccf  xor     ecx, ecx; char *
0x180032cd1  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180032cd6  lea     rcx, [rbp+100h+var_138]; Frame
0x180032cda  call    cs:__imp_RtlPopFrame
0x180032ce1  nop     dword ptr [rax+rax+00h]
0x180032ce6  jmp     loc_180032AB5
0x180032ceb  call    cs:__imp_GetLastError
0x180032cf2  nop     dword ptr [rax+rax+00h]
0x180032cf7  mov     ecx, eax; unsigned int
0x180032cf9  xor     edx, edx; Format
0x180032cfb  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180032d00  lea     rcx, [rbp+100h+var_138]; Frame
0x180032d04  call    cs:__imp_RtlPopFrame
0x180032d0b  nop     dword ptr [rax+rax+00h]
0x180032d10  lea     rcx, [rbp+100h+Frame]; this
0x180032d14  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180032d19  lea     rcx, off_1800795C8; struct _CALL_SITE_INFO *
0x180032d20  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180032d25  jmp     loc_180032BE4
0x180032d2a  call    cs:__imp_GetLastError
0x180032d31  nop     dword ptr [rax+rax+00h]
0x180032d36  mov     rcx, [rbp+100h+var_140]
0x180032d3a  xor     edx, edx; char *
0x180032d3c  mov     edi, eax
0x180032d3e  mov     ecx, [rcx]; int
0x180032d40  test    ecx, ecx
0x180032d42  js      short loc_180032D4B
0x180032d44  call    ?FusionpTraceCallCOMSuccessfulExit@@YAXJPEBDZZ; FusionpTraceCallCOMSuccessfulExit(long,char const *,...)
0x180032d49  jmp     short loc_180032D50
0x180032d4b  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180032d50  mov     ecx, edi; dwErrCode
0x180032d52  call    cs:__imp_SetLastError
0x180032d59  nop     dword ptr [rax+rax+00h]
0x180032d5e  jmp     loc_180032C53
```
