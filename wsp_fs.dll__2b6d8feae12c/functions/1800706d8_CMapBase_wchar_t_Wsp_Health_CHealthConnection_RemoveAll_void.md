# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::RemoveAll(void)

- ea: `0x1800706d8`
- end: `0x18007071c`
- name: `?RemoveAll@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAXXZ`
- size: `68`
- prototype: `__int64 __fastcall(PVOID TableContext)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006f138`
- `0x18006f2f8`
- `0x18006f4f0`

## callees

- `0x18006ffd0`
- `0x1800706d8`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800706ff`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800706ff`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800706f1`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800706f1`

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
0x1800706d8  mov     [rsp+arg_0], rbx
0x1800706dd  push    rdi
0x1800706de  sub     rsp, 20h
0x1800706e2  mov     rbx, rcx
0x1800706e5  lea     rdi, [rcx+8]
0x1800706e9  jmp     short loc_1800706FA
0x1800706eb  mov     rdx, rax; Buffer
0x1800706ee  mov     rcx, rdi; Table
0x1800706f1  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800706f7  dec     dword ptr [rbx+70h]
0x1800706fa  mov     dl, 1; Restart
0x1800706fc  mov     rcx, rdi; Table
0x1800706ff  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180070705  test    rax, rax
0x180070708  jnz     short loc_1800706EB
0x18007070a  mov     rcx, rbx; TableContext
0x18007070d  mov     rbx, [rsp+28h+arg_0]
0x180070712  add     rsp, 20h
0x180070716  pop     rdi
0x180070717  jmp     ?Initialize@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@AEAAXXZ; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Initialize(void)
```
