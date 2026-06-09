# BrainInputDefault::module2Path(void const *)

- ea: `0x18003eb80`
- end: `0x18003eca3`
- name: `?module2Path@BrainInputDefault@@UEBA?AV?$optional@Vpath@filesystem@std@@@std@@PEBX@Z`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800295e8`
- `0x180029644`
- `0x18003e1bc`
- `0x18003eb80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebe3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall BrainInputDefault::module2Path(__int64 a1, _OWORD *a2, __int64 a3)
{
  __int64 v4; // rcx
  _BYTE *v5; // rax
  char v6; // bl
  LPVOID pv; // [rsp+20h] [rbp-49h] BYREF
  int v9; // [rsp+28h] [rbp-41h]
  _QWORD v10[2]; // [rsp+30h] [rbp-39h] BYREF
  __int128 v11; // [rsp+40h] [rbp-29h] BYREF
  __m128i si128; // [rsp+50h] [rbp-19h]
  _OWORD v13[2]; // [rsp+60h] [rbp-9h] BYREF
  char v14; // [rsp+80h] [rbp+17h]
  _BYTE v15[32]; // [rsp+88h] [rbp+1Fh] BYREF
  char v16; // [rsp+A8h] [rbp+3Fh]

  pv = a2;
  v9 = 0;
  if ( a3 )
  {
    pv = 0;
    wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
      &pv,
      a2,
      a3);
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)pv + v4) );
    v10[0] = pv;
    v10[1] = v4;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v11, v10);
    if ( pv )
      CoTaskMemFree(pv);
    v13[0] = v11;
    v13[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v11) = 0;
    v14 = 1;
    v5 = v13;
    v6 = 59;
  }
  else
  {
    v16 = 0;
    v5 = v15;
    v6 = 12;
  }
  *((_BYTE *)a2 + 32) = 0;
  if ( v5[32] )
  {
    *a2 = *(_OWORD *)v5;
    a2[1] = *((_OWORD *)v5 + 1);
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 7;
    *(_WORD *)v5 = 0;
    *((_BYTE *)a2 + 32) = 1;
  }
  if ( (v6 & 4) != 0 )
  {
    v6 &= ~4u;
    if ( v16 )
      std::wstring::_Tidy_deallocate(v15);
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( v14 )
      std::wstring::_Tidy_deallocate(v13);
  }
  if ( (v6 & 1) != 0 )
    std::wstring::_Tidy_deallocate(&v11);
  return a2;
}

```

## disassembly

```asm
0x18003eb80  mov     [rsp-8+arg_0], rbx
0x18003eb85  push    rbp
0x18003eb86  push    rsi
0x18003eb87  push    rdi
0x18003eb88  lea     rbp, [rsp-47h]
0x18003eb8d  sub     rsp, 0B0h
0x18003eb94  mov     rdi, rdx
0x18003eb97  mov     [rbp+57h+pv], rdx
0x18003eb9b  xor     esi, esi
0x18003eb9d  mov     [rbp+57h+var_98], esi
0x18003eba0  test    r8, r8
0x18003eba3  jz      short loc_18003EC19
0x18003eba5  mov     [rbp+57h+pv], rsi
0x18003eba9  lea     rcx, [rbp+57h+pv]
0x18003ebad  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x18003ebb2  nop
0x18003ebb3  mov     rax, [rbp+57h+pv]
0x18003ebb7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ebbb  inc     rcx
0x18003ebbe  cmp     [rax+rcx*2], si
0x18003ebc2  jnz     short loc_18003EBBB
0x18003ebc4  mov     [rbp+57h+var_90], rax
0x18003ebc8  mov     [rbp+57h+var_88], rcx
0x18003ebcc  lea     rdx, [rbp+57h+var_90]
0x18003ebd0  lea     rcx, [rbp+57h+var_80]
0x18003ebd4  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18003ebd9  nop
0x18003ebda  mov     rcx, [rbp+57h+pv]; pv
0x18003ebde  test    rcx, rcx
0x18003ebe1  jz      short loc_18003EBE9
0x18003ebe3  call    cs:__imp_CoTaskMemFree
0x18003ebe9  movups  xmm0, [rbp+57h+var_80]
0x18003ebed  movups  [rbp+57h+var_60], xmm0
0x18003ebf1  movups  xmm1, [rbp+57h+var_70]
0x18003ebf5  movups  [rbp+57h+var_50], xmm1
0x18003ebf9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18003ec01  movdqu  [rbp+57h+var_70], xmm0
0x18003ec06  mov     word ptr [rbp+57h+var_80], si
0x18003ec0a  mov     [rbp+57h+var_40], 1
0x18003ec0e  lea     rax, [rbp+57h+var_60]
0x18003ec12  mov     ebx, 3Bh ; ';'
0x18003ec17  jmp     short loc_18003EC26
0x18003ec19  mov     [rbp+57h+var_18], sil
0x18003ec1d  lea     rax, [rbp+57h+var_38]
0x18003ec21  mov     ebx, 0Ch
0x18003ec26  mov     [rdi+20h], sil
0x18003ec2a  cmp     [rax+20h], sil
0x18003ec2e  jz      short loc_18003EC51
0x18003ec30  movups  xmm0, xmmword ptr [rax]
0x18003ec33  movups  xmmword ptr [rdi], xmm0
0x18003ec36  movups  xmm1, xmmword ptr [rax+10h]
0x18003ec3a  movups  xmmword ptr [rdi+10h], xmm1
0x18003ec3e  mov     [rax+10h], rsi
0x18003ec42  mov     qword ptr [rax+18h], 7
0x18003ec4a  mov     [rax], si
0x18003ec4d  mov     byte ptr [rdi+20h], 1
0x18003ec51  test    bl, 4
0x18003ec54  jz      short loc_18003EC68
0x18003ec56  and     ebx, 0FFFFFFFBh
0x18003ec59  cmp     [rbp+57h+var_18], sil
0x18003ec5d  jz      short loc_18003EC68
0x18003ec5f  lea     rcx, [rbp+57h+var_38]
0x18003ec63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ec68  test    bl, 2
0x18003ec6b  jz      short loc_18003EC7F
0x18003ec6d  and     ebx, 0FFFFFFFDh
0x18003ec70  cmp     [rbp+57h+var_40], sil
0x18003ec74  jz      short loc_18003EC7F
0x18003ec76  lea     rcx, [rbp+57h+var_60]
0x18003ec7a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ec7f  test    bl, 1
0x18003ec82  jz      short loc_18003EC8D
0x18003ec84  lea     rcx, [rbp+57h+var_80]
0x18003ec88  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ec8d  mov     rax, rdi
0x18003ec90  mov     rbx, [rsp+0C0h+arg_0]
0x18003ec98  add     rsp, 0B0h
0x18003ec9f  pop     rdi
0x18003eca0  pop     rsi
0x18003eca1  pop     rbp
0x18003eca2  retn
```
