# ContainerMapDeleteContainer

- ea: `0x18002ee0c`
- end: `0x18002eedb`
- name: `ContainerMapDeleteContainer`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016adc`
- `0x18002e180`

## callees

- `0x180009e82`
- `0x18000d9d0`
- `0x18002e3bc`
- `0x18002ee0c`
- `0x18002f1c8`

## pseudocode

```c
__int64 __fastcall ContainerMapDeleteContainer(__int64 a1, unsigned __int16 *a2, unsigned __int8 *a3)
{
  unsigned int v5; // eax
  void *v6; // rbx
  unsigned int v7; // edi
  unsigned __int8 v8; // di
  char *v9; // r9
  unsigned __int8 i; // cl
  __int64 v11; // rdx
  char v12; // al
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int8 v16[8]; // [rsp+30h] [rbp-38h] BYREF
  char *v17; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int8 v18; // [rsp+88h] [rbp+20h] BYREF

  v17 = 0;
  v16[0] = 0;
  v18 = 0;
  v5 = I_ContainerMapFind(a1, a2, v16, &v17, &v18);
  v6 = v17;
  v7 = v5;
  if ( !v5 )
  {
    v8 = v16[0];
    v9 = &v17[86 * v16[0]];
    if ( (v9[80] & 2) != 0 )
    {
      for ( i = 0; i < v18; ++i )
      {
        if ( i != v16[0] )
        {
          v11 = 86LL * i;
          v12 = v17[v11 + 80];
          if ( (v12 & 1) != 0 )
          {
            v17[v11 + 80] = v12 | 2;
            break;
          }
        }
      }
    }
    memset_0(v9, 0, 0x56u);
    v13 = 86 * (unsigned int)v18;
    *a3 = v8;
    v7 = CspWriteFile(a1, v13, "cmapfile", v14, v6, v13);
  }
  if ( v6 )
    CspFreeH(v6);
  return v7;
}

```

## disassembly

```asm
0x18002ee0c  mov     r11, rsp
0x18002ee0f  push    rbx
0x18002ee10  push    rsi
0x18002ee11  push    rdi
0x18002ee12  push    r14
0x18002ee14  sub     rsp, 48h
0x18002ee18  mov     r14, r8
0x18002ee1b  mov     qword ptr [r11-30h], 0
0x18002ee23  lea     rax, [r11+20h]
0x18002ee27  mov     [rsp+68h+var_38], 0
0x18002ee2c  lea     r8, [r11-38h]
0x18002ee30  mov     [r11-48h], rax
0x18002ee34  lea     r9, [r11-30h]
0x18002ee38  mov     byte ptr [r11+20h], 0
0x18002ee3d  mov     rsi, rcx
0x18002ee40  call    I_ContainerMapFind
0x18002ee45  mov     rbx, [rsp+68h+var_30]
0x18002ee4a  mov     edi, eax
0x18002ee4c  test    eax, eax
0x18002ee4e  jnz     short loc_18002EEC2
0x18002ee50  movzx   edi, [rsp+68h+var_38]
0x18002ee55  imul    r9, rdi, 56h ; 'V'
0x18002ee59  add     r9, rbx
0x18002ee5c  test    byte ptr [r9+50h], 2
0x18002ee61  jz      short loc_18002EE8C
0x18002ee63  xor     cl, cl
0x18002ee65  cmp     cl, [rsp+68h+arg_18]
0x18002ee6c  jnb     short loc_18002EE8C
0x18002ee6e  cmp     cl, dil
0x18002ee71  jz      short loc_18002EE82
0x18002ee73  movzx   eax, cl
0x18002ee76  imul    rdx, rax, 56h ; 'V'
0x18002ee7a  mov     al, [rdx+rbx+50h]
0x18002ee7e  test    al, 1
0x18002ee80  jnz     short loc_18002EE86
0x18002ee82  inc     cl
0x18002ee84  jmp     short loc_18002EE65
0x18002ee86  or      al, 2
0x18002ee88  mov     [rdx+rbx+50h], al
0x18002ee8c  xor     edx, edx; Val
0x18002ee8e  mov     rcx, r9; void *
0x18002ee91  lea     r8d, [rdx+56h]; Size
0x18002ee95  call    memset_0
0x18002ee9a  movzx   eax, [rsp+68h+arg_18]
0x18002eea2  lea     r8, aCmapfile; "cmapfile"
0x18002eea9  imul    edx, eax, 56h ; 'V'
0x18002eeac  mov     rcx, rsi
0x18002eeaf  mov     [r14], dil
0x18002eeb2  mov     [rsp+68h+var_40], edx
0x18002eeb6  mov     [rsp+68h+var_48], rbx
0x18002eebb  call    CspWriteFile
0x18002eec0  mov     edi, eax
0x18002eec2  test    rbx, rbx
0x18002eec5  jz      short loc_18002EECF
0x18002eec7  mov     rcx, rbx
0x18002eeca  call    CspFreeH
0x18002eecf  mov     eax, edi
0x18002eed1  add     rsp, 48h
0x18002eed5  pop     r14
0x18002eed7  pop     rdi
0x18002eed8  pop     rsi
0x18002eed9  pop     rbx
0x18002eeda  retn
```
