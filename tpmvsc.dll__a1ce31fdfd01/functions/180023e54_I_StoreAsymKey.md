# I_StoreAsymKey

- ea: `0x180023e54`
- end: `0x180024371`
- name: `I_StoreAsymKey`
- size: `1309`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f558`
- `0x180021f84`

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
- `0x18001cbc4`
- `0x18001d0ec`
- `0x18001de40`
- `0x18001e8f0`
- `0x180020040`
- `0x180023e54`
- `0x180028250`
- `0x18002bb98`
- `0x1800348a0`
- `0x180037010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002411d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002411d`

## string_xrefs

- `0x180024211`: `Unable to update key map record`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall I_StoreAsymKey(const struct VCARD_DATA **a1, unsigned __int8 a2, __int64 *a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // bl
  unsigned int v9; // esi
  __int64 *v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  unsigned int v16; // esi
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  int v21; // edx
  const char *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 *v25; // rcx
  __int64 v26; // rdx
  unsigned __int8 v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Guid; // [rsp+38h] [rbp-C8h] BYREF
  const struct VCARD_DATA **v29; // [rsp+40h] [rbp-C0h] BYREF
  NCRYPT_HANDLE v30; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v36[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v37[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v39; // [rsp+B8h] [rbp-48h]
  _QWORD v40[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v41[40]; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+130h] [rbp+30h]
  unsigned __int16 v43[48]; // [rsp+140h] [rbp+40h] BYREF
  char v44[16]; // [rsp+1A0h] [rbp+A0h] BYREF

  v29 = a1;
  v27 = a2;
  v40[3] = a3;
  Guid = 0;
  v32 = 0;
  strcpy(v44, "I_StoreAsymKey");
  v40[0] = v44;
  v40[1] = &v32;
  v40[2] = &Guid;
  lambda_0a4ca27310ab60b36dc9abd96c3b7412_::operator()(v40);
  v32 = 1;
  v31 = v40;
  v5 = (__int64)v29;
  if ( !v29 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v4);
    v5 = (__int64)v29;
  }
  if ( !(unsigned int)I_IsRoleAuthenticated(v5, 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  v8 = v27;
  if ( (unsigned __int8)(v27 + 0x80) > 0x20u )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
    v8 = v27;
  }
  if ( v8 == -96 )
  {
    WppTraceIndent(v7, 2u);
    v9 = 5;
    Guid = 5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        5,
        (__int64)"The AIK can not be modified");
      v9 = Guid;
    }
    WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____::_WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____(&v31);
    v10 = (__int64 *)a3[7];
    if ( v10 )
    {
      v11 = *v10;
      LOBYTE(v11) = v10 != a3;
      (*(void (__fastcall **)(__int64 *, __int64))(*v10 + 32))(v10, v11);
      a3[7] = 0;
    }
    return v9;
  }
  else
  {
    memset_0(v43, 0, 0x54u);
    I_KeyMapGetRecord(*v29, v8, (struct KEY_MAP_RECORD *)v43);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v36);
    Guid = I_UnprotectMemory(v29 + 16, v36);
    if ( Guid )
    {
      WppTraceIndent(v13, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)"Unable to recover auth key");
      }
      v14 = Guid;
    }
    else
    {
      memset_0(v41, 0, sizeof(v41));
      v42 = 2;
      v30 = 0;
      v16 = 0;
      v17 = 0;
      while ( v16 < 0xA )
      {
        Guid = I_GenerateGuid(v41);
        if ( Guid )
        {
          WppTraceIndent(v18, 2u);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v21 = 75;
            v22 = "Unable to generate key name";
            goto LABEL_32;
          }
          goto LABEL_33;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &v30,
          0);
        v37[0] = &v30;
        v35 = 0;
        v33 = v41;
        v19 = a3[7];
        if ( !v19 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, _QWORD *, _QWORD *, int *))(*(_QWORD *)v19 + 16LL))(
                v19,
                &v33,
                v37,
                v36,
                &v35);
        Guid = v17;
        if ( v17 != -2146893809 )
          break;
        ++v16;
      }
      if ( v17 )
      {
        WppTraceIndent(v15, 2u);
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 76;
          v22 = "Unable to store asymmetric key within retry limit";
LABEL_32:
          WPP_SF_sDs(
            v20[2],
            v21,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            (_DWORD)WPP_pszIndent,
            Guid,
            (__int64)v22);
        }
LABEL_33:
        v14 = Guid;
        goto LABEL_53;
      }
      v33 = (unsigned __int16 *)&v30;
      v34 = 258;
      Guid = I_KeyMapSetRecord(*v29, v27, (const struct KEY_MAP_RECORD *)v41);
      if ( Guid )
      {
        WppTraceIndent(v23, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            (_DWORD)WPP_pszIndent,
            Guid,
            (__int64)"Unable to update key map record");
        }
        v14 = Guid;
      }
      else
      {
        v38[0] = &v29;
        v38[1] = &v27;
        v38[2] = v43;
        v39 = 258;
        v37[0] = &v29;
        v37[1] = &v27;
        Guid = lambda_8c3f3f9318d47bbee88f8487c2dace11_::operator()(v37);
        if ( Guid )
        {
          WppTraceIndent(v24, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sDs(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              80,
              (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
              (_DWORD)WPP_pszIndent,
              Guid,
              (__int64)"Updating key maps failed");
          }
        }
        else
        {
          HIBYTE(v34) = 0;
          HIBYTE(v39) = 0;
          I_DeleteKeyMaterial(*v29, (const struct KEY_MAP_RECORD *)v43);
        }
        v14 = Guid;
        wil::details::ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9___::operator()(v38);
      }
      wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()((__int64)&v33);
LABEL_53:
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v30);
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v36);
    WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____::_WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____(&v31);
    v25 = (__int64 *)a3[7];
    if ( v25 )
    {
      v26 = *v25;
      LOBYTE(v26) = v25 != a3;
      (*(void (__fastcall **)(__int64 *, __int64))(*v25 + 32))(v25, v26);
      a3[7] = 0;
    }
    return v14;
  }
}

```

## disassembly

```asm
0x180023e54  push    rbp
0x180023e56  push    rbx
0x180023e57  push    rsi
0x180023e58  push    rdi
0x180023e59  push    r14
0x180023e5b  lea     rbp, [rsp-0C0h]
0x180023e63  sub     rsp, 1C0h
0x180023e6a  mov     rax, cs:__security_cookie
0x180023e71  xor     rax, rsp
0x180023e74  mov     [rbp+0E0h+var_30], rax
0x180023e7b  mov     rdi, r8
0x180023e7e  mov     [rsp+1E0h+var_1A0], rcx
0x180023e83  mov     [rsp+1E0h+var_1B0], dl
0x180023e87  mov     [rbp+0E0h+var_108], r8
0x180023e8b  xor     r14d, r14d
0x180023e8e  mov     [rsp+1E0h+var_1A8], r14d
0x180023e93  mov     [rsp+1E0h+var_188], r14d
0x180023e98  movsd   xmm0, qword ptr cs:aIStoreasymkey; "I_StoreAsymKey"
0x180023ea0  movsd   qword ptr [rbp+0E0h+var_40], xmm0
0x180023ea8  mov     eax, dword ptr cs:aIStoreasymkey+8; "symKey"
0x180023eae  mov     dword ptr [rbp+0E0h+var_40+8], eax
0x180023eb4  movzx   eax, word ptr cs:aIStoreasymkey+0Ch; "ey"
0x180023ebb  mov     word ptr [rbp+0E0h+var_40+0Ch], ax
0x180023ec2  mov     al, byte ptr cs:aIStoreasymkey+0Eh; ""
0x180023ec8  mov     [rbp+0E0h+var_40+0Eh], al
0x180023ece  lea     rax, [rbp+0E0h+var_40]
0x180023ed5  mov     [rbp+0E0h+var_120], rax
0x180023ed9  lea     rax, [rsp+1E0h+var_188]
0x180023ede  mov     [rbp+0E0h+var_118], rax
0x180023ee2  lea     rax, [rsp+1E0h+var_1A8]
0x180023ee7  mov     [rbp+0E0h+var_110], rax
0x180023eeb  lea     rcx, [rbp+0E0h+var_120]
0x180023eef  call    _lambda_0a4ca27310ab60b36dc9abd96c3b7412___operator__
0x180023ef4  mov     [rsp+1E0h+var_188], 1
0x180023efc  lea     rax, [rbp+0E0h+var_120]
0x180023f00  mov     [rsp+1E0h+var_190], rax
0x180023f05  mov     rcx, [rsp+1E0h+var_1A0]
0x180023f0a  test    rcx, rcx
0x180023f0d  jnz     short loc_180023F19
0x180023f0f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023f14  mov     rcx, [rsp+1E0h+var_1A0]
0x180023f19  mov     edx, 1
0x180023f1e  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x180023f23  test    eax, eax
0x180023f25  jnz     short loc_180023F2C
0x180023f27  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023f2c  mov     bl, [rsp+1E0h+var_1B0]
0x180023f30  lea     eax, [rbx-80h]
0x180023f33  cmp     al, 20h ; ' '
0x180023f35  jbe     short loc_180023F40
0x180023f37  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023f3c  mov     bl, [rsp+1E0h+var_1B0]
0x180023f40  cmp     bl, 0A0h
0x180023f43  jnz     loc_180023FD9
0x180023f49  mov     ebx, 2
0x180023f4e  mov     edx, ebx
0x180023f50  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023f55  lea     esi, [rbx+3]
0x180023f58  mov     [rsp+1E0h+var_1A8], esi
0x180023f5c  lea     rax, WPP_GLOBAL_Control
0x180023f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f6a  cmp     rcx, rax
0x180023f6d  jz      short loc_180023FA8
0x180023f6f  test    byte ptr [rcx+1Ch], 1
0x180023f73  jz      short loc_180023FA8
0x180023f75  cmp     [rcx+19h], bl
0x180023f78  jb      short loc_180023FA8
0x180023f7a  lea     edx, [rbx+47h]
0x180023f7d  lea     rax, aTheAikCanNotBe; "The AIK can not be modified"
0x180023f84  mov     [rsp+1E0h+var_1B8], rax
0x180023f89  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x180023f8d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023f94  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023f9b  mov     rcx, [rcx+10h]
0x180023f9f  call    WPP_SF_sDs
0x180023fa4  mov     esi, [rsp+1E0h+var_1A8]
0x180023fa8  lea     rcx, [rsp+1E0h+var_190]
0x180023fad  call    WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412_______WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____
0x180023fb2  nop
0x180023fb3  mov     rcx, [rdi+38h]
0x180023fb7  test    rcx, rcx
0x180023fba  jz      short loc_180023FD2
0x180023fbc  mov     rdx, [rcx]
0x180023fbf  mov     rax, [rdx+20h]
0x180023fc3  cmp     rcx, rdi
0x180023fc6  setnz   dl
0x180023fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fce  mov     [rdi+38h], r14
0x180023fd2  mov     eax, esi
0x180023fd4  jmp     loc_180024354
0x180023fd9  xor     edx, edx; Val
0x180023fdb  lea     r8d, [rdx+54h]; Size
0x180023fdf  lea     rcx, [rbp+0E0h+var_A0]; void *
0x180023fe3  call    memset_0
0x180023fe8  lea     r8, [rbp+0E0h+var_A0]; struct KEY_MAP_RECORD *
0x180023fec  mov     dl, bl; unsigned __int8
0x180023fee  mov     rcx, [rsp+1E0h+var_1A0]
0x180023ff3  mov     rcx, [rcx]; struct VCARD_DATA *
0x180023ff6  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x180023ffb  lea     rcx, [rsp+1E0h+var_168]
0x180024000  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180024005  nop
0x180024006  mov     rcx, [rsp+1E0h+var_1A0]
0x18002400b  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18002400f  lea     rdx, [rsp+1E0h+var_168]
0x180024014  call    ?I_UnprotectMemory@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_UnprotectMemory(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x180024019  mov     [rsp+1E0h+var_1A8], eax
0x18002401d  test    eax, eax
0x18002401f  jz      short loc_180024082
0x180024021  mov     ebx, 2
0x180024026  mov     edx, ebx
0x180024028  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002402d  lea     rax, WPP_GLOBAL_Control
0x180024034  mov     rcx, cs:WPP_GLOBAL_Control
0x18002403b  cmp     rcx, rax
0x18002403e  jz      short loc_180024079
0x180024040  test    byte ptr [rcx+1Ch], 1
0x180024044  jz      short loc_180024079
0x180024046  cmp     [rcx+19h], bl
0x180024049  jb      short loc_180024079
0x18002404b  lea     edx, [rbx+48h]
0x18002404e  lea     rax, aUnableToRecove; "Unable to recover auth key"
0x180024055  mov     [rsp+1E0h+var_1B8], rax
0x18002405a  mov     eax, [rsp+1E0h+var_1A8]
0x18002405e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180024062  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024069  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024070  mov     rcx, [rcx+10h]
0x180024074  call    WPP_SF_sDs
0x180024079  mov     ebx, [rsp+1E0h+var_1A8]
0x18002407d  jmp     loc_18002431D
0x180024082  xor     edx, edx; Val
0x180024084  lea     r8d, [rdx+50h]; Size
0x180024088  lea     rcx, [rbp+0E0h+var_100]; void *
0x18002408c  call    memset_0
0x180024091  mov     ebx, 2
0x180024096  mov     [rbp+0E0h+var_B0], ebx
0x180024099  mov     [rsp+1E0h+var_198], r14
0x18002409e  mov     esi, r14d
0x1800240a1  mov     eax, r14d
0x1800240a4  cmp     esi, 0Ah
0x1800240a7  jnb     loc_180024182
0x1800240ad  lea     rcx, [rbp+0E0h+var_100]; unsigned __int16 *
0x1800240b1  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x1800240b6  mov     [rsp+1E0h+var_1A8], eax
0x1800240ba  test    eax, eax
0x1800240bc  jnz     short loc_180024124
0x1800240be  xor     edx, edx
0x1800240c0  lea     rcx, [rsp+1E0h+var_198]
0x1800240c5  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800240ca  lea     rax, [rsp+1E0h+var_198]
0x1800240cf  mov     [rbp+0E0h+var_150], rax
0x1800240d3  mov     [rsp+1E0h+var_170], r14d
0x1800240d8  lea     rax, [rbp+0E0h+var_100]
0x1800240dc  mov     [rsp+1E0h+var_180], rax
0x1800240e1  mov     rcx, [rdi+38h]
0x1800240e5  test    rcx, rcx
0x1800240e8  jz      short loc_18002411D
0x1800240ea  mov     rax, [rcx]
0x1800240ed  lea     rdx, [rsp+1E0h+var_170]
0x1800240f2  mov     [rsp+1E0h+var_1C0], rdx
0x1800240f7  lea     r9, [rsp+1E0h+var_168]
0x1800240fc  lea     r8, [rbp+0E0h+var_150]
0x180024100  lea     rdx, [rsp+1E0h+var_180]
0x180024105  mov     rax, [rax+10h]
0x180024109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002410e  mov     [rsp+1E0h+var_1A8], eax
0x180024112  cmp     eax, 8009000Fh
0x180024117  jnz     short loc_180024182
0x180024119  inc     esi
0x18002411b  jmp     short loc_1800240A4
0x18002411d  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180024123  int     3; Trap to Debugger
0x180024124  mov     edx, ebx
0x180024126  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002412b  lea     rax, WPP_GLOBAL_Control
0x180024132  mov     rcx, cs:WPP_GLOBAL_Control
0x180024139  cmp     rcx, rax
0x18002413c  jz      short loc_180024179
0x18002413e  test    byte ptr [rcx+1Ch], 1
0x180024142  jz      short loc_180024179
0x180024144  cmp     [rcx+19h], bl
0x180024147  jb      short loc_180024179
0x180024149  mov     edx, 4Bh ; 'K'
0x18002414e  lea     rax, aUnableToGenera_5; "Unable to generate key name"
0x180024155  mov     [rsp+1E0h+var_1B8], rax
0x18002415a  mov     eax, [rsp+1E0h+var_1A8]
0x18002415e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180024162  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024169  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024170  mov     rcx, [rcx+10h]
0x180024174  call    WPP_SF_sDs
0x180024179  mov     ebx, [rsp+1E0h+var_1A8]
0x18002417d  jmp     loc_180024312
0x180024182  test    eax, eax
0x180024184  jz      short loc_1800241B9
0x180024186  mov     edx, ebx
0x180024188  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002418d  lea     rax, WPP_GLOBAL_Control
0x180024194  mov     rcx, cs:WPP_GLOBAL_Control
0x18002419b  cmp     rcx, rax
0x18002419e  jz      short loc_180024179
0x1800241a0  test    byte ptr [rcx+1Ch], 1
0x1800241a4  jz      short loc_180024179
0x1800241a6  cmp     [rcx+19h], bl
0x1800241a9  jb      short loc_180024179
0x1800241ab  mov     edx, 4Ch ; 'L'
0x1800241b0  lea     rax, aUnableToStoreA; "Unable to store asymmetric key within r"...
0x1800241b7  jmp     short loc_180024155
0x1800241b9  lea     rax, [rsp+1E0h+var_198]
0x1800241be  mov     [rsp+1E0h+var_180], rax
0x1800241c3  mov     [rsp+1E0h+var_178], 102h
0x1800241ca  lea     r8, [rbp+0E0h+var_100]; struct KEY_MAP_RECORD *
0x1800241ce  mov     dl, [rsp+1E0h+var_1B0]; unsigned __int8
0x1800241d2  mov     rcx, [rsp+1E0h+var_1A0]
0x1800241d7  mov     rcx, [rcx]; struct VCARD_DATA *
0x1800241da  call    ?I_KeyMapSetRecord@@YAKPEBUVCARD_DATA@@EPEBUKEY_MAP_RECORD@@@Z; I_KeyMapSetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD const *)
0x1800241df  mov     [rsp+1E0h+var_1A8], eax
0x1800241e3  test    eax, eax
0x1800241e5  jz      short loc_180024245
0x1800241e7  mov     edx, ebx
0x1800241e9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800241ee  lea     rax, WPP_GLOBAL_Control
0x1800241f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241fc  cmp     rcx, rax
0x1800241ff  jz      short loc_18002423C
0x180024201  test    byte ptr [rcx+1Ch], 1
0x180024205  jz      short loc_18002423C
0x180024207  cmp     [rcx+19h], bl
0x18002420a  jb      short loc_18002423C
0x18002420c  mov     edx, 4Dh ; 'M'
0x180024211  lea     rax, aUnableToUpdate_3; "Unable to update key map record"
0x180024218  mov     [rsp+1E0h+var_1B8], rax
0x18002421d  mov     eax, [rsp+1E0h+var_1A8]
0x180024221  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180024225  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002422c  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180024233  mov     rcx, [rcx+10h]
0x180024237  call    WPP_SF_sDs
0x18002423c  mov     ebx, [rsp+1E0h+var_1A8]
0x180024240  jmp     loc_180024307
0x180024245  lea     rax, [rsp+1E0h+var_1A0]
0x18002424a  mov     [rbp+0E0h+var_140], rax
0x18002424e  lea     rax, [rsp+1E0h+var_1B0]
0x180024253  mov     [rbp+0E0h+var_138], rax
0x180024257  lea     rax, [rbp+0E0h+var_A0]
0x18002425b  mov     [rbp+0E0h+var_130], rax
0x18002425f  mov     [rbp+0E0h+var_128], 102h
0x180024265  lea     rax, [rsp+1E0h+var_1A0]
0x18002426a  mov     [rbp+0E0h+var_150], rax
0x18002426e  lea     rax, [rsp+1E0h+var_1B0]
0x180024273  mov     [rbp+0E0h+var_148], rax
0x180024277  lea     rcx, [rbp+0E0h+var_150]
0x18002427b  call    _lambda_8c3f3f9318d47bbee88f8487c2dace11___operator__
0x180024280  mov     [rsp+1E0h+var_1A8], eax
0x180024284  test    eax, eax
0x180024286  jz      short loc_1800242DF
0x180024288  mov     edx, ebx
0x18002428a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002428f  lea     rax, WPP_GLOBAL_Control
0x180024296  mov     rcx, cs:WPP_GLOBAL_Control
0x18002429d  cmp     rcx, rax
0x1800242a0  jz      short loc_1800242F9
0x1800242a2  test    byte ptr [rcx+1Ch], 1
0x1800242a6  jz      short loc_1800242F9
0x1800242a8  cmp     [rcx+19h], bl
0x1800242ab  jb      short loc_1800242F9
0x1800242ad  mov     edx, 50h ; 'P'
0x1800242b2  lea     rax, aUpdatingKeyMap; "Updating key maps failed"
0x1800242b9  mov     [rsp+1E0h+var_1B8], rax
0x1800242be  mov     eax, [rsp+1E0h+var_1A8]
0x1800242c2  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800242c6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800242cd  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800242d4  mov     rcx, [rcx+10h]
0x1800242d8  call    WPP_SF_sDs
0x1800242dd  jmp     short loc_1800242F9
0x1800242df  mov     byte ptr [rsp+1E0h+var_178+1], r14b
0x1800242e4  mov     byte ptr [rbp+0E0h+var_128+1], r14b
0x1800242e8  lea     rdx, [rbp+0E0h+var_A0]; unsigned __int16 *
0x1800242ec  mov     rcx, [rsp+1E0h+var_1A0]
0x1800242f1  mov     rcx, [rcx]; struct VCARD_DATA *
0x1800242f4  call    I_DeleteKeyMaterial
0x1800242f9  mov     ebx, [rsp+1E0h+var_1A8]
0x1800242fd  lea     rcx, [rbp+0E0h+var_140]
0x180024301  call    wil__details__ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9_____operator__
0x180024306  nop
0x180024307  lea     rcx, [rsp+1E0h+var_180]
0x18002430c  call    wil__details__ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f_____operator__
0x180024311  nop
0x180024312  lea     rcx, [rsp+1E0h+var_198]
0x180024317  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18002431c  nop
0x18002431d  lea     rcx, [rsp+1E0h+var_168]
0x180024322  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180024327  nop
0x180024328  lea     rcx, [rsp+1E0h+var_190]
0x18002432d  call    WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412_______WppTraceUnwinder__lambda_0a4ca27310ab60b36dc9abd96c3b7412____
0x180024332  nop
0x180024333  mov     rcx, [rdi+38h]
  ... truncated ...
```
