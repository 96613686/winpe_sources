# std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern>>::~vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern>>(void)

- ea: `0x18004f7cc`
- end: `0x18004f89e`
- name: `??1?$vector@UCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WindowsUpdate@Diagnostics@@@OrderFromChaos@Diagnostics@@V?$allocator@UCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WindowsUpdate@Diagnostics@@@OrderFromChaos@Diagnostics@@@std@@@std@@QEAA@XZ`
- size: `210`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

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
- `0x18009b481`
- `0x18009b640`

## callees

- `0x1800185a8`
- `0x180018eec`
- `0x180020a30`
- `0x18004f7cc`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004f897`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18004f897`

## pseudocode

```c
void __fastcall std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern>>::~vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::CompiledAttributePattern>>(
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
      std::vector<std::filesystem::path>::~vector<std::filesystem::path>(v1 + 72);
      std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>((__int64 *)(v1 + 32));
      std::wstring::~wstring(v1);
      v1 += 96;
    }
    v4 = (_QWORD *)*a1;
    v5 = 32 * ((a1[2] - *a1) >> 5);
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
0x18004f7cc  mov     [rsp+arg_8], rbx
0x18004f7d1  mov     [rsp+arg_10], rsi
0x18004f7d6  push    rdi
0x18004f7d7  sub     rsp, 30h
0x18004f7db  mov     rbx, [rcx]
0x18004f7de  mov     rdi, rcx
0x18004f7e1  test    rbx, rbx
0x18004f7e4  jz      loc_18004F874
0x18004f7ea  mov     rsi, [rcx+8]
0x18004f7ee  jmp     short loc_18004F80E
0x18004f7f0  lea     rcx, [rbx+48h]
0x18004f7f4  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x18004f7f9  lea     rcx, [rbx+20h]; void *
0x18004f7fd  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x18004f802  mov     rcx, rbx
0x18004f805  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f80a  add     rbx, 60h ; '`'
0x18004f80e  cmp     rbx, rsi
0x18004f811  jnz     short loc_18004F7F0
0x18004f813  mov     rcx, [rdi]
0x18004f816  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18004f820  mov     rax, [rdi+10h]
0x18004f824  sub     rax, rcx
0x18004f827  sar     rax, 5
0x18004f82b  imul    rax, rdx
0x18004f82f  lea     rdx, [rax+rax*2]
0x18004f833  shl     rdx, 5
0x18004f837  cmp     rdx, 1000h
0x18004f83e  jb      short loc_18004F858
0x18004f840  mov     rax, [rcx-8]
0x18004f844  add     rdx, 27h ; '''; unsigned __int64
0x18004f848  sub     rcx, rax
0x18004f84b  sub     rcx, 8
0x18004f84f  cmp     rcx, 1Fh
0x18004f853  ja      short loc_18004F884
0x18004f855  mov     rcx, rax; void *
0x18004f858  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004f85d  mov     qword ptr [rdi], 0
0x18004f864  mov     qword ptr [rdi+8], 0
0x18004f86c  mov     qword ptr [rdi+10h], 0
0x18004f874  mov     rbx, [rsp+38h+arg_8]
0x18004f879  mov     rsi, [rsp+38h+arg_10]
0x18004f87e  add     rsp, 30h
0x18004f882  pop     rdi
0x18004f883  retn
0x18004f884  xor     r9d, r9d; LineNo
0x18004f887  mov     [rsp+38h+Reserved], 0; Reserved
0x18004f890  xor     r8d, r8d; FileName
0x18004f893  xor     edx, edx; FunctionName
0x18004f895  xor     ecx, ecx; Expression
0x18004f897  call    cs:__imp__invoke_watson
```
