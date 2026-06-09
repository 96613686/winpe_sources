# NtUserInitializeGenericHidInjection

- ea: `0x1401db9a0`
- end: `0x1401dbded`
- name: `NtUserInitializeGenericHidInjection`
- size: `1101`
- prototype: `__int64 __fastcall(_OWORD *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140029710`
- `0x140049ec0`
- `0x14004c020`
- `0x14004f4c0`
- `0x14006f3a4`
- `0x1400700d8`
- `0x1400701d4`
- `0x14007b930`
- `0x14007df80`
- `0x1401aab9c`
- `0x1401b1258`
- `0x1401db9a0`
- `0x14020409c`
- `0x140238a40`
- `0x140238f80`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401dbb55`
- `ntoskrnl!ProbeForRead` at `0x1401dbbc1`
- `ntoskrnl!ProbeForRead` at `0x1401dbc03`
- `ntoskrnl!ProbeForRead` at `0x1401dbb55`
- `ntoskrnl!ProbeForRead` at `0x1401dbbc1`
- `ntoskrnl!ProbeForRead` at `0x1401dbc03`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbb2e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbb9d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbbde`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbb2e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbb9d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dbbde`
- `WIN32K!W32GetUserSessionState` at `0x1401db9d0`
- `WIN32K!W32GetUserSessionState` at `0x1401dbad6`
- `WIN32K!W32GetUserSessionState` at `0x1401db9d0`
- `WIN32K!W32GetUserSessionState` at `0x1401dbad6`

## pseudocode

```c
__int64 __fastcall NtUserInitializeGenericHidInjection(_OWORD *a1, __int64 a2)
{
  int v3; // r14d
  __int64 UserSessionState; // rdi
  __int64 v5; // rax
  _QWORD *v6; // r15
  char v7; // r13
  bool v8; // bl
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  __int64 CurrentProcessWow64Process; // rax
  __m128i v13; // xmm7
  __m128i v14; // xmm6
  __int64 v15; // rax
  void *v16; // r12
  unsigned __int16 epi16; // di
  __int64 v18; // rax
  void *v19; // r15
  unsigned __int64 v20; // rcx
  void *v21; // rax
  char v22; // di
  unsigned __int16 v23; // ax
  void *v24; // rax
  int v25; // eax
  char v27; // [rsp+41h] [rbp-D7h]
  _OWORD v28[4]; // [rsp+70h] [rbp-A8h] BYREF
  size_t Size; // [rsp+B0h] [rbp-68h]
  __int64 v31; // [rsp+138h] [rbp+20h] BYREF

  v3 = 1;
  while ( 1 )
  {
    UserSessionState = W32GetUserSessionState();
    v5 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
           UserSessionState,
           0,
           0,
           _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v5;
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = *(_QWORD **)(UserSessionState + 19544);
        if ( !v6 )
          break;
        *(_QWORD *)(UserSessionState + 19544) = v6[2];
        v6[2] = 0;
        if ( !*(_DWORD *)(*v6 + 8LL) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
        HMUnlockObject(*v6);
      }
      DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
      DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
    }
    v31 = 0;
    memset(v28, 0, sizeof(v28));
    v27 = 0;
    v7 = 0;
    if ( !(unsigned int)RIMIDECheckInjectionCapability() )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        LOBYTE(v3) = 0;
      }
      v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v9 = W32GetUserSessionState();
        LOBYTE(v10) = v8;
        LOBYTE(v11) = v3;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v11,
          v10,
          *(_QWORD *)(v9 + 69136),
          2,
          2,
          11,
          (__int64)WPP_29643b9594b93d88c3f18e16ab9eb5e9_Traceguids);
      }
      v3 = 0;
      UserSetLastError(5);
      goto LABEL_42;
    }
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a1, 0x40u, CurrentProcessWow64Process != 0 ? 1 : 4);
    v28[0] = *a1;
    v28[1] = a1[1];
    v28[2] = a1[2];
    v13 = (__m128i)v28[2];
    v28[3] = a1[3];
    v14 = (__m128i)v28[3];
    v15 = PsGetCurrentProcessWow64Process();
    v16 = (void *)v14.m128i_i64[0];
    ProbeForRead((volatile void *)v14.m128i_i64[0], (unsigned __int16)_mm_extract_epi16(v14, 4), v15 != 0 ? 1 : 4);
    epi16 = _mm_extract_epi16(v13, 4);
    Size = epi16;
    v18 = PsGetCurrentProcessWow64Process();
    v19 = (void *)v13.m128i_i64[0];
    ProbeForRead((volatile void *)v13.m128i_i64[0], epi16, v18 != 0 ? 1 : 4);
    if ( epi16 )
    {
      v21 = Win32AllocPoolWithQuotaZInitImpl(v20, epi16, 0x74697355u);
      v19 = v21;
      *(_QWORD *)&v28[2] = v21;
      if ( !v21 )
        goto LABEL_20;
      v22 = 1;
      v27 = 1;
      memmove(v21, (const void *)v13.m128i_i64[0], Size);
    }
    else
    {
      v22 = 0;
    }
    v23 = _mm_extract_epi16(v14, 4);
    if ( v23 )
    {
      v24 = Win32AllocPoolWithQuotaZInitImpl(v20, v23, 0x74697355u);
      v16 = v24;
      *(_QWORD *)&v28[3] = v24;
      if ( !v24 )
      {
LABEL_20:
        v3 = 0;
        UserSetLastError(8);
        goto LABEL_38;
      }
      v7 = 1;
      memmove(v24, (const void *)v14.m128i_i64[0], (unsigned __int16)_mm_extract_epi16(v14, 4));
    }
    if ( !v19 )
    {
      v3 = 0;
      UserSetLastError(87);
      goto LABEL_38;
    }
    v25 = RIMIDE_CreateGenericHidDevice(v28, &v31);
    if ( v25 >= 0 )
    {
      RtlWriteULong64ToUser(a2, v31);
      goto LABEL_37;
    }
    if ( v25 != -2147483631 )
      break;
    if ( v22 )
      GreDeleteFastMutex(*(PVOID *)&v28[2]);
    if ( v7 )
      GreDeleteFastMutex(*(PVOID *)&v28[3]);
    UserSessionSwitchLeaveCritWithNonPaged();
  }
  v3 = 0;
  UserSetLastError(87);
LABEL_37:
  v16 = *(void **)&v28[3];
  v19 = *(void **)&v28[2];
LABEL_38:
  if ( v27 )
    GreDeleteFastMutex(v19);
  if ( v7 )
    GreDeleteFastMutex(v16);
LABEL_42:
  UserSessionSwitchLeaveCritWithNonPaged();
  return v3;
}

```

## disassembly

```asm
0x1401db9a0  mov     rax, rsp
0x1401db9a3  mov     [rax+8], rcx
0x1401db9a7  push    rbx
0x1401db9a8  push    rsi
0x1401db9a9  push    rdi
0x1401db9aa  push    r12
0x1401db9ac  push    r13
0x1401db9ae  push    r14
0x1401db9b0  push    r15
0x1401db9b2  sub     rsp, 0E0h
0x1401db9b9  movaps  xmmword ptr [rax-48h], xmm6
0x1401db9bd  movaps  xmmword ptr [rax-58h], xmm7
0x1401db9c1  mov     rbx, rdx
0x1401db9c4  xor     esi, esi
0x1401db9c6  lea     r14d, [rsi+1]
0x1401db9ca  mov     r12d, 2
0x1401db9d0  call    cs:__imp_W32GetUserSessionState
0x1401db9d7  nop     dword ptr [rax+rax+00h]
0x1401db9dc  mov     rdi, rax
0x1401db9df  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401db9e6  xor     r8d, r8d
0x1401db9e9  xor     edx, edx
0x1401db9eb  mov     rcx, rax
0x1401db9ee  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401db9f3  mov     [rdi+10h], rax
0x1401db9f7  test    rax, rax
0x1401db9fa  jz      short loc_1401DBA66
0x1401db9fc  jmp     short loc_1401DBA42
0x1401db9fe  mov     rax, [r15+10h]
0x1401dba02  mov     [rdi+4C58h], rax
0x1401dba09  mov     [r15+10h], rsi
0x1401dba0d  mov     rax, [r15]
0x1401dba10  cmp     [rax+8], r14d
0x1401dba14  jnb     short loc_1401DBA3A
0x1401dba16  mov     [rsp+118h+arg_10], 20000h
0x1401dba21  mov     r8d, 1236h
0x1401dba27  mov     edx, [rsp+118h+arg_10]
0x1401dba2e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401dba35  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401dba3a  mov     rcx, [r15]
0x1401dba3d  call    HMUnlockObject
0x1401dba42  mov     r15, [rdi+4C58h]
0x1401dba49  test    r15, r15
0x1401dba4c  jnz     short loc_1401DB9FE
0x1401dba4e  lea     rcx, [rdi+4C78h]
0x1401dba55  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dba5a  lea     rcx, [rdi+4C68h]
0x1401dba61  call    DestroyDeferredUnlockObjectAssignmentList
0x1401dba66  mov     [rsp+118h+arg_18], rsi
0x1401dba6e  xor     edx, edx; Val
0x1401dba70  lea     r8d, [rdx+40h]; Size
0x1401dba74  lea     rcx, [rsp+118h+var_A8]; void *
0x1401dba79  call    memset
0x1401dba7e  mov     [rsp+118h+var_D7], sil
0x1401dba83  mov     r13b, sil
0x1401dba86  mov     [rsp+118h+var_D8], sil
0x1401dba8b  call    RIMIDECheckInjectionCapability
0x1401dba90  test    eax, eax
0x1401dba92  jnz     loc_1401DBB2E
0x1401dba98  lea     rax, WPP_GLOBAL_Control
0x1401dba9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401dbaa6  cmp     rcx, rax
0x1401dbaa9  jz      short loc_1401DBAB9
0x1401dbaab  mov     eax, [rcx+2Ch]
0x1401dbaae  test    r12b, al
0x1401dbab1  jz      short loc_1401DBAB9
0x1401dbab3  cmp     [rcx+29h], r12b
0x1401dbab7  jnb     short loc_1401DBABC
0x1401dbab9  mov     r14b, sil
0x1401dbabc  lea     rax, WPP_RECORDER_INITIALIZED
0x1401dbac3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401dbaca  setnz   bl
0x1401dbacd  test    r14b, r14b
0x1401dbad0  jnz     short loc_1401DBAD6
0x1401dbad2  test    bl, bl
0x1401dbad4  jz      short loc_1401DBB1C
0x1401dbad6  call    cs:__imp_W32GetUserSessionState
0x1401dbadd  nop     dword ptr [rax+rax+00h]
0x1401dbae2  mov     r9, [rax+10E10h]
0x1401dbae9  lea     rax, WPP_29643b9594b93d88c3f18e16ab9eb5e9_Traceguids
0x1401dbaf0  mov     [rsp+118h+var_E0], rax
0x1401dbaf5  mov     [rsp+118h+var_E8], 0Bh
0x1401dbafc  mov     [rsp+118h+var_F0], r12d
0x1401dbb01  mov     [rsp+118h+var_F8], r12b
0x1401dbb06  mov     r8b, bl
0x1401dbb09  mov     dl, r14b
0x1401dbb0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401dbb13  mov     rcx, [rcx+18h]
0x1401dbb17  call    WPP_RECORDER_AND_TRACE_SF_
0x1401dbb1c  mov     r14d, esi
0x1401dbb1f  mov     ecx, 5
0x1401dbb24  call    UserSetLastError
0x1401dbb29  jmp     loc_1401DBDC3
0x1401dbb2e  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dbb35  nop     dword ptr [rax+rax+00h]
0x1401dbb3a  neg     rax
0x1401dbb3d  sbb     r8d, r8d
0x1401dbb40  and     r8d, 0FFFFFFFDh
0x1401dbb44  add     r8d, 4; Alignment
0x1401dbb48  mov     edx, 40h ; '@'; Length
0x1401dbb4d  mov     rcx, [rsp+118h+Address]; Address
0x1401dbb55  call    cs:__imp_ProbeForRead
0x1401dbb5c  nop     dword ptr [rax+rax+00h]
0x1401dbb61  mov     rax, [rsp+118h+Address]
0x1401dbb69  movups  xmm0, xmmword ptr [rax]
0x1401dbb6c  movaps  [rsp+118h+var_A8], xmm0
0x1401dbb71  movups  xmm1, xmmword ptr [rax+10h]
0x1401dbb75  movaps  [rsp+118h+var_98], xmm1
0x1401dbb7d  movups  xmm7, xmmword ptr [rax+20h]
0x1401dbb81  movaps  xmmword ptr [rsp+118h+Buffer], xmm7
0x1401dbb89  movups  xmm6, xmmword ptr [rax+30h]
0x1401dbb8d  movaps  xmmword ptr [rsp+118h+var_78], xmm6
0x1401dbb95  pextrw  eax, xmm6, 4
0x1401dbb9a  movzx   edi, ax
0x1401dbb9d  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dbba4  nop     dword ptr [rax+rax+00h]
0x1401dbba9  neg     rax
0x1401dbbac  sbb     r8d, r8d
0x1401dbbaf  and     r8d, 0FFFFFFFDh
0x1401dbbb3  add     r8d, 4; Alignment
0x1401dbbb7  mov     edx, edi; Length
0x1401dbbb9  movq    r12, xmm6
0x1401dbbbe  mov     rcx, r12; Address
0x1401dbbc1  call    cs:__imp_ProbeForRead
0x1401dbbc8  nop     dword ptr [rax+rax+00h]
0x1401dbbcd  pextrw  edi, xmm7, 4
0x1401dbbd2  movzx   r15d, di
0x1401dbbd6  mov     [rsp+118h+Size], r15
0x1401dbbde  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401dbbe5  nop     dword ptr [rax+rax+00h]
0x1401dbbea  neg     rax
0x1401dbbed  sbb     r8d, r8d
0x1401dbbf0  and     r8d, 0FFFFFFFDh
0x1401dbbf4  add     r8d, 4; Alignment
0x1401dbbf8  mov     edx, r15d; Length
0x1401dbbfb  movq    r15, xmm7
0x1401dbc00  mov     rcx, r15; Address
0x1401dbc03  call    cs:__imp_ProbeForRead
0x1401dbc0a  nop     dword ptr [rax+rax+00h]
0x1401dbc0f  test    di, di
0x1401dbc12  jz      short loc_1401DBC6A
0x1401dbc14  mov     [rsp+118h+Src], r15
0x1401dbc19  mov     r8d, 74697355h; unsigned int
0x1401dbc1f  movzx   edx, di; unsigned __int64
0x1401dbc22  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dbc27  mov     r15, rax
0x1401dbc2a  mov     [rsp+118h+Buffer], rax
0x1401dbc32  test    rax, rax
0x1401dbc35  jnz     short loc_1401DBC4B
0x1401dbc37  mov     r14d, esi
0x1401dbc3a  mov     [rsp+118h+var_D4], esi
0x1401dbc3e  lea     ecx, [rax+8]
0x1401dbc41  call    UserSetLastError
0x1401dbc46  jmp     loc_1401DBDA7
0x1401dbc4b  mov     dil, r14b
0x1401dbc4e  mov     [rsp+118h+var_D7], r14b
0x1401dbc53  mov     r8, [rsp+118h+Size]; Size
0x1401dbc5b  mov     rdx, [rsp+118h+Src]; Src
0x1401dbc60  mov     rcx, rax; void *
0x1401dbc63  call    memmove
0x1401dbc68  jmp     short loc_1401DBC6F
0x1401dbc6a  mov     dil, [rsp+118h+var_D7]
0x1401dbc6f  pextrw  eax, xmm6, 4
0x1401dbc74  test    ax, ax
0x1401dbc77  jz      short loc_1401DBCD0
0x1401dbc79  mov     [rsp+118h+Src], r12
0x1401dbc7e  mov     r8d, 74697355h; unsigned int
0x1401dbc84  movzx   edx, ax; unsigned __int64
0x1401dbc87  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401dbc8c  mov     r12, rax
0x1401dbc8f  mov     [rsp+118h+var_78], rax
0x1401dbc97  test    rax, rax
0x1401dbc9a  jnz     short loc_1401DBCB0
0x1401dbc9c  mov     r14d, esi
0x1401dbc9f  mov     [rsp+118h+var_D4], esi
0x1401dbca3  lea     ecx, [rax+8]
0x1401dbca6  call    UserSetLastError
0x1401dbcab  jmp     loc_1401DBDA7
0x1401dbcb0  mov     r13b, r14b
0x1401dbcb3  mov     [rsp+118h+var_D8], r14b
0x1401dbcb8  pextrw  r8d, xmm6, 4
0x1401dbcbe  movzx   r8d, r8w; Size
0x1401dbcc2  mov     rdx, [rsp+118h+Src]; Src
0x1401dbcc7  mov     rcx, rax; void *
0x1401dbcca  call    memmove
0x1401dbccf  nop
0x1401dbcd0  test    r15, r15
0x1401dbcd3  jnz     short loc_1401DBCE6
0x1401dbcd5  mov     r14d, esi
0x1401dbcd8  lea     ecx, [r15+57h]
0x1401dbcdc  call    UserSetLastError
0x1401dbce1  jmp     loc_1401DBDA7
0x1401dbce6  lea     rdx, [rsp+118h+arg_18]
0x1401dbcee  lea     rcx, [rsp+118h+var_A8]
0x1401dbcf3  call    RIMIDE_CreateGenericHidDevice
0x1401dbcf8  test    eax, eax
0x1401dbcfa  js      short loc_1401DBD34
0x1401dbcfc  mov     rdx, [rsp+118h+arg_18]
0x1401dbd04  mov     rcx, rbx
0x1401dbd07  call    RtlWriteULong64ToUser
0x1401dbd0c  mov     [rsp+118h+var_D4], r14d
0x1401dbd11  jmp     short loc_1401DBD76
0x1401dbd13  xor     r14d, r14d
0x1401dbd16  mov     [rsp+118h+var_D4], r14d
0x1401dbd1b  xor     esi, esi
0x1401dbd1d  mov     r12, [rsp+118h+var_78]
0x1401dbd25  mov     r15, [rsp+118h+Buffer]
0x1401dbd2d  mov     r13b, [rsp+118h+var_D8]
0x1401dbd32  jmp     short loc_1401DBDA7
0x1401dbd34  cmp     eax, 80000011h
0x1401dbd39  jnz     short loc_1401DBD69
0x1401dbd3b  test    dil, dil
0x1401dbd3e  jz      short loc_1401DBD4D
0x1401dbd40  mov     rcx, [rsp+118h+Buffer]; Buffer
0x1401dbd48  call    GreDeleteFastMutex
0x1401dbd4d  test    r13b, r13b
0x1401dbd50  jz      short loc_1401DBD5F
0x1401dbd52  mov     rcx, [rsp+118h+var_78]; Buffer
0x1401dbd5a  call    GreDeleteFastMutex
0x1401dbd5f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401dbd64  jmp     loc_1401DB9CA
0x1401dbd69  mov     r14d, esi
0x1401dbd6c  mov     ecx, 57h ; 'W'
0x1401dbd71  call    UserSetLastError
0x1401dbd76  mov     r12, [rsp+118h+var_78]
0x1401dbd7e  mov     r15, [rsp+118h+Buffer]
0x1401dbd86  jmp     short loc_1401DBDA7
0x1401dbd88  xor     r14d, r14d
0x1401dbd8b  mov     [rsp+118h+var_D4], r14d
0x1401dbd90  xor     esi, esi
0x1401dbd92  mov     r12, [rsp+118h+var_78]
0x1401dbd9a  mov     r15, [rsp+118h+Buffer]
0x1401dbda2  mov     r13b, [rsp+118h+var_D8]
0x1401dbda7  cmp     [rsp+118h+var_D7], sil
0x1401dbdac  jz      short loc_1401DBDB6
0x1401dbdae  mov     rcx, r15; Buffer
0x1401dbdb1  call    GreDeleteFastMutex
0x1401dbdb6  test    r13b, r13b
0x1401dbdb9  jz      short loc_1401DBDC3
0x1401dbdbb  mov     rcx, r12; Buffer
0x1401dbdbe  call    GreDeleteFastMutex
0x1401dbdc3  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401dbdc8  movsxd  rax, r14d
0x1401dbdcb  lea     r11, [rsp+118h+var_38]
0x1401dbdd3  movaps  xmm6, xmmword ptr [r11-10h]
0x1401dbdd8  movaps  xmm7, xmmword ptr [r11-20h]
0x1401dbddd  mov     rsp, r11
0x1401dbde0  pop     r15
0x1401dbde2  pop     r14
0x1401dbde4  pop     r13
0x1401dbde6  pop     r12
0x1401dbde8  pop     rdi
0x1401dbde9  pop     rsi
0x1401dbdea  pop     rbx
0x1401dbdeb  retn
0x14023a424  push    rbp
0x14023a426  sub     rsp, 40h
0x14023a42a  mov     rbp, rdx
0x14023a42d  mov     rax, [rcx]
0x14023a430  mov     ecx, [rax]
0x14023a432  mov     [rbp+58h], ecx
0x14023a435  mov     ecx, [rbp+58h]
0x14023a438  call    SetLastNtError
0x14023a43d  mov     dword ptr [rbp+60h], 1
0x14023a444  mov     eax, [rbp+60h]
0x14023a447  add     rsp, 40h
0x14023a44b  pop     rbp
0x14023a44c  retn
0x14023a44e  push    rbp
0x14023a450  sub     rsp, 40h
0x14023a454  mov     rbp, rdx
0x14023a457  mov     rax, [rcx]
0x14023a45a  mov     ecx, [rax]
0x14023a45c  mov     [rbp+48h], ecx
0x14023a45f  mov     ecx, [rbp+48h]
0x14023a462  call    SetLastNtError
0x14023a467  mov     dword ptr [rbp+50h], 1
0x14023a46e  mov     eax, [rbp+50h]
0x14023a471  add     rsp, 40h
0x14023a475  pop     rbp
0x14023a476  retn
```
