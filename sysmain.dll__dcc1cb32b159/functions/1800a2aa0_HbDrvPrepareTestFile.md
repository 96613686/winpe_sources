# HbDrvPrepareTestFile

- ea: `0x1800a2aa0`
- end: `0x1800a2dc1`
- name: `HbDrvPrepareTestFile`
- size: `801`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, HANDLE hFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800a5b88`

## callees

- `0x1800a0dec`
- `0x1800a1580`
- `0x1800a2aa0`
- `0x1800a4f80`
- `0x1800a5738`
- `0x1800a62bc`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a2b9e`
- `ntdll!RtlNtStatusToDosError` at `0x1800a2b9e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2c12`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2cac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2c12`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a2cac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2c28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2da1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2c28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2d82`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2da1`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a2b92`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a2bc9`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a2b92`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuCacheHitsControl` at `0x1800a2bc9`

## pseudocode

```c
__int64 __fastcall HbDrvPrepareTestFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        HANDLE hFile)
{
  __int64 v10; // rcx
  ULONG HybridDiskInfo; // ebx
  int v12; // r14d
  void *v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r8
  NTSTATUS v16; // eax
  int v17; // r14d
  __int64 v18; // r12
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r13
  __int64 v21; // rcx
  int i; // ebx
  unsigned int v24; // [rsp+44h] [rbp-1Ch] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  LPVOID v27; // [rsp+58h] [rbp-8h]
  unsigned int v28; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v29; // [rsp+B8h] [rbp+58h]

  v29 = a4;
  v24 = 0;
  v26 = 0;
  v10 = *(_QWORD *)(a1 + 32);
  v28 = 0;
  lpMem = 0;
  v27 = 0;
  HybridDiskInfo = HbDrvGetHybridDiskInfo(
                     v10,
                     (unsigned int)&lpMem,
                     (unsigned int)&v26,
                     0,
                     (__int64)&v24,
                     (__int64)&v28);
  if ( HybridDiskInfo )
    goto LABEL_32;
  if ( v28 )
  {
    HybridDiskInfo = 0;
LABEL_32:
    v13 = lpMem;
    goto LABEL_33;
  }
  v12 = a5;
  if ( !a5 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))a1)(*(_QWORD *)(a1 + 16)) )
    {
      HybridDiskInfo = HbDrvFindBitmapSetRunsWithMetadata((int)a3 + 24, 0);
      if ( !HybridDiskInfo )
        HybridDiskInfo = 0;
      if ( v27 )
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v27);
    }
    else
    {
      HybridDiskInfo = 995;
    }
    goto LABEL_32;
  }
  v13 = lpMem;
  if ( a5 >= *((unsigned __int8 *)lpMem + 44) )
  {
    HybridDiskInfo = 50;
    goto LABEL_33;
  }
  v14 = *(_QWORD *)(a1 + 32);
  v27 = (LPVOID)(3LL * a5);
  v28 = *((_DWORD *)lpMem + 6 * a5 + 19);
  v15 = *(_QWORD *)(v14 + 16);
  v24 = *((_DWORD *)lpMem + 6);
  if ( a5 >= 5 )
    v12 = 5;
  HybridDiskInfo = HbDrvSetBitmap(a1, a2, v15, a3 + 24, v12, 1);
  if ( !HybridDiskInfo )
  {
    v16 = SmuCacheHitsControl(a2, 0);
    if ( v16 < 0 )
      goto LABEL_11;
    HybridDiskInfo = HbDrvSpeedTestCreateTestFile(0, (LARGE_INTEGER)a4, hFile);
    if ( HybridDiskInfo )
      goto LABEL_33;
    v16 = SmuCacheHitsControl(a2, 1);
    if ( v16 < 0 )
    {
LABEL_11:
      HybridDiskInfo = RtlNtStatusToDosError(v16);
      goto LABEL_33;
    }
    v17 = 120;
    v18 = v29;
    v19 = v26 * (unsigned __int64)v28 % v24;
    v20 = v26 * (unsigned __int64)v28 / v24;
    while ( v17 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, unsigned __int64))a1)(*(_QWORD *)(a1 + 16), v19) )
      {
LABEL_20:
        HybridDiskInfo = 995;
        goto LABEL_33;
      }
      Sleep(0x3E8u);
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v13);
      v21 = *(_QWORD *)(a1 + 32);
      lpMem = 0;
      HybridDiskInfo = HbDrvGetHybridDiskInfo(v21, (unsigned int)&lpMem, (unsigned int)&v26, 0, 0, 0);
      if ( HybridDiskInfo )
        goto LABEL_32;
      v13 = lpMem;
      v19 = v26 * (unsigned __int64)*((unsigned int *)lpMem + 2 * (_QWORD)v27 + 19) % *((unsigned int *)lpMem + 6);
      if ( v26 * (unsigned __int64)*((unsigned int *)lpMem + 2 * (_QWORD)v27 + 19) / *((unsigned int *)lpMem + 6) >= v18 + v20 )
        break;
      --v17;
    }
    for ( i = 60; i; --i )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, unsigned __int64))a1)(*(_QWORD *)(a1 + 16), v19) )
        goto LABEL_20;
      Sleep(0x7D0u);
    }
    HybridDiskInfo = 0;
  }
LABEL_33:
  if ( v13 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v13);
  return HybridDiskInfo;
}

```

## disassembly

```asm
0x1800a2aa0  mov     r11, rsp
0x1800a2aa3  mov     [r11+10h], rbx
0x1800a2aa7  mov     [r11+20h], r9d
0x1800a2aab  push    rbp
0x1800a2aac  push    rsi
0x1800a2aad  push    rdi
0x1800a2aae  push    r12
0x1800a2ab0  push    r13
0x1800a2ab2  push    r14
0x1800a2ab4  push    r15
0x1800a2ab6  mov     rbp, rsp
0x1800a2ab9  sub     rsp, 60h
0x1800a2abd  xor     edi, edi
0x1800a2abf  lea     rax, [rbp+arg_0]
0x1800a2ac3  mov     [r11-70h], rax
0x1800a2ac7  mov     r15d, r9d
0x1800a2aca  lea     rax, [rbp+var_1C]
0x1800a2ace  mov     [rbp+var_20], edi
0x1800a2ad1  mov     r13, r8
0x1800a2ad4  mov     [r11-78h], rax
0x1800a2ad8  mov     r12, rdx
0x1800a2adb  mov     [rbp+var_1C], edi
0x1800a2ade  mov     rsi, rcx
0x1800a2ae1  mov     [rbp+var_10], rdi
0x1800a2ae5  mov     rcx, [rcx+20h]
0x1800a2ae9  lea     r8, [rbp+var_10]
0x1800a2aed  xor     r9d, r9d
0x1800a2af0  mov     [rbp+arg_0], edi
0x1800a2af3  lea     rdx, [rbp+lpMem]
0x1800a2af7  mov     [rbp+lpMem], rdi
0x1800a2afb  mov     [rbp+var_8], rdi
0x1800a2aff  call    HbDrvGetHybridDiskInfo
0x1800a2b04  mov     ebx, eax
0x1800a2b06  test    eax, eax
0x1800a2b08  jnz     loc_1800A2D88
0x1800a2b0e  cmp     [rbp+arg_0], edi
0x1800a2b11  jz      short loc_1800A2B1A
0x1800a2b13  mov     ebx, edi
0x1800a2b15  jmp     loc_1800A2D88
0x1800a2b1a  mov     r14d, [rbp+arg_20]
0x1800a2b1e  test    r14d, r14d
0x1800a2b21  jz      loc_1800A2CBE
0x1800a2b27  mov     rdi, [rbp+lpMem]
0x1800a2b2b  movzx   eax, byte ptr [rdi+2Ch]
0x1800a2b2f  cmp     r14d, eax
0x1800a2b32  jb      short loc_1800A2B3E
0x1800a2b34  mov     ebx, 32h ; '2'
0x1800a2b39  jmp     loc_1800A2D8C
0x1800a2b3e  mov     r8, [rsi+20h]
0x1800a2b42  lea     rax, [r14+r14*2]
0x1800a2b46  mov     [rbp+var_8], rax
0x1800a2b4a  lea     r9, [r13+18h]
0x1800a2b4e  mov     eax, [rdi+rax*8+4Ch]
0x1800a2b52  mov     rdx, r12
0x1800a2b55  mov     [rbp+arg_0], eax
0x1800a2b58  mov     rcx, rsi
0x1800a2b5b  mov     eax, [rdi+18h]
0x1800a2b5e  mov     r8, [r8+10h]
0x1800a2b62  mov     [rbp+var_1C], eax
0x1800a2b65  mov     eax, 5
0x1800a2b6a  cmp     r14d, eax
0x1800a2b6d  mov     dword ptr [rsp+60h+var_38], 1
0x1800a2b75  cmovnb  r14d, eax
0x1800a2b79  mov     dword ptr [rsp+60h+var_40], r14d
0x1800a2b7e  call    HbDrvSetBitmap
0x1800a2b83  mov     ebx, eax
0x1800a2b85  test    eax, eax
0x1800a2b87  jnz     loc_1800A2D8C
0x1800a2b8d  xor     edx, edx
0x1800a2b8f  mov     rcx, r12
0x1800a2b92  call    cs:__imp_SmuCacheHitsControl
0x1800a2b98  test    eax, eax
0x1800a2b9a  jns     short loc_1800A2BAB
0x1800a2b9c  mov     ecx, eax; Status
0x1800a2b9e  call    cs:__imp_RtlNtStatusToDosError
0x1800a2ba4  mov     ebx, eax
0x1800a2ba6  jmp     loc_1800A2D8C
0x1800a2bab  mov     r8, [rbp+hFile]; hFile
0x1800a2baf  mov     edx, r15d; liDistanceToMove
0x1800a2bb2  xor     ecx, ecx; lpFileName
0x1800a2bb4  call    HbDrvSpeedTestCreateTestFile
0x1800a2bb9  mov     ebx, eax
0x1800a2bbb  test    eax, eax
0x1800a2bbd  jnz     loc_1800A2D8C
0x1800a2bc3  lea     edx, [rax+1]
0x1800a2bc6  mov     rcx, r12
0x1800a2bc9  call    cs:__imp_SmuCacheHitsControl
0x1800a2bcf  test    eax, eax
0x1800a2bd1  js      short loc_1800A2B9C
0x1800a2bd3  mov     eax, [rbp+arg_0]
0x1800a2bd6  lea     r14d, [rbx+78h]
0x1800a2bda  imul    rax, [rbp+var_10]
0x1800a2bdf  mov     ecx, [rbp+var_1C]
0x1800a2be2  xor     edx, edx
0x1800a2be4  mov     r12d, [rbp+arg_18]
0x1800a2be8  div     rcx
0x1800a2beb  or      r15d, 0FFFFFFFFh
0x1800a2bef  mov     r13, rax
0x1800a2bf2  xor     ebx, ebx
0x1800a2bf4  test    r14d, r14d
0x1800a2bf7  jz      loc_1800A2C8E
0x1800a2bfd  mov     rcx, [rsi+10h]
0x1800a2c01  mov     rax, [rsi]
0x1800a2c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c09  test    eax, eax
0x1800a2c0b  jz      short loc_1800A2C84
0x1800a2c0d  mov     ecx, 3E8h; dwMilliseconds
0x1800a2c12  call    cs:__imp_Sleep
0x1800a2c18  mov     rcx, cs:PfSvcGlobals
0x1800a2c1f  mov     r8, rdi; lpMem
0x1800a2c22  xor     edx, edx; dwFlags
0x1800a2c24  mov     rcx, [rcx+58h]; hHeap
0x1800a2c28  call    cs:__imp_HeapFree
0x1800a2c2e  mov     rcx, [rsi+20h]
0x1800a2c32  lea     r8, [rbp+var_10]
0x1800a2c36  xor     r9d, r9d
0x1800a2c39  mov     [rsp+60h+var_38], rbx
0x1800a2c3e  lea     rdx, [rbp+lpMem]
0x1800a2c42  mov     [rbp+lpMem], rbx
0x1800a2c46  mov     [rsp+60h+var_40], rbx
0x1800a2c4b  call    HbDrvGetHybridDiskInfo
0x1800a2c50  mov     ebx, eax
0x1800a2c52  test    eax, eax
0x1800a2c54  jnz     loc_1800A2D88
0x1800a2c5a  mov     rdi, [rbp+lpMem]
0x1800a2c5e  xor     edx, edx
0x1800a2c60  mov     rax, [rbp+var_8]
0x1800a2c64  mov     ecx, [rdi+18h]
0x1800a2c67  mov     eax, [rdi+rax*8+4Ch]
0x1800a2c6b  imul    rax, [rbp+var_10]
0x1800a2c70  div     rcx
0x1800a2c73  lea     rcx, [r12+r13]
0x1800a2c77  cmp     rax, rcx
0x1800a2c7a  jnb     short loc_1800A2C8E
0x1800a2c7c  add     r14d, r15d
0x1800a2c7f  jmp     loc_1800A2BF2
0x1800a2c84  mov     ebx, 3E3h
0x1800a2c89  jmp     loc_1800A2D8C
0x1800a2c8e  mov     ebx, 3Ch ; '<'
0x1800a2c93  test    ebx, ebx
0x1800a2c95  jz      short loc_1800A2CB7
0x1800a2c97  mov     rcx, [rsi+10h]
0x1800a2c9b  mov     rax, [rsi]
0x1800a2c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2ca3  test    eax, eax
0x1800a2ca5  jz      short loc_1800A2C84
0x1800a2ca7  mov     ecx, 7D0h; dwMilliseconds
0x1800a2cac  call    cs:__imp_Sleep
0x1800a2cb2  add     ebx, r15d
0x1800a2cb5  jmp     short loc_1800A2C93
0x1800a2cb7  xor     ebx, ebx
0x1800a2cb9  jmp     loc_1800A2D8C
0x1800a2cbe  mov     rcx, [rsi+10h]
0x1800a2cc2  mov     rax, [rsi]
0x1800a2cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2cca  test    eax, eax
0x1800a2ccc  jnz     short loc_1800A2CD8
0x1800a2cce  mov     ebx, 3E3h
0x1800a2cd3  jmp     loc_1800A2D88
0x1800a2cd8  mov     cl, [rsi+18h]
0x1800a2cdb  lea     r9, [rbp+var_20]
0x1800a2cdf  xor     edx, edx
0x1800a2ce1  mov     [rsp+60h+var_40], rdi; __int64
0x1800a2ce6  mov     r8d, 1
0x1800a2cec  or      eax, 0FFFFFFFFh
0x1800a2cef  shl     r8d, cl
0x1800a2cf2  lea     rcx, [r13+18h]; int
0x1800a2cf6  div     r8d
0x1800a2cf9  lea     r8, [rbp+var_8]
0x1800a2cfd  mov     edx, eax
0x1800a2cff  call    HbDrvFindBitmapSetRunsWithMetadata
0x1800a2d04  mov     rdi, [rbp+var_8]
0x1800a2d08  mov     ebx, eax
0x1800a2d0a  test    eax, eax
0x1800a2d0c  jnz     short loc_1800A2D6D
0x1800a2d0e  mov     r15d, [rbp+var_20]
0x1800a2d12  test    r15d, r15d
0x1800a2d15  jz      short loc_1800A2D6B
0x1800a2d17  mov     rcx, [rsi+10h]
0x1800a2d1b  mov     rax, [rsi]
0x1800a2d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d23  test    eax, eax
0x1800a2d25  jnz     short loc_1800A2D2E
0x1800a2d27  mov     ebx, 3E3h
0x1800a2d2c  jmp     short loc_1800A2D6D
0x1800a2d2e  xor     ebx, ebx
0x1800a2d30  mov     r8, [rsi+20h]
0x1800a2d34  mov     r9, rdi
0x1800a2d37  mov     [rsp+60h+var_28], 0
0x1800a2d3f  mov     rdx, r12
0x1800a2d42  mov     [rsp+60h+var_30], r14d
0x1800a2d47  mov     rcx, rsi
0x1800a2d4a  mov     dword ptr [rsp+60h+var_38], 7
0x1800a2d52  mov     r8, [r8+10h]
0x1800a2d56  mov     dword ptr [rsp+60h+var_40], r15d
0x1800a2d5b  call    HbDrvSendStoreUpdateRequest
0x1800a2d60  test    eax, eax
0x1800a2d62  jz      short loc_1800A2D6B
0x1800a2d64  inc     ebx
0x1800a2d66  cmp     ebx, 3
0x1800a2d69  jb      short loc_1800A2D30
0x1800a2d6b  xor     ebx, ebx
0x1800a2d6d  test    rdi, rdi
0x1800a2d70  jz      short loc_1800A2D88
0x1800a2d72  mov     rcx, cs:PfSvcGlobals
0x1800a2d79  mov     r8, rdi; lpMem
0x1800a2d7c  xor     edx, edx; dwFlags
0x1800a2d7e  mov     rcx, [rcx+58h]; hHeap
0x1800a2d82  call    cs:__imp_HeapFree
0x1800a2d88  mov     rdi, [rbp+lpMem]
0x1800a2d8c  test    rdi, rdi
0x1800a2d8f  jz      short loc_1800A2DA7
0x1800a2d91  mov     rcx, cs:PfSvcGlobals
0x1800a2d98  mov     r8, rdi; lpMem
0x1800a2d9b  xor     edx, edx; dwFlags
0x1800a2d9d  mov     rcx, [rcx+58h]; hHeap
0x1800a2da1  call    cs:__imp_HeapFree
0x1800a2da7  mov     eax, ebx
0x1800a2da9  mov     rbx, [rsp+60h+arg_8]
0x1800a2db1  add     rsp, 60h
0x1800a2db5  pop     r15
0x1800a2db7  pop     r14
0x1800a2db9  pop     r13
0x1800a2dbb  pop     r12
0x1800a2dbd  pop     rdi
0x1800a2dbe  pop     rsi
0x1800a2dbf  pop     rbp
0x1800a2dc0  retn
```
