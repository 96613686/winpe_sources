# OutOfProcessExceptionEventSignatureCallback(void *,_WER_RUNTIME_EXCEPTION_INFORMATION * const,ulong,ushort *,ulong *,ushort *,ulong *)

- ea: `0x18006f130`
- end: `0x18006f3a4`
- name: `?OutOfProcessExceptionEventSignatureCallback@@YAJPEAXQEAU_WER_RUNTIME_EXCEPTION_INFORMATION@@KPEAGPEAK23@Z`
- size: `628`
- prototype: `int(void *, struct _WER_RUNTIME_EXCEPTION_INFORMATION *const, unsigned int, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004cc0`
- `0x18005388c`
- `0x1800694bc`
- `0x180069524`
- `0x18006f130`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f2ee`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f327`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f2ee`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006f327`

## string_xrefs

- `0x18006f37d`: `onecore\ds\security\biometrics\service\service\winbiowerinterface.cpp`

## pseudocode

```c
__int64 __fastcall OutOfProcessExceptionEventSignatureCallback(
        void *a1,
        struct _WER_RUNTIME_EXCEPTION_INFORMATION *const a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 *lpBuffer,
        unsigned int *a7)
{
  __int64 v7; // rsi
  EXCEPTION_RECORD *p_exceptionRecord; // r14
  __int64 v11; // rdx
  BOOL v12; // ebx
  unsigned int v13; // eax
  HANDLE hProcess; // rcx
  __int64 v15; // r11
  const void *v16; // rdx
  unsigned int v17; // esi
  unsigned int v18; // eax
  int lpNumberOfBytesRead; // [rsp+20h] [rbp-68h]
  __int128 Buffer; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = a3;
  if ( !a2 || !a4 || !a5 || !*a5 || !lpBuffer || !a7 || !*a7 )
  {
    v11 = 137;
    goto LABEL_27;
  }
  p_exceptionRecord = &a2->exceptionRecord;
  if ( a2 == (struct _WER_RUNTIME_EXCEPTION_INFORMATION *const)-24LL )
  {
    v11 = 141;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\service\\winbiowerinterface.cpp",
      (const char *)0x80004005LL,
      lpNumberOfBytesRead);
    return 2147500037LL;
  }
  v12 = 1;
  if ( a2->exceptionRecord.ExceptionInformation[1] != 1 || a3 >= 0xA )
    goto LABEL_22;
  if ( dword_180110D10 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180110D10);
    if ( dword_180110D10 == -1 )
    {
      qword_1801103D0[0] = (__int64)L"BiometricFactor";
      qword_1801103D8 = (__int64)L"Manufacturer";
      qword_1801103E0 = (__int64)L"Description";
      qword_1801103E8 = (__int64)L"OperationalState";
      qword_1801103F0 = (__int64)L"SensorAdapter";
      qword_1801103F8 = (__int64)L"EngineAdapter";
      qword_180110400 = (__int64)L"StorageAdapter";
      qword_180110408 = (__int64)L"IsolationSensorAdapter";
      qword_180110410 = (__int64)L"IsolationEngineAdapter";
      qword_180110418 = (__int64)L"IsolationStorageAdapter";
      Init_thread_footer(&dword_180110D10);
    }
  }
  v13 = StringCchCopyW(a4, *a5, (const unsigned __int16 *)qword_1801103D0[v7]);
  hProcess = a2->hProcess;
  v16 = (const void *)(p_exceptionRecord->ExceptionInformation[1] + 16 * v15);
  v17 = v13 >> 31;
  Buffer = 0;
  if ( ReadProcessMemory(hProcess, v16, &Buffer, 0x10u, 0) && (_QWORD)Buffer && DWORD2(Buffer) > 1 )
  {
    v18 = *a7;
    if ( DWORD2(Buffer) < *a7 )
      v18 = DWORD2(Buffer);
    v12 = !ReadProcessMemory(a2->hProcess, (LPCVOID)Buffer, lpBuffer, 2LL * v18, 0);
    lpBuffer[*a7 - 1] = 0;
  }
  if ( v17 )
LABEL_22:
    StringCchCopyW(a4, *a5, L"Unknown");
  if ( v12 )
    StringCchCopyW(lpBuffer, *a7, L"Unavailable");
  return 0;
}

```

## disassembly

```asm
0x18006f130  push    rbx
0x18006f132  push    rbp
0x18006f133  push    rsi
0x18006f134  push    rdi
0x18006f135  push    r12
0x18006f137  push    r13
0x18006f139  push    r14
0x18006f13b  push    r15
0x18006f13d  sub     rsp, 48h
0x18006f141  mov     esi, r8d
0x18006f144  mov     r12, r9
0x18006f147  mov     r13, rdx
0x18006f14a  test    rdx, rdx
0x18006f14d  jz      loc_18006F370
0x18006f153  test    r9, r9
0x18006f156  jz      loc_18006F370
0x18006f15c  mov     rbp, [rsp+88h+arg_20]
0x18006f164  test    rbp, rbp
0x18006f167  jz      loc_18006F370
0x18006f16d  cmp     dword ptr [rbp+0], 0
0x18006f171  jz      loc_18006F370
0x18006f177  mov     r15, [rsp+88h+lpBuffer]
0x18006f17f  test    r15, r15
0x18006f182  jz      loc_18006F370
0x18006f188  mov     rdi, [rsp+88h+arg_30]
0x18006f190  test    rdi, rdi
0x18006f193  jz      loc_18006F370
0x18006f199  cmp     dword ptr [rdi], 0
0x18006f19c  jz      loc_18006F370
0x18006f1a2  lea     r14, [rdx+18h]
0x18006f1a6  test    r14, r14
0x18006f1a9  jnz     short loc_18006F1B5
0x18006f1ab  mov     edx, 8Dh
0x18006f1b0  jmp     loc_18006F375
0x18006f1b5  mov     ebx, 1
0x18006f1ba  cmp     [r14+28h], rbx
0x18006f1be  jnz     loc_18006F345
0x18006f1c4  cmp     esi, 0Ah
0x18006f1c7  jnb     loc_18006F345
0x18006f1cd  mov     ecx, cs:_tls_index
0x18006f1d3  mov     rax, gs:58h
0x18006f1dc  mov     edx, 4
0x18006f1e1  mov     rax, [rax+rcx*8]
0x18006f1e5  mov     eax, [rdx+rax]
0x18006f1e8  cmp     cs:dword_180110D10, eax
0x18006f1ee  jle     loc_18006F2A5
0x18006f1f4  lea     rcx, dword_180110D10
0x18006f1fb  call    _Init_thread_header
0x18006f200  cmp     cs:dword_180110D10, 0FFFFFFFFh
0x18006f207  jnz     loc_18006F2A5
0x18006f20d  lea     rax, aBiometricfacto; "BiometricFactor"
0x18006f214  mov     cs:qword_1801103D0, rax
0x18006f21b  lea     rcx, dword_180110D10
0x18006f222  lea     rax, aManufacturer_0; "Manufacturer"
0x18006f229  mov     cs:qword_1801103D8, rax
0x18006f230  lea     rax, aDescription; "Description"
0x18006f237  mov     cs:qword_1801103E0, rax
0x18006f23e  lea     rax, aOperationalsta; "OperationalState"
0x18006f245  mov     cs:qword_1801103E8, rax
0x18006f24c  lea     rax, aSensoradapter; "SensorAdapter"
0x18006f253  mov     cs:qword_1801103F0, rax
0x18006f25a  lea     rax, aEngineadapter; "EngineAdapter"
0x18006f261  mov     cs:qword_1801103F8, rax
0x18006f268  lea     rax, aStorageadapter_20; "StorageAdapter"
0x18006f26f  mov     cs:qword_180110400, rax
0x18006f276  lea     rax, aIsolationsenso; "IsolationSensorAdapter"
0x18006f27d  mov     cs:qword_180110408, rax
0x18006f284  lea     rax, aIsolationengin; "IsolationEngineAdapter"
0x18006f28b  mov     cs:qword_180110410, rax
0x18006f292  lea     rax, aIsolationstora; "IsolationStorageAdapter"
0x18006f299  mov     cs:qword_180110418, rax
0x18006f2a0  call    _Init_thread_footer
0x18006f2a5  mov     edx, [rbp+0]; unsigned __int64
0x18006f2a8  lea     r8, qword_1801103D0
0x18006f2af  mov     r8, [r8+rsi*8]; unsigned __int16 *
0x18006f2b3  mov     rcx, r12; unsigned __int16 *
0x18006f2b6  mov     r11, rsi
0x18006f2b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f2be  mov     rcx, [r13+8]; hProcess
0x18006f2c2  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x18006f2c7  shl     r11, 4
0x18006f2cb  mov     esi, eax
0x18006f2cd  add     r11, [r14+28h]
0x18006f2d1  xorps   xmm0, xmm0
0x18006f2d4  mov     rdx, r11; lpBaseAddress
0x18006f2d7  shr     esi, 1Fh
0x18006f2da  mov     r9d, 10h; nSize
0x18006f2e0  mov     qword ptr [rsp+88h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18006f2e9  movups  [rsp+88h+Buffer], xmm0
0x18006f2ee  call    cs:__imp_ReadProcessMemory
0x18006f2f4  test    eax, eax
0x18006f2f6  jz      short loc_18006F341
0x18006f2f8  mov     rdx, qword ptr [rsp+88h+Buffer]; lpBaseAddress
0x18006f2fd  test    rdx, rdx
0x18006f300  jz      short loc_18006F341
0x18006f302  mov     ecx, dword ptr [rsp+88h+Buffer+8]
0x18006f306  cmp     ecx, ebx
0x18006f308  jbe     short loc_18006F341
0x18006f30a  mov     eax, [rdi]
0x18006f30c  mov     r8, r15; lpBuffer
0x18006f30f  cmp     ecx, eax
0x18006f311  mov     qword ptr [rsp+88h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18006f31a  cmovb   eax, ecx
0x18006f31d  mov     rcx, [r13+8]; hProcess
0x18006f321  mov     r9d, eax
0x18006f324  add     r9, r9; nSize
0x18006f327  call    cs:__imp_ReadProcessMemory
0x18006f32d  mov     ecx, [rdi]
0x18006f32f  xor     edx, edx
0x18006f331  test    eax, eax
0x18006f333  setz    dl
0x18006f336  sub     ecx, ebx
0x18006f338  xor     eax, eax
0x18006f33a  mov     ebx, edx
0x18006f33c  mov     [r15+rcx*2], ax
0x18006f341  test    esi, esi
0x18006f343  jz      short loc_18006F357
0x18006f345  mov     edx, [rbp+0]; unsigned __int64
0x18006f348  lea     r8, aUnknown; "Unknown"
0x18006f34f  mov     rcx, r12; unsigned __int16 *
0x18006f352  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f357  test    ebx, ebx
0x18006f359  jz      short loc_18006F36C
0x18006f35b  mov     edx, [rdi]; unsigned __int64
0x18006f35d  lea     r8, aUnavailable; "Unavailable"
0x18006f364  mov     rcx, r15; unsigned __int16 *
0x18006f367  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006f36c  xor     eax, eax
0x18006f36e  jmp     short loc_18006F393
0x18006f370  mov     edx, 89h; void *
0x18006f375  mov     rcx, [rsp+88h]; this
0x18006f37d  lea     r8, aOnecoreDsSecur_47; "onecore\\ds\\security\\biometrics\\serv"...
0x18006f384  mov     ebx, 80004005h
0x18006f389  mov     r9d, ebx; char *
0x18006f38c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f391  mov     eax, ebx
0x18006f393  add     rsp, 48h
0x18006f397  pop     r15
0x18006f399  pop     r14
0x18006f39b  pop     r13
0x18006f39d  pop     r12
0x18006f39f  pop     rdi
0x18006f3a0  pop     rsi
0x18006f3a1  pop     rbp
0x18006f3a2  pop     rbx
0x18006f3a3  retn
```
