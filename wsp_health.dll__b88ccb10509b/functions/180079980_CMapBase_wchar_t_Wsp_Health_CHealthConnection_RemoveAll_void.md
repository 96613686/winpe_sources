# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)

- ea: `0x180079980`
- end: `0x1800799c4`
- name: `?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ`
- size: `68`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180077e44`
- `0x180077fc4`
- `0x1800781b0`

## callees

- `0x180079310`
- `0x180079980`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079999`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079999`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800799a7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800799a7`

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
0x180079980  mov     [rsp+arg_0], rbx
0x180079985  push    rdi
0x180079986  sub     rsp, 20h
0x18007998a  mov     rbx, rcx
0x18007998d  lea     rdi, [rcx+8]
0x180079991  jmp     short loc_1800799A2
0x180079993  mov     rdx, rax; Buffer
0x180079996  mov     rcx, rdi; Table
0x180079999  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007999f  dec     dword ptr [rbx+70h]
0x1800799a2  mov     dl, 1; Restart
0x1800799a4  mov     rcx, rdi; Table
0x1800799a7  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800799ad  test    rax, rax
0x1800799b0  jnz     short loc_180079993
0x1800799b2  mov     rcx, rbx; TableContext
0x1800799b5  mov     rbx, [rsp+28h+arg_0]
0x1800799ba  add     rsp, 20h
0x1800799be  pop     rdi
0x1800799bf  jmp     ?Initialize@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@AEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Initialize(void)
```
