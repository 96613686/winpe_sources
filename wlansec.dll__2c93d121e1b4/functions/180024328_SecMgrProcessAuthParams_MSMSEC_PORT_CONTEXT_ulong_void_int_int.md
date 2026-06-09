# SecMgrProcessAuthParams(MSMSEC_PORT_CONTEXT *,ulong,void *,int *,int)

- ea: `0x180024328`
- end: `0x1800246a8`
- name: `?SecMgrProcessAuthParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@KPEAXPEAHH@Z`
- size: `896`
- prototype: `unsigned int __usercall@<eax>(struct MSMSEC_PORT_CONTEXT *@<rcx>, unsigned int@<edx>, void *@<r8>, int *@<r9>, int)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180023fc0`
- `0x180073760`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18001057c`
- `0x1800169c0`
- `0x180024328`
- `0x18002d79c`
- `0x18002db40`
- `0x18004456c`
- `0x180057dec`
- `0x18005c738`
- `0x180062824`
- `0x18006b788`
- `0x180071050`

## import_xrefs

- `OneX!OneXCopyAuthParams` at `0x1800243ce`
- `OneX!OneXCopyAuthParams` at `0x1800243ce`
- `MobileNetworking!ReleaseWriteLock` at `0x180024627`
- `MobileNetworking!ReleaseWriteLock` at `0x180024627`
- `MobileNetworking!AcquireWriteLock` at `0x180024465`
- `MobileNetworking!AcquireWriteLock` at `0x180024465`

## pseudocode

```c
__int64 __fastcall SecMgrProcessAuthParams(
        struct MSMSEC_PORT_CONTEXT *a1,
        unsigned int a2,
        _DWORD *a3,
        int *a4,
        int a5)
{
  int v5; // r14d
  int v7; // r12d
  PVOID *v11; // rcx
  unsigned int v12; // eax
  int v13; // edi
  unsigned int v14; // r15d
  __int64 v15; // rdx
  struct DOT11_AUTH_AKM_SUITE *v16; // rdx
  __int64 v17; // r8
  unsigned int v19; // [rsp+50h] [rbp-71h] BYREF
  void *v20; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int8 *v21; // [rsp+60h] [rbp-61h] BYREF
  unsigned __int8 *v22; // [rsp+68h] [rbp-59h] BYREF
  unsigned int v23[4]; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v24[24]; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int16 v25; // [rsp+98h] [rbp-29h]
  struct DOT11_AUTH_AKM_SUITE *v26; // [rsp+A0h] [rbp-21h] BYREF

  v5 = 0;
  v20 = 0;
  v7 = 0;
  v22 = 0;
  v19 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 37, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *a3 )
  {
    v14 = 0;
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 68) & 2) == 0 )
      goto LABEL_43;
    WPP_SF_(v11[7], 41, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
LABEL_42:
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
    *a4 = v7;
    goto LABEL_44;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 68) & 2) != 0 )
    WPP_SF_(v11[7], 38, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids);
  v12 = OneXCopyAuthParams(a2, a3, &v20);
  v13 = 0;
  v14 = v12;
  if ( !v12 )
  {
    SetPortAuthParams(a1, a2, v20);
    TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
    AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrProcessAuthParams", 381);
    v21 = 0;
    memset_0(v24, 0, 0x48u);
    if ( !QueryStationRSNIE(a1, &v21, v23) )
    {
      v12 = IEPRSNParseIE(v21 + 2, v21[1]);
      if ( v12 )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v14;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_44;
        v15 = 40;
        goto LABEL_12;
      }
      v16 = (struct DOT11_AUTH_AKM_SUITE *)&v26;
      if ( v25 > 1u )
        v16 = v26;
      if ( IsFtAkmPresent(v25, v16) && !QueryStationMDDIE(a1, &v22, &v19) && v22 )
        v5 = 1;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_58508574>::GetImpl'::`2'::impl) )
    {
      v17 = *((_QWORD *)a1 + 3);
      if ( *(_BYTE *)(v17 + 3012) )
      {
        SetPMKCacheValid((struct MSMSEC_PMKCACHE_CONTEXT *)(v17 + 3000), 0);
LABEL_38:
        TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
        ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrProcessAuthParams", 469);
        goto LABEL_42;
      }
      if ( *(_DWORD *)(v17 + 2500) )
      {
        v13 = 1;
      }
      else if ( v5 && a5 )
      {
        v13 = 1;
      }
      PmkCacheValidate(
        (struct MSMSEC_PMKCACHE_CONTEXT *)(v17 + 3000),
        (struct MSMSEC_NW_DESC *)(v17 + 2728),
        *(struct DOT11_MSMSEC_CONNECTION_PROFILE **)(v17 + 2784),
        *((_DWORD *)a1 + 164),
        *((void **)a1 + 83),
        (unsigned __int8 (*)[6])((char *)a1 + 302),
        (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 512),
        (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 640),
        v13);
    }
    else
    {
      if ( v5 && a5 )
        v13 = 1;
      PmkCacheValidate(
        (struct MSMSEC_PMKCACHE_CONTEXT *)(*((_QWORD *)a1 + 3) + 3000LL),
        (struct MSMSEC_NW_DESC *)(*((_QWORD *)a1 + 3) + 2728LL),
        *(struct DOT11_MSMSEC_CONNECTION_PROFILE **)(*((_QWORD *)a1 + 3) + 2784LL),
        *((_DWORD *)a1 + 164),
        *((void **)a1 + 83),
        (unsigned __int8 (*)[6])((char *)a1 + 302),
        (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 512),
        (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 640),
        v13);
    }
    v7 = 1;
    goto LABEL_38;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v15 = 39;
LABEL_12:
    WPP_SF_d(v11[7], v15, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v12);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_44:
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 42, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180024328  push    rbp
0x18002432a  push    rbx
0x18002432b  push    rsi
0x18002432c  push    rdi
0x18002432d  push    r12
0x18002432f  push    r13
0x180024331  push    r14
0x180024333  push    r15
0x180024335  lea     rbp, [rsp-17h]
0x18002433a  sub     rsp, 0D8h
0x180024341  xor     r14d, r14d
0x180024344  mov     r13, r9
0x180024347  mov     [rbp+4Fh+var_B8], r14
0x18002434b  mov     r12d, r14d
0x18002434e  mov     [rbp+4Fh+var_A8], r14
0x180024352  mov     rdi, r8
0x180024355  mov     [rbp+4Fh+var_C0], r14d
0x180024359  mov     esi, edx
0x18002435b  mov     rbx, rcx
0x18002435e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024365  lea     rax, WPP_GLOBAL_Control
0x18002436c  cmp     rcx, rax
0x18002436f  jz      short loc_18002439C
0x180024371  test    dword ptr [rcx+44h], 100h
0x180024378  jz      short loc_18002439C
0x18002437a  mov     rcx, [rcx+38h]
0x18002437e  lea     edx, [r14+25h]
0x180024382  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180024389  call    WPP_SF_
0x18002438e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024395  lea     rax, WPP_GLOBAL_Control
0x18002439c  cmp     [rdi], r14d
0x18002439f  jnz     loc_180024635
0x1800243a5  cmp     rcx, rax
0x1800243a8  jz      short loc_1800243C5
0x1800243aa  test    byte ptr [rcx+44h], 2
0x1800243ae  jz      short loc_1800243C5
0x1800243b0  mov     rcx, [rcx+38h]
0x1800243b4  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x1800243bb  mov     edx, 26h ; '&'
0x1800243c0  call    WPP_SF_
0x1800243c5  lea     r8, [rbp+4Fh+var_B8]
0x1800243c9  mov     rdx, rdi
0x1800243cc  mov     ecx, esi
0x1800243ce  call    cs:__imp_OneXCopyAuthParams
0x1800243d5  nop     dword ptr [rax+rax+00h]
0x1800243da  xor     edi, edi
0x1800243dc  mov     r15d, eax
0x1800243df  test    eax, eax
0x1800243e1  jz      short loc_180024429
0x1800243e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243ea  lea     rbx, WPP_GLOBAL_Control
0x1800243f1  cmp     rcx, rbx
0x1800243f4  jz      loc_180024690
0x1800243fa  lea     esi, [rdi+1]
0x1800243fd  test    [rcx+44h], sil
0x180024401  jz      loc_18002466A
0x180024407  lea     edx, [rdi+27h]
0x18002440a  mov     rcx, [rcx+38h]
0x18002440e  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180024415  mov     r9d, eax
0x180024418  call    WPP_SF_d
0x18002441d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024424  jmp     loc_18002466A
0x180024429  mov     r8, [rbp+4Fh+var_B8]; void *
0x18002442d  mov     edx, esi; unsigned int
0x18002442f  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024432  call    ?SetPortAuthParams@@YAXPEAUMSMSEC_PORT_CONTEXT@@KPEAX@Z; SetPortAuthParams(MSMSEC_PORT_CONTEXT *,ulong,void *)
0x180024437  mov     rcx, [rbx+18h]
0x18002443b  lea     rdx, aLocking; ">>> Locking >>>"
0x180024442  mov     ecx, [rcx+9C0h]; unsigned int
0x180024448  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002444d  mov     rcx, [rbx+18h]
0x180024451  lea     r8, aSecmgrprocessa; "SecMgrProcessAuthParams"
0x180024458  mov     r9d, 17Dh
0x18002445e  lea     rdx, [rcx+9D0h]
0x180024465  call    cs:__imp_AcquireWriteLock
0x18002446c  nop     dword ptr [rax+rax+00h]
0x180024471  xor     edx, edx; Val
0x180024473  mov     [rbp+4Fh+var_B0], rdi
0x180024477  lea     rcx, [rbp+4Fh+var_90]; void *
0x18002447b  lea     r8d, [rdx+48h]; Size
0x18002447f  call    memset_0
0x180024484  lea     r8, [rbp+4Fh+var_A0]; unsigned int *
0x180024488  mov     [rbp+4Fh+arg_10], edi
0x18002448b  lea     rdx, [rbp+4Fh+var_B0]; unsigned __int8 **
0x18002448f  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024492  call    ?QueryStationRSNIE@@YAKPEBUMSMSEC_PORT_CONTEXT@@PEAPEAEPEAK@Z; QueryStationRSNIE(MSMSEC_PORT_CONTEXT const *,uchar * *,ulong *)
0x180024497  mov     esi, 1
0x18002449c  test    eax, eax
0x18002449e  jnz     short loc_18002451B
0x1800244a0  mov     rcx, [rbp+4Fh+var_B0]
0x1800244a4  lea     r9, [rbp+4Fh+var_90]
0x1800244a8  lea     r8, [rbp+4Fh+arg_10]
0x1800244ac  movzx   edx, byte ptr [rcx+1]; int
0x1800244b0  add     rcx, 2; unsigned __int8 *
0x1800244b4  call    IEPRSNParseIE
0x1800244b9  test    eax, eax
0x1800244bb  jz      short loc_1800244E6
0x1800244bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244c4  lea     rbx, WPP_GLOBAL_Control
0x1800244cb  cmp     rcx, rbx
0x1800244ce  jz      loc_180024690
0x1800244d4  test    [rcx+44h], sil
0x1800244d8  jz      loc_18002466A
0x1800244de  lea     edx, [rsi+27h]
0x1800244e1  jmp     loc_18002440A
0x1800244e6  movzx   ecx, [rbp+4Fh+var_78]; unsigned __int16
0x1800244ea  lea     rdx, [rbp+4Fh+var_70]
0x1800244ee  cmp     cx, si
0x1800244f1  cmova   rdx, [rbp+4Fh+var_70]; struct DOT11_AUTH_AKM_SUITE *
0x1800244f6  call    ?IsFtAkmPresent@@YA_NGPEAUDOT11_AUTH_AKM_SUITE@@@Z; IsFtAkmPresent(ushort,DOT11_AUTH_AKM_SUITE *)
0x1800244fb  test    al, al
0x1800244fd  jz      short loc_18002451B
0x1800244ff  lea     r8, [rbp+4Fh+var_C0]; unsigned int *
0x180024503  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180024506  lea     rdx, [rbp+4Fh+var_A8]; unsigned __int8 **
0x18002450a  call    ?QueryStationMDDIE@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAPEAEPEAK@Z; QueryStationMDDIE(MSMSEC_PORT_CONTEXT *,uchar * *,ulong *)
0x18002450f  test    eax, eax
0x180024511  jnz     short loc_18002451B
0x180024513  cmp     [rbp+4Fh+var_A8], rdi
0x180024517  cmovnz  r14d, esi
0x18002451b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_58508574@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58508574@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_58508574>::GetImpl(void)'::`2'::impl
0x180024522  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58508574@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58508574>::__private_IsEnabled(void)
0x180024527  xor     ecx, ecx
0x180024529  test    al, al
0x18002452b  jz      short loc_180024592
0x18002452d  mov     r8, [rbx+18h]
0x180024531  lea     r10, [r8+0BB8h]
0x180024538  cmp     [r10+0Ch], cl
0x18002453c  jz      short loc_18002454D
0x18002453e  xor     edx, edx; int
0x180024540  mov     rcx, r10; struct MSMSEC_PMKCACHE_CONTEXT *
0x180024543  call    ?SetPMKCacheValid@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@H@Z; SetPMKCacheValid(MSMSEC_PMKCACHE_CONTEXT *,int)
0x180024548  jmp     loc_1800245F9
0x18002454d  cmp     [r8+9C4h], ecx
0x180024554  jbe     short loc_18002455A
0x180024556  mov     edi, esi
0x180024558  jmp     short loc_180024565
0x18002455a  test    r14d, r14d
0x18002455d  jz      short loc_180024565
0x18002455f  cmp     [rbp+4Fh+arg_20], ecx
0x180024562  cmovnz  edi, esi
0x180024565  mov     [rsp+110h+var_D0], edi
0x180024569  lea     rcx, [rbx+200h]
0x180024570  lea     rax, [rbx+280h]
0x180024577  mov     [rsp+110h+var_D8], rax
0x18002457c  lea     r9, [rbx+12Eh]
0x180024583  mov     [rsp+110h+var_E0], rcx
0x180024588  mov     rcx, r10
0x18002458b  mov     [rsp+110h+var_E8], r9
0x180024590  jmp     short loc_1800245D0
0x180024592  test    r14d, r14d
0x180024595  jz      short loc_18002459D
0x180024597  cmp     [rbp+4Fh+arg_20], ecx
0x18002459a  cmovnz  edi, esi
0x18002459d  mov     r8, [rbx+18h]
0x1800245a1  lea     rax, [rbx+280h]
0x1800245a8  mov     [rsp+110h+var_D0], edi; int
0x1800245ac  lea     r9, [rbx+200h]
0x1800245b3  mov     [rsp+110h+var_D8], rax; struct MSMSEC_RAW_DATA *
0x1800245b8  lea     r10, [rbx+12Eh]
0x1800245bf  mov     [rsp+110h+var_E0], r9; struct MSMSEC_RAW_DATA *
0x1800245c4  lea     rcx, [r8+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x1800245cb  mov     [rsp+110h+var_E8], r10; unsigned __int8 (*)[6]
0x1800245d0  mov     rax, [rbx+298h]
0x1800245d7  lea     rdx, [r8+0AA8h]; struct MSMSEC_NW_DESC *
0x1800245de  mov     r8, [r8+0AE0h]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800245e5  mov     r9d, [rbx+290h]; unsigned int
0x1800245ec  mov     [rsp+110h+var_F0], rax; void *
0x1800245f1  call    ?PmkCacheValidate@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAUMSMSEC_NW_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@KPEAXPEAY05EPEAUMSMSEC_RAW_DATA@@5H@Z; PmkCacheValidate(MSMSEC_PMKCACHE_CONTEXT *,MSMSEC_NW_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong,void *,uchar (*)[6],MSMSEC_RAW_DATA *,MSMSEC_RAW_DATA *,int)
0x1800245f6  mov     r12d, esi
0x1800245f9  mov     rcx, [rbx+18h]
0x1800245fd  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180024604  mov     ecx, [rcx+9C0h]; unsigned int
0x18002460a  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18002460f  mov     rcx, [rbx+18h]
0x180024613  lea     r8, aSecmgrprocessa; "SecMgrProcessAuthParams"
0x18002461a  mov     r9d, 1D5h
0x180024620  lea     rdx, [rcx+9D0h]
0x180024627  call    cs:__imp_ReleaseWriteLock
0x18002462e  nop     dword ptr [rax+rax+00h]
0x180024633  jmp     short loc_180024658
0x180024635  mov     r15d, r14d
0x180024638  cmp     rcx, rax
0x18002463b  jz      short loc_18002465F
0x18002463d  test    byte ptr [rcx+44h], 2
0x180024641  jz      short loc_18002465F
0x180024643  mov     rcx, [rcx+38h]
0x180024647  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x18002464e  mov     edx, 29h ; ')'
0x180024653  call    WPP_SF_
0x180024658  mov     rcx, cs:WPP_GLOBAL_Control
0x18002465f  mov     [r13+0], r12d
0x180024663  lea     rbx, WPP_GLOBAL_Control
0x18002466a  cmp     rcx, rbx
0x18002466d  jz      short loc_180024690
0x18002466f  test    dword ptr [rcx+44h], 100h
0x180024676  jz      short loc_180024690
0x180024678  mov     rcx, [rcx+38h]
0x18002467c  lea     r8, WPP_6b4468b8a73334dd0914b2db0c523d9b_Traceguids
0x180024683  mov     edx, 2Ah ; '*'
0x180024688  mov     r9d, r15d
0x18002468b  call    WPP_SF_d
0x180024690  mov     eax, r15d
0x180024693  add     rsp, 0D8h
0x18002469a  pop     r15
0x18002469c  pop     r14
0x18002469e  pop     r13
0x1800246a0  pop     r12
0x1800246a2  pop     rdi
0x1800246a3  pop     rsi
0x1800246a4  pop     rbx
0x1800246a5  pop     rbp
0x1800246a6  retn
```
