# THREAD_POOL_DATA::InitializeThreadPool(THREAD_POOL_CONFIG *)

- ea: `0x1800017a0`
- end: `0x180001864`
- name: `?InitializeThreadPool@THREAD_POOL_DATA@@QEAAHPEAUTHREAD_POOL_CONFIG@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(THREAD_POOL_DATA *__hidden this, struct THREAD_POOL_CONFIG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800037c0`

## callees

- `0x1800017a0`
- `0x180001870`
- `0x180002ab8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000184c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000184c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180001801`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180001801`

## pseudocode

```c
__int64 __fastcall THREAD_POOL_DATA::InitializeThreadPool(THREAD_POOL_DATA *this, struct THREAD_POOL_CONFIG *a2)
{
  int v3; // eax
  struct THREAD_POOL *v4; // rdx
  HANDLE IoCompletionPort; // rax
  unsigned int (*v6)(void *); // rdx
  int v7; // eax
  unsigned int v8; // edi
  void *v10; // rcx

  *((_OWORD *)this + 3) = *(_OWORD *)a2;
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 4);
  v3 = *((_DWORD *)a2 + 20);
  v4 = (struct THREAD_POOL *)*((_QWORD *)this + 5);
  *((_DWORD *)this + 32) = v3;
  if ( (int)THREAD_MANAGER::CreateThreadManager((struct THREAD_MANAGER **)this + 4, v4, this) >= 0
    && (IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, *((_DWORD *)this + 18)),
        (*((_QWORD *)this + 1) = IoCompletionPort) != 0) )
  {
    v7 = *((_DWORD *)this + 21);
    if ( v7 )
      *((_DWORD *)this + 12) = v7;
    v8 = 0;
    if ( !*((_DWORD *)this + 12) )
      *((_DWORD *)this + 12) = 1;
    do
    {
      THREAD_MANAGER::CreateThread(*((THREAD_MANAGER **)this + 4), v6, this);
      ++v8;
    }
    while ( v8 < *((_DWORD *)this + 12) );
    return 1;
  }
  else
  {
    v10 = (void *)*((_QWORD *)this + 1);
    if ( v10 )
    {
      CloseHandle(v10);
      *((_QWORD *)this + 1) = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800017a0  push    rbx
0x1800017a2  push    rsi
0x1800017a3  push    rdi
0x1800017a4  push    r14
0x1800017a6  sub     rsp, 28h
0x1800017aa  movups  xmm0, xmmword ptr [rdx]
0x1800017ad  mov     rbx, rcx
0x1800017b0  mov     r8, rcx; struct THREAD_POOL_DATA *
0x1800017b3  movups  xmmword ptr [rcx+30h], xmm0
0x1800017b7  movups  xmm1, xmmword ptr [rdx+10h]
0x1800017bb  movups  xmmword ptr [rcx+40h], xmm1
0x1800017bf  movups  xmm0, xmmword ptr [rdx+20h]
0x1800017c3  movups  xmmword ptr [rcx+50h], xmm0
0x1800017c7  movups  xmm1, xmmword ptr [rdx+30h]
0x1800017cb  movups  xmmword ptr [rcx+60h], xmm1
0x1800017cf  movups  xmm0, xmmword ptr [rdx+40h]
0x1800017d3  movups  xmmword ptr [rcx+70h], xmm0
0x1800017d7  mov     eax, [rdx+50h]
0x1800017da  mov     rdx, [rcx+28h]; struct THREAD_POOL *
0x1800017de  mov     [rcx+80h], eax
0x1800017e4  add     rcx, 20h ; ' '; struct THREAD_MANAGER **
0x1800017e8  call    ?CreateThreadManager@THREAD_MANAGER@@SAJPEAPEAV1@PEAVTHREAD_POOL@@PEAVTHREAD_POOL_DATA@@@Z; THREAD_MANAGER::CreateThreadManager(THREAD_MANAGER * *,THREAD_POOL *,THREAD_POOL_DATA *)
0x1800017ed  test    eax, eax
0x1800017ef  js      short loc_180001843
0x1800017f1  mov     r9d, [rbx+48h]; NumberOfConcurrentThreads
0x1800017f5  xor     r8d, r8d; CompletionKey
0x1800017f8  xor     edx, edx; ExistingCompletionPort
0x1800017fa  mov     rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180001801  call    cs:__imp_CreateIoCompletionPort
0x180001807  mov     [rbx+8], rax
0x18000180b  test    rax, rax
0x18000180e  jz      short loc_180001843
0x180001810  mov     eax, [rbx+54h]
0x180001813  test    eax, eax
0x180001815  jz      short loc_18000181A
0x180001817  mov     [rbx+30h], eax
0x18000181a  xor     edi, edi
0x18000181c  cmp     dword ptr [rbx+30h], 1
0x180001820  jnb     short loc_180001829
0x180001822  mov     dword ptr [rbx+30h], 1
0x180001829  mov     rcx, [rbx+20h]; this
0x18000182d  mov     r8, rbx; void *
0x180001830  call    ?CreateThread@THREAD_MANAGER@@QEAAHP6AKPEAX@Z0@Z; THREAD_MANAGER::CreateThread(ulong (*)(void *),void *)
0x180001835  inc     edi
0x180001837  cmp     edi, [rbx+30h]
0x18000183a  jb      short loc_180001829
0x18000183c  mov     eax, 1
0x180001841  jmp     short loc_18000185A
0x180001843  mov     rcx, [rbx+8]; hObject
0x180001847  test    rcx, rcx
0x18000184a  jz      short loc_180001858
0x18000184c  call    cs:__imp_CloseHandle
0x180001852  xor     edi, edi
0x180001854  mov     [rbx+8], rdi
0x180001858  xor     eax, eax
0x18000185a  add     rsp, 28h
0x18000185e  pop     r14
0x180001860  pop     rdi
0x180001861  pop     rsi
0x180001862  pop     rbx
0x180001863  retn
```
