# AgCxFUSDbDeleteCheck

- ea: `0x1800a9a3c`
- end: `0x1800a9c11`
- name: `AgCxFUSDbDeleteCheck`
- size: `469`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a9c18`

## callees

- `0x18002341c`
- `0x1800236e8`
- `0x18004b9fc`
- `0x180052b7c`
- `0x18005e780`
- `0x1800a9a3c`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x1800a9b2c`
- `ntdll!NtQueryInformationThread` at `0x1800a9b2c`
- `ntdll!RtlNtStatusToDosError` at `0x1800a9b3e`
- `ntdll!RtlNtStatusToDosError` at `0x1800a9b3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a9a8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a9a8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a9ba7`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800a9bd9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800a9bd9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a9a9c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800a9a9c`

## pseudocode

```c
_BOOL8 __fastcall AgCxFUSDbDeleteCheck(__int64 a1, __int64 a2)
{
  BOOL v3; // esi
  int ViewOfFile; // eax
  PUCHAR v5; // rbx
  int v6; // ecx
  _DWORD *v7; // r14
  HANDLE CurrentThread; // rax
  int v9; // eax
  int v10; // r15d
  HANDLE v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rax
  HANDLE v14; // rax
  unsigned int v16; // [rsp+30h] [rbp-40h] BYREF
  int ThreadInformation; // [rsp+34h] [rbp-3Ch] BYREF
  LPVOID lpAddress; // [rsp+38h] [rbp-38h] BYREF
  PUCHAR Buffer[2]; // [rsp+40h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  v16 = 0;
  lpAddress = 0;
  FileTime = 0;
  SystemTime = 0;
  v3 = 0;
  *(_OWORD *)Buffer = 0;
  GetLocalTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  ViewOfFile = PfSvGetViewOfFileEx(a2, 0, Buffer, &v16);
  v5 = Buffer[1];
  if ( ViewOfFile )
    goto LABEL_20;
  v6 = PfsDecompressBuffer(Buffer[1], v16, (__int64)&lpAddress, (__int64)&v16, 0);
  if ( !v6 )
  {
    PfSvUnmapViewOfFile(Buffer);
    v7 = lpAddress;
    *(_OWORD *)Buffer = 0;
    v5 = (PUCHAR)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
LABEL_6:
    CurrentThread = GetCurrentThread();
    ThreadInformation = 0;
    v9 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
    if ( v9 >= 0 )
    {
      v10 = ThreadInformation;
    }
    else
    {
      v10 = 8;
      RtlNtStatusToDosError(v9);
    }
    v11 = GetCurrentThread();
    PfSetPagePriorityThread(v11);
    if ( (unsigned int)PfScFileVerify(v7, v16)
      || ((v12 = v7[32], v12 < 0xC) ? (v13 = v12 - 1) : (v13 = 11),
          *(_QWORD *)&FileTime - *(_QWORD *)&v7[2 * v13 + 34] > 0x185C22CE4000uLL) )
    {
      v3 = 1;
    }
    if ( v10 != 8 )
    {
      v14 = GetCurrentThread();
      PfSetPagePriorityThread(v14);
    }
    goto LABEL_18;
  }
  if ( v6 == 605 )
  {
    v7 = v5;
    goto LABEL_6;
  }
  v3 = v6 == 11;
LABEL_18:
  if ( lpAddress )
    VirtualFree(lpAddress, 0, 0x8000u);
LABEL_20:
  if ( v5 )
    PfSvUnmapViewOfFile(Buffer);
  return v3;
}

```

## disassembly

```asm
0x1800a9a3c  mov     [rsp-18h+arg_0], rbx
0x1800a9a41  mov     [rsp-18h+arg_10], rsi
0x1800a9a46  push    rbp
0x1800a9a47  push    r14
0x1800a9a49  push    r15
0x1800a9a4b  mov     rbp, rsp
0x1800a9a4e  sub     rsp, 70h
0x1800a9a52  mov     rax, cs:__security_cookie
0x1800a9a59  xor     rax, rsp
0x1800a9a5c  mov     [rbp+var_8], rax
0x1800a9a60  xorps   xmm0, xmm0
0x1800a9a63  mov     [rbp+var_40], 0
0x1800a9a6a  xorps   xmm1, xmm1
0x1800a9a6d  mov     [rbp+lpAddress], 0
0x1800a9a75  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800a9a79  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800a9a81  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800a9a85  mov     rbx, rdx
0x1800a9a88  xor     esi, esi
0x1800a9a8a  movups  xmmword ptr [rbp+Buffer], xmm1
0x1800a9a8e  call    cs:__imp_GetLocalTime
0x1800a9a94  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800a9a98  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800a9a9c  call    cs:__imp_SystemTimeToFileTime
0x1800a9aa2  lea     r9, [rbp+var_40]
0x1800a9aa6  xor     edx, edx
0x1800a9aa8  lea     r8, [rbp+Buffer]
0x1800a9aac  mov     rcx, rbx
0x1800a9aaf  call    PfSvGetViewOfFileEx
0x1800a9ab4  mov     rbx, [rbp+Buffer+8]
0x1800a9ab8  test    eax, eax
0x1800a9aba  jnz     loc_1800A9BDF
0x1800a9ac0  mov     edx, [rbp+var_40]
0x1800a9ac3  lea     r9, [rbp+var_40]
0x1800a9ac7  lea     r8, [rbp+lpAddress]
0x1800a9acb  mov     [rsp+70h+ReturnLength], rsi; __int64
0x1800a9ad0  mov     rcx, rbx; Buffer
0x1800a9ad3  call    PfsDecompressBuffer
0x1800a9ad8  mov     ecx, eax
0x1800a9ada  test    eax, eax
0x1800a9adc  jnz     short loc_1800A9AFE
0x1800a9ade  lea     rcx, [rbp+Buffer]
0x1800a9ae2  call    PfSvUnmapViewOfFile
0x1800a9ae7  mov     r14, [rbp+lpAddress]
0x1800a9aeb  xorps   xmm0, xmm0
0x1800a9aee  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800a9af2  psrldq  xmm0, 8
0x1800a9af7  movq    rbx, xmm0
0x1800a9afc  jmp     short loc_1800A9B0D
0x1800a9afe  cmp     ecx, 25Dh
0x1800a9b04  jnz     loc_1800A9BBA
0x1800a9b0a  mov     r14, rbx
0x1800a9b0d  call    cs:__imp_GetCurrentThread
0x1800a9b13  mov     r9d, 4; ThreadInformationLength
0x1800a9b19  mov     [rbp+ThreadInformation], esi
0x1800a9b1c  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800a9b20  mov     [rsp+70h+ReturnLength], rsi; ReturnLength
0x1800a9b25  mov     rcx, rax; ThreadHandle
0x1800a9b28  lea     edx, [r9+14h]; ThreadInformationClass
0x1800a9b2c  call    cs:__imp_NtQueryInformationThread
0x1800a9b32  test    eax, eax
0x1800a9b34  jns     short loc_1800A9B46
0x1800a9b36  mov     ecx, eax; Status
0x1800a9b38  mov     r15d, 8
0x1800a9b3e  call    cs:__imp_RtlNtStatusToDosError
0x1800a9b44  jmp     short loc_1800A9B4A
0x1800a9b46  mov     r15d, [rbp+ThreadInformation]
0x1800a9b4a  call    cs:__imp_GetCurrentThread
0x1800a9b50  mov     rcx, rax; ThreadHandle
0x1800a9b53  mov     edx, 1
0x1800a9b58  call    PfSetPagePriorityThread
0x1800a9b5d  mov     edx, [rbp+var_40]
0x1800a9b60  mov     rcx, r14
0x1800a9b63  call    PfScFileVerify
0x1800a9b68  test    eax, eax
0x1800a9b6a  jnz     short loc_1800A9B9C
0x1800a9b6c  mov     eax, [r14+80h]
0x1800a9b73  cmp     eax, 0Ch
0x1800a9b76  jb      short loc_1800A9B7F
0x1800a9b78  mov     eax, 0Bh
0x1800a9b7d  jmp     short loc_1800A9B81
0x1800a9b7f  dec     eax
0x1800a9b81  mov     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x1800a9b85  sub     rcx, [r14+rax*8+88h]
0x1800a9b8d  mov     rax, 185C22CE4000h
0x1800a9b97  cmp     rcx, rax
0x1800a9b9a  jbe     short loc_1800A9BA1
0x1800a9b9c  mov     esi, 1
0x1800a9ba1  cmp     r15d, 8
0x1800a9ba5  jz      short loc_1800A9BC6
0x1800a9ba7  call    cs:__imp_GetCurrentThread
0x1800a9bad  mov     rcx, rax; ThreadHandle
0x1800a9bb0  mov     edx, r15d
0x1800a9bb3  call    PfSetPagePriorityThread
0x1800a9bb8  jmp     short loc_1800A9BC6
0x1800a9bba  mov     eax, 0Bh
0x1800a9bbf  cmp     ecx, eax
0x1800a9bc1  jnz     short loc_1800A9BC6
0x1800a9bc3  lea     esi, [rax-0Ah]
0x1800a9bc6  cmp     [rbp+lpAddress], 0
0x1800a9bcb  jz      short loc_1800A9BDF
0x1800a9bcd  mov     rcx, [rbp+lpAddress]; lpAddress
0x1800a9bd1  xor     edx, edx; dwSize
0x1800a9bd3  mov     r8d, 8000h; dwFreeType
0x1800a9bd9  call    cs:__imp_VirtualFree
0x1800a9bdf  test    rbx, rbx
0x1800a9be2  jz      short loc_1800A9BED
0x1800a9be4  lea     rcx, [rbp+Buffer]
0x1800a9be8  call    PfSvUnmapViewOfFile
0x1800a9bed  mov     eax, esi
0x1800a9bef  mov     rcx, [rbp+var_8]
0x1800a9bf3  xor     rcx, rsp; StackCookie
0x1800a9bf6  call    __security_check_cookie
0x1800a9bfb  lea     r11, [rsp+70h+var_s0]
0x1800a9c00  mov     rbx, [r11+20h]
0x1800a9c04  mov     rsi, [r11+30h]
0x1800a9c08  mov     rsp, r11
0x1800a9c0b  pop     r15
0x1800a9c0d  pop     r14
0x1800a9c0f  pop     rbp
0x1800a9c10  retn
```
