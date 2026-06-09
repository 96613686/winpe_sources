# CTSparseBlock<ulong,CASFStreamPrioritizationObject::PRIORITIZATION_REC,20,0>::CreateBlock(CTSparseBlock<ulong,CASFStreamPrioritizationObject::PRIORITIZATION_REC,20,0> * *)

- ea: `0x18001a930`
- end: `0x18001a98d`
- name: `?CreateBlock@?$CTSparseBlock@KUPRIORITIZATION_REC@CASFStreamPrioritizationObject@@$0BE@$0A@@@MEAAJPEAPEAV1@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18001a930`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPrioritizationObject::PRIORITIZATION_REC,20,0>::CreateBlock(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax

  v3 = operator new(0x80u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTDynArray<CASFStreamPrioritizationObject::PRIORITIZATION_REC,20>::`vftable';
    *((_WORD *)v3 + 10) = 0;
    *((_BYTE *)v3 + 22) = 0;
    v3[13] = 0;
    v3[14] = v3;
    *((_DWORD *)v3 + 30) = 0;
  }
  else
  {
    v4 = 0;
  }
  *a2 = v4;
  result = 0;
  if ( !v4 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18001a930  push    rbx
0x18001a932  sub     rsp, 20h
0x18001a936  mov     ecx, 80h; Size
0x18001a93b  mov     rbx, rdx
0x18001a93e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a943  xor     r8d, r8d
0x18001a946  mov     rcx, rax
0x18001a949  test    rax, rax
0x18001a94c  jz      short loc_18001A973
0x18001a94e  lea     rax, ??_7?$CTDynArray@UPRIORITIZATION_REC@CASFStreamPrioritizationObject@@$0BE@@@6B@; const CTDynArray<CASFStreamPrioritizationObject::PRIORITIZATION_REC,20>::`vftable'
0x18001a955  mov     [rcx+8], r8
0x18001a959  mov     [rcx], rax
0x18001a95c  xor     eax, eax
0x18001a95e  mov     [rcx+14h], ax
0x18001a962  mov     [rcx+16h], al
0x18001a965  mov     [rcx+68h], r8
0x18001a969  mov     [rcx+70h], rcx
0x18001a96d  mov     [rcx+78h], r8d
0x18001a971  jmp     short loc_18001A976
0x18001a973  mov     rcx, r8
0x18001a976  test    rcx, rcx
0x18001a979  mov     [rbx], rcx
0x18001a97c  mov     eax, r8d
0x18001a97f  mov     edx, 8007000Eh
0x18001a984  cmovz   eax, edx
0x18001a987  add     rsp, 20h
0x18001a98b  pop     rbx
0x18001a98c  retn
```
