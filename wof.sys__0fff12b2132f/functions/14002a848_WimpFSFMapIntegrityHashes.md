# WimpFSFMapIntegrityHashes

- ea: `0x14002a848`
- end: `0x14002a9d5`
- name: `WimpFSFMapIntegrityHashes`
- size: `397`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140028488`

## callees

- `0x14002a848`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002a9b6`
- `ntoskrnl!ZwClose` at `0x14002a9b6`
- `ntoskrnl!MmMapViewOfSection` at `0x14002a953`
- `ntoskrnl!MmMapViewOfSection` at `0x14002a953`
- `ntoskrnl!ZwCreateSection` at `0x14002a8c0`
- `ntoskrnl!ZwCreateSection` at `0x14002a8c0`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002a906`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002a8f0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002a8f0`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a9a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a9a1`

## pseudocode

```c
__int64 __fastcall WimpFSFMapIntegrityHashes(
        HANDLE FileHandle,
        unsigned int a2,
        PVOID *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v7; // rbx
  NTSTATUS v9; // edi
  PVOID v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rbx
  PVOID Object; // [rsp+50h] [rbp-49h] BYREF
  __int64 v15; // [rsp+58h] [rbp-41h] BYREF
  __int64 v16; // [rsp+60h] [rbp-39h] BYREF
  __int64 v17; // [rsp+68h] [rbp-31h] BYREF
  void *SectionHandle; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF

  v7 = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  SectionHandle = 0;
  Object = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  if ( v9 < 0
    || (v9 = ObReferenceObjectByHandle(SectionHandle, 0, 0, 0, &Object, 0), v9 < 0)
    || (v17 = v7,
        v15 = 0,
        v16 = 0,
        v9 = MmMapViewOfSection(Object, PsInitialSystemProcess, &v15, 0, 0, &v17, &v16, 2, 0, 2),
        v9 < 0) )
  {
    v10 = Object;
  }
  else
  {
    v10 = 0;
    v11 = v15;
    v12 = v7 - v17;
    *a3 = Object;
    *a5 = v16;
    Object = 0;
    *a4 = v11;
    *a6 = v11 + v12;
  }
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002a848  push    rbp
0x14002a84a  push    rbx
0x14002a84b  push    rsi
0x14002a84c  push    rdi
0x14002a84d  push    r14
0x14002a84f  push    r15
0x14002a851  lea     rbp, [rsp-1Fh]
0x14002a856  sub     rsp, 0B8h
0x14002a85d  xor     r15d, r15d
0x14002a860  mov     [rsp+0E0h+FileHandle], rcx; FileHandle
0x14002a865  mov     rsi, r9
0x14002a868  mov     ebx, edx
0x14002a86a  mov     r14, r8
0x14002a86d  mov     [rsp+0E0h+AllocationAttributes], 8000000h; AllocationAttributes
0x14002a875  xorps   xmm0, xmm0
0x14002a878  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14002a880  lea     edx, [r15+4]; DesiredAccess
0x14002a884  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 200h
0x14002a88c  xor     r9d, r9d; MaximumSize
0x14002a88f  mov     [rbp+47h+SectionHandle], r15
0x14002a893  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14002a897  mov     [rbp+47h+Object], r15
0x14002a89b  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x14002a89f  mov     [rbp+47h+var_78], r15
0x14002a8a3  mov     [rbp+47h+var_88], r15
0x14002a8a7  mov     [rbp+47h+var_80], r15
0x14002a8ab  mov     [rbp+47h+ObjectAttributes.RootDirectory], r15
0x14002a8af  mov     [rbp+47h+ObjectAttributes.ObjectName], r15
0x14002a8b3  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a8b8  mov     [rsp+0E0h+SectionPageProtection], 2; SectionPageProtection
0x14002a8c0  call    cs:__imp_ZwCreateSection
0x14002a8c7  nop     dword ptr [rax+rax+00h]
0x14002a8cc  mov     edi, eax
0x14002a8ce  test    eax, eax
0x14002a8d0  js      loc_14002A995
0x14002a8d6  mov     rcx, [rbp+47h+SectionHandle]; Handle
0x14002a8da  lea     rax, [rbp+47h+Object]
0x14002a8de  mov     qword ptr [rsp+0E0h+AllocationAttributes], r15; HandleInformation
0x14002a8e3  xor     r9d, r9d; AccessMode
0x14002a8e6  xor     r8d, r8d; ObjectType
0x14002a8e9  mov     qword ptr [rsp+0E0h+SectionPageProtection], rax; Object
0x14002a8ee  xor     edx, edx; DesiredAccess
0x14002a8f0  call    cs:__imp_ObReferenceObjectByHandle
0x14002a8f7  nop     dword ptr [rax+rax+00h]
0x14002a8fc  mov     edi, eax
0x14002a8fe  test    eax, eax
0x14002a900  js      loc_14002A995
0x14002a906  mov     rdx, cs:__imp_PsInitialSystemProcess
0x14002a90d  lea     rax, [rbp+47h+var_80]
0x14002a911  mov     rcx, [rbp+47h+Object]
0x14002a915  lea     r8, [rbp+47h+var_88]
0x14002a919  mov     [rsp+0E0h+var_98], 2
0x14002a921  xor     r9d, r9d
0x14002a924  mov     [rsp+0E0h+var_A0], r15d
0x14002a929  mov     [rsp+0E0h+var_A8], 2
0x14002a931  mov     [rsp+0E0h+FileHandle], rax
0x14002a936  lea     rax, [rbp+47h+var_78]
0x14002a93a  mov     [rbp+47h+var_78], rbx
0x14002a93e  mov     [rbp+47h+var_88], r15
0x14002a942  mov     [rbp+47h+var_80], r15
0x14002a946  mov     rdx, [rdx]
0x14002a949  mov     qword ptr [rsp+0E0h+AllocationAttributes], rax
0x14002a94e  mov     qword ptr [rsp+0E0h+SectionPageProtection], r15
0x14002a953  call    cs:__imp_MmMapViewOfSection
0x14002a95a  nop     dword ptr [rax+rax+00h]
0x14002a95f  mov     edi, eax
0x14002a961  test    eax, eax
0x14002a963  js      short loc_14002A995
0x14002a965  mov     rax, [rbp+47h+Object]
0x14002a969  mov     r8d, r15d
0x14002a96c  mov     rdx, [rbp+47h+var_88]
0x14002a970  mov     rcx, [rbp+47h+arg_20]
0x14002a974  sub     rbx, [rbp+47h+var_78]
0x14002a978  mov     [r14], rax
0x14002a97b  add     rbx, rdx
0x14002a97e  mov     rax, [rbp+47h+var_80]
0x14002a982  mov     [rcx], rax
0x14002a985  mov     rax, [rbp+47h+arg_28]
0x14002a989  mov     [rbp+47h+Object], r15
0x14002a98d  mov     [rsi], rdx
0x14002a990  mov     [rax], rbx
0x14002a993  jmp     short loc_14002A999
0x14002a995  mov     r8, [rbp+47h+Object]
0x14002a999  test    r8, r8
0x14002a99c  jz      short loc_14002A9AD
0x14002a99e  mov     rcx, r8; Object
0x14002a9a1  call    cs:__imp_ObfDereferenceObject
0x14002a9a8  nop     dword ptr [rax+rax+00h]
0x14002a9ad  mov     rcx, [rbp+47h+SectionHandle]; Handle
0x14002a9b1  test    rcx, rcx
0x14002a9b4  jz      short loc_14002A9C2
0x14002a9b6  call    cs:__imp_ZwClose
0x14002a9bd  nop     dword ptr [rax+rax+00h]
0x14002a9c2  mov     eax, edi
0x14002a9c4  add     rsp, 0B8h
0x14002a9cb  pop     r15
0x14002a9cd  pop     r14
0x14002a9cf  pop     rdi
0x14002a9d0  pop     rsi
0x14002a9d1  pop     rbx
0x14002a9d2  pop     rbp
0x14002a9d3  retn
```
