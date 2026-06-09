# SiScopeRegeneration(ushort *)

- ea: `0x14000ac90`
- end: `0x14000afb2`
- name: `?SiScopeRegeneration@@YAHPEAG@Z`
- size: `802`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x14000b434`

## callees

- `0x14000ac90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ad9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ae8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ad85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000adad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000ad85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000adad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ae9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000aea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ae9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000aea8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000ae83`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000af68`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000ae83`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14000af68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000ad62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000ad62`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14000aceb`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x14000aceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aeb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aeb1`
- `ntdll!RtlInitializeBitMap` at `0x14000aef8`
- `ntdll!RtlInitializeBitMap` at `0x14000aef8`
- `ntdll!RtlFindNextForwardRunClear` at `0x14000af89`
- `ntdll!RtlFindNextForwardRunClear` at `0x14000af89`

## pseudocode

```c
__int64 __fastcall SiScopeRegeneration(LPCWSTR lpFileName)
{
  unsigned int DiskFreeSpaceW; // edi
  __int64 v3; // rsi
  __int64 v4; // r15
  LPCWSTR v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  HANDLE FileW; // r13
  HLOCAL v9; // r14
  _OWORD *v10; // rax
  _DWORD *v11; // rbx
  int v12; // eax
  __int64 v13; // r8
  int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // r12
  __int64 v20; // rsi
  ULONG v21; // edx
  unsigned __int64 v22; // rcx
  ULONG NextForwardRunClear; // r15d
  DWORD BytesReturned; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+44h] [rbp-3Ch]
  __int64 InBuffer; // [rsp+48h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-30h]
  _RTL_BITMAP BitMapHeader; // [rsp+58h] [rbp-28h] BYREF
  __int16 v29; // [rsp+69h] [rbp-17h]
  char v30; // [rsp+6Bh] [rbp-15h]
  ULONG StartingRunIndex; // [rsp+C8h] [rbp+48h] BYREF
  DWORD SectorsPerCluster; // [rsp+D0h] [rbp+50h] BYREF
  DWORD BytesPerSector; // [rsp+D8h] [rbp+58h] BYREF

  InBuffer = 0;
  BytesReturned = 0;
  BitMapHeader = 0;
  BytesPerSector = 0;
  v29 = 0;
  v30 = 0;
  StartingRunIndex = 0;
  SectorsPerCluster = 0;
  DiskFreeSpaceW = GetDiskFreeSpaceW(lpFileName, &SectorsPerCluster, &BytesPerSector, 0, 0);
  if ( !DiskFreeSpaceW )
    return DiskFreeSpaceW;
  v3 = SectorsPerCluster;
  v4 = BytesPerSector;
  if ( !lpFileName )
    goto LABEL_7;
  v5 = lpFileName;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = (260 - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
LABEL_7:
    v7 = 0;
  lpFileName[v7 - 1] = 0;
  FileW = CreateFileW(lpFileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  v9 = LocalAlloc(0x40u, 0x800010u);
  if ( !v9 )
  {
    DiskFreeSpaceW = 0;
    SetLastError(0x5AAu);
    goto LABEL_30;
  }
  v10 = LocalAlloc(0x40u, 0x30u);
  v11 = v10;
  if ( !v10 )
  {
    DiskFreeSpaceW = 0;
    SetLastError(0x5AAu);
    goto LABEL_29;
  }
  v25 = 0;
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v12 = 28;
  v11[1] = -2147483630;
  *v11 = 28;
  v27 = v3 * v4;
  v13 = (unsigned int)v11[6];
  if ( (_DWORD)v13 )
  {
    v15 = v11[5];
    v16 = v15 + (unsigned int)v13;
  }
  else
  {
    v14 = v11[4];
    if ( v14 )
      v12 = v14 + v11[3];
    v15 = v11[5];
    v16 = (v12 + 7) & 0xFFFFFFF8;
  }
  if ( (unsigned int)(48 - v16) >= 0x10 )
  {
    if ( v15 )
      v16 = v15;
    else
      v11[5] = v16;
    v17 = (char *)v11 + (v13 & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)&v17[v16] = 0;
    *(_QWORD *)&v17[v16 + 8] = 0;
    v11[6] += 16;
  }
  v18 = (unsigned int)v11[5];
  while ( DeviceIoControl(FileW, 0x9006Fu, &InBuffer, 8u, v9, 0x800010u, &BytesReturned, 0) )
  {
    v25 = 1;
LABEL_33:
    v20 = *((_QWORD *)v9 + 1);
    if ( v20 > 0x4000000 )
      LODWORD(v20) = 0x4000000;
    RtlInitializeBitMap(&BitMapHeader, (PULONG)v9 + 4, v20);
    v21 = 0;
    for ( StartingRunIndex = 0; ; StartingRunIndex += NextForwardRunClear )
    {
      NextForwardRunClear = RtlFindNextForwardRunClear(&BitMapHeader, v21, &StartingRunIndex);
      if ( !NextForwardRunClear )
        break;
      *(_QWORD *)((char *)v11 + v18) = v27 * (*(_QWORD *)v9 + StartingRunIndex);
      v22 = v27 * NextForwardRunClear;
      *(_QWORD *)((char *)v11 + v18 + 8) = v22;
      if ( v22 >= 0x400000000LL )
      {
        DiskFreeSpaceW = DeviceIoControl(FileW, 0x2D9404u, v11, 0x30u, 0, 0, &BytesReturned, 0);
        if ( !DiskFreeSpaceW )
          goto LABEL_28;
      }
      v21 = NextForwardRunClear + StartingRunIndex;
    }
    InBuffer = *(_QWORD *)v9 + (unsigned int)v20;
    if ( v25 )
      goto LABEL_28;
  }
  if ( GetLastError() == 234 )
    goto LABEL_33;
  DiskFreeSpaceW = 0;
LABEL_28:
  LocalFree(v11);
LABEL_29:
  LocalFree(v9);
LABEL_30:
  CloseHandle(FileW);
  return DiskFreeSpaceW;
}

```

## disassembly

```asm
0x14000ac90  mov     [rsp-38h+arg_0], rbx
0x14000ac95  push    rbp
0x14000ac96  push    rsi
0x14000ac97  push    rdi
0x14000ac98  push    r12
0x14000ac9a  push    r13
0x14000ac9c  push    r14
0x14000ac9e  push    r15
0x14000aca0  mov     rbp, rsp
0x14000aca3  sub     rsp, 80h
0x14000acaa  xor     r12d, r12d
0x14000acad  lea     r8, [rbp+BytesPerSector]; lpBytesPerSector
0x14000acb1  xor     eax, eax
0x14000acb3  mov     [rbp+InBuffer], r12
0x14000acb7  xorps   xmm0, xmm0
0x14000acba  mov     word ptr [rbp+BitMapHeader+5], ax
0x14000acbe  mov     byte ptr [rbp+BitMapHeader+7], al
0x14000acc1  lea     rdx, [rbp+SectorsPerCluster]; lpSectorsPerCluster
0x14000acc5  xor     r9d, r9d; lpNumberOfFreeClusters
0x14000acc8  mov     [rbp+BytesReturned], r12d
0x14000accc  movups  xmmword ptr [rbp-28h], xmm0
0x14000acd0  mov     rbx, rcx
0x14000acd3  mov     [rbp+BytesPerSector], r12d
0x14000acd7  mov     [rbp+var_17], ax
0x14000acdb  mov     [rbp+var_15], al
0x14000acde  mov     [rbp+StartingRunIndex], r12d
0x14000ace2  mov     [rbp+SectorsPerCluster], r12d
0x14000ace6  mov     [rsp+80h+lpTotalNumberOfClusters], r12; lpTotalNumberOfClusters
0x14000aceb  call    cs:__imp_GetDiskFreeSpaceW
0x14000acf1  mov     edi, eax
0x14000acf3  test    eax, eax
0x14000acf5  jz      loc_14000AEB7
0x14000acfb  mov     esi, [rbp+SectorsPerCluster]
0x14000acfe  mov     r15d, [rbp+BytesPerSector]
0x14000ad02  test    rbx, rbx
0x14000ad05  jz      short loc_14000AD35
0x14000ad07  mov     edx, 104h
0x14000ad0c  mov     rax, rbx
0x14000ad0f  mov     ecx, edx
0x14000ad11  cmp     [rax], r12w
0x14000ad15  jz      short loc_14000AD21
0x14000ad17  add     rax, 2
0x14000ad1b  sub     rcx, 1
0x14000ad1f  jnz     short loc_14000AD11
0x14000ad21  sub     rdx, rcx
0x14000ad24  mov     rax, rcx
0x14000ad27  neg     rax
0x14000ad2a  sbb     r8, r8
0x14000ad2d  and     r8, rdx
0x14000ad30  test    rcx, rcx
0x14000ad33  jnz     short loc_14000AD38
0x14000ad35  mov     r8, r12
0x14000ad38  xor     r9d, r9d; lpSecurityAttributes
0x14000ad3b  mov     [rbx+r8*2-2], r12w
0x14000ad41  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x14000ad46  mov     edx, 0C0000000h; dwDesiredAccess
0x14000ad4b  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000ad53  mov     rcx, rbx; lpFileName
0x14000ad56  mov     dword ptr [rsp+80h+lpTotalNumberOfClusters], 3; dwCreationDisposition
0x14000ad5e  lea     r8d, [r9+7]; dwShareMode
0x14000ad62  call    cs:__imp_CreateFileW
0x14000ad68  mov     r13, rax
0x14000ad6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ad6f  jnz     short loc_14000AD79
0x14000ad71  mov     edi, r12d
0x14000ad74  jmp     loc_14000AEB7
0x14000ad79  mov     ebx, 40h ; '@'
0x14000ad7e  mov     edx, 800010h; uBytes
0x14000ad83  mov     ecx, ebx; uFlags
0x14000ad85  call    cs:__imp_LocalAlloc
0x14000ad8b  mov     r14, rax
0x14000ad8e  test    rax, rax
0x14000ad91  jnz     short loc_14000ADA6
0x14000ad93  mov     ecx, 5AAh; dwErrCode
0x14000ad98  mov     edi, r12d
0x14000ad9b  call    cs:__imp_SetLastError
0x14000ada1  jmp     loc_14000AEAE
0x14000ada6  mov     edx, 30h ; '0'; uBytes
0x14000adab  mov     ecx, ebx; uFlags
0x14000adad  call    cs:__imp_LocalAlloc
0x14000adb3  mov     rbx, rax
0x14000adb6  test    rax, rax
0x14000adb9  jnz     short loc_14000ADCE
0x14000adbb  mov     ecx, 5AAh; dwErrCode
0x14000adc0  mov     edi, r12d
0x14000adc3  call    cs:__imp_SetLastError
0x14000adc9  jmp     loc_14000AEA5
0x14000adce  xorps   xmm0, xmm0
0x14000add1  mov     [rbp+var_3C], r12d
0x14000add5  movups  xmmword ptr [rax], xmm0
0x14000add8  movups  xmmword ptr [rax+10h], xmm0
0x14000addc  movups  xmmword ptr [rax+20h], xmm0
0x14000ade0  mov     eax, 1Ch
0x14000ade5  mov     dword ptr [rbx+4], 80000012h
0x14000adec  imul    r15, rsi
0x14000adf0  mov     [rbx], eax
0x14000adf2  mov     [rbp+var_30], r15
0x14000adf6  mov     r8d, [rbx+18h]
0x14000adfa  test    r8d, r8d
0x14000adfd  jnz     short loc_14000AE19
0x14000adff  mov     ecx, [rbx+10h]
0x14000ae02  test    ecx, ecx
0x14000ae04  jz      short loc_14000AE0B
0x14000ae06  mov     eax, [rbx+0Ch]
0x14000ae09  add     eax, ecx
0x14000ae0b  mov     edx, [rbx+14h]
0x14000ae0e  mov     ecx, eax
0x14000ae10  add     rcx, 7
0x14000ae14  and     ecx, 0FFFFFFF8h
0x14000ae17  jmp     short loc_14000AE20
0x14000ae19  mov     edx, [rbx+14h]
0x14000ae1c  lea     ecx, [rdx+r8]
0x14000ae20  mov     eax, 30h ; '0'
0x14000ae25  sub     eax, ecx
0x14000ae27  cmp     eax, 10h
0x14000ae2a  jb      short loc_14000AE4E
0x14000ae2c  test    edx, edx
0x14000ae2e  jnz     short loc_14000AE35
0x14000ae30  mov     [rbx+14h], ecx
0x14000ae33  jmp     short loc_14000AE37
0x14000ae35  mov     ecx, edx
0x14000ae37  mov     rax, r8
0x14000ae3a  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000ae3e  add     rax, rbx
0x14000ae41  mov     [rcx+rax], r12
0x14000ae45  mov     [rcx+rax+8], r12
0x14000ae4a  add     dword ptr [rbx+18h], 10h
0x14000ae4e  mov     r12d, [rbx+14h]
0x14000ae52  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x14000ae5b  lea     rax, [rbp+BytesReturned]
0x14000ae5f  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x14000ae64  lea     r8, [rbp+InBuffer]; lpInBuffer
0x14000ae68  mov     [rsp+80h+dwFlagsAndAttributes], 800010h; nOutBufferSize
0x14000ae70  mov     r9d, 8; nInBufferSize
0x14000ae76  mov     edx, 9006Fh; dwIoControlCode
0x14000ae7b  mov     [rsp+80h+lpTotalNumberOfClusters], r14; lpOutBuffer
0x14000ae80  mov     rcx, r13; hDevice
0x14000ae83  call    cs:__imp_DeviceIoControl
0x14000ae89  test    eax, eax
0x14000ae8b  jnz     short loc_14000AED4
0x14000ae8d  call    cs:__imp_GetLastError
0x14000ae93  cmp     eax, 0EAh
0x14000ae98  jz      short loc_14000AEDB
0x14000ae9a  xor     edi, edi
0x14000ae9c  mov     rcx, rbx; hMem
0x14000ae9f  call    cs:__imp_LocalFree
0x14000aea5  mov     rcx, r14; hMem
0x14000aea8  call    cs:__imp_LocalFree
0x14000aeae  mov     rcx, r13; hObject
0x14000aeb1  call    cs:__imp_CloseHandle
0x14000aeb7  mov     rbx, [rsp+80h+arg_0]
0x14000aebf  mov     eax, edi
0x14000aec1  add     rsp, 80h
0x14000aec8  pop     r15
0x14000aeca  pop     r14
0x14000aecc  pop     r13
0x14000aece  pop     r12
0x14000aed0  pop     rdi
0x14000aed1  pop     rsi
0x14000aed2  pop     rbp
0x14000aed3  retn
0x14000aed4  mov     [rbp+var_3C], 1
0x14000aedb  mov     rsi, [r14+8]
0x14000aedf  cmp     rsi, 4000000h
0x14000aee6  jle     short loc_14000AEED
0x14000aee8  mov     esi, 4000000h
0x14000aeed  lea     rdx, [r14+10h]; BitMapBuffer
0x14000aef1  mov     r8d, esi; SizeOfBitMap
0x14000aef4  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14000aef8  call    cs:__imp_RtlInitializeBitMap
0x14000aefe  xor     edx, edx
0x14000af00  mov     [rbp+StartingRunIndex], 0
0x14000af07  jmp     short loc_14000AF81
0x14000af09  mov     ecx, [rbp+StartingRunIndex]
0x14000af0c  mov     rax, 400000000h
0x14000af16  add     rcx, [r14]
0x14000af19  imul    rcx, [rbp+var_30]
0x14000af1e  mov     [r12+rbx], rcx
0x14000af22  mov     ecx, r15d
0x14000af25  imul    rcx, [rbp+var_30]
0x14000af2a  mov     [r12+rbx+8], rcx
0x14000af2f  cmp     rcx, rax
0x14000af32  jb      short loc_14000AF78
0x14000af34  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x14000af3d  lea     rax, [rbp+BytesReturned]
0x14000af41  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x14000af46  mov     r9d, 30h ; '0'; nInBufferSize
0x14000af4c  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14000af54  mov     r8, rbx; lpInBuffer
0x14000af57  mov     edx, 2D9404h; dwIoControlCode
0x14000af5c  mov     [rsp+80h+lpTotalNumberOfClusters], 0; lpOutBuffer
0x14000af65  mov     rcx, r13; hDevice
0x14000af68  call    cs:__imp_DeviceIoControl
0x14000af6e  mov     edi, eax
0x14000af70  test    eax, eax
0x14000af72  jz      loc_14000AE9C
0x14000af78  mov     edx, [rbp+StartingRunIndex]
0x14000af7b  add     edx, r15d; FromIndex
0x14000af7e  mov     [rbp+StartingRunIndex], edx
0x14000af81  lea     r8, [rbp+StartingRunIndex]; StartingRunIndex
0x14000af85  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x14000af89  call    cs:__imp_RtlFindNextForwardRunClear
0x14000af8f  mov     r15d, eax
0x14000af92  test    eax, eax
0x14000af94  jnz     loc_14000AF09
0x14000af9a  mov     eax, esi
0x14000af9c  add     rax, [r14]
0x14000af9f  cmp     [rbp+var_3C], 0
0x14000afa3  mov     [rbp+InBuffer], rax
0x14000afa7  jz      loc_14000AE52
0x14000afad  jmp     loc_14000AE9C
```
