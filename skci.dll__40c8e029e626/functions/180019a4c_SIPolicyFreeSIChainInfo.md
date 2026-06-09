# SIPolicyFreeSIChainInfo

- ea: `0x180019a4c`
- end: `0x180019b25`
- name: `SIPolicyFreeSIChainInfo`
- size: `217`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019410`
- `0x18001d258`
- `0x18001d9d4`
- `0x18001dc98`
- `0x18002019c`
- `0x180020bd4`
- `0x180047a80`
- `0x18004f184`

## callees

- `0x1800187d4`
- `0x180019a4c`

## import_xrefs

- `securekernel!RtlFreeUnicodeString` at `0x180019a88`
- `securekernel!RtlFreeUnicodeString` at `0x180019a9e`
- `securekernel!RtlFreeUnicodeString` at `0x180019ad1`
- `securekernel!RtlFreeUnicodeString` at `0x180019a88`
- `securekernel!RtlFreeUnicodeString` at `0x180019a9e`
- `securekernel!RtlFreeUnicodeString` at `0x180019ad1`

## pseudocode

```c
__int64 __fastcall SIPolicyFreeSIChainInfo(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rbp
  __int64 *i; // rsi
  unsigned int v5; // ebp
  unsigned int v6; // ebx
  __int64 j; // rsi

  if ( !a1 )
    return 0;
  v3 = 0;
  for ( i = (__int64 *)(a1 + 24); (unsigned int)v3 < *(_DWORD *)(a1 + 32); v3 = (unsigned int)(v3 + 1) )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)(48 * v3 + *i + 32));
    RtlFreeUnicodeString((PUNICODE_STRING)(48 * v3 + *i + 16));
    SIPolicyFree(*(_QWORD *)(*i + 48 * v3 + 8));
  }
  SIPolicyFree(*i);
  if ( *(_QWORD *)(a1 + 48) )
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 40));
  v5 = *(_DWORD *)(a1 + 16);
  v6 = 0;
  for ( j = *(_QWORD *)(a1 + 8); v6 < v5; ++v6 )
    SIPolicyFree(*(_QWORD *)(j + 16LL * v6 + 8));
  SIPolicyFree(j);
  result = 0;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x180019a4c  push    rbx
0x180019a4e  push    rbp
0x180019a4f  push    rsi
0x180019a50  push    rdi
0x180019a51  sub     rsp, 28h
0x180019a55  mov     rdi, rcx
0x180019a58  test    rcx, rcx
0x180019a5b  jnz     short loc_180019A64
0x180019a5d  xor     eax, eax
0x180019a5f  jmp     loc_180019B1B
0x180019a64  xor     ebp, ebp
0x180019a66  lea     rsi, [rcx+18h]
0x180019a6a  cmp     [rcx+20h], ebp
0x180019a6d  jbe     short loc_180019ABE
0x180019a6f  mov     rcx, [rsi]
0x180019a72  lea     rbx, ds:0[rbp*2]
0x180019a7a  add     rcx, 20h ; ' '
0x180019a7e  add     rbx, rbp
0x180019a81  shl     rbx, 4
0x180019a85  add     rcx, rbx; UnicodeString
0x180019a88  call    cs:__imp_RtlFreeUnicodeString
0x180019a8f  nop     dword ptr [rax+rax+00h]
0x180019a94  mov     rcx, [rsi]
0x180019a97  add     rcx, 10h
0x180019a9b  add     rcx, rbx; UnicodeString
0x180019a9e  call    cs:__imp_RtlFreeUnicodeString
0x180019aa5  nop     dword ptr [rax+rax+00h]
0x180019aaa  mov     rcx, [rsi]
0x180019aad  mov     rcx, [rcx+rbx+8]
0x180019ab2  call    SIPolicyFree
0x180019ab7  inc     ebp
0x180019ab9  cmp     ebp, [rdi+20h]
0x180019abc  jb      short loc_180019A6F
0x180019abe  mov     rcx, [rsi]
0x180019ac1  call    SIPolicyFree
0x180019ac6  cmp     qword ptr [rdi+30h], 0
0x180019acb  jz      short loc_180019ADD
0x180019acd  lea     rcx, [rdi+28h]; UnicodeString
0x180019ad1  call    cs:__imp_RtlFreeUnicodeString
0x180019ad8  nop     dword ptr [rax+rax+00h]
0x180019add  mov     ebp, [rdi+10h]
0x180019ae0  xor     ebx, ebx
0x180019ae2  mov     rsi, [rdi+8]
0x180019ae6  test    ebp, ebp
0x180019ae8  jz      short loc_180019AFF
0x180019aea  mov     ecx, ebx
0x180019aec  add     rcx, rcx
0x180019aef  mov     rcx, [rsi+rcx*8+8]
0x180019af4  call    SIPolicyFree
0x180019af9  inc     ebx
0x180019afb  cmp     ebx, ebp
0x180019afd  jb      short loc_180019AEA
0x180019aff  mov     rcx, rsi
0x180019b02  call    SIPolicyFree
0x180019b07  xorps   xmm0, xmm0
0x180019b0a  xor     eax, eax
0x180019b0c  movups  xmmword ptr [rdi], xmm0
0x180019b0f  movups  xmmword ptr [rdi+10h], xmm0
0x180019b13  movups  xmmword ptr [rdi+20h], xmm0
0x180019b17  mov     [rdi+30h], rax
0x180019b1b  add     rsp, 28h
0x180019b1f  pop     rdi
0x180019b20  pop     rsi
0x180019b21  pop     rbp
0x180019b22  pop     rbx
0x180019b23  retn
```
