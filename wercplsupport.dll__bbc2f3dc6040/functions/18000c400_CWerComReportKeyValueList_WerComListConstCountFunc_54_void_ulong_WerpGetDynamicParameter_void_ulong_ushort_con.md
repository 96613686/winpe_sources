# CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c400`
- end: `0x18000c475`
- name: `?QueryInterface@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c480`

## callees

- `0x18000c400`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v3; // rax

  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = a1;
LABEL_7:
    *a3 = v3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
  if ( *a2 == *(_QWORD *)&IID_IWerKeyValueList.Data1 && a2[1] == *(_QWORD *)IID_IWerKeyValueList.Data4 )
  {
    v3 = (a1 + 24) & -(__int64)(a1 != 0);
    goto LABEL_7;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c400  sub     rsp, 28h
0x18000c404  mov     rax, [rdx]
0x18000c407  mov     r9, rcx
0x18000c40a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c411  jnz     short loc_18000C425
0x18000c413  mov     rax, [rdx+8]
0x18000c417  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c41e  jnz     short loc_18000C425
0x18000c420  mov     rax, rcx
0x18000c423  jmp     short loc_18000C44E
0x18000c425  mov     rax, [rdx]
0x18000c428  cmp     rax, qword ptr cs:IID_IWerKeyValueList.Data1
0x18000c42f  jnz     short loc_18000C464
0x18000c431  mov     rax, [rdx+8]
0x18000c435  cmp     rax, qword ptr cs:IID_IWerKeyValueList.Data4
0x18000c43c  jnz     short loc_18000C464
0x18000c43e  add     rcx, 18h
0x18000c442  mov     rax, r9
0x18000c445  neg     rax
0x18000c448  sbb     rax, rax
0x18000c44b  and     rax, rcx
0x18000c44e  mov     [r8], rax
0x18000c451  mov     rcx, r9
0x18000c454  mov     rax, [r9]
0x18000c457  mov     rax, [rax+8]
0x18000c45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c460  xor     eax, eax
0x18000c462  jmp     short loc_18000C470
0x18000c464  mov     qword ptr [r8], 0
0x18000c46b  mov     eax, 80004002h
0x18000c470  add     rsp, 28h
0x18000c474  retn
```
