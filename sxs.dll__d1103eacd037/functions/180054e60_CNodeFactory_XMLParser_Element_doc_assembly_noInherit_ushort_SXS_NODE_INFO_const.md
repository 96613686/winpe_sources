# CNodeFactory::XMLParser_Element_doc_assembly_noInherit(ushort,_SXS_NODE_INFO const *)

- ea: `0x180054e60`
- end: `0x1800550bd`
- name: `?XMLParser_Element_doc_assembly_noInherit@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18002fffc`
- `0x1800515ec`
- `0x180054e60`
- `0x18005c978`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180054f34`
- `ntdll!RtlPopFrame` at `0x180054f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800550a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f71`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_noInherit(
        CNodeFactory *this,
        __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // ebx
  int v9; // ebx
  char **v10; // rcx
  DWORD LastError; // eax
  const struct _UNICODE_STRING *v12; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v13; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v14; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v15; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v16; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v17; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v18; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v19; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v20; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v21; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v22; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v23; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v24; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v25; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v26; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v27; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v28; // [rsp+B0h] [rbp-90h]
  struct _UNICODE_STRING v29; // [rsp+C0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v30; // [rsp+D0h] [rbp-70h] BYREF
  int v31; // [rsp+E0h] [rbp-60h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v33; // [rsp+100h] [rbp-40h]
  int v34; // [rsp+108h] [rbp-38h]
  unsigned int *v35; // [rsp+110h] [rbp-30h]

  v33 = 544438355;
  v31 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180072530;
  Frame.Previous = 0;
  v34 = 2244;
  Frame.Flags = 1;
  v35 = (unsigned int *)&v31;
  CFrame::BaseEnter((CFrame *)&Frame);
  v5 = *((_DWORD *)this + 94);
  if ( v5 == 1 )
  {
    if ( a2 == 1 )
    {
      v6 = *((_QWORD *)this + 2);
      if ( *(_BYTE *)(v6 + 1292) )
      {
        v9 = CNodeFactory::LogParseError(
               this,
               0xC101002F,
               0x84u,
               0,
               0,
               0,
               v12,
               v13,
               v14,
               v15,
               v16,
               v17,
               v18,
               v19,
               v20,
               v21,
               v22,
               v23,
               v24,
               v25,
               v26,
               v27,
               v28);
        CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&Frame, v9);
        v10 = off_180079328;
      }
      else
      {
        if ( !*((_BYTE *)this + 1833) )
        {
          *(_BYTE *)(v6 + 1292) = 1;
          SetLastError(0);
          *v35 = 1;
          goto LABEL_6;
        }
        v29.Buffer = (PWSTR)L"assemblyIdentity";
        *(_DWORD *)&v29.Length = 2097184;
        v30.Buffer = L"noInherit";
        *(_DWORD *)&v30.Length = 1179666;
        v9 = CNodeFactory::LogParseError(
               this,
               0xC1010049,
               0x85u,
               &v30,
               &v29,
               0,
               v12,
               v13,
               v14,
               v15,
               v16,
               v17,
               v18,
               v19,
               v20,
               v21,
               v22,
               v23,
               v24,
               v25,
               v26,
               v27,
               v28);
        CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&Frame, v9);
        v10 = off_180079308;
      }
    }
    else
    {
      v9 = CNodeFactory::LogParseError(
             this,
             0xC101002E,
             0x83u,
             0,
             0,
             0,
             v12,
             v13,
             v14,
             v15,
             v16,
             v17,
             v18,
             v19,
             v20,
             v21,
             v22,
             v23,
             v24,
             v25,
             v26,
             v27,
             v28);
      CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&Frame, v9);
      v10 = off_180079348;
    }
  }
  else
  {
    if ( v5 != 3 )
    {
      SetLastError(0x54Fu);
      *v35 = 0;
      goto LABEL_6;
    }
    v9 = CNodeFactory::LogParseError(
           this,
           0xC1010030,
           0x86u,
           0,
           0,
           0,
           v12,
           v13,
           v14,
           v15,
           v16,
           v17,
           v18,
           v19,
           v20,
           v21,
           v22,
           v23,
           v24,
           v25,
           v26,
           v27,
           v28);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&Frame, v9);
    v10 = off_1800792E8;
  }
  FusionpTraceCOMFailureOrigination((const struct _CALL_SITE_INFO *)v10, v9);
LABEL_6:
  v7 = *v35;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v7 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v7;
}

```

## disassembly

```asm
0x180054e60  mov     [rsp-8+arg_8], rbx
0x180054e65  mov     [rsp-8+arg_10], rsi
0x180054e6a  push    rbp
0x180054e6b  push    rdi
0x180054e6c  push    r14
0x180054e6e  lea     rbp, [rsp+20h]
0x180054e73  sub     rsp, 120h
0x180054e7a  mov     rax, cs:__security_cookie
0x180054e81  xor     rax, rsp
0x180054e84  mov     [rbp-10h+var_18], rax
0x180054e88  xor     esi, esi
0x180054e8a  mov     [rbp-10h+var_30], 20737853h
0x180054e92  lea     rax, qword_180072530
0x180054e99  mov     [rbp-10h+var_50], esi
0x180054e9c  mov     [rbp-10h+Frame.Context], rax
0x180054ea0  mov     rbx, rcx
0x180054ea3  lea     rax, [rbp-10h+var_50]
0x180054ea7  mov     [rbp-10h+Frame.Previous], rsi
0x180054eab  lea     r14d, [rsi+1]
0x180054eaf  mov     [rbp-10h+var_28], 8C4h
0x180054eb6  lea     rcx, [rbp-10h+Frame]; this
0x180054eba  mov     [rbp-10h+Frame.Flags], r14d
0x180054ebe  movzx   edi, dx
0x180054ec1  mov     [rbp-10h+var_20], rax
0x180054ec5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180054eca  mov     eax, [rbx+178h]
0x180054ed0  cmp     eax, r14d
0x180054ed3  jnz     loc_180054F67
0x180054ed9  cmp     di, r14w
0x180054edd  jnz     loc_180054FBE
0x180054ee3  mov     rax, [rbx+10h]
0x180054ee7  cmp     [rax+50Ch], sil
0x180054eee  jnz     loc_18005505D
0x180054ef4  cmp     [rbx+729h], sil
0x180054efb  jnz     loc_180054FF4
0x180054f01  xor     ecx, ecx; dwErrCode
0x180054f03  mov     [rax+50Ch], r14b
0x180054f0a  call    cs:__imp_SetLastError
0x180054f11  nop     dword ptr [rax+rax+00h]
0x180054f16  mov     rax, [rbp-10h+var_20]
0x180054f1a  mov     [rax], r14d
0x180054f1d  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x180054f24  mov     rax, [rbp-10h+var_20]
0x180054f28  mov     ebx, [rax]
0x180054f2a  jnz     loc_180055093
0x180054f30  lea     rcx, [rbp-10h+Frame]; Frame
0x180054f34  call    cs:__imp_RtlPopFrame
0x180054f3b  nop     dword ptr [rax+rax+00h]
0x180054f40  mov     eax, ebx
0x180054f42  mov     rcx, [rbp-10h+var_18]
0x180054f46  xor     rcx, rsp; StackCookie
0x180054f49  call    __security_check_cookie
0x180054f4e  lea     r11, [rsp+130h+var_10]
0x180054f56  mov     rbx, [r11+28h]
0x180054f5a  mov     rsi, [r11+30h]
0x180054f5e  mov     rsp, r11
0x180054f61  pop     r14
0x180054f63  pop     rdi
0x180054f64  pop     rbp
0x180054f65  retn
0x180054f67  cmp     eax, 3
0x180054f6a  jz      short loc_180054F85
0x180054f6c  mov     ecx, 54Fh; dwErrCode
0x180054f71  call    cs:__imp_SetLastError
0x180054f78  nop     dword ptr [rax+rax+00h]
0x180054f7d  mov     rax, [rbp-10h+var_20]
0x180054f81  mov     [rax], esi
0x180054f83  jmp     short loc_180054F1D
0x180054f85  mov     [rsp+130h+var_108], rsi; struct _UNICODE_STRING *
0x180054f8a  xor     r9d, r9d; struct _UNICODE_STRING *
0x180054f8d  mov     edx, 0C1010030h; unsigned int
0x180054f92  mov     [rsp+130h+var_110], rsi; struct _UNICODE_STRING *
0x180054f97  mov     r8d, 86h; unsigned int
0x180054f9d  mov     rcx, rbx; this
0x180054fa0  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180054fa5  mov     edx, eax; int
0x180054fa7  lea     rcx, [rbp-10h+Frame]; this
0x180054fab  mov     ebx, eax
0x180054fad  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x180054fb2  lea     rcx, off_1800792E8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180054fb9  jmp     loc_180055051
0x180054fbe  mov     [rsp+130h+var_108], rsi; struct _UNICODE_STRING *
0x180054fc3  xor     r9d, r9d; struct _UNICODE_STRING *
0x180054fc6  mov     edx, 0C101002Eh; unsigned int
0x180054fcb  mov     [rsp+130h+var_110], rsi; struct _UNICODE_STRING *
0x180054fd0  mov     r8d, 83h; unsigned int
0x180054fd6  mov     rcx, rbx; this
0x180054fd9  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180054fde  mov     edx, eax; int
0x180054fe0  lea     rcx, [rbp-10h+Frame]; this
0x180054fe4  mov     ebx, eax
0x180054fe6  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x180054feb  lea     rcx, off_180079348; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180054ff2  jmp     short loc_180055051
0x180054ff4  lea     rax, aAssemblyidenti; "assemblyIdentity"
0x180054ffb  mov     [rsp+130h+var_108], rsi; struct _UNICODE_STRING *
0x180055000  mov     [rbp-10h+var_70.Buffer], rax
0x180055004  lea     r9, [rbp-10h+var_60]; struct _UNICODE_STRING *
0x180055008  lea     rax, aNoinherit; "noInherit"
0x18005500f  mov     dword ptr [rbp-10h+var_70.Length], 200020h
0x180055016  mov     [rbp-10h+var_60.Buffer], rax
0x18005501a  mov     edx, 0C1010049h; unsigned int
0x18005501f  lea     rax, [rbp-10h+var_70]
0x180055023  mov     dword ptr [rbp-10h+var_60.Length], 120012h
0x18005502a  mov     r8d, 85h; unsigned int
0x180055030  mov     [rsp+130h+var_110], rax; struct _UNICODE_STRING *
0x180055035  mov     rcx, rbx; this
0x180055038  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18005503d  mov     edx, eax; int
0x18005503f  lea     rcx, [rbp-10h+Frame]; this
0x180055043  mov     ebx, eax
0x180055045  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005504a  lea     rcx, off_180079308; struct _CALL_SITE_INFO *
0x180055051  mov     edx, ebx; int
0x180055053  call    ?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z; FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)
0x180055058  jmp     loc_180054F1D
0x18005505d  mov     [rsp+130h+var_108], rsi; struct _UNICODE_STRING *
0x180055062  xor     r9d, r9d; struct _UNICODE_STRING *
0x180055065  mov     edx, 0C101002Fh; unsigned int
0x18005506a  mov     [rsp+130h+var_110], rsi; struct _UNICODE_STRING *
0x18005506f  mov     r8d, 84h; unsigned int
0x180055075  mov     rcx, rbx; this
0x180055078  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18005507d  mov     edx, eax; int
0x18005507f  lea     rcx, [rbp-10h+Frame]; this
0x180055083  mov     ebx, eax
0x180055085  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005508a  lea     rcx, off_180079328; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180055091  jmp     short loc_180055051
0x180055093  test    ebx, ebx
0x180055095  jz      short loc_1800550A3
0x180055097  xor     ecx, ecx; char *
0x180055099  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18005509e  jmp     loc_180054F30
0x1800550a3  call    cs:__imp_GetLastError
0x1800550aa  nop     dword ptr [rax+rax+00h]
0x1800550af  mov     ecx, eax; unsigned int
0x1800550b1  xor     edx, edx; Format
0x1800550b3  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800550b8  jmp     loc_180054F30
```
