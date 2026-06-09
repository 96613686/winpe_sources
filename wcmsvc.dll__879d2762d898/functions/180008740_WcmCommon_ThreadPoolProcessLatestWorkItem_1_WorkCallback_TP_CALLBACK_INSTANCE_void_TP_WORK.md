# WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180008740`
- end: `0x180008aa3`
- name: `?WorkCallback@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `867`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180008740`
- `0x180008c2c`
- `0x180008c78`
- `0x180010080`
- `0x18004f2cc`
- `0x180070464`
- `0x180084f50`
- `0x180085bc4`
- `0x1800a1520`
- `0x1800f7010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180008a6d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180008a6d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000896e`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18000896e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008778`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000894a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800087a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000894a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<1>::WorkCallback(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  HANDLE *i; // rdi
  __int64 v4; // rbx
  _OWORD *v5; // rcx
  void ***v6; // rcx
  std::_Ref_count_base *v7; // rbx
  __int64 (__fastcall ***v8)(_QWORD, _BYTE *); // rcx
  __int64 v9; // rax
  _BYTE *v10; // rdx
  __int64 result; // rax
  __int128 *v12; // rcx
  _OWORD v13[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  _OWORD *v15; // [rsp+48h] [rbp-B8h]
  void (__fastcall **v16)(_OWORD *); // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[64]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v20; // [rsp+B0h] [rbp-50h]
  __int64 v21; // [rsp+C0h] [rbp-40h]
  __int64 v22; // [rsp+C8h] [rbp-38h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  _BYTE v25[56]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v26; // [rsp+118h] [rbp+18h]

  memset_0(&v19, 0, 0x40u);
  EnterCriticalSection(a2);
  for ( i = (HANDLE *)&a2[3].SpinCount; ; i += 8 )
  {
    if ( i == &a2[5].OwningThread )
    {
      if ( a2 )
        LeaveCriticalSection(a2);
      goto LABEL_48;
    }
    if ( i[7] )
      break;
  }
  memset_0(v13, 0, 0x40u);
  v17 = v24;
  if ( (v24 & 3) != 0 )
  {
    if ( (v24 & 3) == 1 )
    {
      v16 = (void (__fastcall **)(_OWORD *))v23;
      v15 = (_OWORD *)v22;
      v24 = 0;
      goto LABEL_14;
    }
    if ( (v24 & 3) == 2 )
    {
      v16 = (void (__fastcall **)(_OWORD *))v23;
      (*(void (__fastcall **)(_OWORD *, __int128 *))(v23 + 16))(v13, &v19);
      goto LABEL_14;
    }
  }
  v13[0] = v19;
  v13[1] = v20;
  v14 = v21;
  v15 = (_OWORD *)v22;
  v16 = (void (__fastcall **)(_OWORD *))v23;
LABEL_14:
  v4 = std::any::any((std::any *)v18, (struct std::any *)i);
  if ( (v24 & 3) == 1 )
  {
    (*(void (__fastcall **)(__int64))v23)(v22);
  }
  else if ( (v24 & 3) == 2 )
  {
    (*(void (__fastcall **)(__int128 *))v23)(&v19);
  }
  v24 = 0;
  v24 = *(_QWORD *)(v4 + 56);
  if ( (v24 & 3) != 0 )
  {
    if ( (v24 & 3) == 1 )
    {
      v23 = *(_QWORD *)(v4 + 48);
      v22 = *(_QWORD *)(v4 + 40);
      *(_QWORD *)(v4 + 56) = 0;
      goto LABEL_24;
    }
    if ( (v24 & 3) == 2 )
    {
      v23 = *(_QWORD *)(v4 + 48);
      (*(void (__fastcall **)(__int128 *, __int64))(v23 + 16))(&v19, v4);
      goto LABEL_24;
    }
  }
  v19 = *(_OWORD *)v4;
  v20 = *(_OWORD *)(v4 + 16);
  v21 = *(_QWORD *)(v4 + 32);
  v22 = *(_QWORD *)(v4 + 40);
  v23 = *(_QWORD *)(v4 + 48);
LABEL_24:
  std::any::reset((std::any *)v4);
  std::any::operator=((std::any *)i);
  if ( (v17 & 3) == 1 )
  {
    v5 = v15;
    goto LABEL_28;
  }
  if ( (v17 & 3) == 2 )
  {
    v5 = v13;
LABEL_28:
    (*v16)(v5);
  }
  if ( a2 )
    LeaveCriticalSection(a2);
  v6 = &void `RTTI Type Descriptor';
  if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    v6 = (void ***)(v24 & 0xFFFFFFFFFFFFFFFCuLL);
  if ( (unsigned int)__std_type_info_compare(v6 + 1, &qword_18013AC80) )
  {
    if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || !(unsigned __int8)type_info::operator==(
                             v24 & 0xFFFFFFFFFFFFFFFCuLL,
                             &std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor') )
    {
      std::_Throw_bad_any_cast();
    }
    if ( *((_QWORD *)&v19 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL));
    v7 = (std::_Ref_count_base *)*((_QWORD *)&v19 + 1);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(v19);
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
  }
  else
  {
    if ( (v24 & 0xFFFFFFFFFFFFFFFCuLL) == 0
      || !(unsigned __int8)type_info::operator==(
                             v24 & 0xFFFFFFFFFFFFFFFCuLL,
                             &std::function<void (void)> `RTTI Type Descriptor')
      || !v22 )
    {
      std::_Throw_bad_any_cast();
    }
    v26 = 0;
    v8 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(v22 + 56);
    if ( !v8 || (v9 = (**v8)(v8, v25), (v26 = (_BYTE *)v9) == 0) )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v26 )
    {
      v10 = v25;
      LOBYTE(v10) = v26 != v25;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v26 + 32LL))(v26, v10);
    }
  }
LABEL_48:
  result = (v24 & 3) - 1;
  if ( (v24 & 3) == 1 )
  {
    v12 = (__int128 *)v22;
  }
  else
  {
    if ( (v24 & 3) != 2 )
      return result;
    v12 = &v19;
  }
  return (*(__int64 (__fastcall **)(__int128 *))v23)(v12);
}

```

## disassembly

```asm
0x180008740  push    rbp
0x180008742  push    rbx
0x180008743  push    rsi
0x180008744  push    rdi
0x180008745  lea     rbp, [rsp-38h]
0x18000874a  sub     rsp, 138h
0x180008751  mov     rax, cs:__security_cookie
0x180008758  xor     rax, rsp
0x18000875b  mov     [rbp+50h+var_30], rax
0x18000875f  mov     rsi, rdx
0x180008762  mov     ebx, 40h ; '@'
0x180008767  mov     r8d, ebx; Size
0x18000876a  xor     edx, edx; Val
0x18000876c  lea     rcx, [rbp+50h+var_B0]; void *
0x180008770  call    memset_0
0x180008775  mov     rcx, rsi; lpCriticalSection
0x180008778  call    cs:__imp_EnterCriticalSection
0x18000877e  lea     rdi, [rsi+98h]
0x180008785  lea     rax, [rdi+40h]
0x180008789  jmp     short loc_180008795
0x18000878b  cmp     qword ptr [rdi+38h], 0
0x180008790  jnz     short loc_1800087AE
0x180008792  add     rdi, rbx
0x180008795  cmp     rdi, rax
0x180008798  jnz     short loc_18000878B
0x18000879a  test    rsi, rsi
0x18000879d  jz      short loc_1800087A9
0x18000879f  mov     rcx, rsi; lpCriticalSection
0x1800087a2  call    cs:__imp_LeaveCriticalSection
0x1800087a8  nop
0x1800087a9  jmp     loc_180008A54
0x1800087ae  mov     r8, rbx; Size
0x1800087b1  xor     edx, edx; Val
0x1800087b3  lea     rcx, [rsp+150h+var_130]; void *
0x1800087b8  call    memset_0
0x1800087bd  nop
0x1800087be  mov     rax, [rbp+50h+var_78]
0x1800087c2  mov     [rsp+150h+var_F8], rax
0x1800087c7  and     eax, 3
0x1800087ca  jz      short loc_180008811
0x1800087cc  sub     rax, 1
0x1800087d0  jz      short loc_1800087F5
0x1800087d2  cmp     rax, 1
0x1800087d6  jnz     short loc_180008811
0x1800087d8  mov     rax, [rbp+50h+var_80]
0x1800087dc  mov     [rsp+150h+var_100], rax
0x1800087e1  lea     rdx, [rbp+50h+var_B0]
0x1800087e5  lea     rcx, [rsp+150h+var_130]
0x1800087ea  mov     rax, [rax+10h]
0x1800087ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f3  jmp     short loc_180008840
0x1800087f5  mov     rax, [rbp+50h+var_80]
0x1800087f9  mov     [rsp+150h+var_100], rax
0x1800087fe  mov     rax, [rbp+50h+var_88]
0x180008802  mov     [rsp+150h+var_108], rax
0x180008807  mov     [rbp+50h+var_78], 0
0x18000880f  jmp     short loc_180008840
0x180008811  movaps  xmm0, [rbp+50h+var_B0]
0x180008815  movups  [rsp+150h+var_130], xmm0
0x18000881a  movaps  xmm1, [rbp+50h+var_A0]
0x18000881e  movups  [rsp+150h+var_120], xmm1
0x180008823  movsd   xmm0, [rbp+50h+var_90]
0x180008828  movsd   [rsp+150h+var_110], xmm0
0x18000882e  mov     rax, [rbp+50h+var_88]
0x180008832  mov     [rsp+150h+var_108], rax
0x180008837  mov     rax, [rbp+50h+var_80]
0x18000883b  mov     [rsp+150h+var_100], rax
0x180008840  mov     rdx, rdi; struct std::any *
0x180008843  lea     rcx, [rsp+150h+var_F0]; this
0x180008848  call    ??0any@std@@QEAA@$$QEAV01@@Z; std::any::any(std::any &&)
0x18000884d  mov     rbx, rax
0x180008850  mov     rax, [rbp+50h+var_78]
0x180008854  and     eax, 3
0x180008857  sub     rax, 1
0x18000885b  jz      short loc_180008870
0x18000885d  cmp     rax, 1
0x180008861  jnz     short loc_180008880
0x180008863  mov     rcx, [rbp+50h+var_80]
0x180008867  mov     rax, [rcx]
0x18000886a  lea     rcx, [rbp+50h+var_B0]
0x18000886e  jmp     short loc_18000887B
0x180008870  mov     rax, [rbp+50h+var_80]
0x180008874  mov     rcx, [rbp+50h+var_88]
0x180008878  mov     rax, [rax]
0x18000887b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008880  mov     [rbp+50h+var_78], 0
0x180008888  mov     rax, [rbx+38h]
0x18000888c  mov     [rbp+50h+var_78], rax
0x180008890  and     eax, 3
0x180008893  jz      short loc_1800088D5
0x180008895  sub     rax, 1
0x180008899  jz      short loc_1800088BB
0x18000889b  cmp     rax, 1
0x18000889f  jnz     short loc_1800088D5
0x1800088a1  mov     rax, [rbx+30h]
0x1800088a5  mov     [rbp+50h+var_80], rax
0x1800088a9  mov     rdx, rbx
0x1800088ac  lea     rcx, [rbp+50h+var_B0]
0x1800088b0  mov     rax, [rax+10h]
0x1800088b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b9  jmp     short loc_1800088FE
0x1800088bb  mov     rax, [rbx+30h]
0x1800088bf  mov     [rbp+50h+var_80], rax
0x1800088c3  mov     rax, [rbx+28h]
0x1800088c7  mov     [rbp+50h+var_88], rax
0x1800088cb  mov     qword ptr [rbx+38h], 0
0x1800088d3  jmp     short loc_1800088FE
0x1800088d5  movups  xmm0, xmmword ptr [rbx]
0x1800088d8  movaps  [rbp+50h+var_B0], xmm0
0x1800088dc  movups  xmm1, xmmword ptr [rbx+10h]
0x1800088e0  movaps  [rbp+50h+var_A0], xmm1
0x1800088e4  movsd   xmm0, qword ptr [rbx+20h]
0x1800088e9  movsd   [rbp+50h+var_90], xmm0
0x1800088ee  mov     rax, [rbx+28h]
0x1800088f2  mov     [rbp+50h+var_88], rax
0x1800088f6  mov     rax, [rbx+30h]
0x1800088fa  mov     [rbp+50h+var_80], rax
0x1800088fe  mov     rcx, rbx; this
0x180008901  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x180008906  lea     rdx, [rsp+150h+var_130]
0x18000890b  mov     rcx, rdi; this
0x18000890e  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180008913  nop
0x180008914  mov     rax, [rsp+150h+var_F8]
0x180008919  and     eax, 3
0x18000891c  sub     rax, 1
0x180008920  jz      short loc_18000892F
0x180008922  cmp     rax, 1
0x180008926  jnz     short loc_180008942
0x180008928  lea     rcx, [rsp+150h+var_130]
0x18000892d  jmp     short loc_180008934
0x18000892f  mov     rcx, [rsp+150h+var_108]
0x180008934  mov     rax, [rsp+150h+var_100]
0x180008939  mov     rax, [rax]
0x18000893c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008941  nop
0x180008942  test    rsi, rsi
0x180008945  jz      short loc_180008950
0x180008947  mov     rcx, rsi; lpCriticalSection
0x18000894a  call    cs:__imp_LeaveCriticalSection
0x180008950  mov     rax, [rbp+50h+var_78]
0x180008954  and     rax, 0FFFFFFFFFFFFFFFCh
0x180008958  lea     rcx, ??_R0X@8; void `RTTI Type Descriptor'
0x18000895f  cmovnz  rcx, rax
0x180008963  add     rcx, 8
0x180008967  lea     rdx, qword_18013AC80
0x18000896e  call    cs:__imp___std_type_info_compare
0x180008974  mov     rcx, [rbp+50h+var_78]
0x180008978  test    eax, eax
0x18000897a  jz      short loc_1800089D2
0x18000897c  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180008980  jz      short loc_1800089CC
0x180008982  lea     rdx, ??_R0?AV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@8; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> `RTTI Type Descriptor'
0x180008989  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x18000898e  test    al, al
0x180008990  jz      short loc_1800089CC
0x180008992  lea     rbx, [rbp+50h+var_B0]
0x180008996  mov     rax, [rbx+8]
0x18000899a  test    rax, rax
0x18000899d  jz      short loc_1800089A3
0x18000899f  lock inc dword ptr [rax+8]
0x1800089a3  mov     rcx, [rbx]
0x1800089a6  mov     rbx, [rbx+8]
0x1800089aa  mov     rax, [rcx]
0x1800089ad  mov     rax, [rax+8]
0x1800089b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b6  test    rbx, rbx
0x1800089b9  jz      loc_180008A54
0x1800089bf  mov     rcx, rbx; this
0x1800089c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800089c7  jmp     loc_180008A54
0x1800089cc  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x1800089d2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800089d6  jz      loc_180008A74
0x1800089dc  lea     rdx, ??_R0?AV?$function@$$A6AXXZ@std@@@8; std::function<void (void)> `RTTI Type Descriptor'
0x1800089e3  call    ??8type_info@@QEBA_NAEBV0@@Z; type_info::operator==(type_info const &)
0x1800089e8  test    al, al
0x1800089ea  jz      loc_180008A74
0x1800089f0  mov     rax, [rbp+50h+var_88]
0x1800089f4  test    rax, rax
0x1800089f7  jz      short loc_180008A74
0x1800089f9  mov     [rbp+50h+var_38], 0
0x180008a01  mov     rcx, [rax+38h]
0x180008a05  test    rcx, rcx
0x180008a08  jz      short loc_180008A6D
0x180008a0a  mov     rax, [rcx]
0x180008a0d  lea     rdx, [rbp+50h+var_70]
0x180008a11  mov     rax, [rax]
0x180008a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a19  mov     rdx, rax
0x180008a1c  mov     [rbp+50h+var_38], rax
0x180008a20  test    rax, rax
0x180008a23  jz      short loc_180008A6D
0x180008a25  mov     rcx, [rax]
0x180008a28  mov     rax, [rcx+10h]
0x180008a2c  mov     rcx, rdx
0x180008a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a34  mov     rcx, [rbp+50h+var_38]
0x180008a38  test    rcx, rcx
0x180008a3b  jz      short loc_180008A54
0x180008a3d  mov     rax, [rcx]
0x180008a40  lea     rdx, [rbp+50h+var_70]
0x180008a44  cmp     rcx, rdx
0x180008a47  setnz   dl
0x180008a4a  mov     rax, [rax+20h]
0x180008a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a53  nop
0x180008a54  mov     rax, [rbp+50h+var_78]
0x180008a58  and     eax, 3
0x180008a5b  sub     rax, 1
0x180008a5f  jz      short loc_180008A7A
0x180008a61  cmp     rax, 1
0x180008a65  jnz     short loc_180008A8B
0x180008a67  lea     rcx, [rbp+50h+var_B0]
0x180008a6b  jmp     short loc_180008A7E
0x180008a6d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180008a73  int     3; Trap to Debugger
0x180008a74  call    ?_Throw_bad_any_cast@std@@YAXXZ; std::_Throw_bad_any_cast(void)
0x180008a7a  mov     rcx, [rbp+50h+var_88]
0x180008a7e  mov     rax, [rbp+50h+var_80]
0x180008a82  mov     rax, [rax]
0x180008a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8a  nop
0x180008a8b  mov     rcx, [rbp+50h+var_30]
0x180008a8f  xor     rcx, rsp; StackCookie
0x180008a92  call    __security_check_cookie
0x180008a97  add     rsp, 138h
0x180008a9e  pop     rdi
0x180008a9f  pop     rsi
0x180008aa0  pop     rbx
0x180008aa1  pop     rbp
0x180008aa2  retn
```
