# DllCanUnloadNow

- ea: `0x180002750`
- end: `0x180002786`
- name: `DllCanUnloadNow`
- size: `54`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002750`
- `0x180002ad4`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return g_cDllRefs > 0;
}

```

## disassembly

```asm
0x180002750  sub     rsp, 28h
0x180002754  mov     rcx, cs:WPP_GLOBAL_Control
0x18000275b  lea     rax, WPP_GLOBAL_Control
0x180002762  cmp     rcx, rax
0x180002765  jz      short loc_180002776
0x180002767  test    byte ptr [rcx+1Ch], 8
0x18000276b  jz      short loc_180002776
0x18000276d  mov     rcx, [rcx+10h]
0x180002771  call    WPP_SF_D
0x180002776  xor     eax, eax
0x180002778  cmp     cs:?g_cDllRefs@@3JA, eax; long g_cDllRefs
0x18000277e  setnle  al
0x180002781  add     rsp, 28h
0x180002785  retn
```
