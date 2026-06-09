# VhdmpiVhd2MapAndUnmapDaxFile(_VHD_BACKING_STORE_HEADER *)

- ea: `0x1400c4228`
- end: `0x1400c444d`
- name: `?VhdmpiVhd2MapAndUnmapDaxFile@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c5424`

## callees

- `0x140022654`
- `0x140023980`
- `0x140026930`
- `0x140036284`
- `0x1400c4228`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x1400c4359`
- `ntoskrnl!ZwCreateSection` at `0x1400c4359`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400c43de`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400c43de`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400c43f5`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400c43f5`
- `ntoskrnl!NtClose` at `0x1400c440c`
- `ntoskrnl!NtClose` at `0x1400c440c`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd2MapAndUnmapDaxFile(struct _VHD_BACKING_STORE_HEADER *a1, __int64 a2)
{
  char v2; // r14
  bool v3; // zf
  NTSTATUS v5; // ebx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned __int16 v8; // cx
  void *SectionHandle; // [rsp+80h] [rbp+30h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp+38h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp+40h] BYREF
  ULONG_PTR ViewSize; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  SectionHandle = 0;
  v3 = (*((_DWORD *)a1 + 52) & 0x800) == 0;
  FileHandle = 0;
  BaseAddress = 0;
  ViewSize = 0;
  if ( v3 )
  {
    v5 = -1073741811;
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      TraceEvents("VhdmpiVhd2MapAndUnmapDaxFile", 0xA33u, 2u, v6, "Cleanup [Status = ((NTSTATUS)0xC000000DL)]");
    goto LABEL_17;
  }
  LOBYTE(a2) = 1;
  v5 = VhdmpiPinFile(a1, a2, &FileHandle);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      goto LABEL_17;
    v8 = 2614;
    goto LABEL_9;
  }
  v2 = 1;
  v5 = ZwCreateSection(&SectionHandle, 6u, 0, 0, 4u, 0x8000000u, FileHandle);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x80000) )
      goto LABEL_17;
    v8 = 2625;
LABEL_9:
    TraceEvents("VhdmpiVhd2MapAndUnmapDaxFile", v8, 2u, v7, "Cleanup with status 0x%08X", v5);
    goto LABEL_17;
  }
  if ( ZwMapViewOfSection(
         SectionHandle,
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &BaseAddress,
         0,
         0,
         0,
         &ViewSize,
         ViewUnmap,
         0,
         4u) >= 0 )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  v5 = 0;
LABEL_17:
  if ( SectionHandle )
  {
    NtClose(SectionHandle);
    SectionHandle = 0;
  }
  if ( v2 && a1 != (struct _VHD_BACKING_STORE_HEADER *)&VhdmpiEmptyISOBackingStore )
    VhdmpiFileWrapperUnpinFile((char *)a1 + 72, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400c4228  push    rbp
0x1400c422a  push    rbx
0x1400c422b  push    rsi
0x1400c422c  push    rdi
0x1400c422d  push    r14
0x1400c422f  mov     rbp, rsp
0x1400c4232  sub     rsp, 50h
0x1400c4236  xor     r14b, r14b
0x1400c4239  mov     [rbp+SectionHandle], 0
0x1400c4241  test    dword ptr [rcx+0D0h], 800h
0x1400c424b  mov     rdi, rcx
0x1400c424e  mov     [rbp+arg_8], 0
0x1400c4256  mov     [rbp+BaseAddress], 0
0x1400c425e  mov     [rbp+ViewSize], 0
0x1400c4266  jnz     short loc_1400C42C2
0x1400c4268  mov     eax, cs:dword_1400876D0
0x1400c426e  mov     ebx, 0C000000Dh
0x1400c4273  cmp     eax, 2
0x1400c4276  jbe     loc_1400C4403
0x1400c427c  mov     edx, 80000h
0x1400c4281  lea     rcx, dword_1400876D0
0x1400c4288  call    _tlgKeywordOn
0x1400c428d  test    al, al
0x1400c428f  jz      loc_1400C4403
0x1400c4295  mov     ecx, 0A33h
0x1400c429a  lea     rax, aCleanupStatusN_7; "Cleanup [Status = ((NTSTATUS)0xC000000D"...
0x1400c42a1  mov     r9d, edx; int
0x1400c42a4  mov     qword ptr [rsp+50h+SectionPageProtection], rax; char *
0x1400c42a9  mov     edx, ecx; int
0x1400c42ab  mov     r8d, 2; int
0x1400c42b1  lea     rcx, aVhdmpivhd2mapa; "VhdmpiVhd2MapAndUnmapDaxFile"
0x1400c42b8  call    TraceEvents
0x1400c42bd  jmp     loc_1400C4403
0x1400c42c2  xor     r9d, r9d
0x1400c42c5  lea     r8, [rbp+arg_8]
0x1400c42c9  mov     dl, 1
0x1400c42cb  call    VhdmpiPinFile
0x1400c42d0  mov     ebx, eax
0x1400c42d2  test    eax, eax
0x1400c42d4  jns     short loc_1400C432F
0x1400c42d6  mov     ecx, cs:dword_1400876D0
0x1400c42dc  cmp     ecx, 2
0x1400c42df  jbe     loc_1400C4403
0x1400c42e5  mov     edx, 80000h
0x1400c42ea  lea     rcx, dword_1400876D0
0x1400c42f1  call    _tlgKeywordOn
0x1400c42f6  test    al, al
0x1400c42f8  jz      loc_1400C4403
0x1400c42fe  mov     ecx, 0A36h
0x1400c4303  mov     r9d, edx; int
0x1400c4306  mov     [rsp+50h+AllocationAttributes], ebx; char
0x1400c430a  mov     edx, ecx; int
0x1400c430c  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x1400c4313  lea     rcx, aVhdmpivhd2mapa; "VhdmpiVhd2MapAndUnmapDaxFile"
0x1400c431a  mov     qword ptr [rsp+50h+SectionPageProtection], rax; char *
0x1400c431f  mov     r8d, 2; int
0x1400c4325  call    TraceEvents
0x1400c432a  jmp     loc_1400C4403
0x1400c432f  mov     rax, [rbp+arg_8]
0x1400c4333  lea     rcx, [rbp+SectionHandle]; SectionHandle
0x1400c4337  mov     [rsp+50h+FileHandle], rax; FileHandle
0x1400c433c  xor     r9d, r9d; MaximumSize
0x1400c433f  mov     [rsp+50h+AllocationAttributes], 8000000h; AllocationAttributes
0x1400c4347  xor     r8d, r8d; ObjectAttributes
0x1400c434a  mov     r14b, 1
0x1400c434d  mov     [rsp+50h+SectionPageProtection], 4; SectionPageProtection
0x1400c4355  lea     edx, [r9+6]; DesiredAccess
0x1400c4359  call    cs:__imp_ZwCreateSection
0x1400c4360  nop     dword ptr [rax+rax+00h]
0x1400c4365  mov     ebx, eax
0x1400c4367  test    eax, eax
0x1400c4369  jns     short loc_1400C4399
0x1400c436b  mov     eax, cs:dword_1400876D0
0x1400c4371  cmp     eax, 2
0x1400c4374  jbe     loc_1400C4403
0x1400c437a  mov     edx, 80000h
0x1400c437f  lea     rcx, dword_1400876D0
0x1400c4386  call    _tlgKeywordOn
0x1400c438b  test    al, al
0x1400c438d  jz      short loc_1400C4403
0x1400c438f  mov     ecx, 0A41h
0x1400c4394  jmp     loc_1400C4303
0x1400c4399  mov     rcx, [rbp+SectionHandle]; SectionHandle
0x1400c439d  lea     rax, [rbp+ViewSize]
0x1400c43a1  mov     [rsp+50h+Win32Protect], 4; Win32Protect
0x1400c43a9  lea     r8, [rbp+BaseAddress]; BaseAddress
0x1400c43ad  mov     [rsp+50h+AllocationType], 0; AllocationType
0x1400c43b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400c43b9  mov     [rsp+50h+InheritDisposition], 2; InheritDisposition
0x1400c43c1  xor     r9d, r9d; ZeroBits
0x1400c43c4  mov     [rsp+50h+FileHandle], rax; ViewSize
0x1400c43c9  mov     rdx, rbx; ProcessHandle
0x1400c43cc  mov     qword ptr [rsp+50h+AllocationAttributes], 0; SectionOffset
0x1400c43d5  mov     qword ptr [rsp+50h+SectionPageProtection], 0; CommitSize
0x1400c43de  call    cs:__imp_ZwMapViewOfSection
0x1400c43e5  nop     dword ptr [rax+rax+00h]
0x1400c43ea  test    eax, eax
0x1400c43ec  js      short loc_1400C4401
0x1400c43ee  mov     rdx, [rbp+BaseAddress]; BaseAddress
0x1400c43f2  mov     rcx, rbx; ProcessHandle
0x1400c43f5  call    cs:__imp_ZwUnmapViewOfSection
0x1400c43fc  nop     dword ptr [rax+rax+00h]
0x1400c4401  xor     ebx, ebx
0x1400c4403  mov     rcx, [rbp+SectionHandle]; Handle
0x1400c4407  test    rcx, rcx
0x1400c440a  jz      short loc_1400C4420
0x1400c440c  call    cs:__imp_NtClose
0x1400c4413  nop     dword ptr [rax+rax+00h]
0x1400c4418  mov     [rbp+SectionHandle], 0
0x1400c4420  test    r14b, r14b
0x1400c4423  jz      short loc_1400C443F
0x1400c4425  lea     rax, VhdmpiEmptyISOBackingStore
0x1400c442c  cmp     rdi, rax
0x1400c442f  jz      short loc_1400C443F
0x1400c4431  mov     edx, 1
0x1400c4436  lea     rcx, [rdi+48h]
0x1400c443a  call    VhdmpiFileWrapperUnpinFile
0x1400c443f  mov     eax, ebx
0x1400c4441  add     rsp, 50h
0x1400c4445  pop     r14
0x1400c4447  pop     rdi
0x1400c4448  pop     rsi
0x1400c4449  pop     rbx
0x1400c444a  pop     rbp
0x1400c444b  retn
```
