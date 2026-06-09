# InitializeThreadPoolConfigWithDefaults(THREAD_POOL_CONFIG *)

- ea: `0x180003950`
- end: `0x180003a6c`
- name: `?InitializeThreadPoolConfigWithDefaults@@YAJPEAUTHREAD_POOL_CONFIG@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct THREAD_POOL_CONFIG *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003d80`

## callees

- `0x180003950`
- `0x1800041a6`
- `0x1800041d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800039a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800039a4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1800039d8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1800039d8`
- `iisutil!IISGetPlatformType` at `0x180003983`
- `iisutil!IISGetPlatformType` at `0x180003983`

## pseudocode

```c
__int64 __fastcall InitializeThreadPoolConfigWithDefaults(struct THREAD_POOL_CONFIG *a1)
{
  int v2; // ebx
  DWORD dwNumberOfProcessors; // ecx
  unsigned int v4; // eax
  __int64 result; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-19h] BYREF
  _MEMORYSTATUS Buffer; // [rsp+50h] [rbp+17h] BYREF

  memset_0(a1, 0, 0x54u);
  v2 = IISGetPlatformType();
  g_PlatformType = v2;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  g_dwNumProcs = SystemInfo.dwNumberOfProcessors;
  if ( v2 != 2 )
    goto LABEL_7;
  memset(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 56;
  GlobalMemoryStatus(&Buffer);
  v4 = (Buffer.dwTotalPhys >> 19) + 2;
  *((_DWORD *)a1 + 1) = v4;
  if ( v4 < 0x40 )
  {
    dwNumberOfProcessors = g_dwNumProcs;
LABEL_7:
    *((_DWORD *)a1 + 1) = 64;
    goto LABEL_8;
  }
  if ( v4 > 0x100 )
    *((_DWORD *)a1 + 1) = 256;
  dwNumberOfProcessors = g_dwNumProcs;
LABEL_8:
  *(_QWORD *)((char *)a1 + 20) = 95;
  *(_QWORD *)((char *)a1 + 12) = 1800000;
  *((_DWORD *)a1 + 2) = 20 * dwNumberOfProcessors;
  *((_DWORD *)a1 + 7) = 10000;
  *((_QWORD *)a1 + 4) = 1000;
  *((_QWORD *)a1 + 5) = 0;
  if ( dwNumberOfProcessors < 4 )
    dwNumberOfProcessors = 4;
  result = 0;
  *(_DWORD *)a1 = dwNumberOfProcessors;
  return result;
}

```

## disassembly

```asm
0x180003950  mov     [rsp-8+arg_8], rbx
0x180003955  mov     [rsp-8+arg_10], rdi
0x18000395a  push    rbp
0x18000395b  lea     rbp, [rsp-57h]
0x180003960  sub     rsp, 90h
0x180003967  mov     rax, cs:__security_cookie
0x18000396e  xor     rax, rsp
0x180003971  mov     [rbp+57h+var_8], rax
0x180003975  xor     edx, edx; Val
0x180003977  mov     rdi, rcx
0x18000397a  lea     r8d, [rdx+54h]; Size
0x18000397e  call    memset_0
0x180003983  call    cs:__imp_IISGetPlatformType
0x180003989  xorps   xmm0, xmm0
0x18000398c  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180003990  mov     ebx, eax
0x180003992  mov     cs:g_PlatformType, eax
0x180003998  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18000399c  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800039a0  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800039a4  call    cs:__imp_GetSystemInfo
0x1800039aa  mov     ecx, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x1800039ad  mov     cs:?g_dwNumProcs@@3KA, ecx; ulong g_dwNumProcs
0x1800039b3  cmp     ebx, 2
0x1800039b6  jnz     short loc_180003A0A
0x1800039b8  xorps   xmm0, xmm0
0x1800039bb  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800039bf  xor     eax, eax
0x1800039c1  movups  xmmword ptr [rbp+57h+Buffer.dwLength], xmm0
0x1800039c5  mov     [rbp+57h+Buffer.dwLength], 38h ; '8'
0x1800039cc  movups  xmmword ptr [rbp+57h+Buffer.dwAvailPhys], xmm0
0x1800039d0  mov     [rbp+57h+Buffer.dwAvailVirtual], rax
0x1800039d4  movups  xmmword ptr [rbp+57h+Buffer.dwAvailPageFile], xmm0
0x1800039d8  call    cs:__imp_GlobalMemoryStatus
0x1800039de  mov     rax, [rbp+57h+Buffer.dwTotalPhys]
0x1800039e2  shr     rax, 13h
0x1800039e6  add     eax, ebx
0x1800039e8  mov     [rdi+4], eax
0x1800039eb  cmp     eax, 40h ; '@'
0x1800039ee  jb      short loc_180003A04
0x1800039f0  mov     ecx, 100h
0x1800039f5  cmp     eax, ecx
0x1800039f7  jbe     short loc_1800039FC
0x1800039f9  mov     [rdi+4], ecx
0x1800039fc  mov     ecx, cs:?g_dwNumProcs@@3KA; ulong g_dwNumProcs
0x180003a02  jmp     short loc_180003A11
0x180003a04  mov     ecx, cs:?g_dwNumProcs@@3KA; ulong g_dwNumProcs
0x180003a0a  mov     dword ptr [rdi+4], 40h ; '@'
0x180003a11  xor     edx, edx
0x180003a13  mov     qword ptr [rdi+14h], 5Fh ; '_'
0x180003a1b  lea     eax, [rcx+rcx*4]
0x180003a1e  mov     qword ptr [rdi+0Ch], 1B7740h
0x180003a26  shl     eax, 2
0x180003a29  mov     [rdi+8], eax
0x180003a2c  lea     eax, [rdx+4]
0x180003a2f  mov     dword ptr [rdi+1Ch], 2710h
0x180003a36  cmp     ecx, eax
0x180003a38  mov     qword ptr [rdi+20h], 3E8h
0x180003a40  mov     [rdi+28h], rdx
0x180003a44  cmovb   ecx, eax
0x180003a47  xor     eax, eax
0x180003a49  mov     [rdi], ecx
0x180003a4b  mov     rcx, [rbp+57h+var_8]
0x180003a4f  xor     rcx, rsp; StackCookie
0x180003a52  call    __security_check_cookie
0x180003a57  lea     r11, [rsp+90h+var_s0]
0x180003a5f  mov     rbx, [r11+18h]
0x180003a63  mov     rdi, [r11+20h]
0x180003a67  mov     rsp, r11
0x180003a6a  pop     rbp
0x180003a6b  retn
```
