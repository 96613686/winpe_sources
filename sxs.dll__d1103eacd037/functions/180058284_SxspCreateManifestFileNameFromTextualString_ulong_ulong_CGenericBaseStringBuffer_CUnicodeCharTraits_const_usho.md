# SxspCreateManifestFileNameFromTextualString(ulong,ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,ushort const *,_ACTCTXGENCTX *,CGenericBaseStringBuffer<CUnicodeCharTraits> &,_ASSEMBLY_IDENTITY * *)

- ea: `0x180058284`
- end: `0x18005844a`
- name: `?SxspCreateManifestFileNameFromTextualString@@YAHKKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@PEBGPEAU_ACTCTXGENCTX@@AEAV1@PEAPEAU_ASSEMBLY_IDENTITY@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(int, int, int, int, struct _ACTCTXGENCTX *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18005ae60`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18000e160`
- `0x18001c270`
- `0x180022d40`
- `0x180023ee0`
- `0x18002cc78`
- `0x180058284`
- `0x18005d2b0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058376`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800583b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058376`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800583b3`

## pseudocode

```c
__int64 __fastcall SxspCreateManifestFileNameFromTextualString(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        struct _ACTCTXGENCTX *a5,
        __int64 a6,
        struct _ASSEMBLY_IDENTITY **a7)
{
  const char *v9; // rcx
  struct _ASSEMBLY_IDENTITY *v10; // rbx
  char **v11; // rcx
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+40h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-29h] BYREF
  int v16; // [rsp+50h] [rbp-21h] BYREF
  int v17; // [rsp+58h] [rbp-19h] BYREF
  __int64 v18; // [rsp+60h] [rbp-11h]
  __int64 *v19; // [rsp+68h] [rbp-9h]
  __int64 v20; // [rsp+70h] [rbp-1h]
  int v21; // [rsp+78h] [rbp+7h]
  int *v22; // [rsp+80h] [rbp+Fh]

  v19 = &qword_180072B10;
  v16 = 0;
  v22 = &v16;
  v17 = 1;
  v18 = 0;
  v20 = 544438355;
  v21 = 3796;
  CFrame::BaseEnter((CFrame *)&v17);
  lpMem = 0;
  v14 = 0;
  if ( !a4 )
  {
    v21 = 3801;
    FusionpTraceParameterCheck(v9);
    SetLastError(0x57u);
    *v22 = 0;
    goto LABEL_15;
  }
  SetLastError(0);
  if ( (unsigned int)SxspCreateAssemblyIdentityFromTextualString(a4, (struct _ASSEMBLY_IDENTITY **)&lpMem) )
  {
    SetLastError(0);
    v10 = (struct _ASSEMBLY_IDENTITY *)lpMem;
    if ( (unsigned int)SxspApplyPolicy((struct _ASSEMBLY_IDENTITY *)lpMem, a5, &v14) )
    {
      SetLastError(0);
      if ( (unsigned int)SxspGetInstalledPath(
                           (v14 >> 2) & 8,
                           1u,
                           *(_QWORD *)(a3 + 16),
                           *(_QWORD *)(a3 + 32),
                           v10,
                           0,
                           a6) )
      {
        if ( a7 )
        {
          *a7 = v10;
          v10 = 0;
        }
        v16 = 1;
        goto LABEL_13;
      }
      v11 = off_180072B30;
    }
    else
    {
      v11 = off_180075130;
    }
    *v22 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
  }
  else
  {
    *v22 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075150);
    v10 = (struct _ASSEMBLY_IDENTITY *)lpMem;
  }
LABEL_13:
  if ( v10 )
    SxsDestroyAssemblyIdentity(v10);
LABEL_15:
  v12 = v16;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v17);
  return v12;
}

```

## disassembly

```asm
0x180058284  mov     [rsp-8+arg_0], rbx
0x180058289  push    rbp
0x18005828a  push    rsi
0x18005828b  push    rdi
0x18005828c  push    r14
0x18005828e  push    r15
0x180058290  lea     rbp, [rsp-1Fh]
0x180058295  sub     rsp, 90h
0x18005829c  mov     rax, cs:__security_cookie
0x1800582a3  xor     rax, rsp
0x1800582a6  mov     [rbp+3Fh+var_28], rax
0x1800582aa  mov     r14, [rbp+3Fh+arg_20]
0x1800582ae  lea     rax, qword_180072B10
0x1800582b5  mov     r15, [rbp+3Fh+arg_28]
0x1800582b9  lea     rcx, [rbp+3Fh+var_58]; this
0x1800582bd  mov     rdi, [rbp+3Fh+arg_30]
0x1800582c1  mov     rbx, r9
0x1800582c4  mov     [rbp+3Fh+var_48], rax
0x1800582c8  mov     rsi, r8
0x1800582cb  lea     rax, [rbp+3Fh+var_60]
0x1800582cf  mov     [rbp+3Fh+var_60], 0
0x1800582d6  mov     [rbp+3Fh+var_30], rax
0x1800582da  mov     [rbp+3Fh+var_58], 1
0x1800582e1  mov     [rbp+3Fh+var_50], 0
0x1800582e9  mov     [rbp+3Fh+var_40], 20737853h
0x1800582f1  mov     [rbp+3Fh+var_38], 0ED4h
0x1800582f8  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800582fd  mov     [rbp+3Fh+lpMem], 0
0x180058305  mov     [rbp+3Fh+var_70], 0
0x18005830c  test    rbx, rbx
0x18005830f  jnz     short loc_180058337
0x180058311  mov     [rbp+3Fh+var_38], 0ED9h
0x180058318  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005831d  lea     ecx, [rbx+57h]; dwErrCode
0x180058320  call    cs:__imp_SetLastError
0x180058327  nop     dword ptr [rax+rax+00h]
0x18005832c  mov     rax, [rbp+3Fh+var_30]
0x180058330  mov     [rax], ebx
0x180058332  jmp     loc_180058418
0x180058337  xor     ecx, ecx; dwErrCode
0x180058339  call    cs:__imp_SetLastError
0x180058340  nop     dword ptr [rax+rax+00h]
0x180058345  lea     rdx, [rbp+3Fh+lpMem]
0x180058349  mov     rcx, rbx
0x18005834c  call    SxspCreateAssemblyIdentityFromTextualString
0x180058351  test    eax, eax
0x180058353  jnz     short loc_180058374
0x180058355  mov     rax, [rbp+3Fh+var_30]
0x180058359  lea     rcx, off_180075150; struct _CALL_SITE_INFO *
0x180058360  mov     dword ptr [rax], 0
0x180058366  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005836b  mov     rbx, [rbp+3Fh+lpMem]
0x18005836f  jmp     loc_18005840B
0x180058374  xor     ecx, ecx; dwErrCode
0x180058376  call    cs:__imp_SetLastError
0x18005837d  nop     dword ptr [rax+rax+00h]
0x180058382  mov     rbx, [rbp+3Fh+lpMem]
0x180058386  lea     r8, [rbp+3Fh+var_70]; unsigned int *
0x18005838a  mov     rcx, rbx; struct _ASSEMBLY_IDENTITY *
0x18005838d  mov     rdx, r14; struct _ACTCTXGENCTX *
0x180058390  call    ?SxspApplyPolicy@@YAHPEAU_ASSEMBLY_IDENTITY@@PEAU_ACTCTXGENCTX@@AEAK@Z; SxspApplyPolicy(_ASSEMBLY_IDENTITY *,_ACTCTXGENCTX *,ulong &)
0x180058395  test    eax, eax
0x180058397  jnz     short loc_1800583B1
0x180058399  lea     rcx, off_180075130; struct _CALL_SITE_INFO *
0x1800583a0  mov     rax, [rbp+3Fh+var_30]
0x1800583a4  mov     dword ptr [rax], 0
0x1800583aa  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800583af  jmp     short loc_18005840B
0x1800583b1  xor     ecx, ecx; dwErrCode
0x1800583b3  call    cs:__imp_SetLastError
0x1800583ba  nop     dword ptr [rax+rax+00h]
0x1800583bf  mov     ecx, [rbp+3Fh+var_70]
0x1800583c2  mov     edx, 1; int
0x1800583c7  mov     r9, [rsi+20h]; int
0x1800583cb  mov     r8, [rsi+10h]; int
0x1800583cf  shr     ecx, 2
0x1800583d2  mov     [rsp+0B0h+var_80], r15; __int64
0x1800583d7  and     ecx, 8; int
0x1800583da  mov     [rsp+0B0h+var_88], 0; __int64
0x1800583e3  mov     [rsp+0B0h+var_90], rbx; struct _ASSEMBLY_IDENTITY *
0x1800583e8  call    ?SxspGetInstalledPath@@YAHKKPEBG_KPEBU_ASSEMBLY_IDENTITY@@PEAU_PROBING_ATTRIBUTE_CACHE@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspGetInstalledPath(ulong,ulong,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY const *,_PROBING_ATTRIBUTE_CACHE *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x1800583ed  test    eax, eax
0x1800583ef  jnz     short loc_1800583FA
0x1800583f1  lea     rcx, off_180072B30; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x1800583f8  jmp     short loc_1800583A0
0x1800583fa  test    rdi, rdi
0x1800583fd  jz      short loc_180058404
0x1800583ff  mov     [rdi], rbx
0x180058402  xor     ebx, ebx
0x180058404  mov     [rbp+3Fh+var_60], 1
0x18005840b  test    rbx, rbx
0x18005840e  jz      short loc_180058418
0x180058410  mov     rcx, rbx; lpMem
0x180058413  call    SxsDestroyAssemblyIdentity
0x180058418  mov     ebx, [rbp+3Fh+var_60]
0x18005841b  lea     rcx, [rbp+3Fh+var_58]; this
0x18005841f  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180058424  mov     eax, ebx
0x180058426  mov     rcx, [rbp+3Fh+var_28]
0x18005842a  xor     rcx, rsp; StackCookie
0x18005842d  call    __security_check_cookie
0x180058432  mov     rbx, [rsp+0B0h+arg_0]
0x18005843a  add     rsp, 90h
0x180058441  pop     r15
0x180058443  pop     r14
0x180058445  pop     rdi
0x180058446  pop     rsi
0x180058447  pop     rbp
0x180058448  retn
```
