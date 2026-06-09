# HasAMatchingStart

- ea: `0x140005834`
- end: `0x14000590c`
- name: `HasAMatchingStart`
- size: `216`
- prototype: `__int64 __fastcall(struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004778`

## callees

- `0x140004c2c`
- `0x140005834`
- `0x14001ceb0`
- `0x14001d700`

## string_xrefs

- `0x1400058db`: `ProcessId`
- `0x140005891`: `TThreadId`

## pseudocode

```c
char __fastcall HasAMatchingStart(struct _EVENT_RECORD *a1, struct _PROCESS_RECORD **a2)
{
  char v3; // al
  char v6; // di
  struct _PROCESS_RECORD *ProcessById; // rax
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+20h] BYREF

  v3 = a1->EventHeader.EventDescriptor.Opcode - 2;
  v9 = 0;
  v10 = 0;
  if ( (v3 & 0xFD) != 0 )
    return 0;
  v6 = 0;
  if ( *(_QWORD *)&a1->EventHeader.ProviderId.Data1 != ThreadGuid
    || *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x7CBAD74FC000DA9DLL )
  {
    if ( *(_QWORD *)&a1->EventHeader.ProviderId.Data1 != ProcessGuid )
      return v6;
    if ( *(_QWORD *)a1->EventHeader.ProviderId.Data4 != 0x7CBAD74FC000DA9DLL )
      return v6;
    v8 = 4;
    if ( GetMofData(a1, L"ProcessId", &v10, &v8) )
      return v6;
    ProcessById = FindProcessById(v10, 0);
    goto LABEL_11;
  }
  v8 = 4;
  if ( !GetMofData(a1, L"TThreadId", &v9, &v8) )
  {
    ProcessById = FindGlobalThreadById(v9, a1);
LABEL_11:
    if ( ProcessById )
    {
      *a2 = ProcessById;
      return 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140005834  push    rbx
0x140005836  push    rsi
0x140005837  push    rdi
0x140005838  sub     rsp, 20h
0x14000583c  mov     al, [rcx+2Dh]
0x14000583f  mov     rsi, rdx
0x140005842  sub     al, 2
0x140005844  mov     [rsp+38h+arg_10], 0
0x14000584c  mov     [rsp+38h+arg_18], 0
0x140005854  mov     rbx, rcx
0x140005857  test    al, 0FDh
0x140005859  jz      short loc_140005862
0x14000585b  xor     al, al
0x14000585d  jmp     loc_140005904
0x140005862  mov     rax, [rcx+18h]
0x140005866  xor     dil, dil
0x140005869  cmp     rax, cs:ThreadGuid
0x140005870  jnz     short loc_1400058AF
0x140005872  mov     rax, [rcx+20h]
0x140005876  cmp     rax, cs:qword_1400431B0
0x14000587d  jnz     short loc_1400058AF
0x14000587f  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x140005884  mov     [rsp+38h+arg_0], 4
0x14000588c  lea     r8, [rsp+38h+arg_10]; void *
0x140005891  lea     rdx, aTthreadid; "TThreadId"
0x140005898  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000589d  test    eax, eax
0x14000589f  jnz     short loc_140005901
0x1400058a1  mov     ecx, [rsp+38h+arg_10]; unsigned int
0x1400058a5  mov     rdx, rbx; struct _EVENT_RECORD *
0x1400058a8  call    ?FindGlobalThreadById@@YAPEAU_THREAD_RECORD@@KPEAU_EVENT_RECORD@@@Z; FindGlobalThreadById(ulong,_EVENT_RECORD *)
0x1400058ad  jmp     short loc_1400058F6
0x1400058af  mov     rax, [rcx+18h]
0x1400058b3  cmp     rax, cs:ProcessGuid
0x1400058ba  jnz     short loc_140005901
0x1400058bc  mov     rax, [rcx+20h]
0x1400058c0  cmp     rax, cs:qword_140043210
0x1400058c7  jnz     short loc_140005901
0x1400058c9  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x1400058ce  mov     [rsp+38h+arg_0], 4
0x1400058d6  lea     r8, [rsp+38h+arg_18]; void *
0x1400058db  lea     rdx, aProcessid; "ProcessId"
0x1400058e2  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400058e7  test    eax, eax
0x1400058e9  jnz     short loc_140005901
0x1400058eb  mov     ecx, [rsp+38h+arg_18]; unsigned int
0x1400058ef  xor     edx, edx; unsigned __int8
0x1400058f1  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x1400058f6  test    rax, rax
0x1400058f9  jz      short loc_140005901
0x1400058fb  mov     [rsi], rax
0x1400058fe  mov     dil, 1
0x140005901  mov     al, dil
0x140005904  add     rsp, 20h
0x140005908  pop     rdi
0x140005909  pop     rsi
0x14000590a  pop     rbx
0x14000590b  retn
```
