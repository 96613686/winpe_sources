# _SetGestureProgress(DirectUI::Element *,int)

- ea: `0x1800158ec`
- end: `0x1800159cb`
- name: `?_SetGestureProgress@@YAXPEAVElement@DirectUI@@H@Z`
- size: `223`
- prototype: `void __fastcall(struct DirectUI::Element *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015480`
- `0x180015630`

## callees

- `0x180010d04`
- `0x1800158ec`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180015994`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180015994`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180015947`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180015947`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180015988`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180015988`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180015925`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180015925`

## pseudocode

```c
void __fastcall _SetGestureProgress(struct DirectUI::Element *a1, int a2)
{
  char v2; // di
  __int64 v5; // rsi
  __int64 Children; // r15
  int v7; // ecx
  bool v8; // dl
  __int64 v9; // rbx
  DirectUI::Element *v10; // rbx
  int v11; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+24h] [rbp-34h]
  int v13; // [rsp+2Ch] [rbp-2Ch]
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  v11 = 16;
  v12 = 0;
  v13 = 0;
  if ( SystemParametersInfoW(0x42u, 0x10u, &v11, 0) )
    v2 = v12 & 1;
  v14 = 0;
  v5 = 0;
  Children = DirectUI::Element::GetChildren(a1, &v14);
  v7 = *(_DWORD *)Children;
  if ( (*(_DWORD *)Children & 0xFFFFFFF) != 0 )
  {
    do
    {
      v8 = !v2 || (_DWORD)v5 == a2;
      if ( (v7 & 0x10000000) != 0 )
        v9 = *(_QWORD *)(Children + 8);
      else
        v9 = Children + 8;
      v10 = *(DirectUI::Element **)(v9 + 8 * v5);
      DirectUI::Element::SetVisible(v10, v8);
      DirectUI::Element::SetSelected(v10, (_DWORD)v5 == a2);
      v7 = *(_DWORD *)Children;
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (int)v5 < (*(_DWORD *)Children & 0xFFFFFFF) );
  }
  CValuePtr::Release((CValuePtr *)&v14);
}

```

## disassembly

```asm
0x1800158ec  mov     r11, rsp
0x1800158ef  mov     [r11+8], rbx
0x1800158f3  mov     [r11+10h], rbp
0x1800158f7  push    rsi
0x1800158f8  push    rdi
0x1800158f9  push    r12
0x1800158fb  push    r14
0x1800158fd  push    r15
0x1800158ff  sub     rsp, 30h
0x180015903  xor     eax, eax
0x180015905  lea     r8, [r11-38h]; pvParam
0x180015909  xor     edi, edi
0x18001590b  mov     ebp, edx
0x18001590d  mov     rbx, rcx
0x180015910  xor     r9d, r9d; fWinIni
0x180015913  lea     edx, [rdi+10h]; uiParam
0x180015916  mov     [rsp+58h+var_38], edx
0x18001591a  lea     ecx, [rdi+42h]; uiAction
0x18001591d  mov     [r11-34h], rax
0x180015921  mov     [rsp+58h+var_2C], eax
0x180015925  call    cs:__imp_SystemParametersInfoW
0x18001592b  test    eax, eax
0x18001592d  jz      short loc_180015936
0x18001592f  mov     edi, dword ptr [rsp+58h+var_34]
0x180015933  and     edi, 1
0x180015936  lea     rdx, [rsp+58h+arg_10]
0x18001593b  mov     [rsp+58h+arg_10], 0
0x180015944  mov     rcx, rbx
0x180015947  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18001594d  xor     esi, esi
0x18001594f  mov     r15, rax
0x180015952  mov     ecx, [rax]
0x180015954  test    ecx, 0FFFFFFFh
0x18001595a  jbe     short loc_1800159AA
0x18001595c  cmp     esi, ebp
0x18001595e  setz    r12b
0x180015962  test    dil, dil
0x180015965  jz      short loc_18001596F
0x180015967  cmp     esi, ebp
0x180015969  jz      short loc_18001596F
0x18001596b  xor     dl, dl
0x18001596d  jmp     short loc_180015971
0x18001596f  mov     dl, 1
0x180015971  bt      ecx, 1Ch
0x180015975  jnb     short loc_18001597D
0x180015977  mov     rbx, [r15+8]
0x18001597b  jmp     short loc_180015981
0x18001597d  lea     rbx, [r15+8]
0x180015981  mov     rbx, [rbx+rsi*8]
0x180015985  mov     rcx, rbx
0x180015988  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18001598e  mov     dl, r12b
0x180015991  mov     rcx, rbx
0x180015994  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001599a  mov     ecx, [r15]
0x18001599d  inc     esi
0x18001599f  mov     eax, ecx
0x1800159a1  and     eax, 0FFFFFFFh
0x1800159a6  cmp     esi, eax
0x1800159a8  jl      short loc_18001595C
0x1800159aa  lea     rcx, [rsp+58h+arg_10]; this
0x1800159af  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800159b4  mov     rbx, [rsp+58h+arg_0]
0x1800159b9  mov     rbp, [rsp+58h+arg_8]
0x1800159be  add     rsp, 30h
0x1800159c2  pop     r15
0x1800159c4  pop     r14
0x1800159c6  pop     r12
0x1800159c8  pop     rdi
0x1800159c9  pop     rsi
0x1800159ca  retn
```
