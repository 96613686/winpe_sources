# RtlFileMapMapView

- ea: `0x1400115f8`
- end: `0x1400117c1`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000fa64`

## callees

- `0x1400115f8`
- `0x14002e420`

## import_xrefs

- `ntdll!ZwClose` at `0x14001178e`
- `ntdll!ZwClose` at `0x14001178e`
- `ntdll!ZwUnmapViewOfSection` at `0x1400117a1`
- `ntdll!ZwUnmapViewOfSection` at `0x1400117a1`
- `ntdll!ZwCreateSection` at `0x1400116df`
- `ntdll!ZwCreateSection` at `0x1400116df`
- `ntdll!ZwMapViewOfSection` at `0x140011731`
- `ntdll!ZwMapViewOfSection` at `0x140011731`
- `ntdll!ZwQueryInformationFile` at `0x140011672`
- `ntdll!ZwQueryInformationFile` at `0x140011672`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapView(__int64 a1, char a2)
{
  NTSTATUS v4; // ebx
  ULONG_PTR v5; // rcx
  ULONG_PTR v6; // rax
  PVOID v7; // rdx
  void *v8; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-69h]
  void *SectionHandle; // [rsp+50h] [rbp-49h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-41h] BYREF
  ULONG_PTR ViewSize; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-1h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+B8h] [rbp+1Fh]

  v17 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SectionHandle = 0;
  BaseAddress = 0;
  ViewSize = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    return (unsigned int)-1073741554;
  }
  else
  {
    v4 = ZwQueryInformationFile(*(HANDLE *)a1, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v4 < 0
      || (ObjectAttributes.Length = 48,
          memset(&ObjectAttributes.RootDirectory, 0, 20),
          FileHandle = *(HANDLE *)a1,
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
          v4 = ZwCreateSection(
                 &SectionHandle,
                 0xF0005u,
                 &ObjectAttributes,
                 0,
                 2u,
                 a2 != 0 ? 285212672 : 0x8000000,
                 FileHandle),
          v4 < 0)
      || (v4 = ZwMapViewOfSection(
                 SectionHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &BaseAddress,
                 0,
                 0,
                 0,
                 &ViewSize,
                 ViewUnmap,
                 0x500000u,
                 2u),
          v4 < 0) )
    {
      v8 = SectionHandle;
      v7 = BaseAddress;
    }
    else
    {
      v5 = *((_QWORD *)&FileInformation + 1);
      *(_QWORD *)(a1 + 8) = SectionHandle;
      *(_QWORD *)(a1 + 24) = BaseAddress;
      v6 = v5;
      if ( a2 )
        v6 = ViewSize;
      v7 = 0;
      *(_QWORD *)(a1 + 16) = v5;
      v8 = 0;
      SectionHandle = 0;
      v4 = 0;
      BaseAddress = 0;
      *(_BYTE *)(a1 + 44) = 0;
      *(_WORD *)(a1 + 41) = 257;
      *(_QWORD *)(a1 + 32) = v6;
      *(_BYTE *)(a1 + 43) = a2;
    }
    if ( v8 )
    {
      ZwClose(v8);
      v7 = BaseAddress;
    }
    if ( v7 )
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400115f8  push    rbp
0x1400115fa  push    rbx
0x1400115fb  push    rsi
0x1400115fc  push    rdi
0x1400115fd  lea     rbp, [rsp-3Fh]
0x140011602  sub     rsp, 0D8h
0x140011609  mov     rax, cs:__security_cookie
0x140011610  xor     rax, rsp
0x140011613  mov     [rbp+57h+var_30], rax
0x140011617  xor     eax, eax
0x140011619  xorps   xmm0, xmm0
0x14001161c  xorps   xmm1, xmm1
0x14001161f  mov     sil, dl
0x140011622  mov     rdi, rcx
0x140011625  mov     [rbp+57h+var_38], rax
0x140011629  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14001162d  mov     [rbp+57h+SectionHandle], rax
0x140011631  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140011635  mov     [rbp+57h+BaseAddress], rax
0x140011639  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001163d  mov     [rbp+57h+ViewSize], rax
0x140011641  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140011645  movups  [rbp+57h+FileInformation], xmm1
0x140011649  cmp     [rcx+18h], rax
0x14001164d  jz      short loc_140011659
0x14001164f  mov     ebx, 0C000010Eh
0x140011654  jmp     loc_1400117A7
0x140011659  mov     rcx, [rcx]; FileHandle
0x14001165c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140011660  mov     r9d, 18h; Length
0x140011666  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x14001166e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140011672  call    cs:__imp_ZwQueryInformationFile
0x140011678  mov     ebx, eax
0x14001167a  test    eax, eax
0x14001167c  js      loc_140011781
0x140011682  mov     al, sil
0x140011685  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001168c  neg     al
0x14001168e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140011696  mov     rax, [rdi]
0x140011699  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001169d  sbb     ecx, ecx
0x14001169f  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x1400116a4  and     ecx, 9000000h
0x1400116aa  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1400116b1  add     ecx, 8000000h
0x1400116b7  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1400116bf  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x1400116c3  xorps   xmm0, xmm0
0x1400116c6  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1400116ca  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x1400116d2  xor     r9d, r9d; MaximumSize
0x1400116d5  mov     edx, 0F0005h; DesiredAccess
0x1400116da  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400116df  call    cs:__imp_ZwCreateSection
0x1400116e5  mov     ebx, eax
0x1400116e7  test    eax, eax
0x1400116e9  js      loc_140011781
0x1400116ef  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1400116f3  lea     rax, [rbp+57h+ViewSize]
0x1400116f7  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x1400116ff  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x140011703  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x14001170b  xor     r9d, r9d; ZeroBits
0x14001170e  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x140011716  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001171a  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x14001171f  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x140011728  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x140011731  call    cs:__imp_ZwMapViewOfSection
0x140011737  mov     ebx, eax
0x140011739  test    eax, eax
0x14001173b  js      short loc_140011781
0x14001173d  mov     rax, [rbp+57h+SectionHandle]
0x140011741  test    sil, sil
0x140011744  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x140011748  mov     [rdi+8], rax
0x14001174c  mov     rax, [rbp+57h+BaseAddress]
0x140011750  mov     [rdi+18h], rax
0x140011754  mov     rax, rcx
0x140011757  cmovnz  rax, [rbp+57h+ViewSize]
0x14001175c  xor     edx, edx
0x14001175e  mov     [rdi+10h], rcx
0x140011762  xor     ecx, ecx
0x140011764  mov     [rbp+57h+SectionHandle], rcx
0x140011768  xor     ebx, ebx
0x14001176a  mov     [rbp+57h+BaseAddress], rdx
0x14001176e  mov     [rdi+2Ch], cl
0x140011771  mov     word ptr [rdi+29h], 101h
0x140011777  mov     [rdi+20h], rax
0x14001177b  mov     [rdi+2Bh], sil
0x14001177f  jmp     short loc_140011789
0x140011781  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x140011785  mov     rdx, [rbp+57h+BaseAddress]
0x140011789  test    rcx, rcx
0x14001178c  jz      short loc_140011798
0x14001178e  call    cs:__imp_ZwClose
0x140011794  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x140011798  test    rdx, rdx
0x14001179b  jz      short loc_1400117A7
0x14001179d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400117a1  call    cs:__imp_ZwUnmapViewOfSection
0x1400117a7  mov     eax, ebx
0x1400117a9  mov     rcx, [rbp+57h+var_30]
0x1400117ad  xor     rcx, rsp; StackCookie
0x1400117b0  call    __security_check_cookie
0x1400117b5  add     rsp, 0D8h
0x1400117bc  pop     rdi
0x1400117bd  pop     rsi
0x1400117be  pop     rbx
0x1400117bf  pop     rbp
0x1400117c0  retn
```
