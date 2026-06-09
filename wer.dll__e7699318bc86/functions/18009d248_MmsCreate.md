# MmsCreate

- ea: `0x18009d248`
- end: `0x18009d35d`
- name: `MmsCreate`
- size: `277`
- prototype: `signed int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18007fda8`

## callees

- `0x1800517cc`
- `0x18009cd88`
- `0x18009d248`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009d2a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009d2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d31d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009d30e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009d30e`

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
    *(_QWORD *)a1 = &off_1800AF900;
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
0x18009d248  mov     [rsp-8+arg_0], rbx
0x18009d24d  push    rbp
0x18009d24e  mov     rbp, rsp
0x18009d251  sub     rsp, 80h
0x18009d258  xor     edx, edx; Val
0x18009d25a  mov     rbx, rcx
0x18009d25d  lea     rcx, [rbp+SystemInfo]; void *
0x18009d261  lea     r8d, [rdx+50h]; Size
0x18009d265  call    memset_0
0x18009d26a  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x18009d26e  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18009d272  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x18009d276  movaps  xmmword ptr [rbx], xmm0
0x18009d279  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x18009d27d  movaps  xmmword ptr [rbx+10h], xmm1
0x18009d281  movups  xmm1, [rbp+var_20]
0x18009d285  movaps  xmmword ptr [rbx+20h], xmm0
0x18009d289  movups  xmm0, [rbp+var_10]
0x18009d28d  movaps  xmmword ptr [rbx+30h], xmm1
0x18009d291  xorps   xmm1, xmm1
0x18009d294  movaps  xmmword ptr [rbx+40h], xmm0
0x18009d298  movups  xmmword ptr [rbp+SystemInfo], xmm1
0x18009d29c  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18009d2a0  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm1
0x18009d2a4  call    cs:__imp_GetSystemInfo
0x18009d2aa  mov     r9d, [rbp+SystemInfo.dwAllocationGranularity]
0x18009d2ae  lea     eax, [r9-1]
0x18009d2b2  bt      eax, 1Ah
0x18009d2b6  jnb     short loc_18009D2C2
0x18009d2b8  mov     eax, 8007046Ch
0x18009d2bd  jmp     loc_18009D34C
0x18009d2c2  mov     ecx, [rbp+SystemInfo.dwPageSize]
0x18009d2c5  call    MmspCalculateIntegerShift
0x18009d2ca  mov     [rbx+48h], al
0x18009d2cd  test    al, al
0x18009d2cf  jz      short loc_18009D347
0x18009d2d1  mov     ecx, r9d
0x18009d2d4  call    MmspCalculateIntegerShift
0x18009d2d9  mov     [rbx+49h], al
0x18009d2dc  test    al, al
0x18009d2de  jz      short loc_18009D347
0x18009d2e0  mov     r9d, 2; dwMaximumSizeHigh
0x18009d2e6  mov     [rsp+80h+lpName], 0; lpName
0x18009d2ef  xor     edx, edx; lpFileMappingAttributes
0x18009d2f1  mov     [rbx+2Ch], r9d
0x18009d2f5  mov     r8d, 4000004h; flProtect
0x18009d2fb  mov     dword ptr [rbx+28h], 0
0x18009d302  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18009d306  mov     [rsp+80h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18009d30e  call    cs:__imp_CreateFileMappingW
0x18009d314  mov     [rbx+8], rax
0x18009d318  test    rax, rax
0x18009d31b  jnz     short loc_18009D331
0x18009d31d  call    cs:__imp_GetLastError
0x18009d323  test    eax, eax
0x18009d325  jle     short loc_18009D34C
0x18009d327  movzx   eax, ax
0x18009d32a  or      eax, 80070000h
0x18009d32f  jmp     short loc_18009D34C
0x18009d331  lea     rax, off_1800AF900
0x18009d338  mov     qword ptr [rbx+10h], 4000000h
0x18009d340  mov     [rbx], rax
0x18009d343  xor     eax, eax
0x18009d345  jmp     short loc_18009D34C
0x18009d347  mov     eax, 800705B6h
0x18009d34c  mov     rbx, [rsp+80h+arg_0]
0x18009d354  add     rsp, 80h
0x18009d35b  pop     rbp
0x18009d35c  retn
```
