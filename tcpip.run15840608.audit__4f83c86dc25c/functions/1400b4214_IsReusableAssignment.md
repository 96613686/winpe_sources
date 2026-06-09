# IsReusableAssignment

- ea: `0x1400b4214`
- end: `0x1400b455c`
- name: `IsReusableAssignment`
- size: `840`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, __int16, __int64, PKLOCK_QUEUE_HANDLE LockHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b1e04`
- `0x1400b2e40`

## callees

- `0x1400b4214`
- `0x1400b4570`
- `0x1400b459c`
- `0x1400b461c`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400b4499`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400b4499`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b4480`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b4480`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400b4470`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400b4470`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x1400b4460`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x1400b4460`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b44e2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b44e2`
- `ntoskrnl!SeAccessCheck` at `0x1400b4525`
- `ntoskrnl!SeAccessCheck` at `0x1400b4525`
- `ntoskrnl!SeLockSubjectContext` at `0x1400b4394`
- `ntoskrnl!SeLockSubjectContext` at `0x1400b4394`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400b4384`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1400b4384`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b42f7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b42f7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b43c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b43dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b440b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b43c6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b43dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b440b`

## pseudocode

```c
__int64 __fastcall IsReusableAssignment(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned int a4,
        int a5,
        struct _KPROCESS *a6,
        struct _KTHREAD *a7,
        unsigned __int16 a8,
        __int64 a9,
        PKLOCK_QUEUE_HANDLE LockHandle)
{
  int v12; // eax
  __int64 i; // rbx
  char v14; // di
  unsigned __int64 v15; // rbx
  __int64 v16; // rsi
  int v17; // ecx
  __int64 v18; // rdx
  void *v19; // rdi
  BOOLEAN v20; // si
  __int64 result; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  int AccessStatus; // [rsp+48h] [rbp-B8h]
  _BYTE v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v25; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  PEPROCESS Process; // [rsp+80h] [rbp-80h]
  PETHREAD Thread; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v34; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v35; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t pszDest[16]; // [rsp+E8h] [rbp-18h] BYREF

  Process = a6;
  Thread = a7;
  v29 = a9;
  v12 = *a3;
  v28 = a4;
  v32 = a2;
  if ( (v12 & 1) != 0 )
    return 3221225506LL;
  if ( (a5 & 0x10) == 0 )
  {
    for ( i = *((_QWORD *)a3 + 2); i; i = *(_QWORD *)v15 )
    {
      v27 = -1073741802;
      v25 = 0;
      v14 = i & 3;
      if ( (i & 3) != 0 )
      {
        v15 = i & 0xFFFFFFFFFFFFFFFCuLL;
        LOBYTE(a2) = v14;
        v16 = (*(__int64 (__fastcall **)(unsigned __int64, __int64, unsigned __int16 *))(a1 + 112))(v15, a2, &v25);
        if ( v16 != -1 )
        {
          v17 = *(_DWORD *)(v15 + 16);
          if ( (v17 & 2) == 0 && ((v17 & 1) == 0 || (a5 & 2) == 0) )
          {
            KeReleaseInStackQueuedSpinLock(LockHandle);
            LOBYTE(v18) = v14;
            v19 = (void *)(*(__int64 (__fastcall **)(unsigned __int64, __int64))(a1 + 120))(v15, v18);
            v27 = CheckAddressesForPortReusability(a5, *a3 & 0x1F, a8, v25, v29, v16, (__int64)v19);
            if ( (a5 & 0x80u) == 0 )
            {
              v20 = 0;
              GrantedAccess = 0;
              memset(&SubjectContext, 0, sizeof(SubjectContext));
              v24[0] = 0;
              DestinationString = 0;
              v34 = 0;
              v35 = 0;
              SeCaptureSubjectContextEx(Thread, Process, &SubjectContext);
              SeLockSubjectContext(&SubjectContext);
              if ( v27 == 259 )
              {
                GenericMapping = IoGetFileObjectGenericMapping();
                v20 = SeAccessCheck(v19, &SubjectContext, 1u, 3u, 0, 0, GenericMapping, 1, &GrantedAccess, &v27);
              }
              else if ( v27 >= 0 )
              {
                v20 = 1;
                GrantedAccess = 3;
              }
              else
              {
                GrantedAccess = 0;
              }
              RtlInitUnicodeString(&DestinationString, L"TCP/IP");
              RtlInitUnicodeString(&v35, L"InternetPort");
              RtlStringCbPrintfW(pszDest, 0x20u, L"Port %u", v28);
              RtlInitUnicodeString(&v34, pszDest);
              if ( v19 )
              {
                LOBYTE(AccessStatus) = v20;
                SeOpenObjectAuditAlarmForNonObObject(
                  &DestinationString,
                  0,
                  &v35,
                  &v34,
                  v19,
                  &SubjectContext,
                  3,
                  GrantedAccess,
                  0,
                  AccessStatus,
                  v24);
              }
              SeUnlockSubjectContext(&SubjectContext);
              SeReleaseSubjectContext(&SubjectContext);
            }
            if ( v19 )
              ObDereferenceSecurityDescriptor(v19, 1);
            RtlAcquireWriteLock(v32, LockHandle);
            result = (unsigned int)v27;
            if ( v27 < 0 )
              return result;
          }
        }
      }
      else
      {
        v15 = i & 0xFFFFFFFFFFFFFFFCuLL;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400b4214  push    rbp
0x1400b4216  push    rbx
0x1400b4217  push    rsi
0x1400b4218  push    rdi
0x1400b4219  push    r12
0x1400b421b  push    r13
0x1400b421d  push    r15
0x1400b421f  lea     rbp, [rsp-10h]
0x1400b4224  sub     rsp, 110h
0x1400b422b  mov     rax, cs:__security_cookie
0x1400b4232  xor     rax, rsp
0x1400b4235  mov     [rbp+40h+var_38], rax
0x1400b4239  mov     rax, [rbp+40h+arg_28]
0x1400b423d  mov     r15, r8
0x1400b4240  mov     r12, [rbp+40h+LockHandle]
0x1400b4247  mov     r13, rcx
0x1400b424a  mov     [rbp+40h+Process], rax
0x1400b424e  mov     rax, [rbp+40h+arg_30]
0x1400b4255  mov     [rbp+40h+Thread], rax
0x1400b4259  mov     rax, [rbp+40h+arg_40]
0x1400b4260  mov     [rsp+140h+var_C8], rax
0x1400b4265  mov     eax, [r8]
0x1400b4268  mov     [rsp+140h+var_D0], r9d
0x1400b426d  mov     [rbp+40h+var_B0], rdx
0x1400b4271  test    al, 1
0x1400b4273  jnz     loc_1400B4549
0x1400b4279  test    byte ptr [rbp+40h+arg_20], 10h
0x1400b427d  jnz     loc_1400B44C1
0x1400b4283  mov     rbx, [r8+10h]
0x1400b4287  test    rbx, rbx
0x1400b428a  jz      loc_1400B44C1
0x1400b4290  xor     eax, eax
0x1400b4292  mov     [rsp+140h+var_D4], 0C0000016h
0x1400b429a  mov     dil, bl
0x1400b429d  mov     [rsp+140h+var_DC], ax
0x1400b42a2  and     dil, 3
0x1400b42a6  jz      loc_1400B4553
0x1400b42ac  mov     rax, [r13+70h]
0x1400b42b0  lea     r8, [rsp+140h+var_DC]
0x1400b42b5  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400b42b9  mov     dl, dil
0x1400b42bc  mov     rcx, rbx
0x1400b42bf  call    _guard_dispatch_icall
0x1400b42c4  mov     rsi, rax
0x1400b42c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400b42cb  jz      loc_1400B44B9
0x1400b42d1  mov     ecx, [rbx+10h]
0x1400b42d4  test    cl, 2
0x1400b42d7  jnz     loc_1400B44B9
0x1400b42dd  test    cl, 1
0x1400b42e0  setnz   r8b
0x1400b42e4  test    byte ptr [rbp+40h+arg_20], 2
0x1400b42e8  setnz   cl
0x1400b42eb  test    cl, r8b
0x1400b42ee  jnz     loc_1400B44B9
0x1400b42f4  mov     rcx, r12; LockHandle
0x1400b42f7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b42fe  nop     dword ptr [rax+rax+00h]
0x1400b4303  mov     rax, [r13+78h]
0x1400b4307  mov     dl, dil
0x1400b430a  mov     rcx, rbx
0x1400b430d  call    _guard_dispatch_icall
0x1400b4312  mov     edx, [r15]
0x1400b4315  mov     rdi, rax
0x1400b4318  movzx   r9d, [rsp+140h+var_DC]
0x1400b431e  and     edx, 1Fh
0x1400b4321  movzx   r8d, [rbp+40h+arg_38]
0x1400b4329  mov     ecx, [rbp+40h+arg_20]
0x1400b432c  mov     [rsp+140h+GenericMapping], rax
0x1400b4331  mov     rax, [rsp+140h+var_C8]
0x1400b4336  mov     [rsp+140h+Privileges], rsi
0x1400b433b  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax
0x1400b4340  call    CheckAddressesForPortReusability
0x1400b4345  test    byte ptr [rbp+40h+arg_20], 80h
0x1400b4349  mov     [rsp+140h+var_D4], eax
0x1400b434d  jnz     loc_1400B448C
0x1400b4353  mov     rdx, [rbp+40h+Process]; Process
0x1400b4357  lea     r8, [rbp+40h+SubjectContext]; SubjectContext
0x1400b435b  mov     rcx, [rbp+40h+Thread]; Thread
0x1400b435f  xorps   xmm0, xmm0
0x1400b4362  xor     esi, esi
0x1400b4364  xorps   xmm1, xmm1
0x1400b4367  mov     [rsp+140h+var_D8], esi
0x1400b436b  movups  xmmword ptr [rbp+40h+SubjectContext.ClientToken], xmm0
0x1400b436f  mov     [rsp+140h+var_E0], sil
0x1400b4374  movups  xmmword ptr [rbp+40h+SubjectContext.PrimaryToken], xmm0
0x1400b4378  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x1400b437c  movups  xmmword ptr [rbp+40h+var_88.Length], xmm1
0x1400b4380  movups  xmmword ptr [rbp+40h+var_78.Length], xmm0
0x1400b4384  call    cs:__imp_SeCaptureSubjectContextEx
0x1400b438b  nop     dword ptr [rax+rax+00h]
0x1400b4390  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b4394  call    cs:__imp_SeLockSubjectContext
0x1400b439b  nop     dword ptr [rax+rax+00h]
0x1400b43a0  mov     eax, [rsp+140h+var_D4]
0x1400b43a4  cmp     eax, 103h
0x1400b43a9  jz      loc_1400B44E2
0x1400b43af  test    eax, eax
0x1400b43b1  jns     loc_1400B4539
0x1400b43b7  mov     [rsp+140h+var_D8], esi
0x1400b43bb  lea     rdx, aTcpIp; "TCP/IP"
0x1400b43c2  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1400b43c6  call    cs:__imp_RtlInitUnicodeString
0x1400b43cd  nop     dword ptr [rax+rax+00h]
0x1400b43d2  lea     rdx, aInternetport; "InternetPort"
0x1400b43d9  lea     rcx, [rbp+40h+var_78]; DestinationString
0x1400b43dd  call    cs:__imp_RtlInitUnicodeString
0x1400b43e4  nop     dword ptr [rax+rax+00h]
0x1400b43e9  mov     r9d, [rsp+140h+var_D0]
0x1400b43ee  lea     r8, aPortU; "Port %u"
0x1400b43f5  mov     edx, 20h ; ' '; cbDest
0x1400b43fa  lea     rcx, [rbp+40h+pszDest]; pszDest
0x1400b43fe  call    RtlStringCbPrintfW
0x1400b4403  lea     rdx, [rbp+40h+pszDest]; SourceString
0x1400b4407  lea     rcx, [rbp+40h+var_88]; DestinationString
0x1400b440b  call    cs:__imp_RtlInitUnicodeString
0x1400b4412  nop     dword ptr [rax+rax+00h]
0x1400b4417  test    rdi, rdi
0x1400b441a  jz      short loc_1400B446C
0x1400b441c  lea     rax, [rsp+140h+var_E0]
0x1400b4421  xor     edx, edx
0x1400b4423  mov     [rsp+140h+var_F0], rax
0x1400b4428  lea     r9, [rbp+40h+var_88]
0x1400b442c  mov     eax, [rsp+140h+var_D8]
0x1400b4430  lea     r8, [rbp+40h+var_78]
0x1400b4434  mov     byte ptr [rsp+140h+AccessStatus], sil
0x1400b4439  lea     rcx, [rbp+40h+DestinationString]
0x1400b443d  mov     [rsp+140h+GrantedAccess], 0
0x1400b4446  mov     dword ptr [rsp+140h+AccessMode], eax
0x1400b444a  lea     rax, [rbp+40h+SubjectContext]
0x1400b444e  mov     dword ptr [rsp+140h+GenericMapping], 3
0x1400b4456  mov     [rsp+140h+Privileges], rax
0x1400b445b  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rdi
0x1400b4460  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x1400b4467  nop     dword ptr [rax+rax+00h]
0x1400b446c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b4470  call    cs:__imp_SeUnlockSubjectContext
0x1400b4477  nop     dword ptr [rax+rax+00h]
0x1400b447c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x1400b4480  call    cs:__imp_SeReleaseSubjectContext
0x1400b4487  nop     dword ptr [rax+rax+00h]
0x1400b448c  test    rdi, rdi
0x1400b448f  jz      short loc_1400B44A5
0x1400b4491  mov     edx, 1
0x1400b4496  mov     rcx, rdi
0x1400b4499  call    cs:__imp_ObDereferenceSecurityDescriptor
0x1400b44a0  nop     dword ptr [rax+rax+00h]
0x1400b44a5  mov     rcx, [rbp+40h+var_B0]
0x1400b44a9  mov     rdx, r12
0x1400b44ac  call    RtlAcquireWriteLock
0x1400b44b1  mov     eax, [rsp+140h+var_D4]
0x1400b44b5  test    eax, eax
0x1400b44b7  js      short loc_1400B44C3
0x1400b44b9  mov     rbx, [rbx]
0x1400b44bc  jmp     loc_1400B4287
0x1400b44c1  xor     eax, eax
0x1400b44c3  mov     rcx, [rbp+40h+var_38]
0x1400b44c7  xor     rcx, rsp; StackCookie
0x1400b44ca  call    __security_check_cookie
0x1400b44cf  add     rsp, 110h
0x1400b44d6  pop     r15
0x1400b44d8  pop     r13
0x1400b44da  pop     r12
0x1400b44dc  pop     rdi
0x1400b44dd  pop     rsi
0x1400b44de  pop     rbx
0x1400b44df  pop     rbp
0x1400b44e0  retn
0x1400b44e2  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b44e9  nop     dword ptr [rax+rax+00h]
0x1400b44ee  lea     rcx, [rsp+140h+var_D4]
0x1400b44f3  mov     r9d, 3; DesiredAccess
0x1400b44f9  mov     [rsp+140h+AccessStatus], rcx; AccessStatus
0x1400b44fe  lea     rdx, [rbp+40h+SubjectContext]; SubjectSecurityContext
0x1400b4502  lea     rcx, [rsp+140h+var_D8]
0x1400b4507  mov     r8b, 1; SubjectContextLocked
0x1400b450a  mov     [rsp+140h+GrantedAccess], rcx; GrantedAccess
0x1400b450f  mov     rcx, rdi; SecurityDescriptor
0x1400b4512  mov     [rsp+140h+AccessMode], 1; AccessMode
0x1400b4517  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x1400b451c  mov     [rsp+140h+Privileges], rsi; Privileges
0x1400b4521  mov     [rsp+140h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x1400b4525  call    cs:__imp_SeAccessCheck
0x1400b452c  nop     dword ptr [rax+rax+00h]
0x1400b4531  mov     sil, al
0x1400b4534  jmp     loc_1400B43BB
0x1400b4539  mov     sil, 1
0x1400b453c  mov     [rsp+140h+var_D8], 3
0x1400b4544  jmp     loc_1400B43BB
0x1400b4549  mov     eax, 0C0000022h
0x1400b454e  jmp     loc_1400B44C3
0x1400b4553  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400b4557  jmp     loc_1400B44B9
```
