# VhdmpiVhd2MapAndUnmapDaxFile(_VHD_BACKING_STORE_HEADER *)

- ea: `0x1400c4238`
- end: `0x1400c445d`
- name: `?VhdmpiVhd2MapAndUnmapDaxFile@@YAJPEAU_VHD_BACKING_STORE_HEADER@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c5434`

## callees

- `0x140022234`
- `0x140023560`
- `0x140026510`
- `0x140035e94`
- `0x1400c4238`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x1400c4369`
- `ntoskrnl!ZwCreateSection` at `0x1400c4369`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400c43ee`
- `ntoskrnl!ZwMapViewOfSection` at `0x1400c43ee`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400c4405`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400c4405`
- `ntoskrnl!NtClose` at `0x1400c441c`
- `ntoskrnl!NtClose` at `0x1400c441c`

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
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      TraceEvents("VhdmpiVhd2MapAndUnmapDaxFile", 0xA33u, 2u, v6, "Cleanup [Status = ((NTSTATUS)0xC000000DL)]");
    goto LABEL_17;
  }
  LOBYTE(a2) = 1;
  v5 = VhdmpiPinFile(a1, a2, &FileHandle, 0);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
      goto LABEL_17;
    v8 = 2614;
    goto LABEL_9;
  }
  v2 = 1;
  v5 = ZwCreateSection(&SectionHandle, 6u, 0, 0, 4u, 0x8000000u, FileHandle);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 0x80000) )
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
0x1400c4238  push    rbp
0x1400c423a  push    rbx
0x1400c423b  push    rsi
0x1400c423c  push    rdi
0x1400c423d  push    r14
0x1400c423f  mov     rbp, rsp
0x1400c4242  sub     rsp, 50h
0x1400c4246  xor     r14b, r14b
0x1400c4249  mov     [rbp+SectionHandle], 0
0x1400c4251  test    dword ptr [rcx+0D0h], 800h
0x1400c425b  mov     rdi, rcx
0x1400c425e  mov     [rbp+arg_8], 0
0x1400c4266  mov     [rbp+BaseAddress], 0
0x1400c426e  mov     [rbp+ViewSize], 0
0x1400c4276  jnz     short loc_1400C42D2
0x1400c4278  mov     eax, cs:dword_140087708
0x1400c427e  mov     ebx, 0C000000Dh
0x1400c4283  cmp     eax, 2
0x1400c4286  jbe     loc_1400C4413
0x1400c428c  mov     edx, 80000h
0x1400c4291  lea     rcx, dword_140087708
0x1400c4298  call    _tlgKeywordOn
0x1400c429d  test    al, al
0x1400c429f  jz      loc_1400C4413
0x1400c42a5  mov     ecx, 0A33h
0x1400c42aa  lea     rax, aCleanupStatusN_7; "Cleanup [Status = ((NTSTATUS)0xC000000D"...
0x1400c42b1  mov     r9d, edx; int
0x1400c42b4  mov     qword ptr [rsp+50h+SectionPageProtection], rax; char *
0x1400c42b9  mov     edx, ecx; int
0x1400c42bb  mov     r8d, 2; int
0x1400c42c1  lea     rcx, aVhdmpivhd2mapa; "VhdmpiVhd2MapAndUnmapDaxFile"
0x1400c42c8  call    TraceEvents
0x1400c42cd  jmp     loc_1400C4413
0x1400c42d2  xor     r9d, r9d
0x1400c42d5  lea     r8, [rbp+arg_8]
0x1400c42d9  mov     dl, 1
0x1400c42db  call    VhdmpiPinFile
0x1400c42e0  mov     ebx, eax
0x1400c42e2  test    eax, eax
0x1400c42e4  jns     short loc_1400C433F
0x1400c42e6  mov     ecx, cs:dword_140087708
0x1400c42ec  cmp     ecx, 2
0x1400c42ef  jbe     loc_1400C4413
0x1400c42f5  mov     edx, 80000h
0x1400c42fa  lea     rcx, dword_140087708
0x1400c4301  call    _tlgKeywordOn
0x1400c4306  test    al, al
0x1400c4308  jz      loc_1400C4413
0x1400c430e  mov     ecx, 0A36h
0x1400c4313  mov     r9d, edx; int
0x1400c4316  mov     [rsp+50h+AllocationAttributes], ebx; char
0x1400c431a  mov     edx, ecx; int
0x1400c431c  lea     rax, aCleanupWithSta_1; "Cleanup with status 0x%08X"
0x1400c4323  lea     rcx, aVhdmpivhd2mapa; "VhdmpiVhd2MapAndUnmapDaxFile"
0x1400c432a  mov     qword ptr [rsp+50h+SectionPageProtection], rax; char *
0x1400c432f  mov     r8d, 2; int
0x1400c4335  call    TraceEvents
0x1400c433a  jmp     loc_1400C4413
0x1400c433f  mov     rax, [rbp+arg_8]
0x1400c4343  lea     rcx, [rbp+SectionHandle]; SectionHandle
0x1400c4347  mov     [rsp+50h+FileHandle], rax; FileHandle
0x1400c434c  xor     r9d, r9d; MaximumSize
0x1400c434f  mov     [rsp+50h+AllocationAttributes], 8000000h; AllocationAttributes
0x1400c4357  xor     r8d, r8d; ObjectAttributes
0x1400c435a  mov     r14b, 1
0x1400c435d  mov     [rsp+50h+SectionPageProtection], 4; SectionPageProtection
0x1400c4365  lea     edx, [r9+6]; DesiredAccess
0x1400c4369  call    cs:__imp_ZwCreateSection
0x1400c4370  nop     dword ptr [rax+rax+00h]
0x1400c4375  mov     ebx, eax
0x1400c4377  test    eax, eax
0x1400c4379  jns     short loc_1400C43A9
0x1400c437b  mov     eax, cs:dword_140087708
0x1400c4381  cmp     eax, 2
0x1400c4384  jbe     loc_1400C4413
0x1400c438a  mov     edx, 80000h
0x1400c438f  lea     rcx, dword_140087708
0x1400c4396  call    _tlgKeywordOn
0x1400c439b  test    al, al
0x1400c439d  jz      short loc_1400C4413
0x1400c439f  mov     ecx, 0A41h
0x1400c43a4  jmp     loc_1400C4313
0x1400c43a9  mov     rcx, [rbp+SectionHandle]; SectionHandle
0x1400c43ad  lea     rax, [rbp+ViewSize]
0x1400c43b1  mov     [rsp+50h+Win32Protect], 4; Win32Protect
0x1400c43b9  lea     r8, [rbp+BaseAddress]; BaseAddress
0x1400c43bd  mov     [rsp+50h+AllocationType], 0; AllocationType
0x1400c43c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400c43c9  mov     [rsp+50h+InheritDisposition], 2; InheritDisposition
0x1400c43d1  xor     r9d, r9d; ZeroBits
0x1400c43d4  mov     [rsp+50h+FileHandle], rax; ViewSize
0x1400c43d9  mov     rdx, rbx; ProcessHandle
0x1400c43dc  mov     qword ptr [rsp+50h+AllocationAttributes], 0; SectionOffset
0x1400c43e5  mov     qword ptr [rsp+50h+SectionPageProtection], 0; CommitSize
0x1400c43ee  call    cs:__imp_ZwMapViewOfSection
0x1400c43f5  nop     dword ptr [rax+rax+00h]
0x1400c43fa  test    eax, eax
0x1400c43fc  js      short loc_1400C4411
0x1400c43fe  mov     rdx, [rbp+BaseAddress]; BaseAddress
0x1400c4402  mov     rcx, rbx; ProcessHandle
0x1400c4405  call    cs:__imp_ZwUnmapViewOfSection
0x1400c440c  nop     dword ptr [rax+rax+00h]
0x1400c4411  xor     ebx, ebx
0x1400c4413  mov     rcx, [rbp+SectionHandle]; Handle
0x1400c4417  test    rcx, rcx
0x1400c441a  jz      short loc_1400C4430
0x1400c441c  call    cs:__imp_NtClose
0x1400c4423  nop     dword ptr [rax+rax+00h]
0x1400c4428  mov     [rbp+SectionHandle], 0
0x1400c4430  test    r14b, r14b
0x1400c4433  jz      short loc_1400C444F
0x1400c4435  lea     rax, VhdmpiEmptyISOBackingStore
0x1400c443c  cmp     rdi, rax
0x1400c443f  jz      short loc_1400C444F
0x1400c4441  mov     edx, 1
0x1400c4446  lea     rcx, [rdi+48h]
0x1400c444a  call    VhdmpiFileWrapperUnpinFile
0x1400c444f  mov     eax, ebx
0x1400c4451  add     rsp, 50h
0x1400c4455  pop     r14
0x1400c4457  pop     rdi
0x1400c4458  pop     rsi
0x1400c4459  pop     rbx
0x1400c445a  pop     rbp
0x1400c445b  retn
```
