# CINet::CheckIAuthenticateHostUI(HWND__ *)

- ea: `0x1800d5b60`
- end: `0x1800d5e15`
- name: `?CheckIAuthenticateHostUI@CINet@@IEAAKPEAUHWND__@@@Z`
- size: `693`
- prototype: `unsigned int __fastcall(CINet *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d53d0`

## callees

- `0x180008300`
- `0x1800d592c`
- `0x1800d5b60`
- `0x1800d6240`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d5c37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5c0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d5c0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d5b91`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d5cae`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d5b91`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d5cae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5dc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5dc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d5df4`
- `WININET!InternetSetOptionW` at `0x1800d5d08`
- `WININET!InternetSetOptionW` at `0x1800d5d47`
- `WININET!InternetSetOptionW` at `0x1800d5d08`
- `WININET!InternetSetOptionW` at `0x1800d5d47`

## pseudocode

```c
__int64 __fastcall CINet::CheckIAuthenticateHostUI(HINTERNET *this, HWND a2)
{
  unsigned int v5; // r12d
  int v6; // eax
  _WORD *v7; // r14
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 i; // rax
  __int64 v11; // r9
  _BYTE *v12; // r8
  __int64 v13; // rdi
  __int64 v14; // r9
  _BYTE *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  _BYTE *j; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  LPVOID v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-10h] BYREF
  bool v26; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID lpBuffer; // [rsp+B8h] [rbp+58h] BYREF

  InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
  if ( !byte_18015DE34 )
    return 1223;
  v5 = 0;
  pv = 0;
  lpBuffer = 0;
  v23 = 0;
  v26 = 0;
  if ( this[44] )
  {
    CINet::GetPreviouslySubmittedCredential((CINet *)this, (unsigned __int16 **)&pv);
    v24 = 0;
    v6 = CINet::CheckAuthHeaders((CINet *)this, &v26);
    v7 = pv;
    v8 = v6;
    if ( v6 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v8 = -2147467263;
      v9 = 0;
      EnterCriticalSection(&g_csDll);
      for ( i = qword_18015E5D8; i; i = *(_QWORD *)(i + 16) )
      {
        if ( *(HWND *)i == a2 )
        {
          v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(i + 8);
          break;
        }
      }
      LeaveCriticalSection(&g_csDll);
      if ( !v9 || (v8 = (**v9)(v9, &GUID_ac78490a_ea21_4757_87d2_12bf26030d30, &v24)) != 0 )
      {
        if ( v8 == -2147467263 )
        {
          InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
          if ( byte_18015DE35 )
            v8 = -2147467259;
        }
      }
      else
      {
        LOBYTE(v11) = v26;
        v8 = (*(__int64 (__fastcall **)(__int64, HINTERNET, _WORD *, __int64, LPVOID *, LPVOID *))(*(_QWORD *)v24 + 24LL))(
               v24,
               this[14],
               v7,
               v11,
               &lpBuffer,
               &v23);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v12 = lpBuffer;
    v13 = -1;
    if ( v8 < 0 )
    {
      v15 = v23;
    }
    else
    {
      if ( lpBuffer )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)lpBuffer + v14) );
        InternetSetOptionW(this[44], ((_BYTE)this[124] & 1) != 0 ? 43 : 28, lpBuffer, v14 + 1);
        v12 = lpBuffer;
      }
      v15 = v23;
      if ( v23 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v23 + v16) );
        InternetSetOptionW(this[44], ((_BYTE)this[124] & 1) != 0 ? 44 : 29, v23, v16 + 1);
        v12 = lpBuffer;
        v15 = v23;
      }
      v5 = 12032;
    }
    if ( v7 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v18 = 2 * v17;
      for ( j = v7; v18; --v18 )
        *j++ = 0;
      CoTaskMemFree(v7);
      v12 = lpBuffer;
      v15 = v23;
    }
    if ( v12 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v12[2 * v20] );
      v21 = 2 * v20;
      if ( v21 )
      {
        do
        {
          *v12++ = 0;
          --v21;
        }
        while ( v21 );
        v12 = lpBuffer;
      }
      CoTaskMemFree(v12);
      v15 = v23;
    }
    if ( v15 )
    {
      do
        ++v13;
      while ( *(_WORD *)&v15[2 * v13] );
      v22 = 2 * v13;
      if ( v22 )
      {
        do
        {
          *v15++ = 0;
          --v22;
        }
        while ( v22 );
        v15 = v23;
      }
      CoTaskMemFree(v15);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800d5b60  mov     [rsp-38h+arg_0], rbx
0x1800d5b65  push    rbp
0x1800d5b66  push    rsi
0x1800d5b67  push    rdi
0x1800d5b68  push    r12
0x1800d5b6a  push    r13
0x1800d5b6c  push    r14
0x1800d5b6e  push    r15
0x1800d5b70  mov     rbp, rsp
0x1800d5b73  sub     rsp, 60h
0x1800d5b77  mov     r15, rdx
0x1800d5b7a  mov     rsi, rcx
0x1800d5b7d  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800d5b84  xor     r9d, r9d; Context
0x1800d5b87  lea     rcx, stru_18015EA38; InitOnce
0x1800d5b8e  xor     r8d, r8d; Parameter
0x1800d5b91  call    cs:__imp_InitOnceExecuteOnce
0x1800d5b97  xor     r13d, r13d
0x1800d5b9a  cmp     cs:byte_18015DE34, r13b
0x1800d5ba1  jnz     short loc_1800D5BAD
0x1800d5ba3  mov     eax, 4C7h
0x1800d5ba8  jmp     loc_1800D5DFD
0x1800d5bad  mov     r12d, r13d
0x1800d5bb0  mov     [rbp+pv], r13
0x1800d5bb4  mov     [rbp+lpBuffer], r13
0x1800d5bb8  mov     [rbp+var_20], r13
0x1800d5bbc  mov     [rbp+arg_10], r13b
0x1800d5bc0  cmp     [rsi+160h], r13
0x1800d5bc7  jz      loc_1800D5DFA
0x1800d5bcd  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800d5bd1  mov     rcx, rsi; this
0x1800d5bd4  call    ?GetPreviouslySubmittedCredential@CINet@@IEAAHPEAPEAG@Z; CINet::GetPreviouslySubmittedCredential(ushort * *)
0x1800d5bd9  lea     rdx, [rbp+arg_10]; bool *
0x1800d5bdd  mov     [rbp+var_18], r13
0x1800d5be1  mov     rcx, rsi; this
0x1800d5be4  call    ?CheckAuthHeaders@CINet@@IEAAJPEA_N@Z; CINet::CheckAuthHeaders(bool *)
0x1800d5be9  mov     r14, [rbp+pv]
0x1800d5bed  mov     ebx, eax
0x1800d5bef  test    eax, eax
0x1800d5bf1  js      loc_1800D5CC1
0x1800d5bf7  lea     rcx, [rbp+var_18]
0x1800d5bfb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d5c00  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d5c07  mov     ebx, 80004001h
0x1800d5c0c  mov     rdi, r13
0x1800d5c0f  call    cs:__imp_EnterCriticalSection
0x1800d5c15  mov     rax, cs:qword_18015E5D8
0x1800d5c1c  test    rax, rax
0x1800d5c1f  jz      short loc_1800D5C30
0x1800d5c21  cmp     [rax], r15
0x1800d5c24  jz      short loc_1800D5C2C
0x1800d5c26  mov     rax, [rax+10h]
0x1800d5c2a  jmp     short loc_1800D5C1C
0x1800d5c2c  mov     rdi, [rax+8]
0x1800d5c30  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800d5c37  call    cs:__imp_LeaveCriticalSection
0x1800d5c3d  test    rdi, rdi
0x1800d5c40  jz      short loc_1800D5C92
0x1800d5c42  mov     rax, [rdi]
0x1800d5c45  lea     r8, [rbp+var_18]
0x1800d5c49  lea     rdx, _GUID_ac78490a_ea21_4757_87d2_12bf26030d30
0x1800d5c50  mov     rcx, rdi
0x1800d5c53  mov     rax, [rax]
0x1800d5c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5c5b  mov     ebx, eax
0x1800d5c5d  test    eax, eax
0x1800d5c5f  jnz     short loc_1800D5C92
0x1800d5c61  mov     rcx, [rbp+var_18]
0x1800d5c65  lea     rdx, [rbp+var_20]
0x1800d5c69  mov     r9b, [rbp+arg_10]
0x1800d5c6d  mov     r8, r14
0x1800d5c70  mov     [rsp+60h+var_38], rdx
0x1800d5c75  lea     rdx, [rbp+lpBuffer]
0x1800d5c79  mov     [rsp+60h+var_40], rdx
0x1800d5c7e  mov     rax, [rcx]
0x1800d5c81  mov     rdx, [rsi+70h]
0x1800d5c85  mov     rax, [rax+18h]
0x1800d5c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5c8e  mov     ebx, eax
0x1800d5c90  jmp     short loc_1800D5CC1
0x1800d5c92  cmp     ebx, 80004001h
0x1800d5c98  jnz     short loc_1800D5CC1
0x1800d5c9a  xor     r9d, r9d; Context
0x1800d5c9d  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800d5ca4  xor     r8d, r8d; Parameter
0x1800d5ca7  lea     rcx, stru_18015EA38; InitOnce
0x1800d5cae  call    cs:__imp_InitOnceExecuteOnce
0x1800d5cb4  cmp     cs:byte_18015DE35, r13b
0x1800d5cbb  lea     eax, [rbx+4]
0x1800d5cbe  cmovnz  ebx, eax
0x1800d5cc1  lea     rcx, [rbp+var_18]
0x1800d5cc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d5cca  mov     r8, [rbp+lpBuffer]; lpBuffer
0x1800d5cce  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d5cd2  test    ebx, ebx
0x1800d5cd4  js      loc_1800D5D5D
0x1800d5cda  test    r8, r8
0x1800d5cdd  jz      short loc_1800D5D12
0x1800d5cdf  mov     r9, rdi
0x1800d5ce2  inc     r9
0x1800d5ce5  cmp     [r8+r9*2], r13w
0x1800d5cea  jnz     short loc_1800D5CE2
0x1800d5cec  mov     al, [rsi+3E0h]
0x1800d5cf2  inc     r9d; dwBufferLength
0x1800d5cf5  mov     rcx, [rsi+160h]; hInternet
0x1800d5cfc  and     al, 1
0x1800d5cfe  neg     al
0x1800d5d00  sbb     edx, edx
0x1800d5d02  and     edx, 0Fh
0x1800d5d05  add     edx, 1Ch; dwOption
0x1800d5d08  call    cs:__imp_InternetSetOptionW
0x1800d5d0e  mov     r8, [rbp+lpBuffer]
0x1800d5d12  mov     rcx, [rbp+var_20]
0x1800d5d16  test    rcx, rcx
0x1800d5d19  jz      short loc_1800D5D55
0x1800d5d1b  mov     r9, rdi
0x1800d5d1e  inc     r9
0x1800d5d21  cmp     [rcx+r9*2], r13w
0x1800d5d26  jnz     short loc_1800D5D1E
0x1800d5d28  mov     al, [rsi+3E0h]
0x1800d5d2e  inc     r9d; dwBufferLength
0x1800d5d31  and     al, 1
0x1800d5d33  mov     r8, rcx; lpBuffer
0x1800d5d36  mov     rcx, [rsi+160h]; hInternet
0x1800d5d3d  neg     al
0x1800d5d3f  sbb     edx, edx
0x1800d5d41  and     edx, 0Fh
0x1800d5d44  add     edx, 1Dh; dwOption
0x1800d5d47  call    cs:__imp_InternetSetOptionW
0x1800d5d4d  mov     r8, [rbp+lpBuffer]
0x1800d5d51  mov     rcx, [rbp+var_20]
0x1800d5d55  mov     r12d, 2F00h
0x1800d5d5b  jmp     short loc_1800D5D61
0x1800d5d5d  mov     rcx, [rbp+var_20]
0x1800d5d61  test    r14, r14
0x1800d5d64  jz      short loc_1800D5D9C
0x1800d5d66  mov     rax, rdi
0x1800d5d69  inc     rax
0x1800d5d6c  cmp     [r14+rax*2], r13w
0x1800d5d71  jnz     short loc_1800D5D69
0x1800d5d73  lea     rdx, [rax+rax]
0x1800d5d77  mov     rax, r14
0x1800d5d7a  test    rdx, rdx
0x1800d5d7d  jz      short loc_1800D5D8B
0x1800d5d7f  mov     [rax], r13b
0x1800d5d82  inc     rax
0x1800d5d85  sub     rdx, 1
0x1800d5d89  jnz     short loc_1800D5D7F
0x1800d5d8b  mov     rcx, r14; pv
0x1800d5d8e  call    cs:__imp_CoTaskMemFree
0x1800d5d94  mov     r8, [rbp+lpBuffer]
0x1800d5d98  mov     rcx, [rbp+var_20]
0x1800d5d9c  test    r8, r8
0x1800d5d9f  jz      short loc_1800D5DD0
0x1800d5da1  mov     rax, rdi
0x1800d5da4  inc     rax
0x1800d5da7  cmp     [r8+rax*2], r13w
0x1800d5dac  jnz     short loc_1800D5DA4
0x1800d5dae  add     rax, rax
0x1800d5db1  jz      short loc_1800D5DC3
0x1800d5db3  mov     [r8], r13b
0x1800d5db6  inc     r8
0x1800d5db9  sub     rax, 1
0x1800d5dbd  jnz     short loc_1800D5DB3
0x1800d5dbf  mov     r8, [rbp+lpBuffer]
0x1800d5dc3  mov     rcx, r8; pv
0x1800d5dc6  call    cs:__imp_CoTaskMemFree
0x1800d5dcc  mov     rcx, [rbp+var_20]
0x1800d5dd0  test    rcx, rcx
0x1800d5dd3  jz      short loc_1800D5DFA
0x1800d5dd5  inc     rdi
0x1800d5dd8  cmp     [rcx+rdi*2], r13w
0x1800d5ddd  jnz     short loc_1800D5DD5
0x1800d5ddf  add     rdi, rdi
0x1800d5de2  jz      short loc_1800D5DF4
0x1800d5de4  mov     [rcx], r13b
0x1800d5de7  inc     rcx
0x1800d5dea  sub     rdi, 1
0x1800d5dee  jnz     short loc_1800D5DE4
0x1800d5df0  mov     rcx, [rbp+var_20]; pv
0x1800d5df4  call    cs:__imp_CoTaskMemFree
0x1800d5dfa  mov     eax, r12d
0x1800d5dfd  mov     rbx, [rsp+60h+arg_0]
0x1800d5e05  add     rsp, 60h
0x1800d5e09  pop     r15
0x1800d5e0b  pop     r14
0x1800d5e0d  pop     r13
0x1800d5e0f  pop     r12
0x1800d5e11  pop     rdi
0x1800d5e12  pop     rsi
0x1800d5e13  pop     rbp
0x1800d5e14  retn
```
