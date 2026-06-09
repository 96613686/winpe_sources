# PrintVaultSidInBuffer(void * const,ushort *,ulong)

- ea: `0x180045d1c`
- end: `0x180045d98`
- name: `?PrintVaultSidInBuffer@@YAXQEAXPEAGK@Z`
- size: `124`
- prototype: `void(void *const, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013080`

## callees

- `0x180045d1c`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045d89`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180045d3b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180045d3b`

## pseudocode

```c
void __fastcall PrintVaultSidInBuffer(void *const a1, unsigned __int16 *a2)
{
  LPWSTR v3; // rdi
  BOOL v4; // eax
  unsigned __int64 v5; // rax
  __int64 v6; // rbx
  LPWSTR StringSid; // [rsp+50h] [rbp+8h] BYREF

  StringSid = 0;
  v3 = 0;
  if ( !a1 )
    goto LABEL_8;
  v4 = ConvertSidToStringSidW(a1, &StringSid);
  v3 = StringSid;
  if ( !v4 )
    goto LABEL_8;
  if ( !StringSid )
    goto LABEL_8;
  v5 = -1;
  do
    ++v5;
  while ( StringSid[v5] );
  if ( v5 < 0x104 )
  {
    v6 = (unsigned int)v5;
    memcpy_0(a2, StringSid, v6 * 2);
    a2[v6] = 0;
  }
  else
  {
LABEL_8:
    *a2 = 0;
  }
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x180045d1c  push    rbx
0x180045d1e  push    rbp
0x180045d1f  push    rsi
0x180045d20  push    rdi
0x180045d21  sub     rsp, 28h
0x180045d25  xor     ebp, ebp
0x180045d27  mov     rsi, rdx
0x180045d2a  mov     [rsp+48h+StringSid], rbp
0x180045d2f  mov     edi, ebp
0x180045d31  test    rcx, rcx
0x180045d34  jz      short loc_180045D7E
0x180045d36  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180045d3b  call    cs:__imp_ConvertSidToStringSidW
0x180045d41  mov     rdi, [rsp+48h+StringSid]
0x180045d46  test    eax, eax
0x180045d48  jz      short loc_180045D7E
0x180045d4a  test    rdi, rdi
0x180045d4d  jz      short loc_180045D7E
0x180045d4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045d53  inc     rax
0x180045d56  cmp     [rdi+rax*2], bp
0x180045d5a  jnz     short loc_180045D53
0x180045d5c  cmp     rax, 104h
0x180045d62  jnb     short loc_180045D7E
0x180045d64  mov     eax, eax
0x180045d66  mov     rdx, rdi; Src
0x180045d69  mov     rcx, rsi; void *
0x180045d6c  lea     rbx, [rax+rax]
0x180045d70  mov     r8, rbx; Size
0x180045d73  call    memcpy_0
0x180045d78  mov     [rbx+rsi], bp
0x180045d7c  jmp     short loc_180045D81
0x180045d7e  mov     [rsi], bp
0x180045d81  test    rdi, rdi
0x180045d84  jz      short loc_180045D8F
0x180045d86  mov     rcx, rdi; hMem
0x180045d89  call    cs:__imp_LocalFree
0x180045d8f  add     rsp, 28h
0x180045d93  pop     rdi
0x180045d94  pop     rsi
0x180045d95  pop     rbp
0x180045d96  pop     rbx
0x180045d97  retn
```
