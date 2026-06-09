# VmsVmNicPartialCopyMdl

- ea: `0x140199c6c`
- end: `0x14019a330`
- name: `VmsVmNicPartialCopyMdl`
- size: `1732`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400468a0`

## callees

- `0x140006620`
- `0x14019807c`
- `0x140198ab0`
- `0x140199c6c`
- `0x1401bbc40`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140199dec`
- `ntoskrnl!MmSizeOfMdl` at `0x14019a118`
- `ntoskrnl!MmSizeOfMdl` at `0x140199dec`
- `ntoskrnl!MmSizeOfMdl` at `0x14019a118`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019a0cd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019a0cd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140199f92`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140199f92`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140199cd8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140199cd8`
- `ntoskrnl!IoBuildPartialMdl` at `0x14019a1b3`
- `ntoskrnl!IoBuildPartialMdl` at `0x14019a1b3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140199d3a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14019a262`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140199d3a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14019a262`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140199e0e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019a137`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140199e0e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019a137`

## pseudocode

```c
struct _MDL *__fastcall VmsVmNicPartialCopyMdl(__int64 a1, __int64 a2, struct _MDL *a3)
{
  struct _MDL *v3; // rdi
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  unsigned int v8; // esi
  __int64 v9; // r8
  unsigned int ByteCount; // r13d
  char *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdi
  ULONG v14; // ebp
  SIZE_T v15; // r15
  struct _LOOKASIDE_LIST_EX *ListIndex; // rax
  struct _MDL *v17; // rax
  struct _MDL *v18; // r14
  char *v19; // r10
  char *v20; // r11
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 *v24; // rdi
  __int64 v25; // rcx
  unsigned int v26; // eax
  _DWORD *v27; // r8
  unsigned int v28; // r15d
  _DWORD *v29; // rax
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r9
  volatile signed __int32 *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r9
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rdx
  unsigned __int64 v46; // rdi
  unsigned int v47; // eax
  struct _LOOKASIDE_LIST_EX *v48; // rax
  struct _MDL *v49; // rax
  unsigned int v50; // edx
  unsigned int v51; // ecx
  _DWORD *v52; // r8
  struct _MDL *v53; // rbx
  __int64 v54; // rsi
  unsigned int v55; // edi
  _DWORD *MappedSystemVa; // rax
  int v58; // [rsp+30h] [rbp-B8h]
  unsigned int v59; // [rsp+34h] [rbp-B4h]
  struct _MDL *v60; // [rsp+38h] [rbp-B0h]
  ULONG CurrentProcessorNumber; // [rsp+40h] [rbp-A8h]
  char *Src; // [rsp+48h] [rbp-A0h]
  int v63; // [rsp+50h] [rbp-98h]
  unsigned int v64; // [rsp+54h] [rbp-94h]
  unsigned int v65; // [rsp+58h] [rbp-90h]
  char *v66; // [rsp+60h] [rbp-88h]
  char *v67; // [rsp+68h] [rbp-80h]
  struct _MDL *v68; // [rsp+70h] [rbp-78h]
  _DWORD v70[8]; // [rsp+80h] [rbp-68h]

  v3 = 0;
  v60 = 0;
  if ( *(_DWORD *)(a1 + 384) >= VmsVmNicMaxSendShadowSizeInBytes )
    return v3;
  v6 = 0;
  v68 = 0;
  v58 = 0;
  v7 = 0;
  v59 = 0;
  v8 = 0;
  v65 = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
LABEL_3:
  if ( a3 )
  {
    ByteCount = a3->ByteCount;
    v64 = ByteCount;
    if ( v8 < ByteCount || (v11 = 0, v67 = 0, v6) )
    {
      v11 = (char *)((a3->MdlFlags & 5) != 0
                   ? a3->MappedSystemVa
                   : MmMapLockedPagesSpecifyCache(a3, 0, MmCached, 0, 0, 0x40000000u));
      v67 = v11;
      if ( !v11 )
      {
LABEL_91:
        if ( v68 )
        {
          VmsVmNicFreeShadowMdl(v3);
          return 0;
        }
        return v3;
      }
    }
    v12 = 0;
    while ( 1 )
    {
      v63 = v12;
      if ( !ByteCount )
      {
        a3 = a3->Next;
        goto LABEL_3;
      }
      if ( v8 )
      {
        v13 = (unsigned int)v12;
      }
      else
      {
        if ( ByteCount < 0x2C || v7 >= 8 )
          goto LABEL_91;
        v13 = (unsigned int)v12;
        if ( !v7 && *(_DWORD *)&v11[v12] != 1 )
          goto LABEL_90;
        v8 = *(_DWORD *)&v11[(unsigned int)v12 + 4];
        if ( v8 < 0x2C )
          goto LABEL_90;
        v6 = dword_1401F9944 + VmsSafeHeaderSize;
        v65 = v7 + 1;
        v58 = dword_1401F9944 + VmsSafeHeaderSize;
        v70[v7] = v8;
        if ( v8 < v6 )
        {
          v6 = v8;
          v58 = v8;
LABEL_22:
          v14 = ByteCount;
          if ( v6 < ByteCount )
            v14 = v6;
          v15 = MmSizeOfMdl((PVOID)0xFFF, v14);
          ListIndex = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(qword_1401FA2E0, CurrentProcessorNumber);
          v17 = (struct _MDL *)ExAllocateFromLookasideListEx(ListIndex);
          v18 = v17;
          if ( !v17 )
            goto LABEL_90;
          v19 = (char *)v17 + v15;
          v58 -= v14;
          v59 += dword_1401F9938;
          v66 = (char *)v17 + v15;
          v17->Next = 0;
          v17->MdlFlags = 0;
          v20 = &v67[v13];
          v17->Size = 8 * (((v14 + (((int)v17 + (int)v15) & 0xFFFuLL) + 4095) >> 12) + 6);
          v17->ByteOffset = ((_DWORD)v17 + v15) & 0xFFF;
          v17->ByteCount = v14;
          v17->StartVa = (void *)(((unsigned __int64)v17 + v15) & 0xFFFFFFFFFFFFF000uLL);
          v17->MappedSystemVa = (char *)v17 + v15;
          Src = &v67[v13];
          if ( !a2 )
            goto LABEL_62;
          v21 = *(_QWORD *)(a2 + 80);
          if ( *(_BYTE *)(v21 + 1) == 1 && !*(_BYTE *)(a2 + 4) )
          {
            v22 = *(unsigned int *)(a2 + 12);
            v23 = 0;
            *(_BYTE *)(a2 + 4) = 1;
            if ( (_DWORD)v22 != -1 )
            {
              v21 = *(_QWORD *)(v21 + 24);
              if ( v21 )
                v23 = v21 + 20 * v22;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v23 + 16), 1u);
          }
          v24 = (__int64 *)(a2 + 80);
          v25 = *(_QWORD *)(a2 + 80);
          v26 = *(_DWORD *)(v25 + 4);
          if ( !v26 )
          {
            if ( *(_DWORD *)(a2 + 20) )
            {
              LOBYTE(v21) = 1;
              BLFlushBatchOpContextEx(a2, v21, 0);
              v19 = v66;
              v20 = Src;
            }
            if ( (*(_BYTE *)(a2 + 8) & 5) == 5 || (*(_BYTE *)(a2 + 8) & 6) == 6 )
            {
              (*(void (**)(void))(*v24 + 32))();
              memmove((char *)v18 + v15, Src, v14);
              (*(void (**)(void))(*v24 + 40))();
LABEL_63:
              MmBuildMdlForNonPagedPool(v18);
              ByteCount = v64;
              goto LABEL_73;
            }
LABEL_62:
            memmove(v19, v20, v14);
            goto LABEL_63;
          }
          v27 = *(_DWORD **)(a2 + 32);
          v28 = v27[2];
          if ( v28 >= v27[3] )
          {
            v28 = 0;
            if ( *(_DWORD *)(a2 + 16) >= v26 )
            {
              LOBYTE(v21) = 1;
              goto LABEL_41;
            }
            v29 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v25 + 64));
            v27 = v29;
            if ( v29 )
            {
              *(_QWORD *)v29 = 0;
              v29[2] = 0;
              v30 = *(_DWORD *)(*v24 + 8);
              *((_QWORD *)v29 + 2) = v29 + 6;
              v29[3] = v30;
              **(_QWORD **)(a2 + 32) = v29;
              v31 = *v24;
              ++*(_DWORD *)(a2 + 16);
              *(_QWORD *)(a2 + 32) = v29;
              if ( *(_BYTE *)(v31 + 1) == 1 )
              {
                v32 = *(unsigned int *)(a2 + 12);
                v33 = 0;
                if ( (_DWORD)v32 != -1 )
                {
                  v34 = *(_QWORD *)(v31 + 24);
                  if ( v34 )
                    v33 = v34 + 20 * v32;
                }
                _InterlockedAdd16((volatile signed __int16 *)(v33 + 12), 1u);
                v35 = *(unsigned int *)(a2 + 12);
                v36 = 0;
                if ( (_DWORD)v35 != -1 )
                {
                  v37 = *(_QWORD *)(*v24 + 24);
                  if ( v37 )
                    v36 = (volatile signed __int32 *)(v37 + 20 * v35);
                }
                _InterlockedAdd(v36, 1u);
              }
            }
            else
            {
              v21 = 1;
LABEL_41:
              BLFlushBatchOpContextEx(a2, v21, 0);
              v27 = (_DWORD *)(a2 + 56);
            }
            v20 = Src;
            v19 = v66;
          }
          ++*(_DWORD *)(a2 + 20);
          ++v27[2];
          if ( *(_BYTE *)(*v24 + 1) == 1 )
          {
            v38 = *(unsigned int *)(a2 + 12);
            v39 = 0;
            if ( (_DWORD)v38 != -1 )
            {
              v40 = *(_QWORD *)(*v24 + 24);
              if ( v40 )
                v39 = v40 + 20 * v38;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v39 + 14), 1u);
            v41 = *(unsigned int *)(a2 + 12);
            v42 = 0;
            if ( (_DWORD)v41 != -1 )
            {
              v43 = *(_QWORD *)(*v24 + 24);
              if ( v43 )
                v42 = v43 + 20 * v41;
            }
            _InterlockedAdd((volatile signed __int32 *)(v42 + 4), 1u);
          }
          v44 = *((_QWORD *)v27 + 2);
          v45 = 3LL * v28;
          *(_QWORD *)(v44 + 8 * v45) = v19;
          *(_QWORD *)(v44 + 8 * v45 + 8) = v20;
          *(_DWORD *)(v44 + 8 * v45 + 16) = (16 * v14) | 1;
          goto LABEL_63;
        }
      }
      if ( v6 )
        goto LABEL_22;
      v46 = (unsigned __int64)a3->StartVa + a3->ByteOffset + v13;
      v47 = ByteCount;
      if ( v8 < ByteCount )
        v47 = v8;
      if ( v47 >= 0x40000 )
      {
        v14 = 0x40000;
      }
      else
      {
        v14 = ByteCount;
        if ( v8 < ByteCount )
          v14 = v8;
      }
      MmSizeOfMdl((PVOID)v46, v14);
      v48 = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(qword_1401FA2E8, CurrentProcessorNumber);
      v49 = (struct _MDL *)ExAllocateFromLookasideListEx(v48);
      v18 = v49;
      if ( !v49 )
        goto LABEL_90;
      v59 += dword_1401F993C;
      v49->Next = 0;
      v49->ByteCount = v14;
      v49->MdlFlags = 0;
      v49->Size = 8 * (((v14 + (v46 & 0xFFF) + 4095) >> 12) + 6);
      v49->ByteOffset = v46 & 0xFFF;
      v49->StartVa = (void *)(v46 & 0xFFFFFFFFFFFFF000uLL);
      IoBuildPartialMdl(a3, v49, (PVOID)v46, v14);
LABEL_73:
      v3 = v60;
      if ( v60 )
      {
        v68->Next = v18;
      }
      else
      {
        v3 = v18;
        v60 = v18;
      }
      ByteCount -= v14;
      v11 = v67;
      v12 = v14 + v63;
      v8 -= v14;
      v68 = v18;
      v7 = v65;
      v6 = v58;
      v64 = ByteCount;
    }
  }
  LOBYTE(v9) = 1;
  BLFlushBatchOpContextEx(a2, 0, v9);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = v3;
  v54 = 0;
  while ( v53 )
  {
    v55 = v53->ByteCount;
    if ( !v50
      && ((v53->MdlFlags & 5) == 0
        ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(v53, 0, MmCached, 0, 0, 0x40000000u))
        : (MappedSystemVa = v53->MappedSystemVa),
          (v50 = v70[v54], v52 = MappedSystemVa + 1, v50 != MappedSystemVa[1])
       || (v54 = (unsigned int)(v54 + 1), v51 = MappedSystemVa[2] + MappedSystemVa[3] + 8, v51 > v50))
      || v55 > v50 )
    {
LABEL_90:
      v3 = v60;
      goto LABEL_91;
    }
    v50 -= v55;
    if ( v51 < v55 )
    {
      v53->ByteCount = v51;
      *v52 += v51 - v55;
    }
    v51 -= v53->ByteCount;
    v53 = v53->Next;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 384), v59);
  v3 = v60;
  if ( (VmsDiagnosticFlags & 4) != 0 )
    _InterlockedAdd((volatile signed __int32 *)VmsPlanCpuTable + 1360 * CurrentProcessorNumber + 124, v59);
  return v3;
}

```

## disassembly

```asm
0x140199c6c  mov     [rsp+arg_18], rbx
0x140199c71  push    rbp
0x140199c72  push    rsi
0x140199c73  push    rdi
0x140199c74  push    r12
0x140199c76  push    r13
0x140199c78  push    r14
0x140199c7a  push    r15
0x140199c7c  sub     rsp, 0B0h
0x140199c83  mov     rax, cs:__security_cookie
0x140199c8a  xor     rax, rsp
0x140199c8d  mov     [rsp+0E8h+var_48], rax
0x140199c95  mov     eax, [rcx+180h]
0x140199c9b  xor     edi, edi
0x140199c9d  cmp     eax, cs:VmsVmNicMaxSendShadowSizeInBytes
0x140199ca3  mov     r12, r8
0x140199ca6  mov     rbx, rdx
0x140199ca9  mov     [rsp+0E8h+var_70], rcx
0x140199cae  mov     [rsp+0E8h+var_B0], rdi
0x140199cb3  jge     loc_14019A301
0x140199cb9  xor     r14d, r14d
0x140199cbc  mov     [rsp+0E8h+var_78], rdi
0x140199cc1  xor     r15d, r15d
0x140199cc4  mov     [rsp+0E8h+var_B8], r14d
0x140199cc9  xor     ebp, ebp
0x140199ccb  mov     [rsp+0E8h+var_B4], r15d
0x140199cd0  xor     esi, esi
0x140199cd2  mov     [rsp+0E8h+var_90], ebp
0x140199cd6  xor     ecx, ecx; ProcNumber
0x140199cd8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140199cdf  nop     dword ptr [rax+rax+00h]
0x140199ce4  mov     [rsp+0E8h+var_A8], eax
0x140199ce8  lea     r15d, [rdi+1]
0x140199cec  test    r12, r12
0x140199cef  jz      loc_14019A212
0x140199cf5  mov     r13d, [r12+28h]
0x140199cfa  mov     [rsp+0E8h+var_94], r13d
0x140199cff  cmp     esi, r13d
0x140199d02  jb      short loc_140199D10
0x140199d04  xor     ecx, ecx
0x140199d06  mov     [rsp+0E8h+var_80], rcx
0x140199d0b  test    r14d, r14d
0x140199d0e  jz      short loc_140199D57
0x140199d10  test    byte ptr [r12+0Ah], 5
0x140199d16  jz      short loc_140199D1F
0x140199d18  mov     rcx, [r12+18h]
0x140199d1d  jmp     short loc_140199D49
0x140199d1f  mov     [rsp+0E8h+Priority], 40000000h; Priority
0x140199d27  xor     r9d, r9d; RequestedAddress
0x140199d2a  mov     r8d, r15d; CacheType
0x140199d2d  mov     [rsp+0E8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140199d35  xor     edx, edx; AccessMode
0x140199d37  mov     rcx, r12; MemoryDescriptorList
0x140199d3a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140199d41  nop     dword ptr [rax+rax+00h]
0x140199d46  mov     rcx, rax
0x140199d49  mov     [rsp+0E8h+var_80], rcx
0x140199d4e  test    rcx, rcx
0x140199d51  jz      loc_14019A2AF
0x140199d57  xor     eax, eax
0x140199d59  mov     [rsp+0E8h+var_98], eax
0x140199d5d  test    r13d, r13d
0x140199d60  jz      loc_14019A209
0x140199d66  test    esi, esi
0x140199d68  jnz     short loc_140199DCD
0x140199d6a  cmp     r13d, 2Ch ; ','
0x140199d6e  jb      loc_14019A2AF
0x140199d74  cmp     ebp, 8
0x140199d77  jnb     loc_14019A2AF
0x140199d7d  mov     edi, eax
0x140199d7f  test    ebp, ebp
0x140199d81  jnz     short loc_140199D8F
0x140199d83  mov     eax, [rax+rcx]
0x140199d86  cmp     eax, r15d
0x140199d89  jnz     loc_14019A2AA
0x140199d8f  mov     esi, [rdi+rcx+4]
0x140199d93  cmp     esi, 2Ch ; ','
0x140199d96  jb      loc_14019A2AA
0x140199d9c  mov     r14d, cs:VmsSafeHeaderSize
0x140199da3  add     r14d, cs:dword_1401F9944
0x140199daa  mov     eax, ebp
0x140199dac  add     ebp, r15d
0x140199daf  mov     [rsp+0E8h+var_90], ebp
0x140199db3  mov     [rsp+0E8h+var_B8], r14d
0x140199db8  mov     [rsp+rax*4+0E8h+var_68], esi
0x140199dbf  cmp     esi, r14d
0x140199dc2  jnb     short loc_140199DCF
0x140199dc4  mov     r14d, esi
0x140199dc7  mov     [rsp+0E8h+var_B8], esi
0x140199dcb  jmp     short loc_140199DD8
0x140199dcd  mov     edi, eax
0x140199dcf  test    r14d, r14d
0x140199dd2  jz      loc_14019A0E3
0x140199dd8  cmp     r14d, r13d
0x140199ddb  mov     ebp, r13d
0x140199dde  mov     ecx, 0FFFh; Base
0x140199de3  cmovb   ebp, r14d
0x140199de7  mov     edx, ebp; Length
0x140199de9  mov     r13d, ebp
0x140199dec  call    cs:__imp_MmSizeOfMdl
0x140199df3  nop     dword ptr [rax+rax+00h]
0x140199df8  mov     edx, [rsp+0E8h+var_A8]
0x140199dfc  mov     r15, rax
0x140199dff  mov     rcx, cs:qword_1401FA2E0
0x140199e06  call    PplpRetrieveListIndex
0x140199e0b  mov     rcx, rax; Lookaside
0x140199e0e  call    cs:__imp_ExAllocateFromLookasideListEx
0x140199e15  nop     dword ptr [rax+rax+00h]
0x140199e1a  mov     r14, rax
0x140199e1d  test    rax, rax
0x140199e20  jz      loc_14019A2AA
0x140199e26  mov     eax, [rsp+0E8h+var_B4]
0x140199e2a  lea     r10, [r14+r15]
0x140199e2e  add     eax, cs:dword_1401F9938
0x140199e34  mov     r9d, 0FFFh
0x140199e3a  mov     r11, [rsp+0E8h+var_80]
0x140199e3f  mov     r8d, r10d
0x140199e42  sub     [rsp+0E8h+var_B8], ebp
0x140199e46  mov     edx, r8d
0x140199e49  and     rdx, r9
0x140199e4c  mov     [rsp+0E8h+var_B4], eax
0x140199e50  add     rdx, r9
0x140199e53  mov     [rsp+0E8h+var_88], r10
0x140199e58  add     rdx, r13
0x140199e5b  mov     qword ptr [r14], 0
0x140199e62  xor     eax, eax
0x140199e64  shr     rdx, 0Ch
0x140199e68  mov     [r14+0Ah], ax
0x140199e6d  add     dx, 6
0x140199e71  shl     dx, 3
0x140199e75  and     r8d, r9d
0x140199e78  add     r11, rdi
0x140199e7b  mov     [r14+8], dx
0x140199e80  mov     rax, r10
0x140199e83  mov     [r14+2Ch], r8d
0x140199e87  and     rax, 0FFFFFFFFFFFFF000h
0x140199e8d  mov     [r14+28h], ebp
0x140199e91  mov     [r14+20h], rax
0x140199e95  mov     [r14+18h], r10
0x140199e99  mov     [rsp+0E8h+Src], r11
0x140199e9e  test    rbx, rbx
0x140199ea1  jz      loc_14019A0BC
0x140199ea7  mov     rdx, [rbx+50h]
0x140199eab  mov     r9d, 1
0x140199eb1  cmp     [rdx+1], r9b
0x140199eb5  jnz     short loc_140199EE2
0x140199eb7  cmp     byte ptr [rbx+4], 0
0x140199ebb  jnz     short loc_140199EE2
0x140199ebd  mov     ecx, [rbx+0Ch]
0x140199ec0  xor     eax, eax
0x140199ec2  mov     [rbx+4], r9b
0x140199ec6  cmp     ecx, 0FFFFFFFFh
0x140199ec9  jz      short loc_140199EDC
0x140199ecb  mov     rdx, [rdx+18h]
0x140199ecf  test    rdx, rdx
0x140199ed2  jz      short loc_140199EDC
0x140199ed4  lea     rcx, [rcx+rcx*4]
0x140199ed8  lea     rax, [rdx+rcx*4]
0x140199edc  lock add [rax+10h], r9w
0x140199ee2  lea     rdi, [rbx+50h]
0x140199ee6  mov     rcx, [rdi]
0x140199ee9  mov     eax, [rcx+4]
0x140199eec  test    eax, eax
0x140199eee  jnz     short loc_140199F57
0x140199ef0  cmp     [rbx+14h], eax
0x140199ef3  jz      short loc_140199F0D
0x140199ef5  xor     r8d, r8d
0x140199ef8  mov     dl, r9b
0x140199efb  mov     rcx, rbx
0x140199efe  call    BLFlushBatchOpContextEx
0x140199f03  mov     r10, [rsp+0E8h+var_88]
0x140199f08  mov     r11, [rsp+0E8h+Src]
0x140199f0d  mov     eax, [rbx+8]
0x140199f10  and     eax, 5
0x140199f13  cmp     al, 5
0x140199f15  jz      short loc_140199F29
0x140199f17  mov     eax, [rbx+8]
0x140199f1a  mov     ecx, 6
0x140199f1f  and     eax, ecx
0x140199f21  cmp     al, cl
0x140199f23  jnz     loc_14019A0BC
0x140199f29  mov     rax, [rdi]
0x140199f2c  mov     rax, [rax+20h]
0x140199f30  call    _guard_dispatch_icall
0x140199f35  mov     rdx, [rsp+0E8h+Src]; Src
0x140199f3a  lea     rcx, [r14+r15]; void *
0x140199f3e  mov     r8, r13; Size
0x140199f41  call    memmove
0x140199f46  mov     rax, [rdi]
0x140199f49  mov     rax, [rax+28h]
0x140199f4d  call    _guard_dispatch_icall
0x140199f52  jmp     loc_14019A0CA
0x140199f57  mov     r8, [rbx+20h]
0x140199f5b  mov     r15d, [r8+8]
0x140199f5f  cmp     r15d, [r8+0Ch]
0x140199f63  jb      loc_14019A037
0x140199f69  xor     r15d, r15d
0x140199f6c  cmp     [rbx+10h], eax
0x140199f6f  jb      short loc_140199F8E
0x140199f71  mov     dl, r9b
0x140199f74  xor     r8d, r8d
0x140199f77  mov     rcx, rbx
0x140199f7a  call    BLFlushBatchOpContextEx
0x140199f7f  lea     r8, [rbx+38h]
0x140199f83  mov     r9d, 1
0x140199f89  jmp     loc_14019A02D
0x140199f8e  add     rcx, 40h ; '@'; Lookaside
0x140199f92  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140199f99  nop     dword ptr [rax+rax+00h]
0x140199f9e  mov     r8, rax
0x140199fa1  test    rax, rax
0x140199fa4  jnz     short loc_140199FAB
0x140199fa6  lea     edx, [rax+1]
0x140199fa9  jmp     short loc_140199F74
0x140199fab  mov     [rax], r15
0x140199fae  mov     r9d, 1
0x140199fb4  mov     [rax+8], r15d
0x140199fb8  mov     rax, [rdi]
0x140199fbb  mov     ecx, [rax+8]
0x140199fbe  lea     rax, [r8+18h]
0x140199fc2  mov     [r8+10h], rax
0x140199fc6  mov     [r8+0Ch], ecx
0x140199fca  mov     rax, [rbx+20h]
0x140199fce  mov     [rax], r8
0x140199fd1  mov     rdx, [rdi]
0x140199fd4  add     [rbx+10h], r9d
0x140199fd8  mov     [rbx+20h], r8
0x140199fdc  cmp     [rdx+1], r9b
0x140199fe0  jnz     short loc_14019A02D
0x140199fe2  mov     ecx, [rbx+0Ch]
0x140199fe5  xor     eax, eax
0x140199fe7  cmp     ecx, 0FFFFFFFFh
0x140199fea  jz      short loc_140199FFD
0x140199fec  mov     rdx, [rdx+18h]
0x140199ff0  test    rdx, rdx
0x140199ff3  jz      short loc_140199FFD
0x140199ff5  lea     rcx, [rcx+rcx*4]
0x140199ff9  lea     rax, [rdx+rcx*4]
0x140199ffd  lock add [rax+0Ch], r9w
0x14019a003  mov     r9d, [rbx+0Ch]
0x14019a007  xor     ecx, ecx
0x14019a009  cmp     r9d, 0FFFFFFFFh
0x14019a00d  jz      short loc_14019A023
0x14019a00f  mov     rax, [rdi]
0x14019a012  mov     rdx, [rax+18h]
0x14019a016  test    rdx, rdx
0x14019a019  jz      short loc_14019A023
0x14019a01b  lea     rcx, [r9+r9*4]
0x14019a01f  lea     rcx, [rdx+rcx*4]
0x14019a023  mov     r9d, 1
0x14019a029  lock add [rcx], r9d
0x14019a02d  mov     r11, [rsp+0E8h+Src]
0x14019a032  mov     r10, [rsp+0E8h+var_88]
0x14019a037  add     [rbx+14h], r9d
0x14019a03b  add     [r8+8], r9d
0x14019a03f  mov     rcx, [rdi]
0x14019a042  cmp     [rcx+1], r9b
0x14019a046  jnz     short loc_14019A09A
0x14019a048  mov     r9d, [rbx+0Ch]
0x14019a04c  xor     eax, eax
0x14019a04e  cmp     r9d, 0FFFFFFFFh
0x14019a052  jz      short loc_14019A065
0x14019a054  mov     rdx, [rcx+18h]
0x14019a058  test    rdx, rdx
0x14019a05b  jz      short loc_14019A065
0x14019a05d  lea     rcx, [r9+r9*4]
0x14019a061  lea     rax, [rdx+rcx*4]
0x14019a065  mov     ecx, 1
0x14019a06a  lock add [rax+0Eh], cx
0x14019a06f  mov     r9d, [rbx+0Ch]
0x14019a073  xor     ecx, ecx
0x14019a075  cmp     r9d, 0FFFFFFFFh
0x14019a079  jz      short loc_14019A08F
0x14019a07b  mov     rax, [rdi]
0x14019a07e  mov     rdx, [rax+18h]
0x14019a082  test    rdx, rdx
0x14019a085  jz      short loc_14019A08F
0x14019a087  lea     rcx, [r9+r9*4]
0x14019a08b  lea     rcx, [rdx+rcx*4]
0x14019a08f  mov     r9d, 1
0x14019a095  lock add [rcx+4], r9d
0x14019a09a  mov     rcx, [r8+10h]
0x14019a09e  mov     eax, r15d
0x14019a0a1  lea     rdx, [rax+rax*2]
0x14019a0a5  mov     eax, ebp
0x14019a0a7  mov     [rcx+rdx*8], r10
0x14019a0ab  shl     eax, 4
0x14019a0ae  or      eax, r9d
0x14019a0b1  mov     [rcx+rdx*8+8], r11
0x14019a0b6  mov     [rcx+rdx*8+10h], eax
0x14019a0ba  jmp     short loc_14019A0CA
0x14019a0bc  mov     r8, r13; Size
0x14019a0bf  mov     rdx, r11; Src
0x14019a0c2  mov     rcx, r10; void *
0x14019a0c5  call    memmove
0x14019a0ca  mov     rcx, r14; MemoryDescriptorList
0x14019a0cd  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14019a0d4  nop     dword ptr [rax+rax+00h]
0x14019a0d9  mov     r13d, [rsp+0E8h+var_94]
0x14019a0de  jmp     loc_14019A1BF
  ... truncated ...
```
