# RegistryPaths::GetAutoLoggerSecurityRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14002f018`
- end: `0x14002f0cf`
- name: `?GetAutoLoggerSecurityRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014988`
- `0x1400151ec`

## callees

- `0x140006cd0`
- `0x14000d6e8`
- `0x140022cec`
- `0x14002f018`

## string_xrefs

- `0x14002f056`: `\ControlSet001\Control\WMI\Security`

## pseudocode

```c
__int64 __fastcall RegistryPaths::GetAutoLoggerSecurityRegPath(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _WORD *v7; // rcx

  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          a3,
                          qword_1400421F0,
                          (qword_1400421F8 - qword_1400421F0) >> 1)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          a3,
                          L"\\ControlSet001\\Control\\WMI\\Security",
                          35) )
  {
    v7 = *(_WORD **)a4;
    *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
    *v7 = 0;
    *a2 = qword_140042240;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_102b51fcdce430aa865b164defc92936_Traceguids, 14);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x14002f018  mov     [rsp+arg_0], rbx
0x14002f01d  mov     [rsp+arg_8], rsi
0x14002f022  push    rdi
0x14002f023  sub     rsp, 20h
0x14002f027  mov     rdi, r8
0x14002f02a  mov     rsi, rdx
0x14002f02d  mov     rdx, cs:qword_1400421F0
0x14002f034  mov     rcx, rdi
0x14002f037  mov     r8, cs:qword_1400421F8
0x14002f03e  mov     rbx, r9
0x14002f041  sub     r8, rdx
0x14002f044  sar     r8, 1
0x14002f047  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14002f04c  test    al, al
0x14002f04e  jz      short loc_14002F083
0x14002f050  mov     r8d, 23h ; '#'
0x14002f056  lea     rdx, aControlset001C_0; "\\ControlSet001\\Control\\WMI\\Security"
0x14002f05d  mov     rcx, rdi
0x14002f060  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14002f065  test    al, al
0x14002f067  jz      short loc_14002F083
0x14002f069  mov     rcx, [rbx]
0x14002f06c  xor     eax, eax
0x14002f06e  mov     [rbx+8], rcx
0x14002f072  mov     [rcx], ax
0x14002f075  mov     rax, cs:qword_140042240
0x14002f07c  mov     [rsi], rax
0x14002f07f  xor     eax, eax
0x14002f081  jmp     short loc_14002F0BF
0x14002f083  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f08a  lea     rax, WPP_GLOBAL_Control
0x14002f091  mov     ebx, 0Eh
0x14002f096  cmp     rcx, rax
0x14002f099  jz      short loc_14002F0BD
0x14002f09b  test    byte ptr [rcx+1Ch], 4
0x14002f09f  jz      short loc_14002F0BD
0x14002f0a1  cmp     byte ptr [rcx+19h], 2
0x14002f0a5  jb      short loc_14002F0BD
0x14002f0a7  mov     rcx, [rcx+10h]
0x14002f0ab  lea     edx, [rbx-1]
0x14002f0ae  mov     r9d, ebx
0x14002f0b1  lea     r8, WPP_102b51fcdce430aa865b164defc92936_Traceguids
0x14002f0b8  call    WPP_SF_d
0x14002f0bd  mov     eax, ebx
0x14002f0bf  mov     rbx, [rsp+28h+arg_0]
0x14002f0c4  mov     rsi, [rsp+28h+arg_8]
0x14002f0c9  add     rsp, 20h
0x14002f0cd  pop     rdi
0x14002f0ce  retn
```
