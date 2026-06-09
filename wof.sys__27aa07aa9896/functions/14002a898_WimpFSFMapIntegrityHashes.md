# WimpFSFMapIntegrityHashes

- ea: `0x14002a898`
- end: `0x14002aa25`
- name: `WimpFSFMapIntegrityHashes`
- size: `397`
- prototype: `__int64 __fastcall(HANDLE FileHandle, unsigned int, PVOID *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400284d8`

## callees

- `0x14002a898`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002aa06`
- `ntoskrnl!ZwClose` at `0x14002aa06`
- `ntoskrnl!MmMapViewOfSection` at `0x14002a9a3`
- `ntoskrnl!MmMapViewOfSection` at `0x14002a9a3`
- `ntoskrnl!ZwCreateSection` at `0x14002a910`
- `ntoskrnl!ZwCreateSection` at `0x14002a910`
- `ntoskrnl!PsInitialSystemProcess` at `0x14002a956`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002a940`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002a940`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a9f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a9f1`

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
0x14002a898  push    rbp
0x14002a89a  push    rbx
0x14002a89b  push    rsi
0x14002a89c  push    rdi
0x14002a89d  push    r14
0x14002a89f  push    r15
0x14002a8a1  lea     rbp, [rsp-1Fh]
0x14002a8a6  sub     rsp, 0B8h
0x14002a8ad  xor     r15d, r15d
0x14002a8b0  mov     [rsp+0E0h+FileHandle], rcx; FileHandle
0x14002a8b5  mov     rsi, r9
0x14002a8b8  mov     ebx, edx
0x14002a8ba  mov     r14, r8
0x14002a8bd  mov     [rsp+0E0h+AllocationAttributes], 8000000h; AllocationAttributes
0x14002a8c5  xorps   xmm0, xmm0
0x14002a8c8  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14002a8d0  lea     edx, [r15+4]; DesiredAccess
0x14002a8d4  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 200h
0x14002a8dc  xor     r9d, r9d; MaximumSize
0x14002a8df  mov     [rbp+47h+SectionHandle], r15
0x14002a8e3  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14002a8e7  mov     [rbp+47h+Object], r15
0x14002a8eb  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x14002a8ef  mov     [rbp+47h+var_78], r15
0x14002a8f3  mov     [rbp+47h+var_88], r15
0x14002a8f7  mov     [rbp+47h+var_80], r15
0x14002a8fb  mov     [rbp+47h+ObjectAttributes.RootDirectory], r15
0x14002a8ff  mov     [rbp+47h+ObjectAttributes.ObjectName], r15
0x14002a903  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a908  mov     [rsp+0E0h+SectionPageProtection], 2; SectionPageProtection
0x14002a910  call    cs:__imp_ZwCreateSection
0x14002a917  nop     dword ptr [rax+rax+00h]
0x14002a91c  mov     edi, eax
0x14002a91e  test    eax, eax
0x14002a920  js      loc_14002A9E5
0x14002a926  mov     rcx, [rbp+47h+SectionHandle]; Handle
0x14002a92a  lea     rax, [rbp+47h+Object]
0x14002a92e  mov     qword ptr [rsp+0E0h+AllocationAttributes], r15; HandleInformation
0x14002a933  xor     r9d, r9d; AccessMode
0x14002a936  xor     r8d, r8d; ObjectType
0x14002a939  mov     qword ptr [rsp+0E0h+SectionPageProtection], rax; Object
0x14002a93e  xor     edx, edx; DesiredAccess
0x14002a940  call    cs:__imp_ObReferenceObjectByHandle
0x14002a947  nop     dword ptr [rax+rax+00h]
0x14002a94c  mov     edi, eax
0x14002a94e  test    eax, eax
0x14002a950  js      loc_14002A9E5
0x14002a956  mov     rdx, cs:__imp_PsInitialSystemProcess
0x14002a95d  lea     rax, [rbp+47h+var_80]
0x14002a961  mov     rcx, [rbp+47h+Object]
0x14002a965  lea     r8, [rbp+47h+var_88]
0x14002a969  mov     [rsp+0E0h+var_98], 2
0x14002a971  xor     r9d, r9d
0x14002a974  mov     [rsp+0E0h+var_A0], r15d
0x14002a979  mov     [rsp+0E0h+var_A8], 2
0x14002a981  mov     [rsp+0E0h+FileHandle], rax
0x14002a986  lea     rax, [rbp+47h+var_78]
0x14002a98a  mov     [rbp+47h+var_78], rbx
0x14002a98e  mov     [rbp+47h+var_88], r15
0x14002a992  mov     [rbp+47h+var_80], r15
0x14002a996  mov     rdx, [rdx]
0x14002a999  mov     qword ptr [rsp+0E0h+AllocationAttributes], rax
0x14002a99e  mov     qword ptr [rsp+0E0h+SectionPageProtection], r15
0x14002a9a3  call    cs:__imp_MmMapViewOfSection
0x14002a9aa  nop     dword ptr [rax+rax+00h]
0x14002a9af  mov     edi, eax
0x14002a9b1  test    eax, eax
0x14002a9b3  js      short loc_14002A9E5
0x14002a9b5  mov     rax, [rbp+47h+Object]
0x14002a9b9  mov     r8d, r15d
0x14002a9bc  mov     rdx, [rbp+47h+var_88]
0x14002a9c0  mov     rcx, [rbp+47h+arg_20]
0x14002a9c4  sub     rbx, [rbp+47h+var_78]
0x14002a9c8  mov     [r14], rax
0x14002a9cb  add     rbx, rdx
0x14002a9ce  mov     rax, [rbp+47h+var_80]
0x14002a9d2  mov     [rcx], rax
0x14002a9d5  mov     rax, [rbp+47h+arg_28]
0x14002a9d9  mov     [rbp+47h+Object], r15
0x14002a9dd  mov     [rsi], rdx
0x14002a9e0  mov     [rax], rbx
0x14002a9e3  jmp     short loc_14002A9E9
0x14002a9e5  mov     r8, [rbp+47h+Object]
0x14002a9e9  test    r8, r8
0x14002a9ec  jz      short loc_14002A9FD
0x14002a9ee  mov     rcx, r8; Object
0x14002a9f1  call    cs:__imp_ObfDereferenceObject
0x14002a9f8  nop     dword ptr [rax+rax+00h]
0x14002a9fd  mov     rcx, [rbp+47h+SectionHandle]; Handle
0x14002aa01  test    rcx, rcx
0x14002aa04  jz      short loc_14002AA12
0x14002aa06  call    cs:__imp_ZwClose
0x14002aa0d  nop     dword ptr [rax+rax+00h]
0x14002aa12  mov     eax, edi
0x14002aa14  add     rsp, 0B8h
0x14002aa1b  pop     r15
0x14002aa1d  pop     r14
0x14002aa1f  pop     rdi
0x14002aa20  pop     rsi
0x14002aa21  pop     rbx
0x14002aa22  pop     rbp
0x14002aa23  retn
```
