# AllocAndLoadString(uint,CUser *)

- ea: `0x1400064b0`
- end: `0x1400066fb`
- name: `?AllocAndLoadString@@YAPEAGIPEAVCUser@@@Z`
- size: `587`
- prototype: `unsigned __int16 *__fastcall(unsigned int, struct CUser *)`
- caller_count: `21`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015820`
- `0x140018e10`
- `0x140047370`
- `0x14004d23c`
- `0x14005b81c`
- `0x1400647e0`
- `0x1400690d0`
- `0x140069380`
- `0x14006a184`
- `0x14006ae14`
- `0x14006e950`
- `0x140071780`
- `0x140077464`
- `0x140079d50`
- `0x14007f40c`
- `0x14007faa0`
- `0x140081074`
- `0x140084e20`
- `0x1400877f0`
- `0x14008a390`
- `0x14008bb68`

## callees

- `0x1400057f4`
- `0x1400064b0`
- `0x140006970`
- `0x140041c34`
- `0x14004f03c`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140006575`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140006575`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140006589`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140006589`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140006597`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x140006597`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400065ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400065ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400065db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000650f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000650f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006678`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006505`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006539`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006505`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140006539`

## pseudocode

```c
unsigned __int16 *__fastcall AllocAndLoadString(unsigned __int16 a1, struct CUser *a2)
{
  BOOL v2; // esi
  void *v4; // rsi
  DWORD v5; // ebx
  DWORD LastError; // eax
  CUser *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rbp
  HRSRC Resource; // rax
  CUser *v11; // rcx
  HGLOBAL v12; // rax
  _WORD *v13; // rax
  _WORD *v14; // rbx
  unsigned __int16 v15; // ax
  char *v16; // rbx
  int i; // edi
  char *v18; // rcx
  size_t v19; // r14
  HANDLE ProcessHeap; // rax
  void *v21; // rax

  v2 = 0;
  if ( !a2 )
    goto LABEL_12;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
    v4 = (void *)*((_QWORD *)a2 + 17);
    v5 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      if ( !ImpersonateLoggedOnUser(v4) )
      {
        LastError = GetLastError();
        v5 = LastError;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 25;
          goto LABEL_30;
        }
LABEL_11:
        v2 = v5 == 0;
        if ( v5 && v7 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)v7 + 2), 22, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v5);
        goto LABEL_12;
      }
    }
    else if ( !ImpersonateLoggedOnUser(v4) )
    {
      LastError = GetLastError();
      v5 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 27;
LABEL_30:
        WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
        goto LABEL_10;
      }
      goto LABEL_11;
    }
LABEL_10:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids);
  }
LABEL_12:
  v9 = 0;
  Resource = FindResourceExW(0, (LPCWSTR)6, (LPCWSTR)((a1 >> 4) + 1), 0);
  if ( Resource )
  {
    v12 = LoadResource(0, Resource);
    if ( v12 )
    {
      v13 = LockResource(v12);
      v14 = v13;
      if ( v13 )
      {
        v15 = *v13;
        v16 = (char *)(v14 + 1);
        for ( i = a1 & 0xF; i; --i )
        {
          v18 = &v16[2 * v15];
          v15 = *(_WORD *)v18;
          v16 = v18 + 2;
        }
        v19 = 2LL * v15;
        ProcessHeap = GetProcessHeap();
        v21 = HeapAlloc(ProcessHeap, 8u, v19 + 2);
        v9 = v21;
        if ( v21 )
          memcpy_0(v21, v16, v19);
      }
    }
  }
  if ( v2 )
    CUser::StopImpersonating(v11);
  return (unsigned __int16 *)v9;
}

```

## disassembly

```asm
0x1400064b0  push    rbp
0x1400064b2  sub     rsp, 20h
0x1400064b6  mov     [rsp+28h+arg_0], rbx
0x1400064bb  mov     [rsp+28h+arg_8], rsi
0x1400064c0  xor     esi, esi
0x1400064c2  mov     [rsp+28h+arg_10], rdi
0x1400064c7  mov     edi, ecx
0x1400064c9  test    rdx, rdx
0x1400064cc  jz      loc_14000655E
0x1400064d2  mov     eax, gs:179Ch
0x1400064da  test    eax, eax
0x1400064dc  jnz     loc_140006633
0x1400064e2  mov     rsi, [rdx+88h]
0x1400064e9  xor     ebx, ebx
0x1400064eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1400064f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1400064f7  lea     rbp, WPP_GLOBAL_Control
0x1400064fe  mov     rcx, rsi; hToken
0x140006501  test    al, al
0x140006503  jnz     short loc_140006539
0x140006505  call    cs:__imp_ImpersonateLoggedOnUser
0x14000650b  test    eax, eax
0x14000650d  jnz     short loc_140006547
0x14000650f  call    cs:__imp_GetLastError
0x140006515  mov     ebx, eax
0x140006517  mov     rcx, cs:WPP_GLOBAL_Control
0x14000651e  cmp     rcx, rbp
0x140006521  jz      short loc_14000654E
0x140006523  test    byte ptr [rcx+1Ch], 20h
0x140006527  jz      short loc_14000654E
0x140006529  cmp     byte ptr [rcx+19h], 2
0x14000652d  jb      short loc_14000654E
0x14000652f  mov     edx, 1Bh
0x140006534  jmp     loc_1400066A9
0x140006539  call    cs:__imp_ImpersonateLoggedOnUser
0x14000653f  test    eax, eax
0x140006541  jz      loc_140006678
0x140006547  mov     rcx, cs:WPP_GLOBAL_Control
0x14000654e  xor     esi, esi
0x140006550  test    ebx, ebx
0x140006552  setz    sil
0x140006556  test    ebx, ebx
0x140006558  jnz     loc_1400066C1
0x14000655e  movzx   r8d, di
0x140006562  xor     r9d, r9d; wLanguage
0x140006565  shr     r8d, 4
0x140006569  mov     edx, 6; lpType
0x14000656e  inc     r8d; lpName
0x140006571  xor     ecx, ecx; hModule
0x140006573  xor     ebp, ebp
0x140006575  call    cs:__imp_FindResourceExW
0x14000657b  test    rax, rax
0x14000657e  jz      loc_140006600
0x140006584  mov     rdx, rax; hResInfo
0x140006587  xor     ecx, ecx; hModule
0x140006589  call    cs:__imp_LoadResource
0x14000658f  test    rax, rax
0x140006592  jz      short loc_140006600
0x140006594  mov     rcx, rax; hResData
0x140006597  call    cs:__imp_LockResource
0x14000659d  mov     rbx, rax
0x1400065a0  test    rax, rax
0x1400065a3  jz      short loc_140006600
0x1400065a5  movzx   eax, word ptr [rax]
0x1400065a8  add     rbx, 2
0x1400065ac  mov     [rsp+28h+arg_18], r14
0x1400065b1  and     edi, 0Fh
0x1400065b4  jz      short loc_1400065D4
0x1400065b6  nop     word ptr [rax+rax+00000000h]
0x1400065c0  movzx   eax, ax
0x1400065c3  lea     rcx, [rbx+rax*2]
0x1400065c7  movzx   eax, word ptr [rbx+rax*2]
0x1400065cb  lea     rbx, [rcx+2]
0x1400065cf  add     edi, 0FFFFFFFFh
0x1400065d2  jnz     short loc_1400065C0
0x1400065d4  movzx   eax, ax
0x1400065d7  lea     r14, [rax+rax]
0x1400065db  call    cs:__imp_GetProcessHeap
0x1400065e1  lea     r8, [r14+2]; dwBytes
0x1400065e5  mov     edx, 8; dwFlags
0x1400065ea  mov     rcx, rax; hHeap
0x1400065ed  call    cs:__imp_HeapAlloc
0x1400065f3  mov     rbp, rax
0x1400065f6  test    rax, rax
0x1400065f9  jnz     short loc_140006623
0x1400065fb  mov     r14, [rsp+28h+arg_18]
0x140006600  mov     rdi, [rsp+28h+arg_10]
0x140006605  test    esi, esi
0x140006607  mov     rsi, [rsp+28h+arg_8]
0x14000660c  mov     rbx, [rsp+28h+arg_0]
0x140006611  jnz     short loc_14000661C
0x140006613  mov     rax, rbp
0x140006616  add     rsp, 20h
0x14000661a  pop     rbp
0x14000661b  retn
0x14000661c  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x140006621  jmp     short loc_140006613
0x140006623  mov     r8, r14; Size
0x140006626  mov     rdx, rbx; Src
0x140006629  mov     rcx, rax; void *
0x14000662c  call    memcpy_0
0x140006631  jmp     short loc_1400065FB
0x140006633  mov     rcx, cs:WPP_GLOBAL_Control
0x14000663a  lea     rbp, WPP_GLOBAL_Control
0x140006641  cmp     rcx, rbp
0x140006644  jz      loc_14000655E
0x14000664a  test    byte ptr [rcx+1Ch], 1
0x14000664e  jz      loc_14000655E
0x140006654  cmp     byte ptr [rcx+19h], 4
0x140006658  jb      loc_14000655E
0x14000665e  mov     rcx, [rcx+10h]
0x140006662  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x140006669  mov     edx, 15h
0x14000666e  call    WPP_SF_
0x140006673  jmp     loc_14000655E
0x140006678  call    cs:__imp_GetLastError
0x14000667e  mov     ebx, eax
0x140006680  mov     rcx, cs:WPP_GLOBAL_Control
0x140006687  cmp     rcx, rbp
0x14000668a  jz      loc_14000654E
0x140006690  test    byte ptr [rcx+1Ch], 20h
0x140006694  jz      loc_14000654E
0x14000669a  cmp     byte ptr [rcx+19h], 2
0x14000669e  jb      loc_14000654E
0x1400066a4  mov     edx, 19h
0x1400066a9  mov     rcx, [rcx+10h]
0x1400066ad  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400066b4  mov     r9d, eax
0x1400066b7  call    WPP_SF_d
0x1400066bc  jmp     loc_140006547
0x1400066c1  cmp     rcx, rbp
0x1400066c4  jz      loc_14000655E
0x1400066ca  test    byte ptr [rcx+1Ch], 1
0x1400066ce  jz      loc_14000655E
0x1400066d4  cmp     byte ptr [rcx+19h], 2
0x1400066d8  jb      loc_14000655E
0x1400066de  mov     rcx, [rcx+10h]
0x1400066e2  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x1400066e9  mov     edx, 16h
0x1400066ee  mov     r9d, ebx
0x1400066f1  call    WPP_SF_d
0x1400066f6  jmp     loc_14000655E
```
