# IsReusableAssignment

- ea: `0x14005e324`
- end: `0x14005e66c`
- name: `IsReusableAssignment`
- size: `840`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, __int16, __int64, PKLOCK_QUEUE_HANDLE LockHandle)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005bec4`
- `0x14005cf50`

## callees

- `0x14005e324`
- `0x14005e680`
- `0x14005e6ac`
- `0x14005e72c`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005e5a9`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005e5a9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005e590`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14005e590`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005e580`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14005e580`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005e570`
- `ntoskrnl!SeOpenObjectAuditAlarmForNonObObject` at `0x14005e570`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005e5f2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005e5f2`
- `ntoskrnl!SeAccessCheck` at `0x14005e635`
- `ntoskrnl!SeAccessCheck` at `0x14005e635`
- `ntoskrnl!SeLockSubjectContext` at `0x14005e4a4`
- `ntoskrnl!SeLockSubjectContext` at `0x14005e4a4`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005e494`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14005e494`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e407`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005e407`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e4d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e4ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e51b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e4d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e4ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005e51b`

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
0x14005e324  push    rbp
0x14005e326  push    rbx
0x14005e327  push    rsi
0x14005e328  push    rdi
0x14005e329  push    r12
0x14005e32b  push    r13
0x14005e32d  push    r15
0x14005e32f  lea     rbp, [rsp-10h]
0x14005e334  sub     rsp, 110h
0x14005e33b  mov     rax, cs:__security_cookie
0x14005e342  xor     rax, rsp
0x14005e345  mov     [rbp+40h+var_38], rax
0x14005e349  mov     rax, [rbp+40h+arg_28]
0x14005e34d  mov     r15, r8
0x14005e350  mov     r12, [rbp+40h+LockHandle]
0x14005e357  mov     r13, rcx
0x14005e35a  mov     [rbp+40h+Process], rax
0x14005e35e  mov     rax, [rbp+40h+arg_30]
0x14005e365  mov     [rbp+40h+Thread], rax
0x14005e369  mov     rax, [rbp+40h+arg_40]
0x14005e370  mov     [rsp+140h+var_C8], rax
0x14005e375  mov     eax, [r8]
0x14005e378  mov     [rsp+140h+var_D0], r9d
0x14005e37d  mov     [rbp+40h+var_B0], rdx
0x14005e381  test    al, 1
0x14005e383  jnz     loc_14005E659
0x14005e389  test    byte ptr [rbp+40h+arg_20], 10h
0x14005e38d  jnz     loc_14005E5D1
0x14005e393  mov     rbx, [r8+10h]
0x14005e397  test    rbx, rbx
0x14005e39a  jz      loc_14005E5D1
0x14005e3a0  xor     eax, eax
0x14005e3a2  mov     [rsp+140h+var_D4], 0C0000016h
0x14005e3aa  mov     dil, bl
0x14005e3ad  mov     [rsp+140h+var_DC], ax
0x14005e3b2  and     dil, 3
0x14005e3b6  jz      loc_14005E663
0x14005e3bc  mov     rax, [r13+70h]
0x14005e3c0  lea     r8, [rsp+140h+var_DC]
0x14005e3c5  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14005e3c9  mov     dl, dil
0x14005e3cc  mov     rcx, rbx
0x14005e3cf  call    _guard_dispatch_icall
0x14005e3d4  mov     rsi, rax
0x14005e3d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14005e3db  jz      loc_14005E5C9
0x14005e3e1  mov     ecx, [rbx+10h]
0x14005e3e4  test    cl, 2
0x14005e3e7  jnz     loc_14005E5C9
0x14005e3ed  test    cl, 1
0x14005e3f0  setnz   r8b
0x14005e3f4  test    byte ptr [rbp+40h+arg_20], 2
0x14005e3f8  setnz   cl
0x14005e3fb  test    cl, r8b
0x14005e3fe  jnz     loc_14005E5C9
0x14005e404  mov     rcx, r12; LockHandle
0x14005e407  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005e40e  nop     dword ptr [rax+rax+00h]
0x14005e413  mov     rax, [r13+78h]
0x14005e417  mov     dl, dil
0x14005e41a  mov     rcx, rbx
0x14005e41d  call    _guard_dispatch_icall
0x14005e422  mov     edx, [r15]
0x14005e425  mov     rdi, rax
0x14005e428  movzx   r9d, [rsp+140h+var_DC]
0x14005e42e  and     edx, 1Fh
0x14005e431  movzx   r8d, [rbp+40h+arg_38]
0x14005e439  mov     ecx, [rbp+40h+arg_20]
0x14005e43c  mov     [rsp+140h+GenericMapping], rax
0x14005e441  mov     rax, [rsp+140h+var_C8]
0x14005e446  mov     [rsp+140h+Privileges], rsi
0x14005e44b  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rax
0x14005e450  call    CheckAddressesForPortReusability
0x14005e455  test    byte ptr [rbp+40h+arg_20], 80h
0x14005e459  mov     [rsp+140h+var_D4], eax
0x14005e45d  jnz     loc_14005E59C
0x14005e463  mov     rdx, [rbp+40h+Process]; Process
0x14005e467  lea     r8, [rbp+40h+SubjectContext]; SubjectContext
0x14005e46b  mov     rcx, [rbp+40h+Thread]; Thread
0x14005e46f  xorps   xmm0, xmm0
0x14005e472  xor     esi, esi
0x14005e474  xorps   xmm1, xmm1
0x14005e477  mov     [rsp+140h+var_D8], esi
0x14005e47b  movups  xmmword ptr [rbp+40h+SubjectContext.ClientToken], xmm0
0x14005e47f  mov     [rsp+140h+var_E0], sil
0x14005e484  movups  xmmword ptr [rbp+40h+SubjectContext.PrimaryToken], xmm0
0x14005e488  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14005e48c  movups  xmmword ptr [rbp+40h+var_88.Length], xmm1
0x14005e490  movups  xmmword ptr [rbp+40h+var_78.Length], xmm0
0x14005e494  call    cs:__imp_SeCaptureSubjectContextEx
0x14005e49b  nop     dword ptr [rax+rax+00h]
0x14005e4a0  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e4a4  call    cs:__imp_SeLockSubjectContext
0x14005e4ab  nop     dword ptr [rax+rax+00h]
0x14005e4b0  mov     eax, [rsp+140h+var_D4]
0x14005e4b4  cmp     eax, 103h
0x14005e4b9  jz      loc_14005E5F2
0x14005e4bf  test    eax, eax
0x14005e4c1  jns     loc_14005E649
0x14005e4c7  mov     [rsp+140h+var_D8], esi
0x14005e4cb  lea     rdx, SourceString; "TCP/IP"
0x14005e4d2  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14005e4d6  call    cs:__imp_RtlInitUnicodeString
0x14005e4dd  nop     dword ptr [rax+rax+00h]
0x14005e4e2  lea     rdx, aInternetport; "InternetPort"
0x14005e4e9  lea     rcx, [rbp+40h+var_78]; DestinationString
0x14005e4ed  call    cs:__imp_RtlInitUnicodeString
0x14005e4f4  nop     dword ptr [rax+rax+00h]
0x14005e4f9  mov     r9d, [rsp+140h+var_D0]
0x14005e4fe  lea     r8, aPortU; "Port %u"
0x14005e505  mov     edx, 20h ; ' '; cbDest
0x14005e50a  lea     rcx, [rbp+40h+pszDest]; pszDest
0x14005e50e  call    RtlStringCbPrintfW
0x14005e513  lea     rdx, [rbp+40h+pszDest]; SourceString
0x14005e517  lea     rcx, [rbp+40h+var_88]; DestinationString
0x14005e51b  call    cs:__imp_RtlInitUnicodeString
0x14005e522  nop     dword ptr [rax+rax+00h]
0x14005e527  test    rdi, rdi
0x14005e52a  jz      short loc_14005E57C
0x14005e52c  lea     rax, [rsp+140h+var_E0]
0x14005e531  xor     edx, edx
0x14005e533  mov     [rsp+140h+var_F0], rax
0x14005e538  lea     r9, [rbp+40h+var_88]
0x14005e53c  mov     eax, [rsp+140h+var_D8]
0x14005e540  lea     r8, [rbp+40h+var_78]
0x14005e544  mov     byte ptr [rsp+140h+AccessStatus], sil
0x14005e549  lea     rcx, [rbp+40h+DestinationString]
0x14005e54d  mov     [rsp+140h+GrantedAccess], 0
0x14005e556  mov     dword ptr [rsp+140h+AccessMode], eax
0x14005e55a  lea     rax, [rbp+40h+SubjectContext]
0x14005e55e  mov     dword ptr [rsp+140h+GenericMapping], 3
0x14005e566  mov     [rsp+140h+Privileges], rax
0x14005e56b  mov     qword ptr [rsp+140h+PreviouslyGrantedAccess], rdi
0x14005e570  call    cs:__imp_SeOpenObjectAuditAlarmForNonObObject
0x14005e577  nop     dword ptr [rax+rax+00h]
0x14005e57c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e580  call    cs:__imp_SeUnlockSubjectContext
0x14005e587  nop     dword ptr [rax+rax+00h]
0x14005e58c  lea     rcx, [rbp+40h+SubjectContext]; SubjectContext
0x14005e590  call    cs:__imp_SeReleaseSubjectContext
0x14005e597  nop     dword ptr [rax+rax+00h]
0x14005e59c  test    rdi, rdi
0x14005e59f  jz      short loc_14005E5B5
0x14005e5a1  mov     edx, 1
0x14005e5a6  mov     rcx, rdi
0x14005e5a9  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14005e5b0  nop     dword ptr [rax+rax+00h]
0x14005e5b5  mov     rcx, [rbp+40h+var_B0]
0x14005e5b9  mov     rdx, r12
0x14005e5bc  call    RtlAcquireWriteLock
0x14005e5c1  mov     eax, [rsp+140h+var_D4]
0x14005e5c5  test    eax, eax
0x14005e5c7  js      short loc_14005E5D3
0x14005e5c9  mov     rbx, [rbx]
0x14005e5cc  jmp     loc_14005E397
0x14005e5d1  xor     eax, eax
0x14005e5d3  mov     rcx, [rbp+40h+var_38]
0x14005e5d7  xor     rcx, rsp; StackCookie
0x14005e5da  call    __security_check_cookie
0x14005e5df  add     rsp, 110h
0x14005e5e6  pop     r15
0x14005e5e8  pop     r13
0x14005e5ea  pop     r12
0x14005e5ec  pop     rdi
0x14005e5ed  pop     rsi
0x14005e5ee  pop     rbx
0x14005e5ef  pop     rbp
0x14005e5f0  retn
0x14005e5f2  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005e5f9  nop     dword ptr [rax+rax+00h]
0x14005e5fe  lea     rcx, [rsp+140h+var_D4]
0x14005e603  mov     r9d, 3; DesiredAccess
0x14005e609  mov     [rsp+140h+AccessStatus], rcx; AccessStatus
0x14005e60e  lea     rdx, [rbp+40h+SubjectContext]; SubjectSecurityContext
0x14005e612  lea     rcx, [rsp+140h+var_D8]
0x14005e617  mov     r8b, 1; SubjectContextLocked
0x14005e61a  mov     [rsp+140h+GrantedAccess], rcx; GrantedAccess
0x14005e61f  mov     rcx, rdi; SecurityDescriptor
0x14005e622  mov     [rsp+140h+AccessMode], 1; AccessMode
0x14005e627  mov     [rsp+140h+GenericMapping], rax; GenericMapping
0x14005e62c  mov     [rsp+140h+Privileges], rsi; Privileges
0x14005e631  mov     [rsp+140h+PreviouslyGrantedAccess], esi; PreviouslyGrantedAccess
0x14005e635  call    cs:__imp_SeAccessCheck
0x14005e63c  nop     dword ptr [rax+rax+00h]
0x14005e641  mov     sil, al
0x14005e644  jmp     loc_14005E4CB
0x14005e649  mov     sil, 1
0x14005e64c  mov     [rsp+140h+var_D8], 3
0x14005e654  jmp     loc_14005E4CB
0x14005e659  mov     eax, 0C0000022h
0x14005e65e  jmp     loc_14005E5D3
0x14005e663  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14005e667  jmp     loc_14005E5C9
```
