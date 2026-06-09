# MmsCreate

- ea: `0x1800a1ba8`
- end: `0x1800a1cd4`
- name: `MmsCreate`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180083840`

## callees

- `0x180053d3c`
- `0x1800a16e4`
- `0x1800a1ba8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a1c04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800a1c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1c8d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a1c78`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a1c78`

## pseudocode

```c
signed int __fastcall MmsCreate(__int64 a1)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  signed int result; // eax
  char v7; // al
  unsigned int v8; // r9d
  char v9; // al
  HANDLE FileMappingW; // rax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]
  __int128 v13; // [rsp+70h] [rbp-10h]

  memset_0(&SystemInfo, 0, 0x50u);
  v2 = *(_OWORD *)&SystemInfo.lpMaximumApplicationAddress;
  *(_OWORD *)a1 = *(_OWORD *)&SystemInfo.dwOemId;
  v3 = *(_OWORD *)&SystemInfo.dwNumberOfProcessors;
  *(_OWORD *)(a1 + 16) = v2;
  v4 = v12;
  *(_OWORD *)(a1 + 32) = v3;
  v5 = v13;
  *(_OWORD *)(a1 + 48) = v4;
  *(_OWORD *)(a1 + 64) = v5;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( ((SystemInfo.dwAllocationGranularity - 1) & 0x4000000) != 0 )
    return -2147023764;
  v7 = MmspCalculateIntegerShift(SystemInfo.dwPageSize);
  *(_BYTE *)(a1 + 72) = v7;
  if ( !v7 )
    return -2147023434;
  v9 = MmspCalculateIntegerShift(v8);
  *(_BYTE *)(a1 + 73) = v9;
  if ( !v9 )
    return -2147023434;
  *(_DWORD *)(a1 + 44) = 2;
  *(_DWORD *)(a1 + 40) = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 2u, 0, 0);
  *(_QWORD *)(a1 + 8) = FileMappingW;
  if ( FileMappingW )
  {
    *(_QWORD *)(a1 + 16) = 0x4000000;
    *(_QWORD *)a1 = &off_1800B4900;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800a1ba8  mov     [rsp-8+arg_0], rbx
0x1800a1bad  push    rbp
0x1800a1bae  mov     rbp, rsp
0x1800a1bb1  sub     rsp, 80h
0x1800a1bb8  xor     edx, edx; Val
0x1800a1bba  mov     rbx, rcx
0x1800a1bbd  lea     rcx, [rbp+SystemInfo]; void *
0x1800a1bc1  lea     r8d, [rdx+50h]; Size
0x1800a1bc5  call    memset_0
0x1800a1bca  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x1800a1bce  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800a1bd2  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x1800a1bd6  movaps  xmmword ptr [rbx], xmm0
0x1800a1bd9  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x1800a1bdd  movaps  xmmword ptr [rbx+10h], xmm1
0x1800a1be1  movups  xmm1, [rbp+var_20]
0x1800a1be5  movaps  xmmword ptr [rbx+20h], xmm0
0x1800a1be9  movups  xmm0, [rbp+var_10]
0x1800a1bed  movaps  xmmword ptr [rbx+30h], xmm1
0x1800a1bf1  xorps   xmm1, xmm1
0x1800a1bf4  movaps  xmmword ptr [rbx+40h], xmm0
0x1800a1bf8  movups  xmmword ptr [rbp+SystemInfo], xmm1
0x1800a1bfc  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm1
0x1800a1c00  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm1
0x1800a1c04  call    cs:__imp_GetSystemInfo
0x1800a1c0b  nop     dword ptr [rax+rax+00h]
0x1800a1c10  mov     r9d, [rbp+SystemInfo.dwAllocationGranularity]
0x1800a1c14  lea     eax, [r9-1]
0x1800a1c18  bt      eax, 1Ah
0x1800a1c1c  jnb     short loc_1800A1C28
0x1800a1c1e  mov     eax, 8007046Ch
0x1800a1c23  jmp     loc_1800A1CC2
0x1800a1c28  mov     ecx, [rbp+SystemInfo.dwPageSize]
0x1800a1c2b  call    MmspCalculateIntegerShift
0x1800a1c30  mov     [rbx+48h], al
0x1800a1c33  test    al, al
0x1800a1c35  jz      loc_1800A1CBD
0x1800a1c3b  mov     ecx, r9d
0x1800a1c3e  call    MmspCalculateIntegerShift
0x1800a1c43  mov     [rbx+49h], al
0x1800a1c46  test    al, al
0x1800a1c48  jz      short loc_1800A1CBD
0x1800a1c4a  mov     r9d, 2; dwMaximumSizeHigh
0x1800a1c50  mov     [rsp+80h+lpName], 0; lpName
0x1800a1c59  xor     edx, edx; lpFileMappingAttributes
0x1800a1c5b  mov     [rbx+2Ch], r9d
0x1800a1c5f  mov     r8d, 4000004h; flProtect
0x1800a1c65  mov     dword ptr [rbx+28h], 0
0x1800a1c6c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800a1c70  mov     [rsp+80h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x1800a1c78  call    cs:__imp_CreateFileMappingW
0x1800a1c7f  nop     dword ptr [rax+rax+00h]
0x1800a1c84  mov     [rbx+8], rax
0x1800a1c88  test    rax, rax
0x1800a1c8b  jnz     short loc_1800A1CA7
0x1800a1c8d  call    cs:__imp_GetLastError
0x1800a1c94  nop     dword ptr [rax+rax+00h]
0x1800a1c99  test    eax, eax
0x1800a1c9b  jle     short loc_1800A1CC2
0x1800a1c9d  movzx   eax, ax
0x1800a1ca0  or      eax, 80070000h
0x1800a1ca5  jmp     short loc_1800A1CC2
0x1800a1ca7  lea     rax, off_1800B4900
0x1800a1cae  mov     qword ptr [rbx+10h], 4000000h
0x1800a1cb6  mov     [rbx], rax
0x1800a1cb9  xor     eax, eax
0x1800a1cbb  jmp     short loc_1800A1CC2
0x1800a1cbd  mov     eax, 800705B6h
0x1800a1cc2  mov     rbx, [rsp+80h+arg_0]
0x1800a1cca  add     rsp, 80h
0x1800a1cd1  pop     rbp
0x1800a1cd2  retn
```
