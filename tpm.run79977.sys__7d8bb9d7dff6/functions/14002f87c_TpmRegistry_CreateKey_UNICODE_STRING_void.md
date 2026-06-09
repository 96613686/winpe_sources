# TpmRegistry::CreateKey(_UNICODE_STRING *,void *)

- ea: `0x14002f87c`
- end: `0x14002fc84`
- name: `?CreateKey@TpmRegistry@@CAJPEAU_UNICODE_STRING@@PEAX@Z`
- size: `1032`
- prototype: `static int(struct _UNICODE_STRING *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002fc8c`
- `0x14002fd1c`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14000fe5c`
- `0x14002f87c`
- `0x140039740`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x14002fa84`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002fa84`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002fbf6`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002fbf6`
- `ntoskrnl!ZwCreateKey` at `0x14002f91f`
- `ntoskrnl!ZwCreateKey` at `0x14002f91f`
- `ntoskrnl!ObGetObjectSecurity` at `0x14002fa05`
- `ntoskrnl!ObGetObjectSecurity` at `0x14002fa05`
- `ntoskrnl!SeAssignSecurityEx` at `0x14002fac5`
- `ntoskrnl!SeAssignSecurityEx` at `0x14002fac5`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x14002fb17`
- `ntoskrnl!RtlSetControlSecurityDescriptor` at `0x14002fb17`
- `ntoskrnl!ZwSetSecurityObject` at `0x14002fb9f`
- `ntoskrnl!ZwSetSecurityObject` at `0x14002fb9f`
- `ntoskrnl!SeDeassignSecurity` at `0x14002fc0c`
- `ntoskrnl!SeDeassignSecurity` at `0x14002fc0c`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14002fc24`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14002fc24`
- `ntoskrnl!ZwClose` at `0x14002fc4d`
- `ntoskrnl!ZwClose` at `0x14002fc4d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f9b0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002f9b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fc38`
- `ntoskrnl!ObfDereferenceObject` at `0x14002fc38`

## pseudocode

```c
__int64 __fastcall TpmRegistry::CreateKey(struct _UNICODE_STRING *a1, void *a2)
{
  PVOID v3; // rdi
  NTSTATUS ObjectSecurity; // ebx
  NTSTATUS v5; // eax
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned __int8 MemoryAllocated[8]; // [rsp+50h] [rbp-79h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+58h] [rbp-71h] BYREF
  __int128 v13; // [rsp+60h] [rbp-69h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-51h] BYREF
  PVOID Object[2]; // [rsp+80h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-39h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+C0h] [rbp-9h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp+17h] BYREF

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  SecurityDescriptor = 0;
  MemoryAllocated[0] = 0;
  v3 = 0;
  NewDescriptor = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GenericMapping.GenericRead = 131097;
  GenericMapping.GenericWrite = 131078;
  GenericMapping.GenericExecute = 131097;
  GenericMapping.GenericAll = 983103;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectSecurity = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( ObjectSecurity < 0 || !a2 )
    goto LABEL_38;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    Object[1] = (PVOID)40;
    Object[0] = a2;
    v13 = *(_OWORD *)Object;
    WPP_SF__HEX_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, &v13);
  }
  Object[0] = 0;
  v5 = ObReferenceObjectByHandle(KeyHandle, 0x2001Fu, 0, 0, Object, 0);
  v3 = Object[0];
  ObjectSecurity = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v7 = 17;
LABEL_10:
      WPP_SF_d(v6->AttachedDevice, v7, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, (unsigned int)ObjectSecurity);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  ObjectSecurity = ObGetObjectSecurity(Object[0], &SecurityDescriptor, MemoryAllocated);
  if ( ObjectSecurity >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      *((_QWORD *)&v13 + 1) = 40;
      *(_QWORD *)&v13 = SecurityDescriptor;
      WPP_SF__HEX_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, &v13);
    }
    SeCaptureSubjectContext(&SubjectContext);
    ObjectSecurity = SeAssignSecurityEx(
                       SecurityDescriptor,
                       a2,
                       &NewDescriptor,
                       0,
                       1u,
                       0x1Bu,
                       &SubjectContext,
                       &GenericMapping,
                       PagedPool);
    if ( ObjectSecurity >= 0 )
    {
      ObjectSecurity = RtlSetControlSecurityDescriptor(NewDescriptor, 0x300u, 0x300u);
      if ( ObjectSecurity >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          *((_QWORD *)&v13 + 1) = 40;
          *(_QWORD *)&v13 = NewDescriptor;
          WPP_SF__HEX_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, &v13);
        }
        ObjectSecurity = ZwSetSecurityObject(KeyHandle, 0xFu, NewDescriptor);
        if ( ObjectSecurity >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids);
          }
          goto LABEL_37;
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        {
LABEL_37:
          SeReleaseSubjectContext(&SubjectContext);
          goto LABEL_38;
        }
        v9 = 23;
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_37;
        v9 = 21;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_37;
      v9 = 20;
    }
    WPP_SF_d(v8->AttachedDevice, v9, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids, (unsigned int)ObjectSecurity);
    goto LABEL_37;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v7 = 18;
    goto LABEL_10;
  }
LABEL_38:
  if ( NewDescriptor )
    SeDeassignSecurity(&NewDescriptor);
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
  if ( v3 )
    ObfDereferenceObject(v3);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)ObjectSecurity;
}

```

## disassembly

```asm
0x14002f87c  mov     [rsp-8+arg_10], rbx
0x14002f881  mov     [rsp-8+arg_18], rsi
0x14002f886  push    rbp
0x14002f887  push    rdi
0x14002f888  push    r12
0x14002f88a  push    r14
0x14002f88c  push    r15
0x14002f88e  lea     rbp, [rsp-37h]
0x14002f893  sub     rsp, 100h
0x14002f89a  mov     rax, cs:__security_cookie
0x14002f8a1  xor     rax, rsp
0x14002f8a4  mov     [rbp+57h+var_30], rax
0x14002f8a8  xor     r14d, r14d
0x14002f8ab  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14002f8af  mov     eax, 20019h
0x14002f8b4  mov     [rsp+120h+Disposition], r14; Disposition
0x14002f8b9  xorps   xmm0, xmm0
0x14002f8bc  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x14002f8c1  mov     rsi, rdx
0x14002f8c4  mov     [rbp+57h+KeyHandle], r14
0x14002f8c8  xor     r9d, r9d; TitleIndex
0x14002f8cb  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002f8d3  lea     edx, [rax+6]; DesiredAccess
0x14002f8d6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002f8de  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002f8e2  mov     [rbp+57h+SecurityDescriptor], r14
0x14002f8e6  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002f8ea  mov     [rbp+57h+MemoryAllocated], r14b
0x14002f8ee  mov     edi, r14d
0x14002f8f1  mov     [rbp+57h+NewDescriptor], r14
0x14002f8f5  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14002f8f9  mov     [rbp+57h+var_40.GenericRead], eax
0x14002f8fc  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14002f900  mov     [rbp+57h+var_40.GenericWrite], 20006h
0x14002f907  mov     [rbp+57h+var_40.GenericExecute], eax
0x14002f90a  mov     [rbp+57h+var_40.GenericAll], 0F003Fh
0x14002f911  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14002f915  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002f91a  mov     [rsp+120h+Class], r14; Class
0x14002f91f  call    cs:__imp_ZwCreateKey
0x14002f926  nop     dword ptr [rax+rax+00h]
0x14002f92b  mov     ebx, eax
0x14002f92d  test    eax, eax
0x14002f92f  js      loc_14002FC02
0x14002f935  test    rsi, rsi
0x14002f938  jz      loc_14002FC02
0x14002f93e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f945  lea     r15, WPP_GLOBAL_Control
0x14002f94c  lea     edx, [r14+28h]
0x14002f950  lea     r12, WPP_94e382a665763f71bd92d92ac5fb5bd5_Traceguids
0x14002f957  cmp     rcx, r15
0x14002f95a  jz      short loc_14002F98F
0x14002f95c  mov     eax, [rcx+2Ch]
0x14002f95f  test    al, 10h
0x14002f961  jz      short loc_14002F98F
0x14002f963  xorps   xmm0, xmm0
0x14002f966  lea     r9, [rbp+57h+var_C0]
0x14002f96a  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14002f96e  mov     word ptr [rbp+57h+Object+8], dx
0x14002f972  mov     r8, r12
0x14002f975  mov     [rbp+57h+Object], rsi
0x14002f979  lea     edx, [r14+10h]
0x14002f97d  movaps  xmm0, xmmword ptr [rbp+57h+Object]
0x14002f981  movdqa  [rbp+57h+var_C0], xmm0
0x14002f986  mov     rcx, [rcx+18h]
0x14002f98a  call    WPP_SF__HEX_
0x14002f98f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002f993  lea     rax, [rbp+57h+Object]
0x14002f997  mov     qword ptr [rsp+120h+CreateOptions], r14; HandleInformation
0x14002f99c  xor     r9d, r9d; AccessMode
0x14002f99f  xor     r8d, r8d; ObjectType
0x14002f9a2  mov     [rsp+120h+Class], rax; Object
0x14002f9a7  mov     edx, 2001Fh; DesiredAccess
0x14002f9ac  mov     [rbp+57h+Object], r14
0x14002f9b0  call    cs:__imp_ObReferenceObjectByHandle
0x14002f9b7  nop     dword ptr [rax+rax+00h]
0x14002f9bc  mov     rdi, [rbp+57h+Object]
0x14002f9c0  mov     ebx, eax
0x14002f9c2  test    eax, eax
0x14002f9c4  jns     short loc_14002F9FA
0x14002f9c6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f9cd  cmp     rcx, r15
0x14002f9d0  jz      loc_14002FC02
0x14002f9d6  mov     eax, [rcx+2Ch]
0x14002f9d9  test    al, 1
0x14002f9db  jz      loc_14002FC02
0x14002f9e1  mov     edx, 11h
0x14002f9e6  mov     rcx, [rcx+18h]
0x14002f9ea  mov     r9d, ebx
0x14002f9ed  mov     r8, r12
0x14002f9f0  call    WPP_SF_d
0x14002f9f5  jmp     loc_14002FC02
0x14002f9fa  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14002f9fe  mov     rcx, rdi; Object
0x14002fa01  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14002fa05  call    cs:__imp_ObGetObjectSecurity
0x14002fa0c  nop     dword ptr [rax+rax+00h]
0x14002fa11  mov     ebx, eax
0x14002fa13  test    eax, eax
0x14002fa15  jns     short loc_14002FA39
0x14002fa17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fa1e  cmp     rcx, r15
0x14002fa21  jz      loc_14002FC02
0x14002fa27  mov     eax, [rcx+2Ch]
0x14002fa2a  test    al, 1
0x14002fa2c  jz      loc_14002FC02
0x14002fa32  mov     edx, 12h
0x14002fa37  jmp     short loc_14002F9E6
0x14002fa39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fa40  cmp     rcx, r15
0x14002fa43  jz      short loc_14002FA80
0x14002fa45  mov     eax, [rcx+2Ch]
0x14002fa48  test    al, 10h
0x14002fa4a  jz      short loc_14002FA80
0x14002fa4c  mov     rax, [rbp+57h+SecurityDescriptor]
0x14002fa50  lea     r9, [rbp+57h+var_C0]
0x14002fa54  xorps   xmm0, xmm0
0x14002fa57  mov     r8, r12
0x14002fa5a  movups  [rbp+57h+var_C0], xmm0
0x14002fa5e  mov     qword ptr [rbp+57h+var_C0], rax
0x14002fa62  mov     eax, 28h ; '('
0x14002fa67  mov     word ptr [rbp+57h+var_C0+8], ax
0x14002fa6b  movaps  xmm0, [rbp+57h+var_C0]
0x14002fa6f  movdqa  [rbp+57h+var_C0], xmm0
0x14002fa74  mov     rcx, [rcx+18h]
0x14002fa78  lea     edx, [rax-15h]
0x14002fa7b  call    WPP_SF__HEX_
0x14002fa80  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14002fa84  call    cs:__imp_SeCaptureSubjectContext
0x14002fa8b  nop     dword ptr [rax+rax+00h]
0x14002fa90  mov     rcx, [rbp+57h+SecurityDescriptor]; ParentDescriptor
0x14002fa94  lea     rax, [rbp+57h+var_40]
0x14002fa98  mov     [rsp+120h+PoolType], 1; PoolType
0x14002faa0  lea     r8, [rbp+57h+NewDescriptor]; NewDescriptor
0x14002faa4  mov     [rsp+120h+GenericMapping], rax; GenericMapping
0x14002faa9  xor     r9d, r9d; ObjectType
0x14002faac  lea     rax, [rbp+57h+SubjectContext]
0x14002fab0  mov     rdx, rsi; ExplicitDescriptor
0x14002fab3  mov     [rsp+120h+Disposition], rax; SubjectContext
0x14002fab8  mov     [rsp+120h+CreateOptions], 1Bh; AutoInheritFlags
0x14002fac0  mov     byte ptr [rsp+120h+Class], 1; IsDirectoryObject
0x14002fac5  call    cs:__imp_SeAssignSecurityEx
0x14002facc  nop     dword ptr [rax+rax+00h]
0x14002fad1  mov     ebx, eax
0x14002fad3  test    eax, eax
0x14002fad5  jns     short loc_14002FB0B
0x14002fad7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fade  cmp     rcx, r15
0x14002fae1  jz      loc_14002FBF2
0x14002fae7  mov     eax, [rcx+2Ch]
0x14002faea  test    al, 1
0x14002faec  jz      loc_14002FBF2
0x14002faf2  mov     edx, 14h
0x14002faf7  mov     rcx, [rcx+18h]
0x14002fafb  mov     r9d, ebx
0x14002fafe  mov     r8, r12
0x14002fb01  call    WPP_SF_d
0x14002fb06  jmp     loc_14002FBF2
0x14002fb0b  mov     rcx, [rbp+57h+NewDescriptor]; SecurityDescriptor
0x14002fb0f  mov     edx, 300h; ControlBitsOfInterest
0x14002fb14  mov     r8d, edx; ControlBitsToSet
0x14002fb17  call    cs:__imp_RtlSetControlSecurityDescriptor
0x14002fb1e  nop     dword ptr [rax+rax+00h]
0x14002fb23  mov     ebx, eax
0x14002fb25  test    eax, eax
0x14002fb27  jns     short loc_14002FB4B
0x14002fb29  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fb30  cmp     rcx, r15
0x14002fb33  jz      loc_14002FBF2
0x14002fb39  mov     eax, [rcx+2Ch]
0x14002fb3c  test    al, 1
0x14002fb3e  jz      loc_14002FBF2
0x14002fb44  mov     edx, 15h
0x14002fb49  jmp     short loc_14002FAF7
0x14002fb4b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fb52  cmp     rcx, r15
0x14002fb55  jz      short loc_14002FB92
0x14002fb57  mov     eax, [rcx+2Ch]
0x14002fb5a  test    al, 10h
0x14002fb5c  jz      short loc_14002FB92
0x14002fb5e  mov     rax, [rbp+57h+NewDescriptor]
0x14002fb62  lea     r9, [rbp+57h+var_C0]
0x14002fb66  xorps   xmm0, xmm0
0x14002fb69  mov     r8, r12
0x14002fb6c  movups  [rbp+57h+var_C0], xmm0
0x14002fb70  mov     qword ptr [rbp+57h+var_C0], rax
0x14002fb74  mov     eax, 28h ; '('
0x14002fb79  mov     word ptr [rbp+57h+var_C0+8], ax
0x14002fb7d  movaps  xmm0, [rbp+57h+var_C0]
0x14002fb81  movdqa  [rbp+57h+var_C0], xmm0
0x14002fb86  mov     rcx, [rcx+18h]
0x14002fb8a  lea     edx, [rax-12h]
0x14002fb8d  call    WPP_SF__HEX_
0x14002fb92  mov     r8, [rbp+57h+NewDescriptor]; SecurityDescriptor
0x14002fb96  mov     edx, 0Fh; SecurityInformation
0x14002fb9b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002fb9f  call    cs:__imp_ZwSetSecurityObject
0x14002fba6  nop     dword ptr [rax+rax+00h]
0x14002fbab  mov     ebx, eax
0x14002fbad  test    eax, eax
0x14002fbaf  jns     short loc_14002FBCE
0x14002fbb1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fbb8  cmp     rcx, r15
0x14002fbbb  jz      short loc_14002FBF2
0x14002fbbd  mov     eax, [rcx+2Ch]
0x14002fbc0  test    al, 1
0x14002fbc2  jz      short loc_14002FBF2
0x14002fbc4  mov     edx, 17h
0x14002fbc9  jmp     loc_14002FAF7
0x14002fbce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fbd5  cmp     rcx, r15
0x14002fbd8  jz      short loc_14002FBF2
0x14002fbda  mov     eax, [rcx+2Ch]
0x14002fbdd  test    al, 4
0x14002fbdf  jz      short loc_14002FBF2
0x14002fbe1  mov     rcx, [rcx+18h]
0x14002fbe5  mov     edx, 18h
0x14002fbea  mov     r8, r12
0x14002fbed  call    WPP_SF_
0x14002fbf2  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14002fbf6  call    cs:__imp_SeReleaseSubjectContext
0x14002fbfd  nop     dword ptr [rax+rax+00h]
0x14002fc02  cmp     [rbp+57h+NewDescriptor], r14
0x14002fc06  jz      short loc_14002FC18
0x14002fc08  lea     rcx, [rbp+57h+NewDescriptor]; SecurityDescriptor
0x14002fc0c  call    cs:__imp_SeDeassignSecurity
0x14002fc13  nop     dword ptr [rax+rax+00h]
0x14002fc18  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14002fc1c  test    rcx, rcx
0x14002fc1f  jz      short loc_14002FC30
0x14002fc21  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14002fc24  call    cs:__imp_ObReleaseObjectSecurity
0x14002fc2b  nop     dword ptr [rax+rax+00h]
0x14002fc30  test    rdi, rdi
0x14002fc33  jz      short loc_14002FC44
0x14002fc35  mov     rcx, rdi; Object
0x14002fc38  call    cs:__imp_ObfDereferenceObject
0x14002fc3f  nop     dword ptr [rax+rax+00h]
0x14002fc44  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002fc48  test    rcx, rcx
0x14002fc4b  jz      short loc_14002FC59
0x14002fc4d  call    cs:__imp_ZwClose
0x14002fc54  nop     dword ptr [rax+rax+00h]
0x14002fc59  mov     eax, ebx
0x14002fc5b  mov     rcx, [rbp+57h+var_30]
0x14002fc5f  xor     rcx, rsp; StackCookie
0x14002fc62  call    __security_check_cookie
0x14002fc67  lea     r11, [rsp+120h+var_20]
0x14002fc6f  mov     rbx, [r11+40h]
0x14002fc73  mov     rsi, [r11+48h]
0x14002fc77  mov     rsp, r11
0x14002fc7a  pop     r15
0x14002fc7c  pop     r14
0x14002fc7e  pop     r12
0x14002fc80  pop     rdi
0x14002fc81  pop     rbp
0x14002fc82  retn
```
