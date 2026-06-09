# ThumbnailCacheTelemetry::CheckRecreateFileMapping::StopActivity(void)

- ea: `0x1800329f0`
- end: `0x180033009`
- name: `?StopActivity@CheckRecreateFileMapping@ThumbnailCacheTelemetry@@MEAAXXZ`
- size: `1561`
- prototype: `void __fastcall(ThumbnailCacheTelemetry::CheckRecreateFileMapping *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18001f1c0`
- `0x180027890`
- `0x1800329f0`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032efc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032efc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032a79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032a94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032aae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ebb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ed5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032a79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032a94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032aae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ea0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ebb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032ed5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032a61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032e88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032a61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032e88`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180032fcc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180032fcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThumbnailCacheTelemetry::CheckRecreateFileMapping::StopActivity(
        ThumbnailCacheTelemetry::CheckRecreateFileMapping *this)
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
  char *v52; // [rsp+90h] [rbp-70h]
  int v53; // [rsp+98h] [rbp-68h]
  int v54; // [rsp+9Ch] [rbp-64h]
  PSRWLOCK *v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  PSRWLOCK *v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *p_SRWLock; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v62; // [rsp+E0h] [rbp-20h]
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
        v62 = &word_18005766E;
        v63 = 327;
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
    v52 = byte_180057615;
    v53 = 77;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v37 + 32), &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_61:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ThumbnailCacheTelemetry::CheckRecreateFileMapping *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800329f0  push    rbp
0x1800329f2  push    rbx
0x1800329f3  push    rsi
0x1800329f4  push    rdi
0x1800329f5  push    r12
0x1800329f7  push    r13
0x1800329f9  push    r14
0x1800329fb  push    r15
0x1800329fd  lea     rbp, [rsp-138h]
0x180032a05  sub     rsp, 238h
0x180032a0c  mov     rax, cs:__security_cookie
0x180032a13  xor     rax, rsp
0x180032a16  mov     [rbp+170h+var_50], rax
0x180032a1d  mov     rsi, rcx
0x180032a20  xor     r14d, r14d
0x180032a23  mov     rdi, [rcx+110h]
0x180032a2a  mov     eax, [rdi+48h]
0x180032a2d  test    eax, eax
0x180032a2f  jns     loc_180032E72
0x180032a35  add     rdi, 50h ; 'P'
0x180032a39  cmp     eax, [rdi+8]
0x180032a3c  jnz     loc_180032E72
0x180032a42  mov     rbx, [rcx+118h]
0x180032a49  test    rdi, rdi
0x180032a4c  jz      loc_180032E79
0x180032a52  test    rbx, rbx
0x180032a55  jz      short loc_180032A9C
0x180032a57  add     rbx, 108h
0x180032a5e  mov     rcx, rbx; SRWLock
0x180032a61  call    cs:__imp_AcquireSRWLockExclusive
0x180032a67  lea     rax, [rsp+270h+SRWLock]
0x180032a6c  mov     [rax], r14
0x180032a6f  mov     rcx, [rsp+270h+SRWLock]; SRWLock
0x180032a74  test    rcx, rcx
0x180032a77  jz      short loc_180032A7F
0x180032a79  call    cs:__imp_ReleaseSRWLockExclusive
0x180032a7f  mov     rax, [rsi+110h]
0x180032a86  mov     dword ptr [rax], 2
0x180032a8c  test    rbx, rbx
0x180032a8f  jz      short loc_180032AC1
0x180032a91  mov     rcx, rbx; SRWLock
0x180032a94  call    cs:__imp_ReleaseSRWLockExclusive
0x180032a9a  jmp     short loc_180032AC1
0x180032a9c  lea     rax, [rsp+270h+var_230]
0x180032aa1  mov     [rax], r14
0x180032aa4  mov     rcx, [rsp+270h+var_230]; SRWLock
0x180032aa9  test    rcx, rcx
0x180032aac  jz      short loc_180032AB4
0x180032aae  call    cs:__imp_ReleaseSRWLockExclusive
0x180032ab4  mov     rax, [rsi+110h]
0x180032abb  mov     dword ptr [rax], 2
0x180032ac1  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x180032ac6  mov     r13, [rax+8]
0x180032aca  mov     eax, [r13+0]
0x180032ace  cmp     eax, 5
0x180032ad1  jbe     loc_180032FD3
0x180032ad7  mov     rdx, [rdi+30h]
0x180032adb  mov     eax, [rdi+44h]
0x180032ade  mov     [rsp+270h+var_220], eax
0x180032ae2  mov     eax, [rdi+10h]
0x180032ae5  mov     [rsp+270h+var_21C], eax
0x180032ae9  mov     r8, [rdi+78h]
0x180032aed  mov     r9, [rdi+70h]
0x180032af1  mov     eax, [rdi+68h]
0x180032af4  mov     [rsp+270h+var_218], eax
0x180032af8  mov     r10, [rdi+60h]
0x180032afc  mov     r11, [rdi+58h]
0x180032b00  mov     eax, [rdi+50h]
0x180032b03  mov     [rsp+270h+var_214], eax
0x180032b07  mov     rbx, [rdi+48h]
0x180032b0b  mov     eax, [rdi+20h]
0x180032b0e  mov     [rsp+270h+var_210], eax
0x180032b12  mov     r14, [rdi+18h]
0x180032b16  mov     eax, [rdi]
0x180032b18  mov     [rsp+270h+var_20C], eax
0x180032b1c  mov     r15, [rdi+80h]
0x180032b23  mov     eax, [rdi+40h]
0x180032b26  mov     [rsp+270h+var_240], eax
0x180032b2a  mov     r12, [rdi+38h]
0x180032b2e  mov     eax, [rdi+8]
0x180032b31  mov     dword ptr [rsp+270h+var_230], eax
0x180032b35  mov     [rsp+270h+var_208], 1000000h
0x180032b3e  mov     [rsp+270h+var_228], 0
0x180032b47  mov     rdi, [rsi+110h]
0x180032b4e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032b55  test    rdx, rdx
0x180032b58  jz      short loc_180032B6D
0x180032b5a  mov     rax, rcx
0x180032b5d  nop     dword ptr [rax]
0x180032b60  inc     rax
0x180032b63  cmp     byte ptr [rdx+rax], 0
0x180032b67  jnz     short loc_180032B60
0x180032b69  inc     eax
0x180032b6b  jmp     short loc_180032B79
0x180032b6d  lea     rdx, qword_180050CF0
0x180032b74  mov     eax, 1
0x180032b79  mov     [rbp+170h+var_60], rdx
0x180032b80  mov     [rbp+170h+var_58], eax
0x180032b86  xor     edx, edx
0x180032b88  mov     [rbp+170h+var_54], edx
0x180032b8e  lea     rax, [rsp+270h+var_220]
0x180032b93  mov     [rbp+170h+var_70], rax
0x180032b9a  mov     [rbp+170h+var_68], 4
0x180032ba5  lea     rax, [rsp+270h+var_21C]
0x180032baa  mov     [rbp+170h+var_80], rax
0x180032bb1  mov     [rbp+170h+var_78], 4
0x180032bbc  test    r8, r8
0x180032bbf  jz      short loc_180032BD8
0x180032bc1  mov     rax, rcx
0x180032bc4  lea     rax, [rax+1]
0x180032bc8  cmp     [r8+rax*2], dx
0x180032bcd  jnz     short loc_180032BC4
0x180032bcf  lea     eax, ds:2[rax*2]
0x180032bd6  jmp     short loc_180032BE4
0x180032bd8  lea     r8, qword_1800509F8
0x180032bdf  mov     eax, 2
0x180032be4  mov     [rbp+170h+var_90], r8
0x180032beb  mov     [rbp+170h+var_88], eax
0x180032bf1  mov     [rbp+170h+var_84], edx
0x180032bf7  test    r9, r9
0x180032bfa  jz      short loc_180032C0D
0x180032bfc  mov     rax, rcx
0x180032bff  nop
0x180032c00  inc     rax
0x180032c03  cmp     [r9+rax], dl
0x180032c07  jnz     short loc_180032C00
0x180032c09  inc     eax
0x180032c0b  jmp     short loc_180032C19
0x180032c0d  lea     r9, qword_180050CF0
0x180032c14  mov     eax, 1
0x180032c19  mov     [rbp+170h+var_A0], r9
0x180032c20  mov     [rbp+170h+var_98], eax
0x180032c26  mov     [rbp+170h+var_94], edx
0x180032c2c  lea     rax, [rsp+270h+var_218]
0x180032c31  mov     [rbp+170h+var_B0], rax
0x180032c38  mov     [rbp+170h+var_A8], 4
0x180032c43  test    r10, r10
0x180032c46  jz      short loc_180032C64
0x180032c48  mov     rax, rcx
0x180032c4b  nop     dword ptr [rax+rax+00h]
0x180032c50  lea     rax, [rax+1]
0x180032c54  cmp     [r10+rax*2], dx
0x180032c59  jnz     short loc_180032C50
0x180032c5b  lea     eax, ds:2[rax*2]
0x180032c62  jmp     short loc_180032C70
0x180032c64  lea     r10, qword_1800509F8
0x180032c6b  mov     eax, 2
0x180032c70  mov     [rbp+170h+var_C0], r10
0x180032c77  mov     [rbp+170h+var_B8], eax
0x180032c7d  mov     [rbp+170h+var_B4], edx
0x180032c83  test    r11, r11
0x180032c86  jz      short loc_180032C9D
0x180032c88  mov     rax, rcx
0x180032c8b  nop     dword ptr [rax+rax+00h]
0x180032c90  inc     rax
0x180032c93  cmp     [r11+rax], dl
0x180032c97  jnz     short loc_180032C90
0x180032c99  inc     eax
0x180032c9b  jmp     short loc_180032CA9
0x180032c9d  lea     r11, qword_180050CF0
0x180032ca4  mov     eax, 1
0x180032ca9  mov     [rbp+170h+var_D0], r11
0x180032cb0  mov     [rbp+170h+var_C8], eax
0x180032cb6  mov     [rbp+170h+var_C4], edx
0x180032cbc  lea     rax, [rsp+270h+var_214]
0x180032cc1  mov     [rbp+170h+var_E0], rax
0x180032cc8  mov     [rbp+170h+var_D8], 4
0x180032cd3  test    rbx, rbx
0x180032cd6  jz      short loc_180032CEC
0x180032cd8  mov     rax, rcx
0x180032cdb  nop     dword ptr [rax+rax+00h]
0x180032ce0  inc     rax
0x180032ce3  cmp     [rbx+rax], dl
0x180032ce6  jnz     short loc_180032CE0
0x180032ce8  inc     eax
0x180032cea  jmp     short loc_180032CF8
0x180032cec  lea     rbx, qword_180050CF0
0x180032cf3  mov     eax, 1
0x180032cf8  mov     [rbp+170h+var_F0], rbx
0x180032cff  mov     [rbp+170h+var_E8], eax
0x180032d05  mov     [rbp+170h+var_E4], edx
0x180032d0b  lea     rax, [rsp+270h+var_210]
0x180032d10  mov     [rbp+170h+var_100], rax
0x180032d14  mov     [rbp+170h+var_F8], 4
0x180032d1c  test    r14, r14
0x180032d1f  jz      short loc_180032D38
0x180032d21  mov     rax, rcx
0x180032d24  lea     rax, [rax+1]
0x180032d28  cmp     [r14+rax*2], dx
0x180032d2d  jnz     short loc_180032D24
0x180032d2f  lea     eax, ds:2[rax*2]
0x180032d36  jmp     short loc_180032D44
0x180032d38  lea     r14, qword_1800509F8
0x180032d3f  mov     eax, 2
0x180032d44  mov     [rbp+170h+var_110], r14
0x180032d48  mov     [rbp+170h+var_108], eax
0x180032d4b  mov     [rbp+170h+var_104], edx
0x180032d4e  lea     rax, [rsp+270h+var_20C]
0x180032d53  mov     [rbp+170h+var_120], rax
0x180032d57  mov     [rbp+170h+var_118], 4
0x180032d5f  test    r15, r15
0x180032d62  jz      short loc_180032D74
0x180032d64  mov     rax, rcx
0x180032d67  inc     rax
0x180032d6a  cmp     [r15+rax], dl
0x180032d6e  jnz     short loc_180032D67
0x180032d70  inc     eax
0x180032d72  jmp     short loc_180032D80
0x180032d74  lea     r15, qword_180050CF0
0x180032d7b  mov     eax, 1
0x180032d80  mov     [rbp+170h+var_130], r15
0x180032d84  mov     [rbp+170h+var_128], eax
0x180032d87  mov     [rbp+170h+var_124], edx
0x180032d8a  lea     rax, [rsp+270h+var_240]
0x180032d8f  mov     [rbp+170h+var_140], rax
0x180032d93  mov     [rbp+170h+var_138], 4
0x180032d9b  test    r12, r12
0x180032d9e  jz      short loc_180032DAD
0x180032da0  inc     rcx
0x180032da3  cmp     [r12+rcx], dl
0x180032da7  jnz     short loc_180032DA0
0x180032da9  inc     ecx
0x180032dab  jmp     short loc_180032DB9
0x180032dad  lea     r12, qword_180050CF0
0x180032db4  mov     ecx, 1
0x180032db9  mov     [rbp+170h+var_150], r12
0x180032dbd  mov     [rbp+170h+var_148], ecx
0x180032dc0  mov     [rbp+170h+var_144], edx
0x180032dc3  lea     rax, [rsp+270h+var_230]
0x180032dc8  mov     [rbp+170h+var_160], rax
0x180032dcc  mov     [rbp+170h+var_158], 4
0x180032dd4  lea     rax, [rsp+270h+var_208]
0x180032dd9  mov     [rbp+170h+var_170], rax
0x180032ddd  mov     [rbp+170h+var_168], 8
0x180032de5  lea     rax, [rsp+270h+var_228]
0x180032dea  mov     [rbp+170h+var_180], rax
0x180032dee  mov     [rbp+170h+var_178], 8
0x180032df6  mov     dword ptr [rsp+270h+EventDescriptor.Id], 0B000000h
0x180032dfe  movzx   eax, cs:word_180057664
0x180032e05  mov     dword ptr [rsp+270h+EventDescriptor.Level], eax
0x180032e09  mov     [rsp+270h+EventDescriptor.Keyword], rdx
0x180032e0e  mov     rax, [r13+8]
0x180032e12  mov     [rbp+170h+var_1A0], rax
0x180032e16  movzx   eax, word ptr [rax]
0x180032e19  mov     [rbp+170h+var_198], eax
0x180032e1c  mov     [rbp+170h+var_194], 2
0x180032e23  lea     rax, word_18005766E
0x180032e2a  mov     [rbp+170h+var_190], rax
0x180032e2e  mov     [rbp+170h+var_188], 147h
0x180032e35  mov     [rbp+170h+var_184], 1
0x180032e3c  lea     rax, _TraceLoggingMetadataEnd
0x180032e43  lea     rdx, _TraceLoggingMetadata
0x180032e4a  sub     eax, edx
0x180032e4c  mov     dword ptr [rsp+270h+SRWLock], eax
0x180032e50  mov     eax, dword ptr [rsp+270h+SRWLock]
0x180032e54  lea     rax, [rbp+170h+var_1A0]
0x180032e58  mov     [rsp+270h+UserData], rax
0x180032e5d  mov     [rsp+270h+UserDataCount], 15h
0x180032e65  lea     r8, [rdi+8]
0x180032e69  mov     rcx, [r13+20h]
0x180032e6d  jmp     loc_180032FC4
0x180032e72  mov     rbx, [rcx+118h]
0x180032e79  test    rbx, rbx
0x180032e7c  jz      short loc_180032EC3
0x180032e7e  add     rbx, 108h
0x180032e85  mov     rcx, rbx; SRWLock
0x180032e88  call    cs:__imp_AcquireSRWLockExclusive
0x180032e8e  lea     rax, [rsp+270h+var_228]
0x180032e93  mov     [rax], r14
0x180032e96  mov     rcx, [rsp+270h+var_228]; SRWLock
0x180032e9b  test    rcx, rcx
0x180032e9e  jz      short loc_180032EA6
0x180032ea0  call    cs:__imp_ReleaseSRWLockExclusive
0x180032ea6  mov     rax, [rsi+110h]
0x180032ead  mov     dword ptr [rax], 2
0x180032eb3  test    rbx, rbx
0x180032eb6  jz      short loc_180032EE8
0x180032eb8  mov     rcx, rbx; SRWLock
0x180032ebb  call    cs:__imp_ReleaseSRWLockExclusive
0x180032ec1  jmp     short loc_180032EE8
0x180032ec3  lea     rax, [rsp+270h+var_208]
0x180032ec8  mov     [rax], r14
0x180032ecb  mov     rcx, [rsp+270h+var_208]; SRWLock
0x180032ed0  test    rcx, rcx
0x180032ed3  jz      short loc_180032EDB
0x180032ed5  call    cs:__imp_ReleaseSRWLockExclusive
0x180032edb  mov     rax, [rsi+110h]
0x180032ee2  mov     dword ptr [rax], 2
0x180032ee8  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x180032eed  mov     rbx, [rax+8]
0x180032ef1  mov     eax, [rbx]
0x180032ef3  cmp     eax, 5
0x180032ef6  jbe     loc_180032FD3
0x180032efc  call    cs:__imp_GetCurrentThreadId
0x180032f02  mov     dword ptr [rsp+270h+SRWLock], eax
0x180032f06  mov     r8, [rsi+110h]
0x180032f0d  mov     eax, [r8+48h]
0x180032f11  mov     dword ptr [rsp+270h+var_230], eax
0x180032f15  mov     [rsp+270h+var_228], r14
0x180032f1a  lea     rax, [rsp+270h+SRWLock]
  ... truncated ...
```
