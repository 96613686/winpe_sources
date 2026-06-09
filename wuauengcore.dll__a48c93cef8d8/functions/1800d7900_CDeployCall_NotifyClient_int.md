# CDeployCall::NotifyClient(int *)

- ea: `0x1800d7900`
- end: `0x1800d80e6`
- name: `?NotifyClient@CDeployCall@@UEAAJPEAH@Z`
- size: `2022`
- prototype: `__int64 __fastcall(CDeployCall *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800d7900`
- `0x18011a14c`
- `0x18012b618`
- `0x18012bed4`
- `0x18012bf80`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d796d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d79dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7be6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7fca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d802d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d796d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d79dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7be6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d7fca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d802d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7ff7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d809c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7998`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d7ff7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d809c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7a5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7a5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d7ce2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d7a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d7cd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d7a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d7cd1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800d7a54`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800d7cda`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800d7a54`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800d7cda`

## string_xrefs

- `0x1800d7aac`: `Deploy call %ws : NotifyClient (%d)(%d) called for update id %ws, code = %ws, percent complete = %d`
- `0x1800d7f6c`: `Deploy call %ws : NotifyClient, m_fNoMoreCallbackNeeded = %ws, m_fCallbackNeededForCall = %ws, fNoMorePerUpdateCallbackNeeded = %ws, JobCallbackComplete = %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeployCall::NotifyClient(CDeployCall *this, int *a2)
{
  int *v2; // r14
  int v4; // r15d
  __int64 v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  unsigned int v7; // ecx
  __int64 v8; // r12
  const struct tagDSGlobalUpdateId *v9; // rsi
  unsigned int v10; // ecx
  BOOL v11; // edx
  int v12; // r15d
  __int64 updated; // r14
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  DWORD CurrentThreadId; // edi
  __int64 CallbackCodeAsString; // rax
  __int64 v18; // rdx
  int v19; // r12d
  unsigned int v20; // eax
  _DWORD *v21; // rdx
  __int64 v22; // r8
  __m128i v23; // xmm6
  int v24; // ecx
  int v25; // ecx
  const wchar_t *v26; // rax
  int v27; // eax
  bool v28; // zf
  int v29; // eax
  __int64 v30; // rax
  HANDLE v31; // rax
  int v32; // esi
  DWORD v33; // edi
  __int64 v34; // rax
  __int64 v35; // rdx
  unsigned int v36; // edi
  int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  const wchar_t *v42; // r14
  const wchar_t *v43; // rsi
  const wchar_t *v44; // rdi
  __int64 v45; // rax
  const wchar_t *v46; // rdx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  __int64 v52; // rax
  unsigned int i; // edx
  __int64 v55; // [rsp+40h] [rbp-C8h]
  __int64 v56; // [rsp+48h] [rbp-C0h]
  __int64 v57; // [rsp+48h] [rbp-C0h]
  __int64 v58; // [rsp+60h] [rbp-A8h]
  int v59; // [rsp+68h] [rbp-A0h]
  const wchar_t *v60; // [rsp+68h] [rbp-A0h]
  int v61; // [rsp+68h] [rbp-A0h]
  unsigned int v62; // [rsp+70h] [rbp-98h]
  int v63; // [rsp+74h] [rbp-94h]
  int v64; // [rsp+78h] [rbp-90h]
  struct _GUID v66; // [rsp+88h] [rbp-80h] BYREF
  __int64 v67; // [rsp+98h] [rbp-70h]
  _OWORD v68[8]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v69[7]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v70; // [rsp+198h] [rbp+90h]

  v2 = a2;
  v4 = 0;
  v5 = 0;
  v67 = 0;
  v64 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    goto LABEL_72;
  }
  *a2 = 0;
  if ( !*((_DWORD *)this + 8) )
  {
    v4 = -2147024809;
    goto LABEL_72;
  }
  *((_DWORD *)this + 8) = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 904);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
  if ( *((_QWORD *)this + 122) )
  {
    v5 = *((_QWORD *)this + 122);
    v67 = v5;
    *((_QWORD *)this + 122) = 0;
    *((_DWORD *)this + 20) = 1;
  }
  LeaveCriticalSection(v6);
  if ( !v5 )
  {
    EnterCriticalSection(v6);
    v49 = *((_DWORD *)this + 237);
    if ( v49 == 3 || (v28 = ((v49 - 2) & 0xFFFFFFFD) == 0, v50 = 0, v28) )
      v50 = 1;
    *v2 = v50;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
    goto LABEL_72;
  }
  v7 = 0;
  v59 = 0;
  if ( *((_DWORD *)this + 256) )
  {
    while ( 1 )
    {
      v8 = *((_QWORD *)this + 130) + 144LL * v7;
      if ( *(_DWORD *)v8 )
        break;
LABEL_21:
      if ( *(_DWORD *)(v8 + 4) )
      {
        v59 = ++v7;
        if ( v7 < *((_DWORD *)this + 256) )
          continue;
      }
      v2 = a2;
      goto LABEL_24;
    }
    v9 = (const struct tagDSGlobalUpdateId *)(v8 + 28);
    while ( 1 )
    {
      EnterCriticalSection(v6);
      *(_DWORD *)v8 = 0;
      v10 = *(_DWORD *)(v8 + 24);
      v62 = v10;
      v11 = v10 == 3 || ((v10 - 2) & 0xFFFFFFFD) == 0 || v10 - 6 <= 3;
      *(_DWORD *)(v8 + 4) = v11;
      if ( v10 != 5 || (v63 = 1, *(_DWORD *)(v8 + 136)) )
        v63 = 0;
      v12 = *(unsigned __int16 *)(v8 + 56);
      updated = Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v68, v9);
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      CurrentThreadId = GetCurrentThreadId();
      v66 = *(struct _GUID *)((char *)this + 116);
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
      CallbackCodeAsString = GetCallbackCodeAsString(v62);
      LODWORD(v58) = v12;
      LODWORD(v56) = ThreadPriority;
      LODWORD(v55) = CurrentThreadId;
      WUTrace(
        0,
        0,
        1,
        (unsigned int)(v63 + 4),
        0,
        L"Deploy call %ws : NotifyClient (%d)(%d) called for update id %ws, code = %ws, percent complete = %d",
        v18,
        v55,
        v56,
        updated,
        CallbackCodeAsString,
        v58);
      v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 904);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
      v68[0] = *(_OWORD *)(v8 + 16);
      v68[1] = *(_OWORD *)(v8 + 32);
      v68[2] = *(_OWORD *)(v8 + 48);
      v68[3] = *(_OWORD *)(v8 + 64);
      v68[4] = *(_OWORD *)(v8 + 80);
      v68[5] = *(_OWORD *)(v8 + 96);
      v68[6] = *(_OWORD *)(v8 + 112);
      *(_QWORD *)&v68[7] = *(_QWORD *)(v8 + 128);
      v4 = (*(__int64 (__fastcall **)(__int64, char *, _OWORD *))(*(_QWORD *)v5 + 24LL))(v5, (char *)this + 116, v68);
      if ( v4 < 0 )
        break;
      v9 = (const struct tagDSGlobalUpdateId *)(v8 + 28);
      if ( !*(_DWORD *)v8 )
      {
        v7 = v59;
        goto LABEL_21;
      }
    }
    *(_QWORD *)v8 = 1;
    v27 = *(_DWORD *)(v8 + 104);
    if ( v27 == 3 || (v28 = ((v27 - 2) & 0xFFFFFFFD) == 0, v29 = 0, v28) )
      v29 = 1;
    v2 = a2;
    *a2 = v29;
    v66 = *(struct _GUID *)((char *)this + 116);
    v30 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
    WUTrace(0, 0, 1, 4, v4, L"Deploy call %ws : Failed to call back to client.", v30);
    goto LABEL_72;
  }
LABEL_24:
  v19 = 1;
  v20 = *((_DWORD *)this + 256);
  if ( v20 )
  {
    v21 = (_DWORD *)(*((_QWORD *)this + 130) + 4LL);
    v22 = v20;
    do
    {
      v19 = *v21 != 0 ? v19 : 0;
      v21 += 36;
      --v22;
    }
    while ( v22 );
  }
  if ( *((_DWORD *)this + 242) )
  {
    memset((char *)v68 + 4, 0, 0x74u);
    LODWORD(v68[0]) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
    *(_OWORD *)((char *)&v68[5] + 8) = *(_OWORD *)((char *)this + 948);
    v23 = *(__m128i *)((char *)&v68[5] + 8);
    DWORD2(v68[6]) = *((_DWORD *)this + 241);
    *((_DWORD *)this + 242) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
    v24 = _mm_cvtsi128_si32(_mm_srli_si128(v23, 12));
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 == 1 )
          v26 = (const wchar_t *)"m\x00a\x00n\x00d\x00a\x00t\x00o\x00r\x00y\x00 \x00r\x00e\x00b\x00o\x00o\x00t";
        else
          v26 = L"unknown";
      }
      else
      {
        v26 = L"non mandatory reboot";
      }
    }
    else
    {
      v26 = L"unspecified";
    }
    v60 = v26;
    v31 = GetCurrentThread();
    v32 = GetThreadPriority(v31);
    v33 = GetCurrentThreadId();
    v66 = *(struct _GUID *)((char *)this + 116);
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
    v34 = GetCallbackCodeAsString((unsigned int)_mm_cvtsi128_si32(v23));
    LODWORD(v56) = v32;
    LODWORD(v55) = v33;
    WUTrace(
      0,
      0,
      1,
      4,
      0,
      L"Deploy call %ws : NotifyClient (%d)(%d) called with Deployment callback code = %ws, reboot status = %ws",
      v35,
      v55,
      v56,
      v34,
      v60);
    v36 = _mm_cvtsi128_si32(v23);
    if ( v36 - 2 > 2 || v19 )
    {
      v37 = *((_DWORD *)this + 237);
      if ( (v37 == 3 || ((v37 - 2) & 0xFFFFFFFD) == 0) && *((_DWORD *)this + 243) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 163) + 8LL))(*((_QWORD *)this + 163));
        v64 = 1;
      }
      v69[0] = v68[0];
      v69[1] = v68[1];
      v69[2] = v68[2];
      v69[3] = v68[3];
      v69[4] = v68[4];
      v69[5] = v68[5];
      v69[6] = v68[6];
      v70 = *(_QWORD *)&v68[7];
      v4 = (*(__int64 (__fastcall **)(__int64, char *, _OWORD *))(*(_QWORD *)v5 + 24LL))(v5, (char *)this + 116, v69);
      if ( v4 < 0 )
      {
        *((_DWORD *)this + 242) = 1;
        *v2 = v36 - 2 <= 2;
        v66 = *(struct _GUID *)((char *)this + 116);
        v38 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
        WUTrace(0, 0, 1, 4, v4, L"Deploy call %ws : Failed to callback to client", v38);
        goto LABEL_66;
      }
      v66 = *(struct _GUID *)((char *)this + 116);
      Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
      v39 = GetCallbackCodeAsString(v36);
      LODWORD(v57) = _mm_cvtsi128_si32(_mm_srli_si128(v23, 4));
      WUTrace(0, 0, 1, 4, 0, L"Deploy call %ws : Callback to client with code %ws and error %#lx ", v40, v39, v57);
    }
    else
    {
      *((_DWORD *)this + 242) = 1;
    }
    v41 = *((_DWORD *)this + 237);
    if ( v41 == 3 || (v61 = 0, ((v41 - 2) & 0xFFFFFFFD) == 0) )
      v61 = 1;
    v42 = L"No";
    v43 = L"No";
    if ( *((_DWORD *)this + 242) )
      v43 = L"Yes";
    v44 = L"No";
    if ( *a2 )
      v44 = L"Yes";
    v66 = *(struct _GUID *)((char *)this + 116);
    v45 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v69, &v66);
    v46 = L"No";
    if ( v61 )
      v46 = L"Yes";
    if ( v19 )
      v42 = L"Yes";
    WUTrace(
      0,
      0,
      1,
      5 - (unsigned int)(*((_DWORD *)this + 242) != 0),
      0,
      L"Deploy call %ws : NotifyClient, m_fNoMoreCallbackNeeded = %ws, m_fCallbackNeededForCall = %ws, fNoMorePerUpdateCal"
       "lbackNeeded = %ws, JobCallbackComplete = %ws",
      v45,
      v44,
      v43,
      v42,
      v46);
    if ( !v19
      || (v47 = *((_DWORD *)this + 237), v47 != 3) && ((v47 - 2) & 0xFFFFFFFD) != 0
      || (v48 = 1, *((_DWORD *)this + 242)) )
    {
      v48 = 0;
    }
    v2 = a2;
    *a2 = v48;
LABEL_66:
    if ( v64 )
      goto LABEL_75;
  }
LABEL_72:
  v51 = *((_DWORD *)this + 237);
  if ( v51 == 3 || ((v51 - 2) & 0xFFFFFFFD) == 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 163) + 8LL))(*((_QWORD *)this + 163));
LABEL_75:
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
  if ( !*((_DWORD *)this + 21) && !*((_QWORD *)this + 122) )
  {
    v52 = v5;
    v5 = 0;
    *((_QWORD *)this + 122) = v52;
  }
  *((_QWORD *)this + 10) = 0;
  if ( *v2 )
  {
    for ( i = 0; i < *((_DWORD *)this + 256); ++i )
      *(_DWORD *)(*((_QWORD *)this + 130) + 144LL * i + 4) = 1;
    *((_DWORD *)this + 242) = 0;
    *((_DWORD *)this + 8) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 904));
  if ( v4 == -2147418110 )
    v5 = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d7900  mov     rax, rsp
0x1800d7903  mov     [rax+18h], rbx
0x1800d7907  push    rbp
0x1800d7908  push    rsi
0x1800d7909  push    rdi
0x1800d790a  push    r12
0x1800d790c  push    r13
0x1800d790e  push    r14
0x1800d7910  push    r15
0x1800d7912  lea     rbp, [rax-0E8h]
0x1800d7919  sub     rsp, 1B0h
0x1800d7920  movaps  xmmword ptr [rax-48h], xmm6
0x1800d7924  mov     r14, rdx
0x1800d7927  mov     [rsp+1E0h+var_168], rdx
0x1800d792c  mov     r13, rcx
0x1800d792f  xor     esi, esi
0x1800d7931  mov     r15d, esi
0x1800d7934  mov     ebx, esi
0x1800d7936  mov     [rbp+0E0h+var_150], rbx
0x1800d793a  mov     dword ptr [rsp+1E0h+var_170], esi
0x1800d793e  test    rdx, rdx
0x1800d7941  jnz     short loc_1800D794E
0x1800d7943  mov     r15d, 80004003h
0x1800d7949  jmp     loc_1800D7FFD
0x1800d794e  mov     [rdx], esi
0x1800d7950  cmp     [rcx+20h], esi
0x1800d7953  jnz     short loc_1800D7960
0x1800d7955  mov     r15d, 80070057h
0x1800d795b  jmp     loc_1800D7FFD
0x1800d7960  mov     [rcx+20h], esi
0x1800d7963  lea     rdi, [rcx+388h]
0x1800d796a  mov     rcx, rdi; lpCriticalSection
0x1800d796d  call    cs:__imp_EnterCriticalSection
0x1800d7973  mov     rax, [r13+3D0h]
0x1800d797a  test    rax, rax
0x1800d797d  jz      short loc_1800D7995
0x1800d797f  mov     rbx, rax
0x1800d7982  mov     [rbp+0E0h+var_150], rax
0x1800d7986  mov     [r13+3D0h], rsi
0x1800d798d  mov     dword ptr [r13+50h], 1
0x1800d7995  mov     rcx, rdi; lpCriticalSection
0x1800d7998  call    cs:__imp_LeaveCriticalSection
0x1800d799e  test    rbx, rbx
0x1800d79a1  jz      loc_1800D7FC7
0x1800d79a7  mov     ecx, esi
0x1800d79a9  mov     dword ptr [rsp+1E0h+var_180], ecx
0x1800d79ad  cmp     [r13+400h], esi
0x1800d79b4  jbe     loc_1800D7B87
0x1800d79ba  mov     eax, ecx
0x1800d79bc  lea     r12, [rax+rax*8]
0x1800d79c0  shl     r12, 4
0x1800d79c4  add     r12, [r13+410h]
0x1800d79cb  cmp     [r12], esi
0x1800d79cf  jz      loc_1800D7B68
0x1800d79d5  lea     rsi, [r12+1Ch]
0x1800d79da  mov     rcx, rdi; lpCriticalSection
0x1800d79dd  call    cs:__imp_EnterCriticalSection
0x1800d79e3  xor     r8d, r8d
0x1800d79e6  mov     [r12], r8d
0x1800d79ea  mov     ecx, [r12+18h]
0x1800d79ef  mov     [rsp+1E0h+var_178], ecx
0x1800d79f3  cmp     ecx, 3
0x1800d79f6  jz      short loc_1800D7A10
0x1800d79f8  lea     eax, [rcx-2]
0x1800d79fb  test    eax, 0FFFFFFFDh
0x1800d7a00  jz      short loc_1800D7A10
0x1800d7a02  lea     eax, [rcx-6]
0x1800d7a05  mov     edx, r8d
0x1800d7a08  cmp     eax, 3
0x1800d7a0b  setbe   dl
0x1800d7a0e  jmp     short loc_1800D7A15
0x1800d7a10  mov     edx, 1
0x1800d7a15  mov     [r12+4], edx
0x1800d7a1a  cmp     ecx, 5
0x1800d7a1d  jnz     short loc_1800D7A31
0x1800d7a1f  mov     [rsp+1E0h+var_174], 1
0x1800d7a27  cmp     [r12+88h], r8d
0x1800d7a2f  jz      short loc_1800D7A36
0x1800d7a31  mov     [rsp+1E0h+var_174], r8d
0x1800d7a36  movzx   r15d, word ptr [r12+38h]
0x1800d7a3c  mov     rdx, rsi; struct tagDSGlobalUpdateId *
0x1800d7a3f  lea     rcx, [rbp+0E0h+var_140]; this
0x1800d7a43  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800d7a48  mov     r14, rax
0x1800d7a4b  call    cs:__imp_GetCurrentThread
0x1800d7a51  mov     rcx, rax; hThread
0x1800d7a54  call    cs:__imp_GetThreadPriority
0x1800d7a5a  mov     esi, eax
0x1800d7a5c  call    cs:__imp_GetCurrentThreadId
0x1800d7a62  mov     edi, eax
0x1800d7a64  movups  xmm0, xmmword ptr [r13+74h]
0x1800d7a69  movdqu  xmmword ptr [rbp+0E0h+var_160.Data1], xmm0
0x1800d7a6e  lea     rdx, [rbp+0E0h+var_160]; struct _GUID *
0x1800d7a72  lea     rcx, [rbp+0E0h+var_C0]; this
0x1800d7a76  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800d7a7b  mov     rdx, rax
0x1800d7a7e  mov     ecx, [rsp+1E0h+var_178]
0x1800d7a82  call    ?GetCallbackCodeAsString@@YAPEB_WW4tagCallbackCode@@@Z; GetCallbackCodeAsString(tagCallbackCode)
0x1800d7a87  mov     r9d, [rsp+1E0h+var_174]
0x1800d7a8c  add     r9d, 4
0x1800d7a90  mov     dword ptr [rsp+1E0h+var_188], r15d
0x1800d7a95  mov     qword ptr [rsp+1E0h+var_190], rax
0x1800d7a9a  mov     [rsp+1E0h+var_198], r14
0x1800d7a9f  mov     dword ptr [rsp+1E0h+var_1A0], esi
0x1800d7aa3  mov     dword ptr [rsp+1E0h+var_1A8], edi
0x1800d7aa7  mov     [rsp+1E0h+var_1B0], rdx
0x1800d7aac  lea     rax, aDeployCallWsNo_1; "Deploy call %ws : NotifyClient (%d)(%d)"...
0x1800d7ab3  mov     [rsp+1E0h+var_1B8], rax
0x1800d7ab8  xor     esi, esi
0x1800d7aba  mov     [rsp+1E0h+var_1C0], rsi
0x1800d7abf  xor     edx, edx
0x1800d7ac1  xor     ecx, ecx
0x1800d7ac3  lea     r8d, [rsi+1]
0x1800d7ac7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800d7acc  lea     rdi, [r13+388h]
0x1800d7ad3  mov     rcx, rdi; lpCriticalSection
0x1800d7ad6  call    cs:__imp_LeaveCriticalSection
0x1800d7adc  movups  xmm0, xmmword ptr [r12+10h]
0x1800d7ae2  movaps  [rbp+0E0h+var_140], xmm0
0x1800d7ae6  movups  xmm1, xmmword ptr [r12+20h]
0x1800d7aec  movaps  [rbp+0E0h+var_130], xmm1
0x1800d7af0  movups  xmm0, xmmword ptr [r12+30h]
0x1800d7af6  movaps  [rbp+0E0h+var_120], xmm0
0x1800d7afa  movups  xmm1, xmmword ptr [r12+40h]
0x1800d7b00  movaps  [rbp+0E0h+var_110], xmm1
0x1800d7b04  movups  xmm0, xmmword ptr [r12+50h]
0x1800d7b0a  movaps  [rbp+0E0h+var_100], xmm0
0x1800d7b0e  movups  xmm1, xmmword ptr [r12+60h]
0x1800d7b14  movaps  [rbp+0E0h+var_F0], xmm1
0x1800d7b18  movups  xmm0, xmmword ptr [r12+70h]
0x1800d7b1e  movaps  [rbp+0E0h+var_E0], xmm0
0x1800d7b22  movsd   xmm1, qword ptr [r12+80h]
0x1800d7b2c  movsd   [rbp+0E0h+var_D0], xmm1
0x1800d7b31  mov     rax, [rbx]
0x1800d7b34  lea     r8, [rbp+0E0h+var_140]
0x1800d7b38  lea     rdx, [r13+74h]
0x1800d7b3c  mov     rcx, rbx
0x1800d7b3f  mov     rax, [rax+18h]
0x1800d7b43  call    _guard_dispatch_icall
0x1800d7b48  mov     r15d, eax
0x1800d7b4b  test    eax, eax
0x1800d7b4d  js      loc_1800D7C45
0x1800d7b53  cmp     [r12], esi
0x1800d7b57  lea     rsi, [r12+1Ch]
0x1800d7b5c  jnz     loc_1800D79DA
0x1800d7b62  mov     ecx, dword ptr [rsp+1E0h+var_180]
0x1800d7b66  xor     esi, esi
0x1800d7b68  cmp     [r12+4], esi
0x1800d7b6d  jz      short loc_1800D7B82
0x1800d7b6f  inc     ecx
0x1800d7b71  mov     dword ptr [rsp+1E0h+var_180], ecx
0x1800d7b75  cmp     ecx, [r13+400h]
0x1800d7b7c  jb      loc_1800D79BA
0x1800d7b82  mov     r14, [rsp+1E0h+var_168]
0x1800d7b87  mov     r12d, 1
0x1800d7b8d  mov     eax, [r13+400h]
0x1800d7b94  test    eax, eax
0x1800d7b96  jz      short loc_1800D7BBC
0x1800d7b98  mov     rdx, [r13+410h]
0x1800d7b9f  add     rdx, 4
0x1800d7ba3  mov     r8d, eax
0x1800d7ba6  mov     eax, [rdx]
0x1800d7ba8  neg     eax
0x1800d7baa  sbb     ecx, ecx
0x1800d7bac  and     r12d, ecx
0x1800d7baf  lea     rdx, [rdx+90h]
0x1800d7bb6  sub     r8, 1
0x1800d7bba  jnz     short loc_1800D7BA6
0x1800d7bbc  cmp     [r13+3C8h], esi
0x1800d7bc3  jz      loc_1800D7FFD
0x1800d7bc9  xor     edx, edx; Val
0x1800d7bcb  lea     r8d, [rdx+74h]; Size
0x1800d7bcf  lea     rcx, [rbp+0E0h+var_140+4]; void *
0x1800d7bd3  call    memset
0x1800d7bd8  mov     dword ptr [rbp+0E0h+var_140], 1
0x1800d7bdf  lea     rcx, [r13+388h]; lpCriticalSection
0x1800d7be6  call    cs:__imp_EnterCriticalSection
0x1800d7bec  movups  xmm6, xmmword ptr [r13+3B4h]
0x1800d7bf4  movups  [rbp+0E0h+var_F0+8], xmm6
0x1800d7bf8  mov     eax, [r13+3C4h]
0x1800d7bff  mov     dword ptr [rbp+0E0h+var_E0+8], eax
0x1800d7c02  mov     [r13+3C8h], esi
0x1800d7c09  lea     rcx, [r13+388h]; lpCriticalSection
0x1800d7c10  call    cs:__imp_LeaveCriticalSection
0x1800d7c16  movdqa  xmm0, xmm6
0x1800d7c1a  psrldq  xmm0, 0Ch
0x1800d7c1f  movd    ecx, xmm0
0x1800d7c23  test    ecx, ecx
0x1800d7c25  jz      loc_1800D7CC5
0x1800d7c2b  sub     ecx, 1
0x1800d7c2e  jz      loc_1800D7CBC
0x1800d7c34  cmp     ecx, 1
0x1800d7c37  jz      short loc_1800D7CB3
0x1800d7c39  lea     rax, aUnknown_2; "unknown"
0x1800d7c40  jmp     loc_1800D7CCC
0x1800d7c45  mov     qword ptr [r12], 1
0x1800d7c4d  mov     eax, [r12+68h]
0x1800d7c52  cmp     eax, 3
0x1800d7c55  jz      short loc_1800D7C63
0x1800d7c57  add     eax, 0FFFFFFFEh
0x1800d7c5a  test    eax, 0FFFFFFFDh
0x1800d7c5f  mov     eax, esi
0x1800d7c61  jnz     short loc_1800D7C68
0x1800d7c63  mov     eax, 1
0x1800d7c68  mov     r14, [rsp+1E0h+var_168]
0x1800d7c6d  mov     [r14], eax
0x1800d7c70  movups  xmm0, xmmword ptr [r13+74h]
0x1800d7c75  movdqu  xmmword ptr [rbp+0E0h+var_160.Data1], xmm0
0x1800d7c7a  lea     rdx, [rbp+0E0h+var_160]; struct _GUID *
0x1800d7c7e  lea     rcx, [rbp+0E0h+var_C0]; this
0x1800d7c82  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800d7c87  mov     [rsp+1E0h+var_1B0], rax
0x1800d7c8c  lea     rax, aDeployCallWsFa_0; "Deploy call %ws : Failed to call back t"...
0x1800d7c93  mov     [rsp+1E0h+var_1B8], rax
0x1800d7c98  mov     dword ptr [rsp+1E0h+var_1C0], r15d
0x1800d7c9d  xor     edx, edx
0x1800d7c9f  xor     ecx, ecx
0x1800d7ca1  lea     r9d, [rdx+4]
0x1800d7ca5  lea     r8d, [rdx+1]
0x1800d7ca9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800d7cae  jmp     loc_1800D7FFD
0x1800d7cb3  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; "m\x00a\x00n\x00d\x00a\x00t\x00o\x00r"...
0x1800d7cba  jmp     short loc_1800D7CCC
0x1800d7cbc  lea     rax, aNonMandatoryRe; "non mandatory reboot"
0x1800d7cc3  jmp     short loc_1800D7CCC
0x1800d7cc5  lea     rax, aUnspecified; "unspecified"
0x1800d7ccc  mov     [rsp+1E0h+var_180], rax
0x1800d7cd1  call    cs:__imp_GetCurrentThread
0x1800d7cd7  mov     rcx, rax; hThread
0x1800d7cda  call    cs:__imp_GetThreadPriority
0x1800d7ce0  mov     esi, eax
0x1800d7ce2  call    cs:__imp_GetCurrentThreadId
0x1800d7ce8  mov     edi, eax
0x1800d7cea  movups  xmm0, xmmword ptr [r13+74h]
0x1800d7cef  movdqu  xmmword ptr [rbp+0E0h+var_160.Data1], xmm0
0x1800d7cf4  lea     rdx, [rbp+0E0h+var_160]; struct _GUID *
0x1800d7cf8  lea     rcx, [rbp+0E0h+var_C0]; this
0x1800d7cfc  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800d7d01  mov     rdx, rax
0x1800d7d04  movd    [rsp+1E0h+var_178], xmm6
0x1800d7d0a  movd    ecx, xmm6
0x1800d7d0e  call    ?GetCallbackCodeAsString@@YAPEB_WW4tagCallbackCode@@@Z; GetCallbackCodeAsString(tagCallbackCode)
0x1800d7d13  mov     rcx, [rsp+1E0h+var_180]
0x1800d7d18  mov     qword ptr [rsp+1E0h+var_190], rcx
0x1800d7d1d  mov     [rsp+1E0h+var_198], rax
0x1800d7d22  mov     dword ptr [rsp+1E0h+var_1A0], esi
0x1800d7d26  mov     dword ptr [rsp+1E0h+var_1A8], edi
0x1800d7d2a  mov     [rsp+1E0h+var_1B0], rdx
0x1800d7d2f  lea     rax, aDeployCallWsNo_0; "Deploy call %ws : NotifyClient (%d)(%d)"...
0x1800d7d36  mov     [rsp+1E0h+var_1B8], rax
0x1800d7d3b  xor     esi, esi
0x1800d7d3d  mov     [rsp+1E0h+var_1C0], rsi
0x1800d7d42  xor     edx, edx
0x1800d7d44  xor     ecx, ecx
0x1800d7d46  lea     r9d, [rsi+4]
0x1800d7d4a  lea     r8d, [rsi+1]
0x1800d7d4e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800d7d53  mov     edi, [rsp+1E0h+var_178]
0x1800d7d57  lea     eax, [rdi-2]
0x1800d7d5a  cmp     eax, 2
0x1800d7d5d  ja      short loc_1800D7D74
0x1800d7d5f  test    r12d, r12d
0x1800d7d62  jnz     short loc_1800D7D74
0x1800d7d64  mov     dword ptr [r13+3C8h], 1
0x1800d7d6f  jmp     loc_1800D7EC4
0x1800d7d74  mov     eax, [r13+3B4h]
0x1800d7d7b  cmp     eax, 3
0x1800d7d7e  jz      short loc_1800D7D8A
0x1800d7d80  add     eax, 0FFFFFFFEh
0x1800d7d83  test    eax, 0FFFFFFFDh
0x1800d7d88  jnz     short loc_1800D7DAE
0x1800d7d8a  cmp     [r13+3CCh], esi
0x1800d7d91  jz      short loc_1800D7DAE
0x1800d7d93  mov     rcx, [r13+518h]
0x1800d7d9a  mov     rax, [rcx]
0x1800d7d9d  mov     rax, [rax+8]
0x1800d7da1  call    _guard_dispatch_icall
0x1800d7da6  mov     dword ptr [rsp+1E0h+var_170], 1
0x1800d7dae  movaps  xmm0, [rbp+0E0h+var_140]
0x1800d7db2  movaps  [rbp+0E0h+var_C0], xmm0
0x1800d7db6  movaps  xmm1, [rbp+0E0h+var_130]
0x1800d7dba  movaps  [rbp+0E0h+var_B0], xmm1
0x1800d7dbe  movaps  xmm0, [rbp+0E0h+var_120]
0x1800d7dc2  movaps  [rbp+0E0h+var_A0], xmm0
0x1800d7dc6  movaps  xmm1, [rbp+0E0h+var_110]
0x1800d7dca  movaps  [rbp+0E0h+var_90], xmm1
0x1800d7dce  movaps  xmm0, [rbp+0E0h+var_100]
0x1800d7dd2  movaps  [rbp+0E0h+var_80], xmm0
0x1800d7dd6  movaps  xmm1, [rbp+0E0h+var_F0]
0x1800d7dda  movaps  [rbp+0E0h+var_70], xmm1
0x1800d7dde  movaps  xmm0, [rbp+0E0h+var_E0]
0x1800d7de2  movaps  [rbp+0E0h+var_60], xmm0
0x1800d7de9  movsd   xmm1, [rbp+0E0h+var_D0]
0x1800d7dee  movsd   [rbp+0E0h+var_50], xmm1
0x1800d7df6  lea     rdx, [r13+74h]
0x1800d7dfa  mov     rax, [rbx]
0x1800d7dfd  lea     r8, [rbp+0E0h+var_C0]
0x1800d7e01  mov     rcx, rbx
0x1800d7e04  mov     rax, [rax+18h]
0x1800d7e08  call    _guard_dispatch_icall
  ... truncated ...
```
