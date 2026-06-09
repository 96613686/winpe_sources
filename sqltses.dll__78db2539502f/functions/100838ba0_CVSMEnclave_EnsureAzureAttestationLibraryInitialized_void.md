# CVSMEnclave::EnsureAzureAttestationLibraryInitialized(void)

- ea: `0x100838ba0`
- end: `0x100838eeb`
- name: `?EnsureAzureAttestationLibraryInitialized@CVSMEnclave@@EEAAXXZ`
- size: `843`
- prototype: `void __fastcall(CVSMEnclave *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x10049f780`
- `0x1004c7420`
- `0x1008109c0`
- `0x100838ba0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100838c13`
- `KERNEL32!GetProcAddress` at `0x100838c86`
- `KERNEL32!GetProcAddress` at `0x100838cf6`
- `KERNEL32!GetProcAddress` at `0x100838d66`
- `KERNEL32!GetProcAddress` at `0x100838dd6`
- `KERNEL32!GetProcAddress` at `0x100838c13`
- `KERNEL32!GetProcAddress` at `0x100838c86`
- `KERNEL32!GetProcAddress` at `0x100838cf6`
- `KERNEL32!GetProcAddress` at `0x100838d66`
- `KERNEL32!GetProcAddress` at `0x100838dd6`
- `KERNEL32!GetLastError` at `0x100838c25`
- `KERNEL32!GetLastError` at `0x100838c98`
- `KERNEL32!GetLastError` at `0x100838d08`
- `KERNEL32!GetLastError` at `0x100838d78`
- `KERNEL32!GetLastError` at `0x100838de8`
- `KERNEL32!GetLastError` at `0x100838c25`
- `KERNEL32!GetLastError` at `0x100838c98`
- `KERNEL32!GetLastError` at `0x100838d08`
- `KERNEL32!GetLastError` at `0x100838d78`
- `KERNEL32!GetLastError` at `0x100838de8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100838e9c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100838e9c`
- `AzureAttestManager!InitializeAttestationLibrary` at `0x100838e3f`
- `AzureAttestManager!InitializeAttestationLibrary` at `0x100838e3f`

## string_xrefs

- `0x100838c08`: `VsmEnclaveAttestationConfigure`
- `0x100838c2e`: `VsmEnclaveAttestationConfigure`
- `0x100838c7b`: `VsmEnclaveAttestationCreateSession`
- `0x100838ca1`: `VsmEnclaveAttestationCreateSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVSMEnclave::EnsureAzureAttestationLibraryInitialized(CVSMEnclave *this)
{
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  int v4; // ebx
  __int64 v5; // rdi
  bool v6; // zf
  FARPROC v7; // rax
  DWORD v8; // eax
  int v9; // ebx
  __int64 v10; // rdi
  FARPROC v11; // rax
  DWORD v12; // eax
  int v13; // ebx
  __int64 v14; // rdi
  FARPROC v15; // rax
  DWORD v16; // eax
  int v17; // ebx
  __int64 v18; // rdi
  FARPROC v19; // rax
  DWORD v20; // eax
  int v21; // ebx
  __int64 v22; // rdi
  int v23; // ebx
  __int64 v24; // rdi
  int v25; // ebx
  __int64 v26; // rdi
  char *v27; // [rsp+38h] [rbp-18h] BYREF
  int v28; // [rsp+40h] [rbp-10h]

  if ( !CVSMEnclave::m_attestationLibraryInitalized )
  {
    v27 = (char *)this + 288;
    v28 = 0;
    TAutoMutex<SOS_Mutex,1>::GetAccess((__int64)&v27, 4195753);
    if ( !CVSMEnclave::m_attestationLibraryInitalized )
    {
      *((_DWORD *)this + 86) = 0;
      *((_QWORD *)this + 44) = 0;
      ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "VsmEnclaveAttestationConfigure");
      *((_QWORD *)this + 45) = ProcAddress;
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        scierrlog(0x9275u, L"VBS", L"VsmEnclaveAttestationConfigure", LastError);
        v4 = v28;
        if ( v28 )
        {
          v5 = (__int64)v27;
          do
          {
            *(_QWORD *)(v5 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v5, 0);
            v6 = v4-- == 1;
            v28 = v4;
          }
          while ( !v6 );
        }
LABEL_32:
        ex_raise(331, 96, 16, 72, L"EnsureAzureAttestationLibraryInitialized", -2147467259, -2);
        return;
      }
      v7 = GetProcAddress(*((HMODULE *)this + 1), "VsmEnclaveAttestationCreateSession");
      *((_QWORD *)this + 46) = v7;
      if ( !v7 )
      {
        v8 = GetLastError();
        scierrlog(0x9275u, L"VBS", L"VsmEnclaveAttestationCreateSession", v8);
        v9 = v28;
        if ( v28 )
        {
          v10 = (__int64)v27;
          do
          {
            *(_QWORD *)(v10 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v10, 0);
            v6 = v9-- == 1;
            v28 = v9;
          }
          while ( !v6 );
        }
        goto LABEL_32;
      }
      v11 = GetProcAddress(*((HMODULE *)this + 1), "VsmEnclaveAttestationAttest");
      *((_QWORD *)this + 47) = v11;
      if ( !v11 )
      {
        v12 = GetLastError();
        scierrlog(0x9275u, L"VBS", L"VsmEnclaveAttestationAttest", v12);
        v13 = v28;
        if ( v28 )
        {
          v14 = (__int64)v27;
          do
          {
            *(_QWORD *)(v14 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v14, 0);
            v6 = v13-- == 1;
            v28 = v13;
          }
          while ( !v6 );
        }
        goto LABEL_32;
      }
      v15 = GetProcAddress(*((HMODULE *)this + 1), "VsmEnclaveAttestationGetReport");
      *((_QWORD *)this + 48) = v15;
      if ( !v15 )
      {
        v16 = GetLastError();
        scierrlog(0x9275u, L"VBS", L"VsmEnclaveAttestationGetReport", v16);
        v17 = v28;
        if ( v28 )
        {
          v18 = (__int64)v27;
          do
          {
            *(_QWORD *)(v18 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v18, 0);
            v6 = v17-- == 1;
            v28 = v17;
          }
          while ( !v6 );
        }
        goto LABEL_32;
      }
      v19 = GetProcAddress(*((HMODULE *)this + 1), "VsmEnclaveAttestationCloseSession");
      *((_QWORD *)this + 49) = v19;
      if ( !v19 )
      {
        v20 = GetLastError();
        scierrlog(0x9275u, L"VBS", L"VsmEnclaveAttestationCloseSession", v20);
        v21 = v28;
        if ( v28 )
        {
          v22 = (__int64)v27;
          do
          {
            *(_QWORD *)(v22 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v22, 0);
            v6 = v21-- == 1;
            v28 = v21;
          }
          while ( !v6 );
        }
        goto LABEL_32;
      }
      if ( (int)InitializeAttestationLibrary((char *)this + 344) < 0 )
      {
        v23 = v28;
        if ( v28 )
        {
          v24 = (__int64)v27;
          do
          {
            *(_QWORD *)(v24 + 48) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v24, 0);
            v6 = v23-- == 1;
            v28 = v23;
          }
          while ( !v6 );
        }
        goto LABEL_32;
      }
      CVSMEnclave::m_attestationLibraryInitalized = 1;
    }
    v25 = v28;
    if ( v28 )
    {
      v26 = (__int64)v27;
      do
      {
        *(_QWORD *)(v26 + 48) = 0;
        EventAutoInternal<SuspendQueueSLock>::Signal(v26, 0);
        v6 = v25-- == 1;
        v28 = v25;
      }
      while ( !v6 );
    }
  }
}

```

## disassembly

```asm
0x100838ba0  push    rbp
0x100838ba2  mov     rbp, rsp
0x100838ba5  sub     rsp, 50h
0x100838ba9  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x100838bb1  mov     [rsp+50h+arg_0], rbx
0x100838bb6  mov     [rsp+50h+arg_8], rsi
0x100838bbb  mov     [rsp+50h+arg_10], rdi
0x100838bc0  mov     rbx, rcx
0x100838bc3  cmp     cs:?m_attestationLibraryInitalized@CVSMEnclave@@0_NA, 0; bool CVSMEnclave::m_attestationLibraryInitalized
0x100838bca  jnz     loc_100838ED6
0x100838bd0  lea     rax, [rcx+120h]
0x100838bd7  mov     [rbp+var_18], rax
0x100838bdb  xor     esi, esi
0x100838bdd  mov     [rbp+var_10], esi
0x100838be0  mov     edx, 4005A9h
0x100838be5  lea     rcx, [rbp+var_18]
0x100838be9  call    ?GetAccess@?$TAutoMutex@VSOS_Mutex@@$00@@QEAAXI@Z; TAutoMutex<SOS_Mutex,1>::GetAccess(uint)
0x100838bee  cmp     cs:?m_attestationLibraryInitalized@CVSMEnclave@@0_NA, sil; bool CVSMEnclave::m_attestationLibraryInitalized
0x100838bf5  jnz     loc_100838EAB
0x100838bfb  mov     [rbx+158h], esi
0x100838c01  mov     [rbx+160h], rsi
0x100838c08  lea     rdx, aVsmenclaveatte_4; "VsmEnclaveAttestationConfigure"
0x100838c0f  mov     rcx, [rbx+8]; hModule
0x100838c13  call    cs:__imp_GetProcAddress
0x100838c19  mov     [rbx+168h], rax
0x100838c20  test    rax, rax
0x100838c23  jnz     short loc_100838C7B
0x100838c25  call    cs:__imp_GetLastError
0x100838c2b  mov     r9d, eax
0x100838c2e  lea     r8, aVsmenclaveatte_7; "VsmEnclaveAttestationConfigure"
0x100838c35  lea     rdx, aVbs; "VBS"
0x100838c3c  mov     ecx, 9275h; unsigned int
0x100838c41  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838c46  nop
0x100838c47  mov     ebx, [rbp+var_10]
0x100838c4a  test    ebx, ebx
0x100838c4c  jz      loc_100838E76
0x100838c52  mov     rdi, [rbp+var_18]
0x100838c56  nop     word ptr [rax+rax+00000000h]
0x100838c60  mov     [rdi+30h], rsi
0x100838c64  xor     edx, edx
0x100838c66  mov     rcx, rdi
0x100838c69  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838c6e  add     ebx, 0FFFFFFFFh
0x100838c71  mov     [rbp+var_10], ebx
0x100838c74  jnz     short loc_100838C60
0x100838c76  jmp     loc_100838E76
0x100838c7b  lea     rdx, aVsmenclaveatte_6; "VsmEnclaveAttestationCreateSession"
0x100838c82  mov     rcx, [rbx+8]; hModule
0x100838c86  call    cs:__imp_GetProcAddress
0x100838c8c  mov     [rbx+170h], rax
0x100838c93  test    rax, rax
0x100838c96  jnz     short loc_100838CEB
0x100838c98  call    cs:__imp_GetLastError
0x100838c9e  mov     r9d, eax
0x100838ca1  lea     r8, aVsmenclaveatte_2; "VsmEnclaveAttestationCreateSession"
0x100838ca8  lea     rdx, aVbs; "VBS"
0x100838caf  mov     ecx, 9275h; unsigned int
0x100838cb4  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838cb9  nop
0x100838cba  mov     ebx, [rbp+var_10]
0x100838cbd  test    ebx, ebx
0x100838cbf  jz      loc_100838E76
0x100838cc5  mov     rdi, [rbp+var_18]
0x100838cc9  nop     dword ptr [rax+00000000h]
0x100838cd0  mov     [rdi+30h], rsi
0x100838cd4  xor     edx, edx
0x100838cd6  mov     rcx, rdi
0x100838cd9  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838cde  add     ebx, 0FFFFFFFFh
0x100838ce1  mov     [rbp+var_10], ebx
0x100838ce4  jnz     short loc_100838CD0
0x100838ce6  jmp     loc_100838E76
0x100838ceb  lea     rdx, aVsmenclaveatte_3; "VsmEnclaveAttestationAttest"
0x100838cf2  mov     rcx, [rbx+8]; hModule
0x100838cf6  call    cs:__imp_GetProcAddress
0x100838cfc  mov     [rbx+178h], rax
0x100838d03  test    rax, rax
0x100838d06  jnz     short loc_100838D5B
0x100838d08  call    cs:__imp_GetLastError
0x100838d0e  mov     r9d, eax
0x100838d11  lea     r8, aVsmenclaveatte_0; "VsmEnclaveAttestationAttest"
0x100838d18  lea     rdx, aVbs; "VBS"
0x100838d1f  mov     ecx, 9275h; unsigned int
0x100838d24  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838d29  nop
0x100838d2a  mov     ebx, [rbp+var_10]
0x100838d2d  test    ebx, ebx
0x100838d2f  jz      loc_100838E76
0x100838d35  mov     rdi, [rbp+var_18]
0x100838d39  nop     dword ptr [rax+00000000h]
0x100838d40  mov     [rdi+30h], rsi
0x100838d44  xor     edx, edx
0x100838d46  mov     rcx, rdi
0x100838d49  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838d4e  add     ebx, 0FFFFFFFFh
0x100838d51  mov     [rbp+var_10], ebx
0x100838d54  jnz     short loc_100838D40
0x100838d56  jmp     loc_100838E76
0x100838d5b  lea     rdx, aVsmenclaveatte_1; "VsmEnclaveAttestationGetReport"
0x100838d62  mov     rcx, [rbx+8]; hModule
0x100838d66  call    cs:__imp_GetProcAddress
0x100838d6c  mov     [rbx+180h], rax
0x100838d73  test    rax, rax
0x100838d76  jnz     short loc_100838DCB
0x100838d78  call    cs:__imp_GetLastError
0x100838d7e  mov     r9d, eax
0x100838d81  lea     r8, aVsmenclaveatte_8; "VsmEnclaveAttestationGetReport"
0x100838d88  lea     rdx, aVbs; "VBS"
0x100838d8f  mov     ecx, 9275h; unsigned int
0x100838d94  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838d99  nop
0x100838d9a  mov     ebx, [rbp+var_10]
0x100838d9d  test    ebx, ebx
0x100838d9f  jz      loc_100838E76
0x100838da5  mov     rdi, [rbp+var_18]
0x100838da9  nop     dword ptr [rax+00000000h]
0x100838db0  mov     [rdi+30h], rsi
0x100838db4  xor     edx, edx
0x100838db6  mov     rcx, rdi
0x100838db9  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838dbe  add     ebx, 0FFFFFFFFh
0x100838dc1  mov     [rbp+var_10], ebx
0x100838dc4  jnz     short loc_100838DB0
0x100838dc6  jmp     loc_100838E76
0x100838dcb  lea     rdx, aVsmenclaveatte; "VsmEnclaveAttestationCloseSession"
0x100838dd2  mov     rcx, [rbx+8]; hModule
0x100838dd6  call    cs:__imp_GetProcAddress
0x100838ddc  mov     [rbx+188h], rax
0x100838de3  test    rax, rax
0x100838de6  jnz     short loc_100838E38
0x100838de8  call    cs:__imp_GetLastError
0x100838dee  mov     r9d, eax
0x100838df1  lea     r8, aVsmenclaveatte_5; "VsmEnclaveAttestationCloseSession"
0x100838df8  lea     rdx, aVbs; "VBS"
0x100838dff  mov     ecx, 9275h; unsigned int
0x100838e04  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100838e09  nop
0x100838e0a  mov     ebx, [rbp+var_10]
0x100838e0d  test    ebx, ebx
0x100838e0f  jz      short loc_100838E76
0x100838e11  mov     rdi, [rbp+var_18]
0x100838e15  nop     word ptr [rax+rax+00000000h]
0x100838e20  mov     [rdi+30h], rsi
0x100838e24  xor     edx, edx
0x100838e26  mov     rcx, rdi
0x100838e29  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838e2e  add     ebx, 0FFFFFFFFh
0x100838e31  mov     [rbp+var_10], ebx
0x100838e34  jnz     short loc_100838E20
0x100838e36  jmp     short loc_100838E76
0x100838e38  lea     rcx, [rbx+158h]
0x100838e3f  call    cs:__imp_InitializeAttestationLibrary
0x100838e45  test    eax, eax
0x100838e47  jns     short loc_100838EA4
0x100838e49  mov     ebx, [rbp+var_10]
0x100838e4c  test    ebx, ebx
0x100838e4e  jz      short loc_100838E76
0x100838e50  mov     rdi, [rbp+var_18]
0x100838e54  nop     dword ptr [rax+00h]
0x100838e58  nop     dword ptr [rax+rax+00000000h]
0x100838e60  mov     [rdi+30h], rsi
0x100838e64  xor     edx, edx
0x100838e66  mov     rcx, rdi
0x100838e69  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838e6e  add     ebx, 0FFFFFFFFh
0x100838e71  mov     [rbp+var_10], ebx
0x100838e74  jnz     short loc_100838E60
0x100838e76  mov     [rsp+50h+var_28], 80004005h
0x100838e7e  lea     rax, aEnsureazureatt; "EnsureAzureAttestationLibraryInitialize"...
0x100838e85  mov     [rsp+50h+var_30], rax
0x100838e8a  mov     edx, 60h ; '`'
0x100838e8f  mov     ecx, 14Bh
0x100838e94  lea     r9d, [rdx-18h]
0x100838e98  lea     r8d, [rdx-50h]
0x100838e9c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100838ea2  jmp     short loc_100838ED6
0x100838ea4  mov     cs:?m_attestationLibraryInitalized@CVSMEnclave@@0_NA, 1; bool CVSMEnclave::m_attestationLibraryInitalized
0x100838eab  mov     ebx, [rbp+var_10]
0x100838eae  test    ebx, ebx
0x100838eb0  jz      short loc_100838ED6
0x100838eb2  mov     rdi, [rbp+var_18]
0x100838eb6  nop     word ptr [rax+rax+00000000h]
0x100838ec0  mov     [rdi+30h], rsi
0x100838ec4  xor     edx, edx
0x100838ec6  mov     rcx, rdi
0x100838ec9  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x100838ece  add     ebx, 0FFFFFFFFh
0x100838ed1  mov     [rbp+var_10], ebx
0x100838ed4  jnz     short loc_100838EC0
0x100838ed6  mov     rbx, [rsp+50h+arg_0]
0x100838edb  mov     rsi, [rsp+50h+arg_8]
0x100838ee0  mov     rdi, [rsp+50h+arg_10]
0x100838ee5  add     rsp, 50h
0x100838ee9  pop     rbp
0x100838eea  retn
```
