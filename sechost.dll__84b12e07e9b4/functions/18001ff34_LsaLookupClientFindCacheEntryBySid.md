# LsaLookupClientFindCacheEntryBySid

- ea: `0x18001ff34`
- end: `0x18001ffcc`
- name: `LsaLookupClientFindCacheEntryBySid`
- size: `152`
- prototype: `__int64 __fastcall(PSID Sid2)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ffd4`
- `0x180020d40`

## callees

- `0x180019af0`
- `0x18001ff34`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18001ff50`
- `ntdll!RtlValidSid` at `0x18001ff50`
- `ntdll!RtlEqualSid` at `0x18001ff7e`
- `ntdll!RtlEqualSid` at `0x18001ff7e`

## pseudocode

```c
__int64 __fastcall LsaLookupClientFindCacheEntryBySid(PSID Sid2)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 restarted; // rax
  __int64 *v6; // rsi
  __int64 v7; // rbx
  __int64 **v8; // rax
  __int64 *v9; // rcx
  __int64 *v11; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  v11 = 0;
  if ( RtlValidSid(Sid2) )
  {
    restarted = RtlRestartKeyByIndexGenericTable2(v4, v3, &v11);
    v6 = v11;
    v7 = restarted;
    while ( v7 )
    {
      if ( RtlEqualSid(*(PSID *)v7, Sid2) && *(_BYTE *)(v7 + 88) )
        return v7;
      v8 = (__int64 **)&qword_18007C870;
      if ( v6 )
        v8 = (__int64 **)v6;
      v9 = *v8;
      if ( *v8 == &qword_18007C870 )
        v7 = 0;
      else
        v7 = v9[2];
      v6 = 0;
      if ( v9 != &qword_18007C870 )
        v6 = *v8;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001ff34  mov     [rsp+arg_0], rbx
0x18001ff39  mov     [rsp+arg_10], rbp
0x18001ff3e  push    rsi
0x18001ff3f  push    rdi
0x18001ff40  push    r14
0x18001ff42  sub     rsp, 20h
0x18001ff46  xor     edi, edi
0x18001ff48  mov     rbp, rcx
0x18001ff4b  mov     [rsp+38h+arg_8], rdi
0x18001ff50  call    cs:__imp_RtlValidSid
0x18001ff56  test    al, al
0x18001ff58  jz      short loc_18001FFB6
0x18001ff5a  lea     r8, [rsp+38h+arg_8]
0x18001ff5f  call    RtlRestartKeyByIndexGenericTable2
0x18001ff64  mov     rsi, [rsp+38h+arg_8]
0x18001ff69  lea     r14, qword_18007C870
0x18001ff70  mov     rbx, rax
0x18001ff73  test    rbx, rbx
0x18001ff76  jz      short loc_18001FFB6
0x18001ff78  mov     rcx, [rbx]; Sid1
0x18001ff7b  mov     rdx, rbp; Sid2
0x18001ff7e  call    cs:__imp_RtlEqualSid
0x18001ff84  test    al, al
0x18001ff86  jz      short loc_18001FF8E
0x18001ff88  cmp     [rbx+58h], dil
0x18001ff8c  jnz     short loc_18001FFB3
0x18001ff8e  test    rsi, rsi
0x18001ff91  mov     rax, r14
0x18001ff94  cmovnz  rax, rsi
0x18001ff98  mov     rcx, [rax]
0x18001ff9b  cmp     rcx, r14
0x18001ff9e  jnz     short loc_18001FFA4
0x18001ffa0  xor     ebx, ebx
0x18001ffa2  jmp     short loc_18001FFA8
0x18001ffa4  mov     rbx, [rcx+10h]
0x18001ffa8  xor     esi, esi
0x18001ffaa  cmp     rcx, r14
0x18001ffad  cmovnz  rsi, rcx
0x18001ffb1  jmp     short loc_18001FF73
0x18001ffb3  mov     rdi, rbx
0x18001ffb6  mov     rbx, [rsp+38h+arg_0]
0x18001ffbb  mov     rax, rdi
0x18001ffbe  mov     rbp, [rsp+38h+arg_10]
0x18001ffc3  add     rsp, 20h
0x18001ffc7  pop     r14
0x18001ffc9  pop     rdi
0x18001ffca  pop     rsi
0x18001ffcb  retn
```
