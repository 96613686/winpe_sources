# SetDisplayConfig

- ea: `0x1800595c0`
- end: `0x18005976d`
- name: `SetDisplayConfig`
- size: `429`
- prototype: `LONG __stdcall(UINT32 numPathArrayElements, DISPLAYCONFIG_PATH_INFO *pathArray, UINT32 numModeInfoArrayElements, DISPLAYCONFIG_MODE_INFO *modeInfoArray, UINT32 flags)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18004ce4c`
- `0x1800595c0`
- `0x180059774`
- `0x1800597c4`
- `0x180065574`
- `0x180095600`
- `0x180096dad`

## import_xrefs

- `win32u!NtUserSetDisplayConfig` at `0x18005967b`
- `win32u!NtUserSetDisplayConfig` at `0x18005967b`
- `ntdll!RtlNtStatusToDosError` at `0x1800596b8`
- `ntdll!RtlFreeHeap` at `0x18005973d`
- `ntdll!RtlFreeHeap` at `0x180059754`
- `ntdll!RtlFreeHeap` at `0x18005973d`
- `ntdll!RtlFreeHeap` at `0x180059754`
- `ntdll!RtlAllocateHeap` at `0x18005960d`
- `ntdll!RtlAllocateHeap` at `0x180059708`
- `ntdll!RtlAllocateHeap` at `0x18005960d`
- `ntdll!RtlAllocateHeap` at `0x180059708`

## pseudocode

```c
LONG __stdcall SetDisplayConfig(
        UINT32 numPathArrayElements,
        DISPLAYCONFIG_PATH_INFO *pathArray,
        UINT32 numModeInfoArrayElements,
        DISPLAYCONFIG_MODE_INFO *modeInfoArray,
        UINT32 flags)
{
  UINT32 v5; // r12d
  __int64 v7; // r15
  UINT32 v9; // esi
  void *v10; // rdi
  char v11; // r13
  void *v12; // rbp
  PVOID v13; // rax
  NTSTATUS v14; // ebx
  void *v15; // r14
  char *Heap; // rax
  __int64 v18; // r9
  __int64 i; // rdx
  __int64 v20; // rcx
  void *v21; // [rsp+88h] [rbp+10h] BYREF

  v5 = flags;
  v7 = numModeInfoArrayElements;
  v9 = numPathArrayElements;
  if ( pathArray )
  {
    Heap = (char *)RtlAllocateHeap(pUserHeap, 8u, 72LL * numPathArrayElements);
    v10 = Heap;
    if ( !Heap )
    {
      v14 = -1073741801;
LABEL_29:
      LogCodePointPacket(99, (unsigned int)v14, v5);
      return RtlNtStatusToDosError(v14);
    }
    v18 = 0;
    for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
    {
      if ( (pathArray[i].flags & 1) != 0 )
      {
        v20 = 9 * v18;
        v18 = (unsigned int)(v18 + 1);
        *(_OWORD *)&Heap[8 * v20] = *(_OWORD *)&pathArray[i].sourceInfo.adapterId.LowPart;
        *(_OWORD *)&Heap[8 * v20 + 16] = *(_OWORD *)&pathArray[i].sourceInfo.statusFlags;
        *(_OWORD *)&Heap[8 * v20 + 32] = *(_OWORD *)&pathArray[i].targetInfo.modeInfoIdx;
        *(_OWORD *)&Heap[8 * v20 + 48] = *(_OWORD *)&pathArray[i].targetInfo.refreshRate.Numerator;
        *(_QWORD *)&Heap[8 * v20 + 64] = *(_QWORD *)&pathArray[i].targetInfo.statusFlags;
      }
    }
    v9 = v18;
  }
  else
  {
    v10 = 0;
  }
  v11 = 0;
  v12 = 0;
  if ( modeInfoArray )
  {
    v13 = RtlAllocateHeap(pUserHeap, 8u, v7 << 6);
    v12 = v13;
    if ( !v13 )
    {
      v14 = -1073741801;
      goto LABEL_11;
    }
    memcpy_0(v13, modeInfoArray, v7 << 6);
  }
  v14 = SdcCompat::SetDisplayConfigValidateParamsUserMode(
          v9,
          (__int64)v10,
          (_DWORD *)(unsigned int)v7,
          (__int64)v12,
          v5);
  if ( v14 < 0 || (v14 = SdcCompat::TranslateWddm13VirtualCloneTopologySdcv1Call(v5, v9, v10), v14 < 0) )
  {
LABEL_11:
    if ( !v10 )
      goto LABEL_12;
    goto LABEL_20;
  }
  v15 = 0;
  v21 = 0;
  if ( !v10 )
  {
LABEL_9:
    v11 = 1;
    v14 = NtUserSetDisplayConfig(v9, v15, v5, 0, 0);
    if ( v15 )
      DisplayDelete<DISPLAYCONFIG_PATH_INFO_INTERNAL>(v15);
    goto LABEL_11;
  }
  v14 = SdcCompat::ConvertDisplayConfigToInternalPaths(v9, (_DWORD)v10, v7, (_DWORD)v12, v5, (__int64)&v21);
  if ( v14 >= 0 )
  {
    v15 = v21;
    goto LABEL_9;
  }
LABEL_20:
  RtlFreeHeap(pUserHeap, 0, v10);
LABEL_12:
  if ( v12 )
    RtlFreeHeap(pUserHeap, 0, v12);
  if ( v14 < 0 && !v11 )
    goto LABEL_29;
  return RtlNtStatusToDosError(v14);
}

```

## disassembly

```asm
0x1800595c0  push    rbx
0x1800595c2  push    rbp
0x1800595c3  push    rsi
0x1800595c4  push    rdi
0x1800595c5  push    r12
0x1800595c7  push    r13
0x1800595c9  push    r14
0x1800595cb  push    r15
0x1800595cd  sub     rsp, 38h
0x1800595d1  mov     r12d, [rsp+78h+flags]
0x1800595d9  mov     r14, r9
0x1800595dc  mov     r15d, r8d
0x1800595df  mov     rbx, rdx
0x1800595e2  mov     esi, ecx
0x1800595e4  test    rdx, rdx
0x1800595e7  jnz     loc_1800596F4
0x1800595ed  xor     edi, edi
0x1800595ef  xor     r13b, r13b
0x1800595f2  xor     ebp, ebp
0x1800595f4  test    r14, r14
0x1800595f7  jz      short loc_180059626
0x1800595f9  mov     rcx, cs:pUserHeap; HeapHandle
0x180059600  lea     edx, [rbp+8]; Flags
0x180059603  mov     rbx, r15
0x180059606  shl     rbx, 6
0x18005960a  mov     r8, rbx; Size
0x18005960d  call    cs:__imp_RtlAllocateHeap
0x180059613  mov     rbp, rax
0x180059616  test    rax, rax
0x180059619  jnz     loc_18009F86D
0x18005961f  mov     ebx, 0C0000017h
0x180059624  jmp     short loc_18005968C
0x180059626  mov     r9, rbp
0x180059629  mov     dword ptr [rsp+78h+var_58], r12d
0x18005962e  mov     r8d, r15d
0x180059631  mov     rdx, rdi
0x180059634  mov     ecx, esi
0x180059636  call    SdcCompat__SetDisplayConfigValidateParamsUserMode
0x18005963b  mov     ebx, eax
0x18005963d  test    eax, eax
0x18005963f  js      short loc_18005968C
0x180059641  mov     r8, rdi
0x180059644  mov     edx, esi
0x180059646  mov     ecx, r12d
0x180059649  call    SdcCompat__TranslateWddm13VirtualCloneTopologySdcv1Call
0x18005964e  mov     ebx, eax
0x180059650  test    eax, eax
0x180059652  js      short loc_18005968C
0x180059654  xor     r14d, r14d
0x180059657  mov     [rsp+78h+arg_8], r14
0x18005965f  test    rdi, rdi
0x180059662  jnz     short loc_1800596BF
0x180059664  xor     r9d, r9d
0x180059667  mov     [rsp+78h+var_58], 0
0x180059670  mov     r8d, r12d
0x180059673  mov     rdx, r14
0x180059676  mov     ecx, esi
0x180059678  mov     r13b, 1
0x18005967b  call    cs:__imp_NtUserSetDisplayConfig
0x180059681  mov     ebx, eax
0x180059683  test    r14, r14
0x180059686  jnz     loc_180059724
0x18005968c  test    rdi, rdi
0x18005968f  jnz     loc_180059731
0x180059695  test    rbp, rbp
0x180059698  jnz     loc_180059748
0x18005969e  test    ebx, ebx
0x1800596a0  js      loc_18005975F
0x1800596a6  mov     ecx, ebx
0x1800596a8  add     rsp, 38h
0x1800596ac  pop     r15
0x1800596ae  pop     r14
0x1800596b0  pop     r13
0x1800596b2  pop     r12
0x1800596b4  pop     rdi
0x1800596b5  pop     rsi
0x1800596b6  pop     rbp
0x1800596b7  pop     rbx
0x1800596b8  jmp     cs:__imp_RtlNtStatusToDosError
0x1800596bf  lea     rax, [rsp+78h+arg_8]
0x1800596c7  mov     r9, rbp
0x1800596ca  mov     [rsp+78h+var_50], rax
0x1800596cf  mov     r8d, r15d
0x1800596d2  mov     rdx, rdi
0x1800596d5  mov     dword ptr [rsp+78h+var_58], r12d
0x1800596da  mov     ecx, esi
0x1800596dc  call    SdcCompat__ConvertDisplayConfigToInternalPaths
0x1800596e1  mov     ebx, eax
0x1800596e3  test    eax, eax
0x1800596e5  js      short loc_180059731
0x1800596e7  mov     r14, [rsp+78h+arg_8]
0x1800596ef  jmp     loc_180059664
0x1800596f4  mov     rcx, cs:pUserHeap; HeapHandle
0x1800596fb  lea     r8, [rsi+rsi*8]
0x1800596ff  shl     r8, 3; Size
0x180059703  mov     edx, 8; Flags
0x180059708  call    cs:__imp_RtlAllocateHeap
0x18005970e  mov     rdi, rax
0x180059711  test    rax, rax
0x180059714  jnz     loc_18009F80C
0x18005971a  mov     ebx, 0C0000017h
0x18005971f  jmp     loc_18009F881
0x180059724  mov     rcx, r14; P
0x180059727  call    ??$DisplayDelete@UDISPLAYCONFIG_PATH_INFO_INTERNAL@@@@YAXPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@@Z; DisplayDelete<DISPLAYCONFIG_PATH_INFO_INTERNAL>(DISPLAYCONFIG_PATH_INFO_INTERNAL *)
0x18005972c  jmp     loc_18005968C
0x180059731  mov     rcx, cs:pUserHeap; HeapHandle
0x180059738  mov     r8, rdi; P
0x18005973b  xor     edx, edx; Flags
0x18005973d  call    cs:__imp_RtlFreeHeap
0x180059743  jmp     loc_180059695
0x180059748  mov     rcx, cs:pUserHeap; HeapHandle
0x18005974f  mov     r8, rbp; P
0x180059752  xor     edx, edx; Flags
0x180059754  call    cs:__imp_RtlFreeHeap
0x18005975a  jmp     loc_18005969E
0x18005975f  test    r13b, r13b
0x180059762  jnz     loc_1800596A6
0x180059768  jmp     loc_18009F881
0x18009f80c  xor     r9d, r9d
0x18009f80f  xor     edx, edx
0x18009f811  test    esi, esi
0x18009f813  jz      short loc_18009F865
0x18009f815  lea     r8, [rdx+rdx*8]
0x18009f819  test    byte ptr [rbx+r8*8+44h], 1
0x18009f81f  jz      short loc_18009F85F
0x18009f821  movups  xmm0, xmmword ptr [rbx+r8*8]
0x18009f826  lea     rcx, [r9+r9*8]
0x18009f82a  inc     r9d
0x18009f82d  movups  xmmword ptr [rax+rcx*8], xmm0
0x18009f831  movups  xmm1, xmmword ptr [rbx+r8*8+10h]
0x18009f837  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x18009f83c  movups  xmm0, xmmword ptr [rbx+r8*8+20h]
0x18009f842  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x18009f847  movups  xmm1, xmmword ptr [rbx+r8*8+30h]
0x18009f84d  movups  xmmword ptr [rax+rcx*8+30h], xmm1
0x18009f852  movsd   xmm0, qword ptr [rbx+r8*8+40h]
0x18009f859  movsd   qword ptr [rax+rcx*8+40h], xmm0
0x18009f85f  inc     edx
0x18009f861  cmp     edx, esi
0x18009f863  jb      short loc_18009F815
0x18009f865  mov     esi, r9d
0x18009f868  jmp     loc_1800595EF
0x18009f86d  mov     r8, rbx; Size
0x18009f870  mov     rdx, r14; Src
0x18009f873  mov     rcx, rax; void *
0x18009f876  call    memcpy_0
0x18009f87b  nop
0x18009f87c  jmp     loc_180059626
0x18009f881  movzx   r9d, si
0x18009f885  mov     r8d, r12d
0x18009f888  shl     r15d, 10h
0x18009f88c  mov     edx, ebx
0x18009f88e  or      r9d, r15d
0x18009f891  mov     ecx, 63h ; 'c'
0x18009f896  call    ?LogCodePointPacket@@YAXW4_DXGK_DIAG_CODE_POINT_TYPE@@III@Z; LogCodePointPacket(_DXGK_DIAG_CODE_POINT_TYPE,uint,uint,uint)
0x18009f89b  nop
0x18009f89c  jmp     loc_1800596A6
```
