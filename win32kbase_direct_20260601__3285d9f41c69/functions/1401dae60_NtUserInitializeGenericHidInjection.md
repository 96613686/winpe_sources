# NtUserInitializeGenericHidInjection

- ea: `0x1401dae60`
- end: `0x1401db2ad`
- name: `NtUserInitializeGenericHidInjection`
- size: `1101`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14001bdf0`
- `0x1400325a4`
- `0x140033268`
- `0x140033364`
- `0x14004a0d0`
- `0x14004c720`
- `0x140072a90`
- `0x140074bf0`
- `0x140078090`
- `0x1401a9f9c`
- `0x1401b0044`
- `0x1401dae60`
- `0x14020383c`
- `0x1402382c0`
- `0x140238800`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401db015`
- `ntoskrnl!ProbeForRead` at `0x1401db081`
- `ntoskrnl!ProbeForRead` at `0x1401db0c3`
- `ntoskrnl!ProbeForRead` at `0x1401db015`
- `ntoskrnl!ProbeForRead` at `0x1401db081`
- `ntoskrnl!ProbeForRead` at `0x1401db0c3`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dafee`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db05d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db09e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401dafee`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db05d`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db09e`
- `WIN32K!W32GetUserSessionState` at `0x1401dae90`
- `WIN32K!W32GetUserSessionState` at `0x1401daf96`
- `WIN32K!W32GetUserSessionState` at `0x1401dae90`
- `WIN32K!W32GetUserSessionState` at `0x1401daf96`

## pseudocode

```c
__int64 __fastcall NtUserInitializeGenericHidInjection(_OWORD *a1, __int64 a2, __int64 a3)
{
  int v4; // r14d
  __int64 UserSessionState; // rdi
  __int64 v6; // rax
  _QWORD *v7; // r15
  char v8; // r13
  __int64 v9; // rdx
  __int64 v10; // r8
  bool v11; // bl
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  __int64 CurrentProcessWow64Process; // rax
  __m128i v16; // xmm7
  __m128i v17; // xmm6
  __int64 v18; // rax
  void *v19; // r12
  unsigned __int16 epi16; // di
  __int64 v21; // rax
  void *v22; // r15
  unsigned __int64 v23; // rcx
  void *v24; // rax
  char v25; // di
  unsigned __int16 v26; // ax
  void *v27; // rax
  int v28; // eax
  char v30; // [rsp+41h] [rbp-D7h]
  _OWORD v31[4]; // [rsp+70h] [rbp-A8h] BYREF
  size_t Size; // [rsp+B0h] [rbp-68h]
  __int64 v34; // [rsp+138h] [rbp+20h] BYREF

  v4 = 1;
  while ( 1 )
  {
    UserSessionState = W32GetUserSessionState(a1, a2, a3);
    v6 = UserCritInternal::_anonymous_namespace_::EnterCritInternal(
           UserSessionState,
           0,
           0,
           _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_);
    *(_QWORD *)(UserSessionState + 16) = v6;
    if ( v6 )
    {
      while ( 1 )
      {
        v7 = *(_QWORD **)(UserSessionState + 19544);
        if ( !v7 )
          break;
        *(_QWORD *)(UserSessionState + 19544) = v7[2];
        v7[2] = 0;
        if ( !*(_DWORD *)(*v7 + 8LL) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4662);
        HMUnlockObject(*v7);
      }
      DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19576);
      DestroyDeferredUnlockObjectAssignmentList(UserSessionState + 19560);
    }
    v34 = 0;
    memset(v31, 0, sizeof(v31));
    v30 = 0;
    v8 = 0;
    if ( !(unsigned int)RIMIDECheckInjectionCapability() )
    {
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        LOBYTE(v4) = 0;
      }
      v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = W32GetUserSessionState(WPP_GLOBAL_Control, v9, v10);
        LOBYTE(v13) = v11;
        LOBYTE(v14) = v4;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v14,
          v13,
          *(_QWORD *)(v12 + 69136),
          2,
          2,
          11,
          (__int64)WPP_3a5b2c13686b34ca498e471343e64ddb_Traceguids);
      }
      v4 = 0;
      UserSetLastError(5);
      goto LABEL_42;
    }
    CurrentProcessWow64Process = PsGetCurrentProcessWow64Process();
    ProbeForRead(a1, 0x40u, CurrentProcessWow64Process != 0 ? 1 : 4);
    v31[0] = *a1;
    v31[1] = a1[1];
    v31[2] = a1[2];
    v16 = (__m128i)v31[2];
    v31[3] = a1[3];
    v17 = (__m128i)v31[3];
    v18 = PsGetCurrentProcessWow64Process();
    v19 = (void *)v17.m128i_i64[0];
    ProbeForRead((volatile void *)v17.m128i_i64[0], (unsigned __int16)_mm_extract_epi16(v17, 4), v18 != 0 ? 1 : 4);
    epi16 = _mm_extract_epi16(v16, 4);
    Size = epi16;
    v21 = PsGetCurrentProcessWow64Process();
    v22 = (void *)v16.m128i_i64[0];
    ProbeForRead((volatile void *)v16.m128i_i64[0], epi16, v21 != 0 ? 1 : 4);
    if ( epi16 )
    {
      v24 = Win32AllocPoolWithQuotaZInitImpl(v23, epi16, 0x74697355u);
      v22 = v24;
      *(_QWORD *)&v31[2] = v24;
      if ( !v24 )
        goto LABEL_20;
      v25 = 1;
      v30 = 1;
      memmove(v24, (const void *)v16.m128i_i64[0], Size);
    }
    else
    {
      v25 = 0;
    }
    v26 = _mm_extract_epi16(v17, 4);
    if ( v26 )
    {
      v27 = Win32AllocPoolWithQuotaZInitImpl(v23, v26, 0x74697355u);
      v19 = v27;
      *(_QWORD *)&v31[3] = v27;
      if ( !v27 )
      {
LABEL_20:
        v4 = 0;
        UserSetLastError(8);
        goto LABEL_38;
      }
      v8 = 1;
      memmove(v27, (const void *)v17.m128i_i64[0], (unsigned __int16)_mm_extract_epi16(v17, 4));
    }
    if ( !v22 )
    {
      v4 = 0;
      UserSetLastError(87);
      goto LABEL_38;
    }
    v28 = RIMIDE_CreateGenericHidDevice(v31, &v34);
    if ( v28 >= 0 )
    {
      RtlWriteULong64ToUser(a2, v34);
      goto LABEL_37;
    }
    if ( v28 != -2147483631 )
      break;
    if ( v25 )
      GreDeleteFastMutex(*(PVOID *)&v31[2]);
    if ( v8 )
      GreDeleteFastMutex(*(PVOID *)&v31[3]);
    UserSessionSwitchLeaveCritWithNonPaged();
  }
  v4 = 0;
  UserSetLastError(87);
LABEL_37:
  v19 = *(void **)&v31[3];
  v22 = *(void **)&v31[2];
LABEL_38:
  if ( v30 )
    GreDeleteFastMutex(v22);
  if ( v8 )
    GreDeleteFastMutex(v19);
LABEL_42:
  UserSessionSwitchLeaveCritWithNonPaged();
  return v4;
}

```

## disassembly

```asm
0x1401dae60  mov     rax, rsp
0x1401dae63  mov     [rax+8], rcx
0x1401dae67  push    rbx
0x1401dae68  push    rsi
0x1401dae69  push    rdi
0x1401dae6a  push    r12
0x1401dae6c  push    r13
0x1401dae6e  push    r14
0x1401dae70  push    r15
0x1401dae72  sub     rsp, 0E0h
0x1401dae79  movaps  xmmword ptr [rax-48h], xmm6
0x1401dae7d  movaps  xmmword ptr [rax-58h], xmm7
0x1401dae81  mov     rbx, rdx
0x1401dae84  xor     esi, esi
0x1401dae86  lea     r14d, [rsi+1]
0x1401dae8a  mov     r12d, 2
0x1401dae90  call    cs:__imp_W32GetUserSessionState
0x1401dae97  nop     dword ptr [rax+rax+00h]
0x1401dae9c  mov     rdi, rax
0x1401dae9f  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401daea6  xor     r8d, r8d
0x1401daea9  xor     edx, edx
0x1401daeab  mov     rcx, rax
0x1401daeae  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401daeb3  mov     [rdi+10h], rax
0x1401daeb7  test    rax, rax
0x1401daeba  jz      short loc_1401DAF26
0x1401daebc  jmp     short loc_1401DAF02
0x1401daebe  mov     rax, [r15+10h]
0x1401daec2  mov     [rdi+4C58h], rax
0x1401daec9  mov     [r15+10h], rsi
0x1401daecd  mov     rax, [r15]
0x1401daed0  cmp     [rax+8], r14d
0x1401daed4  jnb     short loc_1401DAEFA
0x1401daed6  mov     [rsp+118h+arg_10], 20000h
0x1401daee1  mov     r8d, 1236h
0x1401daee7  mov     edx, [rsp+118h+arg_10]
0x1401daeee  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401daef5  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401daefa  mov     rcx, [r15]
0x1401daefd  call    HMUnlockObject
0x1401daf02  mov     r15, [rdi+4C58h]
0x1401daf09  test    r15, r15
0x1401daf0c  jnz     short loc_1401DAEBE
0x1401daf0e  lea     rcx, [rdi+4C78h]
0x1401daf15  call    DestroyDeferredUnlockObjectAssignmentList
0x1401daf1a  lea     rcx, [rdi+4C68h]
0x1401daf21  call    DestroyDeferredUnlockObjectAssignmentList
0x1401daf26  mov     [rsp+118h+arg_18], rsi
0x1401daf2e  xor     edx, edx; Val
0x1401daf30  lea     r8d, [rdx+40h]; Size
0x1401daf34  lea     rcx, [rsp+118h+var_A8]; void *
0x1401daf39  call    memset
0x1401daf3e  mov     [rsp+118h+var_D7], sil
0x1401daf43  mov     r13b, sil
0x1401daf46  mov     [rsp+118h+var_D8], sil
0x1401daf4b  call    RIMIDECheckInjectionCapability
0x1401daf50  test    eax, eax
0x1401daf52  jnz     loc_1401DAFEE
0x1401daf58  lea     rax, WPP_GLOBAL_Control
0x1401daf5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401daf66  cmp     rcx, rax
0x1401daf69  jz      short loc_1401DAF79
0x1401daf6b  mov     eax, [rcx+2Ch]
0x1401daf6e  test    r12b, al
0x1401daf71  jz      short loc_1401DAF79
0x1401daf73  cmp     [rcx+29h], r12b
0x1401daf77  jnb     short loc_1401DAF7C
0x1401daf79  mov     r14b, sil
0x1401daf7c  lea     rax, WPP_RECORDER_INITIALIZED
0x1401daf83  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401daf8a  setnz   bl
0x1401daf8d  test    r14b, r14b
0x1401daf90  jnz     short loc_1401DAF96
0x1401daf92  test    bl, bl
0x1401daf94  jz      short loc_1401DAFDC
0x1401daf96  call    cs:__imp_W32GetUserSessionState
0x1401daf9d  nop     dword ptr [rax+rax+00h]
0x1401dafa2  mov     r9, [rax+10E10h]
0x1401dafa9  lea     rax, WPP_3a5b2c13686b34ca498e471343e64ddb_Traceguids
0x1401dafb0  mov     [rsp+118h+var_E0], rax
0x1401dafb5  mov     [rsp+118h+var_E8], 0Bh
0x1401dafbc  mov     [rsp+118h+var_F0], r12d
0x1401dafc1  mov     [rsp+118h+var_F8], r12b
0x1401dafc6  mov     r8b, bl
0x1401dafc9  mov     dl, r14b
0x1401dafcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401dafd3  mov     rcx, [rcx+18h]
0x1401dafd7  call    WPP_RECORDER_AND_TRACE_SF_
0x1401dafdc  mov     r14d, esi
0x1401dafdf  mov     ecx, 5
0x1401dafe4  call    UserSetLastError
0x1401dafe9  jmp     loc_1401DB283
0x1401dafee  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401daff5  nop     dword ptr [rax+rax+00h]
0x1401daffa  neg     rax
0x1401daffd  sbb     r8d, r8d
0x1401db000  and     r8d, 0FFFFFFFDh
0x1401db004  add     r8d, 4; Alignment
0x1401db008  mov     edx, 40h ; '@'; Length
0x1401db00d  mov     rcx, [rsp+118h+Address]; Address
0x1401db015  call    cs:__imp_ProbeForRead
0x1401db01c  nop     dword ptr [rax+rax+00h]
0x1401db021  mov     rax, [rsp+118h+Address]
0x1401db029  movups  xmm0, xmmword ptr [rax]
0x1401db02c  movaps  [rsp+118h+var_A8], xmm0
0x1401db031  movups  xmm1, xmmword ptr [rax+10h]
0x1401db035  movaps  [rsp+118h+var_98], xmm1
0x1401db03d  movups  xmm7, xmmword ptr [rax+20h]
0x1401db041  movaps  xmmword ptr [rsp+118h+Buffer], xmm7
0x1401db049  movups  xmm6, xmmword ptr [rax+30h]
0x1401db04d  movaps  xmmword ptr [rsp+118h+var_78], xmm6
0x1401db055  pextrw  eax, xmm6, 4
0x1401db05a  movzx   edi, ax
0x1401db05d  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db064  nop     dword ptr [rax+rax+00h]
0x1401db069  neg     rax
0x1401db06c  sbb     r8d, r8d
0x1401db06f  and     r8d, 0FFFFFFFDh
0x1401db073  add     r8d, 4; Alignment
0x1401db077  mov     edx, edi; Length
0x1401db079  movq    r12, xmm6
0x1401db07e  mov     rcx, r12; Address
0x1401db081  call    cs:__imp_ProbeForRead
0x1401db088  nop     dword ptr [rax+rax+00h]
0x1401db08d  pextrw  edi, xmm7, 4
0x1401db092  movzx   r15d, di
0x1401db096  mov     [rsp+118h+Size], r15
0x1401db09e  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db0a5  nop     dword ptr [rax+rax+00h]
0x1401db0aa  neg     rax
0x1401db0ad  sbb     r8d, r8d
0x1401db0b0  and     r8d, 0FFFFFFFDh
0x1401db0b4  add     r8d, 4; Alignment
0x1401db0b8  mov     edx, r15d; Length
0x1401db0bb  movq    r15, xmm7
0x1401db0c0  mov     rcx, r15; Address
0x1401db0c3  call    cs:__imp_ProbeForRead
0x1401db0ca  nop     dword ptr [rax+rax+00h]
0x1401db0cf  test    di, di
0x1401db0d2  jz      short loc_1401DB12A
0x1401db0d4  mov     [rsp+118h+Src], r15
0x1401db0d9  mov     r8d, 74697355h; unsigned int
0x1401db0df  movzx   edx, di; unsigned __int64
0x1401db0e2  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401db0e7  mov     r15, rax
0x1401db0ea  mov     [rsp+118h+Buffer], rax
0x1401db0f2  test    rax, rax
0x1401db0f5  jnz     short loc_1401DB10B
0x1401db0f7  mov     r14d, esi
0x1401db0fa  mov     [rsp+118h+var_D4], esi
0x1401db0fe  lea     ecx, [rax+8]
0x1401db101  call    UserSetLastError
0x1401db106  jmp     loc_1401DB267
0x1401db10b  mov     dil, r14b
0x1401db10e  mov     [rsp+118h+var_D7], r14b
0x1401db113  mov     r8, [rsp+118h+Size]; Size
0x1401db11b  mov     rdx, [rsp+118h+Src]; Src
0x1401db120  mov     rcx, rax; void *
0x1401db123  call    memmove
0x1401db128  jmp     short loc_1401DB12F
0x1401db12a  mov     dil, [rsp+118h+var_D7]
0x1401db12f  pextrw  eax, xmm6, 4
0x1401db134  test    ax, ax
0x1401db137  jz      short loc_1401DB190
0x1401db139  mov     [rsp+118h+Src], r12
0x1401db13e  mov     r8d, 74697355h; unsigned int
0x1401db144  movzx   edx, ax; unsigned __int64
0x1401db147  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401db14c  mov     r12, rax
0x1401db14f  mov     [rsp+118h+var_78], rax
0x1401db157  test    rax, rax
0x1401db15a  jnz     short loc_1401DB170
0x1401db15c  mov     r14d, esi
0x1401db15f  mov     [rsp+118h+var_D4], esi
0x1401db163  lea     ecx, [rax+8]
0x1401db166  call    UserSetLastError
0x1401db16b  jmp     loc_1401DB267
0x1401db170  mov     r13b, r14b
0x1401db173  mov     [rsp+118h+var_D8], r14b
0x1401db178  pextrw  r8d, xmm6, 4
0x1401db17e  movzx   r8d, r8w; Size
0x1401db182  mov     rdx, [rsp+118h+Src]; Src
0x1401db187  mov     rcx, rax; void *
0x1401db18a  call    memmove
0x1401db18f  nop
0x1401db190  test    r15, r15
0x1401db193  jnz     short loc_1401DB1A6
0x1401db195  mov     r14d, esi
0x1401db198  lea     ecx, [r15+57h]
0x1401db19c  call    UserSetLastError
0x1401db1a1  jmp     loc_1401DB267
0x1401db1a6  lea     rdx, [rsp+118h+arg_18]
0x1401db1ae  lea     rcx, [rsp+118h+var_A8]
0x1401db1b3  call    RIMIDE_CreateGenericHidDevice
0x1401db1b8  test    eax, eax
0x1401db1ba  js      short loc_1401DB1F4
0x1401db1bc  mov     rdx, [rsp+118h+arg_18]
0x1401db1c4  mov     rcx, rbx
0x1401db1c7  call    RtlWriteULong64ToUser
0x1401db1cc  mov     [rsp+118h+var_D4], r14d
0x1401db1d1  jmp     short loc_1401DB236
0x1401db1d3  xor     r14d, r14d
0x1401db1d6  mov     [rsp+118h+var_D4], r14d
0x1401db1db  xor     esi, esi
0x1401db1dd  mov     r12, [rsp+118h+var_78]
0x1401db1e5  mov     r15, [rsp+118h+Buffer]
0x1401db1ed  mov     r13b, [rsp+118h+var_D8]
0x1401db1f2  jmp     short loc_1401DB267
0x1401db1f4  cmp     eax, 80000011h
0x1401db1f9  jnz     short loc_1401DB229
0x1401db1fb  test    dil, dil
0x1401db1fe  jz      short loc_1401DB20D
0x1401db200  mov     rcx, [rsp+118h+Buffer]; Buffer
0x1401db208  call    GreDeleteFastMutex
0x1401db20d  test    r13b, r13b
0x1401db210  jz      short loc_1401DB21F
0x1401db212  mov     rcx, [rsp+118h+var_78]; Buffer
0x1401db21a  call    GreDeleteFastMutex
0x1401db21f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db224  jmp     loc_1401DAE8A
0x1401db229  mov     r14d, esi
0x1401db22c  mov     ecx, 57h ; 'W'
0x1401db231  call    UserSetLastError
0x1401db236  mov     r12, [rsp+118h+var_78]
0x1401db23e  mov     r15, [rsp+118h+Buffer]
0x1401db246  jmp     short loc_1401DB267
0x1401db248  xor     r14d, r14d
0x1401db24b  mov     [rsp+118h+var_D4], r14d
0x1401db250  xor     esi, esi
0x1401db252  mov     r12, [rsp+118h+var_78]
0x1401db25a  mov     r15, [rsp+118h+Buffer]
0x1401db262  mov     r13b, [rsp+118h+var_D8]
0x1401db267  cmp     [rsp+118h+var_D7], sil
0x1401db26c  jz      short loc_1401DB276
0x1401db26e  mov     rcx, r15; Buffer
0x1401db271  call    GreDeleteFastMutex
0x1401db276  test    r13b, r13b
0x1401db279  jz      short loc_1401DB283
0x1401db27b  mov     rcx, r12; Buffer
0x1401db27e  call    GreDeleteFastMutex
0x1401db283  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db288  movsxd  rax, r14d
0x1401db28b  lea     r11, [rsp+118h+var_38]
0x1401db293  movaps  xmm6, xmmword ptr [r11-10h]
0x1401db298  movaps  xmm7, xmmword ptr [r11-20h]
0x1401db29d  mov     rsp, r11
0x1401db2a0  pop     r15
0x1401db2a2  pop     r14
0x1401db2a4  pop     r13
0x1401db2a6  pop     r12
0x1401db2a8  pop     rdi
0x1401db2a9  pop     rsi
0x1401db2aa  pop     rbx
0x1401db2ab  retn
0x140239c81  push    rbp
0x140239c83  sub     rsp, 40h
0x140239c87  mov     rbp, rdx
0x140239c8a  mov     rax, [rcx]
0x140239c8d  mov     ecx, [rax]
0x140239c8f  mov     [rbp+58h], ecx
0x140239c92  mov     ecx, [rbp+58h]
0x140239c95  call    SetLastNtError
0x140239c9a  mov     dword ptr [rbp+60h], 1
0x140239ca1  mov     eax, [rbp+60h]
0x140239ca4  add     rsp, 40h
0x140239ca8  pop     rbp
0x140239ca9  retn
0x140239cab  push    rbp
0x140239cad  sub     rsp, 40h
0x140239cb1  mov     rbp, rdx
0x140239cb4  mov     rax, [rcx]
0x140239cb7  mov     ecx, [rax]
0x140239cb9  mov     [rbp+48h], ecx
0x140239cbc  mov     ecx, [rbp+48h]
0x140239cbf  call    SetLastNtError
0x140239cc4  mov     dword ptr [rbp+50h], 1
0x140239ccb  mov     eax, [rbp+50h]
0x140239cce  add     rsp, 40h
0x140239cd2  pop     rbp
0x140239cd3  retn
```
