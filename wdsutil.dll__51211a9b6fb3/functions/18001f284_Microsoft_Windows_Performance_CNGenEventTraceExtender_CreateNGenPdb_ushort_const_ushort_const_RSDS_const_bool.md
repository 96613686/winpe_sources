# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18001f284`
- end: `0x18001f5e7`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `867`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _RSDS *@<r9>, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001ef34`

## callees

- `0x1800085b8`
- `0x18000ab2c`
- `0x18000b87c`
- `0x18000b92c`
- `0x18001e14c`
- `0x18001eb64`
- `0x18001f284`
- `0x18001f5f0`
- `0x18001f6b4`
- `0x18001f7d4`
- `0x180020808`
- `0x180020868`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!strrchr` at `0x18001f2cb`
- `msvcrt!strrchr` at `0x18001f2e2`
- `msvcrt!strrchr` at `0x18001f2cb`
- `msvcrt!strrchr` at `0x18001f2e2`

## string_xrefs

- `0x18001f422`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v9; // rdi
  char *v10; // rbx
  char *v11; // rax
  const char *v12; // r12
  int v13; // ecx
  unsigned __int16 *v14; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v15; // rcx
  __int64 v16; // rcx
  char *v17; // rax
  char *v18; // rsi
  int v19; // edx
  int v20; // ecx
  int v21; // esi
  void (*v22)(void); // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v24; // rcx
  unsigned __int16 *v25; // rdi
  int v26; // eax
  __int64 v27; // r8
  int v28; // r15d
  unsigned __int16 *v29; // rdx
  int v30; // eax
  char *v31; // rax
  char *v32; // rsi
  int v33; // edx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v34; // rcx
  unsigned __int16 *v35; // [rsp+30h] [rbp-51h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-41h] BYREF
  int v38; // [rsp+48h] [rbp-39h] BYREF
  __int64 v39; // [rsp+50h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+58h] [rbp-29h] BYREF
  int *v41; // [rsp+68h] [rbp-19h]
  __int64 v42; // [rsp+70h] [rbp-11h]
  unsigned __int16 **v43; // [rsp+78h] [rbp-9h]
  __int64 v44; // [rsp+80h] [rbp-1h]

  v39 = -2;
  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v9;
  v37 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&v37,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v37, L"\\", 1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v37, v12);
  v14 = v37;
  if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v15, v37) )
  {
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v16, TraceMerge_NGEN_CandidateEncountered_ExistingPDB, v14);
    if ( a2 )
    {
      v17 = (char *)*((_QWORD *)this + 7);
      v18 = (char *)(a2 - v17);
      do
      {
        v19 = *(unsigned __int16 *)&v18[(_QWORD)v17];
        v20 = *(unsigned __int16 *)v17 - v19;
        if ( v20 )
          break;
        v17 += 2;
      }
      while ( v19 );
      if ( v20 )
      {
        v21 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
        if ( v21 < 0 )
        {
          if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) > 0 )
            return (unsigned int)v21;
          v22 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
LABEL_16:
          v22();
          return (unsigned int)v21;
        }
      }
LABEL_42:
      if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
      return 0;
    }
    goto LABEL_45;
  }
  v35 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v35,
    L"%wsngen.exe createpdb %ws %ws",
    *((_QWORD *)this + a5 + 5),
    a3,
    a2);
  v25 = v35;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v24, TraceMerge_NGEN_CreatingPDB_Start, v35);
  v36 = 0;
  if ( *((int *)v25 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&v35, *((unsigned int *)v25 - 4));
    v25 = v35;
  }
  v26 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v24, v25, &v36);
  v28 = v26;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
  {
    LODWORD(v35) = v36;
    v38 = v26;
    v41 = &v38;
    v42 = 4;
    v43 = &v35;
    v44 = 4;
    McGenEventWrite_EventWriteTransfer(v36, (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_CreatingPDB_Stop, v27, 3u, &v40);
  }
  v29 = v25 - 12;
  v30 = _InterlockedDecrement((volatile signed __int32 *)v25 - 2);
  if ( v28 >= 0 )
  {
    if ( v30 <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
    if ( a2 )
    {
      v31 = (char *)*((_QWORD *)this + 7);
      v32 = (char *)(a2 - v31);
      do
      {
        v33 = *(unsigned __int16 *)&v32[(_QWORD)v31];
        v34 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)((unsigned int)*(unsigned __int16 *)v31 - v33);
        if ( (_DWORD)v34 )
          break;
        v31 += 2;
      }
      while ( v33 );
      if ( (_DWORD)v34 )
      {
        if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v34, v14) )
        {
          v21 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
          if ( v21 < 0 )
          {
            if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) > 0 )
              return (unsigned int)v21;
            v22 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
            goto LABEL_16;
          }
        }
      }
      goto LABEL_42;
    }
LABEL_45:
    ATL::AtlThrowImpl(-2147467259);
  }
  if ( v30 <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29);
  if ( _InterlockedDecrement((volatile signed __int32 *)v14 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x18001f284  push    rbp
0x18001f286  push    rbx
0x18001f287  push    rsi
0x18001f288  push    rdi
0x18001f289  push    r12
0x18001f28b  push    r13
0x18001f28d  push    r14
0x18001f28f  push    r15
0x18001f291  lea     rbp, [rsp-17h]
0x18001f296  sub     rsp, 98h
0x18001f29d  mov     [rbp+4Fh+var_80], 0FFFFFFFFFFFFFFFEh
0x18001f2a5  mov     rax, cs:__security_cookie
0x18001f2ac  xor     rax, rsp
0x18001f2af  mov     [rbp+4Fh+var_48], rax
0x18001f2b3  mov     r13, r9
0x18001f2b6  mov     r15, r8
0x18001f2b9  mov     rsi, rdx
0x18001f2bc  mov     r14, rcx
0x18001f2bf  lea     rdi, [r9+18h]
0x18001f2c3  mov     edx, 2Fh ; '/'; Ch
0x18001f2c8  mov     rcx, rdi; Str
0x18001f2cb  call    cs:__imp_strrchr
0x18001f2d2  nop     dword ptr [rax+rax+00h]
0x18001f2d7  mov     rbx, rax
0x18001f2da  mov     edx, 5Ch ; '\'; Ch
0x18001f2df  mov     rcx, rdi; Str
0x18001f2e2  call    cs:__imp_strrchr
0x18001f2e9  nop     dword ptr [rax+rax+00h]
0x18001f2ee  cmp     rbx, rax
0x18001f2f1  cmova   rax, rbx
0x18001f2f5  lea     r12, [rax+1]
0x18001f2f9  test    rax, rax
0x18001f2fc  cmovz   r12, rdi
0x18001f300  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f307  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f30e  mov     rax, [rax+18h]
0x18001f312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f317  add     rax, 18h
0x18001f31b  mov     [rbp+4Fh+var_90], rax
0x18001f31f  mov     [rsp+0D0h+var_B0], r13
0x18001f324  mov     r9, r12
0x18001f327  mov     r8, rsi
0x18001f32a  lea     rdx, [rbp+4Fh+var_90]
0x18001f32e  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18001f333  mov     r8d, 1
0x18001f339  lea     rdx, pszSrc; "\\"
0x18001f340  lea     rcx, [rbp+4Fh+var_90]
0x18001f344  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001f349  mov     rdx, r12
0x18001f34c  lea     rcx, [rbp+4Fh+var_90]
0x18001f350  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18001f355  mov     rbx, [rbp+4Fh+var_90]
0x18001f359  mov     rdx, rbx; unsigned __int16 *
0x18001f35c  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18001f361  test    al, al
0x18001f363  jz      loc_18001F3F1
0x18001f369  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001f370  jz      short loc_18001F381
0x18001f372  mov     r8, rbx
0x18001f375  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x18001f37c  call    McTemplateU0z_EventWriteTransfer
0x18001f381  test    rsi, rsi
0x18001f384  jz      loc_18001F5DC
0x18001f38a  mov     rax, [r14+38h]
0x18001f38e  sub     rsi, rax
0x18001f391  movzx   ecx, word ptr [rax]
0x18001f394  movzx   edx, word ptr [rax+rsi]
0x18001f398  sub     ecx, edx
0x18001f39a  jnz     short loc_18001F3A4
0x18001f39c  add     rax, 2
0x18001f3a0  test    edx, edx
0x18001f3a2  jnz     short loc_18001F391
0x18001f3a4  test    ecx, ecx
0x18001f3a6  jz      short loc_18001F3E9
0x18001f3a8  mov     r9, r13; struct _RSDS *
0x18001f3ab  mov     r8, r12; char *
0x18001f3ae  mov     rdx, rbx; unsigned __int16 *
0x18001f3b1  mov     rcx, r14; this
0x18001f3b4  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18001f3b9  mov     esi, eax
0x18001f3bb  test    eax, eax
0x18001f3bd  jns     short loc_18001F3E9
0x18001f3bf  lea     rdx, [rbx-18h]
0x18001f3c3  or      edi, 0FFFFFFFFh
0x18001f3c6  mov     ecx, edi
0x18001f3c8  lock xadd [rdx+10h], ecx
0x18001f3cd  add     ecx, edi
0x18001f3cf  test    ecx, ecx
0x18001f3d1  jg      short loc_18001F3E2
0x18001f3d3  mov     rcx, [rdx]
0x18001f3d6  mov     rax, [rcx]
0x18001f3d9  mov     rax, [rax+8]
0x18001f3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3e2  mov     eax, esi
0x18001f3e4  jmp     loc_18001F5BB
0x18001f3e9  or      edi, 0FFFFFFFFh
0x18001f3ec  jmp     loc_18001F599
0x18001f3f1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f3f8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001f3ff  mov     rax, [rax+18h]
0x18001f403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f408  add     rax, 18h
0x18001f40c  mov     [rbp+4Fh+var_A0], rax
0x18001f410  movzx   r8d, [rbp+4Fh+arg_20]
0x18001f415  mov     [rsp+0D0h+var_B0], rsi
0x18001f41a  mov     r9, r15
0x18001f41d  mov     r8, [r14+r8*8+28h]
0x18001f422  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x18001f429  lea     rcx, [rbp+4Fh+var_A0]
0x18001f42d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001f432  mov     rdi, [rbp+4Fh+var_A0]
0x18001f436  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001f43d  jz      short loc_18001F44E
0x18001f43f  mov     r8, rdi
0x18001f442  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x18001f449  call    McTemplateU0z_EventWriteTransfer
0x18001f44e  mov     [rbp+4Fh+var_98], 0
0x18001f455  cmp     dword ptr [rdi-8], 1
0x18001f459  jle     short loc_18001F46B
0x18001f45b  mov     edx, [rdi-10h]
0x18001f45e  lea     rcx, [rbp+4Fh+var_A0]
0x18001f462  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x18001f467  mov     rdi, [rbp+4Fh+var_A0]
0x18001f46b  lea     r8, [rbp+4Fh+var_98]; unsigned int *
0x18001f46f  mov     rdx, rdi; unsigned __int16 *
0x18001f472  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x18001f477  mov     r15d, eax
0x18001f47a  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18001f481  jz      short loc_18001F4C7
0x18001f483  mov     ecx, [rbp+4Fh+var_98]
0x18001f486  mov     dword ptr [rbp+4Fh+var_A0], ecx
0x18001f489  mov     [rbp+4Fh+var_88], eax
0x18001f48c  lea     rax, [rbp+4Fh+var_88]
0x18001f490  mov     [rbp+4Fh+var_68], rax
0x18001f494  mov     [rbp+4Fh+var_60], 4
0x18001f49c  lea     rax, [rbp+4Fh+var_A0]
0x18001f4a0  mov     [rbp+4Fh+var_58], rax
0x18001f4a4  mov     [rbp+4Fh+var_50], 4
0x18001f4ac  lea     rax, [rbp+4Fh+var_78]
0x18001f4b0  mov     [rsp+0D0h+var_B0], rax
0x18001f4b5  mov     r9d, 3
0x18001f4bb  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x18001f4c2  call    McGenEventWrite_EventWriteTransfer
0x18001f4c7  lea     rdx, [rdi-18h]
0x18001f4cb  or      edi, 0FFFFFFFFh
0x18001f4ce  mov     eax, edi
0x18001f4d0  lock xadd [rdx+10h], eax
0x18001f4d5  add     eax, edi
0x18001f4d7  test    r15d, r15d
0x18001f4da  jns     short loc_18001F518
0x18001f4dc  test    eax, eax
0x18001f4de  jg      short loc_18001F4F0
0x18001f4e0  mov     rcx, [rdx]
0x18001f4e3  mov     rax, [rcx]
0x18001f4e6  mov     rax, [rax+8]
0x18001f4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ef  nop
0x18001f4f0  lea     rdx, [rbx-18h]
0x18001f4f4  mov     eax, edi
0x18001f4f6  lock xadd [rdx+10h], eax
0x18001f4fb  add     eax, edi
0x18001f4fd  test    eax, eax
0x18001f4ff  jg      short loc_18001F510
0x18001f501  mov     rcx, [rdx]
0x18001f504  mov     rax, [rcx]
0x18001f507  mov     rax, [rax+8]
0x18001f50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f510  mov     eax, r15d
0x18001f513  jmp     loc_18001F5BB
0x18001f518  test    eax, eax
0x18001f51a  jg      short loc_18001F52B
0x18001f51c  mov     rcx, [rdx]
0x18001f51f  mov     rax, [rcx]
0x18001f522  mov     rax, [rax+8]
0x18001f526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f52b  test    rsi, rsi
0x18001f52e  jz      loc_18001F5DC
0x18001f534  mov     rax, [r14+38h]
0x18001f538  sub     rsi, rax
0x18001f53b  movzx   ecx, word ptr [rax]
0x18001f53e  movzx   edx, word ptr [rax+rsi]
0x18001f542  sub     ecx, edx; this
0x18001f544  jnz     short loc_18001F54E
0x18001f546  add     rax, 2
0x18001f54a  test    edx, edx
0x18001f54c  jnz     short loc_18001F53B
0x18001f54e  test    ecx, ecx
0x18001f550  jz      short loc_18001F599
0x18001f552  mov     rdx, rbx; unsigned __int16 *
0x18001f555  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18001f55a  test    al, al
0x18001f55c  jz      short loc_18001F599
0x18001f55e  mov     r9, r13; struct _RSDS *
0x18001f561  mov     r8, r12; char *
0x18001f564  mov     rdx, rbx; unsigned __int16 *
0x18001f567  mov     rcx, r14; this
0x18001f56a  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18001f56f  mov     esi, eax
0x18001f571  test    eax, eax
0x18001f573  jns     short loc_18001F599
0x18001f575  lea     rdx, [rbx-18h]
0x18001f579  mov     ecx, edi
0x18001f57b  lock xadd [rdx+10h], ecx
0x18001f580  add     ecx, edi
0x18001f582  test    ecx, ecx
0x18001f584  jg      loc_18001F3E2
0x18001f58a  mov     rcx, [rdx]
0x18001f58d  mov     r8, [rcx]
0x18001f590  mov     rax, [r8+8]
0x18001f594  jmp     loc_18001F3DD
0x18001f599  lea     rdx, [rbx-18h]
0x18001f59d  mov     eax, edi
0x18001f59f  lock xadd [rdx+10h], eax
0x18001f5a4  add     eax, edi
0x18001f5a6  test    eax, eax
0x18001f5a8  jg      short loc_18001F5B9
0x18001f5aa  mov     rcx, [rdx]
0x18001f5ad  mov     rax, [rcx]
0x18001f5b0  mov     rax, [rax+8]
0x18001f5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5b9  xor     eax, eax
0x18001f5bb  mov     rcx, [rbp+4Fh+var_48]
0x18001f5bf  xor     rcx, rsp; StackCookie
0x18001f5c2  call    __security_check_cookie
0x18001f5c7  add     rsp, 98h
0x18001f5ce  pop     r15
0x18001f5d0  pop     r14
0x18001f5d2  pop     r13
0x18001f5d4  pop     r12
0x18001f5d6  pop     rdi
0x18001f5d7  pop     rsi
0x18001f5d8  pop     rbx
0x18001f5d9  pop     rbp
0x18001f5da  retn
0x18001f5dc  mov     ecx, 80004005h; int
0x18001f5e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
