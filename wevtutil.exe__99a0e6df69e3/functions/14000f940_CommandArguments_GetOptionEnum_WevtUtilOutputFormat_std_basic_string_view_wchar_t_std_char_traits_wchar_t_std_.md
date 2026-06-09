# CommandArguments::GetOptionEnum<WevtUtilOutputFormat>(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,utl::span<ENUM_NAMEVALUE_PAIR<WevtUtilOutputFormat> const,-1>,WevtUtilOutputFormat)

- ea: `0x14000f940`
- end: `0x14000fa68`
- name: `??$GetOptionEnum@W4WevtUtilOutputFormat@@@CommandArguments@@QEBA?AW4WevtUtilOutputFormat@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0V?$span@$$CBU?$ENUM_NAMEVALUE_PAIR@W4WevtUtilOutputFormat@@@@$0?0@utl@@W41@@Z`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001c6b0`
- `0x1400260ac`

## callees

- `0x14000f940`
- `0x140010450`
- `0x140011904`
- `0x140026058`
- `0x140031810`

## pseudocode

```c
__int64 __fastcall CommandArguments::GetOptionEnum<enum WevtUtilOutputFormat>(
        _QWORD *a1,
        __int128 *a2,
        __int128 *a3,
        __int64 *a4)
{
  __int128 v5; // xmm1
  __int64 v7; // rcx
  __int64 v8; // rsi
  const wchar_t *Src; // rsi
  __int64 v11; // rbx
  __int64 v12; // rdi
  const wchar_t *v13; // rsi
  const char *v14; // [rsp+20h] [rbp-78h]
  __int128 v15; // [rsp+40h] [rbp-58h] BYREF
  __int128 v16; // [rsp+50h] [rbp-48h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+8h] BYREF

  v5 = *a2;
  v15 = *a3;
  v16 = v5;
  CommandArguments::GetOption(a1, &v18, &v16, &v15);
  v8 = v18;
  if ( v18 == *a1 )
    return 0;
  if ( !*(_BYTE *)(v18 + 64) )
  {
    Src = (const wchar_t *)(v18 + 32);
    if ( *(_QWORD *)(v18 + 56) > 7u )
      Src = *(const wchar_t **)Src;
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v14, 94, 0xAu, Src);
    throw (EvtException *)pExceptionObject;
  }
  v11 = *a4;
  v12 = *a4 + 16 * a4[1];
  while ( 1 )
  {
    if ( v11 == v12 )
    {
      v13 = (const wchar_t *)(v8 + 32);
      if ( *((_QWORD *)v13 + 3) > 7u )
        v13 = *(const wchar_t **)v13;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v14, 111, 0xDu, v13);
      throw (EvtException *)pExceptionObject;
    }
    if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,std::wstring,wchar_t,wchar_t,0>(
                            v7,
                            v11,
                            v8 + 72) )
      break;
    v11 += 16;
  }
  return *(unsigned int *)(v11 + 8);
}

```

## disassembly

```asm
0x14000f940  mov     rax, rsp
0x14000f943  mov     [rax+10h], rbx
0x14000f947  mov     [rax+18h], rsi
0x14000f94b  push    rdi
0x14000f94c  sub     rsp, 90h
0x14000f953  movaps  xmm0, xmmword ptr [r8]
0x14000f957  mov     rdi, r9
0x14000f95a  movaps  xmm1, xmmword ptr [rdx]
0x14000f95d  lea     r9, [rax-58h]
0x14000f961  lea     r8, [rax-48h]
0x14000f965  movdqa  xmmword ptr [rax-58h], xmm0
0x14000f96a  lea     rdx, [rax+8]
0x14000f96e  movdqa  xmmword ptr [rax-48h], xmm1
0x14000f973  mov     rbx, rcx
0x14000f976  call    ?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::GetOption(std::wstring_view,std::wstring_view)
0x14000f97b  mov     rsi, [rsp+98h+arg_0]
0x14000f983  cmp     rsi, [rbx]
0x14000f986  jnz     short loc_14000F99F
0x14000f988  xor     eax, eax
0x14000f98a  lea     r11, [rsp+98h+var_8]
0x14000f992  mov     rbx, [r11+18h]
0x14000f996  mov     rsi, [r11+20h]
0x14000f99a  mov     rsp, r11
0x14000f99d  pop     rdi
0x14000f99e  retn
0x14000f99f  cmp     byte ptr [rsi+40h], 0
0x14000f9a3  jnz     short loc_14000F9EE
0x14000f9a5  add     rsi, 20h ; ' '
0x14000f9a9  cmp     qword ptr [rsi+18h], 7
0x14000f9ae  jbe     short loc_14000F9B3
0x14000f9b0  mov     rsi, [rsi]
0x14000f9b3  xor     r9d, r9d; unsigned int
0x14000f9b6  mov     [rsp+98h+Src], rsi; Src
0x14000f9bb  mov     [rsp+98h+var_68], 0Ah; unsigned int
0x14000f9c3  lea     rcx, [rsp+98h+pExceptionObject]; this
0x14000f9c8  xor     r8d, r8d; unsigned int
0x14000f9cb  mov     [rsp+98h+var_70], 5Eh ; '^'; int
0x14000f9d3  lea     edx, [r9+57h]; unsigned int
0x14000f9d7  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000f9dc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000f9e3  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14000f9e8  call    _CxxThrowException_0
0x14000f9ee  mov     rbx, [rdi]
0x14000f9f1  mov     rdi, [rdi+8]
0x14000f9f5  shl     rdi, 4
0x14000f9f9  add     rdi, rbx
0x14000f9fc  cmp     rbx, rdi
0x14000f9ff  jz      short loc_14000FA1F
0x14000fa01  lea     r8, [rsi+48h]
0x14000fa05  mov     rdx, rbx
0x14000fa08  call    ??$?RPEB_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBQEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,std::wstring,wchar_t,wchar_t,0>(wchar_t const * const &,std::wstring const &)
0x14000fa0d  test    al, al
0x14000fa0f  jnz     short loc_14000FA17
0x14000fa11  add     rbx, 10h
0x14000fa15  jmp     short loc_14000F9FC
0x14000fa17  mov     eax, [rbx+8]
0x14000fa1a  jmp     loc_14000F98A
0x14000fa1f  add     rsi, 20h ; ' '
0x14000fa23  cmp     qword ptr [rsi+18h], 7
0x14000fa28  jbe     short loc_14000FA2D
0x14000fa2a  mov     rsi, [rsi]
0x14000fa2d  xor     r9d, r9d; unsigned int
0x14000fa30  mov     [rsp+98h+Src], rsi; Src
0x14000fa35  mov     [rsp+98h+var_68], 0Dh; unsigned int
0x14000fa3d  lea     rcx, [rsp+98h+pExceptionObject]; this
0x14000fa42  xor     r8d, r8d; unsigned int
0x14000fa45  mov     [rsp+98h+var_70], 6Fh ; 'o'; int
0x14000fa4d  lea     edx, [r9+57h]; unsigned int
0x14000fa51  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fa56  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fa5d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x14000fa62  call    _CxxThrowException_0
```
