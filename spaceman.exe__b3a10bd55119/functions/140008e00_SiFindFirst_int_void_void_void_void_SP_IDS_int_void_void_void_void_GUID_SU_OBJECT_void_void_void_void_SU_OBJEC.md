# SiFindFirst(int (*)(void *,void *,void *,void *,_SP_IDS * *),int (*)(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *),void *,void *,void *,void *,_SU_OBJECT * *)

- ea: `0x140008e00`
- end: `0x140008fe8`
- name: `?SiFindFirst@@YAPEAXP6AHPEAX000PEAPEAU_SP_IDS@@@ZP6AH0000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z00004@Z`
- size: `488`
- prototype: `__int64 __fastcall(int (*)(void *, void *, void *, void *, struct _SP_IDS **), int (*)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **), void *, void *, void *, void *, struct _SU_OBJECT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14000c7a4`

## callees

- `0x1400052b4`
- `0x140005cf8`
- `0x140008e00`
- `0x140009188`
- `0x140009200`
- `0x140009258`
- `0x14000b940`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140008f9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140008f9f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140008f40`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140008f40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x140008f70`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x140008f70`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140008f5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140008f5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ec7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008eb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008eb4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140008e2c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140008e2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140008e70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140008e70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008fad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140008fad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140008e95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140008e95`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140008eaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140008eaa`

## pseudocode

```c
__int64 __fastcall SiFindFirst(
        int (*a1)(void *, void *, void *, void *, struct _SP_IDS **),
        int (*a2)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **),
        void *a3,
        void *a4,
        void *a5,
        void *a6,
        struct _SU_OBJECT **a7)
{
  struct _SU_OBJECT **v9; // r12
  __int64 v10; // r15
  _QWORD *v11; // rax
  void *v12; // rbx
  HANDLE CurrentThread; // rax
  int Control; // eax
  HLOCAL v15; // r14
  struct _TP_WORK *v16; // rdi
  unsigned int i; // esi
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-29h] BYREF
  struct _SP_IDS *v21; // [rsp+68h] [rbp-21h] BYREF
  int v22; // [rsp+70h] [rbp-19h]
  __int64 (__fastcall *v23)(void *, void *, void *, void *, struct _GUID *, struct _SU_OBJECT **); // [rsp+78h] [rbp-11h]
  void *v24; // [rsp+80h] [rbp-9h]
  void *v25; // [rsp+88h] [rbp-1h]
  __int64 v26; // [rsp+90h] [rbp+7h]
  __int64 v27; // [rsp+98h] [rbp+Fh]
  void *v28; // [rsp+A0h] [rbp+17h]
  HLOCAL hMem; // [rsp+E0h] [rbp+57h] BYREF

  hMem = a2;
  InitializeCriticalSection(&CriticalSection);
  v9 = a7;
  v10 = -1;
  TokenHandle = 0;
  v21 = 0;
  v22 = 0;
  v28 = 0;
  hMem = 0;
  *a7 = 0;
  v11 = LocalAlloc(0x40u, 0x10u);
  v12 = v11;
  if ( !v11 )
  {
    SetLastError(0x5AAu);
    goto LABEL_22;
  }
  v11[1] = v11;
  *v11 = v11;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
    {
LABEL_21:
      SuFindClose(v12);
      goto LABEL_22;
    }
    SetLastError(0);
  }
  if ( !(unsigned int)SiGetDriveIdsCallback(a3, a4, 0, 0, &v21) )
    goto LABEL_21;
  v24 = a3;
  v23 = SiGetDriveCallback;
  v25 = a4;
  v26 = 0;
  v27 = 0;
  v28 = v12;
  Control = SuGetControl((struct _SP_CONTROL_INFO **)&hMem);
  v15 = hMem;
  if ( !Control )
    goto LABEL_18;
  if ( *((_BYTE *)hMem + 46) )
  {
    v16 = 0;
    SI_GET_CONTEXT::Callback(&CriticalSection);
  }
  else
  {
    v16 = CreateThreadpoolWork(SiFindFirstCallback, &CriticalSection, &ThreadpoolEnv);
    if ( !v16 )
      goto LABEL_18;
    for ( i = 0; i < *(_DWORD *)v21; ++i )
      SubmitThreadpoolWork(v16);
    WaitForThreadpoolWorkCallbacks(v16, 0);
  }
  if ( (unsigned int)SuFindNext(v12, v9) )
  {
    v10 = (__int64)v12;
    v12 = 0;
  }
  if ( v16 )
    CloseThreadpoolWork(v16);
LABEL_18:
  if ( v15 )
    LocalFree(v15);
  if ( v12 )
    goto LABEL_21;
LABEL_22:
  SI_GET_CONTEXT::~SI_GET_CONTEXT(&CriticalSection);
  return v10;
}

```

## disassembly

```asm
0x140008e00  mov     rax, rsp
0x140008e03  mov     [rax+8], rbx
0x140008e07  mov     [rax+18h], rsi
0x140008e0b  mov     [rax+10h], rdx
0x140008e0f  push    rbp
0x140008e10  push    rdi
0x140008e11  push    r12
0x140008e13  push    r14
0x140008e15  push    r15
0x140008e17  lea     rbp, [rax-47h]
0x140008e1b  sub     rsp, 0A0h
0x140008e22  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x140008e26  mov     rdi, r9
0x140008e29  mov     rsi, r8
0x140008e2c  call    cs:__imp_InitializeCriticalSection
0x140008e32  mov     r12, [rbp+3Fh+arg_30]
0x140008e36  or      r15, 0FFFFFFFFFFFFFFFFh
0x140008e3a  mov     [rbp+3Fh+TokenHandle], 0
0x140008e42  mov     [rbp+3Fh+var_60], 0
0x140008e4a  mov     [rbp+3Fh+var_58], 0
0x140008e51  lea     edx, [r15+11h]; uBytes
0x140008e55  mov     [rbp+3Fh+var_28], 0
0x140008e5d  lea     ecx, [rdx+30h]; uFlags
0x140008e60  mov     [rbp+3Fh+hMem], 0
0x140008e68  mov     qword ptr [r12], 0
0x140008e70  call    cs:__imp_LocalAlloc
0x140008e76  mov     rbx, rax
0x140008e79  test    rax, rax
0x140008e7c  jnz     short loc_140008E8E
0x140008e7e  mov     ecx, 5AAh; dwErrCode
0x140008e83  call    cs:__imp_SetLastError
0x140008e89  jmp     loc_140008FC0
0x140008e8e  mov     [rax+8], rbx
0x140008e92  mov     [rax], rbx
0x140008e95  call    cs:__imp_GetCurrentThread
0x140008e9b  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x140008e9f  xor     r8d, r8d; OpenAsSelf
0x140008ea2  mov     rcx, rax; ThreadHandle
0x140008ea5  mov     edx, 2000Ch; DesiredAccess
0x140008eaa  call    cs:__imp_OpenThreadToken
0x140008eb0  test    eax, eax
0x140008eb2  jnz     short loc_140008ECD
0x140008eb4  call    cs:__imp_GetLastError
0x140008eba  cmp     eax, 3F0h
0x140008ebf  jnz     loc_140008FB8
0x140008ec5  xor     ecx, ecx; dwErrCode
0x140008ec7  call    cs:__imp_SetLastError
0x140008ecd  lea     rax, [rbp+3Fh+var_60]
0x140008ed1  xor     r9d, r9d; void *
0x140008ed4  xor     r8d, r8d; void *
0x140008ed7  mov     [rsp+0C0h+var_A0], rax; struct _SP_IDS **
0x140008edc  mov     rdx, rdi; void *
0x140008edf  mov     rcx, rsi; void *
0x140008ee2  call    ?SiGetDriveIdsCallback@@YAHPEAX000PEAPEAU_SP_IDS@@@Z; SiGetDriveIdsCallback(void *,void *,void *,void *,_SP_IDS * *)
0x140008ee7  test    eax, eax
0x140008ee9  jz      loc_140008FB8
0x140008eef  lea     rax, ?SiGetDriveCallback@@YAHPEAX000PEAU_GUID@@PEAPEAU_SU_OBJECT@@@Z; SiGetDriveCallback(void *,void *,void *,void *,_GUID *,_SU_OBJECT * *)
0x140008ef6  mov     [rbp+3Fh+var_48], rsi
0x140008efa  lea     rcx, [rbp+3Fh+hMem]; struct _SP_CONTROL_INFO **
0x140008efe  mov     [rbp+3Fh+var_50], rax
0x140008f02  mov     [rbp+3Fh+var_40], rdi
0x140008f06  mov     [rbp+3Fh+var_38], 0
0x140008f0e  mov     [rbp+3Fh+var_30], 0
0x140008f16  mov     [rbp+3Fh+var_28], rbx
0x140008f1a  call    ?SuGetControl@@YAHPEAPEAU_SP_CONTROL_INFO@@@Z; SuGetControl(_SP_CONTROL_INFO * *)
0x140008f1f  mov     r14, [rbp+3Fh+hMem]
0x140008f23  test    eax, eax
0x140008f25  jz      short loc_140008FA5
0x140008f27  cmp     byte ptr [r14+2Eh], 0
0x140008f2c  jnz     short loc_140008F78
0x140008f2e  lea     r8, ?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x140008f35  lea     rdx, [rbp+3Fh+CriticalSection]; pv
0x140008f39  lea     rcx, ?SiFindFirstCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140008f40  call    cs:__imp_CreateThreadpoolWork
0x140008f46  mov     rdi, rax
0x140008f49  test    rax, rax
0x140008f4c  jz      short loc_140008FA5
0x140008f4e  mov     rcx, [rbp+3Fh+var_60]
0x140008f52  xor     esi, esi
0x140008f54  cmp     [rcx], esi
0x140008f56  jbe     short loc_140008F6B
0x140008f58  mov     rcx, rdi; pwk
0x140008f5b  call    cs:__imp_SubmitThreadpoolWork
0x140008f61  mov     rcx, [rbp+3Fh+var_60]
0x140008f65  inc     esi
0x140008f67  cmp     esi, [rcx]
0x140008f69  jb      short loc_140008F58
0x140008f6b  xor     edx, edx; fCancelPendingCallbacks
0x140008f6d  mov     rcx, rdi; pwk
0x140008f70  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x140008f76  jmp     short loc_140008F83
0x140008f78  xor     edi, edi
0x140008f7a  lea     rcx, [rbp+3Fh+CriticalSection]; lpCriticalSection
0x140008f7e  call    ?Callback@SI_GET_CONTEXT@@QEAAXXZ; SI_GET_CONTEXT::Callback(void)
0x140008f83  mov     rdx, r12; struct _SU_OBJECT **
0x140008f86  mov     rcx, rbx; void *
0x140008f89  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x140008f8e  test    eax, eax
0x140008f90  jz      short loc_140008F97
0x140008f92  mov     r15, rbx
0x140008f95  xor     ebx, ebx
0x140008f97  test    rdi, rdi
0x140008f9a  jz      short loc_140008FA5
0x140008f9c  mov     rcx, rdi; pwk
0x140008f9f  call    cs:__imp_CloseThreadpoolWork
0x140008fa5  test    r14, r14
0x140008fa8  jz      short loc_140008FB3
0x140008faa  mov     rcx, r14; hMem
0x140008fad  call    cs:__imp_LocalFree
0x140008fb3  test    rbx, rbx
0x140008fb6  jz      short loc_140008FC0
0x140008fb8  mov     rcx, rbx; hMem
0x140008fbb  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x140008fc0  lea     rcx, [rbp+3Fh+CriticalSection]; this
0x140008fc4  call    ??1SI_GET_CONTEXT@@QEAA@XZ; SI_GET_CONTEXT::~SI_GET_CONTEXT(void)
0x140008fc9  lea     r11, [rsp+0C0h+var_20]
0x140008fd1  mov     rax, r15
0x140008fd4  mov     rbx, [r11+30h]
0x140008fd8  mov     rsi, [r11+40h]
0x140008fdc  mov     rsp, r11
0x140008fdf  pop     r15
0x140008fe1  pop     r14
0x140008fe3  pop     r12
0x140008fe5  pop     rdi
0x140008fe6  pop     rbp
0x140008fe7  retn
```
