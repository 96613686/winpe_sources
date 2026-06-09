# CalliopeTipTests::DiagHealth::Cleanup(void)

- ea: `0x180004d9c`
- end: `0x180004e97`
- name: `?Cleanup@DiagHealth@CalliopeTipTests@@YAXXZ`
- size: `251`
- prototype: `void __fastcall(CalliopeTipTests::DiagHealth *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004ea0`

## callees

- `0x180004d9c`
- `0x180005848`
- `0x180005950`
- `0x180005c34`
- `0x180005d48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004deb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e11`

## pseudocode

```c
void __fastcall CalliopeTipTests::DiagHealth::Cleanup(CalliopeTipTests::DiagHealth *this)
{
  __int64 *v1; // rax
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  while ( 1 )
  {
    v1 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,_GUID * &>(
           &pv,
           &v4);
    v2 = *v1;
    *v1 = 0;
    v3 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(v3);
      CoTaskMemFree(v3);
    }
    if ( !v2 )
      break;
    if ( !(unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v2 + 8) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 288), 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>((struct _RTL_CRITICAL_SECTION *)v2);
        CoTaskMemFree((LPVOID)v2);
      }
      return;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    *(_DWORD *)(v2 + 72) |= 0x300u;
    if ( *(_QWORD *)(v2 + 248) )
      tip2::details::shared_data<1,0,0>::complete_helper(v2 + 8, 2);
    if ( v2 != -200 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 288), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>((struct _RTL_CRITICAL_SECTION *)v2);
      CoTaskMemFree((LPVOID)v2);
    }
  }
}

```

## disassembly

```asm
0x180004d9c  push    rbx
0x180004d9e  push    rsi
0x180004d9f  push    rdi
0x180004da0  sub     rsp, 20h
0x180004da4  mov     [rsp+38h+arg_8], 0
0x180004dad  lea     rdx, [rsp+38h+arg_8]
0x180004db2  lea     rcx, [rsp+38h+pv]
0x180004db7  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>,_GUID * &>(_GUID * &)
0x180004dbc  mov     rbx, [rax]
0x180004dbf  mov     qword ptr [rax], 0
0x180004dc6  mov     rdi, [rsp+38h+pv]
0x180004dcb  test    rdi, rdi
0x180004dce  jz      short loc_180004DF1
0x180004dd0  or      eax, 0FFFFFFFFh
0x180004dd3  lock xadd [rdi+120h], eax
0x180004ddb  cmp     eax, 1
0x180004dde  jnz     short loc_180004DF1
0x180004de0  mov     rcx, rdi
0x180004de3  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x180004de8  mov     rcx, rdi; pv
0x180004deb  call    cs:__imp_CoTaskMemFree
0x180004df1  test    rbx, rbx
0x180004df4  jz      loc_180004E8F
0x180004dfa  lea     rcx, [rbx+8]
0x180004dfe  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x180004e03  test    al, al
0x180004e05  jz      short loc_180004E6E
0x180004e07  lea     rsi, [rbx+0C8h]
0x180004e0e  mov     rcx, rsi; lpCriticalSection
0x180004e11  call    cs:__imp_EnterCriticalSection
0x180004e17  or      dword ptr [rbx+48h], 300h
0x180004e1e  cmp     qword ptr [rbx+0F8h], 0
0x180004e26  jz      short loc_180004E36
0x180004e28  mov     edx, 2
0x180004e2d  lea     rcx, [rbx+8]
0x180004e31  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180004e36  test    rsi, rsi
0x180004e39  jz      short loc_180004E44
0x180004e3b  mov     rcx, rsi; lpCriticalSection
0x180004e3e  call    cs:__imp_LeaveCriticalSection
0x180004e44  or      eax, 0FFFFFFFFh
0x180004e47  lock xadd [rbx+120h], eax
0x180004e4f  cmp     eax, 1
0x180004e52  jnz     loc_180004DAD
0x180004e58  mov     rcx, rbx
0x180004e5b  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x180004e60  mov     rcx, rbx; pv
0x180004e63  call    cs:__imp_CoTaskMemFree
0x180004e69  jmp     loc_180004DAD
0x180004e6e  or      eax, 0FFFFFFFFh
0x180004e71  lock xadd [rbx+120h], eax
0x180004e79  cmp     eax, 1
0x180004e7c  jnz     short loc_180004E8F
0x180004e7e  mov     rcx, rbx
0x180004e81  call    ??1?$merged_data@U_tip_DiagHealthTipTest@DiagHealth@CalliopeTipTests@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>::~merged_data<CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest,CalliopeTipTests::DiagHealth::_tip_DiagHealthTipTest>(void)
0x180004e86  mov     rcx, rbx; pv
0x180004e89  call    cs:__imp_CoTaskMemFree
0x180004e8f  add     rsp, 20h
0x180004e93  pop     rdi
0x180004e94  pop     rsi
0x180004e95  pop     rbx
0x180004e96  retn
```
