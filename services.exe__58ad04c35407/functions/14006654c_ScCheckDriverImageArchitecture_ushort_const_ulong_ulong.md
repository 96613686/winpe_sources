# ScCheckDriverImageArchitecture(ushort const *,ulong,ulong)

- ea: `0x14006654c`
- end: `0x14006683f`
- name: `?ScCheckDriverImageArchitecture@@YAKPEBGKK@Z`
- size: `755`
- prototype: `unsigned int __fastcall(PCWSTR Source, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140066ef4`

## callees

- `0x14006654c`
- `0x14006ae54`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x140066756`
- `ntdll!RtlImageNtHeader` at `0x140066756`
- `ntdll!NtMapViewOfSection` at `0x14006672f`
- `ntdll!NtMapViewOfSection` at `0x14006672f`
- `ntdll!NtCreateSection` at `0x1400666e0`
- `ntdll!NtCreateSection` at `0x1400666e0`
- `ntdll!NtOpenFile` at `0x1400666a9`
- `ntdll!NtOpenFile` at `0x1400666a9`
- `ntdll!RtlAppendUnicodeToString` at `0x140066634`
- `ntdll!RtlAppendUnicodeToString` at `0x140066642`
- `ntdll!RtlAppendUnicodeToString` at `0x140066634`
- `ntdll!RtlAppendUnicodeToString` at `0x140066642`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400665c7`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400665c7`
- `ntdll!NtClose` at `0x1400667f1`
- `ntdll!NtClose` at `0x140066801`
- `ntdll!NtClose` at `0x1400667f1`
- `ntdll!NtClose` at `0x140066801`
- `ntdll!RtlNtStatusToDosError` at `0x14006673b`
- `ntdll!RtlNtStatusToDosError` at `0x14006673b`
- `ntdll!RtlFreeHeap` at `0x14006681e`
- `ntdll!RtlFreeHeap` at `0x14006681e`
- `ntdll!NtUnmapViewOfSection` at `0x1400667e1`
- `ntdll!NtUnmapViewOfSection` at `0x1400667e1`
- `ntdll!RtlAllocateHeap` at `0x1400665fb`
- `ntdll!RtlAllocateHeap` at `0x1400665fb`

## pseudocode

```c
__int64 __fastcall ScCheckDriverImageArchitecture(PCWSTR Source, unsigned int a2, int a3)
{
  WCHAR *v4; // r14
  __int64 v5; // rax
  USHORT v6; // r15
  ULONG v7; // edi
  WCHAR *Heap; // rax
  int v9; // eax
  int Machine; // edi
  PIMAGE_NT_HEADERS v11; // rax
  void *SectionHandle; // [rsp+58h] [rbp-90h] BYREF
  void *FileHandle; // [rsp+60h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-80h] BYREF
  ULONG_PTR ViewSize; // [rsp+78h] [rbp-70h] BYREF
  WCHAR *v17; // [rsp+80h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-30h] BYREF
  PVOID BaseAddress; // [rsp+108h] [rbp+20h] BYREF

  v4 = 0;
  v17 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileHandle = 0;
  SectionHandle = 0;
  BaseAddress = 0;
  ViewSize = 0;
  if ( a2 >= 2 || (unsigned int)(a3 - 2) > 1 )
    goto LABEL_20;
  if ( *Source == 92 )
  {
    RtlInitUnicodeStringEx(&DestinationString, Source);
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( Source[v5] );
    v6 = 2 * v5 + 24;
    v7 = 8;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v5 + 24);
    v4 = Heap;
    v17 = Heap;
    if ( !Heap )
      goto LABEL_21;
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.MaximumLength = v6;
    DestinationString.Buffer = Heap;
    RtlAppendUnicodeToString(&DestinationString, L"\\SystemRoot\\");
    RtlAppendUnicodeToString(&DestinationString, Source);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x60u) < 0
    || NtCreateSection(&SectionHandle, 4u, 0, 0, 2u, 0x11000000u, FileHandle) < 0 )
  {
    goto LABEL_20;
  }
  ViewSize = 0;
  v9 = NtMapViewOfSection(
         SectionHandle,
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &BaseAddress,
         0,
         0,
         0,
         &ViewSize,
         ViewShare,
         0,
         2u);
  if ( v9 < 0 )
  {
    v7 = RtlNtStatusToDosError(v9);
    goto LABEL_21;
  }
  Machine = 0;
  v11 = RtlImageNtHeader(BaseAddress);
  if ( v11 )
    Machine = v11->FileHeader.Machine;
  if ( Machine == 34404 )
  {
LABEL_20:
    v7 = 0;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_DDS(
      WPP_GLOBAL_Control->StubInfo,
      96,
      (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
      Machine,
      100,
      (__int64)Source);
  v7 = 1275;
LABEL_21:
  if ( BaseAddress )
    NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  if ( SectionHandle )
    NtClose(SectionHandle);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v7;
}

```

## disassembly

```asm
0x14006654c  mov     rax, rsp
0x14006654f  mov     [rax+10h], rbx
0x140066553  mov     [rax+18h], rsi
0x140066557  mov     [rax+8], rcx
0x14006655b  push    rdi
0x14006655c  push    r14
0x14006655e  push    r15
0x140066560  sub     rsp, 0D0h
0x140066567  mov     rsi, rcx
0x14006656a  xor     ebx, ebx
0x14006656c  mov     r14d, ebx
0x14006656f  mov     [rsp+0E8h+var_68], rbx
0x140066577  xorps   xmm0, xmm0
0x14006657a  movups  xmmword ptr [rax-80h], xmm0
0x14006657e  xorps   xmm1, xmm1
0x140066581  movups  xmmword ptr [rax-60h], xmm1
0x140066585  movups  xmmword ptr [rax-50h], xmm1
0x140066589  movups  xmmword ptr [rax-40h], xmm1
0x14006658d  movups  xmmword ptr [rax-30h], xmm0
0x140066591  mov     [rsp+0E8h+FileHandle], rbx
0x140066596  mov     [rsp+0E8h+SectionHandle], rbx
0x14006659b  mov     [rax+20h], rbx
0x14006659f  mov     [rax-70h], rbx
0x1400665a3  cmp     edx, 2
0x1400665a6  jnb     loc_1400667CE
0x1400665ac  lea     eax, [r8-2]
0x1400665b0  cmp     eax, 1
0x1400665b3  ja      loc_1400667CE
0x1400665b9  cmp     word ptr [rcx], 5Ch ; '\'
0x1400665bd  jnz     short loc_1400665CF
0x1400665bf  mov     rdx, rcx; SourceString
0x1400665c2  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1400665c7  call    cs:__imp_RtlInitUnicodeStringEx
0x1400665cd  jmp     short loc_140066648
0x1400665cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400665d3  inc     rax
0x1400665d6  cmp     [rcx+rax*2], bx
0x1400665da  jnz     short loc_1400665D3
0x1400665dc  lea     r15, ds:18h[rax*2]
0x1400665e4  mov     rcx, gs:60h
0x1400665ed  mov     r8, r15; Size
0x1400665f0  mov     edi, 8
0x1400665f5  mov     edx, edi; Flags
0x1400665f7  mov     rcx, [rcx+30h]; HeapHandle
0x1400665fb  call    cs:__imp_RtlAllocateHeap
0x140066601  mov     r14, rax
0x140066604  mov     [rsp+0E8h+var_68], rax
0x14006660c  test    rax, rax
0x14006660f  jz      loc_1400667D0
0x140066615  xorps   xmm0, xmm0
0x140066618  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x14006661d  mov     [rsp+0E8h+DestinationString.MaximumLength], r15w
0x140066623  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x140066628  lea     rdx, aSystemroot_0; "\\SystemRoot\\"
0x14006662f  lea     rcx, [rsp+0E8h+DestinationString]; Destination
0x140066634  call    cs:__imp_RtlAppendUnicodeToString
0x14006663a  mov     rdx, rsi; Source
0x14006663d  lea     rcx, [rsp+0E8h+DestinationString]; Destination
0x140066642  call    cs:__imp_RtlAppendUnicodeToString
0x140066648  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x140066653  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], rbx
0x14006665b  mov     [rsp+0E8h+ObjectAttributes.Attributes], 40h ; '@'
0x140066666  lea     rax, [rsp+0E8h+DestinationString]
0x14006666b  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rax
0x140066673  xorps   xmm0, xmm0
0x140066676  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14006667f  mov     [rsp+0E8h+OpenOptions], 60h ; '`'; OpenOptions
0x140066687  mov     [rsp+0E8h+ShareAccess], 1; ShareAccess
0x14006668f  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x140066697  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x14006669f  mov     edx, 100001h; DesiredAccess
0x1400666a4  lea     rcx, [rsp+0E8h+FileHandle]; FileHandle
0x1400666a9  call    cs:__imp_NtOpenFile
0x1400666af  test    eax, eax
0x1400666b1  js      loc_1400667CE
0x1400666b7  mov     rax, [rsp+0E8h+FileHandle]
0x1400666bc  mov     [rsp+0E8h+var_B8], rax; FileHandle
0x1400666c1  mov     [rsp+0E8h+OpenOptions], 11000000h; AllocationAttributes
0x1400666c9  mov     [rsp+0E8h+ShareAccess], 2; SectionPageProtection
0x1400666d1  xor     r9d, r9d; MaximumSize
0x1400666d4  xor     r8d, r8d; ObjectAttributes
0x1400666d7  lea     edx, [r9+4]; DesiredAccess
0x1400666db  lea     rcx, [rsp+0E8h+SectionHandle]; SectionHandle
0x1400666e0  call    cs:__imp_NtCreateSection
0x1400666e6  test    eax, eax
0x1400666e8  js      loc_1400667CE
0x1400666ee  mov     [rsp+0E8h+ViewSize], rbx
0x1400666f3  mov     [rsp+0E8h+AccessProtection], 2; AccessProtection
0x1400666fb  mov     [rsp+0E8h+AllocationType], ebx; AllocationType
0x1400666ff  mov     [rsp+0E8h+InheritDisposition], 1; InheritDisposition
0x140066707  lea     rax, [rsp+0E8h+ViewSize]
0x14006670c  mov     [rsp+0E8h+var_B8], rax; ViewSize
0x140066711  mov     qword ptr [rsp+0E8h+OpenOptions], rbx; SectionOffset
0x140066716  mov     qword ptr [rsp+0E8h+ShareAccess], rbx; CommitSize
0x14006671b  xor     r9d, r9d; ZeroBits
0x14006671e  lea     r8, [rsp+0E8h+BaseAddress]; BaseAddress
0x140066726  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14006672a  mov     rcx, [rsp+0E8h+SectionHandle]; SectionHandle
0x14006672f  call    cs:__imp_NtMapViewOfSection
0x140066735  test    eax, eax
0x140066737  jns     short loc_140066748
0x140066739  mov     ecx, eax; Status
0x14006673b  call    cs:__imp_RtlNtStatusToDosError
0x140066741  mov     edi, eax
0x140066743  jmp     loc_1400667D0
0x140066748  mov     edi, ebx
0x14006674a  mov     [rsp+0E8h+var_98], ebx
0x14006674e  mov     rcx, [rsp+0E8h+BaseAddress]; BaseAddress
0x140066756  call    cs:__imp_RtlImageNtHeader
0x14006675c  test    rax, rax
0x14006675f  jz      short loc_140066781
0x140066761  movzx   edi, word ptr [rax+4]
0x140066765  mov     [rsp+0E8h+var_98], edi
0x140066769  jmp     short loc_140066781
0x14006676b  xor     ebx, ebx
0x14006676d  mov     rsi, [rsp+0E8h+arg_0]
0x140066775  mov     r14, [rsp+0E8h+var_68]
0x14006677d  mov     edi, [rsp+0E8h+var_98]
0x140066781  mov     r8d, 8664h
0x140066787  cmp     edi, r8d
0x14006678a  jz      short loc_1400667CE
0x14006678c  lea     rax, WPP_GLOBAL_Control
0x140066793  mov     rcx, cs:WPP_GLOBAL_Control
0x14006679a  cmp     rcx, rax
0x14006679d  jz      short loc_1400667C7
0x14006679f  test    byte ptr [rcx+1Ch], 1
0x1400667a3  jz      short loc_1400667C7
0x1400667a5  mov     edx, 60h ; '`'
0x1400667aa  mov     qword ptr [rsp+0E8h+OpenOptions], rsi
0x1400667af  mov     [rsp+0E8h+ShareAccess], r8d
0x1400667b4  mov     r9d, edi
0x1400667b7  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x1400667be  mov     rcx, [rcx+10h]
0x1400667c2  call    WPP_SF_DDS
0x1400667c7  mov     edi, 4FBh
0x1400667cc  jmp     short loc_1400667D0
0x1400667ce  mov     edi, ebx
0x1400667d0  mov     rdx, [rsp+0E8h+BaseAddress]; BaseAddress
0x1400667d8  test    rdx, rdx
0x1400667db  jz      short loc_1400667E7
0x1400667dd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400667e1  call    cs:__imp_NtUnmapViewOfSection
0x1400667e7  mov     rcx, [rsp+0E8h+SectionHandle]; Handle
0x1400667ec  test    rcx, rcx
0x1400667ef  jz      short loc_1400667F7
0x1400667f1  call    cs:__imp_NtClose
0x1400667f7  mov     rcx, [rsp+0E8h+FileHandle]; Handle
0x1400667fc  test    rcx, rcx
0x1400667ff  jz      short loc_140066807
0x140066801  call    cs:__imp_NtClose
0x140066807  test    r14, r14
0x14006680a  jz      short loc_140066824
0x14006680c  mov     rcx, gs:60h
0x140066815  mov     r8, r14; P
0x140066818  xor     edx, edx; Flags
0x14006681a  mov     rcx, [rcx+30h]; HeapHandle
0x14006681e  call    cs:__imp_RtlFreeHeap
0x140066824  mov     eax, edi
0x140066826  lea     r11, [rsp+0E8h+var_18]
0x14006682e  mov     rbx, [r11+28h]
0x140066832  mov     rsi, [r11+30h]
0x140066836  mov     rsp, r11
0x140066839  pop     r15
0x14006683b  pop     r14
0x14006683d  pop     rdi
0x14006683e  retn
```
