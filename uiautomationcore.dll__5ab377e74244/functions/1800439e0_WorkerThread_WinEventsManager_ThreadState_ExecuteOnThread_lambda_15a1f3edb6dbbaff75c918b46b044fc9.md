# WorkerThread_WinEventsManager::ThreadState_::ExecuteOnThread__lambda_15a1f3edb6dbbaff75c918b46b044fc9___

- ea: `0x1800439e0`
- end: `0x180043e53`
- name: `WorkerThread_WinEventsManager::ThreadState_::ExecuteOnThread__lambda_15a1f3edb6dbbaff75c918b46b044fc9___`
- size: `1139`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042b1c`

## callees

- `0x180032724`
- `0x180034360`
- `0x180042d18`
- `0x1800435d8`
- `0x1800439e0`
- `0x180043e5c`
- `0x180043eb0`
- `0x180043ee0`
- `0x1800dbd88`
- `0x1801b2924`
- `0x1801e8320`
- `0x1801e8380`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180043ce3`
- `msvcp_win!_Mtx_unlock` at `0x180043ce3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043a32`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043a32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180043d41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180043d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a44`

## string_xrefs

- `0x180043d82`: `onecore\windows\accessibletech\common\WorkerThread.h`
- `0x180043e0f`: `onecore\windows\accessibletech\common\WorkerThread.h`
- `0x180043e41`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180043e28`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WorkerThread_WinEventsManager::ThreadState_::ExecuteOnThread__lambda_15a1f3edb6dbbaff75c918b46b044fc9___(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3)
{
  char v6; // di
  HANDLE Event; // rsi
  const char *v8; // r9
  char *v9; // r13
  _DWORD *v10; // rsi
  __m128i v11; // xmm1
  __int128 v12; // kr00_16
  _DWORD *v13; // rcx
  void *v14; // rdx
  wil::details **v15; // rcx
  wil::details *v16; // rcx
  _QWORD *v17; // rdx
  void *v18; // rcx
  DWORD v19; // eax
  const char *v20; // r9
  __int64 v21; // rdx
  std::_Ref_count_base *v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+40h] [rbp-C0h]
  __m128i v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  char *v27; // [rsp+70h] [rbp-90h]
  std::_Ref_count_base *v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 *v31; // [rsp+90h] [rbp-70h]
  __int128 v32; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+B0h] [rbp-50h]
  std::_Ref_count_base *v34[2]; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+D0h] [rbp-30h] BYREF
  int v36; // [rsp+D8h] [rbp-28h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int128 v39; // [rsp+100h] [rbp+0h]
  char *v40; // [rsp+110h] [rbp+10h]
  std::_Ref_count_base *v41; // [rsp+118h] [rbp+18h]
  _QWORD v42[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v43; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v39 = 0;
  v6 = 1;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v8);
  GetLastError();
  v9 = (char *)operator new(0x18u);
  *(_OWORD *)v9 = 0;
  *((_DWORD *)v9 + 2) = 1;
  *((_DWORD *)v9 + 3) = 1;
  *(_QWORD *)v9 = ___7___Ref_count_obj2_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__6B_;
  *((_QWORD *)v9 + 2) = Event;
  *(_QWORD *)&v39 = v9 + 16;
  *((_QWORD *)&v39 + 1) = v9;
  v23 = (std::_Ref_count_base *)operator new(0x18u);
  *(_OWORD *)v23 = 0;
  *((_DWORD *)v23 + 2) = 1;
  *((_DWORD *)v23 + 3) = 1;
  *(_QWORD *)v23 = &std::_Ref_count_obj2<std::unique_ptr<WinEventsManager::ListenerGuard>>::`vftable';
  v31 = (__int64 *)((char *)v23 + 16);
  *((_QWORD *)v23 + 2) = 0;
  v40 = (char *)v23 + 16;
  v41 = v23;
  _InterlockedAdd((volatile signed __int32 *)v23 + 2, 1u);
  v25 = 0;
  _InterlockedAdd((volatile signed __int32 *)v9 + 2, 1u);
  v25.m128i_i64[0] = (__int64)(v9 + 16);
  v25.m128i_i64[1] = (__int64)v9;
  v10 = operator new(0x20u);
  *(_OWORD *)v10 = 0;
  v10[2] = 1;
  v10[3] = 1;
  *(_QWORD *)v10 = off_1802E2330;
  v11 = v25;
  v25 = 0;
  *((_QWORD *)v10 + 2) = v11.m128i_i64[0];
  *((_QWORD *)v10 + 3) = _mm_srli_si128(v11, 8).m128i_u64[0];
  v32 = 0;
  StringMapOperand::~StringMapOperand((StringMapOperand *)&v32);
  v33[0] = (std::_Ref_count_base *)(v10 + 4);
  v33[1] = (std::_Ref_count_base *)v10;
  v27 = (char *)v23 + 16;
  v34[0] = (std::_Ref_count_base *)((char *)v23 + 16);
  v28 = v23;
  v34[1] = v23;
  v29 = *a3;
  v35 = v29;
  v36 = *((_DWORD *)a3 + 2);
  v24 = v36;
  v30 = a3[2];
  *(_QWORD *)&v37 = v30;
  v26 = a3[3];
  *((_QWORD *)&v37 + 1) = v26;
  a3[2] = 0;
  a3[3] = 0;
  v38 = *((_OWORD *)a3 + 2);
  v12 = v38;
  a3[4] = 0;
  a3[5] = 0;
  StringMapOperand::~StringMapOperand((StringMapOperand *)&v25);
  v13 = operator new(0x60u);
  *(_OWORD *)v13 = 0;
  v13[2] = 1;
  v13[3] = 1;
  *(_QWORD *)v13 = off_1802E2380;
  *((_QWORD *)v13 + 2) = v10 + 4;
  *((_QWORD *)v13 + 3) = v10;
  *(_OWORD *)v33 = 0;
  *((_QWORD *)v13 + 4) = v27;
  *((_QWORD *)v13 + 5) = v28;
  *(_OWORD *)v34 = 0;
  *((_QWORD *)v13 + 6) = v29;
  v13[14] = v24;
  *((_QWORD *)v13 + 8) = v30;
  *((_QWORD *)v13 + 9) = v26;
  v37 = 0;
  *((_OWORD *)v13 + 5) = v12;
  v38 = 0;
  v42[0] = off_1802ED5D0;
  v42[1] = v13 + 4;
  v42[2] = v13;
  v43 = v42;
  *(_QWORD *)&v32 = a1 + 5;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 5));
  std::list<std::function<void (WinEventsManager::ThreadState &)>>::_Emplace<std::function<void (WinEventsManager::ThreadState &)>>(
    a1 + 15,
    a1[15],
    v42);
  v15 = (wil::details **)a1[3];
  if ( v15 )
    v16 = *v15;
  else
    v16 = 0;
  wil::details::SetEvent(v16, v14);
  _Mtx_unlock((_Mtx_t)(a1 + 5));
  if ( v43 )
  {
    v17 = v42;
    LOBYTE(v17) = v43 != v42;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v43 + 32LL))(v43, v17);
  }
  lambda_15a1f3edb6dbbaff75c918b46b044fc9_::__lambda_15a1f3edb6dbbaff75c918b46b044fc9_(&v35);
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  if ( v33[1] )
    std::_Ref_count_base::_Decref(v33[1]);
  if ( v9 == (char *)-16LL )
    v18 = 0;
  else
    v18 = (void *)*((_QWORD *)v9 + 2);
  v19 = WaitForSingleObjectEx(v18, 0xFFFFFFFF, 0);
  if ( v19 != 258 )
  {
    if ( v19 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v20);
    v6 = 0;
  }
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\WorkerThread.h",
      (const char *)0x80004005LL,
      SDWORD2(v12));
  v21 = *v31;
  if ( !*v31 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\WorkerThread.h",
      (const char *)0x80004005LL,
      SDWORD2(v12));
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)a2 = *(_QWORD *)v21;
  *(_QWORD *)(a2 + 8) = *(_QWORD *)(v21 + 8);
  *(_QWORD *)v21 = 0;
  *(_QWORD *)(v21 + 8) = 0;
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(v21 + 16);
  *(_DWORD *)(a2 + 20) = *(_DWORD *)(v21 + 20);
  std::_Ref_count_base::_Decref(v23);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v9);
  return a2;
}

```

## disassembly

```asm
0x1800439e0  mov     [rsp-8+arg_18], rbx
0x1800439e5  push    rbp
0x1800439e6  push    rsi
0x1800439e7  push    rdi
0x1800439e8  push    r12
0x1800439ea  push    r13
0x1800439ec  push    r14
0x1800439ee  push    r15
0x1800439f0  lea     rbp, [rsp-70h]
0x1800439f5  sub     rsp, 170h
0x1800439fc  mov     rax, cs:__security_cookie
0x180043a03  xor     rax, rsp
0x180043a06  mov     [rbp+0A0h+var_40], rax
0x180043a0a  mov     r12, r8
0x180043a0d  mov     rbx, rdx
0x180043a10  mov     r15, rcx
0x180043a13  mov     [rsp+1A0h+var_178], rdx
0x180043a18  xorps   xmm0, xmm0
0x180043a1b  movdqu  [rbp+0A0h+var_A0], xmm0
0x180043a20  mov     edi, 1
0x180043a25  mov     r9d, 1F0003h; dwDesiredAccess
0x180043a2b  mov     r8d, edi; dwFlags
0x180043a2e  xor     edx, edx; lpName
0x180043a30  xor     ecx, ecx; lpEventAttributes
0x180043a32  call    cs:__imp_CreateEventExW
0x180043a38  mov     rsi, rax
0x180043a3b  test    rax, rax
0x180043a3e  jz      loc_180043E21
0x180043a44  call    cs:__imp_GetLastError
0x180043a4a  mov     [rsp+1A0h+var_178], rsi
0x180043a4f  lea     ecx, [rdi+17h]; Size
0x180043a52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043a57  mov     r13, rax
0x180043a5a  mov     [rsp+1A0h+var_178], rax
0x180043a5f  xorps   xmm0, xmm0
0x180043a62  movups  xmmword ptr [rax], xmm0
0x180043a65  mov     [rax+8], edi
0x180043a68  mov     [rax+0Ch], edi
0x180043a6b  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@6B@
0x180043a72  mov     [r13+0], rax
0x180043a76  lea     r14, [r13+10h]
0x180043a7a  mov     [r14], rsi
0x180043a7d  mov     qword ptr [rbp+0A0h+var_A0], r14
0x180043a81  mov     qword ptr [rbp+0A0h+var_A0+8], r13
0x180043a85  lea     ecx, [rdi+17h]; Size
0x180043a88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043a8d  mov     [rsp+1A0h+var_178], rax
0x180043a92  xorps   xmm0, xmm0
0x180043a95  movups  xmmword ptr [rax], xmm0
0x180043a98  mov     [rax+8], edi
0x180043a9b  mov     [rax+0Ch], edi
0x180043a9e  lea     rcx, ??_7?$_Ref_count_obj2@V?$unique_ptr@VListenerGuard@WinEventsManager@@U?$default_delete@VListenerGuard@WinEventsManager@@@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::unique_ptr<WinEventsManager::ListenerGuard>>::`vftable'
0x180043aa5  mov     [rax], rcx
0x180043aa8  lea     rcx, [rax+10h]
0x180043aac  mov     [rbp+0A0h+var_110], rcx
0x180043ab0  mov     qword ptr [rcx], 0
0x180043ab7  mov     [rbp+0A0h+var_90], rcx
0x180043abb  mov     [rbp+0A0h+var_88], rax
0x180043abf  movdqu  xmmword ptr [rsp+1A0h+var_170], xmm0
0x180043ac5  lock add [rax+8], edi
0x180043ac9  mov     [rsp+1A0h+var_170], rcx
0x180043ace  mov     [rsp+1A0h+var_170+8], rax
0x180043ad3  lea     rax, [rsp+1A0h+var_170]
0x180043ad8  mov     qword ptr [rsp+1A0h+var_180], rax
0x180043add  movdqa  [rsp+1A0h+var_150], xmm0
0x180043ae3  lock add [r13+8], edi
0x180043ae8  mov     qword ptr [rsp+1A0h+var_150], r14
0x180043aed  mov     qword ptr [rsp+1A0h+var_150+8], r13
0x180043af2  lea     rax, [rsp+1A0h+var_150]
0x180043af7  mov     [rsp+1A0h+var_158], rax
0x180043afc  lea     ecx, [rdi+1Fh]; Size
0x180043aff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043b04  mov     rsi, rax
0x180043b07  mov     qword ptr [rsp+1A0h+var_180], rax
0x180043b0c  xorps   xmm0, xmm0
0x180043b0f  movups  xmmword ptr [rax], xmm0
0x180043b12  mov     [rax+8], edi
0x180043b15  mov     [rax+0Ch], edi
0x180043b18  lea     rax, off_1802E2330
0x180043b1f  mov     [rsi], rax
0x180043b22  movaps  xmm1, [rsp+1A0h+var_150]
0x180043b27  movdqa  [rsp+1A0h+var_150], xmm0
0x180043b2d  movq    qword ptr [rsi+10h], xmm1
0x180043b33  psrldq  xmm1, 8
0x180043b38  movq    qword ptr [rsi+18h], xmm1
0x180043b3e  movdqa  [rbp+0A0h+var_100], xmm0
0x180043b43  lea     rcx, [rbp+0A0h+var_100]; this
0x180043b47  call    ??1StringMapOperand@@QEAA@XZ; StringMapOperand::~StringMapOperand(void)
0x180043b4c  lea     rax, [rsi+10h]
0x180043b50  mov     [rbp+0A0h+var_F0], rax
0x180043b54  mov     [rbp+0A0h+var_F0+8], rsi
0x180043b58  mov     rax, [rsp+1A0h+var_170]
0x180043b5d  mov     [rsp+1A0h+var_130], rax
0x180043b62  mov     [rbp+0A0h+var_E0], rax
0x180043b66  mov     rax, [rsp+1A0h+var_170+8]
0x180043b6b  mov     [rsp+1A0h+var_128], rax
0x180043b70  mov     [rbp+0A0h+var_E0+8], rax
0x180043b74  xorps   xmm0, xmm0
0x180043b77  movdqu  xmmword ptr [rsp+1A0h+var_170], xmm0
0x180043b7d  mov     rax, [r12]
0x180043b81  mov     [rbp+0A0h+var_120], rax
0x180043b85  mov     [rbp+0A0h+var_D0], rax
0x180043b89  mov     eax, [r12+8]
0x180043b8e  mov     [rsp+1A0h+var_160], eax
0x180043b92  mov     [rbp+0A0h+var_C8], eax
0x180043b95  mov     rax, [r12+10h]
0x180043b9a  mov     [rbp+0A0h+var_118], rax
0x180043b9e  mov     qword ptr [rbp+0A0h+var_C0], rax
0x180043ba2  mov     rax, [r12+18h]
0x180043ba7  mov     [rsp+1A0h+var_140], rax
0x180043bac  mov     qword ptr [rbp+0A0h+var_C0+8], rax
0x180043bb0  xor     ecx, ecx
0x180043bb2  mov     [r12+10h], rcx
0x180043bb7  mov     [r12+18h], rcx
0x180043bbc  mov     rax, [r12+20h]
0x180043bc1  mov     [rsp+1A0h+var_158], rax
0x180043bc6  mov     qword ptr [rbp+0A0h+var_B0], rax
0x180043bca  mov     rax, [r12+28h]
0x180043bcf  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x180043bd4  mov     qword ptr [rbp+0A0h+var_B0+8], rax
0x180043bd8  mov     [r12+20h], rcx
0x180043bdd  mov     [r12+28h], rcx
0x180043be2  lea     rcx, [rsp+1A0h+var_150]; this
0x180043be7  call    ??1StringMapOperand@@QEAA@XZ; StringMapOperand::~StringMapOperand(void)
0x180043bec  nop
0x180043bed  mov     rcx, [rsp+1A0h+var_170+8]; this
0x180043bf2  xor     r12d, r12d
0x180043bf5  test    rcx, rcx
0x180043bf8  jz      short loc_180043C00
0x180043bfa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043bff  nop
0x180043c00  mov     ecx, 60h ; '`'; Size
0x180043c05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043c0a  mov     rcx, rax
0x180043c0d  mov     qword ptr [rbp+0A0h+var_100], rax
0x180043c11  xorps   xmm0, xmm0
0x180043c14  movups  xmmword ptr [rax], xmm0
0x180043c17  mov     [rax+8], edi
0x180043c1a  mov     [rax+0Ch], edi
0x180043c1d  lea     rax, off_1802E2380
0x180043c24  mov     [rcx], rax
0x180043c27  lea     rax, [rcx+10h]
0x180043c2b  lea     rdx, [rsi+10h]
0x180043c2f  mov     [rax], rdx
0x180043c32  mov     [rax+8], rsi
0x180043c36  movdqu  xmmword ptr [rbp+0A0h+var_F0], xmm0
0x180043c3b  mov     rdx, [rsp+1A0h+var_130]
0x180043c40  mov     [rax+10h], rdx
0x180043c44  mov     rdx, [rsp+1A0h+var_128]
0x180043c49  mov     [rax+18h], rdx
0x180043c4d  movdqu  xmmword ptr [rbp+0A0h+var_E0], xmm0
0x180043c52  mov     rdx, [rbp+0A0h+var_120]
0x180043c56  mov     [rax+20h], rdx
0x180043c5a  mov     edx, [rsp+1A0h+var_160]
0x180043c5e  mov     [rax+28h], edx
0x180043c61  mov     rdx, [rbp+0A0h+var_118]
0x180043c65  mov     [rax+30h], rdx
0x180043c69  mov     rdx, [rsp+1A0h+var_140]
0x180043c6e  mov     [rax+38h], rdx
0x180043c72  movdqu  [rbp+0A0h+var_C0], xmm0
0x180043c77  mov     rdx, [rsp+1A0h+var_158]
0x180043c7c  mov     [rax+40h], rdx
0x180043c80  mov     rdx, qword ptr [rsp+1A0h+var_180]
0x180043c85  mov     [rax+48h], rdx
0x180043c89  movdqu  [rbp+0A0h+var_B0], xmm0
0x180043c8e  lea     rdx, off_1802ED5D0
0x180043c95  mov     [rbp+0A0h+var_80], rdx
0x180043c99  mov     [rbp+0A0h+var_78], rax
0x180043c9d  mov     [rbp+0A0h+var_70], rcx
0x180043ca1  lea     rax, [rbp+0A0h+var_80]
0x180043ca5  mov     [rbp+0A0h+var_48], rax
0x180043ca9  lea     rsi, [r15+28h]
0x180043cad  mov     qword ptr [rbp+0A0h+var_100], rsi
0x180043cb1  mov     rcx, rsi; this
0x180043cb4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180043cb9  nop
0x180043cba  lea     rcx, [r15+78h]
0x180043cbe  lea     r8, [rbp+0A0h+var_80]
0x180043cc2  mov     rdx, [rcx]
0x180043cc5  call    ??$_Emplace@V?$function@$$A6AXAEAUThreadState@WinEventsManager@@@Z@std@@@?$list@V?$function@$$A6AXAEAUThreadState@WinEventsManager@@@Z@std@@V?$allocator@V?$function@$$A6AXAEAUThreadState@WinEventsManager@@@Z@std@@@2@@std@@QEAAPEAU?$_List_node@V?$function@$$A6AXAEAUThreadState@WinEventsManager@@@Z@std@@PEAX@1@QEAU21@$$QEAV?$function@$$A6AXAEAUThreadState@WinEventsManager@@@Z@1@@Z; std::list<std::function<void (WinEventsManager::ThreadState &)>>::_Emplace<std::function<void (WinEventsManager::ThreadState &)>>(std::_List_node<std::function<void (WinEventsManager::ThreadState &)>,void *> * const,std::function<void (WinEventsManager::ThreadState &)> &&)
0x180043cca  mov     rcx, [r15+18h]
0x180043cce  test    rcx, rcx
0x180043cd1  jz      loc_180043DF9
0x180043cd7  mov     rcx, [rcx]; this
0x180043cda  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180043cdf  nop
0x180043ce0  mov     rcx, rsi; _Mtx_t
0x180043ce3  call    cs:__imp__Mtx_unlock
0x180043ce9  nop
0x180043cea  mov     rcx, [rbp+0A0h+var_48]
0x180043cee  test    rcx, rcx
0x180043cf1  jz      short loc_180043D0A
0x180043cf3  mov     rax, [rcx]
0x180043cf6  lea     rdx, [rbp+0A0h+var_80]
0x180043cfa  cmp     rcx, rdx
0x180043cfd  setnz   dl
0x180043d00  mov     rax, [rax+20h]
0x180043d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d09  nop
0x180043d0a  lea     rcx, [rbp+0A0h+var_D0]
0x180043d0e  call    _lambda_15a1f3edb6dbbaff75c918b46b044fc9_____lambda_15a1f3edb6dbbaff75c918b46b044fc9_
0x180043d13  mov     rcx, [rbp+0A0h+var_E0+8]; this
0x180043d17  test    rcx, rcx
0x180043d1a  jz      short loc_180043D21
0x180043d1c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043d21  mov     rcx, [rbp+0A0h+var_F0+8]; this
0x180043d25  test    rcx, rcx
0x180043d28  jz      short loc_180043D2F
0x180043d2a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043d2f  test    r14, r14
0x180043d32  jz      loc_180043E01
0x180043d38  mov     rcx, [r14]; hHandle
0x180043d3b  xor     r8d, r8d; bAlertable
0x180043d3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180043d41  call    cs:__imp_WaitForSingleObjectEx
0x180043d47  cmp     eax, 102h
0x180043d4c  jz      short loc_180043D59
0x180043d4e  test    eax, eax
0x180043d50  jnz     loc_180043E3A
0x180043d56  mov     dil, r12b
0x180043d59  mov     rcx, [rbp+0A8h]; this
0x180043d60  test    dil, dil
0x180043d63  jnz     loc_180043E09
0x180043d69  mov     rcx, [rbp+0A8h]; this
0x180043d70  mov     rdx, [rbp+0A0h+var_110]
0x180043d74  mov     rdx, [rdx]
0x180043d77  test    rdx, rdx
0x180043d7a  jnz     short loc_180043D94
0x180043d7c  mov     r9d, 80004005h; char *
0x180043d82  lea     r8, aOnecoreWindows_177; "onecore\\windows\\accessibletech\\commo"...
0x180043d89  mov     edx, 116h; void *
0x180043d8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043d94  mov     [rbx], r12
0x180043d97  mov     [rbx+8], r12
0x180043d9b  mov     rax, [rdx]
0x180043d9e  mov     [rbx], rax
0x180043da1  mov     rcx, [rdx+8]
0x180043da5  mov     [rbx+8], rcx
0x180043da9  mov     [rdx], r12
0x180043dac  mov     [rdx+8], r12
0x180043db0  mov     ecx, [rdx+10h]
0x180043db3  mov     [rbx+10h], ecx
0x180043db6  mov     ecx, [rdx+14h]
0x180043db9  mov     [rbx+14h], ecx
0x180043dbc  mov     rcx, [rsp+1A0h+var_178]; this
0x180043dc1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043dc6  nop
0x180043dc7  mov     rcx, r13; this
0x180043dca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180043dcf  mov     rax, rbx
0x180043dd2  mov     rcx, [rbp+0A0h+var_40]
0x180043dd6  xor     rcx, rsp; StackCookie
0x180043dd9  call    __security_check_cookie
0x180043dde  mov     rbx, [rsp+1A0h+arg_18]
0x180043de6  add     rsp, 170h
0x180043ded  pop     r15
0x180043def  pop     r14
0x180043df1  pop     r13
0x180043df3  pop     r12
0x180043df5  pop     rdi
0x180043df6  pop     rsi
0x180043df7  pop     rbp
0x180043df8  retn
0x180043df9  mov     rcx, r12
0x180043dfc  jmp     loc_180043CDA
0x180043e01  mov     rcx, r12
0x180043e04  jmp     loc_180043D3B
0x180043e09  mov     r9d, 80004005h; char *
0x180043e0f  lea     r8, aOnecoreWindows_177; "onecore\\windows\\accessibletech\\commo"...
0x180043e16  mov     edx, 113h; void *
0x180043e1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043e21  mov     rcx, [rbp+0A8h]; this
0x180043e28  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180043e2f  mov     edx, 1CC8h; void *
0x180043e34  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180043e3a  mov     rcx, [rbp+0A8h]; this
0x180043e41  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180043e48  mov     edx, 0B0Fh; void *
0x180043e4d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
