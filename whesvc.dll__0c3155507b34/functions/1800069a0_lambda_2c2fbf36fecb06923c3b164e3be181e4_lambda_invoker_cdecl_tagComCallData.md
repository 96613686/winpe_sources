# _lambda_2c2fbf36fecb06923c3b164e3be181e4_::_lambda_invoker_cdecl_(tagComCallData *)

- ea: `0x1800069a0`
- end: `0x1800069fc`
- name: `?_lambda_invoker_cdecl_@_lambda_2c2fbf36fecb06923c3b164e3be181e4_@@CA@PEAUtagComCallData@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800069a0`
- `0x180008bc0`
- `0x180009044`
- `0x18000999c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1800069df`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x1800069df`

## string_xrefs

- `0x1800069cb`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
__int64 __fastcall _lambda_2c2fbf36fecb06923c3b164e3be181e4_::_lambda_invoker_cdecl_(struct tagComCallData *a1)
{
  Microsoft::WRL::Details **pUserDefined; // rbx
  const unsigned __int16 *v2; // r8
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  pUserDefined = (Microsoft::WRL::Details **)a1->pUserDefined;
  PreDisconnectContextCallback();
  v3 = Microsoft::WRL::Details::UnregisterObjects(*pUserDefined, pUserDefined[1], v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = CoDisconnectContext(0xFFFFFFFF);
    v4 = v3;
    if ( v3 >= 0 )
      return 0;
    v5 = 102;
  }
  else
  {
    v5 = 98;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
    (const char *)(unsigned int)v3,
    v7);
  return v4;
}

```

## disassembly

```asm
0x1800069a0  push    rbx; int
0x1800069a2  sub     rsp, 20h
0x1800069a6  mov     rbx, [rcx+8]
0x1800069aa  call    ?PreDisconnectContextCallback@@YAXXZ; PreDisconnectContextCallback(void)
0x1800069af  mov     rdx, [rbx+8]; struct Microsoft::WRL::Details::ModuleBase *
0x1800069b3  mov     rcx, [rbx]; this
0x1800069b6  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x1800069bb  mov     ebx, eax
0x1800069bd  test    eax, eax
0x1800069bf  jns     short loc_1800069DC
0x1800069c1  mov     edx, 62h ; 'b'; void *
0x1800069c6  mov     rcx, [rsp+28h]; this
0x1800069cb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x1800069d2  mov     r9d, eax; char *
0x1800069d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069da  jmp     short loc_1800069F4
0x1800069dc  or      ecx, 0FFFFFFFFh; dwTimeout
0x1800069df  call    cs:__imp_CoDisconnectContext
0x1800069e5  mov     ebx, eax
0x1800069e7  test    eax, eax
0x1800069e9  jns     short loc_1800069F2
0x1800069eb  mov     edx, 66h ; 'f'
0x1800069f0  jmp     short loc_1800069C6
0x1800069f2  xor     ebx, ebx
0x1800069f4  mov     eax, ebx
0x1800069f6  add     rsp, 20h
0x1800069fa  pop     rbx
0x1800069fb  retn
```
