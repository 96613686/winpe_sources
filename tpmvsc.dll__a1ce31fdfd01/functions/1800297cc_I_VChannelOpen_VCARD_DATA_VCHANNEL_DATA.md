# I_VChannelOpen(VCARD_DATA *,VCHANNEL_DATA * *)

- ea: `0x1800297cc`
- end: `0x180029932`
- name: `?I_VChannelOpen@@YAKPEAUVCARD_DATA@@PEAPEAUVCHANNEL_DATA@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, struct VCHANNEL_DATA **)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016954`
- `0x180017448`
- `0x18002e354`

## callees

- `0x180001ec0`
- `0x1800023c0`
- `0x18000653c`
- `0x1800273a0`
- `0x18002743c`
- `0x180027d30`
- `0x1800295a4`
- `0x1800297cc`
- `0x180029d2c`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180029896`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180029896`

## string_xrefs

- `0x1800297fd`: `I_VChannelOpen`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_VChannelOpen(struct VCARD_DATA *a1, struct VCHANNEL_DATA **a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // rbx
  unsigned int v9; // edx
  int v11; // [rsp+20h] [rbp-50h] BYREF
  int v12; // [rsp+24h] [rbp-4Ch] BYREF
  VCHANNEL_DATA *v13; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v14; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-38h] BYREF
  char v16[16]; // [rsp+58h] [rbp-18h] BYREF

  v12 = 0;
  v11 = 0;
  strcpy(v16, "I_VChannelOpen");
  v15[0] = v16;
  v15[1] = &v11;
  v15[2] = &v12;
  lambda_f15c6207539b57b57ad861f3bca64379_::operator()(v15);
  v11 = 1;
  v14 = v15;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !(unsigned int)I_VCardIsLoaded(a1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7, v6);
  v8 = (char *)operator new(0xB0u);
  v13 = (VCHANNEL_DATA *)v8;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 8), 0, 0);
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 7) = 0;
  std::_Tree<std::_Tmap_traits<unsigned char,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Alloc_sentinel_and_proxy((_QWORD *)v8 + 6);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v8 + 10);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v8 + 13);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v8 + 16);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>((_QWORD *)v8 + 19);
  *(_QWORD *)v8 = a1;
  *((_QWORD *)v8 + 8) = 0;
  v8[72] = 0;
  _InterlockedIncrement((volatile signed __int32 *)a1 + 30);
  v13 = 0;
  *a2 = (struct VCHANNEL_DATA *)v8;
  LODWORD(v8) = v12;
  std::unique_ptr<VCHANNEL_DATA>::~unique_ptr<VCHANNEL_DATA>(&v13, v9);
  WppTraceUnwinder__lambda_f15c6207539b57b57ad861f3bca64379____::_WppTraceUnwinder__lambda_f15c6207539b57b57ad861f3bca64379____(&v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800297cc  mov     [rsp-18h+arg_10], rbx
0x1800297d1  push    rbp
0x1800297d2  push    rsi
0x1800297d3  push    rdi
0x1800297d4  mov     rbp, rsp
0x1800297d7  sub     rsp, 70h
0x1800297db  mov     rax, cs:__security_cookie
0x1800297e2  xor     rax, rsp
0x1800297e5  mov     [rbp+var_8], rax
0x1800297e9  mov     rsi, rdx
0x1800297ec  mov     rdi, rcx
0x1800297ef  mov     [rbp+var_4C], 0
0x1800297f6  mov     [rbp+var_50], 0
0x1800297fd  movsd   xmm0, qword ptr cs:aIVchannelopen; "I_VChannelOpen"
0x180029805  movsd   qword ptr [rbp+var_18], xmm0
0x18002980a  mov     eax, dword ptr cs:aIVchannelopen+8; "elOpen"
0x180029810  mov     dword ptr [rbp+var_18+8], eax
0x180029813  movzx   eax, word ptr cs:aIVchannelopen+0Ch; "en"
0x18002981a  mov     word ptr [rbp+var_18+0Ch], ax
0x18002981e  mov     al, byte ptr cs:aIVchannelopen+0Eh; ""
0x180029824  mov     [rbp+var_18+0Eh], al
0x180029827  lea     rax, [rbp+var_18]
0x18002982b  mov     [rbp+var_38], rax
0x18002982f  lea     rax, [rbp+var_50]
0x180029833  mov     [rbp+var_30], rax
0x180029837  lea     rax, [rbp+var_4C]
0x18002983b  mov     [rbp+var_28], rax
0x18002983f  lea     rcx, [rbp+var_38]
0x180029843  call    _lambda_f15c6207539b57b57ad861f3bca64379___operator__
0x180029848  mov     [rbp+var_50], 1
0x18002984f  lea     rax, [rbp+var_38]
0x180029853  mov     [rbp+var_40], rax
0x180029857  test    rdi, rdi
0x18002985a  jnz     short loc_180029861
0x18002985c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180029861  test    rsi, rsi
0x180029864  jnz     short loc_18002986B
0x180029866  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002986b  mov     rcx, rdi; struct VCARD_DATA *
0x18002986e  call    ?I_VCardIsLoaded@@YAHPEBUVCARD_DATA@@@Z; I_VCardIsLoaded(VCARD_DATA const *)
0x180029873  test    eax, eax
0x180029875  jnz     short loc_18002987C
0x180029877  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002987c  mov     ecx, 0B0h; Size
0x180029881  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029886  mov     rbx, rax
0x180029889  mov     [rbp+var_48], rax
0x18002988d  lea     rcx, [rax+8]; lpCriticalSection
0x180029891  xor     r8d, r8d; Flags
0x180029894  xor     edx, edx; dwSpinCount
0x180029896  call    cs:__imp_InitializeCriticalSectionEx
0x18002989c  nop
0x18002989d  lea     rcx, [rbx+30h]
0x1800298a1  mov     qword ptr [rcx], 0
0x1800298a8  mov     qword ptr [rcx+8], 0
0x1800298b0  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@EV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<uchar,std::unique_ptr<KEY_MAP_RECORD_CACHE>,std::less<uchar>,std::allocator<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800298b5  lea     rcx, [rbx+50h]
0x1800298b9  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800298be  lea     rcx, [rbx+68h]
0x1800298c2  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800298c7  lea     rcx, [rbx+80h]
0x1800298ce  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800298d3  lea     rcx, [rbx+98h]
0x1800298da  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800298df  nop
0x1800298e0  mov     [rbx], rdi
0x1800298e3  mov     qword ptr [rbx+40h], 0
0x1800298eb  mov     byte ptr [rbx+48h], 0
0x1800298ef  lock inc dword ptr [rdi+78h]
0x1800298f3  mov     [rbp+var_48], 0
0x1800298fb  mov     [rsi], rbx
0x1800298fe  mov     ebx, [rbp+var_4C]
0x180029901  lea     rcx, [rbp+var_48]
0x180029905  call    ??1?$unique_ptr@UVCHANNEL_DATA@@U?$default_delete@UVCHANNEL_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<VCHANNEL_DATA>::~unique_ptr<VCHANNEL_DATA>(void)
0x18002990a  nop
0x18002990b  lea     rcx, [rbp+var_40]
0x18002990f  call    WppTraceUnwinder__lambda_f15c6207539b57b57ad861f3bca64379_______WppTraceUnwinder__lambda_f15c6207539b57b57ad861f3bca64379____
0x180029914  mov     eax, ebx
0x180029916  mov     rcx, [rbp+var_8]
0x18002991a  xor     rcx, rsp; StackCookie
0x18002991d  call    __security_check_cookie
0x180029922  mov     rbx, [rsp+70h+arg_10]
0x18002992a  add     rsp, 70h
0x18002992e  pop     rdi
0x18002992f  pop     rsi
0x180029930  pop     rbp
0x180029931  retn
```
