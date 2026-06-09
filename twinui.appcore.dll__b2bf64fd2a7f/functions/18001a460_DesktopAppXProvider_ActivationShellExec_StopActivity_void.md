# DesktopAppXProvider::ActivationShellExec::StopActivity(void)

- ea: `0x18001a460`
- end: `0x18001abe1`
- name: `?StopActivity@ActivationShellExec@DesktopAppXProvider@@MEAAXXZ`
- size: `1921`
- prototype: `void __fastcall(DesktopAppXProvider::ActivationShellExec *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180015548`
- `0x1800166e4`
- `0x18001a460`
- `0x18002b1b0`
- `0x18002b590`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a5c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001aac4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a5c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001aac4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a54d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001aa4f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a54d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001aa4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a9d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a4d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a9d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a503`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a51d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a4e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a503`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a51d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a9ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001aa1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a9a9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001abad`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a9a9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001abad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aade`

## pseudocode

```c
void __fastcall DesktopAppXProvider::ActivationShellExec::StopActivity(DesktopAppXProvider::ActivationShellExec *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  void (*v7)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  _QWORD *Ptr; // r13
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rdx
  const WCHAR *v11; // r8
  const unsigned __int16 *v12; // r9
  const WCHAR *v13; // r10
  const unsigned __int16 *v14; // r11
  const unsigned __int16 *v15; // rbx
  const WCHAR *v16; // r14
  const unsigned __int16 *v17; // r15
  const unsigned __int16 *v18; // r12
  int v19; // eax
  __int64 v20; // rdi
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  bool v24; // zf
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  int v38; // ecx
  RTL_SRWLOCK *v39; // rbx
  void (*v40)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  _QWORD *v41; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v43; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v46; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v47; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+58h] [rbp-A8h] BYREF
  int v50; // [rsp+5Ch] [rbp-A4h] BYREF
  int v51; // [rsp+60h] [rbp-A0h] BYREF
  int v52; // [rsp+64h] [rbp-9Ch] BYREF
  int v53; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK v54; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v57; // [rsp+A0h] [rbp-60h]
  int v58; // [rsp+A8h] [rbp-58h]
  int v59; // [rsp+ACh] [rbp-54h]
  PSRWLOCK *v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v62; // [rsp+C0h] [rbp-40h]
  __int64 v63; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v65; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  void *v67; // [rsp+F0h] [rbp-10h]
  int v68; // [rsp+F8h] [rbp-8h]
  int v69; // [rsp+FCh] [rbp-4h]
  PSRWLOCK *v70; // [rsp+100h] [rbp+0h]
  __int64 v71; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v72; // [rsp+110h] [rbp+10h]
  __int64 v73; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v74; // [rsp+120h] [rbp+20h]
  __int64 v75; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v76; // [rsp+130h] [rbp+30h]
  int v77; // [rsp+138h] [rbp+38h]
  int v78; // [rsp+13Ch] [rbp+3Ch]
  unsigned int *v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v81; // [rsp+150h] [rbp+50h]
  int v82; // [rsp+158h] [rbp+58h]
  int v83; // [rsp+15Ch] [rbp+5Ch]
  int *v84; // [rsp+160h] [rbp+60h]
  __int64 v85; // [rsp+168h] [rbp+68h]
  const WCHAR *v86; // [rsp+170h] [rbp+70h]
  int v87; // [rsp+178h] [rbp+78h]
  int v88; // [rsp+17Ch] [rbp+7Ch]
  int *v89; // [rsp+180h] [rbp+80h]
  __int64 v90; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v91; // [rsp+190h] [rbp+90h]
  int v92; // [rsp+198h] [rbp+98h]
  int v93; // [rsp+19Ch] [rbp+9Ch]
  int *v94; // [rsp+1A0h] [rbp+A0h]
  __int64 v95; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v96; // [rsp+1B0h] [rbp+B0h]
  int v97; // [rsp+1B8h] [rbp+B8h]
  int v98; // [rsp+1BCh] [rbp+BCh]
  const WCHAR *v99; // [rsp+1C0h] [rbp+C0h]
  int v100; // [rsp+1C8h] [rbp+C8h]
  int v101; // [rsp+1CCh] [rbp+CCh]
  int *v102; // [rsp+1D0h] [rbp+D0h]
  __int64 v103; // [rsp+1D8h] [rbp+D8h]
  const unsigned __int16 *v104; // [rsp+1E0h] [rbp+E0h]
  int v105; // [rsp+1E8h] [rbp+E8h]
  int v106; // [rsp+1ECh] [rbp+ECh]
  const WCHAR *v107; // [rsp+1F0h] [rbp+F0h]
  int v108; // [rsp+1F8h] [rbp+F8h]
  int v109; // [rsp+1FCh] [rbp+FCh]
  int *v110; // [rsp+200h] [rbp+100h]
  __int64 v111; // [rsp+208h] [rbp+108h]
  WINBOOL *p_fPending; // [rsp+210h] [rbp+110h]
  __int64 v113; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v114; // [rsp+220h] [rbp+120h]
  int v115; // [rsp+228h] [rbp+128h]
  int v116; // [rsp+22Ch] [rbp+12Ch]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) )
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = v5 + 33;
        AcquireSRWLockExclusive(v6);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
      }
      else
      {
        v47 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      SRWLock = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
        && fPending )
      {
        qword_1800B3468 = 0;
        SRWLock = (PSRWLOCK)&qword_1800B3460;
        qword_1800B3460 = &PickerTelemetryProvider::`vftable';
        byte_1800B3470 = 0;
        dword_1800B3474 = 0;
        qword_1800B3478 = (struct _tlgProvider_t *)&`DesktopAppXProvider::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_7d47696adb3c506dad77b6b0f3bb8e0c_::_lambda_invoker_cdecl_);
        wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800B3460, qword_1800B3478, v7);
        InitOnceComplete(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &qword_1800B3460);
      }
      Ptr = SRWLock[1].Ptr;
      if ( *(_DWORD *)Ptr > 5u )
      {
        v9 = -1;
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        v11 = (const WCHAR *)*((_QWORD *)v4 + 15);
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v13 = (const WCHAR *)*((_QWORD *)v4 + 12);
        v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v16 = (const WCHAR *)*((_QWORD *)v4 + 3);
        v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        fPending = v4[17];
        v49 = v4[4];
        v50 = v4[26];
        v51 = v4[20];
        v52 = v4[8];
        v53 = *v4;
        v46 = v4[16];
        v19 = v4[2];
        v20 = *((_QWORD *)this + 34);
        LODWORD(v47) = v19;
        v54 = (PSRWLOCK)0x1000000;
        v48 = 0;
        if ( v10 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_BYTE *)v10 + v21) );
          v22 = v21 + 1;
        }
        else
        {
          v10 = &word_18009494A;
          v22 = 1;
        }
        v115 = v22;
        v114 = v10;
        p_fPending = &fPending;
        v110 = &v49;
        v116 = 0;
        v113 = 4;
        v111 = 4;
        if ( v11 )
        {
          v23 = -1;
          do
            v24 = v11[++v23] == 0;
          while ( !v24 );
          v25 = 2 * v23 + 2;
        }
        else
        {
          v11 = &pszDefault;
          v25 = 2;
        }
        v107 = v11;
        v108 = v25;
        v109 = 0;
        if ( v12 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *((_BYTE *)v12 + v26) );
          v27 = v26 + 1;
        }
        else
        {
          v12 = &word_18009494A;
          v27 = 1;
        }
        v105 = v27;
        v102 = &v50;
        v104 = v12;
        v106 = 0;
        v103 = 4;
        if ( v13 )
        {
          v28 = -1;
          do
            v24 = v13[++v28] == 0;
          while ( !v24 );
          v29 = 2 * v28 + 2;
        }
        else
        {
          v13 = &pszDefault;
          v29 = 2;
        }
        v99 = v13;
        v100 = v29;
        v101 = 0;
        if ( v14 )
        {
          v30 = -1;
          do
            ++v30;
          while ( *((_BYTE *)v14 + v30) );
          v31 = v30 + 1;
        }
        else
        {
          v14 = &word_18009494A;
          v31 = 1;
        }
        v97 = v31;
        v94 = &v51;
        v96 = v14;
        v98 = 0;
        v95 = 4;
        if ( v15 )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_BYTE *)v15 + v32) );
          v33 = v32 + 1;
        }
        else
        {
          v15 = &word_18009494A;
          v33 = 1;
        }
        v92 = v33;
        v89 = &v52;
        v91 = v15;
        v93 = 0;
        v90 = 4;
        if ( v16 )
        {
          v34 = -1;
          do
            v24 = v16[++v34] == 0;
          while ( !v24 );
          v35 = 2 * v34 + 2;
        }
        else
        {
          v16 = &pszDefault;
          v35 = 2;
        }
        v87 = v35;
        v84 = &v53;
        v86 = v16;
        v88 = 0;
        v85 = 4;
        if ( v17 )
        {
          v36 = -1;
          do
            ++v36;
          while ( *((_BYTE *)v17 + v36) );
          v37 = v36 + 1;
        }
        else
        {
          v17 = &word_18009494A;
          v37 = 1;
        }
        v82 = v37;
        v81 = v17;
        v79 = &v46;
        v83 = 0;
        v80 = 4;
        if ( v18 )
        {
          do
            ++v9;
          while ( *((_BYTE *)v18 + v9) );
          v38 = v9 + 1;
        }
        else
        {
          v18 = &word_18009494A;
          v38 = 1;
        }
        v78 = 0;
        v74 = &v47;
        EventDescriptor.Keyword = 0;
        v72 = &v54;
        v77 = v38;
        v70 = &v48;
        *(_DWORD *)&EventDescriptor.Level = 517;
        UserData.Ptr = Ptr[1];
        v76 = v18;
        v75 = 4;
        v73 = 8;
        v71 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v67 = &unk_18009E9C8;
        UserData.Reserved = 2;
        v68 = 322;
        v69 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(Ptr[4], &EventDescriptor, (LPCGUID)(v20 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_67;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v39 = v5 + 33;
    AcquireSRWLockExclusive(v39);
    v48 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v39 )
      ReleaseSRWLockExclusive(v39);
  }
  else
  {
    v54 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_1800B3468 = 0;
    SRWLock = (PSRWLOCK)&qword_1800B3460;
    qword_1800B3460 = &PickerTelemetryProvider::`vftable';
    byte_1800B3470 = 0;
    dword_1800B3474 = 0;
    qword_1800B3478 = (struct _tlgProvider_t *)&`DesktopAppXProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_7d47696adb3c506dad77b6b0f3bb8e0c_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800B3460, qword_1800B3478, v40);
    InitOnceComplete(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &qword_1800B3460);
  }
  v41 = SRWLock[1].Ptr;
  if ( *(_DWORD *)v41 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v43 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v65 = 4;
    v63 = 4;
    LODWORD(v47) = *(_DWORD *)(v43 + 72);
    p_SRWLock = &SRWLock;
    v62 = &v47;
    v60 = &v48;
    *(_DWORD *)&EventDescriptor.Level = 517;
    v56.Ptr = v41[1];
    v48 = 0;
    v61 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v56.Size = *(unsigned __int16 *)v56.Ptr;
    v57 = &word_18009EB16;
    v56.Reserved = 2;
    v58 = 72;
    v59 = 1;
    v46 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(v41[4], &EventDescriptor, (LPCGUID)(v43 + 8), 0, 5u, &v56);
  }
LABEL_67:
  wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001a460  mov     [rsp-8+arg_18], rbx
0x18001a465  push    rbp
0x18001a466  push    rsi
0x18001a467  push    rdi
0x18001a468  push    r13
0x18001a46a  push    r14
0x18001a46c  lea     rbp, [rsp-140h]
0x18001a474  sub     rsp, 240h
0x18001a47b  mov     rax, cs:__security_cookie
0x18001a482  xor     rax, rsp
0x18001a485  mov     [rbp+160h+var_30], rax
0x18001a48c  mov     rdi, [rcx+110h]
0x18001a493  xor     r14d, r14d
0x18001a496  mov     rsi, rcx
0x18001a499  mov     eax, [rdi+48h]
0x18001a49c  test    eax, eax
0x18001a49e  jns     loc_18001A9BC
0x18001a4a4  add     rdi, 50h ; 'P'
0x18001a4a8  cmp     eax, [rdi+8]
0x18001a4ab  jnz     loc_18001A9BC
0x18001a4b1  mov     rbx, [rcx+118h]
0x18001a4b8  test    rdi, rdi
0x18001a4bb  jz      loc_18001A9C3
0x18001a4c1  test    rbx, rbx
0x18001a4c4  jz      short loc_18001A50B
0x18001a4c6  add     rbx, 108h
0x18001a4cd  mov     rcx, rbx; SRWLock
0x18001a4d0  call    cs:__imp_AcquireSRWLockExclusive
0x18001a4d6  lea     rax, [rsp+260h+SRWLock]
0x18001a4db  mov     [rax], r14
0x18001a4de  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x18001a4e3  test    rcx, rcx
0x18001a4e6  jz      short loc_18001A4EE
0x18001a4e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a4ee  mov     rax, [rsi+110h]
0x18001a4f5  mov     dword ptr [rax], 2
0x18001a4fb  test    rbx, rbx
0x18001a4fe  jz      short loc_18001A530
0x18001a500  mov     rcx, rbx; SRWLock
0x18001a503  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a509  jmp     short loc_18001A530
0x18001a50b  lea     rax, [rsp+260h+var_218]
0x18001a510  mov     [rax], r14
0x18001a513  mov     rcx, [rsp+260h+var_218]; SRWLock
0x18001a518  test    rcx, rcx
0x18001a51b  jz      short loc_18001A523
0x18001a51d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a523  mov     rax, [rsi+110h]
0x18001a52a  mov     dword ptr [rax], 2
0x18001a530  lea     r9, [rsp+260h+SRWLock]; lpContext
0x18001a535  mov     [rsp+260h+SRWLock], r14
0x18001a53a  lea     r8, [rsp+260h+fPending]; fPending
0x18001a53f  mov     [rsp+260h+fPending], r14d
0x18001a544  xor     edx, edx; dwFlags
0x18001a546  lea     rcx, ?wrapper@?1??Instance@DesktopAppXProvider@@KAPEAV2@XZ@4V?$static_lazy@VDesktopAppXProvider@@@details@wil@@A; lpInitOnce
0x18001a54d  call    cs:__imp_InitOnceBeginInitialize
0x18001a553  test    eax, eax
0x18001a555  jz      short loc_18001A5C8
0x18001a557  cmp     [rsp+260h+fPending], r14d
0x18001a55c  jz      short loc_18001A5C8
0x18001a55e  lea     rbx, qword_1800B3460
0x18001a565  mov     cs:qword_1800B3468, r14
0x18001a56c  lea     rax, ??_7PickerTelemetryProvider@@6B@; const PickerTelemetryProvider::`vftable'
0x18001a573  mov     [rsp+260h+SRWLock], rbx
0x18001a578  mov     cs:qword_1800B3460, rax
0x18001a57f  mov     cs:byte_1800B3470, r14b
0x18001a586  mov     cs:dword_1800B3474, r14d
0x18001a58d  lea     rax, ?__hInner@?1???0StaticHandle@DesktopAppXProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DesktopAppXProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001a594  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7d47696adb3c506dad77b6b0f3bb8e0c_@@CA@XZ; void (__cdecl *)()
0x18001a59b  mov     cs:qword_1800B3478, rax
0x18001a5a2  call    atexit
0x18001a5a7  mov     rdx, cs:qword_1800B3478; struct _tlgProvider_t *
0x18001a5ae  mov     rcx, rbx; this
0x18001a5b1  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001a5b6  mov     r8, rbx; lpContext
0x18001a5b9  lea     rcx, ?wrapper@?1??Instance@DesktopAppXProvider@@KAPEAV2@XZ@4V?$static_lazy@VDesktopAppXProvider@@@details@wil@@A; lpInitOnce
0x18001a5c0  xor     edx, edx; dwFlags
0x18001a5c2  call    cs:__imp_InitOnceComplete
0x18001a5c8  mov     rax, [rsp+260h+SRWLock]
0x18001a5cd  mov     r13, [rax+8]
0x18001a5d1  mov     eax, [r13+0]
0x18001a5d5  cmp     eax, 5
0x18001a5d8  jbe     loc_18001ABB3
0x18001a5de  mov     [rsp+260h+arg_8], r12
0x18001a5e6  mov     [rsp+260h+arg_10], r15
0x18001a5ee  mov     eax, [rdi+44h]
0x18001a5f1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a5f8  mov     rdx, [rdi+30h]
0x18001a5fc  mov     r8, [rdi+78h]
0x18001a600  mov     r9, [rdi+70h]
0x18001a604  mov     r10, [rdi+60h]
0x18001a608  mov     r11, [rdi+58h]
0x18001a60c  mov     rbx, [rdi+48h]
0x18001a610  mov     r14, [rdi+18h]
0x18001a614  mov     r15, [rdi+80h]
0x18001a61b  mov     r12, [rdi+38h]
0x18001a61f  mov     [rsp+260h+fPending], eax
0x18001a623  mov     eax, [rdi+10h]
0x18001a626  mov     [rsp+260h+var_208], eax
0x18001a62a  mov     eax, [rdi+68h]
0x18001a62d  mov     [rsp+260h+var_204], eax
0x18001a631  mov     eax, [rdi+50h]
0x18001a634  mov     [rsp+260h+var_200], eax
0x18001a638  mov     eax, [rdi+20h]
0x18001a63b  mov     [rsp+260h+var_1FC], eax
0x18001a63f  mov     eax, [rdi]
0x18001a641  mov     [rsp+260h+var_1F8], eax
0x18001a645  mov     eax, [rdi+40h]
0x18001a648  mov     [rsp+260h+var_220], eax
0x18001a64c  mov     eax, [rdi+8]
0x18001a64f  mov     rdi, [rsi+110h]
0x18001a656  mov     dword ptr [rsp+260h+var_218], eax
0x18001a65a  mov     [rsp+260h+var_1F0], 1000000h
0x18001a663  mov     [rsp+260h+var_210], 0
0x18001a66c  test    rdx, rdx
0x18001a66f  jz      short loc_18001A681
0x18001a671  mov     rax, rcx
0x18001a674  inc     rax
0x18001a677  cmp     byte ptr [rdx+rax], 0
0x18001a67b  jnz     short loc_18001A674
0x18001a67d  inc     eax
0x18001a67f  jmp     short loc_18001A68D
0x18001a681  lea     rdx, word_18009494A
0x18001a688  mov     eax, 1
0x18001a68d  mov     [rbp+160h+var_38], eax
0x18001a693  lea     rax, [rsp+260h+fPending]
0x18001a698  mov     [rbp+160h+var_40], rdx
0x18001a69f  xor     edx, edx
0x18001a6a1  mov     [rbp+160h+var_50], rax
0x18001a6a8  lea     rax, [rsp+260h+var_208]
0x18001a6ad  mov     [rbp+160h+var_60], rax
0x18001a6b4  mov     [rbp+160h+var_34], edx
0x18001a6ba  mov     [rbp+160h+var_48], 4
0x18001a6c5  mov     [rbp+160h+var_58], 4
0x18001a6d0  test    r8, r8
0x18001a6d3  jz      short loc_18001A6F5
0x18001a6d5  mov     rax, rcx
0x18001a6d8  nop     dword ptr [rax+rax+00000000h]
0x18001a6e0  cmp     [r8+rax*2+2], dx
0x18001a6e6  lea     rax, [rax+1]
0x18001a6ea  jnz     short loc_18001A6E0
0x18001a6ec  lea     eax, ds:2[rax*2]
0x18001a6f3  jmp     short loc_18001A701
0x18001a6f5  lea     r8, pszDefault
0x18001a6fc  mov     eax, 2
0x18001a701  mov     [rbp+160h+var_70], r8
0x18001a708  mov     [rbp+160h+var_68], eax
0x18001a70e  mov     [rbp+160h+var_64], edx
0x18001a714  test    r9, r9
0x18001a717  jz      short loc_18001A72D
0x18001a719  mov     rax, rcx
0x18001a71c  nop     dword ptr [rax+00h]
0x18001a720  inc     rax
0x18001a723  cmp     [r9+rax], dl
0x18001a727  jnz     short loc_18001A720
0x18001a729  inc     eax
0x18001a72b  jmp     short loc_18001A739
0x18001a72d  lea     r9, word_18009494A
0x18001a734  mov     eax, 1
0x18001a739  mov     [rbp+160h+var_78], eax
0x18001a73f  lea     rax, [rsp+260h+var_204]
0x18001a744  mov     [rbp+160h+var_90], rax
0x18001a74b  mov     [rbp+160h+var_80], r9
0x18001a752  mov     [rbp+160h+var_74], edx
0x18001a758  mov     [rbp+160h+var_88], 4
0x18001a763  test    r10, r10
0x18001a766  jz      short loc_18001A785
0x18001a768  mov     rax, rcx
0x18001a76b  nop     dword ptr [rax+rax+00h]
0x18001a770  cmp     [r10+rax*2+2], dx
0x18001a776  lea     rax, [rax+1]
0x18001a77a  jnz     short loc_18001A770
0x18001a77c  lea     eax, ds:2[rax*2]
0x18001a783  jmp     short loc_18001A791
0x18001a785  lea     r10, pszDefault
0x18001a78c  mov     eax, 2
0x18001a791  mov     [rbp+160h+var_A0], r10
0x18001a798  mov     [rbp+160h+var_98], eax
0x18001a79e  mov     [rbp+160h+var_94], edx
0x18001a7a4  test    r11, r11
0x18001a7a7  jz      short loc_18001A7BD
0x18001a7a9  mov     rax, rcx
0x18001a7ac  nop     dword ptr [rax+00h]
0x18001a7b0  inc     rax
0x18001a7b3  cmp     [r11+rax], dl
0x18001a7b7  jnz     short loc_18001A7B0
0x18001a7b9  inc     eax
0x18001a7bb  jmp     short loc_18001A7C9
0x18001a7bd  lea     r11, word_18009494A
0x18001a7c4  mov     eax, 1
0x18001a7c9  mov     [rbp+160h+var_A8], eax
0x18001a7cf  lea     rax, [rsp+260h+var_200]
0x18001a7d4  mov     [rbp+160h+var_C0], rax
0x18001a7db  mov     [rbp+160h+var_B0], r11
0x18001a7e2  mov     [rbp+160h+var_A4], edx
0x18001a7e8  mov     [rbp+160h+var_B8], 4
0x18001a7f3  test    rbx, rbx
0x18001a7f6  jz      short loc_18001A80C
0x18001a7f8  mov     rax, rcx
0x18001a7fb  nop     dword ptr [rax+rax+00h]
0x18001a800  inc     rax
0x18001a803  cmp     [rbx+rax], dl
0x18001a806  jnz     short loc_18001A800
0x18001a808  inc     eax
0x18001a80a  jmp     short loc_18001A818
0x18001a80c  lea     rbx, word_18009494A
0x18001a813  mov     eax, 1
0x18001a818  mov     [rbp+160h+var_C8], eax
0x18001a81e  lea     rax, [rsp+260h+var_1FC]
0x18001a823  mov     [rbp+160h+var_E0], rax
0x18001a82a  mov     [rbp+160h+var_D0], rbx
0x18001a831  mov     [rbp+160h+var_C4], edx
0x18001a837  mov     [rbp+160h+var_D8], 4
0x18001a842  test    r14, r14
0x18001a845  jz      short loc_18001A865
0x18001a847  mov     rax, rcx
0x18001a84a  nop     word ptr [rax+rax+00h]
0x18001a850  cmp     [r14+rax*2+2], dx
0x18001a856  lea     rax, [rax+1]
0x18001a85a  jnz     short loc_18001A850
0x18001a85c  lea     eax, ds:2[rax*2]
0x18001a863  jmp     short loc_18001A871
0x18001a865  lea     r14, pszDefault
0x18001a86c  mov     eax, 2
0x18001a871  mov     [rbp+160h+var_E8], eax
0x18001a874  lea     rax, [rsp+260h+var_1F8]
0x18001a879  mov     [rbp+160h+var_100], rax
0x18001a87d  mov     [rbp+160h+var_F0], r14
0x18001a881  mov     [rbp+160h+var_E4], edx
0x18001a884  mov     [rbp+160h+var_F8], 4
0x18001a88c  test    r15, r15
0x18001a88f  jz      short loc_18001A8A1
0x18001a891  mov     rax, rcx
0x18001a894  inc     rax
0x18001a897  cmp     [r15+rax], dl
0x18001a89b  jnz     short loc_18001A894
0x18001a89d  inc     eax
0x18001a89f  jmp     short loc_18001A8AD
0x18001a8a1  lea     r15, word_18009494A
0x18001a8a8  mov     eax, 1
0x18001a8ad  mov     [rbp+160h+var_108], eax
0x18001a8b0  lea     rax, [rsp+260h+var_220]
0x18001a8b5  mov     [rbp+160h+var_110], r15
0x18001a8b9  mov     r15, [rsp+260h+arg_10]
0x18001a8c1  mov     [rbp+160h+var_120], rax
0x18001a8c5  mov     [rbp+160h+var_104], edx
0x18001a8c8  mov     [rbp+160h+var_118], 4
0x18001a8d0  test    r12, r12
0x18001a8d3  jz      short loc_18001A8E2
0x18001a8d5  inc     rcx
0x18001a8d8  cmp     [r12+rcx], dl
0x18001a8dc  jnz     short loc_18001A8D5
0x18001a8de  inc     ecx
0x18001a8e0  jmp     short loc_18001A8EE
0x18001a8e2  lea     r12, word_18009494A
0x18001a8e9  mov     ecx, 1
0x18001a8ee  mov     [rbp+160h+var_124], edx
0x18001a8f1  lea     rax, [rsp+260h+var_218]
0x18001a8f6  mov     [rbp+160h+var_140], rax
0x18001a8fa  lea     r8, [rdi+8]; ActivityId
0x18001a8fe  mov     [rbp+160h+EventDescriptor.Keyword], rdx
0x18001a902  lea     rax, [rsp+260h+var_1F0]
0x18001a907  mov     [rbp+160h+var_150], rax
0x18001a90b  lea     rdx, _TraceLoggingMetadata
0x18001a912  mov     [rbp+160h+var_128], ecx
0x18001a915  lea     rax, [rsp+260h+var_210]
0x18001a91a  mov     [rbp+160h+var_160], rax
0x18001a91e  xor     r9d, r9d; RelatedActivityId
0x18001a921  movzx   eax, cs:word_18009E9BE
0x18001a928  mov     dword ptr [rsp+260h+EventDescriptor.Level], eax
0x18001a92c  mov     rax, [r13+8]
0x18001a930  mov     [rbp+160h+var_180.Ptr], rax
0x18001a934  mov     [rbp+160h+var_130], r12
0x18001a938  mov     [rbp+160h+var_138], 4
0x18001a940  mov     [rbp+160h+var_148], 8
0x18001a948  mov     [rbp+160h+var_158], 8
0x18001a950  mov     dword ptr [rsp+260h+EventDescriptor.Id], 0B000000h
0x18001a958  movzx   eax, word ptr [rax]
0x18001a95b  mov     [rbp+160h+var_180.Size], eax
0x18001a95e  lea     rax, unk_18009E9C8
0x18001a965  mov     [rbp+160h+var_170], rax
0x18001a969  lea     rax, _TraceLoggingMetadataEnd
0x18001a970  sub     eax, edx
0x18001a972  mov     dword ptr [rbp+160h+var_180.0Ch], 2
0x18001a979  mov     [rbp+160h+var_168], 142h
0x18001a980  lea     rdx, [rsp+260h+EventDescriptor]; EventDescriptor
0x18001a985  mov     [rbp+160h+var_164], 1
0x18001a98c  mov     dword ptr [rsp+260h+SRWLock], eax
0x18001a990  mov     eax, dword ptr [rsp+260h+SRWLock]
0x18001a994  mov     rcx, [r13+20h]; RegHandle
0x18001a998  lea     rax, [rbp+160h+var_180]
0x18001a99c  mov     [rsp+260h+UserData], rax; UserData
0x18001a9a1  mov     [rsp+260h+UserDataCount], 15h; UserDataCount
0x18001a9a9  call    cs:__imp_EventWriteTransfer
0x18001a9af  mov     r12, [rsp+260h+arg_8]
0x18001a9b7  jmp     loc_18001ABB3
0x18001a9bc  mov     rbx, [rcx+118h]
0x18001a9c3  test    rbx, rbx
0x18001a9c6  jz      short loc_18001AA0D
0x18001a9c8  add     rbx, 108h
  ... truncated ...
```
