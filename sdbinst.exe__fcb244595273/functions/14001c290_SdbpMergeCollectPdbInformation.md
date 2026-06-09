# SdbpMergeCollectPdbInformation

- ea: `0x14001c290`
- end: `0x14001c4f9`
- name: `SdbpMergeCollectPdbInformation`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14001b7e8`

## callees

- `0x14000d8ac`
- `0x14001008c`
- `0x140010d44`
- `0x140013898`
- `0x140013cb8`
- `0x140013d54`
- `0x140013dc0`
- `0x140014380`
- `0x1400165cc`
- `0x14001a834`
- `0x14001c290`
- `0x14002e3e2`

## string_xrefs

- `0x14001c2f6`: `Failed to duplicate path [%x]`

## pseudocode

```c
__int64 __fastcall SdbpMergeCollectPdbInformation(__int64 a1, _OWORD *a2)
{
  int FileTimestamp; // eax
  unsigned int v5; // edi
  const char *v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  int v11; // eax
  unsigned int FirstTag; // esi
  unsigned int v13; // eax
  _WORD *StringTagPtr; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  int v25; // [rsp+28h] [rbp-69h]
  __int128 v26; // [rsp+38h] [rbp-59h] BYREF
  __int128 v27; // [rsp+48h] [rbp-49h] BYREF
  __int128 v28; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v29[48]; // [rsp+68h] [rbp-29h]
  __int128 v30; // [rsp+98h] [rbp+7h] BYREF
  __int64 v31; // [rsp+F8h] [rbp+67h] BYREF

  v31 = 0;
  memset_0(a2, 0, 0x50u);
  memset_0(&v28, 0, 0x50u);
  if ( *(_QWORD *)a1 )
  {
    FileTimestamp = AslStringDuplicate(&v28, **(_WORD ***)a1);
    v5 = FileTimestamp;
    if ( FileTimestamp < 0 )
    {
      v6 = "Failed to duplicate path [%x]";
      v7 = 2318;
LABEL_4:
      v25 = FileTimestamp;
      AslLogCallPrintf(1, "SdbpMergeCollectPdbInformation", v7, v6, v25);
      goto LABEL_26;
    }
    FileTimestamp = SdbpGetFileTimestamp(&v31, (const WCHAR *)v28, 1);
    v5 = FileTimestamp;
    if ( FileTimestamp < 0 )
    {
      v6 = "SdbpGetFileTimestamp failed [%x]";
      v7 = 2324;
      goto LABEL_4;
    }
    *((_QWORD *)&v28 + 1) = v31;
  }
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 && (v9 = *(_DWORD *)(a1 + 20)) != 0 )
  {
    v10 = 4096;
    if ( v9 < 0x1000 )
      v10 = *(_DWORD *)(a1 + 20);
    v11 = AslComputeCrc32(0, v8, v10);
  }
  else
  {
    v11 = 0;
  }
  *(_DWORD *)&v29[40] = v11;
  FirstTag = SdbFindFirstTag(a1, 0, 28673);
  v13 = SdbFindFirstTag(a1, FirstTag, 24610);
  if ( v13 )
  {
    StringTagPtr = (_WORD *)SdbGetStringTagPtr(a1, v13);
    FileTimestamp = AslStringDuplicate(&v30, StringTagPtr);
    v5 = FileTimestamp;
    if ( FileTimestamp < 0 )
    {
      v6 = "AslStringDuplicate failed [%x]";
      v7 = 2341;
      goto LABEL_4;
    }
  }
  v15 = SdbFindFirstTag(a1, FirstTag, 36871);
  if ( v15 )
  {
    v26 = 0;
    *(_OWORD *)&v29[8] = *SdbReadGUIDTag(&v27, a1, v15, &v26);
  }
  v16 = SdbFindFirstTag(a1, FirstTag, 36878);
  if ( v16 )
  {
    v26 = 0;
    *(_OWORD *)&v29[24] = *SdbReadGUIDTag(&v27, a1, v16, &v26);
  }
  v17 = SdbFindFirstTag(a1, FirstTag, 16417);
  if ( v17 )
    DWORD2(v30) = SdbReadDWORDTag(a1, v17, 0);
  v18 = SdbFindFirstTag(a1, FirstTag, 20481);
  if ( v18 )
    *(_QWORD *)v29 = SdbReadQWORDTag(a1, v18, 0);
  v19 = SdbFindFirstTag(a1, FirstTag, 28748);
  v20 = *(_OWORD *)v29;
  *a2 = v28;
  v21 = *(_OWORD *)&v29[16];
  a2[1] = v20;
  v22 = *(_OWORD *)&v29[32];
  a2[2] = v21;
  HIDWORD(v30) = v19 != 0;
  v23 = v30;
  a2[3] = v22;
  a2[4] = v23;
  memset_0(&v28, 0, 0x50u);
  v5 = 0;
LABEL_26:
  SdbMergeFreePdbInformation(&v28);
  return v5;
}

```

## disassembly

```asm
0x14001c290  mov     rax, rsp
0x14001c293  push    rbp
0x14001c294  push    rbx
0x14001c295  push    rsi
0x14001c296  push    rdi
0x14001c297  push    r12
0x14001c299  push    r14
0x14001c29b  lea     rbp, [rax-5Fh]
0x14001c29f  sub     rsp, 0B8h
0x14001c2a6  mov     r14, rdx
0x14001c2a9  movaps  xmmword ptr [rax-48h], xmm6
0x14001c2ad  mov     rbx, rcx
0x14001c2b0  mov     [rbp+57h+arg_0], 0
0x14001c2b8  mov     r12d, 50h ; 'P'
0x14001c2be  mov     rcx, r14; void *
0x14001c2c1  mov     r8d, r12d; Size
0x14001c2c4  xor     edx, edx; Val
0x14001c2c6  call    memset_0
0x14001c2cb  mov     r8d, r12d; Size
0x14001c2ce  lea     rcx, [rbp+57h+var_90]; void *
0x14001c2d2  xor     edx, edx; Val
0x14001c2d4  call    memset_0
0x14001c2d9  mov     rdx, [rbx]
0x14001c2dc  xorps   xmm6, xmm6
0x14001c2df  test    rdx, rdx
0x14001c2e2  jz      short loc_14001C351
0x14001c2e4  mov     rdx, [rdx]
0x14001c2e7  lea     rcx, [rbp+57h+var_90]
0x14001c2eb  call    AslStringDuplicate
0x14001c2f0  mov     edi, eax
0x14001c2f2  test    eax, eax
0x14001c2f4  jns     short loc_14001C31D
0x14001c2f6  lea     r9, aFailedToDuplic_1; "Failed to duplicate path [%x]"
0x14001c2fd  mov     r8d, 90Eh
0x14001c303  lea     rdx, aSdbpmergecolle_0; "SdbpMergeCollectPdbInformation"
0x14001c30a  mov     [rsp+20h], eax
0x14001c30e  mov     ecx, 1
0x14001c313  call    AslLogCallPrintf
0x14001c318  jmp     loc_14001C4D6
0x14001c31d  mov     rdx, qword ptr [rbp+57h+var_90]
0x14001c321  lea     rcx, [rbp+57h+arg_0]
0x14001c325  mov     r8d, 1
0x14001c32b  call    SdbpGetFileTimestamp
0x14001c330  mov     edi, eax
0x14001c332  test    eax, eax
0x14001c334  jns     short loc_14001C345
0x14001c336  lea     r9, aSdbpgetfiletim; "SdbpGetFileTimestamp failed [%x]"
0x14001c33d  mov     r8d, 914h
0x14001c343  jmp     short loc_14001C303
0x14001c345  mov     eax, dword ptr [rbp+57h+arg_0]
0x14001c348  mov     dword ptr [rbp+57h+var_90+8], eax
0x14001c34b  mov     eax, dword ptr [rbp+57h+arg_0+4]
0x14001c34e  mov     dword ptr [rbp+57h+var_90+0Ch], eax
0x14001c351  mov     rdx, [rbx+8]
0x14001c355  test    rdx, rdx
0x14001c358  jz      short loc_14001C377
0x14001c35a  mov     eax, [rbx+14h]
0x14001c35d  test    eax, eax
0x14001c35f  jz      short loc_14001C377
0x14001c361  mov     r8d, 1000h
0x14001c367  cmp     eax, r8d
0x14001c36a  cmovb   r8d, eax
0x14001c36e  xor     ecx, ecx
0x14001c370  call    AslComputeCrc32
0x14001c375  jmp     short loc_14001C379
0x14001c377  xor     eax, eax
0x14001c379  xor     edx, edx
0x14001c37b  mov     [rbp+57h+var_58], eax
0x14001c37e  mov     r8d, 7001h
0x14001c384  mov     rcx, rbx
0x14001c387  call    SdbFindFirstTag
0x14001c38c  mov     r8d, 6022h
0x14001c392  mov     edx, eax
0x14001c394  mov     rcx, rbx
0x14001c397  mov     esi, eax
0x14001c399  call    SdbFindFirstTag
0x14001c39e  test    eax, eax
0x14001c3a0  jz      short loc_14001C3D0
0x14001c3a2  mov     edx, eax
0x14001c3a4  mov     rcx, rbx
0x14001c3a7  call    SdbGetStringTagPtr
0x14001c3ac  mov     rdx, rax
0x14001c3af  lea     rcx, [rbp+57h+var_50]
0x14001c3b3  call    AslStringDuplicate
0x14001c3b8  mov     edi, eax
0x14001c3ba  test    eax, eax
0x14001c3bc  jns     short loc_14001C3D0
0x14001c3be  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x14001c3c5  mov     r8d, 925h
0x14001c3cb  jmp     loc_14001C303
0x14001c3d0  mov     r8d, 9007h
0x14001c3d6  mov     edx, esi
0x14001c3d8  mov     rcx, rbx
0x14001c3db  call    SdbFindFirstTag
0x14001c3e0  test    eax, eax
0x14001c3e2  jz      short loc_14001C404
0x14001c3e4  lea     r9, [rbp+57h+var_B0]
0x14001c3e8  movdqa  [rbp+57h+var_B0], xmm6
0x14001c3ed  mov     r8d, eax
0x14001c3f0  lea     rcx, [rbp+57h+var_A0]
0x14001c3f4  mov     rdx, rbx
0x14001c3f7  call    SdbReadGUIDTag
0x14001c3fc  movups  xmm0, xmmword ptr [rax]
0x14001c3ff  movdqu  [rbp+57h+var_80+8], xmm0
0x14001c404  mov     r8d, 900Eh
0x14001c40a  mov     edx, esi
0x14001c40c  mov     rcx, rbx
0x14001c40f  call    SdbFindFirstTag
0x14001c414  test    eax, eax
0x14001c416  jz      short loc_14001C438
0x14001c418  lea     r9, [rbp+57h+var_B0]
0x14001c41c  movdqa  [rbp+57h+var_B0], xmm6
0x14001c421  mov     r8d, eax
0x14001c424  lea     rcx, [rbp+57h+var_A0]
0x14001c428  mov     rdx, rbx
0x14001c42b  call    SdbReadGUIDTag
0x14001c430  movups  xmm0, xmmword ptr [rax]
0x14001c433  movdqu  [rbp+57h+var_68], xmm0
0x14001c438  mov     r8d, 4021h
0x14001c43e  mov     edx, esi
0x14001c440  mov     rcx, rbx
0x14001c443  call    SdbFindFirstTag
0x14001c448  test    eax, eax
0x14001c44a  jz      short loc_14001C45C
0x14001c44c  xor     r8d, r8d
0x14001c44f  mov     edx, eax
0x14001c451  mov     rcx, rbx
0x14001c454  call    SdbReadDWORDTag
0x14001c459  mov     dword ptr [rbp+57h+var_50+8], eax
0x14001c45c  mov     r8d, 5001h
0x14001c462  mov     edx, esi
0x14001c464  mov     rcx, rbx
0x14001c467  call    SdbFindFirstTag
0x14001c46c  test    eax, eax
0x14001c46e  jz      short loc_14001C481
0x14001c470  xor     r8d, r8d
0x14001c473  mov     edx, eax
0x14001c475  mov     rcx, rbx
0x14001c478  call    SdbReadQWORDTag
0x14001c47d  mov     qword ptr [rbp+57h+var_80], rax
0x14001c481  mov     r8w, 704Ch
0x14001c486  mov     edx, esi
0x14001c488  mov     rcx, rbx
0x14001c48b  call    SdbFindFirstTag
0x14001c490  movaps  xmm0, [rbp+57h+var_90]
0x14001c494  xor     ecx, ecx
0x14001c496  movaps  xmm1, [rbp+57h+var_80]
0x14001c49a  test    eax, eax
0x14001c49c  movaps  xmmword ptr [r14], xmm0
0x14001c4a0  mov     r8, r12; Size
0x14001c4a3  movaps  xmm0, xmmword ptr [rbp-19h]
0x14001c4a7  setnz   cl
0x14001c4aa  movaps  xmmword ptr [r14+10h], xmm1
0x14001c4af  xor     edx, edx; Val
0x14001c4b1  movaps  xmm1, [rbp+57h+var_68+8]
0x14001c4b5  movaps  xmmword ptr [r14+20h], xmm0
0x14001c4ba  mov     dword ptr [rbp+57h+var_50+0Ch], ecx
0x14001c4bd  lea     rcx, [rbp+57h+var_90]; void *
0x14001c4c1  movaps  xmm0, [rbp+57h+var_50]
0x14001c4c5  movaps  xmmword ptr [r14+30h], xmm1
0x14001c4ca  movaps  xmmword ptr [r14+40h], xmm0
0x14001c4cf  call    memset_0
0x14001c4d4  xor     edi, edi
0x14001c4d6  lea     rcx, [rbp+57h+var_90]; void *
0x14001c4da  call    SdbMergeFreePdbInformation
0x14001c4df  movaps  xmm6, xmmword ptr [rsp+0A0h]
0x14001c4e7  mov     eax, edi
0x14001c4e9  add     rsp, 0B8h
0x14001c4f0  pop     r14
0x14001c4f2  pop     r12
0x14001c4f4  pop     rdi
0x14001c4f5  pop     rsi
0x14001c4f6  pop     rbx
0x14001c4f7  pop     rbp
0x14001c4f8  retn
```
