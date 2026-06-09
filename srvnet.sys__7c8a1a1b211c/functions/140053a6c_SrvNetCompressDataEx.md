# SrvNetCompressDataEx

- ea: `0x140053a6c`
- end: `0x140053e9f`
- name: `SrvNetCompressDataEx`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400539b8`

## callees

- `0x140002060`
- `0x140012b50`
- `0x14001389c`
- `0x140015790`
- `0x140020ba4`
- `0x140020d44`
- `0x14002a540`
- `0x140053a6c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053ba2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053c2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053e45`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053ba2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053c2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053e45`
- `TDI!TdiCopyMdlToBuffer` at `0x140053cf1`
- `TDI!TdiCopyMdlToBuffer` at `0x140053cf1`

## pseudocode

```c
__int64 __fastcall SrvNetCompressDataEx(unsigned int *a1)
{
  __int64 *v1; // rax
  __int64 v3; // rbx
  volatile signed __int64 *v4; // rax
  __int64 Buffer; // rax
  __int64 v6; // r15
  int v7; // ebx
  __int64 v8; // rsi
  _QWORD *v9; // r14
  int v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  struct _MDL *v14; // rcx
  PVOID MappedSystemVa; // rdx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  struct _MDL *Next; // rcx
  int v19; // ecx
  __int64 v20; // rax
  NTSTATUS v21; // eax
  volatile signed __int64 *v23; // rax
  volatile signed __int64 *v24; // rdx
  __int64 v25; // rcx
  PVOID v26; // rax
  _QWORD *v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // [rsp+60h] [rbp+30h] BYREF
  ULONG BytesCopied; // [rsp+68h] [rbp+38h] BYREF

  v1 = (__int64 *)*((_QWORD *)a1 + 1);
  BytesCopied = 0;
  v29 = 0;
  v3 = *v1;
  v4 = (volatile signed __int64 *)*((_QWORD *)a1 + 15);
  if ( v4 )
    _InterlockedAdd64(v4, 1u);
  BytesCopied = *a1 + 16;
  Buffer = SrvNetAllocateBuffer(BytesCopied, 0);
  v6 = Buffer;
  if ( !Buffer )
    return (unsigned int)-1073741670;
  v8 = *(_QWORD *)(Buffer + 24);
  v9 = 0;
  *(_DWORD *)v8 = 1112364028;
  *(_DWORD *)(v8 + 4) = *a1;
  *(_WORD *)(v8 + 8) = 0;
  *(_WORD *)(v8 + 10) = 0;
  *(_DWORD *)(v8 + 12) = 0;
  if ( (a1[1] & 2) != 0 )
  {
    v10 = SmbCompressionMdlCompress(a1[23], *((_QWORD *)a1 + 1), *a1, v8 + 8, &v29);
    v29 += 8;
    v7 = v10;
    *(_WORD *)(v8 + 10) |= 1u;
    goto LABEL_45;
  }
  if ( !a1[22] )
  {
    v7 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_54;
    }
    v12 = 17;
    v13 = 3221225485LL;
    goto LABEL_53;
  }
  *(_WORD *)(v8 + 8) = *((_WORD *)a1 + 44);
  v14 = (struct _MDL *)*((_QWORD *)a1 + 1);
  if ( v3 )
  {
    Next = v14->Next;
    if ( Next->Next || Next->ByteCount <= 0x1000 )
    {
      v20 = SrvNetAllocateBuffer(*a1, 0);
      v9 = (_QWORD *)v20;
      if ( !v20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids);
        }
        goto LABEL_22;
      }
      v21 = TdiCopyMdlToBuffer(*((PMDL *)a1 + 1), 0, *(PVOID *)(v20 + 24), 0, *a1, &BytesCopied);
      MappedSystemVa = (PVOID)v9[3];
      v7 = v21;
      if ( (int)(v21 + 0x80000000) >= 0 && v21 != -2147483643 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_54;
        }
        v12 = 21;
LABEL_52:
        v13 = (unsigned int)v7;
LABEL_53:
        WPP_SF_d(v11->AttachedDevice, v12, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids, v13);
LABEL_54:
        SrvNetFreeBuffer((PVOID)v6);
        if ( v9 )
          SrvNetFreeBuffer(v9);
        return (unsigned int)v7;
      }
    }
    else
    {
      if ( (Next->MdlFlags & 5) != 0 )
        MappedSystemVa = Next->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000010u);
      v19 = *(_DWORD *)(*((_QWORD *)a1 + 1) + 40LL);
      *(_DWORD *)(v8 + 4) -= v19;
      *(_DWORD *)(v8 + 12) = v19;
      if ( !MappedSystemVa )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_22;
        }
        v17 = 19;
        goto LABEL_21;
      }
    }
  }
  else
  {
    if ( (v14->MdlFlags & 5) != 0 )
      MappedSystemVa = v14->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_22;
      }
      v17 = 18;
LABEL_21:
      WPP_SF_d(v16->AttachedDevice, v17, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids, 0);
LABEL_22:
      v7 = -1073741670;
      goto LABEL_54;
    }
  }
  v7 = SmbCompressionLegacyCompress(
         a1[22],
         MappedSystemVa,
         *a1 - *(_DWORD *)(v8 + 12),
         v8 + *(unsigned int *)(v8 + 12) + 16LL,
         &v29);
  v29 += 16 + *(_DWORD *)(v8 + 12);
LABEL_45:
  if ( v29 >= *a1 )
  {
    v7 = -1073741789;
    goto LABEL_54;
  }
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_54;
    }
    v12 = 22;
    goto LABEL_52;
  }
  v23 = (volatile signed __int64 *)*((_QWORD *)a1 + 14);
  if ( v23 )
    _InterlockedAdd64(v23, 1u);
  v24 = (volatile signed __int64 *)*((_QWORD *)a1 + 13);
  if ( v24 )
    _InterlockedAdd64(v24, *a1 - v29);
  if ( v9 )
    SrvNetFreeBuffer(v9);
  if ( (a1[1] & 2) == 0 && *(_DWORD *)(v8 + 12) )
  {
    v25 = *((_QWORD *)a1 + 1);
    if ( (*(_BYTE *)(v25 + 10) & 5) != 0 )
      v26 = *(PVOID *)(v25 + 24);
    else
      v26 = MmMapLockedPagesSpecifyCache((PMDL)v25, 0, MmCached, 0, 0, 0x40000010u);
    memmove((void *)(v8 + 16), v26, *(unsigned int *)(v8 + 12));
  }
  v27 = *(_QWORD **)(v6 + 56);
  *(_DWORD *)(v6 + 36) = v29;
  *v27 = *((_QWORD *)a1 + 1);
  *((_QWORD *)a1 + 1) = *(_QWORD *)(v6 + 56);
  v28 = *(_DWORD *)(v6 + 36);
  a1[12] |= 0x10u;
  *a1 = v28;
  return 0;
}

```

## disassembly

```asm
0x140053a6c  mov     [rsp-28h+arg_10], rbx
0x140053a71  mov     [rsp-28h+arg_18], rsi
0x140053a76  push    rbp
0x140053a77  push    rdi
0x140053a78  push    r13
0x140053a7a  push    r14
0x140053a7c  push    r15
0x140053a7e  mov     rbp, rsp
0x140053a81  sub     rsp, 30h
0x140053a85  mov     rax, [rcx+8]
0x140053a89  mov     rdi, rcx
0x140053a8c  mov     [rbp+BytesCopied], 0
0x140053a93  mov     r13d, 1
0x140053a99  mov     [rbp+arg_0], 0
0x140053aa0  mov     rbx, [rax]
0x140053aa3  mov     rax, [rcx+78h]
0x140053aa7  test    rax, rax
0x140053aaa  jz      short loc_140053AB0
0x140053aac  lock add [rax], r13
0x140053ab0  mov     eax, [rcx]
0x140053ab2  xor     edx, edx
0x140053ab4  add     eax, 10h
0x140053ab7  mov     ecx, eax
0x140053ab9  mov     [rbp+BytesCopied], eax
0x140053abc  call    SrvNetAllocateBuffer
0x140053ac1  mov     r15, rax
0x140053ac4  test    rax, rax
0x140053ac7  jnz     short loc_140053AD3
0x140053ac9  mov     ebx, 0C000009Ah
0x140053ace  jmp     loc_140053DDD
0x140053ad3  mov     rsi, [rax+18h]
0x140053ad7  xor     r14d, r14d
0x140053ada  mov     edx, 40000010h
0x140053adf  mov     dword ptr [rsi], 424D53FCh
0x140053ae5  lea     rcx, [rsi+8]
0x140053ae9  mov     eax, [rdi]
0x140053aeb  mov     [rsi+4], eax
0x140053aee  xor     eax, eax
0x140053af0  mov     [rcx], ax
0x140053af3  mov     [rsi+0Ah], ax
0x140053af7  mov     [rsi+0Ch], eax
0x140053afa  mov     eax, [rdi+4]
0x140053afd  test    al, 2
0x140053aff  jz      short loc_140053B2C
0x140053b01  mov     r8d, [rdi]
0x140053b04  lea     rax, [rbp+arg_0]
0x140053b08  mov     rdx, [rdi+8]
0x140053b0c  mov     r9, rcx
0x140053b0f  mov     ecx, [rdi+5Ch]
0x140053b12  mov     qword ptr [rsp+30h+BugCheckOnFailure], rax
0x140053b17  call    SmbCompressionMdlCompress
0x140053b1c  add     [rbp+arg_0], 8
0x140053b20  mov     ebx, eax
0x140053b22  or      [rsi+0Ah], r13w
0x140053b27  jmp     loc_140053D7C
0x140053b2c  cmp     [rdi+58h], r14d
0x140053b30  jnz     short loc_140053B75
0x140053b32  mov     ebx, 0C000000Dh
0x140053b37  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053b3e  lea     rax, WPP_GLOBAL_Control
0x140053b45  cmp     rcx, rax
0x140053b48  jz      loc_140053DC8
0x140053b4e  test    dword ptr [rcx+2Ch], 100000h
0x140053b55  jz      loc_140053DC8
0x140053b5b  cmp     [rcx+29h], r13b
0x140053b5f  jb      loc_140053DC8
0x140053b65  mov     edx, 11h
0x140053b6a  mov     r9d, 0C000000Dh
0x140053b70  jmp     loc_140053DB8
0x140053b75  movzx   eax, word ptr [rdi+58h]
0x140053b79  mov     [rcx], ax
0x140053b7c  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140053b80  test    rbx, rbx
0x140053b83  jnz     short loc_140053BFE
0x140053b85  test    byte ptr [rcx+0Ah], 5
0x140053b89  jz      short loc_140053B91
0x140053b8b  mov     rdx, [rcx+18h]
0x140053b8f  jmp     short loc_140053BB1
0x140053b91  mov     [rsp+30h+Priority], edx; Priority
0x140053b95  xor     r9d, r9d; RequestedAddress
0x140053b98  xor     edx, edx; AccessMode
0x140053b9a  mov     [rsp+30h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x140053b9f  mov     r8d, r13d; CacheType
0x140053ba2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140053ba9  nop     dword ptr [rax+rax+00h]
0x140053bae  mov     rdx, rax
0x140053bb1  test    rdx, rdx
0x140053bb4  jnz     loc_140053D4B
0x140053bba  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053bc1  lea     rax, WPP_GLOBAL_Control
0x140053bc8  cmp     rcx, rax
0x140053bcb  jz      short loc_140053BF4
0x140053bcd  test    dword ptr [rcx+2Ch], 100000h
0x140053bd4  jz      short loc_140053BF4
0x140053bd6  cmp     [rcx+29h], r13b
0x140053bda  jb      short loc_140053BF4
0x140053bdc  mov     edx, 12h
0x140053be1  mov     rcx, [rcx+18h]
0x140053be5  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x140053bec  xor     r9d, r9d
0x140053bef  call    WPP_SF_d
0x140053bf4  mov     ebx, 0C000009Ah
0x140053bf9  jmp     loc_140053DC8
0x140053bfe  mov     rcx, [rcx]; MemoryDescriptorList
0x140053c01  cmp     [rcx], r14
0x140053c04  jnz     short loc_140053C7D
0x140053c06  cmp     dword ptr [rcx+28h], 1000h
0x140053c0d  jbe     short loc_140053C7D
0x140053c0f  test    byte ptr [rcx+0Ah], 5
0x140053c13  jz      short loc_140053C1B
0x140053c15  mov     rdx, [rcx+18h]
0x140053c19  jmp     short loc_140053C3B
0x140053c1b  mov     [rsp+30h+Priority], edx; Priority
0x140053c1f  xor     r9d, r9d; RequestedAddress
0x140053c22  xor     edx, edx; AccessMode
0x140053c24  mov     [rsp+30h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x140053c29  mov     r8d, r13d; CacheType
0x140053c2c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140053c33  nop     dword ptr [rax+rax+00h]
0x140053c38  mov     rdx, rax
0x140053c3b  mov     rax, [rdi+8]
0x140053c3f  mov     ecx, [rax+28h]
0x140053c42  sub     [rsi+4], ecx
0x140053c45  mov     [rsi+0Ch], ecx
0x140053c48  test    rdx, rdx
0x140053c4b  jnz     loc_140053D4B
0x140053c51  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053c58  lea     rax, WPP_GLOBAL_Control
0x140053c5f  cmp     rcx, rax
0x140053c62  jz      short loc_140053BF4
0x140053c64  test    dword ptr [rcx+2Ch], 100000h
0x140053c6b  jz      short loc_140053BF4
0x140053c6d  cmp     [rcx+29h], r13b
0x140053c71  jb      short loc_140053BF4
0x140053c73  mov     edx, 13h
0x140053c78  jmp     loc_140053BE1
0x140053c7d  mov     ecx, [rdi]
0x140053c7f  xor     edx, edx
0x140053c81  call    SrvNetAllocateBuffer
0x140053c86  mov     r14, rax
0x140053c89  test    rax, rax
0x140053c8c  jnz     short loc_140053CD5
0x140053c8e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053c95  lea     rax, WPP_GLOBAL_Control
0x140053c9c  cmp     rcx, rax
0x140053c9f  jz      loc_140053BF4
0x140053ca5  test    dword ptr [rcx+2Ch], 100000h
0x140053cac  jz      loc_140053BF4
0x140053cb2  cmp     [rcx+29h], r13b
0x140053cb6  jb      loc_140053BF4
0x140053cbc  mov     rcx, [rcx+18h]
0x140053cc0  lea     edx, [r14+14h]
0x140053cc4  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x140053ccb  call    WPP_SF_
0x140053cd0  jmp     loc_140053BF4
0x140053cd5  mov     r8, [r14+18h]; DestinationBuffer
0x140053cd9  lea     rax, [rbp+BytesCopied]
0x140053cdd  mov     rcx, [rdi+8]; SourceMdlChain
0x140053ce1  xor     r9d, r9d; DestinationOffset
0x140053ce4  mov     qword ptr [rsp+30h+Priority], rax; BytesCopied
0x140053ce9  xor     edx, edx; SourceOffset
0x140053ceb  mov     eax, [rdi]
0x140053ced  mov     [rsp+30h+BugCheckOnFailure], eax; DestinationBufferSize
0x140053cf1  call    cs:__imp_TdiCopyMdlToBuffer
0x140053cf8  nop     dword ptr [rax+rax+00h]
0x140053cfd  mov     rdx, [r14+18h]
0x140053d01  mov     ecx, 80000000h
0x140053d06  mov     ebx, eax
0x140053d08  add     eax, ecx
0x140053d0a  test    ecx, eax
0x140053d0c  jnz     short loc_140053D4B
0x140053d0e  cmp     ebx, 80000005h
0x140053d14  jz      short loc_140053D4B
0x140053d16  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053d1d  lea     rax, WPP_GLOBAL_Control
0x140053d24  cmp     rcx, rax
0x140053d27  jz      loc_140053DC8
0x140053d2d  test    dword ptr [rcx+2Ch], 100000h
0x140053d34  jz      loc_140053DC8
0x140053d3a  cmp     [rcx+29h], r13b
0x140053d3e  jb      loc_140053DC8
0x140053d44  mov     edx, 15h
0x140053d49  jmp     short loc_140053DB5
0x140053d4b  mov     eax, [rsi+0Ch]
0x140053d4e  mov     r8d, [rdi]
0x140053d51  mov     ecx, [rdi+58h]
0x140053d54  sub     r8d, eax
0x140053d57  lea     r9, [rax+10h]
0x140053d5b  lea     rax, [rbp+arg_0]
0x140053d5f  add     r9, rsi
0x140053d62  mov     qword ptr [rsp+30h+BugCheckOnFailure], rax
0x140053d67  call    SmbCompressionLegacyCompress
0x140053d6c  mov     ecx, [rsi+0Ch]
0x140053d6f  mov     ebx, eax
0x140053d71  mov     eax, [rbp+arg_0]
0x140053d74  add     eax, 10h
0x140053d77  add     ecx, eax
0x140053d79  mov     [rbp+arg_0], ecx
0x140053d7c  mov     eax, [rdi]
0x140053d7e  cmp     [rbp+arg_0], eax
0x140053d81  jb      short loc_140053D8A
0x140053d83  mov     ebx, 0C0000023h
0x140053d88  jmp     short loc_140053DC8
0x140053d8a  test    ebx, ebx
0x140053d8c  jns     short loc_140053DE4
0x140053d8e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140053d95  lea     rax, WPP_GLOBAL_Control
0x140053d9c  cmp     rcx, rax
0x140053d9f  jz      short loc_140053DC8
0x140053da1  test    dword ptr [rcx+2Ch], 100000h
0x140053da8  jz      short loc_140053DC8
0x140053daa  cmp     [rcx+29h], r13b
0x140053dae  jb      short loc_140053DC8
0x140053db0  mov     edx, 16h
0x140053db5  mov     r9d, ebx
0x140053db8  mov     rcx, [rcx+18h]
0x140053dbc  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x140053dc3  call    WPP_SF_d
0x140053dc8  mov     rcx, r15; Entry
0x140053dcb  call    SrvNetFreeBuffer
0x140053dd0  test    r14, r14
0x140053dd3  jz      short loc_140053DDD
0x140053dd5  mov     rcx, r14; Entry
0x140053dd8  call    SrvNetFreeBuffer
0x140053ddd  mov     eax, ebx
0x140053ddf  jmp     loc_140053E87
0x140053de4  mov     rax, [rdi+70h]
0x140053de8  test    rax, rax
0x140053deb  jz      short loc_140053DF1
0x140053ded  lock add [rax], r13
0x140053df1  mov     rdx, [rdi+68h]
0x140053df5  test    rdx, rdx
0x140053df8  jz      short loc_140053E03
0x140053dfa  mov     ecx, [rdi]
0x140053dfc  sub     ecx, [rbp+arg_0]
0x140053dff  lock add [rdx], rcx
0x140053e03  test    r14, r14
0x140053e06  jz      short loc_140053E10
0x140053e08  mov     rcx, r14; Entry
0x140053e0b  call    SrvNetFreeBuffer
0x140053e10  mov     eax, [rdi+4]
0x140053e13  test    al, 2
0x140053e15  jnz     short loc_140053E61
0x140053e17  cmp     dword ptr [rsi+0Ch], 0
0x140053e1b  jbe     short loc_140053E61
0x140053e1d  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140053e21  test    byte ptr [rcx+0Ah], 5
0x140053e25  jz      short loc_140053E2D
0x140053e27  mov     rax, [rcx+18h]
0x140053e2b  jmp     short loc_140053E51
0x140053e2d  mov     [rsp+30h+Priority], 40000010h; Priority
0x140053e35  xor     r9d, r9d; RequestedAddress
0x140053e38  mov     r8d, r13d; CacheType
0x140053e3b  mov     [rsp+30h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140053e43  xor     edx, edx; AccessMode
0x140053e45  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140053e4c  nop     dword ptr [rax+rax+00h]
0x140053e51  mov     r8d, [rsi+0Ch]; Size
0x140053e55  lea     rcx, [rsi+10h]; void *
0x140053e59  mov     rdx, rax; Src
0x140053e5c  call    memmove
0x140053e61  mov     rcx, [r15+38h]
0x140053e65  mov     eax, [rbp+arg_0]
0x140053e68  mov     [r15+24h], eax
0x140053e6c  mov     rax, [rdi+8]
0x140053e70  mov     [rcx], rax
0x140053e73  mov     rax, [r15+38h]
0x140053e77  mov     [rdi+8], rax
0x140053e7b  mov     eax, [r15+24h]
0x140053e7f  or      dword ptr [rdi+30h], 10h
0x140053e83  mov     [rdi], eax
0x140053e85  xor     eax, eax
0x140053e87  mov     rbx, [rsp+30h+arg_10]
0x140053e8c  mov     rsi, [rsp+30h+arg_18]
0x140053e91  add     rsp, 30h
0x140053e95  pop     r15
0x140053e97  pop     r14
0x140053e99  pop     r13
0x140053e9b  pop     rdi
0x140053e9c  pop     rbp
0x140053e9d  retn
```
