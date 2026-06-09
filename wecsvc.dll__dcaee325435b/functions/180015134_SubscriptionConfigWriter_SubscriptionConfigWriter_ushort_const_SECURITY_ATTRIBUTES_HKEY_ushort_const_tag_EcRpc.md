# SubscriptionConfigWriter::SubscriptionConfigWriter(ushort const *,_SECURITY_ATTRIBUTES *,HKEY__ *,ushort const *,tag_EcRpcMetadataPropertyList &)

- ea: `0x180015134`
- end: `0x1800153b9`
- name: `??0SubscriptionConfigWriter@@QEAA@PEBGPEAU_SECURITY_ATTRIBUTES@@PEAUHKEY__@@0AEAUtag_EcRpcMetadataPropertyList@@@Z`
- size: `645`
- prototype: `SubscriptionConfigWriter *__fastcall(SubscriptionConfigWriter *this, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, HKEY, const unsigned __int16 *, struct tag_EcRpcMetadataPropertyList *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b80`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800060e8`
- `0x1800062d4`
- `0x180006400`
- `0x1800064e0`
- `0x18000669c`
- `0x180006910`
- `0x180015134`
- `0x1800189e8`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800152e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800152e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SubscriptionConfigWriter *__fastcall SubscriptionConfigWriter::SubscriptionConfigWriter(
        SubscriptionConfigWriter *this,
        const unsigned __int16 *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        HKEY a4,
        const unsigned __int16 *a5,
        struct tag_EcRpcMetadataPropertyList *a6)
{
  HKEY *phkResult; // r15
  __int64 v9; // rsi
  LPCWSTR *v10; // rax
  LPCWSTR *v11; // rcx
  __int64 v12; // rdi
  LPCWSTR *v13; // rax
  LPCWSTR *v14; // rcx
  const WCHAR *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // edi
  DWORD dwDisposition; // [rsp+50h] [rbp-59h] BYREF
  void **pExceptionObject; // [rsp+58h] [rbp-51h] BYREF
  char v21; // [rsp+60h] [rbp-49h]
  const char *v22; // [rsp+68h] [rbp-41h]
  __int64 v23; // [rsp+70h] [rbp-39h]
  __int64 v24; // [rsp+78h] [rbp-31h]
  unsigned int v25; // [rsp+80h] [rbp-29h]
  int v26; // [rsp+84h] [rbp-25h]
  int v27; // [rsp+88h] [rbp-21h]
  SubscriptionConfigWriter *v28; // [rsp+90h] [rbp-19h]
  LPCWSTR lpSubKey[2]; // [rsp+98h] [rbp-11h] BYREF
  __int64 v30; // [rsp+A8h] [rbp-1h]
  unsigned __int64 v31; // [rsp+B0h] [rbp+7h]

  v28 = this;
  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  phkResult = (HKEY *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &SubscriptionConfigWriter::`vftable';
  *((_QWORD *)this + 3) = a6;
  *((_BYTE *)this + 32) = 0;
  *((_BYTE *)this + 40) = 0;
  v31 = 7;
  v30 = 0;
  LOWORD(lpSubKey[0]) = 0;
  ValidateRegKeyName(a2);
  std::wstring::reserve(lpSubKey, 48);
  std::wstring::assign(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  if ( v30 == -1 || v30 == -2 )
    std::wstring::_Xlen();
  v9 = v30 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v30 + 1, 0) )
  {
    v10 = lpSubKey;
    if ( v31 >= 8 )
      v10 = (LPCWSTR *)lpSubKey[0];
    *((_WORD *)v10 + v30) = 92;
    v11 = lpSubKey;
    if ( v31 >= 8 )
      v11 = (LPCWSTR *)lpSubKey[0];
    v30 = v9;
    *((_WORD *)v11 + v9) = 0;
  }
  std::wstring::append(lpSubKey, L"Subscriptions");
  if ( v30 == -1 || v30 == -2 )
    std::wstring::_Xlen();
  v12 = v30 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v30 + 1, 0) )
  {
    v13 = lpSubKey;
    if ( v31 >= 8 )
      v13 = (LPCWSTR *)lpSubKey[0];
    *((_WORD *)v13 + v30) = 92;
    v14 = lpSubKey;
    if ( v31 >= 8 )
      v14 = (LPCWSTR *)lpSubKey[0];
    v30 = v12;
    *((_WORD *)v14 + v12) = 0;
  }
  std::wstring::append(lpSubKey, a2);
  dwDisposition = 0;
  v15 = (const WCHAR *)lpSubKey;
  if ( v31 >= 8 )
    v15 = lpSubKey[0];
  v17 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0, 0, 0x2001Fu, 0, phkResult, &dwDisposition);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v17);
    }
    v21 = 0;
    v22 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v23 = 0;
    v24 = 0;
    v25 = v17;
    v26 = -1;
    v27 = 580;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( dwDisposition == 1 )
    *((_BYTE *)this + 40) = 1;
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(lpSubKey, v16, 0);
  return this;
}

```

## disassembly

```asm
0x180015134  mov     [rsp-8+arg_10], rbx
0x180015139  push    rbp
0x18001513a  push    rsi
0x18001513b  push    rdi
0x18001513c  push    r12
0x18001513e  push    r13
0x180015140  push    r14
0x180015142  push    r15
0x180015144  lea     rbp, [rsp-17h]
0x180015149  sub     rsp, 0C0h
0x180015150  mov     rax, cs:__security_cookie
0x180015157  xor     rax, rsp
0x18001515a  mov     [rbp+47h+var_38], rax
0x18001515e  mov     r14, rdx
0x180015161  mov     rbx, rcx
0x180015164  mov     [rbp+47h+var_60], rcx
0x180015168  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18001516f  mov     [rcx], rax
0x180015172  xor     r12d, r12d
0x180015175  mov     [rcx+8], r12d
0x180015179  lea     r15, [rcx+10h]
0x18001517d  mov     [r15], r12
0x180015180  lea     rax, ??_7SubscriptionConfigWriter@@6B@; const SubscriptionConfigWriter::`vftable'
0x180015187  mov     [rcx], rax
0x18001518a  mov     rax, [rbp+47h+arg_28]
0x18001518e  mov     [rcx+18h], rax
0x180015192  mov     [rcx+20h], r12b
0x180015196  mov     [rcx+28h], r12b
0x18001519a  mov     [rbp+47h+var_40], 7
0x1800151a2  mov     [rbp+47h+var_48], r12
0x1800151a6  mov     word ptr [rbp+47h+lpSubKey], r12w
0x1800151ab  mov     rcx, rdx; unsigned __int16 *
0x1800151ae  call    ?ValidateRegKeyName@@YAXPEBG@Z; ValidateRegKeyName(ushort const *)
0x1800151b3  lea     edx, [r12+30h]
0x1800151b8  lea     rcx, [rbp+47h+lpSubKey]
0x1800151bc  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800151c1  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800151c8  lea     rcx, [rbp+47h+lpSubKey]
0x1800151cc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800151d1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800151d5  mov     rax, rdi
0x1800151d8  mov     rsi, [rbp+47h+var_48]
0x1800151dc  sub     rax, rsi
0x1800151df  cmp     rax, 1
0x1800151e3  jbe     loc_1800153AD
0x1800151e9  inc     rsi
0x1800151ec  xor     r8d, r8d
0x1800151ef  mov     rdx, rsi
0x1800151f2  lea     rcx, [rbp+47h+lpSubKey]
0x1800151f6  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800151fb  lea     r13d, [r12+5Ch]
0x180015200  test    al, al
0x180015202  jz      short loc_180015232
0x180015204  mov     rcx, [rbp+47h+var_48]
0x180015208  lea     rax, [rbp+47h+lpSubKey]
0x18001520c  cmp     [rbp+47h+var_40], 8
0x180015211  cmovnb  rax, [rbp+47h+lpSubKey]
0x180015216  mov     [rax+rcx*2], r13w
0x18001521b  lea     rcx, [rbp+47h+lpSubKey]
0x18001521f  cmp     [rbp+47h+var_40], 8
0x180015224  cmovnb  rcx, [rbp+47h+lpSubKey]
0x180015229  mov     [rbp+47h+var_48], rsi
0x18001522d  mov     [rcx+rsi*2], r12w
0x180015232  lea     rdx, aSubscriptions_0; "Subscriptions"
0x180015239  lea     rcx, [rbp+47h+lpSubKey]
0x18001523d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180015242  mov     rax, [rbp+47h+var_48]
0x180015246  sub     rdi, rax
0x180015249  cmp     rdi, 1
0x18001524d  jbe     loc_1800153B3
0x180015253  lea     rdi, [rax+1]
0x180015257  xor     r8d, r8d
0x18001525a  mov     rdx, rdi
0x18001525d  lea     rcx, [rbp+47h+lpSubKey]
0x180015261  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180015266  test    al, al
0x180015268  jz      short loc_180015298
0x18001526a  mov     rcx, [rbp+47h+var_48]
0x18001526e  lea     rax, [rbp+47h+lpSubKey]
0x180015272  cmp     [rbp+47h+var_40], 8
0x180015277  cmovnb  rax, [rbp+47h+lpSubKey]
0x18001527c  mov     [rax+rcx*2], r13w
0x180015281  lea     rcx, [rbp+47h+lpSubKey]
0x180015285  cmp     [rbp+47h+var_40], 8
0x18001528a  cmovnb  rcx, [rbp+47h+lpSubKey]
0x18001528f  mov     [rbp+47h+var_48], rdi
0x180015293  mov     [rcx+rdi*2], r12w
0x180015298  mov     rdx, r14
0x18001529b  lea     rcx, [rbp+47h+lpSubKey]
0x18001529f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800152a4  mov     [rbp+47h+dwDisposition], r12d
0x1800152a8  lea     rdx, [rbp+47h+lpSubKey]
0x1800152ac  cmp     [rbp+47h+var_40], 8
0x1800152b1  cmovnb  rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800152b6  lea     rax, [rbp+47h+dwDisposition]
0x1800152ba  mov     [rsp+0F0h+lpdwDisposition], rax; lpdwDisposition
0x1800152bf  mov     [rsp+0F0h+phkResult], r15; phkResult
0x1800152c4  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800152c9  mov     [rsp+0F0h+samDesired], 2001Fh; samDesired
0x1800152d1  mov     [rsp+0F0h+dwOptions], r12d; dwOptions
0x1800152d6  xor     r9d, r9d; lpClass
0x1800152d9  xor     r8d, r8d; Reserved
0x1800152dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800152e3  call    cs:__imp_RegCreateKeyExW
0x1800152e9  mov     edi, eax
0x1800152eb  test    eax, eax
0x1800152ed  jnz     short loc_180015332
0x1800152ef  cmp     [rbp+47h+dwDisposition], 1
0x1800152f3  jnz     short loc_1800152F9
0x1800152f5  mov     byte ptr [rbx+28h], 1
0x1800152f9  xor     r8d, r8d
0x1800152fc  mov     dl, 1
0x1800152fe  lea     rcx, [rbp+47h+lpSubKey]
0x180015302  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015307  nop
0x180015308  mov     rax, rbx
0x18001530b  mov     rcx, [rbp+47h+var_38]
0x18001530f  xor     rcx, rsp; StackCookie
0x180015312  call    __security_check_cookie
0x180015317  mov     rbx, [rsp+0F0h+arg_10]
0x18001531f  add     rsp, 0C0h
0x180015326  pop     r15
0x180015328  pop     r14
0x18001532a  pop     r13
0x18001532c  pop     r12
0x18001532e  pop     rdi
0x18001532f  pop     rsi
0x180015330  pop     rbp
0x180015331  retn
0x180015332  lea     rax, WPP_GLOBAL_Control
0x180015339  mov     rcx, cs:WPP_GLOBAL_Control
0x180015340  cmp     rcx, rax
0x180015343  jz      short loc_180015369
0x180015345  test    byte ptr [rcx+1Ch], 40h
0x180015349  jz      short loc_180015369
0x18001534b  cmp     byte ptr [rcx+19h], 2
0x18001534f  jb      short loc_180015369
0x180015351  mov     edx, 18h
0x180015356  mov     r9d, edi
0x180015359  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180015360  mov     rcx, [rcx+10h]
0x180015364  call    WPP_SF_D
0x180015369  mov     [rbp+47h+var_90], r12b
0x18001536d  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x180015374  mov     [rbp+47h+var_88], rax
0x180015378  mov     [rbp+47h+var_80], r12
0x18001537c  mov     [rbp+47h+var_78], r12
0x180015380  mov     [rbp+47h+var_70], edi
0x180015383  mov     [rbp+47h+var_6C], 0FFFFFFFFh
0x18001538a  mov     [rbp+47h+var_68], 244h
0x180015391  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180015398  mov     [rbp+47h+pExceptionObject], rax
0x18001539c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800153a3  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x1800153a7  call    _CxxThrowException_0
0x1800153ad  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x1800153b3  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
