# WaImpersonateSessionToken

- ea: `0x18003a4a0`
- end: `0x18003a6ca`
- name: `WaImpersonateSessionToken`
- size: `554`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b780`
- `0x18003a020`
- `0x180058314`
- `0x18005e068`
- `0x18005e5a8`
- `0x180060ea8`
- `0x180063d28`
- `0x18007688c`
- `0x1800826dc`
- `0x180082824`
- `0x1800829c0`

## callees

- `0x1800180e0`
- `0x18002e460`
- `0x18003a4a0`
- `0x1800722f0`
- `0x180092500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003a556`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003a556`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a52f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a52f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a686`

## pseudocode

```c
__int64 __fastcall WaImpersonateSessionToken(__int64 a1, __int64 *a2)
{
  __int64 result; // rax
  void *v5; // r14
  HANDLE CurrentThread; // rax
  __int64 v7; // rbp
  DWORD v8; // esi
  __int64 v9; // r8
  DWORD v10; // ebx
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD v13; // [rsp+38h] [rbp-80h] BYREF
  void *v14; // [rsp+40h] [rbp-78h] BYREF
  __int64 v15; // [rsp+48h] [rbp-70h] BYREF
  char v16[16]; // [rsp+50h] [rbp-68h] BYREF
  void **v17; // [rsp+60h] [rbp-58h]
  __int64 v18; // [rsp+68h] [rbp-50h]
  __int64 *v19; // [rsp+70h] [rbp-48h]
  __int64 v20; // [rsp+78h] [rbp-40h]
  DWORD *v21; // [rsp+80h] [rbp-38h]
  __int64 v22; // [rsp+88h] [rbp-30h]

  result = 0;
  *a2 = -1;
  if ( !*(_BYTE *)(a1 + 33) )
  {
    v5 = *(void **)(a1 + 112);
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    {
      v7 = (__int64)TokenHandle;
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      v8 = 0;
      if ( LastError != 1008 )
        v8 = LastError;
      v7 = -(__int64)(LastError != 1008);
      TokenHandle = (void *)v7;
      if ( v8 )
        goto LABEL_7;
    }
    if ( !v5 && !v7 )
    {
      v7 = -1;
      goto LABEL_11;
    }
    v8 = 0;
    if ( !SetThreadToken(0, v5) )
      v8 = WaGetLastError();
LABEL_7:
    if ( v7 != -1 && (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v13 = v8;
      v17 = &v14;
      v15 = v7;
      v19 = &v15;
      v14 = v5;
      v21 = &v13;
      v18 = 8;
      v20 = 8;
      v22 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenSet, v9, 4, v16);
    }
    if ( v8 )
    {
      if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v7);
      *a2 = -1;
      v10 = v8;
      if ( (xmmword_1800AD710 & 2) != 0 )
        WPP_SF_qD(513, 17, WPP_247e30510a1b3c47cfbd7b690ee005cd_Traceguids, a1, v8);
      return v10;
    }
LABEL_11:
    *a2 = v7;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18003a4a0  push    rbx
0x18003a4a2  push    rdi
0x18003a4a3  sub     rsp, 0A8h
0x18003a4aa  mov     rax, cs:__security_cookie
0x18003a4b1  xor     rax, rsp
0x18003a4b4  mov     [rsp+0B8h+var_28], rax
0x18003a4bc  xor     eax, eax
0x18003a4be  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18003a4c5  mov     rbx, rdx
0x18003a4c8  mov     rdi, rcx
0x18003a4cb  cmp     [rcx+21h], al
0x18003a4ce  jz      short loc_18003A4EB
0x18003a4d0  mov     rcx, [rsp+0B8h+var_28]
0x18003a4d8  xor     rcx, rsp; StackCookie
0x18003a4db  call    __security_check_cookie
0x18003a4e0  add     rsp, 0A8h
0x18003a4e7  pop     rdi
0x18003a4e8  pop     rbx
0x18003a4e9  retn
0x18003a4eb  mov     [rsp+0B8h+var_18], r14
0x18003a4f3  mov     r14, [rcx+70h]
0x18003a4f7  mov     [rsp+0B8h+arg_10], rbp
0x18003a4ff  mov     [rsp+0B8h+arg_18], rsi
0x18003a507  mov     [rsp+0B8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18003a510  call    cs:__imp_GetCurrentThread
0x18003a517  nop     dword ptr [rax+rax+00h]
0x18003a51c  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x18003a521  mov     edx, 2000Ch; DesiredAccess
0x18003a526  mov     rcx, rax; ThreadHandle
0x18003a529  mov     r8d, 1; OpenAsSelf
0x18003a52f  call    cs:__imp_OpenThreadToken
0x18003a536  nop     dword ptr [rax+rax+00h]
0x18003a53b  test    eax, eax
0x18003a53d  jz      short loc_18003A5AD
0x18003a53f  mov     rbp, [rsp+0B8h+TokenHandle]
0x18003a544  xor     esi, esi
0x18003a546  test    r14, r14
0x18003a549  jz      loc_18003A5E6
0x18003a54f  mov     rdx, r14; Token
0x18003a552  xor     ecx, ecx; Thread
0x18003a554  xor     esi, esi
0x18003a556  call    cs:__imp_SetThreadToken
0x18003a55d  nop     dword ptr [rax+rax+00h]
0x18003a562  test    eax, eax
0x18003a564  jz      loc_18003A66D
0x18003a56a  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18003a56e  jz      short loc_18003A579
0x18003a570  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x18003a577  jnz     short loc_18003A5F8
0x18003a579  test    esi, esi
0x18003a57b  jnz     loc_18003A679
0x18003a581  mov     [rbx], rbp
0x18003a584  mov     ebx, esi
0x18003a586  test    esi, esi
0x18003a588  jnz     loc_18003A69B
0x18003a58e  mov     rsi, [rsp+0B8h+arg_18]
0x18003a596  mov     eax, ebx
0x18003a598  mov     rbp, [rsp+0B8h+arg_10]
0x18003a5a0  mov     r14, [rsp+0B8h+var_18]
0x18003a5a8  jmp     loc_18003A4D0
0x18003a5ad  call    cs:__imp_GetLastError
0x18003a5b4  nop     dword ptr [rax+rax+00h]
0x18003a5b9  test    eax, eax
0x18003a5bb  mov     ecx, 54Fh
0x18003a5c0  cmovz   eax, ecx
0x18003a5c3  xor     esi, esi
0x18003a5c5  cmp     eax, 3F0h
0x18003a5ca  cmovnz  esi, eax
0x18003a5cd  sub     eax, 3F0h
0x18003a5d2  neg     eax
0x18003a5d4  sbb     rbp, rbp
0x18003a5d7  mov     [rsp+0B8h+TokenHandle], rbp
0x18003a5dc  test    esi, esi
0x18003a5de  jz      loc_18003A546
0x18003a5e4  jmp     short loc_18003A56A
0x18003a5e6  test    rbp, rbp
0x18003a5e9  jnz     loc_18003A54F
0x18003a5ef  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18003a5f6  jmp     short loc_18003A581
0x18003a5f8  lea     rax, [rsp+0B8h+var_78]
0x18003a5fd  mov     [rsp+0B8h+var_80], esi
0x18003a601  mov     [rsp+0B8h+var_58], rax
0x18003a606  lea     rdx, ThreadTokenSet
0x18003a60d  lea     rax, [rsp+0B8h+var_70]
0x18003a612  mov     [rsp+0B8h+var_70], rbp
0x18003a617  mov     [rsp+0B8h+var_48], rax
0x18003a61c  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18003a623  lea     rax, [rsp+0B8h+var_80]
0x18003a628  mov     [rsp+0B8h+var_78], r14
0x18003a62d  mov     [rsp+0B8h+var_38], rax
0x18003a635  mov     r9d, 4
0x18003a63b  lea     rax, [rsp+0B8h+var_68]
0x18003a640  mov     [rsp+0B8h+var_50], 8
0x18003a649  mov     [rsp+0B8h+var_98], rax
0x18003a64e  mov     [rsp+0B8h+var_40], 8
0x18003a657  mov     [rsp+0B8h+var_30], 4
0x18003a663  call    McGenEventWrite_EventWriteTransfer
0x18003a668  jmp     loc_18003A579
0x18003a66d  call    WaGetLastError
0x18003a672  mov     esi, eax
0x18003a674  jmp     loc_18003A56A
0x18003a679  lea     rax, [rbp-1]
0x18003a67d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003a681  ja      short loc_18003A692
0x18003a683  mov     rcx, rbp; hObject
0x18003a686  call    cs:__imp_CloseHandle
0x18003a68d  nop     dword ptr [rax+rax+00h]
0x18003a692  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18003a699  mov     ebx, esi
0x18003a69b  test    byte ptr cs:xmmword_1800AD710, 2
0x18003a6a2  jz      loc_18003A58E
0x18003a6a8  mov     edx, 11h
0x18003a6ad  mov     dword ptr [rsp+0B8h+var_98], esi
0x18003a6b1  mov     ecx, 201h
0x18003a6b6  lea     r8, WPP_247e30510a1b3c47cfbd7b690ee005cd_Traceguids
0x18003a6bd  mov     r9, rdi
0x18003a6c0  call    WPP_SF_qD
0x18003a6c5  jmp     loc_18003A58E
```
