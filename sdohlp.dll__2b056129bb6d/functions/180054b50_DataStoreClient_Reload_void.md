# DataStoreClient::Reload(void)

- ea: `0x180054b50`
- end: `0x180054bca`
- name: `?Reload@DataStoreClient@@UEAAJXZ`
- size: `122`
- prototype: `__int64 __fastcall(DataStoreClient *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002cca4`
- `0x180042a80`
- `0x180054b50`
- `0x180058010`

## string_xrefs

- `0x180054b93`: `Reload() is called on a machine that doesn't support IIASDataStoreComServer2`

## pseudocode

```c
__int64 __fastcall DataStoreClient::Reload(DataStoreClient *this)
{
  __int64 v1; // rcx
  unsigned int v2; // ebx

  v1 = *((_QWORD *)this + 8);
  if ( v1 )
  {
    return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v1 + 80LL))(v1);
  }
  else
  {
    v2 = -2147467262;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Reload() is called on a machine that doesn't support IIASDataStoreComServer2");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids, "NPSDS");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180054b50  push    rbx
0x180054b52  sub     rsp, 20h
0x180054b56  mov     rcx, [rcx+40h]
0x180054b5a  test    rcx, rcx
0x180054b5d  jz      short loc_180054B6F
0x180054b5f  mov     rax, [rcx]
0x180054b62  mov     rax, [rax+50h]
0x180054b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b6b  mov     ebx, eax
0x180054b6d  jmp     short loc_180054BC2
0x180054b6f  mov     rax, cs:WPP_GLOBAL_Control
0x180054b76  lea     rcx, WPP_GLOBAL_Control
0x180054b7d  mov     ebx, 80004002h
0x180054b82  cmp     rax, rcx
0x180054b85  jz      short loc_180054BC2
0x180054b87  cmp     byte ptr [rax+19h], 2
0x180054b8b  jb      short loc_180054BC2
0x180054b8d  test    byte ptr [rax+1Ch], 10h
0x180054b91  jz      short loc_180054BC2
0x180054b93  lea     rcx, aReloadIsCalled; "Reload() is called on a machine that do"...
0x180054b9a  call    WppDbgPrint
0x180054b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ba6  lea     r9, aNpsds; "NPSDS"
0x180054bad  mov     edx, 0Eh
0x180054bb2  lea     r8, WPP_bc84e2600b1038389a22987ce46afadc_Traceguids
0x180054bb9  mov     rcx, [rcx+10h]
0x180054bbd  call    WPP_SF_s
0x180054bc2  mov     eax, ebx
0x180054bc4  add     rsp, 20h
0x180054bc8  pop     rbx
0x180054bc9  retn
```
