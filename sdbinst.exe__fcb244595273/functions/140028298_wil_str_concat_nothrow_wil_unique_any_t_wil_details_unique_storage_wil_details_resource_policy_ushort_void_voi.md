# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)

- ea: `0x140028298`
- end: `0x14002834a`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBV10@@Z`
- size: `178`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140028714`
- `0x14002955c`

## callees

- `0x14002198c`
- `0x140028298`

## string_xrefs

- `0x1400282c9`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 __fastcall wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v4; // r10
  __int64 v5; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int128 v11; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 v13; // [rsp+50h] [rbp-20h] BYREF
  __int128 v14; // [rsp+60h] [rbp-10h] BYREF

  v4 = *a4;
  v5 = -1;
  if ( *a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v4 + 2 * v7) );
  }
  else
  {
    v7 = 0;
  }
  v8 = -1;
  do
    ++v8;
  while ( aSoftwareMicros_12[v8] );
  v9 = *a1;
  if ( *a1 )
  {
    do
      ++v5;
    while ( *(_WORD *)(v9 + 2 * v5) );
  }
  else
  {
    v5 = 0;
  }
  *((_QWORD *)&v11 + 1) = v7;
  *((_QWORD *)&v14 + 1) = v5;
  *(_QWORD *)&v12 = L"\\";
  *((_QWORD *)&v13 + 1) = v8;
  *(_QWORD *)&v14 = v9;
  *(_QWORD *)&v11 = v4;
  *((_QWORD *)&v12 + 1) = 1;
  *(_QWORD *)&v13 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates";
  return wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
           (__int64)a1,
           &v14,
           &v13,
           &v12,
           &v11);
}

```

## disassembly

```asm
0x140028298  mov     [rsp-8+arg_0], rbx
0x14002829d  push    rbp
0x14002829e  mov     rbp, rsp
0x1400282a1  sub     rsp, 70h
0x1400282a5  mov     r10, [r9]
0x1400282a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400282ac  xor     r9d, r9d
0x1400282af  mov     r11, rcx
0x1400282b2  test    r10, r10
0x1400282b5  jz      short loc_1400282C6
0x1400282b7  mov     rdx, rax
0x1400282ba  inc     rdx
0x1400282bd  cmp     [r10+rdx*2], r9w
0x1400282c2  jnz     short loc_1400282BA
0x1400282c4  jmp     short loc_1400282C9
0x1400282c6  mov     rdx, r9
0x1400282c9  lea     rbx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400282d0  mov     rcx, rax
0x1400282d3  inc     rcx
0x1400282d6  cmp     [rbx+rcx*2], r9w
0x1400282db  jnz     short loc_1400282D3
0x1400282dd  mov     r8, [r11]
0x1400282e0  test    r8, r8
0x1400282e3  jz      short loc_1400282F1
0x1400282e5  inc     rax
0x1400282e8  cmp     [r8+rax*2], r9w
0x1400282ed  jnz     short loc_1400282E5
0x1400282ef  jmp     short loc_1400282F4
0x1400282f1  mov     rax, r9
0x1400282f4  mov     [rbp+var_38], rdx
0x1400282f8  lea     r9, [rbp+var_30]
0x1400282fc  lea     rdx, asc_1400326D0; "\\"
0x140028303  mov     [rbp+var_8], rax
0x140028307  mov     [rbp+var_30], rdx
0x14002830b  lea     rax, [rbp+var_40]
0x14002830f  mov     [rbp+var_18], rcx
0x140028313  lea     rdx, [rbp+var_10]
0x140028317  mov     [rbp+var_10], r8
0x14002831b  mov     rcx, r11
0x14002831e  lea     r8, [rbp+var_20]
0x140028322  mov     [rbp+var_40], r10
0x140028326  mov     [rbp+var_28], 1
0x14002832e  mov     [rbp+var_20], rbx
0x140028332  mov     [rsp+70h+var_50], rax
0x140028337  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@111@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x14002833c  mov     rbx, [rsp+70h+arg_0]
0x140028344  add     rsp, 70h
0x140028348  pop     rbp
0x140028349  retn
```
