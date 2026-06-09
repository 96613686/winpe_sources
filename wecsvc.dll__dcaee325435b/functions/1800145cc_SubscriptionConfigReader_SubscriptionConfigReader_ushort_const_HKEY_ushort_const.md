# SubscriptionConfigReader::SubscriptionConfigReader(ushort const *,HKEY__ *,ushort const *)

- ea: `0x1800145cc`
- end: `0x180014835`
- name: `??0SubscriptionConfigReader@@QEAA@PEBGPEAUHKEY__@@0@Z`
- size: `617`
- prototype: `SubscriptionConfigReader *__fastcall(SubscriptionConfigReader *this, const unsigned __int16 *, HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800042d0`
- `0x180004760`
- `0x180004b80`
- `0x1800052cc`

## callees

- `0x180001260`
- `0x18000195c`
- `0x1800032dc`
- `0x1800060e8`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000669c`
- `0x180006910`
- `0x1800145cc`
- `0x1800189e8`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001475b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001475b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SubscriptionConfigReader *__fastcall SubscriptionConfigReader::SubscriptionConfigReader(
        SubscriptionConfigReader *this,
        const unsigned __int16 *a2,
        HKEY a3,
        const unsigned __int16 *a4)
{
  HKEY *phkResult; // r15
  __int64 v7; // rdi
  LPCWSTR *v8; // rax
  LPCWSTR *v9; // rcx
  __int64 v10; // rbx
  LPCWSTR *v11; // rax
  LPCWSTR *v12; // rcx
  const WCHAR *v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-39h] BYREF
  char v18; // [rsp+38h] [rbp-31h]
  const char *v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h]
  __int64 v21; // [rsp+50h] [rbp-19h]
  unsigned int v22; // [rsp+58h] [rbp-11h]
  int v23; // [rsp+5Ch] [rbp-Dh]
  int v24; // [rsp+60h] [rbp-9h]
  SubscriptionConfigReader *v25; // [rsp+68h] [rbp-1h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v27; // [rsp+80h] [rbp+17h]
  unsigned __int64 v28; // [rsp+88h] [rbp+1Fh]

  v25 = this;
  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  phkResult = (HKEY *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &SubscriptionGlobalsReader::`vftable';
  v28 = 7;
  v27 = 0;
  LOWORD(lpSubKey[0]) = 0;
  ValidateRegKeyName(a2);
  std::wstring::reserve(lpSubKey, 48);
  std::wstring::assign(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  if ( v27 == -1 || v27 == -2 )
    goto LABEL_24;
  v7 = v27 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v27 + 1, 0) )
  {
    v8 = lpSubKey;
    if ( v28 >= 8 )
      v8 = (LPCWSTR *)lpSubKey[0];
    *((_WORD *)v8 + v27) = 92;
    v9 = lpSubKey;
    if ( v28 >= 8 )
      v9 = (LPCWSTR *)lpSubKey[0];
    v27 = v7;
    *((_WORD *)v9 + v7) = 0;
  }
  std::wstring::append(lpSubKey, L"Subscriptions");
  if ( v27 == -1 || v27 == -2 )
LABEL_24:
    std::_Xlength_error("string too long");
  v10 = v27 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(lpSubKey, v27 + 1, 0) )
  {
    v11 = lpSubKey;
    if ( v28 >= 8 )
      v11 = (LPCWSTR *)lpSubKey[0];
    *((_WORD *)v11 + v27) = 92;
    v12 = lpSubKey;
    if ( v28 >= 8 )
      v12 = (LPCWSTR *)lpSubKey[0];
    v27 = v10;
    *((_WORD *)v12 + v10) = 0;
  }
  std::wstring::append(lpSubKey, a2);
  v13 = (const WCHAR *)lpSubKey;
  if ( v28 >= 8 )
    v13 = lpSubKey[0];
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, 0x20019u, phkResult);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v15);
    }
    v18 = 0;
    v19 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v20 = 0;
    v21 = 0;
    v22 = v15;
    v23 = -1;
    v24 = 190;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(lpSubKey, v14, 0);
  return this;
}

```

## disassembly

```asm
0x1800145cc  mov     [rsp-8+arg_10], rbx
0x1800145d1  mov     [rsp-8+arg_18], rsi
0x1800145d6  push    rbp
0x1800145d7  push    rdi
0x1800145d8  push    r13
0x1800145da  push    r14
0x1800145dc  push    r15
0x1800145de  lea     rbp, [rsp-37h]
0x1800145e3  sub     rsp, 0A0h
0x1800145ea  mov     rax, cs:__security_cookie
0x1800145f1  xor     rax, rsp
0x1800145f4  mov     [rbp+57h+var_30], rax
0x1800145f8  mov     r14, rdx
0x1800145fb  mov     rsi, rcx
0x1800145fe  mov     [rbp+57h+var_58], rcx
0x180014602  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180014609  mov     [rcx], rax
0x18001460c  mov     dword ptr [rcx+8], 0
0x180014613  lea     r15, [rcx+10h]
0x180014617  mov     qword ptr [r15], 0
0x18001461e  lea     rax, ??_7SubscriptionGlobalsReader@@6B@; const SubscriptionGlobalsReader::`vftable'
0x180014625  mov     [rcx], rax
0x180014628  mov     [rbp+57h+var_38], 7
0x180014630  mov     [rbp+57h+var_40], 0
0x180014638  xor     eax, eax
0x18001463a  mov     word ptr [rbp+57h+lpSubKey], ax
0x18001463e  mov     rcx, rdx; unsigned __int16 *
0x180014641  call    ?ValidateRegKeyName@@YAXPEBG@Z; ValidateRegKeyName(ushort const *)
0x180014646  mov     edx, 30h ; '0'
0x18001464b  lea     rcx, [rbp+57h+lpSubKey]
0x18001464f  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x180014654  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001465b  lea     rcx, [rbp+57h+lpSubKey]
0x18001465f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180014664  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014668  mov     rax, rbx
0x18001466b  mov     rdi, [rbp+57h+var_40]
0x18001466f  sub     rax, rdi
0x180014672  cmp     rax, 1
0x180014676  jbe     loc_180014828
0x18001467c  inc     rdi
0x18001467f  xor     r8d, r8d
0x180014682  mov     rdx, rdi
0x180014685  lea     rcx, [rbp+57h+lpSubKey]
0x180014689  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18001468e  lea     r13d, [rbx+5Dh]
0x180014692  test    al, al
0x180014694  jz      short loc_1800146C5
0x180014696  mov     rcx, [rbp+57h+var_40]
0x18001469a  lea     rax, [rbp+57h+lpSubKey]
0x18001469e  cmp     [rbp+57h+var_38], 8
0x1800146a3  cmovnb  rax, [rbp+57h+lpSubKey]
0x1800146a8  mov     [rax+rcx*2], r13w
0x1800146ad  lea     rcx, [rbp+57h+lpSubKey]
0x1800146b1  cmp     [rbp+57h+var_38], 8
0x1800146b6  cmovnb  rcx, [rbp+57h+lpSubKey]
0x1800146bb  mov     [rbp+57h+var_40], rdi
0x1800146bf  xor     eax, eax
0x1800146c1  mov     [rcx+rdi*2], ax
0x1800146c5  lea     rdx, aSubscriptions_0; "Subscriptions"
0x1800146cc  lea     rcx, [rbp+57h+lpSubKey]
0x1800146d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800146d5  mov     rax, [rbp+57h+var_40]
0x1800146d9  sub     rbx, rax
0x1800146dc  cmp     rbx, 1
0x1800146e0  jbe     loc_180014828
0x1800146e6  lea     rbx, [rax+1]
0x1800146ea  xor     r8d, r8d
0x1800146ed  mov     rdx, rbx
0x1800146f0  lea     rcx, [rbp+57h+lpSubKey]
0x1800146f4  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800146f9  test    al, al
0x1800146fb  jz      short loc_18001472C
0x1800146fd  mov     rcx, [rbp+57h+var_40]
0x180014701  lea     rax, [rbp+57h+lpSubKey]
0x180014705  cmp     [rbp+57h+var_38], 8
0x18001470a  cmovnb  rax, [rbp+57h+lpSubKey]
0x18001470f  mov     [rax+rcx*2], r13w
0x180014714  lea     rcx, [rbp+57h+lpSubKey]
0x180014718  cmp     [rbp+57h+var_38], 8
0x18001471d  cmovnb  rcx, [rbp+57h+lpSubKey]
0x180014722  mov     [rbp+57h+var_40], rbx
0x180014726  xor     eax, eax
0x180014728  mov     [rcx+rbx*2], ax
0x18001472c  mov     rdx, r14
0x18001472f  lea     rcx, [rbp+57h+lpSubKey]
0x180014733  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180014738  lea     rdx, [rbp+57h+lpSubKey]
0x18001473c  cmp     [rbp+57h+var_38], 8
0x180014741  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180014746  mov     [rsp+0C0h+phkResult], r15; phkResult
0x18001474b  mov     r9d, 20019h; samDesired
0x180014751  xor     r8d, r8d; ulOptions
0x180014754  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001475b  call    cs:__imp_RegOpenKeyExW
0x180014761  mov     ebx, eax
0x180014763  test    eax, eax
0x180014765  jz      loc_1800147EE
0x18001476b  lea     rax, WPP_GLOBAL_Control
0x180014772  mov     rcx, cs:WPP_GLOBAL_Control
0x180014779  cmp     rcx, rax
0x18001477c  jz      short loc_1800147A2
0x18001477e  test    byte ptr [rcx+1Ch], 40h
0x180014782  jz      short loc_1800147A2
0x180014784  cmp     byte ptr [rcx+19h], 2
0x180014788  jb      short loc_1800147A2
0x18001478a  mov     edx, 13h
0x18001478f  mov     r9d, ebx
0x180014792  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x180014799  mov     rcx, [rcx+10h]
0x18001479d  call    WPP_SF_D
0x1800147a2  mov     [rbp+57h+var_88], 0
0x1800147a6  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800147ad  mov     [rbp+57h+var_80], rax
0x1800147b1  mov     [rbp+57h+var_78], 0
0x1800147b9  mov     [rbp+57h+var_70], 0
0x1800147c1  mov     [rbp+57h+var_68], ebx
0x1800147c4  mov     [rbp+57h+var_64], 0FFFFFFFFh
0x1800147cb  mov     [rbp+57h+var_60], 0BEh
0x1800147d2  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800147d9  mov     [rbp+57h+pExceptionObject], rax
0x1800147dd  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800147e4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800147e8  call    _CxxThrowException_0
0x1800147ee  xor     r8d, r8d
0x1800147f1  mov     dl, 1
0x1800147f3  lea     rcx, [rbp+57h+lpSubKey]
0x1800147f7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800147fc  nop
0x1800147fd  mov     rax, rsi
0x180014800  mov     rcx, [rbp+57h+var_30]
0x180014804  xor     rcx, rsp; StackCookie
0x180014807  call    __security_check_cookie
0x18001480c  lea     r11, [rsp+0C0h+var_20]
0x180014814  mov     rbx, [r11+40h]
0x180014818  mov     rsi, [r11+48h]
0x18001481c  mov     rsp, r11
0x18001481f  pop     r15
0x180014821  pop     r14
0x180014823  pop     r13
0x180014825  pop     rdi
0x180014826  pop     rbp
0x180014827  retn
0x180014828  lea     rcx, aStringTooLong; "string too long"
0x18001482f  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
