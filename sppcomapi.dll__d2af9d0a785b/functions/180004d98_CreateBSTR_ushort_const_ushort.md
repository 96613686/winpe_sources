# CreateBSTR(ushort const *,ushort * *)

- ea: `0x180004d98`
- end: `0x180004e11`
- name: `?CreateBSTR@@YAJPEBGPEAPEAG@Z`
- size: `121`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180005810`
- `0x180019170`
- `0x180019400`
- `0x1800196d0`
- `0x18001e1d0`
- `0x18001e2e0`
- `0x18001e330`
- `0x18001e380`
- `0x180020e90`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004d98`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004dc4`
- `OLEAUT32!__imp_SysAllocString` at `0x180004dc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004df2`
- `OLEAUT32!__imp_SysFreeString` at `0x180004df2`

## pseudocode

```c
__int64 __fastcall CreateBSTR(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v3; // rcx
  unsigned int v4; // edi
  unsigned __int16 *v5; // rax

  if ( a1 && a2 )
  {
    v5 = SysAllocString(a1);
    if ( v5 )
    {
      v4 = 0;
      *a2 = v5;
      goto LABEL_8;
    }
    v4 = -2147024882;
    v3 = 2147942414LL;
  }
  else
  {
    v3 = 2147942487LL;
    v4 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
LABEL_8:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180004d98  mov     [rsp+arg_0], rbx
0x180004d9d  mov     [rsp+arg_8], rsi
0x180004da2  push    rdi
0x180004da3  sub     rsp, 20h
0x180004da7  xor     ebx, ebx
0x180004da9  mov     rsi, rdx
0x180004dac  test    rcx, rcx
0x180004daf  jnz     short loc_180004DBF
0x180004db1  mov     ecx, 80070057h
0x180004db6  mov     edi, ecx
0x180004db8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004dbd  jmp     short loc_180004DE3
0x180004dbf  test    rsi, rsi
0x180004dc2  jz      short loc_180004DB1
0x180004dc4  call    cs:__imp_SysAllocString
0x180004dcb  nop     dword ptr [rax+rax+00h]
0x180004dd0  test    rax, rax
0x180004dd3  jnz     short loc_180004DDE
0x180004dd5  mov     edi, 8007000Eh
0x180004dda  mov     ecx, edi
0x180004ddc  jmp     short loc_180004DB8
0x180004dde  xor     edi, edi
0x180004de0  mov     [rsi], rax
0x180004de3  mov     ecx, edi
0x180004de5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004dea  test    rbx, rbx
0x180004ded  jz      short loc_180004DFE
0x180004def  mov     rcx, rbx; bstrString
0x180004df2  call    cs:__imp_SysFreeString
0x180004df9  nop     dword ptr [rax+rax+00h]
0x180004dfe  mov     rbx, [rsp+28h+arg_0]
0x180004e03  mov     eax, edi
0x180004e05  mov     rsi, [rsp+28h+arg_8]
0x180004e0a  add     rsp, 20h
0x180004e0e  pop     rdi
0x180004e0f  retn
```
