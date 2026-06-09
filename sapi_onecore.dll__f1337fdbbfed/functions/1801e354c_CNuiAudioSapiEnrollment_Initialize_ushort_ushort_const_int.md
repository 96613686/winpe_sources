# CNuiAudioSapiEnrollment::Initialize(ushort,ushort const *,int)

- ea: `0x1801e354c`
- end: `0x1801e3a40`
- name: `?Initialize@CNuiAudioSapiEnrollment@@QEAAJGPEBGH@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CNuiAudioSapiEnrollment *__hidden this, unsigned __int16, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801b7624`
- `0x1801e5ad4`

## callees

- `0x180079e30`
- `0x18007aae4`
- `0x1801e354c`
- `0x1801e3a48`
- `0x1801e3afc`
- `0x1801e4218`
- `0x1801e44f8`
- `0x1801e4614`
- `0x1801e46c8`
- `0x1801e6000`
- `0x1801e9c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801e3782`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801e3782`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e3642`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e36a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e3642`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e36a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e365a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e36b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e365a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e36b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e3948`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801e393e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1801e393e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801e35fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801e35fd`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncEnumBiometricUnits` at `0x1801e378f`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncEnumBiometricUnits` at `0x1801e378f`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenFramework` at `0x1801e3763`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenFramework` at `0x1801e3763`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenSession` at `0x1801e3726`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenSession` at `0x1801e3726`

## pseudocode

```c
__int64 __fastcall CNuiAudioSapiEnrollment::Initialize(
        CNuiAudioSapiEnrollment *this,
        __int16 a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  HRESULT SID; // eax
  signed int v13; // ebx
  const char *v14; // r8
  LPVOID v15; // rax
  int v16; // r9d
  HANDLE EventA; // rax
  signed int LastError; // eax
  HANDLE v19; // rax
  signed int v20; // eax
  unsigned int v21; // r8d
  unsigned int i; // edx
  signed int v23; // eax
  int v24; // eax
  const char *v25; // r8
  SIZE_T v27[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v28[3]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v29[2]; // [rsp+B0h] [rbp-50h]
  CHAR MultiByteStr[2]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(v28, 0, 0x4Cu);
  v8 = v28[1];
  *((_OWORD *)this + 1) = v28[0];
  v9 = v28[2];
  *((_OWORD *)this + 2) = v8;
  *((_WORD *)this + 6) = a2;
  v10 = v29[0];
  *((_OWORD *)this + 3) = v9;
  *((_DWORD *)this + 30) = 0;
  v11 = *(_OWORD *)((char *)v29 + 12);
  *((_OWORD *)this + 4) = v10;
  *(_OWORD *)((char *)this + 76) = v11;
  SID = GetSID((struct _WINBIO_IDENTITY *)((char *)this + 16));
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "69";
LABEL_55:
    v16 = SID;
    goto LABEL_56;
  }
  *((_QWORD *)this + 12) = 204800;
  if ( !*((_QWORD *)this + 13) )
  {
    v15 = CoTaskMemAlloc(0x32000u);
    *((_QWORD *)this + 13) = v15;
    if ( !v15 )
    {
      v13 = -2147024882;
      *((_QWORD *)this + 12) = 0;
      v16 = -2147024882;
      v14 = "70";
      goto LABEL_56;
    }
  }
  if ( ((*((_QWORD *)this + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    EventA = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 16) = EventA;
    if ( (((unsigned __int64)EventA + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( v13 < 0 )
      {
        v16 = v13;
        v14 = "80";
        goto LABEL_56;
      }
    }
  }
  if ( ((*((_QWORD *)this + 17) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v19 = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 17) = v19;
    if ( (((unsigned __int64)v19 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v20 = GetLastError();
      v13 = v20;
      if ( v20 > 0 )
        v13 = (unsigned __int16)v20 | 0x80070000;
      if ( v13 < 0 )
      {
        v16 = v13;
        v14 = "90";
        goto LABEL_56;
      }
    }
  }
  SID = WinBioAsyncOpenSession(
          4u,
          1u,
          0,
          0,
          0,
          (GUID *)1,
          WINBIO_ASYNC_NOTIFY_CALLBACK,
          0,
          0,
          CNuiAudioSapiEnrollment::WbsAsyncCallback,
          this,
          0,
          (WINBIO_SESSION_HANDLE *)this);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "107";
    goto LABEL_55;
  }
  SID = WinBioAsyncOpenFramework(
          WINBIO_ASYNC_NOTIFY_CALLBACK,
          0,
          0,
          CNuiAudioSapiEnrollment::WbsAsyncCallback,
          this,
          0,
          (WINBIO_FRAMEWORK_HANDLE *)this + 1);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "117";
    goto LABEL_55;
  }
  ResetEvent(*((HANDLE *)this + 16));
  SID = WinBioAsyncEnumBiometricUnits(*((_DWORD *)this + 1), 4u);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "123";
    goto LABEL_55;
  }
  SID = CNuiAudioSapiEnrollment::WaitForAsyncOperationCompletion(this, *((void **)this + 16), v21);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "125";
    goto LABEL_55;
  }
  if ( *((_DWORD *)this + 2) == -1 )
  {
    v13 = -2147483391;
    v14 = "129";
    v16 = -2147483391;
    goto LABEL_56;
  }
  SID = CNuiAudioSapiEnrollment::LockVoiceBioUnit(this);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "133";
    goto LABEL_55;
  }
  SID = CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(this, 1u, (PUCHAR)this + 16, 0x4Cu);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "139";
    goto LABEL_55;
  }
  SID = CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(this, 2u, (PUCHAR)this + 14, 1u);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "144";
    goto LABEL_55;
  }
  v27[0] = 0;
  if ( a4 )
  {
    memset_0(MultiByteStr, 0, 0xC8u);
    SID = CNuiAudioSapiEnrollment::ReceiveWinBioControlUnitCommand(
            this,
            0xCu,
            (unsigned __int8 *)MultiByteStr,
            0xC8u,
            v27);
    v13 = SID;
    if ( SID < 0 )
    {
      v14 = "158";
      goto LABEL_55;
    }
    if ( v27[0] >> 1 )
    {
      for ( i = 0; i < v27[0] >> 1; ++i )
      {
        if ( *(_WORD *)&MultiByteStr[2 * i] == *((_WORD *)this + 6) )
          goto LABEL_43;
      }
      v13 = -2147200942;
      v14 = "176";
      v16 = -2147200942;
LABEL_56:
      DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "CNuiAudioSapiEnrollment::Initialize", v14, v16);
      v24 = CNuiAudioSapiEnrollment::Uninitialize(this);
      if ( v24 < 0 )
      {
        v25 = "209";
LABEL_60:
        DumpTraceWin32(
          "Function %s(%s) : *** TRACE *** code = 0x%x!\n",
          "CNuiAudioSapiEnrollment::Initialize",
          v25,
          v24);
        return (unsigned int)v13;
      }
      return (unsigned int)v13;
    }
  }
LABEL_43:
  SID = CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(this, 3u, (PUCHAR)this + 12, 2u);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "183";
    goto LABEL_55;
  }
  if ( a3 )
  {
    memset_0(MultiByteStr, 0, 0x104u);
    if ( !WideCharToMultiByte(0, 0x400u, a3, -1, MultiByteStr, 260, 0, 0) )
    {
      v23 = GetLastError();
      v13 = v23;
      if ( v23 > 0 )
        v13 = (unsigned __int16)v23 | 0x80070000;
      if ( v13 < 0 )
      {
        v16 = v13;
        v14 = "191";
        goto LABEL_56;
      }
    }
    SID = CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(this, 5u, (PUCHAR)MultiByteStr, 0x104u);
    v13 = SID;
    if ( SID < 0 )
    {
      v14 = "196";
      goto LABEL_55;
    }
  }
  SID = CNuiAudioSapiEnrollment::ReceiveWinBioControlUnitCommand(
          this,
          0xBu,
          &CNuiAudioSapiEnrollment::s_ui32VAConfig,
          4u,
          v27);
  v13 = SID;
  if ( SID < 0 )
  {
    v14 = "204";
    goto LABEL_55;
  }
  v24 = CNuiAudioSapiEnrollment::UnlockVoiceBioUnit(this);
  if ( v24 < 0 )
  {
    v25 = "213";
    goto LABEL_60;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801e354c  mov     [rsp-8+arg_8], rbx
0x1801e3551  push    rbp
0x1801e3552  push    rsi
0x1801e3553  push    rdi
0x1801e3554  push    r12
0x1801e3556  push    r13
0x1801e3558  push    r14
0x1801e355a  push    r15
0x1801e355c  lea     rbp, [rsp-0F0h]
0x1801e3564  sub     rsp, 1F0h
0x1801e356b  mov     rax, cs:__security_cookie
0x1801e3572  xor     rax, rsp
0x1801e3575  mov     [rbp+120h+var_40], rax
0x1801e357c  movzx   ebx, dx
0x1801e357f  mov     r12, r8
0x1801e3582  xor     edx, edx; Val
0x1801e3584  mov     rdi, rcx
0x1801e3587  lea     rcx, [rbp+120h+var_1A0]; void *
0x1801e358b  mov     r13d, r9d
0x1801e358e  lea     r8d, [rdx+4Ch]; Size
0x1801e3592  call    memset_0
0x1801e3597  movaps  xmm0, [rbp+120h+var_1A0]
0x1801e359b  lea     r14, [rdi+10h]
0x1801e359f  movaps  xmm1, [rbp+120h+var_190]
0x1801e35a3  lea     r15, [rdi+0Ch]
0x1801e35a7  movups  xmmword ptr [r14], xmm0
0x1801e35ab  xor     esi, esi
0x1801e35ad  mov     rcx, r14; struct _WINBIO_IDENTITY *
0x1801e35b0  movaps  xmm0, [rbp+120h+var_180]
0x1801e35b4  movups  xmmword ptr [r14+10h], xmm1
0x1801e35b9  mov     [r15], bx
0x1801e35bd  movaps  xmm1, xmmword ptr [rbp+120h+var_170]
0x1801e35c1  movups  xmmword ptr [r14+20h], xmm0
0x1801e35c6  mov     [rdi+78h], esi
0x1801e35c9  movups  xmm0, xmmword ptr [rbp+120h+var_170+0Ch]
0x1801e35cd  movups  xmmword ptr [r14+30h], xmm1
0x1801e35d2  movups  xmmword ptr [r14+3Ch], xmm0
0x1801e35d7  call    ?GetSID@@YAJPEAU_WINBIO_IDENTITY@@@Z; GetSID(_WINBIO_IDENTITY *)
0x1801e35dc  mov     ebx, eax
0x1801e35de  test    eax, eax
0x1801e35e0  jns     short loc_1801E35EE
0x1801e35e2  lea     r8, a69; "69"
0x1801e35e9  jmp     loc_1801E39C0
0x1801e35ee  mov     ecx, 32000h; cb
0x1801e35f3  mov     [rdi+60h], rcx
0x1801e35f7  cmp     [rdi+68h], rsi
0x1801e35fb  jnz     short loc_1801E3624
0x1801e35fd  call    cs:__imp_CoTaskMemAlloc
0x1801e3603  mov     [rdi+68h], rax
0x1801e3607  test    rax, rax
0x1801e360a  jnz     short loc_1801E3624
0x1801e360c  mov     ebx, 8007000Eh
0x1801e3611  mov     [rdi+60h], rsi
0x1801e3615  mov     r9d, ebx
0x1801e3618  lea     r8, a70; "70"
0x1801e361f  jmp     loc_1801E39C3
0x1801e3624  mov     rax, [rdi+80h]
0x1801e362b  inc     rax
0x1801e362e  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e3634  jnz     short loc_1801E3682
0x1801e3636  xor     r9d, r9d; lpName
0x1801e3639  xor     r8d, r8d; bInitialState
0x1801e363c  xor     ecx, ecx; lpEventAttributes
0x1801e363e  lea     edx, [r9+1]; bManualReset
0x1801e3642  call    cs:__imp_CreateEventA
0x1801e3648  mov     [rdi+80h], rax
0x1801e364f  inc     rax
0x1801e3652  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e3658  jnz     short loc_1801E3682
0x1801e365a  call    cs:__imp_GetLastError
0x1801e3660  mov     ebx, eax
0x1801e3662  test    eax, eax
0x1801e3664  jle     short loc_1801E366F
0x1801e3666  movzx   ebx, ax
0x1801e3669  or      ebx, 80070000h
0x1801e366f  test    ebx, ebx
0x1801e3671  jns     short loc_1801E3682
0x1801e3673  mov     r9d, ebx
0x1801e3676  lea     r8, a80; "80"
0x1801e367d  jmp     loc_1801E39C3
0x1801e3682  mov     rax, [rdi+88h]
0x1801e3689  inc     rax
0x1801e368c  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e3692  jnz     short loc_1801E36E0
0x1801e3694  xor     r9d, r9d; lpName
0x1801e3697  xor     r8d, r8d; bInitialState
0x1801e369a  xor     ecx, ecx; lpEventAttributes
0x1801e369c  lea     edx, [r9+1]; bManualReset
0x1801e36a0  call    cs:__imp_CreateEventA
0x1801e36a6  mov     [rdi+88h], rax
0x1801e36ad  inc     rax
0x1801e36b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e36b6  jnz     short loc_1801E36E0
0x1801e36b8  call    cs:__imp_GetLastError
0x1801e36be  mov     ebx, eax
0x1801e36c0  test    eax, eax
0x1801e36c2  jle     short loc_1801E36CD
0x1801e36c4  movzx   ebx, ax
0x1801e36c7  or      ebx, 80070000h
0x1801e36cd  test    ebx, ebx
0x1801e36cf  jns     short loc_1801E36E0
0x1801e36d1  mov     r9d, ebx
0x1801e36d4  lea     r8, a90; "90"
0x1801e36db  jmp     loc_1801E39C3
0x1801e36e0  mov     [rsp+220h+SessionHandle], rdi; SessionHandle
0x1801e36e5  lea     rax, ?WbsAsyncCallback@CNuiAudioSapiEnrollment@@CAXPEAU_WINBIO_ASYNC_RESULT@@@Z; CNuiAudioSapiEnrollment::WbsAsyncCallback(_WINBIO_ASYNC_RESULT *)
0x1801e36ec  mov     [rsp+220h+AsynchronousOpen], esi; AsynchronousOpen
0x1801e36f0  xor     r9d, r9d; UnitArray
0x1801e36f3  mov     [rsp+220h+UserData], rdi; UserData
0x1801e36f8  xor     r8d, r8d; Flags
0x1801e36fb  mov     [rsp+220h+CallbackRoutine], rax; CallbackRoutine
0x1801e3700  mov     [rsp+220h+MessageCode], esi; MessageCode
0x1801e3704  mov     [rsp+220h+TargetWindow], rsi; TargetWindow
0x1801e3709  lea     edx, [r9+1]; PoolType
0x1801e370d  mov     [rsp+220h+NotificationMethod], 1; NotificationMethod
0x1801e3715  lea     ecx, [rdx+3]; Factor
0x1801e3718  mov     [rsp+220h+DatabaseId], 1; DatabaseId
0x1801e3721  mov     [rsp+220h+UnitCount], rsi; UnitCount
0x1801e3726  call    cs:__imp_WinBioAsyncOpenSession
0x1801e372c  mov     ebx, eax
0x1801e372e  test    eax, eax
0x1801e3730  jns     short loc_1801E373E
0x1801e3732  lea     r8, a107; "107"
0x1801e3739  jmp     loc_1801E39C0
0x1801e373e  xor     edx, edx; TargetWindow
0x1801e3740  lea     rsi, [rdi+4]
0x1801e3744  mov     qword ptr [rsp+220h+NotificationMethod], rsi; FrameworkHandle
0x1801e3749  lea     r9, ?WbsAsyncCallback@CNuiAudioSapiEnrollment@@CAXPEAU_WINBIO_ASYNC_RESULT@@@Z; CallbackRoutine
0x1801e3750  mov     dword ptr [rsp+220h+DatabaseId], 0; AsynchronousOpen
0x1801e3758  xor     r8d, r8d; MessageCode
0x1801e375b  mov     [rsp+220h+UnitCount], rdi; UserData
0x1801e3760  lea     ecx, [rdx+1]; NotificationMethod
0x1801e3763  call    cs:__imp_WinBioAsyncOpenFramework
0x1801e3769  mov     ebx, eax
0x1801e376b  test    eax, eax
0x1801e376d  jns     short loc_1801E377B
0x1801e376f  lea     r8, a117; "117"
0x1801e3776  jmp     loc_1801E39C0
0x1801e377b  mov     rcx, [rdi+80h]; hEvent
0x1801e3782  call    cs:__imp_ResetEvent
0x1801e3788  mov     ecx, [rsi]; FrameworkHandle
0x1801e378a  mov     edx, 4; Factor
0x1801e378f  call    cs:__imp_WinBioAsyncEnumBiometricUnits
0x1801e3795  xor     esi, esi
0x1801e3797  mov     ebx, eax
0x1801e3799  test    eax, eax
0x1801e379b  jns     short loc_1801E37A9
0x1801e379d  lea     r8, a123; "123"
0x1801e37a4  jmp     loc_1801E39C0
0x1801e37a9  mov     rdx, [rdi+80h]; void *
0x1801e37b0  mov     rcx, rdi; this
0x1801e37b3  call    ?WaitForAsyncOperationCompletion@CNuiAudioSapiEnrollment@@AEAAJPEAXK@Z; CNuiAudioSapiEnrollment::WaitForAsyncOperationCompletion(void *,ulong)
0x1801e37b8  mov     ebx, eax
0x1801e37ba  test    eax, eax
0x1801e37bc  jns     short loc_1801E37CA
0x1801e37be  lea     r8, a125; "125"
0x1801e37c5  jmp     loc_1801E39C0
0x1801e37ca  cmp     dword ptr [rdi+8], 0FFFFFFFFh
0x1801e37ce  jnz     short loc_1801E37E4
0x1801e37d0  mov     ebx, 80000101h
0x1801e37d5  lea     r8, a129; "129"
0x1801e37dc  mov     r9d, ebx
0x1801e37df  jmp     loc_1801E39C3
0x1801e37e4  mov     rcx, rdi; this
0x1801e37e7  call    ?LockVoiceBioUnit@CNuiAudioSapiEnrollment@@AEAAJXZ; CNuiAudioSapiEnrollment::LockVoiceBioUnit(void)
0x1801e37ec  mov     ebx, eax
0x1801e37ee  test    eax, eax
0x1801e37f0  jns     short loc_1801E37FE
0x1801e37f2  lea     r8, a133; "133"
0x1801e37f9  jmp     loc_1801E39C0
0x1801e37fe  mov     r9d, 4Ch ; 'L'; SendBufferSize
0x1801e3804  mov     r8, r14; SendBuffer
0x1801e3807  mov     rcx, rdi; this
0x1801e380a  lea     r14d, [r9-4Bh]
0x1801e380e  mov     edx, r14d; ControlCode
0x1801e3811  call    ?SendWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_K@Z; CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(ulong,uchar *,unsigned __int64)
0x1801e3816  mov     ebx, eax
0x1801e3818  test    eax, eax
0x1801e381a  jns     short loc_1801E3828
0x1801e381c  lea     r8, a139; "139"
0x1801e3823  jmp     loc_1801E39C0
0x1801e3828  lea     r8, [rdi+0Eh]; SendBuffer
0x1801e382c  mov     r9, r14; SendBufferSize
0x1801e382f  mov     edx, 2; ControlCode
0x1801e3834  mov     rcx, rdi; this
0x1801e3837  call    ?SendWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_K@Z; CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(ulong,uchar *,unsigned __int64)
0x1801e383c  mov     ebx, eax
0x1801e383e  test    eax, eax
0x1801e3840  jns     short loc_1801E384E
0x1801e3842  lea     r8, a144; "144"
0x1801e3849  jmp     loc_1801E39C0
0x1801e384e  mov     [rsp+220h+var_1B0], rsi
0x1801e3853  test    r13d, r13d
0x1801e3856  jz      short loc_1801E38D4
0x1801e3858  mov     ebx, 0C8h
0x1801e385d  lea     rcx, [rbp+120h+MultiByteStr]; void *
0x1801e3861  mov     r8d, ebx; Size
0x1801e3864  xor     edx, edx; Val
0x1801e3866  call    memset_0
0x1801e386b  lea     rax, [rsp+220h+var_1B0]
0x1801e3870  mov     r9d, ebx; DestinationSize
0x1801e3873  lea     r8, [rbp+120h+MultiByteStr]; Destination
0x1801e3877  mov     [rsp+220h+UnitCount], rax; SIZE_T *
0x1801e387c  mov     edx, 0Ch; ControlCode
0x1801e3881  mov     rcx, rdi; this
0x1801e3884  call    ?ReceiveWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_KPEA_K@Z; CNuiAudioSapiEnrollment::ReceiveWinBioControlUnitCommand(ulong,uchar *,unsigned __int64,unsigned __int64 *)
0x1801e3889  mov     ebx, eax
0x1801e388b  test    eax, eax
0x1801e388d  jns     short loc_1801E389B
0x1801e388f  lea     r8, a158; "158"
0x1801e3896  jmp     loc_1801E39C0
0x1801e389b  mov     rcx, [rsp+220h+var_1B0]
0x1801e38a0  shr     rcx, 1
0x1801e38a3  jz      short loc_1801E38D4
0x1801e38a5  mov     edx, esi
0x1801e38a7  mov     r8d, edx
0x1801e38aa  cmp     r8, rcx
0x1801e38ad  jnb     short loc_1801E38C0
0x1801e38af  movzx   eax, word ptr [r15]
0x1801e38b3  cmp     word ptr [rbp+r8*2+120h+MultiByteStr], ax
0x1801e38b9  jz      short loc_1801E38D4
0x1801e38bb  add     edx, r14d
0x1801e38be  jmp     short loc_1801E38A7
0x1801e38c0  mov     ebx, 80045052h
0x1801e38c5  lea     r8, a176; "176"
0x1801e38cc  mov     r9d, ebx
0x1801e38cf  jmp     loc_1801E39C3
0x1801e38d4  mov     r9d, 2; SendBufferSize
0x1801e38da  mov     r8, r15; SendBuffer
0x1801e38dd  mov     rcx, rdi; this
0x1801e38e0  lea     edx, [r9+1]; ControlCode
0x1801e38e4  call    ?SendWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_K@Z; CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(ulong,uchar *,unsigned __int64)
0x1801e38e9  mov     ebx, eax
0x1801e38eb  test    eax, eax
0x1801e38ed  jns     short loc_1801E38FB
0x1801e38ef  lea     r8, a183; "183"
0x1801e38f6  jmp     loc_1801E39C0
0x1801e38fb  test    r12, r12
0x1801e38fe  jz      loc_1801E3990
0x1801e3904  mov     r14d, 104h
0x1801e390a  lea     rcx, [rbp+120h+MultiByteStr]; void *
0x1801e390e  mov     r8d, r14d; Size
0x1801e3911  xor     edx, edx; Val
0x1801e3913  call    memset_0
0x1801e3918  mov     [rsp+220h+TargetWindow], rsi; lpUsedDefaultChar
0x1801e391d  lea     rax, [rbp+120h+MultiByteStr]
0x1801e3921  mov     qword ptr [rsp+220h+NotificationMethod], rsi; lpDefaultChar
0x1801e3926  or      r9d, 0FFFFFFFFh; cchWideChar
0x1801e392a  mov     dword ptr [rsp+220h+DatabaseId], r14d; cbMultiByte
0x1801e392f  mov     r8, r12; lpWideCharStr
0x1801e3932  mov     edx, 400h; dwFlags
0x1801e3937  mov     [rsp+220h+UnitCount], rax; lpMultiByteStr
0x1801e393c  xor     ecx, ecx; CodePage
0x1801e393e  call    cs:__imp_WideCharToMultiByte
0x1801e3944  test    eax, eax
0x1801e3946  jnz     short loc_1801E396D
0x1801e3948  call    cs:__imp_GetLastError
0x1801e394e  mov     ebx, eax
0x1801e3950  test    eax, eax
0x1801e3952  jle     short loc_1801E395D
0x1801e3954  movzx   ebx, ax
0x1801e3957  or      ebx, 80070000h
0x1801e395d  test    ebx, ebx
0x1801e395f  jns     short loc_1801E396D
0x1801e3961  mov     r9d, ebx
0x1801e3964  lea     r8, a191; "191"
0x1801e396b  jmp     short loc_1801E39C3
0x1801e396d  mov     r9, r14; SendBufferSize
0x1801e3970  lea     r8, [rbp+120h+MultiByteStr]; SendBuffer
0x1801e3974  mov     edx, 5; ControlCode
0x1801e3979  mov     rcx, rdi; this
0x1801e397c  call    ?SendWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_K@Z; CNuiAudioSapiEnrollment::SendWinBioControlUnitCommand(ulong,uchar *,unsigned __int64)
0x1801e3981  mov     ebx, eax
0x1801e3983  test    eax, eax
0x1801e3985  jns     short loc_1801E3990
0x1801e3987  lea     r8, a196; "196"
0x1801e398e  jmp     short loc_1801E39C0
0x1801e3990  mov     r9d, 4; DestinationSize
0x1801e3996  lea     rax, [rsp+220h+var_1B0]
0x1801e399b  lea     r8, ?s_ui32VAConfig@CNuiAudioSapiEnrollment@@0IA; Destination
0x1801e39a2  mov     [rsp+220h+UnitCount], rax; SIZE_T *
0x1801e39a7  mov     rcx, rdi; this
0x1801e39aa  lea     edx, [r9+7]; ControlCode
0x1801e39ae  call    ?ReceiveWinBioControlUnitCommand@CNuiAudioSapiEnrollment@@AEAAJKPEAE_KPEA_K@Z; CNuiAudioSapiEnrollment::ReceiveWinBioControlUnitCommand(ulong,uchar *,unsigned __int64,unsigned __int64 *)
0x1801e39b3  mov     ebx, eax
0x1801e39b5  test    eax, eax
0x1801e39b7  jns     short loc_1801E39EB
0x1801e39b9  lea     r8, a204; "204"
0x1801e39c0  mov     r9d, eax; int
0x1801e39c3  lea     rdx, aCnuiaudiosapie_2; "CNuiAudioSapiEnrollment::Initialize"
0x1801e39ca  lea     rcx, aFunctionSSTrac_0; "Function %s(%s) : *** TRACE *** code = "...
0x1801e39d1  call    ?DumpTraceWin32@@YAXPEBD00H@Z; DumpTraceWin32(char const *,char const *,char const *,int)
0x1801e39d6  mov     rcx, rdi; this
0x1801e39d9  call    ?Uninitialize@CNuiAudioSapiEnrollment@@QEAAJXZ; CNuiAudioSapiEnrollment::Uninitialize(void)
0x1801e39de  test    eax, eax
0x1801e39e0  jns     short loc_1801E3A14
0x1801e39e2  lea     r8, a209; "209"
0x1801e39e9  jmp     short loc_1801E39FE
0x1801e39eb  mov     rcx, rdi; this
0x1801e39ee  call    ?UnlockVoiceBioUnit@CNuiAudioSapiEnrollment@@AEAAJXZ; CNuiAudioSapiEnrollment::UnlockVoiceBioUnit(void)
  ... truncated ...
```
