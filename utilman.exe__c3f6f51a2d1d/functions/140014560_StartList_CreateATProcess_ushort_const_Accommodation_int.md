# StartList::CreateATProcess(ushort const *,Accommodation *,int)

- ea: `0x140014560`
- end: `0x14001483d`
- name: `?CreateATProcess@StartList@@AEAAJPEBGPEAVAccommodation@@H@Z`
- size: `733`
- prototype: `int(StartList *__hidden this, const unsigned __int16 *, struct Accommodation *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400172b0`
- `0x1400178a4`

## callees

- `0x140002480`
- `0x1400088cc`
- `0x140013fdc`
- `0x140014560`
- `0x140017a8c`
- `0x140018010`
- `0x140018130`
- `0x14001cb14`
- `0x14001cb68`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001464e`
- `KERNEL32!GetLastError` at `0x14001464e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001463c`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001463c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014618`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001466c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014685`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400147b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400147e7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014618`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001466c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014685`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400147b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400147e7`
- `SHELL32!ShellExecuteW` at `0x14001475d`
- `SHELL32!ShellExecuteW` at `0x14001475d`

## string_xrefs

- `0x1400146c0`: `/launchnarratorupdates`
- `0x1400145a5`: `StartList::CreateATProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateATProcess(StartList *this, const unsigned __int16 *a2, struct Accommodation *a3)
{
  unsigned __int64 v5; // rdx
  const unsigned __int16 *v6; // r15
  char *v7; // rsi
  int v8; // edi
  void *v9; // rbx
  DWORD v10; // eax
  signed int LastError; // eax
  char IsEnabled; // al
  const unsigned __int16 *v13; // r9
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rdx
  const wchar_t *v16; // rax
  HINSTANCE v17; // rsi
  int v18; // r8d
  char *v19; // rsi
  char *v20; // rsi
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Parameters[256]; // [rsp+60h] [rbp-A0h] BYREF

  v23 = 0;
  _Trace::_Trace((_Trace *)v24, L"StartList::CreateATProcess", &v23);
  if ( a2 && *a2 )
  {
    v6 = (const unsigned __int16 *)*((_QWORD *)a3 + 4);
    Block = 0;
    if ( (int)StringCchLengthW(a2, v5, (unsigned __int64 *)&Block) < 0 )
      goto LABEL_39;
    v7 = (char *)Block + 260;
    if ( (char *)Block + 260 < Block )
      goto LABEL_39;
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v7) )
    {
      free(Block);
      v8 = -2147024882;
LABEL_40:
      _Trace::~_Trace((_Trace *)v24);
      return (unsigned int)v8;
    }
    v9 = Block;
    v10 = ExpandEnvironmentStringsW(a2, (LPWSTR)Block, (DWORD)v7);
    v8 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError <= 0 )
      {
LABEL_11:
        free(v9);
        goto LABEL_40;
      }
      v8 = (unsigned __int16)LastError;
LABEL_10:
      v8 |= 0x80070000;
      goto LABEL_11;
    }
    if ( v10 > (unsigned __int64)v7 )
    {
      free(v9);
      v8 = -2147024774;
      goto LABEL_40;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
    v13 = &qword_14002C590;
    v14 = L"/launchnarratorhome";
    v15 = L"/hardwarebuttonlaunch";
    if ( IsEnabled )
    {
      v16 = L"/launchnarratorupdates";
      if ( !*((_BYTE *)a3 + 86) )
        v16 = &qword_14002C590;
      if ( !*((_BYTE *)a3 + 85) )
        v14 = &qword_14002C590;
      if ( !*((_BYTE *)a3 + 84) )
        v15 = &qword_14002C590;
      if ( v6 )
        v13 = v6;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s %s", v13, v15, v14, v16);
    }
    else
    {
      if ( !*((_BYTE *)a3 + 85) )
        v14 = &qword_14002C590;
      if ( !*((_BYTE *)a3 + 84) )
        v15 = &qword_14002C590;
      if ( v6 )
        v13 = v6;
      StringCchPrintfW(Parameters, 0x100u, L"%s %s %s", v13, v15, v14);
    }
    v17 = ShellExecuteW(0, 0, (LPCWSTR)v9, Parameters, 0, 5);
    if ( (__int64)v17 <= 32 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v18, (_DWORD)v9, (char)v17);
      v19 = (char *)v17 - 2;
      if ( !v19 || (v20 = v19 - 1) == 0 || v20 == (char *)8 )
      {
        if ( v8 <= 0 )
          goto LABEL_11;
        v8 = (unsigned __int16)v8;
        goto LABEL_10;
      }
      free(v9);
LABEL_39:
      v8 = -2147467259;
      goto LABEL_40;
    }
    free(v9);
    _Trace::~_Trace((_Trace *)v24);
    return 0;
  }
  else
  {
    _Trace::~_Trace((_Trace *)v24);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140014560  mov     [rsp-8+arg_0], rbx
0x140014565  mov     [rsp-8+arg_18], rsi
0x14001456a  push    rbp
0x14001456b  push    rdi
0x14001456c  push    r12
0x14001456e  push    r14
0x140014570  push    r15
0x140014572  lea     rbp, [rsp-170h]
0x14001457a  sub     rsp, 270h
0x140014581  mov     rax, cs:__security_cookie
0x140014588  xor     rax, rsp
0x14001458b  mov     [rbp+190h+var_30], rax
0x140014592  mov     r14, r8
0x140014595  mov     rdi, rdx
0x140014598  xor     r12d, r12d
0x14001459b  mov     [rsp+290h+var_248], r12d
0x1400145a0  lea     r8, [rsp+290h+var_248]; int *
0x1400145a5  lea     rdx, aStartlistCreat; "StartList::CreateATProcess"
0x1400145ac  lea     rcx, [rsp+290h+var_240]; this
0x1400145b1  call    ??0_Trace@@QEAA@PEBGPEAJ@Z; _Trace::_Trace(ushort const *,long *)
0x1400145b6  nop
0x1400145b7  test    rdi, rdi
0x1400145ba  jz      loc_140014802
0x1400145c0  cmp     [rdi], r12w
0x1400145c4  jz      loc_140014802
0x1400145ca  mov     r15, [r14+20h]
0x1400145ce  mov     [rsp+290h+Block], r12
0x1400145d3  lea     r8, [rsp+290h+Block]; unsigned __int64 *
0x1400145d8  mov     rcx, rdi; unsigned __int16 *
0x1400145db  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400145e0  test    eax, eax
0x1400145e2  js      loc_1400147C1
0x1400145e8  mov     rax, [rsp+290h+Block]
0x1400145ed  lea     rsi, [rax+104h]
0x1400145f4  cmp     rsi, rax
0x1400145f7  jb      loc_1400147C1
0x1400145fd  mov     [rsp+290h+Block], r12
0x140014602  mov     rdx, rsi
0x140014605  lea     rcx, [rsp+290h+Block]
0x14001460a  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001460f  test    al, al
0x140014611  jnz     short loc_14001462E
0x140014613  mov     rcx, [rsp+290h+Block]; Block
0x140014618  call    cs:__imp_free
0x14001461f  nop     dword ptr [rax+rax+00h]
0x140014624  mov     edi, 8007000Eh
0x140014629  jmp     loc_1400147C6
0x14001462e  mov     r8d, esi; nSize
0x140014631  mov     rbx, [rsp+290h+Block]
0x140014636  mov     rdx, rbx; lpDst
0x140014639  mov     rcx, rdi; lpSrc
0x14001463c  call    cs:__imp_ExpandEnvironmentStringsW
0x140014643  nop     dword ptr [rax+rax+00h]
0x140014648  mov     edi, eax
0x14001464a  test    eax, eax
0x14001464c  jnz     short loc_14001467D
0x14001464e  call    cs:__imp_GetLastError
0x140014655  nop     dword ptr [rax+rax+00h]
0x14001465a  mov     edi, eax
0x14001465c  test    eax, eax
0x14001465e  jle     short loc_140014669
0x140014660  movzx   edi, ax
0x140014663  or      edi, 80070000h
0x140014669  mov     rcx, rbx; Block
0x14001466c  call    cs:__imp_free
0x140014673  nop     dword ptr [rax+rax+00h]
0x140014678  jmp     loc_1400147C6
0x14001467d  cmp     rdi, rsi
0x140014680  jbe     short loc_14001469B
0x140014682  mov     rcx, rbx; Block
0x140014685  call    cs:__imp_free
0x14001468c  nop     dword ptr [rax+rax+00h]
0x140014691  mov     edi, 8007007Ah
0x140014696  jmp     loc_1400147C6
0x14001469b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x1400146a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x1400146a7  lea     r9, qword_14002C590
0x1400146ae  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x1400146b5  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1400146bc  test    al, al
0x1400146be  jz      short loc_14001470D
0x1400146c0  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x1400146c7  cmp     [r14+56h], r12b
0x1400146cb  cmovz   rax, r9
0x1400146cf  cmp     [r14+55h], r12b
0x1400146d3  cmovz   rcx, r9
0x1400146d7  cmp     [r14+54h], r12b
0x1400146db  cmovz   rdx, r9
0x1400146df  test    r15, r15
0x1400146e2  cmovnz  r9, r15
0x1400146e6  mov     [rsp+290h+var_260], rax
0x1400146eb  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x1400146f0  mov     [rsp+290h+lpDirectory], rdx
0x1400146f5  lea     r8, aSSSS; "%s %s %s %s"
0x1400146fc  mov     edx, 100h; unsigned __int64
0x140014701  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x140014706  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001470b  jmp     short loc_140014744
0x14001470d  cmp     [r14+55h], r12b
0x140014711  cmovz   rcx, r9
0x140014715  cmp     [r14+54h], r12b
0x140014719  cmovz   rdx, r9
0x14001471d  test    r15, r15
0x140014720  cmovnz  r9, r15
0x140014724  mov     qword ptr [rsp+290h+nShowCmd], rcx
0x140014729  mov     [rsp+290h+lpDirectory], rdx
0x14001472e  lea     r8, aSSS; "%s %s %s"
0x140014735  mov     edx, 100h; unsigned __int64
0x14001473a  lea     rcx, [rsp+290h+Parameters]; unsigned __int16 *
0x14001473f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014744  mov     [rsp+290h+nShowCmd], 5; nShowCmd
0x14001474c  mov     [rsp+290h+lpDirectory], r12; lpDirectory
0x140014751  lea     r9, [rsp+290h+Parameters]; lpParameters
0x140014756  mov     r8, rbx; lpFile
0x140014759  xor     edx, edx; lpOperation
0x14001475b  xor     ecx, ecx; hwnd
0x14001475d  call    cs:__imp_ShellExecuteW
0x140014764  nop     dword ptr [rax+rax+00h]
0x140014769  mov     rsi, rax
0x14001476c  cmp     rax, 20h ; ' '
0x140014770  jg      short loc_1400147E4
0x140014772  lea     rax, WPP_GLOBAL_Control
0x140014779  mov     rcx, cs:WPP_GLOBAL_Control
0x140014780  cmp     rcx, rax
0x140014783  jz      short loc_1400147A0
0x140014785  test    byte ptr [rcx+1Ch], 8
0x140014789  jz      short loc_1400147A0
0x14001478b  mov     edx, 1Eh
0x140014790  mov     dword ptr [rsp+290h+lpDirectory], esi
0x140014794  mov     r9, rbx
0x140014797  mov     rcx, [rcx+10h]
0x14001479b  call    WPP_SF_Sd
0x1400147a0  sub     rsi, 2
0x1400147a4  jz      short loc_1400147D4
0x1400147a6  sub     rsi, 1
0x1400147aa  jz      short loc_1400147D4
0x1400147ac  cmp     rsi, 8
0x1400147b0  jz      short loc_1400147D4
0x1400147b2  mov     rcx, rbx; Block
0x1400147b5  call    cs:__imp_free
0x1400147bc  nop     dword ptr [rax+rax+00h]
0x1400147c1  mov     edi, 80004005h
0x1400147c6  lea     rcx, [rsp+290h+var_240]; this
0x1400147cb  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x1400147d0  mov     eax, edi
0x1400147d2  jmp     short loc_140014811
0x1400147d4  test    edi, edi
0x1400147d6  jle     loc_140014669
0x1400147dc  movzx   edi, di
0x1400147df  jmp     loc_140014663
0x1400147e4  mov     rcx, rbx; Block
0x1400147e7  call    cs:__imp_free
0x1400147ee  nop     dword ptr [rax+rax+00h]
0x1400147f3  nop
0x1400147f4  lea     rcx, [rsp+290h+var_240]; this
0x1400147f9  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x1400147fe  xor     eax, eax
0x140014800  jmp     short loc_140014811
0x140014802  lea     rcx, [rsp+290h+var_240]; this
0x140014807  call    ??1_Trace@@QEAA@XZ; _Trace::~_Trace(void)
0x14001480c  mov     eax, 80070057h
0x140014811  mov     rcx, [rbp+190h+var_30]
0x140014818  xor     rcx, rsp; StackCookie
0x14001481b  call    __security_check_cookie
0x140014820  lea     r11, [rsp+290h+var_20]
0x140014828  mov     rbx, [r11+30h]
0x14001482c  mov     rsi, [r11+48h]
0x140014830  mov     rsp, r11
0x140014833  pop     r15
0x140014835  pop     r14
0x140014837  pop     r12
0x140014839  pop     rdi
0x14001483a  pop     rbp
0x14001483b  retn
```
