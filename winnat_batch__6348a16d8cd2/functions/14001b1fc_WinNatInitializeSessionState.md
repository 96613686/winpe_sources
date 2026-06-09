# WinNatInitializeSessionState

- ea: `0x14001b1fc`
- end: `0x14001b4ab`
- name: `WinNatInitializeSessionState`
- size: `687`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001896c`

## callees

- `0x14000d634`
- `0x14000d8c8`
- `0x14000e488`
- `0x14001b1fc`
- `0x14001ede0`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14001b3ba`
- `ntoskrnl!KeInitializeDpc` at `0x14001b3ba`
- `ntoskrnl!ExAllocatePool2` at `0x14001b33c`
- `ntoskrnl!ExAllocatePool2` at `0x14001b33c`
- `ntoskrnl!KeInitializeTimer` at `0x14001b39d`
- `ntoskrnl!KeInitializeTimer` at `0x14001b39d`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b283`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b2ac`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b2cc`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b283`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b2ac`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b2cc`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14001b473`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14001b473`
- `NETIO!RtlInitializeTimerWheel` at `0x14001b3e0`
- `NETIO!RtlInitializeTimerWheel` at `0x14001b3e0`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001b43c`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001b43c`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001b316`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001b316`
- `ksecdd!BCryptGenRandom` at `0x14001b2f6`
- `ksecdd!BCryptGenRandom` at `0x14001b2f6`

## pseudocode

```c
NTSTATUS __fastcall WinNatInitializeSessionState(char *DeferredContext, int a2, int a3, int a4)
{
  char v4; // si
  __int64 LookasideList; // rax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rax
  NTSTATUS result; // eax
  __int64 Pool2; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-78h]
  int v18; // [rsp+20h] [rbp-78h]
  int v19; // [rsp+38h] [rbp-60h]
  int v20; // [rsp+38h] [rbp-60h]
  __int128 SystemInformation; // [rsp+50h] [rbp-48h] BYREF
  __int64 v22; // [rsp+60h] [rbp-38h]

  v4 = a2;
  SystemInformation = 0;
  v22 = 0;
  LookasideList = PplCreateLookasideList((int)DeferredContext, a2, a3, a4, v17, 0x168u, 0x65734C57u, v19, 0x65734C57u);
  *(_QWORD *)DeferredContext = LookasideList;
  if ( !LookasideList )
    return -1073741670;
  v11 = PplCreateLookasideList(v8, v7, v9, v10, v18, 0x150u, 0x65734C57u, v20, 0x65734C57u);
  *((_QWORD *)DeferredContext + 1) = v11;
  if ( !v11 )
    return -1073741670;
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)DeferredContext + 49, 0, 0) )
    return -1073741670;
  RtlInitializeScalableMrswLock(DeferredContext + 64);
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)DeferredContext + 48, 0, 0)
    || !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)DeferredContext + 50, 0, 0) )
  {
    return -1073741670;
  }
  result = BCryptGenRandom(0, (PUCHAR)DeferredContext + 432, 0x28u, 2u);
  if ( result < 0 )
    return result;
  if ( !(unsigned __int8)RtlInitializeToeplitzHash(DeferredContext + 408, DeferredContext + 432, 40) )
    return -1073741823;
  Pool2 = ExAllocatePool2(64, 1592, 1702054999);
  *((_QWORD *)DeferredContext + 59) = Pool2;
  if ( !Pool2 )
  {
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v14,
        v15,
        L"Session timerwheel allocation failed");
    return -1073741670;
  }
  KeInitializeTimer((PKTIMER)(DeferredContext + 488));
  KeInitializeDpc((PRKDPC)(DeferredContext + 552), WinNatSessionTimerDpc, DeferredContext);
  if ( !(unsigned __int8)RtlInitializeTimerWheel(*((_QWORD *)DeferredContext + 59), 64, 1) )
    return -1073741670;
  *((_DWORD *)DeferredContext + 154) = 0;
  RtlUpdateCurrentTimerWheelTick(*((_QWORD *)DeferredContext + 59), MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8);
  DeferredContext[628] ^= (DeferredContext[628] ^ (2 * v4)) & 2;
  if ( ZwQuerySystemInformation(SystemPrefetcherInformation|0x80, &SystemInformation, 0x18u, 0) >= 0 )
    v16 = (unsigned __int64)SystemInformation >> 6;
  else
    v16 = 0x40000;
  SessionSizeLimit = v16;
  result = 0;
  SessionLimitEventLoggedTick = 0;
  return result;
}

```

## disassembly

```asm
0x14001b1fc  mov     r11, rsp
0x14001b1ff  push    rbx
0x14001b200  push    rsi
0x14001b201  push    rdi
0x14001b202  push    r14
0x14001b204  sub     rsp, 78h
0x14001b208  mov     rax, cs:__security_cookie
0x14001b20f  xor     rax, rsp
0x14001b212  mov     [rsp+98h+var_30], rax
0x14001b217  mov     r14d, 65734C57h
0x14001b21d  xorps   xmm0, xmm0
0x14001b220  mov     [r11-58h], r14d
0x14001b224  xor     eax, eax
0x14001b226  mov     [r11-68h], r14d
0x14001b22a  mov     sil, dl
0x14001b22d  movups  [rsp+98h+SystemInformation], xmm0
0x14001b232  mov     qword ptr [r11-70h], 168h
0x14001b23a  mov     rbx, rcx
0x14001b23d  mov     [r11-38h], rax
0x14001b241  call    PplCreateLookasideList
0x14001b246  mov     [rbx], rax
0x14001b249  test    rax, rax
0x14001b24c  jz      loc_14001B379
0x14001b252  mov     [rsp+98h+var_58], r14d; ULONG
0x14001b257  mov     [rsp+98h+var_68], r14d; ULONG
0x14001b25c  mov     [rsp+98h+var_70], 150h; SIZE_T
0x14001b265  call    PplCreateLookasideList
0x14001b26a  mov     [rbx+8], rax
0x14001b26e  test    rax, rax
0x14001b271  jz      loc_14001B379
0x14001b277  lea     rcx, [rbx+188h]; HashTable
0x14001b27e  xor     r8d, r8d; Flags
0x14001b281  xor     edx, edx; Shift
0x14001b283  call    cs:__imp_RtlCreateHashTable
0x14001b28a  nop     dword ptr [rax+rax+00h]
0x14001b28f  test    al, al
0x14001b291  jz      loc_14001B379
0x14001b297  lea     rcx, [rbx+40h]
0x14001b29b  call    RtlInitializeScalableMrswLock
0x14001b2a0  lea     rcx, [rbx+180h]; HashTable
0x14001b2a7  xor     r8d, r8d; Flags
0x14001b2aa  xor     edx, edx; Shift
0x14001b2ac  call    cs:__imp_RtlCreateHashTable
0x14001b2b3  nop     dword ptr [rax+rax+00h]
0x14001b2b8  test    al, al
0x14001b2ba  jz      loc_14001B379
0x14001b2c0  lea     rcx, [rbx+190h]; HashTable
0x14001b2c7  xor     r8d, r8d; Flags
0x14001b2ca  xor     edx, edx; Shift
0x14001b2cc  call    cs:__imp_RtlCreateHashTable
0x14001b2d3  nop     dword ptr [rax+rax+00h]
0x14001b2d8  test    al, al
0x14001b2da  jz      loc_14001B379
0x14001b2e0  mov     r9d, 2; dwFlags
0x14001b2e6  lea     rdi, [rbx+1B0h]
0x14001b2ed  mov     rdx, rdi; pbBuffer
0x14001b2f0  xor     ecx, ecx; hAlgorithm
0x14001b2f2  lea     r8d, [r9+26h]; cbBuffer
0x14001b2f6  call    cs:__imp_BCryptGenRandom
0x14001b2fd  nop     dword ptr [rax+rax+00h]
0x14001b302  test    eax, eax
0x14001b304  js      short loc_14001B37E
0x14001b306  lea     rcx, [rbx+198h]
0x14001b30d  mov     r8d, 28h ; '('
0x14001b313  mov     rdx, rdi
0x14001b316  call    cs:__imp_RtlInitializeToeplitzHash
0x14001b31d  nop     dword ptr [rax+rax+00h]
0x14001b322  test    al, al
0x14001b324  jnz     short loc_14001B32D
0x14001b326  mov     eax, 0C0000001h
0x14001b32b  jmp     short loc_14001B37E
0x14001b32d  mov     edi, 40h ; '@'
0x14001b332  mov     r8d, r14d
0x14001b335  mov     ecx, edi
0x14001b337  mov     edx, 638h
0x14001b33c  call    cs:__imp_ExAllocatePool2
0x14001b343  nop     dword ptr [rax+rax+00h]
0x14001b348  mov     [rbx+1D8h], rax
0x14001b34f  test    rax, rax
0x14001b352  jnz     short loc_14001B396
0x14001b354  cmp     cs:dword_140026104, 1
0x14001b35b  jnz     short loc_14001B379
0x14001b35d  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14001b364  jz      short loc_14001B379
0x14001b366  lea     r9, aSessionTimerwh; "Session timerwheel allocation failed"
0x14001b36d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001b374  call    McTemplateK0z_EtwWriteTransfer
0x14001b379  mov     eax, 0C000009Ah
0x14001b37e  mov     rcx, [rsp+98h+var_30]
0x14001b383  xor     rcx, rsp; StackCookie
0x14001b386  call    __security_check_cookie
0x14001b38b  add     rsp, 78h
0x14001b38f  pop     r14
0x14001b391  pop     rdi
0x14001b392  pop     rsi
0x14001b393  pop     rbx
0x14001b394  retn
0x14001b396  lea     rcx, [rbx+1E8h]; Timer
0x14001b39d  call    cs:__imp_KeInitializeTimer
0x14001b3a4  nop     dword ptr [rax+rax+00h]
0x14001b3a9  lea     rcx, [rbx+228h]; Dpc
0x14001b3b0  mov     r8, rbx; DeferredContext
0x14001b3b3  lea     rdx, WinNatSessionTimerDpc; DeferredRoutine
0x14001b3ba  call    cs:__imp_KeInitializeDpc
0x14001b3c1  nop     dword ptr [rax+rax+00h]
0x14001b3c6  mov     rcx, [rbx+1D8h]
0x14001b3cd  mov     r9d, 1
0x14001b3d3  mov     r8d, r9d
0x14001b3d6  mov     [rsp+98h+var_78], 0
0x14001b3de  mov     edx, edi
0x14001b3e0  call    cs:__imp_RtlInitializeTimerWheel
0x14001b3e7  nop     dword ptr [rax+rax+00h]
0x14001b3ec  test    al, al
0x14001b3ee  jz      short loc_14001B379
0x14001b3f0  mov     dword ptr [rbx+268h], 0
0x14001b3fa  mov     rcx, 0FFFFF78000000008h
0x14001b404  mov     rax, 346DC5D63886594Bh
0x14001b40e  mov     rcx, [rcx]
0x14001b411  mul     rcx
0x14001b414  mov     rax, 624DD2F1A9FBE77h
0x14001b41e  mov     rcx, rdx
0x14001b421  shr     rcx, 0Bh
0x14001b425  mul     rcx
0x14001b428  sub     rcx, rdx
0x14001b42b  shr     rcx, 1
0x14001b42e  add     rdx, rcx
0x14001b431  mov     rcx, [rbx+1D8h]
0x14001b438  shr     rdx, 9
0x14001b43c  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14001b443  nop     dword ptr [rax+rax+00h]
0x14001b448  mov     al, [rbx+274h]
0x14001b44e  lea     rdx, [rsp+98h+SystemInformation]; SystemInformation
0x14001b453  add     sil, sil
0x14001b456  xor     r9d, r9d; ReturnLength
0x14001b459  xor     sil, al
0x14001b45c  mov     ecx, 0B8h; SystemInformationClass
0x14001b461  and     sil, 2
0x14001b465  xor     sil, al
0x14001b468  lea     r8d, [r9+18h]; SystemInformationLength
0x14001b46c  mov     [rbx+274h], sil
0x14001b473  call    cs:__imp_ZwQuerySystemInformation
0x14001b47a  nop     dword ptr [rax+rax+00h]
0x14001b47f  test    eax, eax
0x14001b481  jns     short loc_14001B48A
0x14001b483  mov     eax, 40000h
0x14001b488  jmp     short loc_14001B493
0x14001b48a  mov     rax, qword ptr [rsp+98h+SystemInformation]
0x14001b48f  shr     rax, 6
0x14001b493  mov     cs:SessionSizeLimit, rax
0x14001b49a  xor     eax, eax
0x14001b49c  mov     cs:SessionLimitEventLoggedTick, 0
0x14001b4a6  jmp     loc_14001B37E
```
