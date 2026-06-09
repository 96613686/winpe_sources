# CScript::GenerateFuncScript(ScriptNode const *)

- ea: `0x1800c4df4`
- end: `0x1800c50e3`
- name: `?GenerateFuncScript@CScript@@AEAAJPEBUScriptNode@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(CScript *__hidden this, const struct ScriptNode *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c50ec`

## callees

- `0x1800c4c44`
- `0x1800c4df4`

## string_xrefs

- `0x1800c4ee2`: `    var rgToken_%d = {};\n`
- `0x1800c4efc`: `    Alt_%d.cToken = %d;\n`
- `0x1800c4f3f`: `    var Token_%d_%d = {};\n`
- `0x1800c4f5a`: `    Token_%d_%d.Latt = %d;\n`
- `0x1800c4fa9`: `    Token_%d_%d.StrIn = "%s";\n`
- `0x1800c4fbc`: `    Token_%d_%d.StrIn = "";\n`
- `0x1800c4fec`: `    Token_%d_%d.RuleName = "%s";\n`
- `0x1800c4fff`: `    Token_%d_%d.RuleName = "";\n`
- `0x1800c5018`: `    rgToken_%d[%d] = Token_%d_%d;\n`
- `0x1800c5045`: `    Alt_%d.rgToken = rgToken_%d;\n`

## pseudocode

```c
__int64 __fastcall CScript::GenerateFuncScript(CScript *this, const struct ScriptNode *a2)
{
  __int64 result; // rax
  unsigned __int16 i; // bp
  unsigned __int16 j; // r15
  __int64 v7; // [rsp+20h] [rbp-58h]
  __int64 v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+28h] [rbp-50h]

  result = CScript::AppendScript(this, L"function ScriptNode_%d()\n", *(unsigned __int16 *)a2);
  if ( (int)result >= 0 )
  {
    result = CScript::AppendScript(this, L"{\n");
    if ( (int)result >= 0 )
    {
      result = CScript::AppendScript(this, L"    var $={};\n");
      if ( (int)result >= 0 )
      {
        result = CScript::AppendScript(this, L"    $.Parsed={};\n");
        if ( (int)result >= 0 )
        {
          result = CScript::AppendScript(this, L"    $.Latt = %d;\n", *(unsigned __int16 *)a2);
          if ( (int)result >= 0 )
          {
            result = CScript::AppendScript(this, L"    $.Parsed.cAlt = %d;\n", *((unsigned __int16 *)a2 + 8));
            if ( (int)result >= 0 )
            {
              result = CScript::AppendScript(this, L"    var rgAlt = {};\n");
              if ( (int)result >= 0 )
              {
                for ( i = 0; i < *((_WORD *)a2 + 8); ++i )
                {
                  result = CScript::AppendScript(this, L"    var Alt_%d = {};\n", i);
                  if ( (int)result < 0 )
                    return result;
                  result = CScript::AppendScript(this, L"    var rgToken_%d = {};\n", i);
                  if ( (int)result < 0 )
                    return result;
                  result = CScript::AppendScript(
                             this,
                             L"    Alt_%d.cToken = %d;\n",
                             i,
                             *(unsigned __int16 *)(*((_QWORD *)a2 + 3) + 24LL * i));
                  if ( (int)result < 0 )
                    return result;
                  for ( j = 0; j < *(_WORD *)(*((_QWORD *)a2 + 3) + 24LL * i); ++j )
                  {
                    result = CScript::AppendScript(this, L"    var Token_%d_%d = {};\n", i, j);
                    if ( (int)result < 0 )
                      return result;
                    LODWORD(v7) = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL * i + 8) + 24LL * j);
                    result = CScript::AppendScript(this, L"    Token_%d_%d.Latt = %d;\n", i, j, v7);
                    if ( (int)result < 0 )
                      return result;
                    result = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL * i + 8) + 24LL * j + 8)
                           ? CScript::AppendScript(
                               this,
                               L"    Token_%d_%d.StrIn = \"%s\";\n",
                               i,
                               j,
                               *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL * i + 8) + 24LL * j + 8))
                           : CScript::AppendScript(this, L"    Token_%d_%d.StrIn = \"\";\n", i, j);
                    if ( (int)result < 0 )
                      return result;
                    result = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL * i + 8) + 24LL * j + 16)
                           ? CScript::AppendScript(
                               this,
                               L"    Token_%d_%d.RuleName = \"%s\";\n",
                               i,
                               j,
                               *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL * i + 8) + 24LL * j + 16))
                           : CScript::AppendScript(this, L"    Token_%d_%d.RuleName = \"\";\n", i, j);
                    if ( (int)result < 0 )
                      return result;
                    LODWORD(v9) = j;
                    LODWORD(v8) = i;
                    result = CScript::AppendScript(this, L"    rgToken_%d[%d] = Token_%d_%d;\n", i, j, v8, v9);
                    if ( (int)result < 0 )
                      return result;
                  }
                  result = CScript::AppendScript(this, L"    Alt_%d.rgToken = rgToken_%d;\n", i, i);
                  if ( (int)result < 0 )
                    return result;
                  result = CScript::AppendScript(this, L"    rgAlt[%d] = Alt_%d;\n", i, i);
                  if ( (int)result < 0 )
                    return result;
                }
                result = CScript::AppendScript(this, L"    $.Parsed.rgAlt = rgAlt;\n");
                if ( (int)result >= 0 )
                {
                  result = CScript::AppendScript(this, L"    $.Network = {};\n");
                  if ( (int)result >= 0 )
                  {
                    result = CScript::AppendScript(this, L"%s", *((_QWORD *)a2 + 1));
                    if ( (int)result >= 0 )
                    {
                      result = CScript::AppendScript(this, L"    return $;\n");
                      if ( (int)result >= 0 )
                        return CScript::AppendScript(this, L"}\n");
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c4df4  push    rbx
0x1800c4df6  push    rbp
0x1800c4df7  push    rsi
0x1800c4df8  push    rdi
0x1800c4df9  push    r12
0x1800c4dfb  push    r13
0x1800c4dfd  push    r14
0x1800c4dff  push    r15
0x1800c4e01  sub     rsp, 38h
0x1800c4e05  movzx   r8d, word ptr [rdx]
0x1800c4e09  mov     rsi, rdx
0x1800c4e0c  lea     rdx, aFunctionScript; "function ScriptNode_%d()\n"
0x1800c4e13  mov     rbx, rcx
0x1800c4e16  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e1b  test    eax, eax
0x1800c4e1d  js      loc_1800C50D2
0x1800c4e23  lea     rdx, asc_1801147FC; "{\n"
0x1800c4e2a  mov     rcx, rbx; this
0x1800c4e2d  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e32  test    eax, eax
0x1800c4e34  js      loc_1800C50D2
0x1800c4e3a  lea     rdx, aVar; "    var $={};\n"
0x1800c4e41  mov     rcx, rbx; this
0x1800c4e44  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e49  test    eax, eax
0x1800c4e4b  js      loc_1800C50D2
0x1800c4e51  lea     rdx, aParsed; "    $.Parsed={};\n"
0x1800c4e58  mov     rcx, rbx; this
0x1800c4e5b  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e60  test    eax, eax
0x1800c4e62  js      loc_1800C50D2
0x1800c4e68  movzx   r8d, word ptr [rsi]
0x1800c4e6c  lea     rdx, aLattD; "    $.Latt = %d;\n"
0x1800c4e73  mov     rcx, rbx; this
0x1800c4e76  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e7b  test    eax, eax
0x1800c4e7d  js      loc_1800C50D2
0x1800c4e83  movzx   r8d, word ptr [rsi+10h]
0x1800c4e88  lea     rdx, aParsedCaltD; "    $.Parsed.cAlt = %d;\n"
0x1800c4e8f  mov     rcx, rbx; this
0x1800c4e92  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4e97  test    eax, eax
0x1800c4e99  js      loc_1800C50D2
0x1800c4e9f  lea     rdx, aVarRgalt; "    var rgAlt = {};\n"
0x1800c4ea6  mov     rcx, rbx; this
0x1800c4ea9  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4eae  test    eax, eax
0x1800c4eb0  js      loc_1800C50D2
0x1800c4eb6  xor     ebp, ebp
0x1800c4eb8  mov     rcx, rbx; this
0x1800c4ebb  cmp     bp, [rsi+10h]
0x1800c4ebf  jnb     loc_1800C5076
0x1800c4ec5  movzx   edi, bp
0x1800c4ec8  lea     rdx, aVarAltD; "    var Alt_%d = {};\n"
0x1800c4ecf  mov     r8d, edi
0x1800c4ed2  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4ed7  test    eax, eax
0x1800c4ed9  js      loc_1800C50D2
0x1800c4edf  mov     r8d, edi
0x1800c4ee2  lea     rdx, aVarRgtokenD; "    var rgToken_%d = {};\n"
0x1800c4ee9  mov     rcx, rbx; this
0x1800c4eec  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4ef1  test    eax, eax
0x1800c4ef3  js      loc_1800C50D2
0x1800c4ef9  movzx   eax, bp
0x1800c4efc  lea     rdx, aAltDCtokenD; "    Alt_%d.cToken = %d;\n"
0x1800c4f03  mov     r8d, edi
0x1800c4f06  mov     rcx, rbx; this
0x1800c4f09  lea     r12, [rax+rax*2]
0x1800c4f0d  mov     rax, [rsi+18h]
0x1800c4f11  movzx   r9d, word ptr [rax+r12*8]
0x1800c4f16  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4f1b  test    eax, eax
0x1800c4f1d  js      loc_1800C50D2
0x1800c4f23  xor     r15d, r15d
0x1800c4f26  mov     rax, [rsi+18h]
0x1800c4f2a  mov     r8d, edi
0x1800c4f2d  mov     rcx, rbx; this
0x1800c4f30  cmp     r15w, [rax+r12*8]
0x1800c4f35  jnb     loc_1800C5042
0x1800c4f3b  movzx   r14d, r15w
0x1800c4f3f  lea     rdx, aVarTokenDD; "    var Token_%d_%d = {};\n"
0x1800c4f46  mov     r9d, r14d
0x1800c4f49  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4f4e  test    eax, eax
0x1800c4f50  js      loc_1800C50D2
0x1800c4f56  movzx   eax, r15w
0x1800c4f5a  lea     rdx, aTokenDDLattD; "    Token_%d_%d.Latt = %d;\n"
0x1800c4f61  mov     r9d, r14d
0x1800c4f64  mov     r8d, edi
0x1800c4f67  lea     r13, [rax+rax*2]
0x1800c4f6b  mov     rax, [rsi+18h]
0x1800c4f6f  mov     rcx, [rax+r12*8+8]
0x1800c4f74  movzx   eax, word ptr [rcx+r13*8]
0x1800c4f79  mov     rcx, rbx; this
0x1800c4f7c  mov     dword ptr [rsp+78h+var_58], eax
0x1800c4f80  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4f85  test    eax, eax
0x1800c4f87  js      loc_1800C50D2
0x1800c4f8d  mov     rax, [rsi+18h]
0x1800c4f91  mov     r9d, r14d
0x1800c4f94  mov     r8d, edi
0x1800c4f97  mov     rcx, [rax+r12*8+8]
0x1800c4f9c  mov     rax, [rcx+r13*8+8]
0x1800c4fa1  mov     rcx, rbx; this
0x1800c4fa4  test    rax, rax
0x1800c4fa7  jz      short loc_1800C4FBC
0x1800c4fa9  lea     rdx, aTokenDDStrinS; "    Token_%d_%d.StrIn = \"%s\";\n"
0x1800c4fb0  mov     [rsp+78h+var_58], rax
0x1800c4fb5  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4fba  jmp     short loc_1800C4FC8
0x1800c4fbc  lea     rdx, aTokenDDStrin; "    Token_%d_%d.StrIn = \"\";\n"
0x1800c4fc3  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4fc8  test    eax, eax
0x1800c4fca  js      loc_1800C50D2
0x1800c4fd0  mov     rax, [rsi+18h]
0x1800c4fd4  mov     r9d, r14d
0x1800c4fd7  mov     r8d, edi
0x1800c4fda  mov     rcx, [rax+r12*8+8]
0x1800c4fdf  mov     rax, [rcx+r13*8+10h]
0x1800c4fe4  mov     rcx, rbx; this
0x1800c4fe7  test    rax, rax
0x1800c4fea  jz      short loc_1800C4FFF
0x1800c4fec  lea     rdx, aTokenDDRulenam; "    Token_%d_%d.RuleName = \"%s\";\n"
0x1800c4ff3  mov     [rsp+78h+var_58], rax
0x1800c4ff8  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c4ffd  jmp     short loc_1800C500B
0x1800c4fff  lea     rdx, aTokenDDRulenam_0; "    Token_%d_%d.RuleName = \"\";\n"
0x1800c5006  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c500b  test    eax, eax
0x1800c500d  js      loc_1800C50D2
0x1800c5013  mov     dword ptr [rsp+78h+var_50], r14d
0x1800c5018  lea     rdx, aRgtokenDDToken; "    rgToken_%d[%d] = Token_%d_%d;\n"
0x1800c501f  mov     r9d, r14d
0x1800c5022  mov     dword ptr [rsp+78h+var_58], edi
0x1800c5026  mov     r8d, edi
0x1800c5029  mov     rcx, rbx; this
0x1800c502c  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c5031  test    eax, eax
0x1800c5033  js      loc_1800C50D2
0x1800c5039  inc     r15w
0x1800c503d  jmp     loc_1800C4F26
0x1800c5042  mov     r9d, edi
0x1800c5045  lea     rdx, aAltDRgtokenRgt; "    Alt_%d.rgToken = rgToken_%d;\n"
0x1800c504c  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c5051  test    eax, eax
0x1800c5053  js      short loc_1800C50D2
0x1800c5055  mov     r9d, edi
0x1800c5058  lea     rdx, aRgaltDAltD; "    rgAlt[%d] = Alt_%d;\n"
0x1800c505f  mov     r8d, edi
0x1800c5062  mov     rcx, rbx; this
0x1800c5065  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c506a  test    eax, eax
0x1800c506c  js      short loc_1800C50D2
0x1800c506e  inc     bp
0x1800c5071  jmp     loc_1800C4EB8
0x1800c5076  lea     rdx, aParsedRgaltRga; "    $.Parsed.rgAlt = rgAlt;\n"
0x1800c507d  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c5082  test    eax, eax
0x1800c5084  js      short loc_1800C50D2
0x1800c5086  lea     rdx, aNetwork_0; "    $.Network = {};\n"
0x1800c508d  mov     rcx, rbx; this
0x1800c5090  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c5095  test    eax, eax
0x1800c5097  js      short loc_1800C50D2
0x1800c5099  mov     r8, [rsi+8]
0x1800c509d  lea     rdx, aS_2; "%s"
0x1800c50a4  mov     rcx, rbx; this
0x1800c50a7  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c50ac  test    eax, eax
0x1800c50ae  js      short loc_1800C50D2
0x1800c50b0  lea     rdx, aReturn; "    return $;\n"
0x1800c50b7  mov     rcx, rbx; this
0x1800c50ba  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c50bf  test    eax, eax
0x1800c50c1  js      short loc_1800C50D2
0x1800c50c3  lea     rdx, asc_180114C68; "}\n"
0x1800c50ca  mov     rcx, rbx; this
0x1800c50cd  call    ?AppendScript@CScript@@AEAAJPEBGZZ; CScript::AppendScript(ushort const *,...)
0x1800c50d2  add     rsp, 38h
0x1800c50d6  pop     r15
0x1800c50d8  pop     r14
0x1800c50da  pop     r13
0x1800c50dc  pop     r12
0x1800c50de  pop     rdi
0x1800c50df  pop     rsi
0x1800c50e0  pop     rbp
0x1800c50e1  pop     rbx
0x1800c50e2  retn
```
