# ParseXmlBooleanString

- ea: `0x14002b2a8`
- end: `0x14002b3af`
- name: `ParseXmlBooleanString`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400178bc`
- `0x1400182c4`

## callees

- `0x140008b40`
- `0x140022cec`
- `0x140024a90`
- `0x14002b2a8`
- `0x14002f6c8`
- `0x140031810`

## pseudocode

```c
char __fastcall ParseXmlBooleanString(_WORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax
  const char *v5; // r8
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF
  _WORD *v8; // [rsp+60h] [rbp+8h] BYREF

  v8 = a1;
  if ( a1 && *a1 )
  {
    if ( (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(
                            a1,
                            &v8,
                            L"true")
      || (unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(
                            v2,
                            &v8,
                            L"1") )
    {
      return 1;
    }
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
    if ( (v4 != 5
       || (unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                          (__int64)a1,
                          (__int64)L"false",
                          5))
      && !(unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(
                             v3,
                             &v8,
                             L"0") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v5, 87);
      throw (EvtException *)pExceptionObject;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002b2a8  mov     [rsp+arg_8], rbx
0x14002b2ad  mov     [rsp+arg_0], rcx
0x14002b2b2  push    rdi
0x14002b2b3  sub     rsp, 50h
0x14002b2b7  xor     edi, edi
0x14002b2b9  mov     rbx, rcx
0x14002b2bc  test    rcx, rcx
0x14002b2bf  jz      loc_14002B3A2
0x14002b2c5  cmp     [rcx], di
0x14002b2c8  jz      loc_14002B3A2
0x14002b2ce  lea     r8, aTrue; "true"
0x14002b2d5  lea     rdx, [rsp+58h+arg_0]
0x14002b2da  call    ??$?RPEB_W$$BY04_W_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBQEB_WAEAY04$$CB_W@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(wchar_t const * const &,wchar_t const (&)[5])
0x14002b2df  test    al, al
0x14002b2e1  jnz     loc_14002B39E
0x14002b2e7  lea     r8, a1; "1"
0x14002b2ee  lea     rdx, [rsp+58h+arg_0]
0x14002b2f3  call    ??$?RPEB_W$$BY04_W_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBQEB_WAEAY04$$CB_W@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(wchar_t const * const &,wchar_t const (&)[5])
0x14002b2f8  test    al, al
0x14002b2fa  jnz     loc_14002B39E
0x14002b300  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b304  inc     rax
0x14002b307  cmp     [rbx+rax*2], di
0x14002b30b  jnz     short loc_14002B304
0x14002b30d  mov     r8d, 5
0x14002b313  cmp     rax, r8
0x14002b316  jnz     short loc_14002B32B
0x14002b318  lea     rdx, aFalse; "false"
0x14002b31f  mov     rcx, rbx
0x14002b322  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14002b327  test    eax, eax
0x14002b329  jz      short loc_14002B3A2
0x14002b32b  lea     r8, a0; "0"
0x14002b332  lea     rdx, [rsp+58h+arg_0]
0x14002b337  call    ??$?RPEB_W$$BY04_W_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBQEB_WAEAY04$$CB_W@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(wchar_t const * const &,wchar_t const (&)[5])
0x14002b33c  test    al, al
0x14002b33e  jnz     short loc_14002B3A2
0x14002b340  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b347  lea     rax, WPP_GLOBAL_Control
0x14002b34e  mov     ebx, 0Dh
0x14002b353  cmp     rcx, rax
0x14002b356  jz      short loc_14002B37A
0x14002b358  test    byte ptr [rcx+1Ch], 4
0x14002b35c  jz      short loc_14002B37A
0x14002b35e  cmp     byte ptr [rcx+19h], 2
0x14002b362  jb      short loc_14002B37A
0x14002b364  mov     rcx, [rcx+10h]
0x14002b368  lea     edx, [rbx-1]
0x14002b36b  mov     r9d, ebx
0x14002b36e  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002b375  call    WPP_SF_d
0x14002b37a  mov     r9d, 57h ; 'W'; int
0x14002b380  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14002b385  mov     edx, ebx; unsigned int
0x14002b387  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14002b38c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002b393  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14002b398  call    _CxxThrowException_0
0x14002b39e  mov     al, 1
0x14002b3a0  jmp     short loc_14002B3A4
0x14002b3a2  xor     al, al
0x14002b3a4  mov     rbx, [rsp+58h+arg_8]
0x14002b3a9  add     rsp, 50h
0x14002b3ad  pop     rdi
0x14002b3ae  retn
```
