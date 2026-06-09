# GetApplicationParameters(ulong,SecurityType)

- ea: `0x180006fec`
- end: `0x180007119`
- name: `?GetApplicationParameters@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KW4SecurityType@@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007938`

## callees

- `0x18000485c`
- `0x180004c48`
- `0x180004e9c`
- `0x180006fec`
- `0x18000811c`
- `0x1800081c4`
- `0x1800089e4`

## string_xrefs

- `0x1800070b8`: `/enable /update`
- `0x180007052`: `/update`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char **__fastcall GetApplicationParameters(char **a1, unsigned int a2, int a3)
{
  unsigned int v6; // r8d
  wchar_t *v7; // rdx
  unsigned int v8; // edi
  char **v9; // rcx
  const wchar_t *v10; // rdx

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    &unk_18000F684);
  if ( (unsigned int)ExtractProductState(a2) == 0x4000 || (unsigned int)ExtractProductNotification(a2) )
  {
    v6 = 6;
    v7 = L"/renew";
    goto LABEL_14;
  }
  if ( (unsigned int)ExtractProductState(a2) == 4096 )
  {
    v6 = 7;
    v7 = L"/update";
LABEL_14:
    v9 = a1;
    goto LABEL_15;
  }
  v8 = a2 & 0x10;
  if ( (v8 & 0xF0) != v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, 240, v8, 240);
    v8 &= 0xF0u;
  }
  v9 = a1;
  if ( v8 )
  {
    v6 = 15;
    v7 = L"/enable /update";
  }
  else
  {
    v6 = 7;
    v7 = L"/enable";
  }
LABEL_15:
  ATL::CSimpleStringT<unsigned short,0>::SetString(v9, v7, v6);
  switch ( a3 )
  {
    case 1:
      v10 = L" /fw";
LABEL_21:
      ATL::CSimpleStringT<unsigned short,0>::Append(a1, v10, 4);
      return a1;
    case 3:
      v10 = L" /av";
      goto LABEL_21;
    case 4:
      v10 = L" /as";
      goto LABEL_21;
  }
  return a1;
}

```

## disassembly

```asm
0x180006fec  mov     [rsp+arg_0], rcx
0x180006ff1  push    rbx
0x180006ff2  push    rbp
0x180006ff3  push    rsi
0x180006ff4  push    rdi
0x180006ff5  sub     rsp, 48h
0x180006ff9  mov     ebp, r8d
0x180006ffc  mov     edi, edx
0x180006ffe  mov     rbx, rcx
0x180007001  mov     [rsp+68h+var_38], 0
0x180007009  lea     rdx, byte_18000F684
0x180007010  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007015  mov     [rsp+68h+var_38], 1
0x18000701d  mov     ecx, edi
0x18000701f  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x180007024  cmp     eax, 4000h
0x180007029  jz      loc_1800070C1
0x18000702f  mov     ecx, edi
0x180007031  call    ?ExtractProductNotification@@YA?AW4ProductNotification@@K@Z; ExtractProductNotification(ulong)
0x180007036  test    eax, eax
0x180007038  jnz     loc_1800070C1
0x18000703e  mov     ecx, edi
0x180007040  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x180007045  cmp     eax, 1000h
0x18000704a  jnz     short loc_18000705B
0x18000704c  mov     r8d, 7
0x180007052  lea     rdx, aUpdate; "/update"
0x180007059  jmp     short loc_1800070CE
0x18000705b  and     edi, 10h
0x18000705e  mov     esi, edi
0x180007060  mov     r8d, 0F0h
0x180007066  and     esi, r8d
0x180007069  cmp     esi, edi
0x18000706b  jz      short loc_18000709E
0x18000706d  lea     rax, WPP_GLOBAL_Control
0x180007074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000707b  cmp     rcx, rax
0x18000707e  jz      short loc_18000709C
0x180007080  test    byte ptr [rcx+1Ch], 1
0x180007084  jz      short loc_18000709C
0x180007086  mov     edx, 0Ah
0x18000708b  mov     [rsp+68h+var_48], r8d
0x180007090  mov     r9d, edi
0x180007093  mov     rcx, [rcx+10h]
0x180007097  call    WPP_SF_DD
0x18000709c  mov     edi, esi
0x18000709e  mov     rcx, rbx
0x1800070a1  test    edi, edi
0x1800070a3  jnz     short loc_1800070B2
0x1800070a5  lea     r8d, [rdi+7]
0x1800070a9  lea     rdx, aEnable; "/enable"
0x1800070b0  jmp     short loc_1800070D1
0x1800070b2  mov     r8d, 0Fh
0x1800070b8  lea     rdx, aEnableUpdate; "/enable /update"
0x1800070bf  jmp     short loc_1800070D1
0x1800070c1  mov     r8d, 6
0x1800070c7  lea     rdx, aRenew; "/renew"
0x1800070ce  mov     rcx, rbx
0x1800070d1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800070d6  cmp     ebp, 1
0x1800070d9  jnz     short loc_1800070E4
0x1800070db  lea     rdx, aFw; " /fw"
0x1800070e2  jmp     short loc_1800070FE
0x1800070e4  cmp     ebp, 3
0x1800070e7  jnz     short loc_1800070F2
0x1800070e9  lea     rdx, aAv; " /av"
0x1800070f0  jmp     short loc_1800070FE
0x1800070f2  cmp     ebp, 4
0x1800070f5  jnz     short loc_18000710C
0x1800070f7  lea     rdx, aAs; " /as"
0x1800070fe  mov     r8d, 4
0x180007104  mov     rcx, rbx
0x180007107  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18000710c  mov     rax, rbx
0x18000710f  add     rsp, 48h
0x180007113  pop     rdi
0x180007114  pop     rsi
0x180007115  pop     rbp
0x180007116  pop     rbx
0x180007117  retn
```
