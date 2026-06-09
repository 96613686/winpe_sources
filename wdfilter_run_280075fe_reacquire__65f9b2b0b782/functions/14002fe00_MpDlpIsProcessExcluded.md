# MpDlpIsProcessExcluded

- ea: `0x14002fe00`
- end: `0x14003005b`
- name: `MpDlpIsProcessExcluded`
- size: `603`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003f700`
- `0x140042be0`

## callees

- `0x140002450`
- `0x1400118d0`
- `0x14002fe00`
- `0x140030060`
- `0x14003a1b0`
- `0x14003a2c0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14002fed8`
- `ntoskrnl!PsGetProcessId` at `0x14002fed8`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fff5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003004a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14002fff5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003004a`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002fe98`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14002fe98`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002fec6`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14002fec6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ff80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ff80`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ff74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002ff74`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002ff0f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002ff0f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fefd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002fefd`
- `ntoskrnl!IoGetCurrentProcess` at `0x140030016`
- `ntoskrnl!IoGetCurrentProcess` at `0x140030016`

## pseudocode

```c
bool __fastcall MpDlpIsProcessExcluded(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rbp
  bool v5; // bl
  _QWORD *v7; // r15
  PACCESS_TOKEN v8; // rax
  void *v9; // rdi
  struct _KPROCESS *RequestorProcess; // rbx
  LONGLONG TimeQuadPart; // r12
  unsigned __int64 ProcessId; // rdi
  int v13; // r14d
  char *v14; // rbx
  _QWORD *v15; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v17; // rcx
  struct _KPROCESS *CurrentProcess; // rax
  int ProcessContextByObject; // eax
  _QWORD *v20; // [rsp+20h] [rbp-58h]
  _QWORD *v21; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+31h] [rbp-47h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+34h] [rbp-44h] BYREF

  v4 = a2;
  if ( a2 )
    goto LABEL_2;
  if ( !a1 )
    return 0;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  v7 = 0;
  v20 = 0;
  v8 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  v21 = 0;
  if ( (int)MpDlpGetProcessContextFromTokenAttribute(v8, &v21) < 0 )
  {
    PsDereferenceImpersonationToken(v9);
    goto LABEL_10;
  }
  v4 = v21;
  PsDereferenceImpersonationToken(v9);
  if ( !v4 )
  {
LABEL_10:
    RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
    ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
    v13 = -1073741275;
    if ( ProcessId )
    {
      v14 = (char *)MpProcessTable;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)(v14 + 8), 1u);
      v15 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
      for ( i = (_QWORD *)*v15; i != v15; i = (_QWORD *)*i )
      {
        v17 = (volatile signed __int32 *)(i - 1);
        if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v17 + 4) )
        {
          _InterlockedIncrement(v17 + 12);
          v7 = i - 1;
          v20 = i - 1;
          v13 = 0;
          break;
        }
      }
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
    }
    if ( v13 >= 0 && v7
      || (CurrentProcess = IoGetCurrentProcess(),
          ProcessContextByObject = MpGetProcessContextByObject(CurrentProcess),
          v7 = v20,
          v13 = ProcessContextByObject,
          v20) )
    {
      if ( v13 < 0 )
      {
        MpReleaseProcessContext(v7);
        return 0;
      }
      v4 = v7;
    }
    else if ( ProcessContextByObject < 0 )
    {
      return 0;
    }
    if ( v4 )
      goto LABEL_2;
    return 0;
  }
LABEL_2:
  v5 = (v4[7] & 0x40000000) != 0 || *((_DWORD *)v4 + 60) == 33;
  if ( v4 != a2 )
    MpReleaseProcessContext(v4);
  return v5;
}

```

## disassembly

```asm
0x14002fe00  push    rbx
0x14002fe02  push    rbp
0x14002fe03  push    rsi
0x14002fe04  push    rdi
0x14002fe05  push    r13
0x14002fe07  push    r14
0x14002fe09  push    r15
0x14002fe0b  sub     rsp, 40h
0x14002fe0f  mov     rax, cs:__security_cookie
0x14002fe16  xor     rax, rsp
0x14002fe19  mov     [rsp+78h+var_40], rax
0x14002fe1e  mov     rsi, rdx
0x14002fe21  mov     rbx, rcx
0x14002fe24  mov     rbp, rdx
0x14002fe27  test    rdx, rdx
0x14002fe2a  jz      short loc_14002FE5D
0x14002fe2c  test    dword ptr [rbp+38h], 40000000h
0x14002fe33  jnz     loc_14003000F
0x14002fe39  cmp     dword ptr [rbp+0F0h], 21h ; '!'
0x14002fe40  jz      loc_14003000F
0x14002fe46  xor     bl, bl
0x14002fe48  cmp     rbp, rsi
0x14002fe4b  jz      short loc_14002FE55
0x14002fe4d  mov     rcx, rbp
0x14002fe50  call    MpReleaseProcessContext
0x14002fe55  movzx   eax, bl
0x14002fe58  jmp     loc_14002FFAD
0x14002fe5d  test    rbx, rbx
0x14002fe60  jz      loc_14002FFAB
0x14002fe66  xor     r13d, r13d
0x14002fe69  lea     r9, [rsp+78h+ImpersonationLevel]; ImpersonationLevel
0x14002fe6e  mov     [rsp+78h+CopyOnOpen], r13b
0x14002fe73  lea     r8, [rsp+78h+EffectiveOnly]; EffectiveOnly
0x14002fe78  mov     [rsp+78h+EffectiveOnly], r13b
0x14002fe7d  lea     rdx, [rsp+78h+CopyOnOpen]; CopyOnOpen
0x14002fe82  mov     [rsp+78h+ImpersonationLevel], r13d
0x14002fe87  mov     r15d, r13d
0x14002fe8a  mov     rcx, gs:188h; Thread
0x14002fe93  mov     [rsp+78h+var_58], r13
0x14002fe98  call    cs:__imp_PsReferenceImpersonationToken
0x14002fe9f  nop     dword ptr [rax+rax+00h]
0x14002fea4  mov     rdi, rax
0x14002fea7  test    rax, rax
0x14002feaa  jnz     loc_14002FFD7
0x14002feb0  mov     rcx, rbx
0x14002feb3  mov     [rsp+78h+arg_10], r12
0x14002febb  call    MpGetRequestorProcess
0x14002fec0  mov     rcx, rax; Process
0x14002fec3  mov     rbx, rax
0x14002fec6  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14002fecd  nop     dword ptr [rax+rax+00h]
0x14002fed2  mov     rcx, rbx; Process
0x14002fed5  mov     r12, rax
0x14002fed8  call    cs:__imp_PsGetProcessId
0x14002fedf  nop     dword ptr [rax+rax+00h]
0x14002fee4  mov     rdi, rax
0x14002fee7  mov     r14d, 0C0000225h
0x14002feed  test    rax, rax
0x14002fef0  jz      loc_14002FF8C
0x14002fef6  mov     rbx, cs:MpProcessTable
0x14002fefd  call    cs:__imp_KeEnterCriticalRegion
0x14002ff04  nop     dword ptr [rax+rax+00h]
0x14002ff09  mov     dl, 1; Wait
0x14002ff0b  lea     rcx, [rbx+8]; Resource
0x14002ff0f  call    cs:__imp_ExAcquireResourceSharedLite
0x14002ff16  nop     dword ptr [rax+rax+00h]
0x14002ff1b  mov     rax, cs:MpProcessTable
0x14002ff22  mov     r8, rdi
0x14002ff25  shr     r8, 2
0x14002ff29  and     r8d, 7Fh
0x14002ff2d  shl     r8, 4
0x14002ff31  add     r8, [rax+180h]
0x14002ff38  mov     rax, [r8]
0x14002ff3b  nop     dword ptr [rax+rax+00h]
0x14002ff40  cmp     rax, r8
0x14002ff43  jz      short loc_14002FF69
0x14002ff45  cmp     rdi, [rax+10h]
0x14002ff49  lea     rcx, [rax-8]
0x14002ff4d  jz      short loc_14002FF54
0x14002ff4f  mov     rax, [rax]
0x14002ff52  jmp     short loc_14002FF40
0x14002ff54  cmp     r12, [rcx+20h]
0x14002ff58  jnz     short loc_14002FF4F
0x14002ff5a  lock inc dword ptr [rcx+30h]
0x14002ff5e  mov     r15, rcx
0x14002ff61  mov     [rsp+78h+var_58], rcx
0x14002ff66  mov     r14d, r13d
0x14002ff69  mov     rcx, cs:MpProcessTable
0x14002ff70  add     rcx, 8; Resource
0x14002ff74  call    cs:__imp_ExReleaseResourceLite
0x14002ff7b  nop     dword ptr [rax+rax+00h]
0x14002ff80  call    cs:__imp_KeLeaveCriticalRegion
0x14002ff87  nop     dword ptr [rax+rax+00h]
0x14002ff8c  mov     r12, [rsp+78h+arg_10]
0x14002ff94  test    r14d, r14d
0x14002ff97  js      short loc_140030016
0x14002ff99  test    r15, r15
0x14002ff9c  jz      short loc_140030016
0x14002ff9e  test    r14d, r14d
0x14002ffa1  jns     short loc_14002FFCA
0x14002ffa3  mov     rcx, r15
0x14002ffa6  call    MpReleaseProcessContext
0x14002ffab  xor     al, al
0x14002ffad  mov     rcx, [rsp+78h+var_40]
0x14002ffb2  xor     rcx, rsp; StackCookie
0x14002ffb5  call    __security_check_cookie
0x14002ffba  add     rsp, 40h
0x14002ffbe  pop     r15
0x14002ffc0  pop     r14
0x14002ffc2  pop     r13
0x14002ffc4  pop     rdi
0x14002ffc5  pop     rsi
0x14002ffc6  pop     rbp
0x14002ffc7  pop     rbx
0x14002ffc8  retn
0x14002ffca  mov     rbp, r15
0x14002ffcd  test    rbp, rbp
0x14002ffd0  jz      short loc_14002FFAB
0x14002ffd2  jmp     loc_14002FE2C
0x14002ffd7  lea     rdx, [rsp+78h+var_50]
0x14002ffdc  mov     [rsp+78h+var_50], r13
0x14002ffe1  mov     rcx, rdi
0x14002ffe4  call    MpDlpGetProcessContextFromTokenAttribute
0x14002ffe9  mov     rcx, rdi; ImpersonationToken
0x14002ffec  test    eax, eax
0x14002ffee  js      short loc_14003004A
0x14002fff0  mov     rbp, [rsp+78h+var_50]
0x14002fff5  call    cs:__imp_PsDereferenceImpersonationToken
0x14002fffc  nop     dword ptr [rax+rax+00h]
0x140030001  test    rbp, rbp
0x140030004  jz      loc_14002FEB0
0x14003000a  jmp     loc_14002FE2C
0x14003000f  mov     bl, 1
0x140030011  jmp     loc_14002FE48
0x140030016  call    cs:__imp_IoGetCurrentProcess
0x14003001d  nop     dword ptr [rax+rax+00h]
0x140030022  mov     rcx, rax; Process
0x140030025  lea     rdx, [rsp+78h+var_58]
0x14003002a  call    MpGetProcessContextByObject
0x14003002f  mov     r15, [rsp+78h+var_58]
0x140030034  mov     r14d, eax
0x140030037  test    r15, r15
0x14003003a  jnz     loc_14002FF9E
0x140030040  test    eax, eax
0x140030042  js      loc_14002FFAB
0x140030048  jmp     short loc_14002FFCD
0x14003004a  call    cs:__imp_PsDereferenceImpersonationToken
0x140030051  nop     dword ptr [rax+rax+00h]
0x140030056  jmp     loc_14002FEB0
```
