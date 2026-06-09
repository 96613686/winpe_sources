# QueryDisplayConfig

- ea: `0x180041310`
- end: `0x1800415af`
- name: `QueryDisplayConfig`
- size: `671`
- prototype: `LONG __stdcall(UINT32 flags, UINT32 *numPathArrayElements, DISPLAYCONFIG_PATH_INFO *pathArray, UINT32 *numModeInfoArrayElements, DISPLAYCONFIG_MODE_INFO *modeInfoArray, DISPLAYCONFIG_TOPOLOGY_ID *currentTopologyId)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180041310`
- `0x1800415c0`
- `0x180096db9`
- `0x180096e00`

## import_xrefs

- `win32u!NtGdiDdDDIEscape` at `0x180041584`
- `win32u!NtGdiDdDDIEscape` at `0x180041584`
- `win32u!NtUserQueryDisplayConfig` at `0x180041373`
- `win32u!NtUserQueryDisplayConfig` at `0x180041373`
- `ntdll!RtlNtStatusToDosError` at `0x1800414c2`
- `ntdll!RtlNtStatusToDosError` at `0x1800414c2`
- `ntdll!RtlFreeHeap` at `0x1800414b6`
- `ntdll!RtlFreeHeap` at `0x1800414b6`
- `ntdll!RtlAllocateHeap` at `0x180041516`
- `ntdll!RtlAllocateHeap` at `0x180041516`

## pseudocode

```c
LONG __stdcall QueryDisplayConfig(
        UINT32 flags,
        UINT32 *numPathArrayElements,
        DISPLAYCONFIG_PATH_INFO *pathArray,
        UINT32 *numModeInfoArrayElements,
        DISPLAYCONFIG_MODE_INFO *modeInfoArray,
        DISPLAYCONFIG_TOPOLOGY_ID *currentTopologyId)
{
  char *Heap; // r14
  char v10; // r13
  NTSTATUS DisplayConfig; // edi
  __int64 v12; // r10
  char *v13; // rdi
  int v14; // ecx
  UINT32 *v15; // rsi
  UINT32 v16; // edx
  UINT32 v17; // r8d
  __int64 v18; // rax
  int v20; // ecx
  __int64 v21; // [rsp+40h] [rbp-49h] BYREF
  __int64 v22; // [rsp+48h] [rbp-41h]
  UINT32 **v23; // [rsp+50h] [rbp-39h]
  __int64 v24; // [rsp+58h] [rbp-31h]
  DISPLAYCONFIG_PATH_INFO *v25; // [rsp+60h] [rbp-29h]
  DISPLAYCONFIG_MODE_INFO *v26; // [rsp+68h] [rbp-21h]
  UINT32 *v27; // [rsp+70h] [rbp-19h] BYREF
  UINT32 v28; // [rsp+78h] [rbp-11h]
  int v29; // [rsp+7Ch] [rbp-Dh]

  v27 = numModeInfoArrayElements;
  Heap = 0;
  if ( pathArray )
  {
    Heap = (char *)RtlAllocateHeap(pUserHeap, 8u, 216LL * *numPathArrayElements);
    if ( !Heap )
    {
      v15 = v27;
      DisplayConfig = -1073741801;
LABEL_25:
      v20 = (*v15 << 16) | *(unsigned __int16 *)numPathArrayElements;
      LODWORD(v27) = 100;
      v29 = v20;
      HIDWORD(v27) = DisplayConfig;
      v28 = flags;
      v21 = 0;
      v22 = 32;
      v24 = 16;
      v23 = &v27;
      NtGdiDdDDIEscape(&v21);
      return RtlNtStatusToDosError(DisplayConfig);
    }
  }
  v10 = 1;
  DisplayConfig = NtUserQueryDisplayConfig(flags, numPathArrayElements, Heap, currentTopologyId, 0);
  if ( DisplayConfig >= 0 && (v12 = *numPathArrayElements, (_DWORD)v12) )
  {
    if ( Heap < &Heap[216 * v12] )
    {
      v13 = Heap;
      do
      {
        v14 = *((_DWORD *)v13 + 47);
        if ( !v14 || v14 == 1 && (flags & 0x20) != 0 )
        {
          v13 += 216;
        }
        else
        {
          if ( v13 + 216 != &Heap[216 * (unsigned int)v12] )
            memmove_0(v13, v13 + 216, 216 * ((unsigned int)v12 - 0x84BDA12F684BDA13uLL * ((v13 - Heap) >> 3)) - 216);
          LODWORD(v12) = --*numPathArrayElements;
        }
      }
      while ( v13 < &Heap[216 * (unsigned int)v12] );
      v10 = 1;
    }
    v26 = modeInfoArray;
    *(_WORD *)((char *)&v21 + 1) = 0;
    BYTE3(v21) = 0;
    HIDWORD(v23) = 0;
    v24 = (__int64)modeInfoArray;
    v15 = v27;
    LODWORD(v23) = *v27;
    v25 = pathArray;
    v22 = (__int64)pathArray;
    HIDWORD(v21) = v12;
    LOBYTE(v21) = 0;
    DisplayConfig = QdcCompat::ConvertPathModalityToDisplayConfig(
                      v12,
                      (__int64)Heap,
                      (flags & 4) != 0,
                      (flags & 0x10) != 0,
                      (flags & 0x40) != 0,
                      (flags & 0x40000000) != 0,
                      (__int64)&v21);
    if ( DisplayConfig < 0 )
    {
      v10 = 0;
    }
    else
    {
      v16 = 0;
      *numPathArrayElements = 954437177 * (((__int64)v25 - v22) >> 3);
      *v15 = ((__int64)v26 - v24) >> 6;
      v17 = *numPathArrayElements;
      if ( *numPathArrayElements )
      {
        v18 = 0;
        do
        {
          if ( pathArray[v18].targetInfo.refreshRate.Numerator == -2
            && pathArray[v18].targetInfo.refreshRate.Denominator == -2 )
          {
            pathArray[v18].targetInfo.refreshRate.Numerator = 64;
            pathArray[v18].targetInfo.refreshRate.Denominator = 1;
          }
          ++v16;
          ++v18;
        }
        while ( v16 < v17 );
      }
    }
  }
  else
  {
    v15 = v27;
  }
  if ( Heap )
    RtlFreeHeap(pUserHeap, 0, Heap);
  if ( DisplayConfig < 0 && !v10 )
    goto LABEL_25;
  return RtlNtStatusToDosError(DisplayConfig);
}

```

## disassembly

```asm
0x180041310  push    rbp
0x180041312  push    rbx
0x180041313  push    rsi
0x180041314  push    rdi
0x180041315  push    r12
0x180041317  push    r13
0x180041319  push    r14
0x18004131b  push    r15
0x18004131d  lea     rbp, [rsp-0Fh]
0x180041322  sub     rsp, 98h
0x180041329  mov     rax, cs:__security_cookie
0x180041330  xor     rax, rsp
0x180041333  mov     [rbp+47h+var_50], rax
0x180041337  mov     rsi, [rbp+47h+modeInfoArray]
0x18004133b  xor     r13d, r13d
0x18004133e  mov     rdi, [rbp+47h+currentTopologyId]
0x180041342  mov     rbx, r8
0x180041345  mov     [rbp+47h+var_60], r9
0x180041349  mov     r15, rdx
0x18004134c  mov     r12d, ecx
0x18004134f  mov     r14d, r13d
0x180041352  test    r8, r8
0x180041355  jnz     loc_180041501
0x18004135b  mov     r9, rdi
0x18004135e  mov     [rsp+0D0h+var_B0], 0
0x180041367  mov     r8, r14
0x18004136a  mov     rdx, r15
0x18004136d  mov     ecx, r12d
0x180041370  mov     r13b, 1
0x180041373  call    cs:__imp_NtUserQueryDisplayConfig
0x180041379  mov     edi, eax
0x18004137b  test    eax, eax
0x18004137d  js      loc_180041533
0x180041383  mov     r10d, [r15]
0x180041386  test    r10d, r10d
0x180041389  jz      loc_180041533
0x18004138f  imul    rcx, r10, 0D8h
0x180041396  add     rcx, r14
0x180041399  cmp     r14, rcx
0x18004139c  jnb     short loc_1800413D5
0x18004139e  mov     rdi, r14
0x1800413a1  mov     r13, 84BDA12F684BDA13h
0x1800413ab  mov     ecx, [rdi+0BCh]
0x1800413b1  test    ecx, ecx
0x1800413b3  jnz     loc_180041597
0x1800413b9  add     rdi, 0D8h
0x1800413c0  mov     eax, r10d
0x1800413c3  imul    rcx, rax, 0D8h
0x1800413ca  add     rcx, r14
0x1800413cd  cmp     rdi, rcx
0x1800413d0  jb      short loc_1800413AB
0x1800413d2  mov     r13b, 1
0x1800413d5  xor     eax, eax
0x1800413d7  mov     [rbp+47h+var_68], rsi
0x1800413db  mov     word ptr [rbp+47h+var_90+1], ax
0x1800413df  lea     rcx, [rbp+47h+var_90]
0x1800413e3  mov     byte ptr [rbp+47h+var_90+3], al
0x1800413e6  mov     edx, r12d
0x1800413e9  mov     dword ptr [rbp+47h+var_80+4], eax
0x1800413ec  mov     r9d, r12d
0x1800413ef  mov     [rsp+0D0h+var_A0], rcx
0x1800413f4  mov     r8d, r12d
0x1800413f7  shr     edx, 1Eh
0x1800413fa  mov     ecx, r10d
0x1800413fd  and     dl, 1
0x180041400  mov     [rbp+47h+var_78], rsi
0x180041404  mov     rsi, [rbp+47h+var_60]
0x180041408  mov     [rsp+0D0h+var_A8], dl
0x18004140c  mov     rdx, r14
0x18004140f  shr     r9d, 4
0x180041413  shr     r8d, 2
0x180041417  and     r9b, 1
0x18004141b  mov     eax, [rsi]
0x18004141d  and     r8b, 1
0x180041421  mov     dword ptr [rbp+47h+var_80], eax
0x180041424  mov     eax, r12d
0x180041427  shr     eax, 6
0x18004142a  and     al, 1
0x18004142c  mov     [rbp+47h+var_70], rbx
0x180041430  mov     byte ptr [rsp+0D0h+var_B0], al
0x180041434  mov     [rbp+47h+var_88], rbx
0x180041438  mov     dword ptr [rbp+47h+var_90+4], r10d
0x18004143c  mov     byte ptr [rbp+47h+var_90], 0
0x180041440  call    QdcCompat__ConvertPathModalityToDisplayConfig
0x180041445  mov     edi, eax
0x180041447  test    eax, eax
0x180041449  js      loc_18004158F
0x18004144f  mov     rax, [rbp+47h+var_70]
0x180041453  mov     rcx, 8E38E38E38E38E39h
0x18004145d  sub     rax, [rbp+47h+var_88]
0x180041461  xor     edx, edx
0x180041463  sar     rax, 3
0x180041467  imul    rax, rcx
0x18004146b  mov     [r15], eax
0x18004146e  mov     rax, [rbp+47h+var_68]
0x180041472  sub     rax, [rbp+47h+var_78]
0x180041476  sar     rax, 6
0x18004147a  mov     [rsi], eax
0x18004147c  mov     r8d, [r15]
0x18004147f  test    r8d, r8d
0x180041482  jz      short loc_1800414A5
0x180041484  xor     eax, eax
0x180041486  nop     word ptr [rax+rax+00000000h]
0x180041490  lea     rcx, [rax+rax*8]
0x180041494  cmp     dword ptr [rbx+rcx*8+30h], 0FFFFFFFEh
0x180041499  jz      short loc_1800414E8
0x18004149b  inc     edx
0x18004149d  inc     rax
0x1800414a0  cmp     edx, r8d
0x1800414a3  jb      short loc_180041490
0x1800414a5  test    r14, r14
0x1800414a8  jz      short loc_1800414BC
0x1800414aa  mov     rcx, cs:pUserHeap; HeapHandle
0x1800414b1  mov     r8, r14; P
0x1800414b4  xor     edx, edx; Flags
0x1800414b6  call    cs:__imp_RtlFreeHeap
0x1800414bc  test    edi, edi
0x1800414be  js      short loc_18004153C
0x1800414c0  mov     ecx, edi; Status
0x1800414c2  call    cs:__imp_RtlNtStatusToDosError
0x1800414c8  mov     rcx, [rbp+47h+var_50]
0x1800414cc  xor     rcx, rsp; StackCookie
0x1800414cf  call    __security_check_cookie
0x1800414d4  add     rsp, 98h
0x1800414db  pop     r15
0x1800414dd  pop     r14
0x1800414df  pop     r13
0x1800414e1  pop     r12
0x1800414e3  pop     rdi
0x1800414e4  pop     rsi
0x1800414e5  pop     rbx
0x1800414e6  pop     rbp
0x1800414e7  retn
0x1800414e8  cmp     dword ptr [rbx+rcx*8+34h], 0FFFFFFFEh
0x1800414ed  jnz     short loc_18004149B
0x1800414ef  mov     dword ptr [rbx+rcx*8+30h], 40h ; '@'
0x1800414f7  mov     dword ptr [rbx+rcx*8+34h], 1
0x1800414ff  jmp     short loc_18004149B
0x180041501  mov     eax, [rdx]
0x180041503  mov     edx, 8; Flags
0x180041508  mov     rcx, cs:pUserHeap; HeapHandle
0x18004150f  imul    r8, rax, 0D8h; Size
0x180041516  call    cs:__imp_RtlAllocateHeap
0x18004151c  mov     r14, rax
0x18004151f  test    rax, rax
0x180041522  jnz     loc_18004135B
0x180041528  mov     rsi, [rbp+47h+var_60]
0x18004152c  mov     edi, 0C0000017h
0x180041531  jmp     short loc_180041548
0x180041533  mov     rsi, [rbp+47h+var_60]
0x180041537  jmp     loc_1800414A5
0x18004153c  test    r13b, r13b
0x18004153f  jnz     loc_1800414C0
0x180041545  xor     r13d, r13d
0x180041548  mov     eax, [rsi]
0x18004154a  movzx   ecx, word ptr [r15]
0x18004154e  shl     eax, 10h
0x180041551  or      ecx, eax
0x180041553  mov     dword ptr [rbp+47h+var_60], 64h ; 'd'
0x18004155a  mov     [rbp+47h+var_54], ecx
0x18004155d  lea     rax, [rbp+47h+var_60]
0x180041561  lea     rcx, [rbp+47h+var_90]
0x180041565  mov     dword ptr [rbp+47h+var_60+4], edi
0x180041568  mov     [rbp+47h+var_58], r12d
0x18004156c  mov     [rbp+47h+var_90], r13
0x180041570  mov     [rbp+47h+var_88], 20h ; ' '
0x180041578  mov     [rbp+47h+var_78], 10h
0x180041580  mov     [rbp+47h+var_80], rax
0x180041584  call    cs:__imp_NtGdiDdDDIEscape
0x18004158a  jmp     loc_1800414C0
0x18004158f  xor     r13b, r13b
0x180041592  jmp     loc_1800414A5
0x180041597  cmp     ecx, 1
0x18004159a  jnz     loc_18009DD3E
0x1800415a0  test    r12b, 20h
0x1800415a4  jnz     loc_1800413B9
0x1800415aa  jmp     loc_18009DD3E
0x18009dd3e  mov     ecx, r10d
0x18009dd41  lea     rdx, [rdi+0D8h]; Src
0x18009dd48  imul    rax, rcx, 0D8h
0x18009dd4f  add     rax, r14
0x18009dd52  cmp     rdx, rax
0x18009dd55  jz      short loc_18009DD7E
0x18009dd57  mov     rax, rdi
0x18009dd5a  sub     rax, r14
0x18009dd5d  sar     rax, 3
0x18009dd61  imul    rax, r13
0x18009dd65  sub     rcx, rax
0x18009dd68  imul    r8, rcx, 0D8h
0x18009dd6f  mov     rcx, rdi; void *
0x18009dd72  sub     r8, 0D8h; Size
0x18009dd79  call    memmove_0
0x18009dd7e  dec     dword ptr [r15]
0x18009dd81  mov     r10d, [r15]
0x18009dd84  jmp     loc_1800413C0
```
