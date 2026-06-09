# RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14001915c`
- end: `0x140019242`
- name: `?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x140006de0`
- `0x140019094`
- `0x14002cc9c`

## callees

- `0x140006cd0`
- `0x14000d6e8`
- `0x14001915c`
- `0x140022cec`

## string_xrefs

- `0x1400191da`: `SYSTEM\CurrentControlSet\Services\Eventlog`
- `0x14001919b`: `\ControlSet001\services\eventlog`

## pseudocode

```c
__int64 __fastcall RegistryPaths::GetEventlogServiceRegPath(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  if ( byte_140042230 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             a3,
                             qword_1400421F0,
                             (qword_1400421F8 - qword_1400421F0) >> 1)
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             a3,
                             L"\\ControlSet001\\services\\eventlog",
                             32) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 14;
      }
      v6 = 11;
LABEL_13:
      WPP_SF_d(v5[2], v6, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids, 14);
      return 14;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                a3,
                                L"SYSTEM\\CurrentControlSet\\Services\\Eventlog",
                                42) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 14;
    }
    v6 = 12;
    goto LABEL_13;
  }
  *a2 = qword_140042240;
  return 0;
}

```

## disassembly

```asm
0x14001915c  mov     [rsp+arg_0], rbx
0x140019161  push    rdi
0x140019162  sub     rsp, 20h
0x140019166  cmp     cs:byte_140042230, 0
0x14001916d  mov     rbx, r8
0x140019170  mov     rcx, rbx
0x140019173  mov     rdi, rdx
0x140019176  jz      short loc_1400191D4
0x140019178  mov     rdx, cs:qword_1400421F0
0x14001917f  mov     r8, cs:qword_1400421F8
0x140019186  sub     r8, rdx
0x140019189  sar     r8, 1
0x14001918c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140019191  test    al, al
0x140019193  jz      short loc_1400191AE
0x140019195  mov     r8d, 20h ; ' '
0x14001919b  lea     rdx, aControlset001S; "\\ControlSet001\\services\\eventlog"
0x1400191a2  mov     rcx, rbx
0x1400191a5  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400191aa  test    al, al
0x1400191ac  jnz     short loc_14001922B
0x1400191ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191b5  lea     rax, WPP_GLOBAL_Control
0x1400191bc  cmp     rcx, rax
0x1400191bf  jz      short loc_140019224
0x1400191c1  test    byte ptr [rcx+1Ch], 4
0x1400191c5  jz      short loc_140019224
0x1400191c7  cmp     byte ptr [rcx+19h], 2
0x1400191cb  jb      short loc_140019224
0x1400191cd  mov     edx, 0Bh
0x1400191d2  jmp     short loc_14001920E
0x1400191d4  mov     r8d, 2Ah ; '*'
0x1400191da  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1400191e1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400191e6  test    al, al
0x1400191e8  jnz     short loc_14001922B
0x1400191ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191f1  lea     rax, WPP_GLOBAL_Control
0x1400191f8  cmp     rcx, rax
0x1400191fb  jz      short loc_140019224
0x1400191fd  test    byte ptr [rcx+1Ch], 4
0x140019201  jz      short loc_140019224
0x140019203  cmp     byte ptr [rcx+19h], 2
0x140019207  jb      short loc_140019224
0x140019209  mov     edx, 0Ch
0x14001920e  mov     rcx, [rcx+10h]
0x140019212  lea     r8, WPP_ae15e7b640843c37a4c21db51df2f09e_Traceguids
0x140019219  mov     r9d, 0Eh
0x14001921f  call    WPP_SF_d
0x140019224  mov     eax, 0Eh
0x140019229  jmp     short loc_140019237
0x14001922b  mov     rax, cs:qword_140042240
0x140019232  mov     [rdi], rax
0x140019235  xor     eax, eax
0x140019237  mov     rbx, [rsp+28h+arg_0]
0x14001923c  add     rsp, 20h
0x140019240  pop     rdi
0x140019241  retn
```
