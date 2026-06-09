# RADIUSAccounting::StartInterimAccouting(void)

- ea: `0x180060bcc`
- end: `0x180060f65`
- name: `?StartInterimAccouting@RADIUSAccounting@@IEAAKXZ`
- size: `921`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180060880`

## callees

- `0x180007794`
- `0x1800077bc`
- `0x180060bcc`
- `0x180065d28`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e3c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180060e2e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180060e2e`

## string_xrefs

- `0x180060f10`: `Interim accounting not configured.`
- `0x180060e87`: `CreateTimerQueueTimer failed %x`

## pseudocode

```c
__int64 __fastcall RADIUSAccounting::StartInterimAccouting(PVOID Parameter)
{
  PVOID *v2; // rbx
  __int64 v3; // rdx
  const wchar_t *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rdx
  PVOID v12; // rcx
  DWORD LastError; // eax
  unsigned int v14; // ebx
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+7Ch] [rbp-84h]
  int v23; // [rsp+80h] [rbp-80h] BYREF
  char v24[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v16 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RADIUSAccounting::StartInterimAccouting",
      &v16,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
    v2 = (PVOID *)WPP_GLOBAL_Control;
    v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
  }
  if ( !*(_QWORD *)(*((_QWORD *)Parameter + 2) + 32LL) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x20000000) != 0 && *((_BYTE *)v2 + 25) >= 3u )
    {
      WPP_SF_(v2[2], 23, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
      v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
    }
    if ( v3 )
    {
      v4 = L"No need to support Interim Accounting";
LABEL_49:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gBaseTemplateFunc)(
        gBaseEtwContext,
        v3,
        v4);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  v5 = *((_QWORD *)Parameter + 1);
  v6 = *(_QWORD *)(v5 + 112);
  if ( *(_DWORD *)(v6 + 2164) )
  {
    v7 = *(_DWORD *)(v6 + 2168);
    goto LABEL_22;
  }
  v8 = *(_QWORD *)(v5 + 120);
  if ( v8 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v10 = RasAuthAttributeGet(85, v9);
    if ( v10 )
    {
      v7 = v10[2];
      v2 = (PVOID *)WPP_GLOBAL_Control;
      v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
LABEL_22:
      if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x20000000) != 0 && *((_BYTE *)v2 + 25) >= 3u )
      {
        WPP_SF_d(v2[2], 26, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids, v7);
        v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
      }
      if ( v3 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"Accouting InterimInterval: %u", v7);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
          gBaseEtwContext,
          *((_QWORD *)&xmmword_1800AABC0 + 1),
          &v23);
      }
      if ( v7 < 0x3C )
        v7 = 60;
      if ( !CreateTimerQueueTimer(
              (PHANDLE)Parameter + 3,
              0,
              RADIUSAccounting::InterimAccountingTimerCallback,
              Parameter,
              1000 * v7,
              1000 * v7,
              0) )
      {
        LastError = GetLastError();
        v16 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids, LastError);
        }
        if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
        {
          LOWORD(v23) = 0;
          FormatRRASErrorString(&v23, L"CreateTimerQueueTimer failed %x", v16);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
            gBaseEtwContext,
            *((_QWORD *)&xmmword_1800AABC0 + 1),
            &v23);
        }
        *((_QWORD *)Parameter + 3) = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_46;
    }
    v11 = 24;
    v12 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_45:
    WPP_SF_(v12, v11, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
LABEL_46:
    v3 = *((_QWORD *)&xmmword_1800AABC0 + 1);
    goto LABEL_47;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x20000000) != 0 && *((_BYTE *)v2 + 25) >= 3u )
  {
    v11 = 25;
    v12 = v2[2];
    goto LABEL_45;
  }
LABEL_47:
  if ( v3 )
  {
    v4 = L"Interim accounting not configured.";
    goto LABEL_49;
  }
LABEL_50:
  v14 = v16;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v14;
}

```

## disassembly

```asm
0x180060bcc  mov     [rsp-8+arg_8], rbx
0x180060bd1  mov     [rsp-8+arg_10], rsi
0x180060bd6  push    rbp
0x180060bd7  push    rdi
0x180060bd8  push    r12
0x180060bda  push    r13
0x180060bdc  push    r15
0x180060bde  lea     rbp, [rsp-790h]
0x180060be6  sub     rsp, 890h
0x180060bed  mov     rax, cs:__security_cookie
0x180060bf4  xor     rax, rsp
0x180060bf7  mov     [rbp+7B0h+var_30], rax
0x180060bfe  mov     rsi, rcx
0x180060c01  mov     [rsp+8B0h+var_870], 0
0x180060c09  lea     r12, WPP_GLOBAL_Control
0x180060c10  mov     r15d, 20000000h
0x180060c16  lea     r13, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x180060c1d  mov     rbx, cs:WPP_GLOBAL_Control
0x180060c24  cmp     rbx, r12
0x180060c27  jz      short loc_180060C47
0x180060c29  test    [rbx+1Ch], r15d
0x180060c2d  jz      short loc_180060C47
0x180060c2f  mov     edx, 16h
0x180060c34  mov     r8, r13
0x180060c37  mov     rcx, [rbx+10h]
0x180060c3b  call    WPP_SF_
0x180060c40  mov     rbx, cs:WPP_GLOBAL_Control
0x180060c47  xor     eax, eax
0x180060c49  mov     [rbp+7B0h+var_830], eax
0x180060c4c  xor     edx, edx; Val
0x180060c4e  mov     r8d, 7FCh; Size
0x180060c54  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180060c58  call    memset_0
0x180060c5d  xorps   xmm0, xmm0
0x180060c60  movdqu  [rsp+8B0h+var_860], xmm0
0x180060c66  mov     [rsp+8B0h+var_868], 0
0x180060c6f  xorps   xmm1, xmm1
0x180060c72  movdqu  [rsp+8B0h+var_850], xmm1
0x180060c78  mov     [rsp+8B0h+var_840], 0
0x180060c81  mov     [rsp+8B0h+var_838], 0FFFFFFFFh
0x180060c89  mov     [rsp+8B0h+var_834], 0
0x180060c91  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060c98  test    rdx, rdx
0x180060c9b  jz      short loc_180060CC8
0x180060c9d  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180060ca4  lea     r8, [rsp+8B0h+var_870]; unsigned int *
0x180060ca9  lea     rdx, aRadiusaccounti_2; "RADIUSAccounting::StartInterimAccouting"
0x180060cb0  lea     rcx, [rsp+8B0h+var_868]; this
0x180060cb5  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180060cba  mov     rbx, cs:WPP_GLOBAL_Control
0x180060cc1  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060cc8  mov     rax, [rsi+10h]
0x180060ccc  cmp     qword ptr [rax+20h], 0
0x180060cd1  jnz     short loc_180060D11
0x180060cd3  cmp     rbx, r12
0x180060cd6  jz      short loc_180060CFC
0x180060cd8  test    [rbx+1Ch], r15d
0x180060cdc  jz      short loc_180060CFC
0x180060cde  cmp     byte ptr [rbx+19h], 3
0x180060ce2  jb      short loc_180060CFC
0x180060ce4  mov     edx, 17h
0x180060ce9  mov     r8, r13
0x180060cec  mov     rcx, [rbx+10h]
0x180060cf0  call    WPP_SF_
0x180060cf5  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060cfc  test    rdx, rdx
0x180060cff  jz      loc_180060F2A
0x180060d05  lea     r8, aNoNeedToSuppor; "No need to support Interim Accounting"
0x180060d0c  jmp     loc_180060F17
0x180060d11  mov     rax, [rsi+8]
0x180060d15  mov     rdi, [rax+70h]
0x180060d19  cmp     dword ptr [rdi+874h], 0
0x180060d20  jz      short loc_180060D2A
0x180060d22  mov     edi, [rdi+878h]
0x180060d28  jmp     short loc_180060D96
0x180060d2a  mov     rcx, [rax+78h]
0x180060d2e  test    rcx, rcx
0x180060d31  jz      loc_180060EE2
0x180060d37  mov     rax, [rcx]
0x180060d3a  mov     rax, [rax+10h]
0x180060d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060d43  mov     rdx, rax
0x180060d46  mov     ecx, 55h ; 'U'
0x180060d4b  call    RasAuthAttributeGet
0x180060d50  test    rax, rax
0x180060d53  jnz     short loc_180060D85
0x180060d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d5c  cmp     rcx, r12
0x180060d5f  jz      loc_180060F04
0x180060d65  test    [rcx+1Ch], r15d
0x180060d69  jz      loc_180060F04
0x180060d6f  cmp     byte ptr [rcx+19h], 3
0x180060d73  jb      loc_180060F04
0x180060d79  lea     edx, [rax+18h]
0x180060d7c  mov     rcx, [rcx+10h]
0x180060d80  jmp     loc_180060EFC
0x180060d85  mov     edi, [rax+8]
0x180060d88  mov     rbx, cs:WPP_GLOBAL_Control
0x180060d8f  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060d96  cmp     rbx, r12
0x180060d99  jz      short loc_180060DC2
0x180060d9b  test    [rbx+1Ch], r15d
0x180060d9f  jz      short loc_180060DC2
0x180060da1  cmp     byte ptr [rbx+19h], 3
0x180060da5  jb      short loc_180060DC2
0x180060da7  mov     edx, 1Ah
0x180060dac  mov     r9d, edi
0x180060daf  mov     r8, r13
0x180060db2  mov     rcx, [rbx+10h]
0x180060db6  call    WPP_SF_d
0x180060dbb  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060dc2  test    rdx, rdx
0x180060dc5  jz      short loc_180060DFE
0x180060dc7  xor     eax, eax
0x180060dc9  mov     word ptr [rbp+7B0h+var_830], ax
0x180060dcd  mov     r8d, edi
0x180060dd0  lea     rdx, aAccoutingInter; "Accouting InterimInterval: %u"
0x180060dd7  lea     rcx, [rbp+7B0h+var_830]
0x180060ddb  call    FormatRRASErrorString
0x180060de0  lea     r8, [rbp+7B0h+var_830]
0x180060de4  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060deb  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180060df2  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060dfe  mov     eax, 3Ch ; '<'
0x180060e03  cmp     edi, eax
0x180060e05  cmovb   edi, eax
0x180060e08  imul    eax, edi, 3E8h
0x180060e0e  mov     [rsp+8B0h+Flags], 0; Flags
0x180060e16  mov     [rsp+8B0h+Period], eax; Period
0x180060e1a  mov     [rsp+8B0h+DueTime], eax; DueTime
0x180060e1e  mov     r9, rsi; Parameter
0x180060e21  lea     r8, ?InterimAccountingTimerCallback@RADIUSAccounting@@KAXPEAXE@Z; Callback
0x180060e28  xor     edx, edx; TimerQueue
0x180060e2a  lea     rcx, [rsi+18h]; phNewTimer
0x180060e2e  call    cs:__imp_CreateTimerQueueTimer
0x180060e34  test    eax, eax
0x180060e36  jnz     loc_180060EBD
0x180060e3c  call    cs:__imp_GetLastError
0x180060e42  mov     [rsp+8B0h+var_870], eax
0x180060e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e4d  cmp     rcx, r12
0x180060e50  jz      short loc_180060E72
0x180060e52  test    [rcx+1Ch], r15d
0x180060e56  jz      short loc_180060E72
0x180060e58  cmp     byte ptr [rcx+19h], 1
0x180060e5c  jb      short loc_180060E72
0x180060e5e  mov     edx, 1Bh
0x180060e63  mov     r9d, eax
0x180060e66  mov     r8, r13
0x180060e69  mov     rcx, [rcx+10h]
0x180060e6d  call    WPP_SF_d
0x180060e72  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x180060e7a  jz      short loc_180060EB5
0x180060e7c  xor     eax, eax
0x180060e7e  mov     word ptr [rbp+7B0h+var_830], ax
0x180060e82  mov     r8d, [rsp+8B0h+var_870]
0x180060e87  lea     rdx, aCreatetimerque_1; "CreateTimerQueueTimer failed %x"
0x180060e8e  lea     rcx, [rbp+7B0h+var_830]
0x180060e92  call    FormatRRASErrorString
0x180060e97  lea     r8, [rbp+7B0h+var_830]
0x180060e9b  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060ea2  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180060ea9  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060eb5  mov     qword ptr [rsi+18h], 0
0x180060ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180060ec4  cmp     rcx, r12
0x180060ec7  jz      short loc_180060F2A
0x180060ec9  test    [rcx+1Ch], r15d
0x180060ecd  jz      short loc_180060F2A
0x180060ecf  mov     edx, 1Ch
0x180060ed4  mov     r8, r13
0x180060ed7  mov     rcx, [rcx+10h]
0x180060edb  call    WPP_SF_
0x180060ee0  jmp     short loc_180060F2A
0x180060ee2  cmp     rbx, r12
0x180060ee5  jz      short loc_180060F0B
0x180060ee7  test    [rbx+1Ch], r15d
0x180060eeb  jz      short loc_180060F0B
0x180060eed  cmp     byte ptr [rbx+19h], 3
0x180060ef1  jb      short loc_180060F0B
0x180060ef3  mov     edx, 19h
0x180060ef8  mov     rcx, [rbx+10h]
0x180060efc  mov     r8, r13
0x180060eff  call    WPP_SF_
0x180060f04  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180060f0b  test    rdx, rdx
0x180060f0e  jz      short loc_180060F2A
0x180060f10  lea     r8, aInterimAccount; "Interim accounting not configured."
0x180060f17  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180060f1e  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180060f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f2a  mov     ebx, [rsp+8B0h+var_870]
0x180060f2e  lea     rcx, [rsp+8B0h+var_868]; this
0x180060f33  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180060f38  mov     eax, ebx
0x180060f3a  mov     rcx, [rbp+7B0h+var_30]
0x180060f41  xor     rcx, rsp; StackCookie
0x180060f44  call    __security_check_cookie
0x180060f49  lea     r11, [rsp+8B0h+var_20]
0x180060f51  mov     rbx, [r11+38h]
0x180060f55  mov     rsi, [r11+40h]
0x180060f59  mov     rsp, r11
0x180060f5c  pop     r15
0x180060f5e  pop     r13
0x180060f60  pop     r12
0x180060f62  pop     rdi
0x180060f63  pop     rbp
0x180060f64  retn
```
