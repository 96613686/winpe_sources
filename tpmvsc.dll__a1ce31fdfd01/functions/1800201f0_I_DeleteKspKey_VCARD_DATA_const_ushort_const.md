# I_DeleteKspKey(VCARD_DATA const *,ushort const *)

- ea: `0x1800201f0`
- end: `0x1800203f5`
- name: `?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z`
- size: `517`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800085b8`
- `0x180008d28`
- `0x180009154`
- `0x18000a81c`
- `0x18001670c`
- `0x180017448`
- `0x180020040`

## callees

- `0x180001ec0`
- `0x1800068dc`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x18001a31c`
- `0x18001ccdc`
- `0x18001d644`
- `0x1800201f0`
- `0x1800348a0`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800202be`
- `ncrypt!NCryptOpenKey` at `0x1800202be`
- `ncrypt!NCryptDeleteKey` at `0x180020342`
- `ncrypt!NCryptDeleteKey` at `0x180020342`

## string_xrefs

- `0x180020310`: `Unable to open KSP key`
- `0x180020227`: `I_DeleteKspKey`
- `0x180020386`: `Unable to delete KSP key`

## pseudocode

```c
__int64 __fastcall I_DeleteKspKey(const struct VCARD_DATA *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  SECURITY_STATUS v7; // edi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  SECURITY_STATUS v10; // ebx
  unsigned int v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+34h] [rbp-4Ch] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v16; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-38h] BYREF
  char v18[16]; // [rsp+60h] [rbp-20h] BYREF

  v13 = 0;
  v14 = 0;
  strcpy(v18, "I_DeleteKspKey");
  v17[0] = v18;
  v17[1] = &v14;
  v17[2] = &v13;
  lambda_2e75b3a536e5f43e73da19b5467f24fa_::operator()(v17);
  v14 = 1;
  v16 = v17;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v7 = NCryptOpenKey(*((_QWORD *)a1 + 11), &phKey, a2, 0, 0x40u);
  if ( v7 )
  {
    WppTraceIndent(v6, 2);
    v8 = I_MapSecurityStatusToWinError(v7);
    v13 = v8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v7,
        (__int64)"Unable to open KSP key");
LABEL_17:
      v8 = v13;
    }
  }
  else
  {
    v10 = NCryptDeleteKey(phKey, 0);
    if ( !v10 )
    {
      phKey = 0;
      goto LABEL_17;
    }
    WppTraceIndent(v9, 2);
    v11 = I_MapSecurityStatusToWinError(v10);
    v13 = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v10,
        (__int64)"Unable to delete KSP key");
      v11 = v13;
    }
    v8 = v11;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  WppTraceUnwinder__lambda_2e75b3a536e5f43e73da19b5467f24fa____::_WppTraceUnwinder__lambda_2e75b3a536e5f43e73da19b5467f24fa____(&v16);
  return v8;
}

```

## disassembly

```asm
0x1800201f0  mov     [rsp-8+arg_10], rbx
0x1800201f5  mov     [rsp-8+arg_18], rdi
0x1800201fa  push    rbp
0x1800201fb  mov     rbp, rsp
0x1800201fe  sub     rsp, 80h
0x180020205  mov     rax, cs:__security_cookie
0x18002020c  xor     rax, rsp
0x18002020f  mov     [rbp+var_10], rax
0x180020213  mov     rbx, rdx
0x180020216  mov     rdi, rcx
0x180020219  mov     [rbp+var_50], 0
0x180020220  mov     [rbp+var_4C], 0
0x180020227  movsd   xmm0, qword ptr cs:aIDeletekspkey; "I_DeleteKspKey"
0x18002022f  movsd   qword ptr [rbp+var_20], xmm0
0x180020234  mov     eax, dword ptr cs:aIDeletekspkey+8; "KspKey"
0x18002023a  mov     dword ptr [rbp+var_20+8], eax
0x18002023d  movzx   eax, word ptr cs:aIDeletekspkey+0Ch; "ey"
0x180020244  mov     word ptr [rbp+var_20+0Ch], ax
0x180020248  mov     al, byte ptr cs:aIDeletekspkey+0Eh; ""
0x18002024e  mov     [rbp+var_20+0Eh], al
0x180020251  lea     rax, [rbp+var_20]
0x180020255  mov     [rbp+var_38], rax
0x180020259  lea     rax, [rbp+var_4C]
0x18002025d  mov     [rbp+var_30], rax
0x180020261  lea     rax, [rbp+var_50]
0x180020265  mov     [rbp+var_28], rax
0x180020269  lea     rcx, [rbp+var_38]
0x18002026d  call    _lambda_2e75b3a536e5f43e73da19b5467f24fa___operator__
0x180020272  mov     [rbp+var_4C], 1
0x180020279  lea     rax, [rbp+var_38]
0x18002027d  mov     [rbp+var_40], rax
0x180020281  test    rdi, rdi
0x180020284  jnz     short loc_18002028B
0x180020286  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002028b  test    rbx, rbx
0x18002028e  jnz     short loc_180020295
0x180020290  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020295  mov     [rbp+phKey], 0
0x18002029d  xor     edx, edx
0x18002029f  lea     rcx, [rbp+phKey]
0x1800202a3  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800202a8  mov     [rsp+80h+dwFlags], 40h ; '@'; dwFlags
0x1800202b0  xor     r9d, r9d; dwLegacyKeySpec
0x1800202b3  mov     r8, rbx; pszKeyName
0x1800202b6  lea     rdx, [rbp+phKey]; phKey
0x1800202ba  mov     rcx, [rdi+58h]; hProvider
0x1800202be  call    cs:__imp_NCryptOpenKey
0x1800202c4  mov     edi, eax
0x1800202c6  test    eax, eax
0x1800202c8  jz      short loc_18002033C
0x1800202ca  mov     edx, 2
0x1800202cf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800202d4  mov     ecx, edi; int
0x1800202d6  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x1800202db  mov     ebx, eax
0x1800202dd  mov     [rbp+var_50], eax
0x1800202e0  lea     rdx, WPP_GLOBAL_Control
0x1800202e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202ee  cmp     rcx, rdx
0x1800202f1  jz      loc_1800203BF
0x1800202f7  test    byte ptr [rcx+1Ch], 1
0x1800202fb  jz      loc_1800203BF
0x180020301  cmp     byte ptr [rcx+19h], 2
0x180020305  jb      loc_1800203BF
0x18002030b  mov     edx, 2Ah ; '*'
0x180020310  lea     rax, aUnableToOpenKs; "Unable to open KSP key"
0x180020317  mov     [rsp+80h+var_58], rax
0x18002031c  mov     [rsp+80h+dwFlags], edi
0x180020320  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180020327  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18002032e  mov     rcx, [rcx+10h]
0x180020332  call    WPP_SF_sDs
0x180020337  jmp     loc_1800203BC
0x18002033c  xor     edx, edx; dwFlags
0x18002033e  mov     rcx, [rbp+phKey]; hKey
0x180020342  call    cs:__imp_NCryptDeleteKey
0x180020348  mov     ebx, eax
0x18002034a  test    eax, eax
0x18002034c  jz      short loc_1800203B4
0x18002034e  mov     edx, 2
0x180020353  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020358  mov     ecx, ebx; int
0x18002035a  call    ?I_MapSecurityStatusToWinError@@YAKJ@Z; I_MapSecurityStatusToWinError(long)
0x18002035f  mov     [rbp+var_50], eax
0x180020362  lea     rdx, WPP_GLOBAL_Control
0x180020369  mov     rcx, cs:WPP_GLOBAL_Control
0x180020370  cmp     rcx, rdx
0x180020373  jz      short loc_1800203B0
0x180020375  test    byte ptr [rcx+1Ch], 1
0x180020379  jz      short loc_1800203B0
0x18002037b  cmp     byte ptr [rcx+19h], 2
0x18002037f  jb      short loc_1800203B0
0x180020381  mov     edx, 2Bh ; '+'
0x180020386  lea     rax, aUnableToDelete_3; "Unable to delete KSP key"
0x18002038d  mov     [rsp+80h+var_58], rax
0x180020392  mov     [rsp+80h+dwFlags], ebx
0x180020396  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002039d  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800203a4  mov     rcx, [rcx+10h]
0x1800203a8  call    WPP_SF_sDs
0x1800203ad  mov     eax, [rbp+var_50]
0x1800203b0  mov     ebx, eax
0x1800203b2  jmp     short loc_1800203BF
0x1800203b4  mov     [rbp+phKey], 0
0x1800203bc  mov     ebx, [rbp+var_50]
0x1800203bf  lea     rcx, [rbp+phKey]
0x1800203c3  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800203c8  nop
0x1800203c9  lea     rcx, [rbp+var_40]
0x1800203cd  call    WppTraceUnwinder__lambda_2e75b3a536e5f43e73da19b5467f24fa_______WppTraceUnwinder__lambda_2e75b3a536e5f43e73da19b5467f24fa____
0x1800203d2  mov     eax, ebx
0x1800203d4  mov     rcx, [rbp+var_10]
0x1800203d8  xor     rcx, rsp; StackCookie
0x1800203db  call    __security_check_cookie
0x1800203e0  lea     r11, [rsp+80h+var_s0]
0x1800203e8  mov     rbx, [r11+20h]
0x1800203ec  mov     rdi, [r11+28h]
0x1800203f0  mov     rsp, r11
0x1800203f3  pop     rbp
0x1800203f4  retn
```
