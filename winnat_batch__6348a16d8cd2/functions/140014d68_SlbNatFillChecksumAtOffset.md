# SlbNatFillChecksumAtOffset

- ea: `0x140014d68`
- end: `0x140014e2f`
- name: `SlbNatFillChecksumAtOffset`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014e38`

## callees

- `0x140014d68`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014dbf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014dbf`
- `NETIO!RtlCopyBufferToMdl` at `0x140014e12`
- `NETIO!RtlCopyBufferToMdl` at `0x140014e12`

## pseudocode

```c
char *__fastcall SlbNatFillChecksumAtOffset(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  __int64 v3; // r10
  __int16 v4; // r9
  int v5; // r11d
  __int64 v7; // rdi
  char *result; // rax
  __int64 v9; // rcx
  char *v10; // rdx
  __int64 v11; // rdx
  __int16 v12[12]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  v4 = 0;
  v5 = *(_DWORD *)(a3 + 16);
  v7 = a2;
  v12[0] = 0;
  if ( *(_DWORD *)(v3 + 40) - v5 < (unsigned int)a2 + 2 )
  {
    LODWORD(v9) = v5;
  }
  else
  {
    if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    {
      result = *(char **)(v3 + 24);
    }
    else
    {
      result = (char *)MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000000u);
      v4 = v12[0];
    }
    v9 = *(unsigned int *)(a3 + 16);
    v10 = &result[v9];
    if ( (((_BYTE)v9 + (_BYTE)result) & 1) == 0 && v10 )
    {
      *(_WORD *)&v10[v7] = v4;
      return result;
    }
  }
  v11 = *(_QWORD *)(a3 + 8);
  v13 = 0;
  return (char *)RtlCopyBufferToMdl(v12, v11, (unsigned int)(v7 + v9), 2, &v13);
}

```

## disassembly

```asm
0x140014d68  mov     [rsp+arg_0], rbx
0x140014d6d  mov     [rsp+arg_8], rsi
0x140014d72  push    rdi
0x140014d73  sub     rsp, 40h
0x140014d77  mov     r10, [r8+8]
0x140014d7b  xor     r9d, r9d; RequestedAddress
0x140014d7e  mov     r11d, [r8+10h]
0x140014d82  mov     rbx, r8
0x140014d85  movzx   edi, dx
0x140014d88  mov     [rsp+48h+var_18], r9w
0x140014d8e  mov     ecx, [r10+28h]
0x140014d92  sub     ecx, r11d
0x140014d95  lea     eax, [rdi+2]
0x140014d98  cmp     ecx, eax
0x140014d9a  jb      short loc_140014DE9
0x140014d9c  test    byte ptr [r10+0Ah], 5
0x140014da1  jz      short loc_140014DA9
0x140014da3  mov     rax, [r10+18h]
0x140014da7  jmp     short loc_140014DD1
0x140014da9  xor     edx, edx; AccessMode
0x140014dab  mov     [rsp+48h+Priority], 40000000h; Priority
0x140014db3  mov     rcx, r10; MemoryDescriptorList
0x140014db6  mov     [rsp+48h+BugCheckOnFailure], r9d; BugCheckOnFailure
0x140014dbb  lea     r8d, [rdx+1]; CacheType
0x140014dbf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014dc6  nop     dword ptr [rax+rax+00h]
0x140014dcb  movzx   r9d, [rsp+48h+var_18]
0x140014dd1  mov     ecx, [rbx+10h]
0x140014dd4  lea     rdx, [rcx+rax]
0x140014dd8  test    dl, 1
0x140014ddb  jnz     short loc_140014DEC
0x140014ddd  test    rdx, rdx
0x140014de0  jz      short loc_140014DEC
0x140014de2  mov     [rdi+rdx], r9w
0x140014de7  jmp     short loc_140014E1E
0x140014de9  mov     ecx, r11d
0x140014dec  mov     rdx, [rbx+8]
0x140014df0  lea     r8d, [rdi+rcx]
0x140014df4  lea     rax, [rsp+48h+arg_10]
0x140014df9  mov     [rsp+48h+arg_10], 0
0x140014e02  lea     rcx, [rsp+48h+var_18]
0x140014e07  mov     qword ptr [rsp+48h+BugCheckOnFailure], rax
0x140014e0c  mov     r9d, 2
0x140014e12  call    cs:__imp_RtlCopyBufferToMdl
0x140014e19  nop     dword ptr [rax+rax+00h]
0x140014e1e  mov     rbx, [rsp+48h+arg_0]
0x140014e23  mov     rsi, [rsp+48h+arg_8]
0x140014e28  add     rsp, 40h
0x140014e2c  pop     rdi
0x140014e2d  retn
```
