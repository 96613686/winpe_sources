# ReplaceGatewayList(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,_SSTP_TENANT_GATEWAY_ENTRY *)

- ea: `0x180012648`
- end: `0x180012746`
- name: `?ReplaceGatewayList@@YAKV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAU_SSTP_TENANT_GATEWAY_ENTRY@@@Z`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x180008b90`
- `0x180012648`
- `0x180013524`
- `0x18001378c`
- `0x18001cd60`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180012712`
- `msvcrt!wcscpy_s` at `0x180012712`

## string_xrefs

- `0x1800126ad`: `ReplaceGatewayList: Failed to allocate memory for GATEWAY_CONFIG structure.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReplaceGatewayList(_QWORD *a1, __int64 a2)
{
  unsigned __int64 v4; // rax
  unsigned int v5; // esi
  unsigned __int64 v6; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rax

  v4 = *(_QWORD *)(a2 + 24);
  if ( v4
    || (v4 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3)) == 0
    || (v4 = (unsigned __int64)MIDL_user_allocate(102 * ((__int64)(a1[1] - *a1) >> 3)), (*(_QWORD *)(a2 + 24) = v4) != 0) )
  {
    v5 = 0;
    v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
    *(_DWORD *)(a2 + 16) = v6;
    if ( v4 )
    {
      v7 = 0;
      if ( (_DWORD)v6 )
      {
        do
        {
          v8 = std::vector<std::wstring>::at(a1, v7);
          if ( *(_QWORD *)(v8 + 24) >= 8u )
            v8 = *(_QWORD *)v8;
          wcscpy_s((wchar_t *)(*(_QWORD *)(a2 + 24) + 510LL * v7++), 0xFFu, (const wchar_t *)v8);
        }
        while ( v7 < *(_DWORD *)(a2 + 16) );
      }
    }
    *(_DWORD *)(a2 + 32) = 0;
  }
  else
  {
    v5 = 14;
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasSSTPSvcTraceError,
        L"ReplaceGatewayList: Failed to allocate memory for GATEWAY_CONFIG structure.");
  }
  std::vector<std::wstring>::_Tidy(a1);
  return v5;
}

```

## disassembly

```asm
0x180012648  mov     [rsp+arg_10], rbx
0x18001264d  mov     [rsp+arg_18], rbp
0x180012652  mov     [rsp+arg_0], rcx
0x180012657  push    rsi
0x180012658  push    rdi
0x180012659  push    r14
0x18001265b  sub     rsp, 20h
0x18001265f  mov     rdi, rdx
0x180012662  mov     rbx, rcx
0x180012665  mov     rax, [rdx+18h]
0x180012669  mov     rbp, 0CCCCCCCCCCCCCCCDh
0x180012673  test    rax, rax
0x180012676  jnz     short loc_1800126C9
0x180012678  mov     rax, [rcx+8]
0x18001267c  sub     rax, [rcx]
0x18001267f  sar     rax, 3
0x180012683  imul    rax, rbp
0x180012687  test    rax, rax
0x18001268a  jz      short loc_1800126C9
0x18001268c  imul    rcx, rax, 1FEh; size
0x180012693  call    MIDL_user_allocate
0x180012698  mov     [rdi+18h], rax
0x18001269c  test    rax, rax
0x18001269f  jnz     short loc_1800126C9
0x1800126a1  lea     esi, [rax+0Eh]
0x1800126a4  test    cs:byte_18002E903, 8
0x1800126ab  jz      short loc_180012728
0x1800126ad  lea     r8, aReplacegateway; "ReplaceGatewayList: Failed to allocate "...
0x1800126b4  lea     rdx, RasSSTPSvcTraceError
0x1800126bb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800126c2  call    McTemplateU0z_EventWriteTransfer
0x1800126c7  jmp     short loc_180012728
0x1800126c9  xor     esi, esi
0x1800126cb  mov     rcx, [rbx+8]
0x1800126cf  sub     rcx, [rbx]
0x1800126d2  sar     rcx, 3
0x1800126d6  imul    rcx, rbp
0x1800126da  mov     [rdi+10h], ecx
0x1800126dd  test    rax, rax
0x1800126e0  jz      short loc_180012725
0x1800126e2  xor     ebp, ebp
0x1800126e4  test    ecx, ecx
0x1800126e6  jz      short loc_180012725
0x1800126e8  mov     r14d, ebp
0x1800126eb  mov     edx, ebp
0x1800126ed  mov     rcx, rbx
0x1800126f0  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x1800126f5  cmp     qword ptr [rax+18h], 8
0x1800126fa  jb      short loc_1800126FF
0x1800126fc  mov     rax, [rax]
0x1800126ff  imul    rcx, r14, 1FEh
0x180012706  add     rcx, [rdi+18h]; Destination
0x18001270a  mov     r8, rax; Source
0x18001270d  mov     edx, 0FFh; SizeInWords
0x180012712  call    cs:__imp_wcscpy_s
0x180012719  nop     dword ptr [rax+rax+00h]
0x18001271e  inc     ebp
0x180012720  cmp     ebp, [rdi+10h]
0x180012723  jb      short loc_1800126E8
0x180012725  mov     [rdi+20h], esi
0x180012728  mov     rcx, rbx
0x18001272b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180012730  mov     eax, esi
0x180012732  mov     rbx, [rsp+38h+arg_10]
0x180012737  mov     rbp, [rsp+38h+arg_18]
0x18001273c  add     rsp, 20h
0x180012740  pop     r14
0x180012742  pop     rdi
0x180012743  pop     rsi
0x180012744  retn
```
