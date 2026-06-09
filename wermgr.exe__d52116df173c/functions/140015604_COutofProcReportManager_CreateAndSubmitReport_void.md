# COutofProcReportManager::CreateAndSubmitReport(void)

- ea: `0x140015604`
- end: `0x140015a89`
- name: `?CreateAndSubmitReport@COutofProcReportManager@@AEAAJXZ`
- size: `1157`
- prototype: `__int64 __fastcall(COutofProcReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140015a90`

## callees

- `0x140002fbc`
- `0x140003224`
- `0x140003230`
- `0x14000e318`
- `0x14000e340`
- `0x14001533c`
- `0x140015604`
- `0x1400170a4`
- `0x14001c9a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001574c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x14001574c`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x140015971`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x140015971`
- `wer!WerReportCloseHandle` at `0x14001565d`
- `wer!WerReportCloseHandle` at `0x14001565d`
- `wer!WerReportSubmit` at `0x1400159f8`
- `wer!WerReportSubmit` at `0x1400159f8`
- `wer!WerpSetCallBack` at `0x14001590d`
- `wer!WerpSetCallBack` at `0x14001590d`
- `wer!WerpGetReportInformation` at `0x140015820`
- `wer!WerpGetReportInformation` at `0x140015820`
- `wer!WerpGetReportType` at `0x1400157e1`
- `wer!WerpGetReportType` at `0x1400157e1`
- `wer!WerpGetReportSettings` at `0x1400156e1`
- `wer!WerpGetReportSettings` at `0x1400156e1`
- `wer!WerpLoadReportFromBuffer` at `0x14001567a`
- `wer!WerpLoadReportFromBuffer` at `0x14001567a`
- `wer!WerpSetReportInformation` at `0x1400158c9`
- `wer!WerpSetReportInformation` at `0x1400158c9`

## pseudocode

```c
__int64 __fastcall COutofProcReportManager::CreateAndSubmitReport(COutofProcReportManager *this)
{
  _QWORD *v2; // r15
  HREPORT *v3; // r14
  void *v4; // rcx
  HRESULT ReportFromBuffer; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // ecx
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  DWORD v15; // ebx
  int RestartCommandLine; // eax
  bool v17; // zf
  void *Src; // [rsp+30h] [rbp-D0h] BYREF
  APPLICATION_RECOVERY_CALLBACK pRecoveryCallback; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[2552]; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+A50h] [rbp+950h] BYREF
  int v24; // [rsp+A58h] [rbp+958h] BYREF
  int v25; // [rsp+A60h] [rbp+960h] BYREF
  __int64 v26; // [rsp+A68h] [rbp+968h] BYREF

  pRecoveryCallback = 0;
  v2 = 0;
  v21 = 0;
  v24 = 0;
  Src = 0;
  v23 = 0;
  v26 = 0;
  v3 = (HREPORT *)((char *)this + 8272);
  v4 = (void *)*((_QWORD *)this + 1034);
  *v3 = 0;
  if ( v4 )
    WerReportCloseHandle(v4);
  ReportFromBuffer = WerpLoadReportFromBuffer(*((_QWORD *)this + 4) + 2624LL, *((unsigned int *)this + 2066), v3, 0);
  if ( ReportFromBuffer < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 12;
LABEL_7:
      WPP_SF_d(v6[2], v7, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids, (unsigned int)ReportFromBuffer);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( !*((_DWORD *)this + 2071) )
  {
LABEL_23:
    COutofProcReportManager::AddSingleDumpToReport(this, (struct OO_PROC_DUMP_DATA *)(*((_QWORD *)this + 4) + 664LL));
    COutofProcReportManager::AddSingleDumpToReport(this, (struct OO_PROC_DUMP_DATA *)(*((_QWORD *)this + 4) + 24LL));
    COutofProcReportManager::AddSingleDumpToReport(this, (struct OO_PROC_DUMP_DATA *)(*((_QWORD *)this + 4) + 1304LL));
    COutofProcReportManager::AddSingleDumpToReport(this, (struct OO_PROC_DUMP_DATA *)(*((_QWORD *)this + 4) + 1944LL));
    ReportFromBuffer = WerpGetReportType(*v3, &v23);
    if ( ReportFromBuffer < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 16;
        goto LABEL_7;
      }
      goto LABEL_62;
    }
    ReportFromBuffer = WerpGetReportInformation(*v3, &Src);
    if ( ReportFromBuffer < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 17;
        goto LABEL_7;
      }
      goto LABEL_62;
    }
    v12 = operator new(0x9C8u, (const struct std::nothrow_t *)&std::nothrow);
    v2 = v12;
    if ( !v12 )
    {
      v2 = 0;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v11 = 18;
LABEL_61:
      WPP_SF_(v10[2], v11, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids);
      goto LABEL_62;
    }
    memset_0(v12, 0, 0x9C8u);
    v21 = v2;
    memcpy_0(v22, Src, 0x9C8u);
    memcpy_0(v2, v22, 0x9C8u);
    v2[1] = *((_QWORD *)this + 1031);
    v2[275] = *(_QWORD *)(*((_QWORD *)this + 4) + 2600LL);
    ReportFromBuffer = WerpSetReportInformation(*v3, v2);
    if ( ReportFromBuffer < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 19;
        goto LABEL_7;
      }
      goto LABEL_62;
    }
    ReportFromBuffer = WerpSetCallBack(*v3, COutofProcReportManager::Static_WerCallbackFunction, this);
    if ( ReportFromBuffer < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 20;
        goto LABEL_7;
      }
      goto LABEL_62;
    }
    v14 = *((_QWORD *)this + 4);
    v15 = *(_DWORD *)(v14 + 2596) & 0xFFFFFFDF;
    if ( (*(_BYTE *)(v14 + 2596) & 1) != 0
      && (GetApplicationRecoveryCallback(*((HANDLE *)this + 1031), &pRecoveryCallback, 0, 0, 0) || !pRecoveryCallback) )
    {
      v15 &= ~1u;
    }
    if ( (v15 & 2) != 0 )
    {
      v25 = 0;
      RestartCommandLine = WerpGetRestartCommandLine(*((_QWORD *)this + 1031), v13, &v25, &v24);
      if ( RestartCommandLine != -2147024774 )
      {
        if ( RestartCommandLine )
          goto LABEL_52;
      }
      if ( v23 == 2 )
      {
        v17 = (v24 & 1) == 0;
      }
      else
      {
        if ( v23 != 3 )
          goto LABEL_53;
        v17 = (v24 & 2) == 0;
      }
      if ( !v17 )
LABEL_52:
        v15 &= ~2u;
    }
LABEL_53:
    ReportFromBuffer = WerReportSubmit(
                         *v3,
                         *(WER_CONSENT *)(*((_QWORD *)this + 4) + 2592LL),
                         v15,
                         (PWER_SUBMIT_RESULT)(*((_QWORD *)this + 4) + 2616LL));
    *(_DWORD *)(*((_QWORD *)this + 4) + 2612LL) = ReportFromBuffer;
    if ( ReportFromBuffer >= 0 )
    {
      ReportFromBuffer = 0;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 21;
        goto LABEL_7;
      }
    }
    goto LABEL_62;
  }
  ReportFromBuffer = WerpGetReportSettings(*v3, &v26);
  if ( ReportFromBuffer >= 0 )
  {
    if ( !*(_BYTE *)(v26 + 2288)
      || ((v8 = *(_DWORD *)(v26 + 2292)) != 0
        ? (v8 != 1
         ? (v9 = *(_DWORD *)(v26 + 2384))
         : (v9 = wcstol(*(const wchar_t **)(v26 + 2296), 0, 10)))
        : (v9 = **(_DWORD **)(v26 + 2296)),
          !v9) )
    {
      ReportFromBuffer = -2147024891;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v11 = 14;
      goto LABEL_61;
    }
    goto LABEL_23;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 13;
    goto LABEL_7;
  }
LABEL_62:
  if ( v2 )
    operator delete(v2, (const struct std::nothrow_t *)0x9C8);
  return (unsigned int)ReportFromBuffer;
}

```

## disassembly

```asm
0x140015604  push    rbp
0x140015606  push    rbx
0x140015607  push    rsi
0x140015608  push    r13
0x14001560a  push    r14
0x14001560c  push    r15
0x14001560e  lea     rbp, [rsp-918h]
0x140015616  sub     rsp, 0A18h
0x14001561d  mov     rsi, rcx
0x140015620  mov     [rsp+0A40h+pRecoveryCallback], 0
0x140015629  xor     r15d, r15d
0x14001562c  mov     [rsp+0A40h+var_A00], r15
0x140015631  mov     [rbp+940h+arg_8], r15d
0x140015638  mov     [rsp+0A40h+Src], r15
0x14001563d  mov     [rbp+940h+arg_0], r15d
0x140015644  mov     [rbp+940h+arg_18], r15
0x14001564b  lea     r14, [rcx+2050h]
0x140015652  mov     rcx, [r14]; hReportHandle
0x140015655  mov     [r14], r15
0x140015658  test    rcx, rcx
0x14001565b  jz      short loc_140015663
0x14001565d  call    cs:__imp_WerReportCloseHandle
0x140015663  mov     rcx, [rsi+20h]
0x140015667  add     rcx, 0A40h
0x14001566e  xor     r9d, r9d
0x140015671  mov     r8, r14
0x140015674  mov     edx, [rsi+2048h]
0x14001567a  call    cs:__imp_WerpLoadReportFromBuffer
0x140015680  mov     ebx, eax
0x140015682  mov     r13d, 9C8h
0x140015688  test    eax, eax
0x14001568a  jns     short loc_1400156CA
0x14001568c  lea     rax, WPP_GLOBAL_Control
0x140015693  mov     rcx, cs:WPP_GLOBAL_Control
0x14001569a  cmp     rcx, rax
0x14001569d  jz      loc_140015A66
0x1400156a3  test    byte ptr [rcx+1Ch], 1
0x1400156a7  jz      loc_140015A66
0x1400156ad  mov     edx, 0Ch
0x1400156b2  mov     r9d, ebx
0x1400156b5  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x1400156bc  mov     rcx, [rcx+10h]
0x1400156c0  call    WPP_SF_d
0x1400156c5  jmp     loc_140015A66
0x1400156ca  cmp     dword ptr [rsi+205Ch], 0
0x1400156d1  jz      loc_14001578E
0x1400156d7  lea     rdx, [rbp+940h+arg_18]
0x1400156de  mov     rcx, [r14]
0x1400156e1  call    cs:__imp_WerpGetReportSettings
0x1400156e7  mov     ebx, eax
0x1400156e9  test    eax, eax
0x1400156eb  jns     short loc_140015715
0x1400156ed  lea     rax, WPP_GLOBAL_Control
0x1400156f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156fb  cmp     rcx, rax
0x1400156fe  jz      loc_140015A66
0x140015704  test    byte ptr [rcx+1Ch], 1
0x140015708  jz      loc_140015A66
0x14001570e  mov     edx, 0Dh
0x140015713  jmp     short loc_1400156B2
0x140015715  mov     rax, [rbp+940h+arg_18]
0x14001571c  cmp     byte ptr [rax+8F0h], 0
0x140015723  jz      short loc_14001575E
0x140015725  mov     ecx, [rax+8F4h]
0x14001572b  test    ecx, ecx
0x14001572d  jnz     short loc_14001573A
0x14001572f  mov     rax, [rax+8F8h]
0x140015736  mov     eax, [rax]
0x140015738  jmp     short loc_14001575A
0x14001573a  cmp     ecx, 1
0x14001573d  jnz     short loc_140015754
0x14001573f  xor     edx, edx; EndPtr
0x140015741  lea     r8d, [rcx+9]; Radix
0x140015745  mov     rcx, [rax+8F8h]; String
0x14001574c  call    cs:__imp_wcstol
0x140015752  jmp     short loc_14001575A
0x140015754  mov     eax, [rax+950h]
0x14001575a  test    eax, eax
0x14001575c  jnz     short loc_14001578E
0x14001575e  mov     ebx, 80070005h
0x140015763  lea     rax, WPP_GLOBAL_Control
0x14001576a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015771  cmp     rcx, rax
0x140015774  jz      loc_140015A66
0x14001577a  test    byte ptr [rcx+1Ch], 1
0x14001577e  jz      loc_140015A66
0x140015784  mov     edx, 0Eh
0x140015789  jmp     loc_140015A55
0x14001578e  mov     rdx, [rsi+20h]
0x140015792  add     rdx, 298h; struct OO_PROC_DUMP_DATA *
0x140015799  mov     rcx, rsi; this
0x14001579c  call    ?AddSingleDumpToReport@COutofProcReportManager@@AEAAJPEAUOO_PROC_DUMP_DATA@@@Z; COutofProcReportManager::AddSingleDumpToReport(OO_PROC_DUMP_DATA *)
0x1400157a1  mov     rdx, [rsi+20h]
0x1400157a5  add     rdx, 18h; struct OO_PROC_DUMP_DATA *
0x1400157a9  mov     rcx, rsi; this
0x1400157ac  call    ?AddSingleDumpToReport@COutofProcReportManager@@AEAAJPEAUOO_PROC_DUMP_DATA@@@Z; COutofProcReportManager::AddSingleDumpToReport(OO_PROC_DUMP_DATA *)
0x1400157b1  mov     rdx, [rsi+20h]
0x1400157b5  add     rdx, 518h; struct OO_PROC_DUMP_DATA *
0x1400157bc  mov     rcx, rsi; this
0x1400157bf  call    ?AddSingleDumpToReport@COutofProcReportManager@@AEAAJPEAUOO_PROC_DUMP_DATA@@@Z; COutofProcReportManager::AddSingleDumpToReport(OO_PROC_DUMP_DATA *)
0x1400157c4  mov     rdx, [rsi+20h]
0x1400157c8  add     rdx, 798h; struct OO_PROC_DUMP_DATA *
0x1400157cf  mov     rcx, rsi; this
0x1400157d2  call    ?AddSingleDumpToReport@COutofProcReportManager@@AEAAJPEAUOO_PROC_DUMP_DATA@@@Z; COutofProcReportManager::AddSingleDumpToReport(OO_PROC_DUMP_DATA *)
0x1400157d7  lea     rdx, [rbp+940h+arg_0]
0x1400157de  mov     rcx, [r14]
0x1400157e1  call    cs:__imp_WerpGetReportType
0x1400157e7  mov     ebx, eax
0x1400157e9  test    eax, eax
0x1400157eb  jns     short loc_140015818
0x1400157ed  lea     rax, WPP_GLOBAL_Control
0x1400157f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157fb  cmp     rcx, rax
0x1400157fe  jz      loc_140015A66
0x140015804  test    byte ptr [rcx+1Ch], 1
0x140015808  jz      loc_140015A66
0x14001580e  mov     edx, 10h
0x140015813  jmp     loc_1400156B2
0x140015818  lea     rdx, [rsp+0A40h+Src]
0x14001581d  mov     rcx, [r14]
0x140015820  call    cs:__imp_WerpGetReportInformation
0x140015826  mov     ebx, eax
0x140015828  test    eax, eax
0x14001582a  jns     short loc_140015857
0x14001582c  lea     rax, WPP_GLOBAL_Control
0x140015833  mov     rcx, cs:WPP_GLOBAL_Control
0x14001583a  cmp     rcx, rax
0x14001583d  jz      loc_140015A66
0x140015843  test    byte ptr [rcx+1Ch], 1
0x140015847  jz      loc_140015A66
0x14001584d  mov     edx, 11h
0x140015852  jmp     loc_1400156B2
0x140015857  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001585e  mov     rcx, r13; unsigned __int64
0x140015861  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140015866  mov     r15, rax
0x140015869  test    rax, rax
0x14001586c  jz      loc_140015A35
0x140015872  mov     r8, r13; Size
0x140015875  xor     edx, edx; Val
0x140015877  mov     rcx, rax; void *
0x14001587a  call    memset_0
0x14001587f  mov     [rsp+0A40h+var_A00], r15
0x140015884  lea     rcx, [rsp+0A40h+var_9F8]; void *
0x140015889  mov     rdx, [rsp+0A40h+Src]; Src
0x14001588e  mov     r8, r13; Size
0x140015891  call    memcpy_0
0x140015896  mov     rcx, r15; void *
0x140015899  lea     rdx, [rsp+0A40h+var_9F8]; Src
0x14001589e  mov     r8, r13; Size
0x1400158a1  call    memcpy_0
0x1400158a6  mov     rax, [rsi+2038h]
0x1400158ad  mov     [r15+8], rax
0x1400158b1  mov     rax, [rsi+20h]
0x1400158b5  mov     rcx, [rax+0A28h]
0x1400158bc  mov     [r15+898h], rcx
0x1400158c3  mov     rdx, r15
0x1400158c6  mov     rcx, [r14]
0x1400158c9  call    cs:__imp_WerpSetReportInformation
0x1400158cf  mov     ebx, eax
0x1400158d1  test    eax, eax
0x1400158d3  jns     short loc_140015900
0x1400158d5  lea     rax, WPP_GLOBAL_Control
0x1400158dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400158e3  cmp     rcx, rax
0x1400158e6  jz      loc_140015A66
0x1400158ec  test    byte ptr [rcx+1Ch], 1
0x1400158f0  jz      loc_140015A66
0x1400158f6  mov     edx, 13h
0x1400158fb  jmp     loc_1400156B2
0x140015900  mov     r8, rsi
0x140015903  lea     rdx, ?Static_WerCallbackFunction@COutofProcReportManager@@CAHPEAXQEAU_WER_CALLBACK_INPUT@@@Z; COutofProcReportManager::Static_WerCallbackFunction(void *,_WER_CALLBACK_INPUT * const)
0x14001590a  mov     rcx, [r14]
0x14001590d  call    cs:__imp_WerpSetCallBack
0x140015913  mov     ebx, eax
0x140015915  test    eax, eax
0x140015917  jns     short loc_140015944
0x140015919  lea     rax, WPP_GLOBAL_Control
0x140015920  mov     rcx, cs:WPP_GLOBAL_Control
0x140015927  cmp     rcx, rax
0x14001592a  jz      loc_140015A66
0x140015930  test    byte ptr [rcx+1Ch], 1
0x140015934  jz      loc_140015A66
0x14001593a  mov     edx, 14h
0x14001593f  jmp     loc_1400156B2
0x140015944  mov     rax, [rsi+20h]
0x140015948  mov     ebx, [rax+0A24h]
0x14001594e  and     ebx, 0FFFFFFDFh
0x140015951  test    bl, 1
0x140015954  jz      short loc_140015986
0x140015956  mov     [rsp+0A40h+pdwFlags], 0; pdwFlags
0x14001595f  xor     r9d, r9d; pdwPingInterval
0x140015962  xor     r8d, r8d; ppvParameter
0x140015965  lea     rdx, [rsp+0A40h+pRecoveryCallback]; pRecoveryCallback
0x14001596a  mov     rcx, [rsi+2038h]; hProcess
0x140015971  call    cs:__imp_GetApplicationRecoveryCallback
0x140015977  test    eax, eax
0x140015979  jnz     short loc_140015983
0x14001597b  cmp     [rsp+0A40h+pRecoveryCallback], 0
0x140015981  jnz     short loc_140015986
0x140015983  and     ebx, 0FFFFFFFEh
0x140015986  test    bl, 2
0x140015989  jz      short loc_1400159E1
0x14001598b  mov     [rbp+940h+arg_10], 0
0x140015995  lea     r9, [rbp+940h+arg_8]
0x14001599c  lea     r8, [rbp+940h+arg_10]
0x1400159a3  mov     rcx, [rsi+2038h]
0x1400159aa  call    WerpGetRestartCommandLine
0x1400159af  cmp     eax, 8007007Ah
0x1400159b4  jz      short loc_1400159BA
0x1400159b6  test    eax, eax
0x1400159b8  jnz     short loc_1400159DE
0x1400159ba  cmp     [rbp+940h+arg_0], 2
0x1400159c1  jnz     short loc_1400159CC
0x1400159c3  test    byte ptr [rbp+940h+arg_8], 1
0x1400159ca  jmp     short loc_1400159DC
0x1400159cc  cmp     [rbp+940h+arg_0], 3
0x1400159d3  jnz     short loc_1400159E1
0x1400159d5  test    byte ptr [rbp+940h+arg_8], 2
0x1400159dc  jz      short loc_1400159E1
0x1400159de  and     ebx, 0FFFFFFFDh
0x1400159e1  mov     rdx, [rsi+20h]
0x1400159e5  lea     r9, [rdx+0A38h]; pSubmitResult
0x1400159ec  mov     r8d, ebx; dwFlags
0x1400159ef  mov     edx, [rdx+0A20h]; consent
0x1400159f5  mov     rcx, [r14]; hReportHandle
0x1400159f8  call    cs:__imp_WerReportSubmit
0x1400159fe  mov     ebx, eax
0x140015a00  mov     rax, [rsi+20h]
0x140015a04  mov     [rax+0A34h], ebx
0x140015a0a  test    ebx, ebx
0x140015a0c  jns     short loc_140015A31
0x140015a0e  lea     rax, WPP_GLOBAL_Control
0x140015a15  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a1c  cmp     rcx, rax
0x140015a1f  jz      short loc_140015A66
0x140015a21  test    byte ptr [rcx+1Ch], 1
0x140015a25  jz      short loc_140015A66
0x140015a27  mov     edx, 15h
0x140015a2c  jmp     loc_1400156B2
0x140015a31  xor     ebx, ebx
0x140015a33  jmp     short loc_140015A66
0x140015a35  xor     r15d, r15d
0x140015a38  lea     rax, WPP_GLOBAL_Control
0x140015a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a46  cmp     rcx, rax
0x140015a49  jz      short loc_140015A66
0x140015a4b  test    byte ptr [rcx+1Ch], 1
0x140015a4f  jz      short loc_140015A66
0x140015a51  lea     edx, [r15+12h]
0x140015a55  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x140015a5c  mov     rcx, [rcx+10h]
0x140015a60  call    WPP_SF_
0x140015a65  nop
0x140015a66  test    r15, r15
0x140015a69  jz      short loc_140015A76
0x140015a6b  mov     rdx, r13; struct std::nothrow_t *
0x140015a6e  mov     rcx, r15; void *
0x140015a71  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015a76  mov     eax, ebx
0x140015a78  add     rsp, 0A18h
0x140015a7f  pop     r15
0x140015a81  pop     r14
0x140015a83  pop     r13
0x140015a85  pop     rsi
0x140015a86  pop     rbx
0x140015a87  pop     rbp
0x140015a88  retn
```
