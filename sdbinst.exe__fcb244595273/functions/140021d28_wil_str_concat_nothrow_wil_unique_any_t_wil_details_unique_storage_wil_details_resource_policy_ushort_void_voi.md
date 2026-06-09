# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [14],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[14],ushort const * const &)

- ea: `0x140021d28`
- end: `0x140021dac`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0O@GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0O@$$CBGAEBQEBG@Z`
- size: `132`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002285c`
- `0x140022e1c`

## callees

- `0x140021934`
- `0x140021d28`

## string_xrefs

- `0x140021d71`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [14],unsigned short const *>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // r9
  __int64 v4; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v10[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-18h] BYREF

  v3 = *a3;
  v4 = -1;
  if ( *a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v3 + 2 * v6) );
  }
  else
  {
    v6 = 0;
  }
  v7 = *a1;
  if ( v7 )
  {
    do
      ++v4;
    while ( *(_WORD *)(v7 + 2 * v4) );
  }
  else
  {
    v4 = 0;
  }
  v9[1] = v6;
  v9[0] = v3;
  v10[0] = L"StagedDelete_";
  v11[0] = v7;
  v10[1] = 13;
  v11[1] = v4;
  return wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
           a1,
           v11,
           v10,
           v9);
}

```

## disassembly

```asm
0x140021d28  sub     rsp, 58h
0x140021d2c  mov     r9, [r8]
0x140021d2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021d33  xor     r8d, r8d
0x140021d36  mov     r10, rcx
0x140021d39  test    r9, r9
0x140021d3c  jz      short loc_140021D4D
0x140021d3e  mov     rdx, rax
0x140021d41  inc     rdx
0x140021d44  cmp     [r9+rdx*2], r8w
0x140021d49  jnz     short loc_140021D41
0x140021d4b  jmp     short loc_140021D50
0x140021d4d  mov     rdx, r8
0x140021d50  mov     rcx, [rcx]
0x140021d53  test    rcx, rcx
0x140021d56  jz      short loc_140021D64
0x140021d58  inc     rax
0x140021d5b  cmp     [rcx+rax*2], r8w
0x140021d60  jnz     short loc_140021D58
0x140021d62  jmp     short loc_140021D67
0x140021d64  mov     rax, r8
0x140021d67  mov     [rsp+58h+var_30], rdx
0x140021d6c  lea     r8, [rsp+58h+var_28]
0x140021d71  lea     rdx, aStageddelete; "StagedDelete_"
0x140021d78  mov     [rsp+58h+var_38], r9
0x140021d7d  mov     [rsp+58h+var_28], rdx
0x140021d82  lea     r9, [rsp+58h+var_38]
0x140021d87  mov     [rsp+58h+var_18], rcx
0x140021d8c  lea     rdx, [rsp+58h+var_18]
0x140021d91  mov     rcx, r10
0x140021d94  mov     [rsp+58h+var_20], 0Dh
0x140021d9d  mov     [rsp+58h+var_10], rax
0x140021da2  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x140021da7  add     rsp, 58h
0x140021dab  retn
```
