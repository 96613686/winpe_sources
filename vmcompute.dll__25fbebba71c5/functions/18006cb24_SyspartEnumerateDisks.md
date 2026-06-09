# SyspartEnumerateDisks

- ea: `0x18006cb24`
- end: `0x18006cd8c`
- name: `SyspartEnumerateDisks`
- size: `616`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180068264`
- `0x18006bca8`

## callees

- `0x180003de4`
- `0x18006ca68`
- `0x18006cb24`
- `0x180086010`

## import_xrefs

- `ntdll!NtClose` at `0x18006cc61`
- `ntdll!NtClose` at `0x18006cc8f`
- `ntdll!NtClose` at `0x18006cc61`
- `ntdll!NtClose` at `0x18006cc8f`
- `ntdll!RtlAllocateHeap` at `0x18006cc3f`
- `ntdll!RtlAllocateHeap` at `0x18006ccca`
- `ntdll!RtlAllocateHeap` at `0x18006cc3f`
- `ntdll!RtlAllocateHeap` at `0x18006ccca`
- `ntdll!RtlFreeHeap` at `0x18006cc1e`
- `ntdll!RtlFreeHeap` at `0x18006cd54`
- `ntdll!RtlFreeHeap` at `0x18006cd7b`
- `ntdll!RtlFreeHeap` at `0x18006cc1e`
- `ntdll!RtlFreeHeap` at `0x18006cd54`
- `ntdll!RtlFreeHeap` at `0x18006cd7b`
- `ntdll!RtlInitUnicodeString` at `0x18006cb75`
- `ntdll!RtlInitUnicodeString` at `0x18006cb75`
- `ntdll!NtOpenDirectoryObject` at `0x18006cbaf`
- `ntdll!NtOpenDirectoryObject` at `0x18006cbaf`
- `ntdll!NtQueryDirectoryObject` at `0x18006cbf7`
- `ntdll!NtQueryDirectoryObject` at `0x18006cbf7`

## pseudocode

```c
__int64 __fastcall SyspartEnumerateDisks(unsigned __int8 (__fastcall *a1)(wchar_t *, _QWORD, __int64), __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG v5; // esi
  SIZE_T i; // r8
  _WORD *Heap; // rdi
  wchar_t *v9; // r14
  wchar_t **v10; // rsi
  void *FileHandle; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-11h] BYREF
  ULONG Context; // [rsp+E8h] [rbp+7Fh] BYREF

  Context = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenDirectoryObject(&FileHandle, 1u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    v5 = 4096;
    for ( i = 4096; ; i = v5 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, i);
      if ( !Heap )
      {
        v4 = -1073741801;
        goto LABEL_7;
      }
      Context = 0;
      v4 = NtQueryDirectoryObject(FileHandle, Heap, v5, 0, 1u, &Context, 0);
      if ( v4 != 261 )
        break;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v5 += 4096;
    }
    NtClose(FileHandle);
    FileHandle = 0;
    if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147483622 )
    {
      v9 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x6Au);
      if ( v9 )
      {
        v4 = 0;
        v10 = (wchar_t **)Heap;
        if ( *Heap )
        {
          do
          {
            if ( (unsigned __int8)SiIsValidDiskDevice(v10[1], v10[3]) )
            {
              swprintf_s(v9, 0x35u, L"\\Device\\Harddisk%lu\\Partition%lu", 0, 0);
              if ( a1(v9, 0, a2) )
                break;
            }
            v10 += 4;
          }
          while ( *(_WORD *)v10 );
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      }
      else
      {
        v4 = -1073741801;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
LABEL_7:
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006cb24  mov     [rsp-8+arg_0], rbx
0x18006cb29  push    rbp
0x18006cb2a  push    rsi
0x18006cb2b  push    rdi
0x18006cb2c  push    r12
0x18006cb2e  push    r13
0x18006cb30  push    r14
0x18006cb32  push    r15
0x18006cb34  lea     rbp, [rsp-27h]
0x18006cb39  sub     rsp, 90h
0x18006cb40  xorps   xmm0, xmm0
0x18006cb43  xor     r13d, r13d
0x18006cb46  mov     r15, rdx
0x18006cb49  mov     [rbp+57h+arg_18], r13d
0x18006cb4d  mov     r12, rcx
0x18006cb50  mov     [rbp+57h+arg_10], r13d
0x18006cb54  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006cb58  xor     eax, eax
0x18006cb5a  mov     [rbp+57h+FileHandle], r13
0x18006cb5e  lea     rdx, aDevice; "\\Device"
0x18006cb65  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006cb69  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006cb6d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18006cb71  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006cb75  call    cs:__imp_RtlInitUnicodeString
0x18006cb7c  nop     dword ptr [rax+rax+00h]
0x18006cb81  lea     rax, [rbp+57h+DestinationString]
0x18006cb85  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006cb8c  xorps   xmm0, xmm0
0x18006cb8f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006cb93  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006cb97  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18006cb9b  lea     edx, [r13+1]; DesiredAccess
0x18006cb9f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18006cba6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18006cbaa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006cbaf  call    cs:__imp_NtOpenDirectoryObject
0x18006cbb6  nop     dword ptr [rax+rax+00h]
0x18006cbbb  mov     ebx, eax
0x18006cbbd  test    eax, eax
0x18006cbbf  js      loc_18006CC58
0x18006cbc5  mov     r14d, 1000h
0x18006cbcb  mov     esi, r14d
0x18006cbce  mov     r8d, r14d
0x18006cbd1  jmp     short loc_18006CC30
0x18006cbd3  mov     rcx, [rbp+57h+FileHandle]; DirectoryHandle
0x18006cbd7  lea     rax, [rbp+57h+arg_18]
0x18006cbdb  mov     [rsp+0C0h+ReturnLength], r13; ReturnLength
0x18006cbe0  xor     r9d, r9d; ReturnSingleEntry
0x18006cbe3  mov     [rsp+0C0h+Context], rax; Context
0x18006cbe8  mov     r8d, esi; BufferLength
0x18006cbeb  mov     rdx, rdi; Buffer
0x18006cbee  mov     [rsp+0C0h+RestartScan], 1; RestartScan
0x18006cbf3  mov     [rbp+57h+arg_18], r13d
0x18006cbf7  call    cs:__imp_NtQueryDirectoryObject
0x18006cbfe  nop     dword ptr [rax+rax+00h]
0x18006cc03  mov     ebx, eax
0x18006cc05  cmp     eax, 105h
0x18006cc0a  jnz     short loc_18006CC8B
0x18006cc0c  mov     rcx, gs:60h
0x18006cc15  mov     r8, rdi; P
0x18006cc18  xor     edx, edx; Flags
0x18006cc1a  mov     rcx, [rcx+30h]; HeapHandle
0x18006cc1e  call    cs:__imp_RtlFreeHeap
0x18006cc25  nop     dword ptr [rax+rax+00h]
0x18006cc2a  add     esi, r14d
0x18006cc2d  mov     r8d, esi; Size
0x18006cc30  mov     rcx, gs:60h
0x18006cc39  xor     edx, edx; Flags
0x18006cc3b  mov     rcx, [rcx+30h]; HeapHandle
0x18006cc3f  call    cs:__imp_RtlAllocateHeap
0x18006cc46  nop     dword ptr [rax+rax+00h]
0x18006cc4b  mov     rdi, rax
0x18006cc4e  test    rax, rax
0x18006cc51  jnz     short loc_18006CBD3
0x18006cc53  mov     ebx, 0C0000017h
0x18006cc58  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18006cc5c  test    rcx, rcx
0x18006cc5f  jz      short loc_18006CC6D
0x18006cc61  call    cs:__imp_NtClose
0x18006cc68  nop     dword ptr [rax+rax+00h]
0x18006cc6d  mov     eax, ebx
0x18006cc6f  mov     rbx, [rsp+0C0h+arg_0]
0x18006cc77  add     rsp, 90h
0x18006cc7e  pop     r15
0x18006cc80  pop     r14
0x18006cc82  pop     r13
0x18006cc84  pop     r12
0x18006cc86  pop     rdi
0x18006cc87  pop     rsi
0x18006cc88  pop     rbp
0x18006cc89  retn
0x18006cc8b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18006cc8f  call    cs:__imp_NtClose
0x18006cc96  nop     dword ptr [rax+rax+00h]
0x18006cc9b  mov     ecx, 80000000h
0x18006cca0  mov     [rbp+57h+FileHandle], r13
0x18006cca4  lea     eax, [rbx+rcx]
0x18006cca7  test    ecx, eax
0x18006cca9  jnz     short loc_18006CCB7
0x18006ccab  cmp     ebx, 8000001Ah
0x18006ccb1  jnz     loc_18006CD60
0x18006ccb7  mov     rcx, gs:60h
0x18006ccc0  xor     edx, edx; Flags
0x18006ccc2  mov     rcx, [rcx+30h]; HeapHandle
0x18006ccc6  lea     r8d, [rdx+6Ah]; Size
0x18006ccca  call    cs:__imp_RtlAllocateHeap
0x18006ccd1  nop     dword ptr [rax+rax+00h]
0x18006ccd6  mov     r14, rax
0x18006ccd9  test    rax, rax
0x18006ccdc  jnz     short loc_18006CCE5
0x18006ccde  mov     ebx, 0C0000017h
0x18006cce3  jmp     short loc_18006CD60
0x18006cce5  mov     ebx, r13d
0x18006cce8  mov     rsi, rdi
0x18006cceb  cmp     [rdi], r13w
0x18006ccef  jz      short loc_18006CD42
0x18006ccf1  mov     rdx, [rsi+18h]; wchar_t *
0x18006ccf5  lea     r8, [rbp+57h+arg_10]
0x18006ccf9  mov     rcx, [rsi+8]; String1
0x18006ccfd  call    SiIsValidDiskDevice
0x18006cd02  test    al, al
0x18006cd04  jz      short loc_18006CD38
0x18006cd06  mov     r9d, [rbp+57h+arg_10]
0x18006cd0a  lea     r8, aDeviceHarddisk; "\\Device\\Harddisk%lu\\Partition%lu"
0x18006cd11  mov     edx, 35h ; '5'; BufferCount
0x18006cd16  mov     qword ptr [rsp+0C0h+RestartScan], r13
0x18006cd1b  mov     rcx, r14; Buffer
0x18006cd1e  call    swprintf_s
0x18006cd23  mov     edx, [rbp+57h+arg_10]
0x18006cd26  mov     r8, r15
0x18006cd29  mov     rcx, r14
0x18006cd2c  mov     rax, r12
0x18006cd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd34  test    al, al
0x18006cd36  jnz     short loc_18006CD42
0x18006cd38  add     rsi, 20h ; ' '
0x18006cd3c  cmp     [rsi], r13w
0x18006cd40  jnz     short loc_18006CCF1
0x18006cd42  mov     rcx, gs:60h
0x18006cd4b  mov     r8, r14; P
0x18006cd4e  xor     edx, edx; Flags
0x18006cd50  mov     rcx, [rcx+30h]; HeapHandle
0x18006cd54  call    cs:__imp_RtlFreeHeap
0x18006cd5b  nop     dword ptr [rax+rax+00h]
0x18006cd60  test    rdi, rdi
0x18006cd63  jz      loc_18006CC58
0x18006cd69  mov     rcx, gs:60h
0x18006cd72  mov     r8, rdi; P
0x18006cd75  xor     edx, edx; Flags
0x18006cd77  mov     rcx, [rcx+30h]; HeapHandle
0x18006cd7b  call    cs:__imp_RtlFreeHeap
0x18006cd82  nop     dword ptr [rax+rax+00h]
0x18006cd87  jmp     loc_18006CC58
```
