# WapIsHostInBypassList

- ea: `0x18005a454`
- end: `0x18005a67f`
- name: `WapIsHostInBypassList`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a214`

## callees

- `0x1800068a0`
- `0x180021e84`
- `0x18005a454`
- `0x18005a868`
- `0x18005a9a0`
- `0x180083148`
- `0x18008348c`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x18005a4e0`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005a5bd`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005a4e0`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005a5bd`

## pseudocode

```c
char __fastcall WapIsHostInBypassList(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int16 *v8; // rsi
  const wchar_t *v9; // r8
  __int64 v10; // rcx
  char v11; // r14
  __int16 v12; // ax
  __int64 NextProxyListToken; // rax
  __int64 v14; // rsi
  __int64 v15; // r15
  volatile signed __int32 *v16; // rbx
  int v18; // [rsp+20h] [rbp-30h]
  __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF
  __int16 *v22; // [rsp+90h] [rbp+40h] BYREF
  __int64 v23; // [rsp+98h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v19 = 0;
  if ( !(unsigned int)WapUriGetTransformedComponentW(a1, 3, 335544324, a4, (__int64)&v22, (__int64)&v19) )
  {
    v6 = v19;
    v7 = 9;
    v8 = v22;
    if ( v19 == 9 )
    {
      v9 = L"localhost";
    }
    else
    {
      v7 = 8;
      if ( v19 != 8 )
      {
LABEL_7:
        if ( *(_DWORD *)(a1 + 64) == 1 )
        {
          if ( *(_BYTE *)(a1 + 76) != 127 )
            goto LABEL_19;
        }
        else if ( *(_DWORD *)(a1 + 64) != 2
               || *(_WORD *)(a1 + 80)
               || *(_WORD *)(a1 + 82)
               || *(_WORD *)(a1 + 84)
               || *(_WORD *)(a1 + 86)
               || *(_WORD *)(a1 + 88)
               || *(_WORD *)(a1 + 90)
               || *(_WORD *)(a1 + 92)
               || *(_WORD *)(a1 + 94) != 256 )
        {
LABEL_19:
          v10 = *(_QWORD *)(a2 + 16);
          if ( v10 )
          {
            v11 = 0;
            if ( *(_DWORD *)(a1 + 64) != 3 )
              goto LABEL_25;
            do
            {
              if ( !v6 )
              {
                v11 = 1;
                break;
              }
              v12 = *v8;
              --v6;
              ++v8;
            }
            while ( v12 != 46 );
LABEL_25:
            while ( 1 )
            {
              NextProxyListToken = WapGetNextProxyListToken(v10, &v23);
              v14 = NextProxyListToken;
              if ( !NextProxyListToken )
                break;
              v15 = v23;
              lpMem[0] = 0;
              v20 = 0;
              v19 = 0;
              LODWORD(v22) = 0;
              LOBYTE(v18) = 1;
              if ( !(unsigned int)RtlCompareUnicodeStrings(NextProxyListToken, v23, L"<local>", 7, v18) && v11 )
                return 1;
              if ( (unsigned int)WapParseProxyBypassToken(
                                   v14,
                                   v15,
                                   (unsigned int)&v22,
                                   (unsigned int)&v20,
                                   (__int64)&v19)
                || (unsigned int)WaCreateProxyUri((unsigned int)v22, v20, v19, 6, lpMem) )
              {
                return 0;
              }
              v16 = (volatile signed __int32 *)lpMem[0];
              if ( (unsigned __int8)WaCompareUriIsBypassMatch(lpMem[0], a1) )
              {
                if ( _InterlockedExchangeAdd(v16 + 1, 0xFFFFFFFF) == 1 )
                  WapUriFreeUriObject((LPVOID)v16);
                return 1;
              }
              if ( _InterlockedExchangeAdd(v16 + 1, 0xFFFFFFFF) == 1 )
                WapUriFreeUriObject((LPVOID)v16);
              v10 = v14 + 2 * v15;
            }
          }
          return 0;
        }
        return 1;
      }
      v9 = L"loopback";
    }
    LOBYTE(v18) = 1;
    if ( !(unsigned int)RtlCompareUnicodeStrings(v22, v7, v9, v7, v18) )
      return 1;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x18005a454  mov     r11, rsp
0x18005a457  mov     [r11+8], rbx
0x18005a45b  mov     [r11+10h], rsi
0x18005a45f  push    rbp
0x18005a460  push    rdi
0x18005a461  push    r12
0x18005a463  push    r14
0x18005a465  push    r15
0x18005a467  mov     rbp, rsp
0x18005a46a  sub     rsp, 50h
0x18005a46e  xor     r12d, r12d
0x18005a471  lea     rax, [rbp+var_20]
0x18005a475  mov     [r11-50h], rax
0x18005a479  mov     r14, rdx
0x18005a47c  lea     rax, [rbp+arg_10]
0x18005a480  mov     [rbp+arg_18], r12
0x18005a484  mov     r8d, 14000004h
0x18005a48a  mov     [rbp+arg_10], r12
0x18005a48e  lea     edx, [r12+3]
0x18005a493  mov     [rbp+var_20], r12
0x18005a497  mov     rdi, rcx
0x18005a49a  mov     [r11-58h], rax
0x18005a49e  call    WapUriGetTransformedComponentW
0x18005a4a3  test    eax, eax
0x18005a4a5  jnz     loc_18005A663
0x18005a4ab  mov     rbx, [rbp+var_20]
0x18005a4af  lea     edx, [rax+9]
0x18005a4b2  mov     rsi, [rbp+arg_10]
0x18005a4b6  cmp     rbx, rdx
0x18005a4b9  jnz     short loc_18005A4C4
0x18005a4bb  lea     r8, aLocalhost; "localhost"
0x18005a4c2  jmp     short loc_18005A4D5
0x18005a4c4  mov     edx, 8
0x18005a4c9  cmp     rbx, rdx
0x18005a4cc  jnz     short loc_18005A4F4
0x18005a4ce  lea     r8, aLoopback; "loopback"
0x18005a4d5  mov     r9, rdx
0x18005a4d8  mov     byte ptr [rsp+50h+var_30], 1
0x18005a4dd  mov     rcx, rsi
0x18005a4e0  call    cs:__imp_RtlCompareUnicodeStrings
0x18005a4e7  nop     dword ptr [rax+rax+00h]
0x18005a4ec  test    eax, eax
0x18005a4ee  jz      loc_18005A65F
0x18005a4f4  cmp     dword ptr [rdi+40h], 1
0x18005a4f8  jnz     short loc_18005A506
0x18005a4fa  cmp     byte ptr [rdi+4Ch], 7Fh
0x18005a4fe  jz      loc_18005A65F
0x18005a504  jmp     short loc_18005A54C
0x18005a506  cmp     dword ptr [rdi+40h], 2
0x18005a50a  jnz     short loc_18005A54C
0x18005a50c  cmp     [rdi+50h], r12w
0x18005a511  jnz     short loc_18005A54C
0x18005a513  cmp     [rdi+52h], r12w
0x18005a518  jnz     short loc_18005A54C
0x18005a51a  cmp     [rdi+54h], r12w
0x18005a51f  jnz     short loc_18005A54C
0x18005a521  cmp     [rdi+56h], r12w
0x18005a526  jnz     short loc_18005A54C
0x18005a528  cmp     [rdi+58h], r12w
0x18005a52d  jnz     short loc_18005A54C
0x18005a52f  cmp     [rdi+5Ah], r12w
0x18005a534  jnz     short loc_18005A54C
0x18005a536  cmp     [rdi+5Ch], r12w
0x18005a53b  jnz     short loc_18005A54C
0x18005a53d  mov     eax, 100h
0x18005a542  cmp     [rdi+5Eh], ax
0x18005a546  jz      loc_18005A65F
0x18005a54c  mov     rcx, [r14+10h]
0x18005a550  test    rcx, rcx
0x18005a553  jz      loc_18005A663
0x18005a559  cmp     dword ptr [rdi+40h], 3
0x18005a55d  mov     r14b, r12b
0x18005a560  jnz     short loc_18005A57C
0x18005a562  test    rbx, rbx
0x18005a565  jz      short loc_18005A579
0x18005a567  movzx   eax, word ptr [rsi]
0x18005a56a  dec     rbx
0x18005a56d  add     rsi, 2
0x18005a571  cmp     ax, 2Eh ; '.'
0x18005a575  jnz     short loc_18005A562
0x18005a577  jmp     short loc_18005A57C
0x18005a579  mov     r14b, 1
0x18005a57c  lea     rdx, [rbp+arg_18]
0x18005a580  call    WapGetNextProxyListToken
0x18005a585  mov     rsi, rax
0x18005a588  test    rax, rax
0x18005a58b  jz      loc_18005A663
0x18005a591  mov     r15, [rbp+arg_18]
0x18005a595  lea     r8, aLocal; "<local>"
0x18005a59c  mov     rdx, r15
0x18005a59f  mov     [rbp+lpMem], r12
0x18005a5a3  mov     r9d, 7
0x18005a5a9  mov     [rbp+var_18], r12
0x18005a5ad  mov     rcx, rax
0x18005a5b0  mov     [rbp+var_20], r12
0x18005a5b4  mov     dword ptr [rbp+arg_10], r12d
0x18005a5b8  mov     byte ptr [rsp+50h+var_30], 1
0x18005a5bd  call    cs:__imp_RtlCompareUnicodeStrings
0x18005a5c4  nop     dword ptr [rax+rax+00h]
0x18005a5c9  test    eax, eax
0x18005a5cb  jnz     short loc_18005A5D6
0x18005a5cd  test    r14b, r14b
0x18005a5d0  jnz     loc_18005A65F
0x18005a5d6  lea     rax, [rbp+var_20]
0x18005a5da  mov     rdx, r15
0x18005a5dd  lea     r9, [rbp+var_18]
0x18005a5e1  mov     qword ptr [rsp+50h+var_30], rax
0x18005a5e6  lea     r8, [rbp+arg_10]
0x18005a5ea  mov     rcx, rsi
0x18005a5ed  call    WapParseProxyBypassToken
0x18005a5f2  test    eax, eax
0x18005a5f4  jnz     short loc_18005A663
0x18005a5f6  mov     r8, [rbp+var_20]
0x18005a5fa  lea     rax, [rbp+lpMem]
0x18005a5fe  mov     rdx, [rbp+var_18]
0x18005a602  mov     r9d, 6
0x18005a608  mov     ecx, dword ptr [rbp+arg_10]
0x18005a60b  mov     qword ptr [rsp+50h+var_30], rax
0x18005a610  call    WaCreateProxyUri
0x18005a615  test    eax, eax
0x18005a617  jnz     short loc_18005A663
0x18005a619  mov     rbx, [rbp+lpMem]
0x18005a61d  mov     rdx, rdi
0x18005a620  mov     rcx, rbx
0x18005a623  call    WaCompareUriIsBypassMatch
0x18005a628  test    al, al
0x18005a62a  jnz     short loc_18005A64A
0x18005a62c  or      eax, 0FFFFFFFFh
0x18005a62f  lock xadd [rbx+4], eax
0x18005a634  cmp     eax, 1
0x18005a637  jnz     short loc_18005A641
0x18005a639  mov     rcx, rbx; lpMem
0x18005a63c  call    WapUriFreeUriObject
0x18005a641  lea     rcx, [rsi+r15*2]
0x18005a645  jmp     loc_18005A57C
0x18005a64a  or      edx, 0FFFFFFFFh
0x18005a64d  lock xadd [rbx+4], edx
0x18005a652  cmp     edx, 1
0x18005a655  jnz     short loc_18005A65F
0x18005a657  mov     rcx, rbx; lpMem
0x18005a65a  call    WapUriFreeUriObject
0x18005a65f  mov     al, 1
0x18005a661  jmp     short loc_18005A665
0x18005a663  xor     al, al
0x18005a665  lea     r11, [rsp+50h+var_s0]
0x18005a66a  mov     rbx, [r11+30h]
0x18005a66e  mov     rsi, [r11+38h]
0x18005a672  mov     rsp, r11
0x18005a675  pop     r15
0x18005a677  pop     r14
0x18005a679  pop     r12
0x18005a67b  pop     rdi
0x18005a67c  pop     rbp
0x18005a67d  retn
```
