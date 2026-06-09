# GetDefenderParameters(SecurityAction)

- ea: `0x180007120`
- end: `0x1800071ad`
- name: `?GetDefenderParameters@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4SecurityAction@@@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007b08`

## callees

- `0x18000485c`
- `0x180004c48`
- `0x180004e9c`
- `0x180007120`

## string_xrefs

- `0x18000717a`: `/enableandupdate`
- `0x18000716b`: `/update`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char **__fastcall GetDefenderParameters(char **a1, int a2)
{
  unsigned int v4; // r8d
  wchar_t *v5; // rdx

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    &unk_18000F684);
  if ( a2 == 110 )
  {
    v4 = 7;
    v5 = L"/enable";
  }
  else if ( a2 == 111 )
  {
    v4 = 7;
    v5 = L"/update";
  }
  else
  {
    v4 = 16;
    v5 = L"/enableandupdate";
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v5, v4);
  ATL::CSimpleStringT<unsigned short,0>::Append(a1, L" /as", 4);
  return a1;
}

```

## disassembly

```asm
0x180007120  mov     [rsp+arg_8], rbx
0x180007125  mov     [rsp+arg_0], rcx
0x18000712a  push    rdi
0x18000712b  sub     rsp, 30h
0x18000712f  mov     edi, edx
0x180007131  mov     rbx, rcx
0x180007134  mov     [rsp+38h+var_18], 0
0x18000713c  lea     rdx, byte_18000F684
0x180007143  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007148  mov     [rsp+38h+var_18], 1
0x180007150  cmp     edi, 6Eh ; 'n'
0x180007153  jnz     short loc_180007162
0x180007155  lea     r8d, [rdi-67h]
0x180007159  lea     rdx, aEnable; "/enable"
0x180007160  jmp     short loc_180007181
0x180007162  cmp     edi, 6Fh ; 'o'
0x180007165  jnz     short loc_180007174
0x180007167  lea     r8d, [rdi-68h]
0x18000716b  lea     rdx, aUpdate; "/update"
0x180007172  jmp     short loc_180007181
0x180007174  mov     r8d, 10h
0x18000717a  lea     rdx, aEnableandupdat; "/enableandupdate"
0x180007181  mov     rcx, rbx
0x180007184  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180007189  mov     r8d, 4
0x18000718f  lea     rdx, aAs; " /as"
0x180007196  mov     rcx, rbx
0x180007199  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000719e  mov     rax, rbx
0x1800071a1  mov     rbx, [rsp+38h+arg_8]
0x1800071a6  add     rsp, 30h
0x1800071aa  pop     rdi
0x1800071ab  retn
```
