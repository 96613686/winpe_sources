# CTpUtils::GetRandomNumber(unsigned __int64)

- ea: `0x1800a3604`
- end: `0x1800a3777`
- name: `?GetRandomNumber@CTpUtils@@CA_K_K@Z`
- size: `371`
- prototype: `unsigned __int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a34d0`

## callees

- `0x18003bf14`
- `0x1800a3604`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a36f7`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a36f7`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a36f1`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a36f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a36d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a36d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a36ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a36ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a36b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a36b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a36c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a36c4`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a36e7`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a36e7`
- `CRYPTSP!CryptReleaseContext` at `0x1800a36a1`
- `CRYPTSP!CryptReleaseContext` at `0x1800a36a1`
- `CRYPTSP!CryptGenRandom` at `0x1800a3660`
- `CRYPTSP!CryptGenRandom` at `0x1800a3660`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a3644`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a3644`

## pseudocode

```c
unsigned __int64 __fastcall CTpUtils::GetRandomNumber()
{
  HCRYPTPROV v0; // rcx
  unsigned __int64 result; // rax
  DWORD v2; // ebx
  DWORD v3; // edi
  DWORD v4; // ebx
  DWORD v5; // edi
  unsigned int v6; // eax
  int v7; // eax
  unsigned __int64 v8; // rcx
  double v9; // xmm0_8
  unsigned __int64 pbBuffer; // [rsp+50h] [rbp+20h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF

  phProv = 0;
  pbBuffer = 0;
  SystemTimeAsFileTime = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    v0 = phProv;
    if ( phProv )
    {
      while ( 1 )
      {
        CryptGenRandom(v0, 8u, (BYTE *)&pbBuffer);
        if ( pbBuffer <= 0xFFFFFFFFFB69296BuLL )
          break;
        v0 = phProv;
      }
      pbBuffer += 1 - 100000000 * (pbBuffer / 0x5F5E100);
      CryptReleaseContext(phProv, 0);
    }
  }
  result = pbBuffer;
  if ( !pbBuffer )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime.dwHighDateTime ^ SystemTimeAsFileTime.dwLowDateTime;
    v3 = v2 ^ GetTickCount();
    v4 = v3 ^ GetCurrentProcessId();
    v5 = v4 ^ GetCurrentThreadId();
    v6 = (unsigned int)EncodePointer((PVOID)0xDEADBEEFLL);
    _o_srand(v5 ^ v6);
    v7 = rand();
    v8 = 0;
    v9 = (double)v7 / 32767.0 * 99999999.0 + 1.0;
    if ( v9 >= 9.223372036854776e18 )
    {
      v9 = v9 - 9.223372036854776e18;
      if ( v9 < 9.223372036854776e18 )
        v8 = 0x8000000000000000uLL;
    }
    result = v8 + (unsigned int)(int)v9;
    pbBuffer = result;
    if ( !result )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      result = pbBuffer;
    }
  }
  if ( result > 0x5F5E100 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return pbBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x1800a3604  mov     [rsp-18h+pbBuffer], rcx
0x1800a3609  push    rbp
0x1800a360a  push    rbx
0x1800a360b  push    rdi
0x1800a360c  mov     rbp, rsp
0x1800a360f  sub     rsp, 30h
0x1800a3613  mov     ebx, 1
0x1800a3618  mov     [rbp+phProv], 0
0x1800a3620  mov     r9d, ebx; dwProvType
0x1800a3623  mov     [rbp+pbBuffer], 0
0x1800a362b  xor     r8d, r8d; szProvider
0x1800a362e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800a3636  xor     edx, edx; szContainer
0x1800a3638  mov     [rsp+30h+dwFlags], 0F0000000h; dwFlags
0x1800a3640  lea     rcx, [rbp+phProv]; phProv
0x1800a3644  call    cs:__imp_CryptAcquireContextW
0x1800a364a  test    eax, eax
0x1800a364c  jz      short loc_1800A36A7
0x1800a364e  mov     rcx, [rbp+phProv]; hProv
0x1800a3652  test    rcx, rcx
0x1800a3655  jz      short loc_1800A36A7
0x1800a3657  lea     r8, [rbp+pbBuffer]; pbBuffer
0x1800a365b  mov     edx, 8; dwLen
0x1800a3660  call    cs:__imp_CryptGenRandom
0x1800a3666  mov     rcx, [rbp+pbBuffer]
0x1800a366a  cmp     rcx, 0FFFFFFFFFB69296Bh
0x1800a3671  jbe     short loc_1800A3679
0x1800a3673  mov     rcx, [rbp+phProv]
0x1800a3677  jmp     short loc_1800A3657
0x1800a3679  mov     rax, 0ABCC77118461CEFDh
0x1800a3683  mul     rcx
0x1800a3686  shr     rdx, 1Ah
0x1800a368a  imul    rax, rdx, 5F5E100h
0x1800a3691  xor     edx, edx; dwFlags
0x1800a3693  sub     rbx, rax
0x1800a3696  add     rcx, rbx
0x1800a3699  mov     [rbp+pbBuffer], rcx
0x1800a369d  mov     rcx, [rbp+phProv]; hProv
0x1800a36a1  call    cs:__imp_CryptReleaseContext
0x1800a36a7  mov     rax, [rbp+pbBuffer]
0x1800a36ab  test    rax, rax
0x1800a36ae  jnz     loc_1800A375E
0x1800a36b4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a36b8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a36be  mov     ebx, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a36c1  xor     ebx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800a36c4  call    cs:__imp_GetTickCount
0x1800a36ca  mov     edi, eax
0x1800a36cc  xor     edi, ebx
0x1800a36ce  call    cs:__imp_GetCurrentProcessId
0x1800a36d4  mov     ebx, eax
0x1800a36d6  xor     ebx, edi
0x1800a36d8  call    cs:__imp_GetCurrentThreadId
0x1800a36de  mov     edi, eax
0x1800a36e0  mov     ecx, 0DEADBEEFh; Ptr
0x1800a36e5  xor     edi, ebx
0x1800a36e7  call    cs:__imp_EncodePointer
0x1800a36ed  xor     eax, edi
0x1800a36ef  mov     ecx, eax
0x1800a36f1  call    cs:__imp__o_srand
0x1800a36f7  call    cs:__imp_rand
0x1800a36fd  movsd   xmm1, cs:__real@43e0000000000000
0x1800a3705  xor     ecx, ecx
0x1800a3707  movd    xmm0, eax
0x1800a370b  cvtdq2pd xmm0, xmm0
0x1800a370f  divsd   xmm0, cs:__real@40dfffc000000000
0x1800a3717  mulsd   xmm0, cs:__real@4197d783fc000000
0x1800a371f  addsd   xmm0, cs:__real@3ff0000000000000
0x1800a3727  comisd  xmm0, xmm1
0x1800a372b  jb      short loc_1800A3744
0x1800a372d  subsd   xmm0, xmm1
0x1800a3731  comisd  xmm0, xmm1
0x1800a3735  jnb     short loc_1800A3744
0x1800a3737  mov     rax, 8000000000000000h
0x1800a3741  mov     rcx, rax
0x1800a3744  cvttsd2si rax, xmm0
0x1800a3749  add     rax, rcx
0x1800a374c  mov     [rbp+pbBuffer], rax
0x1800a3750  test    rax, rax
0x1800a3753  jnz     short loc_1800A375E
0x1800a3755  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a375a  mov     rax, [rbp+pbBuffer]
0x1800a375e  cmp     rax, 5F5E100h
0x1800a3764  jbe     short loc_1800A376F
0x1800a3766  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a376b  mov     rax, [rbp+pbBuffer]
0x1800a376f  add     rsp, 30h
0x1800a3773  pop     rdi
0x1800a3774  pop     rbx
0x1800a3775  pop     rbp
0x1800a3776  retn
```
