# CInputHostLayout::_QueueNotification(IHM_NOTIFICATION_DATA const *)

- ea: `0x180083c1c`
- end: `0x180083edb`
- name: `?_QueueNotification@CInputHostLayout@@AEAAJPEBUIHM_NOTIFICATION_DATA@@@Z`
- size: `703`
- prototype: `__int64 __fastcall(CInputHostLayout *__hidden this, const struct IHM_NOTIFICATION_DATA *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180083ae0`
- `0x180254d40`

## callees

- `0x18000b7e8`
- `0x180031970`
- `0x180042a60`
- `0x180083c1c`
- `0x180083ee4`
- `0x180083fbc`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083c51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083d4f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083c51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180083d4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083cf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083d84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083cf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083d84`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180083da5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180083da5`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083df7`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083e05`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083e13`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083df7`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083e05`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180083e13`

## pseudocode

```c
__int64 __fastcall CInputHostLayout::_QueueNotification(CInputHostLayout *this, const RECT *a2)
{
  RTL_SRWLOCK *v2; // r13
  __int64 v5; // rbx
  _QWORD *v6; // rdi
  unsigned __int64 v7; // r14
  int v8; // ebx
  __int64 v9; // rdx
  struct IPerWindowNotificationQueue **v10; // rdx
  struct IPerWindowNotificationQueue *v11; // rcx
  struct IPerWindowNotificationQueue *v12; // rcx
  __int64 v14; // rdx
  volatile int *v15; // rdx
  struct IPerWindowNotificationQueue *v16; // r14
  unsigned __int64 v17; // r12
  unsigned __int64 i; // r14
  RECT *v19; // rdx
  struct IPerWindowNotificationQueue *v20; // [rsp+20h] [rbp-50h] BYREF
  LONG bottom; // [rsp+28h] [rbp-48h] BYREF
  struct tagRECT rcDst; // [rsp+2Ch] [rbp-44h] BYREF
  struct tagRECT v23; // [rsp+3Ch] [rbp-34h] BYREF
  struct tagRECT v24; // [rsp+4Ch] [rbp-24h] BYREF
  LONG right; // [rsp+5Ch] [rbp-14h]

  v2 = (RTL_SRWLOCK *)((char *)this + 256);
  AcquireSRWLockExclusive((PSRWLOCK)this + 32);
  v5 = *(_QWORD *)&a2->left;
  v6 = (_QWORD *)((char *)this + 264);
  v7 = 0;
  v20 = 0;
  while ( v7 < *((_QWORD *)this + 34) )
  {
    if ( v5 == (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*v6 + 8 * v7) + 24LL))(*(_QWORD *)(*v6 + 8 * v7)) )
    {
      v8 = 0;
      v16 = *(struct IPerWindowNotificationQueue **)(*v6 + 8 * v7);
      if ( v20 != v16 )
      {
        if ( v16 )
          (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v16 + 8LL))(v16);
        v20 = v16;
      }
LABEL_23:
      bottom = a2->bottom;
      right = a2->right;
      CopyRect(&rcDst, a2 + 1);
      CopyRect(&v23, a2 + 2);
      CopyRect(&v24, a2 + 3);
      if ( a2->bottom == 1 )
      {
        v8 = (*(__int64 (__fastcall **)(struct IPerWindowNotificationQueue *, LONG *))(*(_QWORD *)v20 + 40LL))(
               v20,
               &bottom);
      }
      else
      {
        v17 = *((_QWORD *)this + 34);
        for ( i = 0; i < v17; ++i )
          (*(void (__fastcall **)(_QWORD, LONG *))(**(_QWORD **)(*v6 + 8 * i) + 40LL))(
            *(_QWORD *)(*v6 + 8 * i),
            &bottom);
      }
      goto LABEL_11;
    }
    ++v7;
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v20);
  v8 = CPerWindowNotificationQueue_CreateInstance(*(HWND *)&a2->left, &v20);
  if ( v8 >= 0 )
  {
    v9 = *((_QWORD *)this + 34);
    v8 = 0;
    if ( v9 != *((_QWORD *)this + 36)
      || (v8 = CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(
                 (char *)this + 264,
                 v9 + 1),
          v8 >= 0) )
    {
      v10 = (struct IPerWindowNotificationQueue **)(*((_QWORD *)this + 33) + 8 * (*((_QWORD *)this + 34))++);
      if ( v10 )
      {
        v11 = v20;
        *v10 = v20;
        if ( v11 )
          (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    if ( v8 >= 0 )
      goto LABEL_23;
  }
LABEL_11:
  ReleaseSRWLockExclusive(v2);
  if ( v8 >= 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 37);
    v8 = 0;
    v14 = *((_QWORD *)this + 39);
    if ( v14 != *((_QWORD *)this + 41)
      || (v8 = CTSimpleArray<IHM_NOTIFICATION_DATA,4294967294,CTPolicyCoTaskMem<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardCompareHelper<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardMergeHelper<IHM_NOTIFICATION_DATA>>::_EnsureCapacity(
                 (char *)this + 304,
                 v14 + 1),
          v8 >= 0) )
    {
      v19 = (RECT *)((++*((_QWORD *)this + 39) << 6) + *((_QWORD *)this + 38) - 64LL);
      if ( v19 )
      {
        *v19 = *a2;
        v19[1] = a2[1];
        v19[2] = a2[2];
        v19[3] = a2[3];
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 37);
    if ( v8 >= 0 )
    {
      Microsoft::WRL::Details::SafeUnknownIncrementReference((CInputHostLayout *)((char *)this + 156), v15);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 42));
    }
  }
  v12 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(struct IPerWindowNotificationQueue *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180083c1c  mov     [rsp-38h+arg_10], rbx
0x180083c21  push    rbp
0x180083c22  push    rsi
0x180083c23  push    rdi
0x180083c24  push    r12
0x180083c26  push    r13
0x180083c28  push    r14
0x180083c2a  push    r15
0x180083c2c  mov     rbp, rsp
0x180083c2f  sub     rsp, 70h
0x180083c33  mov     rax, cs:__security_cookie
0x180083c3a  xor     rax, rsp
0x180083c3d  mov     [rbp+var_10], rax
0x180083c41  lea     r13, [rcx+100h]
0x180083c48  mov     r15, rcx
0x180083c4b  mov     rcx, r13; SRWLock
0x180083c4e  mov     rsi, rdx
0x180083c51  call    cs:__imp_AcquireSRWLockExclusive
0x180083c57  mov     rbx, [rsi]
0x180083c5a  lea     rdi, [r15+108h]
0x180083c61  xor     r14d, r14d
0x180083c64  mov     [rbp+var_50], 0
0x180083c6c  cmp     r14, [rdi+8]
0x180083c70  jnb     short loc_180083C93
0x180083c72  mov     rax, [rdi]
0x180083c75  mov     rcx, [rax+r14*8]
0x180083c79  mov     rax, [rcx]
0x180083c7c  mov     rax, [rax+18h]
0x180083c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c85  cmp     rbx, rax
0x180083c88  jz      loc_180083DB0
0x180083c8e  inc     r14
0x180083c91  jmp     short loc_180083C6C
0x180083c93  lea     rcx, [rbp+var_50]
0x180083c97  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180083c9c  mov     rcx, [rsi]; HWND
0x180083c9f  lea     rdx, [rbp+var_50]; struct IPerWindowNotificationQueue **
0x180083ca3  call    ?CPerWindowNotificationQueue_CreateInstance@@YAJPEAUHWND__@@PEAPEAUIPerWindowNotificationQueue@@@Z; CPerWindowNotificationQueue_CreateInstance(HWND__ *,IPerWindowNotificationQueue * *)
0x180083ca8  mov     ebx, eax
0x180083caa  test    eax, eax
0x180083cac  js      short loc_180083CF5
0x180083cae  mov     rdx, [rdi+8]
0x180083cb2  xor     ebx, ebx
0x180083cb4  cmp     rdx, [rdi+18h]
0x180083cb8  jz      loc_180083E82
0x180083cbe  inc     qword ptr [rdi+8]
0x180083cc2  mov     rdx, [rdi+8]
0x180083cc6  mov     rax, [rdi]
0x180083cc9  dec     rdx
0x180083ccc  lea     rdx, [rax+rdx*8]
0x180083cd0  test    rdx, rdx
0x180083cd3  jz      short loc_180083CED
0x180083cd5  mov     rcx, [rbp+var_50]
0x180083cd9  mov     [rdx], rcx
0x180083cdc  test    rcx, rcx
0x180083cdf  jz      short loc_180083CED
0x180083ce1  mov     rax, [rcx]
0x180083ce4  mov     rax, [rax+8]
0x180083ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ced  test    ebx, ebx
0x180083cef  jns     loc_180083DE3
0x180083cf5  mov     rcx, r13; SRWLock
0x180083cf8  call    cs:__imp_ReleaseSRWLockExclusive
0x180083cfe  test    ebx, ebx
0x180083d00  jns     short loc_180083D45
0x180083d02  mov     rcx, [rbp+var_50]
0x180083d06  test    rcx, rcx
0x180083d09  jz      short loc_180083D1F
0x180083d0b  mov     [rbp+var_50], 0
0x180083d13  mov     rax, [rcx]
0x180083d16  mov     rax, [rax+10h]
0x180083d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d1f  mov     eax, ebx
0x180083d21  mov     rcx, [rbp+var_10]
0x180083d25  xor     rcx, rsp; StackCookie
0x180083d28  call    __security_check_cookie
0x180083d2d  mov     rbx, [rsp+70h+arg_10]
0x180083d35  add     rsp, 70h
0x180083d39  pop     r15
0x180083d3b  pop     r14
0x180083d3d  pop     r13
0x180083d3f  pop     r12
0x180083d41  pop     rdi
0x180083d42  pop     rsi
0x180083d43  pop     rbp
0x180083d44  retn
0x180083d45  lea     r14, [r15+128h]
0x180083d4c  mov     rcx, r14; SRWLock
0x180083d4f  call    cs:__imp_AcquireSRWLockExclusive
0x180083d55  lea     rdi, [r15+130h]
0x180083d5c  xor     ebx, ebx
0x180083d5e  mov     rdx, [rdi+8]
0x180083d62  cmp     rdx, [rdi+18h]
0x180083d66  jnz     loc_180083E9C
0x180083d6c  inc     rdx
0x180083d6f  mov     rcx, rdi
0x180083d72  call    ?_EnsureCapacity@?$CTSimpleArray@UIHM_NOTIFICATION_DATA@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UIHM_NOTIFICATION_DATA@@@@V?$CSimpleArrayStandardCompareHelper@UIHM_NOTIFICATION_DATA@@@@V?$CSimpleArrayStandardMergeHelper@UIHM_NOTIFICATION_DATA@@@@@@QEAAJ_K0@Z; CTSimpleArray<IHM_NOTIFICATION_DATA,4294967294,CTPolicyCoTaskMem<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardCompareHelper<IHM_NOTIFICATION_DATA>,CSimpleArrayStandardMergeHelper<IHM_NOTIFICATION_DATA>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180083d77  mov     ebx, eax
0x180083d79  test    eax, eax
0x180083d7b  jns     loc_180083E9C
0x180083d81  mov     rcx, r14; SRWLock
0x180083d84  call    cs:__imp_ReleaseSRWLockExclusive
0x180083d8a  test    ebx, ebx
0x180083d8c  js      loc_180083D02
0x180083d92  lea     rcx, [r15+9Ch]; this
0x180083d99  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180083d9e  mov     rcx, [r15+150h]; pwk
0x180083da5  call    cs:__imp_SubmitThreadpoolWork
0x180083dab  jmp     loc_180083D02
0x180083db0  mov     rax, [rdi]
0x180083db3  xor     ebx, ebx
0x180083db5  mov     rcx, [rbp+var_50]
0x180083db9  mov     r14, [rax+r14*8]
0x180083dbd  cmp     rcx, r14
0x180083dc0  jz      short loc_180083DE3
0x180083dc2  test    r14, r14
0x180083dc5  jz      short loc_180083DDA
0x180083dc7  mov     rax, [r14]
0x180083dca  mov     rcx, r14
0x180083dcd  mov     rax, [rax+8]
0x180083dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083dd6  mov     rcx, [rbp+var_50]
0x180083dda  mov     [rbp+var_50], r14
0x180083dde  test    rcx, rcx
0x180083de1  jnz     short loc_180083E56
0x180083de3  mov     eax, [rsi+0Ch]
0x180083de6  lea     rdx, [rsi+10h]; lprcSrc
0x180083dea  mov     [rbp+var_48], eax
0x180083ded  lea     rcx, [rbp+rcDst]; lprcDst
0x180083df1  mov     eax, [rsi+8]
0x180083df4  mov     [rbp+var_14], eax
0x180083df7  call    cs:__imp_CopyRect
0x180083dfd  lea     rdx, [rsi+20h]; lprcSrc
0x180083e01  lea     rcx, [rbp+var_34]; lprcDst
0x180083e05  call    cs:__imp_CopyRect
0x180083e0b  lea     rdx, [rsi+30h]; lprcSrc
0x180083e0f  lea     rcx, [rbp+var_24]; lprcDst
0x180083e13  call    cs:__imp_CopyRect
0x180083e19  cmp     dword ptr [rsi+0Ch], 1
0x180083e1d  jz      short loc_180083E67
0x180083e1f  mov     r12, [r15+110h]
0x180083e26  xor     r14d, r14d
0x180083e29  test    r12, r12
0x180083e2c  jz      loc_180083CF5
0x180083e32  mov     rax, [rdi]
0x180083e35  lea     rdx, [rbp+var_48]
0x180083e39  mov     rcx, [rax+r14*8]
0x180083e3d  mov     rax, [rcx]
0x180083e40  mov     rax, [rax+28h]
0x180083e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e49  inc     r14
0x180083e4c  cmp     r14, r12
0x180083e4f  jb      short loc_180083E32
0x180083e51  jmp     loc_180083CF5
0x180083e56  mov     rax, [rcx]
0x180083e59  mov     rax, [rax+10h]
0x180083e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e62  jmp     loc_180083DE3
0x180083e67  mov     rcx, [rbp+var_50]
0x180083e6b  lea     rdx, [rbp+var_48]
0x180083e6f  mov     rax, [rcx]
0x180083e72  mov     rax, [rax+28h]
0x180083e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e7b  mov     ebx, eax
0x180083e7d  jmp     loc_180083CF5
0x180083e82  inc     rdx
0x180083e85  mov     rcx, rdi
0x180083e88  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIGestureClient@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIGestureClient@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIGestureClient@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIGestureClient@@@@@@QEAAJ_K0@Z; CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180083e8d  mov     ebx, eax
0x180083e8f  test    eax, eax
0x180083e91  js      loc_180083CED
0x180083e97  jmp     loc_180083CBE
0x180083e9c  inc     qword ptr [rdi+8]
0x180083ea0  mov     rcx, [rdi+8]
0x180083ea4  mov     rdx, [rdi]
0x180083ea7  shl     rcx, 6
0x180083eab  add     rdx, 0FFFFFFFFFFFFFFC0h
0x180083eaf  add     rdx, rcx
0x180083eb2  jz      loc_180083D81
0x180083eb8  movups  xmm0, xmmword ptr [rsi]
0x180083ebb  movups  xmmword ptr [rdx], xmm0
0x180083ebe  movups  xmm1, xmmword ptr [rsi+10h]
0x180083ec2  movups  xmmword ptr [rdx+10h], xmm1
0x180083ec6  movups  xmm0, xmmword ptr [rsi+20h]
0x180083eca  movups  xmmword ptr [rdx+20h], xmm0
0x180083ece  movups  xmm1, xmmword ptr [rsi+30h]
0x180083ed2  movups  xmmword ptr [rdx+30h], xmm1
0x180083ed6  jmp     loc_180083D81
```
