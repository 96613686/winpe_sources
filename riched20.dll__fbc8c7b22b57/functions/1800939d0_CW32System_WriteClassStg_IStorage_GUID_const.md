# CW32System::WriteClassStg(IStorage *,_GUID const &)

- ea: `0x1800939d0`
- end: `0x180093a36`
- name: `?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(struct IStorage *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180054a88`

## callees

- `0x1800427ac`
- `0x1800931b0`
- `0x1800939d0`
- `0x180095010`

## string_xrefs

- `0x1800939f7`: `WriteClassStg`

## pseudocode

```c
__int64 __fastcall CW32System::WriteClassStg(struct IStorage *a1, const struct _GUID *a2)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v5)(struct IStorage *, const struct _GUID *); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v5 = (__int64 (__fastcall **)(struct IStorage *, const struct _GUID *))((char *)Ole32Procs + 224);
  if ( !*((_QWORD *)Ole32Procs + 28) )
    SetProcAddr((FARPROC *)Ole32Procs + 28, 1, "WriteClassStg");
  if ( *v5 )
    return (*v5)(a1, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800939d0  mov     [rsp+arg_0], rbx
0x1800939d5  mov     [rsp+arg_8], rsi
0x1800939da  push    rdi
0x1800939db  sub     rsp, 20h
0x1800939df  mov     rdi, rdx
0x1800939e2  mov     rsi, rcx
0x1800939e5  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x1800939ea  lea     rbx, [rax+0E0h]
0x1800939f1  cmp     qword ptr [rbx], 0
0x1800939f5  jnz     short loc_180093A0B
0x1800939f7  lea     r8, aWriteclassstg; "WriteClassStg"
0x1800939fe  mov     edx, 1
0x180093a03  mov     rcx, rbx
0x180093a06  call    SetProcAddr
0x180093a0b  mov     rax, [rbx]
0x180093a0e  test    rax, rax
0x180093a11  jz      short loc_180093A20
0x180093a13  mov     rdx, rdi
0x180093a16  mov     rcx, rsi
0x180093a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a1e  jmp     short loc_180093A25
0x180093a20  mov     eax, 80004005h
0x180093a25  mov     rbx, [rsp+28h+arg_0]
0x180093a2a  mov     rsi, [rsp+28h+arg_8]
0x180093a2f  add     rsp, 20h
0x180093a33  pop     rdi
0x180093a34  retn
```
