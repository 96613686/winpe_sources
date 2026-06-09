# CWMIContext::WriteWin32Error(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800065a0`
- end: `0x1800065c9`
- name: `?WriteWin32Error@CWMIContext@@UEAAXKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ad4`
- `0x1800065a0`

## pseudocode

```c
__int64 __fastcall CWMIContext::WriteWin32Error(__int64 a1, int a2, __int64 a3)
{
  __int64 result; // rax

  if ( !*(_BYTE *)(a1 + 8) )
  {
    if ( a2 )
    {
      *(_DWORD *)(a1 + 68) = a2;
      *(_WORD *)(a1 + 8) = 257;
      return std::wstring::operator=(a1 + 16, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800065a0  sub     rsp, 28h
0x1800065a4  cmp     byte ptr [rcx+8], 0
0x1800065a8  jnz     short loc_1800065C3
0x1800065aa  test    edx, edx
0x1800065ac  jz      short loc_1800065C3
0x1800065ae  mov     [rcx+44h], edx
0x1800065b1  mov     rdx, r8
0x1800065b4  mov     word ptr [rcx+8], 101h
0x1800065ba  add     rcx, 10h
0x1800065be  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800065c3  add     rsp, 28h
0x1800065c7  retn
```
