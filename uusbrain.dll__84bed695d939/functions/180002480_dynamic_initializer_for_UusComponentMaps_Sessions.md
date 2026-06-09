# _dynamic_initializer_for__UusComponentMaps::Sessions__

- ea: `0x180002480`
- end: `0x180002f24`
- name: `_dynamic_initializer_for__UusComponentMaps::Sessions__`
- size: `2724`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002480`
- `0x180009c38`
- `0x18001b030`
- `0x180028728`
- `0x180029518`
- `0x18003f658`
- `0x180042ba4`
- `0x180042bfc`
- `0x180043404`

## string_xrefs

- `0x18000259b`: `updateplatformmldata.aggregator`
- `0x180002633`: `updatecli`
- `0x18000265f`: `updatecli`
- `0x1800027fb`: `system.monotificationuxpath`
- `0x180002938`: `WaasMedicAgent`
- `0x180002909`: `waasmedic.agent`
- `0x180002a6c`: `wu.core.updatedeploy`
- `0x180002b9e`: `WuStoreAuthPlugin`
- `0x180002b72`: `wu.authplugin`
- `0x180002bf6`: `WuUpdatePolicy`
- `0x180002bca`: `wu.updatepolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
int dynamic_initializer_for__UusComponentMaps::Sessions__()
{
  __int64 v0; // rcx
  _QWORD *v1; // r14
  _BYTE *v2; // rsi
  __int64 v3; // rax
  __int128 v4; // xmm6
  __int64 v5; // rbx
  __int64 *v6; // rdi
  __int64 *v8; // [rsp+28h] [rbp-E0h]
  _QWORD v9[3]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+48h] [rbp-C0h]
  _BYTE v11[40]; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v12[2]; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v13[2]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v14[2]; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v15[2]; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD v16[2]; // [rsp+F8h] [rbp-10h] BYREF
  _OWORD v17[2]; // [rsp+118h] [rbp+10h] BYREF
  _OWORD v18[2]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v19[2]; // [rsp+158h] [rbp+50h] BYREF
  _OWORD v20[2]; // [rsp+178h] [rbp+70h] BYREF
  _OWORD v21[2]; // [rsp+198h] [rbp+90h] BYREF
  _OWORD v22[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _OWORD v23[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  _OWORD v24[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _OWORD v25[2]; // [rsp+218h] [rbp+110h] BYREF
  _OWORD v26[2]; // [rsp+238h] [rbp+130h] BYREF
  _OWORD v27[2]; // [rsp+258h] [rbp+150h] BYREF
  _OWORD v28[2]; // [rsp+278h] [rbp+170h] BYREF
  _OWORD v29[2]; // [rsp+298h] [rbp+190h] BYREF
  _OWORD v30[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _OWORD v31[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _OWORD v32[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _OWORD v33[2]; // [rsp+318h] [rbp+210h] BYREF
  _OWORD v34[2]; // [rsp+338h] [rbp+230h] BYREF
  _OWORD v35[2]; // [rsp+358h] [rbp+250h] BYREF
  _OWORD v36[2]; // [rsp+378h] [rbp+270h] BYREF
  _OWORD v37[2]; // [rsp+398h] [rbp+290h] BYREF
  _OWORD v38[2]; // [rsp+3B8h] [rbp+2B0h] BYREF
  _OWORD v39[2]; // [rsp+3D8h] [rbp+2D0h] BYREF
  _OWORD v40[2]; // [rsp+3F8h] [rbp+2F0h] BYREF
  _OWORD v41[2]; // [rsp+418h] [rbp+310h] BYREF
  _OWORD v42[2]; // [rsp+438h] [rbp+330h] BYREF
  _OWORD v43[2]; // [rsp+458h] [rbp+350h] BYREF
  _OWORD v44[2]; // [rsp+478h] [rbp+370h] BYREF
  _OWORD v45[2]; // [rsp+498h] [rbp+390h] BYREF
  _OWORD v46[2]; // [rsp+4B8h] [rbp+3B0h] BYREF
  _OWORD v47[2]; // [rsp+4D8h] [rbp+3D0h] BYREF
  _OWORD v48[2]; // [rsp+4F8h] [rbp+3F0h] BYREF
  _OWORD v49[2]; // [rsp+518h] [rbp+410h] BYREF
  _OWORD v50[2]; // [rsp+538h] [rbp+430h] BYREF
  _OWORD v51[2]; // [rsp+558h] [rbp+450h] BYREF
  _OWORD v52[2]; // [rsp+578h] [rbp+470h] BYREF
  _OWORD v53[2]; // [rsp+598h] [rbp+490h] BYREF
  _OWORD v54[2]; // [rsp+5B8h] [rbp+4B0h] BYREF
  _OWORD v55[2]; // [rsp+5D8h] [rbp+4D0h] BYREF
  _OWORD v56[2]; // [rsp+5F8h] [rbp+4F0h] BYREF
  _OWORD v57[2]; // [rsp+618h] [rbp+510h] BYREF
  _OWORD v58[2]; // [rsp+638h] [rbp+530h] BYREF
  _OWORD v59[2]; // [rsp+658h] [rbp+550h] BYREF
  _OWORD v60[2]; // [rsp+678h] [rbp+570h] BYREF
  _OWORD v61[2]; // [rsp+698h] [rbp+590h] BYREF
  _OWORD v62[2]; // [rsp+6B8h] [rbp+5B0h] BYREF
  _OWORD v63[2]; // [rsp+6D8h] [rbp+5D0h] BYREF
  _OWORD v64[2]; // [rsp+6F8h] [rbp+5F0h] BYREF
  _BYTE v65[48]; // [rsp+718h] [rbp+610h] BYREF

  memset(&v11[8], 0, 32);
  std::wstring::_Construct<1,wchar_t const *>(&v11[8], L"aggregatorhost.uusmodules", 0x19u);
  memset(v12, 0, sizeof(v12));
  std::wstring::_Construct<1,wchar_t const *>(v12, L"UusFailover", 0xBu);
  memset(v13, 0, sizeof(v13));
  std::wstring::_Construct<1,wchar_t const *>(v13, L"uusfailover.aggregator", 0x16u);
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,wchar_t const *>(v14, L"UusFailover", 0xBu);
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,wchar_t const *>(v15, L"uuscorehealth.aggregator", 0x18u);
  memset(v16, 0, sizeof(v16));
  std::wstring::_Construct<1,wchar_t const *>(v16, L"UusFailover", 0xBu);
  memset(v17, 0, sizeof(v17));
  std::wstring::_Construct<1,wchar_t const *>(v17, L"updateplatformmldata.aggregator", 0x1Fu);
  memset(v18, 0, sizeof(v18));
  std::wstring::_Construct<1,wchar_t const *>(v18, L"UusFailover", 0xBu);
  memset(v19, 0, sizeof(v19));
  std::wstring::_Construct<1,wchar_t const *>(v19, L"mousocoreworker", 0xFu);
  memset(v20, 0, sizeof(v20));
  std::wstring::_Construct<1,wchar_t const *>(v20, L"MoUsoCoreWorker", 0xFu);
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,wchar_t const *>(v21, L"updatecli", 9u);
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,wchar_t const *>(v22, L"updatecli", 9u);
  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct<1,wchar_t const *>(v23, L"usoclientimpl", 0xDu);
  memset(v24, 0, sizeof(v24));
  std::wstring::_Construct<1,wchar_t const *>(v24, L"UsoClientImpl", 0xDu);
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,wchar_t const *>(v25, L"usosvc.mousocoreworker", 0x16u);
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,wchar_t const *>(v26, L"MoUsoCoreWorker", 0xFu);
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,wchar_t const *>(v27, L"usosvc.usosvcimpl", 0x11u);
  memset(v28, 0, sizeof(v28));
  std::wstring::_Construct<1,wchar_t const *>(v28, L"UsoSvcImpl", 0xAu);
  memset(v29, 0, sizeof(v29));
  std::wstring::_Construct<1,wchar_t const *>(v29, L"deliveryoptimization", 0x14u);
  memset(v30, 0, sizeof(v30));
  std::wstring::_Construct<1,wchar_t const *>(v30, &qword_180050DC0, 0);
  memset(v31, 0, sizeof(v31));
  std::wstring::_Construct<1,wchar_t const *>(v31, L"system.monotificationuxpath", 0x1Bu);
  memset(v32, 0, sizeof(v32));
  std::wstring::_Construct<1,wchar_t const *>(v32, L"MoNotificationUx", 0x10u);
  memset(v33, 0, sizeof(v33));
  std::wstring::_Construct<1,wchar_t const *>(v33, L"monotificationux", 0x10u);
  memset(v34, 0, sizeof(v34));
  std::wstring::_Construct<1,wchar_t const *>(v34, L"MoNotificationUx", 0x10u);
  memset(v35, 0, sizeof(v35));
  std::wstring::_Construct<1,wchar_t const *>(v35, L"waasmedic.engine", 0x10u);
  memset(v36, 0, sizeof(v36));
  std::wstring::_Construct<1,wchar_t const *>(v36, L"WaasMedicEngine", 0xFu);
  memset(v37, 0, sizeof(v37));
  std::wstring::_Construct<1,wchar_t const *>(v37, L"waasmedic.agent", 0xFu);
  memset(v38, 0, sizeof(v38));
  std::wstring::_Construct<1,wchar_t const *>(v38, L"WaasMedicAgent", 0xEu);
  memset(v39, 0, sizeof(v39));
  std::wstring::_Construct<1,wchar_t const *>(v39, L"waasmedic.capsule", 0x11u);
  memset(v40, 0, sizeof(v40));
  std::wstring::_Construct<1,wchar_t const *>(v40, L"WaasMedicCapsule", 0x10u);
  memset(v41, 0, sizeof(v41));
  std::wstring::_Construct<1,wchar_t const *>(v41, L"wu.handler", 0xAu);
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,wchar_t const *>(v42, L"WuHandler", 9u);
  memset(v43, 0, sizeof(v43));
  std::wstring::_Construct<1,wchar_t const *>(v43, L"wu.proxystubs", 0xDu);
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,wchar_t const *>(v44, L"WuCoreProxyStubs", 0x10u);
  memset(v45, 0, sizeof(v45));
  std::wstring::_Construct<1,wchar_t const *>(v45, L"wu.core.updatedeploy", 0x14u);
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,wchar_t const *>(v46, L"WuCoreModules", 0xDu);
  memset(v47, 0, sizeof(v47));
  std::wstring::_Construct<1,wchar_t const *>(v47, L"wu.core.wuapi", 0xDu);
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,wchar_t const *>(v48, L"WuCoreModules", 0xDu);
  memset(v49, 0, sizeof(v49));
  std::wstring::_Construct<1,wchar_t const *>(v49, L"wu.core.wuaueng", 0xFu);
  memset(v50, 0, sizeof(v50));
  std::wstring::_Construct<1,wchar_t const *>(v50, L"WuCoreModules", 0xDu);
  memset(v51, 0, sizeof(v51));
  std::wstring::_Construct<1,wchar_t const *>(v51, L"wu.authplugin", 0xDu);
  memset(v52, 0, sizeof(v52));
  std::wstring::_Construct<1,wchar_t const *>(v52, L"WuStoreAuthPlugin", 0x11u);
  memset(v53, 0, sizeof(v53));
  std::wstring::_Construct<1,wchar_t const *>(v53, L"wu.updatepolicy", 0xFu);
  memset(v54, 0, sizeof(v54));
  std::wstring::_Construct<1,wchar_t const *>(v54, L"WuUpdatePolicy", 0xEu);
  memset(v55, 0, sizeof(v55));
  std::wstring::_Construct<1,wchar_t const *>(v55, L"wu.wuaucltcore", 0xEu);
  memset(v56, 0, sizeof(v56));
  std::wstring::_Construct<1,wchar_t const *>(v56, L"Wuauclt", 7u);
  memset(v57, 0, sizeof(v57));
  std::wstring::_Construct<1,wchar_t const *>(v57, L"wu.wutrust", 0xAu);
  memset(v58, 0, sizeof(v58));
  std::wstring::_Construct<1,wchar_t const *>(v58, L"WuTrust", 7u);
  memset(v59, 0, sizeof(v59));
  std::wstring::_Construct<1,wchar_t const *>(v59, L"sih", 3u);
  memset(v60, 0, sizeof(v60));
  std::wstring::_Construct<1,wchar_t const *>(v60, L"Sih", 3u);
  memset(v61, 0, sizeof(v61));
  std::wstring::_Construct<1,wchar_t const *>(v61, L"mlengine", 8u);
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,wchar_t const *>(v62, L"MLEngine", 8u);
  memset(v63, 0, sizeof(v63));
  std::wstring::_Construct<1,wchar_t const *>(v63, L"uieorchestrator", 0xFu);
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(v64, L"UIEOrchestrator", 0xFu);
  UusComponentMaps::Sessions = 0;
  qword_180063CE8 = 0;
  v1 = operator new(0x60u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  UusComponentMaps::Sessions = (__int64)v1;
  v2 = &v11[8];
  do
  {
    v3 = std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_hint<std::wstring>(
           v0,
           v65,
           v1,
           v2,
           v8,
           v9[0]);
    v4 = *(_OWORD *)v3;
    v10 = *(_QWORD *)(v3 + 16);
    if ( !(_BYTE)v10 )
    {
      if ( qword_180063CE8 == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v5 = UusComponentMaps::Sessions;
      v8 = &UusComponentMaps::Sessions;
      v6 = (__int64 *)operator new(0x60u);
      std::wstring::wstring((__int64)(v6 + 4), (__int64)v2);
      std::wstring::wstring((__int64)(v6 + 8), (__int64)(v2 + 32));
      *v6 = v5;
      v6[1] = v5;
      v6[2] = v5;
      *((_WORD *)v6 + 12) = 0;
      v9[0] = 0;
      *(_OWORD *)&v9[1] = v4;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
        &UusComponentMaps::Sessions,
        &v9[1],
        v6);
    }
    v2 += 64;
  }
  while ( v2 != v65 );
  `eh vector destructor iterator'(
    &v11[8],
    0x40u,
    0x1Bu,
    (void (*)(void *))PackageActivationData::~PackageActivationData);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusComponentMaps::Sessions__);
}

```

## disassembly

```asm
0x180002480  mov     rax, rsp
0x180002483  mov     [rax+10h], rbx
0x180002487  mov     [rax+18h], rsi
0x18000248b  mov     [rax+20h], rdi
0x18000248f  push    rbp
0x180002490  push    r12
0x180002492  push    r13
0x180002494  push    r14
0x180002496  push    r15
0x180002498  lea     rbp, [rax-668h]
0x18000249f  sub     rsp, 740h
0x1800024a6  movaps  xmmword ptr [rax-38h], xmm6
0x1800024aa  xorps   xmm0, xmm0
0x1800024ad  movups  [rsp+760h+var_718+8], xmm0
0x1800024b2  xorps   xmm1, xmm1
0x1800024b5  movdqa  [rsp+760h+var_708+8], xmm1
0x1800024bb  mov     r8d, 19h
0x1800024c1  lea     rdx, aAggregatorhost; "aggregatorhost.uusmodules"
0x1800024c8  lea     rcx, [rsp+760h+var_718+8]
0x1800024cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800024d2  nop
0x1800024d3  xorps   xmm0, xmm0
0x1800024d6  movups  [rsp+760h+var_6F8+8], xmm0
0x1800024db  xorps   xmm1, xmm1
0x1800024de  movdqa  [rbp+660h+var_6E0], xmm1
0x1800024e3  mov     edi, 0Bh
0x1800024e8  mov     r8d, edi
0x1800024eb  lea     rbx, aUusfailover; "UusFailover"
0x1800024f2  mov     rdx, rbx
0x1800024f5  lea     rcx, [rsp+760h+var_6F8+8]
0x1800024fa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800024ff  nop
0x180002500  xorps   xmm0, xmm0
0x180002503  movups  [rbp+660h+var_6D0], xmm0
0x180002507  xorps   xmm1, xmm1
0x18000250a  movdqa  [rbp+660h+var_6C0], xmm1
0x18000250f  lea     esi, [rdi+0Bh]
0x180002512  mov     r8d, esi
0x180002515  lea     rdx, aUusfailoverAgg; "uusfailover.aggregator"
0x18000251c  lea     rcx, [rbp+660h+var_6D0]
0x180002520  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002525  nop
0x180002526  xorps   xmm0, xmm0
0x180002529  movups  [rbp+660h+var_6B0], xmm0
0x18000252d  xorps   xmm1, xmm1
0x180002530  movdqa  [rbp+660h+var_6A0], xmm1
0x180002535  mov     r8d, edi
0x180002538  mov     rdx, rbx
0x18000253b  lea     rcx, [rbp+660h+var_6B0]
0x18000253f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002544  nop
0x180002545  xorps   xmm0, xmm0
0x180002548  movups  [rbp+660h+var_690], xmm0
0x18000254c  xorps   xmm1, xmm1
0x18000254f  movdqa  [rbp+660h+var_680], xmm1
0x180002554  lea     r8d, [rdi+0Dh]
0x180002558  lea     rdx, aUuscorehealthA; "uuscorehealth.aggregator"
0x18000255f  lea     rcx, [rbp+660h+var_690]
0x180002563  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002568  nop
0x180002569  xorps   xmm0, xmm0
0x18000256c  movups  [rbp+660h+var_670], xmm0
0x180002570  xorps   xmm1, xmm1
0x180002573  movdqa  [rbp+660h+var_660], xmm1
0x180002578  mov     r8d, edi
0x18000257b  mov     rdx, rbx
0x18000257e  lea     rcx, [rbp+660h+var_670]
0x180002582  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002587  nop
0x180002588  xorps   xmm0, xmm0
0x18000258b  movups  [rbp+660h+var_650], xmm0
0x18000258f  xorps   xmm1, xmm1
0x180002592  movdqa  [rbp+660h+var_640], xmm1
0x180002597  lea     r8d, [rdi+14h]
0x18000259b  lea     rdx, aUpdateplatform; "updateplatformmldata.aggregator"
0x1800025a2  lea     rcx, [rbp+660h+var_650]
0x1800025a6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800025ab  nop
0x1800025ac  xorps   xmm0, xmm0
0x1800025af  movups  [rbp+660h+var_630], xmm0
0x1800025b3  xorps   xmm1, xmm1
0x1800025b6  movdqa  [rbp+660h+var_620], xmm1
0x1800025bb  mov     r8d, edi
0x1800025be  mov     rdx, rbx
0x1800025c1  lea     rcx, [rbp+660h+var_630]
0x1800025c5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800025ca  nop
0x1800025cb  xorps   xmm0, xmm0
0x1800025ce  movups  [rbp+660h+var_610], xmm0
0x1800025d2  xorps   xmm1, xmm1
0x1800025d5  movdqa  [rbp+660h+var_600], xmm1
0x1800025da  lea     ebx, [rdi+4]
0x1800025dd  mov     r8d, ebx
0x1800025e0  lea     rdx, aMousocoreworke; "mousocoreworker"
0x1800025e7  lea     rcx, [rbp+660h+var_610]
0x1800025eb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800025f0  nop
0x1800025f1  xorps   xmm0, xmm0
0x1800025f4  movups  [rbp+660h+var_5F0], xmm0
0x1800025f8  xorps   xmm1, xmm1
0x1800025fb  movdqa  [rbp+660h+var_5E0], xmm1
0x180002603  mov     r8d, ebx
0x180002606  lea     rdx, aMousocoreworke_0; "MoUsoCoreWorker"
0x18000260d  lea     rcx, [rbp+660h+var_5F0]
0x180002611  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002616  nop
0x180002617  xorps   xmm0, xmm0
0x18000261a  movups  [rbp+660h+var_5D0], xmm0
0x180002621  xorps   xmm1, xmm1
0x180002624  movdqa  [rbp+660h+var_5C0], xmm1
0x18000262c  lea     r14d, [rdi-2]
0x180002630  mov     r8d, r14d
0x180002633  lea     rdx, aUpdatecli; "updatecli"
0x18000263a  lea     rcx, [rbp+660h+var_5D0]
0x180002641  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002646  nop
0x180002647  xorps   xmm0, xmm0
0x18000264a  movups  [rbp+660h+var_5B0], xmm0
0x180002651  xorps   xmm1, xmm1
0x180002654  movdqa  [rbp+660h+var_5A0], xmm1
0x18000265c  mov     r8d, r14d
0x18000265f  lea     rdx, aUpdatecli; "updatecli"
0x180002666  lea     rcx, [rbp+660h+var_5B0]
0x18000266d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002672  nop
0x180002673  xorps   xmm0, xmm0
0x180002676  movups  [rbp+660h+var_590], xmm0
0x18000267d  xorps   xmm1, xmm1
0x180002680  movdqa  [rbp+660h+var_580], xmm1
0x180002688  lea     r12d, [rdi+2]
0x18000268c  mov     r8d, r12d
0x18000268f  lea     rdx, aUsoclientimpl_0; "usoclientimpl"
0x180002696  lea     rcx, [rbp+660h+var_590]
0x18000269d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800026a2  nop
0x1800026a3  xorps   xmm0, xmm0
0x1800026a6  movups  [rbp+660h+var_570], xmm0
0x1800026ad  xorps   xmm1, xmm1
0x1800026b0  movdqa  [rbp+660h+var_560], xmm1
0x1800026b8  mov     r8d, r12d
0x1800026bb  lea     rdx, aUsoclientimpl; "UsoClientImpl"
0x1800026c2  lea     rcx, [rbp+660h+var_570]
0x1800026c9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800026ce  nop
0x1800026cf  xorps   xmm0, xmm0
0x1800026d2  movups  [rbp+660h+var_550], xmm0
0x1800026d9  xorps   xmm1, xmm1
0x1800026dc  movdqa  [rbp+660h+var_540], xmm1
0x1800026e4  mov     r8d, esi
0x1800026e7  lea     rdx, aUsosvcMousocor; "usosvc.mousocoreworker"
0x1800026ee  lea     rcx, [rbp+660h+var_550]
0x1800026f5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800026fa  nop
0x1800026fb  xorps   xmm0, xmm0
0x1800026fe  movups  [rbp+660h+var_530], xmm0
0x180002705  xorps   xmm1, xmm1
0x180002708  movdqa  [rbp+660h+var_520], xmm1
0x180002710  mov     r8d, ebx
0x180002713  lea     rdx, aMousocoreworke_0; "MoUsoCoreWorker"
0x18000271a  lea     rcx, [rbp+660h+var_530]
0x180002721  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002726  nop
0x180002727  xorps   xmm0, xmm0
0x18000272a  movups  [rbp+660h+var_510], xmm0
0x180002731  xorps   xmm1, xmm1
0x180002734  movdqa  [rbp+660h+var_500], xmm1
0x18000273c  lea     r15d, [rdi+6]
0x180002740  mov     r8d, r15d
0x180002743  lea     rdx, aUsosvcUsosvcim; "usosvc.usosvcimpl"
0x18000274a  lea     rcx, [rbp+660h+var_510]
0x180002751  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002756  nop
0x180002757  xorps   xmm0, xmm0
0x18000275a  movups  [rbp+660h+var_4F0], xmm0
0x180002761  xorps   xmm1, xmm1
0x180002764  movdqa  [rbp+660h+var_4E0], xmm1
0x18000276c  lea     r13d, [rdi-1]
0x180002770  mov     r8d, r13d
0x180002773  lea     rdx, aUsosvcimpl; "UsoSvcImpl"
0x18000277a  lea     rcx, [rbp+660h+var_4F0]
0x180002781  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002786  nop
0x180002787  xorps   xmm0, xmm0
0x18000278a  movups  [rbp+660h+var_4D0], xmm0
0x180002791  xorps   xmm1, xmm1
0x180002794  movdqa  [rbp+660h+var_4C0], xmm1
0x18000279c  lea     edi, [rsi-2]
0x18000279f  mov     r8d, edi
0x1800027a2  lea     rdx, aDeliveryoptimi; "deliveryoptimization"
0x1800027a9  lea     rcx, [rbp+660h+var_4D0]
0x1800027b0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800027b5  nop
0x1800027b6  xorps   xmm0, xmm0
0x1800027b9  movups  [rbp+660h+var_4B0], xmm0
0x1800027c0  xorps   xmm1, xmm1
0x1800027c3  movdqa  [rbp+660h+var_4A0], xmm1
0x1800027cb  xor     r8d, r8d
0x1800027ce  lea     rdx, qword_180050DC0
0x1800027d5  lea     rcx, [rbp+660h+var_4B0]
0x1800027dc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800027e1  nop
0x1800027e2  xorps   xmm0, xmm0
0x1800027e5  movups  [rbp+660h+var_490], xmm0
0x1800027ec  xorps   xmm1, xmm1
0x1800027ef  movdqa  [rbp+660h+var_480], xmm1
0x1800027f7  lea     r8d, [rsi+5]
0x1800027fb  lea     rdx, aSystemMonotifi; "system.monotificationuxpath"
0x180002802  lea     rcx, [rbp+660h+var_490]
0x180002809  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000280e  nop
0x18000280f  xorps   xmm0, xmm0
0x180002812  movups  [rbp+660h+var_470], xmm0
0x180002819  xorps   xmm1, xmm1
0x18000281c  movdqa  [rbp+660h+var_460], xmm1
0x180002824  lea     ebx, [rsi-6]
0x180002827  mov     r8d, ebx
0x18000282a  lea     rdx, aMonotification_0; "MoNotificationUx"
0x180002831  lea     rcx, [rbp+660h+var_470]
0x180002838  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000283d  nop
0x18000283e  xorps   xmm0, xmm0
0x180002841  movups  [rbp+660h+var_450], xmm0
0x180002848  xorps   xmm1, xmm1
0x18000284b  movdqa  [rbp+660h+var_440], xmm1
0x180002853  mov     r8d, ebx
0x180002856  lea     rdx, aMonotification; "monotificationux"
0x18000285d  lea     rcx, [rbp+660h+var_450]
0x180002864  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002869  nop
0x18000286a  xorps   xmm0, xmm0
0x18000286d  movups  [rbp+660h+var_430], xmm0
0x180002874  xorps   xmm1, xmm1
0x180002877  movdqa  [rbp+660h+var_420], xmm1
0x18000287f  mov     r8d, ebx
0x180002882  lea     rdx, aMonotification_0; "MoNotificationUx"
0x180002889  lea     rcx, [rbp+660h+var_430]
0x180002890  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002895  nop
0x180002896  xorps   xmm0, xmm0
0x180002899  movups  [rbp+660h+var_410], xmm0
0x1800028a0  xorps   xmm1, xmm1
0x1800028a3  movdqa  [rbp+660h+var_400], xmm1
0x1800028ab  mov     r8d, ebx
0x1800028ae  lea     rdx, aWaasmedicEngin; "waasmedic.engine"
0x1800028b5  lea     rcx, [rbp+660h+var_410]
0x1800028bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800028c1  nop
0x1800028c2  xorps   xmm0, xmm0
0x1800028c5  movups  [rbp+660h+var_3F0], xmm0
0x1800028cc  xorps   xmm1, xmm1
0x1800028cf  movdqa  [rbp+660h+var_3E0], xmm1
0x1800028d7  lea     esi, [rdi-5]
0x1800028da  mov     r8d, esi
0x1800028dd  lea     rdx, aWaasmedicengin; "WaasMedicEngine"
0x1800028e4  lea     rcx, [rbp+660h+var_3F0]
0x1800028eb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800028f0  nop
0x1800028f1  xorps   xmm0, xmm0
0x1800028f4  movups  [rbp+660h+var_3D0], xmm0
0x1800028fb  xorps   xmm1, xmm1
0x1800028fe  movdqa  [rbp+660h+var_3C0], xmm1
0x180002906  mov     r8d, esi
0x180002909  lea     rdx, aWaasmedicAgent; "waasmedic.agent"
0x180002910  lea     rcx, [rbp+660h+var_3D0]
0x180002917  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000291c  nop
0x18000291d  xorps   xmm0, xmm0
0x180002920  movups  [rbp+660h+var_3B0], xmm0
0x180002927  xorps   xmm1, xmm1
0x18000292a  movdqa  [rbp+660h+var_3A0], xmm1
0x180002932  lea     esi, [rdi-6]
0x180002935  mov     r8d, esi
0x180002938  lea     rdx, aWaasmedicagent; "WaasMedicAgent"
0x18000293f  lea     rcx, [rbp+660h+var_3B0]
0x180002946  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000294b  nop
0x18000294c  xorps   xmm0, xmm0
0x18000294f  movups  [rbp+660h+var_390], xmm0
0x180002956  xorps   xmm1, xmm1
0x180002959  movdqa  [rbp+660h+var_380], xmm1
0x180002961  mov     r8d, r15d
0x180002964  lea     rdx, aWaasmedicCapsu; "waasmedic.capsule"
0x18000296b  lea     rcx, [rbp+660h+var_390]
0x180002972  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002977  nop
0x180002978  xorps   xmm0, xmm0
0x18000297b  movups  [rbp+660h+var_370], xmm0
0x180002982  xorps   xmm1, xmm1
0x180002985  movdqa  [rbp+660h+var_360], xmm1
0x18000298d  mov     r8d, ebx
0x180002990  lea     rdx, aWaasmediccapsu; "WaasMedicCapsule"
0x180002997  lea     rcx, [rbp+660h+var_370]
0x18000299e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800029a3  nop
0x1800029a4  xorps   xmm0, xmm0
0x1800029a7  movups  [rbp+660h+var_350], xmm0
0x1800029ae  xorps   xmm1, xmm1
0x1800029b1  movdqa  [rbp+660h+var_340], xmm1
0x1800029b9  mov     r8d, r13d
0x1800029bc  lea     rdx, aWuHandler; "wu.handler"
  ... truncated ...
```
