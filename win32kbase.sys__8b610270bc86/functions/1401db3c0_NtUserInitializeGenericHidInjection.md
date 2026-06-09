# NtUserInitializeGenericHidInjection

- ea: `0x1401db3c0`
- end: `0x1401db80d`
- name: `NtUserInitializeGenericHidInjection`
- size: `1101`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140012c80`
- `0x140029324`
- `0x140029fe8`
- `0x14002a0e4`
- `0x1400411c0`
- `0x140043810`
- `0x1400718f0`
- `0x140073a50`
- `0x140076ef0`
- `0x1401aa4fc`
- `0x1401b05a4`
- `0x1401db3c0`
- `0x14020405c`
- `0x140238c40`
- `0x140239180`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401db575`
- `ntoskrnl!ProbeForRead` at `0x1401db5e1`
- `ntoskrnl!ProbeForRead` at `0x1401db623`
- `ntoskrnl!ProbeForRead` at `0x1401db575`
- `ntoskrnl!ProbeForRead` at `0x1401db5e1`
- `ntoskrnl!ProbeForRead` at `0x1401db623`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db54e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db5bd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db5fe`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db54e`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db5bd`
- `ntoskrnl!PsGetCurrentProcessWow64Process` at `0x1401db5fe`
- `WIN32K!W32GetUserSessionState` at `0x1401db3f0`
- `WIN32K!W32GetUserSessionState` at `0x1401db4f6`
- `WIN32K!W32GetUserSessionState` at `0x1401db3f0`
- `WIN32K!W32GetUserSessionState` at `0x1401db4f6`

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
    UserSessionState = W32GetUserSessionState(a1);
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
        v9 = W32GetUserSessionState(WPP_GLOBAL_Control);
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
          (__int64)WPP_3a5b2c13686b34ca498e471343e64ddb_Traceguids);
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
0x1401db3c0  mov     rax, rsp
0x1401db3c3  mov     [rax+8], rcx
0x1401db3c7  push    rbx
0x1401db3c8  push    rsi
0x1401db3c9  push    rdi
0x1401db3ca  push    r12
0x1401db3cc  push    r13
0x1401db3ce  push    r14
0x1401db3d0  push    r15
0x1401db3d2  sub     rsp, 0E0h
0x1401db3d9  movaps  xmmword ptr [rax-48h], xmm6
0x1401db3dd  movaps  xmmword ptr [rax-58h], xmm7
0x1401db3e1  mov     rbx, rdx
0x1401db3e4  xor     esi, esi
0x1401db3e6  lea     r14d, [rsi+1]
0x1401db3ea  mov     r12d, 2
0x1401db3f0  call    cs:__imp_W32GetUserSessionState
0x1401db3f7  nop     dword ptr [rax+rax+00h]
0x1401db3fc  mov     rdi, rax
0x1401db3ff  lea     r9, ?_lambda_invoker_cdecl_@_lambda_63b61c2369133a205197eda5bd671ee7_@@CAXPEAU_FAST_ERESOURCE@@PEAU_W32THREADNONPAGED@@@Z; _lambda_63b61c2369133a205197eda5bd671ee7_::_lambda_invoker_cdecl_(_FAST_ERESOURCE *,_W32THREADNONPAGED *)
0x1401db406  xor     r8d, r8d
0x1401db409  xor     edx, edx
0x1401db40b  mov     rcx, rax
0x1401db40e  call    UserCritInternal___anonymous_namespace___EnterCritInternal
0x1401db413  mov     [rdi+10h], rax
0x1401db417  test    rax, rax
0x1401db41a  jz      short loc_1401DB486
0x1401db41c  jmp     short loc_1401DB462
0x1401db41e  mov     rax, [r15+10h]
0x1401db422  mov     [rdi+4C58h], rax
0x1401db429  mov     [r15+10h], rsi
0x1401db42d  mov     rax, [r15]
0x1401db430  cmp     [rax+8], r14d
0x1401db434  jnb     short loc_1401DB45A
0x1401db436  mov     [rsp+118h+arg_10], 20000h
0x1401db441  mov     r8d, 1236h
0x1401db447  mov     edx, [rsp+118h+arg_10]
0x1401db44e  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401db455  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401db45a  mov     rcx, [r15]
0x1401db45d  call    HMUnlockObject
0x1401db462  mov     r15, [rdi+4C58h]
0x1401db469  test    r15, r15
0x1401db46c  jnz     short loc_1401DB41E
0x1401db46e  lea     rcx, [rdi+4C78h]
0x1401db475  call    DestroyDeferredUnlockObjectAssignmentList
0x1401db47a  lea     rcx, [rdi+4C68h]
0x1401db481  call    DestroyDeferredUnlockObjectAssignmentList
0x1401db486  mov     [rsp+118h+arg_18], rsi
0x1401db48e  xor     edx, edx; Val
0x1401db490  lea     r8d, [rdx+40h]; Size
0x1401db494  lea     rcx, [rsp+118h+var_A8]; void *
0x1401db499  call    memset
0x1401db49e  mov     [rsp+118h+var_D7], sil
0x1401db4a3  mov     r13b, sil
0x1401db4a6  mov     [rsp+118h+var_D8], sil
0x1401db4ab  call    RIMIDECheckInjectionCapability
0x1401db4b0  test    eax, eax
0x1401db4b2  jnz     loc_1401DB54E
0x1401db4b8  lea     rax, WPP_GLOBAL_Control
0x1401db4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1401db4c6  cmp     rcx, rax
0x1401db4c9  jz      short loc_1401DB4D9
0x1401db4cb  mov     eax, [rcx+2Ch]
0x1401db4ce  test    r12b, al
0x1401db4d1  jz      short loc_1401DB4D9
0x1401db4d3  cmp     [rcx+29h], r12b
0x1401db4d7  jnb     short loc_1401DB4DC
0x1401db4d9  mov     r14b, sil
0x1401db4dc  lea     rax, WPP_RECORDER_INITIALIZED
0x1401db4e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401db4ea  setnz   bl
0x1401db4ed  test    r14b, r14b
0x1401db4f0  jnz     short loc_1401DB4F6
0x1401db4f2  test    bl, bl
0x1401db4f4  jz      short loc_1401DB53C
0x1401db4f6  call    cs:__imp_W32GetUserSessionState
0x1401db4fd  nop     dword ptr [rax+rax+00h]
0x1401db502  mov     r9, [rax+10E10h]
0x1401db509  lea     rax, WPP_3a5b2c13686b34ca498e471343e64ddb_Traceguids
0x1401db510  mov     [rsp+118h+var_E0], rax
0x1401db515  mov     [rsp+118h+var_E8], 0Bh
0x1401db51c  mov     [rsp+118h+var_F0], r12d
0x1401db521  mov     [rsp+118h+var_F8], r12b
0x1401db526  mov     r8b, bl
0x1401db529  mov     dl, r14b
0x1401db52c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401db533  mov     rcx, [rcx+18h]
0x1401db537  call    WPP_RECORDER_AND_TRACE_SF_
0x1401db53c  mov     r14d, esi
0x1401db53f  mov     ecx, 5
0x1401db544  call    UserSetLastError
0x1401db549  jmp     loc_1401DB7E3
0x1401db54e  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db555  nop     dword ptr [rax+rax+00h]
0x1401db55a  neg     rax
0x1401db55d  sbb     r8d, r8d
0x1401db560  and     r8d, 0FFFFFFFDh
0x1401db564  add     r8d, 4; Alignment
0x1401db568  mov     edx, 40h ; '@'; Length
0x1401db56d  mov     rcx, [rsp+118h+Address]; Address
0x1401db575  call    cs:__imp_ProbeForRead
0x1401db57c  nop     dword ptr [rax+rax+00h]
0x1401db581  mov     rax, [rsp+118h+Address]
0x1401db589  movups  xmm0, xmmword ptr [rax]
0x1401db58c  movaps  [rsp+118h+var_A8], xmm0
0x1401db591  movups  xmm1, xmmword ptr [rax+10h]
0x1401db595  movaps  [rsp+118h+var_98], xmm1
0x1401db59d  movups  xmm7, xmmword ptr [rax+20h]
0x1401db5a1  movaps  xmmword ptr [rsp+118h+Buffer], xmm7
0x1401db5a9  movups  xmm6, xmmword ptr [rax+30h]
0x1401db5ad  movaps  xmmword ptr [rsp+118h+var_78], xmm6
0x1401db5b5  pextrw  eax, xmm6, 4
0x1401db5ba  movzx   edi, ax
0x1401db5bd  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db5c4  nop     dword ptr [rax+rax+00h]
0x1401db5c9  neg     rax
0x1401db5cc  sbb     r8d, r8d
0x1401db5cf  and     r8d, 0FFFFFFFDh
0x1401db5d3  add     r8d, 4; Alignment
0x1401db5d7  mov     edx, edi; Length
0x1401db5d9  movq    r12, xmm6
0x1401db5de  mov     rcx, r12; Address
0x1401db5e1  call    cs:__imp_ProbeForRead
0x1401db5e8  nop     dword ptr [rax+rax+00h]
0x1401db5ed  pextrw  edi, xmm7, 4
0x1401db5f2  movzx   r15d, di
0x1401db5f6  mov     [rsp+118h+Size], r15
0x1401db5fe  call    cs:__imp_PsGetCurrentProcessWow64Process
0x1401db605  nop     dword ptr [rax+rax+00h]
0x1401db60a  neg     rax
0x1401db60d  sbb     r8d, r8d
0x1401db610  and     r8d, 0FFFFFFFDh
0x1401db614  add     r8d, 4; Alignment
0x1401db618  mov     edx, r15d; Length
0x1401db61b  movq    r15, xmm7
0x1401db620  mov     rcx, r15; Address
0x1401db623  call    cs:__imp_ProbeForRead
0x1401db62a  nop     dword ptr [rax+rax+00h]
0x1401db62f  test    di, di
0x1401db632  jz      short loc_1401DB68A
0x1401db634  mov     [rsp+118h+Src], r15
0x1401db639  mov     r8d, 74697355h; unsigned int
0x1401db63f  movzx   edx, di; unsigned __int64
0x1401db642  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401db647  mov     r15, rax
0x1401db64a  mov     [rsp+118h+Buffer], rax
0x1401db652  test    rax, rax
0x1401db655  jnz     short loc_1401DB66B
0x1401db657  mov     r14d, esi
0x1401db65a  mov     [rsp+118h+var_D4], esi
0x1401db65e  lea     ecx, [rax+8]
0x1401db661  call    UserSetLastError
0x1401db666  jmp     loc_1401DB7C7
0x1401db66b  mov     dil, r14b
0x1401db66e  mov     [rsp+118h+var_D7], r14b
0x1401db673  mov     r8, [rsp+118h+Size]; Size
0x1401db67b  mov     rdx, [rsp+118h+Src]; Src
0x1401db680  mov     rcx, rax; void *
0x1401db683  call    memmove
0x1401db688  jmp     short loc_1401DB68F
0x1401db68a  mov     dil, [rsp+118h+var_D7]
0x1401db68f  pextrw  eax, xmm6, 4
0x1401db694  test    ax, ax
0x1401db697  jz      short loc_1401DB6F0
0x1401db699  mov     [rsp+118h+Src], r12
0x1401db69e  mov     r8d, 74697355h; unsigned int
0x1401db6a4  movzx   edx, ax; unsigned __int64
0x1401db6a7  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401db6ac  mov     r12, rax
0x1401db6af  mov     [rsp+118h+var_78], rax
0x1401db6b7  test    rax, rax
0x1401db6ba  jnz     short loc_1401DB6D0
0x1401db6bc  mov     r14d, esi
0x1401db6bf  mov     [rsp+118h+var_D4], esi
0x1401db6c3  lea     ecx, [rax+8]
0x1401db6c6  call    UserSetLastError
0x1401db6cb  jmp     loc_1401DB7C7
0x1401db6d0  mov     r13b, r14b
0x1401db6d3  mov     [rsp+118h+var_D8], r14b
0x1401db6d8  pextrw  r8d, xmm6, 4
0x1401db6de  movzx   r8d, r8w; Size
0x1401db6e2  mov     rdx, [rsp+118h+Src]; Src
0x1401db6e7  mov     rcx, rax; void *
0x1401db6ea  call    memmove
0x1401db6ef  nop
0x1401db6f0  test    r15, r15
0x1401db6f3  jnz     short loc_1401DB706
0x1401db6f5  mov     r14d, esi
0x1401db6f8  lea     ecx, [r15+57h]
0x1401db6fc  call    UserSetLastError
0x1401db701  jmp     loc_1401DB7C7
0x1401db706  lea     rdx, [rsp+118h+arg_18]
0x1401db70e  lea     rcx, [rsp+118h+var_A8]
0x1401db713  call    RIMIDE_CreateGenericHidDevice
0x1401db718  test    eax, eax
0x1401db71a  js      short loc_1401DB754
0x1401db71c  mov     rdx, [rsp+118h+arg_18]
0x1401db724  mov     rcx, rbx
0x1401db727  call    RtlWriteULong64ToUser
0x1401db72c  mov     [rsp+118h+var_D4], r14d
0x1401db731  jmp     short loc_1401DB796
0x1401db733  xor     r14d, r14d
0x1401db736  mov     [rsp+118h+var_D4], r14d
0x1401db73b  xor     esi, esi
0x1401db73d  mov     r12, [rsp+118h+var_78]
0x1401db745  mov     r15, [rsp+118h+Buffer]
0x1401db74d  mov     r13b, [rsp+118h+var_D8]
0x1401db752  jmp     short loc_1401DB7C7
0x1401db754  cmp     eax, 80000011h
0x1401db759  jnz     short loc_1401DB789
0x1401db75b  test    dil, dil
0x1401db75e  jz      short loc_1401DB76D
0x1401db760  mov     rcx, [rsp+118h+Buffer]; Buffer
0x1401db768  call    GreDeleteFastMutex
0x1401db76d  test    r13b, r13b
0x1401db770  jz      short loc_1401DB77F
0x1401db772  mov     rcx, [rsp+118h+var_78]; Buffer
0x1401db77a  call    GreDeleteFastMutex
0x1401db77f  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db784  jmp     loc_1401DB3EA
0x1401db789  mov     r14d, esi
0x1401db78c  mov     ecx, 57h ; 'W'
0x1401db791  call    UserSetLastError
0x1401db796  mov     r12, [rsp+118h+var_78]
0x1401db79e  mov     r15, [rsp+118h+Buffer]
0x1401db7a6  jmp     short loc_1401DB7C7
0x1401db7a8  xor     r14d, r14d
0x1401db7ab  mov     [rsp+118h+var_D4], r14d
0x1401db7b0  xor     esi, esi
0x1401db7b2  mov     r12, [rsp+118h+var_78]
0x1401db7ba  mov     r15, [rsp+118h+Buffer]
0x1401db7c2  mov     r13b, [rsp+118h+var_D8]
0x1401db7c7  cmp     [rsp+118h+var_D7], sil
0x1401db7cc  jz      short loc_1401DB7D6
0x1401db7ce  mov     rcx, r15; Buffer
0x1401db7d1  call    GreDeleteFastMutex
0x1401db7d6  test    r13b, r13b
0x1401db7d9  jz      short loc_1401DB7E3
0x1401db7db  mov     rcx, r12; Buffer
0x1401db7de  call    GreDeleteFastMutex
0x1401db7e3  call    UserSessionSwitchLeaveCritWithNonPaged
0x1401db7e8  movsxd  rax, r14d
0x1401db7eb  lea     r11, [rsp+118h+var_38]
0x1401db7f3  movaps  xmm6, xmmword ptr [r11-10h]
0x1401db7f8  movaps  xmm7, xmmword ptr [r11-20h]
0x1401db7fd  mov     rsp, r11
0x1401db800  pop     r15
0x1401db802  pop     r14
0x1401db804  pop     r13
0x1401db806  pop     r12
0x1401db808  pop     rdi
0x1401db809  pop     rsi
0x1401db80a  pop     rbx
0x1401db80b  retn
0x14023a60b  push    rbp
0x14023a60d  sub     rsp, 40h
0x14023a611  mov     rbp, rdx
0x14023a614  mov     rax, [rcx]
0x14023a617  mov     ecx, [rax]
0x14023a619  mov     [rbp+58h], ecx
0x14023a61c  mov     ecx, [rbp+58h]
0x14023a61f  call    SetLastNtError
0x14023a624  mov     dword ptr [rbp+60h], 1
0x14023a62b  mov     eax, [rbp+60h]
0x14023a62e  add     rsp, 40h
0x14023a632  pop     rbp
0x14023a633  retn
0x14023a635  push    rbp
0x14023a637  sub     rsp, 40h
0x14023a63b  mov     rbp, rdx
0x14023a63e  mov     rax, [rcx]
0x14023a641  mov     ecx, [rax]
0x14023a643  mov     [rbp+48h], ecx
0x14023a646  mov     ecx, [rbp+48h]
0x14023a649  call    SetLastNtError
0x14023a64e  mov     dword ptr [rbp+50h], 1
0x14023a655  mov     eax, [rbp+50h]
0x14023a658  add     rsp, 40h
0x14023a65c  pop     rbp
0x14023a65d  retn
```
