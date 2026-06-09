# HTTP_THREAD_POOL::_WaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18002a360`
- end: `0x18002a608`
- name: `?_WaitCallback@HTTP_THREAD_POOL@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `680`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, HANDLE *, struct _TP_WAIT *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002a360`
- `0x18002a910`
- `0x180098320`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800de010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a5b9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002a5b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a44a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a44a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a442`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002a442`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002a39c`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18002a39c`
- `ntdll!EtwEventActivityIdControl` at `0x18002a408`
- `ntdll!EtwEventActivityIdControl` at `0x18002a46c`
- `ntdll!EtwEventActivityIdControl` at `0x18002a57c`
- `ntdll!EtwEventActivityIdControl` at `0x18002a408`
- `ntdll!EtwEventActivityIdControl` at `0x18002a46c`
- `ntdll!EtwEventActivityIdControl` at `0x18002a57c`

## pseudocode

```c
void __fastcall HTTP_THREAD_POOL::_WaitCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        HANDLE *a2,
        struct _TP_WAIT *a3,
        int a4)
{
  __int64 v6; // rcx
  char *v7; // rbx
  __int64 v8; // rdx
  __int128 *v9; // rax
  __int128 *v10; // rax
  __int64 v11; // rdx
  __int128 *v12; // rax
  int v13; // eax
  bool v14; // sf
  signed __int32 v15; // esi
  signed int v16; // eax
  int v17; // r8d
  int v18; // eax
  void (__fastcall ***v19)(_QWORD, HANDLE); // rcx
  int v20; // ebx
  HANDLE v21; // rdx
  void (__fastcall **v22)(_QWORD, HANDLE); // rax
  int v23; // r8d
  int v24; // eax
  bool v25; // sf
  __int128 v26; // [rsp+30h] [rbp-69h] BYREF
  __int128 v27; // [rsp+40h] [rbp-59h] BYREF
  __int128 v28; // [rsp+50h] [rbp-49h] BYREF
  int v29; // [rsp+60h] [rbp-39h]
  __int128 v30; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v31[16]; // [rsp+80h] [rbp-19h] BYREF
  __int128 *v32; // [rsp+90h] [rbp-9h]
  __int64 v33; // [rsp+98h] [rbp-1h]
  __int128 *v34; // [rsp+A0h] [rbp+7h]
  __int64 v35; // [rsp+A8h] [rbp+Fh]
  _UNKNOWN *retaddr; // [rsp+F8h] [rbp+5Fh]

  v28 = 0;
  v29 = 0;
  CallbackMayRunLong(a1);
  v6 = 16;
  v7 = (char *)(a2 + 4);
  v8 = 16;
  v9 = &v28;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (__int128 *)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  v29 = 0;
  v10 = &v28;
  v26 = 0;
  v11 = 16;
  v30 = 0;
  do
  {
    *(_BYTE *)v10 = 0;
    v10 = (__int128 *)((char *)v10 + 1);
    --v11;
  }
  while ( v11 );
  v27 = 0;
  v12 = &v30;
  do
  {
    *(_BYTE *)v12 = 0;
    v12 = (__int128 *)((char *)v12 + 1);
    --v6;
  }
  while ( v6 );
  v13 = EtwEventActivityIdControl(1, &v27);
  v14 = v13 < 0;
  if ( v13 > 0 )
    v14 = 1;
  if ( v14 )
    DWORD1(v27) = 128;
  else
    v30 = v27;
  if ( a2 == (HANDLE *)-32LL )
  {
    v15 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    DWORD2(v26) = GetTickCount();
    v7 = (char *)&v26;
    HIDWORD(v26) = GetCurrentProcessId();
    *(_QWORD *)&v26 = __PAIR64__(v15, (unsigned int)retaddr);
  }
  DWORD1(v27) = 0;
  v16 = EtwEventActivityIdControl(2, v7);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 < 0 )
    DWORD1(v27) = 144;
  v29 = 1;
  v28 = v30;
  if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
  {
    LODWORD(v27) = 4;
    v32 = &v26;
    *(_QWORD *)&v26 = a2;
    v34 = &v27;
    v33 = 8;
    v35 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)WINHTTP_ETW_PROVIDER_ID_Context,
      (unsigned int)StartThreadAction,
      v17,
      3,
      (__int64)v31);
  }
  v18 = Impersonate(a2[2]);
  v19 = (void (__fastcall ***)(_QWORD, HANDLE))a2[1];
  v20 = v18;
  v21 = a2[3];
  v22 = *v19;
  if ( a4 == 258 )
    (*v22)(v19, v21);
  else
    v22[1](v19, v21);
  if ( v20 )
  {
    RevertToSelf();
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_(1025, 31, WPP_4488b656277339d76b4660bf9f172bbc_Traceguids);
  }
  if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
  {
    LODWORD(v27) = 4;
    v32 = &v26;
    *(_QWORD *)&v26 = a2;
    v34 = &v27;
    v33 = 8;
    v35 = 4;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)WINHTTP_ETW_PROVIDER_ID_Context,
      (unsigned int)StopThreadAction,
      v23,
      3,
      (__int64)v31);
  }
  if ( v29 )
  {
    DWORD1(v26) = 0;
    v24 = EtwEventActivityIdControl(2, &v28);
    v25 = v24 < 0;
    if ( v24 > 0 )
      v25 = 1;
    if ( v25 )
      DWORD1(v26) = 144;
  }
}

```

## disassembly

```asm
0x18002a360  mov     [rsp-8+arg_10], rbx
0x18002a365  push    rbp
0x18002a366  push    rsi
0x18002a367  push    rdi
0x18002a368  push    r12
0x18002a36a  push    r13
0x18002a36c  push    r14
0x18002a36e  push    r15
0x18002a370  lea     rbp, [rsp-27h]
0x18002a375  sub     rsp, 0C0h
0x18002a37c  mov     rax, cs:__security_cookie
0x18002a383  xor     rax, rsp
0x18002a386  mov     [rbp+57h+var_40], rax
0x18002a38a  xorps   xmm0, xmm0
0x18002a38d  xor     eax, eax
0x18002a38f  movups  [rbp+57h+var_A0], xmm0
0x18002a393  mov     [rbp+57h+var_90], eax
0x18002a396  mov     r15d, r9d
0x18002a399  mov     r14, rdx
0x18002a39c  call    cs:__imp_CallbackMayRunLong
0x18002a3a2  mov     ecx, 10h
0x18002a3a7  lea     rbx, [r14+20h]
0x18002a3ab  mov     edx, ecx
0x18002a3ad  lea     rax, [rbp+57h+var_A0]
0x18002a3b1  xor     r12d, r12d
0x18002a3b4  lea     r13d, [rcx-0Fh]
0x18002a3b8  mov     [rax], r12b
0x18002a3bb  add     rax, r13
0x18002a3be  sub     rdx, r13
0x18002a3c1  jnz     short loc_18002A3B8
0x18002a3c3  xorps   xmm0, xmm0
0x18002a3c6  mov     [rbp+57h+var_90], r12d
0x18002a3ca  xorps   xmm1, xmm1
0x18002a3cd  lea     rax, [rbp+57h+var_A0]
0x18002a3d1  movups  [rbp+57h+var_C0], xmm0
0x18002a3d5  mov     rdx, rcx
0x18002a3d8  movups  [rbp+57h+var_80], xmm1
0x18002a3dc  mov     [rax], r12b
0x18002a3df  add     rax, r13
0x18002a3e2  sub     rdx, r13
0x18002a3e5  jnz     short loc_18002A3DC
0x18002a3e7  xorps   xmm0, xmm0
0x18002a3ea  mov     dword ptr [rbp+57h+var_B0+4], r12d
0x18002a3ee  movups  xmmword ptr [rbp-59h], xmm0
0x18002a3f2  lea     rax, [rbp+57h+var_80]
0x18002a3f6  mov     [rax], r12b
0x18002a3f9  add     rax, r13
0x18002a3fc  sub     rcx, r13
0x18002a3ff  jnz     short loc_18002A3F6
0x18002a401  lea     rdx, [rbp+57h+var_B0]
0x18002a405  mov     ecx, r13d
0x18002a408  call    cs:__imp_EtwEventActivityIdControl
0x18002a40e  test    eax, eax
0x18002a410  jle     short loc_18002A41C
0x18002a412  movzx   eax, ax
0x18002a415  or      eax, 80070000h
0x18002a41a  test    eax, eax
0x18002a41c  js      loc_18002A5EC
0x18002a422  movaps  xmm0, [rbp+57h+var_B0]
0x18002a426  movdqa  [rbp+57h+var_80], xmm0
0x18002a42b  test    rbx, rbx
0x18002a42e  jnz     short loc_18002A460
0x18002a430  mov     rdi, [rbp+5Fh]
0x18002a434  mov     esi, r13d
0x18002a437  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18002a43f  add     esi, r13d
0x18002a442  call    cs:__imp_GetTickCount
0x18002a448  mov     ebx, eax
0x18002a44a  call    cs:__imp_GetCurrentProcessId
0x18002a450  mov     dword ptr [rbp+57h+var_C0+8], ebx
0x18002a453  lea     rbx, [rbp+57h+var_C0]
0x18002a457  mov     dword ptr [rbp+57h+var_C0+0Ch], eax
0x18002a45a  mov     dword ptr [rbp+57h+var_C0], edi
0x18002a45d  mov     dword ptr [rbp+57h+var_C0+4], esi
0x18002a460  mov     rdx, rbx
0x18002a463  mov     dword ptr [rbp+57h+var_B0+4], r12d
0x18002a467  mov     ecx, 2
0x18002a46c  call    cs:__imp_EtwEventActivityIdControl
0x18002a472  test    eax, eax
0x18002a474  jle     short loc_18002A47E
0x18002a476  movzx   eax, ax
0x18002a479  or      eax, 80070000h
0x18002a47e  mov     esi, 90h
0x18002a483  test    eax, eax
0x18002a485  js      loc_18002A5F8
0x18002a48b  movaps  xmm0, [rbp+57h+var_80]
0x18002a48f  mov     edi, 8
0x18002a494  test    cs:Microsoft_Windows_WinHttpEnableBits, dil
0x18002a49b  mov     [rbp+57h+var_90], r13d
0x18002a49f  movdqu  [rbp+57h+var_A0], xmm0
0x18002a4a4  lea     r13d, [rdi-4]
0x18002a4a8  jz      short loc_18002A4EA
0x18002a4aa  lea     rax, [rbp+57h+var_C0]
0x18002a4ae  mov     dword ptr [rbp+57h+var_B0], r13d
0x18002a4b2  mov     [rbp+57h+var_60], rax
0x18002a4b6  lea     r9d, [rdi-5]
0x18002a4ba  lea     rax, [rbp+57h+var_B0]
0x18002a4be  mov     qword ptr [rbp+57h+var_C0], r14
0x18002a4c2  mov     [rbp+57h+var_50], rax
0x18002a4c6  lea     rdx, StartThreadAction
0x18002a4cd  lea     rax, [rbp+57h+var_70]
0x18002a4d1  mov     [rbp+57h+var_58], rdi
0x18002a4d5  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x18002a4dc  mov     [rsp+0F0h+var_D0], rax
0x18002a4e1  mov     [rbp+57h+var_48], r13
0x18002a4e5  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a4ea  mov     rcx, [r14+10h]; Token
0x18002a4ee  call    ?Impersonate@@YAHPEAX@Z; Impersonate(void *)
0x18002a4f3  mov     rcx, [r14+8]
0x18002a4f7  mov     ebx, eax
0x18002a4f9  mov     rdx, [r14+18h]
0x18002a4fd  mov     rax, [rcx]
0x18002a500  cmp     r15d, 102h
0x18002a507  jz      loc_18002A600
0x18002a50d  mov     rax, [rax+8]
0x18002a511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a516  test    ebx, ebx
0x18002a518  jnz     loc_18002A5B9
0x18002a51e  test    cs:Microsoft_Windows_WinHttpEnableBits, dil
0x18002a525  jz      short loc_18002A569
0x18002a527  lea     rax, [rbp+57h+var_C0]
0x18002a52b  mov     dword ptr [rbp+57h+var_B0], r13d
0x18002a52f  mov     [rbp+57h+var_60], rax
0x18002a533  lea     rdx, StopThreadAction
0x18002a53a  lea     rax, [rbp+57h+var_B0]
0x18002a53e  mov     qword ptr [rbp+57h+var_C0], r14
0x18002a542  mov     [rbp+57h+var_50], rax
0x18002a546  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x18002a54d  lea     rax, [rbp+57h+var_70]
0x18002a551  mov     [rbp+57h+var_58], rdi
0x18002a555  mov     r9d, 3
0x18002a55b  mov     [rsp+0F0h+var_D0], rax
0x18002a560  mov     [rbp+57h+var_48], r13
0x18002a564  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a569  cmp     [rbp+57h+var_90], r12d
0x18002a56d  jz      short loc_18002A592
0x18002a56f  lea     rdx, [rbp+57h+var_A0]
0x18002a573  mov     dword ptr [rbp+57h+var_C0+4], r12d
0x18002a577  mov     ecx, 2
0x18002a57c  call    cs:__imp_EtwEventActivityIdControl
0x18002a582  test    eax, eax
0x18002a584  jle     short loc_18002A590
0x18002a586  movzx   eax, ax
0x18002a589  or      eax, 80070000h
0x18002a58e  test    eax, eax
0x18002a590  js      short loc_18002A5E7
0x18002a592  mov     rcx, [rbp+57h+var_40]
0x18002a596  xor     rcx, rsp; StackCookie
0x18002a599  call    __security_check_cookie
0x18002a59e  mov     rbx, [rsp+0F0h+arg_10]
0x18002a5a6  add     rsp, 0C0h
0x18002a5ad  pop     r15
0x18002a5af  pop     r14
0x18002a5b1  pop     r13
0x18002a5b3  pop     r12
0x18002a5b5  pop     rdi
0x18002a5b6  pop     rsi
0x18002a5b7  pop     rbp
0x18002a5b8  retn
0x18002a5b9  call    cs:__imp_RevertToSelf
0x18002a5bf  test    byte ptr cs:xmmword_180107A60, 2
0x18002a5c6  jz      loc_18002A51E
0x18002a5cc  mov     edx, 1Fh
0x18002a5d1  lea     r8, WPP_4488b656277339d76b4660bf9f172bbc_Traceguids
0x18002a5d8  mov     ecx, 401h
0x18002a5dd  call    WPP_SF_
0x18002a5e2  jmp     loc_18002A51E
0x18002a5e7  mov     dword ptr [rbp+57h+var_C0+4], esi
0x18002a5ea  jmp     short loc_18002A592
0x18002a5ec  mov     dword ptr [rbp+57h+var_B0+4], 80h
0x18002a5f3  jmp     loc_18002A42B
0x18002a5f8  mov     dword ptr [rbp+57h+var_B0+4], esi
0x18002a5fb  jmp     loc_18002A48B
0x18002a600  mov     rax, [rax]
0x18002a603  jmp     loc_18002A511
```
