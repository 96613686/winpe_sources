# TpmGetUserType(_USER_TYPE *)

- ea: `0x140003ad0`
- end: `0x140003c22`
- name: `?TpmGetUserType@@YAJPEAW4_USER_TYPE@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(enum _USER_TYPE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400038e0`
- `0x140017ea0`

## callees

- `0x140003ad0`
- `0x140004520`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140003af8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140003af8`
- `ntoskrnl!ExGetPreviousMode` at `0x140003b04`
- `ntoskrnl!ExGetPreviousMode` at `0x140003b04`
- `ntoskrnl!SeAccessCheck` at `0x140003b58`
- `ntoskrnl!SeAccessCheck` at `0x140003b58`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003b6c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140003b6c`

## pseudocode

```c
__int64 __fastcall TpmGetUserType(enum _USER_TYPE *a1)
{
  KPROCESSOR_MODE AccessMode; // al
  BOOLEAN v3; // bl
  __int64 result; // rax
  _SECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+50h] [rbp-28h] BYREF
  int AccessStatus; // [rsp+80h] [rbp+8h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp+10h] BYREF

  *(_DWORD *)a1 = 0;
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&SubjectSecurityContext, 0, sizeof(SubjectSecurityContext));
  SeCaptureSubjectContext(&SubjectSecurityContext);
  AccessMode = ExGetPreviousMode();
  v3 = SeAccessCheck(
         qword_14003B9F0,
         &SubjectSecurityContext,
         0,
         1u,
         0,
         0,
         &GenericMapping,
         AccessMode,
         &GrantedAccess,
         &AccessStatus);
  SeReleaseSubjectContext(&SubjectSecurityContext);
  result = (unsigned int)AccessStatus;
  if ( !v3 && (AccessStatus == -1073741790 || (AccessStatus & 0xC0000000) != 0xC0000000) )
    result = 3223916548LL;
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == -1071050748 )
    {
      result = TpmAccessCheck(1);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == -1071050748 )
        {
          result = TpmAccessCheck(3);
          if ( (_DWORD)result )
          {
            if ( (int)result >= 0 )
              return 3221225473LL;
          }
          else
          {
            *(_DWORD *)a1 = 3;
          }
        }
      }
      else
      {
        *(_DWORD *)a1 = 1;
      }
    }
    else if ( (int)result >= 0 )
    {
      return 3221225473LL;
    }
  }
  else
  {
    *(_DWORD *)a1 = 2;
  }
  return result;
}

```

## disassembly

```asm
0x140003ad0  mov     rax, rsp
0x140003ad3  mov     [rax+18h], rbx
0x140003ad7  push    rdi
0x140003ad8  sub     rsp, 70h
0x140003adc  xor     ebx, ebx
0x140003ade  xorps   xmm0, xmm0
0x140003ae1  mov     [rcx], ebx
0x140003ae3  mov     rdi, rcx
0x140003ae6  lea     rcx, [rax-28h]; SubjectContext
0x140003aea  mov     [rax+8], ebx
0x140003aed  mov     [rax+10h], ebx
0x140003af0  movups  xmmword ptr [rax-28h], xmm0
0x140003af4  movups  xmmword ptr [rax-18h], xmm0
0x140003af8  call    cs:__imp_SeCaptureSubjectContext
0x140003aff  nop     dword ptr [rax+rax+00h]
0x140003b04  call    cs:__imp_ExGetPreviousMode
0x140003b0b  nop     dword ptr [rax+rax+00h]
0x140003b10  lea     rcx, [rsp+78h+arg_0]
0x140003b18  mov     r9d, 1; DesiredAccess
0x140003b1e  mov     [rsp+78h+AccessStatus], rcx; AccessStatus
0x140003b23  lea     rdx, [rsp+78h+SubjectSecurityContext]; SubjectSecurityContext
0x140003b28  lea     rcx, [rsp+78h+arg_8]
0x140003b30  xor     r8d, r8d; SubjectContextLocked
0x140003b33  mov     [rsp+78h+GrantedAccess], rcx; GrantedAccess
0x140003b38  lea     rcx, qword_14003B9F0; SecurityDescriptor
0x140003b3f  mov     [rsp+78h+AccessMode], al; AccessMode
0x140003b43  lea     rax, GenericMapping
0x140003b4a  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x140003b4f  mov     [rsp+78h+Privileges], rbx; Privileges
0x140003b54  mov     [rsp+78h+PreviouslyGrantedAccess], ebx; PreviouslyGrantedAccess
0x140003b58  call    cs:__imp_SeAccessCheck
0x140003b5f  nop     dword ptr [rax+rax+00h]
0x140003b64  lea     rcx, [rsp+78h+SubjectSecurityContext]; SubjectContext
0x140003b69  movzx   ebx, al
0x140003b6c  call    cs:__imp_SeReleaseSubjectContext
0x140003b73  nop     dword ptr [rax+rax+00h]
0x140003b78  mov     eax, [rsp+78h+arg_0]
0x140003b7f  test    bl, bl
0x140003b81  jz      short loc_140003BC6
0x140003b83  test    eax, eax
0x140003b85  jnz     short loc_140003B9C
0x140003b87  mov     dword ptr [rdi], 2
0x140003b8d  mov     rbx, [rsp+78h+arg_10]
0x140003b95  add     rsp, 70h
0x140003b99  pop     rdi
0x140003b9a  retn
0x140003b9c  cmp     eax, 0C0291004h
0x140003ba1  jnz     short loc_140003BD4
0x140003ba3  mov     ecx, 1
0x140003ba8  call    ?TpmAccessCheck@@YAJW4_USER_TYPE@@@Z; TpmAccessCheck(_USER_TYPE)
0x140003bad  test    eax, eax
0x140003baf  jnz     short loc_140003BF2
0x140003bb1  mov     rbx, [rsp+78h+arg_10]
0x140003bb9  mov     dword ptr [rdi], 1
0x140003bbf  add     rsp, 70h
0x140003bc3  pop     rdi
0x140003bc4  retn
0x140003bc6  cmp     eax, 0C0000022h
0x140003bcb  jnz     short loc_140003BE0
0x140003bcd  mov     eax, 0C0291004h
0x140003bd2  jmp     short loc_140003B83
0x140003bd4  test    eax, eax
0x140003bd6  mov     ecx, 0C0000001h
0x140003bdb  cmovns  eax, ecx
0x140003bde  jmp     short loc_140003B8D
0x140003be0  mov     ecx, eax
0x140003be2  and     ecx, 0C0000000h
0x140003be8  cmp     ecx, 0C0000000h
0x140003bee  jz      short loc_140003B83
0x140003bf0  jmp     short loc_140003BCD
0x140003bf2  cmp     eax, 0C0291004h
0x140003bf7  jnz     short loc_140003B8D
0x140003bf9  mov     ecx, 3
0x140003bfe  call    ?TpmAccessCheck@@YAJW4_USER_TYPE@@@Z; TpmAccessCheck(_USER_TYPE)
0x140003c03  test    eax, eax
0x140003c05  jnz     short loc_140003C12
0x140003c07  mov     dword ptr [rdi], 3
0x140003c0d  jmp     loc_140003B8D
0x140003c12  js      loc_140003B8D
0x140003c18  mov     eax, 0C0000001h
0x140003c1d  jmp     loc_140003B8D
```
