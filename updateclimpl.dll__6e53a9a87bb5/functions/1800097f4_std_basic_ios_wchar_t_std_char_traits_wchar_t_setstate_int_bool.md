# std::basic_ios<wchar_t,std::char_traits<wchar_t>>::setstate(int,bool)

- ea: `0x1800097f4`
- end: `0x180009882`
- name: `?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, char, char)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180008f78`
- `0x180009320`
- `0x18000960c`
- `0x1800096f4`
- `0x1800099e0`
- `0x18000ee04`

## callees

- `0x1800097f4`
- `0x180009e50`
- `0x18000a1d8`
- `0x18001440c`

## pseudocode

```c
__int64 __fastcall std::wios::setstate(__int64 a1, char a2, char a3)
{
  __int64 result; // rax
  int v4; // r9d
  int v5; // r9d
  const char *v6; // rdx
  const struct std::error_code *error_code; // rax
  const char *v8; // rdx
  _BYTE v9[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  result = -*(_QWORD *)(a1 + 72);
  v4 = *(_DWORD *)(a1 + 16) & 0x17 | a2 & 0x17 | (*(_QWORD *)(a1 + 72) == 0 ? 4 : 0);
  *(_DWORD *)(a1 + 16) = v4;
  v5 = *(_DWORD *)(a1 + 20) & v4;
  if ( v5 )
  {
    if ( a3 )
      throw;
    if ( (v5 & 4) != 0 )
    {
      v6 = "ios_base::badbit set";
    }
    else
    {
      v6 = "ios_base::failbit set";
      if ( (v5 & 2) == 0 )
        v6 = "ios_base::eofbit set";
    }
    error_code = (const struct std::error_code *)std::make_error_code(v9, v6);
    std::ios_base::failure::failure((std::ios_base::failure *)pExceptionObject, v8, error_code);
    throw (std::ios_base::failure *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800097f4  sub     rsp, 68h
0x1800097f8  mov     rax, [rcx+48h]
0x1800097fc  neg     rax
0x1800097ff  sbb     r9d, r9d
0x180009802  not     r9d
0x180009805  and     r9d, 4
0x180009809  or      r9d, edx
0x18000980c  or      r9d, [rcx+10h]
0x180009810  and     r9d, 17h
0x180009814  mov     [rcx+10h], r9d
0x180009818  and     r9d, [rcx+14h]
0x18000981c  jz      short loc_180009825
0x18000981e  test    r8b, r8b
0x180009821  jz      short loc_180009834
0x180009823  jmp     short loc_18000982A
0x180009825  add     rsp, 68h
0x180009829  retn
0x18000982a  xor     edx, edx; pThrowInfo
0x18000982c  xor     ecx, ecx; pExceptionObject
0x18000982e  call    _CxxThrowException
0x180009834  test    r9b, 4
0x180009838  jz      short loc_180009843
0x18000983a  lea     rdx, aIosBaseBadbitS; "ios_base::badbit set"
0x180009841  jmp     short loc_180009859
0x180009843  test    r9b, 2
0x180009847  lea     rdx, aIosBaseFailbit; "ios_base::failbit set"
0x18000984e  lea     rax, aIosBaseEofbitS; "ios_base::eofbit set"
0x180009855  cmovz   rdx, rax
0x180009859  lea     rcx, [rsp+68h+var_48]
0x18000985e  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@1@@Z; std::make_error_code(std::io_errc)
0x180009863  mov     r8, rax; struct std::error_code *
0x180009866  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000986b  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x180009870  lea     rdx, _TI5?AVfailure@ios_base@std@@; pThrowInfo
0x180009877  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000987c  call    _CxxThrowException
```
