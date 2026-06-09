# std::operator+<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140009f9c`
- end: `0x140009fff`
- name: `??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140058604`

## callees

- `0x140009f9c`
- `0x14000a008`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009fc3`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140009fc3`

## string_xrefs

- `0x140009fd9`: `?L2PageUriPath=`

## pseudocode

```c
__int64 __fastcall std::operator+<unsigned short>(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rcx

  v4 = a3[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v4) < 0xF )
    std::_Xlength_error("string too long");
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  std::wstring::wstring(a1, a2, a3, L"?L2PageUriPath=", 15, a3, v4);
  return a1;
}

```

## disassembly

```asm
0x140009f9c  push    rbx
0x140009f9e  sub     rsp, 50h
0x140009fa2  mov     rbx, rcx
0x140009fa5  mov     rax, 7FFFFFFFFFFFFFFEh
0x140009faf  mov     rcx, [r8+10h]
0x140009fb3  sub     rax, rcx
0x140009fb6  cmp     rax, 0Fh
0x140009fba  jnb     short loc_140009FCA
0x140009fbc  lea     rcx, aStringTooLong; "string too long"
0x140009fc3  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140009fca  cmp     qword ptr [r8+18h], 7
0x140009fcf  jbe     short loc_140009FD4
0x140009fd1  mov     r8, [r8]
0x140009fd4  mov     [rsp+58h+var_28], rcx
0x140009fd9  lea     r9, aL2pageuripath; "?L2PageUriPath="
0x140009fe0  mov     [rsp+58h+var_30], r8
0x140009fe5  mov     rcx, rbx
0x140009fe8  mov     [rsp+58h+var_38], 0Fh
0x140009ff1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140009ff6  mov     rax, rbx
0x140009ff9  add     rsp, 50h
0x140009ffd  pop     rbx
0x140009ffe  retn
```
