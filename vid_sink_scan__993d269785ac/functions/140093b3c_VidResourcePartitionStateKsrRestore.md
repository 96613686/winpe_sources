# VidResourcePartitionStateKsrRestore

- ea: `0x140093b3c`
- end: `0x140093f4e`
- name: `VidResourcePartitionStateKsrRestore`
- size: `1042`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400cf86c`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x140076a7c`
- `0x140093b3c`
- `0x140093f54`
- `0x140094034`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140093e81`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140093e81`
- `ntoskrnl!MmSizeOfMdl` at `0x140093bf8`
- `ntoskrnl!MmSizeOfMdl` at `0x140093bf8`
- `ntoskrnl!MmUnmapLockedPages` at `0x140093ead`
- `ntoskrnl!MmUnmapLockedPages` at `0x140093ead`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140093d89`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140093d89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093ec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093edf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093ec1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093edf`
- `ntoskrnl!ExAllocatePool2` at `0x140093c12`
- `ntoskrnl!ExAllocatePool2` at `0x140093c12`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemoryBlock` at `0x140093ef8`
- `ext-ms-win-ntos-ksr-l1-1-7!KsrFreePersistedMemoryBlock` at `0x140093ef8`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionStateKsrRestore(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r15
  __int64 v3; // r12
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // r8
  _QWORD *v7; // r13
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  char *v10; // rsi
  unsigned int i; // edx
  __int64 v12; // rax
  SIZE_T v13; // rax
  __int64 Pool2; // rax
  struct _MDL *v15; // rdi
  int v16; // r9d
  unsigned __int64 *v17; // r8
  unsigned int v18; // ecx
  __int64 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rsi
  _QWORD *v24; // rax
  char *v25; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rbx
  int v29; // r15d
  char *v30; // rax
  unsigned __int64 v31; // rax
  unsigned int v33; // [rsp+30h] [rbp-99h] BYREF
  PVOID P; // [rsp+38h] [rbp-91h] BYREF
  __int64 v35; // [rsp+40h] [rbp-89h]
  char *j; // [rsp+48h] [rbp-81h] BYREF
  _QWORD *v37; // [rsp+50h] [rbp-79h]
  char v38[32]; // [rsp+60h] [rbp-69h] BYREF
  char v39[16]; // [rsp+80h] [rbp-49h] BYREF
  char v40[16]; // [rsp+90h] [rbp-39h] BYREF
  unsigned int *v41; // [rsp+A0h] [rbp-29h]
  __int64 v42; // [rsp+A8h] [rbp-21h]
  PVOID *p_P; // [rsp+B0h] [rbp-19h]
  __int64 v44; // [rsp+B8h] [rbp-11h]
  char **p_j; // [rsp+C0h] [rbp-9h]
  __int64 v46; // [rsp+C8h] [rbp-1h]

  v2 = VidDeviceExtension;
  v3 = 0;
  v37 = VidDeviceExtension;
  v33 = 0;
  P = 0;
  v4 = a2;
  v35 = a2;
  v5 = VidResourcePartitionpClaimPersistedMemory(a1, a2, &P, &v33);
  v7 = P;
  v8 = v5;
  if ( v5 >= 0 )
  {
    v9 = v33;
    if ( v33 )
    {
      v10 = 0;
      for ( i = 0; i < v33; ++i )
      {
        v12 = i;
        v10 += *((_QWORD *)P + v12) >> 40;
      }
      v13 = MmSizeOfMdl(0, (_QWORD)v10 << 12);
      Pool2 = ExAllocatePool2(256, v13, 1917084758);
      v15 = (struct _MDL *)Pool2;
      if ( Pool2 )
      {
        *(_QWORD *)Pool2 = 0;
        v17 = (unsigned __int64 *)(Pool2 + 48);
        *(_QWORD *)(Pool2 + 32) = 0;
        v18 = 0;
        *(_DWORD *)(Pool2 + 44) = 0;
        *(_WORD *)(Pool2 + 8) = 8 * ((_WORD)v10 + 6);
        *(_DWORD *)(Pool2 + 40) = (_DWORD)v10 << 12;
        for ( *(_WORD *)(Pool2 + 10) = 2; v18 < v9; ++v18 )
        {
          v19 = v7[v18] & 0xFFFFFFFFFFLL;
          v20 = 0;
          if ( (v7[v18] & 0xFFFFFF0000000000uLL) != 0 )
          {
            do
            {
              v21 = v20 + v19;
              ++v20;
              *v17++ = v21;
            }
            while ( v20 < v7[v18] >> 40 );
          }
        }
        v22 = MmMapLockedPagesSpecifyCache(v15, 0, MmCached, 0, 0, 0x40000010u);
        v23 = v22;
        if ( !v22 )
        {
          v8 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VidResourcePartitionStateKsrRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
            2421);
          goto LABEL_41;
        }
        if ( !*v22 )
          goto LABEL_39;
        v24 = v22 + 1;
LABEL_19:
        v25 = (char *)VidResourcePartitionpAllocate(&v24[2 * v3], 0);
        P = v25;
        if ( v25 )
        {
          v27 = (unsigned __int64)(v2 + 276);
          v28 = v2[276];
          if ( (v2[277] & 1) != 0 && v28 )
            v28 ^= v27;
          LOBYTE(v26) = 0;
          v29 = v2[277] & 1;
          if ( !v28 )
            goto LABEL_38;
          v30 = v25 + 8;
          for ( j = v30; ; v30 = j )
          {
            if ( (int)VidResourcePartitionCompareById(v30, v28, v26) < 0 )
            {
              v31 = *(_QWORD *)v28;
              if ( v29 )
              {
                if ( !v31 )
                  goto LABEL_36;
                v31 ^= v28;
              }
              if ( !v31 )
              {
LABEL_36:
                LOBYTE(v26) = 0;
LABEL_37:
                v25 = (char *)P;
LABEL_38:
                RtlRbInsertNodeEx(v27, v28, v26, v25 + 32);
                v2 = v37;
                v24 = v23 + 1;
                if ( (unsigned __int64)++v3 >= *v23 )
                {
LABEL_39:
                  v8 = 0;
                  goto LABEL_40;
                }
                goto LABEL_19;
              }
            }
            else
            {
              v31 = *(_QWORD *)(v28 + 8);
              if ( v29 )
              {
                if ( !v31 )
                  goto LABEL_30;
                v31 ^= v28;
              }
              if ( !v31 )
              {
LABEL_30:
                LOBYTE(v26) = 1;
                goto LABEL_37;
              }
            }
            v28 = v31;
          }
        }
        v8 = -1073741670;
        VidTraceErrorStatusInternal0(
          "VidResourcePartitionStateKsrRestore",
          "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
          2436);
LABEL_40:
        MmUnmapLockedPages(v23, v15);
LABEL_41:
        ExFreePoolWithTag(v15, 0x72446456u);
      }
      else
      {
        v8 = -1073741670;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v39, "VidResourcePartitionStateKsrRestore");
          tlgCreate1Sz_char(v40, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(P) = v16;
          v41 = &v33;
          v33 = 2381;
          p_P = &P;
          v42 = 4;
          p_j = &j;
          v44 = 4;
          j = v10;
          v46 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140047D7D, 0, 0, 7, v38);
        }
      }
      v4 = v35;
    }
    else
    {
      v8 = 0;
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VidResourcePartitionStateKsrRestore",
      "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c",
      2354);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0x72446456u);
  LOBYTE(v6) = 1;
  KsrFreePersistedMemoryBlock(VSMM_KSR_GLOBAL_STATE_GUID, v4, v6);
  return v8;
}

```

## disassembly

```asm
0x140093b3c  push    rbp
0x140093b3e  push    rbx
0x140093b3f  push    rsi
0x140093b40  push    rdi
0x140093b41  push    r12
0x140093b43  push    r13
0x140093b45  push    r14
0x140093b47  push    r15
0x140093b49  lea     rbp, [rsp-1Fh]
0x140093b4e  sub     rsp, 0E8h
0x140093b55  mov     rax, cs:__security_cookie
0x140093b5c  xor     rax, rsp
0x140093b5f  mov     [rbp+57h+var_50], rax
0x140093b63  mov     r15, cs:VidDeviceExtension
0x140093b6a  lea     r9, [rsp+120h+var_F0]
0x140093b6f  xor     r12d, r12d
0x140093b72  mov     [rbp+57h+var_D0], r15
0x140093b76  lea     r8, [rsp+120h+P]
0x140093b7b  mov     [rsp+120h+var_F0], r12d
0x140093b80  mov     [rsp+120h+P], r12
0x140093b85  mov     rdi, rdx
0x140093b88  mov     [rsp+120h+var_E0], rdx
0x140093b8d  call    VidResourcePartitionpClaimPersistedMemory
0x140093b92  mov     r13, [rsp+120h+P]
0x140093b97  mov     ebx, eax
0x140093b99  test    eax, eax
0x140093b9b  jns     short loc_140093BBE
0x140093b9d  mov     r9d, eax
0x140093ba0  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093ba7  mov     r8d, 932h
0x140093bad  lea     rcx, aVidresourcepar_6; "VidResourcePartitionStateKsrRestore"
0x140093bb4  call    VidTraceErrorStatusInternal0
0x140093bb9  jmp     loc_140093ED2
0x140093bbe  mov     ebx, [rsp+120h+var_F0]
0x140093bc2  test    ebx, ebx
0x140093bc4  jnz     short loc_140093BCE
0x140093bc6  mov     ebx, r12d
0x140093bc9  jmp     loc_140093ED2
0x140093bce  mov     rsi, r12
0x140093bd1  mov     edx, r12d
0x140093bd4  test    ebx, ebx
0x140093bd6  jz      short loc_140093BEC
0x140093bd8  mov     eax, edx
0x140093bda  inc     edx
0x140093bdc  mov     rcx, [r13+rax*8+0]
0x140093be1  shr     rcx, 28h
0x140093be5  add     rsi, rcx
0x140093be8  cmp     edx, ebx
0x140093bea  jb      short loc_140093BD8
0x140093bec  mov     r14, rsi
0x140093bef  xor     ecx, ecx; Base
0x140093bf1  shl     r14, 0Ch
0x140093bf5  mov     rdx, r14; Length
0x140093bf8  call    cs:__imp_MmSizeOfMdl
0x140093bff  nop     dword ptr [rax+rax+00h]
0x140093c04  mov     ecx, 100h
0x140093c09  mov     r8d, 72446456h
0x140093c0f  mov     rdx, rax
0x140093c12  call    cs:__imp_ExAllocatePool2
0x140093c19  nop     dword ptr [rax+rax+00h]
0x140093c1e  mov     rdi, rax
0x140093c21  test    rax, rax
0x140093c24  jnz     loc_140093CF1
0x140093c2a  mov     eax, cs:dword_140064110
0x140093c30  lea     ecx, [rdi+2]
0x140093c33  mov     r9d, 0C000009Ah
0x140093c39  mov     ebx, r9d
0x140093c3c  cmp     eax, ecx
0x140093c3e  jbe     loc_140093ECD
0x140093c44  mov     edx, 100h
0x140093c49  lea     rcx, dword_140064110
0x140093c50  call    _tlgKeywordOn
0x140093c55  test    al, al
0x140093c57  jz      loc_140093ECD
0x140093c5d  lea     rdx, aVidresourcepar_6; "VidResourcePartitionStateKsrRestore"
0x140093c64  lea     rcx, [rbp+57h+var_A0]
0x140093c68  call    _tlgCreate1Sz_char
0x140093c6d  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093c74  lea     rcx, [rbp+57h+var_90]
0x140093c78  call    _tlgCreate1Sz_char
0x140093c7d  lea     rax, [rsp+120h+var_F0]
0x140093c82  mov     dword ptr [rsp+120h+P], r9d
0x140093c87  mov     [rbp+57h+var_80], rax
0x140093c8b  lea     rdx, byte_140047D7D
0x140093c92  lea     rax, [rsp+120h+P]
0x140093c97  mov     [rsp+120h+var_F0], 94Dh
0x140093c9f  mov     [rbp+57h+var_70], rax
0x140093ca3  lea     rcx, dword_140064110
0x140093caa  lea     rax, [rsp+120h+var_D8]
0x140093caf  mov     [rbp+57h+var_78], 4
0x140093cb7  mov     [rbp+57h+var_60], rax
0x140093cbb  xor     r9d, r9d
0x140093cbe  lea     rax, [rbp+57h+var_C0]
0x140093cc2  mov     [rbp+57h+var_68], 4
0x140093cca  mov     qword ptr [rsp+120h+Priority], rax
0x140093ccf  xor     r8d, r8d
0x140093cd2  mov     [rsp+120h+BugCheckOnFailure], 7
0x140093cda  mov     [rsp+120h+var_D8], rsi
0x140093cdf  mov     [rbp+57h+var_58], 8
0x140093ce7  call    _tlgWriteTransfer_EtwWriteTransfer
0x140093cec  jmp     loc_140093ECD
0x140093cf1  mov     [rax], r12
0x140093cf4  lea     r8, [rdi+30h]
0x140093cf8  mov     rax, r14
0x140093cfb  mov     [rdi+20h], r12
0x140093cff  shr     rax, 0Ch
0x140093d03  mov     ecx, r12d
0x140093d06  add     ax, 6
0x140093d0a  mov     [rdi+2Ch], r12d
0x140093d0e  shl     ax, 3
0x140093d12  mov     [rdi+8], ax
0x140093d16  mov     [rdi+28h], r14d
0x140093d1a  mov     word ptr [rdi+0Ah], 2
0x140093d20  test    ebx, ebx
0x140093d22  jz      short loc_140093D70
0x140093d24  mov     rdx, 0FFFFFFFFFFh
0x140093d2e  mov     r10d, ecx
0x140093d31  mov     r11, 0FFFFFF0000000000h
0x140093d3b  mov     rax, [r13+r10*8+0]
0x140093d40  mov     r9, rax
0x140093d43  and     r9, rdx
0x140093d46  mov     rdx, r12
0x140093d49  test    r11, rax
0x140093d4c  jbe     short loc_140093D6A
0x140093d4e  lea     rax, [rdx+r9]
0x140093d52  inc     rdx
0x140093d55  mov     [r8], rax
0x140093d58  add     r8, 8
0x140093d5c  mov     rax, [r13+r10*8+0]
0x140093d61  shr     rax, 28h
0x140093d65  cmp     rdx, rax
0x140093d68  jb      short loc_140093D4E
0x140093d6a  inc     ecx
0x140093d6c  cmp     ecx, ebx
0x140093d6e  jb      short loc_140093D24
0x140093d70  xor     r9d, r9d; RequestedAddress
0x140093d73  mov     [rsp+120h+Priority], 40000010h; Priority
0x140093d7b  xor     edx, edx; AccessMode
0x140093d7d  mov     [rsp+120h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140093d82  mov     rcx, rdi; MemoryDescriptorList
0x140093d85  lea     r8d, [r9+1]; CacheType
0x140093d89  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140093d90  nop     dword ptr [rax+rax+00h]
0x140093d95  mov     rsi, rax
0x140093d98  test    rax, rax
0x140093d9b  jnz     short loc_140093DC4
0x140093d9d  mov     r9d, 0C000009Ah
0x140093da3  mov     ebx, r9d
0x140093da6  mov     r8d, 975h
0x140093dac  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093db3  lea     rcx, aVidresourcepar_6; "VidResourcePartitionStateKsrRestore"
0x140093dba  call    VidTraceErrorStatusInternal0
0x140093dbf  jmp     loc_140093EB9
0x140093dc4  cmp     [rax], r12
0x140093dc7  jbe     loc_140093EA1
0x140093dcd  add     rax, 8
0x140093dd1  mov     rcx, r12
0x140093dd4  xor     edx, edx
0x140093dd6  shl     rcx, 4
0x140093dda  add     rcx, rax
0x140093ddd  call    VidResourcePartitionpAllocate
0x140093de2  mov     [rsp+120h+P], rax
0x140093de7  test    rax, rax
0x140093dea  jz      loc_140093F27
0x140093df0  test    byte ptr [r15+8A8h], 1
0x140093df8  lea     r14, [r15+8A0h]
0x140093dff  mov     rbx, [r14]
0x140093e02  jz      short loc_140093E0C
0x140093e04  test    rbx, rbx
0x140093e07  jz      short loc_140093E0C
0x140093e09  xor     rbx, r14
0x140093e0c  movzx   r15d, byte ptr [r14+8]
0x140093e11  xor     r8b, r8b
0x140093e14  and     r15d, 1
0x140093e18  test    rbx, rbx
0x140093e1b  jz      short loc_140093E77
0x140093e1d  add     rax, 8
0x140093e21  mov     [rsp+120h+var_D8], rax
0x140093e26  mov     rdx, rbx
0x140093e29  mov     rcx, rax
0x140093e2c  call    VidResourcePartitionCompareById
0x140093e31  test    eax, eax
0x140093e33  js      short loc_140093E50
0x140093e35  mov     rax, [rbx+8]
0x140093e39  test    r15d, r15d
0x140093e3c  jz      short loc_140093E46
0x140093e3e  test    rax, rax
0x140093e41  jz      short loc_140093E4B
0x140093e43  xor     rax, rbx
0x140093e46  test    rax, rax
0x140093e49  jnz     short loc_140093E65
0x140093e4b  mov     r8b, 1
0x140093e4e  jmp     short loc_140093E72
0x140093e50  mov     rax, [rbx]
0x140093e53  test    r15d, r15d
0x140093e56  jz      short loc_140093E60
0x140093e58  test    rax, rax
0x140093e5b  jz      short loc_140093E6F
0x140093e5d  xor     rax, rbx
0x140093e60  test    rax, rax
0x140093e63  jz      short loc_140093E6F
0x140093e65  mov     rbx, rax
0x140093e68  mov     rax, [rsp+120h+var_D8]
0x140093e6d  jmp     short loc_140093E26
0x140093e6f  xor     r8b, r8b
0x140093e72  mov     rax, [rsp+120h+P]
0x140093e77  lea     r9, [rax+20h]
0x140093e7b  mov     rdx, rbx
0x140093e7e  mov     rcx, r14
0x140093e81  call    cs:__imp_RtlRbInsertNodeEx
0x140093e88  nop     dword ptr [rax+rax+00h]
0x140093e8d  mov     r15, [rbp+57h+var_D0]
0x140093e91  lea     rax, [rsi+8]
0x140093e95  inc     r12
0x140093e98  cmp     r12, [rsi]
0x140093e9b  jb      loc_140093DD1
0x140093ea1  xor     r12d, r12d
0x140093ea4  mov     ebx, r12d
0x140093ea7  mov     rdx, rdi; MemoryDescriptorList
0x140093eaa  mov     rcx, rsi; BaseAddress
0x140093ead  call    cs:__imp_MmUnmapLockedPages
0x140093eb4  nop     dword ptr [rax+rax+00h]
0x140093eb9  mov     edx, 72446456h; Tag
0x140093ebe  mov     rcx, rdi; P
0x140093ec1  call    cs:__imp_ExFreePoolWithTag
0x140093ec8  nop     dword ptr [rax+rax+00h]
0x140093ecd  mov     rdi, [rsp+120h+var_E0]
0x140093ed2  test    r13, r13
0x140093ed5  jz      short loc_140093EEB
0x140093ed7  mov     edx, 72446456h; Tag
0x140093edc  mov     rcx, r13; P
0x140093edf  call    cs:__imp_ExFreePoolWithTag
0x140093ee6  nop     dword ptr [rax+rax+00h]
0x140093eeb  mov     r8b, 1
0x140093eee  lea     rcx, VSMM_KSR_GLOBAL_STATE_GUID
0x140093ef5  mov     rdx, rdi
0x140093ef8  call    cs:__imp_KsrFreePersistedMemoryBlock
0x140093eff  nop     dword ptr [rax+rax+00h]
0x140093f04  mov     eax, ebx
0x140093f06  mov     rcx, [rbp+57h+var_50]
0x140093f0a  xor     rcx, rsp; StackCookie
0x140093f0d  call    __security_check_cookie
0x140093f12  add     rsp, 0E8h
0x140093f19  pop     r15
0x140093f1b  pop     r14
0x140093f1d  pop     r13
0x140093f1f  pop     r12
0x140093f21  pop     rdi
0x140093f22  pop     rsi
0x140093f23  pop     rbx
0x140093f24  pop     rbp
0x140093f25  retn
0x140093f27  mov     r9d, 0C000009Ah
0x140093f2d  mov     ebx, r9d
0x140093f30  mov     r8d, 984h
0x140093f36  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140093f3d  lea     rcx, aVidresourcepar_6; "VidResourcePartitionStateKsrRestore"
0x140093f44  call    VidTraceErrorStatusInternal0
0x140093f49  jmp     loc_140093EA7
```
