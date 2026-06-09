# CreateDirectoryWriteThrough(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180062250`
- end: `0x180062441`
- name: `?CreateDirectoryWriteThrough@@YAHPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(PCWSTR Name, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180062140`

## callees

- `0x180062250`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1800622ee`
- `KERNEL32!GetFullPathNameW` at `0x1800622ee`
- `KERNEL32!SetLastError` at `0x180062421`
- `KERNEL32!SetLastError` at `0x180062421`
- `ntdll!RtlNtStatusToDosError` at `0x180062419`
- `ntdll!RtlNtStatusToDosError` at `0x180062419`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800622a5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800622a5`
- `ntdll!RtlFreeHeap` at `0x18006231f`
- `ntdll!RtlFreeHeap` at `0x1800623e9`
- `ntdll!RtlFreeHeap` at `0x18006231f`
- `ntdll!RtlFreeHeap` at `0x1800623e9`
- `ntdll!RtlReleaseRelativeName` at `0x180062306`
- `ntdll!RtlReleaseRelativeName` at `0x1800623d1`
- `ntdll!RtlReleaseRelativeName` at `0x180062306`
- `ntdll!RtlReleaseRelativeName` at `0x1800623d1`
- `ntdll!RtlIsDosDeviceName_U` at `0x180062407`
- `ntdll!RtlIsDosDeviceName_U` at `0x180062407`
- `ntdll!NtCreateFile` at `0x1800623c5`
- `ntdll!NtCreateFile` at `0x1800623c5`
- `ntdll!NtClose` at `0x1800623f7`
- `ntdll!NtClose` at `0x1800623f7`

## pseudocode

```c
__int64 __fastcall CreateDirectoryWriteThrough(PCWSTR Name, struct _SECURITY_ATTRIBUTES *a2)
{
  ULONG v3; // ecx
  bool v4; // zf
  DWORD FullPathNameW; // eax
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  int v8; // edi
  _UNICODE_STRING NtName; // [rsp+68h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-19h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+88h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+6Fh] BYREF
  LPWSTR FilePart; // [rsp+108h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( RtlDosPathNameToRelativeNtPathName_U(Name, &NtName, 0, &RelativeName) )
  {
    if ( NtName.Length <= 0x1F0u
      || (v4 = *Name == 92, FilePart = 0, v4) && Name[1] == 92 && Name[2] == 63 && Name[3] == 92
      || (FullPathNameW = GetFullPathNameW(Name, 0, 0, &FilePart)) != 0 && FullPathNameW + 12 <= 0x104 )
    {
      Buffer = NtName.Buffer;
      if ( RelativeName.RelativeName.Length )
      {
        NtName = RelativeName.RelativeName;
        ContainingDirectory = RelativeName.ContainingDirectory;
      }
      else
      {
        ContainingDirectory = 0;
        RelativeName.ContainingDirectory = 0;
      }
      ObjectAttributes.RootDirectory = ContainingDirectory;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = NtCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 2u, 0x204023u, 0, 0);
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      if ( v8 >= 0 )
      {
        NtClose(FileHandle);
        return 1;
      }
      if ( RtlIsDosDeviceName_U(Name) )
        v8 = -1073741565;
      v3 = RtlNtStatusToDosError(v8);
    }
    else
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
      v3 = 206;
    }
  }
  else
  {
    v3 = 3;
  }
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x180062250  mov     rax, rsp
0x180062253  mov     [rax+8], rbx
0x180062257  mov     [rax+20h], rsi
0x18006225b  mov     [rax+10h], rdx
0x18006225f  push    rbp
0x180062260  push    rdi
0x180062261  push    r14
0x180062263  lea     rbp, [rax-5Fh]
0x180062267  sub     rsp, 0D0h
0x18006226e  xorps   xmm0, xmm0
0x180062271  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x180062275  xorps   xmm1, xmm1
0x180062278  lea     rdx, [rbp+57h+NtName]; NtName
0x18006227c  xor     r14d, r14d
0x18006227f  xor     r8d, r8d; PartName
0x180062282  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180062286  mov     [rbp+57h+FileHandle], r14
0x18006228a  mov     rbx, rcx
0x18006228d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180062291  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062295  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180062299  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18006229d  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800622a1  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800622a5  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800622ab  test    al, al
0x1800622ad  jnz     short loc_1800622B8
0x1800622af  lea     ecx, [r14+3]
0x1800622b3  jmp     loc_180062421
0x1800622b8  mov     eax, 1F0h
0x1800622bd  cmp     [rbp+57h+NtName.Length], ax
0x1800622c1  jbe     short loc_18006232F
0x1800622c3  cmp     word ptr [rbx], 5Ch ; '\'
0x1800622c7  mov     [rbp+57h+FilePart], r14
0x1800622cb  jnz     short loc_1800622E2
0x1800622cd  cmp     word ptr [rbx+2], 5Ch ; '\'
0x1800622d2  jnz     short loc_1800622E2
0x1800622d4  cmp     word ptr [rbx+4], 3Fh ; '?'
0x1800622d9  jnz     short loc_1800622E2
0x1800622db  cmp     word ptr [rbx+6], 5Ch ; '\'
0x1800622e0  jz      short loc_18006232F
0x1800622e2  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x1800622e6  xor     r8d, r8d; lpBuffer
0x1800622e9  xor     edx, edx; nBufferLength
0x1800622eb  mov     rcx, rbx; lpFileName
0x1800622ee  call    cs:__imp_GetFullPathNameW
0x1800622f4  test    eax, eax
0x1800622f6  jz      short loc_180062302
0x1800622f8  add     eax, 0Ch
0x1800622fb  cmp     eax, 104h
0x180062300  jbe     short loc_18006232F
0x180062302  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180062306  call    cs:__imp_RtlReleaseRelativeName
0x18006230c  mov     rcx, gs:60h
0x180062315  xor     edx, edx; Flags
0x180062317  mov     r8, [rbp+57h+NtName.Buffer]; P
0x18006231b  mov     rcx, [rcx+30h]; HeapHandle
0x18006231f  call    cs:__imp_RtlFreeHeap
0x180062325  mov     ecx, 0CEh
0x18006232a  jmp     loc_180062421
0x18006232f  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180062333  mov     rsi, [rbp+57h+NtName.Buffer]
0x180062337  test    ax, ax
0x18006233a  jz      short loc_18006235C
0x18006233c  mov     [rbp+57h+NtName.Length], ax
0x180062340  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180062343  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x180062346  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18006234a  mov     word ptr [rbp+57h+NtName+6], ax
0x18006234e  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180062352  mov     [rbp+57h+NtName.Buffer], rax
0x180062356  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18006235a  jmp     short loc_180062363
0x18006235c  mov     rax, r14
0x18006235f  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180062363  mov     [rsp+0E0h+EaLength], r14d; EaLength
0x180062368  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006236c  mov     [rsp+0E0h+EaBuffer], r14; EaBuffer
0x180062371  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180062375  mov     [rsp+0E0h+CreateOptions], 204023h; CreateOptions
0x18006237d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180062381  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x180062389  xorps   xmm0, xmm0
0x18006238c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180062390  mov     edx, 100001h; DesiredAccess
0x180062395  mov     [rsp+0E0h+ShareAccess], 3; ShareAccess
0x18006239d  lea     rax, [rbp+57h+NtName]
0x1800623a1  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x1800623a9  mov     [rsp+0E0h+AllocationSize], r14; AllocationSize
0x1800623ae  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800623b5  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800623bc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800623c0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800623c5  call    cs:__imp_NtCreateFile
0x1800623cb  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800623cf  mov     edi, eax
0x1800623d1  call    cs:__imp_RtlReleaseRelativeName
0x1800623d7  mov     rcx, gs:60h
0x1800623e0  mov     r8, rsi; P
0x1800623e3  xor     edx, edx; Flags
0x1800623e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800623e9  call    cs:__imp_RtlFreeHeap
0x1800623ef  test    edi, edi
0x1800623f1  js      short loc_180062404
0x1800623f3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800623f7  call    cs:__imp_NtClose
0x1800623fd  mov     eax, 1
0x180062402  jmp     short loc_180062429
0x180062404  mov     rcx, rbx; Name
0x180062407  call    cs:__imp_RtlIsDosDeviceName_U
0x18006240d  mov     ecx, 0C0000103h
0x180062412  test    eax, eax
0x180062414  cmovnz  edi, ecx
0x180062417  mov     ecx, edi; Status
0x180062419  call    cs:__imp_RtlNtStatusToDosError
0x18006241f  mov     ecx, eax; dwErrCode
0x180062421  call    cs:__imp_SetLastError
0x180062427  xor     eax, eax
0x180062429  lea     r11, [rsp+0E0h+var_10]
0x180062431  mov     rbx, [r11+20h]
0x180062435  mov     rsi, [r11+38h]
0x180062439  mov     rsp, r11
0x18006243c  pop     r14
0x18006243e  pop     rdi
0x18006243f  pop     rbp
0x180062440  retn
```
