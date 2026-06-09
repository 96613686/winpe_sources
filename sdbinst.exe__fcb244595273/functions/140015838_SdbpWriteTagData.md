# SdbpWriteTagData

- ea: `0x140015838`
- end: `0x14001592c`
- name: `SdbpWriteTagData`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140014500`
- `0x1400147d0`
- `0x140014d10`
- `0x140014d4c`
- `0x140014f94`
- `0x140014fe0`
- `0x140015060`
- `0x1400150b8`
- `0x140019410`
- `0x14001c730`

## callees

- `0x14001008c`
- `0x14001561c`
- `0x140015838`

## string_xrefs

- `0x1400158ff`: `Failed to write padding data 1 byte`
- `0x14001590c`: `SdbpWriteTagData`

## pseudocode

```c
__int64 __fastcall SdbpWriteTagData(__int64 a1, __int16 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rdx
  unsigned int v5; // edi
  char v9; // [rsp+50h] [rbp+8h] BYREF
  __int16 v10; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a2;
  v4 = *(unsigned int *)(a1 + 20);
  v5 = a4;
  v9 = -37;
  if ( !(unsigned int)SdbpWriteBufferedData(a1, v4, &v10, 2, 0) )
    return 0;
  if ( (v10 & 0xF000u) >= 0x7000 )
  {
    if ( !(unsigned int)SdbpWriteBufferedData(a1, *(unsigned int *)(a1 + 20), &v11, 4, 0) )
      return 0;
    v5 = v11;
  }
  if ( !a3 )
    return 1;
  if ( !(unsigned int)SdbpWriteBufferedData(a1, *(unsigned int *)(a1 + 20), a3, v5, 0) )
    return 0;
  if ( (v5 & 1) != 0 && !(unsigned int)SdbpWriteBufferedData(a1, *(unsigned int *)(a1 + 20), &v9, 1, 0) )
  {
    AslLogCallPrintf(1, "SdbpWriteTagData", 764, "Failed to write padding data 1 byte");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140015838  mov     rax, rsp
0x14001583b  mov     [rax+20h], r9d
0x14001583f  mov     [rax+10h], dx
0x140015843  push    rbx
0x140015844  push    rsi
0x140015845  push    rdi
0x140015846  sub     rsp, 30h
0x14001584a  mov     edx, [rcx+14h]
0x14001584d  mov     edi, r9d
0x140015850  mov     rsi, r8
0x140015853  mov     byte ptr [rax+8], 0DBh
0x140015857  mov     r9d, 2
0x14001585d  mov     dword ptr [rax-28h], 0
0x140015864  lea     r8, [rax+10h]
0x140015868  mov     rbx, rcx
0x14001586b  call    SdbpWriteBufferedData
0x140015870  test    eax, eax
0x140015872  jz      loc_14001591B
0x140015878  movzx   eax, [rsp+48h+arg_8]
0x14001587d  mov     ecx, 0F000h
0x140015882  and     ax, cx
0x140015885  mov     ecx, 7000h
0x14001588a  cmp     ax, cx
0x14001588d  jb      short loc_1400158B5
0x14001588f  mov     edx, [rbx+14h]
0x140015892  lea     r8, [rsp+48h+arg_18]
0x140015897  mov     r9d, 4
0x14001589d  mov     [rsp+48h+var_28], 0
0x1400158a5  mov     rcx, rbx
0x1400158a8  call    SdbpWriteBufferedData
0x1400158ad  test    eax, eax
0x1400158af  jz      short loc_14001591B
0x1400158b1  mov     edi, [rsp+48h+arg_18]
0x1400158b5  test    rsi, rsi
0x1400158b8  jz      short loc_140015925
0x1400158ba  mov     edx, [rbx+14h]
0x1400158bd  mov     r9d, edi
0x1400158c0  mov     r8, rsi
0x1400158c3  mov     [rsp+48h+var_28], 0
0x1400158cb  mov     rcx, rbx
0x1400158ce  call    SdbpWriteBufferedData
0x1400158d3  test    eax, eax
0x1400158d5  jz      short loc_14001591B
0x1400158d7  test    dil, 1
0x1400158db  jz      short loc_140015925
0x1400158dd  mov     edx, [rbx+14h]
0x1400158e0  lea     r8, [rsp+48h+arg_0]
0x1400158e5  mov     r9d, 1
0x1400158eb  mov     [rsp+48h+var_28], 0
0x1400158f3  mov     rcx, rbx
0x1400158f6  call    SdbpWriteBufferedData
0x1400158fb  test    eax, eax
0x1400158fd  jnz     short loc_140015925
0x1400158ff  lea     r9, aFailedToWriteP; "Failed to write padding data 1 byte"
0x140015906  mov     r8d, 2FCh
0x14001590c  lea     rdx, aSdbpwritetagda; "SdbpWriteTagData"
0x140015913  lea     ecx, [rax+1]
0x140015916  call    AslLogCallPrintf
0x14001591b  xor     eax, eax
0x14001591d  add     rsp, 30h
0x140015921  pop     rdi
0x140015922  pop     rsi
0x140015923  pop     rbx
0x140015924  retn
0x140015925  mov     eax, 1
0x14001592a  jmp     short loc_14001591D
```
