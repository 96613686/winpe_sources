# NtsKeyExchangeCallbackComplete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,long,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,NtsForNtpInfoInternal &)

- ea: `0x180054efc`
- end: `0x1800551a2`
- name: `?NtsKeyExchangeCallbackComplete@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J0AEAUNtsForNtpInfoInternal@@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180054b50`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180034488`
- `0x18003a6b8`
- `0x18003b8fc`
- `0x18003d270`
- `0x180051424`
- `0x180053618`
- `0x180054efc`
- `0x180055674`
- `0x180056a44`
- `0x180056a88`
- `0x180056b14`
- `0x180056c5c`

## string_xrefs

- `0x1800550ea`: `SetKeyExchangeEvent: Server %s has no keyExchangeCompleteEvent\n`
- `0x180054f50`: `NtsKeyExchangeCallbackComplete: KE succeeded for %s- attempting to update global state\n`
- `0x180054fd8`: `NtsKeyExchangeCallbackComplete: server %s not found\n`
- `0x18005515c`: `NtsKeyExchangeCallbackComplete: Notified completion for %s\n`
- `0x180055110`: `NtsKeyExchangeCallbackComplete: Failed to notify completion for %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NtsKeyExchangeCallbackComplete(_QWORD *a1, int a2, _QWORD *a3, __int64 a4)
{
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // rdx
  void *v12; // rdx
  wil::details *v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v18[3]; // [rsp+28h] [rbp-60h] BYREF

  v18[1] = a1;
  v18[2] = a3;
  if ( a2 < 0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
    {
      if ( a3[3] <= 7u )
        v9 = a3;
      else
        v9 = (_QWORD *)*a3;
      FileLogAdd(L"NtsKeyExchangeCallbackFail: %s failed with error: 0x%08X\n", v9, (unsigned int)a2);
    }
  }
  else if ( (unsigned __int8)FileLogAllowEntry(200) )
  {
    if ( a1[3] <= 7u )
      v8 = a1;
    else
      v8 = (_QWORD *)*a1;
    FileLogAdd(L"NtsKeyExchangeCallbackComplete: KE succeeded for %s- attempting to update global state\n", v8);
  }
  wil::critical_section::lock(&g_NtsState, &v17);
  std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(
    &qword_1800A4928,
    v18,
    a1);
  v10 = v18[0];
  if ( v18[0] == qword_1800A4928 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(200) )
    {
      if ( a1[3] <= 7u )
        v11 = a1;
      else
        v11 = (_QWORD *)*a1;
      FileLogAdd(L"NtsKeyExchangeCallbackComplete: server %s not found\n", v11);
    }
  }
  else
  {
    ++*(_DWORD *)(v18[0] + 260LL);
    *(_DWORD *)(v10 + 256) = a2;
    if ( a2 < 0 )
    {
      std::vector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,wil::secure_allocator<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>>::clear(v10 + 280);
      std::unique_ptr<AeadCryptoWrapper>::reset(v10 + 272, 0);
    }
    else
    {
      *(_BYTE *)(v10 + 64) = 1;
      *(_DWORD *)(v10 + 236) = *(_DWORD *)(a4 + 172);
      std::unique_ptr<AeadCryptoWrapper>::operator=<std::default_delete<AeadCryptoWrapper>,0>(
        v10 + 272,
        (__int64 *)(a4 + 208));
      *(_OWORD *)(v10 + 104) = *(_OWORD *)(a4 + 40);
      *(_OWORD *)(v10 + 120) = *(_OWORD *)(a4 + 56);
      *(_OWORD *)(v10 + 136) = *(_OWORD *)(a4 + 72);
      *(_OWORD *)(v10 + 152) = *(_OWORD *)(a4 + 88);
      *(_OWORD *)(v10 + 168) = *(_OWORD *)(a4 + 104);
      *(_OWORD *)(v10 + 184) = *(_OWORD *)(a4 + 120);
      *(_OWORD *)(v10 + 200) = *(_OWORD *)(a4 + 136);
      *(_OWORD *)(v10 + 216) = *(_OWORD *)(a4 + 152);
      std::vector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,wil::secure_allocator<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>>::operator=(
        v10 + 280,
        a4 + 216);
      *(_BYTE *)(v10 + 264) = 0;
      std::_Tree<std::_Tset_traits<std::array<unsigned char,32>,std::less<std::array<unsigned char,32>>,std::allocator<std::array<unsigned char,32>>,0>>::clear(v10 + 304);
    }
    v13 = *(wil::details **)(v10 + 328);
    if ( v13 )
    {
      wil::details::SetEvent(v13, v12);
      if ( (unsigned __int8)FileLogAllowEntry(200) )
      {
        if ( a1[3] <= 7u )
          v15 = a1;
        else
          v15 = (_QWORD *)*a1;
        FileLogAdd(L"NtsKeyExchangeCallbackComplete: Notified completion for %s\n", v15);
      }
    }
    else
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(L"SetKeyExchangeEvent: Server %s has no keyExchangeCompleteEvent\n");
      if ( (unsigned __int8)FileLogAllowEntry(0) )
      {
        if ( a1[3] <= 7u )
          v14 = a1;
        else
          v14 = (_QWORD *)*a1;
        FileLogAdd(L"NtsKeyExchangeCallbackComplete: Failed to notify completion for %s\n", v14);
      }
      std::vector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,wil::secure_allocator<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>>::clear(v10 + 280);
      std::unique_ptr<AeadCryptoWrapper>::reset(v10 + 272, 0);
      *(_DWORD *)(v10 + 256) = -2147024890;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
  std::wstring::~wstring((__int64)a1);
  return std::wstring::~wstring((__int64)a3);
}

```

## disassembly

```asm
0x180054efc  push    rbx
0x180054efe  push    rbp
0x180054eff  push    rsi
0x180054f00  push    rdi
0x180054f01  push    r13
0x180054f03  push    r14
0x180054f05  push    r15
0x180054f07  sub     rsp, 50h
0x180054f0b  mov     rax, cs:__security_cookie
0x180054f12  xor     rax, rsp
0x180054f15  mov     [rsp+88h+var_48], rax
0x180054f1a  mov     r13, r9
0x180054f1d  mov     rsi, r8
0x180054f20  mov     ebp, edx
0x180054f22  mov     rdi, rcx
0x180054f25  mov     [rsp+88h+var_58], rcx
0x180054f2a  mov     [rsp+88h+var_50], r8
0x180054f2f  test    edx, edx
0x180054f31  js      short loc_180054F5E
0x180054f33  mov     ecx, 0C8h
0x180054f38  call    FileLogAllowEntry
0x180054f3d  test    al, al
0x180054f3f  jz      short loc_180054F87
0x180054f41  cmp     qword ptr [rdi+18h], 7
0x180054f46  jbe     short loc_180054F4D
0x180054f48  mov     rdx, [rdi]
0x180054f4b  jmp     short loc_180054F50
0x180054f4d  mov     rdx, rdi
0x180054f50  lea     rcx, aNtskeyexchange_6; "NtsKeyExchangeCallbackComplete: KE succ"...
0x180054f57  call    FileLogAdd
0x180054f5c  jmp     short loc_180054F87
0x180054f5e  xor     ecx, ecx
0x180054f60  call    FileLogAllowEntry
0x180054f65  test    al, al
0x180054f67  jz      short loc_180054F87
0x180054f69  cmp     qword ptr [rsi+18h], 7
0x180054f6e  jbe     short loc_180054F75
0x180054f70  mov     rdx, [rsi]
0x180054f73  jmp     short loc_180054F78
0x180054f75  mov     rdx, rsi
0x180054f78  mov     r8d, ebp
0x180054f7b  lea     rcx, aNtskeyexchange_3; "NtsKeyExchangeCallbackFail: %s failed w"...
0x180054f82  call    FileLogAdd
0x180054f87  lea     rdx, [rsp+88h+var_68]
0x180054f8c  lea     rcx, ?g_NtsState@@3UNtsState@@A; NtsState g_NtsState
0x180054f93  call    ?lock@critical_section@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::critical_section::lock(void)
0x180054f98  nop
0x180054f99  mov     r8, rdi
0x180054f9c  lea     rdx, [rsp+88h+var_60]
0x180054fa1  lea     rcx, qword_1800A4928
0x180054fa8  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UNtsForNtpInfoInternal@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,NtsForNtpInfoInternal,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,NtsForNtpInfoInternal>>,0>>::find(std::wstring const &)
0x180054fad  mov     rbx, [rsp+88h+var_60]
0x180054fb2  cmp     rbx, cs:qword_1800A4928
0x180054fb9  jnz     short loc_180054FEA
0x180054fbb  mov     ecx, 0C8h
0x180054fc0  call    FileLogAllowEntry
0x180054fc5  test    al, al
0x180054fc7  jz      short loc_180054FE5
0x180054fc9  cmp     qword ptr [rdi+18h], 7
0x180054fce  jbe     short loc_180054FD5
0x180054fd0  mov     rdx, [rdi]
0x180054fd3  jmp     short loc_180054FD8
0x180054fd5  mov     rdx, rdi
0x180054fd8  lea     rcx, aNtskeyexchange_0; "NtsKeyExchangeCallbackComplete: server "...
0x180054fdf  call    FileLogAdd
0x180054fe4  nop
0x180054fe5  jmp     loc_180055169
0x180054fea  inc     dword ptr [rbx+104h]
0x180054ff0  mov     [rbx+100h], ebp
0x180054ff6  lea     r14, [rbx+110h]
0x180054ffd  lea     r15, [rbx+118h]
0x180055004  test    ebp, ebp
0x180055006  js      loc_1800550B0
0x18005500c  mov     byte ptr [rbx+40h], 1
0x180055010  mov     eax, [r13+0ACh]
0x180055017  mov     [rbx+0ECh], eax
0x18005501d  lea     rdx, [r13+0D0h]
0x180055024  mov     rcx, r14
0x180055027  call    ??$?4U?$default_delete@VAeadCryptoWrapper@@@std@@$0A@@?$unique_ptr@VAeadCryptoWrapper@@U?$default_delete@VAeadCryptoWrapper@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<AeadCryptoWrapper>::operator=<std::default_delete<AeadCryptoWrapper>,0>(std::unique_ptr<AeadCryptoWrapper> &&)
0x18005502c  movups  xmm0, xmmword ptr [r13+28h]
0x180055031  movups  xmmword ptr [rbx+68h], xmm0
0x180055035  movups  xmm1, xmmword ptr [r13+38h]
0x18005503a  movups  xmmword ptr [rbx+78h], xmm1
0x18005503e  movups  xmm0, xmmword ptr [r13+48h]
0x180055043  movups  xmmword ptr [rbx+88h], xmm0
0x18005504a  movups  xmm1, xmmword ptr [r13+58h]
0x18005504f  movups  xmmword ptr [rbx+98h], xmm1
0x180055056  movups  xmm0, xmmword ptr [r13+68h]
0x18005505b  movups  xmmword ptr [rbx+0A8h], xmm0
0x180055062  movups  xmm1, xmmword ptr [r13+78h]
0x180055067  movups  xmmword ptr [rbx+0B8h], xmm1
0x18005506e  movups  xmm0, xmmword ptr [r13+88h]
0x180055076  movups  xmmword ptr [rbx+0C8h], xmm0
0x18005507d  movups  xmm1, xmmword ptr [r13+98h]
0x180055085  movups  xmmword ptr [rbx+0D8h], xmm1
0x18005508c  lea     rdx, [r13+0D8h]
0x180055093  mov     rcx, r15
0x180055096  call    ??4?$vector@V?$vector@EU?$secure_allocator@E@wil@@@std@@U?$secure_allocator@V?$vector@EU?$secure_allocator@E@wil@@@std@@@wil@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<std::vector<uchar,wil::secure_allocator<uchar>>,wil::secure_allocator<std::vector<uchar,wil::secure_allocator<uchar>>>>::operator=(std::vector<std::vector<uchar,wil::secure_allocator<uchar>>,wil::secure_allocator<std::vector<uchar,wil::secure_allocator<uchar>>>> const &)
0x18005509b  mov     byte ptr [rbx+108h], 0
0x1800550a2  lea     rcx, [rbx+130h]
0x1800550a9  call    ?clear@?$_Tree@V?$_Tset_traits@V?$array@E$0CA@@std@@U?$less@V?$array@E$0CA@@std@@@2@V?$allocator@V?$array@E$0CA@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::array<uchar,32>,std::less<std::array<uchar,32>>,std::allocator<std::array<uchar,32>>,0>>::clear(void)
0x1800550ae  jmp     short loc_1800550C2
0x1800550b0  mov     rcx, r15
0x1800550b3  call    ?clear@?$vector@V?$vector@EU?$secure_allocator@E@wil@@@std@@U?$secure_allocator@V?$vector@EU?$secure_allocator@E@wil@@@std@@@wil@@@std@@QEAAXXZ; std::vector<std::vector<uchar,wil::secure_allocator<uchar>>,wil::secure_allocator<std::vector<uchar,wil::secure_allocator<uchar>>>>::clear(void)
0x1800550b8  xor     edx, edx
0x1800550ba  mov     rcx, r14
0x1800550bd  call    ?reset@?$unique_ptr@VAeadCryptoWrapper@@U?$default_delete@VAeadCryptoWrapper@@@std@@@std@@QEAAXPEAVAeadCryptoWrapper@@@Z; std::unique_ptr<AeadCryptoWrapper>::reset(AeadCryptoWrapper *)
0x1800550c2  mov     rcx, [rbx+148h]; this
0x1800550c9  test    rcx, rcx
0x1800550cc  jnz     short loc_18005513A
0x1800550ce  mov     ecx, 0C8h
0x1800550d3  call    FileLogAllowEntry
0x1800550d8  test    al, al
0x1800550da  jz      short loc_1800550F6
0x1800550dc  lea     rdx, [rbx+48h]
0x1800550e0  cmp     qword ptr [rdx+18h], 7
0x1800550e5  jbe     short loc_1800550EA
0x1800550e7  mov     rdx, [rdx]
0x1800550ea  lea     rcx, aSetkeyexchange; "SetKeyExchangeEvent: Server %s has no k"...
0x1800550f1  call    FileLogAdd
0x1800550f6  xor     ecx, ecx
0x1800550f8  call    FileLogAllowEntry
0x1800550fd  test    al, al
0x1800550ff  jz      short loc_18005511C
0x180055101  cmp     qword ptr [rdi+18h], 7
0x180055106  jbe     short loc_18005510D
0x180055108  mov     rdx, [rdi]
0x18005510b  jmp     short loc_180055110
0x18005510d  mov     rdx, rdi
0x180055110  lea     rcx, aNtskeyexchange_4; "NtsKeyExchangeCallbackComplete: Failed "...
0x180055117  call    FileLogAdd
0x18005511c  mov     rcx, r15
0x18005511f  call    ?clear@?$vector@V?$vector@EU?$secure_allocator@E@wil@@@std@@U?$secure_allocator@V?$vector@EU?$secure_allocator@E@wil@@@std@@@wil@@@std@@QEAAXXZ; std::vector<std::vector<uchar,wil::secure_allocator<uchar>>,wil::secure_allocator<std::vector<uchar,wil::secure_allocator<uchar>>>>::clear(void)
0x180055124  xor     edx, edx
0x180055126  mov     rcx, r14
0x180055129  call    ?reset@?$unique_ptr@VAeadCryptoWrapper@@U?$default_delete@VAeadCryptoWrapper@@@std@@@std@@QEAAXPEAVAeadCryptoWrapper@@@Z; std::unique_ptr<AeadCryptoWrapper>::reset(AeadCryptoWrapper *)
0x18005512e  mov     dword ptr [rbx+100h], 80070006h
0x180055138  jmp     short loc_180055169
0x18005513a  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18005513f  mov     ecx, 0C8h
0x180055144  call    FileLogAllowEntry
0x180055149  test    al, al
0x18005514b  jz      short loc_180055169
0x18005514d  cmp     qword ptr [rdi+18h], 7
0x180055152  jbe     short loc_180055159
0x180055154  mov     rdx, [rdi]
0x180055157  jmp     short loc_18005515C
0x180055159  mov     rdx, rdi
0x18005515c  lea     rcx, aNtskeyexchange_5; "NtsKeyExchangeCallbackComplete: Notifie"...
0x180055163  call    FileLogAdd
0x180055168  nop
0x180055169  lea     rcx, [rsp+88h+var_68]
0x18005516e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180055173  nop
0x180055174  mov     rcx, rdi
0x180055177  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005517c  nop
0x18005517d  mov     rcx, rsi
0x180055180  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055185  mov     rcx, [rsp+88h+var_48]
0x18005518a  xor     rcx, rsp; StackCookie
0x18005518d  call    __security_check_cookie
0x180055192  add     rsp, 50h
0x180055196  pop     r15
0x180055198  pop     r14
0x18005519a  pop     r13
0x18005519c  pop     rdi
0x18005519d  pop     rsi
0x18005519e  pop     rbp
0x18005519f  pop     rbx
0x1800551a0  retn
```
