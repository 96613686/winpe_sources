# WdsProviderEndpointRemoved(void *,tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)

- ea: `0x180002b80`
- end: `0x180002bb8`
- name: `?WdsProviderEndpointRemoved@@YAXPEAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `56`
- prototype: `void __fastcall(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002b80`

## import_xrefs

- `WDSSRV!WdsPerfCounterSubtract` at `0x180002ba6`
- `WDSSRV!WdsPerfCounterSubtract` at `0x180002ba6`

## pseudocode

```c
void __fastcall WdsProviderEndpointRemoved(void *a1, struct tagWDS_ENDPOINT *a2, struct tagWDS_INTERFACE_INFO *a3)
{
  __int64 v3; // rcx

  if ( !*((_DWORD *)a2 + 1) && *((_WORD *)a2 + 6) == 4011 )
  {
    v3 = 28;
    if ( *((_DWORD *)a2 + 8) != 4 )
      v3 = 30;
    WdsPerfCounterSubtract(v3);
  }
}

```

## disassembly

```asm
0x180002b80  sub     rsp, 28h
0x180002b84  cmp     dword ptr [rdx+4], 0
0x180002b88  jnz     short loc_180002BB2
0x180002b8a  mov     eax, 0FABh
0x180002b8f  cmp     [rdx+0Ch], ax
0x180002b93  jnz     short loc_180002BB2
0x180002b95  cmp     dword ptr [rdx+20h], 4
0x180002b99  mov     edx, 1
0x180002b9e  lea     ecx, [rdx+1Bh]
0x180002ba1  jz      short loc_180002BA6
0x180002ba3  lea     ecx, [rdx+1Dh]
0x180002ba6  call    cs:__imp_WdsPerfCounterSubtract
0x180002bad  nop     dword ptr [rax+rax+00h]
0x180002bb2  add     rsp, 28h
0x180002bb6  retn
```
