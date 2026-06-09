# SIPolicyIsSidKnownAdmin

- ea: `0x1800261f0`
- end: `0x180026273`
- name: `SIPolicyIsSidKnownAdmin`
- size: `131`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18004b91c`

## callees

- `0x1800261f0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18002621f`
- `ntdll!RtlEqualSid` at `0x18002621f`

## pseudocode

```c
bool __fastcall SIPolicyIsSidKnownAdmin(PSID Sid1)
{
  unsigned int i; // edi
  bool result; // al

  for ( i = 0; i < 0xD; ++i )
  {
    if ( RtlEqualSid(Sid1, (char *)g_SIPolicyWellKnownSids + 68 * i) )
      return 1;
  }
  result = 0;
  if ( *((_BYTE *)Sid1 + 1) > 1u
    && !*((_BYTE *)Sid1 + 2)
    && !*((_BYTE *)Sid1 + 3)
    && !*((_BYTE *)Sid1 + 4)
    && !*((_BYTE *)Sid1 + 5)
    && !*((_BYTE *)Sid1 + 6)
    && *((_BYTE *)Sid1 + 7) == 5 )
  {
    return *((_DWORD *)Sid1 + 2) == 80;
  }
  return result;
}

```

## disassembly

```asm
0x1800261f0  mov     [rsp+arg_0], rbx
0x1800261f5  mov     [rsp+arg_8], rbp
0x1800261fa  push    rdi
0x1800261fb  sub     rsp, 20h
0x1800261ff  xor     edi, edi
0x180026201  mov     rbx, rcx
0x180026204  lea     ebp, [rdi+1]
0x180026207  cmp     edi, 0Dh
0x18002620a  jnb     short loc_180026232
0x18002620c  mov     eax, edi
0x18002620e  mov     rcx, rbx; Sid1
0x180026211  imul    rdx, rax, 44h ; 'D'
0x180026215  lea     rax, g_SIPolicyWellKnownSids
0x18002621c  add     rdx, rax; Sid2
0x18002621f  call    cs:__imp_RtlEqualSid
0x180026225  test    al, al
0x180026227  jnz     short loc_18002622D
0x180026229  add     edi, ebp
0x18002622b  jmp     short loc_180026207
0x18002622d  mov     al, bpl
0x180026230  jmp     short loc_180026263
0x180026232  xor     al, al
0x180026234  cmp     [rbx+1], bpl
0x180026238  jbe     short loc_180026263
0x18002623a  cmp     [rbx+2], al
0x18002623d  jnz     short loc_180026263
0x18002623f  cmp     [rbx+3], al
0x180026242  jnz     short loc_180026263
0x180026244  cmp     [rbx+4], al
0x180026247  jnz     short loc_180026263
0x180026249  cmp     [rbx+5], al
0x18002624c  jnz     short loc_180026263
0x18002624e  cmp     [rbx+6], al
0x180026251  jnz     short loc_180026263
0x180026253  cmp     byte ptr [rbx+7], 5
0x180026257  jnz     short loc_180026263
0x180026259  cmp     dword ptr [rbx+8], 50h ; 'P'
0x18002625d  movzx   eax, al
0x180026260  cmovz   eax, ebp
0x180026263  mov     rbx, [rsp+28h+arg_0]
0x180026268  mov     rbp, [rsp+28h+arg_8]
0x18002626d  add     rsp, 20h
0x180026271  pop     rdi
0x180026272  retn
```
