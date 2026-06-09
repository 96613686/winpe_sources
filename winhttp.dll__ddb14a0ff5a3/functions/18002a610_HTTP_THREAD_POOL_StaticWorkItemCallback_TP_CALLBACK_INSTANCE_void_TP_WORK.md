# HTTP_THREAD_POOL::_StaticWorkItemCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002a610`
- end: `0x18002a8fb`
- name: `?_StaticWorkItemCallback@HTTP_THREAD_POOL@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `747`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, union _SLIST_HEADER *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002a610`
- `0x18002a910`
- `0x180098320`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800de010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a7b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a7b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a8c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a8c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a8bc`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002a650`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18002a650`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002a63a`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002a63a`
- `ntdll!EtwEventActivityIdControl` at `0x18002a6d6`
- `ntdll!EtwEventActivityIdControl` at `0x18002a70e`
- `ntdll!EtwEventActivityIdControl` at `0x18002a83c`
- `ntdll!EtwEventActivityIdControl` at `0x18002a6d6`
- `ntdll!EtwEventActivityIdControl` at `0x18002a70e`
- `ntdll!EtwEventActivityIdControl` at `0x18002a83c`

## pseudocode

```c
void __fastcall HTTP_THREAD_POOL::_StaticWorkItemCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        union _SLIST_HEADER *a2,
        struct _TP_WORK *a3)
{
  PSLIST_ENTRY v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  PSLIST_ENTRY v7; // r14
  struct _SLIST_ENTRY *v8; // rbx
  __int128 *v9; // rax
  __int128 *v10; // rax
  __int64 v11; // rcx
  __int128 *v12; // rax
  int v13; // eax
  bool v14; // sf
  int v15; // eax
  int v16; // r8d
  bool v17; // sf
  int v18; // ebx
  int v19; // r8d
  int v20; // eax
  bool v21; // sf
  __int128 v22; // [rsp+38h] [rbp-59h] BYREF
  __int128 v23; // [rsp+48h] [rbp-49h] BYREF
  __int128 v24; // [rsp+58h] [rbp-39h] BYREF
  int v25; // [rsp+68h] [rbp-29h]
  __int128 v26; // [rsp+78h] [rbp-19h] BYREF
  _BYTE v27[16]; // [rsp+88h] [rbp-9h] BYREF
  __int128 *v28; // [rsp+98h] [rbp+7h]
  __int64 v29; // [rsp+A0h] [rbp+Fh]
  __int128 *v30; // [rsp+A8h] [rbp+17h]
  __int64 v31; // [rsp+B0h] [rbp+1Fh]
  _UNKNOWN *retaddr; // [rsp+F0h] [rbp+5Fh]

  CallbackMayRunLong(a1);
  v24 = 0;
  v25 = 0;
  v4 = InterlockedPopEntrySList(a2 + 6);
  v5 = 16;
  v6 = 16;
  v7 = v4 - 3;
  v8 = v4 - 1;
  v9 = &v24;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (__int128 *)((char *)v9 + 1);
    --v6;
  }
  while ( v6 );
  v10 = &v24;
  v25 = 0;
  v11 = 16;
  v22 = 0;
  v26 = 0;
  do
  {
    *(_BYTE *)v10 = 0;
    v10 = (__int128 *)((char *)v10 + 1);
    --v11;
  }
  while ( v11 );
  v23 = 0;
  v12 = &v26;
  do
  {
    *(_BYTE *)v12 = 0;
    v12 = (__int128 *)((char *)v12 + 1);
    --v5;
  }
  while ( v5 );
  v13 = EtwEventActivityIdControl(1, &v23);
  v14 = v13 < 0;
  if ( v13 > 0 )
    v14 = 1;
  if ( v14 )
    DWORD1(v23) = 128;
  else
    v26 = v23;
  if ( !v8 )
  {
    *(_QWORD *)&v22 = __PAIR64__(
                        _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount),
                        (unsigned int)retaddr);
    DWORD2(v22) = GetTickCount();
    v8 = (struct _SLIST_ENTRY *)&v22;
    HIDWORD(v22) = GetCurrentProcessId();
  }
  DWORD1(v23) = 0;
  v15 = EtwEventActivityIdControl(2, v8);
  v17 = v15 < 0;
  if ( v15 > 0 )
    v17 = 1;
  if ( v17 )
    DWORD1(v23) = 144;
  v24 = v26;
  v25 = 1;
  if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
  {
    LODWORD(v23) = 2;
    v28 = &v22;
    *(_QWORD *)&v22 = v7;
    v30 = &v23;
    v29 = 8;
    v31 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)WINHTTP_ETW_PROVIDER_ID_Context,
      (unsigned int)StartThreadAction,
      v16,
      3,
      (__int64)v27);
  }
  v18 = Impersonate(v7[1].Next);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)&v7->Next + 1) + 32LL))(
    *((_QWORD *)&v7->Next + 1),
    *((_QWORD *)&v7[1].Next + 1));
  if ( v18 )
  {
    RevertToSelf();
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_(1025, 34, WPP_4488b656277339d76b4660bf9f172bbc_Traceguids);
  }
  if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
  {
    LODWORD(v23) = 2;
    v28 = &v22;
    *(_QWORD *)&v22 = v7;
    v30 = &v23;
    v29 = 8;
    v31 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)WINHTTP_ETW_PROVIDER_ID_Context,
      (unsigned int)StopThreadAction,
      v19,
      3,
      (__int64)v27);
  }
  if ( v25 )
  {
    DWORD1(v22) = 0;
    v20 = EtwEventActivityIdControl(2, &v24);
    v21 = v20 < 0;
    if ( v20 > 0 )
      v21 = 1;
    if ( v21 )
      DWORD1(v22) = 144;
  }
}

```

## disassembly

```asm
0x18002a610  mov     r11, rsp
0x18002a613  push    rbp
0x18002a614  push    r15
0x18002a616  lea     rbp, [r11-5Fh]
0x18002a61a  sub     rsp, 0D8h
0x18002a621  mov     rax, cs:__security_cookie
0x18002a628  xor     rax, rsp
0x18002a62b  mov     [rbp+57h+var_30], rax
0x18002a62f  mov     [r11+18h], rbx
0x18002a633  mov     rbx, rdx
0x18002a636  mov     [r11-28h], r14
0x18002a63a  call    cs:__imp_CallbackMayRunLong
0x18002a640  xorps   xmm0, xmm0
0x18002a643  lea     rcx, [rbx+60h]; ListHead
0x18002a647  xor     eax, eax
0x18002a649  movups  [rbp+57h+var_90], xmm0
0x18002a64d  mov     [rbp+57h+var_80], eax
0x18002a650  call    cs:__imp_InterlockedPopEntrySList
0x18002a656  mov     edx, 10h
0x18002a65b  mov     ecx, edx
0x18002a65d  lea     r14, [rax-30h]
0x18002a661  lea     rbx, [r14+20h]
0x18002a665  lea     rax, [rbp+57h+var_90]
0x18002a669  nop     dword ptr [rax+00000000h]
0x18002a670  mov     byte ptr [rax], 0
0x18002a673  lea     rax, [rax+1]
0x18002a677  sub     rcx, 1
0x18002a67b  jnz     short loc_18002A670
0x18002a67d  xor     r15d, r15d
0x18002a680  lea     rax, [rbp+57h+var_90]
0x18002a684  xorps   xmm0, xmm0
0x18002a687  mov     [rbp+57h+var_80], r15d
0x18002a68b  xorps   xmm1, xmm1
0x18002a68e  mov     rcx, rdx
0x18002a691  movups  [rbp+57h+var_B0], xmm0
0x18002a695  movups  [rbp+57h+var_70], xmm1
0x18002a699  nop     dword ptr [rax+00000000h]
0x18002a6a0  mov     [rax], r15b
0x18002a6a3  lea     rax, [rax+1]
0x18002a6a7  sub     rcx, 1
0x18002a6ab  jnz     short loc_18002A6A0
0x18002a6ad  xorps   xmm0, xmm0
0x18002a6b0  mov     dword ptr [rbp+57h+var_A0+4], r15d
0x18002a6b4  movups  xmmword ptr [rbp-49h], xmm0
0x18002a6b8  lea     rax, [rbp+57h+var_70]
0x18002a6bc  nop     dword ptr [rax+00h]
0x18002a6c0  mov     [rax], r15b
0x18002a6c3  lea     rax, [rax+1]
0x18002a6c7  sub     rdx, 1
0x18002a6cb  jnz     short loc_18002A6C0
0x18002a6cd  lea     rdx, [rbp+57h+var_A0]
0x18002a6d1  mov     ecx, 1
0x18002a6d6  call    cs:__imp_EtwEventActivityIdControl
0x18002a6dc  test    eax, eax
0x18002a6de  jle     short loc_18002A6EA
0x18002a6e0  movzx   eax, ax
0x18002a6e3  or      eax, 80070000h
0x18002a6e8  test    eax, eax
0x18002a6ea  js      loc_18002A88D
0x18002a6f0  movaps  xmm0, [rbp+57h+var_A0]
0x18002a6f4  movdqa  [rbp+57h+var_70], xmm0
0x18002a6f9  test    rbx, rbx
0x18002a6fc  jz      loc_18002A899
0x18002a702  mov     rdx, rbx
0x18002a705  mov     dword ptr [rbp+57h+var_A0+4], r15d
0x18002a709  mov     ecx, 2
0x18002a70e  call    cs:__imp_EtwEventActivityIdControl
0x18002a714  test    eax, eax
0x18002a716  jle     short loc_18002A722
0x18002a718  movzx   eax, ax
0x18002a71b  or      eax, 80070000h
0x18002a720  test    eax, eax
0x18002a722  js      loc_18002A8EF
0x18002a728  test    cs:Microsoft_Windows_WinHttpEnableBits, 8
0x18002a72f  movaps  xmm0, [rbp+57h+var_70]
0x18002a733  movups  [rbp+57h+var_90], xmm0
0x18002a737  mov     [rbp+57h+var_80], 1
0x18002a73e  jz      short loc_18002A78D
0x18002a740  lea     rax, [rbp+57h+var_B0]
0x18002a744  mov     dword ptr [rbp+57h+var_A0], 2
0x18002a74b  mov     [rbp+57h+var_50], rax
0x18002a74f  lea     rdx, StartThreadAction
0x18002a756  lea     rax, [rbp+57h+var_A0]
0x18002a75a  mov     qword ptr [rbp+57h+var_B0], r14
0x18002a75e  mov     [rbp+57h+var_40], rax
0x18002a762  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x18002a769  lea     rax, [rbp+57h+var_60]
0x18002a76d  mov     [rbp+57h+var_48], 8
0x18002a775  mov     r9d, 3
0x18002a77b  mov     [rsp+20h], rax
0x18002a780  mov     [rbp+57h+var_38], 4
0x18002a788  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a78d  mov     rcx, [r14+10h]; Token
0x18002a791  call    ?Impersonate@@YAHPEAX@Z; Impersonate(void *)
0x18002a796  mov     rcx, [r14+8]
0x18002a79a  mov     ebx, eax
0x18002a79c  mov     rdx, [rcx]
0x18002a79f  mov     rax, [rdx+20h]
0x18002a7a3  mov     rdx, [r14+18h]
0x18002a7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ac  test    ebx, ebx
0x18002a7ae  mov     rbx, [rsp+0E0h+arg_10]
0x18002a7b6  jz      short loc_18002A7CB
0x18002a7b8  call    cs:__imp_RevertToSelf
0x18002a7be  test    byte ptr cs:xmmword_180107A60, 2
0x18002a7c5  jnz     loc_18002A869
0x18002a7cb  test    cs:Microsoft_Windows_WinHttpEnableBits, 8
0x18002a7d2  jz      short loc_18002A821
0x18002a7d4  lea     rax, [rbp+57h+var_B0]
0x18002a7d8  mov     dword ptr [rbp+57h+var_A0], 2
0x18002a7df  mov     [rbp+57h+var_50], rax
0x18002a7e3  lea     rdx, StopThreadAction
0x18002a7ea  lea     rax, [rbp+57h+var_A0]
0x18002a7ee  mov     qword ptr [rbp+57h+var_B0], r14
0x18002a7f2  mov     [rbp+57h+var_40], rax
0x18002a7f6  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x18002a7fd  lea     rax, [rbp+57h+var_60]
0x18002a801  mov     [rbp+57h+var_48], 8
0x18002a809  mov     r9d, 3
0x18002a80f  mov     [rsp+20h], rax
0x18002a814  mov     [rbp+57h+var_38], 4
0x18002a81c  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a821  mov     r14, [rsp+0E0h+var_20]
0x18002a829  cmp     [rbp+57h+var_80], r15d
0x18002a82d  jz      short loc_18002A852
0x18002a82f  lea     rdx, [rbp+57h+var_90]
0x18002a833  mov     dword ptr [rbp+57h+var_B0+4], r15d
0x18002a837  mov     ecx, 2
0x18002a83c  call    cs:__imp_EtwEventActivityIdControl
0x18002a842  test    eax, eax
0x18002a844  jle     short loc_18002A850
0x18002a846  movzx   eax, ax
0x18002a849  or      eax, 80070000h
0x18002a84e  test    eax, eax
0x18002a850  js      short loc_18002A884
0x18002a852  mov     rcx, [rbp+57h+var_30]
0x18002a856  xor     rcx, rsp; StackCookie
0x18002a859  call    __security_check_cookie
0x18002a85e  add     rsp, 0D8h
0x18002a865  pop     r15
0x18002a867  pop     rbp
0x18002a868  retn
0x18002a869  mov     edx, 22h ; '"'
0x18002a86e  lea     r8, WPP_4488b656277339d76b4660bf9f172bbc_Traceguids
0x18002a875  mov     ecx, 401h
0x18002a87a  call    WPP_SF_
0x18002a87f  jmp     loc_18002A7CB
0x18002a884  mov     dword ptr [rbp+57h+var_B0+4], 90h
0x18002a88b  jmp     short loc_18002A852
0x18002a88d  mov     dword ptr [rbp+57h+var_A0+4], 80h
0x18002a894  jmp     loc_18002A6F9
0x18002a899  mov     [rsp+0D0h], rsi
0x18002a8a1  mov     esi, 1
0x18002a8a6  mov     [rsp+0E0h+var_18], rdi
0x18002a8ae  mov     rdi, [rbp+5Fh]
0x18002a8b2  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18002a8ba  inc     esi
0x18002a8bc  call    cs:__imp_GetTickCount
0x18002a8c2  mov     ebx, eax
0x18002a8c4  call    cs:__imp_GetCurrentProcessId
0x18002a8ca  mov     dword ptr [rbp+57h+var_B0], edi
0x18002a8cd  mov     rdi, [rsp+0E0h+var_18]
0x18002a8d5  mov     dword ptr [rbp+57h+var_B0+4], esi
0x18002a8d8  mov     rsi, [rsp+0D0h]
0x18002a8e0  mov     dword ptr [rbp+57h+var_B0+8], ebx
0x18002a8e3  lea     rbx, [rbp+57h+var_B0]
0x18002a8e7  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x18002a8ea  jmp     loc_18002A702
0x18002a8ef  mov     dword ptr [rbp+57h+var_A0+4], 90h
0x18002a8f6  jmp     loc_18002A728
```
