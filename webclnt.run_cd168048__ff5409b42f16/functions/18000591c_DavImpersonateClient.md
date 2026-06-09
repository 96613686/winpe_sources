# DavImpersonateClient

- ea: `0x18000591c`
- end: `0x180005969`
- name: `DavImpersonateClient`
- size: `77`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003458`
- `0x180003a9c`
- `0x180003cbc`
- `0x1800049bc`
- `0x180005568`
- `0x1800056f4`
- `0x180005844`
- `0x180005de4`
- `0x180006d20`
- `0x180007e10`
- `0x1800099d0`
- `0x18000a770`

## callees

- `0x18000591c`
- `0x18000b7dc`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180005924`
- `RPCRT4!RpcImpersonateClient` at `0x180005924`

## pseudocode

```c
__int64 DavImpersonateClient()
{
  unsigned int v0; // ebx

  v0 = RpcImpersonateClient(0);
  if ( v0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18000591c  push    rbx
0x18000591e  sub     rsp, 20h
0x180005922  xor     ecx, ecx; BindingHandle
0x180005924  call    cs:__imp_RpcImpersonateClient
0x18000592a  mov     ebx, eax
0x18000592c  test    eax, eax
0x18000592e  jz      short loc_180005961
0x180005930  mov     rcx, cs:WPP_GLOBAL_Control
0x180005937  lea     rax, WPP_GLOBAL_Control
0x18000593e  cmp     rcx, rax
0x180005941  jz      short loc_180005961
0x180005943  test    byte ptr [rcx+1Ch], 1
0x180005947  jz      short loc_180005961
0x180005949  mov     rcx, [rcx+10h]
0x18000594d  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180005954  mov     edx, 0E5h
0x180005959  mov     r9d, ebx
0x18000595c  call    WPP_SF_d
0x180005961  mov     eax, ebx
0x180005963  add     rsp, 20h
0x180005967  pop     rbx
0x180005968  retn
```
