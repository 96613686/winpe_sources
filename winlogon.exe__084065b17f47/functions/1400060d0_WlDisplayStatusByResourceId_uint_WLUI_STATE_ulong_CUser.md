# WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)

- ea: `0x1400060d0`
- end: `0x1400064aa`
- name: `?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z`
- size: `986`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004470`
- `0x1400176f8`
- `0x140037a10`
- `0x140044c90`
- `0x140047370`
- `0x14004c400`
- `0x14004ec54`
- `0x140052c20`
- `0x14005bbb8`
- `0x1400619c0`
- `0x1400625d0`
- `0x140065330`
- `0x140065950`
- `0x14006cf20`
- `0x14006e950`
- `0x1400858e0`
- `0x14008a390`

## callees

- `0x1400057f4`
- `0x1400060d0`
- `0x140006970`
- `0x14000fb30`
- `0x1400111ec`
- `0x140041c34`
- `0x14004f03c`
- `0x140050984`
- `0x140055158`
- `0x14005b630`
- `0x14005d714`
- `0x14005f3c4`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400061c2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400061c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1400061d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1400061d2`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1400061e0`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1400061e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000622d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000622d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000621b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000621b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000615e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000615e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006313`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006154`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006188`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006154`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006188`

## pseudocode

```c
__int64 __fastcall WlDisplayStatusByResourceId(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned __int16 v7; // di
  __int64 v8; // r9
  int v9; // esi
  unsigned int v10; // r14d
  void *v11; // rbx
  DWORD v12; // ebp
  DWORD LastError; // eax
  CUser *v14; // rcx
  __int64 v15; // rdx
  void *v16; // rbp
  HRSRC Resource; // rax
  CUser *v18; // rcx
  HGLOBAL v19; // rax
  _WORD *v20; // rax
  _WORD *v21; // rbx
  unsigned __int16 v22; // ax
  char *v23; // rbx
  int i; // edi
  char *v25; // rcx
  size_t v26; // r15
  HANDLE ProcessHeap; // rax
  void *v28; // rax
  HANDLE v29; // rax
  _DWORD v31[8]; // [rsp+30h] [rbp-48h] BYREF

  v7 = a1;
  if ( (unsigned __int8)IsWinLogonExtPresent(a1) )
  {
    v9 = 0;
    v10 = 14;
    if ( !a4 )
      goto LABEL_13;
    if ( NtCurrentTeb()->IsImpersonating )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v8);
      }
LABEL_13:
      v16 = 0;
      Resource = FindResourceExW(0, (LPCWSTR)6, (LPCWSTR)((v7 >> 4) + 1), 0);
      if ( Resource )
      {
        v19 = LoadResource(0, Resource);
        if ( v19 )
        {
          v20 = LockResource(v19);
          v21 = v20;
          if ( v20 )
          {
            v22 = *v20;
            v23 = (char *)(v21 + 1);
            for ( i = v7 & 0xF; i; --i )
            {
              v25 = &v23[2 * v22];
              v22 = *(_WORD *)v25;
              v23 = v25 + 2;
            }
            v26 = 2LL * v22;
            ProcessHeap = GetProcessHeap();
            v28 = HeapAlloc(ProcessHeap, 8u, v26 + 2);
            v16 = v28;
            if ( v28 )
              memcpy_0(v28, v23, v26);
          }
        }
      }
      if ( v9 )
        CUser::StopImpersonating(v18);
      if ( !v16 )
        return v10;
      if ( g_fLaunchedFirstLogonAnimation )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v16);
        }
      }
      else if ( (unsigned __int8)IsWinLogonExtPresent(v18) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(v31, 0);
          v10 = WluiDisplayStatus(v16, a2, a3);
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v31);
        }
        else
        {
          v10 = WluiDisplayStatus(v16, a2, a3);
        }
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
              (_DWORD)v16,
              v10);
          }
        }
        else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v16);
        }
        goto LABEL_26;
      }
      v10 = 0;
LABEL_26:
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v16);
      return v10;
    }
    v11 = *(void **)(a4 + 136);
    v12 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      if ( !ImpersonateLoggedOnUser(v11) )
      {
        LastError = GetLastError();
        v12 = LastError;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 25;
          goto LABEL_37;
        }
LABEL_12:
        LOBYTE(v9) = v12 == 0;
        if ( v12 && v14 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)v14 + 2), 22, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v12);
        goto LABEL_13;
      }
    }
    else if ( !ImpersonateLoggedOnUser(v11) )
    {
      LastError = GetLastError();
      v12 = LastError;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 27;
LABEL_37:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
        goto LABEL_11;
      }
      goto LABEL_12;
    }
LABEL_11:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x1400060d0  push    rbx
0x1400060d2  push    rdi
0x1400060d3  push    r12
0x1400060d5  push    r13
0x1400060d7  sub     rsp, 58h
0x1400060db  mov     rbx, r9
0x1400060de  mov     r12d, r8d
0x1400060e1  mov     r13d, edx
0x1400060e4  mov     edi, ecx
0x1400060e6  call    IsWinLogonExtPresent
0x1400060eb  test    al, al
0x1400060ed  jz      loc_1400062B5
0x1400060f3  mov     [rsp+78h+arg_0], rbp
0x1400060fb  mov     [rsp+78h+arg_8], rsi
0x140006103  xor     esi, esi
0x140006105  mov     [rsp+78h+arg_10], r14
0x14000610d  mov     r14d, 0Eh
0x140006113  mov     [rsp+78h+var_28], r15
0x140006118  lea     r15, WPP_GLOBAL_Control
0x14000611f  test    rbx, rbx
0x140006122  jz      loc_1400061AB
0x140006128  mov     eax, gs:179Ch
0x140006130  test    eax, eax
0x140006132  jnz     loc_1400062D5
0x140006138  mov     rbx, [rbx+88h]
0x14000613f  xor     ebp, ebp
0x140006141  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140006148  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14000614d  mov     rcx, rbx; hToken
0x140006150  test    al, al
0x140006152  jnz     short loc_140006188
0x140006154  call    cs:__imp_ImpersonateLoggedOnUser
0x14000615a  test    eax, eax
0x14000615c  jnz     short loc_140006196
0x14000615e  call    cs:__imp_GetLastError
0x140006164  mov     ebp, eax
0x140006166  mov     rcx, cs:WPP_GLOBAL_Control
0x14000616d  cmp     rcx, r15
0x140006170  jz      short loc_14000619D
0x140006172  test    byte ptr [rcx+1Ch], 20h
0x140006176  jz      short loc_14000619D
0x140006178  cmp     byte ptr [rcx+19h], 2
0x14000617c  jb      short loc_14000619D
0x14000617e  mov     edx, 1Bh
0x140006183  jmp     loc_140006344
0x140006188  call    cs:__imp_ImpersonateLoggedOnUser
0x14000618e  test    eax, eax
0x140006190  jz      loc_140006313
0x140006196  mov     rcx, cs:WPP_GLOBAL_Control
0x14000619d  test    ebp, ebp
0x14000619f  setz    sil
0x1400061a3  test    ebp, ebp
0x1400061a5  jnz     loc_14000635C
0x1400061ab  movzx   r8d, di
0x1400061af  xor     r9d, r9d; wLanguage
0x1400061b2  shr     r8d, 4
0x1400061b6  mov     edx, 6; lpType
0x1400061bb  inc     r8d; lpName
0x1400061be  xor     ecx, ecx; hModule
0x1400061c0  xor     ebp, ebp
0x1400061c2  call    cs:__imp_FindResourceExW
0x1400061c8  test    rax, rax
0x1400061cb  jz      short loc_140006246
0x1400061cd  mov     rdx, rax; hResInfo
0x1400061d0  xor     ecx, ecx; hModule
0x1400061d2  call    cs:__imp_LoadResource
0x1400061d8  test    rax, rax
0x1400061db  jz      short loc_140006246
0x1400061dd  mov     rcx, rax; hResData
0x1400061e0  call    cs:__imp_LockResource
0x1400061e6  mov     rbx, rax
0x1400061e9  test    rax, rax
0x1400061ec  jz      short loc_140006246
0x1400061ee  movzx   eax, word ptr [rax]
0x1400061f1  add     rbx, 2
0x1400061f5  and     edi, 0Fh
0x1400061f8  jz      short loc_140006214
0x1400061fa  nop     word ptr [rax+rax+00h]
0x140006200  movzx   eax, ax
0x140006203  lea     rcx, [rbx+rax*2]
0x140006207  movzx   eax, word ptr [rbx+rax*2]
0x14000620b  lea     rbx, [rcx+2]
0x14000620f  add     edi, 0FFFFFFFFh
0x140006212  jnz     short loc_140006200
0x140006214  movzx   eax, ax
0x140006217  lea     r15, [rax+rax]
0x14000621b  call    cs:__imp_GetProcessHeap
0x140006221  lea     r8, [r15+2]; dwBytes
0x140006225  mov     edx, 8; dwFlags
0x14000622a  mov     rcx, rax; hHeap
0x14000622d  call    cs:__imp_HeapAlloc
0x140006233  mov     rbp, rax
0x140006236  test    rax, rax
0x140006239  jnz     loc_1400062C2
0x14000623f  lea     r15, WPP_GLOBAL_Control
0x140006246  test    esi, esi
0x140006248  mov     rsi, [rsp+78h+arg_8]
0x140006250  jnz     short loc_1400062AE
0x140006252  test    rbp, rbp
0x140006255  jz      short loc_14000628B
0x140006257  cmp     cs:?g_fLaunchedFirstLogonAnimation@@3HA, 0; int g_fLaunchedFirstLogonAnimation
0x14000625e  jz      loc_1400063C7
0x140006264  mov     rcx, cs:WPP_GLOBAL_Control
0x14000626b  cmp     rcx, r15
0x14000626e  jnz     loc_140006396
0x140006274  xor     r14d, r14d
0x140006277  call    cs:__imp_GetProcessHeap
0x14000627d  mov     r8, rbp; lpMem
0x140006280  xor     edx, edx; dwFlags
0x140006282  mov     rcx, rax; hHeap
0x140006285  call    cs:__imp_HeapFree
0x14000628b  mov     r15, [rsp+78h+var_28]
0x140006290  mov     eax, r14d
0x140006293  mov     r14, [rsp+78h+arg_10]
0x14000629b  mov     rbp, [rsp+78h+arg_0]
0x1400062a3  add     rsp, 58h
0x1400062a7  pop     r13
0x1400062a9  pop     r12
0x1400062ab  pop     rdi
0x1400062ac  pop     rbx
0x1400062ad  retn
0x1400062ae  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x1400062b3  jmp     short loc_140006252
0x1400062b5  xor     eax, eax
0x1400062b7  add     rsp, 58h
0x1400062bb  pop     r13
0x1400062bd  pop     r12
0x1400062bf  pop     rdi
0x1400062c0  pop     rbx
0x1400062c1  retn
0x1400062c2  mov     r8, r15; Size
0x1400062c5  mov     rdx, rbx; Src
0x1400062c8  mov     rcx, rax; void *
0x1400062cb  call    memcpy_0
0x1400062d0  jmp     loc_14000623F
0x1400062d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062dc  cmp     rcx, r15
0x1400062df  jz      loc_1400061AB
0x1400062e5  test    byte ptr [rcx+1Ch], 1
0x1400062e9  jz      loc_1400061AB
0x1400062ef  cmp     byte ptr [rcx+19h], 4
0x1400062f3  jb      loc_1400061AB
0x1400062f9  mov     rcx, [rcx+10h]
0x1400062fd  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140006304  mov     edx, 15h
0x140006309  call    WPP_SF_
0x14000630e  jmp     loc_1400061AB
0x140006313  call    cs:__imp_GetLastError
0x140006319  mov     ebp, eax
0x14000631b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006322  cmp     rcx, r15
0x140006325  jz      loc_14000619D
0x14000632b  test    byte ptr [rcx+1Ch], 20h
0x14000632f  jz      loc_14000619D
0x140006335  cmp     byte ptr [rcx+19h], 2
0x140006339  jb      loc_14000619D
0x14000633f  mov     edx, 19h
0x140006344  mov     rcx, [rcx+10h]
0x140006348  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000634f  mov     r9d, eax
0x140006352  call    WPP_SF_d
0x140006357  jmp     loc_140006196
0x14000635c  cmp     rcx, r15
0x14000635f  jz      loc_1400061AB
0x140006365  test    byte ptr [rcx+1Ch], 1
0x140006369  jz      loc_1400061AB
0x14000636f  cmp     byte ptr [rcx+19h], 2
0x140006373  jb      loc_1400061AB
0x140006379  mov     rcx, [rcx+10h]
0x14000637d  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140006384  mov     edx, 16h
0x140006389  mov     r9d, ebp
0x14000638c  call    WPP_SF_d
0x140006391  jmp     loc_1400061AB
0x140006396  test    byte ptr [rcx+1Ch], 1
0x14000639a  jz      loc_140006274
0x1400063a0  cmp     byte ptr [rcx+19h], 2
0x1400063a4  jb      loc_140006274
0x1400063aa  mov     rcx, [rcx+10h]
0x1400063ae  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400063b5  mov     edx, 1Ch
0x1400063ba  mov     r9, rbp
0x1400063bd  call    WPP_SF_S
0x1400063c2  jmp     loc_140006274
0x1400063c7  call    IsWinLogonExtPresent
0x1400063cc  test    al, al
0x1400063ce  jz      loc_140006274
0x1400063d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x1400063db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x1400063e0  test    al, al
0x1400063e2  jz      short loc_14000640D
0x1400063e4  xor     edx, edx
0x1400063e6  lea     rcx, [rsp+78h+var_48]
0x1400063eb  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x1400063f0  mov     r8d, r12d
0x1400063f3  mov     edx, r13d
0x1400063f6  mov     rcx, rbp
0x1400063f9  call    WluiDisplayStatus
0x1400063fe  lea     rcx, [rsp+78h+var_48]; this
0x140006403  mov     r14d, eax
0x140006406  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x14000640b  jmp     short loc_14000641E
0x14000640d  mov     r8d, r12d
0x140006410  mov     edx, r13d
0x140006413  mov     rcx, rbp
0x140006416  call    WluiDisplayStatus
0x14000641b  mov     r14d, eax
0x14000641e  test    r14d, r14d
0x140006421  jz      short loc_140006469
0x140006423  mov     rcx, cs:WPP_GLOBAL_Control
0x14000642a  cmp     rcx, r15
0x14000642d  jz      loc_140006277
0x140006433  test    byte ptr [rcx+1Ch], 1
0x140006437  jz      loc_140006277
0x14000643d  cmp     byte ptr [rcx+19h], 2
0x140006441  jb      loc_140006277
0x140006447  mov     rcx, [rcx+10h]
0x14000644b  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140006452  mov     edx, 1Dh
0x140006457  mov     [rsp+78h+var_58], r14d
0x14000645c  mov     r9, rbp
0x14000645f  call    WPP_SF_SD
0x140006464  jmp     loc_140006277
0x140006469  mov     rcx, cs:WPP_GLOBAL_Control
0x140006470  cmp     rcx, r15
0x140006473  jz      loc_140006277
0x140006479  test    byte ptr [rcx+1Ch], 1
0x14000647d  jz      loc_140006277
0x140006483  cmp     byte ptr [rcx+19h], 4
0x140006487  jb      loc_140006277
0x14000648d  mov     rcx, [rcx+10h]
0x140006491  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140006498  mov     edx, 1Eh
0x14000649d  mov     r9, rbp
0x1400064a0  call    WPP_SF_S
0x1400064a5  jmp     loc_140006277
```
