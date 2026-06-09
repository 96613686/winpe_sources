# CBaseGrammar::CompileCfgFromStream(IStream *,ushort const *,SPGRAMMAROPTIONS,ISpeechResourceLoader *,SPCFGSERIALIZEDHEADER * *)

- ea: `0x18019b260`
- end: `0x18019b733`
- name: `?CompileCfgFromStream@CBaseGrammar@@SAJPEAUIStream@@PEBGW4SPGRAMMAROPTIONS@@PEAUISpeechResourceLoader@@PEAPEAUSPCFGSERIALIZEDHEADER@@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(struct IStream *, const unsigned __int16 *, enum SPGRAMMAROPTIONS, struct ISpeechResourceLoader *, struct SPCFGSERIALIZEDHEADER **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18019b92c`

## callees

- `0x18000bec4`
- `0x180013ec0`
- `0x18006cc80`
- `0x180079e30`
- `0x18007a2dc`
- `0x18007a350`
- `0x18007aae4`
- `0x18007d7b1`
- `0x18019b260`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18019b66f`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18019b66f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019b483`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18019b483`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b4c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b5e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b4c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019b5e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019b680`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18019b680`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18019b693`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18019b693`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019b6cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019b6cd`

## string_xrefs

- `0x18019b396`: `Grammar is in compiled CFG++ format (with engine data)`
- `0x18019b6f9`: `Failed to compile CFG grammar, hr = 0x%X`
- `0x18019b39d`: `Grammar is in compiled CFG format`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBaseGrammar::CompileCfgFromStream(
        struct IStream *a1,
        const unsigned __int16 *a2,
        enum SPGRAMMAROPTIONS a3,
        struct ISpeechResourceLoader *a4,
        struct SPCFGSERIALIZEDHEADER **a5)
{
  char v6; // r15
  void *v9; // rdi
  ULONG v10; // ebx
  int v11; // eax
  const char *v12; // rdx
  _OWORD *v13; // rax
  HRESULT HGlobalFromStream; // ebx
  bool v15; // r14
  HRESULT v16; // ebx
  LPVOID v17; // rcx
  HRESULT v18; // ebx
  const void *v19; // rsi
  SIZE_T v20; // r14
  void *v21; // rax
  HGLOBAL phglobal; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  struct SPCFGSERIALIZEDHEADER **v29; // [rsp+70h] [rbp-90h]
  SPBINARYGRAMMAR v30[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+A0h] [rbp-60h]
  __int128 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+C0h] [rbp-40h]
  __int128 v35; // [rsp+D0h] [rbp-30h]
  __int128 v36; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  __int128 v38; // [rsp+100h] [rbp+0h]
  int v39; // [rsp+110h] [rbp+10h]

  v6 = a3;
  v29 = a5;
  v9 = 0;
  memset_0(v30, 0, 0x94u);
  v28 = 0;
  v27 = 0;
  phglobal = 0;
  v10 = -1;
  v24 = 0;
  if ( !(*(unsigned int (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(*(_QWORD *)a1 + 40LL))(
          a1,
          0,
          1,
          &v28)
    && !(*(unsigned int (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(*(_QWORD *)a1 + 40LL))(
          a1,
          0,
          2,
          &v27) )
  {
    v10 = v27 - v28;
    ppv = (LPVOID)(unsigned int)v28;
    (*(void (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(
      a1,
      (unsigned int)v28,
      0,
      0);
  }
  v11 = (*(__int64 (__fastcall **)(struct IStream *, SPBINARYGRAMMAR *, __int64, unsigned int *))(*(_QWORD *)a1 + 24LL))(
          a1,
          v30,
          148,
          &v24);
  if ( v24 == 148
    && v11 >= 0
    && CSpCfgData::CheckFormatIdValid(v30)
    && v30[0].ulTotalSerializedSize <= v10
    && v30[0].ulTotalSerializedSize >= 0x94 )
  {
    v12 = "Grammar is in compiled CFG++ format (with engine data)";
    if ( !HIDWORD(v38) )
      v12 = "Grammar is in compiled CFG format";
    DoTraceMessage(16, v12);
    v13 = operator new[](v30[0].ulTotalSerializedSize, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v13;
    if ( v13 )
    {
      *v13 = *(_OWORD *)&v30[0].ulTotalSerializedSize;
      v13[1] = v31;
      v13[2] = v32;
      v13[3] = v33;
      v13[4] = v34;
      v13[5] = v35;
      v13[6] = v36;
      v13[7] = v37;
      v13[8] = v38;
      *((_DWORD *)v13 + 36) = v39;
      HGlobalFromStream = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, unsigned int *))(*(_QWORD *)a1 + 24LL))(
                            a1,
                            (__int64)v13 + 148,
                            v30[0].ulTotalSerializedSize - 148,
                            &v24);
      if ( v24 + 148LL == v30[0].ulTotalSerializedSize )
      {
        if ( HGlobalFromStream >= 0 )
          goto LABEL_43;
      }
      else
      {
        operator delete(v9);
        v9 = 0;
      }
    }
  }
  ppstm = 0;
  if ( CreateStreamOnHGlobal(0, 1, &ppstm) < 0 )
    goto LABEL_41;
  v15 = 0;
  if ( (v6 & 2) != 0 )
  {
    phglobal = 0;
    v16 = CoCreateInstance(&CLSID_SpW3CGrammarCompiler, 0, 0x17u, &GUID_b1e29d58_a675_11d2_8302_00c04f8ee6c0, &phglobal);
    if ( v16 >= 0 )
    {
      v17 = 0;
      ppv = 0;
      if ( phglobal )
      {
        (**(void (__fastcall ***)(HGLOBAL, GUID *, LPVOID *))phglobal)(
          phglobal,
          &GUID_2a0e05cf_50e8_462d_b84e_7fe25da91a2f,
          &ppv);
        v17 = ppv;
      }
      if ( v17 )
        v16 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v17 + 40LL))(v17, a2);
      else
        v16 = -2147467263;
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
      if ( v16 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, 0);
        if ( v16 >= 0 )
          v15 = (*(int (__fastcall **)(HGLOBAL, struct IStream *, LPSTREAM, _QWORD, struct ISpeechResourceLoader *, _QWORD, _DWORD))(*(_QWORD *)phglobal + 24LL))(
                  phglobal,
                  a1,
                  ppstm,
                  0,
                  a4,
                  0,
                  0) >= 0;
      }
    }
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&phglobal);
    if ( v16 < 0 )
      goto LABEL_41;
    if ( v15 )
    {
LABEL_35:
      phglobal = 0;
      HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
      if ( HGlobalFromStream >= 0 )
      {
        v19 = GlobalLock(phglobal);
        if ( v19 )
        {
          v20 = GlobalSize(phglobal);
          v21 = operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
          v9 = v21;
          if ( v21 )
            memcpy_0(v21, v19, v20);
          else
            HGlobalFromStream = -2147024882;
          GlobalUnlock(phglobal);
        }
      }
      goto LABEL_42;
    }
  }
  if ( (v6 & 1) != 0 )
  {
    ppv = 0;
    v18 = CoCreateInstance(&CLSID_SpGrammarCompiler, 0, 0x17u, &GUID_b1e29d58_a675_11d2_8302_00c04f8ee6c0, &ppv);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0, 0, 0);
      if ( v18 >= 0
        && (*(int (__fastcall **)(LPVOID, struct IStream *, LPSTREAM, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
             ppv,
             a1,
             ppstm,
             0,
             0,
             0,
             0) >= 0 )
      {
        v15 = 1;
      }
    }
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
    if ( v18 >= 0 && v15 )
      goto LABEL_35;
  }
LABEL_41:
  HGlobalFromStream = -2147201021;
LABEL_42:
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppstm);
LABEL_43:
  if ( HGlobalFromStream < 0 )
    v9 = 0;
  *v29 = (struct SPCFGSERIALIZEDHEADER *)v9;
  if ( HGlobalFromStream < 0 )
    DoTraceMessage(2, "Failed to compile CFG grammar, hr = 0x%X", HGlobalFromStream);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x18019b260  mov     [rsp-8+arg_10], rbx
0x18019b265  push    rbp
0x18019b266  push    rsi
0x18019b267  push    rdi
0x18019b268  push    r12
0x18019b26a  push    r13
0x18019b26c  push    r14
0x18019b26e  push    r15
0x18019b270  lea     rbp, [rsp-30h]
0x18019b275  sub     rsp, 130h
0x18019b27c  mov     rax, cs:__security_cookie
0x18019b283  xor     rax, rsp
0x18019b286  mov     [rbp+60h+var_40], rax
0x18019b28a  mov     r13, r9
0x18019b28d  mov     r15d, r8d
0x18019b290  mov     r12, rdx
0x18019b293  mov     rsi, rcx
0x18019b296  mov     rax, [rbp+60h+arg_20]
0x18019b29d  mov     [rsp+160h+var_F0], rax
0x18019b2a2  xor     edi, edi
0x18019b2a4  mov     r14d, 94h
0x18019b2aa  mov     r8d, r14d; Size
0x18019b2ad  xor     edx, edx; Val
0x18019b2af  lea     rcx, [rbp+60h+var_E0]; void *
0x18019b2b3  call    memset_0
0x18019b2b8  mov     [rsp+160h+var_F8], rdi
0x18019b2bd  mov     [rsp+160h+var_100], rdi
0x18019b2c2  mov     [rsp+160h+phglobal], rdi
0x18019b2c7  or      ebx, 0FFFFFFFFh
0x18019b2ca  mov     [rsp+160h+var_118], edi
0x18019b2ce  mov     rax, [rsi]
0x18019b2d1  lea     r9, [rsp+160h+var_F8]
0x18019b2d6  lea     r8d, [rdi+1]
0x18019b2da  mov     edx, edi
0x18019b2dc  mov     rcx, rsi
0x18019b2df  mov     rax, [rax+28h]
0x18019b2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b2e8  test    eax, eax
0x18019b2ea  jnz     short loc_18019B339
0x18019b2ec  mov     rax, [rsi]
0x18019b2ef  lea     r9, [rsp+160h+var_100]
0x18019b2f4  lea     r8d, [rdi+2]
0x18019b2f8  mov     edx, edi
0x18019b2fa  mov     rcx, rsi
0x18019b2fd  mov     rax, [rax+28h]
0x18019b301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b306  test    eax, eax
0x18019b308  jnz     short loc_18019B339
0x18019b30a  mov     ebx, dword ptr [rsp+160h+var_100]
0x18019b30e  mov     rax, [rsp+160h+var_F8]
0x18019b313  sub     ebx, eax
0x18019b315  mov     dword ptr [rsp+160h+var_110], eax
0x18019b319  xor     eax, eax
0x18019b31b  mov     dword ptr [rsp+160h+var_110+4], eax
0x18019b31f  mov     rax, [rsi]
0x18019b322  xor     r9d, r9d
0x18019b325  xor     r8d, r8d
0x18019b328  mov     rdx, [rsp+160h+var_110]
0x18019b32d  mov     rcx, rsi
0x18019b330  mov     rax, [rax+28h]
0x18019b334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b339  mov     rax, [rsi]
0x18019b33c  lea     r9, [rsp+160h+var_118]
0x18019b341  mov     r8d, r14d
0x18019b344  lea     rdx, [rbp+60h+var_E0]
0x18019b348  mov     rcx, rsi
0x18019b34b  mov     rax, [rax+18h]
0x18019b34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b354  cmp     [rsp+160h+var_118], r14d
0x18019b359  jnz     loc_18019B46E
0x18019b35f  test    eax, eax
0x18019b361  js      loc_18019B46E
0x18019b367  cmp     [rsp+160h+var_118], r14d
0x18019b36c  jnz     loc_18019B46E
0x18019b372  lea     rcx, [rbp+60h+var_E0]; struct SPBINARYGRAMMAR *
0x18019b376  call    ?CheckFormatIdValid@CSpCfgData@@SAHPEBUSPBINARYGRAMMAR@@@Z; CSpCfgData::CheckFormatIdValid(SPBINARYGRAMMAR const *)
0x18019b37b  test    eax, eax
0x18019b37d  jz      loc_18019B46E
0x18019b383  cmp     [rbp+60h+var_E0.ulTotalSerializedSize], ebx
0x18019b386  ja      loc_18019B46E
0x18019b38c  cmp     [rbp+60h+var_E0.ulTotalSerializedSize], r14d
0x18019b390  jb      loc_18019B46E
0x18019b396  lea     rdx, aGrammarIsInCom_0; "Grammar is in compiled CFG++ format (wi"...
0x18019b39d  lea     rax, aGrammarIsInCom; "Grammar is in compiled CFG format"
0x18019b3a4  cmp     [rbp+60h+var_54], edi
0x18019b3a7  cmovz   rdx, rax; char *
0x18019b3ab  mov     ecx, 10h; int
0x18019b3b0  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18019b3b5  mov     ecx, [rbp+60h+var_E0.ulTotalSerializedSize]; unsigned __int64
0x18019b3b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019b3bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019b3c4  mov     rdi, rax
0x18019b3c7  test    rax, rax
0x18019b3ca  jz      loc_18019B46E
0x18019b3d0  movups  xmm0, xmmword ptr [rbp+60h+var_E0.ulTotalSerializedSize]
0x18019b3d4  movups  xmmword ptr [rax], xmm0
0x18019b3d7  movups  xmm1, [rbp+60h+var_D0]
0x18019b3db  movups  xmmword ptr [rax+10h], xmm1
0x18019b3df  movups  xmm0, [rbp+60h+var_C0]
0x18019b3e3  movups  xmmword ptr [rax+20h], xmm0
0x18019b3e7  movups  xmm1, [rbp+60h+var_B0]
0x18019b3eb  movups  xmmword ptr [rax+30h], xmm1
0x18019b3ef  movups  xmm0, [rbp+60h+var_A0]
0x18019b3f3  movups  xmmword ptr [rax+40h], xmm0
0x18019b3f7  movups  xmm1, [rbp+60h+var_90]
0x18019b3fb  movups  xmmword ptr [rax+50h], xmm1
0x18019b3ff  movups  xmm0, [rbp+60h+var_80]
0x18019b403  movups  xmmword ptr [rax+60h], xmm0
0x18019b407  movups  xmm1, [rbp+60h+var_70]
0x18019b40b  movups  xmmword ptr [rax+70h], xmm1
0x18019b40f  movups  xmm0, xmmword ptr [rbp+0]
0x18019b413  movups  xmmword ptr [rax+80h], xmm0
0x18019b41a  mov     eax, [rbp+60h+var_50]
0x18019b41d  mov     [rdi+90h], eax
0x18019b423  mov     rax, [rsi]
0x18019b426  mov     r8d, [rbp+60h+var_E0.ulTotalSerializedSize]
0x18019b42a  add     r8d, 0FFFFFF6Ch
0x18019b431  lea     rdx, [rdi+94h]
0x18019b438  lea     r9, [rsp+160h+var_118]
0x18019b43d  mov     rcx, rsi
0x18019b440  mov     rax, [rax+18h]
0x18019b444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b449  mov     ebx, eax
0x18019b44b  mov     ecx, [rsp+160h+var_118]
0x18019b44f  add     rcx, r14
0x18019b452  mov     eax, [rbp+60h+var_E0.ulTotalSerializedSize]
0x18019b455  cmp     rcx, rax
0x18019b458  jz      short loc_18019B466
0x18019b45a  mov     rcx, rdi; Block
0x18019b45d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18019b462  xor     edi, edi
0x18019b464  jmp     short loc_18019B46E
0x18019b466  test    ebx, ebx
0x18019b468  jns     loc_18019B6E4
0x18019b46e  mov     [rsp+160h+ppstm], 0
0x18019b477  lea     r8, [rsp+160h+ppstm]; ppstm
0x18019b47c  mov     edx, 1; fDeleteOnRelease
0x18019b481  xor     ecx, ecx; hGlobal
0x18019b483  call    cs:__imp_CreateStreamOnHGlobal
0x18019b489  test    eax, eax
0x18019b48b  js      loc_18019B6D5
0x18019b491  xor     r14b, r14b
0x18019b494  test    r15b, 2
0x18019b498  jz      loc_18019B5A9
0x18019b49e  mov     [rsp+160h+phglobal], 0
0x18019b4a7  lea     rax, [rsp+160h+phglobal]
0x18019b4ac  mov     [rsp+160h+ppv], rax; ppv
0x18019b4b1  lea     r9, _GUID_b1e29d58_a675_11d2_8302_00c04f8ee6c0; riid
0x18019b4b8  xor     edx, edx; pUnkOuter
0x18019b4ba  lea     r8d, [rdx+17h]; dwClsContext
0x18019b4be  lea     rcx, CLSID_SpW3CGrammarCompiler; rclsid
0x18019b4c5  call    cs:__imp_CoCreateInstance
0x18019b4cb  mov     ebx, eax
0x18019b4cd  test    eax, eax
0x18019b4cf  js      loc_18019B58E
0x18019b4d5  mov     r9, [rsp+160h+phglobal]
0x18019b4da  xor     ecx, ecx
0x18019b4dc  mov     [rsp+160h+var_110], rcx
0x18019b4e1  test    r9, r9
0x18019b4e4  jz      short loc_18019B505
0x18019b4e6  mov     rax, [r9]
0x18019b4e9  lea     r8, [rsp+160h+var_110]
0x18019b4ee  lea     rdx, _GUID_2a0e05cf_50e8_462d_b84e_7fe25da91a2f
0x18019b4f5  mov     rcx, r9
0x18019b4f8  mov     rax, [rax]
0x18019b4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b500  mov     rcx, [rsp+160h+var_110]
0x18019b505  test    rcx, rcx
0x18019b508  jnz     short loc_18019B511
0x18019b50a  mov     ebx, 80004001h
0x18019b50f  jmp     short loc_18019B522
0x18019b511  mov     rax, [rcx]
0x18019b514  mov     rdx, r12
0x18019b517  mov     rax, [rax+28h]
0x18019b51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b520  mov     ebx, eax
0x18019b522  lea     rcx, [rsp+160h+var_110]
0x18019b527  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18019b52c  test    ebx, ebx
0x18019b52e  js      short loc_18019B58E
0x18019b530  xor     edx, edx
0x18019b532  mov     rax, [rsi]
0x18019b535  xor     r9d, r9d
0x18019b538  xor     r8d, r8d
0x18019b53b  mov     rcx, rsi
0x18019b53e  mov     rax, [rax+28h]
0x18019b542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b547  mov     ebx, eax
0x18019b549  test    eax, eax
0x18019b54b  js      short loc_18019B58E
0x18019b54d  mov     rcx, [rsp+160h+phglobal]
0x18019b552  mov     rax, [rcx]
0x18019b555  mov     [rsp+160h+var_130], 0
0x18019b55d  mov     [rsp+160h+var_138], 0
0x18019b566  mov     [rsp+160h+ppv], r13
0x18019b56b  xor     r9d, r9d
0x18019b56e  mov     r8, [rsp+160h+ppstm]
0x18019b573  mov     rdx, rsi
0x18019b576  mov     rax, [rax+18h]
0x18019b57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b57f  movzx   r14d, r14b
0x18019b583  test    eax, eax
0x18019b585  mov     eax, 1
0x18019b58a  cmovns  r14d, eax
0x18019b58e  lea     rcx, [rsp+160h+phglobal]
0x18019b593  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18019b598  test    ebx, ebx
0x18019b59a  js      loc_18019B6D5
0x18019b5a0  test    r14b, r14b
0x18019b5a3  jnz     loc_18019B65C
0x18019b5a9  mov     r12d, 1
0x18019b5af  test    r12b, r15b
0x18019b5b2  jz      loc_18019B6D5
0x18019b5b8  mov     [rsp+160h+var_110], 0
0x18019b5c1  lea     rax, [rsp+160h+var_110]
0x18019b5c6  mov     [rsp+160h+ppv], rax; ppv
0x18019b5cb  lea     r9, _GUID_b1e29d58_a675_11d2_8302_00c04f8ee6c0; riid
0x18019b5d2  xor     edx, edx; pUnkOuter
0x18019b5d4  lea     r8d, [r12+16h]; dwClsContext
0x18019b5d9  lea     rcx, CLSID_SpGrammarCompiler; rclsid
0x18019b5e0  call    cs:__imp_CoCreateInstance
0x18019b5e6  mov     ebx, eax
0x18019b5e8  test    eax, eax
0x18019b5ea  js      short loc_18019B649
0x18019b5ec  xor     edx, edx
0x18019b5ee  mov     rax, [rsi]
0x18019b5f1  xor     r9d, r9d
0x18019b5f4  xor     r8d, r8d
0x18019b5f7  mov     rcx, rsi
0x18019b5fa  mov     rax, [rax+28h]
0x18019b5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b603  mov     ebx, eax
0x18019b605  test    eax, eax
0x18019b607  js      short loc_18019B649
0x18019b609  mov     rcx, [rsp+160h+var_110]
0x18019b60e  mov     rax, [rcx]
0x18019b611  mov     [rsp+160h+var_130], 0
0x18019b619  mov     [rsp+160h+var_138], 0
0x18019b622  mov     [rsp+160h+ppv], 0
0x18019b62b  xor     r9d, r9d
0x18019b62e  mov     r8, [rsp+160h+ppstm]
0x18019b633  mov     rdx, rsi
0x18019b636  mov     rax, [rax+18h]
0x18019b63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019b63f  movzx   r14d, r14b
0x18019b643  test    eax, eax
0x18019b645  cmovns  r14d, r12d
0x18019b649  lea     rcx, [rsp+160h+var_110]
0x18019b64e  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18019b653  test    ebx, ebx
0x18019b655  js      short loc_18019B6D5
0x18019b657  test    r14b, r14b
0x18019b65a  jz      short loc_18019B6D5
0x18019b65c  mov     [rsp+160h+phglobal], 0
0x18019b665  lea     rdx, [rsp+160h+phglobal]; phglobal
0x18019b66a  mov     rcx, [rsp+160h+ppstm]; pstm
0x18019b66f  call    cs:__imp_GetHGlobalFromStream
0x18019b675  mov     ebx, eax
0x18019b677  test    eax, eax
0x18019b679  js      short loc_18019B6DA
0x18019b67b  mov     rcx, [rsp+160h+phglobal]; hMem
0x18019b680  call    cs:__imp_GlobalLock
0x18019b686  mov     rsi, rax
0x18019b689  test    rax, rax
0x18019b68c  jz      short loc_18019B6DA
0x18019b68e  mov     rcx, [rsp+160h+phglobal]; hMem
0x18019b693  call    cs:__imp_GlobalSize
0x18019b699  mov     r14, rax
0x18019b69c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019b6a3  mov     rcx, rax; unsigned __int64
0x18019b6a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019b6ab  mov     rdi, rax
0x18019b6ae  test    rax, rax
0x18019b6b1  jnz     short loc_18019B6BA
0x18019b6b3  mov     ebx, 8007000Eh
0x18019b6b8  jmp     short loc_18019B6C8
0x18019b6ba  mov     r8, r14; Size
0x18019b6bd  mov     rdx, rsi; Src
0x18019b6c0  mov     rcx, rax; void *
0x18019b6c3  call    memcpy_0
0x18019b6c8  mov     rcx, [rsp+160h+phglobal]; hMem
0x18019b6cd  call    cs:__imp_GlobalUnlock
0x18019b6d3  jmp     short loc_18019B6DA
0x18019b6d5  mov     ebx, 80045003h
0x18019b6da  lea     rcx, [rsp+160h+ppstm]
0x18019b6df  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18019b6e4  xor     eax, eax
0x18019b6e6  test    ebx, ebx
0x18019b6e8  cmovs   rdi, rax
0x18019b6ec  mov     rax, [rsp+160h+var_F0]
0x18019b6f1  mov     [rax], rdi
0x18019b6f4  jns     short loc_18019B70A
0x18019b6f6  mov     r8d, ebx
0x18019b6f9  lea     rdx, aFailedToCompil; "Failed to compile CFG grammar, hr = 0x%"...
0x18019b700  mov     ecx, 2; int
0x18019b705  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18019b70a  mov     eax, ebx
0x18019b70c  mov     rcx, [rbp+60h+var_40]
0x18019b710  xor     rcx, rsp; StackCookie
0x18019b713  call    __security_check_cookie
  ... truncated ...
```
