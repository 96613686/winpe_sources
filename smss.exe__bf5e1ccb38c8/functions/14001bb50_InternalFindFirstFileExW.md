# InternalFindFirstFileExW

- ea: `0x14001bb50`
- end: `0x14001c06b`
- name: `InternalFindFirstFileExW`
- size: `1307`
- prototype: `__int64 __fastcall(PCWSTR DosName)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ae48`

## callees

- `0x14001b9e0`
- `0x14001bb50`
- `0x14001cabc`
- `0x14001cc11`
- `0x14001cc1d`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001bbd9`
- `ntdll!RtlInitUnicodeString` at `0x14001bbd9`
- `ntdll!NtOpenFile` at `0x14001bd94`
- `ntdll!NtOpenFile` at `0x14001bddb`
- `ntdll!NtOpenFile` at `0x14001bd94`
- `ntdll!NtOpenFile` at `0x14001bddb`
- `ntdll!NtClose` at `0x14001be5a`
- `ntdll!NtClose` at `0x14001bf7c`
- `ntdll!NtClose` at `0x14001c02c`
- `ntdll!NtClose` at `0x14001be5a`
- `ntdll!NtClose` at `0x14001bf7c`
- `ntdll!NtClose` at `0x14001c02c`
- `ntdll!RtlFreeHeap` at `0x14001bc56`
- `ntdll!RtlFreeHeap` at `0x14001be03`
- `ntdll!RtlFreeHeap` at `0x14001be4f`
- `ntdll!RtlFreeHeap` at `0x14001bf6d`
- `ntdll!RtlFreeHeap` at `0x14001bc56`
- `ntdll!RtlFreeHeap` at `0x14001be03`
- `ntdll!RtlFreeHeap` at `0x14001be4f`
- `ntdll!RtlFreeHeap` at `0x14001bf6d`
- `ntdll!RtlCompareMemory` at `0x14001be83`
- `ntdll!RtlCompareMemory` at `0x14001be83`
- `ntdll!RtlSetLastWin32Error` at `0x14001c037`
- `ntdll!RtlSetLastWin32Error` at `0x14001c037`
- `ntdll!RtlReleaseRelativeName` at `0x14001bc3e`
- `ntdll!RtlReleaseRelativeName` at `0x14001bdeb`
- `ntdll!RtlReleaseRelativeName` at `0x14001be37`
- `ntdll!RtlReleaseRelativeName` at `0x14001bf55`
- `ntdll!RtlReleaseRelativeName` at `0x14001bc3e`
- `ntdll!RtlReleaseRelativeName` at `0x14001bdeb`
- `ntdll!RtlReleaseRelativeName` at `0x14001be37`
- `ntdll!RtlReleaseRelativeName` at `0x14001bf55`
- `ntdll!RtlIsDosDeviceName_U` at `0x14001bc2e`
- `ntdll!RtlIsDosDeviceName_U` at `0x14001bc2e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x14001bc11`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x14001bc11`
- `ntdll!NtQueryDirectoryFileEx` at `0x14001bf49`
- `ntdll!NtQueryDirectoryFileEx` at `0x14001bf49`

## pseudocode

```c
__int64 __fastcall InternalFindFirstFileExW(PCWSTR DosName, __int64 a2, __int64 a3)
{
  char v5; // r15
  ULONG v6; // ecx
  PWSTR Buffer; // r14
  ULONG IsDosDeviceName_U; // ebx
  char *v9; // rsi
  size_t v10; // r8
  __int64 result; // rax
  USHORT Length; // ax
  __int16 v13; // cx
  unsigned int v14; // edx
  char v15; // si
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  __int64 v18; // rcx
  unsigned int v19; // edx
  WCHAR *v20; // rcx
  int v21; // esi
  unsigned int v22; // eax
  bool v23; // cc
  unsigned __int64 v24; // rbx
  unsigned int v25; // eax
  unsigned __int64 v26; // rbx
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR PartName[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v34[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v35; // [rsp+F8h] [rbp-8h]
  __int64 v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  int v38; // [rsp+118h] [rbp+18h]
  int v39; // [rsp+11Ch] [rbp+1Ch]
  int v40; // [rsp+128h] [rbp+28h]
  unsigned int v41; // [rsp+12Ch] [rbp+2Ch]
  int v42; // [rsp+130h] [rbp+30h]
  char v43; // [rsp+134h] [rbp+34h]
  _BYTE v44[24]; // [rsp+136h] [rbp+36h] BYREF
  _BYTE Src[530]; // [rsp+14Eh] [rbp+4Eh] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)PartName = 0;
  NtName = 0;
  IoStatusBlock = 0;
  memset_0(v34, 0, 0x268u);
  memset(&RelativeName, 0, sizeof(RelativeName));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, DosName);
  if ( !DestinationString.Length
    || (v5 = 1, DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 1] != 46) )
  {
    v5 = 0;
  }
  if ( !RtlDosPathNameToRelativeNtPathName_U(DosName, &NtName, &PartName[1], &RelativeName) )
  {
    v6 = 3;
LABEL_66:
    RtlSetLastWin32Error(v6);
    return -1;
  }
  Buffer = NtName.Buffer;
  IsDosDeviceName_U = RtlIsDosDeviceName_U(DestinationString.Buffer);
  if ( IsDosDeviceName_U )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer);
    v9 = (char *)DestinationString.Buffer + ((unsigned __int64)IsDosDeviceName_U >> 16);
    memset_0((void *)(a3 + 4), 0, 0x24Cu);
    v10 = 520;
    *(_DWORD *)a3 = 32;
    if ( (unsigned __int16)IsDosDeviceName_U < 0x208u )
      v10 = (unsigned __int16)IsDosDeviceName_U;
    memmove_0((void *)(a3 + 44), v9, v10);
    result = 1;
    *(_WORD *)(a3 + 562) = 0;
    return result;
  }
  Length = NtName.Length;
  if ( PartName[1] )
    v13 = NtName.Length + LOWORD(NtName.Buffer) - LOWORD(PartName[1]);
  else
    v13 = 0;
  LOWORD(PartName[0]) = v13;
  WORD1(PartName[0]) = v13;
  if ( !RelativeName.RelativeName.Length || RelativeName.RelativeName.Buffer == PartName[1] )
  {
    RelativeName.ContainingDirectory = 0;
    if ( PartName[1] )
    {
      Length = LOWORD(PartName[1]) - LOWORD(NtName.Buffer);
      goto LABEL_19;
    }
  }
  else if ( PartName[1] )
  {
    NtName.Buffer = RelativeName.RelativeName.Buffer;
    Length = LOWORD(PartName[1]) - LOWORD(RelativeName.RelativeName.Buffer);
LABEL_19:
    NtName.MaximumLength = Length;
    NtName.Length = Length;
  }
  v14 = Length >> 1;
  if ( v14 < 2 || NtName.Buffer[v14 - 2] == 58 || (v15 = 1, NtName.Buffer[v14 - 1] != 92) )
    v15 = 0;
  ObjectAttributes.RootDirectory = RelativeName.ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v16 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  v17 = v16;
  if ( v15 && (v16 == -1073741811 || v16 == -1073741565) )
  {
    NtName.Length -= 2;
    v17 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  }
  if ( v17 < 0 )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer);
    v18 = 3221225530LL;
    if ( v17 == -1073741772 )
    {
LABEL_33:
      BaseSetLastNTError(v18);
      return -1;
    }
    if ( v17 == -1073741788 )
      v17 = -1073741766;
LABEL_32:
    v18 = (unsigned int)v17;
    goto LABEL_33;
  }
  if ( !LOWORD(PartName[0]) )
  {
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer);
    NtClose(FileHandle);
    v6 = 2;
    goto LABEL_66;
  }
  if ( LOWORD(PartName[0]) == 6 && RtlCompareMemory(PartName[1], L"*.*", 6u) == 6 )
  {
    LOWORD(PartName[0]) = 2;
    goto LABEL_55;
  }
  v19 = 0;
  v20 = (WCHAR *)PartName[1];
  if ( ((__int64)PartName[0] & 0xFFFE) != 0 )
  {
    while ( 1 )
    {
      if ( v19 && *v20 == 46 && *(v20 - 1) == 42 )
        *(v20 - 1) = 60;
      if ( *v20 == 63 )
        break;
      if ( *v20 == 42 )
        goto LABEL_48;
LABEL_51:
      ++v19;
      ++v20;
      if ( v19 >= LOWORD(PartName[0]) >> 1 )
        goto LABEL_52;
    }
    *v20 = 62;
LABEL_48:
    if ( v19 && *(v20 - 1) == 46 )
      *(v20 - 1) = 34;
    goto LABEL_51;
  }
LABEL_52:
  if ( v5 && *(v20 - 1) == 42 )
    *(v20 - 1) = 60;
LABEL_55:
  v17 = NtQueryDirectoryFileEx(FileHandle, 0, 0, 0, &IoStatusBlock, v34, 616, 3, 2, PartName);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Buffer);
  if ( v17 < 0 )
  {
    NtClose(FileHandle);
    goto LABEL_32;
  }
  v21 = v40;
  *(_QWORD *)(a3 + 4) = v35;
  *(_QWORD *)(a3 + 12) = v36;
  *(_QWORD *)(a3 + 20) = v37;
  *(_DWORD *)(a3 + 28) = v39;
  *(_DWORD *)(a3 + 32) = v38;
  v22 = v41;
  v23 = v41 <= 0x206;
  *(_DWORD *)a3 = v21;
  if ( !v23 )
    v22 = 518;
  v24 = v22;
  memcpy_0((void *)(a3 + 44), Src, v22);
  v25 = v43;
  *(_WORD *)(a3 + 2 * (v24 >> 1) + 44) = 0;
  if ( (unsigned __int8)v25 > 0x1Au || v25 >= 0x18 )
    v25 = 24;
  v26 = v25;
  memcpy_0((void *)(a3 + 564), v44, v25);
  *(_WORD *)(a3 + 2 * (v26 >> 1) + 564) = 0;
  if ( (v21 & 0x400) != 0 )
    *(_DWORD *)(a3 + 36) = v42;
  result = BasepInitializeFindFileHandle(FileHandle);
  if ( !result )
  {
    NtClose(FileHandle);
    v6 = 8;
    goto LABEL_66;
  }
  return result;
}

```

## disassembly

```asm
0x14001bb50  mov     [rsp-8+arg_8], rbx
0x14001bb55  push    rbp
0x14001bb56  push    rsi
0x14001bb57  push    rdi
0x14001bb58  push    r12
0x14001bb5a  push    r13
0x14001bb5c  push    r14
0x14001bb5e  push    r15
0x14001bb60  lea     rbp, [rsp-270h]
0x14001bb68  sub     rsp, 370h
0x14001bb6f  mov     rax, cs:__security_cookie
0x14001bb76  xor     rax, rsp
0x14001bb79  mov     [rbp+2A0h+var_40], rax
0x14001bb80  xorps   xmm0, xmm0
0x14001bb83  mov     rdi, r8
0x14001bb86  mov     rbx, rcx
0x14001bb89  xorps   xmm1, xmm1
0x14001bb8c  movups  xmmword ptr [rbp+2A0h+ObjectAttributes.ObjectName], xmm0
0x14001bb90  xor     r12d, r12d
0x14001bb93  lea     rcx, [rbp+2A0h+var_2B0]; void *
0x14001bb97  xor     eax, eax
0x14001bb99  mov     [rsp+3A0h+FileHandle], r12
0x14001bb9e  xor     edx, edx; Val
0x14001bba0  mov     r8d, 268h; Size
0x14001bba6  movups  xmmword ptr [rbp+2A0h+ObjectAttributes+1Ch], xmm0
0x14001bbaa  movups  xmmword ptr [rbp+2A0h+ObjectAttributes.Length], xmm0
0x14001bbae  movups  xmmword ptr [rsp+3A0h+PartName], xmm0
0x14001bbb3  movups  xmmword ptr [rsp+3A0h+NtName.Length], xmm1
0x14001bbb8  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x14001bbbc  call    memset_0
0x14001bbc1  xorps   xmm0, xmm0
0x14001bbc4  lea     rcx, [rsp+3A0h+DestinationString]; DestinationString
0x14001bbc9  mov     rdx, rbx; SourceString
0x14001bbcc  movups  xmmword ptr [rbp+2A0h+RelativeName.RelativeName.Length], xmm0
0x14001bbd0  movups  xmmword ptr [rbp+2A0h+RelativeName.ContainingDirectory], xmm0
0x14001bbd4  movups  xmmword ptr [rsp+3A0h+DestinationString.Length], xmm0
0x14001bbd9  call    cs:__imp_RtlInitUnicodeString
0x14001bbdf  movzx   eax, [rsp+3A0h+DestinationString.Length]
0x14001bbe4  test    ax, ax
0x14001bbe7  jz      short loc_14001BBFD
0x14001bbe9  mov     ecx, eax
0x14001bbeb  mov     r15b, 1
0x14001bbee  mov     rax, [rbp+2A0h+DestinationString.Buffer]
0x14001bbf2  shr     rcx, 1
0x14001bbf5  cmp     word ptr [rax+rcx*2-2], 2Eh ; '.'
0x14001bbfb  jz      short loc_14001BC00
0x14001bbfd  mov     r15b, r12b
0x14001bc00  lea     r9, [rbp+2A0h+RelativeName]; RelativeName
0x14001bc04  mov     rcx, rbx; DosName
0x14001bc07  lea     r8, [rsp+3A0h+PartName+8]; PartName
0x14001bc0c  lea     rdx, [rsp+3A0h+NtName]; NtName
0x14001bc11  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x14001bc17  test    al, al
0x14001bc19  jnz     short loc_14001BC25
0x14001bc1b  mov     ecx, 3
0x14001bc20  jmp     loc_14001C037
0x14001bc25  mov     rcx, [rbp+2A0h+DestinationString.Buffer]; Name
0x14001bc29  mov     r14, [rsp+3A0h+NtName.Buffer]
0x14001bc2e  call    cs:__imp_RtlIsDosDeviceName_U
0x14001bc34  mov     ebx, eax
0x14001bc36  test    eax, eax
0x14001bc38  jz      short loc_14001BCAB
0x14001bc3a  lea     rcx, [rbp+2A0h+RelativeName]; RelativeName
0x14001bc3e  call    cs:__imp_RtlReleaseRelativeName
0x14001bc44  mov     rcx, gs:60h
0x14001bc4d  mov     r8, r14; BaseAddress
0x14001bc50  xor     edx, edx; Flags
0x14001bc52  mov     rcx, [rcx+30h]; HeapHandle
0x14001bc56  call    cs:__imp_RtlFreeHeap
0x14001bc5c  mov     esi, ebx
0x14001bc5e  lea     rcx, [rdi+4]; void *
0x14001bc62  shr     rsi, 10h
0x14001bc66  xor     edx, edx; Val
0x14001bc68  add     rsi, [rbp+2A0h+DestinationString.Buffer]
0x14001bc6c  mov     r8d, 24Ch; Size
0x14001bc72  call    memset_0
0x14001bc77  mov     r8d, 208h
0x14001bc7d  mov     dword ptr [rdi], 20h ; ' '
0x14001bc83  cmp     bx, r8w
0x14001bc87  jnb     short loc_14001BC8D
0x14001bc89  movzx   r8d, bx; Size
0x14001bc8d  lea     rcx, [rdi+2Ch]; void *
0x14001bc91  mov     rdx, rsi; Src
0x14001bc94  call    memmove_0
0x14001bc99  mov     eax, 1
0x14001bc9e  mov     [rdi+232h], r12w
0x14001bca6  jmp     loc_14001C041
0x14001bcab  mov     rdx, [rsp+3A0h+PartName+8]
0x14001bcb0  movzx   r8d, word ptr [rsp+3A0h+PartName+8]
0x14001bcb6  movzx   eax, [rsp+3A0h+NtName.Length]
0x14001bcbb  test    rdx, rdx
0x14001bcbe  jz      short loc_14001BCCE
0x14001bcc0  movzx   ecx, word ptr [rsp+3A0h+NtName.Buffer]
0x14001bcc5  sub     cx, r8w
0x14001bcc9  add     cx, ax
0x14001bccc  jmp     short loc_14001BCD1
0x14001bcce  mov     ecx, r12d
0x14001bcd1  mov     word ptr [rsp+3A0h+PartName], cx
0x14001bcd6  mov     word ptr [rsp+3A0h+PartName+2], cx
0x14001bcdb  cmp     [rbp+2A0h+RelativeName.RelativeName.Length], r12w
0x14001bce0  jz      short loc_14001BCFE
0x14001bce2  mov     rcx, [rbp+2A0h+RelativeName.RelativeName.Buffer]
0x14001bce6  cmp     rcx, rdx
0x14001bce9  jz      short loc_14001BCFE
0x14001bceb  test    rdx, rdx
0x14001bcee  jz      short loc_14001BD1A
0x14001bcf0  movzx   eax, r8w
0x14001bcf4  mov     [rsp+3A0h+NtName.Buffer], rcx
0x14001bcf9  sub     ax, cx
0x14001bcfc  jmp     short loc_14001BD10
0x14001bcfe  mov     [rbp+2A0h+RelativeName.ContainingDirectory], r12
0x14001bd02  test    rdx, rdx
0x14001bd05  jz      short loc_14001BD1A
0x14001bd07  movzx   eax, r8w
0x14001bd0b  sub     ax, word ptr [rsp+3A0h+NtName.Buffer]
0x14001bd10  mov     [rsp+3A0h+NtName.MaximumLength], ax
0x14001bd15  mov     [rsp+3A0h+NtName.Length], ax
0x14001bd1a  movzx   edx, ax
0x14001bd1d  mov     r13d, 2
0x14001bd23  shr     edx, 1
0x14001bd25  cmp     edx, r13d
0x14001bd28  jb      short loc_14001BD48
0x14001bd2a  mov     r8, [rsp+3A0h+NtName.Buffer]
0x14001bd2f  lea     eax, [rdx-2]
0x14001bd32  cmp     word ptr [r8+rax*2], 3Ah ; ':'
0x14001bd38  jz      short loc_14001BD48
0x14001bd3a  lea     eax, [rdx-1]
0x14001bd3d  mov     sil, 1
0x14001bd40  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14001bd46  jz      short loc_14001BD4B
0x14001bd48  mov     sil, r12b
0x14001bd4b  mov     rax, [rbp+2A0h+RelativeName.ContainingDirectory]
0x14001bd4f  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x14001bd53  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rax
0x14001bd57  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x14001bd5b  lea     rax, [rsp+3A0h+NtName]
0x14001bd60  mov     [rsp+3A0h+OpenOptions], 4021h; OpenOptions
0x14001bd68  xorps   xmm0, xmm0
0x14001bd6b  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x14001bd6f  mov     edx, 100001h; DesiredAccess
0x14001bd74  mov     [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x14001bd7b  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14001bd80  mov     [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x14001bd87  movdqu  xmmword ptr [rbp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001bd8c  mov     [rsp+3A0h+ShareAccess], 7; ShareAccess
0x14001bd94  call    cs:__imp_NtOpenFile
0x14001bd9a  mov     ebx, eax
0x14001bd9c  test    sil, sil
0x14001bd9f  jz      short loc_14001BDE3
0x14001bda1  cmp     eax, 0C000000Dh
0x14001bda6  jz      short loc_14001BDAF
0x14001bda8  cmp     eax, 0C0000103h
0x14001bdad  jnz     short loc_14001BDE3
0x14001bdaf  mov     eax, 0FFFEh
0x14001bdb4  mov     [rsp+3A0h+OpenOptions], 4021h; OpenOptions
0x14001bdbc  add     [rsp+3A0h+NtName.Length], ax
0x14001bdc1  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x14001bdc5  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x14001bdc9  mov     [rsp+3A0h+ShareAccess], 7; ShareAccess
0x14001bdd1  mov     edx, 100001h; DesiredAccess
0x14001bdd6  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x14001bddb  call    cs:__imp_NtOpenFile
0x14001bde1  mov     ebx, eax
0x14001bde3  test    ebx, ebx
0x14001bde5  jns     short loc_14001BE2B
0x14001bde7  lea     rcx, [rbp+2A0h+RelativeName]; RelativeName
0x14001bdeb  call    cs:__imp_RtlReleaseRelativeName
0x14001bdf1  mov     rcx, gs:60h
0x14001bdfa  mov     r8, r14; BaseAddress
0x14001bdfd  xor     edx, edx; Flags
0x14001bdff  mov     rcx, [rcx+30h]; HeapHandle
0x14001be03  call    cs:__imp_RtlFreeHeap
0x14001be09  mov     ecx, 0C000003Ah
0x14001be0e  cmp     ebx, 0C0000034h
0x14001be14  jz      short loc_14001BE21
0x14001be16  cmp     ebx, 0C0000024h
0x14001be1c  cmovz   ebx, ecx
0x14001be1f  mov     ecx, ebx
0x14001be21  call    BaseSetLastNTError
0x14001be26  jmp     loc_14001C03D
0x14001be2b  cmp     word ptr [rsp+3A0h+PartName], r12w
0x14001be31  jnz     short loc_14001BE68
0x14001be33  lea     rcx, [rbp+2A0h+RelativeName]; RelativeName
0x14001be37  call    cs:__imp_RtlReleaseRelativeName
0x14001be3d  mov     rcx, gs:60h
0x14001be46  mov     r8, r14; BaseAddress
0x14001be49  xor     edx, edx; Flags
0x14001be4b  mov     rcx, [rcx+30h]; HeapHandle
0x14001be4f  call    cs:__imp_RtlFreeHeap
0x14001be55  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x14001be5a  call    cs:__imp_NtClose
0x14001be60  mov     ecx, r13d
0x14001be63  jmp     loc_14001C037
0x14001be68  mov     ebx, 6
0x14001be6d  cmp     word ptr [rsp+3A0h+PartName], bx
0x14001be72  jnz     short loc_14001BE96
0x14001be74  mov     rcx, [rsp+3A0h+PartName+8]; Source1
0x14001be79  lea     rdx, asc_140029AD0; "*.*"
0x14001be80  mov     r8d, ebx; Length
0x14001be83  call    cs:__imp_RtlCompareMemory
0x14001be89  cmp     rax, rbx
0x14001be8c  jnz     short loc_14001BE96
0x14001be8e  mov     word ptr [rsp+3A0h+PartName], r13w
0x14001be94  jmp     short loc_14001BF0B
0x14001be96  movzx   eax, word ptr [rsp+3A0h+PartName]
0x14001be9b  mov     edx, r12d
0x14001be9e  mov     rcx, [rsp+3A0h+PartName+8]
0x14001bea3  mov     r8d, 3Ch ; '<'
0x14001bea9  test    eax, 0FFFFFFFEh
0x14001beae  jbe     short loc_14001BEFA
0x14001beb0  test    edx, edx
0x14001beb2  jz      short loc_14001BEC6
0x14001beb4  cmp     word ptr [rcx], 2Eh ; '.'
0x14001beb8  jnz     short loc_14001BEC6
0x14001beba  cmp     word ptr [rcx-2], 2Ah ; '*'
0x14001bebf  jnz     short loc_14001BEC6
0x14001bec1  mov     [rcx-2], r8w
0x14001bec6  cmp     word ptr [rcx], 3Fh ; '?'
0x14001beca  jz      short loc_14001BED4
0x14001becc  cmp     word ptr [rcx], 2Ah ; '*'
0x14001bed0  jnz     short loc_14001BEEA
0x14001bed2  jmp     short loc_14001BED9
0x14001bed4  mov     word ptr [rcx], 3Eh ; '>'
0x14001bed9  test    edx, edx
0x14001bedb  jz      short loc_14001BEEA
0x14001bedd  cmp     word ptr [rcx-2], 2Eh ; '.'
0x14001bee2  jnz     short loc_14001BEEA
0x14001bee4  mov     word ptr [rcx-2], 22h ; '"'
0x14001beea  movzx   eax, word ptr [rsp+3A0h+PartName]
0x14001beef  inc     edx
0x14001bef1  shr     eax, 1
0x14001bef3  add     rcx, r13
0x14001bef6  cmp     edx, eax
0x14001bef8  jb      short loc_14001BEB0
0x14001befa  test    r15b, r15b
0x14001befd  jz      short loc_14001BF0B
0x14001beff  cmp     word ptr [rcx-2], 2Ah ; '*'
0x14001bf04  jnz     short loc_14001BF0B
0x14001bf06  mov     [rcx-2], r8w
0x14001bf0b  mov     rcx, [rsp+3A0h+FileHandle]
0x14001bf10  lea     rax, [rsp+3A0h+PartName]
0x14001bf15  mov     [rsp+3A0h+var_358], rax
0x14001bf1a  xor     r9d, r9d
0x14001bf1d  mov     [rsp+3A0h+var_360], r13d
0x14001bf22  lea     rax, [rbp+2A0h+var_2B0]
0x14001bf26  mov     [rsp+3A0h+var_368], 3
0x14001bf2e  xor     r8d, r8d
0x14001bf31  mov     [rsp+3A0h+var_370], 268h
0x14001bf39  xor     edx, edx
0x14001bf3b  mov     qword ptr [rsp+3A0h+OpenOptions], rax
0x14001bf40  lea     rax, [rbp+2A0h+IoStatusBlock]
0x14001bf44  mov     qword ptr [rsp+3A0h+ShareAccess], rax
0x14001bf49  call    cs:__imp_NtQueryDirectoryFileEx
0x14001bf4f  lea     rcx, [rbp+2A0h+RelativeName]; RelativeName
0x14001bf53  mov     ebx, eax
0x14001bf55  call    cs:__imp_RtlReleaseRelativeName
0x14001bf5b  mov     rcx, gs:60h
0x14001bf64  mov     r8, r14; BaseAddress
0x14001bf67  xor     edx, edx; Flags
0x14001bf69  mov     rcx, [rcx+30h]; HeapHandle
0x14001bf6d  call    cs:__imp_RtlFreeHeap
0x14001bf73  test    ebx, ebx
0x14001bf75  jns     short loc_14001BF87
0x14001bf77  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x14001bf7c  call    cs:__imp_NtClose
0x14001bf82  jmp     loc_14001BE1F
0x14001bf87  mov     rax, [rbp+2A0h+var_2A8]
0x14001bf8b  lea     rdx, [rbp+2A0h+Src]; Src
0x14001bf8f  mov     rsi, [rbp+2A0h+var_278]
0x14001bf93  mov     ecx, 206h
0x14001bf98  mov     [rdi+4], rax
0x14001bf9c  mov     rax, [rbp+2A0h+var_2A0]
0x14001bfa0  mov     [rdi+0Ch], rax
0x14001bfa4  mov     rax, [rbp+2A0h+var_298]
0x14001bfa8  mov     [rdi+14h], rax
0x14001bfac  mov     eax, [rbp+2A0h+var_284]
0x14001bfaf  mov     [rdi+1Ch], eax
0x14001bfb2  mov     eax, [rbp+2A0h+var_288]
0x14001bfb5  mov     [rdi+20h], eax
0x14001bfb8  mov     eax, dword ptr [rbp+2A0h+var_278+4]
0x14001bfbb  cmp     eax, ecx
0x14001bfbd  mov     [rdi], esi
0x14001bfbf  cmova   eax, ecx
0x14001bfc2  lea     rcx, [rdi+2Ch]; void *
0x14001bfc6  mov     r8d, eax; MaxCount
0x14001bfc9  mov     ebx, eax
0x14001bfcb  call    memcpy_0
0x14001bfd0  movsx   eax, [rbp+2A0h+var_26C]
0x14001bfd4  shr     rbx, 1
0x14001bfd7  mov     [rdi+rbx*2+2Ch], r12w
0x14001bfdd  cmp     al, 1Ah
0x14001bfdf  ja      short loc_14001BFE6
0x14001bfe1  cmp     eax, 18h
0x14001bfe4  jb      short loc_14001BFEB
0x14001bfe6  mov     eax, 18h
0x14001bfeb  lea     rcx, [rdi+234h]; void *
0x14001bff2  mov     r8d, eax; MaxCount
0x14001bff5  lea     rdx, [rbp+2A0h+var_26A]; Src
0x14001bff9  mov     ebx, eax
0x14001bffb  call    memcpy_0
  ... truncated ...
```
