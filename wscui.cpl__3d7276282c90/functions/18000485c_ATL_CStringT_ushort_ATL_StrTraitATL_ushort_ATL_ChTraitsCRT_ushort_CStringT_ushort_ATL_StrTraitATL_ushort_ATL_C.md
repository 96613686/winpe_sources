# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)

- ea: `0x18000485c`
- end: `0x1800048b2`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z`
- size: `86`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800052cc`
- `0x1800058b0`
- `0x180006ad0`
- `0x180006fec`
- `0x180007120`
- `0x180009300`

## callees

- `0x1800047f8`
- `0x18000485c`
- `0x180004904`
- `0x180004c48`
- `0x180004ce4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char **__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        char **a1,
        _BYTE *a2)
{
  unsigned int v4; // eax

  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a1, &ATL::g_strmgr);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           a1,
                           a2) )
  {
    v4 = ATL::CSimpleStringT<unsigned short,0>::StringLength(a2);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2, v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18000485c  mov     [rsp+arg_8], rbx
0x180004861  mov     [rsp+arg_0], rcx
0x180004866  push    rdi
0x180004867  sub     rsp, 20h
0x18000486b  mov     rdi, rdx
0x18000486e  mov     rbx, rcx
0x180004871  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004878  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18000487d  nop
0x18000487e  mov     rdx, rdi
0x180004881  mov     rcx, rbx
0x180004884  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180004889  test    al, al
0x18000488b  jnz     short loc_1800048A4
0x18000488d  mov     rcx, rdi
0x180004890  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180004895  mov     r8d, eax
0x180004898  mov     rdx, rdi
0x18000489b  mov     rcx, rbx
0x18000489e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800048a3  nop
0x1800048a4  mov     rax, rbx
0x1800048a7  mov     rbx, [rsp+28h+arg_8]
0x1800048ac  add     rsp, 20h
0x1800048b0  pop     rdi
0x1800048b1  retn
```
