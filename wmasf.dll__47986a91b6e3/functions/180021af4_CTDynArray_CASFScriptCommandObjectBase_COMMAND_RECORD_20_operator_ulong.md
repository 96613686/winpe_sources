# CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](ulong)

- ea: `0x180021af4`
- end: `0x180021b22`
- name: `??A?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEBA?AUCOMMAND_RECORD@CASFScriptCommandObjectBase@@K@Z`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022050`
- `0x180022120`
- `0x180022370`

## callees

- `0x180021af4`
- `0x180021fa4`

## pseudocode

```c
__int64 __fastcall CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  __int64 v4; // r8

  v4 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( a3 < *(_DWORD *)(a1 + 552) )
    CTSparseBlock<unsigned long,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::GetValue(a1, a3);
  return v4;
}

```

## disassembly

```asm
0x180021af4  sub     rsp, 28h
0x180021af8  mov     eax, r8d
0x180021afb  xorps   xmm0, xmm0
0x180021afe  mov     r8, rdx
0x180021b01  xor     edx, edx
0x180021b03  movups  xmmword ptr [r8], xmm0
0x180021b07  mov     [r8+10h], rdx
0x180021b0b  cmp     eax, [rcx+228h]
0x180021b11  jnb     short loc_180021B1A
0x180021b13  mov     edx, eax
0x180021b15  call    ?GetValue@?$CTSparseBlock@KUCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@$0A@@@QEBAJKPEAUCOMMAND_RECORD@CASFScriptCommandObjectBase@@@Z; CTSparseBlock<ulong,CASFScriptCommandObjectBase::COMMAND_RECORD,20,0>::GetValue(ulong,CASFScriptCommandObjectBase::COMMAND_RECORD *)
0x180021b1a  mov     rax, r8
0x180021b1d  add     rsp, 28h
0x180021b21  retn
```
