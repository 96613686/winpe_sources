# OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{CImpPerf::MakeAllValid(void),0}>::~OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{CImpPerf::MakeAllValid(void),0}>(void)

- ea: `0x18000fa80`
- end: `0x18000fa98`
- name: `??1?$OnDeleteObjIf0@VCImpPerf@@P81@EAAXXZ$H?MakeAllValid@1@QEAAXXZA@@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe68`
- `0x180016b65`

## callees

- `0x18000fa80`
- `0x180010f84`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{public: void CImpPerf::MakeAllValid(void),0}>::~OnDeleteObjIf0<CImpPerf,void (CImpPerf::*)(void),{public: void CImpPerf::MakeAllValid(void),0}>(
        __int64 a1)
{
  if ( !*(_BYTE *)(a1 + 8) )
    CImpPerf::MakeAllValid(*(CImpPerf **)a1);
}

```

## disassembly

```asm
0x18000fa80  sub     rsp, 28h
0x18000fa84  cmp     byte ptr [rcx+8], 0
0x18000fa88  jnz     short loc_18000FA93
0x18000fa8a  mov     rcx, [rcx]; this
0x18000fa8d  call    ?MakeAllValid@CImpPerf@@QEAAXXZ; CImpPerf::MakeAllValid(void)
0x18000fa92  nop
0x18000fa93  add     rsp, 28h
0x18000fa97  retn
```
