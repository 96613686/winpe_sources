# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort const *,ushort [2],ushort [26]>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const * const &,ushort const (&)[2],ushort const (&)[26])

- ea: `0x14002840c`
- end: `0x1400284be`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG$$BY01G$$BY0BK@G@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBQEBGAEAY01$$CBGAEAY0BK@$$CBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140029710`

## callees

- `0x14002198c`
- `0x14002840c`

## string_xrefs

- `0x14002841d`: `temp.????????????????.sdb`

## pseudocode

```c
__int64 __fastcall wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short const *,unsigned short [2],unsigned short [26]>(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int128 v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+40h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-20h] BYREF
  __int128 v12; // [rsp+60h] [rbp-10h] BYREF

  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( aTempSdb[v3] );
  v5 = *a2;
  if ( *a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
  }
  else
  {
    v6 = 0;
  }
  v7 = *a1;
  if ( *a1 )
  {
    do
      ++v2;
    while ( *(_WORD *)(v7 + 2 * v2) );
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)&v9 + 1) = v3;
  *((_QWORD *)&v12 + 1) = v2;
  *(_QWORD *)&v10 = L"\\";
  *(_QWORD *)&v11 = v5;
  *((_QWORD *)&v11 + 1) = v6;
  *(_QWORD *)&v12 = v7;
  *(_QWORD *)&v9 = L"temp.????????????????.sdb";
  *((_QWORD *)&v10 + 1) = 1;
  return wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
           (__int64)a1,
           &v12,
           &v11,
           &v10,
           &v9);
}

```

## disassembly

```asm
0x14002840c  mov     [rsp-8+arg_0], rbx
0x140028411  push    rbp
0x140028412  mov     rbp, rsp
0x140028415  sub     rsp, 70h
0x140028419  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002841d  lea     rbx, aTempSdb; "temp.????????????????.sdb"
0x140028424  mov     r8, rax
0x140028427  xor     r11d, r11d
0x14002842a  mov     r10, rcx
0x14002842d  inc     r8
0x140028430  cmp     [rbx+r8*2], r11w
0x140028435  jnz     short loc_14002842D
0x140028437  mov     r9, [rdx]
0x14002843a  test    r9, r9
0x14002843d  jz      short loc_14002844E
0x14002843f  mov     rcx, rax
0x140028442  inc     rcx
0x140028445  cmp     [r9+rcx*2], r11w
0x14002844a  jnz     short loc_140028442
0x14002844c  jmp     short loc_140028451
0x14002844e  mov     rcx, r11
0x140028451  mov     rdx, [r10]
0x140028454  test    rdx, rdx
0x140028457  jz      short loc_140028465
0x140028459  inc     rax
0x14002845c  cmp     [rdx+rax*2], r11w
0x140028461  jnz     short loc_140028459
0x140028463  jmp     short loc_140028468
0x140028465  mov     rax, r11
0x140028468  mov     [rbp+var_38], r8
0x14002846c  lea     r8, asc_1400326D0; "\\"
0x140028473  mov     [rbp+var_8], rax
0x140028477  lea     rax, [rbp+var_40]
0x14002847b  mov     [rbp+var_30], r8
0x14002847f  lea     r8, [rbp+var_20]
0x140028483  mov     [rbp+var_20], r9
0x140028487  lea     r9, [rbp+var_30]
0x14002848b  mov     [rbp+var_18], rcx
0x14002848f  mov     rcx, r10
0x140028492  mov     [rbp+var_10], rdx
0x140028496  lea     rdx, [rbp+var_10]
0x14002849a  mov     [rbp+var_40], rbx
0x14002849e  mov     [rbp+var_28], 1
0x1400284a6  mov     [rsp+70h+var_50], rax
0x1400284ab  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@111@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1400284b0  mov     rbx, [rsp+70h+arg_0]
0x1400284b8  add     rsp, 70h
0x1400284bc  pop     rbp
0x1400284bd  retn
```
