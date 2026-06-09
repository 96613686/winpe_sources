# SxspAddManifestToActCtxGenCtx(_ACTCTXGENCTX *,CProbedAssemblyInformation &,_ASSEMBLY * *)

- ea: `0x18003f060`
- end: `0x18003f3a1`
- name: `?SxspAddManifestToActCtxGenCtx@@YAHPEAU_ACTCTXGENCTX@@AEAVCProbedAssemblyInformation@@PEAPEAU_ASSEMBLY@@@Z`
- size: `833`
- prototype: `int(struct _ACTCTXGENCTX *, struct CProbedAssemblyInformation *, struct _ASSEMBLY **)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callers

- `0x180021150`
- `0x18004029c`

## callees

- `0x180005d30`
- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x1800176fc`
- `0x180017760`
- `0x18001c270`
- `0x180034328`
- `0x18003eb88`
- `0x18003f060`
- `0x18003f3a8`
- `0x18003f5f4`
- `0x180042a94`
- `0x180058904`
- `0x18005d2b0`
- `0x18005d2e4`
- `0x18005d38c`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f0f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f10f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f19c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f2de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f34f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f0f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f10f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f149`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f19c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f2de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f34f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f2bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f2bb`

## string_xrefs

- `0x18003f1f6`: `SXS.DLL: Failing to add new manifest %S to activation context because it conflicts with existing %S\n`

## pseudocode

```c
__int64 __fastcall SxspAddManifestToActCtxGenCtx(struct _ACTCTXGENCTX *a1, wchar_t **a2, struct _ASSEMBLY **a3)
{
  const char *v6; // rcx
  _ASSEMBLY *v7; // rbx
  char **v8; // rcx
  wchar_t *v9; // rsi
  wchar_t *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r9
  _ASSEMBLY *v15; // rax
  const char *v16; // rcx
  unsigned int v17; // ebx
  struct _UNICODE_STRING *v19; // [rsp+20h] [rbp-59h]
  _ASSEMBLY *v20; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING v21; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING v22; // [rsp+58h] [rbp-21h] BYREF
  int v23; // [rsp+68h] [rbp-11h] BYREF
  int v24; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+78h] [rbp-1h]
  __int64 *v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+88h] [rbp+Fh]
  int v28; // [rsp+90h] [rbp+17h]
  int *v29; // [rsp+98h] [rbp+1Fh]

  v24 = 1;
  v26 = &qword_180070E90;
  v27 = 544438355;
  v29 = &v23;
  v23 = 0;
  v25 = 0;
  v28 = 854;
  CFrame::BaseEnter((CFrame *)&v24);
  v20 = 0;
  *(_QWORD *)&v22.Length = 0;
  *(_QWORD *)&v21.Length = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 )
  {
    v28 = 862;
    FusionpTraceParameterCheck(v6);
    SetLastError(0x57u);
    *v29 = 0;
    goto LABEL_32;
  }
  SetLastError(0);
  if ( !CAssemblyReference::GetAssemblyName(
          (CAssemblyReference *)a2,
          (const unsigned __int16 **)&v22,
          (unsigned __int64 *)&v21.Length) )
  {
    *v29 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C20);
    goto LABEL_32;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspFindAssemblyByName(
                        a1,
                        *(const unsigned __int16 **)&v22.Length,
                        *(unsigned __int64 *)&v21.Length,
                        &v20) )
  {
    *v29 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C00);
    v7 = v20;
    goto LABEL_30;
  }
  v7 = v20;
  if ( v20 )
  {
    LODWORD(v20) = 0;
    SetLastError(0);
    if ( !(unsigned int)SxsAreAssemblyIdentitiesEqual(1, *((_QWORD *)v7 + 4), *a2, &v20) )
    {
      v8 = off_180077BE0;
LABEL_12:
      *v29 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
      goto LABEL_30;
    }
    if ( !(_DWORD)v20 )
    {
      v9 = a2[4];
      v10 = (wchar_t *)*((_QWORD *)v7 + 8);
      _ASSEMBLY::Release(v7);
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: Failing to add new manifest %S to activation context because it conflicts with existing %S\n",
        v9,
        v10);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      v22.Buffer = v10;
      v22.Length = 2 * v12;
      v22.MaximumLength = 2 * v12;
      do
        ++v11;
      while ( v9[v11] );
      v13 = (const unsigned __int16 *)*((_QWORD *)a1 + 164);
      v21.Buffer = v9;
      v21.Length = 2 * v11;
      v21.MaximumLength = 2 * v11;
      FusionpLogActCtxGenError(0xC101004E, v13, &v21, &v22, &g_strEmptyUnicodeString);
      TraceActCtxGenEvents(*((_DWORD *)a1 + 326), v9, v10, v14, &v19->Length, 0x118u, 4u, 0x69u);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v24, 0x36B8u);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180077BC0);
      goto LABEL_32;
    }
    goto LABEL_25;
  }
  v15 = (_ASSEMBLY *)HeapAlloc(g_hHeap, 0, 0x370u);
  if ( v15 )
  {
    v7 = _ASSEMBLY::_ASSEMBLY(v15);
    if ( v7 )
    {
      SetLastError(0);
      if ( !SxspInitAssembly(v7, (struct CProbedAssemblyInformation *)a2) )
      {
        v8 = off_180077BA0;
        goto LABEL_12;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspAddAssemblyToActivationContextGenerationContext(a1, v7) )
      {
        v8 = off_180077B80;
        goto LABEL_12;
      }
LABEL_25:
      if ( a3 )
      {
        *a3 = v7;
        v7 = 0;
      }
      v23 = 1;
      goto LABEL_30;
    }
  }
  else
  {
    v7 = 0;
  }
  FusionpTraceAllocFailure(v16);
  SetLastError(0xEu);
  *v29 = 0;
LABEL_30:
  if ( v7 )
    _ASSEMBLY::Release(v7);
LABEL_32:
  v17 = v23;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v24);
  return v17;
}

```

## disassembly

```asm
0x18003f060  mov     [rsp-8+arg_18], rbx
0x18003f065  push    rbp
0x18003f066  push    rsi
0x18003f067  push    rdi
0x18003f068  push    r14
0x18003f06a  push    r15
0x18003f06c  lea     rbp, [rsp-37h]
0x18003f071  sub     rsp, 0B0h
0x18003f078  mov     rax, cs:__security_cookie
0x18003f07f  xor     rax, rsp
0x18003f082  mov     [rbp+57h+var_30], rax
0x18003f086  lea     rax, qword_180070E90
0x18003f08d  mov     [rbp+57h+var_60], 1
0x18003f094  mov     [rbp+57h+var_50], rax
0x18003f098  mov     r14, rcx
0x18003f09b  lea     rax, [rbp+57h+var_68]
0x18003f09f  mov     [rbp+57h+var_48], 20737853h
0x18003f0a7  xor     r15d, r15d
0x18003f0aa  mov     [rbp+57h+var_38], rax
0x18003f0ae  lea     rcx, [rbp+57h+var_60]; this
0x18003f0b2  mov     [rbp+57h+var_68], r15d
0x18003f0b6  mov     rdi, r8
0x18003f0b9  mov     [rbp+57h+var_58], r15
0x18003f0bd  mov     rsi, rdx
0x18003f0c0  mov     [rbp+57h+var_40], 356h
0x18003f0c7  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003f0cc  mov     [rbp+57h+var_90], r15
0x18003f0d0  mov     qword ptr [rbp+57h+var_78.Length], r15
0x18003f0d4  mov     qword ptr [rbp+57h+var_88.Length], r15
0x18003f0d8  test    rdi, rdi
0x18003f0db  jz      short loc_18003F0E0
0x18003f0dd  mov     [rdi], r15
0x18003f0e0  test    r14, r14
0x18003f0e3  jnz     short loc_18003F10D
0x18003f0e5  mov     [rbp+57h+var_40], 35Eh
0x18003f0ec  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18003f0f1  lea     ecx, [r14+57h]; dwErrCode
0x18003f0f5  call    cs:__imp_SetLastError
0x18003f0fc  nop     dword ptr [rax+rax+00h]
0x18003f101  mov     rax, [rbp+57h+var_38]
0x18003f105  mov     [rax], r15d
0x18003f108  jmp     loc_18003F36F
0x18003f10d  xor     ecx, ecx; dwErrCode
0x18003f10f  call    cs:__imp_SetLastError
0x18003f116  nop     dword ptr [rax+rax+00h]
0x18003f11b  lea     r8, [rbp+57h+var_88]; unsigned __int64 *
0x18003f11f  mov     rcx, rsi; this
0x18003f122  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18003f126  call    ?GetAssemblyName@CAssemblyReference@@QEBAHPEAPEBGPEA_K@Z; CAssemblyReference::GetAssemblyName(ushort const * *,unsigned __int64 *)
0x18003f12b  test    eax, eax
0x18003f12d  jnz     short loc_18003F147
0x18003f12f  mov     rax, [rbp+57h+var_38]
0x18003f133  lea     rcx, off_180077C20; struct _CALL_SITE_INFO *
0x18003f13a  mov     [rax], r15d
0x18003f13d  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003f142  jmp     loc_18003F36F
0x18003f147  xor     ecx, ecx; dwErrCode
0x18003f149  call    cs:__imp_SetLastError
0x18003f150  nop     dword ptr [rax+rax+00h]
0x18003f155  mov     r8, qword ptr [rbp+57h+var_88.Length]; unsigned __int64
0x18003f159  lea     r9, [rbp+57h+var_90]; struct _ASSEMBLY **
0x18003f15d  mov     rdx, qword ptr [rbp+57h+var_78.Length]; unsigned __int16 *
0x18003f161  mov     rcx, r14; struct _ACTCTXGENCTX *
0x18003f164  call    ?SxspFindAssemblyByName@@YAHPEAU_ACTCTXGENCTX@@PEBG_KPEAPEAU_ASSEMBLY@@@Z; SxspFindAssemblyByName(_ACTCTXGENCTX *,ushort const *,unsigned __int64,_ASSEMBLY * *)
0x18003f169  test    eax, eax
0x18003f16b  jnz     short loc_18003F189
0x18003f16d  mov     rax, [rbp+57h+var_38]
0x18003f171  lea     rcx, off_180077C00; struct _CALL_SITE_INFO *
0x18003f178  mov     [rax], r15d
0x18003f17b  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003f180  mov     rbx, [rbp+57h+var_90]
0x18003f184  jmp     loc_18003F362
0x18003f189  mov     rbx, [rbp+57h+var_90]
0x18003f18d  test    rbx, rbx
0x18003f190  jz      loc_18003F2AC
0x18003f196  xor     ecx, ecx; dwErrCode
0x18003f198  mov     dword ptr [rbp+57h+var_90], r15d
0x18003f19c  call    cs:__imp_SetLastError
0x18003f1a3  nop     dword ptr [rax+rax+00h]
0x18003f1a8  mov     r8, [rsi]
0x18003f1ab  lea     r9, [rbp+57h+var_90]
0x18003f1af  mov     rdx, [rbx+20h]
0x18003f1b3  mov     ecx, 1
0x18003f1b8  call    SxsAreAssemblyIdentitiesEqual
0x18003f1bd  test    eax, eax
0x18003f1bf  jnz     short loc_18003F1D9
0x18003f1c1  lea     rcx, off_180077BE0; struct _CALL_SITE_INFO *
0x18003f1c8  mov     rax, [rbp+57h+var_38]
0x18003f1cc  mov     [rax], r15d
0x18003f1cf  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18003f1d4  jmp     loc_18003F362
0x18003f1d9  cmp     dword ptr [rbp+57h+var_90], r15d
0x18003f1dd  jnz     loc_18003F32E
0x18003f1e3  mov     rsi, [rsi+20h]
0x18003f1e7  mov     rcx, rbx; this
0x18003f1ea  mov     rdi, [rbx+40h]
0x18003f1ee  call    ?Release@_ASSEMBLY@@QEAAXXZ; _ASSEMBLY::Release(void)
0x18003f1f3  mov     r9, rdi
0x18003f1f6  lea     rdx, aSxsDllFailingT; "SXS.DLL: Failing to add new manifest %S"...
0x18003f1fd  mov     r8, rsi
0x18003f200  mov     ecx, 0C0000000h; unsigned int
0x18003f205  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18003f20a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003f20e  mov     rax, rcx
0x18003f211  inc     rax
0x18003f214  cmp     [rdi+rax*2], r15w
0x18003f219  jnz     short loc_18003F211
0x18003f21b  add     ax, ax
0x18003f21e  mov     [rbp+57h+var_78.Buffer], rdi
0x18003f222  mov     [rbp+57h+var_78.Length], ax
0x18003f226  mov     [rbp+57h+var_78.MaximumLength], ax
0x18003f22a  inc     rcx
0x18003f22d  cmp     [rsi+rcx*2], r15w
0x18003f232  jnz     short loc_18003F22A
0x18003f234  mov     rdx, [r14+520h]; unsigned __int16 *
0x18003f23b  lea     rax, ?g_strEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const g_strEmptyUnicodeString
0x18003f242  add     cx, cx
0x18003f245  mov     [rbp+57h+var_88.Buffer], rsi
0x18003f249  mov     [rbp+57h+var_88.Length], cx
0x18003f24d  lea     r9, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x18003f251  mov     [rbp+57h+var_88.MaximumLength], cx
0x18003f255  lea     r8, [rbp+57h+var_88]; struct _UNICODE_STRING *
0x18003f259  mov     ecx, 0C101004Eh; unsigned int
0x18003f25e  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x18003f263  call    ?FusionpLogActCtxGenError@@YAJKPEBGPEBU_UNICODE_STRING@@111@Z; FusionpLogActCtxGenError(ulong,ushort const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18003f268  mov     ecx, [r14+518h]; int
0x18003f26f  mov     r8, rdi; unsigned __int16 *
0x18003f272  mov     [rsp+0D0h+var_98], 69h ; 'i'; unsigned __int16
0x18003f279  mov     rdx, rsi; unsigned __int16 *
0x18003f27c  mov     [rsp+0D0h+var_A0], 4; char
0x18003f281  mov     [rsp+0D0h+var_A8], 118h; unsigned __int16
0x18003f288  call    ?TraceActCtxGenEvents@@YAKJPEBG000GEG@Z; TraceActCtxGenEvents(long,ushort const *,ushort const *,ushort const *,ushort const *,ushort,uchar,ushort)
0x18003f28d  mov     edx, 36B8h; unsigned int
0x18003f292  lea     rcx, [rbp+57h+var_60]; this
0x18003f296  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18003f29b  lea     rcx, off_180077BC0; struct _CALL_SITE_INFO *
0x18003f2a2  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18003f2a7  jmp     loc_18003F36F
0x18003f2ac  mov     rcx, cs:g_hHeap; hHeap
0x18003f2b3  xor     edx, edx; dwFlags
0x18003f2b5  mov     r8d, 370h; dwBytes
0x18003f2bb  call    cs:__imp_HeapAlloc
0x18003f2c2  nop     dword ptr [rax+rax+00h]
0x18003f2c7  test    rax, rax
0x18003f2ca  jz      short loc_18003F342
0x18003f2cc  mov     rcx, rax; this
0x18003f2cf  call    ??0_ASSEMBLY@@QEAA@XZ; _ASSEMBLY::_ASSEMBLY(void)
0x18003f2d4  mov     rbx, rax
0x18003f2d7  test    rax, rax
0x18003f2da  jz      short loc_18003F345
0x18003f2dc  xor     ecx, ecx; dwErrCode
0x18003f2de  call    cs:__imp_SetLastError
0x18003f2e5  nop     dword ptr [rax+rax+00h]
0x18003f2ea  mov     rdx, rsi; struct CProbedAssemblyInformation *
0x18003f2ed  mov     rcx, rbx; struct _ASSEMBLY *
0x18003f2f0  call    ?SxspInitAssembly@@YAHPEAU_ASSEMBLY@@AEAVCProbedAssemblyInformation@@@Z; SxspInitAssembly(_ASSEMBLY *,CProbedAssemblyInformation &)
0x18003f2f5  test    eax, eax
0x18003f2f7  jnz     short loc_18003F305
0x18003f2f9  lea     rcx, off_180077BA0; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18003f300  jmp     loc_18003F1C8
0x18003f305  xor     ecx, ecx; dwErrCode
0x18003f307  call    cs:__imp_SetLastError
0x18003f30e  nop     dword ptr [rax+rax+00h]
0x18003f313  mov     rdx, rbx; struct _ASSEMBLY *
0x18003f316  mov     rcx, r14; struct _ACTCTXGENCTX *
0x18003f319  call    ?SxspAddAssemblyToActivationContextGenerationContext@@YAHPEAU_ACTCTXGENCTX@@PEAU_ASSEMBLY@@@Z; SxspAddAssemblyToActivationContextGenerationContext(_ACTCTXGENCTX *,_ASSEMBLY *)
0x18003f31e  test    eax, eax
0x18003f320  jnz     short loc_18003F32E
0x18003f322  lea     rcx, off_180077B80; "clientcore\\base\\win32\\fusion\\sxs\\a"...
0x18003f329  jmp     loc_18003F1C8
0x18003f32e  test    rdi, rdi
0x18003f331  jz      short loc_18003F339
0x18003f333  mov     [rdi], rbx
0x18003f336  mov     rbx, r15
0x18003f339  mov     [rbp+57h+var_68], 1
0x18003f340  jmp     short loc_18003F362
0x18003f342  mov     rbx, r15
0x18003f345  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x18003f34a  mov     ecx, 0Eh; dwErrCode
0x18003f34f  call    cs:__imp_SetLastError
0x18003f356  nop     dword ptr [rax+rax+00h]
0x18003f35b  mov     rax, [rbp+57h+var_38]
0x18003f35f  mov     [rax], r15d
0x18003f362  test    rbx, rbx
0x18003f365  jz      short loc_18003F36F
0x18003f367  mov     rcx, rbx; this
0x18003f36a  call    ?Release@_ASSEMBLY@@QEAAXXZ; _ASSEMBLY::Release(void)
0x18003f36f  mov     ebx, [rbp+57h+var_68]
0x18003f372  lea     rcx, [rbp+57h+var_60]; this
0x18003f376  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18003f37b  mov     eax, ebx
0x18003f37d  mov     rcx, [rbp+57h+var_30]
0x18003f381  xor     rcx, rsp; StackCookie
0x18003f384  call    __security_check_cookie
0x18003f389  mov     rbx, [rsp+0D0h+arg_18]
0x18003f391  add     rsp, 0B0h
0x18003f398  pop     r15
0x18003f39a  pop     r14
0x18003f39c  pop     rdi
0x18003f39d  pop     rsi
0x18003f39e  pop     rbp
0x18003f39f  retn
```
