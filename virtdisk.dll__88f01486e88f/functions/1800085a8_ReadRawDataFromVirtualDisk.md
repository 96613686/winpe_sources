# ReadRawDataFromVirtualDisk

- ea: `0x1800085a8`
- end: `0x18000882b`
- name: `ReadRawDataFromVirtualDisk`
- size: `643`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180007f2c`

## callees

- `0x180004110`
- `0x180004f60`
- `0x180005730`
- `0x1800078f4`
- `0x180007b7c`
- `0x1800085a8`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000870e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000870e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087b4`
- `ntdll!RtlFreeHeap` at `0x1800086dc`
- `ntdll!RtlFreeHeap` at `0x1800087d2`
- `ntdll!RtlFreeHeap` at `0x1800087f5`
- `ntdll!RtlFreeHeap` at `0x1800086dc`
- `ntdll!RtlFreeHeap` at `0x1800087d2`
- `ntdll!RtlFreeHeap` at `0x1800087f5`
- `ntdll!RtlAllocateHeap` at `0x18000863c`
- `ntdll!RtlAllocateHeap` at `0x18000863c`

## pseudocode

```c
__int64 __fastcall ReadRawDataFromVirtualDisk(HANDLE hFile, __int64 a2, __int64 a3, void *a4)
{
  DWORD VirtualDiskInformationFromDriver; // edi
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rax
  void *v9; // r14
  HANDLE v10; // rbx
  unsigned int v11; // r15d
  DWORD v12; // eax
  HANDLE Handle; // [rsp+48h] [rbp-51h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-49h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+58h] [rbp-41h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+88h] [rbp-11h] BYREF
  __int128 InBuffer; // [rsp+A0h] [rbp+7h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Parameters, 0, 32);
  Parameters.Version = 6;
  InBuffer = 0;
  VirtualDiskInformationFromDriver = GetVirtualDiskInformationFromDriver(hFile, 0);
  if ( !VirtualDiskInformationFromDriver )
  {
    *(_DWORD *)&VirtualStorageType.VendorId.Data4[4] = *(_DWORD *)&Parameters.Version3.ResiliencyGuid.Data4[4];
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    *(_OWORD *)&VirtualStorageType.DeviceId = *(_OWORD *)&Parameters.Version3.ReadOnly;
    Heap = RtlAllocateHeap(ProcessHeap, 0, 0x20020u);
    v9 = Heap;
    if ( Heap )
    {
      v10 = hFile;
      *((_OWORD *)Heap + 0x2000) = 0;
      Handle = hFile;
      v11 = 0;
      *((_OWORD *)Heap + 8193) = 0;
      while ( 1 )
      {
        *((_QWORD *)&InBuffer + 1) = 0x20000;
        *(_QWORD *)&InBuffer = 0;
        v12 = IssueSynchronousDeviceIoControl(v10, 0x2D19D2u, &InBuffer, 0x10u, v9, 0x20020u, &NumberOfBytesTransferred);
        VirtualDiskInformationFromDriver = v12;
        if ( !v12 )
          break;
        if ( v12 != 234 )
          goto LABEL_17;
        VirtualDiskInformationFromDriver = GetParentVhdFileName(v10);
        if ( VirtualDiskInformationFromDriver )
          goto LABEL_17;
        if ( v10 != hFile )
        {
          CloseHandle(v10);
          v10 = 0;
          Handle = 0;
        }
        if ( v11 > 0x400 )
        {
          VirtualDiskInformationFromDriver = -1069940712;
          goto LABEL_17;
        }
        memset(&Parameters.Version3.ReadOnly, 0, 36);
        Parameters.Version = OPEN_VIRTUAL_DISK_VERSION_2;
        Parameters.Version1.RWDepth = 1;
        VirtualDiskInformationFromDriver = OpenVirtualDisk(
                                             &VirtualStorageType,
                                             0,
                                             VIRTUAL_DISK_ACCESS_NONE,
                                             OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
                                             &Parameters,
                                             &Handle);
        if ( VirtualDiskInformationFromDriver )
        {
          v10 = Handle;
          goto LABEL_17;
        }
        ++v11;
        v10 = Handle;
      }
      memcpy_0(a4, v9, 0x20000u);
      VirtualDiskInformationFromDriver = 0;
LABEL_17:
      if ( v10 && v10 != hFile )
        CloseHandle(v10);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    }
    else
    {
      return 14;
    }
  }
  return VirtualDiskInformationFromDriver;
}

```

## disassembly

```asm
0x1800085a8  mov     [rsp-8+arg_8], rbx
0x1800085ad  push    rbp
0x1800085ae  push    rsi
0x1800085af  push    rdi
0x1800085b0  push    r12
0x1800085b2  push    r13
0x1800085b4  push    r14
0x1800085b6  push    r15
0x1800085b8  lea     rbp, [rsp-27h]
0x1800085bd  sub     rsp, 0C0h
0x1800085c4  mov     rax, cs:__security_cookie
0x1800085cb  xor     rax, rsp
0x1800085ce  mov     [rbp+57h+var_40], rax
0x1800085d2  xorps   xmm0, xmm0
0x1800085d5  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x1800085dc  xor     esi, esi
0x1800085de  lea     r8, [rbp+57h+var_98]
0x1800085e2  mov     r13, r9
0x1800085e5  mov     [rbp+57h+Path], rsi
0x1800085e9  movups  xmmword ptr [rbp+57h+var_98.Version], xmm0
0x1800085ed  xor     r9d, r9d
0x1800085f0  mov     [rbp+57h+var_98.Version], 6
0x1800085f7  lea     edx, [rsi+20h]
0x1800085fa  mov     [rsp+0F0h+Parameters], rsi; __int64
0x1800085ff  mov     r12, rcx
0x180008602  movups  [rbp+57h+InBuffer], xmm0
0x180008606  movups  xmmword ptr [rbp+57h+var_98.4+0Ch], xmm0
0x18000860a  call    GetVirtualDiskInformationFromDriver
0x18000860f  mov     edi, eax
0x180008611  test    eax, eax
0x180008613  jnz     loc_180008801
0x180008619  mov     rcx, gs:60h
0x180008622  xor     edx, edx; Flags
0x180008624  movups  xmm0, xmmword ptr [rbp+57h+var_98.4+4]
0x180008628  mov     eax, dword ptr [rbp+57h+var_98.4+14h]
0x18000862b  mov     r8d, 20020h; Size
0x180008631  mov     dword ptr [rbp+57h+VirtualStorageType.VendorId.Data4+4], eax
0x180008634  mov     rcx, [rcx+30h]; HeapHandle
0x180008638  movups  xmmword ptr [rbp+57h+VirtualStorageType.DeviceId], xmm0
0x18000863c  call    cs:__imp_RtlAllocateHeap
0x180008643  nop     dword ptr [rax+rax+00h]
0x180008648  mov     r14, rax
0x18000864b  test    rax, rax
0x18000864e  jnz     short loc_180008658
0x180008650  lea     edi, [rsi+0Eh]
0x180008653  jmp     loc_180008801
0x180008658  xorps   xmm0, xmm0
0x18000865b  mov     rbx, r12
0x18000865e  movups  xmmword ptr [rax+20000h], xmm0
0x180008665  mov     [rbp+57h+var_A8], rbx
0x180008669  xor     r15d, r15d
0x18000866c  movups  xmmword ptr [rax+20010h], xmm0
0x180008673  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180008677  mov     qword ptr [rbp+57h+InBuffer+8], 20000h
0x18000867f  mov     [rsp+0F0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180008684  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180008688  mov     dword ptr [rsp+0F0h+Handle], 20020h; DWORD
0x180008690  mov     r9d, 10h; nInBufferSize
0x180008696  mov     edx, 2D19D2h; dwIoControlCode
0x18000869b  mov     [rsp+0F0h+Parameters], r14; LPVOID
0x1800086a0  mov     rcx, rbx; hFile
0x1800086a3  mov     qword ptr [rbp+57h+InBuffer], 0
0x1800086ab  call    IssueSynchronousDeviceIoControl
0x1800086b0  mov     edi, eax
0x1800086b2  test    eax, eax
0x1800086b4  jz      loc_180008794
0x1800086ba  cmp     eax, 0EAh
0x1800086bf  jnz     loc_1800087A7
0x1800086c5  test    rsi, rsi
0x1800086c8  jz      short loc_1800086F0
0x1800086ca  mov     rcx, gs:60h
0x1800086d3  mov     r8, rsi; P
0x1800086d6  xor     edx, edx; Flags
0x1800086d8  mov     rcx, [rcx+30h]; HeapHandle
0x1800086dc  call    cs:__imp_RtlFreeHeap
0x1800086e3  nop     dword ptr [rax+rax+00h]
0x1800086e8  mov     [rbp+57h+Path], 0
0x1800086f0  lea     rdx, [rbp+57h+Path]
0x1800086f4  mov     rcx, rbx; hFile
0x1800086f7  call    GetParentVhdFileName
0x1800086fc  mov     edi, eax
0x1800086fe  test    eax, eax
0x180008700  jnz     loc_18000878E
0x180008706  cmp     rbx, r12
0x180008709  jz      short loc_180008720
0x18000870b  mov     rcx, rbx; hObject
0x18000870e  call    cs:__imp_CloseHandle
0x180008715  nop     dword ptr [rax+rax+00h]
0x18000871a  xor     ebx, ebx
0x18000871c  mov     [rbp+57h+var_A8], rbx
0x180008720  mov     rsi, [rbp+57h+Path]
0x180008724  cmp     r15d, 400h
0x18000872b  ja      short loc_180008787
0x18000872d  xorps   xmm0, xmm0
0x180008730  lea     rax, [rbp+57h+var_A8]
0x180008734  mov     [rsp+0F0h+Handle], rax; Handle
0x180008739  lea     rcx, [rbp+57h+VirtualStorageType]; VirtualStorageType
0x18000873d  movups  xmmword ptr [rbp+57h+var_98.Version], xmm0
0x180008741  mov     ebx, 1
0x180008746  mov     [rbp+57h+var_98.Version], 2
0x18000874d  lea     rax, [rbp+57h+var_98]
0x180008751  mov     dword ptr [rbp+57h+var_98.4], ebx
0x180008754  movups  xmmword ptr [rbp+57h+var_98.4+0Ch], xmm0
0x180008758  mov     r9d, ebx; Flags
0x18000875b  mov     [rsp+0F0h+Parameters], rax; Parameters
0x180008760  xor     r8d, r8d; VirtualDiskAccessMask
0x180008763  mov     rdx, rsi; Path
0x180008766  movups  xmmword ptr [rbp+57h+var_98.4+18h], xmm0
0x18000876a  call    OpenVirtualDisk
0x18000876f  mov     edi, eax
0x180008771  test    eax, eax
0x180008773  jnz     short loc_180008781
0x180008775  add     r15d, ebx
0x180008778  mov     rbx, [rbp+57h+var_A8]
0x18000877c  jmp     loc_180008673
0x180008781  mov     rbx, [rbp+57h+var_A8]
0x180008785  jmp     short loc_1800087A7
0x180008787  mov     edi, 0C03A0018h
0x18000878c  jmp     short loc_1800087A7
0x18000878e  mov     rsi, [rbp+57h+Path]
0x180008792  jmp     short loc_1800087A7
0x180008794  mov     r8d, 20000h; Size
0x18000879a  mov     rdx, r14; Src
0x18000879d  mov     rcx, r13; void *
0x1800087a0  call    memcpy_0
0x1800087a5  xor     edi, edi
0x1800087a7  test    rbx, rbx
0x1800087aa  jz      short loc_1800087C0
0x1800087ac  cmp     rbx, r12
0x1800087af  jz      short loc_1800087C0
0x1800087b1  mov     rcx, rbx; hObject
0x1800087b4  call    cs:__imp_CloseHandle
0x1800087bb  nop     dword ptr [rax+rax+00h]
0x1800087c0  mov     rcx, gs:60h
0x1800087c9  mov     r8, r14; P
0x1800087cc  xor     edx, edx; Flags
0x1800087ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800087d2  call    cs:__imp_RtlFreeHeap
0x1800087d9  nop     dword ptr [rax+rax+00h]
0x1800087de  test    rsi, rsi
0x1800087e1  jz      short loc_180008801
0x1800087e3  mov     rcx, gs:60h
0x1800087ec  mov     r8, rsi; P
0x1800087ef  xor     edx, edx; Flags
0x1800087f1  mov     rcx, [rcx+30h]; HeapHandle
0x1800087f5  call    cs:__imp_RtlFreeHeap
0x1800087fc  nop     dword ptr [rax+rax+00h]
0x180008801  mov     eax, edi
0x180008803  mov     rcx, [rbp+57h+var_40]
0x180008807  xor     rcx, rsp; StackCookie
0x18000880a  call    __security_check_cookie
0x18000880f  mov     rbx, [rsp+0F0h+arg_8]
0x180008817  add     rsp, 0C0h
0x18000881e  pop     r15
0x180008820  pop     r14
0x180008822  pop     r13
0x180008824  pop     r12
0x180008826  pop     rdi
0x180008827  pop     rsi
0x180008828  pop     rbp
0x180008829  retn
```
