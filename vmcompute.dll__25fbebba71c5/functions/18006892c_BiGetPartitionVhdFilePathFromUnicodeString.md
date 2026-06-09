# BiGetPartitionVhdFilePathFromUnicodeString

- ea: `0x18006892c`
- end: `0x180068c24`
- name: `BiGetPartitionVhdFilePathFromUnicodeString`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800688f4`

## callees

- `0x180004829`
- `0x18006892c`
- `0x1800694d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180068a86`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180068a86`
- `ntdll!ZwClose` at `0x180068c00`
- `ntdll!ZwClose` at `0x180068c00`
- `ntdll!ZwDeviceIoControlFile` at `0x180068a1e`
- `ntdll!ZwDeviceIoControlFile` at `0x180068a1e`
- `ntdll!ZwOpenFile` at `0x180068998`
- `ntdll!ZwOpenFile` at `0x180068998`
- `ntdll!RtlAllocateHeap` at `0x1800689cb`
- `ntdll!RtlAllocateHeap` at `0x180068b0b`
- `ntdll!RtlAllocateHeap` at `0x1800689cb`
- `ntdll!RtlAllocateHeap` at `0x180068b0b`
- `ntdll!RtlFreeHeap` at `0x180068a4e`
- `ntdll!RtlFreeHeap` at `0x180068b59`
- `ntdll!RtlFreeHeap` at `0x180068ba3`
- `ntdll!RtlFreeHeap` at `0x180068bc5`
- `ntdll!RtlFreeHeap` at `0x180068be8`
- `ntdll!RtlFreeHeap` at `0x180068a4e`
- `ntdll!RtlFreeHeap` at `0x180068b59`
- `ntdll!RtlFreeHeap` at `0x180068ba3`
- `ntdll!RtlFreeHeap` at `0x180068bc5`
- `ntdll!RtlFreeHeap` at `0x180068be8`

## pseudocode

```c
ULONG *__fastcall BiGetPartitionVhdFilePathFromUnicodeString(struct _UNICODE_STRING *a1)
{
  char v1; // r12
  ULONG *v2; // rdi
  ULONG OutputBufferLength; // ebx
  int i; // esi
  ULONG *OutputBuffer; // rax
  NTSTATUS v6; // eax
  _WORD *v7; // r14
  wchar_t *v8; // r15
  wchar_t *v9; // r13
  wchar_t *j; // rbx
  wchar_t *v11; // rsi
  NTSTATUS v12; // eax
  __int64 v13; // rax
  size_t v14; // rbx
  __int64 v15; // rax
  wchar_t *Heap; // rax
  _WORD *v17; // rbx
  signed int v18; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  int InputBuffer; // [rsp+E0h] [rbp+67h] BYREF
  size_t Size; // [rsp+E8h] [rbp+6Fh]
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  void *Src; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  ObjectAttributes.ObjectName = a1;
  InputBuffer = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  v2 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenFile(&FileHandle, 0xC0100000, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u) >= 0 )
  {
    OutputBufferLength = 520;
    for ( i = 1; ; i = 2 )
    {
      OutputBuffer = (ULONG *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBufferLength);
      v2 = OutputBuffer;
      if ( !OutputBuffer )
        break;
      InputBuffer = 1;
      v6 = ZwDeviceIoControlFile(
             FileHandle,
             0,
             0,
             0,
             &IoStatusBlock,
             0x2D5928u,
             &InputBuffer,
             4u,
             OutputBuffer,
             OutputBufferLength);
      if ( v6 != -1073741789 )
      {
        if ( v6 < 0 )
        {
LABEL_28:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = 0;
          break;
        }
        v7 = 0;
        Src = 0;
        v8 = 0;
        v9 = (wchar_t *)v2;
        for ( j = 0; ; j = v11 )
        {
          v11 = wcsrchr(v9, 0x5Cu);
          if ( j )
            *j = 92;
          if ( !v11 )
            break;
          *v11 = 0;
          v12 = BiTranslateSymbolicLink(v9, (PWSTR *)&Src);
          v7 = Src;
          if ( v12 >= 0 )
          {
            *v11 = 92;
            v13 = -1;
            do
              ++v13;
            while ( v7[v13] );
            v14 = (unsigned int)(2 * v13);
            v15 = -1;
            do
              ++v15;
            while ( v11[v15] );
            LODWORD(Size) = 2 * v15 + 2;
            Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v14 + Size));
            v8 = Heap;
            if ( !Heap )
            {
              v18 = -1073741801;
              goto LABEL_24;
            }
            v1 = 1;
            memcpy_0(Heap, v7, v14);
            v17 = (wchar_t *)((char *)v8 + v14);
            memcpy_0(v17, v11, (unsigned int)Size);
            if ( v9 != (wchar_t *)v2 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            v9 = v8;
            *v17 = 0;
            v11 = v17;
          }
        }
        v18 = v1 == 0 ? 0xC0000001 : 0;
LABEL_24:
        if ( v7 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        if ( v18 >= 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          v2 = (ULONG *)v8;
        }
        break;
      }
      if ( i != 1 )
        goto LABEL_28;
      OutputBufferLength = *v2;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return v2;
}

```

## disassembly

```asm
0x18006892c  push    rbp
0x18006892e  push    rbx
0x18006892f  push    rsi
0x180068930  push    rdi
0x180068931  push    r12
0x180068933  push    r13
0x180068935  push    r14
0x180068937  push    r15
0x180068939  lea     rbp, [rsp-1Fh]
0x18006893e  sub     rsp, 98h
0x180068945  xor     r12d, r12d
0x180068948  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x18006894c  xorps   xmm0, xmm0
0x18006894f  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x180068957  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18006895b  mov     [rbp+57h+arg_0], r12d
0x18006895f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180068963  mov     [rbp+57h+FileHandle], r12
0x180068967  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006896b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18006896f  mov     edx, 0C0100000h; DesiredAccess
0x180068974  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006897c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180068980  mov     edi, r12d
0x180068983  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006898b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180068990  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x180068998  call    cs:__imp_ZwOpenFile
0x18006899f  nop     dword ptr [rax+rax+00h]
0x1800689a4  test    eax, eax
0x1800689a6  js      loc_180068BF7
0x1800689ac  lea     r14d, [r12+1]
0x1800689b1  mov     ebx, 208h
0x1800689b6  mov     esi, r14d
0x1800689b9  mov     rcx, gs:60h
0x1800689c2  xor     edx, edx; Flags
0x1800689c4  mov     r8d, ebx; Size
0x1800689c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800689cb  call    cs:__imp_RtlAllocateHeap
0x1800689d2  nop     dword ptr [rax+rax+00h]
0x1800689d7  mov     rdi, rax
0x1800689da  test    rax, rax
0x1800689dd  jz      loc_180068BF7
0x1800689e3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800689e7  xor     r9d, r9d; ApcContext
0x1800689ea  mov     [rsp+0D0h+OutputBufferLength], ebx; OutputBufferLength
0x1800689ee  xor     r8d, r8d; ApcRoutine
0x1800689f1  mov     [rsp+0D0h+OutputBuffer], rax; OutputBuffer
0x1800689f6  xor     edx, edx; Event
0x1800689f8  mov     [rsp+0D0h+InputBufferLength], 4; InputBufferLength
0x180068a00  lea     rax, [rbp+57h+arg_0]
0x180068a04  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x180068a09  lea     rax, [rbp+57h+IoStatusBlock]
0x180068a0d  mov     [rsp+0D0h+OpenOptions], 2D5928h; IoControlCode
0x180068a15  mov     qword ptr [rsp+0D0h+ShareAccess], rax; IoStatusBlock
0x180068a1a  mov     [rbp+57h+arg_0], r14d
0x180068a1e  call    cs:__imp_ZwDeviceIoControlFile
0x180068a25  nop     dword ptr [rax+rax+00h]
0x180068a2a  cmp     eax, 0C0000023h
0x180068a2f  jnz     short loc_180068A64
0x180068a31  cmp     esi, r14d
0x180068a34  jnz     loc_180068BD6
0x180068a3a  mov     rcx, gs:60h
0x180068a43  mov     r8, rdi; P
0x180068a46  mov     ebx, [rdi]
0x180068a48  xor     edx, edx; Flags
0x180068a4a  mov     rcx, [rcx+30h]; HeapHandle
0x180068a4e  call    cs:__imp_RtlFreeHeap
0x180068a55  nop     dword ptr [rax+rax+00h]
0x180068a5a  mov     esi, 2
0x180068a5f  jmp     loc_1800689B9
0x180068a64  test    eax, eax
0x180068a66  js      loc_180068BD6
0x180068a6c  mov     r14, r12
0x180068a6f  mov     [rbp+57h+Src], r12
0x180068a73  mov     r15, r12
0x180068a76  mov     r13, rdi
0x180068a79  mov     rbx, r12
0x180068a7c  mov     eax, 5Ch ; '\'
0x180068a81  mov     rcx, r13; Str
0x180068a84  mov     edx, eax; Ch
0x180068a86  call    cs:__imp_wcsrchr
0x180068a8d  nop     dword ptr [rax+rax+00h]
0x180068a92  mov     rsi, rax
0x180068a95  xor     eax, eax
0x180068a97  test    rbx, rbx
0x180068a9a  jz      short loc_180068AA1
0x180068a9c  mov     word ptr [rbx], 5Ch ; '\'
0x180068aa1  test    rsi, rsi
0x180068aa4  jz      loc_180068B7F
0x180068aaa  lea     rdx, [rbp+57h+Src]
0x180068aae  mov     [rsi], ax
0x180068ab1  mov     rcx, r13; SourceString
0x180068ab4  call    BiTranslateSymbolicLink
0x180068ab9  mov     r14, [rbp+57h+Src]
0x180068abd  test    eax, eax
0x180068abf  js      loc_180068B70
0x180068ac5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180068ac9  mov     word ptr [rsi], 5Ch ; '\'
0x180068ace  mov     rax, rcx
0x180068ad1  xor     r12d, r12d
0x180068ad4  inc     rax
0x180068ad7  cmp     [r14+rax*2], r12w
0x180068adc  jnz     short loc_180068AD4
0x180068ade  lea     ebx, [rax+rax]
0x180068ae1  mov     rax, rcx
0x180068ae4  inc     rax
0x180068ae7  cmp     [rsi+rax*2], r12w
0x180068aec  jnz     short loc_180068AE4
0x180068aee  mov     rcx, gs:60h
0x180068af7  lea     eax, ds:2[rax*2]
0x180068afe  lea     r8d, [rbx+rax]; Size
0x180068b02  mov     dword ptr [rbp+57h+Size], eax
0x180068b05  xor     edx, edx; Flags
0x180068b07  mov     rcx, [rcx+30h]; HeapHandle
0x180068b0b  call    cs:__imp_RtlAllocateHeap
0x180068b12  nop     dword ptr [rax+rax+00h]
0x180068b17  mov     r15, rax
0x180068b1a  test    rax, rax
0x180068b1d  jz      short loc_180068B78
0x180068b1f  mov     r8, rbx; Size
0x180068b22  mov     rdx, r14; Src
0x180068b25  mov     rcx, rax; void *
0x180068b28  mov     r12b, 1
0x180068b2b  call    memcpy_0
0x180068b30  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180068b34  add     rbx, r15
0x180068b37  mov     rcx, rbx; void *
0x180068b3a  mov     rdx, rsi; Src
0x180068b3d  call    memcpy_0
0x180068b42  cmp     r13, rdi
0x180068b45  jz      short loc_180068B65
0x180068b47  mov     rcx, gs:60h
0x180068b50  mov     r8, r13; P
0x180068b53  xor     edx, edx; Flags
0x180068b55  mov     rcx, [rcx+30h]; HeapHandle
0x180068b59  call    cs:__imp_RtlFreeHeap
0x180068b60  nop     dword ptr [rax+rax+00h]
0x180068b65  xor     eax, eax
0x180068b67  mov     r13, r15
0x180068b6a  mov     [rbx], ax
0x180068b6d  mov     rsi, rbx
0x180068b70  mov     rbx, rsi
0x180068b73  jmp     loc_180068A7C
0x180068b78  mov     ebx, 0C0000017h
0x180068b7d  jmp     short loc_180068B8C
0x180068b7f  neg     r12b
0x180068b82  sbb     ebx, ebx
0x180068b84  not     ebx
0x180068b86  and     ebx, 0C0000001h
0x180068b8c  test    r14, r14
0x180068b8f  jz      short loc_180068BAF
0x180068b91  mov     rcx, gs:60h
0x180068b9a  mov     r8, r14; P
0x180068b9d  xor     edx, edx; Flags
0x180068b9f  mov     rcx, [rcx+30h]; HeapHandle
0x180068ba3  call    cs:__imp_RtlFreeHeap
0x180068baa  nop     dword ptr [rax+rax+00h]
0x180068baf  test    ebx, ebx
0x180068bb1  js      short loc_180068BF7
0x180068bb3  mov     rcx, gs:60h
0x180068bbc  mov     r8, rdi; P
0x180068bbf  xor     edx, edx; Flags
0x180068bc1  mov     rcx, [rcx+30h]; HeapHandle
0x180068bc5  call    cs:__imp_RtlFreeHeap
0x180068bcc  nop     dword ptr [rax+rax+00h]
0x180068bd1  mov     rdi, r15
0x180068bd4  jmp     short loc_180068BF7
0x180068bd6  mov     rcx, gs:60h
0x180068bdf  mov     r8, rdi; P
0x180068be2  xor     edx, edx; Flags
0x180068be4  mov     rcx, [rcx+30h]; HeapHandle
0x180068be8  call    cs:__imp_RtlFreeHeap
0x180068bef  nop     dword ptr [rax+rax+00h]
0x180068bf4  mov     rdi, r12
0x180068bf7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180068bfb  test    rcx, rcx
0x180068bfe  jz      short loc_180068C0C
0x180068c00  call    cs:__imp_ZwClose
0x180068c07  nop     dword ptr [rax+rax+00h]
0x180068c0c  mov     rax, rdi
0x180068c0f  add     rsp, 98h
0x180068c16  pop     r15
0x180068c18  pop     r14
0x180068c1a  pop     r13
0x180068c1c  pop     r12
0x180068c1e  pop     rdi
0x180068c1f  pop     rsi
0x180068c20  pop     rbx
0x180068c21  pop     rbp
0x180068c22  retn
```
