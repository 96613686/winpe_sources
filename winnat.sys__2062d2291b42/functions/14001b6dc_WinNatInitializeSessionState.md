# WinNatInitializeSessionState

- ea: `0x14001b6dc`
- end: `0x14001b98b`
- name: `WinNatInitializeSessionState`
- size: `687`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140018e4c`

## callees

- `0x14000d604`
- `0x14000d898`
- `0x14000e4b0`
- `0x14001b6dc`
- `0x14001f320`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14001b89a`
- `ntoskrnl!KeInitializeDpc` at `0x14001b89a`
- `ntoskrnl!ExAllocatePool2` at `0x14001b81c`
- `ntoskrnl!ExAllocatePool2` at `0x14001b81c`
- `ntoskrnl!KeInitializeTimer` at `0x14001b87d`
- `ntoskrnl!KeInitializeTimer` at `0x14001b87d`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b763`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b78c`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b7ac`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b763`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b78c`
- `ntoskrnl!RtlCreateHashTable` at `0x14001b7ac`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14001b953`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14001b953`
- `NETIO!RtlInitializeTimerWheel` at `0x14001b8c0`
- `NETIO!RtlInitializeTimerWheel` at `0x14001b8c0`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001b91c`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14001b91c`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001b7f6`
- `NETIO!RtlInitializeToeplitzHash` at `0x14001b7f6`
- `ksecdd!BCryptGenRandom` at `0x14001b7d6`
- `ksecdd!BCryptGenRandom` at `0x14001b7d6`

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
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
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
0x14001b6dc  mov     r11, rsp
0x14001b6df  push    rbx
0x14001b6e0  push    rsi
0x14001b6e1  push    rdi
0x14001b6e2  push    r14
0x14001b6e4  sub     rsp, 78h
0x14001b6e8  mov     rax, cs:__security_cookie
0x14001b6ef  xor     rax, rsp
0x14001b6f2  mov     [rsp+98h+var_30], rax
0x14001b6f7  mov     r14d, 65734C57h
0x14001b6fd  xorps   xmm0, xmm0
0x14001b700  mov     [r11-58h], r14d
0x14001b704  xor     eax, eax
0x14001b706  mov     [r11-68h], r14d
0x14001b70a  mov     sil, dl
0x14001b70d  movups  [rsp+98h+SystemInformation], xmm0
0x14001b712  mov     qword ptr [r11-70h], 168h
0x14001b71a  mov     rbx, rcx
0x14001b71d  mov     [r11-38h], rax
0x14001b721  call    PplCreateLookasideList
0x14001b726  mov     [rbx], rax
0x14001b729  test    rax, rax
0x14001b72c  jz      loc_14001B859
0x14001b732  mov     [rsp+98h+var_58], r14d; ULONG
0x14001b737  mov     [rsp+98h+var_68], r14d; ULONG
0x14001b73c  mov     [rsp+98h+var_70], 150h; SIZE_T
0x14001b745  call    PplCreateLookasideList
0x14001b74a  mov     [rbx+8], rax
0x14001b74e  test    rax, rax
0x14001b751  jz      loc_14001B859
0x14001b757  lea     rcx, [rbx+188h]; HashTable
0x14001b75e  xor     r8d, r8d; Flags
0x14001b761  xor     edx, edx; Shift
0x14001b763  call    cs:__imp_RtlCreateHashTable
0x14001b76a  nop     dword ptr [rax+rax+00h]
0x14001b76f  test    al, al
0x14001b771  jz      loc_14001B859
0x14001b777  lea     rcx, [rbx+40h]
0x14001b77b  call    RtlInitializeScalableMrswLock
0x14001b780  lea     rcx, [rbx+180h]; HashTable
0x14001b787  xor     r8d, r8d; Flags
0x14001b78a  xor     edx, edx; Shift
0x14001b78c  call    cs:__imp_RtlCreateHashTable
0x14001b793  nop     dword ptr [rax+rax+00h]
0x14001b798  test    al, al
0x14001b79a  jz      loc_14001B859
0x14001b7a0  lea     rcx, [rbx+190h]; HashTable
0x14001b7a7  xor     r8d, r8d; Flags
0x14001b7aa  xor     edx, edx; Shift
0x14001b7ac  call    cs:__imp_RtlCreateHashTable
0x14001b7b3  nop     dword ptr [rax+rax+00h]
0x14001b7b8  test    al, al
0x14001b7ba  jz      loc_14001B859
0x14001b7c0  mov     r9d, 2; dwFlags
0x14001b7c6  lea     rdi, [rbx+1B0h]
0x14001b7cd  mov     rdx, rdi; pbBuffer
0x14001b7d0  xor     ecx, ecx; hAlgorithm
0x14001b7d2  lea     r8d, [r9+26h]; cbBuffer
0x14001b7d6  call    cs:__imp_BCryptGenRandom
0x14001b7dd  nop     dword ptr [rax+rax+00h]
0x14001b7e2  test    eax, eax
0x14001b7e4  js      short loc_14001B85E
0x14001b7e6  lea     rcx, [rbx+198h]
0x14001b7ed  mov     r8d, 28h ; '('
0x14001b7f3  mov     rdx, rdi
0x14001b7f6  call    cs:__imp_RtlInitializeToeplitzHash
0x14001b7fd  nop     dword ptr [rax+rax+00h]
0x14001b802  test    al, al
0x14001b804  jnz     short loc_14001B80D
0x14001b806  mov     eax, 0C0000001h
0x14001b80b  jmp     short loc_14001B85E
0x14001b80d  mov     edi, 40h ; '@'
0x14001b812  mov     r8d, r14d
0x14001b815  mov     ecx, edi
0x14001b817  mov     edx, 638h
0x14001b81c  call    cs:__imp_ExAllocatePool2
0x14001b823  nop     dword ptr [rax+rax+00h]
0x14001b828  mov     [rbx+1D8h], rax
0x14001b82f  test    rax, rax
0x14001b832  jnz     short loc_14001B876
0x14001b834  cmp     cs:dword_140027104, 1
0x14001b83b  jnz     short loc_14001B859
0x14001b83d  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14001b844  jz      short loc_14001B859
0x14001b846  lea     r9, aSessionTimerwh; "Session timerwheel allocation failed"
0x14001b84d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001b854  call    McTemplateK0z_EtwWriteTransfer
0x14001b859  mov     eax, 0C000009Ah
0x14001b85e  mov     rcx, [rsp+98h+var_30]
0x14001b863  xor     rcx, rsp; StackCookie
0x14001b866  call    __security_check_cookie
0x14001b86b  add     rsp, 78h
0x14001b86f  pop     r14
0x14001b871  pop     rdi
0x14001b872  pop     rsi
0x14001b873  pop     rbx
0x14001b874  retn
0x14001b876  lea     rcx, [rbx+1E8h]; Timer
0x14001b87d  call    cs:__imp_KeInitializeTimer
0x14001b884  nop     dword ptr [rax+rax+00h]
0x14001b889  lea     rcx, [rbx+228h]; Dpc
0x14001b890  mov     r8, rbx; DeferredContext
0x14001b893  lea     rdx, WinNatSessionTimerDpc; DeferredRoutine
0x14001b89a  call    cs:__imp_KeInitializeDpc
0x14001b8a1  nop     dword ptr [rax+rax+00h]
0x14001b8a6  mov     rcx, [rbx+1D8h]
0x14001b8ad  mov     r9d, 1
0x14001b8b3  mov     r8d, r9d
0x14001b8b6  mov     [rsp+98h+var_78], 0
0x14001b8be  mov     edx, edi
0x14001b8c0  call    cs:__imp_RtlInitializeTimerWheel
0x14001b8c7  nop     dword ptr [rax+rax+00h]
0x14001b8cc  test    al, al
0x14001b8ce  jz      short loc_14001B859
0x14001b8d0  mov     dword ptr [rbx+268h], 0
0x14001b8da  mov     rcx, 0FFFFF78000000008h
0x14001b8e4  mov     rax, 346DC5D63886594Bh
0x14001b8ee  mov     rcx, [rcx]
0x14001b8f1  mul     rcx
0x14001b8f4  mov     rax, 624DD2F1A9FBE77h
0x14001b8fe  mov     rcx, rdx
0x14001b901  shr     rcx, 0Bh
0x14001b905  mul     rcx
0x14001b908  sub     rcx, rdx
0x14001b90b  shr     rcx, 1
0x14001b90e  add     rdx, rcx
0x14001b911  mov     rcx, [rbx+1D8h]
0x14001b918  shr     rdx, 9
0x14001b91c  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14001b923  nop     dword ptr [rax+rax+00h]
0x14001b928  mov     al, [rbx+274h]
0x14001b92e  lea     rdx, [rsp+98h+SystemInformation]; SystemInformation
0x14001b933  add     sil, sil
0x14001b936  xor     r9d, r9d; ReturnLength
0x14001b939  xor     sil, al
0x14001b93c  mov     ecx, 0B8h; SystemInformationClass
0x14001b941  and     sil, 2
0x14001b945  xor     sil, al
0x14001b948  lea     r8d, [r9+18h]; SystemInformationLength
0x14001b94c  mov     [rbx+274h], sil
0x14001b953  call    cs:__imp_ZwQuerySystemInformation
0x14001b95a  nop     dword ptr [rax+rax+00h]
0x14001b95f  test    eax, eax
0x14001b961  jns     short loc_14001B96A
0x14001b963  mov     eax, 40000h
0x14001b968  jmp     short loc_14001B973
0x14001b96a  mov     rax, qword ptr [rsp+98h+SystemInformation]
0x14001b96f  shr     rax, 6
0x14001b973  mov     cs:SessionSizeLimit, rax
0x14001b97a  xor     eax, eax
0x14001b97c  mov     cs:SessionLimitEventLoggedTick, 0
0x14001b986  jmp     loc_14001B85E
```
