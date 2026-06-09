# RegSetExpand

- ea: `0x180009418`
- end: `0x180009466`
- name: `RegSetExpand`
- size: `78`
- prototype: `_BOOL8 __fastcall(HKEY, const WCHAR *, const WCHAR *, BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003080`

## callees

- `0x18000932c`
- `0x180009418`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009459`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009459`

## pseudocode

```c
_BOOL8 __fastcall RegSetExpand(HKEY a1, const WCHAR *a2, const WCHAR *a3, BYTE *a4)
{
  __int64 v4; // rax

  if ( a1 && a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a4[2 * v4] );
    return RegSetBinEx(a1, a2, a3, 2u, a4, 2 * (int)v4 + 2);
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180009418  sub     rsp, 38h
0x18000941c  xor     r10d, r10d
0x18000941f  test    rcx, rcx
0x180009422  jz      short loc_180009454
0x180009424  test    r9, r9
0x180009427  jz      short loc_180009454
0x180009429  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000942d  inc     rax
0x180009430  cmp     [r9+rax*2], r10w
0x180009435  jnz     short loc_18000942D
0x180009437  lea     eax, ds:2[rax*2]
0x18000943e  mov     [rsp+38h+var_10], eax
0x180009442  mov     [rsp+38h+var_18], r9
0x180009447  mov     r9d, 2
0x18000944d  call    RegSetBinEx
0x180009452  jmp     short loc_180009461
0x180009454  mov     ecx, 57h ; 'W'; dwErrCode
0x180009459  call    cs:__imp_SetLastError
0x18000945f  xor     eax, eax
0x180009461  add     rsp, 38h
0x180009465  retn
```
