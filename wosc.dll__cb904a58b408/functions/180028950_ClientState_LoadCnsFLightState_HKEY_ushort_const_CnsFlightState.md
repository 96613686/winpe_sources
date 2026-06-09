# ClientState::LoadCnsFLightState(HKEY__ *,ushort const *,CnsFlightState &)

- ea: `0x180028950`
- end: `0x180028bab`
- name: `?LoadCnsFLightState@ClientState@@CAXPEAUHKEY__@@PEBGAEAUCnsFlightState@@@Z`
- size: `603`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, struct CnsFlightState *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180028bb4`

## callees

- `0x18000a230`
- `0x1800101fc`
- `0x18001a718`
- `0x180028250`
- `0x180028550`
- `0x180028714`
- `0x180028950`
- `0x180029c94`

## string_xrefs

- `0x180028b24`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180028b39`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180028b4e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180028b66`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180028b7e`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180028b96`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClientState::LoadCnsFLightState(HKEY a1, const unsigned __int16 *a2, struct CnsFlightState *a3)
{
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // eax
  char v9; // bl
  unsigned int Value; // eax
  unsigned int DWord; // eax
  unsigned int v15; // eax
  unsigned int v17; // eax
  int v18; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+20h] [rbp-48h]
  int v20; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v22,
    0);
  v7 = RegWow64Helpers::OpenKey(a1, a2, v6, 0x20019u, &v22);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x617,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v7,
      v18);
  if ( v22 )
  {
    v8 = RegWow64Helpers::InitializeCoTaskMemNativeString(v22, 0);
    v9 = 1;
    if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61B,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v8,
        v18);
    Value = RegWow64Helpers::GetValue(v22, 0, L"CnsReceiptTime", 0x40u, (char *)a3 + 28, 8u, 0);
    if ( ((Value + 0x80000000) & 0x80000000) == 0 && Value != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61E,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)Value,
        v19);
    DWord = RegWow64Helpers::GetDWord(v22, 0, L"CnsWnsChangeStamp", (unsigned int *)a3 + 6);
    if ( ((DWord + 0x80000000) & 0x80000000) == 0 && DWord != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x621,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)DWord,
        v19);
    v15 = RegWow64Helpers::InitializeCoTaskMemNativeString(v22, 0);
    if ( ((v15 + 0x80000000) & 0x80000000) == 0 && v15 != -2147024894 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x624,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v15,
        v19);
    v17 = RegWow64Helpers::GetValue(v22, 0, L"CnsAcknowledgedTime", 0x40u, (char *)a3 + 64, 8u, 0);
    if ( ((v17 + 0x80000000) & 0x80000000) != 0 || v17 == -2147024894 )
      v9 = 0;
    if ( v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x627,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v17,
        v20);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
}

```

## disassembly

```asm
0x180028950  mov     rax, rsp
0x180028953  push    rbx
0x180028954  push    rsi
0x180028955  push    rdi
0x180028956  push    r14
0x180028958  sub     rsp, 48h
0x18002895c  mov     rsi, r8
0x18002895f  mov     rbx, rdx
0x180028962  mov     rdi, rcx
0x180028965  mov     qword ptr [rax+20h], 0
0x18002896d  xor     edx, edx
0x18002896f  lea     rcx, [rax+20h]
0x180028973  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028978  lea     rax, [rsp+68h+arg_18]
0x180028980  mov     [rsp+68h+var_48], rax; int
0x180028985  mov     r9d, 20019h; unsigned int
0x18002898b  mov     rdx, rbx; unsigned __int16 *
0x18002898e  mov     rcx, rdi; HKEY
0x180028991  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x180028996  mov     rcx, [rsp+68h]; this
0x18002899b  test    eax, eax
0x18002899d  js      loc_180028B36
0x1800289a3  mov     rcx, [rsp+68h+arg_18]; HKEY
0x1800289ab  test    rcx, rcx
0x1800289ae  jz      loc_180028B0A
0x1800289b4  mov     r9, rsi
0x1800289b7  lea     r8, ?c_regvalCnsFlightVersion@ClientState@@0QBGB; "CnsFlightVersion"
0x1800289be  xor     edx, edx; unsigned __int16 *
0x1800289c0  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800289c5  mov     r14d, 80000000h
0x1800289cb  lea     ecx, [rax+r14]
0x1800289cf  mov     bl, 1
0x1800289d1  mov     edi, 80070002h
0x1800289d6  test    r14d, ecx
0x1800289d9  jnz     short loc_1800289E3
0x1800289db  cmp     eax, edi
0x1800289dd  jz      short loc_1800289E3
0x1800289df  mov     cl, bl
0x1800289e1  jmp     short loc_1800289E5
0x1800289e3  xor     cl, cl
0x1800289e5  mov     r10, [rsp+68h]
0x1800289ea  test    cl, cl
0x1800289ec  jnz     loc_180028B4B
0x1800289f2  lea     rax, [rsi+1Ch]
0x1800289f6  mov     [rsp+68h+var_38], 0; unsigned int *
0x1800289ff  mov     [rsp+68h+var_40], 8; unsigned int
0x180028a07  mov     [rsp+68h+var_48], rax; int
0x180028a0c  mov     r9d, 40h ; '@'; unsigned int
0x180028a12  lea     r8, ?c_regvalCnsReceiptTime@ClientState@@0QBGB; "CnsReceiptTime"
0x180028a19  xor     edx, edx; unsigned __int16 *
0x180028a1b  mov     rcx, [rsp+68h+arg_18]; HKEY
0x180028a23  call    ?GetValue@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1KPEAXKPEAK@Z; RegWow64Helpers::GetValue(HKEY__ * const,ushort const * const,ushort const * const,ulong,void *,ulong,ulong *)
0x180028a28  lea     ecx, [rax+r14]
0x180028a2c  test    r14d, ecx
0x180028a2f  jnz     short loc_180028A39
0x180028a31  cmp     eax, edi
0x180028a33  jz      short loc_180028A39
0x180028a35  mov     cl, bl
0x180028a37  jmp     short loc_180028A3B
0x180028a39  xor     cl, cl
0x180028a3b  mov     r10, [rsp+68h]
0x180028a40  test    cl, cl
0x180028a42  jnz     loc_180028B63
0x180028a48  lea     r9, [rsi+18h]; unsigned int *
0x180028a4c  lea     r8, ?c_regvalCnsWnsChangeStamp@ClientState@@0QBGB; "CnsWnsChangeStamp"
0x180028a53  xor     edx, edx; unsigned __int16 *
0x180028a55  mov     rcx, [rsp+68h+arg_18]; HKEY
0x180028a5d  call    ?GetDWord@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1PEAK@Z; RegWow64Helpers::GetDWord(HKEY__ * const,ushort const * const,ushort const * const,ulong *)
0x180028a62  lea     ecx, [rax+r14]
0x180028a66  test    r14d, ecx
0x180028a69  jnz     short loc_180028A73
0x180028a6b  cmp     eax, edi
0x180028a6d  jz      short loc_180028A73
0x180028a6f  mov     cl, bl
0x180028a71  jmp     short loc_180028A75
0x180028a73  xor     cl, cl
0x180028a75  mov     r10, [rsp+68h]
0x180028a7a  test    cl, cl
0x180028a7c  jnz     loc_180028B7B
0x180028a82  lea     r9, [rsi+28h]
0x180028a86  lea     r8, ?c_regvalCnsPayloadFileName@ClientState@@0QBGB; "CnsPayloadFileName"
0x180028a8d  xor     edx, edx; unsigned __int16 *
0x180028a8f  mov     rcx, [rsp+68h+arg_18]; HKEY
0x180028a97  call    ?InitializeCoTaskMemNativeString@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; RegWow64Helpers::InitializeCoTaskMemNativeString(HKEY__ * const,ushort const * const,ushort const * const,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180028a9c  lea     ecx, [rax+r14]
0x180028aa0  test    r14d, ecx
0x180028aa3  jnz     short loc_180028AAD
0x180028aa5  cmp     eax, edi
0x180028aa7  jz      short loc_180028AAD
0x180028aa9  mov     cl, bl
0x180028aab  jmp     short loc_180028AAF
0x180028aad  xor     cl, cl
0x180028aaf  mov     r10, [rsp+68h]
0x180028ab4  test    cl, cl
0x180028ab6  jnz     loc_180028B93
0x180028abc  lea     rax, [rsi+40h]
0x180028ac0  mov     [rsp+68h+var_38], 0; unsigned int *
0x180028ac9  mov     [rsp+68h+var_40], 8; unsigned int
0x180028ad1  mov     [rsp+68h+var_48], rax; int
0x180028ad6  mov     r9d, 40h ; '@'; unsigned int
0x180028adc  lea     r8, ?c_regvalCnsAcknowledgedTime@ClientState@@0QBGB; "CnsAcknowledgedTime"
0x180028ae3  xor     edx, edx; unsigned __int16 *
0x180028ae5  mov     rcx, [rsp+68h+arg_18]; HKEY
0x180028aed  call    ?GetValue@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1KPEAXKPEAK@Z; RegWow64Helpers::GetValue(HKEY__ * const,ushort const * const,ushort const * const,ulong,void *,ulong,ulong *)
0x180028af2  lea     ecx, [rax+r14]
0x180028af6  test    r14d, ecx
0x180028af9  jnz     short loc_180028AFF
0x180028afb  cmp     eax, edi
0x180028afd  jnz     short loc_180028B01
0x180028aff  xor     bl, bl
0x180028b01  mov     rcx, [rsp+68h]; this
0x180028b06  test    bl, bl
0x180028b08  jnz     short loc_180028B21
0x180028b0a  lea     rcx, [rsp+68h+arg_18]
0x180028b12  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028b17  add     rsp, 48h
0x180028b1b  pop     r14
0x180028b1d  pop     rdi
0x180028b1e  pop     rsi
0x180028b1f  pop     rbx
0x180028b20  retn
0x180028b21  mov     r9d, eax; char *
0x180028b24  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b2b  mov     edx, 627h; void *
0x180028b30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b36  mov     r9d, eax; char *
0x180028b39  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b40  mov     edx, 617h; void *
0x180028b45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b4b  mov     r9d, eax; char *
0x180028b4e  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b55  mov     edx, 61Bh; void *
0x180028b5a  mov     rcx, r10; this
0x180028b5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b63  mov     r9d, eax; char *
0x180028b66  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b6d  mov     edx, 61Eh; void *
0x180028b72  mov     rcx, r10; this
0x180028b75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b7b  mov     r9d, eax; char *
0x180028b7e  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b85  mov     edx, 621h; void *
0x180028b8a  mov     rcx, r10; this
0x180028b8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b93  mov     r9d, eax; char *
0x180028b96  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180028b9d  mov     edx, 624h; void *
0x180028ba2  mov     rcx, r10; this
0x180028ba5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
