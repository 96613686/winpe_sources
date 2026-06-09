# WldpIsFileTrusted(void * const,ushort const *,ulong,ulong,uchar,ulong *)

- ea: `0x180015118`
- end: `0x1800155ed`
- name: `?WldpIsFileTrusted@@YAJQEAXPEBGKKEPEAK@Z`
- size: `1237`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned int, unsigned int, char, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180014ad0`

## callees

- `0x180015118`
- `0x1800175fc`
- `0x180018518`
- `0x180018918`
- `0x18001af7c`
- `0x18001e6b8`
- `0x18001f8c4`
- `0x180021ec0`
- `0x180022a10`
- `0x18002a2dc`
- `0x18002b90c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015327`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180015327`
- `WINTRUST!WTLogSmartAppControlDefenderInfo` at `0x180015464`
- `WINTRUST!WTLogSmartAppControlDefenderInfo` at `0x180015464`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x1800154c9`
- `WINTRUST!WTLogConfigCiScriptEvent2` at `0x1800154c9`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x180015509`
- `WINTRUST!WTLogConfigCiSignerEvent` at `0x180015509`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpIsFileTrusted(
        void *const a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        char a5,
        unsigned int *a6)
{
  __int64 v10; // r15
  char v11; // r14
  int v12; // esi
  int IsFileTrustedByConfigCi; // eax
  __int64 v14; // r8
  const char *v15; // r9
  unsigned int v16; // edi
  int v17; // ebx
  int v18; // ecx
  int *v19; // r15
  __int64 v20; // rcx
  unsigned __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rax
  bool v24; // dl
  __int64 v25; // rax
  bool v26; // al
  char *v27; // rax
  char *v28; // rsi
  void *i; // rcx
  unsigned __int64 v30; // r8
  __int64 result; // rax
  char v32; // [rsp+40h] [rbp-1B8h] BYREF
  char v33; // [rsp+41h] [rbp-1B7h]
  int v34; // [rsp+44h] [rbp-1B4h] BYREF
  int v35; // [rsp+48h] [rbp-1B0h]
  void *v36; // [rsp+50h] [rbp-1A8h]
  __int128 v37; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-190h]
  __int128 v39; // [rsp+70h] [rbp-188h] BYREF
  __int64 v40; // [rsp+80h] [rbp-178h]
  __int64 v41; // [rsp+88h] [rbp-170h] BYREF
  unsigned __int64 v42; // [rsp+90h] [rbp-168h]
  unsigned int *v43; // [rsp+98h] [rbp-160h]
  __int128 v44; // [rsp+A0h] [rbp-158h] BYREF
  GUID ActivityId; // [rsp+B0h] [rbp-148h] BYREF
  int v46; // [rsp+C0h] [rbp-138h] BYREF
  int v47; // [rsp+C4h] [rbp-134h] BYREF
  unsigned int v48; // [rsp+C8h] [rbp-130h]
  int v49; // [rsp+CCh] [rbp-12Ch]
  char v50; // [rsp+D0h] [rbp-128h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v36 = a1;
  v43 = a6;
  try
  {
    v35 = 0;
    v44 = 0;
    v34 = 0;
    v32 = 0;
    v10 = 0;
    v41 = 0;
    ActivityId = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v46 = 0;
    memset_0(&v47, 0, 0xE4u);
    if ( (a4 & 0x80000005) == 0x80000005 )
    {
      v11 = 1;
      LOBYTE(v12) = (a4 & 0x80000007) == -2147483641;
      v33 = v12;
      IsFileTrustedByConfigCi = WldpIsFileTrustedByConfigCi(
                                  (unsigned __int64)a1,
                                  (__int64)a2,
                                  (__int64)&v39,
                                  (__int64)&v37,
                                  &v41,
                                  (unsigned int *)&v34,
                                  &v44,
                                  &v32);
      v35 = IsFileTrustedByConfigCi;
      v10 = v41;
    }
    else
    {
      v11 = 0;
      LOBYTE(v12) = (a4 & 0x8000001C) == -2147483620;
      v33 = v12;
      IsFileTrustedByConfigCi = WldpIsFileTrustedBySbcp((int)a1, (int)a2, a5, &v34, &v44, &v32);
      v35 = IsFileTrustedByConfigCi;
    }
    v16 = IsFileTrustedByConfigCi;
    if ( IsFileTrustedByConfigCi < 0 )
    {
      v18 = IsFileTrustedByConfigCi;
      v47 = IsFileTrustedByConfigCi;
      v12 = (unsigned __int8)v12;
      v17 = (unsigned __int8)v12 + 2;
      v48 = v17;
      v34 = v17;
    }
    else
    {
      v17 = v34;
      if ( v34 == 1 )
        v18 = 0;
      else
        v18 = v11 != 0 ? -790036478 : -800915454;
      v47 = v18;
      v48 = v34;
      v12 = (unsigned __int8)v12;
    }
    if ( v18 >= 0 && v17 == 1 )
    {
      LOBYTE(v14) = v32;
      v16 = WldpCheckSipAgainstHostId(&v44, a3, v14);
      v35 = v16;
      if ( v16 == -2147016663 )
      {
        v47 = -2147016663;
        v17 = v12 + 2;
        v48 = v12 + 2;
        v34 = v12 + 2;
      }
    }
    if ( v11 )
    {
      EventActivityIdControl(3u, &ActivityId);
      if ( (_QWORD)v37 == *((_QWORD *)&v37 + 1) )
      {
        v19 = &v46;
      }
      else
      {
        v19 = (int *)(v37 + 232 * v10);
        v19[1] = v47;
        v19[2] = v48;
        v19[3] = v49;
        *((_BYTE *)v19 + 16) = v50;
        WldpSmartAppControlTelemetryAndToast(
          (struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *)v19,
          (struct SAC_REPUTATION_EXTRA_INFO_ *)(v37 + 80),
          a2,
          a3,
          v36);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAC_LocalLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SAC_LocalLogging>::GetImpl'::`2'::impl) )
        {
          v21 = 0;
          v42 = 0;
          while ( v21 < 0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)&v37 + 1) - v37) >> 3) )
          {
            v22 = 232 * v21 + v37;
            v23 = *(_QWORD *)(v22 + 36) - 0x49AEFFF10283AC0FLL;
            if ( *(_QWORD *)(v22 + 36) == 0x49AEFFF10283AC0FLL )
              v23 = *(_QWORD *)(v22 + 44) + 0x2935CFCE6C755E53LL;
            v24 = v23 == 0;
            v25 = *(_QWORD *)(v22 + 36) - 0x49AEFFF11283AC0FLL;
            if ( *(_QWORD *)(v22 + 36) == 0x49AEFFF11283AC0FLL )
              v25 = *(_QWORD *)(v22 + 44) + 0x2935CFCE6C755E53LL;
            v26 = v25 == 0;
            if ( v24 || v26 )
              WTLogSmartAppControlDefenderInfo(v22, &ActivityId, a2, 0xD6CA3031938AA1ADuLL);
            v42 = ++v21;
          }
        }
      }
      if ( (_QWORD)v39 == *((_QWORD *)&v39 + 1) )
        v20 = 0;
      else
        v20 = *(_QWORD *)(v39 + 8 * v41);
      WTLogConfigCiScriptEvent2(v20, v36, a2, -1, 0, v19, &ActivityId);
      if ( v48 != 1 )
      {
        v27 = 0;
        v28 = 0;
        for ( i = 0; ; i = v27 )
        {
          v36 = v27;
          v30 = (__int64)(*((_QWORD *)&v39 + 1) - v39) >> 3;
          if ( (unsigned __int64)v28 >= v30 )
            break;
          WTLogConfigCiSignerEvent(*(_QWORD *)(v39 + 8LL * (_QWORD)i), &ActivityId, v30, (unsigned int)v27);
          v27 = v28 + 1;
          v28 = v27;
        }
      }
    }
    *v43 = v17;
    if ( v33 )
      v16 = 0;
    if ( (_QWORD)v39 )
    {
      std::_Destroy_range_std::allocator_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd::integral_constant_unsigned___int64_0__void___void___0_std::nullptr_t_________(
        v39,
        *((_QWORD *)&v39 + 1));
      std::_Deallocate<16>(v39, (v40 - v39) & 0xFFFFFFFFFFFFFFF8uLL);
      v39 = 0;
      v40 = 0;
    }
    if ( (_QWORD)v37 )
    {
      std::_Destroy_range_std::allocator_wil::unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____(
        v37,
        *((_QWORD *)&v37 + 1));
      std::_Deallocate<16>(v37, 8 * ((v38 - (__int64)v37) >> 3));
      v37 = 0;
      v38 = 0;
    }
    result = v16;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5B7,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180015118  push    rbx
0x18001511a  push    rsi
0x18001511b  push    rdi
0x18001511c  push    r12
0x18001511e  push    r13
0x180015120  push    r14
0x180015122  push    r15
0x180015124  sub     rsp, 1C0h
0x18001512b  mov     rax, cs:__security_cookie
0x180015132  xor     rax, rsp
0x180015135  mov     [rsp+1F8h+var_48], rax
0x18001513d  mov     ebx, r9d
0x180015140  mov     r12d, r8d
0x180015143  mov     r13, rdx
0x180015146  mov     rdi, rcx
0x180015149  mov     [rsp+1F8h+var_1A8], rcx
0x18001514e  mov     rax, [rsp+1F8h+arg_28]
0x180015156  mov     [rsp+1F8h+var_160], rax
0x18001515e  xor     esi, esi
0x180015160  mov     [rsp+1F8h+var_1B0], esi
0x180015164  xorps   xmm0, xmm0
0x180015167  movups  [rsp+1F8h+var_158], xmm0
0x18001516f  mov     [rsp+1F8h+var_1B4], esi
0x180015173  mov     [rsp+1F8h+var_1B8], sil
0x180015178  mov     r15d, esi
0x18001517b  mov     [rsp+1F8h+var_170], rsi
0x180015183  movups  xmmword ptr [rsp+1F8h+ActivityId.Data1], xmm0
0x18001518b  xorps   xmm1, xmm1
0x18001518e  movdqu  [rsp+1F8h+var_1A0], xmm1
0x180015194  mov     [rsp+1F8h+var_190], rsi
0x180015199  movdqu  [rsp+1F8h+var_188], xmm0
0x18001519f  mov     [rsp+1F8h+var_178], rsi
0x1800151a7  mov     [rsp+1F8h+var_138], esi
0x1800151ae  xor     edx, edx; Val
0x1800151b0  mov     r8d, 0E4h; Size
0x1800151b6  lea     rcx, [rsp+1F8h+var_134]; void *
0x1800151be  call    memset_0
0x1800151c3  mov     eax, ebx
0x1800151c5  mov     ecx, 80000005h
0x1800151ca  and     eax, ecx
0x1800151cc  mov     rdx, r13
0x1800151cf  cmp     eax, ecx
0x1800151d1  mov     rcx, rdi
0x1800151d4  jnz     short loc_180015236
0x1800151d6  mov     r14b, 1
0x1800151d9  mov     eax, 80000007h
0x1800151de  and     ebx, eax
0x1800151e0  cmp     ebx, eax
0x1800151e2  setz    sil
0x1800151e6  mov     [rsp+1F8h+var_1B7], sil
0x1800151eb  lea     rax, [rsp+1F8h+var_1B8]
0x1800151f0  mov     [rsp+1F8h+var_1C0], rax
0x1800151f5  lea     rax, [rsp+1F8h+var_158]
0x1800151fd  mov     [rsp+1F8h+var_1C8], rax
0x180015202  lea     rax, [rsp+1F8h+var_1B4]
0x180015207  mov     [rsp+1F8h+var_1D0], rax
0x18001520c  lea     rax, [rsp+1F8h+var_170]
0x180015214  mov     [rsp+1F8h+var_1D8], rax
0x180015219  lea     r9, [rsp+1F8h+var_1A0]
0x18001521e  lea     r8, [rsp+1F8h+var_188]
0x180015223  call    WldpIsFileTrustedByConfigCi
0x180015228  mov     [rsp+1F8h+var_1B0], eax
0x18001522c  mov     r15, [rsp+1F8h+var_170]
0x180015234  jmp     short loc_180015278
0x180015236  mov     r14b, sil
0x180015239  mov     eax, 8000001Ch
0x18001523e  and     ebx, eax
0x180015240  cmp     ebx, eax
0x180015242  setz    sil
0x180015246  mov     [rsp+1F8h+var_1B7], sil
0x18001524b  lea     rax, [rsp+1F8h+var_1B8]
0x180015250  mov     [rsp+1F8h+var_1D0], rax
0x180015255  lea     rax, [rsp+1F8h+var_158]
0x18001525d  mov     [rsp+1F8h+var_1D8], rax
0x180015262  lea     r9, [rsp+1F8h+var_1B4]
0x180015267  mov     r8b, [rsp+1F8h+arg_20]
0x18001526f  call    WldpIsFileTrustedBySbcp
0x180015274  mov     [rsp+1F8h+var_1B0], eax
0x180015278  mov     edi, eax
0x18001527a  test    eax, eax
0x18001527c  js      short loc_1800152B2
0x18001527e  mov     ebx, [rsp+1F8h+var_1B4]
0x180015282  cmp     ebx, 1
0x180015285  jz      short loc_18001529C
0x180015287  mov     al, r14b
0x18001528a  neg     al
0x18001528c  sbb     ecx, ecx
0x18001528e  and     ecx, 0A60000h
0x180015294  add     ecx, 0D0430002h
0x18001529a  jmp     short loc_18001529E
0x18001529c  xor     ecx, ecx
0x18001529e  mov     [rsp+1F8h+var_134], ecx
0x1800152a5  mov     [rsp+1F8h+var_130], ebx
0x1800152ac  movzx   esi, sil
0x1800152b0  jmp     short loc_1800152CD
0x1800152b2  mov     ecx, edi
0x1800152b4  mov     [rsp+1F8h+var_134], ecx
0x1800152bb  movzx   esi, sil
0x1800152bf  lea     ebx, [rsi+2]
0x1800152c2  mov     [rsp+1F8h+var_130], ebx
0x1800152c9  mov     [rsp+1F8h+var_1B4], ebx
0x1800152cd  mov     eax, ebx
0x1800152cf  test    ecx, ecx
0x1800152d1  js      short loc_180015311
0x1800152d3  cmp     eax, 1
0x1800152d6  jnz     short loc_180015311
0x1800152d8  mov     r8b, [rsp+1F8h+var_1B8]
0x1800152dd  mov     edx, r12d
0x1800152e0  lea     rcx, [rsp+1F8h+var_158]
0x1800152e8  call    WldpCheckSipAgainstHostId
0x1800152ed  mov     edi, eax
0x1800152ef  mov     [rsp+1F8h+var_1B0], eax
0x1800152f3  mov     eax, 80072029h
0x1800152f8  cmp     edi, eax
0x1800152fa  jnz     short loc_180015311
0x1800152fc  mov     [rsp+1F8h+var_134], eax
0x180015303  lea     ebx, [rsi+2]
0x180015306  mov     [rsp+1F8h+var_130], ebx
0x18001530d  mov     [rsp+1F8h+var_1B4], ebx
0x180015311  test    r14b, r14b
0x180015314  jz      loc_18001551B
0x18001531a  lea     rdx, [rsp+1F8h+ActivityId]; ActivityId
0x180015322  mov     ecx, 3; ControlCode
0x180015327  call    cs:__imp_EventActivityIdControl
0x18001532d  mov     rcx, qword ptr [rsp+1F8h+var_1A0]
0x180015332  cmp     rcx, qword ptr [rsp+1F8h+var_1A0+8]
0x180015337  jnz     short loc_180015362
0x180015339  lea     r15, [rsp+1F8h+var_138]
0x180015341  mov     r14, 34F72C234F72C235h
0x18001534b  mov     rax, qword ptr [rsp+1F8h+var_188]
0x180015350  cmp     rax, qword ptr [rsp+1F8h+var_188+8]
0x180015355  jnz     loc_180015496
0x18001535b  xor     ecx, ecx
0x18001535d  jmp     loc_1800154A2
0x180015362  imul    r15, 0E8h
0x180015369  add     r15, rcx
0x18001536c  mov     eax, [rsp+1F8h+var_134]
0x180015373  mov     [r15+4], eax
0x180015377  mov     eax, [rsp+1F8h+var_130]
0x18001537e  mov     [r15+8], eax
0x180015382  mov     eax, [rsp+1F8h+var_12C]
0x180015389  mov     [r15+0Ch], eax
0x18001538d  mov     al, [rsp+1F8h+var_128]
0x180015394  mov     [r15+10h], al
0x180015398  mov     rdx, qword ptr [rsp+1F8h+var_1A0]
0x18001539d  add     rdx, 50h ; 'P'; struct SAC_REPUTATION_EXTRA_INFO_ *
0x1800153a1  mov     rax, [rsp+1F8h+var_1A8]
0x1800153a6  mov     [rsp+1F8h+var_1D8], rax; void *
0x1800153ab  mov     r9d, r12d; unsigned int
0x1800153ae  mov     r8, r13; unsigned __int16 *
0x1800153b1  mov     rcx, r15; struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *
0x1800153b4  call    ?WldpSmartAppControlTelemetryAndToast@@YAXPEAUCONFIG_CI_PROV_INFO_RESULT2_PRIVATE_@@PEAUSAC_REPUTATION_EXTRA_INFO_@@PEBGKQEAX@Z; WldpSmartAppControlTelemetryAndToast(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *,SAC_REPUTATION_EXTRA_INFO_ *,ushort const *,ulong,void * const)
0x1800153b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SAC_LocalLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SAC_LocalLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAC_LocalLogging> `wil::Feature<__WilFeatureTraits_Feature_SAC_LocalLogging>::GetImpl(void)'::`2'::impl
0x1800153c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SAC_LocalLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SAC_LocalLogging>::__private_IsEnabled(void)
0x1800153c5  test    al, al
0x1800153c7  jz      loc_180015341
0x1800153cd  xor     esi, esi
0x1800153cf  mov     [rsp+1F8h+var_168], rsi
0x1800153d7  mov     r14, 34F72C234F72C235h
0x1800153e1  mov     r8, cs:qword_180047BB8
0x1800153e8  mov     r10, cs:qword_180047BB0
0x1800153ef  mov     r9, cs:qword_180047BA8
0x1800153f6  mov     r11, cs:qword_180047BA0
0x1800153fd  mov     rcx, qword ptr [rsp+1F8h+var_1A0]
0x180015402  mov     rax, qword ptr [rsp+1F8h+var_1A0+8]
0x180015407  sub     rax, rcx
0x18001540a  sar     rax, 3
0x18001540e  imul    rax, r14
0x180015412  cmp     rsi, rax
0x180015415  jnb     loc_18001534B
0x18001541b  imul    rax, rsi, 0E8h
0x180015422  add     rcx, rax
0x180015425  mov     rax, [rcx+24h]
0x180015429  sub     rax, r10
0x18001542c  jnz     short loc_180015435
0x18001542e  mov     rax, [rcx+2Ch]
0x180015432  sub     rax, r8
0x180015435  test    rax, rax
0x180015438  setz    dl
0x18001543b  mov     rax, [rcx+24h]
0x18001543f  sub     rax, r11
0x180015442  jnz     short loc_18001544B
0x180015444  mov     rax, [rcx+2Ch]
0x180015448  sub     rax, r9
0x18001544b  test    rax, rax
0x18001544e  setz    al
0x180015451  test    dl, dl
0x180015453  jnz     short loc_180015459
0x180015455  test    al, al
0x180015457  jz      short loc_180015486
0x180015459  mov     r8, r13
0x18001545c  lea     rdx, [rsp+1F8h+ActivityId]
0x180015464  call    cs:__imp_WTLogSmartAppControlDefenderInfo
0x18001546a  mov     r8, cs:qword_180047BB8
0x180015471  mov     r10, cs:qword_180047BB0
0x180015478  mov     r9, cs:qword_180047BA8
0x18001547f  mov     r11, cs:qword_180047BA0
0x180015486  inc     rsi
0x180015489  mov     [rsp+1F8h+var_168], rsi
0x180015491  jmp     loc_1800153FD
0x180015496  mov     rcx, [rsp+1F8h+var_170]
0x18001549e  mov     rcx, [rax+rcx*8]
0x1800154a2  lea     rax, [rsp+1F8h+ActivityId]
0x1800154aa  mov     [rsp+1F8h+var_1C8], rax
0x1800154af  mov     [rsp+1F8h+var_1D0], r15
0x1800154b4  mov     [rsp+1F8h+var_1D8], 0
0x1800154bd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800154c1  mov     r8, r13
0x1800154c4  mov     rdx, [rsp+1F8h+var_1A8]
0x1800154c9  call    cs:__imp_WTLogConfigCiScriptEvent2
0x1800154cf  cmp     [rsp+1F8h+var_130], 1
0x1800154d7  jz      short loc_180015525
0x1800154d9  xor     eax, eax
0x1800154db  xor     esi, esi
0x1800154dd  xor     ecx, ecx
0x1800154df  mov     [rsp+1F8h+var_1A8], rax
0x1800154e4  mov     r10, qword ptr [rsp+1F8h+var_188]
0x1800154e9  mov     r8, qword ptr [rsp+1F8h+var_188+8]
0x1800154ee  sub     r8, r10
0x1800154f1  sar     r8, 3
0x1800154f5  cmp     rsi, r8
0x1800154f8  jnb     short loc_180015525
0x1800154fa  mov     r9d, eax
0x1800154fd  lea     rdx, [rsp+1F8h+ActivityId]
0x180015505  mov     rcx, [r10+rcx*8]
0x180015509  call    cs:__imp_WTLogConfigCiSignerEvent
0x18001550f  lea     rax, [rsi+1]
0x180015513  mov     rsi, rax
0x180015516  mov     rcx, rax
0x180015519  jmp     short loc_1800154DF
0x18001551b  mov     r14, 34F72C234F72C235h
0x180015525  mov     rax, [rsp+1F8h+var_160]
0x18001552d  mov     [rax], ebx
0x18001552f  xor     eax, eax
0x180015531  cmp     [rsp+1F8h+var_1B7], al
0x180015535  cmovnz  edi, eax
0x180015538  mov     rcx, qword ptr [rsp+1F8h+var_188]
0x18001553d  test    rcx, rcx
0x180015540  jz      short loc_18001557A
0x180015542  mov     rdx, qword ptr [rsp+1F8h+var_188+8]
0x180015547  call    std___Destroy_range_std__allocator_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_void___void____cdecl___void____noexcept__WldpFreeStateData_wistd__integral_constant_unsigned___int64_0__void___void___0_std__nullptr_t_________
0x18001554c  mov     rcx, qword ptr [rsp+1F8h+var_188]
0x180015551  mov     rdx, [rsp+1F8h+var_178]
0x180015559  sub     rdx, rcx
0x18001555c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180015560  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015565  xorps   xmm0, xmm0
0x180015568  movdqu  [rsp+1F8h+var_188], xmm0
0x18001556e  mov     [rsp+1F8h+var_178], 0
0x18001557a  mov     rcx, qword ptr [rsp+1F8h+var_1A0]
0x18001557f  test    rcx, rcx
0x180015582  jz      short loc_1800155C1
0x180015584  mov     rdx, qword ptr [rsp+1F8h+var_1A0+8]
0x180015589  call    std___Destroy_range_std__allocator_wil__unique_struct_CONFIG_CI_PROV_INFO_RESULT2_PRIVATE__void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE______WTConfigCiFreePrivateData_void____cdecl___CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_____noexcept__NewProviderData_____
0x18001558e  mov     rcx, qword ptr [rsp+1F8h+var_1A0]
0x180015593  mov     rdx, [rsp+1F8h+var_190]
0x180015598  sub     rdx, rcx
0x18001559b  sar     rdx, 3
0x18001559f  imul    rdx, r14
0x1800155a3  imul    rdx, 0E8h
0x1800155aa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800155af  xorps   xmm0, xmm0
0x1800155b2  movdqu  [rsp+1F8h+var_1A0], xmm0
0x1800155b8  mov     [rsp+1F8h+var_190], 0
0x1800155c1  mov     eax, edi
0x1800155c3  jmp     short loc_1800155C9
0x1800155c5  mov     eax, [rsp+1F8h+var_1B4]
0x1800155c9  mov     rcx, [rsp+1F8h+var_48]
0x1800155d1  xor     rcx, rsp; StackCookie
0x1800155d4  call    __security_check_cookie
0x1800155d9  add     rsp, 1C0h
0x1800155e0  pop     r15
0x1800155e2  pop     r14
0x1800155e4  pop     r13
0x1800155e6  pop     r12
0x1800155e8  pop     rdi
0x1800155e9  pop     rsi
0x1800155ea  pop     rbx
0x1800155eb  retn
```
