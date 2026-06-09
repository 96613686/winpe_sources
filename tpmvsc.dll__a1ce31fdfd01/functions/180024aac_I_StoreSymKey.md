# I_StoreSymKey

- ea: `0x180024aac`
- end: `0x180024f0c`
- name: `I_StoreSymKey`
- size: `1120`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800225a0`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000653c`
- `0x1800068dc`
- `0x180007988`
- `0x18000a110`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c010`
- `0x18000c198`
- `0x18000fafc`
- `0x18001130c`
- `0x18001ce80`
- `0x18001e0e0`
- `0x18001e394`
- `0x18001e8f0`
- `0x18001f784`
- `0x180020040`
- `0x180024aac`
- `0x180028250`
- `0x18002bb98`
- `0x1800348a0`

## string_xrefs

- `0x180024d51`: `Unable to create protection key within retry limit`
- `0x180024db6`: `Unable to update key map record`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_StoreSymKey(const struct VCARD_DATA **a1, unsigned __int8 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // bl
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned int v12; // ebx
  unsigned int KspKey; // eax
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  int v16; // edx
  const char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int8 v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Guid; // [rsp+48h] [rbp-B8h] BYREF
  const struct VCARD_DATA **v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  int *v26; // [rsp+68h] [rbp-98h] BYREF
  __int16 v27; // [rsp+70h] [rbp-90h]
  _QWORD *v28; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v29[3]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v30; // [rsp+98h] [rbp-68h]
  _QWORD v31[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v33[4]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszKeyName[40]; // [rsp+F0h] [rbp-10h] BYREF
  int v35; // [rsp+140h] [rbp+40h]
  unsigned __int16 v36[48]; // [rsp+150h] [rbp+50h] BYREF
  char v37[16]; // [rsp+1B0h] [rbp+B0h] BYREF

  v23 = a1;
  v21 = a2;
  Guid = 0;
  v25 = 0;
  strcpy(v37, "I_StoreSymKey");
  v31[0] = v37;
  v31[1] = &v25;
  v31[2] = &Guid;
  lambda_c02248d9c428c0f2edf85595beb7ba58_::operator()(v31);
  v25 = 1;
  v28 = v31;
  v5 = (__int64)v23;
  if ( !v23 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v4);
    v5 = (__int64)v23;
  }
  if ( !(unsigned int)I_IsRoleAuthenticated(v5, 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  v8 = v21;
  if ( (unsigned __int8)(v21 + 0x80) > 0x20u )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
    v8 = v21;
  }
  memset_0(v36, 0, 0x54u);
  I_KeyMapGetRecord(*v23, v8, (struct KEY_MAP_RECORD *)v36);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v32);
  Guid = I_UnprotectMemory(v23 + 16, v32);
  if ( Guid )
  {
    WppTraceIndent(v9, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)"Unable to recover auth key");
    }
    v10 = Guid;
  }
  else
  {
    memset_0(pszKeyName, 0, sizeof(pszKeyName));
    v35 = 1;
    *(_QWORD *)v24 = 0;
    v12 = 0;
    KspKey = 0;
    while ( v12 < 0xA )
    {
      Guid = I_GenerateGuid(pszKeyName);
      if ( Guid )
      {
        WppTraceIndent(v14, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 65;
          v17 = "Unable to generate protection key name";
          goto LABEL_22;
        }
        goto LABEL_23;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
        (NCRYPT_HANDLE *)v24,
        0);
      KspKey = I_CreateKspKey((__int64)*v23, 0x47u, 4, (NCRYPT_KEY_HANDLE *)v24, pszKeyName, v32, 0);
      Guid = KspKey;
      if ( KspKey != -2146893809 )
        break;
      ++v12;
    }
    if ( KspKey )
    {
      WppTraceIndent(v11, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 66;
        v17 = "Unable to create protection key within retry limit";
LABEL_22:
        WPP_SF_sDs(
          v15[2],
          v16,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)v17);
      }
LABEL_23:
      v10 = Guid;
      goto LABEL_43;
    }
    v26 = v24;
    v27 = 258;
    Guid = I_KeyMapSetRecord(*v23, v21, (const struct KEY_MAP_RECORD *)pszKeyName);
    if ( Guid )
    {
      WppTraceIndent(v18, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)"Unable to update key map record");
      }
      v10 = Guid;
    }
    else
    {
      v29[0] = &v23;
      v29[1] = &v21;
      v29[2] = v36;
      v30 = 258;
      v33[0] = &v23;
      v33[1] = &v21;
      v33[2] = v24;
      v33[3] = a3;
      Guid = lambda_a5f41a715fc63d3f8d41a489aab81cde_::operator()(v33);
      if ( Guid )
      {
        WppTraceIndent(v19, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            (_DWORD)WPP_pszIndent,
            Guid,
            (__int64)"Updating key maps failed");
        }
      }
      else
      {
        HIBYTE(v27) = 0;
        HIBYTE(v30) = 0;
        I_DeleteKeyMaterial(*v23, (const struct KEY_MAP_RECORD *)v36);
      }
      v10 = Guid;
      wil::details::ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9___::operator()(v29);
    }
    wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()((__int64)&v26);
LABEL_43:
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>((NCRYPT_HANDLE *)v24);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v32);
  WppTraceUnwinder__lambda_c02248d9c428c0f2edf85595beb7ba58____::_WppTraceUnwinder__lambda_c02248d9c428c0f2edf85595beb7ba58____(&v28);
  return v10;
}

```

## disassembly

```asm
0x180024aac  mov     [rsp-8+arg_10], rbx
0x180024ab1  push    rbp
0x180024ab2  push    rdi
0x180024ab3  push    r14
0x180024ab5  lea     rbp, [rsp-0D0h]
0x180024abd  sub     rsp, 1D0h
0x180024ac4  mov     rax, cs:__security_cookie
0x180024acb  xor     rax, rsp
0x180024ace  mov     [rbp+0E0h+var_20], rax
0x180024ad5  mov     rdi, r8
0x180024ad8  mov     [rsp+1E0h+var_190], rcx
0x180024add  mov     [rsp+1E0h+var_1A0], dl
0x180024ae1  mov     [rsp+1E0h+var_198], 0
0x180024ae9  mov     [rsp+1E0h+var_180], 0
0x180024af1  movsd   xmm0, qword ptr cs:aIStoresymkey; "I_StoreSymKey"
0x180024af9  movsd   qword ptr [rbp+0E0h+var_30], xmm0
0x180024b01  mov     eax, dword ptr cs:aIStoresymkey+8; "ymKey"
0x180024b07  mov     dword ptr [rbp+0E0h+var_30+8], eax
0x180024b0d  movzx   eax, word ptr cs:aIStoresymkey+0Ch; "y"
0x180024b14  mov     word ptr [rbp+0E0h+var_30+0Ch], ax
0x180024b1b  lea     rax, [rbp+0E0h+var_30]
0x180024b22  mov     [rbp+0E0h+var_140], rax
0x180024b26  lea     rax, [rsp+1E0h+var_180]
0x180024b2b  mov     [rbp+0E0h+var_138], rax
0x180024b2f  lea     rax, [rsp+1E0h+var_198]
0x180024b34  mov     [rbp+0E0h+var_130], rax
0x180024b38  lea     rcx, [rbp+0E0h+var_140]
0x180024b3c  call    _lambda_c02248d9c428c0f2edf85595beb7ba58___operator__
0x180024b41  mov     r14d, 1
0x180024b47  mov     [rsp+1E0h+var_180], r14d
0x180024b4c  lea     rax, [rbp+0E0h+var_140]
0x180024b50  mov     [rsp+1E0h+var_168], rax
0x180024b55  mov     rcx, [rsp+1E0h+var_190]
0x180024b5a  test    rcx, rcx
0x180024b5d  jnz     short loc_180024B69
0x180024b5f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024b64  mov     rcx, [rsp+1E0h+var_190]
0x180024b69  mov     edx, r14d
0x180024b6c  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x180024b71  test    eax, eax
0x180024b73  jnz     short loc_180024B7A
0x180024b75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024b7a  mov     bl, [rsp+1E0h+var_1A0]
0x180024b7e  lea     eax, [rbx-80h]
0x180024b81  cmp     al, 20h ; ' '
0x180024b83  jbe     short loc_180024B8E
0x180024b85  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024b8a  mov     bl, [rsp+1E0h+var_1A0]
0x180024b8e  xor     edx, edx; Val
0x180024b90  lea     r8d, [rdx+54h]; Size
0x180024b94  lea     rcx, [rbp+0E0h+var_90]; void *
0x180024b98  call    memset_0
0x180024b9d  lea     r8, [rbp+0E0h+var_90]; struct KEY_MAP_RECORD *
0x180024ba1  mov     dl, bl; unsigned __int8
0x180024ba3  mov     rcx, [rsp+1E0h+var_190]
0x180024ba8  mov     rcx, [rcx]; struct VCARD_DATA *
0x180024bab  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x180024bb0  lea     rcx, [rbp+0E0h+var_128]
0x180024bb4  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180024bb9  nop
0x180024bba  mov     rcx, [rsp+1E0h+var_190]
0x180024bbf  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180024bc3  lea     rdx, [rbp+0E0h+var_128]
0x180024bc7  call    ?I_UnprotectMemory@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_UnprotectMemory(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x180024bcc  mov     [rsp+1E0h+var_198], eax
0x180024bd0  test    eax, eax
0x180024bd2  jz      short loc_180024C36
0x180024bd4  mov     edx, 2
0x180024bd9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024bde  lea     rax, WPP_GLOBAL_Control
0x180024be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bec  cmp     rcx, rax
0x180024bef  jz      short loc_180024C2D
0x180024bf1  test    [rcx+1Ch], r14b
0x180024bf5  jz      short loc_180024C2D
0x180024bf7  cmp     byte ptr [rcx+19h], 2
0x180024bfb  jb      short loc_180024C2D
0x180024bfd  mov     edx, 40h ; '@'
0x180024c02  lea     rax, aUnableToRecove; "Unable to recover auth key"
0x180024c09  mov     [rsp+1E0h+var_1B8], rax
0x180024c0e  mov     eax, [rsp+1E0h+var_198]
0x180024c12  mov     dword ptr [rsp+1E0h+pszKeyName], eax
0x180024c16  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024c1d  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024c24  mov     rcx, [rcx+10h]
0x180024c28  call    WPP_SF_sDs
0x180024c2d  mov     ebx, [rsp+1E0h+var_198]
0x180024c31  jmp     loc_180024ED3
0x180024c36  xor     edx, edx; Val
0x180024c38  lea     r8d, [rdx+50h]; Size
0x180024c3c  lea     rcx, [rbp+0E0h+var_F0]; void *
0x180024c40  call    memset_0
0x180024c45  mov     [rbp+0E0h+var_A0], r14d
0x180024c49  mov     qword ptr [rsp+1E0h+var_188], 0
0x180024c52  xor     ebx, ebx
0x180024c54  xor     eax, eax
0x180024c56  cmp     ebx, 0Ah
0x180024c59  jnb     loc_180024D1F
0x180024c5f  lea     rcx, [rbp+0E0h+var_F0]; unsigned __int16 *
0x180024c63  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x180024c68  mov     [rsp+1E0h+var_198], eax
0x180024c6c  test    eax, eax
0x180024c6e  jnz     short loc_180024CBD
0x180024c70  xor     edx, edx
0x180024c72  lea     rcx, [rsp+1E0h+var_188]
0x180024c77  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180024c7c  mov     [rsp+1E0h+var_1B0], 0; int
0x180024c84  lea     rax, [rbp+0E0h+var_128]
0x180024c88  mov     [rsp+1E0h+var_1B8], rax; __int64
0x180024c8d  lea     rax, [rbp+0E0h+var_F0]
0x180024c91  mov     [rsp+1E0h+pszKeyName], rax; pszKeyName
0x180024c96  lea     r9, [rsp+1E0h+var_188]; int
0x180024c9b  mov     r8b, 4; int
0x180024c9e  mov     dl, 47h ; 'G'; int
0x180024ca0  mov     rcx, [rsp+1E0h+var_190]
0x180024ca5  mov     rcx, [rcx]; int
0x180024ca8  call    ?I_CreateKspKey@@YAKPEBUVCARD_DATA@@EEPEA_KPEBGAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@H@Z; I_CreateKspKey(VCARD_DATA const *,uchar,uchar,unsigned __int64 *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,int)
0x180024cad  mov     [rsp+1E0h+var_198], eax
0x180024cb1  cmp     eax, 8009000Fh
0x180024cb6  jnz     short loc_180024D1F
0x180024cb8  add     ebx, r14d
0x180024cbb  jmp     short loc_180024C56
0x180024cbd  mov     edx, 2
0x180024cc2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024cc7  lea     rax, WPP_GLOBAL_Control
0x180024cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cd5  cmp     rcx, rax
0x180024cd8  jz      short loc_180024D16
0x180024cda  test    [rcx+1Ch], r14b
0x180024cde  jz      short loc_180024D16
0x180024ce0  cmp     byte ptr [rcx+19h], 2
0x180024ce4  jb      short loc_180024D16
0x180024ce6  mov     edx, 41h ; 'A'
0x180024ceb  lea     rax, aUnableToGenera; "Unable to generate protection key name"
0x180024cf2  mov     [rsp+1E0h+var_1B8], rax
0x180024cf7  mov     eax, [rsp+1E0h+var_198]
0x180024cfb  mov     dword ptr [rsp+1E0h+pszKeyName], eax
0x180024cff  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024d06  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024d0d  mov     rcx, [rcx+10h]
0x180024d11  call    WPP_SF_sDs
0x180024d16  mov     ebx, [rsp+1E0h+var_198]
0x180024d1a  jmp     loc_180024EC8
0x180024d1f  test    eax, eax
0x180024d21  jz      short loc_180024D5A
0x180024d23  mov     edx, 2
0x180024d28  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024d2d  lea     rax, WPP_GLOBAL_Control
0x180024d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d3b  cmp     rcx, rax
0x180024d3e  jz      short loc_180024D16
0x180024d40  test    [rcx+1Ch], r14b
0x180024d44  jz      short loc_180024D16
0x180024d46  cmp     byte ptr [rcx+19h], 2
0x180024d4a  jb      short loc_180024D16
0x180024d4c  mov     edx, 42h ; 'B'
0x180024d51  lea     rax, aUnableToCreate_4; "Unable to create protection key within "...
0x180024d58  jmp     short loc_180024CF2
0x180024d5a  lea     rax, [rsp+1E0h+var_188]
0x180024d5f  mov     [rsp+1E0h+var_178], rax
0x180024d64  mov     [rsp+1E0h+var_170], 102h
0x180024d6b  lea     r8, [rbp+0E0h+var_F0]; struct KEY_MAP_RECORD *
0x180024d6f  mov     dl, [rsp+1E0h+var_1A0]; unsigned __int8
0x180024d73  mov     rcx, [rsp+1E0h+var_190]
0x180024d78  mov     rcx, [rcx]; struct VCARD_DATA *
0x180024d7b  call    ?I_KeyMapSetRecord@@YAKPEBUVCARD_DATA@@EPEBUKEY_MAP_RECORD@@@Z; I_KeyMapSetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD const *)
0x180024d80  mov     [rsp+1E0h+var_198], eax
0x180024d84  test    eax, eax
0x180024d86  jz      short loc_180024DEA
0x180024d88  mov     edx, 2
0x180024d8d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024d92  lea     rax, WPP_GLOBAL_Control
0x180024d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180024da0  cmp     rcx, rax
0x180024da3  jz      short loc_180024DE1
0x180024da5  test    [rcx+1Ch], r14b
0x180024da9  jz      short loc_180024DE1
0x180024dab  cmp     byte ptr [rcx+19h], 2
0x180024daf  jb      short loc_180024DE1
0x180024db1  mov     edx, 43h ; 'C'
0x180024db6  lea     rax, aUnableToUpdate_3; "Unable to update key map record"
0x180024dbd  mov     [rsp+1E0h+var_1B8], rax
0x180024dc2  mov     eax, [rsp+1E0h+var_198]
0x180024dc6  mov     dword ptr [rsp+1E0h+pszKeyName], eax
0x180024dca  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024dd1  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024dd8  mov     rcx, [rcx+10h]
0x180024ddc  call    WPP_SF_sDs
0x180024de1  mov     ebx, [rsp+1E0h+var_198]
0x180024de5  jmp     loc_180024EBD
0x180024dea  lea     rax, [rsp+1E0h+var_190]
0x180024def  mov     [rbp+0E0h+var_160], rax
0x180024df3  lea     rax, [rsp+1E0h+var_1A0]
0x180024df8  mov     [rbp+0E0h+var_158], rax
0x180024dfc  lea     rax, [rbp+0E0h+var_90]
0x180024e00  mov     [rbp+0E0h+var_150], rax
0x180024e04  mov     [rbp+0E0h+var_148], 102h
0x180024e0a  lea     rax, [rsp+1E0h+var_190]
0x180024e0f  mov     [rbp+0E0h+var_110], rax
0x180024e13  lea     rax, [rsp+1E0h+var_1A0]
0x180024e18  mov     [rbp+0E0h+var_108], rax
0x180024e1c  lea     rax, [rsp+1E0h+var_188]
0x180024e21  mov     [rbp+0E0h+var_100], rax
0x180024e25  mov     [rbp+0E0h+var_F8], rdi
0x180024e29  lea     rcx, [rbp+0E0h+var_110]
0x180024e2d  call    _lambda_a5f41a715fc63d3f8d41a489aab81cde___operator__
0x180024e32  mov     [rsp+1E0h+var_198], eax
0x180024e36  test    eax, eax
0x180024e38  jz      short loc_180024E95
0x180024e3a  mov     edx, 2
0x180024e3f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024e44  lea     rax, WPP_GLOBAL_Control
0x180024e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e52  cmp     rcx, rax
0x180024e55  jz      short loc_180024EAF
0x180024e57  test    [rcx+1Ch], r14b
0x180024e5b  jz      short loc_180024EAF
0x180024e5d  cmp     byte ptr [rcx+19h], 2
0x180024e61  jb      short loc_180024EAF
0x180024e63  mov     edx, 47h ; 'G'
0x180024e68  lea     rax, aUpdatingKeyMap; "Updating key maps failed"
0x180024e6f  mov     [rsp+1E0h+var_1B8], rax
0x180024e74  mov     eax, [rsp+1E0h+var_198]
0x180024e78  mov     dword ptr [rsp+1E0h+pszKeyName], eax
0x180024e7c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024e83  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024e8a  mov     rcx, [rcx+10h]
0x180024e8e  call    WPP_SF_sDs
0x180024e93  jmp     short loc_180024EAF
0x180024e95  mov     byte ptr [rsp+1E0h+var_170+1], 0
0x180024e9a  mov     byte ptr [rbp+0E0h+var_148+1], 0
0x180024e9e  lea     rdx, [rbp+0E0h+var_90]; unsigned __int16 *
0x180024ea2  mov     rcx, [rsp+1E0h+var_190]
0x180024ea7  mov     rcx, [rcx]; struct VCARD_DATA *
0x180024eaa  call    I_DeleteKeyMaterial
0x180024eaf  mov     ebx, [rsp+1E0h+var_198]
0x180024eb3  lea     rcx, [rbp+0E0h+var_160]
0x180024eb7  call    wil__details__ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9_____operator__
0x180024ebc  nop
0x180024ebd  lea     rcx, [rsp+1E0h+var_178]
0x180024ec2  call    wil__details__ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f_____operator__
0x180024ec7  nop
0x180024ec8  lea     rcx, [rsp+1E0h+var_188]
0x180024ecd  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180024ed2  nop
0x180024ed3  lea     rcx, [rbp+0E0h+var_128]
0x180024ed7  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180024edc  nop
0x180024edd  lea     rcx, [rsp+1E0h+var_168]
0x180024ee2  call    WppTraceUnwinder__lambda_c02248d9c428c0f2edf85595beb7ba58_______WppTraceUnwinder__lambda_c02248d9c428c0f2edf85595beb7ba58____
0x180024ee7  mov     eax, ebx
0x180024ee9  mov     rcx, [rbp+0E0h+var_20]
0x180024ef0  xor     rcx, rsp; StackCookie
0x180024ef3  call    __security_check_cookie
0x180024ef8  mov     rbx, [rsp+1E0h+arg_10]
0x180024f00  add     rsp, 1D0h
0x180024f07  pop     r14
0x180024f09  pop     rdi
0x180024f0a  pop     rbp
0x180024f0b  retn
```
