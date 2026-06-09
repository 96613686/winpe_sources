# KsPropertyHandleDrmSetContentId

- ea: `0x14002c118`
- end: `0x14002c2c6`
- name: `KsPropertyHandleDrmSetContentId`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002c08c`

## callees

- `0x140014e00`
- `0x140015100`
- `0x140022e98`
- `0x14002c118`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14002c1a5`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14002c1a5`
- `ntoskrnl!ProbeForRead` at `0x14002c213`
- `ntoskrnl!ProbeForRead` at `0x14002c213`

## pseudocode

```c
__int64 __fastcall KsPropertyHandleDrmSetContentId(__int64 a1)
{
  __int64 v3; // r13
  size_t v4; // r12
  SIZE_T v5; // rsi
  __int64 v6; // r14
  __int64 v7; // rcx
  char *PoolWithQuotaTag; // rax
  char *v9; // r15
  __int64 v10; // rdx
  int v11; // [rsp+58h] [rbp+10h]

  if ( *(_BYTE *)(a1 + 64) )
    return 3221225488LL;
  v3 = *(_QWORD *)(a1 + 184);
  v4 = *(unsigned int *)(v3 + 16);
  v5 = *(unsigned int *)(v3 + 8);
  v6 = ((_DWORD)v5 + 7) & 0xFFFFFFF8;
  v7 = *(_QWORD *)(a1 + 24);
  if ( !v7 )
  {
    if ( (unsigned int)v4 < 0x18 || (unsigned int)v6 < (unsigned int)v5 || (int)v6 + (int)v4 < (unsigned int)v6 )
      return 3221225990LL;
    v11 = *(_DWORD *)(*(_QWORD *)(v3 + 32) + 20LL);
    PoolWithQuotaTag = (char *)ExAllocatePoolWithQuotaTag((POOL_TYPE)1536, (unsigned int)(v6 + v4), 0x7070534Bu);
    v9 = PoolWithQuotaTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithQuotaTag )
      memset(PoolWithQuotaTag, 0, (unsigned int)(v6 + v4));
    *(_QWORD *)(a1 + 24) = v9;
    if ( v9 )
    {
      *(_DWORD *)(a1 + 16) |= 0x30u;
      memmove(&v9[v6], *(const void **)(v3 + 32), v4);
      *(_DWORD *)(*(_QWORD *)(a1 + 24) + v6 + 20) = v11;
      if ( v11 == 2 )
      {
        if ( (_DWORD)v5 )
        {
          if ( *(_BYTE *)(a1 + 64) )
            ProbeForRead(*(volatile void **)(a1 + 112), v5, 1u);
          memmove(*(void **)(a1 + 24), *(const void **)(a1 + 112), v5);
        }
      }
    }
    v7 = *(_QWORD *)(a1 + 24);
    if ( !v7 )
      return 3221225626LL;
  }
  v10 = v7 + (unsigned int)v6;
  if ( *(_QWORD *)v10 != *(_QWORD *)&KSPROPSETID_DrmAudioStream.Data1
    || *(_QWORD *)(v10 + 8) != *(_QWORD *)KSPROPSETID_DrmAudioStream.Data4 )
  {
    return 3221226032LL;
  }
  if ( *(_DWORD *)(v10 + 16) )
    return 3221226021LL;
  if ( *(_DWORD *)(v10 + 20) != 2 )
    return 3221225474LL;
  if ( (unsigned int)v4 < 0x58 || (unsigned int)v5 < 0x10 )
    return 3221225507LL;
  return USBC_SetContentId(a1, v10, v7 & -(__int64)((_DWORD)v5 != 0));
}

```

## disassembly

```asm
0x14002c118  mov     [rsp+arg_0], rbx
0x14002c11d  mov     [rsp+arg_10], rsi
0x14002c122  mov     [rsp+arg_8], rdx
0x14002c127  push    rdi
0x14002c128  push    r12
0x14002c12a  push    r13
0x14002c12c  push    r14
0x14002c12e  push    r15
0x14002c130  sub     rsp, 20h
0x14002c134  mov     rdi, rcx
0x14002c137  cmp     byte ptr [rcx+40h], 0
0x14002c13b  jz      short loc_14002C147
0x14002c13d  mov     eax, 0C0000010h
0x14002c142  jmp     loc_14002C2AD
0x14002c147  mov     r13, [rcx+0B8h]
0x14002c14e  mov     r12d, [r13+10h]
0x14002c152  mov     esi, [r13+8]
0x14002c156  lea     r14d, [rsi+7]
0x14002c15a  and     r14d, 0FFFFFFF8h
0x14002c15e  mov     rcx, [rcx+18h]
0x14002c162  test    rcx, rcx
0x14002c165  jnz     loc_14002C249
0x14002c16b  cmp     r12d, 18h
0x14002c16f  jb      loc_14002C242
0x14002c175  cmp     r14d, esi
0x14002c178  jb      loc_14002C242
0x14002c17e  lea     ecx, [r14+r12]
0x14002c182  cmp     ecx, r14d
0x14002c185  jb      loc_14002C242
0x14002c18b  mov     rax, [r13+20h]
0x14002c18f  mov     eax, [rax+14h]
0x14002c192  mov     dword ptr [rsp+48h+arg_8], eax
0x14002c196  mov     ebx, ecx
0x14002c198  mov     r8d, 7070534Bh; Tag
0x14002c19e  mov     edx, ecx; NumberOfBytes
0x14002c1a0  mov     ecx, 600h; PoolType
0x14002c1a5  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14002c1ac  nop     dword ptr [rax+rax+00h]
0x14002c1b1  mov     r15, rax
0x14002c1b4  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002c1bb  jnz     short loc_14002C1CF
0x14002c1bd  test    rax, rax
0x14002c1c0  jz      short loc_14002C1CF
0x14002c1c2  mov     r8d, ebx; Size
0x14002c1c5  xor     edx, edx; Val
0x14002c1c7  mov     rcx, rax; void *
0x14002c1ca  call    memset
0x14002c1cf  mov     [rdi+18h], r15
0x14002c1d3  test    r15, r15
0x14002c1d6  jz      short loc_14002C230
0x14002c1d8  or      dword ptr [rdi+10h], 30h
0x14002c1dc  mov     r8, r12; Size
0x14002c1df  lea     rcx, [r14+r15]; void *
0x14002c1e3  mov     rdx, [r13+20h]; Src
0x14002c1e7  call    memmove
0x14002c1ec  mov     rax, [rdi+18h]
0x14002c1f0  mov     ecx, dword ptr [rsp+48h+arg_8]
0x14002c1f4  mov     [rax+r14+14h], ecx
0x14002c1f9  cmp     ecx, 2
0x14002c1fc  jnz     short loc_14002C230
0x14002c1fe  test    esi, esi
0x14002c200  jz      short loc_14002C230
0x14002c202  cmp     byte ptr [rdi+40h], 0
0x14002c206  jz      short loc_14002C21F
0x14002c208  mov     rdx, rsi; Length
0x14002c20b  lea     r8d, [rcx-1]; Alignment
0x14002c20f  mov     rcx, [rdi+70h]; Address
0x14002c213  call    cs:__imp_ProbeForRead
0x14002c21a  nop     dword ptr [rax+rax+00h]
0x14002c21f  mov     r8, rsi; Size
0x14002c222  mov     rdx, [rdi+70h]; Src
0x14002c226  mov     rcx, [rdi+18h]; void *
0x14002c22a  call    memmove
0x14002c22f  nop
0x14002c230  mov     rcx, [rdi+18h]
0x14002c234  test    rcx, rcx
0x14002c237  jnz     short loc_14002C249
0x14002c239  mov     eax, 0C000009Ah
0x14002c23e  jmp     short loc_14002C2AD
0x14002c240  jmp     short loc_14002C2AD
0x14002c242  mov     eax, 0C0000206h
0x14002c247  jmp     short loc_14002C2AD
0x14002c249  mov     eax, esi
0x14002c24b  neg     eax
0x14002c24d  sbb     r8, r8
0x14002c250  and     r8, rcx
0x14002c253  mov     edx, r14d
0x14002c256  add     rdx, rcx
0x14002c259  mov     rax, qword ptr cs:KSPROPSETID_DrmAudioStream.Data1
0x14002c260  cmp     [rdx], rax
0x14002c263  jnz     short loc_14002C2A8
0x14002c265  mov     rax, qword ptr cs:KSPROPSETID_DrmAudioStream.Data4
0x14002c26c  cmp     [rdx+8], rax
0x14002c270  jnz     short loc_14002C2A8
0x14002c272  cmp     dword ptr [rdx+10h], 0
0x14002c276  jz      short loc_14002C27F
0x14002c278  mov     eax, 0C0000225h
0x14002c27d  jmp     short loc_14002C2AD
0x14002c27f  cmp     dword ptr [rdx+14h], 2
0x14002c283  jz      short loc_14002C28C
0x14002c285  mov     eax, 0C0000002h
0x14002c28a  jmp     short loc_14002C2AD
0x14002c28c  cmp     r12d, 58h ; 'X'
0x14002c290  jb      short loc_14002C2A1
0x14002c292  cmp     esi, 10h
0x14002c295  jb      short loc_14002C2A1
0x14002c297  mov     rcx, rdi
0x14002c29a  call    USBC_SetContentId
0x14002c29f  jmp     short loc_14002C2AD
0x14002c2a1  mov     eax, 0C0000023h
0x14002c2a6  jmp     short loc_14002C2AD
0x14002c2a8  mov     eax, 0C0000230h
0x14002c2ad  mov     rbx, [rsp+48h+arg_0]
0x14002c2b2  mov     rsi, [rsp+48h+arg_10]
0x14002c2b7  add     rsp, 20h
0x14002c2bb  pop     r15
0x14002c2bd  pop     r14
0x14002c2bf  pop     r13
0x14002c2c1  pop     r12
0x14002c2c3  pop     rdi
0x14002c2c4  retn
```
