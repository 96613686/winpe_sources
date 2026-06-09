# CWMIContext::WriteWin32Error(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180006560`
- end: `0x180006588`
- name: `?WriteWin32Error@CWMIContext@@UEAAXKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005a94`
- `0x180006560`

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
0x180006560  sub     rsp, 28h
0x180006564  cmp     byte ptr [rcx+8], 0
0x180006568  jnz     short loc_180006583
0x18000656a  test    edx, edx
0x18000656c  jz      short loc_180006583
0x18000656e  mov     [rcx+44h], edx
0x180006571  mov     rdx, r8
0x180006574  mov     word ptr [rcx+8], 101h
0x18000657a  add     rcx, 10h
0x18000657e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180006583  add     rsp, 28h
0x180006587  retn
```
