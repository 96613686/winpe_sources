# CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)

- ea: `0x180093a3c`
- end: `0x180093a9b`
- name: `?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct IStorage *, unsigned __int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180054a88`

## callees

- `0x1800427ac`
- `0x1800931b0`
- `0x180093a3c`
- `0x180095010`

## string_xrefs

- `0x180093a60`: `WriteFmtUserTypeStg`

## pseudocode

```c
__int64 __fastcall CW32System::WriteFmtUserTypeStg(struct IStorage *a1, unsigned __int16 a2, unsigned __int16 *a3)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v7)(struct IStorage *, _QWORD, unsigned __int16 *); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v7 = (__int64 (__fastcall **)(struct IStorage *, _QWORD, unsigned __int16 *))((char *)Ole32Procs + 216);
  if ( !*((_QWORD *)Ole32Procs + 27) )
    SetProcAddr((FARPROC *)Ole32Procs + 27, 1, "WriteFmtUserTypeStg");
  if ( *v7 )
    return (*v7)(a1, a2, a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180093a3c  push    rbx
0x180093a3e  push    rbp
0x180093a3f  push    rsi
0x180093a40  push    rdi
0x180093a41  sub     rsp, 28h
0x180093a45  mov     rdi, r8
0x180093a48  movzx   esi, dx
0x180093a4b  mov     rbp, rcx
0x180093a4e  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180093a53  lea     rbx, [rax+0D8h]
0x180093a5a  cmp     qword ptr [rbx], 0
0x180093a5e  jnz     short loc_180093A74
0x180093a60  lea     r8, aWritefmtuserty; "WriteFmtUserTypeStg"
0x180093a67  mov     edx, 1
0x180093a6c  mov     rcx, rbx
0x180093a6f  call    SetProcAddr
0x180093a74  mov     rax, [rbx]
0x180093a77  test    rax, rax
0x180093a7a  jz      short loc_180093A8C
0x180093a7c  mov     r8, rdi
0x180093a7f  movzx   edx, si
0x180093a82  mov     rcx, rbp
0x180093a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a8a  jmp     short loc_180093A91
0x180093a8c  mov     eax, 80004005h
0x180093a91  add     rsp, 28h
0x180093a95  pop     rdi
0x180093a96  pop     rsi
0x180093a97  pop     rbp
0x180093a98  pop     rbx
0x180093a99  retn
```
