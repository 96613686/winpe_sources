# OplockTipTests::OplockTipTests_Cleanup(void)

- ea: `0x18005aee8`
- end: `0x18005b0d6`
- name: `?OplockTipTests_Cleanup@OplockTipTests@@YAXXZ`
- size: `494`
- prototype: `void __fastcall(OplockTipTests *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003aa8`

## callees

- `0x18002570c`
- `0x1800257b4`
- `0x18002630c`
- `0x180026cb4`
- `0x18002d630`
- `0x180042b2c`
- `0x180042e50`
- `0x180042fc0`
- `0x18004c444`
- `0x180050048`
- `0x180051750`
- `0x180053080`
- `0x18005aee8`
- `0x18005b244`
- `0x18005b278`
- `0x18005bed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005afdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005b051`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005afdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005b051`

## pseudocode

```c
void __fastcall OplockTipTests::OplockTipTests_Cleanup(OplockTipTests *this)
{
  void *v1; // rbx
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  char *v4; // rbx
  LPVOID v5; // rax
  char *v6; // rbx
  LPVOID v7; // rax
  void *v8; // rbx
  LPVOID pv; // [rsp+30h] [rbp+10h] BYREF
  LPVOID v10; // [rsp+38h] [rbp+18h] BYREF

  while ( 1 )
  {
    pv = 0;
    tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::open_helper(
      &pv,
      0);
    v1 = pv;
    if ( !pv )
      break;
    if ( !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)pv + 8) )
    {
      if ( v1 )
        tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(v1);
      goto LABEL_7;
    }
    tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(&pv);
    if ( v1 )
      tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(v1);
  }
  while ( 1 )
  {
LABEL_7:
    v10 = 0;
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
LABEL_33:
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    pv = (LPVOID)tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>(
                   v2,
                   0);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>,wil::err_returncode_policy>::operator=(
      &v10,
      &pv);
    if ( pv )
      tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(pv);
    v4 = (char *)v10;
    if ( !v10 )
      break;
    if ( !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)v10 + 8) )
    {
      if ( v4 )
        tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(v4);
      goto LABEL_16;
    }
    if ( v4 )
    {
      tip2::details::shared_data<1,0,0>::complete_without_lock(v4 + 8);
      tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(v4);
    }
  }
  while ( 1 )
  {
LABEL_16:
    pv = 0;
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      goto LABEL_33;
    v10 = (LPVOID)tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>(
                    v5,
                    0);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::operator=(
      &pv,
      &v10);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(&v10);
    v6 = (char *)pv;
    if ( !pv || !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)pv + 8) )
      break;
    if ( v6 )
      tip2::details::shared_data<1,0,0>::complete_without_lock(v6 + 8);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(&pv);
  }
  wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(&pv);
  while ( 1 )
  {
    pv = 0;
    v7 = CoTaskMemAlloc(0x120u);
    if ( !v7 )
      goto LABEL_33;
    v10 = (LPVOID)tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>(
                    v7,
                    0);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>,wil::err_returncode_policy>::operator=(
      &pv,
      &v10);
    if ( v10 )
      tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(v10);
    v8 = pv;
    if ( !pv )
      return;
    if ( !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)pv + 8) )
      break;
    tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(&pv);
    if ( v8 )
      tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(v8);
  }
  if ( v8 )
    tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(v8);
}

```

## disassembly

```asm
0x18005aee8  mov     [rsp-8+arg_10], rbx
0x18005aeed  mov     [rsp-8+arg_18], rsi
0x18005aef2  push    rbp
0x18005aef3  mov     rbp, rsp
0x18005aef6  sub     rsp, 20h
0x18005aefa  xor     edx, edx
0x18005aefc  mov     [rbp+pv], 0
0x18005af04  lea     rcx, [rbp+pv]
0x18005af08  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::open_helper(_GUID *)
0x18005af0d  mov     rbx, [rbp+pv]
0x18005af11  test    rbx, rbx
0x18005af14  jz      short loc_18005AF48
0x18005af16  lea     rcx, [rbx+8]
0x18005af1a  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18005af1f  test    al, al
0x18005af21  jz      short loc_18005AF3B
0x18005af23  lea     rcx, [rbp+pv]
0x18005af27  call    ?complete@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(void)
0x18005af2c  test    rbx, rbx
0x18005af2f  jz      short loc_18005AEFA
0x18005af31  mov     rcx, rbx; pv
0x18005af34  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x18005af39  jmp     short loc_18005AEFA
0x18005af3b  test    rbx, rbx
0x18005af3e  jz      short loc_18005AF48
0x18005af40  mov     rcx, rbx; pv
0x18005af43  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x18005af48  mov     esi, 120h
0x18005af4d  mov     rcx, rsi; cb
0x18005af50  mov     [rbp+arg_8], 0
0x18005af58  call    cs:__imp_CoTaskMemAlloc
0x18005af5e  test    rax, rax
0x18005af61  jz      loc_18005B0D0
0x18005af67  xor     edx, edx
0x18005af69  mov     rcx, rax
0x18005af6c  call    ??0?$merged_data@U_tip_GetDuplicateOplockHandleTipTest@OplockTipTests@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>(_GUID *)
0x18005af71  lea     rdx, [rbp+pv]
0x18005af75  mov     [rbp+pv], rax
0x18005af79  lea     rcx, [rbp+arg_8]
0x18005af7d  call    ??4?$com_ptr_t@V?$merged_data@U_tip_GetDuplicateOplockHandleTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>,wil::err_returncode_policy> &&)
0x18005af82  mov     rcx, [rbp+pv]; pv
0x18005af86  test    rcx, rcx
0x18005af89  jz      short loc_18005AF90
0x18005af8b  call    ?Release@?$merged_data@U_tip_GetDuplicateOplockHandleTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(void)
0x18005af90  mov     rbx, [rbp+arg_8]
0x18005af94  test    rbx, rbx
0x18005af97  jz      short loc_18005AFD0
0x18005af99  lea     rcx, [rbx+8]
0x18005af9d  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18005afa2  test    al, al
0x18005afa4  jz      short loc_18005AFC3
0x18005afa6  test    rbx, rbx
0x18005afa9  jz      short loc_18005AF4D
0x18005afab  lea     rcx, [rbx+8]
0x18005afaf  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18005afb4  test    rbx, rbx
0x18005afb7  jz      short loc_18005AF4D
0x18005afb9  mov     rcx, rbx; pv
0x18005afbc  call    ?Release@?$merged_data@U_tip_GetDuplicateOplockHandleTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(void)
0x18005afc1  jmp     short loc_18005AF4D
0x18005afc3  test    rbx, rbx
0x18005afc6  jz      short loc_18005AFD0
0x18005afc8  mov     rcx, rbx; pv
0x18005afcb  call    ?Release@?$merged_data@U_tip_GetDuplicateOplockHandleTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_GetDuplicateOplockHandleTipTest,OplockTipTests::_tip_GetDuplicateOplockHandleTipTest>::Release(void)
0x18005afd0  mov     rcx, rsi; cb
0x18005afd3  mov     [rbp+pv], 0
0x18005afdb  call    cs:__imp_CoTaskMemAlloc
0x18005afe1  test    rax, rax
0x18005afe4  jz      loc_18005B0D0
0x18005afea  xor     edx, edx
0x18005afec  mov     rcx, rax
0x18005afef  call    ??0?$merged_data@U_tip_RelinquishOplockInternalTipTest@OplockTipTests@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>(_GUID *)
0x18005aff4  lea     rdx, [rbp+arg_8]
0x18005aff8  mov     [rbp+arg_8], rax
0x18005affc  lea     rcx, [rbp+pv]
0x18005b000  call    ??4?$com_ptr_t@V?$merged_data@U_tip_RelinquishOplockInternalTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy> &&)
0x18005b005  lea     rcx, [rbp+arg_8]
0x18005b009  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RelinquishOplockInternalTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(void)
0x18005b00e  mov     rbx, [rbp+pv]
0x18005b012  test    rbx, rbx
0x18005b015  jz      short loc_18005B03D
0x18005b017  lea     rcx, [rbx+8]
0x18005b01b  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18005b020  test    al, al
0x18005b022  jz      short loc_18005B03D
0x18005b024  test    rbx, rbx
0x18005b027  jz      short loc_18005B032
0x18005b029  lea     rcx, [rbx+8]
0x18005b02d  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18005b032  lea     rcx, [rbp+pv]
0x18005b036  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RelinquishOplockInternalTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(void)
0x18005b03b  jmp     short loc_18005AFD0
0x18005b03d  lea     rcx, [rbp+pv]
0x18005b041  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RelinquishOplockInternalTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RelinquishOplockInternalTipTest,OplockTipTests::_tip_RelinquishOplockInternalTipTest>,wil::err_returncode_policy>(void)
0x18005b046  mov     rcx, rsi; cb
0x18005b049  mov     [rbp+pv], 0
0x18005b051  call    cs:__imp_CoTaskMemAlloc
0x18005b057  test    rax, rax
0x18005b05a  jz      short loc_18005B0D0
0x18005b05c  xor     edx, edx
0x18005b05e  mov     rcx, rax
0x18005b061  call    ??0?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>(_GUID *)
0x18005b066  lea     rdx, [rbp+arg_8]
0x18005b06a  mov     [rbp+arg_8], rax
0x18005b06e  lea     rcx, [rbp+pv]
0x18005b072  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>,wil::err_returncode_policy> &&)
0x18005b077  mov     rcx, [rbp+arg_8]; pv
0x18005b07b  test    rcx, rcx
0x18005b07e  jz      short loc_18005B085
0x18005b080  call    ?Release@?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(void)
0x18005b085  mov     rbx, [rbp+pv]
0x18005b089  test    rbx, rbx
0x18005b08c  jz      short loc_18005B0C0
0x18005b08e  lea     rcx, [rbx+8]
0x18005b092  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18005b097  test    al, al
0x18005b099  jz      short loc_18005B0B3
0x18005b09b  lea     rcx, [rbp+pv]
0x18005b09f  call    ?complete@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(void)
0x18005b0a4  test    rbx, rbx
0x18005b0a7  jz      short loc_18005B046
0x18005b0a9  mov     rcx, rbx; pv
0x18005b0ac  call    ?Release@?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(void)
0x18005b0b1  jmp     short loc_18005B046
0x18005b0b3  test    rbx, rbx
0x18005b0b6  jz      short loc_18005B0C0
0x18005b0b8  mov     rcx, rbx; pv
0x18005b0bb  call    ?Release@?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(void)
0x18005b0c0  mov     rbx, [rsp+20h+arg_10]
0x18005b0c5  mov     rsi, [rsp+20h+arg_18]
0x18005b0ca  add     rsp, 20h
0x18005b0ce  pop     rbp
0x18005b0cf  retn
0x18005b0d0  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
