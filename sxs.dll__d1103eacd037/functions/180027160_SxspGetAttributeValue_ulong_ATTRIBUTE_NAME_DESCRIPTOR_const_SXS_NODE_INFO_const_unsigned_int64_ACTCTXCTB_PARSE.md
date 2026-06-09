# SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)

- ea: `0x180027160`
- end: `0x1800278a0`
- name: `?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z`
- size: `1856`
- prototype: ``
- caller_count: `20`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800017b8`
- `0x180002a70`
- `0x180005338`
- `0x1800143e0`
- `0x1800278b0`
- `0x18002e6d0`
- `0x18002ee20`
- `0x1800345b0`
- `0x1800358d0`
- `0x1800434a0`
- `0x180044820`
- `0x180045cb0`
- `0x180051030`
- `0x180054be0`
- `0x180055cf0`
- `0x180059180`
- `0x1800659f0`
- `0x180065d30`
- `0x180065f30`
- `0x180066140`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000dffc`
- `0x18001c2c8`
- `0x18001e5c0`
- `0x180027160`
- `0x180033b50`
- `0x18005b8a0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180027449`
- `ntdll!RtlCompareUnicodeString` at `0x18002767e`
- `ntdll!RtlCompareUnicodeString` at `0x180027449`
- `ntdll!RtlCompareUnicodeString` at `0x18002767e`
- `ntdll!RtlPopFrame` at `0x18002733f`
- `ntdll!RtlPopFrame` at `0x18002733f`
- `ntdll!RtlPushFrame` at `0x180027205`
- `ntdll!RtlPushFrame` at `0x180027205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800273e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002749f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002754e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800275c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800275f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002783e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800273e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002749f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002754e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800275c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800275f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002783e`

## pseudocode

```c
__int64 __fastcall SxspGetAttributeValue(
        int a1,
        WCHAR **a2,
        __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        _BYTE *a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        unsigned int (__fastcall *a10)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))
{
  const char *v13; // rcx
  WCHAR *v14; // rdx
  __int64 v15; // r14
  WCHAR *v16; // r8
  WCHAR *v17; // rax
  WCHAR *v18; // rdi
  unsigned int v19; // ebx
  __int64 v21; // r9
  WCHAR *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdi
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // rax
  const void *v27; // r9
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // rdx
  _WORD *v32; // rcx
  __int64 v33; // rdi
  WCHAR *v34; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // rdi
  void *v37; // rax
  DWORD LastError; // eax
  __int16 v40; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v41; // [rsp+48h] [rbp-B8h]
  __int64 v42; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v43; // [rsp+50h] [rbp-B0h]
  WCHAR *v44; // [rsp+58h] [rbp-A8h]
  char *v45; // [rsp+58h] [rbp-A8h]
  void *v46; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING String1; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-70h] BYREF
  char v49[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v50; // [rsp+A4h] [rbp-5Ch] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h]
  int v53; // [rsp+C8h] [rbp-38h]
  int *v54; // [rsp+D0h] [rbp-30h]
  void **v55; // [rsp+E0h] [rbp-20h] BYREF
  int v56; // [rsp+E8h] [rbp-18h]
  void *Src; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v58; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v59; // [rsp+100h] [rbp+0h]
  __int16 v60; // [rsp+108h] [rbp+8h] BYREF

  v50 = 0;
  Frame.Previous = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D280;
  v54 = &v50;
  Frame.Flags = 1;
  v52 = 544438355;
  v53 = 1955;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v55 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v56 = 0;
  Src = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  Src = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v55);
  v58 = ((__int64 (__fastcall *)(void ***))v55[3])(&v55);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(Src, 0, 2 * v58);
  *a6 = 0;
  *a9 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 )
  {
    v53 = 1967;
    goto LABEL_25;
  }
  if ( !a2 )
  {
    v53 = 1968;
    goto LABEL_25;
  }
  v13 = (const char *)a4;
  if ( !a3 && a4 )
  {
    v53 = 1969;
    goto LABEL_25;
  }
  if ( !a8 && a7 )
  {
    v53 = 1970;
    goto LABEL_25;
  }
  if ( !a10 && a7 != 168 && a7 != 560 && a7 && a7 != 56 )
  {
    v53 = 1973;
LABEL_25:
    FusionpTraceParameterCheck(v13);
    SetLastError(0x57u);
    *v54 = 0;
    goto LABEL_14;
  }
  v14 = a2[2];
  v15 = 0;
  v16 = a2[3];
  v17 = *a2;
  v18 = a2[1];
  v46 = v14;
  v40 = (__int16)v16;
  v44 = v17;
  while ( 1 )
  {
    if ( (unsigned int)v15 >= (unsigned __int64)v13 )
      goto LABEL_12;
    v21 = a3 + 192 * v15;
    v42 = v21;
    if ( *(_DWORD *)(v21 + 4) == 2 )
      break;
LABEL_19:
    v15 = (unsigned int)(v15 + 1);
  }
  v22 = *(WCHAR **)(v21 + 176);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v22;
  LOWORD(v22) = 2 * *(_WORD *)(v21 + 184);
  *(&String2.MaximumLength + 2) = 0;
  String1.Length = (unsigned __int16)v22;
  String1.MaximumLength = (unsigned __int16)v22;
  String2.Buffer = v14;
  String2.Length = 2 * (_WORD)v16;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * (_WORD)v16);
  if ( RtlCompareUnicodeString(&String1, &String2, 0) )
    goto LABEL_50;
  v23 = *(_QWORD *)(v42 + 40);
  if ( v23 || v18 )
  {
    v34 = *(WCHAR **)(v42 + 24);
    *(&String1.MaximumLength + 2) = 0;
    String1.Buffer = v34;
    *(&String2.MaximumLength + 2) = 0;
    String2.Buffer = v44;
    String1.Length = 2 * v23;
    *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * v23);
    String2.Length = 2 * (_WORD)v18;
    *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * (_WORD)v18);
    if ( RtlCompareUnicodeString(&String1, &String2, 0) )
    {
LABEL_50:
      LOWORD(v16) = v40;
      v14 = (WCHAR *)v46;
      v13 = (const char *)a4;
      goto LABEL_19;
    }
  }
  while ( 1 )
  {
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= a4 )
      break;
    v24 = 192 * v15;
    if ( *(_DWORD *)(192 * v15 + a3 + 4) != 13 )
      break;
    SetLastError(0);
    v25 = *(_QWORD *)(v24 + a3 + 184);
    v41 = v25;
    v26 = v25 + 1;
    *(_QWORD *)&String2.Length = v25 + 1;
    if ( v25 + 1 > 1 )
    {
      v27 = *(const void **)(v24 + a3 + 176);
      v28 = v59;
      v29 = v58;
      *(_QWORD *)&String1.Length = v27;
      v30 = v59 + v26;
      v43 = v59 + v26;
      if ( v59 + v26 > v58 )
      {
        v46 = 0;
        if ( !((unsigned int (__fastcall *)(void ***, unsigned __int64, void **))*v55)(&v55, v59 + v26, &v46) )
        {
          *v54 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075710);
          goto LABEL_14;
        }
        if ( v30 )
        {
          v45 = (char *)v46;
          if ( Src )
          {
            v35 = v59;
            if ( v59 >= v30 )
              v35 = v30 - 1;
            v36 = 2 * v35;
            memcpy_0(v46, Src, 2 * v35);
            *(_WORD *)&v45[v36] = 0;
            v30 = v43;
          }
          else
          {
            *(_WORD *)v46 = 0;
          }
        }
        if ( Src )
        {
          v37 = (void *)((__int64 (__fastcall *)(void ***))v55[2])(&v55);
          if ( Src != v37 )
            ((void (__fastcall *)(void ***))v55[1])(&v55);
        }
        v29 = v30;
        v28 = v59;
        v25 = v41;
        v27 = *(const void **)&String1.Length;
        Src = v46;
        v58 = v30;
      }
      v31 = v29 - v28;
      if ( v31 )
      {
        v32 = (char *)Src + 2 * v28;
        *(_QWORD *)&String1.Length = v32;
        if ( v27 )
        {
          if ( v25 >= v31 )
            v25 = v31 - 1;
          v33 = 2 * v25;
          memcpy_0(v32, v27, 2 * v25);
          *(_WORD *)(v33 + *(_QWORD *)&String1.Length) = 0;
        }
        else
        {
          *v32 = 0;
        }
        v28 = v59;
      }
      v59 = v28 + *(_QWORD *)&String2.Length - 1LL;
    }
  }
  if ( a10 )
  {
    v49[0] = 0;
    SetLastError(0);
    if ( !a10(0, &v55, v49, a7, a8, a9) )
    {
      *v54 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DD18);
      goto LABEL_14;
    }
    if ( v49[0] )
    {
LABEL_43:
      *a6 = 1;
      goto LABEL_12;
    }
    (*(void (__fastcall **)(__int64, WCHAR **, void *, unsigned __int64))(a5 + 112))(a5, a2, Src, v59);
    SetLastError(0x36B5u);
    *v54 = 0;
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_1800756F0);
  }
  else
  {
    if ( !a8 )
      goto LABEL_43;
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(a8, &v55) )
    {
      *v54 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800701B0);
      goto LABEL_14;
    }
    *a9 = 2LL * *(_QWORD *)(a8 + 32);
    *a6 = 1;
LABEL_12:
    if ( (a1 & 1) == 0 || *a6 )
    {
      v50 = 1;
    }
    else
    {
      (*(void (__fastcall **)(__int64, WCHAR **))(a5 + 96))(a5, a2);
      SetLastError(0x36B5u);
      *v54 = 0;
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_1800756D0);
    }
  }
LABEL_14:
  v19 = v50;
  v55 = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  if ( Src != &v60 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v55);
  v55 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  Src = 0;
  v58 = 0;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v54 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v19;
}

```

## disassembly

```asm
0x180027160  mov     [rsp-8+arg_0], rbx
0x180027165  push    rbp
0x180027166  push    rsi
0x180027167  push    rdi
0x180027168  push    r12
0x18002716a  push    r13
0x18002716c  push    r14
0x18002716e  push    r15
0x180027170  lea     rbp, [rsp-220h]
0x180027178  sub     rsp, 320h
0x18002717f  mov     rax, cs:__security_cookie
0x180027186  xor     rax, rsp
0x180027189  mov     [rbp+250h+var_40], rax
0x180027190  mov     rax, [rbp+250h+arg_20]
0x180027197  mov     esi, ecx
0x180027199  mov     rdi, [rbp+250h+arg_38]
0x1800271a0  lea     rcx, [rbp+250h+Frame]; Frame
0x1800271a4  mov     r14, [rbp+250h+arg_40]
0x1800271ab  mov     r15, r8
0x1800271ae  mov     r13, [rbp+250h+arg_28]
0x1800271b5  mov     rbx, rdx
0x1800271b8  mov     r12, [rbp+250h+arg_48]
0x1800271bf  mov     [rsp+350h+var_2E0], rax
0x1800271c4  xor     eax, eax
0x1800271c6  mov     [rbp+250h+var_2AC], eax
0x1800271c9  mov     [rbp+250h+Frame.Previous], rax
0x1800271cd  lea     rax, qword_18006D280
0x1800271d4  mov     [rbp+250h+Frame.Context], rax
0x1800271d8  lea     rax, [rbp+250h+var_2AC]
0x1800271dc  mov     [rbp+250h+var_280], rax
0x1800271e0  mov     [rsp+350h+var_310], r9
0x1800271e5  mov     [rsp+350h+var_2E8], rdi
0x1800271ea  mov     [rsp+350h+var_2F0], r14
0x1800271ef  mov     [rbp+250h+Frame.Flags], 1
0x1800271f6  mov     [rbp+250h+var_290], 20737853h
0x1800271fe  mov     [rbp+250h+var_288], 7A3h
0x180027205  call    cs:__imp_RtlPushFrame
0x18002720c  nop     dword ptr [rax+rax+00h]
0x180027211  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180027218  jnz     loc_180027631
0x18002721e  xor     eax, eax
0x180027220  lea     rcx, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180027227  mov     [rbp+250h+var_270], rcx
0x18002722b  lea     rcx, [rbp+250h+var_270]
0x18002722f  mov     [rbp+250h+var_268], eax
0x180027232  mov     [rbp+250h+Src], rax
0x180027236  mov     [rbp+250h+var_258], rax
0x18002723a  mov     [rbp+250h+var_250], rax
0x18002723e  mov     [rbp+250h+var_248], ax
0x180027242  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180027247  mov     [rbp+250h+Src], rax
0x18002724b  lea     rcx, [rbp+250h+var_270]
0x18002724f  mov     rax, [rbp+250h+var_270]
0x180027253  mov     rax, [rax+18h]
0x180027257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002725c  mov     [rbp+250h+var_258], rax
0x180027260  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180027265  test    eax, eax
0x180027267  jz      short loc_18002727B
0x180027269  mov     r8, [rbp+250h+var_258]
0x18002726d  xor     edx, edx; Val
0x18002726f  mov     rcx, [rbp+250h+Src]; void *
0x180027273  add     r8, r8; Size
0x180027276  call    memset_0
0x18002727b  mov     byte ptr [r13+0], 0
0x180027280  mov     qword ptr [r14], 0
0x180027287  test    esi, 0FFFFFFFEh
0x18002728d  jnz     loc_1800277AB
0x180027293  test    rbx, rbx
0x180027296  jz      loc_1800277B7
0x18002729c  mov     rcx, [rsp+350h+var_310]; char *
0x1800272a1  test    r15, r15
0x1800272a4  jz      loc_1800277C3
0x1800272aa  test    rdi, rdi
0x1800272ad  jz      loc_1800277D8
0x1800272b3  test    r12, r12
0x1800272b6  jz      loc_180027397
0x1800272bc  mov     rdx, [rbx+10h]
0x1800272c0  xor     r14d, r14d
0x1800272c3  mov     r8, [rbx+18h]
0x1800272c7  mov     rax, [rbx]
0x1800272ca  mov     rdi, [rbx+8]
0x1800272ce  mov     [rsp+350h+var_2D8], rdx
0x1800272d3  mov     [rsp+350h+var_308], r8
0x1800272d8  mov     [rsp+350h+var_2F8], rax
0x1800272dd  mov     eax, r14d
0x1800272e0  cmp     rax, rcx
0x1800272e3  jb      loc_180027378
0x1800272e9  test    sil, 1
0x1800272ed  jnz     loc_1800275A3
0x1800272f3  mov     [rbp+250h+var_2AC], 1
0x1800272fa  xor     edi, edi
0x1800272fc  mov     rdx, [rbp+250h+Src]
0x180027300  lea     rax, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180027307  mov     ebx, [rbp+250h+var_2AC]
0x18002730a  mov     [rbp+250h+var_270], rax
0x18002730e  lea     rax, [rbp+250h+var_248]
0x180027312  cmp     rdx, rax
0x180027315  jnz     loc_180027863
0x18002731b  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180027322  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x180027329  mov     [rbp+250h+var_270], rax
0x18002732d  mov     [rbp+250h+Src], rdi
0x180027331  mov     [rbp+250h+var_258], rdi
0x180027335  jnz     loc_180027871
0x18002733b  lea     rcx, [rbp+250h+Frame]; Frame
0x18002733f  call    cs:__imp_RtlPopFrame
0x180027346  nop     dword ptr [rax+rax+00h]
0x18002734b  mov     eax, ebx
0x18002734d  mov     rcx, [rbp+250h+var_40]
0x180027354  xor     rcx, rsp; StackCookie
0x180027357  call    __security_check_cookie
0x18002735c  mov     rbx, [rsp+350h+arg_0]
0x180027364  add     rsp, 320h
0x18002736b  pop     r15
0x18002736d  pop     r14
0x18002736f  pop     r13
0x180027371  pop     r12
0x180027373  pop     rdi
0x180027374  pop     rsi
0x180027375  pop     rbp
0x180027376  retn
0x180027378  lea     r9, [r14+r14*2]
0x18002737c  shl     r9, 6
0x180027380  add     r9, r15
0x180027383  mov     [rsp+350h+var_300], r9
0x180027388  cmp     dword ptr [r9+4], 2
0x18002738d  jz      short loc_1800273FF
0x18002738f  inc     r14d
0x180027392  jmp     loc_1800272DD
0x180027397  cmp     [rbp+250h+arg_30], 0A8h
0x1800273a2  jz      loc_1800272BC
0x1800273a8  cmp     [rbp+250h+arg_30], 230h
0x1800273b3  jz      loc_1800272BC
0x1800273b9  cmp     [rbp+250h+arg_30], 0
0x1800273c1  jz      loc_1800272BC
0x1800273c7  cmp     [rbp+250h+arg_30], 38h ; '8'
0x1800273cf  jz      loc_1800272BC
0x1800273d5  mov     [rbp+250h+var_288], 7B5h
0x1800273dc  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800273e1  mov     ecx, 57h ; 'W'; dwErrCode
0x1800273e6  call    cs:__imp_SetLastError
0x1800273ed  nop     dword ptr [rax+rax+00h]
0x1800273f2  mov     rax, [rbp+250h+var_280]
0x1800273f6  xor     edi, edi
0x1800273f8  mov     [rax], edi
0x1800273fa  jmp     loc_1800272FC
0x1800273ff  mov     rax, [r9+0B0h]
0x180027406  lea     rcx, [rbp+250h+String1]; String1
0x18002740a  xorps   xmm0, xmm0
0x18002740d  xorps   xmm1, xmm1
0x180027410  movups  xmmword ptr [rbp+250h+String1.Length], xmm0
0x180027414  mov     [rbp+250h+String1.Buffer], rax
0x180027418  movzx   eax, word ptr [r9+0B8h]
0x180027420  add     ax, ax
0x180027423  movups  xmmword ptr [rbp+250h+String2.Length], xmm1
0x180027427  mov     [rbp+250h+String1.Length], ax
0x18002742b  mov     [rbp+250h+String1.MaximumLength], ax
0x18002742f  movzx   eax, r8w
0x180027433  add     ax, ax
0x180027436  mov     [rbp+250h+String2.Buffer], rdx
0x18002743a  xor     r8d, r8d; CaseInsensitive
0x18002743d  mov     [rbp+250h+String2.Length], ax
0x180027441  lea     rdx, [rbp+250h+String2]; String2
0x180027445  mov     [rbp+250h+String2.MaximumLength], ax
0x180027449  call    cs:__imp_RtlCompareUnicodeString
0x180027450  nop     dword ptr [rax+rax+00h]
0x180027455  test    eax, eax
0x180027457  jnz     loc_180027692
0x18002745d  mov     rax, [rsp+350h+var_300]
0x180027462  mov     rcx, [rax+28h]
0x180027466  test    rcx, rcx
0x180027469  jnz     loc_18002763B
0x18002746f  test    rdi, rdi
0x180027472  jnz     loc_18002763B
0x180027478  inc     r14d
0x18002747b  mov     eax, r14d
0x18002747e  cmp     rax, [rsp+350h+var_310]
0x180027483  jnb     loc_18002753F
0x180027489  lea     rdi, [r14+r14*2]
0x18002748d  shl     rdi, 6
0x180027491  cmp     dword ptr [rdi+r15+4], 0Dh
0x180027497  jnz     loc_18002753F
0x18002749d  xor     ecx, ecx; dwErrCode
0x18002749f  call    cs:__imp_SetLastError
0x1800274a6  nop     dword ptr [rax+rax+00h]
0x1800274ab  mov     r8, [rdi+r15+0B8h]
0x1800274b3  mov     [rsp+350h+var_308], r8
0x1800274b8  lea     rax, [r8+1]
0x1800274bc  mov     qword ptr [rbp+250h+String2.Length], rax
0x1800274c0  cmp     rax, 1
0x1800274c4  jbe     short loc_180027478
0x1800274c6  mov     r9, [rdi+r15+0B0h]
0x1800274ce  mov     rcx, [rbp+250h+var_250]
0x1800274d2  mov     rdx, [rbp+250h+var_258]
0x1800274d6  mov     qword ptr [rbp+250h+String1.Length], r9
0x1800274da  lea     rdi, [rcx+rax]
0x1800274de  mov     [rsp+350h+var_300], rdi
0x1800274e3  cmp     rdi, rdx
0x1800274e6  ja      loc_1800276A6
0x1800274ec  sub     rdx, rcx
0x1800274ef  jz      short loc_18002752C
0x1800274f1  mov     rax, [rbp+250h+Src]
0x1800274f5  lea     rcx, [rax+rcx*2]; void *
0x1800274f9  mov     qword ptr [rbp+250h+String1.Length], rcx
0x1800274fd  test    r9, r9
0x180027500  jz      loc_180027781
0x180027506  cmp     r8, rdx
0x180027509  jnb     loc_1800277FB
0x18002750f  lea     rdi, [r8+r8]
0x180027513  mov     rdx, r9; Src
0x180027516  mov     r8, rdi; Size
0x180027519  call    memcpy_0
0x18002751e  mov     rcx, qword ptr [rbp+250h+String1.Length]
0x180027522  xor     eax, eax
0x180027524  mov     [rdi+rcx], ax
0x180027528  mov     rcx, [rbp+250h+var_250]
0x18002752c  mov     rax, qword ptr [rbp+250h+String2.Length]
0x180027530  dec     rax
0x180027533  add     rax, rcx
0x180027536  mov     [rbp+250h+var_250], rax
0x18002753a  jmp     loc_180027478
0x18002753f  test    r12, r12
0x180027542  jz      loc_1800275EC
0x180027548  xor     ecx, ecx; dwErrCode
0x18002754a  mov     [rbp+250h+var_2B0], 0
0x18002754e  call    cs:__imp_SetLastError
0x180027555  nop     dword ptr [rax+rax+00h]
0x18002755a  mov     rcx, [rsp+350h+var_2F0]
0x18002755f  lea     r8, [rbp+250h+var_2B0]
0x180027563  mov     rax, [rsp+350h+var_2E8]
0x180027568  lea     rdx, [rbp+250h+var_270]
0x18002756c  mov     r9, [rbp+250h+arg_30]
0x180027573  mov     [rsp+350h+var_328], rcx
0x180027578  xor     ecx, ecx
0x18002757a  mov     [rsp+350h+var_330], rax
0x18002757f  mov     rax, r12
0x180027582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027587  test    eax, eax
0x180027589  jz      loc_180027768
0x18002758f  cmp     [rbp+250h+var_2B0], 0
0x180027593  jz      loc_18002781D
0x180027599  mov     byte ptr [r13+0], 1
0x18002759e  jmp     loc_1800272E9
0x1800275a3  cmp     byte ptr [r13+0], 0
0x1800275a8  jnz     loc_1800272F3
0x1800275ae  mov     rax, [rsp+350h+var_2E0]
0x1800275b3  mov     rdx, rbx
0x1800275b6  mov     rcx, rax
0x1800275b9  mov     rax, [rax+60h]
0x1800275bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275c2  mov     ecx, 36B5h; dwErrCode
0x1800275c7  call    cs:__imp_SetLastError
0x1800275ce  nop     dword ptr [rax+rax+00h]
0x1800275d3  mov     rax, [rbp+250h+var_280]
0x1800275d7  lea     rcx, off_1800756D0; struct _CALL_SITE_INFO *
0x1800275de  xor     edi, edi
0x1800275e0  mov     [rax], edi
0x1800275e2  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800275e7  jmp     loc_1800272FC
0x1800275ec  mov     rdi, [rsp+350h+var_2E8]
0x1800275f1  test    rdi, rdi
0x1800275f4  jz      short loc_180027599
0x1800275f6  xor     ecx, ecx; dwErrCode
0x1800275f8  call    cs:__imp_SetLastError
0x1800275ff  nop     dword ptr [rax+rax+00h]
0x180027604  lea     rdx, [rbp+250h+var_270]
0x180027608  mov     rcx, rdi
0x18002760b  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x180027610  test    eax, eax
0x180027612  jz      loc_180027792
0x180027618  mov     rax, [rdi+20h]
0x18002761c  mov     rcx, [rsp+350h+var_2F0]
0x180027621  add     rax, rax
0x180027624  mov     [rcx], rax
0x180027627  mov     byte ptr [r13+0], 1
0x18002762c  jmp     loc_1800272E9
0x180027631  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180027636  jmp     loc_18002721E
0x18002763b  mov     rax, [rax+18h]
0x18002763f  lea     rdx, [rbp+250h+String2]; String2
0x180027643  add     cx, cx
0x180027646  xorps   xmm0, xmm0
0x180027649  movups  xmmword ptr [rbp+250h+String1.Length], xmm0
0x18002764d  mov     [rbp+250h+String1.Buffer], rax
0x180027651  xor     r8d, r8d; CaseInsensitive
0x180027654  mov     rax, [rsp+350h+var_2F8]
0x180027659  xorps   xmm1, xmm1
0x18002765c  movups  xmmword ptr [rbp+250h+String2.Length], xmm1
0x180027660  mov     [rbp+250h+String2.Buffer], rax
0x180027664  movzx   eax, di
0x180027667  add     ax, ax
0x18002766a  mov     [rbp+250h+String1.Length], cx
0x18002766e  mov     [rbp+250h+String1.MaximumLength], cx
0x180027672  lea     rcx, [rbp+250h+String1]; String1
0x180027676  mov     [rbp+250h+String2.Length], ax
0x18002767a  mov     [rbp+250h+String2.MaximumLength], ax
0x18002767e  call    cs:__imp_RtlCompareUnicodeString
0x180027685  nop     dword ptr [rax+rax+00h]
0x18002768a  test    eax, eax
  ... truncated ...
```
