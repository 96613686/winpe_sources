# _dynamic_atexit_destructor_for___AtlModule__

- ea: `0x18000b050`
- end: `0x18000b0c7`
- name: `_dynamic_atexit_destructor_for___AtlModule__`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001a60`
- `0x180001bf0`
- `0x180004370`
- `0x18000b050`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b0a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b0a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall dynamic_atexit_destructor_for___AtlModule__(ATL::CAtlComModule *a1)
{
  ATL::CAtlComModule::ExecuteObjectMain(a1, 0);
  if ( qword_180014A68 )
  {
    if ( qword_180014A70 )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&qword_180014A68);
      qword_180014A70 = 0;
    }
    if ( qword_180014AA0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180014AA0 + 16LL))(qword_180014AA0);
    DeleteCriticalSection(&CriticalSection);
    qword_180014A68 = 0;
  }
}

```

## disassembly

```asm
0x18000b050  sub     rsp, 28h
0x18000b054  xor     edx, edx; bool
0x18000b056  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18000b05b  nop
0x18000b05c  cmp     dword ptr cs:qword_180014A68, 0
0x18000b063  jz      short loc_18000B0B5
0x18000b065  cmp     cs:qword_180014A70, 0
0x18000b06d  jz      short loc_18000B086
0x18000b06f  lea     rcx, qword_180014A68; struct ATL::_ATL_MODULE70 *
0x18000b076  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18000b07b  mov     cs:qword_180014A70, 0
0x18000b086  mov     rcx, cs:qword_180014AA0
0x18000b08d  test    rcx, rcx
0x18000b090  jz      short loc_18000B09E
0x18000b092  mov     rax, [rcx]
0x18000b095  mov     rax, [rax+10h]
0x18000b099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b09e  lea     rcx, CriticalSection; lpCriticalSection
0x18000b0a5  call    cs:__imp_DeleteCriticalSection
0x18000b0ab  mov     dword ptr cs:qword_180014A68, 0
0x18000b0b5  lea     rcx, qword_180014A68
0x18000b0bc  call    _guard_check_icall_nop
0x18000b0c1  nop
0x18000b0c2  add     rsp, 28h
0x18000b0c6  retn
```
