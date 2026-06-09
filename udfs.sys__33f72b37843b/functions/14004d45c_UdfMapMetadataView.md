# UdfMapMetadataView

- ea: `0x14004d45c`
- end: `0x14004d6fa`
- name: `UdfMapMetadataView`
- size: `670`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x1400050d8`
- `0x14000b2b0`
- `0x14000c0ec`
- `0x14001758c`
- `0x140030818`
- `0x140039d14`
- `0x14003a274`
- `0x14003e368`
- `0x140044f90`
- `0x14004cef4`
- `0x14004cf74`
- `0x14004d074`
- `0x140056ea0`

## callees

- `0x14000653c`
- `0x14000a324`
- `0x14003d660`
- `0x14004d45c`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x14004d610`
- `ntoskrnl!CcMapData` at `0x14004d610`
- `ntoskrnl!ExRaiseStatus` at `0x14004d6d2`
- `ntoskrnl!ExRaiseStatus` at `0x14004d6d2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004d55a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004d55a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a49e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a4d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a49e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a4d0`
- `ntoskrnl!CcPinRead` at `0x14004d66e`
- `ntoskrnl!CcPinRead` at `0x14004d66e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14004d6b1`
- `ntoskrnl!KeDelayExecutionThread` at `0x14004d6b1`

## pseudocode

```c
BOOLEAN __fastcall UdfMapMetadataView(__int64 a1, __int64 a2, __int64 a3, __int16 a4, unsigned int a5, int a6, char a7)
{
  bool v11; // r14
  BOOLEAN result; // al
  char v13; // si
  __int64 v14; // r10
  __int64 v15; // r15
  struct _FILE_OBJECT *v16; // r12
  char v17; // al
  union _LARGE_INTEGER v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  int v21; // r14d
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp-40h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+50h] [rbp-38h] BYREF

  FileOffset.QuadPart = 0;
  v11 = *(_QWORD *)(a3 + 352) != 0;
  result = UdfUnpinView(a1, a2);
  if ( (a7 & 2) == 0 )
  {
    *(_WORD *)(a2 + 16) = a4;
    *(_DWORD *)(a2 + 20) = a5;
    *(_DWORD *)(a2 + 24) = a6;
    *(_DWORD *)(a2 + 28) = -1;
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = 0;
    *(_BYTE *)(a2 + 32) = v11;
    result = a4 == *(_WORD *)(*(_QWORD *)(a3 + 16) + 84LL);
    *(_BYTE *)(a2 + 33) = result;
  }
  v13 = 1;
  if ( (a7 & 1) == 0 )
  {
    v14 = *(_QWORD *)(a3 + 352);
    if ( v14 && (a7 & 0x10) != 0 )
      UdfSeqCacheReserveFileRegion(
        a1,
        v14,
        a5 & *(_DWORD *)(a3 + 76),
        *(unsigned int *)(a3 + 80),
        0,
        0,
        (*(_DWORD *)(a1 + 28) & 0x10) != 0);
    if ( *(_BYTE *)(a2 + 33) )
    {
      v15 = *(_QWORD *)(a3 + 320);
      v16 = *(struct _FILE_OBJECT **)(v15 + 504);
      *(_DWORD *)(a2 + 28) = *(_DWORD *)(a2 + 20);
      ExAcquireResourceSharedLite((PERESOURCE)(a3 + 1096), 1u);
    }
    else
    {
      v15 = *(_QWORD *)((v11 ? 0x50 : 0) + a3 + 272);
      v16 = *(struct _FILE_OBJECT **)(v15 + 504);
      v17 = *(_QWORD *)(a3 + 344) || (*(_DWORD *)(a3 + 48) & 0x20000000) != 0;
      *(_DWORD *)(a2 + 28) = UdfLookupMetaVsnOfExtent(
                               a1,
                               a3,
                               *(unsigned __int16 *)(a2 + 16),
                               *(_DWORD *)(a2 + 20),
                               *(_DWORD *)(a2 + 24),
                               v17);
    }
    v18.QuadPart = (unsigned __int64)*(unsigned int *)(a2 + 28) << *(_DWORD *)(a3 + 72);
    FileOffset = v18;
    v19 = *(unsigned int *)(a2 + 24);
    if ( v19 + v18.QuadPart > *(_QWORD *)(v15 + 24)
      || ((v18.QuadPart ^ (v19 + v18.QuadPart - 1)) & 0xFFFFFFFFFFFC0000uLL) != 0 )
    {
      *(_DWORD *)(a1 + 24) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    v20 = *(_DWORD *)(a3 + 48);
    if ( (v20 & 0x4000) != 0 )
    {
      return CcMapData(v16, &FileOffset, v19, 1u, (PVOID *)(a2 + 8), (PVOID *)a2);
    }
    else
    {
      v21 = 10;
      Interval.QuadPart = -10000;
      if ( !*(_QWORD *)(a3 + 352) && (v20 & 0x20000000) == 0 )
        v13 = 0;
      while ( 1 )
      {
        result = CcPinRead(v16, &FileOffset, *(_DWORD *)(a2 + 24), v13 == 0, (PVOID *)(a2 + 8), (PVOID *)a2);
        if ( result )
          break;
        UdfSeqCacheUnblockVatVPartBcb(a1, v15);
        if ( v21 )
        {
          if ( (unsigned int)--v21 < 5 )
          {
            KeDelayExecutionThread(0, 0, &Interval);
            Interval.LowPart *= 2;
          }
        }
        else
        {
          v13 = 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14004d45c  mov     rax, rsp
0x14004d45f  mov     [rax+8], rbx
0x14004d463  mov     [rax+20h], rsi
0x14004d467  mov     [rax+18h], r8
0x14004d46b  mov     [rax+10h], rdx
0x14004d46f  push    rdi
0x14004d470  push    r12
0x14004d472  push    r13
0x14004d474  push    r14
0x14004d476  push    r15
0x14004d478  sub     rsp, 60h
0x14004d47c  movzx   esi, r9w
0x14004d480  mov     rdi, r8
0x14004d483  mov     rbx, rdx
0x14004d486  mov     r13, rcx
0x14004d489  xor     r15d, r15d
0x14004d48c  mov     [rax-38h], r15
0x14004d490  cmp     [r8+160h], r15
0x14004d497  setnz   r14b
0x14004d49b  mov     [rsp+88h+var_47], r14b
0x14004d4a0  call    UdfUnpinView
0x14004d4a5  mov     edx, [rsp+88h+arg_30]
0x14004d4ac  mov     ecx, [rsp+88h+arg_20]
0x14004d4b3  test    dl, 2
0x14004d4b6  jnz     short loc_14004D4E9
0x14004d4b8  mov     [rbx+10h], si
0x14004d4bc  mov     [rbx+14h], ecx
0x14004d4bf  mov     eax, [rsp+88h+arg_28]
0x14004d4c6  mov     [rbx+18h], eax
0x14004d4c9  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x14004d4d0  mov     [rbx+8], r15
0x14004d4d4  mov     [rbx], r15
0x14004d4d7  mov     [rbx+20h], r14b
0x14004d4db  mov     rax, [rdi+10h]
0x14004d4df  cmp     si, [rax+54h]
0x14004d4e3  setz    al
0x14004d4e6  mov     [rbx+21h], al
0x14004d4e9  mov     esi, 1
0x14004d4ee  test    sil, dl
0x14004d4f1  jnz     loc_14004D6DF
0x14004d4f7  mov     r10, [rdi+160h]
0x14004d4fe  test    r10, r10
0x14004d501  jz      short loc_14004D536
0x14004d503  test    dl, 10h
0x14004d506  jz      short loc_14004D536
0x14004d508  mov     eax, [r13+1Ch]
0x14004d50c  shr     eax, 4
0x14004d50f  and     al, sil
0x14004d512  mov     r8d, [rdi+4Ch]
0x14004d516  and     r8d, ecx
0x14004d519  mov     [rsp+88h+var_58], al
0x14004d51d  mov     byte ptr [rsp+88h+Buffer], r15b
0x14004d522  mov     [rsp+88h+Bcb], r15
0x14004d527  mov     r9d, [rdi+50h]
0x14004d52b  mov     rdx, r10
0x14004d52e  mov     rcx, r13
0x14004d531  call    UdfSeqCacheReserveFileRegion
0x14004d536  cmp     [rbx+21h], r15b
0x14004d53a  jz      short loc_14004D568
0x14004d53c  mov     r15, [rdi+140h]
0x14004d543  mov     r12, [r15+1F8h]
0x14004d54a  mov     eax, [rbx+14h]
0x14004d54d  mov     [rbx+1Ch], eax
0x14004d550  lea     rcx, [rdi+448h]; Resource
0x14004d557  mov     dl, sil; Wait
0x14004d55a  call    cs:__imp_ExAcquireResourceSharedLite
0x14004d561  nop     dword ptr [rax+rax+00h]
0x14004d566  jmp     short loc_14004D5BC
0x14004d568  neg     r14b
0x14004d56b  sbb     rax, rax
0x14004d56e  and     eax, 50h
0x14004d571  mov     r15, [rax+rdi+110h]
0x14004d579  mov     r12, [r15+1F8h]
0x14004d580  cmp     qword ptr [rdi+158h], 0
0x14004d588  jnz     short loc_14004D597
0x14004d58a  test    dword ptr [rdi+30h], 20000000h
0x14004d591  jnz     short loc_14004D597
0x14004d593  xor     al, al
0x14004d595  jmp     short loc_14004D59A
0x14004d597  mov     al, sil
0x14004d59a  mov     byte ptr [rsp+88h+Buffer], al
0x14004d59e  mov     eax, [rbx+18h]
0x14004d5a1  mov     dword ptr [rsp+88h+Bcb], eax
0x14004d5a5  mov     r9d, [rbx+14h]
0x14004d5a9  movzx   r8d, word ptr [rbx+10h]
0x14004d5ae  mov     rdx, rdi
0x14004d5b1  mov     rcx, r13
0x14004d5b4  call    UdfLookupMetaVsnOfExtent
0x14004d5b9  mov     [rbx+1Ch], eax
0x14004d5bc  mov     edx, [rbx+1Ch]
0x14004d5bf  mov     ecx, [rdi+48h]
0x14004d5c2  shl     rdx, cl
0x14004d5c5  mov     qword ptr [rsp+88h+FileOffset], rdx
0x14004d5ca  mov     r8d, [rbx+18h]; Length
0x14004d5ce  lea     rax, [r8+rdx]
0x14004d5d2  cmp     rax, [r15+18h]
0x14004d5d6  jg      loc_14004D6C9
0x14004d5dc  dec     rax
0x14004d5df  xor     rax, rdx
0x14004d5e2  test    rax, 0FFFFFFFFFFFC0000h
0x14004d5e8  jnz     loc_14004D6C9
0x14004d5ee  mov     eax, [rdi+30h]
0x14004d5f1  bt      eax, 0Eh
0x14004d5f5  jnb     short loc_14004D61E
0x14004d5f7  lea     rax, [rbx+8]
0x14004d5fb  mov     [rsp+88h+Buffer], rbx; Buffer
0x14004d600  mov     [rsp+88h+Bcb], rax; Bcb
0x14004d605  mov     r9d, esi; Flags
0x14004d608  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14004d60d  mov     rcx, r12; FileObject
0x14004d610  call    cs:__imp_CcMapData
0x14004d617  nop     dword ptr [rax+rax+00h]
0x14004d61c  jmp     short loc_14004D67E
0x14004d61e  mov     r14d, 0Ah
0x14004d624  mov     [rsp+88h+var_44], r14d
0x14004d629  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFFFD8F0h
0x14004d632  cmp     qword ptr [rdi+160h], 0
0x14004d63a  jnz     short loc_14004D645
0x14004d63c  bt      eax, 1Dh
0x14004d640  jb      short loc_14004D645
0x14004d642  xor     sil, sil
0x14004d645  mov     [rsp+88h+var_48], sil
0x14004d64a  xor     r9d, r9d
0x14004d64d  test    sil, sil
0x14004d650  setz    r9b; Flags
0x14004d654  lea     rax, [rbx+8]
0x14004d658  mov     [rsp+88h+Buffer], rbx; Buffer
0x14004d65d  mov     [rsp+88h+Bcb], rax; Bcb
0x14004d662  mov     r8d, [rbx+18h]; Length
0x14004d666  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x14004d66b  mov     rcx, r12; FileObject
0x14004d66e  call    cs:__imp_CcPinRead
0x14004d675  nop     dword ptr [rax+rax+00h]
0x14004d67a  test    al, al
0x14004d67c  jz      short loc_14004D680
0x14004d67e  jmp     short loc_14004D6DF
0x14004d680  mov     rdx, r15
0x14004d683  mov     rcx, r13
0x14004d686  call    UdfSeqCacheUnblockVatVPartBcb
0x14004d68b  test    r14d, r14d
0x14004d68e  jnz     short loc_14004D69A
0x14004d690  xor     sil, sil
0x14004d693  mov     [rsp+88h+var_48], sil
0x14004d698  jmp     short loc_14004D6C7
0x14004d69a  dec     r14d
0x14004d69d  mov     [rsp+88h+var_44], r14d
0x14004d6a2  cmp     r14d, 5
0x14004d6a6  jnb     short loc_14004D6C7
0x14004d6a8  lea     r8, [rsp+88h+Interval]; Interval
0x14004d6ad  xor     edx, edx; Alertable
0x14004d6af  xor     ecx, ecx; WaitMode
0x14004d6b1  call    cs:__imp_KeDelayExecutionThread
0x14004d6b8  nop     dword ptr [rax+rax+00h]
0x14004d6bd  mov     eax, dword ptr [rsp+88h+Interval]
0x14004d6c1  add     eax, eax
0x14004d6c3  mov     dword ptr [rsp+88h+Interval], eax
0x14004d6c7  jmp     short loc_14004D64A
0x14004d6c9  mov     ecx, 0C0000102h; Status
0x14004d6ce  mov     [r13+18h], ecx
0x14004d6d2  call    cs:__imp_ExRaiseStatus
0x14004d6df  lea     r11, [rsp+88h+var_28]
0x14004d6e4  mov     rbx, [r11+30h]
0x14004d6e8  mov     rsi, [r11+48h]
0x14004d6ec  mov     rsp, r11
0x14004d6ef  pop     r15
0x14004d6f1  pop     r14
0x14004d6f3  pop     r13
0x14004d6f5  pop     r12
0x14004d6f7  pop     rdi
0x14004d6f8  retn
0x14005a47c  push    rbx
0x14005a47e  push    rbp
0x14005a47f  sub     rsp, 48h
0x14005a483  mov     rbp, rdx
0x14005a486  test    cl, cl
0x14005a488  jz      short loc_14005A4EC
0x14005a48a  mov     rcx, [rbp+0A0h]
0x14005a491  cmp     byte ptr [rbp+41h], 0
0x14005a495  jz      short loc_14005A4B3
0x14005a497  add     rcx, 168h; Resource
0x14005a49e  call    cs:__imp_ExReleaseResourceLite
0x14005a4a5  nop     dword ptr [rax+rax+00h]
0x14005a4aa  mov     rbx, [rbp+98h]
0x14005a4b1  jmp     short loc_14005A4DD
0x14005a4b3  mov     rbx, [rbp+98h]
0x14005a4ba  cmp     byte ptr [rbx+21h], 0
0x14005a4be  jz      short loc_14005A4C9
0x14005a4c0  add     rcx, 448h
0x14005a4c7  jmp     short loc_14005A4D0
0x14005a4c9  add     rcx, 3E0h; Resource
0x14005a4d0  call    cs:__imp_ExReleaseResourceLite
0x14005a4d7  nop     dword ptr [rax+rax+00h]
0x14005a4dc  nop
0x14005a4dd  mov     qword ptr [rbx], 0
0x14005a4e4  mov     qword ptr [rbx+8], 0
0x14005a4ec  add     rsp, 48h
0x14005a4f0  pop     rbp
0x14005a4f1  pop     rbx
0x14005a4f2  retn
```
