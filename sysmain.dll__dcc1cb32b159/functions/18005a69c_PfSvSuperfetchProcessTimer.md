# PfSvSuperfetchProcessTimer

- ea: `0x18005a69c`
- end: `0x18005a90b`
- name: `PfSvSuperfetchProcessTimer`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d1c0`

## callees

- `0x18003c814`
- `0x180053cac`
- `0x18005a69c`
- `0x18005a914`
- `0x18005a9e4`
- `0x1800699ac`
- `0x18008e818`
- `0x180090134`
- `0x1800b64c0`
- `0x1800b7010`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18005a75d`
- `ntdll!NtQueryInformationThread` at `0x18005a75d`
- `ntdll!RtlNtStatusToDosError` at `0x18005a76e`
- `ntdll!RtlNtStatusToDosError` at `0x18005a76e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a7a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005a7a1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005a869`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18005a869`

## pseudocode

```c
__int64 __fastcall PfSvSuperfetchProcessTimer(__int64 a1)
{
  int UnbiasedTickCount; // edi
  int v3; // eax
  HANDLE CurrentThread; // rax
  int v5; // eax
  int v6; // esi
  HANDLE v7; // rax
  __int64 v8; // r14
  HANDLE v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  int ThreadInformation; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v18[24]; // [rsp+38h] [rbp-28h] BYREF

  memset(v18, 0, sizeof(v18));
  UnbiasedTickCount = PfsGetUnbiasedTickCount();
  v3 = *(_DWORD *)(a1 + 2508);
  if ( (unsigned int)(UnbiasedTickCount - v3) >= 0x493E0 || !v3 )
  {
    PfClLogSystemTime(a1 + 112);
    *(_DWORD *)(a1 + 2508) = UnbiasedTickCount;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 1252) - *(_DWORD *)(a1 + 2516)) < 0x780 )
  {
    v11 = *(_QWORD *)&PfSvcGlobals;
    v8 = a1 + 1176;
    v10 = 0;
  }
  else
  {
    *(_QWORD *)&v18[12] = 0;
    *(_DWORD *)&v18[20] = 0;
    *(_QWORD *)v18 = 0x100000000000001LL;
    *(_DWORD *)&v18[8] = 1;
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v5 = NtQueryInformationThread(CurrentThread, ThreadIoPriority, &ThreadInformation, 4u, 0);
    if ( v5 >= 0 )
    {
      v6 = ThreadInformation;
    }
    else
    {
      v6 = 5;
      RtlNtStatusToDosError(v5);
    }
    v7 = GetCurrentThread();
    PfSetIoPriorityThread(v7);
    v8 = a1 + 1176;
    PfPrProcessCommand(a1 + 1176, v18);
    if ( v6 != 5 )
    {
      v9 = GetCurrentThread();
      PfSetIoPriorityThread(v9);
    }
    v10 = 1;
    *(_DWORD *)(a1 + 2516) = *(_DWORD *)(a1 + 1252);
    *(_DWORD *)(a1 + 2512) = UnbiasedTickCount;
    v11 = *(_QWORD *)&PfSvcGlobals;
    *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) |= 0x100u;
  }
  if ( (unsigned int)(UnbiasedTickCount - *(_DWORD *)(a1 + 2512)) < 0x36EE80 )
  {
    if ( !v10 )
      goto LABEL_19;
  }
  else
  {
    *(_QWORD *)&v18[12] = 0;
    *(_DWORD *)&v18[20] = 0;
    *(_QWORD *)v18 = 0x100000000000001LL;
    *(_DWORD *)&v18[8] = 5;
    PfPrProcessCommand(v8, v18);
    v12 = *(_QWORD *)(a1 + 1192);
    *(_DWORD *)(a1 + 2512) = UnbiasedTickCount;
    if ( v12 )
      PfCrCombine(*(_QWORD *)(v12 + 16));
    v11 = *(_QWORD *)&PfSvcGlobals;
  }
  if ( *(_QWORD *)(v11 + 1888) )
  {
    VirtualFree(*(LPVOID *)(v11 + 1888), 0, 0x8000u);
    v11 = *(_QWORD *)&PfSvcGlobals;
    *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1888LL) = 0;
    *(_DWORD *)(v11 + 1896) = 0;
  }
LABEL_19:
  v13 = *(_QWORD *)(v11 + 3816);
  if ( v13 )
  {
    v14 = *(_QWORD *)(a1 + 1208);
    if ( v14 )
      RphInitiatePeriodicTasks(v13 + 1872, *(unsigned int *)(v14 + 964));
  }
  if ( (unsigned int)(UnbiasedTickCount - *(_DWORD *)(a1 + 496)) >= 0x36EE80 )
    PfClPdSync(a1 + 376);
  v15 = *(_QWORD *)(a1 + 1216);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v15 + 8))(*(_QWORD *)v15, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18005a69c  mov     [rsp-18h+arg_8], rbx
0x18005a6a1  mov     [rsp-18h+arg_10], rsi
0x18005a6a6  push    rbp
0x18005a6a7  push    rdi
0x18005a6a8  push    r14
0x18005a6aa  mov     rbp, rsp
0x18005a6ad  sub     rsp, 60h
0x18005a6b1  mov     rax, cs:__security_cookie
0x18005a6b8  xor     rax, rsp
0x18005a6bb  mov     [rbp+var_10], rax
0x18005a6bf  xor     eax, eax
0x18005a6c1  xorps   xmm0, xmm0
0x18005a6c4  movups  [rbp+var_28], xmm0
0x18005a6c8  mov     [rbp+var_18], rax
0x18005a6cc  mov     rbx, rcx
0x18005a6cf  call    PfsGetUnbiasedTickCount
0x18005a6d4  mov     edi, eax
0x18005a6d6  mov     eax, [rbx+9CCh]
0x18005a6dc  mov     edx, edi
0x18005a6de  sub     edx, eax
0x18005a6e0  cmp     edx, 493E0h
0x18005a6e6  jnb     short loc_18005A6EC
0x18005a6e8  test    eax, eax
0x18005a6ea  jnz     short loc_18005A6FB
0x18005a6ec  lea     rcx, [rbx+70h]
0x18005a6f0  call    PfClLogSystemTime
0x18005a6f5  mov     [rbx+9CCh], edi
0x18005a6fb  mov     eax, [rbx+4E4h]
0x18005a701  sub     eax, [rbx+9D4h]
0x18005a707  cmp     eax, 780h
0x18005a70c  jb      loc_18005A7D9
0x18005a712  mov     qword ptr [rbp+var_28+0Ch], 0
0x18005a71a  mov     dword ptr [rbp+var_18+4], 0
0x18005a721  mov     dword ptr [rbp+var_28], 1
0x18005a728  mov     dword ptr [rbp+var_28+4], 1000000h
0x18005a72f  mov     dword ptr [rbp+var_28+8], 1
0x18005a736  call    cs:__imp_GetCurrentThread
0x18005a73c  mov     r9d, 4; ThreadInformationLength
0x18005a742  mov     [rbp+ThreadInformation], 0
0x18005a749  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x18005a74d  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18005a756  mov     rcx, rax; ThreadHandle
0x18005a759  lea     edx, [r9+12h]; ThreadInformationClass
0x18005a75d  call    cs:__imp_NtQueryInformationThread
0x18005a763  test    eax, eax
0x18005a765  jns     short loc_18005A776
0x18005a767  mov     ecx, eax; Status
0x18005a769  mov     esi, 5
0x18005a76e  call    cs:__imp_RtlNtStatusToDosError
0x18005a774  jmp     short loc_18005A779
0x18005a776  mov     esi, [rbp+ThreadInformation]
0x18005a779  call    cs:__imp_GetCurrentThread
0x18005a77f  mov     rcx, rax; ThreadHandle
0x18005a782  xor     edx, edx
0x18005a784  call    PfSetIoPriorityThread
0x18005a789  lea     r14, [rbx+498h]
0x18005a790  mov     rcx, r14
0x18005a793  lea     rdx, [rbp+var_28]
0x18005a797  call    PfPrProcessCommand
0x18005a79c  cmp     esi, 5
0x18005a79f  jz      short loc_18005A7B1
0x18005a7a1  call    cs:__imp_GetCurrentThread
0x18005a7a7  mov     rcx, rax; ThreadHandle
0x18005a7aa  mov     edx, esi
0x18005a7ac  call    PfSetIoPriorityThread
0x18005a7b1  mov     eax, [rbx+4E4h]
0x18005a7b7  mov     edx, 1
0x18005a7bc  mov     [rbx+9D4h], eax
0x18005a7c2  mov     [rbx+9D0h], edi
0x18005a7c8  mov     rcx, cs:PfSvcGlobals
0x18005a7cf  bts     dword ptr [rcx+640h], 8
0x18005a7d7  jmp     short loc_18005A7E9
0x18005a7d9  mov     rcx, cs:PfSvcGlobals
0x18005a7e0  lea     r14, [rbx+498h]
0x18005a7e7  xor     edx, edx
0x18005a7e9  mov     eax, edi
0x18005a7eb  mov     esi, 36EE80h
0x18005a7f0  sub     eax, [rbx+9D0h]
0x18005a7f6  cmp     eax, esi
0x18005a7f8  jb      short loc_18005A84E
0x18005a7fa  lea     rdx, [rbp+var_28]
0x18005a7fe  mov     qword ptr [rbp+var_28+0Ch], 0
0x18005a806  mov     rcx, r14
0x18005a809  mov     dword ptr [rbp+var_18+4], 0
0x18005a810  mov     dword ptr [rbp+var_28], 1
0x18005a817  mov     dword ptr [rbp+var_28+4], 1000000h
0x18005a81e  mov     dword ptr [rbp+var_28+8], 5
0x18005a825  call    PfPrProcessCommand
0x18005a82a  mov     rcx, [rbx+4A8h]
0x18005a831  mov     [rbx+9D0h], edi
0x18005a837  test    rcx, rcx
0x18005a83a  jz      short loc_18005A845
0x18005a83c  mov     rcx, [rcx+10h]
0x18005a840  call    PfCrCombine
0x18005a845  mov     rcx, cs:PfSvcGlobals
0x18005a84c  jmp     short loc_18005A852
0x18005a84e  test    edx, edx
0x18005a850  jz      short loc_18005A88B
0x18005a852  mov     rax, [rcx+760h]
0x18005a859  test    rax, rax
0x18005a85c  jz      short loc_18005A88B
0x18005a85e  xor     edx, edx; dwSize
0x18005a860  mov     r8d, 8000h; dwFreeType
0x18005a866  mov     rcx, rax; lpAddress
0x18005a869  call    cs:__imp_VirtualFree
0x18005a86f  mov     rcx, cs:PfSvcGlobals
0x18005a876  mov     qword ptr [rcx+760h], 0
0x18005a881  mov     dword ptr [rcx+768h], 0
0x18005a88b  mov     rcx, [rcx+0EE8h]
0x18005a892  test    rcx, rcx
0x18005a895  jz      short loc_18005A8B5
0x18005a897  mov     rdx, [rbx+4B8h]
0x18005a89e  test    rdx, rdx
0x18005a8a1  jz      short loc_18005A8B5
0x18005a8a3  mov     edx, [rdx+3C4h]
0x18005a8a9  add     rcx, 750h
0x18005a8b0  call    RphInitiatePeriodicTasks
0x18005a8b5  sub     edi, [rbx+1F0h]
0x18005a8bb  cmp     edi, esi
0x18005a8bd  jb      short loc_18005A8CB
0x18005a8bf  lea     rcx, [rbx+178h]
0x18005a8c6  call    PfClPdSync
0x18005a8cb  mov     rax, [rbx+4C0h]
0x18005a8d2  test    rax, rax
0x18005a8d5  jz      short loc_18005A8E8
0x18005a8d7  mov     rcx, [rax]
0x18005a8da  xor     r8d, r8d
0x18005a8dd  mov     rax, [rax+8]
0x18005a8e1  xor     edx, edx
0x18005a8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a8e8  xor     eax, eax
0x18005a8ea  mov     rcx, [rbp+var_10]
0x18005a8ee  xor     rcx, rsp; StackCookie
0x18005a8f1  call    __security_check_cookie
0x18005a8f6  lea     r11, [rsp+60h+var_s0]
0x18005a8fb  mov     rbx, [r11+28h]
0x18005a8ff  mov     rsi, [r11+30h]
0x18005a903  mov     rsp, r11
0x18005a906  pop     r14
0x18005a908  pop     rdi
0x18005a909  pop     rbp
0x18005a90a  retn
```
