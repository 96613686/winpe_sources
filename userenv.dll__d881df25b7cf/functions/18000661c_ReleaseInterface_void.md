# _ReleaseInterface(void *)

- ea: `0x18000661c`
- end: `0x180006662`
- name: `?_ReleaseInterface@@YAJPEAX@Z`
- size: `70`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006300`
- `0x180006798`

## callees

- `0x18000661c`
- `0x18000dae0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000662f`
- `RPCRT4!RpcBindingFree` at `0x18000662f`

## string_xrefs

- `0x18000664c`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
int __fastcall _ReleaseInterface(void *a1)
{
  unsigned int v1; // eax
  unsigned int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  Binding = a1;
  if ( a1 && (v1 = RpcBindingFree(&Binding)) != 0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x61,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\dll\\profrpc.cpp",
             (const char *)v1,
             v3);
  else
    return 0;
}

```

## disassembly

```asm
0x18000661c  mov     [rsp+Binding], rcx
0x180006621  sub     rsp, 28h
0x180006625  test    rcx, rcx
0x180006628  jz      short loc_18000663F
0x18000662a  lea     rcx, [rsp+28h+Binding]; Binding
0x18000662f  call    cs:__imp_RpcBindingFree
0x180006636  nop     dword ptr [rax+rax+00h]
0x18000663b  test    eax, eax
0x18000663d  jnz     short loc_180006647
0x18000663f  xor     eax, eax
0x180006641  add     rsp, 28h
0x180006645  retn
0x180006647  mov     rcx, [rsp+28h]; this
0x18000664c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006653  mov     r9d, eax; char *
0x180006656  mov     edx, 61h ; 'a'; void *
0x18000665b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180006660  jmp     short loc_180006641
```
