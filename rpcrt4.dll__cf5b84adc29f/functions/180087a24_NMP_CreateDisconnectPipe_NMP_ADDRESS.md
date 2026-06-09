# NMP_CreateDisconnectPipe(NMP_ADDRESS *)

- ea: `0x180087a24`
- end: `0x180087bbb`
- name: `?NMP_CreateDisconnectPipe@@YAJPEAUNMP_ADDRESS@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180086690`

## callees

- `0x180087a24`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180087b5b`
- `ntdll!RtlFreeHeap` at `0x180087b5b`
- `ntdll!NtCreateNamedPipeFile` at `0x180087b33`
- `ntdll!NtCreateNamedPipeFile` at `0x180087b33`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180087a76`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180087a76`

## pseudocode

```c
__int64 __fastcall NMP_CreateDisconnectPipe(struct NMP_ADDRESS *a1)
{
  const WCHAR *v2; // rcx
  NTSTATUS v3; // ebx
  bool v4; // cf
  __int64 result; // rax
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+E0h] [rbp+67h] BYREF
  void *NamedPipeFileHandle; // [rsp+E8h] [rbp+6Fh] BYREF
  PCWSTR NtFileNamePart; // [rsp+F0h] [rbp+77h] BYREF

  NamedPipeFileHandle = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  v2 = (const WCHAR *)*((_QWORD *)a1 + 35);
  NtPathName.Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtFileNamePart = 0;
  DefaultTimeOut.QuadPart = 0;
  IoStatusBlock = 0;
  if ( RtlDosPathNameToNtPathName_U(v2, &NtPathName, &NtFileNamePart, 0) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.SecurityDescriptor = (PVOID)*((_QWORD *)a1 + 34);
    v4 = *((_DWORD *)a1 + 72) != 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.SecurityQualityOfService = 0;
    DefaultTimeOut.QuadPart = -500000;
    v3 = NtCreateNamedPipeFile(
           &NamedPipeFileHandle,
           0x100000u,
           &ObjectAttributes,
           &IoStatusBlock,
           3u,
           2u,
           0x20u,
           v4 ? 3 : 1,
           1u,
           0,
           0xFFFFFFFF,
           0x800u,
           0x800u,
           &DefaultTimeOut);
  }
  else
  {
    v3 = -1073741620;
  }
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v3 < 0 )
  {
    *((_QWORD *)a1 + 33) = 0;
    if ( v3 == -1073741790 )
    {
      return 1740;
    }
    else
    {
      result = 1706;
      if ( v3 != -1073741773 && v3 != -1073741620 )
        return 14;
    }
  }
  else
  {
    *((_QWORD *)a1 + 33) = NamedPipeFileHandle;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180087a24  push    rbp
0x180087a26  push    rbx
0x180087a27  push    rdi
0x180087a28  lea     rbp, [rsp-47h]
0x180087a2d  sub     rsp, 0C0h
0x180087a34  xorps   xmm0, xmm0
0x180087a37  mov     [rbp+57h+NamedPipeFileHandle], 0
0x180087a3f  xor     eax, eax
0x180087a41  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x180087a45  mov     rdi, rcx
0x180087a48  mov     qword ptr [rbp+57h+NtPathName.Length], rax
0x180087a4c  mov     rcx, [rcx+118h]; DosPathName
0x180087a53  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180087a57  xor     r9d, r9d; DirectoryInfo
0x180087a5a  mov     [rbp+57h+NtPathName.Buffer], rax
0x180087a5e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180087a62  mov     [rbp+57h+NtFileNamePart], rax
0x180087a66  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180087a6a  mov     qword ptr [rbp+57h+arg_0], rax
0x180087a6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180087a72  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180087a76  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180087a7d  nop     dword ptr [rax+rax+00h]
0x180087a82  test    al, al
0x180087a84  jnz     short loc_180087A90
0x180087a86  mov     ebx, 0C00000CCh
0x180087a8b  jmp     loc_180087B41
0x180087a90  lea     rax, [rbp+57h+NtPathName]
0x180087a94  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180087a9b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180087a9f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180087aa3  mov     rax, [rdi+110h]
0x180087aaa  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180087aae  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180087ab2  mov     edx, 100000h; DesiredAccess
0x180087ab7  mov     eax, [rdi+120h]
0x180087abd  neg     eax
0x180087abf  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180087ac7  lea     rax, [rbp+57h+arg_0]
0x180087acb  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180087ad2  mov     [rsp+0D0h+DefaultTimeOut], rax; DefaultTimeOut
0x180087ad7  sbb     ecx, ecx
0x180087ad9  mov     eax, 800h
0x180087ade  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x180087ae6  mov     [rsp+0D0h+OutBufferSize], eax; OutBufferSize
0x180087aea  and     ecx, 2
0x180087aed  mov     [rsp+0D0h+InBufferSize], eax; InBufferSize
0x180087af1  inc     ecx
0x180087af3  mov     [rsp+0D0h+MaxInstances], 0FFFFFFFFh; MaxInstances
0x180087afb  mov     [rsp+0D0h+NonBlocking], 0; NonBlocking
0x180087b03  mov     [rsp+0D0h+ReadModeMessage], 1; ReadModeMessage
0x180087b0b  mov     [rsp+0D0h+WriteModeMessage], ecx; WriteModeMessage
0x180087b0f  lea     rcx, [rbp+57h+NamedPipeFileHandle]; NamedPipeFileHandle
0x180087b13  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x180087b1b  mov     [rsp+0D0h+CreateDisposition], 2; CreateDisposition
0x180087b23  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x180087b2b  mov     qword ptr [rbp+57h+arg_0], 0FFFFFFFFFFF85EE0h
0x180087b33  call    cs:__imp_NtCreateNamedPipeFile
0x180087b3a  nop     dword ptr [rax+rax+00h]
0x180087b3f  mov     ebx, eax
0x180087b41  cmp     [rbp+57h+NtPathName.Buffer], 0
0x180087b46  jz      short loc_180087B67
0x180087b48  mov     rcx, gs:60h
0x180087b51  xor     edx, edx; Flags
0x180087b53  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x180087b57  mov     rcx, [rcx+30h]; HeapHandle
0x180087b5b  call    cs:__imp_RtlFreeHeap
0x180087b62  nop     dword ptr [rax+rax+00h]
0x180087b67  test    ebx, ebx
0x180087b69  js      short loc_180087B7A
0x180087b6b  mov     rax, [rbp+57h+NamedPipeFileHandle]
0x180087b6f  mov     [rdi+108h], rax
0x180087b76  xor     eax, eax
0x180087b78  jmp     short loc_180087BAF
0x180087b7a  mov     qword ptr [rdi+108h], 0
0x180087b85  cmp     ebx, 0C0000022h
0x180087b8b  jz      short loc_180087BAA
0x180087b8d  mov     eax, 6AAh
0x180087b92  cmp     ebx, 0C0000033h
0x180087b98  jz      short loc_180087BAF
0x180087b9a  cmp     ebx, 0C00000CCh
0x180087ba0  mov     ecx, 0Eh
0x180087ba5  cmovnz  eax, ecx
0x180087ba8  jmp     short loc_180087BAF
0x180087baa  mov     eax, 6CCh
0x180087baf  add     rsp, 0C0h
0x180087bb6  pop     rdi
0x180087bb7  pop     rbx
0x180087bb8  pop     rbp
0x180087bb9  retn
```
