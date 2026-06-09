# DispatchFdoQueryPower

- ea: `0x14000b670`
- end: `0x14000b8c3`
- name: `DispatchFdoQueryPower`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003e88`

## callees

- `0x1400054a0`
- `0x140005940`
- `0x140006af8`
- `0x140006d40`
- `0x1400083c8`
- `0x14000b670`
- `0x14000b8cc`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x14000b7f0`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000b7f0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b833`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000b833`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b70a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b70a`
- `ntoskrnl!PoCallDriver` at `0x14000b78c`
- `ntoskrnl!PoCallDriver` at `0x14000b80a`
- `ntoskrnl!PoCallDriver` at `0x14000b78c`
- `ntoskrnl!PoCallDriver` at `0x14000b80a`

## pseudocode

```c
__int64 __fastcall DispatchFdoQueryPower(__int64 a1, IRP *a2, int a3)
{
  $CED46D45A6A8A9547B35CF2807CA28C5 *v3; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int Options; // edx
  _LARGE_INTEGER *p_ByteOffset; // r14
  _QWORD *v9; // rbp
  KIRQL v10; // al
  unsigned int v11; // ecx
  char v12; // r14
  __int64 v13; // rdx
  $CED46D45A6A8A9547B35CF2807CA28C5 *v14; // rax
  _IO_STACK_LOCATION *v15; // rax
  unsigned int v16; // esi

  v3 = &a2->Tail.Overlay.64;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options )
  {
    if ( Options == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qqL(*(_QWORD *)(a1 + 1368), 1, a3, 46);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Options) = 2;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 1368),
        Options,
        8,
        47,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a1 + 32));
    }
    PoStartNextPowerIrp(a2);
    ++a2->CurrentLocation;
    ++v3->CurrentStackLocation;
    v16 = PoCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), a2);
    UsbcReleaseRemoveLock(a1, a2);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a2, 0x20u);
  }
  else
  {
    p_ByteOffset = &CurrentStackLocation->Parameters.Read.ByteOffset;
    v9 = (_QWORD *)(a1 + 1368);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qqL(*v9, 0, a3, 45);
    if ( p_ByteOffset->LowPart == 1 )
    {
      v14 = v3;
    }
    else
    {
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 344));
      v11 = *(_DWORD *)(a1 + 1228);
      if ( (v11 & 4) != 0 )
      {
        v11 = v11 & 0xFFFFFFFA | 1;
        *(_DWORD *)(a1 + 1228) = v11;
      }
      if ( (v11 & 1) != 0 )
      {
        v12 = 0;
      }
      else
      {
        v12 = 1;
        *(_DWORD *)(a1 + 1228) = v11 | 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 344), v10);
      if ( v12 )
        DisableIdleTimer(a1, v13, 1347506260);
      LOBYTE(v13) = 1;
      CancelFdoIdleIrp(a1, v13);
      v14 = &a2->Tail.Overlay.64;
    }
    v15 = v14->CurrentStackLocation;
    *(_OWORD *)&v15[-1].MajorFunction = *(_OWORD *)&v15->MajorFunction;
    *(_OWORD *)&v15[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v15->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v15[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v15->Parameters.SetQuota + 6);
    v15[-1].FileObject = v15->FileObject;
    v15[-1].Control = 0;
    SetCompletionRoutine(
      *v9,
      *(struct _DEVICE_OBJECT **)(a1 + 32),
      a2,
      (IO_COMPLETION_ROUTINE *)CompletionFdoSystemQueryPower,
      (PVOID)a1);
    v3->CurrentStackLocation->Control |= 1u;
    PoCallDriver(*(PDEVICE_OBJECT *)(a1 + 40), a2);
    return 259;
  }
  return v16;
}

```

## disassembly

```asm
0x14000b670  push    rbx
0x14000b672  push    rbp
0x14000b673  push    rsi
0x14000b674  push    rdi
0x14000b675  push    r12
0x14000b677  push    r14
0x14000b679  push    r15
0x14000b67b  sub     rsp, 40h
0x14000b67f  lea     rsi, [rdx+0B8h]
0x14000b686  mov     rbx, rcx
0x14000b689  mov     rcx, [rsi]
0x14000b68c  mov     rdi, rdx
0x14000b68f  mov     edx, [rcx+10h]
0x14000b692  test    edx, edx
0x14000b694  jnz     loc_14000B7AF
0x14000b69a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b6a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b6a8  lea     r14, [rcx+18h]
0x14000b6ac  lea     rbp, [rbx+558h]
0x14000b6b3  jnz     loc_14000B84C
0x14000b6b9  cmp     dword ptr [r14], 1
0x14000b6bd  jz      loc_14000B844
0x14000b6c3  lea     r12, [rbx+158h]
0x14000b6ca  mov     rcx, r12; SpinLock
0x14000b6cd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b6d4  nop     dword ptr [rax+rax+00h]
0x14000b6d9  mov     ecx, [rbx+4CCh]
0x14000b6df  test    cl, 4
0x14000b6e2  jz      short loc_14000B6F0
0x14000b6e4  and     ecx, 0FFFFFFFBh
0x14000b6e7  or      ecx, 1
0x14000b6ea  mov     [rbx+4CCh], ecx
0x14000b6f0  test    cl, 1
0x14000b6f3  jnz     loc_14000B875
0x14000b6f9  or      ecx, 1
0x14000b6fc  mov     r14b, 1
0x14000b6ff  mov     [rbx+4CCh], ecx
0x14000b705  mov     dl, al; NewIrql
0x14000b707  mov     rcx, r12; SpinLock
0x14000b70a  call    cs:__imp_KeReleaseSpinLock
0x14000b711  nop     dword ptr [rax+rax+00h]
0x14000b716  test    r14b, r14b
0x14000b719  jz      short loc_14000B729
0x14000b71b  mov     r8d, 50515054h
0x14000b721  mov     rcx, rbx
0x14000b724  call    DisableIdleTimer
0x14000b729  mov     dl, 1
0x14000b72b  mov     rcx, rbx
0x14000b72e  call    CancelFdoIdleIrp
0x14000b733  lea     rax, [rdi+0B8h]
0x14000b73a  mov     rax, [rax]
0x14000b73d  lea     r9, CompletionFdoSystemQueryPower
0x14000b744  mov     r8, rdi
0x14000b747  mov     [rsp+78h+var_58], rbx
0x14000b74c  movups  xmm0, xmmword ptr [rax]
0x14000b74f  movups  xmmword ptr [rax-48h], xmm0
0x14000b753  movups  xmm1, xmmword ptr [rax+10h]
0x14000b757  movups  xmmword ptr [rax-38h], xmm1
0x14000b75b  movups  xmm0, xmmword ptr [rax+20h]
0x14000b75f  movups  xmmword ptr [rax-28h], xmm0
0x14000b763  movsd   xmm1, qword ptr [rax+30h]
0x14000b768  movsd   qword ptr [rax-18h], xmm1
0x14000b76d  mov     byte ptr [rax-45h], 0
0x14000b771  mov     rdx, [rbx+20h]
0x14000b775  mov     rcx, [rbp+0]
0x14000b779  call    SetCompletionRoutine
0x14000b77e  mov     rax, [rsi]
0x14000b781  mov     rdx, rdi; Irp
0x14000b784  or      byte ptr [rax+3], 1
0x14000b788  mov     rcx, [rbx+28h]; DeviceObject
0x14000b78c  call    cs:__imp_PoCallDriver
0x14000b793  nop     dword ptr [rax+rax+00h]
0x14000b798  mov     esi, 103h
0x14000b79d  mov     eax, esi
0x14000b79f  add     rsp, 40h
0x14000b7a3  pop     r15
0x14000b7a5  pop     r14
0x14000b7a7  pop     r12
0x14000b7a9  pop     rdi
0x14000b7aa  pop     rsi
0x14000b7ab  pop     rbp
0x14000b7ac  pop     rbx
0x14000b7ad  retn
0x14000b7af  cmp     edx, 1
0x14000b7b2  jnz     loc_14000B87D
0x14000b7b8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b7bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b7c6  jz      short loc_14000B7ED
0x14000b7c8  mov     eax, [rcx+18h]
0x14000b7cb  lea     r9d, [rdx+2Dh]
0x14000b7cf  mov     rcx, [rbx+558h]
0x14000b7d6  mov     [rsp+78h+var_40], eax
0x14000b7da  mov     rax, [rbx+20h]
0x14000b7de  mov     [rsp+78h+var_48], rdi
0x14000b7e3  mov     [rsp+78h+var_50], rax
0x14000b7e8  call    WPP_RECORDER_SF_qqL
0x14000b7ed  mov     rcx, rdi; Irp
0x14000b7f0  call    cs:__imp_PoStartNextPowerIrp
0x14000b7f7  nop     dword ptr [rax+rax+00h]
0x14000b7fc  inc     byte ptr [rdi+43h]
0x14000b7ff  mov     rdx, rdi; Irp
0x14000b802  add     qword ptr [rsi], 48h ; 'H'
0x14000b806  mov     rcx, [rbx+28h]; DeviceObject
0x14000b80a  call    cs:__imp_PoCallDriver
0x14000b811  nop     dword ptr [rax+rax+00h]
0x14000b816  mov     rdx, rdi
0x14000b819  mov     rcx, rbx
0x14000b81c  mov     esi, eax
0x14000b81e  call    UsbcReleaseRemoveLock
0x14000b823  lea     rcx, [rbx+0C8h]; RemoveLock
0x14000b82a  mov     r8d, 20h ; ' '; RemlockSize
0x14000b830  mov     rdx, rdi; Tag
0x14000b833  call    cs:__imp_IoReleaseRemoveLockEx
0x14000b83a  nop     dword ptr [rax+rax+00h]
0x14000b83f  jmp     loc_14000B79D
0x14000b844  mov     rax, rsi
0x14000b847  jmp     loc_14000B73A
0x14000b84c  mov     eax, [r14]
0x14000b84f  mov     r9d, 2Dh ; '-'
0x14000b855  mov     rcx, [rbp+0]
0x14000b859  mov     [rsp+78h+var_40], eax
0x14000b85d  mov     rax, [rbx+20h]
0x14000b861  mov     [rsp+78h+var_48], rdi
0x14000b866  mov     [rsp+78h+var_50], rax
0x14000b86b  call    WPP_RECORDER_SF_qqL
0x14000b870  jmp     loc_14000B6B9
0x14000b875  xor     r14b, r14b
0x14000b878  jmp     loc_14000B705
0x14000b87d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000b884  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b88b  jz      loc_14000B7ED
0x14000b891  mov     rax, [rbx+20h]
0x14000b895  mov     r9d, 2Fh ; '/'
0x14000b89b  mov     rcx, [rbx+558h]
0x14000b8a2  mov     dl, 2
0x14000b8a4  mov     [rsp+78h+var_50], rax
0x14000b8a9  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000b8b0  mov     [rsp+78h+var_58], rax
0x14000b8b5  lea     r8d, [r9-27h]
0x14000b8b9  call    WPP_RECORDER_SF_q
0x14000b8be  jmp     loc_14000B7ED
```
