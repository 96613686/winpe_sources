# RdbDeviceAttachPerformanceTest(_RDB_DEVICE_ACCESS_INFO *,ulong *,double *)

- ea: `0x18009af50`
- end: `0x18009b0d0`
- name: `?RdbDeviceAttachPerformanceTest@@YAKPEAU_RDB_DEVICE_ACCESS_INFO@@PEAKPEAN@Z`
- size: `384`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int *, double *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180057284`

## callees

- `0x18009af50`
- `0x1800a93f4`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18009afe2`
- `ntdll!NtQueryVolumeInformationFile` at `0x18009afe2`
- `ntdll!RtlNtStatusToDosError` at `0x18009afee`
- `ntdll!RtlNtStatusToDosError` at `0x18009afee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009afc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009afc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b0a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b0a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009afb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009afb1`

## pseudocode

```c
__int64 __fastcall RdbDeviceAttachPerformanceTest(const WCHAR *a1, unsigned int *a2, double *a3)
{
  HANDLE FileW; // rax
  void *v5; // rdi
  ULONG Speed; // ebx
  int v7; // eax
  __int64 v9; // [rsp+40h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-61h] BYREF
  __int64 v11; // [rsp+60h] [rbp-49h]
  double v12; // [rsp+68h] [rbp-41h]
  __int64 v13; // [rsp+70h] [rbp-39h]
  double v14; // [rsp+78h] [rbp-31h]
  __int128 v15; // [rsp+80h] [rbp-29h]
  __int128 v16; // [rsp+90h] [rbp-19h]
  __int128 v17; // [rsp+A0h] [rbp-9h]
  __int128 v18; // [rsp+B0h] [rbp+7h]
  int v19; // [rsp+C0h] [rbp+17h]
  int v20; // [rsp+C4h] [rbp+1Bh]
  __int128 FsInformation; // [rsp+D0h] [rbp+27h] BYREF
  __int64 v22; // [rsp+E0h] [rbp+37h]

  *(double *)&v9 = 0.0;
  v22 = 0;
  FsInformation = 0;
  IoStatusBlock = 0;
  FileW = CreateFileW(a1 + 256, 0x80000000, 7u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    v7 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
    if ( v7 >= 0 )
    {
      v11 = DvcPerfTestDefaults;
      v13 = xmmword_1800D29E0;
      v15 = xmmword_1800D29F0;
      v17 = xmmword_1800D2A10;
      v20 = HIDWORD(qword_1800D2A30);
      v19 = HIDWORD(v22);
      v16 = xmmword_1800D2A00;
      v18 = xmmword_1800D2A20;
      v14 = DOUBLE_2_0;
      v12 = DOUBLE_5_0;
      Speed = DvcPerfGetReadSpeed(v5, (__int64)&v9);
      if ( !Speed )
        *a2 = v12 <= *(double *)&v9;
    }
    else
    {
      Speed = RtlNtStatusToDosError(v7);
    }
    CloseHandle(v5);
  }
  return Speed;
}

```

## disassembly

```asm
0x18009af50  mov     [rsp-8+arg_10], rbx
0x18009af55  push    rbp
0x18009af56  push    rsi
0x18009af57  push    rdi
0x18009af58  lea     rbp, [rsp-47h]
0x18009af5d  sub     rsp, 0F0h
0x18009af64  mov     rax, cs:__security_cookie
0x18009af6b  xor     rax, rsp
0x18009af6e  mov     [rbp+57h+var_18], rax
0x18009af72  xor     eax, eax
0x18009af74  xorps   xmm0, xmm0
0x18009af77  mov     [rsp+100h+hTemplateFile], rax; hTemplateFile
0x18009af7c  mov     rsi, rdx
0x18009af7f  xorps   xmm1, xmm1
0x18009af82  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18009af86  add     rcx, 200h; lpFileName
0x18009af8d  movsd   [rbp+57h+var_C0], xmm0
0x18009af92  lea     ebx, [rax+3]
0x18009af95  mov     [rbp+57h+var_20], rax
0x18009af99  xor     r9d, r9d; lpSecurityAttributes
0x18009af9c  mov     [rsp+100h+dwCreationDisposition], ebx; dwCreationDisposition
0x18009afa0  mov     edx, 80000000h; dwDesiredAccess
0x18009afa5  lea     r8d, [rax+7]; dwShareMode
0x18009afa9  movups  [rbp+57h+FsInformation], xmm1
0x18009afad  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18009afb1  call    cs:__imp_CreateFileW
0x18009afb7  mov     rdi, rax
0x18009afba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009afbe  jnz     short loc_18009AFCD
0x18009afc0  call    cs:__imp_GetLastError
0x18009afc6  mov     ebx, eax
0x18009afc8  jmp     loc_18009B0AF
0x18009afcd  mov     r9d, 18h; Length
0x18009afd3  mov     [rsp+100h+dwCreationDisposition], ebx; FsInformationClass
0x18009afd7  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x18009afdb  mov     rcx, rdi; FileHandle
0x18009afde  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18009afe2  call    cs:__imp_NtQueryVolumeInformationFile
0x18009afe8  test    eax, eax
0x18009afea  jns     short loc_18009AFFB
0x18009afec  mov     ecx, eax; Status
0x18009afee  call    cs:__imp_RtlNtStatusToDosError
0x18009aff4  mov     ebx, eax
0x18009aff6  jmp     loc_18009B0A6
0x18009affb  mov     eax, dword ptr [rbp+57h+var_20+4]
0x18009affe  lea     rdx, [rbp+57h+var_A0]
0x18009b002  movaps  xmm0, cs:?DvcPerfTestDefaults@@3U_DVC_PERF_TEST_PARAMS@@A; _DVC_PERF_TEST_PARAMS DvcPerfTestDefaults
0x18009b009  mov     r8d, eax
0x18009b00c  movaps  xmm1, cs:xmmword_1800D29E0
0x18009b013  xor     r9d, r9d
0x18009b016  movaps  [rbp+57h+var_A0], xmm0
0x18009b01a  mov     rcx, rdi; hFile
0x18009b01d  movaps  xmm0, cs:xmmword_1800D29F0
0x18009b024  movaps  [rbp+57h+var_90], xmm1
0x18009b028  movaps  xmm1, cs:xmmword_1800D2A00
0x18009b02f  movaps  [rbp+57h+var_80], xmm0
0x18009b033  movaps  xmm0, cs:xmmword_1800D2A10
0x18009b03a  movaps  [rbp+57h+var_60], xmm0
0x18009b03e  movsd   xmm0, cs:qword_1800D2A30
0x18009b046  movsd   qword ptr [rbp+57h+var_40], xmm0
0x18009b04b  movsd   xmm0, cs:__real@4014000000000000
0x18009b053  mov     [rbp+57h+var_40], eax
0x18009b056  mov     eax, dword ptr [rbp+57h+var_20]
0x18009b059  imul    r8, rax
0x18009b05d  movaps  [rbp+57h+var_70], xmm1
0x18009b061  movaps  xmm1, cs:xmmword_1800D2A20
0x18009b068  movaps  [rbp+57h+var_50], xmm1
0x18009b06c  movsd   xmm1, cs:__real@4000000000000000
0x18009b074  lea     rax, [rbp+57h+var_C0]
0x18009b078  movsd   qword ptr [rbp+57h+var_90+8], xmm1
0x18009b07d  imul    r8, qword ptr [rbp+57h+FsInformation]
0x18009b082  movsd   qword ptr [rbp+57h+var_A0+8], xmm0
0x18009b087  mov     qword ptr [rsp+100h+dwCreationDisposition], rax; __int64
0x18009b08c  call    DvcPerfGetReadSpeed
0x18009b091  mov     ebx, eax
0x18009b093  test    eax, eax
0x18009b095  jnz     short loc_18009B0A6
0x18009b097  movsd   xmm0, qword ptr [rbp+57h+var_A0+8]
0x18009b09c  comisd  xmm0, [rbp+57h+var_C0]
0x18009b0a1  setbe   al
0x18009b0a4  mov     [rsi], eax
0x18009b0a6  mov     rcx, rdi; hObject
0x18009b0a9  call    cs:__imp_CloseHandle
0x18009b0af  mov     eax, ebx
0x18009b0b1  mov     rcx, [rbp+57h+var_18]
0x18009b0b5  xor     rcx, rsp; StackCookie
0x18009b0b8  call    __security_check_cookie
0x18009b0bd  mov     rbx, [rsp+100h+arg_10]
0x18009b0c5  add     rsp, 0F0h
0x18009b0cc  pop     rdi
0x18009b0cd  pop     rsi
0x18009b0ce  pop     rbp
0x18009b0cf  retn
```
