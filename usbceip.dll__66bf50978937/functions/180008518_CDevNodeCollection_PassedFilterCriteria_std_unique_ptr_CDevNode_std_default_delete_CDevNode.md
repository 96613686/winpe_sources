# CDevNodeCollection::PassedFilterCriteria(std::unique_ptr<CDevNode,std::default_delete<CDevNode>> &)

- ea: `0x180008518`
- end: `0x1800085bc`
- name: `?PassedFilterCriteria@CDevNodeCollection@@AEAAEAEAV?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@@Z`
- size: `164`
- prototype: `bool __fastcall(__int64, CDevNode **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008290`

## callees

- `0x180008518`
- `0x18000ad38`
- `0x18000ad94`

## pseudocode

```c
bool __fastcall CDevNodeCollection::PassedFilterCriteria(__int64 a1, CDevNode **a2)
{
  char v4; // bl
  CDevNode *v5; // rcx
  bool v6; // dl
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF

  LOBYTE(v11) = 0;
  CDevNode::GetProperty(*a2, &DEVPKEY_Device_IsPresent, (bool *)&v11);
  v4 = v11;
  if ( (_BYTE)v11 )
  {
    v5 = *a2;
    v11 = 0;
    CDevNode::GetProperty(v5, &DEVPKEY_Device_ProblemCode, &v11);
    v6 = v11 == 0;
  }
  else
  {
    v6 = 0;
  }
  v7 = *(_DWORD *)(a1 + 8);
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 1 )
          return v4 == 0;
        return 1;
      }
      if ( v4 && !v6 )
        return 1;
    }
    else if ( v4 && v6 )
    {
      return 1;
    }
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180008518  mov     rax, rsp
0x18000851b  mov     [rax+10h], rbx
0x18000851f  mov     [rax+18h], rsi
0x180008523  push    rdi
0x180008524  sub     rsp, 20h
0x180008528  mov     rsi, rdx
0x18000852b  mov     byte ptr [rax+8], 0
0x18000852f  mov     rdi, rcx
0x180008532  lea     r8, [rax+8]; unsigned __int8 *
0x180008536  lea     rdx, DEVPKEY_Device_IsPresent; struct _DEVPROPKEY *
0x18000853d  mov     rcx, [rsi]; this
0x180008540  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAE@Z; CDevNode::GetProperty(_DEVPROPKEY const &,uchar &)
0x180008545  mov     bl, byte ptr [rsp+28h+arg_0]
0x180008549  test    bl, bl
0x18000854b  jz      short loc_180008573
0x18000854d  mov     rcx, [rsi]; this
0x180008550  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x180008555  lea     rdx, DEVPKEY_Device_ProblemCode; struct _DEVPROPKEY *
0x18000855c  mov     [rsp+28h+arg_0], 0
0x180008564  call    ?GetProperty@CDevNode@@QEAAXAEBU_DEVPROPKEY@@AEAK@Z; CDevNode::GetProperty(_DEVPROPKEY const &,ulong &)
0x180008569  cmp     [rsp+28h+arg_0], 0
0x18000856e  setz    dl
0x180008571  jmp     short loc_180008575
0x180008573  xor     dl, dl
0x180008575  mov     ecx, [rdi+8]
0x180008578  test    ecx, ecx
0x18000857a  jz      short loc_1800085AA
0x18000857c  sub     ecx, 1
0x18000857f  jz      short loc_1800085A0
0x180008581  sub     ecx, 1
0x180008584  jz      short loc_180008596
0x180008586  cmp     ecx, 1
0x180008589  jz      short loc_18000858F
0x18000858b  mov     bl, 1
0x18000858d  jmp     short loc_1800085AA
0x18000858f  test    bl, bl
0x180008591  setz    bl
0x180008594  jmp     short loc_1800085AA
0x180008596  test    bl, bl
0x180008598  jz      short loc_1800085A8
0x18000859a  test    dl, dl
0x18000859c  jnz     short loc_1800085A8
0x18000859e  jmp     short loc_18000858B
0x1800085a0  test    bl, bl
0x1800085a2  jz      short loc_1800085A8
0x1800085a4  test    dl, dl
0x1800085a6  jnz     short loc_18000858B
0x1800085a8  xor     bl, bl
0x1800085aa  mov     rsi, [rsp+28h+arg_10]
0x1800085af  mov     al, bl
0x1800085b1  mov     rbx, [rsp+28h+arg_8]
0x1800085b6  add     rsp, 20h
0x1800085ba  pop     rdi
0x1800085bb  retn
```
