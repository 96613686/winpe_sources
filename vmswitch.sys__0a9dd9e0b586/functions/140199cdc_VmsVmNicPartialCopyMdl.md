# VmsVmNicPartialCopyMdl

- ea: `0x140199cdc`
- end: `0x14019a3a0`
- name: `VmsVmNicPartialCopyMdl`
- size: `1732`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400468a0`

## callees

- `0x140006620`
- `0x1401980ec`
- `0x140198b20`
- `0x140199cdc`
- `0x1401bbcb0`
- `0x1401bbe80`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140199e5c`
- `ntoskrnl!MmSizeOfMdl` at `0x14019a188`
- `ntoskrnl!MmSizeOfMdl` at `0x140199e5c`
- `ntoskrnl!MmSizeOfMdl` at `0x14019a188`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019a13d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14019a13d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14019a002`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14019a002`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140199d48`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140199d48`
- `ntoskrnl!IoBuildPartialMdl` at `0x14019a223`
- `ntoskrnl!IoBuildPartialMdl` at `0x14019a223`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140199daa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14019a2d2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140199daa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14019a2d2`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140199e7e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019a1a7`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140199e7e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14019a1a7`

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
          ListIndex = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(qword_1401FA2E8, CurrentProcessorNumber);
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
      v48 = (struct _LOOKASIDE_LIST_EX *)PplpRetrieveListIndex(qword_1401FA2E0, CurrentProcessorNumber);
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
0x140199cdc  mov     [rsp+arg_18], rbx
0x140199ce1  push    rbp
0x140199ce2  push    rsi
0x140199ce3  push    rdi
0x140199ce4  push    r12
0x140199ce6  push    r13
0x140199ce8  push    r14
0x140199cea  push    r15
0x140199cec  sub     rsp, 0B0h
0x140199cf3  mov     rax, cs:__security_cookie
0x140199cfa  xor     rax, rsp
0x140199cfd  mov     [rsp+0E8h+var_48], rax
0x140199d05  mov     eax, [rcx+180h]
0x140199d0b  xor     edi, edi
0x140199d0d  cmp     eax, cs:VmsVmNicMaxSendShadowSizeInBytes
0x140199d13  mov     r12, r8
0x140199d16  mov     rbx, rdx
0x140199d19  mov     [rsp+0E8h+var_70], rcx
0x140199d1e  mov     [rsp+0E8h+var_B0], rdi
0x140199d23  jge     loc_14019A371
0x140199d29  xor     r14d, r14d
0x140199d2c  mov     [rsp+0E8h+var_78], rdi
0x140199d31  xor     r15d, r15d
0x140199d34  mov     [rsp+0E8h+var_B8], r14d
0x140199d39  xor     ebp, ebp
0x140199d3b  mov     [rsp+0E8h+var_B4], r15d
0x140199d40  xor     esi, esi
0x140199d42  mov     [rsp+0E8h+var_90], ebp
0x140199d46  xor     ecx, ecx; ProcNumber
0x140199d48  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140199d4f  nop     dword ptr [rax+rax+00h]
0x140199d54  mov     [rsp+0E8h+var_A8], eax
0x140199d58  lea     r15d, [rdi+1]
0x140199d5c  test    r12, r12
0x140199d5f  jz      loc_14019A282
0x140199d65  mov     r13d, [r12+28h]
0x140199d6a  mov     [rsp+0E8h+var_94], r13d
0x140199d6f  cmp     esi, r13d
0x140199d72  jb      short loc_140199D80
0x140199d74  xor     ecx, ecx
0x140199d76  mov     [rsp+0E8h+var_80], rcx
0x140199d7b  test    r14d, r14d
0x140199d7e  jz      short loc_140199DC7
0x140199d80  test    byte ptr [r12+0Ah], 5
0x140199d86  jz      short loc_140199D8F
0x140199d88  mov     rcx, [r12+18h]
0x140199d8d  jmp     short loc_140199DB9
0x140199d8f  mov     [rsp+0E8h+Priority], 40000000h; Priority
0x140199d97  xor     r9d, r9d; RequestedAddress
0x140199d9a  mov     r8d, r15d; CacheType
0x140199d9d  mov     [rsp+0E8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140199da5  xor     edx, edx; AccessMode
0x140199da7  mov     rcx, r12; MemoryDescriptorList
0x140199daa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140199db1  nop     dword ptr [rax+rax+00h]
0x140199db6  mov     rcx, rax
0x140199db9  mov     [rsp+0E8h+var_80], rcx
0x140199dbe  test    rcx, rcx
0x140199dc1  jz      loc_14019A31F
0x140199dc7  xor     eax, eax
0x140199dc9  mov     [rsp+0E8h+var_98], eax
0x140199dcd  test    r13d, r13d
0x140199dd0  jz      loc_14019A279
0x140199dd6  test    esi, esi
0x140199dd8  jnz     short loc_140199E3D
0x140199dda  cmp     r13d, 2Ch ; ','
0x140199dde  jb      loc_14019A31F
0x140199de4  cmp     ebp, 8
0x140199de7  jnb     loc_14019A31F
0x140199ded  mov     edi, eax
0x140199def  test    ebp, ebp
0x140199df1  jnz     short loc_140199DFF
0x140199df3  mov     eax, [rax+rcx]
0x140199df6  cmp     eax, r15d
0x140199df9  jnz     loc_14019A31A
0x140199dff  mov     esi, [rdi+rcx+4]
0x140199e03  cmp     esi, 2Ch ; ','
0x140199e06  jb      loc_14019A31A
0x140199e0c  mov     r14d, cs:VmsSafeHeaderSize
0x140199e13  add     r14d, cs:dword_1401F9944
0x140199e1a  mov     eax, ebp
0x140199e1c  add     ebp, r15d
0x140199e1f  mov     [rsp+0E8h+var_90], ebp
0x140199e23  mov     [rsp+0E8h+var_B8], r14d
0x140199e28  mov     [rsp+rax*4+0E8h+var_68], esi
0x140199e2f  cmp     esi, r14d
0x140199e32  jnb     short loc_140199E3F
0x140199e34  mov     r14d, esi
0x140199e37  mov     [rsp+0E8h+var_B8], esi
0x140199e3b  jmp     short loc_140199E48
0x140199e3d  mov     edi, eax
0x140199e3f  test    r14d, r14d
0x140199e42  jz      loc_14019A153
0x140199e48  cmp     r14d, r13d
0x140199e4b  mov     ebp, r13d
0x140199e4e  mov     ecx, 0FFFh; Base
0x140199e53  cmovb   ebp, r14d
0x140199e57  mov     edx, ebp; Length
0x140199e59  mov     r13d, ebp
0x140199e5c  call    cs:__imp_MmSizeOfMdl
0x140199e63  nop     dword ptr [rax+rax+00h]
0x140199e68  mov     edx, [rsp+0E8h+var_A8]
0x140199e6c  mov     r15, rax
0x140199e6f  mov     rcx, cs:qword_1401FA2E8
0x140199e76  call    PplpRetrieveListIndex
0x140199e7b  mov     rcx, rax; Lookaside
0x140199e7e  call    cs:__imp_ExAllocateFromLookasideListEx
0x140199e85  nop     dword ptr [rax+rax+00h]
0x140199e8a  mov     r14, rax
0x140199e8d  test    rax, rax
0x140199e90  jz      loc_14019A31A
0x140199e96  mov     eax, [rsp+0E8h+var_B4]
0x140199e9a  lea     r10, [r14+r15]
0x140199e9e  add     eax, cs:dword_1401F9938
0x140199ea4  mov     r9d, 0FFFh
0x140199eaa  mov     r11, [rsp+0E8h+var_80]
0x140199eaf  mov     r8d, r10d
0x140199eb2  sub     [rsp+0E8h+var_B8], ebp
0x140199eb6  mov     edx, r8d
0x140199eb9  and     rdx, r9
0x140199ebc  mov     [rsp+0E8h+var_B4], eax
0x140199ec0  add     rdx, r9
0x140199ec3  mov     [rsp+0E8h+var_88], r10
0x140199ec8  add     rdx, r13
0x140199ecb  mov     qword ptr [r14], 0
0x140199ed2  xor     eax, eax
0x140199ed4  shr     rdx, 0Ch
0x140199ed8  mov     [r14+0Ah], ax
0x140199edd  add     dx, 6
0x140199ee1  shl     dx, 3
0x140199ee5  and     r8d, r9d
0x140199ee8  add     r11, rdi
0x140199eeb  mov     [r14+8], dx
0x140199ef0  mov     rax, r10
0x140199ef3  mov     [r14+2Ch], r8d
0x140199ef7  and     rax, 0FFFFFFFFFFFFF000h
0x140199efd  mov     [r14+28h], ebp
0x140199f01  mov     [r14+20h], rax
0x140199f05  mov     [r14+18h], r10
0x140199f09  mov     [rsp+0E8h+Src], r11
0x140199f0e  test    rbx, rbx
0x140199f11  jz      loc_14019A12C
0x140199f17  mov     rdx, [rbx+50h]
0x140199f1b  mov     r9d, 1
0x140199f21  cmp     [rdx+1], r9b
0x140199f25  jnz     short loc_140199F52
0x140199f27  cmp     byte ptr [rbx+4], 0
0x140199f2b  jnz     short loc_140199F52
0x140199f2d  mov     ecx, [rbx+0Ch]
0x140199f30  xor     eax, eax
0x140199f32  mov     [rbx+4], r9b
0x140199f36  cmp     ecx, 0FFFFFFFFh
0x140199f39  jz      short loc_140199F4C
0x140199f3b  mov     rdx, [rdx+18h]
0x140199f3f  test    rdx, rdx
0x140199f42  jz      short loc_140199F4C
0x140199f44  lea     rcx, [rcx+rcx*4]
0x140199f48  lea     rax, [rdx+rcx*4]
0x140199f4c  lock add [rax+10h], r9w
0x140199f52  lea     rdi, [rbx+50h]
0x140199f56  mov     rcx, [rdi]
0x140199f59  mov     eax, [rcx+4]
0x140199f5c  test    eax, eax
0x140199f5e  jnz     short loc_140199FC7
0x140199f60  cmp     [rbx+14h], eax
0x140199f63  jz      short loc_140199F7D
0x140199f65  xor     r8d, r8d
0x140199f68  mov     dl, r9b
0x140199f6b  mov     rcx, rbx
0x140199f6e  call    BLFlushBatchOpContextEx
0x140199f73  mov     r10, [rsp+0E8h+var_88]
0x140199f78  mov     r11, [rsp+0E8h+Src]
0x140199f7d  mov     eax, [rbx+8]
0x140199f80  and     eax, 5
0x140199f83  cmp     al, 5
0x140199f85  jz      short loc_140199F99
0x140199f87  mov     eax, [rbx+8]
0x140199f8a  mov     ecx, 6
0x140199f8f  and     eax, ecx
0x140199f91  cmp     al, cl
0x140199f93  jnz     loc_14019A12C
0x140199f99  mov     rax, [rdi]
0x140199f9c  mov     rax, [rax+20h]
0x140199fa0  call    _guard_dispatch_icall
0x140199fa5  mov     rdx, [rsp+0E8h+Src]; Src
0x140199faa  lea     rcx, [r14+r15]; void *
0x140199fae  mov     r8, r13; Size
0x140199fb1  call    memmove
0x140199fb6  mov     rax, [rdi]
0x140199fb9  mov     rax, [rax+28h]
0x140199fbd  call    _guard_dispatch_icall
0x140199fc2  jmp     loc_14019A13A
0x140199fc7  mov     r8, [rbx+20h]
0x140199fcb  mov     r15d, [r8+8]
0x140199fcf  cmp     r15d, [r8+0Ch]
0x140199fd3  jb      loc_14019A0A7
0x140199fd9  xor     r15d, r15d
0x140199fdc  cmp     [rbx+10h], eax
0x140199fdf  jb      short loc_140199FFE
0x140199fe1  mov     dl, r9b
0x140199fe4  xor     r8d, r8d
0x140199fe7  mov     rcx, rbx
0x140199fea  call    BLFlushBatchOpContextEx
0x140199fef  lea     r8, [rbx+38h]
0x140199ff3  mov     r9d, 1
0x140199ff9  jmp     loc_14019A09D
0x140199ffe  add     rcx, 40h ; '@'; Lookaside
0x14019a002  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14019a009  nop     dword ptr [rax+rax+00h]
0x14019a00e  mov     r8, rax
0x14019a011  test    rax, rax
0x14019a014  jnz     short loc_14019A01B
0x14019a016  lea     edx, [rax+1]
0x14019a019  jmp     short loc_140199FE4
0x14019a01b  mov     [rax], r15
0x14019a01e  mov     r9d, 1
0x14019a024  mov     [rax+8], r15d
0x14019a028  mov     rax, [rdi]
0x14019a02b  mov     ecx, [rax+8]
0x14019a02e  lea     rax, [r8+18h]
0x14019a032  mov     [r8+10h], rax
0x14019a036  mov     [r8+0Ch], ecx
0x14019a03a  mov     rax, [rbx+20h]
0x14019a03e  mov     [rax], r8
0x14019a041  mov     rdx, [rdi]
0x14019a044  add     [rbx+10h], r9d
0x14019a048  mov     [rbx+20h], r8
0x14019a04c  cmp     [rdx+1], r9b
0x14019a050  jnz     short loc_14019A09D
0x14019a052  mov     ecx, [rbx+0Ch]
0x14019a055  xor     eax, eax
0x14019a057  cmp     ecx, 0FFFFFFFFh
0x14019a05a  jz      short loc_14019A06D
0x14019a05c  mov     rdx, [rdx+18h]
0x14019a060  test    rdx, rdx
0x14019a063  jz      short loc_14019A06D
0x14019a065  lea     rcx, [rcx+rcx*4]
0x14019a069  lea     rax, [rdx+rcx*4]
0x14019a06d  lock add [rax+0Ch], r9w
0x14019a073  mov     r9d, [rbx+0Ch]
0x14019a077  xor     ecx, ecx
0x14019a079  cmp     r9d, 0FFFFFFFFh
0x14019a07d  jz      short loc_14019A093
0x14019a07f  mov     rax, [rdi]
0x14019a082  mov     rdx, [rax+18h]
0x14019a086  test    rdx, rdx
0x14019a089  jz      short loc_14019A093
0x14019a08b  lea     rcx, [r9+r9*4]
0x14019a08f  lea     rcx, [rdx+rcx*4]
0x14019a093  mov     r9d, 1
0x14019a099  lock add [rcx], r9d
0x14019a09d  mov     r11, [rsp+0E8h+Src]
0x14019a0a2  mov     r10, [rsp+0E8h+var_88]
0x14019a0a7  add     [rbx+14h], r9d
0x14019a0ab  add     [r8+8], r9d
0x14019a0af  mov     rcx, [rdi]
0x14019a0b2  cmp     [rcx+1], r9b
0x14019a0b6  jnz     short loc_14019A10A
0x14019a0b8  mov     r9d, [rbx+0Ch]
0x14019a0bc  xor     eax, eax
0x14019a0be  cmp     r9d, 0FFFFFFFFh
0x14019a0c2  jz      short loc_14019A0D5
0x14019a0c4  mov     rdx, [rcx+18h]
0x14019a0c8  test    rdx, rdx
0x14019a0cb  jz      short loc_14019A0D5
0x14019a0cd  lea     rcx, [r9+r9*4]
0x14019a0d1  lea     rax, [rdx+rcx*4]
0x14019a0d5  mov     ecx, 1
0x14019a0da  lock add [rax+0Eh], cx
0x14019a0df  mov     r9d, [rbx+0Ch]
0x14019a0e3  xor     ecx, ecx
0x14019a0e5  cmp     r9d, 0FFFFFFFFh
0x14019a0e9  jz      short loc_14019A0FF
0x14019a0eb  mov     rax, [rdi]
0x14019a0ee  mov     rdx, [rax+18h]
0x14019a0f2  test    rdx, rdx
0x14019a0f5  jz      short loc_14019A0FF
0x14019a0f7  lea     rcx, [r9+r9*4]
0x14019a0fb  lea     rcx, [rdx+rcx*4]
0x14019a0ff  mov     r9d, 1
0x14019a105  lock add [rcx+4], r9d
0x14019a10a  mov     rcx, [r8+10h]
0x14019a10e  mov     eax, r15d
0x14019a111  lea     rdx, [rax+rax*2]
0x14019a115  mov     eax, ebp
0x14019a117  mov     [rcx+rdx*8], r10
0x14019a11b  shl     eax, 4
0x14019a11e  or      eax, r9d
0x14019a121  mov     [rcx+rdx*8+8], r11
0x14019a126  mov     [rcx+rdx*8+10h], eax
0x14019a12a  jmp     short loc_14019A13A
0x14019a12c  mov     r8, r13; Size
0x14019a12f  mov     rdx, r11; Src
0x14019a132  mov     rcx, r10; void *
0x14019a135  call    memmove
0x14019a13a  mov     rcx, r14; MemoryDescriptorList
0x14019a13d  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14019a144  nop     dword ptr [rax+rax+00h]
0x14019a149  mov     r13d, [rsp+0E8h+var_94]
0x14019a14e  jmp     loc_14019A22F
  ... truncated ...
```
