# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180016170`
- end: `0x1800161e5`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015cc0`
- `0x180016170`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800161cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800161cd`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rbx
  unsigned __int64 v1; // rax
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = (__int64 *)qword_18001DF80;
    v1 = qword_18001DF88;
    while ( (unsigned __int64)v0 < v1 )
    {
      v2 = *v0;
      if ( *v0 )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v1 = qword_18001DF88;
      }
      ++v0;
    }
    DeleteCriticalSection(&stru_18001DF90);
    ATL::_AtlComModule = 0;
  }
}

```

## disassembly

```asm
0x180016170  mov     [rsp+arg_0], rbx
0x180016175  push    rdi
0x180016176  sub     rsp, 20h
0x18001617a  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180016181  jz      short loc_1800161DA
0x180016183  mov     rbx, cs:qword_18001DF80
0x18001618a  mov     rax, cs:qword_18001DF88
0x180016191  jmp     short loc_1800161C1
0x180016193  mov     rdi, [rbx]
0x180016196  test    rdi, rdi
0x180016199  jz      short loc_1800161BD
0x18001619b  mov     rcx, [rdi+20h]
0x18001619f  test    rcx, rcx
0x1800161a2  jz      short loc_1800161B1
0x1800161a4  mov     rax, [rcx]
0x1800161a7  mov     rax, [rax+10h]
0x1800161ab  call    cs:__guard_dispatch_icall_fptr
0x1800161b1  and     qword ptr [rdi+20h], 0
0x1800161b6  mov     rax, cs:qword_18001DF88
0x1800161bd  add     rbx, 8
0x1800161c1  cmp     rbx, rax
0x1800161c4  jb      short loc_180016193
0x1800161c6  lea     rcx, stru_18001DF90; lpCriticalSection
0x1800161cd  call    cs:__imp_DeleteCriticalSection
0x1800161d3  and     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1800161da  mov     rbx, [rsp+28h+arg_0]
0x1800161df  add     rsp, 20h
0x1800161e3  pop     rdi
0x1800161e4  retn
```
