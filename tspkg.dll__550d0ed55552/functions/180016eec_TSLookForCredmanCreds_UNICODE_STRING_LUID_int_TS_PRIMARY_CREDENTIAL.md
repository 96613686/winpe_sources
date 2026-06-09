# TSLookForCredmanCreds(_UNICODE_STRING *,_LUID *,int,_TS_PRIMARY_CREDENTIAL * *)

- ea: `0x180016eec`
- end: `0x18001730b`
- name: `?TSLookForCredmanCreds@@YAJPEAU_UNICODE_STRING@@PEAU_LUID@@HPEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z`
- size: `1055`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _LUID *, int, struct _TS_PRIMARY_CREDENTIAL **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006650`

## callees

- `0x180005ed0`
- `0x18000a480`
- `0x18000b550`
- `0x18000c1a4`
- `0x1800162a4`
- `0x180016eec`
- `0x1800174a8`
- `0x180017580`
- `0x1800175f8`
- `0x18001d010`

## import_xrefs

- `SspiCli!SspiLocalFree` at `0x180017298`
- `SspiCli!SspiLocalFree` at `0x180017298`
- `SspiCli!SspiPrepareForCredRead` at `0x180016ff2`
- `SspiCli!SspiPrepareForCredRead` at `0x180016ff2`

## pseudocode

```c
__int64 __fastcall TSLookForCredmanCreds(
        struct _UNICODE_STRING *a1,
        struct _LUID *a2,
        int a3,
        struct _TS_PRIMARY_CREDENTIAL **a4)
{
  int v7; // eax
  WCHAR *v8; // r12
  int v9; // ebx
  SECURITY_STATUS v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  wchar_t *v15; // rax
  int v16; // edx
  int v17; // r8d
  PCWSTR pszTargetName; // [rsp+48h] [rbp-B8h] BYREF
  struct _ENCRYPTED_CREDENTIALW **v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+58h] [rbp-A8h]
  PCWSTR ppszCredmanTargetName; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v24[7]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+A8h] [rbp-58h]
  int v26; // [rsp+ACh] [rbp-54h]
  PCWSTR *p_pszTargetName; // [rsp+B0h] [rbp-50h]
  int AuthIdentity; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v29; // [rsp+C4h] [rbp-3Ch]
  int v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+DCh] [rbp-24h]
  __int16 v32; // [rsp+E0h] [rbp-20h]
  int v33; // [rsp+F0h] [rbp-10h]
  __int128 v34; // [rsp+F4h] [rbp-Ch]

  v21 = a3;
  memset_0(v24, 0, 0x48u);
  v23[0] = 2;
  v23[1] = 3;
  v20 = 0;
  ppszCredmanTargetName = 0;
  pszTargetName = 0;
  *a4 = 0;
  if ( !a1 || !a1->Length || !a2 )
    return 3221226021LL;
  v7 = TSUnicodeStringToString((unsigned __int16 **)&pszTargetName, a1);
  v8 = (WCHAR *)pszTargetName;
  v9 = v7;
  if ( v7 >= 0 )
  {
    LODWORD(pszTargetName) = 0;
    memset_0(&AuthIdentity, 0, 0x4Cu);
    AuthIdentity = 513;
    v29 = 48;
    v31 = 48;
    v30 = 76;
    v33 = 1835036;
    v32 = 28;
    v34 = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
    v10 = SspiPrepareForCredRead(&AuthIdentity, v8, (PULONG)&pszTargetName, &ppszCredmanTargetName);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v12 = 30;
      v13 = (unsigned int)v10;
      goto LABEL_35;
    }
    v24[0] = ppszCredmanTargetName;
    p_pszTargetName = &pszTargetName;
    v25 = 1;
    v26 = 1;
    v9 = ((__int64 (__fastcall *)(struct _LUID *, __int64, _QWORD *))TSGlobalLsaFunctions->DummyFunction2)(a2, 1, v24);
    if ( v9 < 0 )
    {
      if ( v9 != -1073741275 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_36;
        v12 = 32;
LABEL_34:
        v13 = (unsigned int)v9;
LABEL_35:
        WPP_SF_d(v11[2], v12, WPP_82746c11848034a638789f4e0723fe0c_Traceguids, v13);
        goto LABEL_36;
      }
      v24[0] = v8;
      v24[6] = L"TSSSP";
      p_pszTargetName = (PCWSTR *)v23;
      v26 = 2;
      v14 = ((__int64 (__fastcall *)(struct _LUID *, __int64, _QWORD *))TSGlobalLsaFunctions->DummyFunction2)(
              a2,
              1,
              v24);
      v9 = v14;
      if ( v14 != -1073741275 && v14 != -1073741729 && v14 != -1073741811 )
        goto LABEL_23;
      v15 = wcschr(v8, 0x2Fu);
      v24[0] = v15;
      if ( v15 )
      {
        v24[0] = v15 + 1;
        v9 = ((__int64 (__fastcall *)(struct _LUID *, __int64, _QWORD *))TSGlobalLsaFunctions->DummyFunction2)(
               a2,
               1,
               v24);
      }
      if ( v9 != -1073741275 && v9 != -1073741729 )
      {
LABEL_23:
        if ( v9 != -1073741811
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_82746c11848034a638789f4e0723fe0c_Traceguids,
            (unsigned int)v9);
        }
      }
      if ( v9 < 0 )
        goto LABEL_36;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_82746c11848034a638789f4e0723fe0c_Traceguids, 0);
    }
    v9 = TSSelectCredManCred(v20, 0, v21, a4);
    if ( (int)(v9 + 0x80000000) < 0 )
      goto LABEL_36;
    if ( v9 == -2146893042 )
      goto LABEL_36;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v12 = 34;
    goto LABEL_34;
  }
LABEL_36:
  if ( v20 )
    ((void (__fastcall *)(_QWORD))TSGlobalLsaFunctions->DummyFunction3)(0);
  TSFree(v8);
  if ( ppszCredmanTargetName )
    SspiLocalFree((PVOID)ppszCredmanTargetName);
  if ( v9 < 0 )
  {
    if ( v9 != -1073741275
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_ZDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, (_DWORD)a1, a2->HighPart, a2->LowPart, v9);
    }
    *a4 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016eec  push    rbp
0x180016eee  push    rbx
0x180016eef  push    rsi
0x180016ef0  push    r12
0x180016ef2  push    r13
0x180016ef4  push    r14
0x180016ef6  push    r15
0x180016ef8  lea     rbp, [rsp-20h]
0x180016efd  sub     rsp, 120h
0x180016f04  mov     rax, cs:__security_cookie
0x180016f0b  xor     rax, rsp
0x180016f0e  mov     [rbp+50h+var_40], rax
0x180016f12  mov     r14, rdx
0x180016f15  mov     [rsp+150h+var_F8], r8d
0x180016f1a  xor     edx, edx; Val
0x180016f1c  mov     r15, rcx
0x180016f1f  lea     rcx, [rsp+150h+var_E0]; void *
0x180016f24  mov     r13, r9
0x180016f27  lea     r8d, [rdx+48h]; Size
0x180016f2b  call    memset_0
0x180016f30  xor     ecx, ecx
0x180016f32  mov     [rsp+150h+var_E8], 2
0x180016f3a  mov     [rsp+150h+var_E4], 3
0x180016f42  mov     [rsp+150h+var_100], rcx
0x180016f47  mov     [rsp+150h+var_110], ecx
0x180016f4b  mov     [rsp+150h+ppszCredmanTargetName], rcx
0x180016f50  mov     [rsp+150h+pszTargetName], rcx
0x180016f55  mov     [r13+0], rcx
0x180016f59  test    r15, r15
0x180016f5c  jz      loc_1800172E7
0x180016f62  cmp     cx, [r15]
0x180016f66  jz      loc_1800172E7
0x180016f6c  test    r14, r14
0x180016f6f  jz      loc_1800172E7
0x180016f75  mov     rdx, r15; struct _UNICODE_STRING *
0x180016f78  lea     rcx, [rsp+150h+pszTargetName]; unsigned __int16 **
0x180016f7d  call    ?TSUnicodeStringToString@@YAJPEAPEAGPEAU_UNICODE_STRING@@@Z; TSUnicodeStringToString(ushort * *,_UNICODE_STRING *)
0x180016f82  mov     r12, [rsp+150h+pszTargetName]
0x180016f87  mov     ebx, eax
0x180016f89  lea     rsi, WPP_GLOBAL_Control
0x180016f90  test    eax, eax
0x180016f92  js      loc_180017265
0x180016f98  mov     ebx, 4Ch ; 'L'
0x180016f9d  mov     dword ptr [rsp+150h+pszTargetName], 0
0x180016fa5  mov     r8d, ebx; Size
0x180016fa8  lea     rcx, [rbp+50h+AuthIdentity]; void *
0x180016fac  xor     edx, edx; Val
0x180016fae  call    memset_0
0x180016fb3  movups  xmm0, cs:SEC_WINNT_AUTH_DATA_TYPE_PASSWORD
0x180016fba  lea     ecx, [rbx-1Ch]
0x180016fbd  mov     [rbp+50h+AuthIdentity], 201h
0x180016fc4  mov     [rbp+50h+var_8C], cx
0x180016fc8  lea     eax, [rbx-30h]
0x180016fcb  mov     [rbp+50h+var_74], ecx
0x180016fce  lea     r9, [rsp+150h+ppszCredmanTargetName]; ppszCredmanTargetName
0x180016fd3  lea     rcx, [rbp+50h+AuthIdentity]; AuthIdentity
0x180016fd7  mov     [rbp+50h+var_88], ebx
0x180016fda  lea     r8, [rsp+150h+pszTargetName]; pCredmanCredentialType
0x180016fdf  mov     [rbp+50h+var_60], 1C001Ch
0x180016fe6  mov     rdx, r12; pszTargetName
0x180016fe9  mov     [rbp+50h+var_70], ax
0x180016fed  movdqu  [rbp+50h+var_5C], xmm0
0x180016ff2  call    cs:__imp_SspiPrepareForCredRead
0x180016ff8  mov     ebx, eax
0x180016ffa  test    eax, eax
0x180016ffc  jns     short loc_18001702C
0x180016ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180017005  cmp     rcx, rsi
0x180017008  jz      loc_180017265
0x18001700e  test    byte ptr [rcx+1Ch], 1
0x180017012  jz      loc_180017265
0x180017018  mov     edx, 1Eh
0x18001701d  lea     r8, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x180017024  mov     r9d, eax
0x180017027  jmp     loc_180017255
0x18001702c  mov     rax, [rsp+150h+ppszCredmanTargetName]
0x180017031  lea     rcx, [rsp+150h+var_100]
0x180017036  mov     [rsp+150h+var_E0], rax
0x18001703b  lea     r8, [rsp+150h+var_E0]
0x180017040  mov     [rsp+150h+var_128], rcx
0x180017045  lea     rax, [rsp+150h+pszTargetName]
0x18001704a  mov     [rbp+50h+var_A0], rax
0x18001704e  lea     rcx, [rsp+150h+var_110]
0x180017053  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18001705a  xor     r9d, r9d
0x18001705d  mov     [rbp+50h+var_A8], 1
0x180017064  mov     [rbp+50h+var_A4], 1
0x18001706b  mov     [rsp+150h+var_130], rcx
0x180017070  mov     rcx, r14
0x180017073  mov     rax, [rax+150h]
0x18001707a  lea     edx, [r9+1]
0x18001707e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017083  lea     rsi, WPP_82746c11848034a638789f4e0723fe0c_Traceguids
0x18001708a  mov     ebx, eax
0x18001708c  test    eax, eax
0x18001708e  js      short loc_1800170CC
0x180017090  mov     rcx, cs:WPP_GLOBAL_Control
0x180017097  lea     rax, WPP_GLOBAL_Control
0x18001709e  cmp     rcx, rax
0x1800170a1  jz      loc_1800171E6
0x1800170a7  test    byte ptr [rcx+1Ch], 4
0x1800170ab  jz      loc_1800171E6
0x1800170b1  mov     r9d, [rsp+150h+var_110]
0x1800170b6  mov     edx, 1Fh
0x1800170bb  mov     rcx, [rcx+10h]
0x1800170bf  mov     r8, rsi
0x1800170c2  call    WPP_SF_d
0x1800170c7  jmp     loc_1800171E6
0x1800170cc  cmp     ebx, 0C0000225h
0x1800170d2  jnz     loc_180017231
0x1800170d8  lea     rax, aTsssp; "TSSSP"
0x1800170df  mov     [rsp+150h+var_E0], r12
0x1800170e4  mov     [rbp+50h+var_B0], rax
0x1800170e8  lea     rcx, [rsp+150h+var_100]
0x1800170ed  mov     [rsp+150h+var_128], rcx
0x1800170f2  lea     rax, [rsp+150h+var_E8]
0x1800170f7  mov     [rbp+50h+var_A0], rax
0x1800170fb  lea     rcx, [rsp+150h+var_110]
0x180017100  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180017107  lea     r8, [rsp+150h+var_E0]
0x18001710c  xor     r9d, r9d
0x18001710f  mov     [rbp+50h+var_A4], 2
0x180017116  mov     [rsp+150h+var_130], rcx
0x18001711b  mov     rcx, r14
0x18001711e  mov     rax, [rax+150h]
0x180017125  lea     edx, [r9+1]
0x180017129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001712e  mov     ebx, eax
0x180017130  cmp     eax, 0C0000225h
0x180017135  jz      short loc_180017145
0x180017137  cmp     eax, 0C000005Fh
0x18001713c  jz      short loc_180017145
0x18001713e  cmp     eax, 0C000000Dh
0x180017143  jnz     short loc_1800171AD
0x180017145  mov     edx, 2Fh ; '/'; Ch
0x18001714a  mov     rcx, r12; Str
0x18001714d  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180017152  mov     [rsp+150h+var_E0], rax
0x180017157  test    rax, rax
0x18001715a  jz      short loc_18001719D
0x18001715c  add     rax, 2
0x180017160  lea     rcx, [rsp+150h+var_100]
0x180017165  mov     [rsp+150h+var_128], rcx
0x18001716a  lea     r8, [rsp+150h+var_E0]
0x18001716f  mov     [rsp+150h+var_E0], rax
0x180017174  lea     rcx, [rsp+150h+var_110]
0x180017179  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180017180  xor     r9d, r9d
0x180017183  mov     [rsp+150h+var_130], rcx
0x180017188  mov     rcx, r14
0x18001718b  mov     rax, [rax+150h]
0x180017192  lea     edx, [r9+1]
0x180017196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719b  mov     ebx, eax
0x18001719d  cmp     ebx, 0C0000225h
0x1800171a3  jz      short loc_1800171E2
0x1800171a5  cmp     ebx, 0C000005Fh
0x1800171ab  jz      short loc_1800171E2
0x1800171ad  cmp     ebx, 0C000000Dh
0x1800171b3  jz      short loc_1800171E2
0x1800171b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171bc  lea     rax, WPP_GLOBAL_Control
0x1800171c3  cmp     rcx, rax
0x1800171c6  jz      short loc_1800171E2
0x1800171c8  test    byte ptr [rcx+1Ch], 1
0x1800171cc  jz      short loc_1800171E2
0x1800171ce  mov     rcx, [rcx+10h]
0x1800171d2  mov     edx, 21h ; '!'
0x1800171d7  mov     r9d, ebx
0x1800171da  mov     r8, rsi
0x1800171dd  call    WPP_SF_d
0x1800171e2  test    ebx, ebx
0x1800171e4  js      short loc_18001725E
0x1800171e6  mov     r8d, [rsp+150h+var_F8]; int
0x1800171eb  mov     r9, r13; struct _TS_PRIMARY_CREDENTIAL **
0x1800171ee  mov     edx, [rsp+150h+var_110]; unsigned int
0x1800171f2  mov     rcx, [rsp+150h+var_100]; struct _ENCRYPTED_CREDENTIALW **
0x1800171f7  call    ?TSSelectCredManCred@@YAJPEAPEAU_ENCRYPTED_CREDENTIALW@@KHPEAPEAU_TS_PRIMARY_CREDENTIAL@@@Z; TSSelectCredManCred(_ENCRYPTED_CREDENTIALW * *,ulong,int,_TS_PRIMARY_CREDENTIAL * *)
0x1800171fc  mov     ecx, 80000000h
0x180017201  mov     ebx, eax
0x180017203  add     eax, ecx
0x180017205  test    ecx, eax
0x180017207  jnz     short loc_18001725E
0x180017209  cmp     ebx, 8009030Eh
0x18001720f  jz      short loc_18001725E
0x180017211  mov     rcx, cs:WPP_GLOBAL_Control
0x180017218  lea     rax, WPP_GLOBAL_Control
0x18001721f  cmp     rcx, rax
0x180017222  jz      short loc_18001725E
0x180017224  test    byte ptr [rcx+1Ch], 1
0x180017228  jz      short loc_18001725E
0x18001722a  mov     edx, 22h ; '"'
0x18001722f  jmp     short loc_18001724F
0x180017231  mov     rcx, cs:WPP_GLOBAL_Control
0x180017238  lea     rax, WPP_GLOBAL_Control
0x18001723f  cmp     rcx, rax
0x180017242  jz      short loc_18001725E
0x180017244  test    byte ptr [rcx+1Ch], 1
0x180017248  jz      short loc_18001725E
0x18001724a  mov     edx, 20h ; ' '
0x18001724f  mov     r8, rsi
0x180017252  mov     r9d, ebx
0x180017255  mov     rcx, [rcx+10h]
0x180017259  call    WPP_SF_d
0x18001725e  lea     rsi, WPP_GLOBAL_Control
0x180017265  mov     rdx, [rsp+150h+var_100]
0x18001726a  test    rdx, rdx
0x18001726d  jz      short loc_180017286
0x18001726f  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180017276  mov     ecx, [rsp+150h+var_110]
0x18001727a  mov     rax, [rax+158h]
0x180017281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017286  mov     rcx, r12; void *
0x180017289  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x18001728e  mov     rcx, [rsp+150h+ppszCredmanTargetName]; DataBuffer
0x180017293  test    rcx, rcx
0x180017296  jz      short loc_18001729E
0x180017298  call    cs:__imp_SspiLocalFree
0x18001729e  test    ebx, ebx
0x1800172a0  jns     short loc_1800172E3
0x1800172a2  cmp     ebx, 0C0000225h
0x1800172a8  jz      short loc_1800172DB
0x1800172aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172b1  cmp     rcx, rsi
0x1800172b4  jz      short loc_1800172DB
0x1800172b6  test    byte ptr [rcx+1Ch], 1
0x1800172ba  jz      short loc_1800172DB
0x1800172bc  mov     eax, [r14]
0x1800172bf  mov     r9, r15
0x1800172c2  mov     rcx, [rcx+10h]
0x1800172c6  mov     [rsp+150h+var_120], ebx
0x1800172ca  mov     dword ptr [rsp+150h+var_128], eax
0x1800172ce  mov     eax, [r14+4]
0x1800172d2  mov     dword ptr [rsp+150h+var_130], eax
0x1800172d6  call    WPP_SF_ZDDD
0x1800172db  mov     qword ptr [r13+0], 0
0x1800172e3  mov     eax, ebx
0x1800172e5  jmp     short loc_1800172EC
0x1800172e7  mov     eax, 0C0000225h
0x1800172ec  mov     rcx, [rbp+50h+var_40]
0x1800172f0  xor     rcx, rsp; StackCookie
0x1800172f3  call    __security_check_cookie
0x1800172f8  add     rsp, 120h
0x1800172ff  pop     r15
0x180017301  pop     r14
0x180017303  pop     r13
0x180017305  pop     r12
0x180017307  pop     rsi
0x180017308  pop     rbx
0x180017309  pop     rbp
0x18001730a  retn
```
