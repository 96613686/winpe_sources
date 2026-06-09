# CNuiAudioWbsAsyncWrapper::Initialize(ushort,int,void const *,void (*)(void const *),void (*)(void const *),void (*)(void const *))

- ea: `0x1801e48d8`
- end: `0x1801e4ad8`
- name: `?Initialize@CNuiAudioWbsAsyncWrapper@@QEAAJGHPEBXP6AX0@Z11@Z`
- size: `512`
- prototype: `__int64 __fastcall(CNuiAudioWbsAsyncWrapper *__hidden this, unsigned __int16, int, const void *, void (*)(const void *), void (*)(const void *), void (*)(const void *))`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801b8860`

## callees

- `0x18007aae4`
- `0x1801e48d8`
- `0x1801e4de0`
- `0x1801e9b84`
- `0x1801e9c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e4ab5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801e4ab5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801e4a7e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801e4a7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e49b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1801e49b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e49cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e49cb`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncEnumBiometricUnits` at `0x1801e4a95`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncEnumBiometricUnits` at `0x1801e4a95`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenFramework` at `0x1801e4a61`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenFramework` at `0x1801e4a61`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenSession` at `0x1801e4a39`
- `ext-ms-win-biometrics-winbio-core-l1-1-0!WinBioAsyncOpenSession` at `0x1801e4a39`

## pseudocode

```c
__int64 __fastcall CNuiAudioWbsAsyncWrapper::Initialize(
        CNuiAudioWbsAsyncWrapper *this,
        __int16 a2,
        int a3,
        const void *a4)
{
  __int128 v6; // xmm0
  struct _WINBIO_IDENTITY *v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  int SID; // eax
  int v13; // ebx
  HANDLE EventA; // rax
  signed int LastError; // eax
  char *v16; // rcx
  WINBIO_FRAMEWORK_HANDLE v17; // ecx
  char *v18; // rcx
  _OWORD v20[3]; // [rsp+70h] [rbp-78h] BYREF
  _OWORD v21[4]; // [rsp+A0h] [rbp-48h]

  *((_WORD *)this + 9) = a2;
  *((_QWORD *)this + 3) = a4;
  memset_0(v20, 0, 0x4Cu);
  v6 = v20[0];
  v7 = (struct _WINBIO_IDENTITY *)((char *)this + 32);
  v8 = v20[1];
  *((_WORD *)this + 8) = 1;
  *((_OWORD *)this + 2) = v6;
  v9 = v20[2];
  *((_OWORD *)this + 3) = v8;
  v10 = v21[0];
  *((_OWORD *)this + 4) = v9;
  v11 = *(_OWORD *)((char *)v21 + 12);
  *((_OWORD *)this + 5) = v10;
  *((_OWORD *)this + 7) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 146) = CSpHwVAEngine::WbsAsyncClientInitCallback;
  *((_QWORD *)this + 145) = CSpHwVAEngine::WbsAsyncClientRecoCallback;
  *((_QWORD *)this + 147) = CSpHwVAEngine::WbsAsyncClientUninitCallback;
  *(_OWORD *)((char *)this + 92) = v11;
  if ( a3 )
    SID = GetSID(v7);
  else
    SID = GetNullSID(v7);
  v13 = SID;
  if ( SID >= 0 )
  {
    if ( ((*((_QWORD *)this + 148) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_10;
    EventA = CreateEventA(0, 1, 0, 0);
    *((_QWORD *)this + 148) = EventA;
    if ( EventA != (HANDLE)-1LL )
      goto LABEL_10;
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
    {
LABEL_10:
      v13 = WinBioAsyncOpenSession(
              4u,
              1u,
              0,
              0,
              0,
              (GUID *)1,
              WINBIO_ASYNC_NOTIFY_CALLBACK,
              0,
              0,
              CNuiAudioWbsAsyncWrapper::WbsAsyncCallback,
              this,
              0,
              (WINBIO_SESSION_HANDLE *)this + 1);
      if ( v13 >= 0 )
      {
        v13 = WinBioAsyncOpenFramework(
                WINBIO_ASYNC_NOTIFY_CALLBACK,
                0,
                0,
                CNuiAudioWbsAsyncWrapper::WbsAsyncCallback,
                this,
                0,
                (WINBIO_FRAMEWORK_HANDLE *)this);
        if ( v13 >= 0 )
        {
          v16 = (char *)*((_QWORD *)this + 148);
          if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            ResetEvent(v16);
          v17 = *(_DWORD *)this;
          *((_DWORD *)this + 298) = 0;
          v13 = WinBioAsyncEnumBiometricUnits(v17, 4u);
          if ( v13 >= 0 )
          {
            v18 = (char *)*((_QWORD *)this + 148);
            if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              WaitForSingleObject(v18, 0xFFFFFFFF);
            v13 = *((_DWORD *)this + 298);
          }
        }
      }
    }
  }
  CNuiAudioWbsAsyncWrapper::RaiseInitCompletionEvent(this);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801e48d8  push    rbx
0x1801e48da  push    rbp
0x1801e48db  push    rdi
0x1801e48dc  push    r14
0x1801e48de  sub     rsp, 0C8h
0x1801e48e5  mov     [rcx+12h], dx
0x1801e48e9  mov     ebx, r8d
0x1801e48ec  xor     edx, edx; Val
0x1801e48ee  mov     [rcx+18h], r9
0x1801e48f2  mov     rdi, rcx
0x1801e48f5  lea     rcx, [rsp+0E8h+var_78]; void *
0x1801e48fa  lea     r8d, [rdx+4Ch]; Size
0x1801e48fe  call    memset_0
0x1801e4903  movaps  xmm0, [rsp+0E8h+var_78]
0x1801e4908  lea     rcx, [rdi+20h]; struct _WINBIO_IDENTITY *
0x1801e490c  movaps  xmm1, [rsp+0E8h+var_68]
0x1801e4914  xor     eax, eax
0x1801e4916  mov     ebp, 1
0x1801e491b  mov     [rdi+10h], bp
0x1801e491f  movups  xmmword ptr [rcx], xmm0
0x1801e4922  movaps  xmm0, [rsp+0E8h+var_58]
0x1801e492a  movups  xmmword ptr [rcx+10h], xmm1
0x1801e492e  movaps  xmm1, [rsp+0E8h+var_48]
0x1801e4936  movups  xmmword ptr [rcx+20h], xmm0
0x1801e493a  movups  xmm0, [rsp+0E8h+var_48+0Ch]
0x1801e4942  movups  xmmword ptr [rcx+30h], xmm1
0x1801e4946  xorps   xmm1, xmm1
0x1801e4949  movups  xmmword ptr [rdi+70h], xmm1
0x1801e494d  mov     [rdi+80h], rax
0x1801e4954  lea     rax, ?WbsAsyncClientInitCallback@CSpHwVAEngine@@CAXPEBX@Z; CSpHwVAEngine::WbsAsyncClientInitCallback(void const *)
0x1801e495b  mov     [rdi+490h], rax
0x1801e4962  lea     rax, ?WbsAsyncClientRecoCallback@CSpHwVAEngine@@CAXPEBX@Z; CSpHwVAEngine::WbsAsyncClientRecoCallback(void const *)
0x1801e4969  mov     [rdi+488h], rax
0x1801e4970  lea     rax, ?WbsAsyncClientUninitCallback@CSpHwVAEngine@@CAXPEBX@Z; CSpHwVAEngine::WbsAsyncClientUninitCallback(void const *)
0x1801e4977  mov     [rdi+498h], rax
0x1801e497e  movups  xmmword ptr [rcx+3Ch], xmm0
0x1801e4982  test    ebx, ebx
0x1801e4984  jz      short loc_1801E498D
0x1801e4986  call    ?GetSID@@YAJPEAU_WINBIO_IDENTITY@@@Z; GetSID(_WINBIO_IDENTITY *)
0x1801e498b  jmp     short loc_1801E4992
0x1801e498d  call    ?GetNullSID@@YAJPEAU_WINBIO_IDENTITY@@@Z; GetNullSID(_WINBIO_IDENTITY *)
0x1801e4992  mov     ebx, eax
0x1801e4994  test    eax, eax
0x1801e4996  js      loc_1801E4AC1
0x1801e499c  mov     rax, [rdi+4A0h]
0x1801e49a3  add     rax, rbp
0x1801e49a6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e49ac  jnz     short loc_1801E49E8
0x1801e49ae  xor     r9d, r9d; lpName
0x1801e49b1  xor     r8d, r8d; bInitialState
0x1801e49b4  mov     edx, ebp; bManualReset
0x1801e49b6  xor     ecx, ecx; lpEventAttributes
0x1801e49b8  call    cs:__imp_CreateEventA
0x1801e49be  mov     [rdi+4A0h], rax
0x1801e49c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801e49c9  jnz     short loc_1801E49E8
0x1801e49cb  call    cs:__imp_GetLastError
0x1801e49d1  mov     ebx, eax
0x1801e49d3  test    eax, eax
0x1801e49d5  jle     short loc_1801E49E0
0x1801e49d7  movzx   ebx, ax
0x1801e49da  or      ebx, 80070000h
0x1801e49e0  test    ebx, ebx
0x1801e49e2  js      loc_1801E4AC1
0x1801e49e8  lea     rax, [rdi+4]
0x1801e49ec  xor     r9d, r9d; UnitArray
0x1801e49ef  mov     [rsp+0E8h+SessionHandle], rax; SessionHandle
0x1801e49f4  lea     r14, ?WbsAsyncCallback@CNuiAudioWbsAsyncWrapper@@CAXPEAU_WINBIO_ASYNC_RESULT@@@Z; CNuiAudioWbsAsyncWrapper::WbsAsyncCallback(_WINBIO_ASYNC_RESULT *)
0x1801e49fb  mov     [rsp+0E8h+AsynchronousOpen], 0; AsynchronousOpen
0x1801e4a03  xor     r8d, r8d; Flags
0x1801e4a06  mov     [rsp+0E8h+UserData], rdi; UserData
0x1801e4a0b  mov     edx, ebp; PoolType
0x1801e4a0d  mov     [rsp+0E8h+CallbackRoutine], r14; CallbackRoutine
0x1801e4a12  lea     ecx, [r9+4]; Factor
0x1801e4a16  mov     [rsp+0E8h+MessageCode], 0; MessageCode
0x1801e4a1e  mov     [rsp+0E8h+TargetWindow], 0; TargetWindow
0x1801e4a27  mov     [rsp+0E8h+NotificationMethod], ebp; NotificationMethod
0x1801e4a2b  mov     [rsp+0E8h+DatabaseId], rbp; DatabaseId
0x1801e4a30  mov     [rsp+0E8h+UnitCount], 0; UnitCount
0x1801e4a39  call    cs:__imp_WinBioAsyncOpenSession
0x1801e4a3f  mov     ebx, eax
0x1801e4a41  test    eax, eax
0x1801e4a43  js      short loc_1801E4AC1
0x1801e4a45  mov     qword ptr [rsp+0E8h+NotificationMethod], rdi; FrameworkHandle
0x1801e4a4a  mov     r9, r14; CallbackRoutine
0x1801e4a4d  mov     dword ptr [rsp+0E8h+DatabaseId], 0; AsynchronousOpen
0x1801e4a55  xor     r8d, r8d; MessageCode
0x1801e4a58  xor     edx, edx; TargetWindow
0x1801e4a5a  mov     [rsp+0E8h+UnitCount], rdi; UserData
0x1801e4a5f  mov     ecx, ebp; NotificationMethod
0x1801e4a61  call    cs:__imp_WinBioAsyncOpenFramework
0x1801e4a67  mov     ebx, eax
0x1801e4a69  test    eax, eax
0x1801e4a6b  js      short loc_1801E4AC1
0x1801e4a6d  mov     rcx, [rdi+4A0h]; hEvent
0x1801e4a74  lea     rax, [rcx-1]
0x1801e4a78  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e4a7c  ja      short loc_1801E4A84
0x1801e4a7e  call    cs:__imp_ResetEvent
0x1801e4a84  mov     ecx, [rdi]; FrameworkHandle
0x1801e4a86  mov     edx, 4; Factor
0x1801e4a8b  mov     dword ptr [rdi+4A8h], 0
0x1801e4a95  call    cs:__imp_WinBioAsyncEnumBiometricUnits
0x1801e4a9b  mov     ebx, eax
0x1801e4a9d  test    eax, eax
0x1801e4a9f  js      short loc_1801E4AC1
0x1801e4aa1  mov     rcx, [rdi+4A0h]; hHandle
0x1801e4aa8  lea     rax, [rcx-1]
0x1801e4aac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801e4ab0  ja      short loc_1801E4ABB
0x1801e4ab2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801e4ab5  call    cs:__imp_WaitForSingleObject
0x1801e4abb  mov     ebx, [rdi+4A8h]
0x1801e4ac1  mov     rcx, rdi; this
0x1801e4ac4  call    ?RaiseInitCompletionEvent@CNuiAudioWbsAsyncWrapper@@AEAAXXZ; CNuiAudioWbsAsyncWrapper::RaiseInitCompletionEvent(void)
0x1801e4ac9  mov     eax, ebx
0x1801e4acb  add     rsp, 0C8h
0x1801e4ad2  pop     r14
0x1801e4ad4  pop     rdi
0x1801e4ad5  pop     rbp
0x1801e4ad6  pop     rbx
0x1801e4ad7  retn
```
