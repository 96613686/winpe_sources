# CWMIContext::WriteMIError(_MI_Result,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180006530`
- end: `0x180006559`
- name: `?WriteMIError@CWMIContext@@UEAAXW4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ad4`
- `0x180006530`

## pseudocode

```c
__int64 __fastcall CWMIContext::WriteMIError(__int64 a1, int a2, __int64 a3)
{
  __int64 result; // rax

  if ( !*(_BYTE *)(a1 + 8) )
  {
    if ( a2 )
    {
      *(_DWORD *)(a1 + 64) = a2;
      *(_WORD *)(a1 + 8) = 257;
      return std::wstring::operator=(a1 + 16, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006530  sub     rsp, 28h
0x180006534  cmp     byte ptr [rcx+8], 0
0x180006538  jnz     short loc_180006553
0x18000653a  test    edx, edx
0x18000653c  jz      short loc_180006553
0x18000653e  mov     [rcx+40h], edx
0x180006541  mov     rdx, r8
0x180006544  mov     word ptr [rcx+8], 101h
0x18000654a  add     rcx, 10h
0x18000654e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180006553  add     rsp, 28h
0x180006557  retn
```
