# CSLLUAComInstance::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x18001dd00`
- end: `0x18001dd67`
- name: `?_InternalQueryInterface@CSLLUAComInstance@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(CSLLUAComInstance *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x18001dd00`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CSLLUAComInstance::_InternalQueryInterface(
        CSLLUAComInstance *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ecx

  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v6;
  }
  if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&GUID_12fbfecb_7cce_473e_8737_78ee6c9ccaeb.Data1
    || *(_QWORD *)a2->Data4 != *(_QWORD *)GUID_12fbfecb_7cce_473e_8737_78ee6c9ccaeb.Data4 )
  {
    v5 = 2147500034LL;
    *a3 = 0;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(CSLLUAComInstance *))(*(_QWORD *)this + 8LL))(this);
  v6 = 0;
  *a3 = this;
  return v6;
}

```

## disassembly

```asm
0x18001dd00  mov     [rsp+arg_0], rbx
0x18001dd05  push    rdi
0x18001dd06  sub     rsp, 20h
0x18001dd0a  mov     rbx, r8
0x18001dd0d  mov     rdi, rcx
0x18001dd10  test    r8, r8
0x18001dd13  jnz     short loc_18001DD1C
0x18001dd15  mov     ecx, 80004003h
0x18001dd1a  jmp     short loc_18001DD54
0x18001dd1c  mov     rax, [rdx]
0x18001dd1f  cmp     rax, qword ptr cs:_GUID_12fbfecb_7cce_473e_8737_78ee6c9ccaeb.Data1
0x18001dd26  jnz     short loc_18001DD48
0x18001dd28  mov     rax, [rdx+8]
0x18001dd2c  cmp     rax, qword ptr cs:_GUID_12fbfecb_7cce_473e_8737_78ee6c9ccaeb.Data4
0x18001dd33  jnz     short loc_18001DD48
0x18001dd35  mov     rax, [rcx]
0x18001dd38  mov     rax, [rax+8]
0x18001dd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd41  xor     ecx, ecx
0x18001dd43  mov     [rbx], rdi
0x18001dd46  jmp     short loc_18001DD59
0x18001dd48  mov     ecx, 80004002h
0x18001dd4d  mov     qword ptr [r8], 0
0x18001dd54  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001dd59  mov     rbx, [rsp+28h+arg_0]
0x18001dd5e  mov     eax, ecx
0x18001dd60  add     rsp, 20h
0x18001dd64  pop     rdi
0x18001dd65  retn
```
