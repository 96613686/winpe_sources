# VmsOmPortGetStats

- ea: `0x14004c744`
- end: `0x14004cab2`
- name: `VmsOmPortGetStats`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400cef18`

## callees

- `0x14004c744`
- `0x14004cab8`
- `0x14004cc08`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14004ca6d`
- `ntoskrnl!KeReleaseMutex` at `0x14004ca6d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004c7bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004c7bf`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c7e6`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c92f`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c7e6`
- `NDIS!NdisAcquireRWLockRead` at `0x14004c92f`
- `NDIS!NdisReleaseRWLock` at `0x14004c918`
- `NDIS!NdisReleaseRWLock` at `0x14004c962`
- `NDIS!NdisReleaseRWLock` at `0x14004caa4`
- `NDIS!NdisReleaseRWLock` at `0x14004c918`
- `NDIS!NdisReleaseRWLock` at `0x14004c962`
- `NDIS!NdisReleaseRWLock` at `0x14004caa4`

## pseudocode

```c
LONG __fastcall VmsOmPortGetStats(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v2; // rbp
  __int64 v5; // rsi
  __int64 v6; // rdx
  _OWORD *v7; // rax
  _OWORD *v8; // rcx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  struct _LOCK_STATE_EX LockState; // [rsp+70h] [rbp+0h] BYREF

  v2 = (unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL;
  *(_WORD *)v2 = 0;
  *(_BYTE *)(v2 + 2) = 0;
  *(_WORD *)(v2 + 4) = 0;
  *(_BYTE *)(v2 + 6) = 0;
  memset((void *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 704), 0, 0x280u);
  *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
  *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 0;
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  memset(a2, 0, 0xC0u);
  NdisAcquireRWLockRead(
    *(PNDIS_RW_LOCK_EX *)(a1 + 56),
    (PLOCK_STATE_EX)((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL),
    0);
  *a2 = *(_QWORD *)(a1 + 1344);
  a2[1] = *(_QWORD *)(a1 + 1352);
  a2[2] = *(_QWORD *)(a1 + 1360);
  a2[3] = *(_QWORD *)(a1 + 1368);
  a2[4] = *(_QWORD *)(a1 + 1376);
  a2[5] = *(_QWORD *)(a1 + 1384);
  a2[6] = *(_QWORD *)(a1 + 1392);
  a2[7] = *(_QWORD *)(a1 + 1400);
  a2[8] = *(_QWORD *)(a1 + 1408);
  a2[9] = *(_QWORD *)(a1 + 1416);
  a2[10] = *(unsigned int *)(a1 + 6368);
  a2[11] = *(_QWORD *)(a1 + 1432);
  a2[12] = *(_QWORD *)(a1 + 1440);
  a2[13] = *(_QWORD *)(a1 + 1448);
  a2[14] = *(_QWORD *)(a1 + 1456);
  v5 = *(_QWORD *)(a1 + 1256);
  if ( v5 && *(_DWORD *)(v5 + 1880) == 1 )
  {
    v6 = 5;
    v7 = (_OWORD *)(a1 + 1536);
    v8 = (_OWORD *)(v2 + 64);
    do
    {
      v9 = v7[1];
      *v8 = *v7;
      v10 = v7[2];
      v8[1] = v9;
      v11 = v7[3];
      v8[2] = v10;
      v12 = v7[4];
      v8[3] = v11;
      v13 = v7[5];
      v8[4] = v12;
      v14 = v7[6];
      v8[5] = v13;
      v15 = v7[7];
      v7 += 8;
      v8[6] = v14;
      v8[7] = v15;
      v8 += 8;
      --v6;
    }
    while ( v6 );
    NdisReleaseRWLock(
      *(PNDIS_RW_LOCK_EX *)(a1 + 56),
      (PLOCK_STATE_EX)((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL));
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v5 + 56), (PLOCK_STATE_EX)(v2 + 4), 0);
    VmsOmNicGetStatsUnsafe(v5, v2 + 704);
    VmsOmNicGetUnhashedPacketsStatsUnsafe(v5, v2 + 8, v2 + 16);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 56), (PLOCK_STATE_EX)(v2 + 4));
    *a2 += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C8)
         - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x48);
    a2[1] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2C0)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x40);
    a2[2] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2D8)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
    a2[3] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2D0)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x50);
    a2[4] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2E8)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x68);
    a2[5] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2E0)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x60);
    a2[6] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2F8)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x78);
    a2[7] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x2F0)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x70);
    a2[9] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x300)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x80);
    a2[8] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x308)
           - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x88);
    a2[11] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x458)
            - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x1D8);
    a2[12] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x450)
            - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x1D0);
    a2[13] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x468)
            - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x1E8);
    a2[14] += *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x460)
            - *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x1E0);
    a2[15] = *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 8);
    a2[16] = *(_QWORD *)(((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
  }
  else
  {
    NdisReleaseRWLock(
      *(PNDIS_RW_LOCK_EX *)(a1 + 56),
      (PLOCK_STATE_EX)((unsigned __int64)&LockState & 0xFFFFFFFFFFFFFFC0uLL));
  }
  return KeReleaseMutex(&VmsOmIoctlMutex, 0);
}

```

## disassembly

```asm
0x14004c744  mov     [rsp-8+arg_10], rbx
0x14004c749  push    rbp
0x14004c74a  push    rsi
0x14004c74b  push    rdi
0x14004c74c  sub     rsp, 5C0h
0x14004c753  lea     rbp, [rsp+70h]
0x14004c758  and     rbp, 0FFFFFFFFFFFFFFC0h
0x14004c75c  mov     rax, cs:__security_cookie
0x14004c763  xor     rax, rsp
0x14004c766  mov     [rbp+560h+var_20], rax
0x14004c76d  xor     eax, eax
0x14004c76f  mov     rbx, rdx
0x14004c772  mov     rdi, rcx
0x14004c775  mov     word ptr [rbp+560h+LockState.OldIrql], ax
0x14004c779  xor     edx, edx; Val
0x14004c77b  mov     [rbp+560h+LockState.Flags], al
0x14004c77e  lea     rcx, [rbp+560h+var_2A0]; void *
0x14004c785  mov     word ptr [rbp+560h+var_55C.OldIrql], ax
0x14004c789  mov     r8d, 280h; Size
0x14004c78f  mov     [rbp+560h+var_55C.Flags], al
0x14004c792  call    memset
0x14004c797  xor     r9d, r9d; Alertable
0x14004c79a  mov     [rbp+560h+var_558], 0
0x14004c7a2  xor     r8d, r8d; WaitMode
0x14004c7a5  mov     [rbp+560h+var_550], 0
0x14004c7ad  xor     edx, edx; WaitReason
0x14004c7af  mov     [rsp+5D0h+Timeout], 0; Timeout
0x14004c7b8  lea     rcx, VmsOmIoctlMutex; Object
0x14004c7bf  call    cs:__imp_KeWaitForSingleObject
0x14004c7c6  nop     dword ptr [rax+rax+00h]
0x14004c7cb  xor     edx, edx; Val
0x14004c7cd  mov     r8d, 0C0h; Size
0x14004c7d3  mov     rcx, rbx; void *
0x14004c7d6  call    memset
0x14004c7db  mov     rcx, [rdi+38h]; Lock
0x14004c7df  lea     rdx, [rbp+560h+LockState]; LockState
0x14004c7e3  xor     r8d, r8d; Flags
0x14004c7e6  call    cs:__imp_NdisAcquireRWLockRead
0x14004c7ed  nop     dword ptr [rax+rax+00h]
0x14004c7f2  mov     rax, [rdi+540h]
0x14004c7f9  mov     [rbx], rax
0x14004c7fc  mov     rax, [rdi+548h]
0x14004c803  mov     [rbx+8], rax
0x14004c807  mov     rax, [rdi+550h]
0x14004c80e  mov     [rbx+10h], rax
0x14004c812  mov     rax, [rdi+558h]
0x14004c819  mov     [rbx+18h], rax
0x14004c81d  mov     rax, [rdi+560h]
0x14004c824  mov     [rbx+20h], rax
0x14004c828  mov     rax, [rdi+568h]
0x14004c82f  mov     [rbx+28h], rax
0x14004c833  mov     rax, [rdi+570h]
0x14004c83a  mov     [rbx+30h], rax
0x14004c83e  mov     rax, [rdi+578h]
0x14004c845  mov     [rbx+38h], rax
0x14004c849  mov     rax, [rdi+580h]
0x14004c850  mov     [rbx+40h], rax
0x14004c854  mov     rax, [rdi+588h]
0x14004c85b  mov     [rbx+48h], rax
0x14004c85f  mov     eax, [rdi+18E0h]
0x14004c865  mov     [rbx+50h], rax
0x14004c869  mov     rax, [rdi+598h]
0x14004c870  mov     [rbx+58h], rax
0x14004c874  mov     rax, [rdi+5A0h]
0x14004c87b  mov     [rbx+60h], rax
0x14004c87f  mov     rax, [rdi+5A8h]
0x14004c886  mov     [rbx+68h], rax
0x14004c88a  mov     rax, [rdi+5B0h]
0x14004c891  mov     [rbx+70h], rax
0x14004c895  mov     rsi, [rdi+4E8h]
0x14004c89c  test    rsi, rsi
0x14004c89f  jz      loc_14004CA9C
0x14004c8a5  cmp     dword ptr [rsi+758h], 1
0x14004c8ac  jnz     loc_14004CA9C
0x14004c8b2  mov     edx, 5
0x14004c8b7  lea     rax, [rdi+600h]
0x14004c8be  lea     rcx, [rbp+560h+var_520]
0x14004c8c2  lea     r8d, [rdx+7Bh]
0x14004c8c6  movups  xmm0, xmmword ptr [rax]
0x14004c8c9  movups  xmm1, xmmword ptr [rax+10h]
0x14004c8cd  movups  xmmword ptr [rcx], xmm0
0x14004c8d0  movups  xmm0, xmmword ptr [rax+20h]
0x14004c8d4  movups  xmmword ptr [rcx+10h], xmm1
0x14004c8d8  movups  xmm1, xmmword ptr [rax+30h]
0x14004c8dc  movups  xmmword ptr [rcx+20h], xmm0
0x14004c8e0  movups  xmm0, xmmword ptr [rax+40h]
0x14004c8e4  movups  xmmword ptr [rcx+30h], xmm1
0x14004c8e8  movups  xmm1, xmmword ptr [rax+50h]
0x14004c8ec  movups  xmmword ptr [rcx+40h], xmm0
0x14004c8f0  movups  xmm0, xmmword ptr [rax+60h]
0x14004c8f4  movups  xmmword ptr [rcx+50h], xmm1
0x14004c8f8  movups  xmm1, xmmword ptr [rax+70h]
0x14004c8fc  add     rax, r8
0x14004c8ff  movups  xmmword ptr [rcx+60h], xmm0
0x14004c903  movups  xmmword ptr [rcx+70h], xmm1
0x14004c907  add     rcx, r8
0x14004c90a  sub     rdx, 1
0x14004c90e  jnz     short loc_14004C8C6
0x14004c910  mov     rcx, [rdi+38h]; Lock
0x14004c914  lea     rdx, [rbp+560h+LockState]; LockState
0x14004c918  call    cs:__imp_NdisReleaseRWLock
0x14004c91f  nop     dword ptr [rax+rax+00h]
0x14004c924  mov     rcx, [rsi+38h]; Lock
0x14004c928  lea     rdx, [rbp+560h+var_55C]; LockState
0x14004c92c  xor     r8d, r8d; Flags
0x14004c92f  call    cs:__imp_NdisAcquireRWLockRead
0x14004c936  nop     dword ptr [rax+rax+00h]
0x14004c93b  lea     rdx, [rbp+560h+var_2A0]
0x14004c942  mov     rcx, rsi
0x14004c945  call    VmsOmNicGetStatsUnsafe
0x14004c94a  lea     r8, [rbp+560h+var_550]
0x14004c94e  mov     rcx, rsi
0x14004c951  lea     rdx, [rbp+560h+var_558]
0x14004c955  call    VmsOmNicGetUnhashedPacketsStatsUnsafe
0x14004c95a  mov     rcx, [rsi+38h]; Lock
0x14004c95e  lea     rdx, [rbp+560h+var_55C]; LockState
0x14004c962  call    cs:__imp_NdisReleaseRWLock
0x14004c969  nop     dword ptr [rax+rax+00h]
0x14004c96e  mov     rax, [rbp+560h+var_298]
0x14004c975  sub     rax, [rbp+560h+var_518]
0x14004c979  add     [rbx], rax
0x14004c97c  mov     rax, [rbp+560h+var_2A0]
0x14004c983  sub     rax, [rbp+560h+var_520]
0x14004c987  add     [rbx+8], rax
0x14004c98b  mov     rax, [rbp+560h+var_288]
0x14004c992  sub     rax, [rbp+560h+var_508]
0x14004c996  add     [rbx+10h], rax
0x14004c99a  mov     rax, [rbp+560h+var_290]
0x14004c9a1  sub     rax, [rbp+560h+var_510]
0x14004c9a5  add     [rbx+18h], rax
0x14004c9a9  mov     rax, [rbp+560h+var_278]
0x14004c9b0  sub     rax, [rbp+560h+var_4F8]
0x14004c9b4  add     [rbx+20h], rax
0x14004c9b8  mov     rax, [rbp+560h+var_280]
0x14004c9bf  sub     rax, [rbp+560h+var_500]
0x14004c9c3  add     [rbx+28h], rax
0x14004c9c7  mov     rax, [rbp+560h+var_268]
0x14004c9ce  sub     rax, [rbp+560h+var_4E8]
0x14004c9d2  add     [rbx+30h], rax
0x14004c9d6  mov     rax, [rbp+560h+var_270]
0x14004c9dd  sub     rax, [rbp+560h+var_4F0]
0x14004c9e1  add     [rbx+38h], rax
0x14004c9e5  mov     rax, [rbp+560h+var_260]
0x14004c9ec  sub     rax, [rbp+560h+var_4E0]
0x14004c9f3  add     [rbx+48h], rax
0x14004c9f7  mov     rax, [rbp+560h+var_258]
0x14004c9fe  sub     rax, [rbp+560h+var_4D8]
0x14004ca05  add     [rbx+40h], rax
0x14004ca09  mov     rax, [rbp+560h+var_108]
0x14004ca10  sub     rax, [rbp+560h+var_388]
0x14004ca17  add     [rbx+58h], rax
0x14004ca1b  mov     rax, [rbp+560h+var_110]
0x14004ca22  sub     rax, [rbp+560h+var_390]
0x14004ca29  add     [rbx+60h], rax
0x14004ca2d  mov     rax, [rbp+560h+var_F8]
0x14004ca34  sub     rax, [rbp+560h+var_378]
0x14004ca3b  add     [rbx+68h], rax
0x14004ca3f  mov     rax, [rbp+560h+var_100]
0x14004ca46  sub     rax, [rbp+560h+var_380]
0x14004ca4d  add     [rbx+70h], rax
0x14004ca51  mov     rax, [rbp+560h+var_558]
0x14004ca55  mov     [rbx+78h], rax
0x14004ca59  mov     rax, [rbp+560h+var_550]
0x14004ca5d  mov     [rbx+80h], rax
0x14004ca64  xor     edx, edx; Wait
0x14004ca66  lea     rcx, VmsOmIoctlMutex; Mutex
0x14004ca6d  call    cs:__imp_KeReleaseMutex
0x14004ca74  nop     dword ptr [rax+rax+00h]
0x14004ca79  mov     rcx, [rbp+560h+var_20]
0x14004ca80  xor     rcx, rsp; StackCookie
0x14004ca83  call    __security_check_cookie
0x14004ca88  mov     rbx, [rsp+5D0h+arg_10]
0x14004ca90  add     rsp, 5C0h
0x14004ca97  pop     rdi
0x14004ca98  pop     rsi
0x14004ca99  pop     rbp
0x14004ca9a  retn
0x14004ca9c  mov     rcx, [rdi+38h]; Lock
0x14004caa0  lea     rdx, [rbp+560h+LockState]; LockState
0x14004caa4  call    cs:__imp_NdisReleaseRWLock
0x14004caab  nop     dword ptr [rax+rax+00h]
0x14004cab0  jmp     short loc_14004CA64
```
