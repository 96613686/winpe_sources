# WanpPreparePacketsForSend

- ea: `0x140015b80`
- end: `0x140015cde`
- name: `WanpPreparePacketsForSend`
- size: `350`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400142dc`

## callees

- `0x1400050b0`
- `0x140015b80`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015ccd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015ccd`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140015c9e`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140015c9e`

## pseudocode

```c
__int64 __fastcall WanpPreparePacketsForSend(__int64 a1, __int64 a2)
{
  __int64 *v2; // rbx
  char *v3; // rdi
  __int64 v5; // r10
  char *v6; // rax
  char *v7; // rdx
  __int16 v8; // ax
  __int64 v10; // xmm0_8
  __int64 i; // [rsp+30h] [rbp-68h] BYREF
  __int64 v12; // [rsp+40h] [rbp-58h] BYREF
  int v13; // [rsp+48h] [rbp-50h]
  __int16 v14; // [rsp+4Ch] [rbp-4Ch]

  v2 = *(__int64 **)(a1 + 8);
  v3 = 0;
  for ( i = 0; v2; v2 = (__int64 *)*v2 )
  {
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a2 + 8) + 280LL));
    v5 = v2[1];
    if ( (unsigned int)(*(_DWORD *)(v5 + 40) - *((_DWORD *)v2 + 4)) < 0xE
      || ((*(_BYTE *)(v5 + 10) & 5) == 0
        ? (v6 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000000u))
        : (v6 = *(char **)(v5 + 24)),
          (v7 = &v6[*((unsigned int *)v2 + 4)], ((unsigned __int8)v7 & 1) != 0) || !v7) )
    {
      v10 = *(_QWORD *)(a2 + 108);
      v13 = *(_DWORD *)(a2 + 116);
      v14 = *(_WORD *)(a2 + 120);
      v12 = v10;
      RtlCopyKernelBufferToMdl(&v12, v2[1], *((unsigned int *)v2 + 4), 14, &i);
    }
    else
    {
      if ( v3 )
      {
        *(_QWORD *)v7 = *(_QWORD *)v3;
        *((_DWORD *)v7 + 2) = *((_DWORD *)v3 + 2);
        v8 = *((_WORD *)v3 + 6);
      }
      else
      {
        v3 = &v6[*((unsigned int *)v2 + 4)];
        *(_QWORD *)v7 = *(_QWORD *)(a2 + 108);
        *((_DWORD *)v7 + 2) = *(_DWORD *)(a2 + 116);
        v8 = *(_WORD *)(a2 + 120);
      }
      *((_WORD *)v7 + 6) = v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140015b80  mov     [rsp+arg_10], rbx
0x140015b85  mov     [rsp+arg_18], rsi
0x140015b8a  push    rdi
0x140015b8b  sub     rsp, 90h
0x140015b92  mov     rax, cs:__security_cookie
0x140015b99  xor     rax, rsp
0x140015b9c  mov     [rsp+98h+var_18], rax
0x140015ba4  mov     rbx, [rcx+8]
0x140015ba8  xor     edi, edi
0x140015baa  mov     [rsp+98h+var_68], 0
0x140015bb3  mov     rsi, rdx
0x140015bb6  test    rbx, rbx
0x140015bb9  jz      short loc_140015C26
0x140015bbb  nop     dword ptr [rax+rax+00h]
0x140015bc0  mov     rax, [rsi+8]
0x140015bc4  lock inc qword ptr [rax+118h]
0x140015bcc  mov     r10, [rbx+8]
0x140015bd0  mov     ecx, [r10+28h]
0x140015bd4  sub     ecx, [rbx+10h]
0x140015bd7  cmp     ecx, 0Eh
0x140015bda  jb      loc_140015C66
0x140015be0  test    byte ptr [r10+0Ah], 5
0x140015be5  jz      loc_140015CAF
0x140015beb  mov     rax, [r10+18h]
0x140015bef  mov     edx, [rbx+10h]
0x140015bf2  add     rdx, rax
0x140015bf5  test    dl, 1
0x140015bf8  jnz     short loc_140015C66
0x140015bfa  test    rdx, rdx
0x140015bfd  jz      short loc_140015C66
0x140015bff  test    rdi, rdi
0x140015c02  jnz     short loc_140015C4E
0x140015c04  movsd   xmm0, qword ptr [rsi+6Ch]
0x140015c09  mov     rdi, rdx
0x140015c0c  movsd   qword ptr [rdx], xmm0
0x140015c10  mov     eax, [rsi+74h]
0x140015c13  mov     [rdx+8], eax
0x140015c16  movzx   eax, word ptr [rsi+78h]
0x140015c1a  mov     [rdx+0Ch], ax
0x140015c1e  mov     rbx, [rbx]
0x140015c21  test    rbx, rbx
0x140015c24  jnz     short loc_140015BC0
0x140015c26  xor     eax, eax
0x140015c28  mov     rcx, [rsp+98h+var_18]
0x140015c30  xor     rcx, rsp; StackCookie
0x140015c33  call    __security_check_cookie
0x140015c38  lea     r11, [rsp+98h+var_8]
0x140015c40  mov     rbx, [r11+20h]
0x140015c44  mov     rsi, [r11+28h]
0x140015c48  mov     rsp, r11
0x140015c4b  pop     rdi
0x140015c4c  retn
0x140015c4e  movsd   xmm0, qword ptr [rdi]
0x140015c52  movsd   qword ptr [rdx], xmm0
0x140015c56  mov     eax, [rdi+8]
0x140015c59  mov     [rdx+8], eax
0x140015c5c  movzx   eax, word ptr [rdi+0Ch]
0x140015c60  mov     [rdx+0Ch], ax
0x140015c64  jmp     short loc_140015C1E
0x140015c66  mov     eax, [rsi+74h]
0x140015c69  lea     rcx, [rsp+98h+var_58]
0x140015c6e  movsd   xmm0, qword ptr [rsi+6Ch]
0x140015c73  mov     r9d, 0Eh
0x140015c79  mov     [rsp+98h+var_50], eax
0x140015c7d  movzx   eax, word ptr [rsi+78h]
0x140015c81  mov     [rsp+98h+var_4C], ax
0x140015c86  lea     rax, [rsp+98h+var_68]
0x140015c8b  movsd   [rsp+98h+var_58], xmm0
0x140015c91  mov     r8d, [rbx+10h]
0x140015c95  mov     rdx, [rbx+8]
0x140015c99  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x140015c9e  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140015ca5  nop     dword ptr [rax+rax+00h]
0x140015caa  jmp     loc_140015C1E
0x140015caf  mov     [rsp+98h+Priority], 40000000h; Priority
0x140015cb7  xor     r9d, r9d; RequestedAddress
0x140015cba  xor     edx, edx; AccessMode
0x140015cbc  mov     [rsp+98h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140015cc4  mov     r8d, 1; CacheType
0x140015cca  mov     rcx, r10; MemoryDescriptorList
0x140015ccd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015cd4  nop     dword ptr [rax+rax+00h]
0x140015cd9  jmp     loc_140015BEF
```
