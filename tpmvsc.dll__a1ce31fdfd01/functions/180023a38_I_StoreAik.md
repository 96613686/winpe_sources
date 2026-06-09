# I_StoreAik

- ea: `0x180023a38`
- end: `0x180023e4c`
- name: `I_StoreAik`
- size: `1044`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callers

- `0x18001f288`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x1800068dc`
- `0x180007988`
- `0x18000bc48`
- `0x18000c010`
- `0x18000c198`
- `0x18000fafc`
- `0x180010cdc`
- `0x18001130c`
- `0x18001ce64`
- `0x18001e324`
- `0x18001e8f0`
- `0x180020040`
- `0x180023a38`
- `0x180028250`
- `0x1800348a0`
- `0x180037010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180023ba4`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180023ba4`

## string_xrefs

- `0x180023c9b`: `Unable to update key map record`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_StoreAik(const struct VCARD_DATA **a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // esi
  PVOID v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rdx
  unsigned __int8 v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Guid; // [rsp+40h] [rbp-C0h] BYREF
  NCRYPT_HANDLE v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  const struct VCARD_DATA **v24; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v26; // [rsp+68h] [rbp-98h] BYREF
  __int16 v27; // [rsp+70h] [rbp-90h]
  NCRYPT_HANDLE *v28; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v29[3]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v30; // [rsp+98h] [rbp-68h]
  _QWORD v31[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v32[40]; // [rsp+C0h] [rbp-40h] BYREF
  int v33; // [rsp+110h] [rbp+10h]
  unsigned __int16 v34[48]; // [rsp+120h] [rbp+20h] BYREF
  char v35[16]; // [rsp+180h] [rbp+80h] BYREF

  v24 = a1;
  v31[3] = a3;
  v20 = -96;
  Guid = 0;
  v23 = 0;
  strcpy(v35, "I_StoreAik");
  v31[0] = v35;
  v31[1] = &v23;
  v31[2] = &Guid;
  lambda_bbd48effdc7a6f04e9100b21615b317b_::operator()(v31);
  v23 = 1;
  v25 = v31;
  memset_0(v34, 0, 0x54u);
  I_KeyMapGetRecord(*v24, 160, (struct KEY_MAP_RECORD *)v34);
  memset_0(v32, 0, sizeof(v32));
  v33 = 2;
  v22 = 0;
  v5 = 0;
  v6 = Guid;
  while ( v5 < 0xA )
  {
    Guid = I_GenerateGuid(v32);
    if ( Guid )
    {
      WppTraceIndent(v7, 2u);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 82;
        v11 = "Unable to generate key name";
        goto LABEL_12;
      }
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &v22,
      0);
    v28 = &v22;
    v26 = v32;
    v8 = a3[7];
    if ( !v8 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, NCRYPT_HANDLE **))(*(_QWORD *)v8 + 16LL))(
           v8,
           &v26,
           &v28);
    Guid = v6;
    if ( v6 != -2146893809 )
      break;
    ++v5;
  }
  if ( v6 )
  {
    WppTraceIndent(v4, 2u);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 83;
      v11 = "Unable to store asymmetric key within retry limit";
LABEL_12:
      WPP_SF_sDs(
        v9[2],
        v10,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v11);
    }
LABEL_13:
    v12 = Guid;
    goto LABEL_37;
  }
  v26 = (unsigned __int16 *)&v22;
  v27 = 258;
  Guid = I_KeyMapSetRecord(*v24, v20, (const struct KEY_MAP_RECORD *)v32);
  if ( Guid )
  {
    WppTraceIndent(v13, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)"Unable to update key map record");
    }
    v12 = Guid;
  }
  else
  {
    v29[0] = &v24;
    v29[1] = &v20;
    v29[2] = v34;
    v30 = 258;
    v15 = I_KeyMapSave(*v24);
    if ( v15 )
    {
      WppTraceIndent(v14, 2u);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          v15,
          (__int64)"Unable to store key maps");
      }
      Guid = v15;
      WppTraceIndent((__int64)v16, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)"Updating key maps failed");
      }
    }
    else
    {
      Guid = 0;
      HIBYTE(v27) = 0;
      HIBYTE(v30) = 0;
      I_DeleteKeyMaterial(*v24, (const struct KEY_MAP_RECORD *)v34);
    }
    v12 = Guid;
    wil::details::ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9___::operator()(v29);
  }
  wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()((__int64)&v26);
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v22);
  WppTraceUnwinder__lambda_bbd48effdc7a6f04e9100b21615b317b____::_WppTraceUnwinder__lambda_bbd48effdc7a6f04e9100b21615b317b____(&v25);
  v17 = (__int64 *)a3[7];
  if ( v17 )
  {
    v18 = *v17;
    LOBYTE(v18) = v17 != a3;
    (*(void (__fastcall **)(__int64 *, __int64))(*v17 + 32))(v17, v18);
    a3[7] = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x180023a38  mov     [rsp-8+arg_8], rbx
0x180023a3d  mov     [rsp-8+arg_18], rsi
0x180023a42  push    rbp
0x180023a43  push    rdi
0x180023a44  push    r15
0x180023a46  lea     rbp, [rsp-0A0h]
0x180023a4e  sub     rsp, 1A0h
0x180023a55  mov     rax, cs:__security_cookie
0x180023a5c  xor     rax, rsp
0x180023a5f  mov     [rbp+0B0h+var_20], rax
0x180023a66  mov     rbx, r8
0x180023a69  mov     [rsp+1B0h+var_158], rcx
0x180023a6e  mov     [rbp+0B0h+var_F8], rbx
0x180023a72  mov     [rsp+1B0h+var_180], 0A0h
0x180023a77  mov     [rsp+1B0h+var_170], 0
0x180023a7f  mov     [rsp+1B0h+var_160], 0
0x180023a87  movsd   xmm0, qword ptr cs:aIStoreaik; "I_StoreAik"
0x180023a8f  movsd   qword ptr [rbp+0B0h+var_30], xmm0
0x180023a97  mov     eax, dword ptr cs:aIStoreaik+7; "Aik"
0x180023a9d  mov     dword ptr [rbp+0B0h+var_30+7], eax
0x180023aa3  lea     rax, [rbp+0B0h+var_30]
0x180023aaa  mov     [rbp+0B0h+var_110], rax
0x180023aae  lea     rax, [rsp+1B0h+var_160]
0x180023ab3  mov     [rbp+0B0h+var_108], rax
0x180023ab7  lea     rax, [rsp+1B0h+var_170]
0x180023abc  mov     [rbp+0B0h+var_100], rax
0x180023ac0  lea     rcx, [rbp+0B0h+var_110]
0x180023ac4  call    _lambda_bbd48effdc7a6f04e9100b21615b317b___operator__
0x180023ac9  mov     [rsp+1B0h+var_160], 1
0x180023ad1  lea     rax, [rbp+0B0h+var_110]
0x180023ad5  mov     [rsp+1B0h+var_150], rax
0x180023ada  mov     dil, [rsp+1B0h+var_180]
0x180023adf  lea     eax, [rdi-80h]
0x180023ae2  cmp     al, 20h ; ' '
0x180023ae4  jbe     short loc_180023AF0
0x180023ae6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023aeb  mov     dil, [rsp+1B0h+var_180]
0x180023af0  mov     esi, 54h ; 'T'
0x180023af5  mov     r8d, esi; Size
0x180023af8  xor     edx, edx; Val
0x180023afa  lea     rcx, [rbp+0B0h+var_90]; void *
0x180023afe  call    memset_0
0x180023b03  lea     r8, [rbp+0B0h+var_90]; struct KEY_MAP_RECORD *
0x180023b07  mov     dl, dil; unsigned __int8
0x180023b0a  mov     rcx, [rsp+1B0h+var_158]
0x180023b0f  mov     rcx, [rcx]; struct VCARD_DATA *
0x180023b12  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x180023b17  xor     edx, edx; Val
0x180023b19  lea     r8d, [rsi-4]; Size
0x180023b1d  lea     rcx, [rbp+0B0h+var_F0]; void *
0x180023b21  call    memset_0
0x180023b26  lea     r15d, [rsi-52h]
0x180023b2a  mov     [rbp+0B0h+var_A0], r15d
0x180023b2e  mov     [rsp+1B0h+var_168], 0
0x180023b37  xor     edi, edi
0x180023b39  mov     eax, [rsp+1B0h+var_170]
0x180023b3d  cmp     edi, 0Ah
0x180023b40  jnb     loc_180023C0B
0x180023b46  lea     rcx, [rbp+0B0h+var_F0]; unsigned __int16 *
0x180023b4a  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x180023b4f  mov     [rsp+1B0h+var_170], eax
0x180023b53  test    eax, eax
0x180023b55  jnz     short loc_180023BAB
0x180023b57  xor     edx, edx
0x180023b59  lea     rcx, [rsp+1B0h+var_168]
0x180023b5e  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x180023b63  lea     rax, [rsp+1B0h+var_168]
0x180023b68  mov     [rsp+1B0h+var_138], rax
0x180023b6d  lea     rax, [rbp+0B0h+var_F0]
0x180023b71  mov     [rsp+1B0h+var_148], rax
0x180023b76  mov     rcx, [rbx+38h]
0x180023b7a  test    rcx, rcx
0x180023b7d  jz      short loc_180023BA4
0x180023b7f  mov     rax, [rcx]
0x180023b82  lea     r8, [rsp+1B0h+var_138]
0x180023b87  lea     rdx, [rsp+1B0h+var_148]
0x180023b8c  mov     rax, [rax+10h]
0x180023b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b95  mov     [rsp+1B0h+var_170], eax
0x180023b99  cmp     eax, 8009000Fh
0x180023b9e  jnz     short loc_180023C0B
0x180023ba0  inc     edi
0x180023ba2  jmp     short loc_180023B3D
0x180023ba4  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180023baa  int     3; Trap to Debugger
0x180023bab  mov     edx, r15d
0x180023bae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023bb3  lea     rdi, WPP_GLOBAL_Control
0x180023bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bc1  cmp     rcx, rdi
0x180023bc4  jz      short loc_180023C02
0x180023bc6  test    byte ptr [rcx+1Ch], 1
0x180023bca  jz      short loc_180023C02
0x180023bcc  cmp     [rcx+19h], r15b
0x180023bd0  jb      short loc_180023C02
0x180023bd2  mov     edx, 52h ; 'R'
0x180023bd7  lea     rax, aUnableToGenera_5; "Unable to generate key name"
0x180023bde  mov     [rsp+1B0h+var_188], rax
0x180023be3  mov     eax, [rsp+1B0h+var_170]
0x180023be7  mov     [rsp+1B0h+var_190], eax
0x180023beb  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023bf2  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023bf9  mov     rcx, [rcx+10h]
0x180023bfd  call    WPP_SF_sDs
0x180023c02  mov     edi, [rsp+1B0h+var_170]
0x180023c06  jmp     loc_180023DEA
0x180023c0b  test    eax, eax
0x180023c0d  jz      short loc_180023C44
0x180023c0f  mov     edx, r15d
0x180023c12  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023c17  lea     rdi, WPP_GLOBAL_Control
0x180023c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c25  cmp     rcx, rdi
0x180023c28  jz      short loc_180023C02
0x180023c2a  test    byte ptr [rcx+1Ch], 1
0x180023c2e  jz      short loc_180023C02
0x180023c30  cmp     [rcx+19h], r15b
0x180023c34  jb      short loc_180023C02
0x180023c36  mov     edx, 53h ; 'S'
0x180023c3b  lea     rax, aUnableToStoreA; "Unable to store asymmetric key within r"...
0x180023c42  jmp     short loc_180023BDE
0x180023c44  lea     rax, [rsp+1B0h+var_168]
0x180023c49  mov     [rsp+1B0h+var_148], rax
0x180023c4e  mov     [rsp+1B0h+var_140], 102h
0x180023c55  lea     r8, [rbp+0B0h+var_F0]; struct KEY_MAP_RECORD *
0x180023c59  mov     dl, [rsp+1B0h+var_180]; unsigned __int8
0x180023c5d  mov     rcx, [rsp+1B0h+var_158]
0x180023c62  mov     rcx, [rcx]; struct VCARD_DATA *
0x180023c65  call    ?I_KeyMapSetRecord@@YAKPEBUVCARD_DATA@@EPEBUKEY_MAP_RECORD@@@Z; I_KeyMapSetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD const *)
0x180023c6a  mov     [rsp+1B0h+var_170], eax
0x180023c6e  test    eax, eax
0x180023c70  jz      short loc_180023CCF
0x180023c72  mov     edx, r15d
0x180023c75  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023c7a  lea     rdi, WPP_GLOBAL_Control
0x180023c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c88  cmp     rcx, rdi
0x180023c8b  jz      short loc_180023CC6
0x180023c8d  test    byte ptr [rcx+1Ch], 1
0x180023c91  jz      short loc_180023CC6
0x180023c93  cmp     [rcx+19h], r15b
0x180023c97  jb      short loc_180023CC6
0x180023c99  mov     edx, esi
0x180023c9b  lea     rax, aUnableToUpdate_3; "Unable to update key map record"
0x180023ca2  mov     [rsp+1B0h+var_188], rax
0x180023ca7  mov     eax, [rsp+1B0h+var_170]
0x180023cab  mov     [rsp+1B0h+var_190], eax
0x180023caf  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023cb6  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023cbd  mov     rcx, [rcx+10h]
0x180023cc1  call    WPP_SF_sDs
0x180023cc6  mov     edi, [rsp+1B0h+var_170]
0x180023cca  jmp     loc_180023DDF
0x180023ccf  lea     rax, [rsp+1B0h+var_158]
0x180023cd4  mov     [rbp+0B0h+var_130], rax
0x180023cd8  lea     rax, [rsp+1B0h+var_180]
0x180023cdd  mov     [rbp+0B0h+var_128], rax
0x180023ce1  lea     rax, [rbp+0B0h+var_90]
0x180023ce5  mov     [rbp+0B0h+var_120], rax
0x180023ce9  mov     [rbp+0B0h+var_118], 102h
0x180023cef  mov     rcx, [rsp+1B0h+var_158]
0x180023cf4  mov     rcx, [rcx]; struct VCARD_DATA *
0x180023cf7  call    ?I_KeyMapSave@@YAKPEBUVCARD_DATA@@@Z; I_KeyMapSave(VCARD_DATA const *)
0x180023cfc  mov     esi, eax
0x180023cfe  test    eax, eax
0x180023d00  jz      loc_180023DAF
0x180023d06  mov     edx, r15d
0x180023d09  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023d0e  lea     rdi, WPP_GLOBAL_Control
0x180023d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d1c  cmp     rcx, rdi
0x180023d1f  jz      short loc_180023D59
0x180023d21  test    byte ptr [rcx+1Ch], 1
0x180023d25  jz      short loc_180023D59
0x180023d27  cmp     [rcx+19h], r15b
0x180023d2b  jb      short loc_180023D59
0x180023d2d  mov     edx, 55h ; 'U'
0x180023d32  lea     rax, aUnableToStoreK; "Unable to store key maps"
0x180023d39  mov     [rsp+1B0h+var_188], rax
0x180023d3e  mov     [rsp+1B0h+var_190], esi
0x180023d42  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023d49  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023d50  mov     rcx, [rcx+10h]
0x180023d54  call    WPP_SF_sDs
0x180023d59  mov     [rsp+1B0h+var_170], esi
0x180023d5d  mov     edx, r15d
0x180023d60  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d6c  cmp     rcx, rdi
0x180023d6f  jz      short loc_180023DD1
0x180023d71  test    byte ptr [rcx+1Ch], 1
0x180023d75  jz      short loc_180023DD1
0x180023d77  cmp     [rcx+19h], r15b
0x180023d7b  jb      short loc_180023DD1
0x180023d7d  mov     edx, 56h ; 'V'
0x180023d82  lea     rax, aUpdatingKeyMap; "Updating key maps failed"
0x180023d89  mov     [rsp+1B0h+var_188], rax
0x180023d8e  mov     eax, [rsp+1B0h+var_170]
0x180023d92  mov     [rsp+1B0h+var_190], eax
0x180023d96  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023d9d  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180023da4  mov     rcx, [rcx+10h]
0x180023da8  call    WPP_SF_sDs
0x180023dad  jmp     short loc_180023DD1
0x180023daf  mov     [rsp+1B0h+var_170], 0
0x180023db7  mov     byte ptr [rsp+1B0h+var_140+1], 0
0x180023dbc  mov     byte ptr [rbp+0B0h+var_118+1], 0
0x180023dc0  lea     rdx, [rbp+0B0h+var_90]; unsigned __int16 *
0x180023dc4  mov     rcx, [rsp+1B0h+var_158]
0x180023dc9  mov     rcx, [rcx]; struct VCARD_DATA *
0x180023dcc  call    I_DeleteKeyMaterial
0x180023dd1  mov     edi, [rsp+1B0h+var_170]
0x180023dd5  lea     rcx, [rbp+0B0h+var_130]
0x180023dd9  call    wil__details__ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9_____operator__
0x180023dde  nop
0x180023ddf  lea     rcx, [rsp+1B0h+var_148]
0x180023de4  call    wil__details__ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f_____operator__
0x180023de9  nop
0x180023dea  lea     rcx, [rsp+1B0h+var_168]
0x180023def  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180023df4  nop
0x180023df5  lea     rcx, [rsp+1B0h+var_150]
0x180023dfa  call    WppTraceUnwinder__lambda_bbd48effdc7a6f04e9100b21615b317b_______WppTraceUnwinder__lambda_bbd48effdc7a6f04e9100b21615b317b____
0x180023dff  nop
0x180023e00  mov     rcx, [rbx+38h]
0x180023e04  test    rcx, rcx
0x180023e07  jz      short loc_180023E23
0x180023e09  mov     rdx, [rcx]
0x180023e0c  mov     rax, [rdx+20h]
0x180023e10  cmp     rcx, rbx
0x180023e13  setnz   dl
0x180023e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1b  mov     qword ptr [rbx+38h], 0
0x180023e23  mov     eax, edi
0x180023e25  mov     rcx, [rbp+0B0h+var_20]
0x180023e2c  xor     rcx, rsp; StackCookie
0x180023e2f  call    __security_check_cookie
0x180023e34  lea     r11, [rsp+1B0h+var_10]
0x180023e3c  mov     rbx, [r11+28h]
0x180023e40  mov     rsi, [r11+38h]
0x180023e44  mov     rsp, r11
0x180023e47  pop     r15
0x180023e49  pop     rdi
0x180023e4a  pop     rbp
0x180023e4b  retn
```
