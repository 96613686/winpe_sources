# wfdClientRegisterNotification(_WFD_CLIENT_CONTEXT *,ulong,int,void (*)(_L2_NOTIFICATION_DATA *,void *),void *,ulong *)

- ea: `0x1800142d8`
- end: `0x1800145c8`
- name: `?wfdClientRegisterNotification@@YAKPEAU_WFD_CLIENT_CONTEXT@@KHP6AXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z2PEAK@Z`
- size: `752`
- prototype: `unsigned int __usercall@<eax>(struct _WFD_CLIENT_CONTEXT *@<rcx>, unsigned int@<edx>, int@<r8d>, void (*)(struct _L2_NOTIFICATION_DATA *, void *)@<r9>, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800028ac`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800101d0`
- `0x1800142d8`
- `0x180019278`
- `0x18005a8b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800143a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800143a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800144df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014527`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800144df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014527`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001451e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001451e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014538`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014541`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014541`
- `RPCRT4!RpcExceptionFilter` at `0x180060b40`
- `RPCRT4!RpcExceptionFilter` at `0x180060b40`

## pseudocode

```c
__int64 __fastcall wfdClientRegisterNotification(
        struct _WFD_CLIENT_CONTEXT *a1,
        unsigned int a2,
        __int64 a3,
        void (*a4)(struct _L2_NOTIFICATION_DATA *, void *),
        void *a5,
        unsigned int *a6)
{
  DWORD LastError; // edi
  union DOT11_OUI_HEADER *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // r15
  _QWORD *v11; // r12
  HANDLE Thread; // rax
  union DOT11_OUI_HEADER *v13; // r10
  __int64 v14; // rcx
  unsigned int v15; // eax
  void *v16; // rsi
  unsigned int v18; // [rsp+80h] [rbp+18h] BYREF
  void (*v19)(struct _L2_NOTIFICATION_DATA *, void *); // [rsp+88h] [rbp+20h]

  v19 = a4;
  LastError = 0;
  v18 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v9 + 105) >= 4u
      && (*((_DWORD *)v9 + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v9 + 12), 25, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, a2);
    }
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 168);
  a6 = (unsigned int *)((char *)a1 + 168);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 168));
  v11 = (_QWORD *)((char *)a1 + 216);
  if ( !*((_QWORD *)a1 + 27) )
  {
    Thread = CreateThread(0, 0, wfdNotificationApcThreadProc, a1, 0, 0);
    *v11 = Thread;
    if ( !Thread )
      LastError = GetLastError();
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 168));
  if ( LastError )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
LABEL_22:
      v13 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v14 = *(_QWORD *)a1;
    if ( *((_DWORD *)a1 + 56) )
      v15 = RpcLowPrivRegisterNotification(v14, a2, &v18);
    else
      v15 = RpcRegisterNotification(v14, a2, &v18);
    LastError = ServiceStatus(v15);
    if ( !LastError )
    {
      EnterCriticalSection(v10);
      *((_QWORD *)a1 + 3) = v19;
      *((_QWORD *)a1 + 12) = *v11;
      *((_QWORD *)a1 + 4) = a5;
      LeaveCriticalSection(v10);
      LastError = wfdClientGetNotification(a1);
      goto LABEL_22;
    }
  }
  if ( LastError )
  {
    v16 = 0;
    EnterCriticalSection(v10);
    if ( *v11 )
    {
      v16 = (void *)*v11;
      *v11 = 0;
      SetEvent(*((HANDLE *)a1 + 26));
    }
    LeaveCriticalSection(v10);
    if ( v16 )
    {
      WaitForSingleObject(v16, 0xFFFFFFFF);
      CloseHandle(v16);
    }
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)v13 + 105) >= 4u && (*((_DWORD *)v13 + 27) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v13 + 12), 28, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v18);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v13 + 105) >= 4u
      && (*((_BYTE *)v13 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v13 + 12), 29, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800142d8  mov     rax, rsp
0x1800142db  mov     [rax+10h], rsi
0x1800142df  mov     [rax+20h], r9
0x1800142e3  mov     [rax+18h], r8d
0x1800142e7  mov     [rax+8], rcx
0x1800142eb  push    rdi
0x1800142ec  push    r12
0x1800142ee  push    r13
0x1800142f0  push    r14
0x1800142f2  push    r15
0x1800142f4  sub     rsp, 40h
0x1800142f8  mov     esi, edx
0x1800142fa  mov     r14, rcx
0x1800142fd  xor     edi, edi
0x1800142ff  mov     [rax+18h], edi
0x180014302  lea     r13, WPP_GLOBAL_Control
0x180014309  mov     rcx, cs:WPP_GLOBAL_Control
0x180014310  cmp     rcx, r13
0x180014313  jz      short loc_180014367
0x180014315  cmp     byte ptr [rcx+69h], 4
0x180014319  jb      short loc_18001433B
0x18001431b  test    byte ptr [rcx+6Ch], 2
0x18001431f  jz      short loc_18001433B
0x180014321  lea     edx, [rdi+18h]
0x180014324  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18001432b  mov     rcx, [rcx+60h]
0x18001432f  call    WPP_SF_
0x180014334  mov     rcx, cs:WPP_GLOBAL_Control
0x18001433b  cmp     rcx, r13
0x18001433e  jz      short loc_180014367
0x180014340  cmp     byte ptr [rcx+69h], 4
0x180014344  jb      short loc_180014367
0x180014346  test    dword ptr [rcx+6Ch], 1000h
0x18001434d  jz      short loc_180014367
0x18001434f  mov     edx, 19h
0x180014354  mov     r9d, esi
0x180014357  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18001435e  mov     rcx, [rcx+60h]
0x180014362  call    WPP_SF_d
0x180014367  lea     r15, [r14+0A8h]
0x18001436e  mov     [rsp+68h+arg_28], r15
0x180014376  mov     rcx, r15; lpCriticalSection
0x180014379  call    cs:__imp_EnterCriticalSection
0x18001437f  lea     r12, [r14+0D8h]
0x180014386  mov     [rsp+68h+var_30], r12
0x18001438b  cmp     [r12], rdi
0x18001438f  jnz     short loc_1800143BF
0x180014391  mov     [rsp+68h+lpThreadId], rdi; lpThreadId
0x180014396  mov     [rsp+68h+dwCreationFlags], edi; dwCreationFlags
0x18001439a  mov     r9, r14; lpParameter
0x18001439d  lea     r8, ?wfdNotificationApcThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800143a4  xor     edx, edx; dwStackSize
0x1800143a6  xor     ecx, ecx; lpThreadAttributes
0x1800143a8  call    cs:__imp_CreateThread
0x1800143ae  mov     [r12], rax
0x1800143b2  test    rax, rax
0x1800143b5  jnz     short loc_1800143BF
0x1800143b7  call    cs:__imp_GetLastError
0x1800143bd  mov     edi, eax
0x1800143bf  mov     rcx, r15; lpCriticalSection
0x1800143c2  call    cs:__imp_LeaveCriticalSection
0x1800143c8  test    edi, edi
0x1800143ca  jz      short loc_180014412
0x1800143cc  mov     r10, cs:WPP_GLOBAL_Control
0x1800143d3  cmp     r10, r13
0x1800143d6  jz      loc_1800144F6
0x1800143dc  cmp     byte ptr [r10+69h], 4
0x1800143e1  jb      loc_1800144F6
0x1800143e7  test    dword ptr [r10+6Ch], 1000h
0x1800143ef  jz      loc_1800144F6
0x1800143f5  mov     edx, 1Ah
0x1800143fa  mov     r9d, edi
0x1800143fd  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180014404  mov     rcx, [r10+60h]
0x180014408  call    WPP_SF_d
0x18001440d  jmp     loc_1800144EF
0x180014412  lea     r8, [rsp+68h+arg_10]
0x18001441a  mov     edx, esi
0x18001441c  mov     rcx, [r14]
0x18001441f  cmp     dword ptr [r14+0E0h], 0
0x180014427  jz      short loc_180014430
0x180014429  call    RpcLowPrivRegisterNotification
0x18001442e  jmp     short loc_180014435
0x180014430  call    RpcRegisterNotification
0x180014435  mov     [rsp+68h+var_38], eax
0x180014439  mov     edi, eax
0x18001443b  mov     r10, cs:WPP_GLOBAL_Control
0x180014442  jmp     short loc_1800144A6
0x180014444  mov     edi, eax
0x180014446  mov     [rsp+68h+var_38], eax
0x18001444a  lea     rax, WPP_GLOBAL_Control
0x180014451  mov     r10, cs:WPP_GLOBAL_Control
0x180014458  cmp     r10, rax
0x18001445b  jz      short loc_18001448D
0x18001445d  cmp     byte ptr [r10+69h], 1
0x180014462  jb      short loc_18001448D
0x180014464  test    dword ptr [r10+6Ch], 1000h
0x18001446c  jz      short loc_18001448D
0x18001446e  mov     edx, 1Bh
0x180014473  mov     r9d, edi
0x180014476  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18001447d  mov     rcx, [r10+60h]
0x180014481  call    WPP_SF_d
0x180014486  mov     r10, cs:WPP_GLOBAL_Control
0x18001448d  lea     r13, WPP_GLOBAL_Control
0x180014494  mov     r14, [rsp+68h+arg_0]
0x180014499  mov     r15, [rsp+68h+arg_28]
0x1800144a1  mov     r12, [rsp+68h+var_30]
0x1800144a6  mov     ecx, edi; unsigned int
0x1800144a8  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800144ad  mov     edi, eax
0x1800144af  test    eax, eax
0x1800144b1  jnz     short loc_1800144F6
0x1800144b3  mov     rcx, r15; lpCriticalSection
0x1800144b6  call    cs:__imp_EnterCriticalSection
0x1800144bc  mov     rax, [rsp+68h+arg_18]
0x1800144c4  mov     [r14+18h], rax
0x1800144c8  mov     rax, [r12]
0x1800144cc  mov     [r14+60h], rax
0x1800144d0  mov     rax, [rsp+68h+arg_20]
0x1800144d8  mov     [r14+20h], rax
0x1800144dc  mov     rcx, r15; lpCriticalSection
0x1800144df  call    cs:__imp_LeaveCriticalSection
0x1800144e5  mov     rcx, r14; struct _WFD_CLIENT_CONTEXT *
0x1800144e8  call    ?wfdClientGetNotification@@YAKPEAU_WFD_CLIENT_CONTEXT@@@Z; wfdClientGetNotification(_WFD_CLIENT_CONTEXT *)
0x1800144ed  mov     edi, eax
0x1800144ef  mov     r10, cs:WPP_GLOBAL_Control
0x1800144f6  test    edi, edi
0x1800144f8  jz      short loc_18001454E
0x1800144fa  xor     esi, esi
0x1800144fc  mov     rcx, r15; lpCriticalSection
0x1800144ff  call    cs:__imp_EnterCriticalSection
0x180014505  cmp     [r12], rsi
0x180014509  jz      short loc_180014524
0x18001450b  mov     rsi, [r12]
0x18001450f  mov     qword ptr [r12], 0
0x180014517  mov     rcx, [r14+0D0h]; hEvent
0x18001451e  call    cs:__imp_SetEvent
0x180014524  mov     rcx, r15; lpCriticalSection
0x180014527  call    cs:__imp_LeaveCriticalSection
0x18001452d  test    rsi, rsi
0x180014530  jz      short loc_180014547
0x180014532  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014535  mov     rcx, rsi; hHandle
0x180014538  call    cs:__imp_WaitForSingleObject
0x18001453e  mov     rcx, rsi; hObject
0x180014541  call    cs:__imp_CloseHandle
0x180014547  mov     r10, cs:WPP_GLOBAL_Control
0x18001454e  cmp     r10, r13
0x180014551  jz      short loc_1800145B3
0x180014553  cmp     byte ptr [r10+69h], 4
0x180014558  jb      short loc_180014588
0x18001455a  test    dword ptr [r10+6Ch], 1000h
0x180014562  jz      short loc_180014588
0x180014564  mov     edx, 1Ch
0x180014569  mov     r9d, [rsp+68h+arg_10]
0x180014571  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180014578  mov     rcx, [r10+60h]
0x18001457c  call    WPP_SF_d
0x180014581  mov     r10, cs:WPP_GLOBAL_Control
0x180014588  cmp     r10, r13
0x18001458b  jz      short loc_1800145B3
0x18001458d  cmp     byte ptr [r10+69h], 4
0x180014592  jb      short loc_1800145B3
0x180014594  test    byte ptr [r10+6Ch], 2
0x180014599  jz      short loc_1800145B3
0x18001459b  mov     edx, 1Dh
0x1800145a0  mov     r9d, edi
0x1800145a3  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800145aa  mov     rcx, [r10+60h]
0x1800145ae  call    WPP_SF_d
0x1800145b3  mov     eax, edi
0x1800145b5  mov     rsi, [rsp+68h+arg_8]
0x1800145ba  add     rsp, 40h
0x1800145be  pop     r15
0x1800145c0  pop     r14
0x1800145c2  pop     r13
0x1800145c4  pop     r12
0x1800145c6  pop     rdi
0x1800145c7  retn
0x180060b32  push    rbp
0x180060b34  sub     rsp, 30h
0x180060b38  mov     rbp, rdx
0x180060b3b  mov     rcx, [rcx]
0x180060b3e  mov     ecx, [rcx]; ExceptionCode
0x180060b40  call    cs:__imp_RpcExceptionFilter
0x180060b46  nop
0x180060b47  add     rsp, 30h
0x180060b4b  pop     rbp
0x180060b4c  retn
```
