# _ReleaseInterface(void *)

- ea: `0x180005e68`
- end: `0x180005ea7`
- name: `?_ReleaseInterface@@YAJPEAX@Z`
- size: `63`
- prototype: `int __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b28`
- `0x180005fc8`

## callees

- `0x180005e68`
- `0x18000ce7c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180005e7b`
- `RPCRT4!RpcBindingFree` at `0x180005e7b`

## string_xrefs

- `0x180005e91`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

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
0x180005e68  mov     [rsp+Binding], rcx
0x180005e6d  sub     rsp, 28h
0x180005e71  test    rcx, rcx
0x180005e74  jz      short loc_180005E85
0x180005e76  lea     rcx, [rsp+28h+Binding]; Binding
0x180005e7b  call    cs:__imp_RpcBindingFree
0x180005e81  test    eax, eax
0x180005e83  jnz     short loc_180005E8C
0x180005e85  xor     eax, eax
0x180005e87  add     rsp, 28h
0x180005e8b  retn
0x180005e8c  mov     rcx, [rsp+28h]; this
0x180005e91  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005e98  mov     r9d, eax; char *
0x180005e9b  mov     edx, 61h ; 'a'; void *
0x180005ea0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180005ea5  jmp     short loc_180005E87
```
