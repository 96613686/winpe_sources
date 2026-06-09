# RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000d62c`
- end: `0x14000d6e2`
- name: `?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z`
- size: `182`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013658`
- `0x14001663c`
- `0x14001aa58`
- `0x14001d828`
- `0x14001e0c0`
- `0x14002a55c`
- `0x14002a814`
- `0x14002bd08`
- `0x14002e0cc`

## callees

- `0x140006cd0`
- `0x14000d62c`
- `0x14000d6e8`
- `0x140022cec`

## pseudocode

```c
__int64 __fastcall RegistryPaths::GetWinevtRegPath(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _WORD *v7; // rcx

  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                          a3,
                          qword_1400421D0,
                          (qword_1400421D8 - qword_1400421D0) >> 1)
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          a3,
                          L"\\Microsoft\\Windows\\CurrentVersion\\WINEVT",
                          40) )
  {
    v7 = *(_WORD **)a4;
    *(_QWORD *)(a4 + 8) = *(_QWORD *)a4;
    *v7 = 0;
    *a2 = hKey;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_102b51fcdce430aa865b164defc92936_Traceguids, 14);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x14000d62c  mov     [rsp+arg_0], rbx
0x14000d631  mov     [rsp+arg_8], rsi
0x14000d636  push    rdi
0x14000d637  sub     rsp, 20h
0x14000d63b  mov     rdi, r8
0x14000d63e  mov     rsi, rdx
0x14000d641  mov     rdx, cs:qword_1400421D0
0x14000d648  mov     rcx, rdi
0x14000d64b  mov     r8, cs:qword_1400421D8
0x14000d652  mov     rbx, r9
0x14000d655  sub     r8, rdx
0x14000d658  sar     r8, 1
0x14000d65b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000d660  test    al, al
0x14000d662  jz      short loc_14000D697
0x14000d664  mov     r8d, 28h ; '('
0x14000d66a  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\CurrentVersion\\W"...
0x14000d671  mov     rcx, rdi
0x14000d674  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14000d679  test    al, al
0x14000d67b  jz      short loc_14000D697
0x14000d67d  mov     rcx, [rbx]
0x14000d680  xor     eax, eax
0x14000d682  mov     [rbx+8], rcx
0x14000d686  mov     [rcx], ax
0x14000d689  mov     rax, cs:hKey
0x14000d690  mov     [rsi], rax
0x14000d693  xor     eax, eax
0x14000d695  jmp     short loc_14000D6D2
0x14000d697  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d69e  lea     rax, WPP_GLOBAL_Control
0x14000d6a5  mov     ebx, 0Eh
0x14000d6aa  cmp     rcx, rax
0x14000d6ad  jz      short loc_14000D6D0
0x14000d6af  test    byte ptr [rcx+1Ch], 4
0x14000d6b3  jz      short loc_14000D6D0
0x14000d6b5  cmp     byte ptr [rcx+19h], 2
0x14000d6b9  jb      short loc_14000D6D0
0x14000d6bb  mov     rcx, [rcx+10h]
0x14000d6bf  lea     r8, WPP_102b51fcdce430aa865b164defc92936_Traceguids
0x14000d6c6  mov     edx, ebx
0x14000d6c8  mov     r9d, ebx
0x14000d6cb  call    WPP_SF_d
0x14000d6d0  mov     eax, ebx
0x14000d6d2  mov     rbx, [rsp+28h+arg_0]
0x14000d6d7  mov     rsi, [rsp+28h+arg_8]
0x14000d6dc  add     rsp, 20h
0x14000d6e0  pop     rdi
0x14000d6e1  retn
```
