# CreateBSTRFromHString(ushort *,ushort * *)

- ea: `0x180004e18`
- end: `0x180004eaa`
- name: `?CreateBSTRFromHString@@YAJPEAGPEAPEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(OLECHAR *strIn, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180019a10`
- `0x180020b70`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004e18`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004e56`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004e56`
- `OLEAUT32!__imp_SysFreeString` at `0x180004e8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180004e8b`

## pseudocode

```c
__int64 __fastcall CreateBSTRFromHString(OLECHAR *strIn, unsigned __int16 **a2)
{
  unsigned int v4; // edi
  UINT v5; // ebx
  unsigned __int16 *v6; // rax

  if ( strIn && a2 )
  {
    v5 = *((_DWORD *)strIn - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v6 = SysAllocStringLen(strIn, v5);
    if ( v6 )
    {
      v4 = 0;
      *a2 = v6;
    }
    else
    {
      v4 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
    }
  }
  else
  {
    v4 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x180004e18  mov     [rsp+arg_0], rbx
0x180004e1d  mov     [rsp+arg_8], rsi
0x180004e22  push    rdi
0x180004e23  sub     rsp, 20h
0x180004e27  xor     ebx, ebx
0x180004e29  mov     rsi, rdx
0x180004e2c  mov     rdi, rcx
0x180004e2f  test    rcx, rcx
0x180004e32  jnz     short loc_180004E42
0x180004e34  mov     ecx, 80070057h
0x180004e39  mov     edi, ecx
0x180004e3b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004e40  jmp     short loc_180004E7C
0x180004e42  test    rsi, rsi
0x180004e45  jz      short loc_180004E34
0x180004e47  mov     ebx, [rcx-4]
0x180004e4a  xor     ecx, ecx
0x180004e4c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004e51  mov     edx, ebx; ui
0x180004e53  mov     rcx, rdi; strIn
0x180004e56  call    cs:__imp_SysAllocStringLen
0x180004e5d  nop     dword ptr [rax+rax+00h]
0x180004e62  test    rax, rax
0x180004e65  jnz     short loc_180004E75
0x180004e67  mov     edi, 8007000Eh
0x180004e6c  mov     ecx, edi
0x180004e6e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004e73  jmp     short loc_180004E7A
0x180004e75  xor     edi, edi
0x180004e77  mov     [rsi], rax
0x180004e7a  xor     ebx, ebx
0x180004e7c  mov     ecx, edi
0x180004e7e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004e83  test    rbx, rbx
0x180004e86  jz      short loc_180004E97
0x180004e88  mov     rcx, rbx; bstrString
0x180004e8b  call    cs:__imp_SysFreeString
0x180004e92  nop     dword ptr [rax+rax+00h]
0x180004e97  mov     rbx, [rsp+28h+arg_0]
0x180004e9c  mov     eax, edi
0x180004e9e  mov     rsi, [rsp+28h+arg_8]
0x180004ea3  add     rsp, 20h
0x180004ea7  pop     rdi
0x180004ea8  retn
```
