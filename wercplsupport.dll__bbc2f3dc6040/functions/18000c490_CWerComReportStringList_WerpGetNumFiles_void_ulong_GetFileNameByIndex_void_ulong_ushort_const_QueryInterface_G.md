# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c490`
- end: `0x18000c505`
- name: `?QueryInterface@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c510`

## callees

- `0x18000c490`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::QueryInterface(
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
  if ( *a2 == *(_QWORD *)&IID_IWerStringList.Data1 && a2[1] == *(_QWORD *)IID_IWerStringList.Data4 )
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
0x18000c490  sub     rsp, 28h
0x18000c494  mov     rax, [rdx]
0x18000c497  mov     r9, rcx
0x18000c49a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c4a1  jnz     short loc_18000C4B5
0x18000c4a3  mov     rax, [rdx+8]
0x18000c4a7  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c4ae  jnz     short loc_18000C4B5
0x18000c4b0  mov     rax, rcx
0x18000c4b3  jmp     short loc_18000C4DE
0x18000c4b5  mov     rax, [rdx]
0x18000c4b8  cmp     rax, qword ptr cs:IID_IWerStringList.Data1
0x18000c4bf  jnz     short loc_18000C4F4
0x18000c4c1  mov     rax, [rdx+8]
0x18000c4c5  cmp     rax, qword ptr cs:IID_IWerStringList.Data4
0x18000c4cc  jnz     short loc_18000C4F4
0x18000c4ce  add     rcx, 18h
0x18000c4d2  mov     rax, r9
0x18000c4d5  neg     rax
0x18000c4d8  sbb     rax, rax
0x18000c4db  and     rax, rcx
0x18000c4de  mov     [r8], rax
0x18000c4e1  mov     rcx, r9
0x18000c4e4  mov     rax, [r9]
0x18000c4e7  mov     rax, [rax+8]
0x18000c4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f0  xor     eax, eax
0x18000c4f2  jmp     short loc_18000C500
0x18000c4f4  mov     qword ptr [r8], 0
0x18000c4fb  mov     eax, 80004002h
0x18000c500  add     rsp, 28h
0x18000c504  retn
```
