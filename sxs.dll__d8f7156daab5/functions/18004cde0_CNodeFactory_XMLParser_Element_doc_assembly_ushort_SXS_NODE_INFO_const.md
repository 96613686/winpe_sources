# CNodeFactory::XMLParser_Element_doc_assembly(ushort,_SXS_NODE_INFO const *)

- ea: `0x18004cde0`
- end: `0x18004d2ca`
- name: `?XMLParser_Element_doc_assembly@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c2c8`
- `0x18002fffc`
- `0x18004cde0`
- `0x1800515ec`
- `0x18005c978`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004cfd7`
- `ntdll!RtlPopFrame` at `0x18004d165`
- `ntdll!RtlPopFrame` at `0x18004d24f`
- `ntdll!RtlPopFrame` at `0x18004d279`
- `ntdll!RtlPopFrame` at `0x18004cfd7`
- `ntdll!RtlPopFrame` at `0x18004d165`
- `ntdll!RtlPopFrame` at `0x18004d24f`
- `ntdll!RtlPopFrame` at `0x18004d279`
- `ntdll!RtlPushFrame` at `0x18004cf43`
- `ntdll!RtlPushFrame` at `0x18004cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ceaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004cfaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d102`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d1a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d225`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ceaf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004cfaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d102`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d1a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d225`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly(
        CNodeFactory *this,
        __int64 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax
  __int64 *v6; // r14
  int v7; // esi
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  __int64 v10; // r15
  const char *v11; // rcx
  __int64 v12; // rsi
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // ebx
  DWORD LastError; // eax
  DWORD v22; // eax
  const struct _UNICODE_STRING *v23; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v24; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v25; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v26; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v27; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v28; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v29; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v30; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v31; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v32; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v33; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v34; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v35; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v36; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v37; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v38; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v39; // [rsp+B0h] [rbp-90h]
  unsigned int v40; // [rsp+C0h] [rbp-80h]
  unsigned int v41; // [rsp+C4h] [rbp-7Ch]
  __int64 v42; // [rsp+C8h] [rbp-78h]
  __int64 v43; // [rsp+D0h] [rbp-70h]
  __int64 v44; // [rsp+D8h] [rbp-68h]
  __int128 v45; // [rsp+E0h] [rbp-60h] BYREF
  __int128 v46; // [rsp+F0h] [rbp-50h]
  __int128 v47; // [rsp+100h] [rbp-40h]
  __int128 v48; // [rsp+110h] [rbp-30h]
  __int128 v49; // [rsp+120h] [rbp-20h]
  __int128 v50; // [rsp+130h] [rbp-10h]
  __int128 v51; // [rsp+140h] [rbp+0h]
  __int128 v52; // [rsp+150h] [rbp+10h]
  __int128 v53; // [rsp+160h] [rbp+20h]
  __int64 v54; // [rsp+170h] [rbp+30h]
  int v55; // [rsp+180h] [rbp+40h] BYREF
  int v56; // [rsp+184h] [rbp+44h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+188h] [rbp+48h] BYREF
  __int64 v58; // [rsp+1A0h] [rbp+60h]
  int v59; // [rsp+1A8h] [rbp+68h]
  int *v60; // [rsp+1B0h] [rbp+70h]
  struct _TEB_ACTIVE_FRAME v61; // [rsp+1B8h] [rbp+78h] BYREF
  __int64 v62; // [rsp+1D0h] [rbp+90h]
  int v63; // [rsp+1D8h] [rbp+98h]
  unsigned int *v64; // [rsp+1E0h] [rbp+A0h]

  v61.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071CD0;
  v61.Flags = 1;
  v64 = (unsigned int *)&v55;
  v55 = 0;
  v61.Previous = 0;
  v62 = 544438355;
  v63 = 2010;
  CFrame::BaseEnter((CFrame *)&v61);
  if ( *((_BYTE *)this + 1832) )
  {
    v20 = CNodeFactory::LogParseError(
            this,
            0xC1010001,
            0x81u,
            0,
            0,
            0,
            v23,
            v24,
            v25,
            v26,
            v27,
            v28,
            v29,
            v30,
            v31,
            v32,
            v33,
            v34,
            v35,
            v36,
            v37,
            v38,
            v39);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v61, v20);
    FusionpTraceCOMFailureOrigination((const struct _CALL_SITE_INFO *)off_180079428, v20);
    goto LABEL_19;
  }
  v4 = 0;
  *((_BYTE *)this + 1832) = 1;
  *((_BYTE *)this + 1838) = 0;
  while ( 1 )
  {
    if ( v4 >= *(_DWORD *)(*((_QWORD *)this + 2) + 8LL) )
    {
      SetLastError(0);
      *v64 = 1;
      goto LABEL_19;
    }
    SetLastError(0);
    v5 = (_DWORD *)*((_QWORD *)this + 3);
    v6 = (__int64 *)*((_QWORD *)this + 2);
    v7 = *((_DWORD *)this + 110);
    Frame.Flags = 1;
    v8 = v5[218];
    v9 = v5[216];
    v10 = *v6;
    v41 = v5[215];
    v44 = *((_QWORD *)this + 57);
    v43 = *((_QWORD *)this + 56);
    v40 = *((_DWORD *)this + 94);
    v42 = *((_QWORD *)this + 49);
    v56 = 0;
    Frame.Previous = 0;
    Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071830;
    v60 = &v56;
    v58 = 544438355;
    v59 = 559;
    RtlPushFrame(&Frame);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v54 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    if ( v7 == 2 )
    {
      v12 = v10 + 48LL * v4;
      if ( *(_DWORD *)(v12 + 8) )
      {
        SetLastError(0x54Fu);
        *v60 = 0;
      }
      else
      {
        v14 = *(_QWORD *)(v12 + 16);
        HIDWORD(v45) = *((_DWORD *)v6 + 301);
        *(_QWORD *)((char *)&v45 + 4) = v6[151];
        *((_QWORD *)&v48 + 1) = v6 + 152;
        *(_QWORD *)&v49 = v6 + 159;
        LODWORD(v45) = 3;
        v15 = *(_BYTE *)(v14 + 61) ? v14 + 16 : 0LL;
        *(_QWORD *)&v46 = v15;
        DWORD2(v46) = *(_DWORD *)(v14 + 32);
        *(_QWORD *)&v47 = *(_QWORD *)(v14 + 40);
        *((_QWORD *)&v47 + 1) = *(_QWORD *)(v12 + 24);
        *((_QWORD *)&v50 + 1) = v40;
        *(_QWORD *)&v50 = v42;
        *((_QWORD *)&v51 + 1) = v43;
        *(_QWORD *)&v52 = v44;
        *((_QWORD *)&v52 + 1) = *((_QWORD *)this + 58);
        *(_QWORD *)&v53 = __PAIR64__(v9, v41);
        *((_QWORD *)&v49 + 1) = v6;
        *(_QWORD *)&v48 = 0;
        LODWORD(v51) = 2;
        *((_QWORD *)&v53 + 1) = v8;
        LODWORD(v54) = 1;
        (*(void (__fastcall **)(__int128 *))(v14 + 48))(&v45);
        if ( (_DWORD)v54 )
        {
          v16 = HIDWORD(v53);
          *(_DWORD *)(v12 + 12) = HIDWORD(v53);
          if ( v16 )
          {
            *(_QWORD *)v12 = 0;
            v17 = 0;
          }
          else
          {
            *(_QWORD *)v12 = v48;
            v17 = 1;
          }
          *(_DWORD *)(v12 + 8) = v17;
          SetLastError(0);
          *v60 = 1;
        }
        else if ( !GetLastError() )
        {
          SetLastError(0x54Fu);
        }
      }
    }
    else
    {
      v59 = 562;
      FusionpTraceParameterCheck(v11);
      SetLastError(0x57u);
      *v60 = 0;
    }
    v13 = *v60;
    if ( g_FusionEnterExitTracingEnabled )
      break;
    RtlPopFrame(&Frame);
    if ( !v13 )
      goto LABEL_30;
LABEL_11:
    ++v4;
  }
  if ( v13 )
  {
    FusionpTraceCallSuccessfulExit(0);
    RtlPopFrame(&Frame);
    goto LABEL_11;
  }
  LastError = GetLastError();
  FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
  RtlPopFrame(&Frame);
LABEL_30:
  *v64 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180079408);
LABEL_19:
  v18 = *v64;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v18 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v22 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v22, 0);
    }
  }
  RtlPopFrame(&v61);
  return v18;
}

```

## disassembly

```asm
0x18004cde0  push    rbp
0x18004cde2  push    rbx
0x18004cde3  lea     rbp, [rsp-0C8h]
0x18004cdeb  sub     rsp, 208h
0x18004cdf2  mov     rax, cs:__security_cookie
0x18004cdf9  xor     rax, rsp
0x18004cdfc  mov     [rbp+0D0h+var_28], rax
0x18004ce03  lea     rax, qword_180071CD0
0x18004ce0a  mov     [rsp+210h+var_20], r15
0x18004ce12  mov     [rbp+0D0h+var_58.Context], rax
0x18004ce19  mov     rbx, rcx
0x18004ce1c  lea     rax, [rbp+0D0h+var_90]
0x18004ce20  mov     [rbp+0D0h+var_58.Flags], 1
0x18004ce27  xor     r15d, r15d
0x18004ce2a  mov     [rbp+0D0h+var_30], rax
0x18004ce31  lea     rcx, [rbp+0D0h+var_58]; this
0x18004ce35  mov     [rbp+0D0h+var_90], r15d
0x18004ce39  mov     [rbp+0D0h+var_58.Previous], r15
0x18004ce40  mov     [rbp+0D0h+var_40], 20737853h
0x18004ce4b  mov     [rbp+0D0h+var_38], 7DAh
0x18004ce55  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004ce5a  cmp     [rbx+728h], r15b
0x18004ce61  jnz     loc_18004D1D4
0x18004ce67  mov     [rsp+210h+arg_10], rdi
0x18004ce6f  mov     edi, r15d
0x18004ce72  mov     [rsp+210h+arg_8], rsi
0x18004ce7a  mov     [rsp+210h+arg_18], r12
0x18004ce82  mov     [rsp+210h+var_10], r13
0x18004ce8a  mov     [rsp+210h+var_18], r14
0x18004ce92  mov     byte ptr [rbx+728h], 1
0x18004ce99  mov     [rbx+72Eh], r15b
0x18004cea0  mov     rax, [rbx+10h]
0x18004cea4  xor     ecx, ecx; dwErrCode
0x18004cea6  cmp     edi, [rax+8]
0x18004cea9  jnb     loc_18004D102
0x18004ceaf  call    cs:__imp_SetLastError
0x18004ceb6  nop     dword ptr [rax+rax+00h]
0x18004cebb  mov     rax, [rbx+18h]
0x18004cebf  lea     rcx, [rbp+0D0h+Frame]; Frame
0x18004cec3  mov     r14, [rbx+10h]
0x18004cec7  mov     esi, [rbx+1B8h]
0x18004cecd  mov     [rbp+0D0h+Frame.Flags], 1
0x18004ced4  mov     r12d, [rax+368h]
0x18004cedb  mov     r13d, [rax+360h]
0x18004cee2  mov     eax, [rax+35Ch]
0x18004cee8  mov     r15, [r14]
0x18004ceeb  mov     [rbp+0D0h+var_14C], eax
0x18004ceee  mov     rax, [rbx+1C8h]
0x18004cef5  mov     [rbp+0D0h+var_138], rax
0x18004cef9  mov     rax, [rbx+1C0h]
0x18004cf00  mov     [rbp+0D0h+var_140], rax
0x18004cf04  mov     eax, [rbx+178h]
0x18004cf0a  mov     [rbp+0D0h+var_150], eax
0x18004cf0d  mov     rax, [rbx+188h]
0x18004cf14  mov     [rbp+0D0h+var_148], rax
0x18004cf18  xor     eax, eax
0x18004cf1a  mov     [rbp+0D0h+var_8C], eax
0x18004cf1d  mov     [rbp+0D0h+Frame.Previous], rax
0x18004cf21  lea     rax, qword_180071830
0x18004cf28  mov     [rbp+0D0h+Frame.Context], rax
0x18004cf2c  lea     rax, [rbp+0D0h+var_8C]
0x18004cf30  mov     [rbp+0D0h+var_60], rax
0x18004cf34  mov     [rbp+0D0h+var_70], 20737853h
0x18004cf3c  mov     [rbp+0D0h+var_68], 22Fh
0x18004cf43  call    cs:__imp_RtlPushFrame
0x18004cf4a  nop     dword ptr [rax+rax+00h]
0x18004cf4f  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004cf56  jnz     loc_18004D1B7
0x18004cf5c  xorps   xmm0, xmm0
0x18004cf5f  xor     eax, eax
0x18004cf61  mov     [rbp+0D0h+var_A0], rax
0x18004cf65  movups  [rbp+0D0h+var_130], xmm0
0x18004cf69  movups  [rbp+0D0h+var_120], xmm0
0x18004cf6d  movups  [rbp+0D0h+var_110], xmm0
0x18004cf71  movups  [rbp+0D0h+var_100], xmm0
0x18004cf75  movups  [rbp+0D0h+var_F0], xmm0
0x18004cf79  movups  [rbp+0D0h+var_E0], xmm0
0x18004cf7d  movups  [rbp+0D0h+var_D0], xmm0
0x18004cf81  movups  [rbp+0D0h+var_C0], xmm0
0x18004cf85  movups  [rbp+0D0h+var_B0], xmm0
0x18004cf89  cmp     esi, 2
0x18004cf8c  jnz     loc_18004D214
0x18004cf92  mov     eax, edi
0x18004cf94  lea     rsi, [rax+rax*2]
0x18004cf98  shl     rsi, 4
0x18004cf9c  add     rsi, r15
0x18004cf9f  cmp     dword ptr [rsi+8], 0
0x18004cfa3  jz      short loc_18004CFF2
0x18004cfa5  mov     ecx, 54Fh; dwErrCode
0x18004cfaa  call    cs:__imp_SetLastError
0x18004cfb1  nop     dword ptr [rax+rax+00h]
0x18004cfb6  mov     rax, [rbp+0D0h+var_60]
0x18004cfba  xor     r15d, r15d
0x18004cfbd  mov     [rax], r15d
0x18004cfc0  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004cfc7  mov     rax, [rbp+0D0h+var_60]
0x18004cfcb  mov     esi, [rax]
0x18004cfcd  jnz     loc_18004D240
0x18004cfd3  lea     rcx, [rbp+0D0h+Frame]; Frame
0x18004cfd7  call    cs:__imp_RtlPopFrame
0x18004cfde  nop     dword ptr [rax+rax+00h]
0x18004cfe3  test    esi, esi
0x18004cfe5  jz      loc_18004D285
0x18004cfeb  inc     edi
0x18004cfed  jmp     loc_18004CEA0
0x18004cff2  mov     eax, [r14+4B4h]
0x18004cff9  xor     r15d, r15d
0x18004cffc  mov     rdx, [rsi+10h]
0x18004d000  mov     dword ptr [rbp+0D0h+var_130+0Ch], eax
0x18004d003  mov     eax, [r14+4B8h]
0x18004d00a  mov     dword ptr [rbp+0D0h+var_130+4], eax
0x18004d00d  mov     eax, [r14+4BCh]
0x18004d014  mov     dword ptr [rbp+0D0h+var_130+8], eax
0x18004d017  lea     rax, [r14+4C0h]
0x18004d01e  mov     qword ptr [rbp+0D0h+var_100+8], rax
0x18004d022  lea     rax, [r14+4F8h]
0x18004d029  mov     qword ptr [rbp+0D0h+var_F0], rax
0x18004d02d  mov     dword ptr [rbp+0D0h+var_130], 3
0x18004d034  cmp     [rdx+3Dh], r15b
0x18004d038  jz      loc_18004D1C1
0x18004d03e  lea     rax, [rdx+10h]
0x18004d042  mov     qword ptr [rbp+0D0h+var_120], rax
0x18004d046  lea     rcx, [rbp+0D0h+var_130]
0x18004d04a  mov     eax, [rdx+20h]
0x18004d04d  mov     dword ptr [rbp+0D0h+var_120+8], eax
0x18004d050  mov     rax, [rdx+28h]
0x18004d054  mov     qword ptr [rbp+0D0h+var_110], rax
0x18004d058  mov     rax, [rsi+18h]
0x18004d05c  mov     qword ptr [rbp+0D0h+var_110+8], rax
0x18004d060  mov     eax, [rbp+0D0h+var_150]
0x18004d063  mov     dword ptr [rbp+0D0h+var_E0+8], eax
0x18004d066  mov     rax, [rbp+0D0h+var_148]
0x18004d06a  mov     qword ptr [rbp+0D0h+var_E0], rax
0x18004d06e  mov     rax, [rbp+0D0h+var_140]
0x18004d072  mov     qword ptr [rbp+0D0h+var_D0+8], rax
0x18004d076  mov     rax, [rbp+0D0h+var_138]
0x18004d07a  mov     qword ptr [rbp+0D0h+var_C0], rax
0x18004d07e  mov     rax, [rbx+1D0h]
0x18004d085  mov     qword ptr [rbp+0D0h+var_C0+8], rax
0x18004d089  mov     eax, [rbp+0D0h+var_14C]
0x18004d08c  mov     dword ptr [rbp+0D0h+var_B0], eax
0x18004d08f  mov     qword ptr [rbp+0D0h+var_F0+8], r14
0x18004d093  mov     qword ptr [rbp+0D0h+var_100], r15
0x18004d097  mov     dword ptr [rbp+0D0h+var_E0+0Ch], r15d
0x18004d09b  mov     dword ptr [rbp+0D0h+var_D0], 2
0x18004d0a2  mov     dword ptr [rbp+0D0h+var_B0+4], r13d
0x18004d0a6  mov     dword ptr [rbp+0D0h+var_B0+8], r12d
0x18004d0aa  mov     dword ptr [rbp+0D0h+var_B0+0Ch], r15d
0x18004d0ae  mov     dword ptr [rbp+0D0h+var_A0], 1
0x18004d0b5  mov     rax, [rdx+30h]
0x18004d0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0be  cmp     dword ptr [rbp+0D0h+var_A0], 0
0x18004d0c2  jz      loc_18004D18D
0x18004d0c8  mov     eax, dword ptr [rbp+0D0h+var_B0+0Ch]
0x18004d0cb  mov     [rsi+0Ch], eax
0x18004d0ce  test    eax, eax
0x18004d0d0  jnz     loc_18004D1C9
0x18004d0d6  mov     rax, qword ptr [rbp+0D0h+var_100]
0x18004d0da  mov     [rsi], rax
0x18004d0dd  mov     eax, 1
0x18004d0e2  xor     ecx, ecx; dwErrCode
0x18004d0e4  mov     [rsi+8], eax
0x18004d0e7  call    cs:__imp_SetLastError
0x18004d0ee  nop     dword ptr [rax+rax+00h]
0x18004d0f3  mov     rax, [rbp+0D0h+var_60]
0x18004d0f7  mov     dword ptr [rax], 1
0x18004d0fd  jmp     loc_18004CFC0
0x18004d102  call    cs:__imp_SetLastError
0x18004d109  nop     dword ptr [rax+rax+00h]
0x18004d10e  mov     rax, [rbp+0D0h+var_30]
0x18004d115  mov     dword ptr [rax], 1
0x18004d11b  mov     r13, [rsp+210h+var_10]
0x18004d123  mov     r12, [rsp+210h+arg_18]
0x18004d12b  mov     rsi, [rsp+210h+arg_8]
0x18004d133  mov     r14, [rsp+210h+var_18]
0x18004d13b  mov     rdi, [rsp+210h+arg_10]
0x18004d143  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18004d14a  mov     rax, [rbp+0D0h+var_30]
0x18004d151  mov     r15, [rsp+210h+var_20]
0x18004d159  mov     ebx, [rax]
0x18004d15b  jnz     loc_18004D2A0
0x18004d161  lea     rcx, [rbp+0D0h+var_58]; Frame
0x18004d165  call    cs:__imp_RtlPopFrame
0x18004d16c  nop     dword ptr [rax+rax+00h]
0x18004d171  mov     eax, ebx
0x18004d173  mov     rcx, [rbp+0D0h+var_28]
0x18004d17a  xor     rcx, rsp; StackCookie
0x18004d17d  call    __security_check_cookie
0x18004d182  add     rsp, 208h
0x18004d189  pop     rbx
0x18004d18a  pop     rbp
0x18004d18b  retn
0x18004d18d  call    cs:__imp_GetLastError
0x18004d194  nop     dword ptr [rax+rax+00h]
0x18004d199  test    eax, eax
0x18004d19b  jnz     loc_18004CFC0
0x18004d1a1  mov     ecx, 54Fh; dwErrCode
0x18004d1a6  call    cs:__imp_SetLastError
0x18004d1ad  nop     dword ptr [rax+rax+00h]
0x18004d1b2  jmp     loc_18004CFC0
0x18004d1b7  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18004d1bc  jmp     loc_18004CF5C
0x18004d1c1  mov     rax, r15
0x18004d1c4  jmp     loc_18004D042
0x18004d1c9  mov     [rsi], r15
0x18004d1cc  mov     eax, r15d
0x18004d1cf  jmp     loc_18004D0E2
0x18004d1d4  mov     [rsp+210h+var_1E8], r15; struct _UNICODE_STRING *
0x18004d1d9  xor     r9d, r9d; struct _UNICODE_STRING *
0x18004d1dc  mov     edx, 0C1010001h; unsigned int
0x18004d1e1  mov     [rsp+210h+var_1F0], r15; struct _UNICODE_STRING *
0x18004d1e6  mov     r8d, 81h; unsigned int
0x18004d1ec  mov     rcx, rbx; this
0x18004d1ef  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18004d1f4  mov     edx, eax; int
0x18004d1f6  lea     rcx, [rbp+0D0h+var_58]; this
0x18004d1fa  mov     ebx, eax
0x18004d1fc  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18004d201  mov     edx, ebx; int
0x18004d203  lea     rcx, off_180079428; struct _CALL_SITE_INFO *
0x18004d20a  call    ?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z; FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)
0x18004d20f  jmp     loc_18004D143
0x18004d214  mov     [rbp+0D0h+var_68], 232h
0x18004d21b  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18004d220  mov     ecx, 57h ; 'W'; dwErrCode
0x18004d225  call    cs:__imp_SetLastError
0x18004d22c  nop     dword ptr [rax+rax+00h]
0x18004d231  mov     rax, [rbp+0D0h+var_60]
0x18004d235  xor     r15d, r15d
0x18004d238  mov     [rax], r15d
0x18004d23b  jmp     loc_18004CFC0
0x18004d240  test    esi, esi
0x18004d242  jz      short loc_18004D260
0x18004d244  xor     ecx, ecx; char *
0x18004d246  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004d24b  lea     rcx, [rbp+0D0h+Frame]; Frame
0x18004d24f  call    cs:__imp_RtlPopFrame
0x18004d256  nop     dword ptr [rax+rax+00h]
0x18004d25b  jmp     loc_18004CFEB
0x18004d260  call    cs:__imp_GetLastError
0x18004d267  nop     dword ptr [rax+rax+00h]
0x18004d26c  mov     ecx, eax; unsigned int
0x18004d26e  xor     edx, edx; Format
0x18004d270  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004d275  lea     rcx, [rbp+0D0h+Frame]; Frame
0x18004d279  call    cs:__imp_RtlPopFrame
0x18004d280  nop     dword ptr [rax+rax+00h]
0x18004d285  mov     rax, [rbp+0D0h+var_30]
0x18004d28c  lea     rcx, off_180079408; struct _CALL_SITE_INFO *
0x18004d293  mov     [rax], r15d
0x18004d296  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004d29b  jmp     loc_18004D11B
0x18004d2a0  test    ebx, ebx
0x18004d2a2  jz      short loc_18004D2B0
0x18004d2a4  xor     ecx, ecx; char *
0x18004d2a6  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004d2ab  jmp     loc_18004D161
0x18004d2b0  call    cs:__imp_GetLastError
0x18004d2b7  nop     dword ptr [rax+rax+00h]
0x18004d2bc  mov     ecx, eax; unsigned int
0x18004d2be  xor     edx, edx; Format
0x18004d2c0  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004d2c5  jmp     loc_18004D161
```
