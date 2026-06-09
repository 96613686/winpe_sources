# std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx>>::~vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx>>(void)

- ea: `0x18004f8a4`
- end: `0x18004f96d`
- name: `??1?$vector@UCompiledLeafRegEx@?$Transformer@UOrderFromChaosConfig@LogTraitsPantherPitr@Diagnostics@@@OrderFromChaos@Diagnostics@@V?$allocator@UCompiledLeafRegEx@?$Transformer@UOrderFromChaosConfig@LogTraitsPantherPitr@Diagnostics@@@OrderFromChaos@Diagnostics@@@std@@@std@@QEAA@XZ`
- size: `201`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180048100`
- `0x180048164`
- `0x180048210`
- `0x180048280`
- `0x1800482f0`
- `0x180048410`
- `0x180048480`
- `0x1800484f0`
- `0x180051b9c`
- `0x180058be0`
- `0x18009b46b`
- `0x18009b62a`

## callees

- `0x180018eec`
- `0x180020a30`
- `0x18004f8a4`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004f966`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004f966`

## pseudocode

```c
void __fastcall std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx>>::~vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraitsPantherPitr::OrderFromChaosConfig>::CompiledLeafRegEx>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  unsigned __int64 v5; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[1];
    while ( v1 != v3 )
    {
      std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>((__int64 *)(v1 + 32));
      std::wstring::~wstring(v1);
      v1 += 72;
    }
    v4 = (_QWORD *)*a1;
    v5 = 8 * ((a1[2] - *a1) >> 3);
    if ( v5 >= 0x1000 )
    {
      v5 += 39LL;
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4, v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18004f8a4  mov     [rsp+arg_8], rbx
0x18004f8a9  mov     [rsp+arg_10], rsi
0x18004f8ae  push    rdi
0x18004f8af  sub     rsp, 30h
0x18004f8b3  mov     rbx, [rcx]
0x18004f8b6  mov     rdi, rcx
0x18004f8b9  test    rbx, rbx
0x18004f8bc  jz      loc_18004F943
0x18004f8c2  mov     rsi, [rcx+8]
0x18004f8c6  jmp     short loc_18004F8DD
0x18004f8c8  lea     rcx, [rbx+20h]; void *
0x18004f8cc  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x18004f8d1  mov     rcx, rbx
0x18004f8d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f8d9  add     rbx, 48h ; 'H'
0x18004f8dd  cmp     rbx, rsi
0x18004f8e0  jnz     short loc_18004F8C8
0x18004f8e2  mov     rcx, [rdi]
0x18004f8e5  mov     rdx, 8E38E38E38E38E39h
0x18004f8ef  mov     rax, [rdi+10h]
0x18004f8f3  sub     rax, rcx
0x18004f8f6  sar     rax, 3
0x18004f8fa  imul    rax, rdx
0x18004f8fe  lea     rdx, [rax+rax*8]
0x18004f902  shl     rdx, 3
0x18004f906  cmp     rdx, 1000h
0x18004f90d  jb      short loc_18004F927
0x18004f90f  mov     rax, [rcx-8]
0x18004f913  add     rdx, 27h ; '''; unsigned __int64
0x18004f917  sub     rcx, rax
0x18004f91a  sub     rcx, 8
0x18004f91e  cmp     rcx, 1Fh
0x18004f922  ja      short loc_18004F953
0x18004f924  mov     rcx, rax; void *
0x18004f927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004f92c  mov     qword ptr [rdi], 0
0x18004f933  mov     qword ptr [rdi+8], 0
0x18004f93b  mov     qword ptr [rdi+10h], 0
0x18004f943  mov     rbx, [rsp+38h+arg_8]
0x18004f948  mov     rsi, [rsp+38h+arg_10]
0x18004f94d  add     rsp, 30h
0x18004f951  pop     rdi
0x18004f952  retn
0x18004f953  xor     r9d, r9d; LineNo
0x18004f956  mov     [rsp+38h+Reserved], 0; Reserved
0x18004f95f  xor     r8d, r8d; FileName
0x18004f962  xor     edx, edx; FunctionName
0x18004f964  xor     ecx, ecx; Expression
0x18004f966  call    cs:__imp__invoke_watson
```
