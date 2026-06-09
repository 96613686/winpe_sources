# KsPropertyHandleDrmSetContentId

- ea: `0x140091b70`
- end: `0x140091d1e`
- name: `KsPropertyHandleDrmSetContentId`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140018000`

## callees

- `0x140014f04`
- `0x140045640`
- `0x140045940`
- `0x140091b70`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140091bfd`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140091bfd`
- `ntoskrnl!ProbeForRead` at `0x140091c6b`
- `ntoskrnl!ProbeForRead` at `0x140091c6b`

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
  return HUBPDO_DrmSetContentId(a1, v10, v7 & -(__int64)((_DWORD)v5 != 0));
}

```

## disassembly

```asm
0x140091b70  mov     [rsp+arg_0], rbx
0x140091b75  mov     [rsp+arg_10], rsi
0x140091b7a  mov     [rsp+arg_8], rdx
0x140091b7f  push    rdi
0x140091b80  push    r12
0x140091b82  push    r13
0x140091b84  push    r14
0x140091b86  push    r15
0x140091b88  sub     rsp, 20h
0x140091b8c  mov     rdi, rcx
0x140091b8f  cmp     byte ptr [rcx+40h], 0
0x140091b93  jz      short loc_140091B9F
0x140091b95  mov     eax, 0C0000010h
0x140091b9a  jmp     loc_140091D05
0x140091b9f  mov     r13, [rcx+0B8h]
0x140091ba6  mov     r12d, [r13+10h]
0x140091baa  mov     esi, [r13+8]
0x140091bae  lea     r14d, [rsi+7]
0x140091bb2  and     r14d, 0FFFFFFF8h
0x140091bb6  mov     rcx, [rcx+18h]
0x140091bba  test    rcx, rcx
0x140091bbd  jnz     loc_140091CA1
0x140091bc3  cmp     r12d, 18h
0x140091bc7  jb      loc_140091C9A
0x140091bcd  cmp     r14d, esi
0x140091bd0  jb      loc_140091C9A
0x140091bd6  lea     ecx, [r14+r12]
0x140091bda  cmp     ecx, r14d
0x140091bdd  jb      loc_140091C9A
0x140091be3  mov     rax, [r13+20h]
0x140091be7  mov     eax, [rax+14h]
0x140091bea  mov     dword ptr [rsp+48h+arg_8], eax
0x140091bee  mov     ebx, ecx
0x140091bf0  mov     r8d, 7070534Bh; Tag
0x140091bf6  mov     edx, ecx; NumberOfBytes
0x140091bf8  mov     ecx, 600h; PoolType
0x140091bfd  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140091c04  nop     dword ptr [rax+rax+00h]
0x140091c09  mov     r15, rax
0x140091c0c  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140091c13  jnz     short loc_140091C27
0x140091c15  test    rax, rax
0x140091c18  jz      short loc_140091C27
0x140091c1a  mov     r8d, ebx; Size
0x140091c1d  xor     edx, edx; Val
0x140091c1f  mov     rcx, rax; void *
0x140091c22  call    memset
0x140091c27  mov     [rdi+18h], r15
0x140091c2b  test    r15, r15
0x140091c2e  jz      short loc_140091C88
0x140091c30  or      dword ptr [rdi+10h], 30h
0x140091c34  mov     r8, r12; Size
0x140091c37  lea     rcx, [r14+r15]; void *
0x140091c3b  mov     rdx, [r13+20h]; Src
0x140091c3f  call    memmove
0x140091c44  mov     rax, [rdi+18h]
0x140091c48  mov     ecx, dword ptr [rsp+48h+arg_8]
0x140091c4c  mov     [rax+r14+14h], ecx
0x140091c51  cmp     ecx, 2
0x140091c54  jnz     short loc_140091C88
0x140091c56  test    esi, esi
0x140091c58  jz      short loc_140091C88
0x140091c5a  cmp     byte ptr [rdi+40h], 0
0x140091c5e  jz      short loc_140091C77
0x140091c60  mov     rdx, rsi; Length
0x140091c63  lea     r8d, [rcx-1]; Alignment
0x140091c67  mov     rcx, [rdi+70h]; Address
0x140091c6b  call    cs:__imp_ProbeForRead
0x140091c72  nop     dword ptr [rax+rax+00h]
0x140091c77  mov     r8, rsi; Size
0x140091c7a  mov     rdx, [rdi+70h]; Src
0x140091c7e  mov     rcx, [rdi+18h]; void *
0x140091c82  call    memmove
0x140091c87  nop
0x140091c88  mov     rcx, [rdi+18h]
0x140091c8c  test    rcx, rcx
0x140091c8f  jnz     short loc_140091CA1
0x140091c91  mov     eax, 0C000009Ah
0x140091c96  jmp     short loc_140091D05
0x140091c98  jmp     short loc_140091D05
0x140091c9a  mov     eax, 0C0000206h
0x140091c9f  jmp     short loc_140091D05
0x140091ca1  mov     eax, esi
0x140091ca3  neg     eax
0x140091ca5  sbb     r8, r8
0x140091ca8  and     r8, rcx
0x140091cab  mov     edx, r14d
0x140091cae  add     rdx, rcx
0x140091cb1  mov     rax, qword ptr cs:KSPROPSETID_DrmAudioStream.Data1
0x140091cb8  cmp     [rdx], rax
0x140091cbb  jnz     short loc_140091D00
0x140091cbd  mov     rax, qword ptr cs:KSPROPSETID_DrmAudioStream.Data4
0x140091cc4  cmp     [rdx+8], rax
0x140091cc8  jnz     short loc_140091D00
0x140091cca  cmp     dword ptr [rdx+10h], 0
0x140091cce  jz      short loc_140091CD7
0x140091cd0  mov     eax, 0C0000225h
0x140091cd5  jmp     short loc_140091D05
0x140091cd7  cmp     dword ptr [rdx+14h], 2
0x140091cdb  jz      short loc_140091CE4
0x140091cdd  mov     eax, 0C0000002h
0x140091ce2  jmp     short loc_140091D05
0x140091ce4  cmp     r12d, 58h ; 'X'
0x140091ce8  jb      short loc_140091CF9
0x140091cea  cmp     esi, 10h
0x140091ced  jb      short loc_140091CF9
0x140091cef  mov     rcx, rdi
0x140091cf2  call    HUBPDO_DrmSetContentId
0x140091cf7  jmp     short loc_140091D05
0x140091cf9  mov     eax, 0C0000023h
0x140091cfe  jmp     short loc_140091D05
0x140091d00  mov     eax, 0C0000230h
0x140091d05  mov     rbx, [rsp+48h+arg_0]
0x140091d0a  mov     rsi, [rsp+48h+arg_10]
0x140091d0f  add     rsp, 20h
0x140091d13  pop     r15
0x140091d15  pop     r14
0x140091d17  pop     r13
0x140091d19  pop     r12
0x140091d1b  pop     rdi
0x140091d1c  retn
```
