# BaseClientNotifyHandler::TpCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180051160`
- end: `0x1800514b7`
- name: `?TpCallback@BaseClientNotifyHandler@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `855`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180051160`
- `0x1800703c0`
- `0x1800742ac`
- `0x1800c50aa`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005119d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005121f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005119d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005121f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800513ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800513ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180051379`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180051379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800513f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005124d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800513d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800513e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005124d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800513d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800513e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800511a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800511a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005136a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005145f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005136a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005145f`

## pseudocode

```c
void __fastcall BaseClientNotifyHandler::TpCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _LIST_ENTRY *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct _LIST_ENTRY *i; // rax
  struct _LIST_ENTRY *v9; // rsi
  PTP_WAIT *v10; // r12
  volatile signed __int32 *v11; // r15
  int v12; // r13d
  struct _LIST_ENTRY *Flink; // rbx
  int v14; // eax
  struct _LIST_ENTRY *Blink; // rbx
  int v16; // edi
  unsigned int *v17; // rdi
  unsigned int v18; // r14d
  __int64 j; // r8
  int v20; // eax
  __int64 v21; // r8
  signed __int32 v22; // eax
  signed int LastError; // eax
  __int64 v24; // r8
  bool v25; // sf
  struct _TP_WAIT *v26; // rcx
  int v27; // eax
  __int64 v28; // r8
  HLOCAL hMem[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v30[200]; // [rsp+40h] [rbp-C0h] BYREF

  EnterCriticalSection(&g_clientNotifyLock);
  if ( LODWORD(g_clientNotifyLock.OwningThread) != GetCurrentThreadId() )
    Log_AssertionEvent_8(v7, v6, 92);
  for ( i = g_adviseList.Flink; i != &g_adviseList; i = i->Flink )
  {
    v9 = i - 3;
    if ( &i[-3] == Context )
    {
      if ( i == (struct _LIST_ENTRY *)48 )
        break;
      v10 = (PTP_WAIT *)&v9[2];
      if ( !v9[2].Flink )
        break;
      v11 = (volatile signed __int32 *)&v9[4];
      _InterlockedIncrement((volatile signed __int32 *)&v9[4]);
      LeaveCriticalSection(&g_clientNotifyLock);
      if ( LODWORD(v9[4].Blink) && WaitResult != 258 )
      {
        EnterCriticalSection(&g_clientNotifyLock);
        v26 = *v10;
        hMem[0] = (HLOCAL)(-10000LL * LODWORD(v9[4].Blink));
        SetThreadpoolWait(v26, v9[2].Blink, (PFILETIME)hMem);
        _InterlockedDecrement(v11);
        break;
      }
      v12 = 0;
      hMem[0] = 0;
      EnterCriticalSection(&g_clientNotifyLock);
      if ( ((unsigned int (__fastcall *)(struct _LIST_ENTRY *))v9->Flink->Blink)(v9) )
      {
        Flink = v9->Flink[1].Flink;
        hMem[0] = 0;
        v14 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, HLOCAL *))Flink)(v9, hMem);
        Blink = v9->Blink;
        v16 = v14;
        if ( Blink )
          ((void (__fastcall *)(struct _LIST_ENTRY *))Blink->Flink->Blink)(v9->Blink);
        LeaveCriticalSection(&g_clientNotifyLock);
        if ( v16 < 0 )
          goto LABEL_40;
        v17 = (unsigned int *)hMem[0];
        if ( hMem[0] )
        {
          v18 = *((_DWORD *)hMem[0] + 1);
          if ( v18 <= 0xC8 )
          {
            memset_0(v30, 0, sizeof(v30));
            for ( j = 0; (unsigned int)j < v18; j = (unsigned int)(j + 1) )
              v30[j] = &v17[20 * j + 2];
            v20 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64, _QWORD *))Blink->Flink[1].Blink)(
                    Blink,
                    *v17,
                    j,
                    v30);
            if ( v20 < 0 )
              Log_UnistoreHREvent_7((unsigned int)v20, 0, v21, 293);
            v12 = 1;
            goto LABEL_21;
          }
LABEL_40:
          v27 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD))Blink->Flink[1].Blink)(Blink, 8, 0);
          if ( v27 < 0 )
            Log_UnistoreHREvent_7((unsigned int)v27, 0, v28, 272);
LABEL_21:
          ((void (__fastcall *)(struct _LIST_ENTRY *))Blink->Flink[1].Flink)(Blink);
          if ( hMem[0] )
LABEL_22:
            LocalFree(hMem[0]);
LABEL_23:
          EnterCriticalSection(&g_clientNotifyLock);
          v22 = _InterlockedDecrement(v11);
          if ( *v10 )
          {
            SetThreadpoolWait(*v10, v9[2].Blink, 0);
            if ( v12 && !SetEvent(v9[2].Blink) )
            {
              LastError = GetLastError();
              v25 = LastError < 0;
              if ( LastError > 0 )
              {
                LastError = (unsigned __int16)LastError | 0x80070000;
                v25 = LastError < 0;
              }
              if ( v25 )
                Log_UnistoreHREvent_7((unsigned int)LastError, 0, v24, 229);
            }
          }
          else if ( !v22 )
          {
            ((void (__fastcall *)(struct _LIST_ENTRY *, __int64))v9->Flink->Flink)(v9, 1);
          }
          break;
        }
        if ( !Blink )
          goto LABEL_23;
        ((void (__fastcall *)(struct _LIST_ENTRY *))Blink->Flink[1].Flink)(Blink);
      }
      else
      {
        LeaveCriticalSection(&g_clientNotifyLock);
      }
      if ( hMem[0] )
        goto LABEL_22;
      goto LABEL_23;
    }
  }
  LeaveCriticalSection(&g_clientNotifyLock);
}

```

## disassembly

```asm
0x180051160  push    rbp
0x180051162  push    rbx
0x180051163  push    rsi
0x180051164  push    rdi
0x180051165  push    r12
0x180051167  push    r13
0x180051169  push    r14
0x18005116b  push    r15
0x18005116d  lea     rbp, [rsp-598h]
0x180051175  sub     rsp, 698h
0x18005117c  mov     rax, cs:__security_cookie
0x180051183  xor     rax, rsp
0x180051186  mov     [rbp+5D0h+var_50], rax
0x18005118d  lea     r14, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_clientNotifyLock
0x180051194  mov     edi, r9d
0x180051197  mov     rcx, r14; lpCriticalSection
0x18005119a  mov     rbx, rdx
0x18005119d  call    cs:__imp_EnterCriticalSection
0x1800511a3  call    cs:__imp_GetCurrentThreadId
0x1800511a9  cmp     dword ptr cs:?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A.OwningThread, eax; utl::recursive_mutex g_clientNotifyLock ...
0x1800511af  jz      short loc_1800511BC
0x1800511b1  mov     r8d, 5Ch ; '\'
0x1800511b7  call    Log_AssertionEvent_8
0x1800511bc  mov     rax, cs:?g_adviseList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_adviseList
0x1800511c3  lea     rcx, ?g_adviseList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_adviseList
0x1800511ca  cmp     rax, rcx
0x1800511cd  jz      loc_180051383
0x1800511d3  lea     rsi, [rax-30h]
0x1800511d7  cmp     rsi, rbx
0x1800511da  jz      short loc_1800511E1
0x1800511dc  mov     rax, [rax]
0x1800511df  jmp     short loc_1800511C3
0x1800511e1  test    rsi, rsi
0x1800511e4  jz      loc_180051383
0x1800511ea  lea     r12, [rsi+20h]
0x1800511ee  cmp     qword ptr [r12], 0
0x1800511f3  jz      loc_180051383
0x1800511f9  lea     r15, [rsi+40h]
0x1800511fd  lock inc dword ptr [r15]
0x180051201  mov     rcx, r14; lpCriticalSection
0x180051204  call    cs:__imp_LeaveCriticalSection
0x18005120a  cmp     dword ptr [rsi+48h], 0
0x18005120e  ja      loc_180051424
0x180051214  xor     r13d, r13d
0x180051217  mov     rcx, r14; lpCriticalSection
0x18005121a  mov     [rsp+6D0h+hMem], r13
0x18005121f  call    cs:__imp_EnterCriticalSection
0x180051225  mov     rax, [rsi]
0x180051228  mov     rcx, rsi
0x18005122b  mov     rax, [rax+8]
0x18005122f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051234  test    eax, eax
0x180051236  jz      loc_1800513EB
0x18005123c  mov     rax, [rsi]
0x18005123f  mov     rcx, [rsp+6D0h+hMem]; hMem
0x180051244  mov     rbx, [rax+10h]
0x180051248  test    rcx, rcx
0x18005124b  jz      short loc_180051253
0x18005124d  call    cs:__imp_LocalFree
0x180051253  lea     rdx, [rsp+6D0h+hMem]
0x180051258  mov     [rsp+6D0h+hMem], r13
0x18005125d  mov     rcx, rsi
0x180051260  mov     rax, rbx
0x180051263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051268  mov     rbx, [rsi+8]
0x18005126c  mov     edi, eax
0x18005126e  test    rbx, rbx
0x180051271  jz      short loc_180051282
0x180051273  mov     rax, [rbx]
0x180051276  mov     rcx, rbx
0x180051279  mov     rax, [rax+8]
0x18005127d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051282  mov     rcx, r14; lpCriticalSection
0x180051285  call    cs:__imp_LeaveCriticalSection
0x18005128b  test    edi, edi
0x18005128d  js      loc_180051482
0x180051293  mov     rdi, [rsp+6D0h+hMem]
0x180051298  test    rdi, rdi
0x18005129b  jz      loc_1800513AF
0x1800512a1  mov     r14d, [rdi+4]
0x1800512a5  cmp     r14d, 0C8h
0x1800512ac  ja      loc_180051482
0x1800512b2  xor     edx, edx; Val
0x1800512b4  lea     rcx, [rsp+6D0h+var_690]; void *
0x1800512b9  mov     r8d, 640h; Size
0x1800512bf  call    memset_0
0x1800512c4  xor     r8d, r8d
0x1800512c7  test    r14d, r14d
0x1800512ca  jz      short loc_1800512E8
0x1800512cc  lea     rax, [r8+r8*4]
0x1800512d0  shl     rax, 4
0x1800512d4  add     rax, 8
0x1800512d8  add     rax, rdi
0x1800512db  mov     [rsp+r8*8+6D0h+var_690], rax
0x1800512e0  inc     r8d
0x1800512e3  cmp     r8d, r14d
0x1800512e6  jb      short loc_1800512CC
0x1800512e8  mov     rax, [rbx]
0x1800512eb  lea     r9, [rsp+6D0h+var_690]
0x1800512f0  mov     edx, [rdi]
0x1800512f2  mov     rcx, rbx
0x1800512f5  mov     rax, [rax+18h]
0x1800512f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512fe  test    eax, eax
0x180051300  js      loc_18005146E
0x180051306  mov     r13d, 1
0x18005130c  mov     rax, [rbx]
0x18005130f  mov     rcx, rbx
0x180051312  mov     rax, [rax+10h]
0x180051316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005131b  mov     rcx, [rsp+6D0h+hMem]; hMem
0x180051320  test    rcx, rcx
0x180051323  jnz     loc_1800513E0
0x180051329  lea     r14, ?g_clientNotifyLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_clientNotifyLock
0x180051330  mov     rcx, r14; lpCriticalSection
0x180051333  call    cs:__imp_EnterCriticalSection
0x180051339  or      eax, 0FFFFFFFFh
0x18005133c  lock xadd [r15], eax
0x180051341  mov     rcx, [r12]; pwa
0x180051345  dec     eax
0x180051347  test    rcx, rcx
0x18005134a  jnz     short loc_180051363
0x18005134c  test    eax, eax
0x18005134e  jnz     short loc_180051383
0x180051350  mov     rax, [rsi]
0x180051353  lea     edx, [rcx+1]
0x180051356  mov     rcx, rsi
0x180051359  mov     rax, [rax]
0x18005135c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051361  jmp     short loc_180051383
0x180051363  mov     rdx, [rsi+28h]; h
0x180051367  xor     r8d, r8d; pftTimeout
0x18005136a  call    cs:__imp_SetThreadpoolWait
0x180051370  test    r13d, r13d
0x180051373  jz      short loc_180051383
0x180051375  mov     rcx, [rsi+28h]; hEvent
0x180051379  call    cs:__imp_SetEvent
0x18005137f  test    eax, eax
0x180051381  jz      short loc_1800513F6
0x180051383  mov     rcx, r14; lpCriticalSection
0x180051386  call    cs:__imp_LeaveCriticalSection
0x18005138c  mov     rcx, [rbp+5D0h+var_50]
0x180051393  xor     rcx, rsp; StackCookie
0x180051396  call    __security_check_cookie
0x18005139b  add     rsp, 698h
0x1800513a2  pop     r15
0x1800513a4  pop     r14
0x1800513a6  pop     r13
0x1800513a8  pop     r12
0x1800513aa  pop     rdi
0x1800513ab  pop     rsi
0x1800513ac  pop     rbx
0x1800513ad  pop     rbp
0x1800513ae  retn
0x1800513af  test    rbx, rbx
0x1800513b2  jz      loc_180051330
0x1800513b8  mov     rax, [rbx]
0x1800513bb  mov     rcx, rbx
0x1800513be  mov     rax, [rax+10h]
0x1800513c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513c7  mov     rcx, [rsp+6D0h+hMem]; hMem
0x1800513cc  test    rcx, rcx
0x1800513cf  jz      loc_180051330
0x1800513d5  call    cs:__imp_LocalFree
0x1800513db  jmp     loc_180051330
0x1800513e0  call    cs:__imp_LocalFree
0x1800513e6  jmp     loc_180051329
0x1800513eb  mov     rcx, r14; lpCriticalSection
0x1800513ee  call    cs:__imp_LeaveCriticalSection
0x1800513f4  jmp     short loc_1800513C7
0x1800513f6  call    cs:__imp_GetLastError
0x1800513fc  test    eax, eax
0x1800513fe  jle     short loc_18005140A
0x180051400  movzx   eax, ax
0x180051403  or      eax, 80070000h
0x180051408  test    eax, eax
0x18005140a  jns     loc_180051383
0x180051410  xor     edx, edx
0x180051412  mov     r9d, 0E5h
0x180051418  mov     ecx, eax
0x18005141a  call    Log_UnistoreHREvent_7
0x18005141f  jmp     loc_180051383
0x180051424  cmp     edi, 102h
0x18005142a  jz      loc_180051214
0x180051430  mov     rcx, r14; lpCriticalSection
0x180051433  call    cs:__imp_EnterCriticalSection
0x180051439  mov     eax, [rsi+48h]
0x18005143c  lea     r8, [rsp+6D0h+hMem]; pftTimeout
0x180051441  mov     rcx, [r12]; pwa
0x180051445  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18005144c  mov     rdx, rax
0x18005144f  mov     dword ptr [rsp+6D0h+hMem], eax
0x180051453  shr     rdx, 20h
0x180051457  mov     dword ptr [rsp+6D0h+hMem+4], edx
0x18005145b  mov     rdx, [rsi+28h]; h
0x18005145f  call    cs:__imp_SetThreadpoolWait
0x180051465  lock dec dword ptr [r15]
0x180051469  jmp     loc_180051383
0x18005146e  xor     edx, edx
0x180051470  mov     r9d, 125h
0x180051476  mov     ecx, eax
0x180051478  call    Log_UnistoreHREvent_7
0x18005147d  jmp     loc_180051306
0x180051482  mov     rax, [rbx]
0x180051485  xor     r9d, r9d
0x180051488  xor     r8d, r8d
0x18005148b  mov     rcx, rbx
0x18005148e  mov     rax, [rax+18h]
0x180051492  lea     edx, [r9+8]
0x180051496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005149b  test    eax, eax
0x18005149d  jns     loc_18005130C
0x1800514a3  xor     edx, edx
0x1800514a5  mov     r9d, 110h
0x1800514ab  mov     ecx, eax
0x1800514ad  call    Log_UnistoreHREvent_7
0x1800514b2  jmp     loc_18005130C
```
