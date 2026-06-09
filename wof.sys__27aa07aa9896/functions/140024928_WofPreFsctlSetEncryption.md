# WofPreFsctlSetEncryption

- ea: `0x140024928`
- end: `0x140024b8a`
- name: `WofPreFsctlSetEncryption`
- size: `610`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140034740`

## callees

- `0x140009910`
- `0x14000a914`
- `0x140011640`
- `0x14002306c`
- `0x140024928`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400249ea`
- `ntoskrnl!ProbeForRead` at `0x1400249ea`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003f14c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003f14c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024b2a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140024b2a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140024aba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140024aba`
- `FLTMGR!FltGetStreamContext` at `0x140024964`
- `FLTMGR!FltGetStreamContext` at `0x140024964`
- `FLTMGR!FltReleaseContext` at `0x1400249c7`
- `FLTMGR!FltReleaseContext` at `0x140024a93`
- `FLTMGR!FltReleaseContext` at `0x140024b6b`
- `FLTMGR!FltReleaseContext` at `0x1400249c7`
- `FLTMGR!FltReleaseContext` at `0x140024a93`
- `FLTMGR!FltReleaseContext` at `0x140024b6b`

## pseudocode

```c
__int64 __fastcall WofPreFsctlSetEncryption(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int StreamContext; // eax
  NTSTATUS v4; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int *Parameters; // r12
  SIZE_T Options; // r13
  unsigned int v9; // r14d
  int ULongFromUser; // r15d
  NTSTATUS IsDataAlternateStream; // eax
  NTSTATUS v12; // eax
  PFLT_CONTEXT v13; // rcx
  __int64 (__fastcall *v14)(__int64, char *, int *, _QWORD); // rax
  NTSTATUS v15; // eax
  PFLT_CONTEXT Context[10]; // [rsp+38h] [rbp-50h] BYREF

  Context[0] = 0;
  StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), Context);
  v4 = StreamContext;
  if ( StreamContext < 0 )
  {
    if ( StreamContext == -1073741275 )
      return 1;
    CallbackData->IoStatus.Status = StreamContext;
    return 4;
  }
  Iopb = CallbackData->Iopb;
  Parameters = (int *)Iopb->Parameters.CreatePipe.Parameters;
  Context[2] = Parameters;
  Options = Iopb->Parameters.Create.Options;
  if ( (unsigned int)Options < 8 )
  {
    CallbackData->IoStatus.Status = -1073741789;
LABEL_8:
    FltReleaseContext(Context[0]);
    return 4;
  }
  v9 = 1;
  if ( CallbackData->RequestorMode && (ProbeForRead(Parameters, Options, 1u), CallbackData->RequestorMode) )
    ULongFromUser = RtlReadULongFromUser(Parameters);
  else
    ULongFromUser = *Parameters;
  if ( v4 < 0 )
  {
    CallbackData->IoStatus.Status = v4;
    goto LABEL_8;
  }
  IsDataAlternateStream = WofIsDataAlternateStream(CallbackData);
  if ( IsDataAlternateStream < 0 )
  {
    CallbackData->IoStatus.Status = IsDataAlternateStream;
    goto LABEL_8;
  }
  if ( ULongFromUser == 4 )
  {
    v12 = WofEnsureExtdFileContext(*(_QWORD *)Context[0]);
    v13 = Context[0];
    if ( v12 < 0 )
    {
LABEL_19:
      CallbackData->IoStatus.Status = v12;
      FltReleaseContext(v13);
      return 4;
    }
    WofEnsureExtdFileContext(*(_QWORD *)Context[0]);
    ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context[0] + 16LL));
    if ( (*((_DWORD *)Context[0] + 2) & 4) == 0 || (*((_DWORD *)Context[0] + 2) & 0x20) != 0 )
    {
      v14 = (__int64 (__fastcall *)(__int64, char *, int *, _QWORD))qword_14001A2D8[53
                                                                                  * *((unsigned int *)Context[0] + 3)];
      if ( v14 )
      {
        v15 = v14(a2, (char *)Context[0] + 64, Parameters, (unsigned int)Options);
        CallbackData->IoStatus.Status = v15;
        if ( v15 < 0 )
          v9 = 4;
      }
    }
    ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context[0] + 16LL));
  }
  else if ( ULongFromUser == 3 )
  {
    v12 = WofEnsureExtdFileContext(*(_QWORD *)Context[0]);
    if ( v12 < 0 )
    {
      v13 = Context[0];
      goto LABEL_19;
    }
    v9 = 0;
  }
  FltReleaseContext(Context[0]);
  return v9;
}

```

## disassembly

```asm
0x140024928  mov     r11, rsp
0x14002492b  mov     [r11+18h], r8
0x14002492f  mov     [r11+10h], rdx
0x140024933  mov     [r11+8], rcx
0x140024937  push    rbx
0x140024938  push    rsi
0x140024939  push    r12
0x14002493b  push    r13
0x14002493d  push    r14
0x14002493f  push    r15
0x140024941  sub     rsp, 58h
0x140024945  mov     rax, rdx
0x140024948  mov     rsi, rcx
0x14002494b  mov     qword ptr [r11-50h], 0
0x140024953  mov     byte ptr [r11+18h], 0
0x140024958  lea     r8, [r11-50h]; Context
0x14002495c  mov     rdx, [rdx+20h]; FileObject
0x140024960  mov     rcx, [rax+18h]; Instance
0x140024964  call    cs:__imp_FltGetStreamContext
0x14002496b  nop     dword ptr [rax+rax+00h]
0x140024970  mov     ebx, eax
0x140024972  test    eax, eax
0x140024974  jns     short loc_140024994
0x140024976  cmp     eax, 0C0000225h
0x14002497b  jnz     short loc_140024987
0x14002497d  mov     eax, 1
0x140024982  jmp     loc_140024B7A
0x140024987  mov     [rsi+18h], eax
0x14002498a  mov     eax, 4
0x14002498f  jmp     loc_140024B7A
0x140024994  mov     [rsp+88h+var_58], 0
0x14002499c  mov     rax, [rsi+10h]
0x1400249a0  mov     r12, [rax+30h]
0x1400249a4  mov     [rsp+88h+var_40], r12
0x1400249a9  mov     r13d, [rax+20h]
0x1400249ad  mov     [rsp+88h+arg_18], r13d
0x1400249b5  cmp     r13d, 8
0x1400249b9  jnb     short loc_1400249D5
0x1400249bb  mov     dword ptr [rsi+18h], 0C0000023h
0x1400249c2  mov     rcx, [rsp+88h+Context]; Context
0x1400249c7  call    cs:__imp_FltReleaseContext
0x1400249ce  nop     dword ptr [rax+rax+00h]
0x1400249d3  jmp     short loc_14002498A
0x1400249d5  mov     r14d, 1
0x1400249db  cmp     byte ptr [rsi+50h], 0
0x1400249df  jz      short loc_140024A09
0x1400249e1  mov     rdx, r13; Length
0x1400249e4  mov     r8d, r14d; Alignment
0x1400249e7  mov     rcx, r12; Address
0x1400249ea  call    cs:__imp_ProbeForRead
0x1400249f1  nop     dword ptr [rax+rax+00h]
0x1400249f6  cmp     byte ptr [rsi+50h], 0
0x1400249fa  jz      short loc_140024A09
0x1400249fc  mov     rcx, r12
0x1400249ff  call    RtlReadULongFromUser
0x140024a04  mov     r15d, eax
0x140024a07  jmp     short loc_140024A0D
0x140024a09  mov     r15d, [r12]
0x140024a0d  mov     [rsp+88h+var_58], r15d
0x140024a12  jmp     short loc_140024A39
0x140024a14  mov     ebx, 0C00000E8h
0x140024a19  mov     r14d, 1
0x140024a1f  mov     rsi, [rsp+88h+arg_0]
0x140024a27  mov     r15d, [rsp+88h+var_58]
0x140024a2c  mov     r12, [rsp+88h+var_40]
0x140024a31  mov     r13d, [rsp+88h+arg_18]
0x140024a39  test    ebx, ebx
0x140024a3b  jns     short loc_140024A42
0x140024a3d  mov     [rsi+18h], ebx
0x140024a40  jmp     short loc_1400249C2
0x140024a42  lea     rdx, [rsp+88h+arg_10]
0x140024a4a  mov     rcx, rsi; CallbackData
0x140024a4d  call    WofIsDataAlternateStream
0x140024a52  test    eax, eax
0x140024a54  jns     short loc_140024A5E
0x140024a56  mov     [rsi+18h], eax
0x140024a59  jmp     loc_1400249C2
0x140024a5e  mov     ebx, 4
0x140024a63  cmp     r15d, ebx
0x140024a66  jnz     loc_140024B38
0x140024a6c  cmp     [rsp+88h+arg_10], 0
0x140024a74  jnz     loc_140024B38
0x140024a7a  mov     rcx, [rsp+88h+Context]
0x140024a7f  mov     rcx, [rcx]
0x140024a82  call    WofEnsureExtdFileContext
0x140024a87  mov     rcx, [rsp+88h+Context]; Context
0x140024a8c  test    eax, eax
0x140024a8e  jns     short loc_140024AA6
0x140024a90  mov     [rsi+18h], eax
0x140024a93  call    cs:__imp_FltReleaseContext
0x140024a9a  nop     dword ptr [rax+rax+00h]
0x140024a9f  mov     eax, ebx
0x140024aa1  jmp     loc_140024B7A
0x140024aa6  mov     rcx, [rcx]
0x140024aa9  call    WofEnsureExtdFileContext
0x140024aae  mov     rax, [rsp+88h+Context]
0x140024ab3  mov     rcx, [rax]
0x140024ab6  mov     rcx, [rcx+10h]; FastMutex
0x140024aba  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140024ac1  nop     dword ptr [rax+rax+00h]
0x140024ac6  mov     rax, [rsp+88h+Context]
0x140024acb  mov     ecx, [rax+8]
0x140024ace  test    bl, cl
0x140024ad0  jz      short loc_140024ADF
0x140024ad2  mov     rax, [rsp+88h+Context]
0x140024ad7  mov     ecx, [rax+8]
0x140024ada  test    cl, 20h
0x140024add  jz      short loc_140024B1E
0x140024adf  mov     rdx, [rsp+88h+Context]
0x140024ae4  mov     eax, [rdx+0Ch]
0x140024ae7  imul    rcx, rax, 1A8h
0x140024aee  lea     rax, qword_14001A2D8
0x140024af5  mov     rax, [rcx+rax]
0x140024af9  test    rax, rax
0x140024afc  jz      short loc_140024B1E
0x140024afe  add     rdx, 40h ; '@'
0x140024b02  mov     r9d, r13d
0x140024b05  mov     r8, r12
0x140024b08  mov     rcx, [rsp+88h+arg_8]
0x140024b10  call    _guard_dispatch_icall
0x140024b15  mov     [rsi+18h], eax
0x140024b18  test    eax, eax
0x140024b1a  cmovs   r14d, ebx
0x140024b1e  mov     rax, [rsp+88h+Context]
0x140024b23  mov     rcx, [rax]
0x140024b26  mov     rcx, [rcx+10h]; FastMutex
0x140024b2a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140024b31  nop     dword ptr [rax+rax+00h]
0x140024b36  jmp     short loc_140024B66
0x140024b38  cmp     r15d, 3
0x140024b3c  jnz     short loc_140024B66
0x140024b3e  cmp     [rsp+88h+arg_10], 0
0x140024b46  jnz     short loc_140024B66
0x140024b48  mov     rcx, [rsp+88h+Context]
0x140024b4d  mov     rcx, [rcx]
0x140024b50  call    WofEnsureExtdFileContext
0x140024b55  test    eax, eax
0x140024b57  jns     short loc_140024B63
0x140024b59  mov     rcx, [rsp+88h+Context]
0x140024b5e  jmp     loc_140024A90
0x140024b63  xor     r14d, r14d
0x140024b66  mov     rcx, [rsp+88h+Context]; Context
0x140024b6b  call    cs:__imp_FltReleaseContext
0x140024b72  nop     dword ptr [rax+rax+00h]
0x140024b77  mov     eax, r14d
0x140024b7a  add     rsp, 58h
0x140024b7e  pop     r15
0x140024b80  pop     r14
0x140024b82  pop     r13
0x140024b84  pop     r12
0x140024b86  pop     rsi
0x140024b87  pop     rbx
0x140024b88  retn
0x14003f136  push    rbp
0x14003f138  sub     rsp, 30h
0x14003f13c  mov     rbp, rdx
0x14003f13f  mov     [rbp+40h], rcx
0x14003f143  mov     rax, [rbp+40h]
0x14003f147  mov     rcx, [rax]
0x14003f14a  mov     ecx, [rcx]; Exception
0x14003f14c  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003f153  nop     dword ptr [rax+rax+00h]
0x14003f158  xor     ecx, ecx
0x14003f15a  test    al, al
0x14003f15c  setz    cl
0x14003f15f  mov     [rbp+34h], ecx
0x14003f162  mov     eax, [rbp+34h]
0x14003f165  add     rsp, 30h
0x14003f169  pop     rbp
0x14003f16a  retn
```
