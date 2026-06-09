# CXMLLogFormatter::EscapeXML(CLogEntryBuilder *,ushort const *,uint *)

- ea: `0x18002365c`
- end: `0x18002378e`
- name: `?EscapeXML@CXMLLogFormatter@@CAHPEAVCLogEntryBuilder@@PEBGPEAI@Z`
- size: `306`
- prototype: `__int64 __fastcall(struct CLogEntryBuilder *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024de0`
- `0x180024fd0`

## callees

- `0x180023380`
- `0x18002365c`

## pseudocode

```c
__int64 __fastcall CXMLLogFormatter::EscapeXML(
        struct CLogEntryBuilder *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  const unsigned __int16 *v4; // rbp
  int v6; // r9d
  unsigned int v7; // esi
  int v8; // eax
  const char *v9; // r8
  const char *v10; // r8

  v4 = a2;
  v6 = 1;
  v7 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      if ( !*v4 )
        goto LABEL_31;
      if ( *v4 == 34 )
        break;
      switch ( *v4 )
      {
        case '&':
          if ( this )
            v6 = CLogEntryBuilder::Printf(this, "%s", "&amp;");
          v8 = 5;
          break;
        case '\'':
          if ( this )
          {
            v10 = "&apos;";
            goto LABEL_24;
          }
          goto LABEL_25;
        case '<':
          if ( this )
          {
            v9 = "&lt;";
LABEL_15:
            v6 = CLogEntryBuilder::Printf(this, "%s", v9);
          }
LABEL_16:
          v8 = 4;
          break;
        case '>':
          if ( this )
          {
            v9 = "&gt;";
            goto LABEL_15;
          }
          goto LABEL_16;
        default:
          if ( this )
            v6 = CLogEntryBuilder::Printf(this, "%C", *v4);
          v8 = 1;
          break;
      }
LABEL_26:
      v7 += v8;
      if ( !v6 )
      {
        if ( a3 )
          *a3 = v7;
        return 0;
      }
      ++v4;
    }
    if ( this )
    {
      v10 = "&quot;";
LABEL_24:
      v6 = CLogEntryBuilder::Printf(this, "%s", v10);
    }
LABEL_25:
    v8 = 6;
    goto LABEL_26;
  }
LABEL_31:
  if ( a3 )
    *a3 = v7;
  return 1;
}

```

## disassembly

```asm
0x18002365c  push    rbx
0x18002365e  push    rbp
0x18002365f  push    rsi
0x180023660  push    rdi
0x180023661  push    r12
0x180023663  push    r14
0x180023665  sub     rsp, 28h
0x180023669  xor     r14d, r14d
0x18002366c  mov     rdi, r8
0x18002366f  mov     rbp, rdx
0x180023672  mov     rbx, rcx
0x180023675  mov     r9d, 1
0x18002367b  mov     esi, r14d
0x18002367e  test    rdx, rdx
0x180023681  jz      loc_180023774
0x180023687  lea     r12, aS_6; "%s"
0x18002368e  cmp     [rbp+0], r14w
0x180023693  jz      loc_180023774
0x180023699  movzx   r8d, word ptr [rbp+0]
0x18002369e  mov     ecx, r8d
0x1800236a1  sub     ecx, 22h ; '"'
0x1800236a4  jz      loc_18002373A
0x1800236aa  sub     ecx, 4
0x1800236ad  jz      short loc_180023719
0x1800236af  sub     ecx, 1
0x1800236b2  jz      short loc_18002370B
0x1800236b4  sub     ecx, 15h
0x1800236b7  jz      short loc_1800236EA
0x1800236b9  cmp     ecx, 2
0x1800236bc  jz      short loc_1800236DC
0x1800236be  test    rbx, rbx
0x1800236c1  jz      short loc_1800236D5
0x1800236c3  lea     rdx, aC_0; "%C"
0x1800236ca  mov     rcx, rbx; this
0x1800236cd  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x1800236d2  mov     r9d, eax
0x1800236d5  mov     eax, 1
0x1800236da  jmp     short loc_180023759
0x1800236dc  test    rbx, rbx
0x1800236df  jz      short loc_180023704
0x1800236e1  lea     r8, aGt; "&gt;"
0x1800236e8  jmp     short loc_1800236F6
0x1800236ea  test    rbx, rbx
0x1800236ed  jz      short loc_180023704
0x1800236ef  lea     r8, aLt; "&lt;"
0x1800236f6  mov     rdx, r12; char *
0x1800236f9  mov     rcx, rbx; this
0x1800236fc  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180023701  mov     r9d, eax
0x180023704  mov     eax, 4
0x180023709  jmp     short loc_180023759
0x18002370b  test    rbx, rbx
0x18002370e  jz      short loc_180023754
0x180023710  lea     r8, aApos; "&apos;"
0x180023717  jmp     short loc_180023746
0x180023719  test    rbx, rbx
0x18002371c  jz      short loc_180023733
0x18002371e  lea     r8, aAmp; "&amp;"
0x180023725  mov     rdx, r12; char *
0x180023728  mov     rcx, rbx; this
0x18002372b  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180023730  mov     r9d, eax
0x180023733  mov     eax, 5
0x180023738  jmp     short loc_180023759
0x18002373a  test    rbx, rbx
0x18002373d  jz      short loc_180023754
0x18002373f  lea     r8, aQuot; "&quot;"
0x180023746  mov     rdx, r12; char *
0x180023749  mov     rcx, rbx; this
0x18002374c  call    ?Printf@CLogEntryBuilder@@QEAAHPEBDZZ; CLogEntryBuilder::Printf(char const *,...)
0x180023751  mov     r9d, eax
0x180023754  mov     eax, 6
0x180023759  add     esi, eax
0x18002375b  test    r9d, r9d
0x18002375e  jz      short loc_180023769
0x180023760  add     rbp, 2
0x180023764  jmp     loc_18002368E
0x180023769  test    rdi, rdi
0x18002376c  jz      short loc_180023770
0x18002376e  mov     [rdi], esi
0x180023770  xor     eax, eax
0x180023772  jmp     short loc_180023780
0x180023774  test    rdi, rdi
0x180023777  jz      short loc_18002377B
0x180023779  mov     [rdi], esi
0x18002377b  mov     eax, 1
0x180023780  add     rsp, 28h
0x180023784  pop     r14
0x180023786  pop     r12
0x180023788  pop     rdi
0x180023789  pop     rsi
0x18002378a  pop     rbp
0x18002378b  pop     rbx
0x18002378c  retn
```
