# UserHardError

- ea: `0x180001960`
- end: `0x180001bb6`
- name: `UserHardError`
- size: `598`
- prototype: `ULONG __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001960`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001b70`
- `ntdll!RtlFreeHeap` at `0x180001b70`
- `ntdll!NtClose` at `0x180001b8d`
- `ntdll!NtClose` at `0x180001b8d`
- `ntdll!NtReadVirtualMemory` at `0x180001a96`
- `ntdll!NtReadVirtualMemory` at `0x180001afd`
- `ntdll!NtReadVirtualMemory` at `0x180001a96`
- `ntdll!NtReadVirtualMemory` at `0x180001afd`
- `ntdll!NtOpenProcess` at `0x180001a10`
- `ntdll!NtOpenProcess` at `0x180001a10`
- `ntdll!DbgPrintEx` at `0x1800019bd`
- `ntdll!DbgPrintEx` at `0x180001a2f`
- `ntdll!DbgPrintEx` at `0x180001a5e`
- `ntdll!DbgPrintEx` at `0x180001b29`
- `ntdll!DbgPrintEx` at `0x180001b4d`
- `ntdll!DbgPrintEx` at `0x1800019bd`
- `ntdll!DbgPrintEx` at `0x180001a2f`
- `ntdll!DbgPrintEx` at `0x180001a5e`
- `ntdll!DbgPrintEx` at `0x180001b29`
- `ntdll!DbgPrintEx` at `0x180001b4d`
- `ntdll!RtlAllocateHeap` at `0x180001ad2`
- `ntdll!RtlAllocateHeap` at `0x180001ad2`

## string_xrefs

- `0x180001a23`: `Failed to open process: %x\n`

## pseudocode

```c
ULONG __fastcall UserHardError(__int64 a1, __int64 a2)
{
  int v2; // r9d
  NTSTATUS v4; // eax
  __int64 v6; // rdi
  wchar_t *v7; // rbx
  int v8; // eax
  unsigned __int16 v9; // cx
  unsigned __int8 v10; // cf
  unsigned int v11; // r15d
  wchar_t *Heap; // rax
  __int128 Buffer; // [rsp+30h] [rbp-29h] BYREF
  _CLIENT_ID ClientId; // [rsp+40h] [rbp-19h] BYREF
  __int128 v15; // [rsp+50h] [rbp-9h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  void *ProcessHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  v2 = *(_DWORD *)(a2 + 40);
  ProcessHandle = 0;
  Buffer = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  ClientId = 0;
  DbgPrintEx(0x65u, 0, "\n\nHardError\n\nStatus = 0x%x\n", v2);
  ClientId.UniqueProcess = *(HANDLE *)(a2 + 8);
  ClientId.UniqueThread = 0;
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenProcess(&ProcessHandle, 0x410u, &ObjectAttributes, &ClientId);
  if ( v4 < 0 )
    return DbgPrintEx(0x65u, 0, "Failed to open process: %x\n", v4);
  v6 = 0;
  if ( *(_DWORD *)(a2 + 64) )
  {
    v7 = (wchar_t *)*((_QWORD *)&v15 + 1);
    do
    {
      DbgPrintEx(0x65u, 0, "Parameter[%d] = ", v6);
      v8 = *(_DWORD *)(a2 + 68);
      v9 = 0;
      v10 = _bittest(&v8, v6);
      *((_QWORD *)&Buffer + 1) = 0;
      LOWORD(Buffer) = 0;
      if ( v10 )
      {
        if ( NtReadVirtualMemory(ProcessHandle, *(PVOID *)(a2 + 8 * v6 + 72), &Buffer, 0x10u, 0) < 0 )
          goto LABEL_11;
        v9 = Buffer;
      }
      v11 = v9;
      v15 = Buffer;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, MinSrvDllTag, v9 + 2LL);
      v7 = Heap;
      if ( !Heap || NtReadVirtualMemory(ProcessHandle, *((PVOID *)&Buffer + 1), Heap, v11, 0) < 0 )
      {
LABEL_11:
        DbgPrintEx(0x65u, 0, "%Id (0x%Ix)\n", *(_QWORD *)(a2 + 8 * v6 + 72), *(_QWORD *)(a2 + 8 * v6 + 72));
        goto LABEL_12;
      }
      v7[(unsigned __int64)(unsigned __int16)v15 >> 1] = 0;
      DbgPrintEx(0x65u, 0, "%S\n", v7);
LABEL_12:
      if ( v7 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v7 = 0;
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *(_DWORD *)(a2 + 64) );
  }
  return NtClose(ProcessHandle);
}

```

## disassembly

```asm
0x180001960  mov     [rsp-8+arg_0], rbx
0x180001965  mov     [rsp-8+arg_10], rsi
0x18000196a  push    rbp
0x18000196b  push    rdi
0x18000196c  push    r13
0x18000196e  push    r14
0x180001970  push    r15
0x180001972  lea     rbp, [rsp-37h]
0x180001977  sub     rsp, 90h
0x18000197e  mov     r9d, [rdx+28h]
0x180001982  lea     r8, Format; "\n\nHardError\n\nStatus = 0x%x\n"
0x180001989  xorps   xmm0, xmm0
0x18000198c  mov     [rbp+57h+ProcessHandle], 0
0x180001994  xor     eax, eax
0x180001996  mov     rsi, rdx
0x180001999  xorps   xmm1, xmm1
0x18000199c  xor     edx, edx; Level
0x18000199e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800019a2  lea     r13d, [rax+65h]
0x1800019a6  mov     ecx, r13d; ComponentId
0x1800019a9  movups  [rbp+57h+Buffer], xmm0
0x1800019ad  movups  [rbp+57h+var_60], xmm1
0x1800019b1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800019b5  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800019b9  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x1800019bd  call    cs:__imp_DbgPrintEx
0x1800019c4  nop     dword ptr [rax+rax+00h]
0x1800019c9  mov     rax, [rsi+8]
0x1800019cd  lea     r9, [rbp+57h+ClientId]; ClientId
0x1800019d1  xorps   xmm0, xmm0
0x1800019d4  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x1800019d8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800019dc  mov     [rbp+57h+ClientId.UniqueThread], 0
0x1800019e4  mov     edx, 410h; DesiredAccess
0x1800019e9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800019f0  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1800019f4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800019fc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001a01  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180001a08  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180001a10  call    cs:__imp_NtOpenProcess
0x180001a17  nop     dword ptr [rax+rax+00h]
0x180001a1c  test    eax, eax
0x180001a1e  jns     short loc_180001A40
0x180001a20  mov     r9d, eax
0x180001a23  lea     r8, aFailedToOpenPr; "Failed to open process: %x\n"
0x180001a2a  xor     edx, edx; Level
0x180001a2c  mov     ecx, r13d; ComponentId
0x180001a2f  call    cs:__imp_DbgPrintEx
0x180001a36  nop     dword ptr [rax+rax+00h]
0x180001a3b  jmp     loc_180001B99
0x180001a40  xor     edi, edi
0x180001a42  cmp     [rsi+40h], edi
0x180001a45  jbe     loc_180001B89
0x180001a4b  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x180001a4f  mov     r9d, edi
0x180001a52  lea     r8, aParameterD; "Parameter[%d] = "
0x180001a59  xor     edx, edx; Level
0x180001a5b  mov     ecx, r13d; ComponentId
0x180001a5e  call    cs:__imp_DbgPrintEx
0x180001a65  nop     dword ptr [rax+rax+00h]
0x180001a6a  mov     eax, [rsi+44h]
0x180001a6d  xor     ecx, ecx
0x180001a6f  bt      eax, edi
0x180001a72  mov     qword ptr [rbp+57h+Buffer+8], 0
0x180001a7a  mov     word ptr [rbp+57h+Buffer], cx
0x180001a7e  jnb     short loc_180001AAE
0x180001a80  mov     rdx, [rsi+rdi*8+48h]; BaseAddress
0x180001a85  lea     r9d, [rcx+10h]; NumberOfBytesToRead
0x180001a89  mov     [rsp+0B0h+NumberOfBytesRead], rcx; NumberOfBytesRead
0x180001a8e  lea     r8, [rbp+57h+Buffer]; Buffer
0x180001a92  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180001a96  call    cs:__imp_NtReadVirtualMemory
0x180001a9d  nop     dword ptr [rax+rax+00h]
0x180001aa2  test    eax, eax
0x180001aa4  js      loc_180001B37
0x180001aaa  movzx   ecx, word ptr [rbp+57h+Buffer]
0x180001aae  movaps  xmm0, [rbp+57h+Buffer]
0x180001ab2  movzx   r15d, cx
0x180001ab6  mov     rcx, gs:60h
0x180001abf  mov     edx, cs:MinSrvDllTag; Flags
0x180001ac5  movdqa  [rbp+57h+var_60], xmm0
0x180001aca  lea     r8, [r15+2]; Size
0x180001ace  mov     rcx, [rcx+30h]; HeapHandle
0x180001ad2  call    cs:__imp_RtlAllocateHeap
0x180001ad9  nop     dword ptr [rax+rax+00h]
0x180001ade  mov     rbx, rax
0x180001ae1  test    rax, rax
0x180001ae4  jz      short loc_180001B37
0x180001ae6  mov     rdx, qword ptr [rbp+57h+Buffer+8]; BaseAddress
0x180001aea  mov     r9d, r15d; NumberOfBytesToRead
0x180001aed  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180001af1  mov     r8, rax; Buffer
0x180001af4  mov     [rsp+0B0h+NumberOfBytesRead], 0; NumberOfBytesRead
0x180001afd  call    cs:__imp_NtReadVirtualMemory
0x180001b04  nop     dword ptr [rax+rax+00h]
0x180001b09  test    eax, eax
0x180001b0b  js      short loc_180001B37
0x180001b0d  movzx   ecx, word ptr [rbp+57h+var_60]
0x180001b11  lea     r8, aS; "%S\n"
0x180001b18  shr     rcx, 1
0x180001b1b  xor     eax, eax
0x180001b1d  mov     r9, rbx
0x180001b20  xor     edx, edx; Level
0x180001b22  mov     [rbx+rcx*2], ax
0x180001b26  mov     ecx, r13d; ComponentId
0x180001b29  call    cs:__imp_DbgPrintEx
0x180001b30  nop     dword ptr [rax+rax+00h]
0x180001b35  jmp     short loc_180001B59
0x180001b37  mov     r9, [rsi+rdi*8+48h]
0x180001b3c  lea     r8, aId0xIx; "%Id (0x%Ix)\n"
0x180001b43  xor     edx, edx; Level
0x180001b45  mov     [rsp+0B0h+NumberOfBytesRead], r9
0x180001b4a  mov     ecx, r13d; ComponentId
0x180001b4d  call    cs:__imp_DbgPrintEx
0x180001b54  nop     dword ptr [rax+rax+00h]
0x180001b59  test    rbx, rbx
0x180001b5c  jz      short loc_180001B7E
0x180001b5e  mov     rcx, gs:60h
0x180001b67  mov     r8, rbx; P
0x180001b6a  xor     edx, edx; Flags
0x180001b6c  mov     rcx, [rcx+30h]; HeapHandle
0x180001b70  call    cs:__imp_RtlFreeHeap
0x180001b77  nop     dword ptr [rax+rax+00h]
0x180001b7c  xor     ebx, ebx
0x180001b7e  inc     edi
0x180001b80  cmp     edi, [rsi+40h]
0x180001b83  jb      loc_180001A4F
0x180001b89  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x180001b8d  call    cs:__imp_NtClose
0x180001b94  nop     dword ptr [rax+rax+00h]
0x180001b99  lea     r11, [rsp+0B0h+var_20]
0x180001ba1  mov     rbx, [r11+30h]
0x180001ba5  mov     rsi, [r11+40h]
0x180001ba9  mov     rsp, r11
0x180001bac  pop     r15
0x180001bae  pop     r14
0x180001bb0  pop     r13
0x180001bb2  pop     rdi
0x180001bb3  pop     rbp
0x180001bb4  retn
```
