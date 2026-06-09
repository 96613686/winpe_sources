# VsmmCloneIoctlTemplateDetach

- ea: `0x1400aec04`
- end: `0x1400aee36`
- name: `VsmmCloneIoctlTemplateDetach`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400377bc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x1400086d4`
- `0x14000a4e0`
- `0x140021650`
- `0x140034554`
- `0x140034914`
- `0x140038630`
- `0x140075afc`
- `0x1400aec04`
- `0x1400af7c8`
- `0x1400faca0`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400aecab`
- `ntoskrnl!PsSetCreateProcessNotifyRoutine` at `0x1400aecab`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400aed01`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400aed01`

## string_xrefs

- `0x1400aecca`: `VsmmCloneIoctlTemplateDetach`
- `0x1400aed49`: `VsmmCloneIoctlTemplateDetach`
- `0x1400aed95`: `VsmmCloneIoctlTemplateDetach`

## pseudocode

```c
__int64 __fastcall VsmmCloneIoctlTemplateDetach(__int64 a1, __int64 a2, _OWORD *a3)
{
  NTSTATUS ProcessNotifyRoutine; // ebx
  __int64 v7; // rax
  _QWORD *v8; // rdi
  __int64 v9; // r14
  _DWORD *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rbx
  int v14; // [rsp+30h] [rbp-69h] BYREF
  NTSTATUS v15; // [rsp+34h] [rbp-65h] BYREF
  char v16[32]; // [rsp+40h] [rbp-59h] BYREF
  char v17[16]; // [rsp+60h] [rbp-39h] BYREF
  char v18[16]; // [rsp+70h] [rbp-29h] BYREF
  int *v19; // [rsp+80h] [rbp-19h]
  __int64 v20; // [rsp+88h] [rbp-11h]
  NTSTATUS *v21; // [rsp+90h] [rbp-9h]
  __int64 v22; // [rsp+98h] [rbp-1h]
  __int64 v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]

  if ( (int)VidSidServiceCheck() >= 0 )
  {
    v7 = VidPartitionTableLookupAndReference(a1, a2, 0);
    v8 = (_QWORD *)v7;
    if ( !v7 )
    {
      ProcessNotifyRoutine = -1070137335;
      goto LABEL_15;
    }
    v9 = v7 + 3736;
    VidObjectLockAcquireExclusive(v7 + 3736);
    v10 = (_DWORD *)v8[1300];
    if ( !v10 || *v10 != 1 )
    {
      ProcessNotifyRoutine = -1073741811;
      VidTraceErrorInternal0("VsmmCloneIoctlTemplateDetach", "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c", 481);
LABEL_14:
      VidObjectLockRelease(v9);
      VidDereferencePartition(v8);
      if ( ProcessNotifyRoutine >= 0 )
        return (unsigned int)ProcessNotifyRoutine;
      goto LABEL_15;
    }
    v11 = a1 + 680;
    VidObjectLockAcquireExclusive(v11);
    if ( !*(_BYTE *)(v11 + 64) )
    {
      ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutine(VsmmClonepTableProcessNotifyRoutine, 0);
      if ( ProcessNotifyRoutine < 0 )
      {
        VidTraceErrorInternal0("VsmmCloneIoctlTemplateDetach", "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c", 495);
LABEL_12:
        VidObjectLockRelease(v11);
        goto LABEL_14;
      }
      *(_BYTE *)(v11 + 64) = 1;
    }
    *a3 = *(_OWORD *)(v8[1300] + 4LL);
    *(_DWORD *)v8[1300] = 2;
    v12 = v8[1300];
    *(_QWORD *)(v12 + 24) = PsGetCurrentProcessId();
    VsmmClonepTableInsertByOwningProcessId(v11, v8[1300]);
    ProcessNotifyRoutine = 0;
    v8[1300] = 0;
    goto LABEL_12;
  }
  ProcessNotifyRoutine = -1073741727;
LABEL_15:
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v17, "VsmmCloneIoctlTemplateDetach");
    tlgCreate1Sz_char(v18, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    v14 = 538;
    v19 = &v14;
    v20 = 4;
    v21 = &v15;
    v15 = ProcessNotifyRoutine;
    v22 = 4;
    v23 = a2;
    v24 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004E931, 0, 0, 7, v16);
  }
  return (unsigned int)ProcessNotifyRoutine;
}

```

## disassembly

```asm
0x1400aec04  push    rbp
0x1400aec06  push    rbx
0x1400aec07  push    rsi
0x1400aec08  push    rdi
0x1400aec09  push    r12
0x1400aec0b  push    r14
0x1400aec0d  push    r15
0x1400aec0f  lea     rbp, [rsp-27h]
0x1400aec14  sub     rsp, 0C0h
0x1400aec1b  mov     rax, cs:__security_cookie
0x1400aec22  xor     rax, rsp
0x1400aec25  mov     [rbp+57h+var_40], rax
0x1400aec29  mov     r12, r8
0x1400aec2c  mov     r15, rdx
0x1400aec2f  mov     rsi, rcx
0x1400aec32  call    VidSidServiceCheck
0x1400aec37  test    eax, eax
0x1400aec39  jns     short loc_1400AEC45
0x1400aec3b  mov     ebx, 0C0000061h
0x1400aec40  jmp     loc_1400AED6D
0x1400aec45  xor     r8d, r8d
0x1400aec48  mov     rdx, r15
0x1400aec4b  mov     rcx, rsi
0x1400aec4e  call    VidPartitionTableLookupAndReference
0x1400aec53  mov     rdi, rax
0x1400aec56  test    rax, rax
0x1400aec59  jnz     short loc_1400AEC65
0x1400aec5b  mov     ebx, 0C0370009h
0x1400aec60  jmp     loc_1400AED6D
0x1400aec65  lea     r14, [rax+0E98h]
0x1400aec6c  mov     rcx, r14
0x1400aec6f  call    VidObjectLockAcquireExclusive
0x1400aec74  mov     rax, [rdi+28A0h]
0x1400aec7b  test    rax, rax
0x1400aec7e  jz      loc_1400AED37
0x1400aec84  cmp     dword ptr [rax], 1
0x1400aec87  jnz     loc_1400AED37
0x1400aec8d  add     rsi, 2A8h
0x1400aec94  mov     rcx, rsi
0x1400aec97  call    VidObjectLockAcquireExclusive
0x1400aec9c  cmp     byte ptr [rsi+40h], 0
0x1400aeca0  jnz     short loc_1400AECDC
0x1400aeca2  xor     edx, edx; Remove
0x1400aeca4  lea     rcx, VsmmClonepTableProcessNotifyRoutine; NotifyRoutine
0x1400aecab  call    cs:__imp_PsSetCreateProcessNotifyRoutine
0x1400aecb2  nop     dword ptr [rax+rax+00h]
0x1400aecb7  mov     ebx, eax
0x1400aecb9  test    eax, eax
0x1400aecbb  jns     short loc_1400AECD8
0x1400aecbd  mov     r8d, 1EFh
0x1400aecc3  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400aecca  lea     rcx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400aecd1  call    VidTraceErrorInternal0
0x1400aecd6  jmp     short loc_1400AED2D
0x1400aecd8  mov     byte ptr [rsi+40h], 1
0x1400aecdc  mov     rax, [rdi+28A0h]
0x1400aece3  movups  xmm0, xmmword ptr [rax+4]
0x1400aece7  movdqu  xmmword ptr [r12], xmm0
0x1400aeced  mov     rax, [rdi+28A0h]
0x1400aecf4  mov     dword ptr [rax], 2
0x1400aecfa  mov     rbx, [rdi+28A0h]
0x1400aed01  call    cs:__imp_PsGetCurrentProcessId
0x1400aed08  nop     dword ptr [rax+rax+00h]
0x1400aed0d  mov     [rbx+18h], rax
0x1400aed11  mov     rcx, rsi
0x1400aed14  mov     rdx, [rdi+28A0h]
0x1400aed1b  call    VsmmClonepTableInsertByOwningProcessId
0x1400aed20  xor     ebx, ebx
0x1400aed22  mov     qword ptr [rdi+28A0h], 0
0x1400aed2d  mov     rcx, rsi
0x1400aed30  call    VidObjectLockRelease
0x1400aed35  jmp     short loc_1400AED55
0x1400aed37  mov     ebx, 0C000000Dh
0x1400aed3c  mov     r8d, 1E1h
0x1400aed42  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400aed49  lea     rcx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400aed50  call    VidTraceErrorInternal0
0x1400aed55  mov     rcx, r14
0x1400aed58  call    VidObjectLockRelease
0x1400aed5d  mov     rcx, rdi; P
0x1400aed60  call    VidDereferencePartition
0x1400aed65  test    ebx, ebx
0x1400aed67  jns     loc_1400AEE15
0x1400aed6d  mov     eax, cs:dword_140064110
0x1400aed73  cmp     eax, 2
0x1400aed76  jbe     loc_1400AEE15
0x1400aed7c  mov     edx, 100h
0x1400aed81  lea     rcx, dword_140064110
0x1400aed88  call    _tlgKeywordOn
0x1400aed8d  test    al, al
0x1400aed8f  jz      loc_1400AEE15
0x1400aed95  lea     rdx, aVsmmcloneioctl; "VsmmCloneIoctlTemplateDetach"
0x1400aed9c  lea     rcx, [rbp+57h+var_90]
0x1400aeda0  call    _tlgCreate1Sz_char
0x1400aeda5  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400aedac  lea     rcx, [rbp+57h+var_80]
0x1400aedb0  call    _tlgCreate1Sz_char
0x1400aedb5  lea     rax, [rbp+57h+var_C0]
0x1400aedb9  mov     [rbp+57h+var_C0], 21Ah
0x1400aedc0  mov     [rbp+57h+var_70], rax
0x1400aedc4  lea     rdx, byte_14004E931
0x1400aedcb  lea     rax, [rbp+57h+var_BC]
0x1400aedcf  mov     [rbp+57h+var_68], 4
0x1400aedd7  mov     [rbp+57h+var_60], rax
0x1400aeddb  lea     rcx, dword_140064110
0x1400aede2  lea     rax, [rbp+57h+var_B0]
0x1400aede6  mov     [rbp+57h+var_BC], ebx
0x1400aede9  mov     [rsp+0F0h+var_C8], rax
0x1400aedee  xor     r9d, r9d
0x1400aedf1  xor     r8d, r8d
0x1400aedf4  mov     [rsp+0F0h+var_D0], 7
0x1400aedfc  mov     [rbp+57h+var_58], 4
0x1400aee04  mov     [rbp+57h+var_50], r15
0x1400aee08  mov     [rbp+57h+var_48], 10h
0x1400aee10  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400aee15  mov     eax, ebx
0x1400aee17  mov     rcx, [rbp+57h+var_40]
0x1400aee1b  xor     rcx, rsp; StackCookie
0x1400aee1e  call    __security_check_cookie
0x1400aee23  add     rsp, 0C0h
0x1400aee2a  pop     r15
0x1400aee2c  pop     r14
0x1400aee2e  pop     r12
0x1400aee30  pop     rdi
0x1400aee31  pop     rsi
0x1400aee32  pop     rbx
0x1400aee33  pop     rbp
0x1400aee34  retn
```
