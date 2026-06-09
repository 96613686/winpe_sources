# wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],ushort const *,ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],ushort const * const &,ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)

- ea: `0x1400281a0`
- end: `0x14002828f`
- name: `??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GPEBG$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBQEBG2AEBV10@@Z`
- size: `239`
- prototype: `__int64 __fastcall(int *, __int64, __int64, __int64 *, int, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002c970`

## callees

- `0x1400219f8`
- `0x1400281a0`
- `0x14002e420`

## string_xrefs

- `0x140028200`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 __fastcall wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],unsigned short const *,unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        int *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        int a5,
        __int64 *a6)
{
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r10
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  _QWORD v15[12]; // [rsp+20h] [rbp-49h] BYREF

  v7 = *a6;
  v8 = -1;
  if ( *a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v7 + 2 * v9) );
  }
  else
  {
    v9 = 0;
  }
  v10 = *a4;
  if ( *a4 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
  }
  else
  {
    v11 = 0;
  }
  v12 = -1;
  do
    ++v12;
  while ( aSoftwareMicros_12[v12] );
  v13 = *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    do
      ++v8;
    while ( *(_WORD *)(v13 + 2 * v8) );
  }
  else
  {
    v8 = 0;
  }
  v15[3] = v12;
  v15[1] = v8;
  v15[4] = L"\\";
  v15[7] = v11;
  v15[8] = L"\\";
  v15[11] = v9;
  v15[0] = v13;
  v15[2] = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates";
  v15[5] = 1;
  v15[6] = v10;
  v15[9] = 1;
  v15[10] = v7;
  return wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           a1,
           (__int64)v15,
           6);
}

```

## disassembly

```asm
0x1400281a0  push    rbp
0x1400281a2  push    rbx
0x1400281a3  push    rsi
0x1400281a4  push    rdi
0x1400281a5  lea     rbp, [rsp-2Fh]
0x1400281aa  sub     rsp, 98h
0x1400281b1  mov     rax, cs:__security_cookie
0x1400281b8  xor     rax, rsp
0x1400281bb  mov     [rbp+47h+var_30], rax
0x1400281bf  mov     rax, [rbp+47h+arg_28]
0x1400281c3  xor     edi, edi
0x1400281c5  mov     rbx, rcx
0x1400281c8  mov     r11, [rax]
0x1400281cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400281cf  test    r11, r11
0x1400281d2  jz      short loc_1400281E3
0x1400281d4  mov     rdx, rax
0x1400281d7  inc     rdx
0x1400281da  cmp     [r11+rdx*2], di
0x1400281df  jnz     short loc_1400281D7
0x1400281e1  jmp     short loc_1400281E6
0x1400281e3  mov     rdx, rdi
0x1400281e6  mov     r10, [r9]
0x1400281e9  test    r10, r10
0x1400281ec  jz      short loc_1400281FD
0x1400281ee  mov     rcx, rax
0x1400281f1  inc     rcx
0x1400281f4  cmp     [r10+rcx*2], di
0x1400281f9  jnz     short loc_1400281F1
0x1400281fb  jmp     short loc_140028200
0x1400281fd  mov     rcx, rdi
0x140028200  lea     rsi, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140028207  mov     r8, rax
0x14002820a  inc     r8
0x14002820d  cmp     [rsi+r8*2], di
0x140028212  jnz     short loc_14002820A
0x140028214  mov     r9, [rbx]
0x140028217  test    r9, r9
0x14002821a  jz      short loc_140028228
0x14002821c  inc     rax
0x14002821f  cmp     [r9+rax*2], di
0x140028224  jnz     short loc_14002821C
0x140028226  jmp     short loc_14002822B
0x140028228  mov     rax, rdi
0x14002822b  mov     [rbp+47h+var_78], r8
0x14002822f  lea     r8, asc_1400326D0; "\\"
0x140028236  mov     [rbp+47h+var_88], rax
0x14002823a  mov     eax, 1
0x14002823f  mov     [rbp+47h+var_70], r8
0x140028243  mov     [rbp+47h+var_58], rcx
0x140028247  mov     rcx, rbx
0x14002824a  mov     [rbp+47h+var_50], r8
0x14002824e  mov     [rbp+47h+var_38], rdx
0x140028252  lea     r8d, [rax+5]
0x140028256  lea     rdx, [rbp+47h+var_90]
0x14002825a  mov     [rbp+47h+var_90], r9
0x14002825e  mov     [rbp+47h+var_80], rsi
0x140028262  mov     [rbp+47h+var_68], rax
0x140028266  mov     [rbp+47h+var_60], r10
0x14002826a  mov     [rbp+47h+var_48], rax
0x14002826e  mov     [rbp+47h+var_40], r11
0x140028272  call    ??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z; wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)
0x140028277  mov     rcx, [rbp+47h+var_30]
0x14002827b  xor     rcx, rsp; StackCookie
0x14002827e  call    __security_check_cookie
0x140028283  add     rsp, 98h
0x14002828a  pop     rdi
0x14002828b  pop     rsi
0x14002828c  pop     rbx
0x14002828d  pop     rbp
0x14002828e  retn
```
