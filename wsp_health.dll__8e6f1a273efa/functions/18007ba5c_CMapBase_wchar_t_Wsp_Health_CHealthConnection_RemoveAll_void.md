# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)

- ea: `0x18007ba5c`
- end: `0x18007baac`
- name: `?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ`
- size: `80`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180079d30`
- `0x180079ec8`
- `0x18007a0f0`

## callees

- `0x18007b310`
- `0x18007ba5c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007ba75`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007ba75`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18007ba89`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18007ba89`

## pseudocode

```c
__int64 __fastcall CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(_DWORD *TableContext)
{
  struct _RTL_AVL_TABLE *v2; // rdi
  PVOID v3; // rax

  v2 = (struct _RTL_AVL_TABLE *)(TableContext + 2);
  while ( 1 )
  {
    v3 = RtlEnumerateGenericTableAvl(v2, 1u);
    if ( !v3 )
      break;
    RtlDeleteElementGenericTableAvl(v2, v3);
    --TableContext[28];
  }
  return CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Initialize(TableContext);
}

```

## disassembly

```asm
0x18007ba5c  mov     [rsp+arg_0], rbx
0x18007ba61  push    rdi
0x18007ba62  sub     rsp, 20h
0x18007ba66  mov     rbx, rcx
0x18007ba69  lea     rdi, [rcx+8]
0x18007ba6d  jmp     short loc_18007BA84
0x18007ba6f  mov     rdx, rax; Buffer
0x18007ba72  mov     rcx, rdi; Table
0x18007ba75  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007ba7c  nop     dword ptr [rax+rax+00h]
0x18007ba81  dec     dword ptr [rbx+70h]
0x18007ba84  mov     dl, 1; Restart
0x18007ba86  mov     rcx, rdi; Table
0x18007ba89  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18007ba90  nop     dword ptr [rax+rax+00h]
0x18007ba95  test    rax, rax
0x18007ba98  jnz     short loc_18007BA6F
0x18007ba9a  mov     rcx, rbx; TableContext
0x18007ba9d  mov     rbx, [rsp+28h+arg_0]
0x18007baa2  add     rsp, 20h
0x18007baa6  pop     rdi
0x18007baa7  jmp     ?Initialize@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@AEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Initialize(void)
```
