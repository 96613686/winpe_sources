# EnableIdleTimer

- ea: `0x140006834`
- end: `0x140006af0`
- name: `EnableIdleTimer`
- size: `700`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x140004f50`
- `0x140005bb0`
- `0x140006630`
- `0x140006d40`
- `0x14000dc18`
- `0x140014040`
- `0x140028800`
- `0x140028f7c`
- `0x14002d86c`

## callees

- `0x140006834`
- `0x140007020`
- `0x140008040`
- `0x1400088b4`
- `0x14000fa04`
- `0x140013d4c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400068e4`
- `ntoskrnl!KeReleaseMutex` at `0x1400068e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000688e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006a69`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000688e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006a69`
- `ntoskrnl!DbgPrint` at `0x140006a3c`
- `ntoskrnl!DbgPrint` at `0x140006a3c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140006991`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140006991`

## string_xrefs

- `0x140006a2d`: `\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n`

## pseudocode

```c
int __fastcall EnableIdleTimer(__int64 a1, char a2, int a3)
{
  _UNKNOWN **v3; // rax
  char v4; // si
  char v5; // bp
  __int64 v7; // r14
  struct _KMUTANT *v8; // r15
  int v9; // ebx
  NTSTATUS v10; // eax
  int v11; // r8d
  const char *v12; // rdx
  NTSTATUS v13; // ecx
  int v14; // ecx
  __int64 v15; // rsi
  int v16; // edx
  int v17; // r8d
  int Timeout; // [rsp+20h] [rbp-78h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h] BYREF
  union _LARGE_INTEGER v21; // [rsp+A0h] [rbp+8h] BYREF
  char v22; // [rsp+A8h] [rbp+10h]
  int v23; // [rsp+B0h] [rbp+18h]

  v3 = &retaddr;
  v23 = a3;
  v22 = a2;
  v4 = a3;
  v5 = a2;
  if ( *(_BYTE *)(a1 + 1376) == 1 )
    return (int)v3;
  v7 = *(_QWORD *)(a1 + 1368);
  v8 = (struct _KMUTANT *)(a1 + 904);
  v21.QuadPart = -600000000;
  v9 = 0;
  v10 = KeWaitForSingleObject((PVOID)(a1 + 904), Executive, 0, 0, &v21);
  v12 = "idleTimerStateMutex";
  v13 = v10;
  if ( v10 == 258 )
  {
    do
    {
      DbgPrint(
        "\nUSBCCGP Watchdog: Thread 0x%p has waited %d minutes waiting to acquire %s\n",
        KeGetCurrentThread(),
        ++v9,
        "idleTimerStateMutex");
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qds(v7, v16, v17, 63, Timeout, (char)KeGetCurrentThread(), v9, (__int64)"idleTimerStateMutex");
      v13 = KeWaitForSingleObject(v8, Executive, 0, 0, &v21);
    }
    while ( v13 == 258 );
    v5 = v22;
    v12 = "idleTimerStateMutex";
  }
  if ( v13 >= 0 )
    goto LABEL_4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_dqs(
      v7,
      (unsigned int)"idleTimerStateMutex",
      v11,
      64,
      Timeout,
      v13,
      (char)KeGetCurrentThread(),
      (__int64)"idleTimerStateMutex");
LABEL_4:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qccccqd(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)v12,
        v11,
        56,
        Timeout,
        *(_QWORD *)(a1 + 32),
        SHIBYTE(v23),
        SBYTE2(v23),
        SBYTE1(v23),
        v4,
        (char)retaddr,
        *(_DWORD *)(a1 + 896));
  }
  if ( !v5 || _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 896), 0xFFFFFFFF) == 1 )
  {
    v14 = *(_DWORD *)(a1 + 856);
    if ( (unsigned int)(v14 - 2) <= 1 )
    {
      *(_DWORD *)(a1 + 856) = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 4;
        WPP_RECORDER_SF_qLL(
          *(_QWORD *)(a1 + 1368),
          (_DWORD)v12,
          7,
          57,
          (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
          *(_QWORD *)(a1 + 32),
          v14,
          1);
      }
      v15 = *(unsigned int *)(a1 + 864);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 4;
        WPP_RECORDER_SF_(
          *(_QWORD *)(a1 + 1368),
          (_DWORD)v12,
          7,
          53,
          (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
      }
      KeSetCoalescableTimer((PKTIMER)(a1 + 704), (LARGE_INTEGER)(-10000 * v15), v15, 0x1F4u, (PKDPC)(a1 + 792));
    }
  }
  LODWORD(v3) = KeReleaseMutex(v8, 0);
  return (int)v3;
}

```

## disassembly

```asm
0x140006834  mov     rax, rsp
0x140006837  mov     [rax+18h], r8d
0x14000683b  mov     [rax+10h], dl
0x14000683e  push    rbx
0x14000683f  push    rbp
0x140006840  push    rsi
0x140006841  push    rdi
0x140006842  push    r13
0x140006844  push    r14
0x140006846  push    r15
0x140006848  sub     rsp, 60h
0x14000684c  cmp     byte ptr [rcx+560h], 1
0x140006853  mov     esi, r8d
0x140006856  mov     bpl, dl
0x140006859  mov     rdi, rcx
0x14000685c  jz      loc_1400068F0
0x140006862  mov     r14, [rcx+558h]
0x140006869  lea     r15, [rcx+388h]
0x140006870  mov     qword ptr [rax+8], 0FFFFFFFFDC3CBA00h
0x140006878  lea     rax, [rax+8]
0x14000687c  mov     rcx, r15; Object
0x14000687f  mov     [rsp+98h+Timeout], rax; Timeout
0x140006884  xor     r9d, r9d; Alertable
0x140006887  xor     r8d, r8d; WaitMode
0x14000688a  xor     edx, edx; WaitReason
0x14000688c  xor     ebx, ebx
0x14000688e  call    cs:__imp_KeWaitForSingleObject
0x140006895  nop     dword ptr [rax+rax+00h]
0x14000689a  lea     rdx, aIdletimerstate; "idleTimerStateMutex"
0x1400068a1  mov     ecx, eax
0x1400068a3  lea     r13, WPP_RECORDER_INITIALIZED
0x1400068aa  cmp     eax, 102h
0x1400068af  jz      loc_140006A1D
0x1400068b5  test    ecx, ecx
0x1400068b7  js      loc_140006AB9
0x1400068bd  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400068c4  jnz     loc_1400069C0
0x1400068ca  test    bpl, bpl
0x1400068cd  jz      short loc_140006900
0x1400068cf  or      eax, 0FFFFFFFFh
0x1400068d2  lock xadd [rdi+380h], eax
0x1400068da  cmp     eax, 1
0x1400068dd  jz      short loc_140006900
0x1400068df  xor     edx, edx; Wait
0x1400068e1  mov     rcx, r15; Mutex
0x1400068e4  call    cs:__imp_KeReleaseMutex
0x1400068eb  nop     dword ptr [rax+rax+00h]
0x1400068f0  add     rsp, 60h
0x1400068f4  pop     r15
0x1400068f6  pop     r14
0x1400068f8  pop     r13
0x1400068fa  pop     rdi
0x1400068fb  pop     rsi
0x1400068fc  pop     rbp
0x1400068fd  pop     rbx
0x1400068fe  retn
0x140006900  mov     ecx, [rdi+358h]
0x140006906  lea     eax, [rcx-2]
0x140006909  cmp     eax, 1
0x14000690c  ja      short loc_1400068DF
0x14000690e  mov     dword ptr [rdi+358h], 1
0x140006918  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000691f  lea     r14, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140006926  mov     ebp, 7
0x14000692b  jz      short loc_14000695C
0x14000692d  mov     rax, [rdi+20h]
0x140006931  lea     r9d, [rbp+32h]
0x140006935  mov     dword ptr [rsp+98h+var_60], 1
0x14000693d  mov     r8d, ebp
0x140006940  mov     dword ptr [rsp+98h+var_68], ecx
0x140006944  mov     dl, 4
0x140006946  mov     rcx, [rdi+558h]
0x14000694d  mov     [rsp+98h+var_70], rax
0x140006952  mov     [rsp+98h+Timeout], r14
0x140006957  call    WPP_RECORDER_SF_qLL
0x14000695c  mov     esi, [rdi+360h]
0x140006962  imul    rbx, rsi, 0FFFFFFFFFFFFD8F0h
0x140006969  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140006970  jnz     short loc_1400069A2
0x140006972  lea     rax, [rdi+318h]
0x140006979  mov     r9d, 1F4h; TolerableDelay
0x14000697f  lea     rcx, [rdi+2C0h]; Timer
0x140006986  mov     [rsp+98h+Timeout], rax; Dpc
0x14000698b  mov     r8d, esi; Period
0x14000698e  mov     rdx, rbx; DueTime
0x140006991  call    cs:__imp_KeSetCoalescableTimer
0x140006998  nop     dword ptr [rax+rax+00h]
0x14000699d  jmp     loc_1400068DF
0x1400069a2  mov     rcx, [rdi+558h]
0x1400069a9  mov     r9d, 35h ; '5'
0x1400069af  mov     r8d, ebp
0x1400069b2  mov     [rsp+98h+Timeout], r14
0x1400069b7  mov     dl, 4
0x1400069b9  call    WPP_RECORDER_SF_
0x1400069be  jmp     short loc_140006972
0x1400069c0  mov     eax, [rdi+380h]
0x1400069c6  mov     r9d, 38h ; '8'
0x1400069cc  mov     rcx, [rsp+98h]
0x1400069d4  mov     [rsp+98h+var_40], eax
0x1400069d8  mov     al, [rsp+98h+arg_11]
0x1400069df  mov     [rsp+98h+var_48], rcx
0x1400069e4  mov     rcx, [rdi+558h]
0x1400069eb  mov     [rsp+98h+var_50], sil
0x1400069f0  mov     [rsp+98h+var_58], al
0x1400069f4  mov     al, [rsp+98h+arg_12]
0x1400069fb  mov     byte ptr [rsp+98h+var_60], al
0x1400069ff  mov     al, [rsp+98h+arg_13]
0x140006a06  mov     byte ptr [rsp+98h+var_68], al
0x140006a0a  mov     rax, [rdi+20h]
0x140006a0e  mov     [rsp+98h+var_70], rax
0x140006a13  call    WPP_RECORDER_SF_qccccqd
0x140006a18  jmp     loc_1400068CA
0x140006a1d  lea     rbp, aIdletimerstate; "idleTimerStateMutex"
0x140006a24  mov     rdx, gs:188h
0x140006a2d  lea     rcx, Format; "\nUSBCCGP Watchdog: Thread 0x%p has wai"...
0x140006a34  inc     ebx
0x140006a36  mov     r9, rbp
0x140006a39  mov     r8d, ebx
0x140006a3c  call    cs:__imp_DbgPrint
0x140006a43  nop     dword ptr [rax+rax+00h]
0x140006a48  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140006a4f  jnz     short loc_140006A92
0x140006a51  lea     rax, [rsp+98h+arg_0]
0x140006a59  xor     r9d, r9d; Alertable
0x140006a5c  xor     r8d, r8d; WaitMode
0x140006a5f  mov     [rsp+98h+Timeout], rax; Timeout
0x140006a64  xor     edx, edx; WaitReason
0x140006a66  mov     rcx, r15; Object
0x140006a69  call    cs:__imp_KeWaitForSingleObject
0x140006a70  nop     dword ptr [rax+rax+00h]
0x140006a75  mov     ecx, eax
0x140006a77  cmp     eax, 102h
0x140006a7c  jz      short loc_140006A24
0x140006a7e  mov     bpl, [rsp+98h+arg_8]
0x140006a86  lea     rdx, aIdletimerstate; "idleTimerStateMutex"
0x140006a8d  jmp     loc_1400068B5
0x140006a92  mov     rax, gs:188h
0x140006a9b  mov     r9d, 3Fh ; '?'
0x140006aa1  mov     [rsp+98h+var_60], rbp
0x140006aa6  mov     rcx, r14
0x140006aa9  mov     dword ptr [rsp+98h+var_68], ebx
0x140006aad  mov     [rsp+98h+var_70], rax
0x140006ab2  call    WPP_RECORDER_SF_qds
0x140006ab7  jmp     short loc_140006A51
0x140006ab9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140006ac0  jz      loc_1400068CA
0x140006ac6  mov     rax, gs:188h
0x140006acf  mov     r9d, 40h ; '@'
0x140006ad5  mov     [rsp+98h+var_60], rdx
0x140006ada  mov     [rsp+98h+var_68], rax
0x140006adf  mov     dword ptr [rsp+98h+var_70], ecx
0x140006ae3  mov     rcx, r14
0x140006ae6  call    WPP_RECORDER_SF_dqs
0x140006aeb  jmp     loc_1400068BD
```
