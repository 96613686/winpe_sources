# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)

- ea: `0x180072184`
- end: `0x1800721d4`
- name: `?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ`
- size: `80`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180070a14`
- `0x180070bf8`
- `0x180070e20`

## callees

- `0x1800719a0`
- `0x180072184`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800721b1`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800721b1`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007219d`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007219d`

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
0x180072184  mov     [rsp+arg_0], rbx
0x180072189  push    rdi
0x18007218a  sub     rsp, 20h
0x18007218e  mov     rbx, rcx
0x180072191  lea     rdi, [rcx+8]
0x180072195  jmp     short loc_1800721AC
0x180072197  mov     rdx, rax; Buffer
0x18007219a  mov     rcx, rdi; Table
0x18007219d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800721a4  nop     dword ptr [rax+rax+00h]
0x1800721a9  dec     dword ptr [rbx+70h]
0x1800721ac  mov     dl, 1; Restart
0x1800721ae  mov     rcx, rdi; Table
0x1800721b1  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800721b8  nop     dword ptr [rax+rax+00h]
0x1800721bd  test    rax, rax
0x1800721c0  jnz     short loc_180072197
0x1800721c2  mov     rcx, rbx; TableContext
0x1800721c5  mov     rbx, [rsp+28h+arg_0]
0x1800721ca  add     rsp, 20h
0x1800721ce  pop     rdi
0x1800721cf  jmp     ?Initialize@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@AEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Initialize(void)
```
