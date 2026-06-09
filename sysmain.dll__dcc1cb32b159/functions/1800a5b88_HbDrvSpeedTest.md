# HbDrvSpeedTest

- ea: `0x1800a5b88`
- end: `0x1800a6081`
- name: `HbDrvSpeedTest`
- size: `1273`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800a4eb0`

## callees

- `0x180074dac`
- `0x18009ef80`
- `0x18009f0d8`
- `0x1800a1ab0`
- `0x1800a2aa0`
- `0x1800a4148`
- `0x1800a5034`
- `0x1800a5b88`
- `0x1800a62bc`
- `0x1800a6440`
- `0x1800b57c0`
- `0x1800b62c8`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a5c8d`
- `ntdll!RtlNtStatusToDosError` at `0x1800a5c8d`
- `ntdll!NtClose` at `0x1800a600e`
- `ntdll!NtClose` at `0x1800a600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a601d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a601d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5e63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5f89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5e63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5f89`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800a5e5a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800a5e5a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a5e6f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a5f95`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a5e6f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a5f95`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a604a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a604a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5e0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5e0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6039`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a6039`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800a5c81`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800a5c81`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a5ca2`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a5ca2`

## pseudocode

```c
__int64 __fastcall HbDrvSpeedTest(__int64 a1, int a2, int a3, __int64 a4, __int64 a5, int *a6)
{
  __int64 v9; // rsi
  int v10; // r15d
  __int64 v11; // rcx
  int v12; // edx
  int ControlDeviceHandle; // eax
  NTSTATUS v14; // ecx
  ULONG SpeedTestFilePath; // ebx
  __int64 v16; // rdx
  NTSTATUS updated; // eax
  LARGE_INTEGER v18; // r14
  _QWORD *v19; // r9
  unsigned __int64 v20; // rdx
  int v21; // r15d
  HANDLE FileW; // rax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r12d
  HANDLE v25; // rax
  int v26; // r10d
  int v27; // r9d
  int v28; // ecx
  unsigned int v29; // r8d
  __int64 v30; // rax
  HANDLE v31; // rdx
  __int64 v32; // xmm0_8
  HANDLE v33; // rax
  unsigned int i; // edi
  HANDLE Handle; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h] BYREF
  int v38; // [rsp+68h] [rbp-A0h]
  int v39; // [rsp+70h] [rbp-98h] BYREF
  int v40; // [rsp+74h] [rbp-94h]
  __int64 v41; // [rsp+78h] [rbp-90h] BYREF
  int v42; // [rsp+80h] [rbp-88h]
  LPVOID lpMem; // [rsp+88h] [rbp-80h] BYREF
  __int64 v44; // [rsp+90h] [rbp-78h]
  int *v45; // [rsp+98h] [rbp-70h]
  _OWORD v46[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-48h]
  _BYTE v48[24]; // [rsp+D8h] [rbp-30h] BYREF
  char v49[8]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-10h]
  __int64 v51; // [rsp+108h] [rbp+0h]
  void (*v52)(void); // [rsp+118h] [rbp+10h]
  unsigned int v53; // [rsp+124h] [rbp+1Ch]
  WCHAR FileName[264]; // [rsp+148h] [rbp+40h] BYREF

  v44 = a5;
  v40 = a3;
  v45 = a6;
  memset_0(v48, 0, 0x68u);
  v39 = 0;
  lpMem = 0;
  Handle = 0;
  v9 = -1;
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  HbDrvBitmapInitialize(v48);
  v10 = *(_DWORD *)(a1 + 3628);
  memset_0(FileName, 0, 0x208u);
  v11 = *(_QWORD *)(a1 + 32);
  v41 = 0;
  v42 = 0;
  v12 = *(_DWORD *)(v11 + 40);
  v37 = 0;
  v38 = 0;
  *(_QWORD *)&v46[0] = *(_QWORD *)(v11 + 28);
  DWORD2(v47) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) & 0xFFFFFFFE | v12 & 1;
  ControlDeviceHandle = SmuGetControlDeviceHandle(&Handle, 3221225472LL);
  if ( ControlDeviceHandle < 0 || (ControlDeviceHandle = SmuCacheHitsControl(Handle, 1), ControlDeviceHandle < 0) )
  {
    v14 = ControlDeviceHandle;
LABEL_3:
    SpeedTestFilePath = RtlNtStatusToDosError(v14);
    goto LABEL_32;
  }
  if ( a2 )
  {
    updated = HbDrvSendStoreUpdateRequestInternal(
                a1,
                (_DWORD)Handle,
                *(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL),
                0,
                0,
                6,
                0,
                0,
                0);
    v16 = 0x80000000LL;
    v14 = updated;
    if ( (int)(updated + 0x80000000) >= 0 && updated != -1073700861 )
      goto LABEL_3;
  }
  SpeedTestFilePath = HbDrvGetSpeedTestFilePath(*(_QWORD *)(a1 + 32), v16, FileName);
  if ( !SpeedTestFilePath )
  {
    v18.QuadPart = (v10 << 20) * (((v10 << 20) + 209715199) / (unsigned int)(v10 << 20));
    SpeedTestFilePath = HbDrvSpeedTestCreateTestFile(FileName, v18, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( !SpeedTestFilePath )
    {
      v19 = *(_QWORD **)(a1 + 32);
      v20 = ((unsigned __int64)(unsigned int)(1 << *(_BYTE *)(a1 + 24)) + *v19 - 1LL)
          / (unsigned int)(1 << *(_BYTE *)(a1 + 24));
      if ( v20 >= 0xFFFFFFFFLL << *(_BYTE *)(a1 + 24) )
        v20 = 0xFFFFFFFFLL << *(_BYTE *)(a1 + 24);
      SpeedTestFilePath = HbDrvBitmapStart((unsigned int)v48, v20, 1, 0, v19[1]);
      if ( !SpeedTestFilePath )
      {
        SpeedTestFilePath = HbDrvRefreshTaskLoadFromFile(a1, FileName, v46, 0, &lpMem, &v39, v48, 1);
        if ( !SpeedTestFilePath )
        {
          if ( !(_DWORD)v47 )
          {
            SpeedTestFilePath = 1359;
            goto LABEL_32;
          }
          v21 = 3;
          FileW = CreateFileW(FileName, 0xC0000000, 0, 0, 3u, 0x20000000u, 0);
          v9 = (__int64)FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            SpeedTestFilePath = GetLastError();
            goto LABEL_32;
          }
          SpeedTestFilePath = HbDrvPrepareTestFile(a1, Handle, v48, v18.LowPart, 0, FileW);
          if ( !SpeedTestFilePath )
          {
            CurrentThread = GetCurrentThread();
            ThreadPriority = GetThreadPriority(CurrentThread);
            v25 = GetCurrentThread();
            SetThreadPriority(v25, 15);
            SpeedTestFilePath = HbDrvSpeedTestInternal(a1, &v41, v9, v18.LowPart, 0);
            if ( !SpeedTestFilePath )
            {
              SpeedTestFilePath = HbDrvPrepareTestFile(a1, Handle, v48, v18.LowPart, v40 - 1, v9);
              if ( !SpeedTestFilePath )
              {
                SpeedTestFilePath = HbDrvSpeedTestInternal(a1, &v37, v9, v18.LowPart, 1);
                if ( !SpeedTestFilePath )
                {
                  v26 = v42;
                  v27 = v38;
                  if ( (unsigned int)v37 < 0x1C00 )
                  {
LABEL_28:
                    v30 = v44;
                    v31 = Handle;
                    *(_QWORD *)a4 = v41;
                    v32 = v37;
                    *(_DWORD *)(a4 + 8) = v26;
                    *(_QWORD *)v30 = v32;
                    *(_DWORD *)(v30 + 8) = v27;
                    *v45 = v21;
                    HbDrvPrepareTestFile(a1, v31, v48, v18.LowPart, 0, v9);
                    SpeedTestFilePath = 0;
                    goto LABEL_30;
                  }
                  v28 = v38 + 4 * HIDWORD(v37);
                  if ( v28 )
                  {
                    v29 = v42 + 4 * HIDWORD(v41);
                    if ( v29 )
                    {
                      v21 = SpeedTestFilePath + 2;
                      if ( 85 * v28 / 0x64u >= v29 )
                        v21 = SpeedTestFilePath + 1;
                      goto LABEL_28;
                    }
                  }
                  SpeedTestFilePath = 13;
                }
              }
            }
LABEL_30:
            if ( ThreadPriority != 32 )
            {
              v33 = GetCurrentThread();
              SetThreadPriority(v33, ThreadPriority);
            }
          }
        }
      }
    }
  }
LABEL_32:
  HbDrvGetFileExtentDataCleanup(v46);
  if ( v50 )
  {
    for ( i = 0; i < v53; ++i )
    {
      if ( (unsigned __int8)RtlpSparseBitmapCheckRangeArrayPage(v49, i) )
      {
        if ( *(_QWORD *)(v50 + 8LL * i) )
          v52();
      }
      else
      {
        i += 511;
      }
    }
    RtlpSparseBitmapRangeArrayCleanup(v49, v50, v51);
  }
  if ( Handle )
    NtClose(Handle);
  if ( v9 != -1 )
    CloseHandle((HANDLE)v9);
  if ( lpMem )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpMem);
  if ( FileName[0] )
    DeleteFileW(FileName);
  return SpeedTestFilePath;
}

```

## disassembly

```asm
0x1800a5b88  mov     rax, rsp
0x1800a5b8b  mov     [rax+10h], rbx
0x1800a5b8f  push    rbp
0x1800a5b90  push    rsi
0x1800a5b91  push    rdi
0x1800a5b92  push    r12
0x1800a5b94  push    r13
0x1800a5b96  push    r14
0x1800a5b98  push    r15
0x1800a5b9a  lea     rbp, [rax-2A8h]
0x1800a5ba1  sub     rsp, 370h
0x1800a5ba8  movaps  xmmword ptr [rax-48h], xmm6
0x1800a5bac  mov     rax, cs:__security_cookie
0x1800a5bb3  xor     rax, rsp
0x1800a5bb6  mov     [rbp+2A0h+var_50], rax
0x1800a5bbd  mov     rax, [rbp+2A0h+arg_20]
0x1800a5bc4  mov     ebx, edx
0x1800a5bc6  xor     edx, edx; Val
0x1800a5bc8  mov     [rbp+2A0h+var_318], rax
0x1800a5bcc  mov     rax, [rbp+2A0h+arg_28]
0x1800a5bd3  mov     rdi, rcx
0x1800a5bd6  mov     dword ptr [rsp+3A0h+var_338+4], r8d
0x1800a5bdb  lea     rcx, [rbp+2A0h+var_2D0]; void *
0x1800a5bdf  mov     r13, r9
0x1800a5be2  mov     [rbp+2A0h+var_310], rax
0x1800a5be6  lea     r8d, [rdx+68h]; Size
0x1800a5bea  call    memset_0
0x1800a5bef  xor     r12d, r12d
0x1800a5bf2  lea     rcx, [rbp+2A0h+var_2D0]
0x1800a5bf6  xorps   xmm6, xmm6
0x1800a5bf9  mov     dword ptr [rsp+3A0h+var_338], r12d
0x1800a5bfe  xorps   xmm0, xmm0
0x1800a5c01  mov     [rbp+2A0h+lpMem], r12
0x1800a5c05  movups  [rbp+2A0h+var_2F8], xmm0
0x1800a5c09  mov     [rsp+3A0h+Handle], r12
0x1800a5c0e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a5c12  movups  [rbp+2A0h+var_308], xmm6
0x1800a5c16  movups  [rbp+2A0h+var_2E8], xmm6
0x1800a5c1a  call    HbDrvBitmapInitialize
0x1800a5c1f  mov     r15d, [rdi+0E2Ch]
0x1800a5c26  lea     rcx, [rbp+2A0h+FileName]; void *
0x1800a5c2a  xor     edx, edx; Val
0x1800a5c2c  mov     r8d, 208h; Size
0x1800a5c32  call    memset_0
0x1800a5c37  mov     rcx, [rdi+20h]
0x1800a5c3b  lea     r14d, [r12+1]
0x1800a5c40  xor     eax, eax
0x1800a5c42  psrldq  xmm6, 8
0x1800a5c47  mov     qword ptr [rsp+3A0h+var_330], rax
0x1800a5c4c  mov     [rsp+3A0h+var_328], eax
0x1800a5c50  mov     edx, [rcx+28h]
0x1800a5c53  mov     qword ptr [rsp+3A0h+var_348], rax
0x1800a5c58  and     edx, r14d
0x1800a5c5b  mov     [rsp+3A0h+var_340], eax
0x1800a5c5f  mov     eax, [rcx+1Ch]
0x1800a5c62  mov     dword ptr [rbp+2A0h+var_308], eax
0x1800a5c65  mov     eax, [rcx+20h]
0x1800a5c68  lea     rcx, [rsp+3A0h+Handle]
0x1800a5c6d  mov     dword ptr [rbp+2A0h+var_308+4], eax
0x1800a5c70  movd    eax, xmm6
0x1800a5c74  and     eax, 0FFFFFFFEh
0x1800a5c77  or      edx, eax
0x1800a5c79  mov     dword ptr [rbp+2A0h+var_2E8+8], edx
0x1800a5c7c  mov     edx, 0C0000000h
0x1800a5c81  call    cs:__imp_SmuGetControlDeviceHandle
0x1800a5c87  test    eax, eax
0x1800a5c89  jns     short loc_1800A5C9A
0x1800a5c8b  mov     ecx, eax; Status
0x1800a5c8d  call    cs:__imp_RtlNtStatusToDosError
0x1800a5c93  mov     ebx, eax
0x1800a5c95  jmp     loc_1800A5FA4
0x1800a5c9a  mov     rcx, [rsp+3A0h+Handle]
0x1800a5c9f  mov     edx, r14d
0x1800a5ca2  call    cs:__imp_SmuCacheHitsControl
0x1800a5ca8  test    eax, eax
0x1800a5caa  js      short loc_1800A5C8B
0x1800a5cac  test    ebx, ebx
0x1800a5cae  jz      short loc_1800A5CF9
0x1800a5cb0  mov     r8, [rdi+20h]
0x1800a5cb4  xor     r9d, r9d
0x1800a5cb7  mov     rdx, [rsp+3A0h+Handle]
0x1800a5cbc  mov     rcx, rdi
0x1800a5cbf  mov     [rsp+3A0h+var_360], r12d
0x1800a5cc4  mov     qword ptr [rsp+3A0h+var_368], r12
0x1800a5cc9  mov     r8, [r8+10h]
0x1800a5ccd  mov     dword ptr [rsp+3A0h+hTemplateFile], r12d
0x1800a5cd2  mov     [rsp+3A0h+dwFlagsAndAttributes], 6
0x1800a5cda  mov     [rsp+3A0h+dwCreationDisposition], r12d
0x1800a5cdf  call    HbDrvSendStoreUpdateRequestInternal
0x1800a5ce4  mov     edx, 80000000h
0x1800a5ce9  mov     ecx, eax
0x1800a5ceb  add     eax, edx
0x1800a5ced  test    edx, eax
0x1800a5cef  jnz     short loc_1800A5CF9
0x1800a5cf1  cmp     ecx, 0C000A003h
0x1800a5cf7  jnz     short loc_1800A5C8D
0x1800a5cf9  mov     rcx, [rdi+20h]
0x1800a5cfd  lea     r8, [rbp+2A0h+FileName]
0x1800a5d01  call    HbDrvGetSpeedTestFilePath
0x1800a5d06  mov     ebx, eax
0x1800a5d08  test    eax, eax
0x1800a5d0a  jnz     loc_1800A5FA4
0x1800a5d10  shl     r15d, 14h
0x1800a5d14  lea     rcx, [rbp+2A0h+FileName]; lpFileName
0x1800a5d18  xor     edx, edx
0x1800a5d1a  or      r8, 0FFFFFFFFFFFFFFFFh; hFile
0x1800a5d1e  lea     eax, [r15+0C7FFFFFh]
0x1800a5d25  div     r15d
0x1800a5d28  mov     r14d, eax
0x1800a5d2b  imul    r14d, r15d
0x1800a5d2f  mov     edx, r14d; liDistanceToMove
0x1800a5d32  call    HbDrvSpeedTestCreateTestFile
0x1800a5d37  mov     ebx, eax
0x1800a5d39  test    eax, eax
0x1800a5d3b  jnz     loc_1800A5F9E
0x1800a5d41  movzx   r8d, byte ptr [rdi+18h]
0x1800a5d46  lea     r15d, [rax+1]
0x1800a5d4a  mov     r9, [rdi+20h]
0x1800a5d4e  xor     edx, edx
0x1800a5d50  mov     ecx, r8d
0x1800a5d53  mov     eax, r15d
0x1800a5d56  shl     eax, cl
0x1800a5d58  mov     ecx, eax
0x1800a5d5a  mov     rax, [r9]
0x1800a5d5d  dec     rax
0x1800a5d60  add     rax, rcx
0x1800a5d63  div     rcx
0x1800a5d66  mov     ecx, r8d
0x1800a5d69  mov     r8d, r15d
0x1800a5d6c  mov     rdx, rax
0x1800a5d6f  mov     eax, 0FFFFFFFFh
0x1800a5d74  shl     rax, cl
0x1800a5d77  lea     rcx, [rbp+2A0h+var_2D0]
0x1800a5d7b  cmp     rdx, rax
0x1800a5d7e  cmovnb  rdx, rax
0x1800a5d82  mov     rax, [r9+8]
0x1800a5d86  xor     r9d, r9d
0x1800a5d89  mov     qword ptr [rsp+3A0h+dwCreationDisposition], rax
0x1800a5d8e  call    HbDrvBitmapStart
0x1800a5d93  mov     ebx, eax
0x1800a5d95  test    eax, eax
0x1800a5d97  jnz     short loc_1800A5DDE
0x1800a5d99  mov     [rsp+3A0h+var_368], r15d
0x1800a5d9e  lea     rax, [rbp+2A0h+var_2D0]
0x1800a5da2  mov     [rsp+3A0h+hTemplateFile], rax
0x1800a5da7  lea     r8, [rbp+2A0h+var_308]
0x1800a5dab  lea     rax, [rsp+3A0h+var_338]
0x1800a5db0  xor     r9d, r9d
0x1800a5db3  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], rax
0x1800a5db8  lea     rdx, [rbp+2A0h+FileName]
0x1800a5dbc  lea     rax, [rbp+2A0h+lpMem]
0x1800a5dc0  mov     rcx, rdi
0x1800a5dc3  mov     qword ptr [rsp+3A0h+dwCreationDisposition], rax
0x1800a5dc8  call    HbDrvRefreshTaskLoadFromFile
0x1800a5dcd  mov     ebx, eax
0x1800a5dcf  test    eax, eax
0x1800a5dd1  jnz     short loc_1800A5DDE
0x1800a5dd3  cmp     dword ptr [rbp+2A0h+var_2E8], r12d
0x1800a5dd7  jnz     short loc_1800A5DE6
0x1800a5dd9  mov     ebx, 54Fh
0x1800a5dde  mov     r14d, r15d
0x1800a5de1  jmp     loc_1800A5FA4
0x1800a5de6  mov     [rsp+3A0h+hTemplateFile], r12; hTemplateFile
0x1800a5deb  lea     rcx, [rbp+2A0h+FileName]; lpFileName
0x1800a5def  mov     r15d, 3
0x1800a5df5  mov     [rsp+3A0h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1800a5dfd  xor     r9d, r9d; lpSecurityAttributes
0x1800a5e00  mov     [rsp+3A0h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800a5e05  xor     r8d, r8d; dwShareMode
0x1800a5e08  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a5e0d  call    cs:__imp_CreateFileW
0x1800a5e13  mov     rsi, rax
0x1800a5e16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5e1a  jnz     short loc_1800A5E29
0x1800a5e1c  call    cs:__imp_GetLastError
0x1800a5e22  mov     ebx, eax
0x1800a5e24  jmp     loc_1800A5F9E
0x1800a5e29  mov     rdx, [rsp+3A0h+Handle]
0x1800a5e2e  lea     r8, [rbp+2A0h+var_2D0]
0x1800a5e32  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], rsi
0x1800a5e37  mov     r9d, r14d
0x1800a5e3a  mov     rcx, rdi
0x1800a5e3d  mov     [rsp+3A0h+dwCreationDisposition], r12d
0x1800a5e42  call    HbDrvPrepareTestFile
0x1800a5e47  mov     ebx, eax
0x1800a5e49  test    eax, eax
0x1800a5e4b  jnz     loc_1800A5F9E
0x1800a5e51  call    cs:__imp_GetCurrentThread
0x1800a5e57  mov     rcx, rax; hThread
0x1800a5e5a  call    cs:__imp_GetThreadPriority
0x1800a5e60  mov     r12d, eax
0x1800a5e63  call    cs:__imp_GetCurrentThread
0x1800a5e69  mov     rcx, rax; hThread
0x1800a5e6c  lea     edx, [rbx+0Fh]; nPriority
0x1800a5e6f  call    cs:__imp_SetThreadPriority
0x1800a5e75  mov     r9d, r14d
0x1800a5e78  mov     [rsp+3A0h+dwCreationDisposition], ebx
0x1800a5e7c  mov     r8, rsi
0x1800a5e7f  lea     rdx, [rsp+3A0h+var_330]
0x1800a5e84  mov     rcx, rdi
0x1800a5e87  call    HbDrvSpeedTestInternal
0x1800a5e8c  mov     ebx, eax
0x1800a5e8e  test    eax, eax
0x1800a5e90  jnz     loc_1800A5F83
0x1800a5e96  mov     eax, dword ptr [rsp+3A0h+var_338+4]
0x1800a5e9a  lea     r8, [rbp+2A0h+var_2D0]
0x1800a5e9e  mov     rdx, [rsp+3A0h+Handle]
0x1800a5ea3  dec     eax
0x1800a5ea5  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], rsi
0x1800a5eaa  mov     r9d, r14d
0x1800a5ead  mov     rcx, rdi
0x1800a5eb0  mov     [rsp+3A0h+dwCreationDisposition], eax
0x1800a5eb4  call    HbDrvPrepareTestFile
0x1800a5eb9  mov     ebx, eax
0x1800a5ebb  test    eax, eax
0x1800a5ebd  jnz     loc_1800A5F83
0x1800a5ec3  mov     r9d, r14d
0x1800a5ec6  mov     [rsp+3A0h+dwCreationDisposition], 1
0x1800a5ece  mov     r8, rsi
0x1800a5ed1  lea     rdx, [rsp+3A0h+var_348]
0x1800a5ed6  mov     rcx, rdi
0x1800a5ed9  call    HbDrvSpeedTestInternal
0x1800a5ede  mov     ebx, eax
0x1800a5ee0  test    eax, eax
0x1800a5ee2  jnz     loc_1800A5F83
0x1800a5ee8  cmp     [rsp+3A0h+var_348], 1C00h
0x1800a5ef0  mov     r10d, [rsp+3A0h+var_328]
0x1800a5ef5  mov     r9d, [rsp+3A0h+var_340]
0x1800a5efa  jb      short loc_1800A5F30
0x1800a5efc  mov     eax, [rsp+3A0h+var_344]
0x1800a5f00  lea     ecx, [r9+rax*4]
0x1800a5f04  test    ecx, ecx
0x1800a5f06  jz      short loc_1800A5F7E
0x1800a5f08  mov     eax, [rsp+3A0h+var_32C]
0x1800a5f0c  lea     r8d, [r10+rax*4]
0x1800a5f10  test    r8d, r8d
0x1800a5f13  jz      short loc_1800A5F7E
0x1800a5f15  imul    ecx, 55h ; 'U'
0x1800a5f18  lea     r15d, [rbx+2]
0x1800a5f1c  mov     eax, 51EB851Fh
0x1800a5f21  mul     ecx
0x1800a5f23  lea     eax, [rbx+1]
0x1800a5f26  shr     edx, 5
0x1800a5f29  cmp     edx, r8d
0x1800a5f2c  cmovnb  r15d, eax
0x1800a5f30  movsd   xmm0, qword ptr [rsp+3A0h+var_330]
0x1800a5f36  lea     r8, [rbp+2A0h+var_2D0]
0x1800a5f3a  mov     rax, [rbp+2A0h+var_318]
0x1800a5f3e  mov     rcx, rdi
0x1800a5f41  mov     rdx, [rsp+3A0h+Handle]
0x1800a5f46  movsd   qword ptr [r13+0], xmm0
0x1800a5f4c  movsd   xmm0, qword ptr [rsp+3A0h+var_348]
0x1800a5f52  mov     [r13+8], r10d
0x1800a5f56  movsd   qword ptr [rax], xmm0
0x1800a5f5a  mov     [rax+8], r9d
0x1800a5f5e  mov     r9d, r14d
0x1800a5f61  mov     rax, [rbp+2A0h+var_310]
0x1800a5f65  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], rsi
0x1800a5f6a  mov     [rsp+3A0h+dwCreationDisposition], 0
0x1800a5f72  mov     [rax], r15d
0x1800a5f75  call    HbDrvPrepareTestFile
0x1800a5f7a  xor     ebx, ebx
0x1800a5f7c  jmp     short loc_1800A5F83
0x1800a5f7e  mov     ebx, 0Dh
0x1800a5f83  cmp     r12d, 20h ; ' '
0x1800a5f87  jz      short loc_1800A5F9B
0x1800a5f89  call    cs:__imp_GetCurrentThread
0x1800a5f8f  mov     rcx, rax; hThread
0x1800a5f92  mov     edx, r12d; nPriority
0x1800a5f95  call    cs:__imp_SetThreadPriority
0x1800a5f9b  xor     r12d, r12d
0x1800a5f9e  mov     r14d, 1
0x1800a5fa4  lea     rcx, [rbp+2A0h+var_308]
0x1800a5fa8  call    HbDrvGetFileExtentDataCleanup
0x1800a5fad  cmp     [rbp+2A0h+var_2B0], r12
0x1800a5fb1  jz      short loc_1800A6004
0x1800a5fb3  mov     edi, r12d
0x1800a5fb6  cmp     [rbp+2A0h+var_284], r12d
0x1800a5fba  jbe     short loc_1800A5FF3
0x1800a5fbc  mov     edx, edi
0x1800a5fbe  lea     rcx, [rbp+2A0h+var_2B8]
0x1800a5fc2  call    RtlpSparseBitmapCheckRangeArrayPage
0x1800a5fc7  test    al, al
0x1800a5fc9  jnz     short loc_1800A5FD3
0x1800a5fcb  add     edi, 1FFh
0x1800a5fd1  jmp     short loc_1800A5FEB
0x1800a5fd3  mov     rax, [rbp+2A0h+var_2B0]
0x1800a5fd7  mov     ecx, edi
0x1800a5fd9  mov     rcx, [rax+rcx*8]
0x1800a5fdd  test    rcx, rcx
0x1800a5fe0  jz      short loc_1800A5FEB
0x1800a5fe2  mov     rax, [rbp+2A0h+var_290]
0x1800a5fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5feb  add     edi, r14d
0x1800a5fee  cmp     edi, [rbp+2A0h+var_284]
0x1800a5ff1  jb      short loc_1800A5FBC
0x1800a5ff3  mov     r8, [rbp+2A0h+var_2A0]
0x1800a5ff7  lea     rcx, [rbp+2A0h+var_2B8]
0x1800a5ffb  mov     rdx, [rbp+2A0h+var_2B0]
0x1800a5fff  call    RtlpSparseBitmapRangeArrayCleanup
  ... truncated ...
```
