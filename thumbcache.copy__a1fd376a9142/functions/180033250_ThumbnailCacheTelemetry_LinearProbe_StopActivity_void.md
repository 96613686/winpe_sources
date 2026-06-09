# ThumbnailCacheTelemetry::LinearProbe::StopActivity(void)

- ea: `0x180033250`
- end: `0x180033869`
- name: `?StopActivity@LinearProbe@ThumbnailCacheTelemetry@@MEAAXXZ`
- size: `1561`
- prototype: `void __fastcall(ThumbnailCacheTelemetry::LinearProbe *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001f1c0`
- `0x180027890`
- `0x180033250`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003375c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003375c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003330e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033700`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003371b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033735`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800332f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003330e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033700`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003371b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033735`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800332c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800336e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800332c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800336e8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003382c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003382c`

## pseudocode

```c
void __fastcall ThumbnailCacheTelemetry::LinearProbe::StopActivity(ThumbnailCacheTelemetry::LinearProbe *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // r13
  const unsigned __int16 *v8; // rdx
  __int64 *v9; // r8
  const unsigned __int16 *v10; // r9
  __int64 *v11; // r10
  const unsigned __int16 *v12; // r11
  const unsigned __int16 *v13; // rbx
  __int64 *v14; // r14
  const unsigned __int16 *v15; // r15
  const unsigned __int16 *v16; // r12
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // ecx
  RTL_SRWLOCK *v36; // rbx
  __int64 v37; // rbx
  __int64 v38; // r8
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v41; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+54h] [rbp-ACh] BYREF
  int v45; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  int v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+64h] [rbp-9Ch] BYREF
  PSRWLOCK v49; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+80h] [rbp-80h] BYREF
  int *v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+98h] [rbp-68h]
  int v54; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  void *v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+E8h] [rbp-18h]
  int v64; // [rsp+ECh] [rbp-14h]
  PSRWLOCK *v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  PSRWLOCK *v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v71; // [rsp+120h] [rbp+20h]
  int v72; // [rsp+128h] [rbp+28h]
  int v73; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v74; // [rsp+130h] [rbp+30h]
  __int64 v75; // [rsp+138h] [rbp+38h]
  const unsigned __int16 *v76; // [rsp+140h] [rbp+40h]
  int v77; // [rsp+148h] [rbp+48h]
  int v78; // [rsp+14Ch] [rbp+4Ch]
  int *v79; // [rsp+150h] [rbp+50h]
  __int64 v80; // [rsp+158h] [rbp+58h]
  __int64 *v81; // [rsp+160h] [rbp+60h]
  int v82; // [rsp+168h] [rbp+68h]
  int v83; // [rsp+16Ch] [rbp+6Ch]
  int *v84; // [rsp+170h] [rbp+70h]
  __int64 v85; // [rsp+178h] [rbp+78h]
  const unsigned __int16 *v86; // [rsp+180h] [rbp+80h]
  int v87; // [rsp+188h] [rbp+88h]
  int v88; // [rsp+18Ch] [rbp+8Ch]
  int *v89; // [rsp+190h] [rbp+90h]
  __int64 v90; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v91; // [rsp+1A0h] [rbp+A0h]
  int v92; // [rsp+1A8h] [rbp+A8h]
  int v93; // [rsp+1ACh] [rbp+ACh]
  __int64 *v94; // [rsp+1B0h] [rbp+B0h]
  int v95; // [rsp+1B8h] [rbp+B8h]
  int v96; // [rsp+1BCh] [rbp+BCh]
  int *v97; // [rsp+1C0h] [rbp+C0h]
  __int64 v98; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v99; // [rsp+1D0h] [rbp+D0h]
  int v100; // [rsp+1D8h] [rbp+D8h]
  int v101; // [rsp+1DCh] [rbp+DCh]
  __int64 *v102; // [rsp+1E0h] [rbp+E0h]
  int v103; // [rsp+1E8h] [rbp+E8h]
  int v104; // [rsp+1ECh] [rbp+ECh]
  int *v105; // [rsp+1F0h] [rbp+F0h]
  __int64 v106; // [rsp+1F8h] [rbp+F8h]
  int *v107; // [rsp+200h] [rbp+100h]
  __int64 v108; // [rsp+208h] [rbp+108h]
  const unsigned __int16 *v109; // [rsp+210h] [rbp+110h]
  int v110; // [rsp+218h] [rbp+118h]
  int v111; // [rsp+21Ch] [rbp+11Ch]

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) )
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
        v41 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      v7 = *((_QWORD *)ThumbnailCacheLogging::Instance() + 1);
      if ( *(_DWORD *)v7 > 5u )
      {
        v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        v43 = v4[17];
        v44 = v4[4];
        v9 = (__int64 *)*((_QWORD *)v4 + 15);
        v10 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v45 = v4[26];
        v11 = (__int64 *)*((_QWORD *)v4 + 12);
        v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v46 = v4[20];
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v47 = v4[8];
        v14 = (__int64 *)*((_QWORD *)v4 + 3);
        v48 = *v4;
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v39 = v4[16];
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(v41) = v4[2];
        v49 = (PSRWLOCK)0x1000000;
        v42 = 0;
        v17 = *((_QWORD *)this + 34);
        v18 = -1;
        if ( v8 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_BYTE *)v8 + v19) );
          v20 = v19 + 1;
        }
        else
        {
          v8 = &qword_180050CF0;
          v20 = 1;
        }
        v109 = v8;
        v110 = v20;
        v111 = 0;
        v107 = &v43;
        v108 = 4;
        v105 = &v44;
        v106 = 4;
        if ( v9 )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_WORD *)v9 + v21) );
          v22 = 2 * v21 + 2;
        }
        else
        {
          v9 = &qword_1800509F8;
          v22 = 2;
        }
        v102 = v9;
        v103 = v22;
        v104 = 0;
        if ( v10 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *((_BYTE *)v10 + v23) );
          v24 = v23 + 1;
        }
        else
        {
          v10 = &qword_180050CF0;
          v24 = 1;
        }
        v99 = v10;
        v100 = v24;
        v101 = 0;
        v97 = &v45;
        v98 = 4;
        if ( v11 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *((_WORD *)v11 + v25) );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v11 = &qword_1800509F8;
          v26 = 2;
        }
        v94 = v11;
        v95 = v26;
        v96 = 0;
        if ( v12 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_BYTE *)v12 + v27) );
          v28 = v27 + 1;
        }
        else
        {
          v12 = &qword_180050CF0;
          v28 = 1;
        }
        v91 = v12;
        v92 = v28;
        v93 = 0;
        v89 = &v46;
        v90 = 4;
        if ( v13 )
        {
          v29 = -1;
          do
            ++v29;
          while ( *((_BYTE *)v13 + v29) );
          v30 = v29 + 1;
        }
        else
        {
          v13 = &qword_180050CF0;
          v30 = 1;
        }
        v86 = v13;
        v87 = v30;
        v88 = 0;
        v84 = &v47;
        v85 = 4;
        if ( v14 )
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)v14 + v31) );
          v32 = 2 * v31 + 2;
        }
        else
        {
          v14 = &qword_1800509F8;
          v32 = 2;
        }
        v81 = v14;
        v82 = v32;
        v83 = 0;
        v79 = &v48;
        v80 = 4;
        if ( v15 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *((_BYTE *)v15 + v33) );
          v34 = v33 + 1;
        }
        else
        {
          v15 = &qword_180050CF0;
          v34 = 1;
        }
        v76 = v15;
        v77 = v34;
        v78 = 0;
        v74 = &v39;
        v75 = 4;
        if ( v16 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v16 + v18) );
          v35 = v18 + 1;
        }
        else
        {
          v16 = &qword_180050CF0;
          v35 = 1;
        }
        v71 = v16;
        v72 = v35;
        v73 = 0;
        v69 = &v41;
        v70 = 4;
        v67 = &v49;
        v68 = 8;
        v65 = &v42;
        v66 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = *(_QWORD *)(v7 + 8);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v62 = &unk_180057850;
        v63 = 314;
        v64 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v17 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_61;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v36 = v5 + 33;
    AcquireSRWLockExclusive(v36);
    v42 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v36 )
      ReleaseSRWLockExclusive(v36);
  }
  else
  {
    v49 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  v37 = *((_QWORD *)ThumbnailCacheLogging::Instance() + 1);
  if ( *(_DWORD *)v37 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v38 = *((_QWORD *)this + 34);
    LODWORD(v41) = *(_DWORD *)(v38 + 72);
    v42 = 0;
    p_SRWLock = &SRWLock;
    v60 = 4;
    v57 = &v41;
    v58 = 4;
    v55 = &v42;
    v56 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 0;
    v51.Ptr = *(_QWORD *)(v37 + 8);
    v51.Size = *(unsigned __int16 *)v51.Ptr;
    v51.Reserved = 2;
    v52 = &dword_180057804;
    v53 = 64;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ThumbnailCacheTelemetry::LinearProbe *)((char *)this + 288));
}

```

## disassembly

```asm
0x180033250  push    rbp
0x180033252  push    rbx
0x180033253  push    rsi
0x180033254  push    rdi
0x180033255  push    r12
0x180033257  push    r13
0x180033259  push    r14
0x18003325b  push    r15
0x18003325d  lea     rbp, [rsp-138h]
0x180033265  sub     rsp, 238h
0x18003326c  mov     rax, cs:__security_cookie
0x180033273  xor     rax, rsp
0x180033276  mov     [rbp+170h+var_50], rax
0x18003327d  mov     rsi, rcx
0x180033280  xor     r14d, r14d
0x180033283  mov     rdi, [rcx+110h]
0x18003328a  mov     eax, [rdi+48h]
0x18003328d  test    eax, eax
0x18003328f  jns     loc_1800336D2
0x180033295  add     rdi, 50h ; 'P'
0x180033299  cmp     eax, [rdi+8]
0x18003329c  jnz     loc_1800336D2
0x1800332a2  mov     rbx, [rcx+118h]
0x1800332a9  test    rdi, rdi
0x1800332ac  jz      loc_1800336D9
0x1800332b2  test    rbx, rbx
0x1800332b5  jz      short loc_1800332FC
0x1800332b7  add     rbx, 108h
0x1800332be  mov     rcx, rbx; SRWLock
0x1800332c1  call    cs:__imp_AcquireSRWLockExclusive
0x1800332c7  lea     rax, [rsp+270h+SRWLock]
0x1800332cc  mov     [rax], r14
0x1800332cf  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x1800332d4  test    rcx, rcx
0x1800332d7  jz      short loc_1800332DF
0x1800332d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800332df  mov     rax, [rsi+110h]
0x1800332e6  mov     dword ptr [rax], 2
0x1800332ec  test    rbx, rbx
0x1800332ef  jz      short loc_180033321
0x1800332f1  mov     rcx, rbx; SRWLock
0x1800332f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800332fa  jmp     short loc_180033321
0x1800332fc  lea     rax, [rsp+270h+var_230]
0x180033301  mov     [rax], r14
0x180033304  mov     rcx, [rsp+270h+var_230]; SRWLock
0x180033309  test    rcx, rcx
0x18003330c  jz      short loc_180033314
0x18003330e  call    cs:__imp_ReleaseSRWLockExclusive
0x180033314  mov     rax, [rsi+110h]
0x18003331b  mov     dword ptr [rax], 2
0x180033321  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x180033326  mov     r13, [rax+8]
0x18003332a  mov     eax, [r13+0]
0x18003332e  cmp     eax, 5
0x180033331  jbe     loc_180033833
0x180033337  mov     rdx, [rdi+30h]
0x18003333b  mov     eax, [rdi+44h]
0x18003333e  mov     [rsp+270h+var_220], eax
0x180033342  mov     eax, [rdi+10h]
0x180033345  mov     [rsp+270h+var_21C], eax
0x180033349  mov     r8, [rdi+78h]
0x18003334d  mov     r9, [rdi+70h]
0x180033351  mov     eax, [rdi+68h]
0x180033354  mov     [rsp+270h+var_218], eax
0x180033358  mov     r10, [rdi+60h]
0x18003335c  mov     r11, [rdi+58h]
0x180033360  mov     eax, [rdi+50h]
0x180033363  mov     [rsp+270h+var_214], eax
0x180033367  mov     rbx, [rdi+48h]
0x18003336b  mov     eax, [rdi+20h]
0x18003336e  mov     [rsp+270h+var_210], eax
0x180033372  mov     r14, [rdi+18h]
0x180033376  mov     eax, [rdi]
0x180033378  mov     [rsp+270h+var_20C], eax
0x18003337c  mov     r15, [rdi+80h]
0x180033383  mov     eax, [rdi+40h]
0x180033386  mov     [rsp+270h+var_240], eax
0x18003338a  mov     r12, [rdi+38h]
0x18003338e  mov     eax, [rdi+8]
0x180033391  mov     dword ptr [rsp+270h+var_230], eax
0x180033395  mov     [rsp+270h+var_208], 1000000h
0x18003339e  mov     [rsp+270h+var_228], 0
0x1800333a7  mov     rdi, [rsi+110h]
0x1800333ae  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800333b5  test    rdx, rdx
0x1800333b8  jz      short loc_1800333CD
0x1800333ba  mov     rax, rcx
0x1800333bd  nop     dword ptr [rax]
0x1800333c0  inc     rax
0x1800333c3  cmp     byte ptr [rdx+rax], 0
0x1800333c7  jnz     short loc_1800333C0
0x1800333c9  inc     eax
0x1800333cb  jmp     short loc_1800333D9
0x1800333cd  lea     rdx, qword_180050CF0
0x1800333d4  mov     eax, 1
0x1800333d9  mov     [rbp+170h+var_60], rdx
0x1800333e0  mov     [rbp+170h+var_58], eax
0x1800333e6  xor     edx, edx
0x1800333e8  mov     [rbp+170h+var_54], edx
0x1800333ee  lea     rax, [rsp+270h+var_220]
0x1800333f3  mov     [rbp+170h+var_70], rax
0x1800333fa  mov     [rbp+170h+var_68], 4
0x180033405  lea     rax, [rsp+270h+var_21C]
0x18003340a  mov     [rbp+170h+var_80], rax
0x180033411  mov     [rbp+170h+var_78], 4
0x18003341c  test    r8, r8
0x18003341f  jz      short loc_180033438
0x180033421  mov     rax, rcx
0x180033424  lea     rax, [rax+1]
0x180033428  cmp     [r8+rax*2], dx
0x18003342d  jnz     short loc_180033424
0x18003342f  lea     eax, ds:2[rax*2]
0x180033436  jmp     short loc_180033444
0x180033438  lea     r8, qword_1800509F8
0x18003343f  mov     eax, 2
0x180033444  mov     [rbp+170h+var_90], r8
0x18003344b  mov     [rbp+170h+var_88], eax
0x180033451  mov     [rbp+170h+var_84], edx
0x180033457  test    r9, r9
0x18003345a  jz      short loc_18003346D
0x18003345c  mov     rax, rcx
0x18003345f  nop
0x180033460  inc     rax
0x180033463  cmp     [r9+rax], dl
0x180033467  jnz     short loc_180033460
0x180033469  inc     eax
0x18003346b  jmp     short loc_180033479
0x18003346d  lea     r9, qword_180050CF0
0x180033474  mov     eax, 1
0x180033479  mov     [rbp+170h+var_A0], r9
0x180033480  mov     [rbp+170h+var_98], eax
0x180033486  mov     [rbp+170h+var_94], edx
0x18003348c  lea     rax, [rsp+270h+var_218]
0x180033491  mov     [rbp+170h+var_B0], rax
0x180033498  mov     [rbp+170h+var_A8], 4
0x1800334a3  test    r10, r10
0x1800334a6  jz      short loc_1800334C4
0x1800334a8  mov     rax, rcx
0x1800334ab  nop     dword ptr [rax+rax+00h]
0x1800334b0  lea     rax, [rax+1]
0x1800334b4  cmp     [r10+rax*2], dx
0x1800334b9  jnz     short loc_1800334B0
0x1800334bb  lea     eax, ds:2[rax*2]
0x1800334c2  jmp     short loc_1800334D0
0x1800334c4  lea     r10, qword_1800509F8
0x1800334cb  mov     eax, 2
0x1800334d0  mov     [rbp+170h+var_C0], r10
0x1800334d7  mov     [rbp+170h+var_B8], eax
0x1800334dd  mov     [rbp+170h+var_B4], edx
0x1800334e3  test    r11, r11
0x1800334e6  jz      short loc_1800334FD
0x1800334e8  mov     rax, rcx
0x1800334eb  nop     dword ptr [rax+rax+00h]
0x1800334f0  inc     rax
0x1800334f3  cmp     [r11+rax], dl
0x1800334f7  jnz     short loc_1800334F0
0x1800334f9  inc     eax
0x1800334fb  jmp     short loc_180033509
0x1800334fd  lea     r11, qword_180050CF0
0x180033504  mov     eax, 1
0x180033509  mov     [rbp+170h+var_D0], r11
0x180033510  mov     [rbp+170h+var_C8], eax
0x180033516  mov     [rbp+170h+var_C4], edx
0x18003351c  lea     rax, [rsp+270h+var_214]
0x180033521  mov     [rbp+170h+var_E0], rax
0x180033528  mov     [rbp+170h+var_D8], 4
0x180033533  test    rbx, rbx
0x180033536  jz      short loc_18003354C
0x180033538  mov     rax, rcx
0x18003353b  nop     dword ptr [rax+rax+00h]
0x180033540  inc     rax
0x180033543  cmp     [rbx+rax], dl
0x180033546  jnz     short loc_180033540
0x180033548  inc     eax
0x18003354a  jmp     short loc_180033558
0x18003354c  lea     rbx, qword_180050CF0
0x180033553  mov     eax, 1
0x180033558  mov     [rbp+170h+var_F0], rbx
0x18003355f  mov     [rbp+170h+var_E8], eax
0x180033565  mov     [rbp+170h+var_E4], edx
0x18003356b  lea     rax, [rsp+270h+var_210]
0x180033570  mov     [rbp+170h+var_100], rax
0x180033574  mov     [rbp+170h+var_F8], 4
0x18003357c  test    r14, r14
0x18003357f  jz      short loc_180033598
0x180033581  mov     rax, rcx
0x180033584  lea     rax, [rax+1]
0x180033588  cmp     [r14+rax*2], dx
0x18003358d  jnz     short loc_180033584
0x18003358f  lea     eax, ds:2[rax*2]
0x180033596  jmp     short loc_1800335A4
0x180033598  lea     r14, qword_1800509F8
0x18003359f  mov     eax, 2
0x1800335a4  mov     [rbp+170h+var_110], r14
0x1800335a8  mov     [rbp+170h+var_108], eax
0x1800335ab  mov     [rbp+170h+var_104], edx
0x1800335ae  lea     rax, [rsp+270h+var_20C]
0x1800335b3  mov     [rbp+170h+var_120], rax
0x1800335b7  mov     [rbp+170h+var_118], 4
0x1800335bf  test    r15, r15
0x1800335c2  jz      short loc_1800335D4
0x1800335c4  mov     rax, rcx
0x1800335c7  inc     rax
0x1800335ca  cmp     [r15+rax], dl
0x1800335ce  jnz     short loc_1800335C7
0x1800335d0  inc     eax
0x1800335d2  jmp     short loc_1800335E0
0x1800335d4  lea     r15, qword_180050CF0
0x1800335db  mov     eax, 1
0x1800335e0  mov     [rbp+170h+var_130], r15
0x1800335e4  mov     [rbp+170h+var_128], eax
0x1800335e7  mov     [rbp+170h+var_124], edx
0x1800335ea  lea     rax, [rsp+270h+var_240]
0x1800335ef  mov     [rbp+170h+var_140], rax
0x1800335f3  mov     [rbp+170h+var_138], 4
0x1800335fb  test    r12, r12
0x1800335fe  jz      short loc_18003360D
0x180033600  inc     rcx
0x180033603  cmp     [r12+rcx], dl
0x180033607  jnz     short loc_180033600
0x180033609  inc     ecx
0x18003360b  jmp     short loc_180033619
0x18003360d  lea     r12, qword_180050CF0
0x180033614  mov     ecx, 1
0x180033619  mov     [rbp+170h+var_150], r12
0x18003361d  mov     [rbp+170h+var_148], ecx
0x180033620  mov     [rbp+170h+var_144], edx
0x180033623  lea     rax, [rsp+270h+var_230]
0x180033628  mov     [rbp+170h+var_160], rax
0x18003362c  mov     [rbp+170h+var_158], 4
0x180033634  lea     rax, [rsp+270h+var_208]
0x180033639  mov     [rbp+170h+var_170], rax
0x18003363d  mov     [rbp+170h+var_168], 8
0x180033645  lea     rax, [rsp+270h+var_228]
0x18003364a  mov     [rbp+170h+var_180], rax
0x18003364e  mov     [rbp+170h+var_178], 8
0x180033656  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x18003365e  movzx   eax, cs:word_180057846
0x180033665  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x180033669  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x18003366e  mov     rax, [r13+8]
0x180033672  mov     [rbp+170h+var_1A0], rax
0x180033676  movzx   eax, word ptr [rax]
0x180033679  mov     [rbp+170h+var_198], eax
0x18003367c  mov     [rbp+170h+var_194], 2
0x180033683  lea     rax, unk_180057850
0x18003368a  mov     [rbp+170h+var_190], rax
0x18003368e  mov     [rbp+170h+var_188], 13Ah
0x180033695  mov     [rbp+170h+var_184], 1
0x18003369c  lea     rax, _TraceLoggingMetadataEnd
0x1800336a3  lea     rdx, _TraceLoggingMetadata
0x1800336aa  sub     eax, edx
0x1800336ac  mov     dword ptr [rsp+270h+SRWLock], eax
0x1800336b0  mov     eax, dword ptr [rsp+270h+SRWLock]
0x1800336b4  lea     rax, [rbp+170h+var_1A0]
0x1800336b8  mov     [rsp+270h+UserData], rax
0x1800336bd  mov     [rsp+270h+UserDataCount], 15h
0x1800336c5  lea     r8, [rdi+8]
0x1800336c9  mov     rcx, [r13+20h]
0x1800336cd  jmp     loc_180033824
0x1800336d2  mov     rbx, [rcx+118h]
0x1800336d9  test    rbx, rbx
0x1800336dc  jz      short loc_180033723
0x1800336de  add     rbx, 108h
0x1800336e5  mov     rcx, rbx; SRWLock
0x1800336e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800336ee  lea     rax, [rsp+270h+var_228]
0x1800336f3  mov     [rax], r14
0x1800336f6  mov     rcx, [rsp+270h+var_228]; SRWLock
0x1800336fb  test    rcx, rcx
0x1800336fe  jz      short loc_180033706
0x180033700  call    cs:__imp_ReleaseSRWLockExclusive
0x180033706  mov     rax, [rsi+110h]
0x18003370d  mov     dword ptr [rax], 2
0x180033713  test    rbx, rbx
0x180033716  jz      short loc_180033748
0x180033718  mov     rcx, rbx; SRWLock
0x18003371b  call    cs:__imp_ReleaseSRWLockExclusive
0x180033721  jmp     short loc_180033748
0x180033723  lea     rax, [rsp+270h+var_208]
0x180033728  mov     [rax], r14
0x18003372b  mov     rcx, [rsp+270h+var_208]; SRWLock
0x180033730  test    rcx, rcx
0x180033733  jz      short loc_18003373B
0x180033735  call    cs:__imp_ReleaseSRWLockExclusive
0x18003373b  mov     rax, [rsi+110h]
0x180033742  mov     dword ptr [rax], 2
0x180033748  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x18003374d  mov     rbx, [rax+8]
0x180033751  mov     eax, [rbx]
0x180033753  cmp     eax, 5
0x180033756  jbe     loc_180033833
0x18003375c  call    cs:__imp_GetCurrentThreadId
0x180033762  mov     dword ptr [rsp+270h+SRWLock], eax
0x180033766  mov     r8, [rsi+110h]
0x18003376d  mov     eax, [r8+48h]
0x180033771  mov     dword ptr [rsp+270h+var_230], eax
0x180033775  mov     [rsp+270h+var_228], r14
0x18003377a  lea     rax, [rsp+270h+SRWLock]
  ... truncated ...
```
