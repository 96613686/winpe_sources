# I_DeleteKeyLocking(VCHANNEL_DATA *,uchar)

- ea: `0x18001fd8c`
- end: `0x180020038`
- name: `?I_DeleteKeyLocking@@YAKPEAUVCHANNEL_DATA@@E@Z`
- size: `684`
- prototype: `__int64 __fastcall(const struct VCARD_DATA **, unsigned __int8)`
- caller_count: `4`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016880`
- `0x1800168d4`
- `0x180017448`
- `0x18002d9d8`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000a110`
- `0x18000bc48`
- `0x18000c198`
- `0x18000fafc`
- `0x18001130c`
- `0x18001cc6c`
- `0x18001d484`
- `0x18001dd60`
- `0x18001e8f0`
- `0x18001fd8c`
- `0x180020040`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020001`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020001`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe6f`

## string_xrefs

- `0x18001fefe`: `Unable to update key map record`
- `0x18001fdd0`: `I_DeleteKeyLocking`

## pseudocode

```c
__int64 __fastcall I_DeleteKeyLocking(const struct VCARD_DATA **a1, unsigned __int8 a2)
{
  __int64 v2; // rdx
  const struct VCARD_DATA **v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // rcx
  unsigned __int8 v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  const struct VCARD_DATA **v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v15; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v17; // [rsp+70h] [rbp-90h]
  _QWORD v18[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v19[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[80]; // [rsp+B0h] [rbp-50h] BYREF
  int v21; // [rsp+100h] [rbp+0h]
  unsigned __int16 v22[48]; // [rsp+110h] [rbp+10h] BYREF
  char v23[24]; // [rsp+170h] [rbp+70h] BYREF

  v13 = a1;
  v11 = a2;
  v12 = 0;
  v14 = 0;
  strcpy(v23, "I_DeleteKeyLocking");
  v18[0] = v23;
  v18[1] = &v14;
  v18[2] = &v12;
  lambda_1ecc10695be0df36c3eedd1aa55ed33c_::operator()(v18);
  v14 = 1;
  v15 = v18;
  v3 = v13;
  if ( !v13 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v2);
    v3 = v13;
  }
  if ( !(unsigned int)I_IsRoleAuthenticated(v3, 1) && !(unsigned int)I_IsRoleAuthenticated(v13, 3) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( (unsigned __int8)(v11 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  v6 = (RTL_SRWLOCK *)((char *)*v13 + 56);
  AcquireSRWLockExclusive(v6);
  v19[2] = v6;
  memset_0(v22, 0, 0x54u);
  I_KeyMapGetRecord(*v13, v11, (struct KEY_MAP_RECORD *)v22);
  v21 = 0;
  memset_0(v20, 0, sizeof(v20));
  v12 = I_KeyMapSetRecord(*v13, v11, (const struct KEY_MAP_RECORD *)v20);
  if ( v12 )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v12,
        (__int64)"Unable to update key map record");
    }
    v8 = v12;
  }
  else
  {
    v16[0] = &v13;
    v16[1] = &v11;
    v16[2] = v22;
    v17 = 258;
    v19[0] = &v13;
    v19[1] = &v11;
    v12 = lambda_8862ce89fb1ae999646dc6521a164977_::operator()(v19);
    if ( v12 )
    {
      WppTraceIndent(v9, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
          (_DWORD)WPP_pszIndent,
          v12,
          (__int64)"Updating key maps failed");
      }
    }
    else
    {
      HIBYTE(v17) = 0;
      I_DeleteKeyMaterial(*v13, v22);
    }
    v8 = v12;
    wil::details::ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9___::operator()(v16);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  WppTraceUnwinder__lambda_1ecc10695be0df36c3eedd1aa55ed33c____::_WppTraceUnwinder__lambda_1ecc10695be0df36c3eedd1aa55ed33c____(&v15);
  return v8;
}

```

## disassembly

```asm
0x18001fd8c  mov     [rsp-8+arg_10], rbx
0x18001fd91  mov     [rsp-8+arg_18], rdi
0x18001fd96  push    rbp
0x18001fd97  lea     rbp, [rsp-90h]
0x18001fd9f  sub     rsp, 190h
0x18001fda6  mov     rax, cs:__security_cookie
0x18001fdad  xor     rax, rsp
0x18001fdb0  mov     [rbp+90h+var_8], rax
0x18001fdb7  mov     [rsp+190h+var_150], rcx
0x18001fdbc  mov     [rsp+190h+var_160], dl
0x18001fdc0  mov     [rsp+190h+var_158], 0
0x18001fdc8  mov     [rsp+190h+var_148], 0
0x18001fdd0  movups  xmm0, xmmword ptr cs:aIDeletekeylock; "I_DeleteKeyLocking"
0x18001fdd7  movups  xmmword ptr [rbp+90h+var_20], xmm0
0x18001fddb  mov     eax, dword ptr cs:aIDeletekeylock+0Fh; "ing"
0x18001fde1  mov     dword ptr [rbp+90h+var_20+0Fh], eax
0x18001fde4  lea     rax, [rbp+90h+var_20]
0x18001fde8  mov     [rsp+190h+var_118], rax
0x18001fded  lea     rax, [rsp+190h+var_148]
0x18001fdf2  mov     [rbp+90h+var_110], rax
0x18001fdf6  lea     rax, [rsp+190h+var_158]
0x18001fdfb  mov     [rbp+90h+var_108], rax
0x18001fdff  lea     rcx, [rsp+190h+var_118]
0x18001fe04  call    _lambda_1ecc10695be0df36c3eedd1aa55ed33c___operator__
0x18001fe09  mov     edi, 1
0x18001fe0e  mov     [rsp+190h+var_148], edi
0x18001fe12  lea     rax, [rsp+190h+var_118]
0x18001fe17  mov     [rsp+190h+var_140], rax
0x18001fe1c  mov     rcx, [rsp+190h+var_150]
0x18001fe21  test    rcx, rcx
0x18001fe24  jnz     short loc_18001FE30
0x18001fe26  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fe2b  mov     rcx, [rsp+190h+var_150]
0x18001fe30  mov     edx, edi
0x18001fe32  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x18001fe37  test    eax, eax
0x18001fe39  jnz     short loc_18001FE51
0x18001fe3b  lea     edx, [rax+3]
0x18001fe3e  mov     rcx, [rsp+190h+var_150]
0x18001fe43  call    ?I_IsRoleAuthenticated@@YAHPEBUVCHANNEL_DATA@@W4_CARD_ROLE@@@Z; I_IsRoleAuthenticated(VCHANNEL_DATA const *,_CARD_ROLE)
0x18001fe48  test    eax, eax
0x18001fe4a  jnz     short loc_18001FE51
0x18001fe4c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fe51  mov     al, [rsp+190h+var_160]
0x18001fe55  sub     al, 80h
0x18001fe57  cmp     al, 20h ; ' '
0x18001fe59  jbe     short loc_18001FE60
0x18001fe5b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fe60  mov     rax, [rsp+190h+var_150]
0x18001fe65  mov     rbx, [rax]
0x18001fe68  add     rbx, 38h ; '8'
0x18001fe6c  mov     rcx, rbx; SRWLock
0x18001fe6f  call    cs:__imp_AcquireSRWLockExclusive
0x18001fe75  mov     [rbp+90h+var_F0], rbx
0x18001fe79  xor     edx, edx; Val
0x18001fe7b  lea     r8d, [rdx+54h]; Size
0x18001fe7f  lea     rcx, [rbp+90h+var_80]; void *
0x18001fe83  call    memset_0
0x18001fe88  lea     r8, [rbp+90h+var_80]; struct KEY_MAP_RECORD *
0x18001fe8c  mov     dl, [rsp+190h+var_160]; unsigned __int8
0x18001fe90  mov     rcx, [rsp+190h+var_150]
0x18001fe95  mov     rcx, [rcx]; struct VCARD_DATA *
0x18001fe98  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x18001fe9d  mov     [rbp+90h+var_90], 0
0x18001fea4  xor     edx, edx; Val
0x18001fea6  lea     r8d, [rdx+50h]; Size
0x18001feaa  lea     rcx, [rbp+90h+var_E0]; void *
0x18001feae  call    memset_0
0x18001feb3  lea     r8, [rbp+90h+var_E0]; struct KEY_MAP_RECORD *
0x18001feb7  mov     dl, [rsp+190h+var_160]; unsigned __int8
0x18001febb  mov     rcx, [rsp+190h+var_150]
0x18001fec0  mov     rcx, [rcx]; struct VCARD_DATA *
0x18001fec3  call    ?I_KeyMapSetRecord@@YAKPEBUVCARD_DATA@@EPEBUKEY_MAP_RECORD@@@Z; I_KeyMapSetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD const *)
0x18001fec8  mov     [rsp+190h+var_158], eax
0x18001fecc  test    eax, eax
0x18001fece  jz      short loc_18001FF32
0x18001fed0  mov     edx, 2
0x18001fed5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001feda  lea     rax, WPP_GLOBAL_Control
0x18001fee1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fee8  cmp     rcx, rax
0x18001feeb  jz      short loc_18001FF29
0x18001feed  test    [rcx+1Ch], dil
0x18001fef1  jz      short loc_18001FF29
0x18001fef3  cmp     byte ptr [rcx+19h], 2
0x18001fef7  jb      short loc_18001FF29
0x18001fef9  mov     edx, 6Bh ; 'k'
0x18001fefe  lea     rax, aUnableToUpdate_3; "Unable to update key map record"
0x18001ff05  mov     [rsp+190h+var_168], rax
0x18001ff0a  mov     eax, [rsp+190h+var_158]
0x18001ff0e  mov     [rsp+190h+var_170], eax
0x18001ff12  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ff19  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001ff20  mov     rcx, [rcx+10h]
0x18001ff24  call    WPP_SF_sDs
0x18001ff29  mov     edi, [rsp+190h+var_158]
0x18001ff2d  jmp     loc_18001FFF9
0x18001ff32  lea     rax, [rsp+190h+var_150]
0x18001ff37  mov     [rsp+190h+var_138], rax
0x18001ff3c  lea     rax, [rsp+190h+var_160]
0x18001ff41  mov     [rsp+190h+var_130], rax
0x18001ff46  lea     rax, [rbp+90h+var_80]
0x18001ff4a  mov     [rsp+190h+var_128], rax
0x18001ff4f  mov     [rsp+190h+var_120], 102h
0x18001ff56  lea     rax, [rsp+190h+var_150]
0x18001ff5b  mov     [rbp+90h+var_100], rax
0x18001ff5f  lea     rax, [rsp+190h+var_160]
0x18001ff64  mov     [rbp+90h+var_F8], rax
0x18001ff68  lea     rcx, [rbp+90h+var_100]
0x18001ff6c  call    _lambda_8862ce89fb1ae999646dc6521a164977___operator__
0x18001ff71  mov     [rsp+190h+var_158], eax
0x18001ff75  test    eax, eax
0x18001ff77  jz      short loc_18001FFD4
0x18001ff79  mov     edx, 2
0x18001ff7e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ff83  lea     rax, WPP_GLOBAL_Control
0x18001ff8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff91  cmp     rcx, rax
0x18001ff94  jz      short loc_18001FFEA
0x18001ff96  test    [rcx+1Ch], dil
0x18001ff9a  jz      short loc_18001FFEA
0x18001ff9c  cmp     byte ptr [rcx+19h], 2
0x18001ffa0  jb      short loc_18001FFEA
0x18001ffa2  mov     edx, 6Eh ; 'n'
0x18001ffa7  lea     rax, aUpdatingKeyMap; "Updating key maps failed"
0x18001ffae  mov     [rsp+190h+var_168], rax
0x18001ffb3  mov     eax, [rsp+190h+var_158]
0x18001ffb7  mov     [rsp+190h+var_170], eax
0x18001ffbb  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ffc2  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001ffc9  mov     rcx, [rcx+10h]
0x18001ffcd  call    WPP_SF_sDs
0x18001ffd2  jmp     short loc_18001FFEA
0x18001ffd4  mov     byte ptr [rsp+190h+var_120+1], 0
0x18001ffd9  lea     rdx, [rbp+90h+var_80]; unsigned __int16 *
0x18001ffdd  mov     rcx, [rsp+190h+var_150]
0x18001ffe2  mov     rcx, [rcx]; struct VCARD_DATA *
0x18001ffe5  call    I_DeleteKeyMaterial
0x18001ffea  mov     edi, [rsp+190h+var_158]
0x18001ffee  lea     rcx, [rsp+190h+var_138]
0x18001fff3  call    wil__details__ScopeExitFnGuard__lambda_ca4cb570e2f7d20a87829b93eb832cd9_____operator__
0x18001fff8  nop
0x18001fff9  test    rbx, rbx
0x18001fffc  jz      short loc_180020008
0x18001fffe  mov     rcx, rbx; SRWLock
0x180020001  call    cs:__imp_ReleaseSRWLockExclusive
0x180020007  nop
0x180020008  lea     rcx, [rsp+190h+var_140]
0x18002000d  call    WppTraceUnwinder__lambda_1ecc10695be0df36c3eedd1aa55ed33c_______WppTraceUnwinder__lambda_1ecc10695be0df36c3eedd1aa55ed33c____
0x180020012  mov     eax, edi
0x180020014  mov     rcx, [rbp+90h+var_8]
0x18002001b  xor     rcx, rsp; StackCookie
0x18002001e  call    __security_check_cookie
0x180020023  lea     r11, [rsp+190h+var_s0]
0x18002002b  mov     rbx, [r11+20h]
0x18002002f  mov     rdi, [r11+28h]
0x180020033  mov     rsp, r11
0x180020036  pop     rbp
0x180020037  retn
```
