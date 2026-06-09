# HTTP2TestHook(tagSystemFunction001Commands,void *,void *)

- ea: `0x18000b920`
- end: `0x18000b9bb`
- name: `?HTTP2TestHook@@YAJW4tagSystemFunction001Commands@@PEAX1@Z`
- size: `155`
- prototype: `int __high(enum tagSystemFunction001Commands, void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b920`
- `0x18001e3d4`

## import_xrefs

- `RPCRT4!I_RpcFree` at `0x18000b945`
- `RPCRT4!I_RpcFree` at `0x18000b982`
- `RPCRT4!I_RpcFree` at `0x18000b945`
- `RPCRT4!I_RpcFree` at `0x18000b982`

## pseudocode

```c
__int64 __fastcall HTTP2TestHook(int a1, const unsigned __int16 *a2)
{
  if ( a1 )
  {
    if ( a1 != 1 )
      return 1766;
    if ( OutChannelTargetTestOverride )
    {
      I_RpcFree(OutChannelTargetTestOverride);
      OutChannelTargetTestOverride = 0;
    }
    if ( a2 )
    {
      OutChannelTargetTestOverride = DuplicateString(a2);
      if ( !OutChannelTargetTestOverride )
        return 14;
    }
  }
  else
  {
    if ( InChannelTargetTestOverride )
    {
      I_RpcFree((void *)InChannelTargetTestOverride);
      InChannelTargetTestOverride = 0;
    }
    if ( a2 )
    {
      InChannelTargetTestOverride = DuplicateString(a2);
      return InChannelTargetTestOverride == 0 ? 0xE : 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b920  push    rbx
0x18000b922  sub     rsp, 20h
0x18000b926  mov     rbx, rdx
0x18000b929  test    ecx, ecx
0x18000b92b  jz      short loc_18000B976
0x18000b92d  cmp     ecx, 1
0x18000b930  jz      short loc_18000B939
0x18000b932  mov     eax, 6E6h
0x18000b937  jmp     short loc_18000B9B5
0x18000b939  mov     rcx, cs:?OutChannelTargetTestOverride@@3PEAGEA; Object
0x18000b940  test    rcx, rcx
0x18000b943  jz      short loc_18000B956
0x18000b945  call    cs:__imp_I_RpcFree
0x18000b94b  mov     cs:?OutChannelTargetTestOverride@@3PEAGEA, 0; ushort * OutChannelTargetTestOverride
0x18000b956  test    rbx, rbx
0x18000b959  jz      short loc_18000B9B3
0x18000b95b  mov     rcx, rbx; Src
0x18000b95e  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18000b963  mov     cs:?OutChannelTargetTestOverride@@3PEAGEA, rax; ushort * OutChannelTargetTestOverride
0x18000b96a  test    rax, rax
0x18000b96d  jnz     short loc_18000B9B3
0x18000b96f  mov     eax, 0Eh
0x18000b974  jmp     short loc_18000B9B5
0x18000b976  mov     rcx, cs:?InChannelTargetTestOverride@@3PEAGEA; Object
0x18000b97d  test    rcx, rcx
0x18000b980  jz      short loc_18000B993
0x18000b982  call    cs:__imp_I_RpcFree
0x18000b988  mov     cs:?InChannelTargetTestOverride@@3PEAGEA, 0; ushort * InChannelTargetTestOverride
0x18000b993  test    rbx, rbx
0x18000b996  jz      short loc_18000B9B3
0x18000b998  mov     rcx, rbx; Src
0x18000b99b  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x18000b9a0  mov     cs:?InChannelTargetTestOverride@@3PEAGEA, rax; ushort * InChannelTargetTestOverride
0x18000b9a7  neg     rax
0x18000b9aa  sbb     eax, eax
0x18000b9ac  not     eax
0x18000b9ae  and     eax, 0Eh
0x18000b9b1  jmp     short loc_18000B9B5
0x18000b9b3  xor     eax, eax
0x18000b9b5  add     rsp, 20h
0x18000b9b9  pop     rbx
0x18000b9ba  retn
```
