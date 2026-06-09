# SmpCopyFile

- ea: `0x140011758`
- end: `0x140011abe`
- name: `SmpCopyFile`
- size: `870`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400127a8`

## callees

- `0x140001008`
- `0x140011758`
- `0x1400120f8`
- `0x140012930`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x1400118eb`
- `ntdll!NtClose` at `0x1400118eb`
- `ntdll!NtSetInformationFile` at `0x140011869`
- `ntdll!NtSetInformationFile` at `0x140011896`
- `ntdll!NtSetInformationFile` at `0x140011869`
- `ntdll!NtSetInformationFile` at `0x140011896`
- `ntdll!NtCreateFile` at `0x1400119b4`
- `ntdll!NtCreateFile` at `0x1400119b4`
- `ntdll!NtReadFile` at `0x140011a19`
- `ntdll!NtReadFile` at `0x140011a19`
- `ntdll!NtAllocateVirtualMemory` at `0x1400117e7`
- `ntdll!NtAllocateVirtualMemory` at `0x1400117e7`
- `ntdll!NtWriteFile` at `0x140011a8a`
- `ntdll!NtWriteFile` at `0x140011a8a`
- `ntdll!NtFreeVirtualMemory` at `0x14001190f`
- `ntdll!NtFreeVirtualMemory` at `0x14001190f`

## pseudocode

```c
__int64 __fastcall SmpCopyFile(HANDLE FileHandle, struct _UNICODE_STRING *a2, union _LARGE_INTEGER a3)
{
  ULONG v6; // r14d
  int v7; // r15d
  union _LARGE_INTEGER v8; // rdi
  NTSTATUS v9; // ebx
  int v10; // eax
  HANDLE v11; // rcx
  NTSTATUS v12; // eax
  int v13; // r8d
  int v14; // r9d
  union _LARGE_INTEGER v16; // rsi
  char v17[8]; // [rsp+60h] [rbp-A0h] BYREF
  union _LARGE_INTEGER FileInformation; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandlea; // [rsp+70h] [rbp-90h] BYREF
  PVOID BaseAddress; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+90h] [rbp-70h] BYREF
  ULONG_PTR RegionSize; // [rsp+98h] [rbp-68h] BYREF
  union _LARGE_INTEGER v24; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  char v26[32]; // [rsp+E0h] [rbp-20h] BYREF
  union _LARGE_INTEGER *p_FileInformation; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  union _LARGE_INTEGER *v29; // [rsp+110h] [rbp+10h]
  __int64 v30; // [rsp+118h] [rbp+18h]

  ByteOffset.QuadPart = 0;
  v17[0] = 0;
  FileHandlea = 0;
  BaseAddress = 0;
  v6 = 0x100000;
  FileInformation.QuadPart = 0;
  RegionSize = 0x100000;
  v7 = 1;
  v8.QuadPart = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v9 = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x3000u, 4u);
  if ( v9 >= 0 )
  {
    if ( a3.QuadPart )
    {
      v8 = a3;
    }
    else
    {
      v10 = SmpQueryFileSize(FileHandle, &FileInformation);
      v8 = FileInformation;
      v9 = v10;
      if ( v10 < 0 )
        goto LABEL_7;
    }
    if ( v8.QuadPart )
    {
      ObjectAttributes.ObjectName = a2;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      if ( v8.QuadPart % (unsigned __int64)(unsigned int)dword_140030B68 )
        v7 = dword_140030B68;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = NtCreateFile(&FileHandlea, 0xC0150000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 0, 0x68u, 0, 0);
      if ( v9 >= 0 )
      {
        v9 = SmpSetDumpSecurityAndAttributes(FileHandlea);
        if ( v9 >= 0 )
        {
          v16.QuadPart = 0;
          do
          {
            ByteOffset = v16;
            v9 = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, BaseAddress, v6, &ByteOffset, 0);
            if ( v9 < 0 )
              break;
            if ( IoStatusBlock.Information != v6 )
            {
              if ( (unsigned __int64)v6 <= v8.QuadPart - v16.QuadPart
                || IoStatusBlock.Information != v8.QuadPart - v16.QuadPart )
              {
                goto LABEL_33;
              }
              v6 = -v7 & (v7 + v8.LowPart - v16.LowPart - 1);
            }
            v9 = NtWriteFile(FileHandlea, 0, 0, 0, &IoStatusBlock, BaseAddress, v6, &ByteOffset, 0);
            if ( v9 < 0 )
              break;
            if ( IoStatusBlock.Information != v6 )
            {
LABEL_33:
              v9 = -1073741823;
              break;
            }
            v16.QuadPart += v6;
          }
          while ( v16.QuadPart < (unsigned __int64)v8.QuadPart );
        }
      }
    }
    else
    {
      v9 = -1073741672;
    }
  }
LABEL_7:
  v11 = FileHandlea;
  if ( FileHandlea )
  {
    if ( v9 < 0
      || v8.QuadPart
      && v7 != 1
      && (FileInformation = v8,
          v12 = NtSetInformationFile(FileHandlea, &IoStatusBlock, &FileInformation, 8u, FileEndOfFileInformation),
          v11 = FileHandlea,
          v9 = v12,
          v12 < 0) )
    {
      v17[0] = 1;
      NtSetInformationFile(v11, &IoStatusBlock, v17, 1u, FileDispositionInformation);
      if ( (unsigned int)dword_14002EE08 > 5 )
      {
        FileInformation.LowPart = v9;
        v28 = 4;
        p_FileInformation = &FileInformation;
        v24 = v8;
        v29 = &v24;
        v30 = 8;
        tlgWriteTransfer_EtwEventWriteTransfer(4, (unsigned int)byte_14002A2D1, v13, v14, 4, (__int64)v26);
      }
      v11 = FileHandlea;
    }
    NtClose(v11);
  }
  if ( BaseAddress )
  {
    RegionSize = 0;
    NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140011758  mov     [rsp-8+arg_18], rbx
0x14001175d  push    rbp
0x14001175e  push    rsi
0x14001175f  push    rdi
0x140011760  push    r12
0x140011762  push    r13
0x140011764  push    r14
0x140011766  push    r15
0x140011768  lea     rbp, [rsp-30h]
0x14001176d  sub     rsp, 130h
0x140011774  mov     rax, cs:__security_cookie
0x14001177b  xor     rax, rsp
0x14001177e  mov     [rbp+60h+var_40], rax
0x140011782  xor     eax, eax
0x140011784  mov     [rsp+160h+Protect], 4; Protect
0x14001178c  xorps   xmm0, xmm0
0x14001178f  mov     qword ptr [rbp+60h+ByteOffset], rax
0x140011793  mov     rsi, r8
0x140011796  mov     [rsp+160h+var_100], al
0x14001179a  mov     r13, rdx
0x14001179d  mov     [rsp+160h+FileHandle], rax
0x1400117a2  mov     r12, rcx
0x1400117a5  mov     [rsp+160h+BaseAddress], rax
0x1400117aa  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1400117ae  mov     r14d, 100000h
0x1400117b4  mov     [rsp+160h+FileInformation], rax
0x1400117b9  lea     r9, [rbp+60h+RegionSize]; RegionSize
0x1400117bd  mov     [rbp+60h+RegionSize], r14
0x1400117c1  xor     r8d, r8d; ZeroBits
0x1400117c4  mov     [rsp+160h+AllocationType], 3000h; AllocationType
0x1400117cc  lea     rdx, [rsp+160h+BaseAddress]; BaseAddress
0x1400117d1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400117d5  lea     r15d, [rax+1]
0x1400117d9  mov     edi, eax
0x1400117db  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1400117df  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x1400117e3  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1400117e7  call    cs:__imp_NtAllocateVirtualMemory
0x1400117ed  mov     ebx, eax
0x1400117ef  test    eax, eax
0x1400117f1  js      short loc_140011823
0x1400117f3  test    rsi, rsi
0x1400117f6  jz      short loc_1400117FD
0x1400117f8  mov     rdi, rsi
0x1400117fb  jmp     short loc_140011815
0x1400117fd  lea     rdx, [rsp+160h+FileInformation]
0x140011802  mov     rcx, r12
0x140011805  call    SmpQueryFileSize
0x14001180a  mov     rdi, [rsp+160h+FileInformation]
0x14001180f  mov     ebx, eax
0x140011811  test    eax, eax
0x140011813  js      short loc_140011823
0x140011815  test    rdi, rdi
0x140011818  jnz     loc_14001193E
0x14001181e  mov     ebx, 0C0000098h
0x140011823  xor     r13d, r13d
0x140011826  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x14001182b  test    rcx, rcx
0x14001182e  jz      loc_1400118F1
0x140011834  mov     esi, 8
0x140011839  test    ebx, ebx
0x14001183b  js      short loc_14001187A
0x14001183d  test    rdi, rdi
0x140011840  jz      loc_1400118EB
0x140011846  cmp     r15d, 1
0x14001184a  jz      loc_1400118EB
0x140011850  mov     r9d, esi; Length
0x140011853  mov     [rsp+160h+FileInformation], rdi
0x140011858  lea     r8, [rsp+160h+FileInformation]; FileInformation
0x14001185d  mov     [rsp+160h+AllocationType], 14h; FileInformationClass
0x140011865  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x140011869  call    cs:__imp_NtSetInformationFile
0x14001186f  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x140011874  mov     ebx, eax
0x140011876  test    eax, eax
0x140011878  jns     short loc_1400118EB
0x14001187a  mov     r9d, 1; Length
0x140011880  mov     [rsp+160h+var_100], 1
0x140011885  lea     r8, [rsp+160h+var_100]; FileInformation
0x14001188a  mov     [rsp+160h+AllocationType], 0Dh; FileInformationClass
0x140011892  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x140011896  call    cs:__imp_NtSetInformationFile
0x14001189c  mov     eax, cs:dword_14002EE08
0x1400118a2  cmp     eax, 5
0x1400118a5  jbe     short loc_1400118E6
0x1400118a7  mov     ecx, 4
0x1400118ac  mov     dword ptr [rsp+160h+FileInformation], ebx
0x1400118b0  lea     rax, [rsp+160h+FileInformation]
0x1400118b5  mov     [rbp+60h+var_58], rcx
0x1400118b9  mov     [rbp+60h+var_60], rax
0x1400118bd  lea     rdx, byte_14002A2D1
0x1400118c4  lea     rax, [rbp+60h+var_C0]
0x1400118c8  mov     [rbp+60h+var_C0], rdi
0x1400118cc  mov     [rbp+60h+var_50], rax
0x1400118d0  lea     rax, [rbp+60h+var_80]
0x1400118d4  mov     qword ptr [rsp+160h+Protect], rax
0x1400118d9  mov     [rsp+160h+AllocationType], ecx
0x1400118dd  mov     [rbp+60h+var_48], rsi
0x1400118e1  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1400118e6  mov     rcx, [rsp+160h+FileHandle]; Handle
0x1400118eb  call    cs:__imp_NtClose
0x1400118f1  cmp     [rsp+160h+BaseAddress], r13
0x1400118f6  jz      short loc_140011915
0x1400118f8  mov     r9d, 8000h; FreeType
0x1400118fe  mov     [rbp+60h+RegionSize], r13
0x140011902  lea     r8, [rbp+60h+RegionSize]; RegionSize
0x140011906  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001190a  lea     rdx, [rsp+160h+BaseAddress]; BaseAddress
0x14001190f  call    cs:__imp_NtFreeVirtualMemory
0x140011915  mov     eax, ebx
0x140011917  mov     rcx, [rbp+60h+var_40]
0x14001191b  xor     rcx, rsp; StackCookie
0x14001191e  call    __security_check_cookie
0x140011923  mov     rbx, [rsp+160h+arg_18]
0x14001192b  add     rsp, 130h
0x140011932  pop     r15
0x140011934  pop     r14
0x140011936  pop     r13
0x140011938  pop     r12
0x14001193a  pop     rdi
0x14001193b  pop     rsi
0x14001193c  pop     rbp
0x14001193d  retn
0x14001193e  mov     r8d, cs:dword_140030B68
0x140011945  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x140011949  xor     edx, edx
0x14001194b  mov     [rbp+60h+ObjectAttributes.ObjectName], r13
0x14001194f  mov     rax, rdi
0x140011952  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x140011959  div     r8
0x14001195c  xorps   xmm0, xmm0
0x14001195f  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x140011967  test    rdx, rdx
0x14001196a  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x140011971  mov     edx, 0C0150000h; DesiredAccess
0x140011976  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x14001197b  cmovnz  r15d, r8d
0x14001197f  xor     r13d, r13d
0x140011982  mov     [rsp+160h+EaLength], r13d; EaLength
0x140011987  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x14001198b  mov     [rsp+160h+EaBuffer], r13; EaBuffer
0x140011990  mov     [rsp+160h+CreateOptions], 68h ; 'h'; CreateOptions
0x140011998  mov     [rsp+160h+CreateDisposition], r13d; CreateDisposition
0x14001199d  mov     [rsp+160h+ShareAccess], r13d; ShareAccess
0x1400119a2  mov     [rsp+160h+Protect], 80h; FileAttributes
0x1400119aa  mov     qword ptr [rsp+160h+AllocationType], r13; AllocationSize
0x1400119af  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400119b4  call    cs:__imp_NtCreateFile
0x1400119ba  mov     ebx, eax
0x1400119bc  test    eax, eax
0x1400119be  js      loc_140011826
0x1400119c4  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x1400119c9  call    SmpSetDumpSecurityAndAttributes
0x1400119ce  mov     ebx, eax
0x1400119d0  test    eax, eax
0x1400119d2  js      loc_140011826
0x1400119d8  mov     esi, r13d
0x1400119db  test    rdi, rdi
0x1400119de  jz      loc_140011826
0x1400119e4  mov     qword ptr [rsp+160h+CreateOptions], r13; Key
0x1400119e9  lea     rax, [rbp+60h+ByteOffset]
0x1400119ed  mov     qword ptr [rsp+160h+CreateDisposition], rax; ByteOffset
0x1400119f2  xor     r9d, r9d; ApcContext
0x1400119f5  mov     rax, [rsp+160h+BaseAddress]
0x1400119fa  xor     r8d, r8d; ApcRoutine
0x1400119fd  mov     [rsp+160h+ShareAccess], r14d; Length
0x140011a02  xor     edx, edx; Event
0x140011a04  mov     qword ptr [rsp+160h+Protect], rax; Buffer
0x140011a09  mov     rcx, r12; FileHandle
0x140011a0c  lea     rax, [rbp+60h+IoStatusBlock]
0x140011a10  mov     qword ptr [rbp+60h+ByteOffset], rsi
0x140011a14  mov     qword ptr [rsp+160h+AllocationType], rax; IoStatusBlock
0x140011a19  call    cs:__imp_NtReadFile
0x140011a1f  mov     ebx, eax
0x140011a21  test    eax, eax
0x140011a23  js      loc_140011826
0x140011a29  mov     ecx, r14d
0x140011a2c  cmp     [rbp+60h+IoStatusBlock.Information], rcx
0x140011a30  jz      short loc_140011A57
0x140011a32  mov     rax, rdi
0x140011a35  sub     rax, rsi
0x140011a38  cmp     rcx, rax
0x140011a3b  jbe     short loc_140011AB4
0x140011a3d  cmp     [rbp+60h+IoStatusBlock.Information], rax
0x140011a41  jnz     short loc_140011AB4
0x140011a43  mov     r14d, edi
0x140011a46  mov     eax, r15d
0x140011a49  sub     r14d, esi
0x140011a4c  neg     eax
0x140011a4e  dec     r14d
0x140011a51  add     r14d, r15d
0x140011a54  and     r14d, eax
0x140011a57  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x140011a5c  lea     rax, [rbp+60h+ByteOffset]
0x140011a60  mov     qword ptr [rsp+160h+CreateOptions], r13; Key
0x140011a65  xor     r9d, r9d; ApcContext
0x140011a68  mov     qword ptr [rsp+160h+CreateDisposition], rax; ByteOffset
0x140011a6d  xor     r8d, r8d; ApcRoutine
0x140011a70  mov     rax, [rsp+160h+BaseAddress]
0x140011a75  xor     edx, edx; Event
0x140011a77  mov     [rsp+160h+ShareAccess], r14d; Length
0x140011a7c  mov     qword ptr [rsp+160h+Protect], rax; Buffer
0x140011a81  lea     rax, [rbp+60h+IoStatusBlock]
0x140011a85  mov     qword ptr [rsp+160h+AllocationType], rax; IoStatusBlock
0x140011a8a  call    cs:__imp_NtWriteFile
0x140011a90  mov     ebx, eax
0x140011a92  test    eax, eax
0x140011a94  js      loc_140011826
0x140011a9a  mov     eax, r14d
0x140011a9d  cmp     [rbp+60h+IoStatusBlock.Information], rax
0x140011aa1  jnz     short loc_140011AB4
0x140011aa3  add     rsi, rax
0x140011aa6  cmp     rsi, rdi
0x140011aa9  jb      loc_1400119E4
0x140011aaf  jmp     loc_140011826
0x140011ab4  mov     ebx, 0C0000001h
0x140011ab9  jmp     loc_140011826
```
