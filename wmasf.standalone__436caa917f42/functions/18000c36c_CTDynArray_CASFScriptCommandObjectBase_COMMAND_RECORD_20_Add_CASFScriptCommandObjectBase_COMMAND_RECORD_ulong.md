# CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(CASFScriptCommandObjectBase::COMMAND_RECORD,ulong *)

- ea: `0x18000c36c`
- end: `0x18000c3ad`
- name: `?Add@?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEAAHUCOMMAND_RECORD@CASFScriptCommandObjectBase@@PEAK@Z`
- size: `65`
- prototype: `_BOOL8 __fastcall(__int64, __int128 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c5d0`
- `0x180021b30`

## callees

- `0x18000c36c`
- `0x18000cb20`

## pseudocode

```c
_BOOL8 __fastcall CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::Add(__int64 a1, __int128 *a2)
{
  __int128 v2; // xmm0
  __int64 v3; // xmm1_8
  __int64 v5; // rdx
  int v6; // eax
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]

  v2 = *a2;
  v3 = *((_QWORD *)a2 + 2);
  v5 = *(unsigned int *)(a1 + 552);
  v8 = v2;
  v9 = v3;
  v6 = CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(a1, v5, &v8);
  if ( v6 >= 0 )
    ++*(_DWORD *)(a1 + 552);
  return v6 >= 0;
}

```

## disassembly

```asm
0x18000c36c  push    rbx
0x18000c36e  sub     rsp, 40h
0x18000c372  movaps  xmm0, xmmword ptr [rdx]
0x18000c375  lea     r8, [rsp+48h+var_28]
0x18000c37a  movsd   xmm1, qword ptr [rdx+10h]
0x18000c37f  mov     rbx, rcx
0x18000c382  mov     edx, [rcx+228h]
0x18000c388  movaps  [rsp+48h+var_28], xmm0
0x18000c38d  movsd   [rsp+48h+var_18], xmm1
0x18000c393  call    ?SetValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEAAJKUCOMMAND_RECORD@CASFScriptCommandObjectBase@@@Z; CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::SetValue(ulong,CASFScriptCommandObjectBase::COMMAND_RECORD)
0x18000c398  test    eax, eax
0x18000c39a  js      short loc_18000C3A2
0x18000c39c  inc     dword ptr [rbx+228h]
0x18000c3a2  not     eax
0x18000c3a4  shr     eax, 1Fh
0x18000c3a7  add     rsp, 40h
0x18000c3ab  pop     rbx
0x18000c3ac  retn
```
