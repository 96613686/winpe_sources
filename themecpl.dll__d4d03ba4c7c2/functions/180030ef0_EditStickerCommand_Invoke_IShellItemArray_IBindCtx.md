# EditStickerCommand::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x180030ef0`
- end: `0x18003121e`
- name: `?Invoke@EditStickerCommand@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(EditStickerCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002280`
- `0x180002f34`
- `0x1800116fc`
- `0x18001daf4`
- `0x18002e434`
- `0x18002eb3c`
- `0x18002f458`
- `0x18002f6f0`
- `0x18002fbdc`
- `0x18002fc48`
- `0x18002fefc`
- `0x1800309a0`
- `0x180030ef0`
- `0x180031cac`
- `0x18003485c`
- `0x180055764`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180031144`
- `SHELL32!ShellExecuteExW` at `0x180031144`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031199`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031199`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031166`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800311cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800311cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall EditStickerCommand::Invoke(
        EditStickerCommand *this,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  unsigned int v3; // r8d
  __int64 v4; // rsi
  _OWORD *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int128 *p_Src; // rbx
  __int64 v9; // rdx
  __int128 *v10; // rax
  const WCHAR *v11; // rax
  _DWORD *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  void *v14; // rbx
  int v16; // [rsp+40h] [rbp-158h] BYREF
  __int16 v17; // [rsp+44h] [rbp-154h]
  __int64 v18; // [rsp+48h] [rbp-150h] BYREF
  _BYTE v19[8]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE v20[48]; // [rsp+58h] [rbp-140h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-110h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+90h] [rbp-108h] BYREF
  __int128 Src; // [rsp+100h] [rbp-98h] BYREF
  __int64 v24; // [rsp+110h] [rbp-88h]
  unsigned __int64 v25; // [rsp+118h] [rbp-80h]
  _QWORD v26[4]; // [rsp+120h] [rbp-78h] BYREF
  _OWORD v27[2]; // [rsp+140h] [rbp-58h] BYREF
  _BYTE v28[32]; // [rsp+160h] [rbp-38h] BYREF

  v3 = *(_DWORD *)Feature_StickerApp__descriptor;
  if ( (*(_DWORD *)Feature_StickerApp__descriptor & 4) == 0 )
  {
    v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StickerApp>::GetCachedFeatureEnabledState(
                       this,
                       &v18);
    v3 = v18;
  }
  v16 = 0;
  v17 = 3;
  wil::details::ReportUsageToService(&qword_180070340, 36321507, (v3 >> 10) & 1, (v3 >> 11) & 1, &v16, 1, 3);
  CplTelemetry::BackgroundStickersContextMenuClicked<int &>();
  ++dword_180070060;
  memset_0(&pExecInfo.fMask, 0, 0x6Cu);
  pExecInfo.cbSize = 112;
  v4 = std::to_wstring(v28);
  Src = 0;
  v24 = 0;
  v25 = 0;
  v5 = operator new(0x30u);
  *(_QWORD *)&Src = v5;
  v24 = 17;
  v25 = 23;
  *v5 = *(_OWORD *)L"ms-stickereditor:";
  v5[1] = *(_OWORD *)L"ereditor:";
  *((_WORD *)v5 + 16) = aMsStickeredito[16];
  *((_WORD *)v5 + 17) = 0;
  v6 = v24;
  if ( v25 - v24 < 0xB )
  {
    v10 = (__int128 *)std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
                        &Src,
                        11);
  }
  else
  {
    v7 = v24 + 11;
    v24 += 11;
    p_Src = &Src;
    if ( v25 > 7 )
      p_Src = (__int128 *)Src;
    memmove_0((char *)p_Src + 2 * v6, L"?sessionId=", 0x16u);
    *((_WORD *)p_Src + v7) = 0;
    v10 = &Src;
  }
  v27[0] = *v10;
  v27[1] = v10[1];
  *((_QWORD *)v10 + 2) = 0;
  *((_QWORD *)v10 + 3) = 7;
  *(_WORD *)v10 = 0;
  std::wstring::wstring(v26, v9, v27, v4);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(&Src);
  std::wstring::~wstring(v28);
  v11 = (const WCHAR *)v26;
  if ( v26[3] > 7u )
    v11 = (const WCHAR *)v26[0];
  pExecInfo.lpFile = v11;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>>>((__int64)v19);
  if ( ShellExecuteExW(&pExecInfo) )
  {
    v12 = pv;
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v12[18] |= 0x300u;
    if ( *((_QWORD *)v12 + 31) )
      tip2::details::shared_data<0,0,1>::complete_helper((__int64)(v12 + 2), 2u);
    if ( v13 )
      LeaveCriticalSection(v13);
  }
  v14 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 84, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(v14);
    CoTaskMemFree(v14);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v20);
  std::wstring::~wstring(v26);
  return 0;
}

```

## disassembly

```asm
0x180030ef0  mov     [rsp+arg_0], rbx
0x180030ef5  mov     [rsp+arg_8], rsi
0x180030efa  push    rdi
0x180030efb  sub     rsp, 190h
0x180030f02  mov     rax, cs:__security_cookie
0x180030f09  xor     rax, rsp
0x180030f0c  mov     [rsp+198h+var_18], rax
0x180030f14  mov     rax, cs:Feature_StickerApp__descriptor
0x180030f1b  mov     r8d, [rax]
0x180030f1e  test    r8b, 4
0x180030f22  jnz     short loc_180030F39
0x180030f24  lea     rdx, [rsp+198h+var_150]
0x180030f29  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StickerApp@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StickerApp>::GetCachedFeatureEnabledState(void)
0x180030f2e  mov     rax, [rax]
0x180030f31  mov     [rsp+198h+var_150], rax
0x180030f36  mov     r8d, eax
0x180030f39  xor     eax, eax
0x180030f3b  mov     [rsp+198h+var_158], eax
0x180030f3f  mov     [rsp+198h+var_154], 3
0x180030f46  mov     r9d, r8d
0x180030f49  shr     r9d, 0Bh
0x180030f4d  lea     ebx, [rax+1]
0x180030f50  and     r9d, ebx
0x180030f53  shr     r8d, 0Ah
0x180030f57  and     r8d, ebx
0x180030f5a  mov     [rsp+198h+var_168], 3
0x180030f62  mov     [rsp+198h+var_170], ebx
0x180030f66  lea     rax, [rsp+198h+var_158]
0x180030f6b  mov     [rsp+198h+var_178], rax
0x180030f70  mov     edx, 22A38E3h
0x180030f75  lea     rcx, qword_180070340
0x180030f7c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180030f81  call    ??$BackgroundStickersContextMenuClicked@AEAH@CplTelemetry@@SAXAEAH@Z; CplTelemetry::BackgroundStickersContextMenuClicked<int &>(int &)
0x180030f86  add     cs:dword_180070060, ebx
0x180030f8c  xor     edx, edx; Val
0x180030f8e  lea     r8d, [rbx+6Bh]; Size
0x180030f92  lea     rcx, [rsp+198h+pExecInfo.fMask]; void *
0x180030f9a  call    memset_0
0x180030f9f  mov     [rsp+198h+pExecInfo.cbSize], 70h ; 'p'
0x180030faa  lea     rcx, [rsp+198h+var_38]
0x180030fb2  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180030fb7  mov     rsi, rax
0x180030fba  xorps   xmm0, xmm0
0x180030fbd  movups  [rsp+198h+Src], xmm0
0x180030fc5  mov     [rsp+198h+var_88], 0
0x180030fd1  mov     [rsp+198h+var_80], 0
0x180030fdd  lea     ecx, [rbx+2Fh]; unsigned __int64
0x180030fe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030fe5  mov     qword ptr [rsp+198h+Src], rax
0x180030fed  mov     [rsp+198h+var_88], 11h
0x180030ff9  mov     [rsp+198h+var_80], 17h
0x180031005  movups  xmm0, xmmword ptr cs:aMsStickeredito; "ms-stickereditor:"
0x18003100c  movups  xmmword ptr [rax], xmm0
0x18003100f  movups  xmm1, xmmword ptr cs:aMsStickeredito+10h; "ereditor:"
0x180031016  movups  xmmword ptr [rax+10h], xmm1
0x18003101a  movzx   ecx, word ptr cs:aMsStickeredito+20h; ":"
0x180031021  mov     [rax+20h], cx
0x180031025  xor     ecx, ecx
0x180031027  mov     [rax+22h], cx
0x18003102b  mov     rcx, [rsp+198h+var_88]
0x180031033  mov     rax, [rsp+198h+var_80]
0x18003103b  sub     rax, rcx
0x18003103e  lea     edx, [rbx+0Ah]
0x180031041  cmp     rax, rdx
0x180031044  jb      short loc_180031090
0x180031046  lea     rdi, [rcx+0Bh]
0x18003104a  mov     [rsp+198h+var_88], rdi
0x180031052  lea     rbx, [rsp+198h+Src]
0x18003105a  cmp     [rsp+198h+var_80], 7
0x180031063  cmova   rbx, qword ptr [rsp+198h+Src]
0x18003106c  lea     rcx, [rbx+rcx*2]; void *
0x180031070  lea     r8d, [rdx+0Bh]; Size
0x180031074  lea     rdx, aSessionid; "?sessionId="
0x18003107b  call    memmove_0
0x180031080  xor     eax, eax
0x180031082  mov     [rbx+rdi*2], ax
0x180031086  lea     rax, [rsp+198h+Src]
0x18003108e  jmp     short loc_1800310A2
0x180031090  mov     [rsp+198h+var_178], rdx; __int64
0x180031095  lea     rcx, [rsp+198h+Src]; Src
0x18003109d  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800310a2  movups  xmm0, xmmword ptr [rax]
0x1800310a5  movups  [rsp+198h+var_58], xmm0
0x1800310ad  movups  xmm1, xmmword ptr [rax+10h]
0x1800310b1  movups  [rsp+198h+var_48], xmm1
0x1800310b9  mov     qword ptr [rax+10h], 0
0x1800310c1  mov     qword ptr [rax+18h], 7
0x1800310c9  xor     ecx, ecx
0x1800310cb  mov     [rax], cx
0x1800310ce  mov     r9, rsi
0x1800310d1  lea     r8, [rsp+198h+var_58]
0x1800310d9  lea     rcx, [rsp+198h+var_78]
0x1800310e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x1800310e6  nop
0x1800310e7  lea     rcx, [rsp+198h+var_58]
0x1800310ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800310f4  nop
0x1800310f5  lea     rcx, [rsp+198h+Src]
0x1800310fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031102  nop
0x180031103  lea     rcx, [rsp+198h+var_38]
0x18003110b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180031110  lea     rax, [rsp+198h+var_78]
0x180031118  cmp     [rsp+198h+var_60], 7
0x180031121  cmova   rax, [rsp+198h+var_78]
0x18003112a  mov     [rsp+198h+pExecInfo.lpFile], rax
0x180031132  lea     rcx, [rsp+198h+var_148]
0x180031137  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003113c  lea     rcx, [rsp+198h+pExecInfo]; pExecInfo
0x180031144  call    cs:__imp_ShellExecuteExW
0x18003114b  nop     dword ptr [rax+rax+00h]
0x180031150  test    eax, eax
0x180031152  jz      short loc_1800311A5
0x180031154  mov     rbx, [rsp+198h+pv]
0x18003115c  lea     rdi, [rbx+0C8h]
0x180031163  mov     rcx, rdi; lpCriticalSection
0x180031166  call    cs:__imp_EnterCriticalSection
0x18003116d  nop     dword ptr [rax+rax+00h]
0x180031172  or      dword ptr [rbx+48h], 300h
0x180031179  cmp     qword ptr [rbx+0F8h], 0
0x180031181  jz      short loc_180031191
0x180031183  mov     edx, 2
0x180031188  lea     rcx, [rbx+8]
0x18003118c  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x180031191  test    rdi, rdi
0x180031194  jz      short loc_1800311A5
0x180031196  mov     rcx, rdi; lpCriticalSection
0x180031199  call    cs:__imp_LeaveCriticalSection
0x1800311a0  nop     dword ptr [rax+rax+00h]
0x1800311a5  mov     rbx, [rsp+198h+pv]
0x1800311ad  test    rbx, rbx
0x1800311b0  jz      short loc_1800311D9
0x1800311b2  or      eax, 0FFFFFFFFh
0x1800311b5  lock xadd [rbx+150h], eax
0x1800311bd  cmp     eax, 1
0x1800311c0  jnz     short loc_1800311D9
0x1800311c2  mov     rcx, rbx
0x1800311c5  call    ??1?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::~merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>(void)
0x1800311ca  mov     rcx, rbx; pv
0x1800311cd  call    cs:__imp_CoTaskMemFree
0x1800311d4  nop     dword ptr [rax+rax+00h]
0x1800311d9  lea     rcx, [rsp+198h+var_140]; this
0x1800311de  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800311e3  lea     rcx, [rsp+198h+var_78]
0x1800311eb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800311f0  xor     eax, eax
0x1800311f2  jmp     short loc_1800311F8
0x1800311f4  mov     eax, [rsp+198h+var_158]
0x1800311f8  mov     rcx, [rsp+198h+var_18]
0x180031200  xor     rcx, rsp; StackCookie
0x180031203  call    __security_check_cookie
0x180031208  lea     r11, [rsp+198h+var_8]
0x180031210  mov     rbx, [r11+10h]
0x180031214  mov     rsi, [r11+18h]
0x180031218  mov     rsp, r11
0x18003121b  pop     rdi
0x18003121c  retn
```
