# CProbedAssemblyInformation::ValidateManifestPath(_WIN32_FILE_ATTRIBUTE_DATA const &,int)

- ea: `0x180053760`
- end: `0x1800539d0`
- name: `?ValidateManifestPath@CProbedAssemblyInformation@@QEAAHAEBU_WIN32_FILE_ATTRIBUTE_DATA@@H@Z`
- size: `624`
- prototype: `__int64 __fastcall(CProbedAssemblyInformation *__hidden this, const struct _WIN32_FILE_ATTRIBUTE_DATA *, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000c070`
- `0x180062568`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x180013150`
- `0x18001c270`
- `0x18001d6f0`
- `0x18002b63c`
- `0x18003eb88`
- `0x18004eb78`
- `0x180053760`
- `0x1800539d8`
- `0x180059b14`
- `0x18005d2b0`
- `0x18005d38c`
- `0x1800607ac`
- `0x180060e14`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800537ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005398c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800537ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053916`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005398c`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::ValidateManifestPath(
        CProbedAssemblyInformation *this,
        const struct _WIN32_FILE_ATTRIBUTE_DATA *a2,
        int a3)
{
  const unsigned __int16 *v6; // rcx
  const char *v7; // rcx
  DWORD v8; // ecx
  int v9; // r14d
  __int64 v10; // rdi
  char HasTrailingPathSeparator; // al
  __int64 v12; // rdx
  char v13; // si
  unsigned __int64 PathElement; // r15
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  const unsigned __int16 *v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  char **v20; // rcx
  unsigned int v21; // ebx
  unsigned __int16 *v23; // [rsp+20h] [rbp-59h]
  unsigned __int16 v24[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-35h] BYREF
  int v26; // [rsp+48h] [rbp-31h] BYREF
  int v27; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h]
  __int64 *v29; // [rsp+60h] [rbp-19h]
  __int64 v30; // [rsp+68h] [rbp-11h]
  int v31; // [rsp+70h] [rbp-9h]
  unsigned int *v32; // [rsp+78h] [rbp-1h]

  v30 = 544438355;
  v26 = 0;
  v29 = &qword_1800723B0;
  v28 = 0;
  v31 = 307;
  v27 = 1;
  v32 = (unsigned int *)&v26;
  CFrame::BaseEnter((CFrame *)&v27);
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  *(_DWORD *)v24 = 0;
  if ( !IsNtDosPath(v6) )
  {
    if ( !*(_QWORD *)this )
    {
      v8 = 1359;
      goto LABEL_3;
    }
    if ( !a3 )
      goto LABEL_25;
    v9 = 0;
    v10 = *((_QWORD *)this + 102) + 640LL;
    HasTrailingPathSeparator = CGenericBaseStringBuffer<CUnicodeCharTraits>::HasTrailingPathSeparator(v10);
    LOBYTE(v12) = 1;
    v13 = HasTrailingPathSeparator;
    PathElement = CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutLastPathElement((char *)this + 16, v12);
    if ( *((_QWORD *)this + 102) )
    {
      if ( !v13 )
        CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(v10);
      v15 = *(_QWORD *)(v10 + 32);
      if ( v15 <= PathElement
        && !FusionpCompareStrings(*(WCHAR **)(v10 + 16), v15, *((WCHAR **)this + 4), *(_QWORD *)(v10 + 32), 1u) )
      {
        v9 = 1;
      }
      if ( !v13 )
        CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(v10);
    }
    SetLastError(0);
    if ( v9 )
    {
      v16 = *(_QWORD *)(v10 + 32);
      v17 = *(const unsigned __int16 **)(*((_QWORD *)this + 102) + 656LL);
    }
    else
    {
      v17 = 0;
      v16 = 0;
    }
    v18 = (const unsigned __int16 *)*((_QWORD *)this + 4);
    v25 = 0;
    if ( !(unsigned int)SxspDoesPathCrossUnsafeReparsePoint(v17, v16, v18, PathElement, (int *)v24, &v25, 0) )
    {
      v20 = off_180078808;
LABEL_20:
      *v32 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v20);
      goto LABEL_28;
    }
    if ( !*(_DWORD *)v24 )
    {
LABEL_25:
      if ( (a2->dwFileAttributes & 0x400) == 0 )
        goto LABEL_27;
      SetLastError(0);
      if ( !(unsigned int)SxspIsReparsePointUnsafe(*((LPCWSTR *)this + 4), (int *)v24) )
      {
        v20 = off_1800787E8;
        goto LABEL_20;
      }
      if ( !*(_DWORD *)v24 )
      {
LABEL_27:
        SetLastError(0);
        *v32 = 1;
        goto LABEL_28;
      }
    }
    TraceActCtxGenEvents(
      *(_DWORD *)(*((_QWORD *)this + 102) + 1304LL),
      *((const unsigned __int16 **)this + 4),
      0,
      v19,
      v23,
      0x107u,
      2u,
      0x67u);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v27, 0x36C4u);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_1800787C8);
    goto LABEL_28;
  }
  v31 = 310;
  FusionpTraceParameterCheck(v7);
  v8 = 87;
LABEL_3:
  SetLastError(v8);
  *v32 = 0;
LABEL_28:
  v21 = *v32;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v27);
  return v21;
}

```

## disassembly

```asm
0x180053760  push    rbp
0x180053762  push    rbx
0x180053763  push    rsi
0x180053764  push    rdi
0x180053765  push    r12
0x180053767  push    r13
0x180053769  push    r14
0x18005376b  push    r15
0x18005376d  lea     rbp, [rsp-1Fh]
0x180053772  sub     rsp, 98h
0x180053779  mov     rax, cs:__security_cookie
0x180053780  xor     rax, rsp
0x180053783  mov     [rbp+57h+var_50], rax
0x180053787  xor     r13d, r13d
0x18005378a  mov     [rbp+57h+var_68], 20737853h
0x180053792  lea     rax, qword_1800723B0
0x180053799  mov     [rbp+57h+var_88], r13d
0x18005379d  mov     [rbp+57h+var_70], rax
0x1800537a1  mov     rbx, rcx
0x1800537a4  lea     rax, [rbp+57h+var_88]
0x1800537a8  mov     [rbp+57h+var_78], r13
0x1800537ac  lea     esi, [r13+1]
0x1800537b0  mov     [rbp+57h+var_60], 133h
0x1800537b7  lea     rcx, [rbp+57h+var_80]; this
0x1800537bb  mov     [rbp+57h+var_80], esi
0x1800537be  mov     edi, r8d
0x1800537c1  mov     [rbp+57h+var_58], rax
0x1800537c5  mov     r12, rdx
0x1800537c8  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800537cd  mov     rcx, [rbx+20h]; unsigned __int16 *
0x1800537d1  mov     dword ptr [rbp+57h+var_90], r13d
0x1800537d5  call    ?IsNtDosPath@@YA_NPEBG@Z; IsNtDosPath(ushort const *)
0x1800537da  test    al, al
0x1800537dc  jz      short loc_180053805
0x1800537de  mov     [rbp+57h+var_60], 136h
0x1800537e5  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800537ea  lea     ecx, [rsi+56h]; dwErrCode
0x1800537ed  call    cs:__imp_SetLastError
0x1800537f4  nop     dword ptr [rax+rax+00h]
0x1800537f9  mov     rax, [rbp+57h+var_58]
0x1800537fd  mov     [rax], r13d
0x180053800  jmp     loc_18005399E
0x180053805  cmp     [rbx], r13
0x180053808  jnz     short loc_180053811
0x18005380a  mov     ecx, 54Fh
0x18005380f  jmp     short loc_1800537ED
0x180053811  test    edi, edi
0x180053813  jz      loc_18005390A
0x180053819  mov     rdi, [rbx+330h]
0x180053820  mov     r14d, r13d
0x180053823  add     rdi, 280h
0x18005382a  mov     rcx, rdi
0x18005382d  call    ?HasTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBA_NXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::HasTrailingPathSeparator(void)
0x180053832  mov     dl, 1
0x180053834  lea     rcx, [rbx+10h]
0x180053838  mov     sil, al
0x18005383b  call    ?CchWithoutLastPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBA_K_N@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutLastPathElement(bool)
0x180053840  mov     r15, rax
0x180053843  cmp     [rbx+330h], r13
0x18005384a  jz      short loc_18005388F
0x18005384c  test    sil, sil
0x18005384f  jnz     short loc_180053859
0x180053851  mov     rcx, rdi
0x180053854  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x180053859  mov     rdx, [rdi+20h]; unsigned __int64
0x18005385d  cmp     rdx, r15
0x180053860  ja      short loc_180053882
0x180053862  mov     r8, [rbx+20h]; unsigned __int16 *
0x180053866  mov     r9, rdx; unsigned __int64
0x180053869  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18005386d  mov     byte ptr [rsp+0D0h+var_B0], 1; bool
0x180053872  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x180053877  test    eax, eax
0x180053879  mov     eax, 1
0x18005387e  cmovz   r14d, eax
0x180053882  test    sil, sil
0x180053885  jnz     short loc_18005388F
0x180053887  mov     rcx, rdi
0x18005388a  call    ?Win32RemoveTrailingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveTrailingPathSeparators(void)
0x18005388f  xor     ecx, ecx; dwErrCode
0x180053891  call    cs:__imp_SetLastError
0x180053898  nop     dword ptr [rax+rax+00h]
0x18005389d  test    r14d, r14d
0x1800538a0  jz      short loc_1800538B6
0x1800538a2  mov     rax, [rbx+330h]
0x1800538a9  mov     rdx, [rdi+20h]
0x1800538ad  mov     rcx, [rax+290h]
0x1800538b4  jmp     short loc_1800538BC
0x1800538b6  mov     rcx, r13; unsigned __int16 *
0x1800538b9  mov     rdx, r13; unsigned __int64
0x1800538bc  mov     r8, [rbx+20h]; unsigned __int16 *
0x1800538c0  lea     rax, [rbp+57h+var_8C]
0x1800538c4  mov     qword ptr [rsp+0D0h+var_A0], r13; unsigned __int64
0x1800538c9  mov     r9, r15; unsigned __int64
0x1800538cc  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x1800538d1  lea     rax, [rbp+57h+var_90]
0x1800538d5  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1800538da  mov     [rbp+57h+var_8C], r13d
0x1800538de  call    ?SxspDoesPathCrossUnsafeReparsePoint@@YAHPEBG_K01AEAHAEAK1ZZ; SxspDoesPathCrossUnsafeReparsePoint(ushort const *,unsigned __int64,ushort const *,unsigned __int64,int &,ulong &,unsigned __int64,...)
0x1800538e3  test    eax, eax
0x1800538e5  jnz     short loc_1800538FF
0x1800538e7  lea     rcx, off_180078808; struct _CALL_SITE_INFO *
0x1800538ee  mov     rax, [rbp+57h+var_58]
0x1800538f2  mov     [rax], r13d
0x1800538f5  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800538fa  jmp     loc_18005399E
0x1800538ff  cmp     dword ptr [rbp+57h+var_90], r13d
0x180053903  jnz     short loc_180053942
0x180053905  mov     esi, 1
0x18005390a  test    dword ptr [r12], 400h
0x180053912  jz      short loc_18005398A
0x180053914  xor     ecx, ecx; dwErrCode
0x180053916  call    cs:__imp_SetLastError
0x18005391d  nop     dword ptr [rax+rax+00h]
0x180053922  mov     rcx, [rbx+20h]; lpFileName
0x180053926  lea     rdx, [rbp+57h+var_90]; int *
0x18005392a  call    ?SxspIsReparsePointUnsafe@@YAHPEBGPEAH@Z; SxspIsReparsePointUnsafe(ushort const *,int *)
0x18005392f  test    eax, eax
0x180053931  jnz     short loc_18005393C
0x180053933  lea     rcx, off_1800787E8; "clientcore\\base\\win32\\fusion\\sxs\\p"...
0x18005393a  jmp     short loc_1800538EE
0x18005393c  cmp     dword ptr [rbp+57h+var_90], r13d
0x180053940  jz      short loc_18005398A
0x180053942  mov     rcx, [rbx+330h]
0x180053949  xor     r8d, r8d; unsigned __int16 *
0x18005394c  mov     rdx, [rbx+20h]; unsigned __int16 *
0x180053950  mov     [rsp+0D0h+var_98], 67h ; 'g'; unsigned __int16
0x180053957  mov     [rsp+0D0h+var_A0], 2; char
0x18005395c  mov     ecx, [rcx+518h]; int
0x180053962  mov     word ptr [rsp+0D0h+var_A8], 107h; unsigned __int16
0x180053969  call    ?TraceActCtxGenEvents@@YAKJPEBG000GEG@Z; TraceActCtxGenEvents(long,ushort const *,ushort const *,ushort const *,ushort const *,ushort,uchar,ushort)
0x18005396e  mov     edx, 36C4h; unsigned int
0x180053973  lea     rcx, [rbp+57h+var_80]; this
0x180053977  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18005397c  lea     rcx, off_1800787C8; struct _CALL_SITE_INFO *
0x180053983  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180053988  jmp     short loc_18005399E
0x18005398a  xor     ecx, ecx; dwErrCode
0x18005398c  call    cs:__imp_SetLastError
0x180053993  nop     dword ptr [rax+rax+00h]
0x180053998  mov     rax, [rbp+57h+var_58]
0x18005399c  mov     [rax], esi
0x18005399e  mov     rax, [rbp+57h+var_58]
0x1800539a2  lea     rcx, [rbp+57h+var_80]; this
0x1800539a6  mov     ebx, [rax]
0x1800539a8  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x1800539ad  mov     eax, ebx
0x1800539af  mov     rcx, [rbp+57h+var_50]
0x1800539b3  xor     rcx, rsp; StackCookie
0x1800539b6  call    __security_check_cookie
0x1800539bb  add     rsp, 98h
0x1800539c2  pop     r15
0x1800539c4  pop     r14
0x1800539c6  pop     r13
0x1800539c8  pop     r12
0x1800539ca  pop     rdi
0x1800539cb  pop     rsi
0x1800539cc  pop     rbx
0x1800539cd  pop     rbp
0x1800539ce  retn
```
