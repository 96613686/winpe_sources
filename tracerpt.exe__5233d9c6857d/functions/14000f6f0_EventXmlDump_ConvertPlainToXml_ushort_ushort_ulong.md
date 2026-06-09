# EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)

- ea: `0x14000f6f0`
- end: `0x14000f885`
- name: `?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z`
- size: `405`
- prototype: `unsigned int __fastcall(EventXmlDump *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000f104`
- `0x14000f88c`

## callees

- `0x140009c78`
- `0x14000f6f0`
- `0x140011f38`
- `0x140040130`

## pseudocode

```c
__int64 __fastcall EventXmlDump::ConvertPlainToXml(
        EventXmlDump *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned __int16 *v6; // rdi
  BOOL v7; // ebx
  int v8; // esi
  int v9; // r9d
  unsigned __int16 *v10; // r8
  unsigned __int16 v11; // cx
  unsigned __int16 v13[16]; // [rsp+20h] [rbp-68h] BYREF

  v6 = a2;
  v7 = *a4 < 2;
  v8 = 0;
  if ( *a2 )
  {
    v9 = 0;
    v10 = 0;
    while ( 1 )
    {
      if ( !v7 )
        v7 = 2 * (unsigned __int64)(unsigned int)(v8 + 1) > *a4;
      if ( v9 )
        break;
      switch ( *v6 )
      {
        case '"':
          v9 = 1;
          v10 = L"&quot;";
          break;
        case '&':
          v9 = 1;
          v10 = L"&amp;";
          break;
        case '<':
          v9 = 1;
          v10 = L"&lt;";
          break;
        case '>':
          v9 = 1;
          v10 = L"&gt;";
          break;
        case '\'':
          v9 = 1;
          v10 = L"&apos;";
          break;
        default:
          if ( !IsPrintable(*v6) )
          {
            v11 = 191;
            goto LABEL_25;
          }
          if ( *v6 <= 0x7Fu )
          {
            v11 = *v6;
LABEL_25:
            ++v6;
LABEL_26:
            if ( !v7 )
              a3[v8] = v11;
            ++v8;
            goto LABEL_29;
          }
          if ( (int)StringCchPrintfW(v13, 0x10u, L"&#%hu;", *v6) < 0 )
            return 13;
          v9 = 1;
          v10 = v13;
LABEL_29:
          if ( !*v6 )
            goto LABEL_30;
          break;
      }
    }
    v11 = *v10;
    if ( *v10 )
    {
      ++v10;
      goto LABEL_26;
    }
    v10 = 0;
    ++v6;
    v9 = 0;
    goto LABEL_29;
  }
LABEL_30:
  if ( !v7 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)(v8 + 1) <= *a4 )
      a3[v8] = 0;
    else
      v7 = 1;
  }
  *a4 = 2 * v8 + 2;
  return v7 ? 0x7A : 0;
}

```

## disassembly

```asm
0x14000f6f0  push    rbx
0x14000f6f2  push    rbp
0x14000f6f3  push    rsi
0x14000f6f4  push    rdi
0x14000f6f5  push    r12
0x14000f6f7  push    r14
0x14000f6f9  push    r15
0x14000f6fb  sub     rsp, 50h
0x14000f6ff  mov     rax, cs:__security_cookie
0x14000f706  xor     rax, rsp
0x14000f709  mov     [rsp+88h+var_48], rax
0x14000f70e  xor     ebp, ebp
0x14000f710  mov     r14, r9
0x14000f713  cmp     dword ptr [r9], 2
0x14000f717  mov     ebx, ebp
0x14000f719  mov     r15, r8
0x14000f71c  mov     rdi, rdx
0x14000f71f  setb    bl
0x14000f722  mov     esi, ebp
0x14000f724  lea     r12d, [rbp+1]
0x14000f728  cmp     [rdx], bp
0x14000f72b  jz      loc_14000F833
0x14000f731  mov     r9d, ebp
0x14000f734  mov     r8d, ebp
0x14000f737  test    ebx, ebx
0x14000f739  jnz     short loc_14000F74B
0x14000f73b  mov     eax, [r14]
0x14000f73e  lea     ecx, [rsi+1]
0x14000f741  add     rcx, rcx
0x14000f744  cmp     rcx, rax
0x14000f747  cmova   ebx, r12d
0x14000f74b  test    r9d, r9d
0x14000f74e  jz      short loc_14000F771
0x14000f750  movzx   ecx, word ptr [r8]
0x14000f754  test    cx, cx
0x14000f757  jnz     short loc_14000F768
0x14000f759  mov     r8, rbp
0x14000f75c  add     rdi, 2
0x14000f760  mov     r9d, ebp
0x14000f763  jmp     loc_14000F827
0x14000f768  add     r8, 2
0x14000f76c  jmp     loc_14000F819
0x14000f771  cmp     word ptr [rdi], 22h ; '"'
0x14000f775  jnz     short loc_14000F783
0x14000f777  mov     r9d, r12d
0x14000f77a  lea     r8, aQuot; "&quot;"
0x14000f781  jmp     short loc_14000F737
0x14000f783  cmp     word ptr [rdi], 26h ; '&'
0x14000f787  jnz     short loc_14000F795
0x14000f789  mov     r9d, r12d
0x14000f78c  lea     r8, aAmp; "&amp;"
0x14000f793  jmp     short loc_14000F737
0x14000f795  cmp     word ptr [rdi], 3Ch ; '<'
0x14000f799  jnz     short loc_14000F7A7
0x14000f79b  mov     r9d, r12d
0x14000f79e  lea     r8, aLt; "&lt;"
0x14000f7a5  jmp     short loc_14000F737
0x14000f7a7  cmp     word ptr [rdi], 3Eh ; '>'
0x14000f7ab  jnz     short loc_14000F7BC
0x14000f7ad  mov     r9d, r12d
0x14000f7b0  lea     r8, aGt; "&gt;"
0x14000f7b7  jmp     loc_14000F737
0x14000f7bc  cmp     word ptr [rdi], 27h ; '''
0x14000f7c0  jnz     short loc_14000F7D1
0x14000f7c2  mov     r9d, r12d
0x14000f7c5  lea     r8, aApos; "&apos;"
0x14000f7cc  jmp     loc_14000F737
0x14000f7d1  movzx   ecx, word ptr [rdi]; unsigned __int16
0x14000f7d4  call    ?IsPrintable@@YA_NG@Z; IsPrintable(ushort)
0x14000f7d9  test    al, al
0x14000f7db  jnz     short loc_14000F7E4
0x14000f7dd  mov     ecx, 0BFh
0x14000f7e2  jmp     short loc_14000F815
0x14000f7e4  cmp     word ptr [rdi], 7Fh
0x14000f7e8  jbe     short loc_14000F812
0x14000f7ea  movzx   r9d, word ptr [rdi]
0x14000f7ee  lea     r8, aHu_0; "&#%hu;"
0x14000f7f5  mov     edx, 10h; unsigned __int64
0x14000f7fa  lea     rcx, [rsp+88h+var_68]; unsigned __int16 *
0x14000f7ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f804  test    eax, eax
0x14000f806  js      short loc_14000F84A
0x14000f808  mov     r9d, r12d
0x14000f80b  lea     r8, [rsp+88h+var_68]
0x14000f810  jmp     short loc_14000F827
0x14000f812  movzx   ecx, word ptr [rdi]
0x14000f815  add     rdi, 2
0x14000f819  test    ebx, ebx
0x14000f81b  jnz     short loc_14000F824
0x14000f81d  mov     eax, esi
0x14000f81f  mov     [r15+rax*2], cx
0x14000f824  add     esi, r12d
0x14000f827  mov     rax, rdi
0x14000f82a  cmp     [rax], bp
0x14000f82d  jnz     loc_14000F737
0x14000f833  test    ebx, ebx
0x14000f835  jnz     short loc_14000F858
0x14000f837  mov     eax, [r14]
0x14000f83a  lea     ecx, [rsi+1]
0x14000f83d  add     rcx, rcx
0x14000f840  cmp     rcx, rax
0x14000f843  jbe     short loc_14000F851
0x14000f845  mov     ebx, r12d
0x14000f848  jmp     short loc_14000F858
0x14000f84a  mov     eax, 0Dh
0x14000f84f  jmp     short loc_14000F869
0x14000f851  mov     ecx, esi
0x14000f853  mov     [r15+rcx*2], bp
0x14000f858  lea     eax, ds:2[rsi*2]
0x14000f85f  neg     ebx
0x14000f861  mov     [r14], eax
0x14000f864  sbb     eax, eax
0x14000f866  and     eax, 7Ah
0x14000f869  mov     rcx, [rsp+88h+var_48]
0x14000f86e  xor     rcx, rsp; StackCookie
0x14000f871  call    __security_check_cookie
0x14000f876  add     rsp, 50h
0x14000f87a  pop     r15
0x14000f87c  pop     r14
0x14000f87e  pop     r12
0x14000f880  pop     rdi
0x14000f881  pop     rsi
0x14000f882  pop     rbp
0x14000f883  pop     rbx
0x14000f884  retn
```
