# SxspCloseManifestGraph(_ACTCTXGENCTX *)

- ea: `0x180015088`
- end: `0x180015510`
- name: `?SxspCloseManifestGraph@@YAHPEAU_ACTCTXGENCTX@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(struct _ACTCTXGENCTX *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18005ae60`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180015088`
- `0x180015518`
- `0x180015920`
- `0x1800159c4`
- `0x180015a80`
- `0x180019740`
- `0x18001c2c8`
- `0x180022f60`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180015134`
- `ntdll!RtlPopFrame` at `0x180015242`
- `ntdll!RtlPopFrame` at `0x1800152fe`
- `ntdll!RtlPopFrame` at `0x180015134`
- `ntdll!RtlPopFrame` at `0x180015242`
- `ntdll!RtlPopFrame` at `0x1800152fe`
- `ntdll!RtlPushFrame` at `0x1800151b0`
- `ntdll!RtlPushFrame` at `0x1800152ae`
- `ntdll!RtlPushFrame` at `0x1800151b0`
- `ntdll!RtlPushFrame` at `0x1800152ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001510b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015177`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800151d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001525d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015311`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015388`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001540f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001510b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015177`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800151d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001525d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800152da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015311`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015346`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015388`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001540f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015438`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800151f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800151f3`

## pseudocode

```c
__int64 __fastcall SxspCloseManifestGraph(struct _ACTCTXGENCTX *a1)
{
  const char *v2; // rcx
  __int64 *i; // rdi
  unsigned int v4; // ebx
  const char *v6; // rcx
  CSxspIncorporateAssemblyLocals *v7; // rax
  struct CSxspIncorporateAssemblyLocals *v8; // r14
  int *v9; // rax
  int v10; // esi
  char **v11; // rcx
  DWORD v12; // ebx
  DWORD v13; // eax
  DWORD LastError; // eax
  DWORD v15; // eax
  unsigned __int64 v16; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-71h] BYREF
  int v18; // [rsp+40h] [rbp-69h] BYREF
  struct _TEB_ACTIVE_FRAME v19; // [rsp+48h] [rbp-61h] BYREF
  __int64 v20; // [rsp+60h] [rbp-49h]
  int v21; // [rsp+68h] [rbp-41h]
  int *v22; // [rsp+70h] [rbp-39h]
  int v23; // [rsp+78h] [rbp-31h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+80h] [rbp-29h] BYREF
  __int64 v25; // [rsp+98h] [rbp-11h]
  int v26; // [rsp+A0h] [rbp-9h]
  unsigned int *v27; // [rsp+A8h] [rbp-1h]

  v26 = 1591;
  v23 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D860;
  Frame.Previous = 0;
  v27 = (unsigned int *)&v23;
  Frame.Flags = 1;
  v25 = 544438355;
  CFrame::BaseEnter((CFrame *)&Frame);
  if ( !a1 )
  {
    v26 = 1594;
    FusionpTraceParameterCheck(v2);
    SetLastError(0x57u);
    *v27 = 0;
    goto LABEL_5;
  }
  for ( i = (__int64 *)*((_QWORD *)a1 + 289); ; i = (__int64 *)*i )
  {
    if ( !i || i == (__int64 *)((char *)a1 + 2312) )
    {
      SetLastError(0);
      *v27 = 1;
      goto LABEL_5;
    }
    if ( *((_DWORD *)i + 214) )
    {
      v18 = 0;
      v19.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CD80;
      v19.Flags = 1;
      v22 = &v18;
      v19.Previous = 0;
      v20 = 544438355;
      v21 = 144;
      RtlPushFrame(&v19);
      if ( g_FusionEnterExitTracingEnabled )
        FusionpTraceCallEntry();
      v16 = 0;
      v17 = 0;
      if ( i[4] )
      {
        SetLastError(0);
        if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                             1u,
                             (const struct _ASSEMBLY_IDENTITY *)i[4],
                             (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                             (const unsigned __int16 **)&v17,
                             &v16) )
        {
          SetLastError(0);
          *v22 = 1;
        }
        else
        {
          *v22 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800785E8);
        }
      }
      else
      {
        SetLastError(0x54Fu);
        *v22 = 0;
      }
      if ( g_FusionEnterExitTracingEnabled )
      {
        if ( *v22 )
        {
          FusionpTraceCallSuccessfulExit(0);
        }
        else
        {
          LastError = GetLastError();
          FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
        }
      }
      RtlPopFrame(&v19);
      goto LABEL_18;
    }
    SetLastError(0);
    v18 = 0;
    v19.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CC80;
    v19.Flags = 1;
    v22 = &v18;
    v19.Previous = 0;
    v20 = 544438355;
    v21 = 1382;
    RtlPushFrame(&v19);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    if ( *((_DWORD *)i + 214) )
    {
      v21 = 1387;
      FusionpTraceParameterCheck(v6);
      SetLastError(0x57u);
      *v22 = 0;
      goto LABEL_15;
    }
    SetLastError(0);
    v7 = (CSxspIncorporateAssemblyLocals *)HeapAlloc(g_hHeap, 0, 0x348u);
    if ( !v7 || (v8 = CSxspIncorporateAssemblyLocals::CSxspIncorporateAssemblyLocals(v7)) == 0 )
    {
      *v22 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006CC60);
LABEL_15:
      v9 = v22;
      v10 = *v22;
      goto LABEL_16;
    }
    SetLastError(0);
    if ( (unsigned int)SxspIncorporateAssembly(a1, (struct _ASSEMBLY *)i, v8) )
    {
      SetLastError(0);
      *v22 = 1;
    }
    else
    {
      *v22 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077920);
    }
    v10 = *v22;
    v12 = GetLastError();
    CSxspIncorporateAssemblyLocals::~CSxspIncorporateAssemblyLocals(v8);
    operator delete(v8);
    SetLastError(v12);
    v9 = v22;
LABEL_16:
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *v9 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v13 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v13, 0);
      }
    }
    RtlPopFrame(&v19);
    if ( !v10 )
    {
      v11 = off_180070350;
      goto LABEL_29;
    }
LABEL_18:
    SetLastError(0);
    if ( !(unsigned int)SxspProcessPendingAssemblies(a1) )
      break;
  }
  v11 = off_180077700;
LABEL_29:
  *v27 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
LABEL_5:
  v4 = *v27;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v4 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v15 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v15, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v4;
}

```

## disassembly

```asm
0x180015088  push    rbp
0x18001508a  push    rbx
0x18001508b  push    rsi
0x18001508c  push    rdi
0x18001508d  push    r12
0x18001508f  push    r13
0x180015091  push    r14
0x180015093  push    r15
0x180015095  lea     rbp, [rsp-1Fh]
0x18001509a  sub     rsp, 0C8h
0x1800150a1  mov     rax, cs:__security_cookie
0x1800150a8  xor     rax, rsp
0x1800150ab  mov     [rbp+57h+var_50], rax
0x1800150af  xor     r13d, r13d
0x1800150b2  mov     [rbp+57h+var_60], 637h
0x1800150b9  lea     rax, qword_18006D860
0x1800150c0  mov     [rbp+57h+var_88], r13d
0x1800150c4  mov     [rbp+57h+Frame.Context], rax
0x1800150c8  mov     r15, rcx
0x1800150cb  lea     rax, [rbp+57h+var_88]
0x1800150cf  mov     [rbp+57h+Frame.Previous], r13
0x1800150d3  lea     ebx, [r13+1]
0x1800150d7  mov     [rbp+57h+var_58], rax
0x1800150db  mov     esi, 20737853h
0x1800150e0  mov     [rbp+57h+Frame.Flags], ebx
0x1800150e3  lea     rcx, [rbp+57h+Frame]; this
0x1800150e7  mov     [rbp+57h+var_68], rsi
0x1800150eb  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800150f0  test    r15, r15
0x1800150f3  jz      loc_1800153FE
0x1800150f9  lea     r12, [r15+908h]
0x180015100  mov     rdi, [r12]
0x180015104  test    rdi, rdi
0x180015107  jnz     short loc_180015163
0x180015109  xor     ecx, ecx; dwErrCode
0x18001510b  call    cs:__imp_SetLastError
0x180015112  nop     dword ptr [rax+rax+00h]
0x180015117  mov     rax, [rbp+57h+var_58]
0x18001511b  mov     [rax], ebx
0x18001511d  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180015124  mov     rax, [rbp+57h+var_58]
0x180015128  mov     ebx, [rax]
0x18001512a  jnz     loc_1800154E6
0x180015130  lea     rcx, [rbp+57h+Frame]; Frame
0x180015134  call    cs:__imp_RtlPopFrame
0x18001513b  nop     dword ptr [rax+rax+00h]
0x180015140  mov     eax, ebx
0x180015142  mov     rcx, [rbp+57h+var_50]
0x180015146  xor     rcx, rsp; StackCookie
0x180015149  call    __security_check_cookie
0x18001514e  add     rsp, 0C8h
0x180015155  pop     r15
0x180015157  pop     r14
0x180015159  pop     r13
0x18001515b  pop     r12
0x18001515d  pop     rdi
0x18001515e  pop     rsi
0x18001515f  pop     rbx
0x180015160  pop     rbp
0x180015161  retn
0x180015163  cmp     rdi, r12
0x180015166  jz      short loc_180015109
0x180015168  cmp     [rdi+358h], r13d
0x18001516f  jnz     loc_180015281
0x180015175  xor     ecx, ecx; dwErrCode
0x180015177  call    cs:__imp_SetLastError
0x18001517e  nop     dword ptr [rax+rax+00h]
0x180015183  lea     rax, qword_18006CC80
0x18001518a  mov     [rbp+57h+var_C0], r13d
0x18001518e  mov     [rbp+57h+var_B8.Context], rax
0x180015192  lea     rcx, [rbp+57h+var_B8]; Frame
0x180015196  lea     rax, [rbp+57h+var_C0]
0x18001519a  mov     [rbp+57h+var_B8.Flags], ebx
0x18001519d  mov     [rbp+57h+var_90], rax
0x1800151a1  mov     [rbp+57h+var_B8.Previous], r13
0x1800151a5  mov     [rbp+57h+var_A0], rsi
0x1800151a9  mov     [rbp+57h+var_98], 566h
0x1800151b0  call    cs:__imp_RtlPushFrame
0x1800151b7  nop     dword ptr [rax+rax+00h]
0x1800151bc  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x1800151c3  jnz     loc_18001535A
0x1800151c9  cmp     [rdi+358h], r13d
0x1800151d0  jnz     loc_180015427
0x1800151d6  xor     ecx, ecx; dwErrCode
0x1800151d8  call    cs:__imp_SetLastError
0x1800151df  nop     dword ptr [rax+rax+00h]
0x1800151e4  mov     rcx, cs:g_hHeap; hHeap
0x1800151eb  xor     edx, edx; dwFlags
0x1800151ed  mov     r8d, 348h; dwBytes
0x1800151f3  call    cs:__imp_HeapAlloc
0x1800151fa  nop     dword ptr [rax+rax+00h]
0x1800151ff  test    rax, rax
0x180015202  jz      short loc_180015218
0x180015204  mov     rcx, rax; this
0x180015207  call    ??0CSxspIncorporateAssemblyLocals@@QEAA@XZ; CSxspIncorporateAssemblyLocals::CSxspIncorporateAssemblyLocals(void)
0x18001520c  mov     r14, rax
0x18001520f  test    rax, rax
0x180015212  jnz     loc_180015386
0x180015218  mov     rax, [rbp+57h+var_90]
0x18001521c  lea     rcx, off_18006CC60; struct _CALL_SITE_INFO *
0x180015223  mov     [rax], r13d
0x180015226  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18001522b  mov     rax, [rbp+57h+var_90]
0x18001522f  mov     esi, [rax]
0x180015231  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180015238  jnz     loc_180015468
0x18001523e  lea     rcx, [rbp+57h+var_B8]; Frame
0x180015242  call    cs:__imp_RtlPopFrame
0x180015249  nop     dword ptr [rax+rax+00h]
0x18001524e  test    esi, esi
0x180015250  jz      loc_18001536E
0x180015256  mov     esi, 20737853h
0x18001525b  xor     ecx, ecx; dwErrCode
0x18001525d  call    cs:__imp_SetLastError
0x180015264  nop     dword ptr [rax+rax+00h]
0x180015269  mov     rcx, r15; struct _ACTCTXGENCTX *
0x18001526c  call    ?SxspProcessPendingAssemblies@@YAHPEAU_ACTCTXGENCTX@@@Z; SxspProcessPendingAssemblies(_ACTCTXGENCTX *)
0x180015271  test    eax, eax
0x180015273  jz      loc_1800154DA
0x180015279  mov     rdi, [rdi]
0x18001527c  jmp     loc_180015104
0x180015281  lea     rax, qword_18006CD80
0x180015288  mov     [rbp+57h+var_C0], r13d
0x18001528c  mov     [rbp+57h+var_B8.Context], rax
0x180015290  lea     rcx, [rbp+57h+var_B8]; Frame
0x180015294  lea     rax, [rbp+57h+var_C0]
0x180015298  mov     [rbp+57h+var_B8.Flags], ebx
0x18001529b  mov     [rbp+57h+var_90], rax
0x18001529f  mov     [rbp+57h+var_B8.Previous], r13
0x1800152a3  mov     [rbp+57h+var_A0], rsi
0x1800152a7  mov     [rbp+57h+var_98], 90h
0x1800152ae  call    cs:__imp_RtlPushFrame
0x1800152b5  nop     dword ptr [rax+rax+00h]
0x1800152ba  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x1800152c1  jnz     loc_180015364
0x1800152c7  mov     [rbp+57h+var_D0], r13
0x1800152cb  mov     [rbp+57h+var_C8], r13
0x1800152cf  cmp     [rdi+20h], r13
0x1800152d3  jnz     short loc_18001530F
0x1800152d5  mov     ecx, 54Fh; dwErrCode
0x1800152da  call    cs:__imp_SetLastError
0x1800152e1  nop     dword ptr [rax+rax+00h]
0x1800152e6  mov     rax, [rbp+57h+var_90]
0x1800152ea  mov     [rax], r13d
0x1800152ed  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x1800152f4  jnz     loc_1800154AB
0x1800152fa  lea     rcx, [rbp+57h+var_B8]; Frame
0x1800152fe  call    cs:__imp_RtlPopFrame
0x180015305  nop     dword ptr [rax+rax+00h]
0x18001530a  jmp     loc_18001525B
0x18001530f  xor     ecx, ecx; dwErrCode
0x180015311  call    cs:__imp_SetLastError
0x180015318  nop     dword ptr [rax+rax+00h]
0x18001531d  mov     rdx, [rdi+20h]; struct _ASSEMBLY_IDENTITY *
0x180015321  lea     rax, [rbp+57h+var_D0]
0x180015325  lea     r9, [rbp+57h+var_C8]; unsigned __int16 **
0x180015329  mov     [rsp+100h+var_E0], rax; unsigned __int64 *
0x18001532e  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180015335  mov     ecx, ebx; unsigned int
0x180015337  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18001533c  test    eax, eax
0x18001533e  jz      loc_180015493
0x180015344  xor     ecx, ecx; dwErrCode
0x180015346  call    cs:__imp_SetLastError
0x18001534d  nop     dword ptr [rax+rax+00h]
0x180015352  mov     rax, [rbp+57h+var_90]
0x180015356  mov     [rax], ebx
0x180015358  jmp     short loc_1800152ED
0x18001535a  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x18001535f  jmp     loc_1800151C9
0x180015364  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180015369  jmp     loc_1800152C7
0x18001536e  lea     rcx, off_180070350; struct _CALL_SITE_INFO *
0x180015375  mov     rax, [rbp+57h+var_58]
0x180015379  mov     [rax], r13d
0x18001537c  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180015381  jmp     loc_18001511D
0x180015386  xor     ecx, ecx; dwErrCode
0x180015388  call    cs:__imp_SetLastError
0x18001538f  nop     dword ptr [rax+rax+00h]
0x180015394  mov     r8, r14; struct CSxspIncorporateAssemblyLocals *
0x180015397  mov     rdx, rdi; struct _ASSEMBLY *
0x18001539a  mov     rcx, r15; struct _ACTCTXGENCTX *
0x18001539d  call    ?SxspIncorporateAssembly@@YAHPEAU_ACTCTXGENCTX@@PEAU_ASSEMBLY@@PEAVCSxspIncorporateAssemblyLocals@@@Z; SxspIncorporateAssembly(_ACTCTXGENCTX *,_ASSEMBLY *,CSxspIncorporateAssemblyLocals *)
0x1800153a2  test    eax, eax
0x1800153a4  jz      loc_180015450
0x1800153aa  xor     ecx, ecx; dwErrCode
0x1800153ac  call    cs:__imp_SetLastError
0x1800153b3  nop     dword ptr [rax+rax+00h]
0x1800153b8  mov     rax, [rbp+57h+var_90]
0x1800153bc  mov     [rax], ebx
0x1800153be  mov     rax, [rbp+57h+var_90]
0x1800153c2  mov     esi, [rax]
0x1800153c4  call    cs:__imp_GetLastError
0x1800153cb  nop     dword ptr [rax+rax+00h]
0x1800153d0  mov     rcx, r14; this
0x1800153d3  mov     ebx, eax
0x1800153d5  call    ??1CSxspIncorporateAssemblyLocals@@QEAA@XZ; CSxspIncorporateAssemblyLocals::~CSxspIncorporateAssemblyLocals(void)
0x1800153da  mov     rcx, r14; void *
0x1800153dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800153e2  mov     ecx, ebx; dwErrCode
0x1800153e4  call    cs:__imp_SetLastError
0x1800153eb  nop     dword ptr [rax+rax+00h]
0x1800153f0  mov     rax, [rbp+57h+var_90]
0x1800153f4  mov     ebx, 1
0x1800153f9  jmp     loc_180015231
0x1800153fe  mov     [rbp+57h+var_60], 63Ah
0x180015405  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18001540a  mov     ecx, 57h ; 'W'; dwErrCode
0x18001540f  call    cs:__imp_SetLastError
0x180015416  nop     dword ptr [rax+rax+00h]
0x18001541b  mov     rax, [rbp+57h+var_58]
0x18001541f  mov     [rax], r13d
0x180015422  jmp     loc_18001511D
0x180015427  mov     [rbp+57h+var_98], 56Bh
0x18001542e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180015433  mov     ecx, 57h ; 'W'; dwErrCode
0x180015438  call    cs:__imp_SetLastError
0x18001543f  nop     dword ptr [rax+rax+00h]
0x180015444  mov     rax, [rbp+57h+var_90]
0x180015448  mov     [rax], r13d
0x18001544b  jmp     loc_18001522B
0x180015450  mov     rax, [rbp+57h+var_90]
0x180015454  lea     rcx, off_180077920; struct _CALL_SITE_INFO *
0x18001545b  mov     [rax], r13d
0x18001545e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180015463  jmp     loc_1800153BE
0x180015468  cmp     [rax], r13d
0x18001546b  jz      short loc_180015479
0x18001546d  xor     ecx, ecx; char *
0x18001546f  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180015474  jmp     loc_18001523E
0x180015479  call    cs:__imp_GetLastError
0x180015480  nop     dword ptr [rax+rax+00h]
0x180015485  mov     ecx, eax; unsigned int
0x180015487  xor     edx, edx; Format
0x180015489  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18001548e  jmp     loc_18001523E
0x180015493  mov     rax, [rbp+57h+var_90]
0x180015497  lea     rcx, off_1800785E8; struct _CALL_SITE_INFO *
0x18001549e  mov     [rax], r13d
0x1800154a1  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800154a6  jmp     loc_1800152ED
0x1800154ab  mov     rax, [rbp+57h+var_90]
0x1800154af  cmp     [rax], r13d
0x1800154b2  jz      short loc_1800154C0
0x1800154b4  xor     ecx, ecx; char *
0x1800154b6  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800154bb  jmp     loc_1800152FA
0x1800154c0  call    cs:__imp_GetLastError
0x1800154c7  nop     dword ptr [rax+rax+00h]
0x1800154cc  mov     ecx, eax; unsigned int
0x1800154ce  xor     edx, edx; Format
0x1800154d0  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800154d5  jmp     loc_1800152FA
0x1800154da  lea     rcx, off_180077700; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x1800154e1  jmp     loc_180015375
0x1800154e6  test    ebx, ebx
0x1800154e8  jz      short loc_1800154F6
0x1800154ea  xor     ecx, ecx; char *
0x1800154ec  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800154f1  jmp     loc_180015130
0x1800154f6  call    cs:__imp_GetLastError
0x1800154fd  nop     dword ptr [rax+rax+00h]
0x180015502  mov     ecx, eax; unsigned int
0x180015504  xor     edx, edx; Format
0x180015506  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18001550b  jmp     loc_180015130
```
