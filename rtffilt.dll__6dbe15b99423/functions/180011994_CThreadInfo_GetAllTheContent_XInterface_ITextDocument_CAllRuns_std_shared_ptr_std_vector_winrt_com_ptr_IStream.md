# CThreadInfo::GetAllTheContent(XInterface<ITextDocument> &,CAllRuns *,std::shared_ptr<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>)

- ea: `0x180011994`
- end: `0x180011cd1`
- name: `?GetAllTheContent@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@PEAVCAllRuns@@V?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int128 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010f28`

## callees

- `0x18000eb50`
- `0x18000fcd4`
- `0x18000fe3c`
- `0x1800103e4`
- `0x180011384`
- `0x180011994`
- `0x1800137e8`
- `0x1800156e4`
- `0x18001929c`
- `0x1800193d4`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011be7`
- `OLEAUT32!__imp_SysFreeString` at `0x180011be7`
- `OLEAUT32!__imp_SysStringLen` at `0x180011ab3`
- `OLEAUT32!__imp_SysStringLen` at `0x180011ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b96`

## string_xrefs

- `0x180011b26`: `CThreadInfo::GetAllTheContent : Failed to extract embedded images from text range, hr(0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThreadInfo::GetAllTheContent(__int64 a1, _QWORD *a2, __int64 a3, __int128 *a4)
{
  int v7; // ebx
  int v8; // r15d
  int v9; // eax
  BSTR v10; // rbx
  UINT v11; // r13d
  int v12; // ecx
  __int64 v13; // rax
  int EmbeddedImageStreams; // eax
  _BYTE *v15; // rbx
  void *v16; // rbx
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rsi
  volatile signed __int32 *v20; // rbx
  __int64 v21; // [rsp+38h] [rbp-49h] BYREF
  int v22; // [rsp+40h] [rbp-41h] BYREF
  int v23; // [rsp+44h] [rbp-3Dh] BYREF
  unsigned int v24; // [rsp+48h] [rbp-39h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-31h] BYREF
  __int128 v26; // [rsp+58h] [rbp-29h] BYREF
  _BYTE v27[8]; // [rsp+68h] [rbp-19h] BYREF
  _BYTE v28[48]; // [rsp+70h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+1Fh]
  __int64 v30; // [rsp+E8h] [rbp+67h] BYREF
  int v31; // [rsp+F8h] [rbp+77h] BYREF
  __int128 *v32; // [rsp+100h] [rbp+7Fh]

  v32 = a4;
  v30 = a1;
  if ( a3 && *(_QWORD *)a4 )
  {
    v31 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 72LL))(*a2, &v31);
    if ( v7 < 0 )
      goto LABEL_30;
    if ( v31 == 1 )
    {
      v21 = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)*a2 + 192LL))(*a2, 0, 0, &v21);
      if ( v7 >= 0 )
      {
        v22 = 0;
        v8 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 176LL))(v21, &v22);
        while ( 1 )
        {
          v7 = v9;
          if ( v9 < 0 )
            break;
          if ( v8 >= v22 )
          {
            if ( *(_DWORD *)(a3 + 8) )
            {
              v7 = 0;
              *(_QWORD *)(a3 + 24) = 0;
              *(_DWORD *)(a3 + 8) = 0;
              *(_QWORD *)(a3 + 16) = 0;
            }
            else
            {
              v7 = -2147467259;
            }
            break;
          }
          LODWORD(v30) = 0;
          v24 = 0;
          v7 = IAdvancedTextRange::MoveEndForLCID((IAdvancedTextRange *)&v21, v8, v22, (int *)&v30, (int *)&v24);
          if ( v7 < 0 )
            break;
          pbstr = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 56LL))(v21, &pbstr);
          if ( v7 < 0 )
            break;
          v10 = pbstr;
          v11 = SysStringLen(pbstr);
          v23 = 0;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 112LL))(v21, &v23);
          v26 = 0;
          v13 = *((_QWORD *)a4 + 1);
          if ( v13 )
            _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
          v26 = *a4;
          EmbeddedImageStreams = CThreadInfo::GetEmbeddedImageStreams(
                                   v12,
                                   (_DWORD)a2,
                                   v23,
                                   v11,
                                   (__int64)v10,
                                   (__int64)&v26);
          if ( EmbeddedImageStreams < 0 )
          {
            SearchIndexerTrace::Error(
              (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\rtf\\rtffilt\\lib\\rtffilt.cxx",
              (const wchar_t *)0x3CA,
              (unsigned int)L"CThreadInfo::GetAllTheContent : Failed to extract embedded images from text range, hr(0x%08x)",
              (const wchar_t *)(unsigned int)EmbeddedImageStreams);
            tip2::open_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>>(v27);
            v15 = pv;
            *(_QWORD *)&v26 = pv;
            if ( pv )
              _InterlockedIncrement((volatile signed __int32 *)pv + 70);
            tip2::details::shared_data<1,0,0>::begin_update(v15 + 8);
            v15[273] = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(&v26);
            v16 = pv;
            if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 70, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(v16);
              CoTaskMemFree(v16);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v28);
          }
          v7 = CAllRuns::Add((CAllRuns *)a3, v30, pbstr, v24);
          if ( v7 < 0 )
          {
            SysFreeString(pbstr);
            break;
          }
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 192LL))(v21, 0);
          v8 += v30;
        }
      }
      v17 = v21;
      v21 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v7 < 0 )
LABEL_30:
        v7 = -2147215613;
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)a4 + 1);
    if ( v18 && _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
    return (unsigned int)v7;
  }
  else
  {
    v20 = (volatile signed __int32 *)*((_QWORD *)a4 + 1);
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    return 2147751683LL;
  }
}

```

## disassembly

```asm
0x180011994  mov     rax, rsp
0x180011997  mov     [rax+10h], rbx
0x18001199b  mov     [rax+20h], r9
0x18001199f  mov     [rax+8], rcx
0x1800119a3  push    rbp
0x1800119a4  push    rsi
0x1800119a5  push    rdi
0x1800119a6  push    r12
0x1800119a8  push    r13
0x1800119aa  push    r14
0x1800119ac  push    r15
0x1800119ae  lea     rbp, [rax-5Fh]
0x1800119b2  sub     rsp, 0A0h
0x1800119b9  mov     r14, r9
0x1800119bc  mov     rsi, r8
0x1800119bf  mov     r12, rdx
0x1800119c2  xor     r13d, r13d
0x1800119c5  test    r8, r8
0x1800119c8  jz      loc_180011C72
0x1800119ce  cmp     [r9], r13
0x1800119d1  jz      loc_180011C72
0x1800119d7  mov     [rbp+57h+arg_10], r13d
0x1800119db  mov     rcx, [rdx]
0x1800119de  mov     rax, [rcx]
0x1800119e1  lea     rdx, [rbp+57h+arg_10]
0x1800119e5  mov     rax, [rax+48h]
0x1800119e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ee  mov     ebx, eax
0x1800119f0  or      edi, 0FFFFFFFFh
0x1800119f3  test    eax, eax
0x1800119f5  js      loc_180011C2D
0x1800119fb  cmp     [rbp+57h+arg_10], 1
0x1800119ff  jnz     loc_180011C32
0x180011a05  mov     [rbp+57h+var_A0], r13
0x180011a09  mov     rcx, [r12]
0x180011a0d  mov     rax, [rcx]
0x180011a10  lea     r9, [rbp+57h+var_A0]
0x180011a14  xor     r8d, r8d
0x180011a17  xor     edx, edx
0x180011a19  mov     rax, [rax+0C0h]
0x180011a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a25  mov     ebx, eax
0x180011a27  test    eax, eax
0x180011a29  js      loc_180011C0F
0x180011a2f  mov     [rbp+57h+var_98], r13d
0x180011a33  mov     r15d, r13d
0x180011a36  mov     rcx, [rbp+57h+var_A0]
0x180011a3a  mov     rax, [rcx]
0x180011a3d  lea     rdx, [rbp+57h+var_98]
0x180011a41  mov     rax, [rax+0B0h]
0x180011a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a4d  jmp     loc_180011BD7
0x180011a52  mov     r8d, [rbp+57h+var_98]; int
0x180011a56  cmp     r15d, r8d
0x180011a59  jge     loc_180011BEF
0x180011a5f  mov     dword ptr [rbp+57h+arg_0], r13d
0x180011a63  mov     [rbp+57h+var_90], r13d
0x180011a67  lea     rax, [rbp+57h+var_90]
0x180011a6b  mov     [rsp+0D0h+var_B0], rax; int *
0x180011a70  lea     r9, [rbp+57h+arg_0]; int *
0x180011a74  mov     edx, r15d; int
0x180011a77  lea     rcx, [rbp+57h+var_A0]; this
0x180011a7b  call    ?MoveEndForLCID@IAdvancedTextRange@@QEAAJJJPEAJ0@Z; IAdvancedTextRange::MoveEndForLCID(long,long,long *,long *)
0x180011a80  mov     ebx, eax
0x180011a82  test    eax, eax
0x180011a84  js      loc_180011C0F
0x180011a8a  mov     [rbp+57h+pbstr], r13
0x180011a8e  mov     rcx, [rbp+57h+var_A0]
0x180011a92  mov     rax, [rcx]
0x180011a95  lea     rdx, [rbp+57h+pbstr]
0x180011a99  mov     rax, [rax+38h]
0x180011a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aa2  mov     ebx, eax
0x180011aa4  test    eax, eax
0x180011aa6  js      loc_180011C0F
0x180011aac  mov     rbx, [rbp+57h+pbstr]
0x180011ab0  mov     rcx, rbx; pbstr
0x180011ab3  call    cs:__imp_SysStringLen
0x180011ab9  mov     r13d, eax
0x180011abc  mov     [rbp+57h+var_94], 0
0x180011ac3  mov     rcx, [rbp+57h+var_A0]
0x180011ac7  mov     rdx, [rcx]
0x180011aca  mov     rax, [rdx+70h]
0x180011ace  lea     rdx, [rbp+57h+var_94]
0x180011ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ad7  xorps   xmm0, xmm0
0x180011ada  movdqu  [rbp+57h+var_80], xmm0
0x180011adf  mov     rax, [r14+8]
0x180011ae3  test    rax, rax
0x180011ae6  jz      short loc_180011AEC
0x180011ae8  lock inc dword ptr [rax+8]
0x180011aec  mov     rax, [r14]
0x180011aef  mov     qword ptr [rbp+57h+var_80], rax
0x180011af3  mov     rax, [r14+8]
0x180011af7  mov     qword ptr [rbp+57h+var_80+8], rax
0x180011afb  lea     rax, [rbp+57h+var_80]
0x180011aff  mov     [rsp+28h], rax
0x180011b04  mov     [rsp+0D0h+var_B0], rbx
0x180011b09  mov     r9d, r13d
0x180011b0c  mov     r8d, [rbp+57h+var_94]
0x180011b10  mov     rdx, r12
0x180011b13  call    ?GetEmbeddedImageStreams@CThreadInfo@@AEAAJAEAV?$XInterface@UITextDocument@@@@JJPEB_WV?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@@Z; CThreadInfo::GetEmbeddedImageStreams(XInterface<ITextDocument> &,long,long,wchar_t const *,std::shared_ptr<std::vector<winrt::com_ptr<IStream>>>)
0x180011b18  xor     r13d, r13d
0x180011b1b  test    eax, eax
0x180011b1d  jns     loc_180011BA5
0x180011b23  mov     r9d, eax; wchar_t *
0x180011b26  lea     r8, aCthreadinfoGet; "CThreadInfo::GetAllTheContent : Failed "...
0x180011b2d  mov     edx, 3CAh; wchar_t *
0x180011b32  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180011b39  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180011b3e  lea     rcx, [rbp+57h+var_70]
0x180011b42  call    ??$open_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180011b47  mov     rbx, [rbp+57h+pv]
0x180011b4b  mov     qword ptr [rbp+57h+var_80], rbx
0x180011b4f  test    rbx, rbx
0x180011b52  jz      short loc_180011B5B
0x180011b54  lock inc dword ptr [rbx+118h]
0x180011b5b  lea     rcx, [rbx+8]
0x180011b5f  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180011b64  mov     byte ptr [rbx+111h], 1
0x180011b6b  lea     rcx, [rbp+57h+var_80]
0x180011b6f  call    ??1?$test_data_control@V?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>::~test_data_control<tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>>(void)
0x180011b74  mov     rbx, [rbp+57h+pv]
0x180011b78  test    rbx, rbx
0x180011b7b  jz      short loc_180011B9C
0x180011b7d  mov     eax, edi
0x180011b7f  lock xadd [rbx+118h], eax
0x180011b87  add     eax, edi
0x180011b89  jnz     short loc_180011B9C
0x180011b8b  mov     rcx, rbx
0x180011b8e  call    ??1?$merged_data@U_tip_RtfFilterContentExtractionTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>::~merged_data<_tip_RtfFilterContentExtractionTipTest,_tip_RtfFilterContentExtractionTipTest>(void)
0x180011b93  mov     rcx, rbx; pv
0x180011b96  call    cs:__imp_CoTaskMemFree
0x180011b9c  lea     rcx, [rbp+57h+var_68]; this
0x180011ba0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180011ba5  mov     r9d, [rbp+57h+var_90]; unsigned int
0x180011ba9  mov     r8, [rbp+57h+pbstr]; wchar_t *
0x180011bad  mov     edx, dword ptr [rbp+57h+arg_0]; int
0x180011bb0  mov     rcx, rsi; this
0x180011bb3  call    ?Add@CAllRuns@@QEAAJJPEA_WK@Z; CAllRuns::Add(long,wchar_t *,ulong)
0x180011bb8  mov     ebx, eax
0x180011bba  test    eax, eax
0x180011bbc  js      short loc_180011BE3
0x180011bbe  mov     rcx, [rbp+57h+var_A0]
0x180011bc2  mov     rax, [rcx]
0x180011bc5  xor     edx, edx
0x180011bc7  mov     rax, [rax+0C0h]
0x180011bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bd3  add     r15d, dword ptr [rbp+57h+arg_0]
0x180011bd7  test    eax, eax
0x180011bd9  mov     ebx, eax
0x180011bdb  jns     loc_180011A52
0x180011be1  jmp     short loc_180011C0F
0x180011be3  mov     rcx, [rbp+57h+pbstr]; bstrString
0x180011be7  call    cs:__imp_SysFreeString
0x180011bed  jmp     short loc_180011C0F
0x180011bef  cmp     [rsi+8], r13d
0x180011bf3  jz      short loc_180011C0A
0x180011bf5  mov     ebx, r13d
0x180011bf8  mov     qword ptr [rsi+18h], 0
0x180011c00  mov     [rsi+8], r13d
0x180011c04  mov     [rsi+10h], r13
0x180011c08  jmp     short loc_180011C0F
0x180011c0a  mov     ebx, 80004005h
0x180011c0f  mov     rcx, [rbp+57h+var_A0]
0x180011c13  mov     [rbp+57h+var_A0], r13
0x180011c17  test    rcx, rcx
0x180011c1a  jz      short loc_180011C29
0x180011c1c  mov     rax, [rcx]
0x180011c1f  mov     rax, [rax+10h]
0x180011c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c28  nop
0x180011c29  test    ebx, ebx
0x180011c2b  jns     short loc_180011C32
0x180011c2d  mov     ebx, 80041703h
0x180011c32  mov     rsi, [r14+8]
0x180011c36  test    rsi, rsi
0x180011c39  jz      short loc_180011C6E
0x180011c3b  mov     eax, edi
0x180011c3d  lock xadd [rsi+8], eax
0x180011c42  add     eax, edi
0x180011c44  jnz     short loc_180011C6E
0x180011c46  mov     rax, [rsi]
0x180011c49  mov     rcx, rsi
0x180011c4c  mov     rax, [rax]
0x180011c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c54  mov     eax, edi
0x180011c56  lock xadd [rsi+0Ch], eax
0x180011c5b  add     eax, edi
0x180011c5d  jnz     short loc_180011C6E
0x180011c5f  mov     rax, [rsi]
0x180011c62  mov     rcx, rsi
0x180011c65  mov     rax, [rax+8]
0x180011c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c6e  mov     eax, ebx
0x180011c70  jmp     short loc_180011CB6
0x180011c72  mov     rbx, [r9+8]
0x180011c76  test    rbx, rbx
0x180011c79  jz      short loc_180011CB1
0x180011c7b  or      edi, 0FFFFFFFFh
0x180011c7e  mov     eax, edi
0x180011c80  lock xadd [rbx+8], eax
0x180011c85  add     eax, edi
0x180011c87  jnz     short loc_180011CB1
0x180011c89  mov     rax, [rbx]
0x180011c8c  mov     rcx, rbx
0x180011c8f  mov     rax, [rax]
0x180011c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c97  mov     eax, edi
0x180011c99  lock xadd [rbx+0Ch], eax
0x180011c9e  add     eax, edi
0x180011ca0  jnz     short loc_180011CB1
0x180011ca2  mov     rax, [rbx]
0x180011ca5  mov     rcx, rbx
0x180011ca8  mov     rax, [rax+8]
0x180011cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb1  mov     eax, 80041703h
0x180011cb6  mov     rbx, [rsp+0D0h+arg_8]
0x180011cbe  add     rsp, 0A0h
0x180011cc5  pop     r15
0x180011cc7  pop     r14
0x180011cc9  pop     r13
0x180011ccb  pop     r12
0x180011ccd  pop     rdi
0x180011cce  pop     rsi
0x180011ccf  pop     rbp
0x180011cd0  retn
```
