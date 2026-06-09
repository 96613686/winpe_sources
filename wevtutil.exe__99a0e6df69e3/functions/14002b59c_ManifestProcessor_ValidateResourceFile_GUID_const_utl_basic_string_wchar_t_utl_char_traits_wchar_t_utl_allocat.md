# ManifestProcessor::ValidateResourceFile(_GUID const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x14002b59c`
- end: `0x14002b6aa`
- name: `?ValidateResourceFile@ManifestProcessor@@AEAAXAEBU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001663c`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x14000cc80`
- `0x14002b59c`
- `0x14002ba08`
- `0x14002f9f4`
- `0x140031008`
- `0x1400312f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ManifestProcessor::ValidateResourceFile(__int64 a1, const struct _GUID *a2, _QWORD *a3)
{
  LPCWSTR *v6; // r8
  int v7; // eax
  const wchar_t *v8; // r8
  const wchar_t *v9; // r9
  unsigned int v10; // eax
  __int64 v11; // rcx
  bool v12; // [rsp+28h] [rbp-41h]
  wchar_t *v13[4]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v14[3]; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+68h] [rbp-1h]
  __int128 v16; // [rsp+70h] [rbp+7h]
  __int128 v17; // [rsp+80h] [rbp+17h]
  __int64 v18; // [rsp+90h] [rbp+27h]

  v14[0] = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13);
  v7 = ExpandEnvStringNoThrow(*v6);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
        *a3,
        v7);
    }
    eventlog::ai::WarningMessage((eventlog::ai *)0x18, *a3);
  }
  else
  {
    v10 = ResourceHolder::Open((ResourceHolder *)v14, v13[0], v8, v9, a2, v12);
    if ( v10 )
    {
      switch ( v10 )
      {
        case 0xDu:
          v11 = 84;
          break;
        case 2u:
          v11 = 85;
          break;
        case 0x715u:
          v11 = 86;
          break;
        default:
          eventlog::ai::WarningMessage((eventlog::ai *)0x18, (unsigned int)v13[0]);
          goto LABEL_16;
      }
      eventlog::ai::WarningMessage((eventlog::ai *)v11, *(_QWORD *)(a1 + 48), v13[0]);
    }
  }
LABEL_16:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13);
  ResourceHolder::Close((ResourceHolder *)v14);
}

```

## disassembly

```asm
0x14002b59c  push    rbp
0x14002b59e  push    rbx
0x14002b59f  push    rsi
0x14002b5a0  push    rdi
0x14002b5a1  lea     rbp, [rsp-3Fh]
0x14002b5a6  sub     rsp, 0A8h
0x14002b5ad  mov     rdi, r8
0x14002b5b0  mov     rsi, rdx
0x14002b5b3  mov     rbx, rcx
0x14002b5b6  mov     [rbp+57h+var_70], 0
0x14002b5be  mov     [rbp+57h+var_58], 0
0x14002b5c5  xorps   xmm0, xmm0
0x14002b5c8  movdqa  [rbp+57h+var_50], xmm0
0x14002b5cd  xorps   xmm1, xmm1
0x14002b5d0  movdqa  [rbp+57h+var_40], xmm1
0x14002b5d5  mov     [rbp+57h+var_30], 0
0x14002b5dd  lea     rcx, [rbp+57h+var_90]
0x14002b5e1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002b5e6  nop
0x14002b5e7  lea     rdx, [rbp+57h+var_90]
0x14002b5eb  mov     rcx, [r8]; lpSrc
0x14002b5ee  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14002b5f3  test    eax, eax
0x14002b5f5  jz      short loc_14002B637
0x14002b5f7  lea     rdx, WPP_GLOBAL_Control
0x14002b5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b605  cmp     rcx, rdx
0x14002b608  jz      short loc_14002B632
0x14002b60a  test    byte ptr [rcx+1Ch], 4
0x14002b60e  jz      short loc_14002B632
0x14002b610  cmp     byte ptr [rcx+19h], 2
0x14002b614  jb      short loc_14002B632
0x14002b616  mov     edx, 30h ; '0'
0x14002b61b  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14002b61f  mov     r9, [rdi]
0x14002b622  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14002b629  mov     rcx, [rcx+10h]
0x14002b62d  call    WPP_SF_SD
0x14002b632  mov     rdx, [rdi]
0x14002b635  jmp     short loc_14002B680
0x14002b637  mov     [rsp+0C0h+var_A0], rsi; struct _GUID *
0x14002b63c  mov     rdx, [rbp+57h+var_90]; wchar_t *
0x14002b640  lea     rcx, [rbp+57h+var_70]; this
0x14002b644  call    ?Open@ResourceHolder@@QEAAKPEB_W00PEBU_GUID@@_N@Z; ResourceHolder::Open(wchar_t const *,wchar_t const *,wchar_t const *,_GUID const *,bool)
0x14002b649  test    eax, eax
0x14002b64b  jz      short loc_14002B68B
0x14002b64d  cmp     eax, 0Dh
0x14002b650  jnz     short loc_14002B657
0x14002b652  lea     ecx, [rax+47h]
0x14002b655  jmp     short loc_14002B66D
0x14002b657  cmp     eax, 2
0x14002b65a  jnz     short loc_14002B661
0x14002b65c  lea     ecx, [rax+53h]
0x14002b65f  jmp     short loc_14002B66D
0x14002b661  cmp     eax, 715h
0x14002b666  jnz     short loc_14002B67C
0x14002b668  mov     ecx, 56h ; 'V'; this
0x14002b66d  mov     r8, [rbp+57h+var_90]
0x14002b671  mov     rdx, [rbx+30h]; unsigned int
0x14002b675  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14002b67a  jmp     short loc_14002B68B
0x14002b67c  mov     rdx, [rbp+57h+var_90]; unsigned int
0x14002b680  mov     ecx, 18h; this
0x14002b685  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14002b68a  nop
0x14002b68b  lea     rcx, [rbp+57h+var_90]
0x14002b68f  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002b694  nop
0x14002b695  lea     rcx, [rbp+57h+var_70]; this
0x14002b699  call    ?Close@ResourceHolder@@QEAAXXZ; ResourceHolder::Close(void)
0x14002b69e  add     rsp, 0A8h
0x14002b6a5  pop     rdi
0x14002b6a6  pop     rsi
0x14002b6a7  pop     rbx
0x14002b6a8  pop     rbp
0x14002b6a9  retn
```
