# Telemetry4UpdateCli::RunCmd::Stop(wchar_t const *,wchar_t const *,long)

- ea: `0x18000c3d0`
- end: `0x18000c81f`
- name: `?Stop@RunCmd@Telemetry4UpdateCli@@QEAAXPEB_W0J@Z`
- size: `1103`
- prototype: `void __fastcall(Telemetry4UpdateCli::RunCmd *__hidden this, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800084bc`

## callees

- `0x180001350`
- `0x180001704`
- `0x180004158`
- `0x18000c3d0`
- `0x18000cf08`
- `0x18000d038`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c469`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c64c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c469`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c64c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c6a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c7aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c6a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c7aa`

## pseudocode

```c
void __fastcall Telemetry4UpdateCli::RunCmd::Stop(
        Telemetry4UpdateCli::RunCmd *this,
        const wchar_t *a2,
        wchar_t *a3,
        int a4)
{
  _DWORD **v4; // r14
  __int64 v5; // rdi
  int v10; // eax
  int *v11; // rdi
  _DWORD **v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  __int64 v14; // r9
  _DWORD *v15; // r8
  char *v16; // r13
  _DWORD *v17; // rax
  int v18; // ebx
  RTL_SRWLOCK *v19; // rcx
  __int64 v20; // r15
  char *v21; // rdi
  DWORD CurrentThreadId; // eax
  _DWORD *v23; // r8
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // ecx
  __int64 **v27; // rbx
  void *v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  __int64 v31; // rax
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-80h] BYREF
  int v33; // [rsp+D0h] [rbp-78h] BYREF
  DWORD v34; // [rsp+D4h] [rbp-74h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-70h] BYREF
  int v36; // [rsp+E0h] [rbp-68h] BYREF
  int v37; // [rsp+E4h] [rbp-64h] BYREF
  int v38; // [rsp+E8h] [rbp-60h] BYREF
  int v39; // [rsp+ECh] [rbp-5Ch] BYREF
  __int64 v40; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v42; // [rsp+100h] [rbp-48h] BYREF
  __int64 v43; // [rsp+108h] [rbp-40h] BYREF
  __int64 v44; // [rsp+110h] [rbp-38h] BYREF
  __int64 v45; // [rsp+118h] [rbp-30h] BYREF
  __int64 v46; // [rsp+120h] [rbp-28h] BYREF
  __int64 v47; // [rsp+128h] [rbp-20h] BYREF
  __int64 v48; // [rsp+130h] [rbp-18h] BYREF
  __int64 v49; // [rsp+138h] [rbp-10h] BYREF
  __int64 v50; // [rsp+140h] [rbp-8h] BYREF
  __int64 v51; // [rsp+148h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+158h] [rbp+10h] BYREF
  __int64 *v53; // [rsp+178h] [rbp+30h]
  __int64 v54; // [rsp+180h] [rbp+38h]
  int *v55; // [rsp+188h] [rbp+40h]
  __int64 v56; // [rsp+190h] [rbp+48h]
  DWORD *v57; // [rsp+198h] [rbp+50h]
  __int64 v58; // [rsp+1A0h] [rbp+58h]
  const wchar_t *v59; // [rsp+1A8h] [rbp+60h]
  int v60; // [rsp+1B0h] [rbp+68h]
  int v61; // [rsp+1B4h] [rbp+6Ch]
  char *v62; // [rsp+1B8h] [rbp+70h]
  int v63; // [rsp+1C0h] [rbp+78h]
  int v64; // [rsp+1C4h] [rbp+7Ch]
  PSRWLOCK *p_SRWLock; // [rsp+1C8h] [rbp+80h]
  __int64 v66; // [rsp+1D0h] [rbp+88h]
  const char *v67; // [rsp+1D8h] [rbp+90h]
  __int64 v68; // [rsp+1E0h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+D8h]

  v4 = (_DWORD **)((char *)this + 272);
  v35 = (__int64)a3;
  v5 = *((_QWORD *)this + 34);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = (int *)(v5 + 80), v10 == v11[2]) )
  {
    v12 = (_DWORD **)((char *)this + 272);
    if ( v11 )
    {
      SRWLock = 0;
      wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        (__int64)this,
        &SRWLock);
      v13 = SRWLock;
      **v4 = 2;
      if ( v13 )
        ReleaseSRWLockExclusive(v13);
      v14 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
      if ( *(_DWORD *)v14 > 5u
        && (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v14 + 24) & 0x400000000000LL) == *(_QWORD *)(v14 + 24) )
      {
        v15 = *v4;
        v40 = (__int64)"1507.2603.28012.0";
        v43 = *((_QWORD *)v11 + 15);
        v44 = *((_QWORD *)v11 + 14);
        v37 = v11[26];
        v45 = *((_QWORD *)v11 + 12);
        v46 = *((_QWORD *)v11 + 11);
        v38 = v11[20];
        v47 = *((_QWORD *)v11 + 9);
        v39 = v11[8];
        v48 = *((_QWORD *)v11 + 3);
        v33 = *v11;
        v49 = *((_QWORD *)v11 + 16);
        v34 = v11[16];
        v50 = *((_QWORD *)v11 + 7);
        LODWORD(SRWLock) = v11[2];
        v51 = 0x1000000;
        v35 = 0x1000000;
        v36 = a4;
        v16 = byte_180018020;
        if ( a3 )
          v16 = (char *)a3;
        v41 = (__int64)v16;
        v42 = (__int64)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v14,
          (int)&byte_18001AA2F,
          (_DWORD)v15 + 8,
          v14,
          (__int64)&v35,
          (__int64)&v51,
          (__int64)&SRWLock,
          (const wchar_t **)&v50,
          (__int64)&v34,
          (const wchar_t **)&v49,
          (__int64)&v33,
          (char **)&v48,
          (__int64)&v39,
          (const wchar_t **)&v47,
          (__int64)&v38,
          (const wchar_t **)&v46,
          (char **)&v45,
          (__int64)&v37,
          (const wchar_t **)&v44,
          (char **)&v43,
          (char **)&v42,
          (char **)&v41,
          (__int64)&v36,
          (const wchar_t **)&v40);
      }
      goto LABEL_30;
    }
  }
  else
  {
    v12 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v17 = *v12;
  v18 = 2;
  v19 = SRWLock;
  *v17 = 2;
  if ( v19 )
    ReleaseSRWLockExclusive(v19);
  v20 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
  if ( *(_DWORD *)v20 > 5u
    && (*(_QWORD *)(v20 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v20 + 24) & 0x400000000000LL) == *(_QWORD *)(v20 + 24) )
  {
    LODWORD(SRWLock) = a4;
    v21 = byte_180018020;
    if ( v35 )
      v21 = (char *)v35;
    CurrentThreadId = GetCurrentThreadId();
    v23 = *v4;
    v34 = CurrentThreadId;
    v68 = 18;
    v66 = 4;
    v33 = v23[18];
    v35 = 0x1000000;
    v67 = "1507.2603.28012.0";
    p_SRWLock = &SRWLock;
    v24 = -1;
    if ( v21 )
    {
      v25 = -1;
      do
        ++v25;
      while ( *(_WORD *)&v21[2 * v25] );
      v26 = 2 * v25 + 2;
    }
    else
    {
      v21 = byte_180018020;
      v26 = 2;
    }
    v62 = v21;
    v63 = v26;
    v64 = 0;
    if ( a2 )
    {
      do
        ++v24;
      while ( a2[v24] );
      v18 = 2 * v24 + 2;
    }
    else
    {
      a2 = (const wchar_t *)byte_180018020;
    }
    v61 = 0;
    v57 = &v34;
    v59 = a2;
    v55 = &v33;
    v60 = v18;
    v53 = &v35;
    v58 = 4;
    v56 = 4;
    v54 = 8;
    tlgWriteTransfer_EventWriteTransfer(v20, (int)&byte_18001AB75, (_DWORD)v23 + 8, 0, 9u, &v52);
  }
LABEL_30:
  if ( *((_DWORD *)this + 78) )
  {
    v27 = (__int64 **)((char *)this + 288);
    if ( *((_DWORD *)this + 78) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v28, v29, (const char *)0x8007029CLL);
    v30 = *v27;
    *((_DWORD *)this + 78) = 0;
    while ( 1 )
    {
      v31 = *v30;
      if ( !*v30 )
        break;
      if ( (__int64 **)v31 == v27 )
      {
        *v30 = *((_QWORD *)this + 38);
        break;
      }
      v30 = (__int64 *)(v31 + 16);
      *v27 = (__int64 *)(v31 + 16);
    }
    *v27 = 0;
  }
}

```

## disassembly

```asm
0x18000c3d0  mov     rax, rsp
0x18000c3d3  mov     [rax+10h], rbx
0x18000c3d7  mov     [rax+18h], rsi
0x18000c3db  mov     [rax+20h], rdi
0x18000c3df  push    rbp
0x18000c3e0  push    r12
0x18000c3e2  push    r13
0x18000c3e4  push    r14
0x18000c3e6  push    r15
0x18000c3e8  lea     rbp, [rax-0D8h]
0x18000c3ef  sub     rsp, 1F0h
0x18000c3f6  mov     rax, cs:__security_cookie
0x18000c3fd  xor     rax, rsp
0x18000c400  mov     [rbp+0D0h+var_30], rax
0x18000c407  lea     r14, [rcx+110h]
0x18000c40e  mov     [rbp+0D0h+var_140], r8
0x18000c412  mov     rdi, [r14]
0x18000c415  mov     rsi, rcx
0x18000c418  xor     ecx, ecx
0x18000c41a  mov     r13d, r9d
0x18000c41d  mov     r15, r8
0x18000c420  mov     r12, rdx
0x18000c423  mov     eax, [rdi+48h]
0x18000c426  test    eax, eax
0x18000c428  jns     loc_18000C626
0x18000c42e  add     rdi, 50h ; 'P'
0x18000c432  cmp     eax, [rdi+8]
0x18000c435  jnz     loc_18000C626
0x18000c43b  mov     rbx, r14
0x18000c43e  test    rdi, rdi
0x18000c441  jz      loc_18000C629
0x18000c447  mov     [rbp+0D0h+SRWLock], rcx
0x18000c44b  lea     rdx, [rbp+0D0h+SRWLock]
0x18000c44f  mov     rcx, rsi
0x18000c452  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c457  mov     rax, [r14]
0x18000c45a  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18000c45e  mov     dword ptr [rax], 2
0x18000c464  test    rcx, rcx
0x18000c467  jz      short loc_18000C46F
0x18000c469  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c46f  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000c474  mov     r9, [rax+8]
0x18000c478  cmp     dword ptr [r9], 5
0x18000c47c  jbe     loc_18000C799
0x18000c482  mov     rcx, 400000000000h
0x18000c48c  test    [r9+10h], rcx
0x18000c490  jz      loc_18000C799
0x18000c496  mov     rax, [r9+18h]
0x18000c49a  and     rax, rcx
0x18000c49d  cmp     rax, [r9+18h]
0x18000c4a1  jnz     loc_18000C799
0x18000c4a7  mov     r8, [r14]
0x18000c4aa  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18000c4b1  mov     [rbp+0D0h+var_128], rax
0x18000c4b5  test    r15, r15
0x18000c4b8  mov     rax, [rdi+78h]
0x18000c4bc  mov     [rbp+0D0h+var_110], rax
0x18000c4c0  mov     rax, [rdi+70h]
0x18000c4c4  mov     [rbp+0D0h+var_108], rax
0x18000c4c8  mov     eax, [rdi+68h]
0x18000c4cb  mov     dword ptr [rbp+0D0h+var_138+4], eax
0x18000c4ce  mov     rax, [rdi+60h]
0x18000c4d2  mov     [rbp+0D0h+var_100], rax
0x18000c4d6  mov     rax, [rdi+58h]
0x18000c4da  mov     [rbp+0D0h+var_F8], rax
0x18000c4de  mov     eax, [rdi+50h]
0x18000c4e1  mov     dword ptr [rbp+0D0h+var_130], eax
0x18000c4e4  mov     rax, [rdi+48h]
0x18000c4e8  mov     [rbp+0D0h+var_F0], rax
0x18000c4ec  mov     eax, [rdi+20h]
0x18000c4ef  mov     dword ptr [rbp+0D0h+var_130+4], eax
0x18000c4f2  mov     rax, [rdi+18h]
0x18000c4f6  mov     [rbp+0D0h+var_E8], rax
0x18000c4fa  mov     eax, [rdi]
0x18000c4fc  mov     dword ptr [rbp+0D0h+var_148], eax
0x18000c4ff  mov     rax, [rdi+80h]
0x18000c506  mov     [rbp+0D0h+var_E0], rax
0x18000c50a  mov     eax, [rdi+40h]
0x18000c50d  mov     dword ptr [rbp+0D0h+var_148+4], eax
0x18000c510  mov     rax, [rdi+38h]
0x18000c514  mov     [rbp+0D0h+var_D8], rax
0x18000c518  mov     eax, [rdi+8]
0x18000c51b  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x18000c51e  mov     eax, 1000000h
0x18000c523  mov     [rbp+0D0h+var_D0], rax
0x18000c527  mov     [rbp+0D0h+var_140], rax
0x18000c52b  lea     rax, [rbp+0D0h+var_128]
0x18000c52f  mov     [rsp+210h+var_158], rax; __int64
0x18000c537  lea     rax, [rbp+0D0h+var_138]
0x18000c53b  mov     [rsp+210h+var_160], rax; __int64
0x18000c543  lea     rax, [rbp+0D0h+var_120]
0x18000c547  mov     [rsp+210h+var_168], rax; __int64
0x18000c54f  lea     rax, [rbp+0D0h+var_118]
0x18000c553  mov     [rsp+210h+var_170], rax; __int64
0x18000c55b  lea     rax, [rbp+0D0h+var_110]
0x18000c55f  mov     [rsp+210h+var_178], rax; __int64
0x18000c567  lea     rax, [rbp+0D0h+var_108]
0x18000c56b  mov     [rsp+210h+var_180], rax; __int64
0x18000c573  lea     rax, [rbp+0D0h+var_138+4]
0x18000c577  mov     [rsp+210h+var_188], rax; __int64
0x18000c57f  lea     rax, [rbp+0D0h+var_100]
0x18000c583  mov     [rsp+210h+var_190], rax; __int64
0x18000c58b  lea     rax, [rbp+0D0h+var_F8]
0x18000c58f  mov     [rsp+210h+var_198], rax; __int64
0x18000c594  lea     rax, [rbp+0D0h+var_130]
0x18000c598  mov     [rsp+210h+var_1A0], rax; __int64
0x18000c59d  lea     rax, [rbp+0D0h+var_F0]
0x18000c5a1  mov     [rsp+210h+var_1A8], rax; __int64
0x18000c5a6  lea     rax, [rbp+0D0h+var_130+4]
0x18000c5aa  mov     [rsp+210h+var_1B0], rax; __int64
0x18000c5af  lea     rax, [rbp+0D0h+var_E8]
0x18000c5b3  mov     [rsp+210h+var_1B8], rax; __int64
0x18000c5b8  lea     rax, [rbp+0D0h+var_148]
0x18000c5bc  mov     [rsp+210h+var_1C0], rax; __int64
0x18000c5c1  lea     rax, [rbp+0D0h+var_E0]
0x18000c5c5  mov     [rsp+210h+var_1C8], rax; __int64
0x18000c5ca  lea     rax, [rbp+0D0h+var_148+4]
0x18000c5ce  mov     [rsp+210h+var_1D0], rax; __int64
0x18000c5d3  lea     rax, [rbp+0D0h+var_D8]
0x18000c5d7  mov     [rsp+210h+var_1D8], rax; __int64
0x18000c5dc  lea     rax, [rbp+0D0h+SRWLock]
0x18000c5e0  mov     [rsp+210h+var_1E0], rax; __int64
0x18000c5e5  lea     rax, [rbp+0D0h+var_D0]
0x18000c5e9  mov     dword ptr [rbp+0D0h+var_138], r13d
0x18000c5ed  lea     r13, byte_180018020
0x18000c5f4  mov     [rsp+210h+var_1E8], rax; __int64
0x18000c5f9  cmovnz  r13, r15
0x18000c5fd  lea     rax, [rbp+0D0h+var_140]
0x18000c601  mov     [rbp+0D0h+var_120], r13
0x18000c605  mov     qword ptr [rsp+210h+var_1F0], rax; __int64
0x18000c60a  add     r8, 8; int
0x18000c60e  mov     [rbp+0D0h+var_118], r12
0x18000c612  lea     rdx, byte_18001AA2F; int
0x18000c619  mov     rcx, r9; int
0x18000c61c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566645@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000c621  jmp     loc_18000C799
0x18000c626  mov     rbx, r14
0x18000c629  mov     [rbp+0D0h+SRWLock], rcx
0x18000c62d  lea     rdx, [rbp+0D0h+SRWLock]
0x18000c631  mov     rcx, rsi
0x18000c634  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000c639  mov     rax, [rbx]
0x18000c63c  mov     ebx, 2
0x18000c641  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18000c645  mov     [rax], ebx
0x18000c647  test    rcx, rcx
0x18000c64a  jz      short loc_18000C652
0x18000c64c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c652  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000c657  mov     r15, [rax+8]
0x18000c65b  cmp     dword ptr [r15], 5
0x18000c65f  jbe     loc_18000C799
0x18000c665  mov     rcx, 400000000000h
0x18000c66f  test    [r15+10h], rcx
0x18000c673  jz      loc_18000C799
0x18000c679  mov     rax, [r15+18h]
0x18000c67d  and     rax, rcx
0x18000c680  cmp     rax, [r15+18h]
0x18000c684  jnz     loc_18000C799
0x18000c68a  mov     rax, [rbp+0D0h+var_140]
0x18000c68e  mov     dword ptr [rbp+0D0h+SRWLock], r13d
0x18000c692  test    rax, rax
0x18000c695  lea     r13, byte_180018020
0x18000c69c  mov     rdi, r13
0x18000c69f  cmovnz  rdi, rax
0x18000c6a3  call    cs:__imp_GetCurrentThreadId
0x18000c6a9  mov     r8, [r14]
0x18000c6ac  xor     edx, edx
0x18000c6ae  mov     dword ptr [rbp+0D0h+var_148+4], eax
0x18000c6b1  mov     [rbp+0D0h+var_38], 12h
0x18000c6bc  mov     [rbp+0D0h+var_48], 4
0x18000c6c7  mov     eax, [r8+48h]
0x18000c6cb  mov     dword ptr [rbp+0D0h+var_148], eax
0x18000c6ce  mov     eax, 1000000h
0x18000c6d3  mov     [rbp+0D0h+var_140], rax
0x18000c6d7  lea     rax, a15072603280120; "1507.2603.28012.0"
0x18000c6de  mov     [rbp+0D0h+var_40], rax
0x18000c6e5  lea     rax, [rbp+0D0h+SRWLock]
0x18000c6e9  mov     [rbp+0D0h+var_50], rax
0x18000c6f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c6f4  test    rdi, rdi
0x18000c6f7  jz      short loc_18000C70E
0x18000c6f9  mov     rcx, rax
0x18000c6fc  inc     rcx
0x18000c6ff  cmp     [rdi+rcx*2], dx
0x18000c703  jnz     short loc_18000C6FC
0x18000c705  lea     ecx, ds:2[rcx*2]
0x18000c70c  jmp     short loc_18000C713
0x18000c70e  mov     rdi, r13
0x18000c711  mov     ecx, ebx
0x18000c713  mov     [rbp+0D0h+var_60], rdi
0x18000c717  mov     [rbp+0D0h+var_58], ecx
0x18000c71a  mov     [rbp+0D0h+var_54], edx
0x18000c71d  test    r12, r12
0x18000c720  jz      short loc_18000C735
0x18000c722  inc     rax
0x18000c725  cmp     [r12+rax*2], dx
0x18000c72a  jnz     short loc_18000C722
0x18000c72c  lea     ebx, ds:2[rax*2]
0x18000c733  jmp     short loc_18000C738
0x18000c735  mov     r12, r13
0x18000c738  lea     rax, [rbp+0D0h+var_148+4]
0x18000c73c  mov     [rbp+0D0h+var_64], edx
0x18000c73f  mov     [rbp+0D0h+var_80], rax
0x18000c743  lea     rdx, byte_18001AB75; int
0x18000c74a  lea     rax, [rbp+0D0h+var_148]
0x18000c74e  mov     [rbp+0D0h+var_70], r12
0x18000c752  mov     [rbp+0D0h+var_90], rax
0x18000c756  add     r8, 8; int
0x18000c75a  lea     rax, [rbp+0D0h+var_140]
0x18000c75e  mov     [rbp+0D0h+var_68], ebx
0x18000c761  mov     [rbp+0D0h+var_A0], rax
0x18000c765  xor     r9d, r9d; int
0x18000c768  lea     rax, [rbp+0D0h+var_C0]
0x18000c76c  mov     [rbp+0D0h+var_78], 4
0x18000c774  mov     [rsp+210h+var_1E8], rax; PEVENT_DATA_DESCRIPTOR
0x18000c779  mov     rcx, r15; int
0x18000c77c  mov     [rsp+210h+var_1F0], 9; int
0x18000c784  mov     [rbp+0D0h+var_88], 4
0x18000c78c  mov     [rbp+0D0h+var_98], 8
0x18000c794  call    _tlgWriteTransfer_EventWriteTransfer
0x18000c799  xor     edi, edi
0x18000c79b  cmp     [rsi+138h], edi
0x18000c7a1  jz      short loc_18000C7EF
0x18000c7a3  lea     rbx, [rsi+120h]
0x18000c7aa  call    cs:__imp_GetCurrentThreadId
0x18000c7b0  cmp     [rbx+18h], eax
0x18000c7b3  jz      short loc_18000C7C7
0x18000c7b5  mov     rcx, [rbp+0D8h]; this
0x18000c7bc  mov     r9d, 8007029Ch; char *
0x18000c7c2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c7c7  mov     rcx, [rbx]
0x18000c7ca  mov     [rbx+18h], edi
0x18000c7cd  jmp     short loc_18000C7DB
0x18000c7cf  cmp     rax, rbx
0x18000c7d2  jz      short loc_18000C7E5
0x18000c7d4  lea     rcx, [rax+10h]
0x18000c7d8  mov     [rbx], rcx
0x18000c7db  mov     rax, [rcx]
0x18000c7de  test    rax, rax
0x18000c7e1  jnz     short loc_18000C7CF
0x18000c7e3  jmp     short loc_18000C7EC
0x18000c7e5  mov     rax, [rbx+10h]
0x18000c7e9  mov     [rcx], rax
0x18000c7ec  mov     [rbx], rdi
0x18000c7ef  mov     rcx, [rbp+0D0h+var_30]
0x18000c7f6  xor     rcx, rsp; StackCookie
0x18000c7f9  call    __security_check_cookie
0x18000c7fe  lea     r11, [rsp+210h+var_20]
0x18000c806  mov     rbx, [r11+38h]
0x18000c80a  mov     rsi, [r11+40h]
0x18000c80e  mov     rdi, [r11+48h]
0x18000c812  mov     rsp, r11
0x18000c815  pop     r15
0x18000c817  pop     r14
0x18000c819  pop     r13
0x18000c81b  pop     r12
0x18000c81d  pop     rbp
0x18000c81e  retn
```
