# CommandArguments::GetOptionInteger64(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,__int64,bool &)

- ea: `0x14000eeb4`
- end: `0x14000f094`
- name: `?GetOptionInteger64@CommandArguments@@QEBA_JV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_JAEA_N@Z`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400124fc`

## callees

- `0x14000eeb4`
- `0x140010450`
- `0x140011904`
- `0x1400225cc`
- `0x140022cec`
- `0x140031810`

## pseudocode

```c
__int64 CommandArguments::GetOptionInteger64(_QWORD *a1, __int128 *a2, __int128 *a3, ...)
{
  __int128 v3; // xmm1
  __int64 v5; // rbx
  const wchar_t *v7; // rcx
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  const wchar_t *Src; // rbx
  const wchar_t *v11; // rbx
  const char *v12; // [rsp+28h] [rbp-21h]
  __int128 v13; // [rsp+48h] [rbp-1h] BYREF
  __int128 v14; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+A8h] [rbp+5Fh] BYREF
  __int64 v17; // [rsp+C0h] [rbp+77h] BYREF
  va_list va; // [rsp+C0h] [rbp+77h]
  _BYTE *v19; // [rsp+C8h] [rbp+7Fh]
  va_list va1; // [rsp+D0h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v17 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _BYTE *);
  v3 = *a2;
  v13 = *a3;
  v14 = v3;
  CommandArguments::GetOption(a1, &v16, &v14, &v13);
  v5 = v16;
  if ( v16 == *a1 )
  {
    *v19 = 0;
    return 0;
  }
  else
  {
    if ( !*(_BYTE *)(v16 + 64)
      || ((v7 = (const wchar_t *)(v16 + 72), *(_QWORD *)(v16 + 96) <= 7u)
        ? (v8 = (const wchar_t *)(v16 + 72))
        : (v8 = *(const wchar_t **)v7),
          !v8 || (*(_QWORD *)(v16 + 96) <= 7u ? (v9 = (const wchar_t *)(v16 + 72)) : (v9 = *(const wchar_t **)v7), !*v9)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
      }
      v11 = (const wchar_t *)(v5 + 32);
      if ( *((_QWORD *)v11 + 3) > 7u )
        v11 = *(const wchar_t **)v11;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v12, 103, 9u, v11);
      throw (EvtException *)pExceptionObject;
    }
    v17 = 0;
    *v19 = 1;
    if ( *(_QWORD *)(v5 + 96) > 7u )
      v7 = *(const wchar_t **)v7;
    if ( swscanf(v7, L"%I64i", va) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
      }
      Src = (const wchar_t *)(v5 + 32);
      if ( *((_QWORD *)Src + 3) > 7u )
        Src = *(const wchar_t **)Src;
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v12, 111, 0x23u, Src);
      throw (EvtException *)pExceptionObject;
    }
    return v17;
  }
}

```

## disassembly

```asm
0x14000eeb4  mov     rax, rsp
0x14000eeb7  mov     [rax+10h], rbx
0x14000eebb  mov     [rax+18h], rdi
0x14000eebf  mov     [rax+20h], r9
0x14000eec3  push    rbp
0x14000eec4  lea     rbp, [rax-57h]
0x14000eec8  sub     rsp, 90h
0x14000eecf  movaps  xmm0, xmmword ptr [r8]
0x14000eed3  lea     r9, [rbp+4Fh+var_50]
0x14000eed7  movaps  xmm1, xmmword ptr [rdx]
0x14000eeda  lea     r8, [rbp+4Fh+var_40]
0x14000eede  lea     rdx, [rbp+4Fh+arg_0]
0x14000eee2  movdqa  [rbp+4Fh+var_50], xmm0
0x14000eee7  movdqa  [rbp+4Fh+var_40], xmm1
0x14000eeec  mov     rdi, rcx
0x14000eeef  call    ?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::GetOption(std::wstring_view,std::wstring_view)
0x14000eef4  mov     rbx, [rbp+4Fh+arg_0]
0x14000eef8  xor     edx, edx
0x14000eefa  cmp     rbx, [rdi]
0x14000eefd  jnz     short loc_14000EF1C
0x14000eeff  mov     rax, [rbp+4Fh+arg_20]
0x14000ef03  mov     [rax], dl
0x14000ef05  xor     eax, eax
0x14000ef07  lea     r11, [rsp+90h+var_s0]
0x14000ef0f  mov     rbx, [r11+18h]
0x14000ef13  mov     rdi, [r11+20h]
0x14000ef17  mov     rsp, r11
0x14000ef1a  pop     rbp
0x14000ef1b  retn
0x14000ef1c  cmp     [rbx+40h], dl
0x14000ef1f  jz      loc_14000F012
0x14000ef25  lea     rcx, [rbx+48h]
0x14000ef29  cmp     qword ptr [rcx+18h], 7
0x14000ef2e  jbe     short loc_14000EF35
0x14000ef30  mov     rax, [rcx]
0x14000ef33  jmp     short loc_14000EF38
0x14000ef35  mov     rax, rcx
0x14000ef38  test    rax, rax
0x14000ef3b  jz      loc_14000F012
0x14000ef41  cmp     qword ptr [rcx+18h], 7
0x14000ef46  jbe     short loc_14000EF4D
0x14000ef48  mov     rax, [rcx]
0x14000ef4b  jmp     short loc_14000EF50
0x14000ef4d  mov     rax, rcx
0x14000ef50  cmp     [rax], dx
0x14000ef53  jz      loc_14000F012
0x14000ef59  mov     rax, [rbp+4Fh+arg_20]
0x14000ef5d  mov     [rbp+4Fh+arg_18], rdx
0x14000ef61  mov     byte ptr [rax], 1
0x14000ef64  cmp     qword ptr [rcx+18h], 7
0x14000ef69  jbe     short loc_14000EF6E
0x14000ef6b  mov     rcx, [rcx]; Buffer
0x14000ef6e  lea     r8, [rbp+4Fh+arg_18]
0x14000ef72  lea     rdx, aI64i; "%I64i"
0x14000ef79  call    swscanf
0x14000ef7e  cmp     eax, 1
0x14000ef81  jz      loc_14000F009
0x14000ef87  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef8e  lea     rax, WPP_GLOBAL_Control
0x14000ef95  mov     edi, 57h ; 'W'
0x14000ef9a  cmp     rcx, rax
0x14000ef9d  jz      short loc_14000EFC4
0x14000ef9f  test    dword ptr [rcx+1Ch], 400000h
0x14000efa6  jz      short loc_14000EFC4
0x14000efa8  cmp     byte ptr [rcx+19h], 2
0x14000efac  jb      short loc_14000EFC4
0x14000efae  mov     rcx, [rcx+10h]
0x14000efb2  lea     edx, [rdi-48h]
0x14000efb5  mov     r9d, edi
0x14000efb8  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14000efbf  call    WPP_SF_d
0x14000efc4  add     rbx, 20h ; ' '
0x14000efc8  cmp     qword ptr [rbx+18h], 7
0x14000efcd  jbe     short loc_14000EFD2
0x14000efcf  mov     rbx, [rbx]
0x14000efd2  mov     [rsp+90h+Src], rbx; Src
0x14000efd7  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000efdb  mov     [rsp+90h+var_60], 23h ; '#'; unsigned int
0x14000efe3  xor     r9d, r9d; unsigned int
0x14000efe6  xor     r8d, r8d; unsigned int
0x14000efe9  mov     [rsp+90h+var_68], 6Fh ; 'o'; int
0x14000eff1  mov     edx, edi; unsigned int
0x14000eff3  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000eff8  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000efff  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000f003  call    _CxxThrowException_0
0x14000f009  mov     rax, [rbp+4Fh+arg_18]
0x14000f00d  jmp     loc_14000EF07
0x14000f012  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f019  lea     rax, WPP_GLOBAL_Control
0x14000f020  mov     edi, 57h ; 'W'
0x14000f025  cmp     rcx, rax
0x14000f028  jz      short loc_14000F04F
0x14000f02a  test    dword ptr [rcx+1Ch], 400000h
0x14000f031  jz      short loc_14000F04F
0x14000f033  cmp     byte ptr [rcx+19h], 2
0x14000f037  jb      short loc_14000F04F
0x14000f039  mov     rcx, [rcx+10h]
0x14000f03d  lea     edx, [rdi-49h]
0x14000f040  mov     r9d, edi
0x14000f043  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14000f04a  call    WPP_SF_d
0x14000f04f  add     rbx, 20h ; ' '
0x14000f053  cmp     qword ptr [rbx+18h], 7
0x14000f058  jbe     short loc_14000F05D
0x14000f05a  mov     rbx, [rbx]
0x14000f05d  mov     [rsp+90h+Src], rbx; Src
0x14000f062  lea     rcx, [rbp+4Fh+pExceptionObject]; this
0x14000f066  mov     [rsp+90h+var_60], 9; unsigned int
0x14000f06e  xor     r9d, r9d; unsigned int
0x14000f071  xor     r8d, r8d; unsigned int
0x14000f074  mov     [rsp+90h+var_68], 67h ; 'g'; int
0x14000f07c  mov     edx, edi; unsigned int
0x14000f07e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000f083  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000f08a  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14000f08e  call    _CxxThrowException_0
```
