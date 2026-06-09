# HTTP_USER_REQUEST::WriteData(uchar * const,ulong,ulong *,int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)

- ea: `0x180039380`
- end: `0x180039ba3`
- name: `?WriteData@HTTP_USER_REQUEST@@QEAAKQEAEKPEAKHP6AXPEAX_KK2K@ZK3@Z`
- size: `2083`
- prototype: `unsigned int __fastcall(HTTP_USER_REQUEST *__hidden this, unsigned __int8 *const, unsigned int, unsigned int *, int, void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int), unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a2b0`

## callees

- `0x18002e6e8`
- `0x180037b20`
- `0x180038e30`
- `0x180039120`
- `0x180039160`
- `0x180039380`
- `0x180062f00`
- `0x18006beb0`
- `0x18008f484`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf1a8`
- `0x1800db704`
- `0x1800db758`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003943e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039555`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003989d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003943e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039555`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003989d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800395b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003986f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800398c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039465`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800395b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003986f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800398c3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003992a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003992a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003993c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003993c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039487`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800398f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800398f5`
- `ntdll!EtwEventActivityIdControl` at `0x1800396b7`
- `ntdll!EtwEventActivityIdControl` at `0x1800396ef`
- `ntdll!EtwEventActivityIdControl` at `0x18003975d`
- `ntdll!EtwEventActivityIdControl` at `0x1800396b7`
- `ntdll!EtwEventActivityIdControl` at `0x1800396ef`
- `ntdll!EtwEventActivityIdControl` at `0x18003975d`

## string_xrefs

- `0x1800394b2`: `WriteData`

## pseudocode

```c
__int64 __fastcall HTTP_USER_REQUEST::WriteData(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned __int8 *const a2,
        unsigned int a3,
        unsigned int *a4,
        int a5,
        void (*a6)(void *, unsigned __int64, unsigned int, void *, unsigned int),
        unsigned int a7,
        unsigned __int64 a8)
{
  unsigned __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 OwningThread_low; // rdx
  void *v16; // rax
  unsigned int v17; // ebx
  _QWORD *p_DebugInfo; // rbp
  void (__fastcall ***SpinCount)(_QWORD); // rcx
  HANDLE_OBJECT *v20; // rbx
  __int64 v21; // rcx
  __int128 *v22; // rax
  __int128 *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  _BYTE *v26; // rax
  int v27; // eax
  bool v28; // sf
  int v29; // eax
  bool v30; // sf
  __int64 v31; // rdx
  ULONG_PTR v32; // rcx
  void (__fastcall *v33)(ULONG_PTR, __int64, __int64, _QWORD, _DWORD); // rax
  int v34; // eax
  bool v35; // sf
  __int64 v36; // rdx
  int v37; // ebx
  void *v38; // rcx
  __int64 v39; // rax
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+60h] [rbp-A8h]
  __int128 v41; // [rsp+70h] [rbp-98h] BYREF
  __int128 v42; // [rsp+80h] [rbp-88h] BYREF
  int v43; // [rsp+90h] [rbp-78h]
  _OWORD v44[2]; // [rsp+A0h] [rbp-68h] BYREF

  if ( a2 )
  {
    if ( !a3 )
    {
LABEL_3:
      if ( (xmmword_180107A50 & 2) != 0 )
        WPP_SF_qqD(513, 80, (unsigned int)WPP_29ecff532d3a35783d73db4432e82274_Traceguids, (_DWORD)this, (__int64)a2);
      return 87;
    }
  }
  else if ( a3 )
  {
    goto LABEL_3;
  }
  if ( !a4 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v36 = 81;
      goto LABEL_65;
    }
    return 87;
  }
  if ( !a5 && !a6 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v36 = 82;
LABEL_65:
      WPP_SF_q(513, v36, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
      return 87;
    }
    return 87;
  }
  if ( a7 && !a6 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v36 = 83;
      goto LABEL_65;
    }
    return 87;
  }
  lpCriticalSection = this + 6;
  v13 = 0;
  EnterCriticalSection(this + 6);
  if ( HIDWORD(this[1].OwningThread) )
  {
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
      WPP_SF_q(769, 84, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    goto LABEL_68;
  }
  OwningThread_low = LODWORD(this[1].OwningThread);
  if ( (unsigned int)(OwningThread_low - 2) > 2 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
    {
      v39 = HTTP_USER_REQUEST::MapState(v14, OwningThread_low);
      WPP_SF_qs(513, 85, (unsigned int)WPP_29ecff532d3a35783d73db4432e82274_Traceguids, (_DWORD)this, v39);
    }
LABEL_55:
    v17 = 12019;
    goto LABEL_56;
  }
  LeaveCriticalSection(this + 6);
  if ( !this[4].SpinCount )
  {
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
      WPP_SF_q(769, 86, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    return 12017;
  }
  v16 = HeapAlloc(g_hWxProcessHeap, 0, 0xB0u);
  v13 = (unsigned __int64)v16;
  if ( !v16 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_q(513, 87, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    return 8;
  }
  memset_0(v16, 0, 0xB0u);
  *(_DWORD *)(v13 + 8) = 1;
  *(_QWORD *)(v13 + 72) = 0;
  *(_QWORD *)(v13 + 16) = "WriteData";
  *(_QWORD *)(v13 + 80) = 0;
  *(_QWORD *)v13 = &PENDING_API_CALL::`vftable';
  *(_DWORD *)(v13 + 124) = 0;
  *(_QWORD *)(v13 + 128) = 0;
  *(_QWORD *)(v13 + 136) = 0;
  *(_QWORD *)(v13 + 168) = 0;
  *(_DWORD *)(v13 + 144) = 0;
  *(_QWORD *)(v13 + 152) = 0;
  *(_QWORD *)(v13 + 160) = 0;
  *(_QWORD *)(v13 + 24) = 4;
  *(_QWORD *)(v13 + 32) = 12004;
  v17 = PENDING_API_CALL::Initialize((PENDING_API_CALL *)v13, a5, 0, a2, a3, 0, 0, 0, a7, a6, a8);
  if ( v17 )
  {
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_q(513, 88, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 8LL))(v13);
    return v17;
  }
  EnterCriticalSection(this + 6);
  if ( !HIDWORD(this[1].OwningThread) )
  {
    if ( this[4].SpinCount )
    {
      p_DebugInfo = &this[7].DebugInfo;
      if ( !this[7].DebugInfo )
      {
        *p_DebugInfo = v13;
        (**(void (__fastcall ***)(unsigned __int64))v13)(v13);
        SpinCount = (void (__fastcall ***)(_QWORD))this[4].SpinCount;
        *(_QWORD *)(v13 + 128) = SpinCount;
        (**SpinCount)(SpinCount);
        LeaveCriticalSection(this + 6);
        v20 = *(HANDLE_OBJECT **)(this->SpinCount + 24);
        if ( (*(unsigned int (__fastcall **)(HANDLE_OBJECT *))(*(_QWORD *)v20 + 8LL))(v20) != 1952804425 )
          v20 = (HANDLE_OBJECT *)*((_QWORD *)v20 + 3);
        if ( (unsigned int)HANDLE_OBJECT::IsInvalidated(v20) )
        {
          if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
            WPP_SF_q(769, 92, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
          HTTP_USER_REQUEST::_TransitToState(this, 5);
          v17 = 12017;
        }
        else
        {
          if ( (*(_BYTE *)(v13 + 56) & 0x30) != 0 )
          {
            v42 = 0;
            v43 = 0;
            if ( !*(_DWORD *)(v13 + 40) || (v37 = *(_DWORD *)(v13 + 44), GetCurrentThreadId() == v37) )
            {
              v21 = 16;
              v22 = &v42;
              do
              {
                *(_BYTE *)v22 = 0;
                v22 = (__int128 *)((char *)v22 + 1);
                --v21;
              }
              while ( v21 );
              v43 = 0;
              v23 = &v42;
              v24 = 16;
              memset(v44, 0, sizeof(v44));
              do
              {
                *(_BYTE *)v23 = 0;
                v23 = (__int128 *)((char *)v23 + 1);
                --v24;
              }
              while ( v24 );
              v41 = 0;
              v25 = 16;
              v26 = v44;
              do
              {
                *v26++ = 0;
                --v25;
              }
              while ( v25 );
              v27 = EtwEventActivityIdControl(1, &v41);
              v28 = v27 < 0;
              if ( v27 > 0 )
                v28 = 1;
              if ( v28 )
                DWORD1(v41) = 128;
              else
                v44[0] = v41;
              DWORD1(v41) = 0;
              v29 = EtwEventActivityIdControl(2, &WinHttpEtwNullActivityId);
              v30 = v29 < 0;
              if ( v29 > 0 )
                v30 = 1;
              if ( v30 )
                DWORD1(v41) = 144;
              v31 = *(_QWORD *)(v13 + 64);
              v32 = this->SpinCount;
              v33 = *(void (__fastcall **)(ULONG_PTR, __int64, __int64, _QWORD, _DWORD))(v13 + 48);
              v42 = v44[0];
              v43 = 1;
              v33(v32, v31, 16, 0, 0);
              if ( v43 )
              {
                DWORD1(v41) = 0;
                v34 = EtwEventActivityIdControl(2, &v42);
                v35 = v34 < 0;
                if ( v34 > 0 )
                  v35 = 1;
                if ( v35 )
                  DWORD1(v41) = 144;
              }
            }
            else
            {
              v38 = *(void **)(v13 + 72);
              *(_QWORD *)(v13 + 152) = 0;
              *(_DWORD *)(v13 + 160) = 0;
              *(_DWORD *)(v13 + 140) = 1;
              *(_DWORD *)(v13 + 144) = 16;
              SetEvent(v38);
              WaitForSingleObjectEx(*(HANDLE *)(v13 + 80), 0xFFFFFFFF, 0);
              *(_QWORD *)(v13 + 140) = 0;
              *(_QWORD *)(v13 + 152) = 0;
              *(_DWORD *)(v13 + 160) = 0;
            }
          }
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->Type)(this);
          (**(void (__fastcall ***)(unsigned __int64))v13)(v13);
          v17 = WEBIO_REQUEST::WriteData(
                  *(WEBIO_REQUEST **)(v13 + 128),
                  a2,
                  a3,
                  a4,
                  v13,
                  *(_DWORD *)(this->SpinCount + 920),
                  0,
                  a3 == 0);
          if ( v17 == 997 )
          {
            if ( *(_DWORD *)(v13 + 40) )
              v17 = HTTP_USER_REQUEST::_HandleSyncPending((HTTP_USER_REQUEST *)this, (struct PENDING_API_CALL *)v13, a4);
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 8LL))(v13);
            return v17;
          }
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 8LL))(v13);
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this->DebugInfo->CriticalSection)(this);
          v17 = HTTP_USER_REQUEST::_PostProcessWriteData(
                  (HTTP_USER_REQUEST *)this,
                  v17,
                  (struct PENDING_API_CALL *)v13,
                  a4);
        }
LABEL_58:
        v17 = HTTP_USER_REQUEST::_CompletePendingCall(this, (struct PENDING_API_CALL *)v13, v17);
        EnterCriticalSection(lpCriticalSection);
        if ( *p_DebugInfo == v13 )
        {
          *p_DebugInfo = 0;
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 8LL))(v13);
        }
        LeaveCriticalSection(lpCriticalSection);
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v13 + 8LL))(v13);
        return v17;
      }
      if ( (xmmword_180107A50 & 2) != 0 )
        WPP_SF_q(513, 91, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
      goto LABEL_55;
    }
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
    {
      WPP_SF_q(769, 90, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
      LODWORD(this[1].OwningThread) = 5;
      v17 = 12017;
      goto LABEL_56;
    }
LABEL_68:
    LODWORD(this[1].OwningThread) = 5;
    v17 = 12017;
    goto LABEL_56;
  }
  if ( (BYTE8(xmmword_180107A50) & 2) == 0 )
    goto LABEL_68;
  WPP_SF_q(769, 89, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
  LODWORD(this[1].OwningThread) = 5;
  v17 = 12017;
LABEL_56:
  LeaveCriticalSection(this + 6);
  if ( v13 )
  {
    p_DebugInfo = &this[7].DebugInfo;
    goto LABEL_58;
  }
  return v17;
}

```

## disassembly

```asm
0x180039380  push    rbx
0x180039382  push    rbp
0x180039383  push    rsi
0x180039384  push    r12
0x180039386  push    r13
0x180039388  push    r14
0x18003938a  push    r15
0x18003938c  sub     rsp, 0D0h
0x180039393  mov     rax, cs:__security_cookie
0x18003939a  xor     rax, rsp
0x18003939d  mov     [rsp+108h+var_48], rax
0x1800393a5  mov     r13, r9
0x1800393a8  mov     r12d, r8d
0x1800393ab  mov     r15, rdx
0x1800393ae  mov     r14, rcx
0x1800393b1  test    rdx, rdx
0x1800393b4  jnz     short loc_1800393F1
0x1800393b6  test    r8d, r8d
0x1800393b9  jz      short loc_1800393F6
0x1800393bb  test    byte ptr cs:xmmword_180107A50, 2
0x1800393c2  jz      short loc_1800393E7
0x1800393c4  mov     edx, 50h ; 'P'
0x1800393c9  mov     [rsp+108h+var_E0], r12d
0x1800393ce  mov     ecx, 201h
0x1800393d3  mov     qword ptr [rsp+108h+var_E8], r15
0x1800393d8  mov     r9, r14
0x1800393db  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x1800393e2  call    WPP_SF_qqD
0x1800393e7  mov     eax, 57h ; 'W'
0x1800393ec  jmp     loc_1800397F3
0x1800393f1  test    r12d, r12d
0x1800393f4  jz      short loc_1800393BB
0x1800393f6  test    r13, r13
0x1800393f9  jz      loc_18003995B
0x1800393ff  mov     esi, [rsp+108h+arg_20]
0x180039406  mov     rbx, [rsp+108h+arg_28]
0x18003940e  test    esi, esi
0x180039410  jz      loc_180039816
0x180039416  mov     ebp, [rsp+108h+arg_30]
0x18003941d  test    ebp, ebp
0x18003941f  jnz     loc_180039836
0x180039425  lea     rax, [rcx+0F0h]
0x18003942c  mov     [rsp+108h+arg_10], rdi
0x180039434  mov     rcx, rax; lpCriticalSection
0x180039437  mov     [rsp+108h+lpCriticalSection], rax
0x18003943c  xor     edi, edi
0x18003943e  call    cs:__imp_EnterCriticalSection
0x180039444  cmp     [r14+3Ch], edi
0x180039448  jnz     loc_180039986
0x18003944e  mov     edx, [r14+38h]
0x180039452  lea     eax, [rdx-2]
0x180039455  cmp     eax, 2
0x180039458  ja      loc_180039856
0x18003945e  lea     rcx, [r14+0F0h]; lpCriticalSection
0x180039465  call    cs:__imp_LeaveCriticalSection
0x18003946b  cmp     [r14+0C0h], rdi
0x180039472  jz      loc_180039A16
0x180039478  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18003947f  xor     edx, edx; dwFlags
0x180039481  mov     r8d, 0B0h; dwBytes
0x180039487  call    cs:__imp_HeapAlloc
0x18003948d  mov     rdi, rax
0x180039490  test    rax, rax
0x180039493  jz      loc_180039B77
0x180039499  xor     edx, edx; Val
0x18003949b  mov     r8d, 0B0h; Size
0x1800394a1  mov     rcx, rax; void *
0x1800394a4  call    memset_0
0x1800394a9  xor     ecx, ecx
0x1800394ab  mov     dword ptr [rdi+8], 1
0x1800394b2  lea     rax, aWritedata; "WriteData"
0x1800394b9  mov     [rdi+48h], rcx
0x1800394bd  mov     [rdi+10h], rax
0x1800394c1  mov     r9, r15; unsigned __int8 *
0x1800394c4  lea     rax, ??_7PENDING_API_CALL@@6B@; const PENDING_API_CALL::`vftable'
0x1800394cb  mov     [rdi+50h], rcx
0x1800394cf  mov     [rdi], rax
0x1800394d2  xor     r8d, r8d; int
0x1800394d5  mov     rax, [rsp+108h+arg_38]
0x1800394dd  mov     edx, esi; int
0x1800394df  mov     [rsp+108h+var_B8], rax; unsigned __int64
0x1800394e4  mov     [rsp+108h+var_C0], rbx; void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x1800394e9  mov     [rsp+108h+var_C8], ebp; unsigned int
0x1800394ed  mov     [rsp+108h+var_D0], ecx; unsigned int
0x1800394f1  mov     [rsp+108h+var_D8], rcx; unsigned __int8 *
0x1800394f6  mov     qword ptr [rsp+108h+var_E0], rcx; unsigned __int64
0x1800394fb  mov     [rdi+7Ch], ecx
0x1800394fe  mov     [rdi+80h], rcx
0x180039505  mov     [rdi+88h], rcx
0x18003950c  mov     [rdi+0A8h], rcx
0x180039513  mov     [rdi+90h], ecx
0x180039519  mov     [rdi+98h], rcx
0x180039520  mov     [rdi+0A0h], rcx
0x180039527  mov     rcx, rdi; this
0x18003952a  mov     qword ptr [rdi+18h], 4
0x180039532  mov     qword ptr [rdi+20h], 2EE4h
0x18003953a  mov     [rsp+108h+var_E8], r12d; unsigned int
0x18003953f  call    ?Initialize@PENDING_API_CALL@@AEAAKHHPEAEK_K0KKP6AXPEAX1K2K@Z1@Z; PENDING_API_CALL::Initialize(int,int,uchar *,ulong,unsigned __int64,uchar *,ulong,ulong,void (*)(void *,unsigned __int64,ulong,void *,ulong),unsigned __int64)
0x180039544  mov     ebx, eax
0x180039546  test    eax, eax
0x180039548  jnz     loc_180039A42
0x18003954e  lea     rcx, [r14+0F0h]; lpCriticalSection
0x180039555  call    cs:__imp_EnterCriticalSection
0x18003955b  cmp     [r14+3Ch], ebx
0x18003955f  jnz     loc_180039A78
0x180039565  cmp     qword ptr [r14+0C0h], 0
0x18003956d  jz      loc_1800399BA
0x180039573  lea     rbp, [r14+118h]
0x18003957a  cmp     qword ptr [rbp+0], 0
0x18003957f  jnz     loc_180039AB0
0x180039585  mov     [rbp+0], rdi
0x180039589  mov     rcx, rdi
0x18003958c  mov     rax, [rdi]
0x18003958f  mov     rax, [rax]
0x180039592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039597  mov     rcx, [r14+0C0h]
0x18003959e  mov     [rdi+80h], rcx
0x1800395a5  mov     rax, [rcx]
0x1800395a8  mov     rax, [rax]
0x1800395ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395b0  lea     rcx, [r14+0F0h]; lpCriticalSection
0x1800395b7  call    cs:__imp_LeaveCriticalSection
0x1800395bd  mov     rax, [r14+20h]
0x1800395c1  mov     rbx, [rax+18h]
0x1800395c5  mov     rcx, rbx
0x1800395c8  mov     rax, [rbx]
0x1800395cb  mov     rax, [rax+8]
0x1800395cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395d4  cmp     eax, 74656E49h
0x1800395d9  jz      short loc_1800395DF
0x1800395db  mov     rbx, [rbx+18h]
0x1800395df  mov     rcx, rbx; this
0x1800395e2  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x1800395e7  test    eax, eax
0x1800395e9  jnz     loc_180039ADB
0x1800395ef  xor     ebx, ebx
0x1800395f1  test    r12d, r12d
0x1800395f4  mov     esi, ebx
0x1800395f6  setz    sil
0x1800395fa  test    byte ptr [rdi+38h], 30h
0x1800395fe  jz      loc_180039777
0x180039604  xor     eax, eax
0x180039606  xorps   xmm0, xmm0
0x180039609  movups  [rsp+108h+var_88], xmm0
0x180039611  mov     [rsp+108h+var_78], eax
0x180039618  cmp     [rdi+28h], eax
0x18003961b  jnz     loc_1800398F2
0x180039621  mov     ecx, 10h
0x180039626  lea     rax, [rsp+108h+var_88]
0x18003962e  xchg    ax, ax
0x180039630  mov     byte ptr [rax], 0
0x180039633  lea     rax, [rax+1]
0x180039637  sub     rcx, 1
0x18003963b  jnz     short loc_180039630
0x18003963d  xorps   xmm0, xmm0
0x180039640  mov     [rsp+108h+var_78], ebx
0x180039647  xorps   xmm1, xmm1
0x18003964a  lea     rax, [rsp+108h+var_88]
0x180039652  movups  [rsp+108h+var_58], xmm0
0x18003965a  mov     ecx, 10h
0x18003965f  movups  [rsp+108h+var_68], xmm1
0x180039667  nop     word ptr [rax+rax+00000000h]
0x180039670  mov     byte ptr [rax], 0
0x180039673  lea     rax, [rax+1]
0x180039677  sub     rcx, 1
0x18003967b  jnz     short loc_180039670
0x18003967d  xorps   xmm0, xmm0
0x180039680  mov     dword ptr [rsp+108h+var_98+4], ebx
0x180039684  movups  xmmword ptr [rsp+70h], xmm0
0x180039689  mov     ecx, 10h
0x18003968e  lea     rax, [rsp+108h+var_68]
0x180039696  nop     word ptr [rax+rax+00000000h]
0x1800396a0  mov     byte ptr [rax], 0
0x1800396a3  lea     rax, [rax+1]
0x1800396a7  sub     rcx, 1
0x1800396ab  jnz     short loc_1800396A0
0x1800396ad  lea     rdx, [rsp+108h+var_98]
0x1800396b2  mov     ecx, 1
0x1800396b7  call    cs:__imp_EtwEventActivityIdControl
0x1800396bd  test    eax, eax
0x1800396bf  jle     short loc_1800396CB
0x1800396c1  movzx   eax, ax
0x1800396c4  or      eax, 80070000h
0x1800396c9  test    eax, eax
0x1800396cb  js      loc_180039B21
0x1800396d1  movaps  xmm0, [rsp+108h+var_98]
0x1800396d6  movdqa  [rsp+108h+var_68], xmm0
0x1800396df  lea     rdx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; _GUID const WinHttpEtwNullActivityId
0x1800396e6  mov     dword ptr [rsp+108h+var_98+4], ebx
0x1800396ea  mov     ecx, 2
0x1800396ef  call    cs:__imp_EtwEventActivityIdControl
0x1800396f5  test    eax, eax
0x1800396f7  jle     short loc_180039703
0x1800396f9  movzx   eax, ax
0x1800396fc  or      eax, 80070000h
0x180039701  test    eax, eax
0x180039703  js      loc_180039B35
0x180039709  movaps  xmm0, [rsp+108h+var_68]
0x180039711  xor     r9d, r9d
0x180039714  mov     rdx, [rdi+40h]
0x180039718  mov     r8d, 10h
0x18003971e  mov     rcx, [r14+20h]
0x180039722  mov     rax, [rdi+30h]
0x180039726  movups  [rsp+108h+var_88], xmm0
0x18003972e  mov     [rsp+108h+var_78], 1
0x180039739  mov     [rsp+108h+var_E8], ebx
0x18003973d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039742  cmp     [rsp+108h+var_78], 0
0x18003974a  jz      short loc_180039777
0x18003974c  lea     rdx, [rsp+108h+var_88]
0x180039754  mov     dword ptr [rsp+108h+var_98+4], ebx
0x180039758  mov     ecx, 2
0x18003975d  call    cs:__imp_EtwEventActivityIdControl
0x180039763  test    eax, eax
0x180039765  jle     short loc_180039771
0x180039767  movzx   eax, ax
0x18003976a  or      eax, 80070000h
0x18003976f  test    eax, eax
0x180039771  js      loc_180039B14
0x180039777  mov     rax, [r14]
0x18003977a  mov     rcx, r14
0x18003977d  mov     rax, [rax]
0x180039780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039785  mov     rax, [rdi]
0x180039788  mov     rcx, rdi
0x18003978b  mov     rax, [rax]
0x18003978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039793  mov     rax, [r14+20h]
0x180039797  mov     r9, r13; unsigned int *
0x18003979a  mov     rcx, [rdi+80h]; this
0x1800397a1  mov     r8d, r12d; unsigned int
0x1800397a4  mov     [rsp+108h+var_D0], esi; int
0x1800397a8  mov     rdx, r15; unsigned __int8 *
0x1800397ab  mov     dword ptr [rsp+108h+var_D8], ebx; int
0x1800397af  mov     eax, [rax+398h]
0x1800397b5  mov     [rsp+108h+var_E0], eax; unsigned int
0x1800397b9  mov     qword ptr [rsp+108h+var_E8], rdi; unsigned __int64
0x1800397be  call    ?WriteData@WEBIO_REQUEST@@QEAAKQEAEKPEAK_KKHH@Z; WEBIO_REQUEST::WriteData(uchar * const,ulong,ulong *,unsigned __int64,ulong,int,int)
0x1800397c3  mov     ebx, eax
0x1800397c5  cmp     eax, 3E5h
0x1800397ca  jnz     loc_180039B42
0x1800397d0  cmp     dword ptr [rdi+28h], 0
0x1800397d4  jnz     loc_1800398DD
0x1800397da  mov     rax, [rdi]
0x1800397dd  mov     rcx, rdi
0x1800397e0  mov     rax, [rax+8]
0x1800397e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397e9  mov     rdi, [rsp+108h+arg_10]
0x1800397f1  mov     eax, ebx
0x1800397f3  mov     rcx, [rsp+108h+var_48]
0x1800397fb  xor     rcx, rsp; StackCookie
0x1800397fe  call    __security_check_cookie
0x180039803  add     rsp, 0D0h
0x18003980a  pop     r15
0x18003980c  pop     r14
0x18003980e  pop     r13
0x180039810  pop     r12
0x180039812  pop     rsi
0x180039813  pop     rbp
0x180039814  pop     rbx
0x180039815  retn
0x180039816  test    rbx, rbx
0x180039819  jnz     loc_180039416
0x18003981f  test    byte ptr cs:xmmword_180107A50, 2
0x180039826  jz      loc_1800393E7
0x18003982c  mov     edx, 52h ; 'R'
0x180039831  jmp     loc_18003996D
0x180039836  test    rbx, rbx
0x180039839  jnz     loc_180039425
0x18003983f  test    byte ptr cs:xmmword_180107A50, 2
0x180039846  jz      loc_1800393E7
0x18003984c  mov     edx, 53h ; 'S'
0x180039851  jmp     loc_18003996D
0x180039856  test    byte ptr cs:xmmword_180107A50, 2
0x18003985d  jnz     loc_1800399EE
0x180039863  mov     ebx, 2EF3h
0x180039868  lea     rcx, [r14+0F0h]; lpCriticalSection
0x18003986f  call    cs:__imp_LeaveCriticalSection
0x180039875  test    rdi, rdi
0x180039878  jz      loc_1800397E9
0x18003987e  lea     rbp, [r14+118h]
0x180039885  mov     r8d, ebx; unsigned int
0x180039888  mov     rdx, rdi; struct PENDING_API_CALL *
0x18003988b  mov     rcx, r14; this
0x18003988e  call    ?_CompletePendingCall@HTTP_USER_REQUEST@@AEAAKPEAVPENDING_API_CALL@@K@Z; HTTP_USER_REQUEST::_CompletePendingCall(PENDING_API_CALL *,ulong)
0x180039893  mov     r14, [rsp+108h+lpCriticalSection]
0x180039898  mov     ebx, eax
0x18003989a  mov     rcx, r14; lpCriticalSection
0x18003989d  call    cs:__imp_EnterCriticalSection
0x1800398a3  cmp     [rbp+0], rdi
0x1800398a7  jnz     short loc_1800398C0
0x1800398a9  mov     qword ptr [rbp+0], 0
0x1800398b1  mov     rcx, rdi
0x1800398b4  mov     rax, [rdi]
0x1800398b7  mov     rax, [rax+8]
0x1800398bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398c0  mov     rcx, r14; lpCriticalSection
0x1800398c3  call    cs:__imp_LeaveCriticalSection
0x1800398c9  mov     rax, [rdi]
0x1800398cc  mov     rcx, rdi
  ... truncated ...
```
