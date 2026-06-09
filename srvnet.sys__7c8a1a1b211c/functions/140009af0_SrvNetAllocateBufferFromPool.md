# SrvNetAllocateBufferFromPool

- ea: `0x140009af0`
- end: `0x140009d33`
- name: `SrvNetAllocateBufferFromPool`
- size: `579`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400010f0`
- `0x140001d70`
- `0x140004250`
- `0x140009ad0`
- `0x140012b50`

## callees

- `0x140009af0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009c78`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140009c78`
- `ntoskrnl!MmMdlPageContentsState` at `0x140009c8d`
- `ntoskrnl!MmMdlPageContentsState` at `0x140009c8d`
- `ntoskrnl!MmSizeOfMdl` at `0x140009b51`
- `ntoskrnl!MmSizeOfMdl` at `0x140009b51`
- `ntoskrnl!ExAllocatePool2` at `0x140009ba5`
- `ntoskrnl!ExAllocatePool2` at `0x140009ba5`

## pseudocode

```c
unsigned __int64 __fastcall SrvNetAllocateBufferFromPool(__int64 a1, unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v3; // rbp
  unsigned __int64 v4; // rdi
  SIZE_T v5; // rax
  unsigned __int64 v6; // rsi
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  __int64 Pool2; // rdx
  signed __int32 v10; // ecx
  __int64 v11; // r9
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r8
  __int16 v14; // dx
  __int64 v15; // r9
  unsigned __int64 v16; // r8
  __int64 v17; // rdx
  int v18; // eax

  if ( a2 > 0xFFFFFFFF )
    return 0;
  v3 = (unsigned int)a2;
  if ( (unsigned __int64)(unsigned int)a2 + 88 < (unsigned __int64)(unsigned int)a2 + 80 )
    return 0;
  v4 = (unsigned int)a2 + 232LL;
  if ( v4 < (unsigned __int64)(unsigned int)a2 + 88 )
    return 0;
  v5 = MmSizeOfMdl(0, (unsigned int)a2 + 232LL);
  v6 = v5 + 8;
  if ( v5 + 8 < v5 )
    return 0;
  v7 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    return 0;
  v8 = v4 + v7;
  if ( v4 + v7 < v4 )
    return 0;
  if ( v8 < 0x1000 )
  {
    v8 = 4096;
  }
  else if ( v8 > 0xFFFFFFFF )
  {
    return 0;
  }
  Pool2 = ExAllocatePool2(66, v8, 808473420);
  if ( !Pool2 )
  {
    _InterlockedIncrement(&dword_1400365E8);
    return 0;
  }
  v10 = v8 + _InterlockedExchangeAdd(&dword_1400365E4, v8);
  if ( (int)v8 > 0 )
  {
    do
      v18 = dword_1400365EC;
    while ( v10 > dword_1400365EC && v18 != _InterlockedCompareExchange(&dword_1400365EC, v10, dword_1400365EC) );
  }
  v11 = Pool2 + 80;
  v12 = (Pool2 + v3 + 87) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v12 + 48) = Pool2;
  v13 = (v12 + 151) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v12 + 24) = Pool2 + 80;
  *(_QWORD *)(v12 + 56) = v13;
  v14 = Pool2 + 80;
  *(_WORD *)(v12 + 16) = 0;
  *(_WORD *)(v12 + 22) = 0;
  *(_DWORD *)(v12 + 32) = v3;
  *(_DWORD *)(v12 + 36) = 0;
  *(_DWORD *)(v12 + 40) = v8;
  *(_DWORD *)(v12 + 64) = 0;
  *(_QWORD *)(v12 + 72) = 0;
  *(_QWORD *)(v12 + 80) = (v12 + v6 + 151) & 0xFFFFFFFFFFFFFFF8uLL;
  *(_QWORD *)(v12 + 88) = 0;
  *(_DWORD *)(v12 + 96) = 0;
  *(_QWORD *)v13 = 0;
  *(_WORD *)(v13 + 8) = 8 * (((v3 + (unsigned __int64)(v14 & 0xFFF) + 4095) >> 12) + 6);
  *(_WORD *)(v13 + 10) = 0;
  *(_QWORD *)(v13 + 32) = v11 & 0xFFFFFFFFFFFFF000uLL;
  *(_DWORD *)(v13 + 44) = v14 & 0xFFF;
  *(_DWORD *)(v13 + 40) = v3;
  MmBuildMdlForNonPagedPool(*(PMDL *)(v12 + 56));
  MmMdlPageContentsState(*(_QWORD *)(v12 + 56), 1);
  *(_WORD *)(*(_QWORD *)(v12 + 56) + 10LL) |= 0x1000u;
  result = v12;
  v15 = *(_QWORD *)(v12 + 80);
  v16 = *(_QWORD *)(v12 + 24) & 0xFFFFFFFFFFFFF000uLL;
  v17 = *(_QWORD *)(v12 + 24) & 0xFFFLL;
  *(_QWORD *)v15 = 0;
  *(_WORD *)(v15 + 10) = 0;
  *(_WORD *)(v15 + 8) = 8 * (((unsigned __int64)(v3 + v17 + 4095) >> 12) + 6);
  *(_QWORD *)(v15 + 32) = v16;
  *(_DWORD *)(v15 + 44) = v17;
  *(_DWORD *)(v15 + 40) = v3;
  *(_WORD *)(*(_QWORD *)(v12 + 80) + 10LL) |= 4u;
  return result;
}

```

## disassembly

```asm
0x140009af0  mov     [rsp+arg_8], rbx
0x140009af5  mov     [rsp+arg_10], rbp
0x140009afa  push    rsi
0x140009afb  push    rdi
0x140009afc  push    r12
0x140009afe  push    r14
0x140009b00  push    r15
0x140009b02  sub     rsp, 20h
0x140009b06  mov     r14d, 0FFFFFFFFh
0x140009b0c  cmp     rdx, r14
0x140009b0f  jbe     short loc_140009B2B
0x140009b11  xor     eax, eax
0x140009b13  mov     rbx, [rsp+48h+arg_8]
0x140009b18  mov     rbp, [rsp+48h+arg_10]
0x140009b1d  add     rsp, 20h
0x140009b21  pop     r15
0x140009b23  pop     r14
0x140009b25  pop     r12
0x140009b27  pop     rdi
0x140009b28  pop     rsi
0x140009b29  retn
0x140009b2b  mov     ebp, edx
0x140009b2d  lea     rax, [rbp+50h]
0x140009b31  cmp     rax, 50h ; 'P'
0x140009b35  jb      short loc_140009B11
0x140009b37  lea     rcx, [rax+8]
0x140009b3b  cmp     rcx, rax
0x140009b3e  jb      short loc_140009B11
0x140009b40  lea     rdi, [rcx+90h]
0x140009b47  cmp     rdi, rcx
0x140009b4a  jb      short loc_140009B11
0x140009b4c  mov     rdx, rdi; Length
0x140009b4f  xor     ecx, ecx; Base
0x140009b51  call    cs:__imp_MmSizeOfMdl
0x140009b58  nop     dword ptr [rax+rax+00h]
0x140009b5d  lea     rsi, [rax+8]
0x140009b61  cmp     rsi, rax
0x140009b64  jb      short loc_140009B11
0x140009b66  mov     eax, 2
0x140009b6b  xor     r12d, r12d
0x140009b6e  mul     rsi
0x140009b71  test    rdx, rdx
0x140009b74  jnz     short loc_140009B11
0x140009b76  lea     rbx, [rdi+rax]
0x140009b7a  cmp     rbx, rdi
0x140009b7d  jb      short loc_140009B11
0x140009b7f  mov     r15d, 1000h
0x140009b85  cmp     rbx, r15
0x140009b88  jb      loc_140009D1F
0x140009b8e  cmp     rbx, r14
0x140009b91  ja      loc_140009B11
0x140009b97  mov     r8d, 3030534Ch
0x140009b9d  mov     rdx, rbx
0x140009ba0  mov     ecx, 42h ; 'B'
0x140009ba5  call    cs:__imp_ExAllocatePool2
0x140009bac  nop     dword ptr [rax+rax+00h]
0x140009bb1  mov     rdx, rax
0x140009bb4  test    rax, rax
0x140009bb7  jz      loc_140009D27
0x140009bbd  mov     ecx, ebx
0x140009bbf  lock xadd cs:dword_1400365E4, ecx
0x140009bc7  add     ecx, ebx
0x140009bc9  test    ebx, ebx
0x140009bcb  jg      loc_140009D02
0x140009bd1  lea     r9, [rdx+50h]
0x140009bd5  lea     rdi, [rbp+57h]
0x140009bd9  add     rdi, rdx
0x140009bdc  lea     rax, [rsi+97h]
0x140009be3  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140009be7  add     rax, rdi
0x140009bea  and     rax, 0FFFFFFFFFFFFFFF8h
0x140009bee  mov     [rdi+30h], rdx
0x140009bf2  lea     r8, [rdi+97h]
0x140009bf9  and     r8, 0FFFFFFFFFFFFFFF8h
0x140009bfd  mov     [rdi+18h], r9
0x140009c01  mov     [rdi+38h], r8
0x140009c05  add     edx, 50h ; 'P'
0x140009c08  mov     [rdi+10h], r12w
0x140009c0d  mov     ecx, edx
0x140009c0f  and     ecx, 0FFFh
0x140009c15  mov     [rdi+16h], r12w
0x140009c1a  mov     [rdi+20h], ebp
0x140009c1d  add     rcx, 0FFFh
0x140009c24  mov     [rdi+24h], r12d
0x140009c28  add     rcx, rbp
0x140009c2b  mov     [rdi+28h], ebx
0x140009c2e  and     r9, 0FFFFFFFFFFFFF000h
0x140009c35  mov     [rdi+40h], r12d
0x140009c39  and     edx, 0FFFh
0x140009c3f  mov     [rdi+48h], r12
0x140009c43  mov     [rdi+50h], rax
0x140009c47  mov     [rdi+58h], r12
0x140009c4b  mov     [rdi+60h], r12d
0x140009c4f  shr     rcx, 0Ch
0x140009c53  add     cx, 6
0x140009c57  mov     [r8], r12
0x140009c5a  shl     cx, 3
0x140009c5e  mov     [r8+8], cx
0x140009c63  mov     [r8+0Ah], r12w
0x140009c68  mov     [r8+20h], r9
0x140009c6c  mov     [r8+2Ch], edx
0x140009c70  mov     [r8+28h], ebp
0x140009c74  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x140009c78  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140009c7f  nop     dword ptr [rax+rax+00h]
0x140009c84  mov     rcx, [rdi+38h]
0x140009c88  mov     edx, 1
0x140009c8d  call    cs:__imp_MmMdlPageContentsState
0x140009c94  nop     dword ptr [rax+rax+00h]
0x140009c99  mov     rax, [rdi+38h]
0x140009c9d  or      [rax+0Ah], r15w
0x140009ca2  mov     rax, rdi
0x140009ca5  mov     r8, [rdi+18h]
0x140009ca9  mov     r9, [rdi+50h]
0x140009cad  mov     edx, r8d
0x140009cb0  mov     ecx, edx
0x140009cb2  and     r8, 0FFFFFFFFFFFFF000h
0x140009cb9  and     ecx, 0FFFh
0x140009cbf  and     edx, 0FFFh
0x140009cc5  add     rcx, 0FFFh
0x140009ccc  add     rcx, rbp
0x140009ccf  mov     [r9], r12
0x140009cd2  shr     rcx, 0Ch
0x140009cd6  add     cx, 6
0x140009cda  mov     [r9+0Ah], r12w
0x140009cdf  shl     cx, 3
0x140009ce3  mov     [r9+8], cx
0x140009ce8  mov     [r9+20h], r8
0x140009cec  mov     [r9+2Ch], edx
0x140009cf0  mov     [r9+28h], ebp
0x140009cf4  mov     rcx, [rdi+50h]
0x140009cf8  or      word ptr [rcx+0Ah], 4
0x140009cfd  jmp     loc_140009B13
0x140009d02  mov     eax, cs:dword_1400365EC
0x140009d08  cmp     ecx, eax
0x140009d0a  jle     loc_140009BD1
0x140009d10  lock cmpxchg cs:dword_1400365EC, ecx
0x140009d18  jnz     short loc_140009D02
0x140009d1a  jmp     loc_140009BD1
0x140009d1f  mov     rbx, r15
0x140009d22  jmp     loc_140009B97
0x140009d27  lock inc cs:dword_1400365E8
0x140009d2e  jmp     loc_140009B11
```
