# WorkQueue::Start(void)

- ea: `0x1800639a0`
- end: `0x180063b4e`
- name: `?Start@WorkQueue@@QEAAJXZ`
- size: `430`
- prototype: `__int64 __fastcall(WorkQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800303ec`

## callees

- `0x180021b9c`
- `0x1800639a0`
- `0x180073520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800639b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800639b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063abe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063aec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800639c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800639c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800639e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x1800639e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180063b08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180063b08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180063ab0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180063ab0`

## pseudocode

```c
__int64 __fastcall WorkQueue::Start(WorkQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 v3; // r8
  PTP_POOL *v4; // rsi
  PTP_POOL Threadpool; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct _TP_CLEANUP_GROUP *v7; // rcx
  PTP_CLEANUP_GROUP v8; // rdi
  char *v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  signed int LastError; // eax
  __int64 v14; // r9
  signed int v15; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 26) )
  {
    v11 = -2147418113;
    v14 = 82;
LABEL_17:
    Log_HREvent_3(v11, 0, v3, v14);
    goto LABEL_13;
  }
  v4 = (PTP_POOL *)((char *)this + 112);
  Threadpool = CreateThreadpool(0);
  if ( Threadpool == *((PTP_POOL *)this + 14) )
  {
    Threadpool = *v4;
  }
  else
  {
    tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::_Delete((char *)this + 112);
    *v4 = Threadpool;
  }
  if ( !Threadpool )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v14 = 86;
    goto LABEL_17;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  v7 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 25);
  v8 = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup == v7 )
  {
    v8 = (PTP_CLEANUP_GROUP)*((_QWORD *)this + 25);
  }
  else
  {
    if ( v7 )
      CloseThreadpoolCleanupGroup(v7);
    *((_QWORD *)this + 25) = v8;
  }
  if ( !v8 )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    v14 = 89;
    goto LABEL_17;
  }
  v9 = (char *)this + 120;
  if ( (WorkQueue *)((char *)this + 120) == *((WorkQueue **)this + 24) )
    v9 = (char *)*((_QWORD *)this + 24);
  else
    *((_QWORD *)this + 24) = v9;
  *(_DWORD *)v9 = 3;
  *((_DWORD *)v9 + 15) = 1;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  *((_QWORD *)v9 + 3) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *((_QWORD *)v9 + 6) = 0;
  *((_DWORD *)v9 + 14) = 0;
  *((_DWORD *)v9 + 16) = 72;
  v10 = *((_QWORD *)this + 24);
  *(_QWORD *)(v10 + 16) = *((_QWORD *)this + 25);
  *(_QWORD *)(v10 + 24) = _CancelCallback;
  *(_QWORD *)(*((_QWORD *)this + 24) + 8LL) = *v4;
  SetThreadpoolThreadMaximum(*v4, 1u);
  *((_DWORD *)this + 26) = 1;
  v11 = 0;
LABEL_13:
  LeaveCriticalSection(v1);
  return v11;
}

```

## disassembly

```asm
0x1800639a0  push    rbx
0x1800639a2  push    rbp
0x1800639a3  push    rsi
0x1800639a4  push    rdi
0x1800639a5  sub     rsp, 38h
0x1800639a9  lea     rbp, [rcx+40h]
0x1800639ad  mov     rbx, rcx
0x1800639b0  mov     rcx, rbp; lpCriticalSection
0x1800639b3  call    cs:__imp_EnterCriticalSection
0x1800639b9  cmp     dword ptr [rbx+68h], 0
0x1800639bd  jnz     loc_180063B1B
0x1800639c3  xor     ecx, ecx; reserved
0x1800639c5  lea     rsi, [rbx+70h]
0x1800639c9  call    cs:__imp_CreateThreadpool
0x1800639cf  mov     rdi, rax
0x1800639d2  cmp     rax, [rsi]
0x1800639d5  jnz     loc_180063B28
0x1800639db  mov     rdi, [rsi]
0x1800639de  test    rdi, rdi
0x1800639e1  jz      loc_180063ACF
0x1800639e7  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800639ed  mov     rcx, [rbx+0C8h]; ptpcg
0x1800639f4  mov     rdi, rax
0x1800639f7  cmp     rax, rcx
0x1800639fa  jz      loc_180063B13
0x180063a00  test    rcx, rcx
0x180063a03  jnz     loc_180063B08
0x180063a09  mov     [rbx+0C8h], rdi
0x180063a10  test    rdi, rdi
0x180063a13  jz      loc_180063AEC
0x180063a19  mov     rcx, [rbx+0C0h]
0x180063a20  lea     rax, [rbx+78h]
0x180063a24  cmp     rax, rcx
0x180063a27  jz      loc_180063B00
0x180063a2d  mov     [rbx+0C0h], rax
0x180063a34  mov     dword ptr [rax], 3
0x180063a3a  mov     edi, 1
0x180063a3f  mov     [rax+3Ch], edi
0x180063a42  mov     qword ptr [rax+8], 0
0x180063a4a  mov     qword ptr [rax+10h], 0
0x180063a52  mov     qword ptr [rax+18h], 0
0x180063a5a  mov     qword ptr [rax+20h], 0
0x180063a62  mov     qword ptr [rax+28h], 0
0x180063a6a  mov     qword ptr [rax+30h], 0
0x180063a72  mov     dword ptr [rax+38h], 0
0x180063a79  mov     dword ptr [rax+40h], 48h ; 'H'
0x180063a80  mov     rdx, [rbx+0C0h]
0x180063a87  mov     rax, [rbx+0C8h]
0x180063a8e  mov     [rdx+10h], rax
0x180063a92  lea     rax, ?_CancelCallback@@YAXPEAX0@Z; _CancelCallback(void *,void *)
0x180063a99  mov     [rdx+18h], rax
0x180063a9d  mov     rdx, [rbx+0C0h]
0x180063aa4  mov     rax, [rsi]
0x180063aa7  mov     [rdx+8], rax
0x180063aab  mov     edx, edi; cthrdMost
0x180063aad  mov     rcx, [rsi]; ptpp
0x180063ab0  call    cs:__imp_SetThreadpoolThreadMaximum
0x180063ab6  mov     [rbx+68h], edi
0x180063ab9  xor     ebx, ebx
0x180063abb  mov     rcx, rbp; lpCriticalSection
0x180063abe  call    cs:__imp_LeaveCriticalSection
0x180063ac4  mov     eax, ebx
0x180063ac6  add     rsp, 38h
0x180063aca  pop     rdi
0x180063acb  pop     rsi
0x180063acc  pop     rbp
0x180063acd  pop     rbx
0x180063ace  retn
0x180063acf  call    cs:__imp_GetLastError
0x180063ad5  mov     ebx, eax
0x180063ad7  test    eax, eax
0x180063ad9  jg      short loc_180063B38
0x180063adb  mov     r9d, 56h ; 'V'
0x180063ae1  xor     edx, edx
0x180063ae3  mov     ecx, ebx
0x180063ae5  call    Log_HREvent_3
0x180063aea  jmp     short loc_180063ABB
0x180063aec  call    cs:__imp_GetLastError
0x180063af2  mov     ebx, eax
0x180063af4  test    eax, eax
0x180063af6  jg      short loc_180063B43
0x180063af8  mov     r9d, 59h ; 'Y'
0x180063afe  jmp     short loc_180063AE1
0x180063b00  mov     rax, rcx
0x180063b03  jmp     loc_180063A34
0x180063b08  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180063b0e  jmp     loc_180063A09
0x180063b13  mov     rdi, rcx
0x180063b16  jmp     loc_180063A10
0x180063b1b  mov     ebx, 8000FFFFh
0x180063b20  mov     r9d, 52h ; 'R'
0x180063b26  jmp     short loc_180063AE1
0x180063b28  mov     rcx, rsi
0x180063b2b  call    ?_Delete@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::_Delete(void)
0x180063b30  mov     [rsi], rdi
0x180063b33  jmp     loc_1800639DE
0x180063b38  movzx   ebx, ax
0x180063b3b  or      ebx, 80070000h
0x180063b41  jmp     short loc_180063ADB
0x180063b43  movzx   ebx, ax
0x180063b46  or      ebx, 80070000h
0x180063b4c  jmp     short loc_180063AF8
```
