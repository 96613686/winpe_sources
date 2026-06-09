# ComTaskHost::QueryInterface(_GUID const &,void * *)

- ea: `0x140006450`
- end: `0x1400064fa`
- name: `?QueryInterface@ComTaskHost@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(ComTaskHost *this, const struct _GUID *, ComTaskHost **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009bc0`

## callees

- `0x140006450`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ComTaskHost::QueryInterface(ComTaskHost *this, const struct _GUID *a2, ComTaskHost **a3)
{
  __int64 v3; // rax
  ComTaskHost *v4; // rdx
  ComTaskHost *v5; // rax
  __int64 v7; // rax
  __int64 v8; // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v3 = *(_QWORD *)&GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a.Data1 == *(_QWORD *)&a2->Data1 )
    v3 = *(_QWORD *)GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a.Data4 - *(_QWORD *)a2->Data4;
  if ( !v3 )
    goto LABEL_5;
  v7 = *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 == *(_QWORD *)&a2->Data1 )
    v7 = *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 - *(_QWORD *)a2->Data4;
  if ( v7 )
  {
    v8 = *(_QWORD *)&GUID_3e4c9351_d966_4b8b_bb87_ceba68bb0107.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&GUID_3e4c9351_d966_4b8b_bb87_ceba68bb0107.Data1 == *(_QWORD *)&a2->Data1 )
      v8 = *(_QWORD *)GUID_3e4c9351_d966_4b8b_bb87_ceba68bb0107.Data4 - *(_QWORD *)a2->Data4;
    if ( v8 )
      return 2147500034LL;
    v4 = (ComTaskHost *)((char *)this + 8);
    if ( !this )
      v4 = 0;
    v5 = v4;
  }
  else
  {
LABEL_5:
    v4 = this;
    v5 = this;
  }
  *a3 = v5;
  if ( !v4 )
    return 2147500034LL;
  (*(void (__fastcall **)(ComTaskHost *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x140006450  sub     rsp, 28h
0x140006454  test    r8, r8
0x140006457  jz      loc_1400064F3
0x14000645d  mov     qword ptr [r8], 0
0x140006464  mov     rax, qword ptr cs:_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a.Data1
0x14000646b  sub     rax, [rdx]
0x14000646e  jnz     short loc_14000647B
0x140006470  mov     rax, qword ptr cs:_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a.Data4
0x140006477  sub     rax, [rdx+8]
0x14000647b  test    rax, rax
0x14000647e  jnz     short loc_140006498
0x140006480  mov     rdx, rcx
0x140006483  mov     rax, rcx
0x140006486  mov     [r8], rax
0x140006489  test    rdx, rdx
0x14000648c  jnz     short loc_1400064E0
0x14000648e  mov     eax, 80004002h
0x140006493  add     rsp, 28h
0x140006497  retn
0x140006498  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x14000649f  sub     rax, [rdx]
0x1400064a2  jnz     short loc_1400064AF
0x1400064a4  mov     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1400064ab  sub     rax, [rdx+8]
0x1400064af  test    rax, rax
0x1400064b2  jz      short loc_140006480
0x1400064b4  mov     rax, qword ptr cs:_GUID_3e4c9351_d966_4b8b_bb87_ceba68bb0107.Data1
0x1400064bb  sub     rax, [rdx]
0x1400064be  jnz     short loc_1400064CB
0x1400064c0  mov     rax, qword ptr cs:_GUID_3e4c9351_d966_4b8b_bb87_ceba68bb0107.Data4
0x1400064c7  sub     rax, [rdx+8]
0x1400064cb  test    rax, rax
0x1400064ce  jnz     short loc_14000648E
0x1400064d0  test    rcx, rcx
0x1400064d3  lea     rdx, [rcx+8]
0x1400064d7  cmovz   rdx, rax
0x1400064db  mov     rax, rdx
0x1400064de  jmp     short loc_140006486
0x1400064e0  mov     rax, [rcx]
0x1400064e3  mov     rax, [rax+8]
0x1400064e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064ec  xor     eax, eax
0x1400064ee  add     rsp, 28h
0x1400064f2  retn
0x1400064f3  mov     eax, 80004003h
0x1400064f8  jmp     short loc_140006493
```
