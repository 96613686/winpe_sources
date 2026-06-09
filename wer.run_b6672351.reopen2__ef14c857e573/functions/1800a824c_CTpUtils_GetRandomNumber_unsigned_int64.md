# CTpUtils::GetRandomNumber(unsigned __int64)

- ea: `0x1800a824c`
- end: `0x1800a83fc`
- name: `?GetRandomNumber@CTpUtils@@CA_K_K@Z`
- size: `432`
- prototype: `unsigned __int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a8108`

## callees

- `0x18003de9c`
- `0x1800a824c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a8375`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800a8375`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a8369`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800a8369`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8334`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8334`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a8312`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a8312`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a8324`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a8324`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a8359`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800a8359`
- `CRYPTSP!CryptReleaseContext` at `0x1800a82f5`
- `CRYPTSP!CryptReleaseContext` at `0x1800a82f5`
- `CRYPTSP!CryptGenRandom` at `0x1800a82ae`
- `CRYPTSP!CryptGenRandom` at `0x1800a82ae`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a828c`
- `CRYPTSP!CryptAcquireContextW` at `0x1800a828c`

## pseudocode

```c
HCRYPTPROV __fastcall CTpUtils::GetRandomNumber()
{
  __int64 v0; // rdx
  HCRYPTPROV v1; // rcx
  __int64 v2; // r8
  HCRYPTPROV result; // rax
  DWORD v4; // ebx
  DWORD v5; // edi
  DWORD v6; // ebx
  DWORD v7; // edi
  unsigned int v8; // eax
  int v9; // eax
  double v10; // xmm0_8
  unsigned __int64 pbBuffer; // [rsp+50h] [rbp+20h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp+28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+30h] BYREF

  phProv = 0;
  pbBuffer = 0;
  SystemTimeAsFileTime = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    v1 = phProv;
    if ( phProv )
    {
      while ( 1 )
      {
        CryptGenRandom(v1, 8u, (BYTE *)&pbBuffer);
        if ( pbBuffer <= 0xFFFFFFFFFB69296BuLL )
          break;
        v1 = phProv;
      }
      pbBuffer += 1 - 100000000 * (pbBuffer / 0x5F5E100);
      CryptReleaseContext(phProv, 0);
    }
  }
  result = pbBuffer;
  if ( !pbBuffer )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = SystemTimeAsFileTime.dwHighDateTime ^ SystemTimeAsFileTime.dwLowDateTime;
    v5 = v4 ^ GetTickCount();
    v6 = v5 ^ GetCurrentProcessId();
    v7 = v6 ^ GetCurrentThreadId();
    v8 = (unsigned int)EncodePointer((PVOID)0xDEADBEEFLL);
    _o_srand(v7 ^ v8);
    v9 = rand();
    v1 = 0;
    v10 = (double)v9 / 32767.0 * 99999999.0 + 1.0;
    if ( v10 >= 9.223372036854776e18 )
    {
      v10 = v10 - 9.223372036854776e18;
      if ( v10 < 9.223372036854776e18 )
        v1 = 0x8000000000000000uLL;
    }
    result = v1 + (unsigned int)(int)v10;
    pbBuffer = result;
    if ( !result )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v1, v0, v2);
      result = pbBuffer;
    }
  }
  if ( result > 0x5F5E100 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v1, v0, v2);
    return pbBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x1800a824c  mov     [rsp-18h+pbBuffer], rcx
0x1800a8251  push    rbp
0x1800a8252  push    rbx
0x1800a8253  push    rdi
0x1800a8254  mov     rbp, rsp
0x1800a8257  sub     rsp, 30h
0x1800a825b  mov     ebx, 1
0x1800a8260  mov     [rbp+phProv], 0
0x1800a8268  mov     r9d, ebx; dwProvType
0x1800a826b  mov     [rbp+pbBuffer], 0
0x1800a8273  xor     r8d, r8d; szProvider
0x1800a8276  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800a827e  xor     edx, edx; szContainer
0x1800a8280  mov     [rsp+30h+dwFlags], 0F0000000h; dwFlags
0x1800a8288  lea     rcx, [rbp+phProv]; phProv
0x1800a828c  call    cs:__imp_CryptAcquireContextW
0x1800a8293  nop     dword ptr [rax+rax+00h]
0x1800a8298  test    eax, eax
0x1800a829a  jz      short loc_1800A8301
0x1800a829c  mov     rcx, [rbp+phProv]; hProv
0x1800a82a0  test    rcx, rcx
0x1800a82a3  jz      short loc_1800A8301
0x1800a82a5  lea     r8, [rbp+pbBuffer]; pbBuffer
0x1800a82a9  mov     edx, 8; dwLen
0x1800a82ae  call    cs:__imp_CryptGenRandom
0x1800a82b5  nop     dword ptr [rax+rax+00h]
0x1800a82ba  mov     rcx, [rbp+pbBuffer]
0x1800a82be  cmp     rcx, 0FFFFFFFFFB69296Bh
0x1800a82c5  jbe     short loc_1800A82CD
0x1800a82c7  mov     rcx, [rbp+phProv]
0x1800a82cb  jmp     short loc_1800A82A5
0x1800a82cd  mov     rax, 0ABCC77118461CEFDh
0x1800a82d7  mul     rcx
0x1800a82da  shr     rdx, 1Ah
0x1800a82de  imul    rax, rdx, 5F5E100h
0x1800a82e5  xor     edx, edx; dwFlags
0x1800a82e7  sub     rbx, rax
0x1800a82ea  add     rcx, rbx
0x1800a82ed  mov     [rbp+pbBuffer], rcx
0x1800a82f1  mov     rcx, [rbp+phProv]; hProv
0x1800a82f5  call    cs:__imp_CryptReleaseContext
0x1800a82fc  nop     dword ptr [rax+rax+00h]
0x1800a8301  mov     rax, [rbp+pbBuffer]
0x1800a8305  test    rax, rax
0x1800a8308  jnz     loc_1800A83E2
0x1800a830e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a8312  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a8319  nop     dword ptr [rax+rax+00h]
0x1800a831e  mov     ebx, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a8321  xor     ebx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800a8324  call    cs:__imp_GetTickCount
0x1800a832b  nop     dword ptr [rax+rax+00h]
0x1800a8330  mov     edi, eax
0x1800a8332  xor     edi, ebx
0x1800a8334  call    cs:__imp_GetCurrentProcessId
0x1800a833b  nop     dword ptr [rax+rax+00h]
0x1800a8340  mov     ebx, eax
0x1800a8342  xor     ebx, edi
0x1800a8344  call    cs:__imp_GetCurrentThreadId
0x1800a834b  nop     dword ptr [rax+rax+00h]
0x1800a8350  mov     edi, eax
0x1800a8352  mov     ecx, 0DEADBEEFh; Ptr
0x1800a8357  xor     edi, ebx
0x1800a8359  call    cs:__imp_EncodePointer
0x1800a8360  nop     dword ptr [rax+rax+00h]
0x1800a8365  xor     eax, edi
0x1800a8367  mov     ecx, eax
0x1800a8369  call    cs:__imp__o_srand
0x1800a8370  nop     dword ptr [rax+rax+00h]
0x1800a8375  call    cs:__imp_rand
0x1800a837c  nop     dword ptr [rax+rax+00h]
0x1800a8381  movsd   xmm1, cs:__real@43e0000000000000
0x1800a8389  xor     ecx, ecx
0x1800a838b  movd    xmm0, eax
0x1800a838f  cvtdq2pd xmm0, xmm0
0x1800a8393  divsd   xmm0, cs:__real@40dfffc000000000
0x1800a839b  mulsd   xmm0, cs:__real@4197d783fc000000
0x1800a83a3  addsd   xmm0, cs:__real@3ff0000000000000
0x1800a83ab  comisd  xmm0, xmm1
0x1800a83af  jb      short loc_1800A83C8
0x1800a83b1  subsd   xmm0, xmm1
0x1800a83b5  comisd  xmm0, xmm1
0x1800a83b9  jnb     short loc_1800A83C8
0x1800a83bb  mov     rax, 8000000000000000h
0x1800a83c5  mov     rcx, rax
0x1800a83c8  cvttsd2si rax, xmm0
0x1800a83cd  add     rax, rcx
0x1800a83d0  mov     [rbp+pbBuffer], rax
0x1800a83d4  test    rax, rax
0x1800a83d7  jnz     short loc_1800A83E2
0x1800a83d9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a83de  mov     rax, [rbp+pbBuffer]
0x1800a83e2  cmp     rax, 5F5E100h
0x1800a83e8  jbe     short loc_1800A83F3
0x1800a83ea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a83ef  mov     rax, [rbp+pbBuffer]
0x1800a83f3  add     rsp, 30h
0x1800a83f7  pop     rdi
0x1800a83f8  pop     rbx
0x1800a83f9  pop     rbp
0x1800a83fa  retn
```
