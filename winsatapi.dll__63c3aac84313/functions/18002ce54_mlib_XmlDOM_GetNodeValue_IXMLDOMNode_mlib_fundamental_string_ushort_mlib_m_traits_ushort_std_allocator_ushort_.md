# mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,unsigned __int64 &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18002ce54`
- end: `0x18002cf39`
- name: `?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_KPEAV42@@Z`
- size: `229`
- prototype: `__int64 __fastcall(int, int, int, int, BSTR bstrString)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180006970`
- `0x18002b3e8`
- `0x18002b5f8`

## callees

- `0x1800071d0`
- `0x180007220`
- `0x180009d50`
- `0x18000a380`
- `0x18002ce54`

## import_xrefs

- `msvcrt!iswdigit` at `0x18002cedb`
- `msvcrt!iswdigit` at `0x18002cf01`
- `msvcrt!iswdigit` at `0x18002cedb`
- `msvcrt!iswdigit` at `0x18002cf01`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cf23`
- `OLEAUT32!__imp_SysFreeString` at `0x18002cf23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mlib::XmlDOM::GetNodeValue(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, BSTR bstrString)
{
  int NodeValue; // r14d
  OLECHAR *v7; // rcx
  __int64 v8; // rbp
  __int64 v9; // rdi
  wint_t *v10; // rbx
  __int64 v11; // rsi
  int v13; // [rsp+20h] [rbp-58h]
  __int64 *v14[9]; // [rsp+30h] [rbp-48h] BYREF

  v14[1] = (__int64 *)-2LL;
  bstrString = 0;
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, a2, 0, (__int64)&bstrString, v13);
  v7 = bstrString;
  if ( NodeValue >= 0 && bstrString )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      v14,
      bstrString);
    v8 = 0;
    v9 = *v14[0];
    if ( *v14[0] )
    {
      v10 = (wint_t *)v14[0][3];
      while ( (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*v10) )
      {
        ++v10;
        if ( !--v9 )
          goto LABEL_12;
      }
      v11 = 0;
      if ( iswdigit(*v10) )
      {
        do
        {
          v11 = *v10 + 2 * (5 * v11 - 24);
          if ( !--v9 )
            break;
          ++v10;
        }
        while ( iswdigit(*v10) );
        v8 = v11;
      }
    }
LABEL_12:
    *a4 = v8;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v14);
    v7 = bstrString;
  }
  SysFreeString(v7);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x18002ce54  mov     rax, rsp
0x18002ce57  push    rbx
0x18002ce58  push    rbp
0x18002ce59  push    rsi
0x18002ce5a  push    rdi
0x18002ce5b  push    r14
0x18002ce5d  push    r15
0x18002ce5f  sub     rsp, 48h
0x18002ce63  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18002ce6b  mov     r15, r9
0x18002ce6e  mov     qword ptr [rax+28h], 0
0x18002ce76  lea     r9, [rax+28h]
0x18002ce7a  xor     r8d, r8d
0x18002ce7d  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAPEAGPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ushort * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18002ce82  mov     r14d, eax
0x18002ce85  mov     rcx, [rsp+78h+bstrString]
0x18002ce8d  test    eax, eax
0x18002ce8f  js      loc_18002CF23
0x18002ce95  test    rcx, rcx
0x18002ce98  jz      loc_18002CF23
0x18002ce9e  mov     rdx, rcx
0x18002cea1  lea     rcx, [rsp+78h+var_48]
0x18002cea6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18002ceab  xor     ebp, ebp
0x18002cead  mov     rcx, [rsp+78h+var_48]
0x18002ceb2  mov     rdi, [rcx]
0x18002ceb5  test    rdi, rdi
0x18002ceb8  jz      short loc_18002CF0E
0x18002ceba  mov     rbx, [rcx+18h]
0x18002cebe  movzx   ecx, word ptr [rbx]
0x18002cec1  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18002cec6  test    al, al
0x18002cec8  jz      short loc_18002CED6
0x18002ceca  add     rbx, 2
0x18002cece  sub     rdi, 1
0x18002ced2  jnz     short loc_18002CEBE
0x18002ced4  jmp     short loc_18002CF0E
0x18002ced6  xor     esi, esi
0x18002ced8  movzx   ecx, word ptr [rbx]; C
0x18002cedb  call    cs:__imp_iswdigit
0x18002cee1  test    eax, eax
0x18002cee3  jz      short loc_18002CF0E
0x18002cee5  lea     rsi, [rsi+rsi*4]
0x18002cee9  movzx   eax, word ptr [rbx]
0x18002ceec  lea     rsi, [rsi-18h]
0x18002cef0  lea     rsi, [rax+rsi*2]
0x18002cef4  sub     rdi, 1
0x18002cef8  jz      short loc_18002CF0B
0x18002cefa  add     rbx, 2
0x18002cefe  movzx   ecx, word ptr [rbx]; C
0x18002cf01  call    cs:__imp_iswdigit
0x18002cf07  test    eax, eax
0x18002cf09  jnz     short loc_18002CEE5
0x18002cf0b  mov     rbp, rsi
0x18002cf0e  mov     [r15], rbp
0x18002cf11  lea     rcx, [rsp+78h+var_48]
0x18002cf16  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18002cf1b  mov     rcx, [rsp+78h+bstrString]; bstrString
0x18002cf23  call    cs:__imp_SysFreeString
0x18002cf29  mov     eax, r14d
0x18002cf2c  add     rsp, 48h
0x18002cf30  pop     r15
0x18002cf32  pop     r14
0x18002cf34  pop     rdi
0x18002cf35  pop     rsi
0x18002cf36  pop     rbp
0x18002cf37  pop     rbx
0x18002cf38  retn
```
