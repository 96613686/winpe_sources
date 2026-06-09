# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002cf40`
- end: `0x18002cfd6`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z`
- size: `150`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002b2e4`
- `0x18002b5f8`

## callees

- `0x1800071d0`
- `0x180007220`
- `0x180009d50`
- `0x18000cda0`
- `0x18002cf40`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002cfc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cfc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, char a3, bool *a4, BSTR bstrString)
{
  int NodeValue; // ebx
  OLECHAR *v7; // rcx
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-28h]
  __int64 *v11[3]; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v12) = a3;
  v11[1] = (__int64 *)-2LL;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v10);
  v7 = bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v11,
      bstrString);
    v12 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::cvt_as_type_signed<int>(
      v8,
      v11[0][3],
      *v11[0],
      &v12);
    *a4 = v12 != 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v11);
    v7 = bstrString;
  }
  SysFreeString(v7);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18002cf40  mov     rax, rsp
0x18002cf43  mov     [rax+18h], r8b
0x18002cf47  push    rdi
0x18002cf48  sub     rsp, 40h
0x18002cf4c  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x18002cf54  mov     [rax+8], rbx
0x18002cf58  mov     rdi, r9
0x18002cf5b  mov     qword ptr [rax+28h], 0
0x18002cf63  lea     r9, [rax+28h]
0x18002cf67  xor     r8d, r8d
0x18002cf6a  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18002cf6f  mov     ebx, eax
0x18002cf71  mov     rcx, [rsp+48h+bstrString]
0x18002cf76  test    eax, eax
0x18002cf78  js      short loc_18002CFC3
0x18002cf7a  test    rcx, rcx
0x18002cf7d  jz      short loc_18002CFC3
0x18002cf7f  mov     rdx, rcx
0x18002cf82  lea     rcx, [rsp+48h+var_18]
0x18002cf87  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18002cf8c  mov     [rsp+48h+arg_10], 0
0x18002cf94  lea     r9, [rsp+48h+arg_10]
0x18002cf99  mov     rdx, [rsp+48h+var_18]
0x18002cf9e  mov     r8, [rdx]
0x18002cfa1  mov     rdx, [rdx+18h]
0x18002cfa5  call    ??$cvt_as_type_signed@H@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEBA_NPEBG_KAEAH_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::cvt_as_type_signed<int>(ushort const *,unsigned __int64,int &,bool)
0x18002cfaa  cmp     [rsp+48h+arg_10], 0
0x18002cfaf  setnz   al
0x18002cfb2  mov     [rdi], al
0x18002cfb4  lea     rcx, [rsp+48h+var_18]
0x18002cfb9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18002cfbe  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18002cfc3  call    cs:__imp_SysFreeString
0x18002cfc9  mov     eax, ebx
0x18002cfcb  mov     rbx, [rsp+48h+arg_0]
0x18002cfd0  add     rsp, 40h
0x18002cfd4  pop     rdi
0x18002cfd5  retn
```
