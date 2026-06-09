# CWindowList::RegisterThumbnail(ulong,MILCMD_DWM_REDIRECTION_REGISTERTHUMBNAIL *)

- ea: `0x1800deb78`
- end: `0x1800def3d`
- name: `?RegisterThumbnail@CWindowList@@AEAAJKPEAUMILCMD_DWM_REDIRECTION_REGISTERTHUMBNAIL@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(CWindowList *this, int, struct MILCMD_DWM_REDIRECTION_REGISTERTHUMBNAIL *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800dd67c`

## callees

- `0x18001cec0`
- `0x18001f43c`
- `0x1800227dc`
- `0x180044e30`
- `0x180066e74`
- `0x180083a34`
- `0x18008a200`
- `0x1800deb78`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800deba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800deba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dec1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dec1b`
- `USER32!GetWindowThreadProcessId` at `0x1800debf0`
- `USER32!GetWindowThreadProcessId` at `0x1800debf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CWindowList::RegisterThumbnail(
        CWindowList *this,
        int a2,
        struct MILCMD_DWM_REDIRECTION_REGISTERTHUMBNAIL *a3)
{
  struct CWindowData *v6; // rsi
  struct CWindowData *v7; // rdi
  bool IsBaseThumbnailDestinationReachable; // al
  char *v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r8d
  int v12; // edi
  unsigned int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r8d
  int v17; // edi
  unsigned int v18; // eax
  int v19; // eax
  char *v20; // r10
  __int64 v21; // rax
  unsigned int v22; // r8d
  int v23; // edi
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // r9d
  unsigned int v29; // [rsp+20h] [rbp-20h]
  struct CWindowData *v30; // [rsp+30h] [rbp-10h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+38h] [rbp-8h] BYREF
  DWORD dwProcessId; // [rsp+80h] [rbp+40h] BYREF
  struct CWindowData *v33; // [rsp+88h] [rbp+48h] BYREF

  v31 = &CDesktopManager::s_csDwmInstance;
  EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
  v33 = 0;
  v30 = 0;
  CWindowList::GetSyncedWindowDataByHwnd(this, *(HWND *)((char *)a3 + 12), &v33);
  CWindowList::GetSyncedWindowDataByHwnd(this, *(HWND *)((char *)a3 + 20), &v30);
  dwProcessId = 0;
  v6 = v33;
  if ( !v33
    || !GetWindowThreadProcessId(*((HWND *)v33 + 5), &dwProcessId)
    || (v7 = v30) == 0
    || a2 != dwProcessId
    || *((_DWORD *)a3 + 7) && a2 != GetCurrentProcessId()
    || (*((_QWORD *)this + 52) = v6,
        IsBaseThumbnailDestinationReachable = CWindowList::IsBaseThumbnailDestinationReachable(this, v7),
        *((_QWORD *)this + 52) = 0,
        IsBaseThumbnailDestinationReachable) )
  {
    v13 = -2147024809;
    goto LABEL_42;
  }
  v9 = (char *)operator new(0x60u);
  if ( !v9 )
  {
    v33 = 0;
    v13 = -2147024882;
    v29 = 4634;
    goto LABEL_38;
  }
  *(_QWORD *)v9 = &CThumbnailData::`vftable';
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_DWORD *)v9 + 8) = 0;
  *(_OWORD *)(v9 + 36) = 0;
  *(_OWORD *)(v9 + 52) = 0;
  *(_OWORD *)(v9 + 65) = 0;
  *((_QWORD *)v9 + 11) = 0;
  v33 = (struct CWindowData *)v9;
  *((_QWORD *)v9 + 1) = *(_QWORD *)((char *)a3 + 4);
  *((_QWORD *)v33 + 2) = v6;
  *((_QWORD *)v33 + 3) = v7;
  *((_BYTE *)v33 + 32) = *((_DWORD *)a3 + 7) != 0;
  *((_BYTE *)v33 + 33) = *((_DWORD *)a3 + 8) != 0;
  *((_BYTE *)v33 + 34) = 0;
  v10 = *((_DWORD *)this + 102);
  v11 = v10 + 1;
  if ( v10 + 1 < v10 )
  {
    v12 = -2147024362;
    v13 = -2147024362;
    v14 = 183;
LABEL_17:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v12, v14, 0);
    v29 = 4643;
LABEL_38:
    v27 = v13;
    goto LABEL_39;
  }
  if ( v11 > *((_DWORD *)this + 101) )
  {
    v19 = DynArrayImpl<0>::AddMultipleAndSet((char *)this + 384, 8, 1, &v33);
    v13 = v19;
    if ( v19 < 0 )
    {
      v12 = v19;
      v14 = 194;
      goto LABEL_17;
    }
  }
  else
  {
    *(_QWORD *)(*((_QWORD *)this + 48) + 8LL * *((unsigned int *)this + 102)) = v33;
    *((_DWORD *)this + 102) = v11;
  }
  v15 = *((_DWORD *)v6 + 140);
  v16 = v15 + 1;
  if ( v15 + 1 < v15 )
  {
    v17 = -2147024362;
    v13 = -2147024362;
    v18 = 183;
LABEL_24:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v17, v18, 0);
    v29 = 4650;
    goto LABEL_38;
  }
  if ( v16 > *((_DWORD *)v6 + 139) )
  {
    v25 = DynArrayImpl<0>::AddMultipleAndSet((char *)v6 + 536, 8, 1, &v33);
    v13 = v25;
    if ( v25 < 0 )
    {
      v17 = v25;
      v18 = 194;
      goto LABEL_24;
    }
  }
  else
  {
    *(_QWORD *)(*((_QWORD *)v6 + 67) + 8LL * *((unsigned int *)v6 + 140)) = v33;
    *((_DWORD *)v6 + 140) = v16;
  }
  v20 = (char *)v7 + 568;
  v21 = *((unsigned int *)v7 + 148);
  v22 = v21 + 1;
  if ( (int)v21 + 1 < (unsigned int)v21 )
  {
    v23 = -2147024362;
    v24 = 183;
LABEL_33:
    v13 = v23;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, v24, 0);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v23, 0x122Bu, 0);
    goto LABEL_42;
  }
  if ( v22 > *((_DWORD *)v7 + 147) )
  {
    v23 = DynArrayImpl<0>::AddMultipleAndSet((char *)v7 + 568, 8, 1, &v33);
    if ( v23 < 0 )
    {
      v24 = 194;
      goto LABEL_33;
    }
  }
  else
  {
    v23 = 0;
    *(_QWORD *)(*(_QWORD *)v20 + 8 * v21) = v33;
    *((_DWORD *)v20 + 6) = v22;
  }
  if ( !*((_QWORD *)v6 + 55) )
  {
    v13 = v23;
    goto LABEL_42;
  }
  v26 = (*(__int64 (__fastcall **)(struct CWindowData *))(*(_QWORD *)v33 + 8LL))(v33);
  v13 = v26;
  if ( v26 < 0 )
  {
    v29 = 4659;
    goto LABEL_35;
  }
  v26 = CTopLevelWindow::OnThumbnailAdded(*((CTopLevelWindow **)v6 + 55), *((struct CVisual **)v33 + 11));
  v13 = v26;
  if ( v26 < 0 )
  {
    v29 = 4661;
LABEL_35:
    v27 = v26;
LABEL_39:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v27, v29, 0);
  }
LABEL_42:
  CGuard<CDwmCS>::~CGuard<CDwmCS>(&v31);
  return v13;
}

```

## disassembly

```asm
0x1800deb78  mov     [rsp-28h+arg_0], rbx
0x1800deb7d  mov     [rsp-28h+arg_8], rsi
0x1800deb82  push    rbp
0x1800deb83  push    rdi
0x1800deb84  push    r12
0x1800deb86  push    r14
0x1800deb88  push    r15
0x1800deb8a  mov     rbp, rsp
0x1800deb8d  sub     rsp, 40h
0x1800deb91  mov     r14, r8
0x1800deb94  mov     r15d, edx
0x1800deb97  mov     rbx, rcx
0x1800deb9a  lea     rcx, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; lpCriticalSection
0x1800deba1  mov     [rbp+var_8], rcx
0x1800deba5  call    cs:__imp_EnterCriticalSection
0x1800debab  nop
0x1800debac  xor     r12d, r12d
0x1800debaf  mov     [rbp+arg_18], r12
0x1800debb3  mov     [rbp+var_10], r12
0x1800debb7  lea     r8, [rbp+arg_18]; struct CWindowData **
0x1800debbb  mov     rdx, [r14+0Ch]; HWND
0x1800debbf  mov     rcx, rbx; this
0x1800debc2  call    ?GetSyncedWindowDataByHwnd@CWindowList@@QEAAXPEAUHWND__@@PEAPEAVCWindowData@@@Z; CWindowList::GetSyncedWindowDataByHwnd(HWND__ *,CWindowData * *)
0x1800debc7  lea     r8, [rbp+var_10]; struct CWindowData **
0x1800debcb  mov     rdx, [r14+14h]; HWND
0x1800debcf  mov     rcx, rbx; this
0x1800debd2  call    ?GetSyncedWindowDataByHwnd@CWindowList@@QEAAXPEAUHWND__@@PEAPEAVCWindowData@@@Z; CWindowList::GetSyncedWindowDataByHwnd(HWND__ *,CWindowData * *)
0x1800debd7  mov     [rbp+dwProcessId], r12d
0x1800debdb  mov     rsi, [rbp+arg_18]
0x1800debdf  test    rsi, rsi
0x1800debe2  jz      loc_1800DEF16
0x1800debe8  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800debec  mov     rcx, [rsi+28h]; hWnd
0x1800debf0  call    cs:__imp_GetWindowThreadProcessId
0x1800debf6  test    eax, eax
0x1800debf8  jz      loc_1800DEF16
0x1800debfe  mov     rdi, [rbp+var_10]
0x1800dec02  test    rdi, rdi
0x1800dec05  jz      loc_1800DEF16
0x1800dec0b  cmp     r15d, [rbp+dwProcessId]
0x1800dec0f  jnz     loc_1800DEF16
0x1800dec15  cmp     [r14+1Ch], r12d
0x1800dec19  jz      short loc_1800DEC2A
0x1800dec1b  call    cs:__imp_GetCurrentProcessId
0x1800dec21  cmp     r15d, eax
0x1800dec24  jnz     loc_1800DEF16
0x1800dec2a  mov     [rbx+1A0h], rsi
0x1800dec31  mov     rdx, rdi; struct CWindowData *
0x1800dec34  mov     rcx, rbx; this
0x1800dec37  call    ?IsBaseThumbnailDestinationReachable@CWindowList@@AEAA_NPEAVCWindowData@@@Z; CWindowList::IsBaseThumbnailDestinationReachable(CWindowData *)
0x1800dec3c  mov     [rbx+1A0h], r12
0x1800dec43  test    al, al
0x1800dec45  jnz     loc_1800DEF16
0x1800dec4b  mov     ecx, 60h ; '`'; unsigned __int64
0x1800dec50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dec55  mov     rcx, rax
0x1800dec58  test    rax, rax
0x1800dec5b  jz      loc_1800DEEEE
0x1800dec61  lea     rax, ??_7CThumbnailData@@6B@; const CThumbnailData::`vftable'
0x1800dec68  mov     [rcx], rax
0x1800dec6b  xor     eax, eax
0x1800dec6d  mov     [rcx+8], rax
0x1800dec71  mov     [rcx+10h], r12
0x1800dec75  mov     [rcx+18h], r12
0x1800dec79  mov     [rcx+20h], r12d
0x1800dec7d  xorps   xmm0, xmm0
0x1800dec80  movups  xmmword ptr [rcx+24h], xmm0
0x1800dec84  movups  xmmword ptr [rcx+34h], xmm0
0x1800dec88  movups  xmmword ptr [rcx+41h], xmm0
0x1800dec8c  mov     [rcx+58h], r12
0x1800dec90  mov     [rbp+arg_18], rcx
0x1800dec94  mov     rax, [r14+4]
0x1800dec98  mov     [rcx+8], rax
0x1800dec9c  mov     rax, [rbp+arg_18]
0x1800deca0  mov     [rax+10h], rsi
0x1800deca4  mov     rax, [rbp+arg_18]
0x1800deca8  mov     [rax+18h], rdi
0x1800decac  cmp     [r14+1Ch], r12d
0x1800decb0  setnz   cl
0x1800decb3  mov     rax, [rbp+arg_18]
0x1800decb7  mov     [rax+20h], cl
0x1800decba  cmp     [r14+20h], r12d
0x1800decbe  setnz   cl
0x1800decc1  mov     rax, [rbp+arg_18]
0x1800decc5  mov     [rax+21h], cl
0x1800decc8  mov     rax, [rbp+arg_18]
0x1800deccc  mov     [rax+22h], r12b
0x1800decd0  mov     eax, [rbx+198h]
0x1800decd6  lea     r8d, [rax+1]
0x1800decda  cmp     r8d, eax
0x1800decdd  jnb     short loc_1800DECED
0x1800decdf  mov     edi, 80070216h
0x1800dece4  mov     ebx, edi
0x1800dece6  mov     eax, 0B7h
0x1800deceb  jmp     short loc_1800DED61
0x1800deced  mov     r14d, 1
0x1800decf3  lea     r15d, [r14+7]
0x1800decf7  cmp     r8d, [rbx+194h]
0x1800decfe  ja      short loc_1800DED3E
0x1800ded00  mov     rdx, rax
0x1800ded03  mov     rcx, [rbx+180h]
0x1800ded0a  mov     rax, [rbp+arg_18]
0x1800ded0e  mov     [rcx+rdx*8], rax
0x1800ded12  mov     [rbx+198h], r8d
0x1800ded19  lea     r10, [rsi+218h]
0x1800ded20  mov     eax, [r10+18h]
0x1800ded24  lea     r8d, [rax+1]
0x1800ded28  cmp     r8d, eax
0x1800ded2b  jnb     short loc_1800DED92
0x1800ded2d  mov     edi, 80070216h
0x1800ded32  mov     ebx, edi
0x1800ded34  mov     eax, 0B7h
0x1800ded39  jmp     loc_1800DEDEC
0x1800ded3e  lea     r9, [rbp+arg_18]
0x1800ded42  mov     r8d, r14d
0x1800ded45  mov     edx, r15d
0x1800ded48  lea     rcx, [rbx+180h]
0x1800ded4f  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800ded54  mov     ebx, eax
0x1800ded56  test    eax, eax
0x1800ded58  jns     short loc_1800DED19
0x1800ded5a  mov     edi, eax
0x1800ded5c  mov     eax, 0C2h
0x1800ded61  mov     rcx, r12
0x1800ded64  mov     r8d, r12d; unsigned int
0x1800ded67  mov     rdx, r12; int *
0x1800ded6a  mov     [rsp+40h+var_18], rcx; void *
0x1800ded6f  mov     [rsp+40h+var_20], eax; unsigned int
0x1800ded73  mov     r9d, edi; int
0x1800ded76  mov     ecx, 14h; unsigned int
0x1800ded7b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800ded80  mov     [rsp+40h+var_18], r12
0x1800ded85  mov     [rsp+40h+var_20], 1223h
0x1800ded8d  jmp     loc_1800DEF04
0x1800ded92  cmp     r8d, [r10+14h]
0x1800ded96  ja      short loc_1800DEDCD
0x1800ded98  mov     rdx, rax
0x1800ded9b  mov     rcx, [r10]
0x1800ded9e  mov     rax, [rbp+arg_18]
0x1800deda2  mov     [rcx+rdx*8], rax
0x1800deda6  mov     [r10+18h], r8d
0x1800dedaa  lea     r10, [rdi+238h]
0x1800dedb1  mov     eax, [r10+18h]
0x1800dedb5  lea     r8d, [rax+1]
0x1800dedb9  cmp     r8d, eax
0x1800dedbc  jnb     short loc_1800DEE1D
0x1800dedbe  mov     edi, 80070216h
0x1800dedc3  mov     eax, 0B7h
0x1800dedc8  jmp     loc_1800DEEA5
0x1800dedcd  lea     r9, [rbp+arg_18]
0x1800dedd1  mov     r8d, r14d
0x1800dedd4  mov     edx, r15d
0x1800dedd7  mov     rcx, r10
0x1800dedda  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800deddf  mov     ebx, eax
0x1800dede1  test    eax, eax
0x1800dede3  jns     short loc_1800DEDAA
0x1800dede5  mov     edi, eax
0x1800dede7  mov     eax, 0C2h
0x1800dedec  mov     rcx, r12
0x1800dedef  mov     r8d, r12d; unsigned int
0x1800dedf2  mov     rdx, r12; int *
0x1800dedf5  mov     [rsp+40h+var_18], rcx; void *
0x1800dedfa  mov     [rsp+40h+var_20], eax; unsigned int
0x1800dedfe  mov     r9d, edi; int
0x1800dee01  mov     ecx, 14h; unsigned int
0x1800dee06  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800dee0b  mov     [rsp+40h+var_18], r12
0x1800dee10  mov     [rsp+40h+var_20], 122Ah
0x1800dee18  jmp     loc_1800DEF04
0x1800dee1d  cmp     r8d, [r10+14h]
0x1800dee21  ja      short loc_1800DEE88
0x1800dee23  mov     edi, r12d
0x1800dee26  mov     rdx, rax
0x1800dee29  mov     rcx, [r10]
0x1800dee2c  mov     rax, [rbp+arg_18]
0x1800dee30  mov     [rcx+rdx*8], rax
0x1800dee34  mov     [r10+18h], r8d
0x1800dee38  cmp     [rsi+1B8h], r12
0x1800dee3f  jz      loc_1800DEEEA
0x1800dee45  mov     rcx, [rbp+arg_18]
0x1800dee49  mov     rax, [rcx]
0x1800dee4c  mov     rax, [rax+8]
0x1800dee50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dee55  mov     ebx, eax
0x1800dee57  test    eax, eax
0x1800dee59  js      short loc_1800DEED8
0x1800dee5b  mov     rdx, [rbp+arg_18]
0x1800dee5f  mov     rdx, [rdx+58h]; struct CVisual *
0x1800dee63  mov     rcx, [rsi+1B8h]; this
0x1800dee6a  call    ?OnThumbnailAdded@CTopLevelWindow@@QEAAJPEAVCVisual@@@Z; CTopLevelWindow::OnThumbnailAdded(CVisual *)
0x1800dee6f  mov     ebx, eax
0x1800dee71  test    eax, eax
0x1800dee73  jns     loc_1800DEF1B
0x1800dee79  mov     [rsp+40h+var_18], r12
0x1800dee7e  mov     [rsp+40h+var_20], 1235h
0x1800dee86  jmp     short loc_1800DEEE5
0x1800dee88  lea     r9, [rbp+arg_18]
0x1800dee8c  mov     r8d, r14d
0x1800dee8f  mov     edx, r15d
0x1800dee92  mov     rcx, r10
0x1800dee95  call    ?AddMultipleAndSet@?$DynArrayImpl@$0A@@@IEAAJIIPEBX@Z; DynArrayImpl<0>::AddMultipleAndSet(uint,uint,void const *)
0x1800dee9a  mov     edi, eax
0x1800dee9c  test    eax, eax
0x1800dee9e  jns     short loc_1800DEE38
0x1800deea0  mov     eax, 0C2h
0x1800deea5  mov     rcx, r12
0x1800deea8  mov     r9d, edi; int
0x1800deeab  mov     r8d, r12d; unsigned int
0x1800deeae  mov     rdx, r12; int *
0x1800deeb1  mov     ebx, edi
0x1800deeb3  mov     [rsp+40h+var_18], rcx; void *
0x1800deeb8  mov     [rsp+40h+var_20], eax; unsigned int
0x1800deebc  mov     ecx, 14h; unsigned int
0x1800deec1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800deec6  mov     [rsp+40h+var_18], r12
0x1800deecb  mov     [rsp+40h+var_20], 122Bh
0x1800deed3  mov     r9d, edi
0x1800deed6  jmp     short loc_1800DEF07
0x1800deed8  mov     [rsp+40h+var_18], r12
0x1800deedd  mov     [rsp+40h+var_20], 1233h
0x1800deee5  mov     r9d, eax
0x1800deee8  jmp     short loc_1800DEF07
0x1800deeea  mov     ebx, edi
0x1800deeec  jmp     short loc_1800DEF1B
0x1800deeee  mov     [rbp+arg_18], r12
0x1800deef2  mov     ebx, 8007000Eh
0x1800deef7  mov     [rsp+40h+var_18], r12; void *
0x1800deefc  mov     [rsp+40h+var_20], 121Ah; unsigned int
0x1800def04  mov     r9d, ebx; int
0x1800def07  xor     r8d, r8d; unsigned int
0x1800def0a  xor     edx, edx; int *
0x1800def0c  lea     ecx, [rdx+14h]; unsigned int
0x1800def0f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800def14  jmp     short loc_1800DEF1B
0x1800def16  mov     ebx, 80070057h
0x1800def1b  lea     rcx, [rbp+var_8]
0x1800def1f  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x1800def24  mov     eax, ebx
0x1800def26  mov     rbx, [rsp+40h+arg_0]
0x1800def2b  mov     rsi, [rsp+40h+arg_8]
0x1800def30  add     rsp, 40h
0x1800def34  pop     r15
0x1800def36  pop     r14
0x1800def38  pop     r12
0x1800def3a  pop     rdi
0x1800def3b  pop     rbp
0x1800def3c  retn
```
