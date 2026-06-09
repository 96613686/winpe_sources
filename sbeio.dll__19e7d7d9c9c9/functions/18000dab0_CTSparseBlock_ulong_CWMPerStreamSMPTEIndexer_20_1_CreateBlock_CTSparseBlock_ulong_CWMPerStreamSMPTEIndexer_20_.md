# CTSparseBlock<ulong,CWMPerStreamSMPTEIndexer *,20,1>::CreateBlock(CTSparseBlock<ulong,CWMPerStreamSMPTEIndexer *,20,1> * *)

- ea: `0x18000dab0`
- end: `0x18000db36`
- name: `?CreateBlock@?$CTSparseBlock@KPEAVCWMPerStreamSMPTEIndexer@@$0BE@$00@@MEAAJPEAPEAV1@@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011a0`
- `0x180001f1c`
- `0x18000dab0`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CWMPerStreamSMPTEIndexer *,20,1>::CreateBlock(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 result; // rax

  v3 = operator new(0xD8u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTSparseBlock<unsigned long,unsigned char *,20,1>::`vftable';
    *((_WORD *)v3 + 12) = 0;
    *((_BYTE *)v3 + 26) = 0;
    memset_0(v3 + 4, 0, 0xA0u);
    v4[24] = 0;
    v4[25] = v4;
    *((_DWORD *)v4 + 52) = 0;
  }
  else
  {
    v4 = 0;
  }
  result = 0;
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18000dab0  mov     [rsp+arg_0], rbx
0x18000dab5  push    rdi
0x18000dab6  sub     rsp, 20h
0x18000daba  mov     ecx, 0D8h; Size
0x18000dabf  mov     rdi, rdx
0x18000dac2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dac7  mov     rbx, rax
0x18000daca  test    rax, rax
0x18000dacd  jz      short loc_18000DB19
0x18000dacf  mov     qword ptr [rbx+8], 0
0x18000dad7  lea     rax, ??_7?$CTSparseBlock@KPEAE$0BE@$00@@6B@; const CTSparseBlock<ulong,uchar *,20,1>::`vftable'
0x18000dade  mov     [rbx], rax
0x18000dae1  lea     rcx, [rbx+20h]; void *
0x18000dae5  xor     eax, eax
0x18000dae7  xor     edx, edx; Val
0x18000dae9  mov     [rbx+18h], ax
0x18000daed  mov     r8d, 0A0h; Size
0x18000daf3  mov     [rbx+1Ah], al
0x18000daf6  call    memset_0
0x18000dafb  mov     qword ptr [rbx+0C0h], 0
0x18000db06  mov     [rbx+0C8h], rbx
0x18000db0d  mov     dword ptr [rbx+0D0h], 0
0x18000db17  jmp     short loc_18000DB1B
0x18000db19  xor     ebx, ebx
0x18000db1b  xor     eax, eax
0x18000db1d  mov     [rdi], rbx
0x18000db20  test    rbx, rbx
0x18000db23  mov     ecx, 8007000Eh
0x18000db28  mov     rbx, [rsp+28h+arg_0]
0x18000db2d  cmovz   eax, ecx
0x18000db30  add     rsp, 20h
0x18000db34  pop     rdi
0x18000db35  retn
```
