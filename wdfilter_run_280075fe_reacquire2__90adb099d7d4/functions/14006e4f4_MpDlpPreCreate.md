# MpDlpPreCreate

- ea: `0x14006e4f4`
- end: `0x14006e7ce`
- name: `MpDlpPreCreate`
- size: `730`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14003c990`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x140007098`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003a2c0`
- `0x140040388`
- `0x14006e4f4`
- `0x14006e7d0`

## import_xrefs

- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006e6d9`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14006e6d9`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006e697`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14006e697`
- `FLTMGR!FltGetFileNameInformation` at `0x14006e5b8`
- `FLTMGR!FltGetFileNameInformation` at `0x14006e5b8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e796`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14006e796`

## string_xrefs

- `0x14006e769`: `[DLP-filter] Denied Process '%wZ' (pid = %#x) from opening file '%wZ' for write on %ws, reason: %d.`

## pseudocode

```c
__int64 __fastcall MpDlpPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  unsigned int v3; // r14d
  struct _KPROCESS *RequestorProcess; // rax
  int ProcessContextByObject; // r8d
  __int64 v8; // rbx
  NTSTATUS v9; // r8d
  int v10; // ecx
  __int64 v11; // rdi
  PACCESS_TOKEN v12; // rax
  void *v13; // r14
  const wchar_t *v14; // rcx
  __int64 v16; // [rsp+28h] [rbp-48h]
  __int64 v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 CopyOnOpen[7]; // [rsp+59h] [rbp-17h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel[2]; // [rsp+60h] [rbp-10h] BYREF

  v3 = 0;
  LODWORD(v17) = 0;
  FileNameInformation = 0;
  *(_QWORD *)ImpersonationLevel = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  if ( RequestorProcess )
  {
    ProcessContextByObject = MpGetProcessContextByObject(RequestorProcess);
    if ( ProcessContextByObject >= 0 )
    {
      v8 = *(_QWORD *)ImpersonationLevel;
      if ( *(_DWORD *)(*(_QWORD *)ImpersonationLevel + 240LL) == 1 )
        goto LABEL_28;
      _mm_lfence();
      v9 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
      if ( v9 >= 0 )
      {
        v10 = *(_DWORD *)(a3 + 84);
        if ( (v10 & 0x10) != 0 )
        {
          _mm_lfence();
          v3 = MpDlpCheckOperation(CallbackData, 1, (__int64)&FileNameInformation->Name, (__int64)&v17);
        }
        else
        {
          if ( (v10 & 0x800) == 0 )
            goto LABEL_28;
          _mm_lfence();
          v11 = v8;
          if ( *(_DWORD *)(v8 + 240) == 3 )
          {
            CopyOnOpen[0] = 0;
            EffectiveOnly = 0;
            ImpersonationLevel[0] = SecurityAnonymous;
            v12 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, ImpersonationLevel);
            v13 = v12;
            if ( v12 )
            {
              v18 = 0;
              if ( (int)MpDlpGetProcessContextFromTokenAttribute(v12, &v18) >= 0 )
              {
                if ( v18 == v8 )
                  MpReleaseProcessContext(v18);
                else
                  v11 = v18;
              }
              PsDereferenceImpersonationToken(v13);
            }
          }
          v3 = MpDlpCheckOperation(CallbackData, 0, (__int64)&FileNameInformation->Name, (__int64)&v17);
          if ( v11 != v8 )
            MpReleaseProcessContext(v11);
        }
        if ( v3 == 2 )
        {
          _mm_lfence();
          v14 = L"remote device";
          if ( (*(_DWORD *)(a3 + 84) & 0x10) == 0 )
            v14 = L"external device";
          LODWORD(v16) = v17;
          MpLogPrintfW(
            L"[DLP-filter] Denied Process '%wZ' (pid = %#x) from opening file '%wZ' for write on %ws, reason: %d.",
            *(_QWORD *)(v8 + 128),
            *(unsigned int *)(v8 + 24),
            &CallbackData->Iopb->TargetFileObject->FileName,
            v14,
            v16);
          MpDlpBlockActionToNtStatus(v8, &v17, &CallbackData->IoStatus);
          CallbackData->IoStatus.Information = 0;
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          109,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          v9);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        108,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        CallbackData->Thread,
        ProcessContextByObject);
    }
  }
LABEL_28:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return v3;
}

```

## disassembly

```asm
0x14006e4f4  push    rbp
0x14006e4f6  push    rbx
0x14006e4f7  push    rsi
0x14006e4f8  push    rdi
0x14006e4f9  push    r12
0x14006e4fb  push    r14
0x14006e4fd  push    r15
0x14006e4ff  mov     rbp, rsp
0x14006e502  sub     rsp, 70h
0x14006e506  mov     rax, cs:__security_cookie
0x14006e50d  xor     rax, rsp
0x14006e510  mov     [rbp+var_8], rax
0x14006e514  xor     r14d, r14d
0x14006e517  xor     ebx, ebx
0x14006e519  mov     dword ptr [rbp+var_30], r14d
0x14006e51d  mov     r15, r8
0x14006e520  mov     [rbp+FileNameInformation], r14
0x14006e524  mov     r12, rdx
0x14006e527  mov     qword ptr [rbp+ImpersonationLevel], rbx
0x14006e52b  mov     rsi, rcx
0x14006e52e  call    MpGetRequestorProcess
0x14006e533  test    rax, rax
0x14006e536  jz      loc_14006E78D
0x14006e53c  lea     rdx, [rbp+ImpersonationLevel]
0x14006e540  mov     rcx, rax; Process
0x14006e543  call    MpGetProcessContextByObject
0x14006e548  mov     r8d, eax
0x14006e54b  test    eax, eax
0x14006e54d  jns     short loc_14006E598
0x14006e54f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e556  lea     rax, WPP_GLOBAL_Control
0x14006e55d  cmp     rcx, rax
0x14006e560  jz      short loc_14006E58F
0x14006e562  mov     eax, [rcx+2Ch]
0x14006e565  test    al, 1
0x14006e567  jz      short loc_14006E58F
0x14006e569  lfence
0x14006e56c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e573  lea     edx, [rbx+6Ch]
0x14006e576  mov     r9, [rsi+8]
0x14006e57a  mov     [rsp+70h+var_50], r8d
0x14006e57f  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14006e586  mov     rcx, [rcx+18h]
0x14006e58a  call    WPP_SF_qD
0x14006e58f  mov     rbx, qword ptr [rbp+ImpersonationLevel]
0x14006e593  jmp     loc_14006E78D
0x14006e598  mov     rbx, qword ptr [rbp+ImpersonationLevel]
0x14006e59c  cmp     dword ptr [rbx+0F0h], 1
0x14006e5a3  jz      loc_14006E78D
0x14006e5a9  lfence
0x14006e5ac  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x14006e5b0  mov     edx, 102h; NameOptions
0x14006e5b5  mov     rcx, rsi; CallbackData
0x14006e5b8  call    cs:__imp_FltGetFileNameInformation
0x14006e5bf  nop     dword ptr [rax+rax+00h]
0x14006e5c4  mov     r8d, eax
0x14006e5c7  test    eax, eax
0x14006e5c9  jns     short loc_14006E61A
0x14006e5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e5d2  lea     rax, WPP_GLOBAL_Control
0x14006e5d9  cmp     rcx, rax
0x14006e5dc  jz      loc_14006E78D
0x14006e5e2  mov     eax, [rcx+2Ch]
0x14006e5e5  test    al, 1
0x14006e5e7  jz      loc_14006E78D
0x14006e5ed  lfence
0x14006e5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e5f7  mov     edx, 6Dh ; 'm'
0x14006e5fc  mov     r9, [rsi+8]
0x14006e600  mov     [rsp+70h+var_50], r8d
0x14006e605  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14006e60c  mov     rcx, [rcx+18h]
0x14006e610  call    WPP_SF_qD
0x14006e615  jmp     loc_14006E78D
0x14006e61a  mov     ecx, [r15+54h]
0x14006e61e  test    cl, 10h
0x14006e621  jz      short loc_14006E65D
0x14006e623  lfence
0x14006e626  mov     rax, [rbp+FileNameInformation]
0x14006e62a  lea     rdx, [rbp+var_30]
0x14006e62e  mov     [rsp+70h+var_40], rdx; __int64
0x14006e633  add     rax, 8
0x14006e637  mov     r9d, ecx
0x14006e63a  mov     [rsp+70h+var_48], rax; __int64
0x14006e63f  mov     r8, rbx
0x14006e642  mov     [rsp+70h+var_50], 1; int
0x14006e64a  mov     rdx, r12
0x14006e64d  mov     rcx, rsi; CallbackData
0x14006e650  call    MpDlpCheckOperation
0x14006e655  mov     r14d, eax
0x14006e658  jmp     loc_14006E725
0x14006e65d  bt      ecx, 0Bh
0x14006e661  jnb     loc_14006E78D
0x14006e667  lfence
0x14006e66a  cmp     dword ptr [rbx+0F0h], 3
0x14006e671  mov     rdi, rbx
0x14006e674  jnz     short loc_14006E6E5
0x14006e676  mov     [rbp+CopyOnOpen], r14b
0x14006e67a  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x14006e67e  mov     [rbp+EffectiveOnly], r14b
0x14006e682  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x14006e686  mov     [rbp+ImpersonationLevel], r14d
0x14006e68a  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14006e68e  mov     rcx, gs:188h; Thread
0x14006e697  call    cs:__imp_PsReferenceImpersonationToken
0x14006e69e  nop     dword ptr [rax+rax+00h]
0x14006e6a3  mov     r14, rax
0x14006e6a6  test    rax, rax
0x14006e6a9  jz      short loc_14006E6E5
0x14006e6ab  lea     rdx, [rbp+var_28]
0x14006e6af  mov     [rbp+var_28], 0
0x14006e6b7  mov     rcx, rax
0x14006e6ba  call    MpDlpGetProcessContextFromTokenAttribute
0x14006e6bf  test    eax, eax
0x14006e6c1  js      short loc_14006E6D6
0x14006e6c3  mov     rcx, [rbp+var_28]
0x14006e6c7  cmp     rcx, rbx
0x14006e6ca  jz      short loc_14006E6D1
0x14006e6cc  mov     rdi, rcx
0x14006e6cf  jmp     short loc_14006E6D6
0x14006e6d1  call    MpReleaseProcessContext
0x14006e6d6  mov     rcx, r14; ImpersonationToken
0x14006e6d9  call    cs:__imp_PsDereferenceImpersonationToken
0x14006e6e0  nop     dword ptr [rax+rax+00h]
0x14006e6e5  mov     rax, [rbp+FileNameInformation]
0x14006e6e9  lea     rcx, [rbp+var_30]
0x14006e6ed  mov     r9d, [r15+54h]
0x14006e6f1  add     rax, 8
0x14006e6f5  mov     [rsp+70h+var_40], rcx; __int64
0x14006e6fa  mov     r8, rdi
0x14006e6fd  mov     [rsp+70h+var_48], rax; __int64
0x14006e702  mov     rdx, r12
0x14006e705  mov     rcx, rsi; CallbackData
0x14006e708  mov     [rsp+70h+var_50], 0; int
0x14006e710  call    MpDlpCheckOperation
0x14006e715  mov     r14d, eax
0x14006e718  cmp     rdi, rbx
0x14006e71b  jz      short loc_14006E725
0x14006e71d  mov     rcx, rdi
0x14006e720  call    MpReleaseProcessContext
0x14006e725  cmp     r14d, 2
0x14006e729  jnz     short loc_14006E78D
0x14006e72b  lfence
0x14006e72e  mov     eax, [r15+54h]
0x14006e732  lea     rcx, aRemoteDevice; "remote device"
0x14006e739  mov     r8d, [rbx+18h]
0x14006e73d  test    al, 10h
0x14006e73f  mov     rdx, [rbx+80h]
0x14006e746  lea     rax, aExternalDevice; "external device"
0x14006e74d  cmovz   rcx, rax
0x14006e751  mov     rax, [rsi+10h]
0x14006e755  mov     r9, [rax+8]
0x14006e759  mov     eax, dword ptr [rbp+var_30]
0x14006e75c  add     r9, 58h ; 'X'
0x14006e760  mov     dword ptr [rsp+70h+var_48], eax
0x14006e764  mov     qword ptr [rsp+70h+var_50], rcx
0x14006e769  lea     rcx, aDlpFilterDenie_2; "[DLP-filter] Denied Process '%wZ' (pid "...
0x14006e770  call    MpLogPrintfW
0x14006e775  lea     r8, [rsi+18h]
0x14006e779  mov     rcx, rbx
0x14006e77c  lea     rdx, [rbp+var_30]
0x14006e780  call    MpDlpBlockActionToNtStatus
0x14006e785  mov     qword ptr [rsi+20h], 0
0x14006e78d  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14006e791  test    rcx, rcx
0x14006e794  jz      short loc_14006E7A2
0x14006e796  call    cs:__imp_FltReleaseFileNameInformation
0x14006e79d  nop     dword ptr [rax+rax+00h]
0x14006e7a2  test    rbx, rbx
0x14006e7a5  jz      short loc_14006E7AF
0x14006e7a7  mov     rcx, rbx
0x14006e7aa  call    MpReleaseProcessContext
0x14006e7af  mov     eax, r14d
0x14006e7b2  mov     rcx, [rbp+var_8]
0x14006e7b6  xor     rcx, rsp; StackCookie
0x14006e7b9  call    __security_check_cookie
0x14006e7be  add     rsp, 70h
0x14006e7c2  pop     r15
0x14006e7c4  pop     r14
0x14006e7c6  pop     r12
0x14006e7c8  pop     rdi
0x14006e7c9  pop     rsi
0x14006e7ca  pop     rbx
0x14006e7cb  pop     rbp
0x14006e7cc  retn
```
