# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000a310`
- end: `0x18000a378`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAV42@PEAV42@@Z`
- size: `104`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b558`
- `0x18002b5f8`
- `0x18002b714`

## callees

- `0x1800030d0`
- `0x180009d50`
- `0x18000a310`
- `0x18000a770`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a365`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a365`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 **a4,
        char *bstrString)
{
  int NodeValue; // ebx
  __int64 v7; // r8
  OLECHAR *v8; // rcx
  int v10; // [rsp+20h] [rbp-28h]

  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v10);
  v8 = (OLECHAR *)bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      a4,
      bstrString,
      v7);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_lt_ws(a4);
    v8 = (OLECHAR *)bstrString;
  }
  SysFreeString(v8);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18000a310  push    rdi
0x18000a312  sub     rsp, 40h
0x18000a316  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a31f  mov     [rsp+48h+arg_0], rbx
0x18000a324  mov     rdi, r9
0x18000a327  mov     [rsp+48h+bstrString], 0
0x18000a330  lea     r9, [rsp+48h+bstrString]
0x18000a335  xor     r8d, r8d
0x18000a338  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000a33d  mov     ebx, eax
0x18000a33f  mov     rcx, [rsp+48h+bstrString]
0x18000a344  test    eax, eax
0x18000a346  js      short loc_18000A365
0x18000a348  test    rcx, rcx
0x18000a34b  jz      short loc_18000A365
0x18000a34d  mov     rdx, rcx
0x18000a350  mov     rcx, rdi
0x18000a353  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x18000a358  mov     rcx, rdi
0x18000a35b  call    ?strip_lt_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_lt_ws(void)
0x18000a360  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18000a365  call    cs:__imp_SysFreeString
0x18000a36b  mov     eax, ebx
0x18000a36d  mov     rbx, [rsp+48h+arg_0]
0x18000a372  add     rsp, 40h
0x18000a376  pop     rdi
0x18000a377  retn
```
