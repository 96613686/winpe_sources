# SxspAddRootManifestToActCtxGenCtx(_ACTCTXGENCTX *,_SXS_GENERATE_ACTIVATION_CONTEXT_PARAMETERS const *,_ASSEMBLY_IDENTITY const *)

- ea: `0x18004029c`
- end: `0x180040636`
- name: `?SxspAddRootManifestToActCtxGenCtx@@YAHPEAU_ACTCTXGENCTX@@PEBU_SXS_GENERATE_ACTIVATION_CONTEXT_PARAMETERS@@PEBU_ASSEMBLY_IDENTITY@@@Z`
- size: `922`
- prototype: `__int64 __fastcall(struct _ACTCTXGENCTX *, const struct _SXS_GENERATE_ACTIVATION_CONTEXT_PARAMETERS *, const struct _ASSEMBLY_IDENTITY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18005ae60`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180016798`
- `0x18001c270`
- `0x180020e20`
- `0x18003ef00`
- `0x18003f060`
- `0x18004029c`
- `0x18004063c`
- `0x180040760`
- `0x180040880`
- `0x1800408d4`
- `0x18005d2b0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004044b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040483`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040540`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004055e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004044b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040483`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800404fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040540`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004055e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405db`

## pseudocode

```c
__int64 __fastcall SxspAddRootManifestToActCtxGenCtx(
        struct _ACTCTXGENCTX *a1,
        const struct _SXS_GENERATE_ACTIVATION_CONTEXT_PARAMETERS *a2,
        const struct _ASSEMBLY_IDENTITY *a3)
{
  const char *v6; // rcx
  _WORD *v7; // rax
  _WORD *v8; // rax
  _WORD *v9; // rax
  char **v10; // rcx
  unsigned int v11; // edx
  const unsigned __int16 *v12; // r8
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r9
  unsigned int v15; // edx
  const unsigned __int16 *v16; // r8
  unsigned int v17; // ebx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 *v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+40h] [rbp-C0h]
  unsigned int *v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v26[73]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[8]; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v28; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v29[8]; // [rsp+380h] [rbp+280h] BYREF
  int v30; // [rsp+388h] [rbp+288h]

  v19 = 1;
  v21 = &qword_180070F10;
  v22 = 544438355;
  v24 = (unsigned int *)&v25;
  v25 = 0;
  v20 = 0;
  v23 = 1008;
  CFrame::BaseEnter((CFrame *)&v19);
  CProbedAssemblyInformation::CProbedAssemblyInformation((CProbedAssemblyInformation *)v26);
  if ( a2 )
  {
    if ( !a1 )
    {
      v23 = 1012;
      goto LABEL_3;
    }
    v7 = (_WORD *)*((_QWORD *)a2 + 2);
    LOWORD(v6) = 63;
    if ( v7 && (*v7 == 92 || *v7 == 47) )
    {
      if ( v7[1] == 63 && v7[2] == 63 && (v7[3] == 92 || v7[3] == 47) )
      {
        v23 = 1016;
        goto LABEL_3;
      }
      if ( (*v7 == 92 || *v7 == 47) && v7[1] == 63 && v7[2] == 63 && (v7[3] == 92 || v7[3] == 47) )
      {
        v23 = 1017;
        goto LABEL_3;
      }
    }
    v8 = (_WORD *)*((_QWORD *)a2 + 5);
    if ( v8 && (*v8 == 92 || *v8 == 47) && v8[1] == 63 && v8[2] == 63 && (v8[3] == 92 || v8[3] == 47) )
    {
      v23 = 1018;
      goto LABEL_3;
    }
    v9 = (_WORD *)*((_QWORD *)a2 + 8);
    if ( v9 && (*v9 == 92 || *v9 == 47) && v9[1] == 63 && v9[2] == 63 && (v9[3] == 92 || v9[3] == 47) )
    {
      v23 = 1019;
      goto LABEL_3;
    }
    SetLastError(0);
    if ( (unsigned int)CProbedAssemblyInformation::Initialize((CProbedAssemblyInformation *)v26, a1) )
    {
      SetLastError(0);
      v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
      v13 = -1;
      if ( v12 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
      }
      else
      {
        v14 = 0;
      }
      if ( (unsigned int)CProbedAssemblyInformation::SetManifestPath((CProbedAssemblyInformation *)v26, v11, v12, v14) )
      {
        SetLastError(0);
        CSmartRef<IStream>::operator=(v27, *((_QWORD *)a2 + 4));
        SetLastError(0);
        v28 = 3;
        SetLastError(0);
        v16 = (const unsigned __int16 *)*((_QWORD *)a2 + 8);
        if ( v16 )
        {
          do
            ++v13;
          while ( v16[v13] );
        }
        else
        {
          v13 = 0;
        }
        if ( (unsigned int)CProbedAssemblyInformation::SetPolicyPath((CProbedAssemblyInformation *)v26, v15, v16, v13) )
        {
          SetLastError(0);
          CSmartRef<IStream>::operator=(v29, *((_QWORD *)a2 + 7));
          SetLastError(0);
          v30 = 3;
          SetLastError(0);
          if ( a3 )
          {
            if ( !(unsigned int)CProbedAssemblyInformation::SetProbedIdentity((CProbedAssemblyInformation *)v26, a3) )
            {
              v10 = off_180077AE0;
              goto LABEL_39;
            }
          }
          else
          {
            v28 |= 0x10u;
          }
          SetLastError(0);
          if ( (unsigned int)SxspAddManifestToActCtxGenCtx(a1, v26, 0) )
          {
            SetLastError(0);
            *v24 = 1;
            goto LABEL_60;
          }
          v10 = off_180077AC0;
          goto LABEL_39;
        }
        v10 = off_180077B00;
      }
      else
      {
        v10 = off_180070F30;
      }
    }
    else
    {
      v10 = off_180077B20;
    }
LABEL_39:
    *v24 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v10);
    goto LABEL_60;
  }
  v23 = 1011;
LABEL_3:
  FusionpTraceParameterCheck(v6);
  SetLastError(0x57u);
  *v24 = 0;
LABEL_60:
  v17 = *v24;
  CProbedAssemblyInformation::~CProbedAssemblyInformation((CProbedAssemblyInformation *)v26);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v19);
  return v17;
}

```

## disassembly

```asm
0x18004029c  mov     [rsp-8+arg_18], rbx
0x1800402a1  push    rbp
0x1800402a2  push    rsi
0x1800402a3  push    rdi
0x1800402a4  push    r14
0x1800402a6  push    r15
0x1800402a8  lea     rbp, [rsp-2B0h]
0x1800402b0  sub     rsp, 3B0h
0x1800402b7  mov     rax, cs:__security_cookie
0x1800402be  xor     rax, rsp
0x1800402c1  mov     [rbp+2D0h+var_30], rax
0x1800402c8  lea     rax, qword_180070F10
0x1800402cf  mov     [rsp+3D0h+var_3B0], 1
0x1800402d7  mov     [rsp+3D0h+var_3A0], rax
0x1800402dc  mov     rsi, rcx
0x1800402df  lea     rax, [rsp+3D0h+var_380]
0x1800402e4  mov     [rsp+3D0h+var_398], 20737853h
0x1800402ed  xor     r15d, r15d
0x1800402f0  mov     [rsp+3D0h+var_388], rax
0x1800402f5  lea     rcx, [rsp+3D0h+var_3B0]; this
0x1800402fa  mov     [rsp+3D0h+var_380], r15d
0x1800402ff  mov     r14, r8
0x180040302  mov     [rsp+3D0h+var_3A8], r15
0x180040307  mov     rdi, rdx
0x18004030a  mov     [rsp+3D0h+var_390], 3F0h
0x180040312  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180040317  lea     rcx, [rsp+3D0h+var_370]; this
0x18004031c  call    ??0CProbedAssemblyInformation@@QEAA@XZ; CProbedAssemblyInformation::CProbedAssemblyInformation(void)
0x180040321  test    rdi, rdi
0x180040324  jnz     short loc_180040351
0x180040326  mov     [rsp+3D0h+var_390], 3F3h
0x18004032e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180040333  mov     ecx, 57h ; 'W'; dwErrCode
0x180040338  call    cs:__imp_SetLastError
0x18004033f  nop     dword ptr [rax+rax+00h]
0x180040344  mov     rax, [rsp+3D0h+var_388]
0x180040349  mov     [rax], r15d
0x18004034c  jmp     loc_1800405F2
0x180040351  test    rsi, rsi
0x180040354  jnz     short loc_180040360
0x180040356  mov     [rsp+3D0h+var_390], 3F4h
0x18004035e  jmp     short loc_18004032E
0x180040360  mov     rax, [rdi+10h]
0x180040364  mov     r8w, 5Ch ; '\'
0x180040369  mov     dx, 2Fh ; '/'
0x18004036d  mov     cx, 3Fh ; '?'
0x180040371  test    rax, rax
0x180040374  jz      short loc_1800403D5
0x180040376  cmp     [rax], r8w
0x18004037a  jz      short loc_180040381
0x18004037c  cmp     [rax], dx
0x18004037f  jnz     short loc_1800403D5
0x180040381  cmp     [rax+2], cx
0x180040385  jnz     short loc_1800403A4
0x180040387  cmp     [rax+4], cx
0x18004038b  jnz     short loc_1800403A4
0x18004038d  cmp     [rax+6], r8w
0x180040392  jz      short loc_18004039A
0x180040394  cmp     [rax+6], dx
0x180040398  jnz     short loc_1800403A4
0x18004039a  mov     [rsp+3D0h+var_390], 3F8h
0x1800403a2  jmp     short loc_18004032E
0x1800403a4  cmp     [rax], r8w
0x1800403a8  jz      short loc_1800403AF
0x1800403aa  cmp     [rax], dx
0x1800403ad  jnz     short loc_1800403D5
0x1800403af  cmp     [rax+2], cx
0x1800403b3  jnz     short loc_1800403D5
0x1800403b5  cmp     [rax+4], cx
0x1800403b9  jnz     short loc_1800403D5
0x1800403bb  cmp     [rax+6], r8w
0x1800403c0  jz      short loc_1800403C8
0x1800403c2  cmp     [rax+6], dx
0x1800403c6  jnz     short loc_1800403D5
0x1800403c8  mov     [rsp+3D0h+var_390], 3F9h
0x1800403d0  jmp     loc_18004032E
0x1800403d5  mov     rax, [rdi+28h]
0x1800403d9  test    rax, rax
0x1800403dc  jz      short loc_18004040F
0x1800403de  cmp     [rax], r8w
0x1800403e2  jz      short loc_1800403E9
0x1800403e4  cmp     [rax], dx
0x1800403e7  jnz     short loc_18004040F
0x1800403e9  cmp     [rax+2], cx
0x1800403ed  jnz     short loc_18004040F
0x1800403ef  cmp     [rax+4], cx
0x1800403f3  jnz     short loc_18004040F
0x1800403f5  cmp     [rax+6], r8w
0x1800403fa  jz      short loc_180040402
0x1800403fc  cmp     [rax+6], dx
0x180040400  jnz     short loc_18004040F
0x180040402  mov     [rsp+3D0h+var_390], 3FAh
0x18004040a  jmp     loc_18004032E
0x18004040f  mov     rax, [rdi+40h]
0x180040413  test    rax, rax
0x180040416  jz      short loc_180040449
0x180040418  cmp     [rax], r8w
0x18004041c  jz      short loc_180040423
0x18004041e  cmp     [rax], dx
0x180040421  jnz     short loc_180040449
0x180040423  cmp     [rax+2], cx
0x180040427  jnz     short loc_180040449
0x180040429  cmp     [rax+4], cx
0x18004042d  jnz     short loc_180040449
0x18004042f  cmp     [rax+6], r8w
0x180040434  jz      short loc_18004043C
0x180040436  cmp     [rax+6], dx
0x18004043a  jnz     short loc_180040449
0x18004043c  mov     [rsp+3D0h+var_390], 3FBh
0x180040444  jmp     loc_18004032E
0x180040449  xor     ecx, ecx; dwErrCode
0x18004044b  call    cs:__imp_SetLastError
0x180040452  nop     dword ptr [rax+rax+00h]
0x180040457  mov     rdx, rsi; struct _ACTCTXGENCTX *
0x18004045a  lea     rcx, [rsp+3D0h+var_370]; this
0x18004045f  call    ?Initialize@CProbedAssemblyInformation@@QEAAHPEBU_ACTCTXGENCTX@@@Z; CProbedAssemblyInformation::Initialize(_ACTCTXGENCTX const *)
0x180040464  test    eax, eax
0x180040466  jnz     short loc_180040481
0x180040468  lea     rcx, off_180077B20; struct _CALL_SITE_INFO *
0x18004046f  mov     rax, [rsp+3D0h+var_388]
0x180040474  mov     [rax], r15d
0x180040477  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004047c  jmp     loc_1800405F2
0x180040481  xor     ecx, ecx; dwErrCode
0x180040483  call    cs:__imp_SetLastError
0x18004048a  nop     dword ptr [rax+rax+00h]
0x18004048f  mov     r8, [rdi+28h]; unsigned __int16 *
0x180040493  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040497  test    r8, r8
0x18004049a  jz      short loc_1800404AB
0x18004049c  mov     r9, rbx
0x18004049f  inc     r9
0x1800404a2  cmp     [r8+r9*2], r15w
0x1800404a7  jnz     short loc_18004049F
0x1800404a9  jmp     short loc_1800404AE
0x1800404ab  mov     r9, r15; unsigned __int64
0x1800404ae  lea     rcx, [rsp+3D0h+var_370]; this
0x1800404b3  call    ?SetManifestPath@CProbedAssemblyInformation@@QEAAHKPEBG_K@Z; CProbedAssemblyInformation::SetManifestPath(ulong,ushort const *,unsigned __int64)
0x1800404b8  test    eax, eax
0x1800404ba  jnz     short loc_1800404C5
0x1800404bc  lea     rcx, off_180070F30; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x1800404c3  jmp     short loc_18004046F
0x1800404c5  xor     ecx, ecx; dwErrCode
0x1800404c7  call    cs:__imp_SetLastError
0x1800404ce  nop     dword ptr [rax+rax+00h]
0x1800404d3  mov     rdx, [rdi+20h]
0x1800404d7  lea     rcx, [rbp+2D0h+var_128]
0x1800404de  call    ??4?$CSmartRef@UIStream@@@@QEAAAEAV0@PEAUIStream@@@Z; CSmartRef<IStream>::operator=(IStream *)
0x1800404e3  xor     ecx, ecx; dwErrCode
0x1800404e5  call    cs:__imp_SetLastError
0x1800404ec  nop     dword ptr [rax+rax+00h]
0x1800404f1  xor     ecx, ecx; dwErrCode
0x1800404f3  mov     [rbp+2D0h+var_120], 3
0x1800404fd  call    cs:__imp_SetLastError
0x180040504  nop     dword ptr [rax+rax+00h]
0x180040509  mov     r8, [rdi+40h]; unsigned __int16 *
0x18004050d  test    r8, r8
0x180040510  jz      short loc_18004051E
0x180040512  inc     rbx
0x180040515  cmp     [r8+rbx*2], r15w
0x18004051a  jnz     short loc_180040512
0x18004051c  jmp     short loc_180040521
0x18004051e  mov     rbx, r15
0x180040521  mov     r9, rbx; unsigned __int64
0x180040524  lea     rcx, [rsp+3D0h+var_370]; this
0x180040529  call    ?SetPolicyPath@CProbedAssemblyInformation@@QEAAHKPEBG_K@Z; CProbedAssemblyInformation::SetPolicyPath(ulong,ushort const *,unsigned __int64)
0x18004052e  test    eax, eax
0x180040530  jnz     short loc_18004053E
0x180040532  lea     rcx, off_180077B00; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x180040539  jmp     loc_18004046F
0x18004053e  xor     ecx, ecx; dwErrCode
0x180040540  call    cs:__imp_SetLastError
0x180040547  nop     dword ptr [rax+rax+00h]
0x18004054c  mov     rdx, [rdi+38h]
0x180040550  lea     rcx, [rbp+2D0h+var_50]
0x180040557  call    ??4?$CSmartRef@UIStream@@@@QEAAAEAV0@PEAUIStream@@@Z; CSmartRef<IStream>::operator=(IStream *)
0x18004055c  xor     ecx, ecx; dwErrCode
0x18004055e  call    cs:__imp_SetLastError
0x180040565  nop     dword ptr [rax+rax+00h]
0x18004056a  xor     ecx, ecx; dwErrCode
0x18004056c  mov     [rbp+2D0h+var_48], 3
0x180040576  call    cs:__imp_SetLastError
0x18004057d  nop     dword ptr [rax+rax+00h]
0x180040582  test    r14, r14
0x180040585  jz      short loc_1800405A4
0x180040587  mov     rdx, r14; struct _ASSEMBLY_IDENTITY *
0x18004058a  lea     rcx, [rsp+3D0h+var_370]; this
0x18004058f  call    ?SetProbedIdentity@CProbedAssemblyInformation@@QEAAHPEBU_ASSEMBLY_IDENTITY@@@Z; CProbedAssemblyInformation::SetProbedIdentity(_ASSEMBLY_IDENTITY const *)
0x180040594  test    eax, eax
0x180040596  jnz     short loc_1800405AB
0x180040598  lea     rcx, off_180077AE0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18004059f  jmp     loc_18004046F
0x1800405a4  or      [rbp+2D0h+var_120], 10h
0x1800405ab  xor     ecx, ecx; dwErrCode
0x1800405ad  call    cs:__imp_SetLastError
0x1800405b4  nop     dword ptr [rax+rax+00h]
0x1800405b9  xor     r8d, r8d; struct _ASSEMBLY **
0x1800405bc  lea     rdx, [rsp+3D0h+var_370]; struct CProbedAssemblyInformation *
0x1800405c1  mov     rcx, rsi; struct _ACTCTXGENCTX *
0x1800405c4  call    ?SxspAddManifestToActCtxGenCtx@@YAHPEAU_ACTCTXGENCTX@@AEAVCProbedAssemblyInformation@@PEAPEAU_ASSEMBLY@@@Z; SxspAddManifestToActCtxGenCtx(_ACTCTXGENCTX *,CProbedAssemblyInformation &,_ASSEMBLY * *)
0x1800405c9  test    eax, eax
0x1800405cb  jnz     short loc_1800405D9
0x1800405cd  lea     rcx, off_180077AC0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x1800405d4  jmp     loc_18004046F
0x1800405d9  xor     ecx, ecx; dwErrCode
0x1800405db  call    cs:__imp_SetLastError
0x1800405e2  nop     dword ptr [rax+rax+00h]
0x1800405e7  mov     rax, [rsp+3D0h+var_388]
0x1800405ec  mov     dword ptr [rax], 1
0x1800405f2  mov     rax, [rsp+3D0h+var_388]
0x1800405f7  lea     rcx, [rsp+3D0h+var_370]; this
0x1800405fc  mov     ebx, [rax]
0x1800405fe  call    ??1CProbedAssemblyInformation@@QEAA@XZ; CProbedAssemblyInformation::~CProbedAssemblyInformation(void)
0x180040603  lea     rcx, [rsp+3D0h+var_3B0]; this
0x180040608  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004060d  mov     eax, ebx
0x18004060f  mov     rcx, [rbp+2D0h+var_30]
0x180040616  xor     rcx, rsp; StackCookie
0x180040619  call    __security_check_cookie
0x18004061e  mov     rbx, [rsp+3D0h+arg_18]
0x180040626  add     rsp, 3B0h
0x18004062d  pop     r15
0x18004062f  pop     r14
0x180040631  pop     rdi
0x180040632  pop     rsi
0x180040633  pop     rbp
0x180040634  retn
```
