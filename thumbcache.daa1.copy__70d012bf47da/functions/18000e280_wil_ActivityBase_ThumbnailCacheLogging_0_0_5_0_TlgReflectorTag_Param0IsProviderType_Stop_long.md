# wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000e280`
- end: `0x18000e4a7`
- name: `?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `551`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000bffc`
- `0x18000d498`
- `0x18000d8c0`
- `0x18000da60`
- `0x18000e6a0`
- `0x18000f31c`
- `0x18000f650`
- `0x18000fcd0`
- `0x18000ffcc`
- `0x18001195c`
- `0x1800152b0`
- `0x180015868`
- `0x180019980`
- `0x18001b1a0`
- `0x1800249d0`
- `0x180028518`
- `0x1800287c4`
- `0x18002ff10`
- `0x18003cfc0`
- `0x18003d6b0`
- `0x18003e890`
- `0x180041270`
- `0x180041360`
- `0x1800429b4`
- `0x1800443fc`

## callees

- `0x18000e280`
- `0x18001f1c0`
- `0x180027890`
- `0x18002ec08`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e35f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e32d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e32d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e2c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e2c2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e437`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e437`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  int v2; // r14d
  RTL_SRWLOCK *v4; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  int v7; // esi
  int v8; // esi
  __int64 v9; // rbx
  const GUID *v10; // r8
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+70h] [rbp-90h]
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+B0h] [rbp-50h]
  __int128 v21; // [rsp+C0h] [rbp-40h]
  __int128 v22; // [rsp+D0h] [rbp-30h]
  __int128 v23; // [rsp+E0h] [rbp-20h]
  __int64 v24; // [rsp+F0h] [rbp-10h]

  v2 = (int)a2;
  v4 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v4 )
  {
    v5 = v4 + 33;
    AcquireSRWLockExclusive(v5);
  }
  else
  {
    v12 = 0;
    v5 = 0;
  }
  v6 = *(_QWORD *)(a1 + 272);
  v7 = *(_DWORD *)(v6 + 248);
  if ( v7 < 1 )
  {
    UserData = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v6 + 72) >= 0 )
    *(_DWORD *)(v6 + 72) = v2;
  v8 = v7 - 1;
  *(_DWORD *)(v6 + 248) = v8;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  if ( v8 )
  {
    v9 = *((_QWORD *)ThumbnailCacheLogging::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(v12) = v2;
      v13 = 0x1000000;
      v10 = (const GUID *)(*(_QWORD *)(a1 + 272) + 8LL);
      *(_QWORD *)&v19 = &CurrentThreadId;
      *((_QWORD *)&v19 + 1) = 4;
      *(_QWORD *)&v18 = &v12;
      *((_QWORD *)&v18 + 1) = 4;
      *(_QWORD *)&v17 = &v13;
      *((_QWORD *)&v17 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *(_QWORD *)(v9 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v16 = &dword_18005403C;
      *((_QWORD *)&v16 + 1) = 0x10000004DLL;
      EventWriteTransfer(*(_QWORD *)(v9 + 32), &EventDescriptor, v10, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x18000e280  push    rbp
0x18000e282  push    rbx
0x18000e283  push    rsi
0x18000e284  push    rdi
0x18000e285  push    r14
0x18000e287  push    r15
0x18000e289  lea     rbp, [rsp-18h]
0x18000e28e  sub     rsp, 118h
0x18000e295  mov     rax, cs:__security_cookie
0x18000e29c  xor     rax, rsp
0x18000e29f  mov     [rbp+40h+var_40], rax
0x18000e2a3  mov     r14d, edx
0x18000e2a6  mov     rdi, rcx
0x18000e2a9  xor     r15d, r15d
0x18000e2ac  mov     rbx, [rcx+118h]
0x18000e2b3  test    rbx, rbx
0x18000e2b6  jz      short loc_18000E2E2
0x18000e2b8  add     rbx, 108h
0x18000e2bf  mov     rcx, rbx; SRWLock
0x18000e2c2  call    cs:__imp_AcquireSRWLockExclusive
0x18000e2c8  lea     rax, [rsp+140h+SRWLock]
0x18000e2cd  mov     [rax], r15
0x18000e2d0  mov     rcx, [rsp+140h+SRWLock]; SRWLock
0x18000e2d5  test    rcx, rcx
0x18000e2d8  jz      short loc_18000E2FD
0x18000e2da  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2e0  jmp     short loc_18000E2FD
0x18000e2e2  lea     rax, [rsp+140h+var_100]
0x18000e2e7  mov     [rax], r15
0x18000e2ea  mov     rcx, [rsp+140h+var_100]; SRWLock
0x18000e2ef  test    rcx, rcx
0x18000e2f2  jz      short loc_18000E2FA
0x18000e2f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2fa  mov     rbx, r15
0x18000e2fd  mov     rax, [rdi+110h]
0x18000e304  mov     esi, [rax+0F8h]
0x18000e30a  cmp     esi, 1
0x18000e30d  jl      loc_18000E46D
0x18000e313  cmp     dword ptr [rax+48h], 0
0x18000e317  jl      short loc_18000E31D
0x18000e319  mov     [rax+48h], r14d
0x18000e31d  dec     esi
0x18000e31f  mov     [rax+0F8h], esi
0x18000e325  test    rbx, rbx
0x18000e328  jz      short loc_18000E333
0x18000e32a  mov     rcx, rbx; SRWLock
0x18000e32d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e333  test    esi, esi
0x18000e335  jnz     short loc_18000E34B
0x18000e337  mov     rax, [rdi]
0x18000e33a  mov     rcx, rdi
0x18000e33d  mov     rax, [rax+8]
0x18000e341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e346  jmp     loc_18000E43E
0x18000e34b  call    ?Instance@ThumbnailCacheLogging@@KAPEAV1@XZ; ThumbnailCacheLogging::Instance(void)
0x18000e350  mov     rbx, [rax+8]
0x18000e354  mov     eax, [rbx]
0x18000e356  cmp     eax, 5
0x18000e359  jbe     loc_18000E43E
0x18000e35f  call    cs:__imp_GetCurrentThreadId
0x18000e365  mov     [rsp+140h+var_108], eax
0x18000e369  mov     dword ptr [rsp+140h+var_100], r14d
0x18000e36e  mov     [rsp+140h+var_F8], 1000000h
0x18000e377  mov     r8, [rdi+110h]
0x18000e37e  add     r8, 8; ActivityId
0x18000e382  lea     rax, [rsp+140h+var_108]
0x18000e387  mov     qword ptr [rbp+40h+var_A0], rax
0x18000e38b  mov     qword ptr [rbp+40h+var_A0+8], 4
0x18000e393  lea     rax, [rsp+140h+var_100]
0x18000e398  mov     qword ptr [rbp+40h+var_B0], rax
0x18000e39c  mov     qword ptr [rbp+40h+var_B0+8], 4
0x18000e3a4  lea     rax, [rsp+140h+var_F8]
0x18000e3a9  mov     qword ptr [rbp+40h+var_C0], rax
0x18000e3ad  mov     qword ptr [rbp+40h+var_C0+8], 8
0x18000e3b5  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x18000e3bd  movzx   eax, cs:word_180054032
0x18000e3c4  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x18000e3c8  mov     [rsp+140h+EventDescriptor.Keyword], r15
0x18000e3cd  mov     rax, [rbx+8]
0x18000e3d1  mov     [rsp+140h+var_E0.Ptr], rax
0x18000e3d6  movzx   eax, word ptr [rax]
0x18000e3d9  mov     [rsp+140h+var_E0.Size], eax
0x18000e3dd  mov     dword ptr [rsp+140h+var_E0.0Ch], 2
0x18000e3e5  lea     rax, dword_18005403C
0x18000e3ec  mov     qword ptr [rsp+140h+var_D0], rax
0x18000e3f1  mov     dword ptr [rsp+140h+var_D0+8], 4Dh ; 'M'
0x18000e3f9  mov     dword ptr [rsp+140h+var_D0+0Ch], 1
0x18000e401  lea     rax, _TraceLoggingMetadataEnd
0x18000e408  lea     rcx, _TraceLoggingMetadata
0x18000e40f  sub     eax, ecx
0x18000e411  mov     dword ptr [rsp+140h+SRWLock], eax
0x18000e415  mov     eax, dword ptr [rsp+140h+SRWLock]
0x18000e419  lea     rax, [rsp+140h+var_E0]
0x18000e41e  mov     [rsp+140h+UserData], rax; UserData
0x18000e423  mov     [rsp+140h+UserDataCount], 5; UserDataCount
0x18000e42b  xor     r9d, r9d; RelatedActivityId
0x18000e42e  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x18000e433  mov     rcx, [rbx+20h]; RegHandle
0x18000e437  call    cs:__imp_EventWriteTransfer
0x18000e43d  nop
0x18000e43e  lea     rcx, [rdi+120h]; this
0x18000e445  cmp     dword ptr [rcx+18h], 0
0x18000e449  jz      short loc_18000E451
0x18000e44b  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18000e450  nop
0x18000e451  mov     rcx, [rbp+40h+var_40]
0x18000e455  xor     rcx, rsp; StackCookie
0x18000e458  call    __security_check_cookie
0x18000e45d  add     rsp, 118h
0x18000e464  pop     r15
0x18000e466  pop     r14
0x18000e468  pop     rdi
0x18000e469  pop     rsi
0x18000e46a  pop     rbx
0x18000e46b  pop     rbp
0x18000e46c  retn
0x18000e46d  xorps   xmm0, xmm0
0x18000e470  xor     eax, eax
0x18000e472  movups  xmmword ptr [rsp+140h+var_E0.Ptr], xmm0
0x18000e477  movups  [rsp+140h+var_D0], xmm0
0x18000e47c  movups  [rbp+40h+var_C0], xmm0
0x18000e480  movups  [rbp+40h+var_B0], xmm0
0x18000e484  movups  [rbp+40h+var_A0], xmm0
0x18000e488  movups  [rbp+40h+var_90], xmm0
0x18000e48c  movups  [rbp+40h+var_80], xmm0
0x18000e490  movups  [rbp+40h+var_70], xmm0
0x18000e494  movups  [rbp+40h+var_60], xmm0
0x18000e498  mov     [rbp+40h+var_50], rax
0x18000e49c  lea     rcx, [rsp+140h+var_E0]; this
0x18000e4a1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
