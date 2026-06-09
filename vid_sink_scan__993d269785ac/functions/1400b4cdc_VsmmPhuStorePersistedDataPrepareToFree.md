# VsmmPhuStorePersistedDataPrepareToFree

- ea: `0x1400b4cdc`
- end: `0x1400b516f`
- name: `VsmmPhuStorePersistedDataPrepareToFree`
- size: `1171`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14009fe78`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400b4cdc`
- `0x1400b5598`
- `0x1400b5658`
- `0x1400b775c`
- `0x1400b8118`
- `0x1400e67f8`
- `0x1400f2d14`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b4fa9`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400b4fa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b5041`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b5041`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4ef4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b4ef4`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b5082`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b5082`
- `winhvr!WinHvCreatePartition` at `0x1400b4da3`
- `winhvr!WinHvCreatePartition` at `0x1400b4da3`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorePersistedDataPrepareToFree(__int64 a1)
{
  __int64 v2; // rcx
  unsigned __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 *v5; // rdi
  int v6; // ebx
  __int16 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  __int64 *Pool2; // r13
  __int64 v17; // r9
  __int64 v18; // r8
  unsigned __int64 v19; // rbx
  int v20; // r15d
  unsigned __int64 v21; // rax
  char v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h]
  char v29[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[16]; // [rsp+B0h] [rbp-50h] BYREF
  int *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  int *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  __int64 v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]

  v28 = 0;
  v2 = a1 + 1128;
  v23 = 0;
  v27 = 0;
  if ( *(_BYTE *)(v2 + 48) )
  {
    v3 = *(_QWORD *)(v2 + 40);
    if ( ((v3 >> 10) & 0xF) - 2 <= 2 || (v3 & 0xC000) == 0x4000 )
    {
      VsmmPhuStorepCreationPropertiesDeserialize(v2, &v27);
      v5 = (__int64 *)(v4 + 56);
      v6 = WinHvCreatePartition(*(_QWORD *)v4, 4, 0x80000000LL, *(unsigned int *)(v4 + 8), &v27, v4 + 56, 0, 0, 0, 0);
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v30, "VsmmPhuStorePersistedDataPrepareToFree");
          tlgCreate1Sz_char(v31, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
          v24 = 2600;
          v32 = &v24;
          v7 = &word_14004FD86;
          v33 = 4;
          v34 = &v25;
          v36 = a1 + 48;
          v8 = *v5;
          v25 = v6;
          v35 = 4;
          goto LABEL_57;
        }
        goto LABEL_58;
      }
      v23 = 1;
    }
  }
  v9 = *(_QWORD *)(a1 + 1256);
  if ( (v9 & 1) != 0 )
  {
    if ( v9 == 1 )
      return 0;
    v10 = v9 ^ ((a1 + 1248) | 1);
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 1256);
  }
  if ( !v10 )
    return 0;
  while ( 1 )
  {
    v11 = *(_QWORD *)(v10 + 8);
    if ( v11 )
    {
      v12 = *(_QWORD **)v11;
      if ( *(_QWORD *)v11 )
      {
        do
        {
          v11 = (unsigned __int64)v12;
          v12 = (_QWORD *)*v12;
        }
        while ( v12 );
      }
    }
    else
    {
      v13 = *(_QWORD *)(v10 + 16);
      v14 = v10;
      while ( 1 )
      {
        v11 = v13 & 0xFFFFFFFFFFFFFFFCuLL;
        if ( !v11 || *(_QWORD *)v11 == v14 )
          break;
        v14 = v11;
        v13 = *(_QWORD *)(v11 + 16);
      }
    }
    if ( *(_DWORD *)(v10 + 32) != 2 )
      goto LABEL_41;
    v15 = v10 + 40;
    if ( (*(_BYTE *)(v10 + 73) & 1) == 0 )
      goto LABEL_41;
    if ( ((*(_BYTE *)(v10 + 64) & 0x10) == 0 || !*(_QWORD *)(v10 + 152))
      && !(unsigned __int8)VsmmPhuStorepMemoryFreeNeedsPreprocessing(a1, v10 + 40) )
    {
      goto LABEL_41;
    }
    Pool2 = (__int64 *)ExAllocatePool2(256, 88, 1833788502);
    if ( !Pool2 )
      break;
    v17 = *(_QWORD *)(v15 + 40);
    v26 = v15 + 40;
    v6 = VsmmPhysicalBufferSetupRestore(0, (__int64 *)(a1 + 48), 2, v17, 1, Pool2 + 3);
    if ( v6 < 0 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmPhuStorePersistedDataPrepareToFree",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        2651);
      VsmmPhysicalBufferTeardown(Pool2 + 3);
      ExFreePoolWithTag(Pool2, 0x6D4D6456u);
      goto LABEL_52;
    }
    v19 = *(_QWORD *)(a1 + 1360);
    if ( (*(_BYTE *)(a1 + 1368) & 1) != 0 )
    {
      if ( v19 )
        v19 ^= a1 + 1360;
      else
        v19 = 0;
    }
    LOBYTE(v18) = 0;
    v20 = *(_BYTE *)(a1 + 1368) & 1;
    if ( v19 )
    {
      while ( 1 )
      {
        if ( (int)VsmmPhuStorepPhysicalBufferCompareByBlockId(v26, v19, v18) < 0 )
        {
          v21 = *(_QWORD *)v19;
          if ( v20 )
          {
            if ( !v21 )
              goto LABEL_49;
            v21 ^= v19;
          }
          if ( !v21 )
          {
LABEL_49:
            LOBYTE(v18) = 0;
            break;
          }
        }
        else
        {
          v21 = *(_QWORD *)(v19 + 8);
          if ( v20 )
          {
            if ( !v21 )
              goto LABEL_39;
            v21 ^= v19;
          }
          if ( !v21 )
          {
LABEL_39:
            LOBYTE(v18) = 1;
            break;
          }
        }
        v19 = v21;
      }
    }
    RtlRbInsertNodeEx(a1 + 1360, v19, v18, Pool2);
LABEL_41:
    v10 = v11;
    if ( !v11 )
      return 0;
  }
  v6 = -1073741670;
  VidTraceErrorStatusInternal0(
    "VsmmPhuStorePersistedDataPrepareToFree",
    "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
    2637);
LABEL_52:
  if ( v23 )
  {
    v6 = WinHvUnlinkPreExistingPartition(*(_QWORD *)(a1 + 1184));
    if ( v6 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v30, "VsmmPhuStorePersistedDataPrepareToFree");
      tlgCreate1Sz_char(v31, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
      v25 = 2686;
      v32 = &v25;
      v7 = (__int16 *)&dword_14004FD2C;
      v33 = 4;
      v34 = &v24;
      v36 = a1 + 48;
      v8 = *(_QWORD *)(a1 + 1184);
      v24 = v6;
      v35 = 4;
LABEL_57:
      v26 = v8;
      v38 = &v26;
      v37 = 16;
      v39 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v7, 0, 0, 8, v29);
    }
  }
LABEL_58:
  VsmmPhuStorepCleanupPhysicalMemoryTable(a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b4cdc  mov     [rsp-8+arg_8], rbx
0x1400b4ce1  mov     [rsp-8+arg_10], rsi
0x1400b4ce6  push    rbp
0x1400b4ce7  push    rdi
0x1400b4ce8  push    r13
0x1400b4cea  push    r14
0x1400b4cec  push    r15
0x1400b4cee  lea     rbp, [rsp-10h]
0x1400b4cf3  sub     rsp, 110h
0x1400b4cfa  mov     rax, cs:__security_cookie
0x1400b4d01  xor     rax, rsp
0x1400b4d04  mov     [rbp+30h+var_30], rax
0x1400b4d08  xor     eax, eax
0x1400b4d0a  xor     r15d, r15d
0x1400b4d0d  mov     rsi, rcx
0x1400b4d10  mov     [rsp+130h+var_B8], rax
0x1400b4d15  add     rcx, 468h
0x1400b4d1c  mov     [rsp+130h+var_E0], r15b
0x1400b4d21  xorps   xmm0, xmm0
0x1400b4d24  movups  [rsp+130h+var_C8], xmm0
0x1400b4d29  lea     r14d, [rax+4]
0x1400b4d2d  cmp     [rcx+30h], r15b
0x1400b4d31  jz      loc_1400B4E43
0x1400b4d37  mov     rdx, [rcx+28h]
0x1400b4d3b  mov     rax, rdx
0x1400b4d3e  shr     rax, 0Ah
0x1400b4d42  and     eax, 0Fh
0x1400b4d45  sub     rax, 2
0x1400b4d49  cmp     rax, 2
0x1400b4d4d  jbe     short loc_1400B4D62
0x1400b4d4f  and     edx, 0C000h
0x1400b4d55  cmp     rdx, 4000h
0x1400b4d5c  jnz     loc_1400B4E43
0x1400b4d62  lea     rdx, [rsp+130h+var_C8]
0x1400b4d67  call    VsmmPhuStorepCreationPropertiesDeserialize
0x1400b4d6c  mov     r9d, [rcx+8]
0x1400b4d70  lea     rdi, [rcx+38h]
0x1400b4d74  mov     rcx, [rcx]
0x1400b4d77  lea     rax, [rsp+130h+var_C8]
0x1400b4d7c  mov     [rsp+130h+var_E8], r15
0x1400b4d81  mov     r8d, 80000000h
0x1400b4d87  mov     [rsp+130h+var_F0], r15
0x1400b4d8c  mov     rdx, r14
0x1400b4d8f  mov     [rsp+130h+var_F8], r15
0x1400b4d94  mov     [rsp+130h+var_100], r15
0x1400b4d99  mov     [rsp+130h+var_108], rdi
0x1400b4d9e  mov     qword ptr [rsp+130h+var_110], rax
0x1400b4da3  call    cs:__imp_WinHvCreatePartition
0x1400b4daa  nop     dword ptr [rax+rax+00h]
0x1400b4daf  mov     ebx, eax
0x1400b4db1  test    eax, eax
0x1400b4db3  jns     loc_1400B4E3E
0x1400b4db9  mov     ecx, cs:dword_140064110
0x1400b4dbf  cmp     ecx, 2
0x1400b4dc2  jbe     loc_1400B5162
0x1400b4dc8  mov     edx, 100h
0x1400b4dcd  lea     rcx, dword_140064110
0x1400b4dd4  call    _tlgKeywordOn
0x1400b4dd9  test    al, al
0x1400b4ddb  jz      loc_1400B5162
0x1400b4de1  lea     rdx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b4de8  lea     rcx, [rbp+30h+var_90]
0x1400b4dec  call    _tlgCreate1Sz_char
0x1400b4df1  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b4df8  lea     rcx, [rbp+30h+var_80]
0x1400b4dfc  call    _tlgCreate1Sz_char
0x1400b4e01  lea     rax, [rsp+130h+var_DC]
0x1400b4e06  mov     [rsp+130h+var_DC], 0A28h
0x1400b4e0e  mov     [rbp+30h+var_70], rax
0x1400b4e12  lea     rdx, word_14004FD86
0x1400b4e19  lea     rax, [rsp+130h+var_D8]
0x1400b4e1e  mov     [rbp+30h+var_68], r14
0x1400b4e22  mov     [rbp+30h+var_60], rax
0x1400b4e26  lea     rax, [rsi+30h]
0x1400b4e2a  mov     [rbp+30h+var_50], rax
0x1400b4e2e  mov     rax, [rdi]
0x1400b4e31  mov     [rsp+130h+var_D8], ebx
0x1400b4e35  mov     [rbp+30h+var_58], r14
0x1400b4e39  jmp     loc_1400B5124
0x1400b4e3e  mov     [rsp+130h+var_E0], 1
0x1400b4e43  lea     rcx, [rsi+4E0h]
0x1400b4e4a  mov     rax, [rcx+8]
0x1400b4e4e  test    al, 1
0x1400b4e50  jz      short loc_1400B4E65
0x1400b4e52  cmp     rax, 1
0x1400b4e56  jz      loc_1400B4FC1
0x1400b4e5c  or      rcx, 1
0x1400b4e60  xor     rcx, rax
0x1400b4e63  jmp     short loc_1400B4E68
0x1400b4e65  mov     rcx, rax
0x1400b4e68  test    rcx, rcx
0x1400b4e6b  jz      loc_1400B4FC1
0x1400b4e71  mov     rdi, [rcx+8]
0x1400b4e75  test    rdi, rdi
0x1400b4e78  jz      short loc_1400B4E92
0x1400b4e7a  mov     rdx, [rdi]
0x1400b4e7d  test    rdx, rdx
0x1400b4e80  jz      short loc_1400B4EAD
0x1400b4e82  mov     rax, [rdx]
0x1400b4e85  mov     rdi, rdx
0x1400b4e88  mov     rdx, rax
0x1400b4e8b  test    rax, rax
0x1400b4e8e  jnz     short loc_1400B4E82
0x1400b4e90  jmp     short loc_1400B4EAD
0x1400b4e92  mov     rdi, [rcx+10h]
0x1400b4e96  mov     rax, rcx
0x1400b4e99  jmp     short loc_1400B4EA7
0x1400b4e9b  cmp     [rdi], rax
0x1400b4e9e  jz      short loc_1400B4EAD
0x1400b4ea0  mov     rax, rdi
0x1400b4ea3  mov     rdi, [rdi+10h]
0x1400b4ea7  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1400b4eab  jnz     short loc_1400B4E9B
0x1400b4ead  cmp     dword ptr [rcx+20h], 2
0x1400b4eb1  jnz     loc_1400B4FB5
0x1400b4eb7  lea     rbx, [rcx+28h]
0x1400b4ebb  test    byte ptr [rbx+21h], 1
0x1400b4ebf  jz      loc_1400B4FB5
0x1400b4ec5  test    byte ptr [rbx+18h], 10h
0x1400b4ec9  jz      short loc_1400B4ED1
0x1400b4ecb  cmp     [rbx+70h], r15
0x1400b4ecf  jnz     short loc_1400B4EE4
0x1400b4ed1  mov     rdx, rbx
0x1400b4ed4  mov     rcx, rsi
0x1400b4ed7  call    VsmmPhuStorepMemoryFreeNeedsPreprocessing
0x1400b4edc  test    al, al
0x1400b4ede  jz      loc_1400B4FB5
0x1400b4ee4  mov     edx, 58h ; 'X'
0x1400b4ee9  mov     ecx, 100h
0x1400b4eee  mov     r8d, 6D4D6456h
0x1400b4ef4  call    cs:__imp_ExAllocatePool2
0x1400b4efb  nop     dword ptr [rax+rax+00h]
0x1400b4f00  mov     r13, rax
0x1400b4f03  test    rax, rax
0x1400b4f06  jz      loc_1400B504F
0x1400b4f0c  lea     rax, [rbx+28h]
0x1400b4f10  mov     r9, [rax]; int
0x1400b4f13  lea     rcx, [r13+18h]
0x1400b4f17  mov     [rsp+130h+var_108], rcx; void *
0x1400b4f1c  lea     rdx, [rsi+30h]; int
0x1400b4f20  xor     ecx, ecx; int
0x1400b4f22  mov     [rsp+130h+var_D0], rax
0x1400b4f27  mov     [rsp+130h+var_110], 1; int
0x1400b4f2f  lea     r8d, [rcx+2]; int
0x1400b4f33  call    VsmmPhysicalBufferSetupRestore
0x1400b4f38  mov     ebx, eax
0x1400b4f3a  test    eax, eax
0x1400b4f3c  js      loc_1400B5014
0x1400b4f42  test    byte ptr [rsi+558h], 1
0x1400b4f49  lea     r14, [rsi+550h]
0x1400b4f50  mov     rbx, [r14]
0x1400b4f53  jz      short loc_1400B4F62
0x1400b4f55  test    rbx, rbx
0x1400b4f58  jz      short loc_1400B4F5F
0x1400b4f5a  xor     rbx, r14
0x1400b4f5d  jmp     short loc_1400B4F62
0x1400b4f5f  mov     rbx, r15
0x1400b4f62  movzx   r15d, byte ptr [r14+8]
0x1400b4f67  xor     r8b, r8b
0x1400b4f6a  and     r15d, 1
0x1400b4f6e  test    rbx, rbx
0x1400b4f71  jz      short loc_1400B4F9D
0x1400b4f73  mov     rcx, [rsp+130h+var_D0]
0x1400b4f78  mov     rdx, rbx
0x1400b4f7b  call    VsmmPhuStorepPhysicalBufferCompareByBlockId
0x1400b4f80  test    eax, eax
0x1400b4f82  js      short loc_1400B4FEF
0x1400b4f84  mov     rax, [rbx+8]
0x1400b4f88  test    r15d, r15d
0x1400b4f8b  jz      short loc_1400B4F95
0x1400b4f8d  test    rax, rax
0x1400b4f90  jz      short loc_1400B4F9A
0x1400b4f92  xor     rax, rbx
0x1400b4f95  test    rax, rax
0x1400b4f98  jnz     short loc_1400B5004
0x1400b4f9a  mov     r8b, 1
0x1400b4f9d  xor     r15d, r15d
0x1400b4fa0  mov     r9, r13
0x1400b4fa3  mov     rdx, rbx
0x1400b4fa6  mov     rcx, r14
0x1400b4fa9  call    cs:__imp_RtlRbInsertNodeEx
0x1400b4fb0  nop     dword ptr [rax+rax+00h]
0x1400b4fb5  mov     rcx, rdi
0x1400b4fb8  test    rdi, rdi
0x1400b4fbb  jnz     loc_1400B4E71
0x1400b4fc1  mov     ebx, r15d
0x1400b4fc4  mov     eax, ebx
0x1400b4fc6  mov     rcx, [rbp+30h+var_30]
0x1400b4fca  xor     rcx, rsp; StackCookie
0x1400b4fcd  call    __security_check_cookie
0x1400b4fd2  lea     r11, [rsp+130h+var_20]
0x1400b4fda  mov     rbx, [r11+38h]
0x1400b4fde  mov     rsi, [r11+40h]
0x1400b4fe2  mov     rsp, r11
0x1400b4fe5  pop     r15
0x1400b4fe7  pop     r14
0x1400b4fe9  pop     r13
0x1400b4feb  pop     rdi
0x1400b4fec  pop     rbp
0x1400b4fed  retn
0x1400b4fef  mov     rax, [rbx]
0x1400b4ff2  test    r15d, r15d
0x1400b4ff5  jz      short loc_1400B4FFF
0x1400b4ff7  test    rax, rax
0x1400b4ffa  jz      short loc_1400B500C
0x1400b4ffc  xor     rax, rbx
0x1400b4fff  test    rax, rax
0x1400b5002  jz      short loc_1400B500C
0x1400b5004  mov     rbx, rax
0x1400b5007  jmp     loc_1400B4F73
0x1400b500c  xor     r15d, r15d
0x1400b500f  mov     r8b, r15b
0x1400b5012  jmp     short loc_1400B4FA0
0x1400b5014  mov     r9d, eax
0x1400b5017  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b501e  mov     r8d, 0A5Bh
0x1400b5024  lea     rcx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b502b  call    VidTraceErrorStatusInternal0
0x1400b5030  lea     rcx, [r13+18h]
0x1400b5034  call    VsmmPhysicalBufferTeardown
0x1400b5039  mov     edx, 6D4D6456h; Tag
0x1400b503e  mov     rcx, r13; P
0x1400b5041  call    cs:__imp_ExFreePoolWithTag
0x1400b5048  nop     dword ptr [rax+rax+00h]
0x1400b504d  jmp     short loc_1400B5070
0x1400b504f  mov     ebx, 0C000009Ah
0x1400b5054  mov     r9d, ebx
0x1400b5057  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b505e  mov     r8d, 0A4Dh
0x1400b5064  lea     rcx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b506b  call    VidTraceErrorStatusInternal0
0x1400b5070  cmp     [rsp+130h+var_E0], r15b
0x1400b5075  jz      loc_1400B5162
0x1400b507b  mov     rcx, [rsi+4A0h]
0x1400b5082  call    cs:__imp_WinHvUnlinkPreExistingPartition
0x1400b5089  nop     dword ptr [rax+rax+00h]
0x1400b508e  mov     ebx, eax
0x1400b5090  test    eax, eax
0x1400b5092  jns     loc_1400B5162
0x1400b5098  mov     eax, cs:dword_140064110
0x1400b509e  cmp     eax, 2
0x1400b50a1  jbe     loc_1400B5162
0x1400b50a7  mov     edx, 100h
0x1400b50ac  lea     rcx, dword_140064110
0x1400b50b3  call    _tlgKeywordOn
0x1400b50b8  test    al, al
0x1400b50ba  jz      loc_1400B5162
0x1400b50c0  lea     rdx, aVsmmphustorepe; "VsmmPhuStorePersistedDataPrepareToFree"
0x1400b50c7  lea     rcx, [rbp+30h+var_90]
0x1400b50cb  call    _tlgCreate1Sz_char
0x1400b50d0  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b50d7  lea     rcx, [rbp+30h+var_80]
0x1400b50db  call    _tlgCreate1Sz_char
0x1400b50e0  lea     rax, [rsp+130h+var_D8]
0x1400b50e5  mov     [rsp+130h+var_D8], 0A7Eh
0x1400b50ed  mov     [rbp+30h+var_70], rax
0x1400b50f1  lea     rdx, dword_14004FD2C
0x1400b50f8  lea     rax, [rsp+130h+var_DC]
0x1400b50fd  mov     [rbp+30h+var_68], 4
0x1400b5105  mov     [rbp+30h+var_60], rax
0x1400b5109  lea     rax, [rsi+30h]
0x1400b510d  mov     [rbp+30h+var_50], rax
0x1400b5111  mov     rax, [rsi+4A0h]
0x1400b5118  mov     [rsp+130h+var_DC], ebx
0x1400b511c  mov     [rbp+30h+var_58], 4
0x1400b5124  mov     [rsp+130h+var_D0], rax
0x1400b5129  lea     rcx, [rbp+30h+var_B0]
0x1400b512d  lea     rax, [rsp+130h+var_D0]
0x1400b5132  mov     [rsp+130h+var_108], rcx
0x1400b5137  mov     [rbp+30h+var_40], rax
0x1400b513b  lea     rcx, dword_140064110
0x1400b5142  mov     eax, 8
0x1400b5147  mov     [rbp+30h+var_48], 10h
0x1400b514f  xor     r9d, r9d
0x1400b5152  mov     [rsp+130h+var_110], eax
0x1400b5156  xor     r8d, r8d
0x1400b5159  mov     [rbp+30h+var_38], rax
0x1400b515d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b5162  mov     rcx, rsi
0x1400b5165  call    VsmmPhuStorepCleanupPhysicalMemoryTable
0x1400b516a  jmp     loc_1400B4FC4
```
