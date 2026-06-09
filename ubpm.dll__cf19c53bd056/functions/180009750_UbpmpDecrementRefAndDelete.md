# UbpmpDecrementRefAndDelete

- ea: `0x180009750`
- end: `0x180009c0c`
- name: `UbpmpDecrementRefAndDelete`
- size: `1212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180002b54`
- `0x180003050`
- `0x180004860`
- `0x180007990`
- `0x180008f30`
- `0x180009c20`
- `0x180009f50`
- `0x18000a014`
- `0x18000a570`
- `0x18000b440`
- `0x18000b6d0`
- `0x18000c650`
- `0x180021060`
- `0x180029590`

## callees

- `0x180009750`
- `0x18000c248`
- `0x180019d90`
- `0x18002046c`
- `0x180030cec`
- `0x180035c10`
- `0x18003c454`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000991f`
- `ntdll!RtlFreeHeap` at `0x180009940`
- `ntdll!RtlFreeHeap` at `0x18000998f`
- `ntdll!RtlFreeHeap` at `0x1800099b0`
- `ntdll!RtlFreeHeap` at `0x1800099d1`
- `ntdll!RtlFreeHeap` at `0x1800099f2`
- `ntdll!RtlFreeHeap` at `0x180009a13`
- `ntdll!RtlFreeHeap` at `0x180009a34`
- `ntdll!RtlFreeHeap` at `0x180009a55`
- `ntdll!RtlFreeHeap` at `0x180009a6d`
- `ntdll!RtlFreeHeap` at `0x18000991f`
- `ntdll!RtlFreeHeap` at `0x180009940`
- `ntdll!RtlFreeHeap` at `0x18000998f`
- `ntdll!RtlFreeHeap` at `0x1800099b0`
- `ntdll!RtlFreeHeap` at `0x1800099d1`
- `ntdll!RtlFreeHeap` at `0x1800099f2`
- `ntdll!RtlFreeHeap` at `0x180009a13`
- `ntdll!RtlFreeHeap` at `0x180009a34`
- `ntdll!RtlFreeHeap` at `0x180009a55`
- `ntdll!RtlFreeHeap` at `0x180009a6d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000976d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009899`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000976d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009899`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800097b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000982b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800098c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800097b6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000982b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800098c3`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180009863`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180009863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000989f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000989f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000986d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000986d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000983d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000984f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000983d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000984f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bf7`
- `profapi!__imp_UnloadProfileBasic` at `0x180009bb2`
- `profapi!__imp_UnloadProfileBasic` at `0x180009bb2`

## pseudocode

```c
char __fastcall UbpmpDecrementRefAndDelete(__int64 *a1, int a2)
{
  __int64 v2; // rbx
  int v3; // edi
  signed __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  _QWORD *v8; // rdx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  DWORD LastError; // eax
  _DWORD *v13; // r14
  bool v14; // zf
  void *v15; // rcx
  void *v16; // rcx
  PSID v17; // r8
  void *v18; // r8
  _QWORD *v19; // r15
  _QWORD *v20; // r15
  void *v21; // r8
  void *v22; // r8
  void *v23; // r8
  void *v24; // r8
  void *v25; // r8
  void *v26; // r8
  void *v27; // r8
  _QWORD *v28; // rax
  _QWORD *v29; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // r8
  _QWORD *v32; // rax
  _QWORD *v33; // rbp
  __int64 v34; // rcx
  int v35; // eax
  _QWORD *v37; // [rsp+60h] [rbp+8h] BYREF

  v2 = *a1;
  v3 = a2;
  if ( a2 )
  {
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    dword_18004CF18 = GetCurrentThreadId();
  }
  v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v2 + 96), 0xFFFFFFFFFFFFFFFFuLL);
  if ( v5 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids);
    v6 = *(_QWORD *)(v2 + 8);
    v7 = (_QWORD *)(v2 + 8);
    if ( *(_QWORD *)(v6 + 8) == v2 + 8 )
    {
      v8 = *(_QWORD **)(v2 + 16);
      if ( (_QWORD *)*v8 == v7 )
      {
        *v8 = v6;
        *(_QWORD *)(v6 + 8) = v8;
        *(_QWORD *)(v2 + 16) = v2 + 8;
        *v7 = v7;
        if ( v3 )
        {
          dword_18004CF18 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
          v3 = 0;
        }
        v9 = *(void **)(v2 + 48);
        if ( v9 )
          CloseHandle(v9);
        v10 = *(void **)(v2 + 232);
        if ( v10 )
          CloseHandle(v10);
        v11 = *(void **)(v2 + 24);
        if ( v11 )
        {
          if ( !TerminateProcess(v11, 0x42Bu) )
          {
            LastError = GetLastError();
            if ( LastError != 5
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                80,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                *(unsigned int *)(v2 + 32),
                LastError);
            }
          }
          CloseHandle(*(HANDLE *)(v2 + 24));
        }
        v13 = *(_DWORD **)(v2 + 416);
        if ( v13 )
        {
          RtlAcquireSRWLockExclusive(&g_TaskHostJobObjectLock);
          dword_18004CF88 = GetCurrentThreadId();
          v14 = (*v13)-- == 1;
          if ( v14 && !v13[1] )
            DestroyJobObjectContext(v13);
          dword_18004CF88 = 0;
          RtlReleaseSRWLockExclusive(&g_TaskHostJobObjectLock);
        }
        if ( *(_QWORD *)(v2 + 240) )
        {
          if ( *(_QWORD *)(v2 + 248) )
          {
            v35 = UnloadProfileBasic();
            if ( v35 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_L(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                81,
                WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                (unsigned int)v35);
          }
        }
        v15 = *(void **)(v2 + 256);
        if ( v15 )
          CloseHandle(v15);
        v16 = *(void **)(v2 + 248);
        if ( v16 )
          CloseHandle(v16);
        v17 = *(PSID *)(v2 + 176);
        if ( v17 != pSid && v17 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
        v18 = *(void **)(v2 + 184);
        if ( v18 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        *(_WORD *)(v2 + 196) = 0;
        v19 = *(_QWORD **)(v2 + 216);
        if ( v19 == (_QWORD *)(v2 + 216) )
        {
LABEL_34:
          v20 = *(_QWORD **)(v2 + 200);
          while ( v20 != (_QWORD *)(v2 + 200) )
          {
            v28 = v20 - 2;
            v20 = (_QWORD *)*v20;
            v37 = v28;
            UbpmpDecrementTaskRefAndDelete(&v37);
          }
          v21 = *(void **)(v2 + 360);
          if ( v21 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
          v22 = *(void **)(v2 + 376);
          if ( v22 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
          v23 = *(void **)(v2 + 344);
          if ( v23 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
          v24 = *(void **)(v2 + 144);
          if ( v24 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
          v25 = *(void **)(v2 + 152);
          if ( v25 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
          v26 = *(void **)(v2 + 160);
          if ( v26 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26);
          v27 = *(void **)(v2 + 400);
          if ( v27 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
          LOBYTE(v5) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v2);
          *a1 = 0;
          goto LABEL_4;
        }
        while ( 1 )
        {
          v29 = (_QWORD *)*v19;
          if ( *(_QWORD **)(*v19 + 8LL) != v19 )
            break;
          v30 = (_QWORD *)v19[1];
          v31 = v19 + 1;
          if ( (_QWORD *)*v30 != v19 )
            break;
          v32 = v19;
          *v30 = v29;
          v29[1] = v30;
          v33 = v19;
          v19 = v29;
          *v31 = v32;
          *v32 = v32;
          v34 = v32[2];
          if ( v34 )
          {
            UBPM_MIDL_user_free(*(_QWORD *)(v34 + 16));
            UBPM_MIDL_user_free(*(_QWORD *)(v33[2] + 24LL));
            UBPM_MIDL_user_free(*(_QWORD *)(v33[2] + 8LL));
            UBPM_MIDL_user_free(v33[2]);
          }
          if ( v33[3] )
            UbpmpDecrementTaskRefAndDelete(v33 + 3);
          UBPM_MIDL_user_free(v33);
          if ( v19 == (_QWORD *)(v2 + 216) )
            goto LABEL_34;
        }
      }
    }
    __fastfail(3u);
  }
LABEL_4:
  if ( v3 )
  {
    dword_18004CF18 = 0;
    LOBYTE(v5) = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
  }
  return v5;
}

```

## disassembly

```asm
0x180009750  push    rbx
0x180009752  push    rsi
0x180009753  push    rdi
0x180009754  push    r12
0x180009756  sub     rsp, 38h
0x18000975a  mov     rbx, [rcx]
0x18000975d  mov     edi, edx
0x18000975f  mov     rsi, rcx
0x180009762  test    edx, edx
0x180009764  jz      short loc_18000977F
0x180009766  lea     rcx, g_TaskHostContextListLock
0x18000976d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009773  call    cs:__imp_GetCurrentThreadId
0x180009779  mov     cs:dword_18004CF18, eax
0x18000977f  mov     [rsp+58h+arg_10], rbp
0x180009784  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000978b  mov     [rsp+58h+arg_18], r14
0x180009790  mov     [rsp+58h+var_28], r15
0x180009795  lock xadd [rbx+60h], rax
0x18000979b  xor     r12d, r12d
0x18000979e  cmp     rax, 1
0x1800097a2  jz      short loc_1800097D5
0x1800097a4  test    edi, edi
0x1800097a6  jz      short loc_1800097BC
0x1800097a8  lea     rcx, g_TaskHostContextListLock
0x1800097af  mov     cs:dword_18004CF18, r12d
0x1800097b6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800097bc  mov     r15, [rsp+58h+var_28]
0x1800097c1  mov     r14, [rsp+58h+arg_18]
0x1800097c6  mov     rbp, [rsp+58h+arg_10]
0x1800097cb  add     rsp, 38h
0x1800097cf  pop     r12
0x1800097d1  pop     rdi
0x1800097d2  pop     rsi
0x1800097d3  pop     rbx
0x1800097d4  retn
0x1800097d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097dc  lea     rbp, WPP_GLOBAL_Control
0x1800097e3  cmp     rcx, rbp
0x1800097e6  jnz     loc_180009A7B
0x1800097ec  mov     rcx, [rbx+8]
0x1800097f0  lea     rax, [rbx+8]
0x1800097f4  cmp     [rcx+8], rax
0x1800097f8  jnz     loc_180009AB9
0x1800097fe  mov     rdx, [rax+8]
0x180009802  cmp     [rdx], rax
0x180009805  jnz     loc_180009AB9
0x18000980b  mov     [rdx], rcx
0x18000980e  mov     [rcx+8], rdx
0x180009812  mov     [rax+8], rax
0x180009816  mov     [rax], rax
0x180009819  test    edi, edi
0x18000981b  jz      short loc_180009834
0x18000981d  lea     rcx, g_TaskHostContextListLock
0x180009824  mov     cs:dword_18004CF18, r12d
0x18000982b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009831  mov     edi, r12d
0x180009834  mov     rcx, [rbx+30h]; hObject
0x180009838  test    rcx, rcx
0x18000983b  jz      short loc_180009843
0x18000983d  call    cs:__imp_CloseHandle
0x180009843  mov     rcx, [rbx+0E8h]; hObject
0x18000984a  test    rcx, rcx
0x18000984d  jz      short loc_180009855
0x18000984f  call    cs:__imp_CloseHandle
0x180009855  mov     rcx, [rbx+18h]; hProcess
0x180009859  test    rcx, rcx
0x18000985c  jz      short loc_180009886
0x18000985e  mov     edx, 42Bh; uExitCode
0x180009863  call    cs:__imp_TerminateProcess
0x180009869  test    eax, eax
0x18000986b  jnz     short loc_18000987C
0x18000986d  call    cs:__imp_GetLastError
0x180009873  cmp     eax, 5
0x180009876  jnz     loc_180009B66
0x18000987c  mov     rcx, [rbx+18h]; hObject
0x180009880  call    cs:__imp_CloseHandle
0x180009886  mov     r14, [rbx+1A0h]
0x18000988d  test    r14, r14
0x180009890  jz      short loc_1800098C9
0x180009892  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x180009899  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000989f  call    cs:__imp_GetCurrentThreadId
0x1800098a5  mov     cs:dword_18004CF88, eax
0x1800098ab  sub     dword ptr [r14], 1
0x1800098af  jz      loc_180009AA2
0x1800098b5  lea     rcx, ?g_TaskHostJobObjectLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TaskHostJobObjectLock
0x1800098bc  mov     cs:dword_18004CF88, r12d
0x1800098c3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800098c9  mov     rdx, [rbx+0F0h]
0x1800098d0  test    rdx, rdx
0x1800098d3  jnz     loc_180009BA2
0x1800098d9  mov     rcx, [rbx+100h]; hObject
0x1800098e0  test    rcx, rcx
0x1800098e3  jz      short loc_1800098EB
0x1800098e5  call    cs:__imp_CloseHandle
0x1800098eb  mov     rcx, [rbx+0F8h]; hObject
0x1800098f2  test    rcx, rcx
0x1800098f5  jnz     loc_180009BF7
0x1800098fb  mov     r8, [rbx+0B0h]; P
0x180009902  cmp     r8, cs:pSid
0x180009909  jz      short loc_180009925
0x18000990b  test    r8, r8
0x18000990e  jz      short loc_180009925
0x180009910  mov     rcx, gs:60h
0x180009919  xor     edx, edx; Flags
0x18000991b  mov     rcx, [rcx+30h]; HeapHandle
0x18000991f  call    cs:__imp_RtlFreeHeap
0x180009925  mov     r8, [rbx+0B8h]; P
0x18000992c  test    r8, r8
0x18000992f  jz      short loc_180009946
0x180009931  mov     rcx, gs:60h
0x18000993a  xor     edx, edx; Flags
0x18000993c  mov     rcx, [rcx+30h]; HeapHandle
0x180009940  call    cs:__imp_RtlFreeHeap
0x180009946  lea     r14, [rbx+0D8h]
0x18000994d  mov     [rbx+0C4h], r12w
0x180009955  mov     r15, [r14]
0x180009958  cmp     r15, r14
0x18000995b  jnz     loc_180009AE1
0x180009961  lea     r14, [rbx+0C8h]
0x180009968  mov     r15, [r14]
0x18000996b  cmp     r15, r14
0x18000996e  jnz     loc_180009AC0
0x180009974  mov     r8, [rbx+168h]; P
0x18000997b  test    r8, r8
0x18000997e  jz      short loc_180009995
0x180009980  mov     rcx, gs:60h
0x180009989  xor     edx, edx; Flags
0x18000998b  mov     rcx, [rcx+30h]; HeapHandle
0x18000998f  call    cs:__imp_RtlFreeHeap
0x180009995  mov     r8, [rbx+178h]; P
0x18000999c  test    r8, r8
0x18000999f  jz      short loc_1800099B6
0x1800099a1  mov     rcx, gs:60h
0x1800099aa  xor     edx, edx; Flags
0x1800099ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800099b0  call    cs:__imp_RtlFreeHeap
0x1800099b6  mov     r8, [rbx+158h]; P
0x1800099bd  test    r8, r8
0x1800099c0  jz      short loc_1800099D7
0x1800099c2  mov     rcx, gs:60h
0x1800099cb  xor     edx, edx; Flags
0x1800099cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800099d1  call    cs:__imp_RtlFreeHeap
0x1800099d7  mov     r8, [rbx+90h]; P
0x1800099de  test    r8, r8
0x1800099e1  jz      short loc_1800099F8
0x1800099e3  mov     rcx, gs:60h
0x1800099ec  xor     edx, edx; Flags
0x1800099ee  mov     rcx, [rcx+30h]; HeapHandle
0x1800099f2  call    cs:__imp_RtlFreeHeap
0x1800099f8  mov     r8, [rbx+98h]; P
0x1800099ff  test    r8, r8
0x180009a02  jz      short loc_180009A19
0x180009a04  mov     rcx, gs:60h
0x180009a0d  xor     edx, edx; Flags
0x180009a0f  mov     rcx, [rcx+30h]; HeapHandle
0x180009a13  call    cs:__imp_RtlFreeHeap
0x180009a19  mov     r8, [rbx+0A0h]; P
0x180009a20  test    r8, r8
0x180009a23  jz      short loc_180009A3A
0x180009a25  mov     rcx, gs:60h
0x180009a2e  xor     edx, edx; Flags
0x180009a30  mov     rcx, [rcx+30h]; HeapHandle
0x180009a34  call    cs:__imp_RtlFreeHeap
0x180009a3a  mov     r8, [rbx+190h]; P
0x180009a41  test    r8, r8
0x180009a44  jz      short loc_180009A5B
0x180009a46  mov     rcx, gs:60h
0x180009a4f  xor     edx, edx; Flags
0x180009a51  mov     rcx, [rcx+30h]; HeapHandle
0x180009a55  call    cs:__imp_RtlFreeHeap
0x180009a5b  mov     rcx, gs:60h
0x180009a64  mov     r8, rbx; P
0x180009a67  xor     edx, edx; Flags
0x180009a69  mov     rcx, [rcx+30h]; HeapHandle
0x180009a6d  call    cs:__imp_RtlFreeHeap
0x180009a73  mov     [rsi], r12
0x180009a76  jmp     loc_1800097A4
0x180009a7b  test    byte ptr [rcx+1Ch], 80h
0x180009a7f  jz      loc_1800097EC
0x180009a85  mov     rcx, [rcx+10h]
0x180009a89  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180009a90  mov     edx, 4Fh ; 'O'
0x180009a95  mov     r9, rbx
0x180009a98  call    WPP_SF_q
0x180009a9d  jmp     loc_1800097EC
0x180009aa2  cmp     [r14+4], r12d
0x180009aa6  jnz     loc_1800098B5
0x180009aac  mov     rcx, r14
0x180009aaf  call    DestroyJobObjectContext
0x180009ab4  jmp     loc_1800098B5
0x180009ab9  mov     ecx, 3
0x180009abe  int     29h; Win8: RtlFailFast(ecx)
0x180009ac0  lea     rax, [r15-10h]
0x180009ac4  mov     r15, [r15]
0x180009ac7  lea     rcx, [rsp+58h+arg_0]
0x180009acc  mov     [rsp+58h+arg_0], rax
0x180009ad1  call    UbpmpDecrementTaskRefAndDelete
0x180009ad6  cmp     r15, r14
0x180009ad9  jz      loc_180009974
0x180009adf  jmp     short loc_180009AC0
0x180009ae1  mov     rcx, [r15]
0x180009ae4  cmp     [rcx+8], r15
0x180009ae8  jnz     short loc_180009AB9
0x180009aea  mov     rdx, [r15+8]
0x180009aee  lea     r8, [r15+8]
0x180009af2  cmp     [rdx], r15
0x180009af5  jnz     short loc_180009AB9
0x180009af7  mov     rax, r15
0x180009afa  mov     [rdx], rcx
0x180009afd  mov     [rcx+8], rdx
0x180009b01  mov     rbp, r15
0x180009b04  mov     r15, rcx
0x180009b07  mov     [r8], rax
0x180009b0a  mov     [rax], rax
0x180009b0d  mov     rcx, [rax+10h]
0x180009b11  test    rcx, rcx
0x180009b14  jz      short loc_180009B42
0x180009b16  mov     rcx, [rcx+10h]
0x180009b1a  call    UBPM_MIDL_user_free
0x180009b1f  mov     rcx, [rbp+10h]
0x180009b23  mov     rcx, [rcx+18h]
0x180009b27  call    UBPM_MIDL_user_free
0x180009b2c  mov     rcx, [rbp+10h]
0x180009b30  mov     rcx, [rcx+8]
0x180009b34  call    UBPM_MIDL_user_free
0x180009b39  mov     rcx, [rbp+10h]
0x180009b3d  call    UBPM_MIDL_user_free
0x180009b42  cmp     [rbp+18h], r12
0x180009b46  lea     rcx, [rbp+18h]
0x180009b4a  jnz     loc_180009C02
0x180009b50  mov     rcx, rbp
0x180009b53  call    UBPM_MIDL_user_free
0x180009b58  cmp     r15, r14
0x180009b5b  jz      loc_180009961
0x180009b61  jmp     loc_180009AE1
0x180009b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b6d  cmp     rcx, rbp
0x180009b70  jz      loc_18000987C
0x180009b76  test    byte ptr [rcx+1Ch], 2
0x180009b7a  jz      loc_18000987C
0x180009b80  mov     r9d, [rbx+20h]
0x180009b84  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180009b8b  mov     rcx, [rcx+10h]
0x180009b8f  mov     edx, 50h ; 'P'
0x180009b94  mov     [rsp+58h+var_38], eax
0x180009b98  call    WPP_SF_dd
0x180009b9d  jmp     loc_18000987C
0x180009ba2  mov     rcx, [rbx+0F8h]
0x180009ba9  test    rcx, rcx
0x180009bac  jz      loc_1800098D9
0x180009bb2  call    cs:__imp_UnloadProfileBasic
0x180009bb8  test    eax, eax
0x180009bba  jns     loc_1800098D9
0x180009bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bc7  cmp     rcx, rbp
0x180009bca  jz      loc_1800098D9
0x180009bd0  test    byte ptr [rcx+1Ch], 1
0x180009bd4  jz      loc_1800098D9
0x180009bda  mov     rcx, [rcx+10h]
0x180009bde  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180009be5  mov     edx, 51h ; 'Q'
0x180009bea  mov     r9d, eax
0x180009bed  call    WPP_SF_L
0x180009bf2  jmp     loc_1800098D9
0x180009bf7  call    cs:__imp_CloseHandle
0x180009bfd  jmp     loc_1800098FB
0x180009c02  call    UbpmpDecrementTaskRefAndDelete
0x180009c07  jmp     loc_180009B50
```
