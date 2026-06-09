# CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD *,20,1>::CreateBlock(CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD *,20,1> * *)

- ea: `0x180008ad0`
- end: `0x180008b56`
- name: `?CreateBlock@?$CTSparseBlock@KPEAU_STREAM_NAME_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@MEAAJPEAPEAV1@@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011a0`
- `0x180001f1c`
- `0x180008ad0`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD *,20,1>::CreateBlock(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  __int64 result; // rax

  v3 = operator new(0xD8u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable';
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
0x180008ad0  mov     [rsp+arg_0], rbx
0x180008ad5  push    rdi
0x180008ad6  sub     rsp, 20h
0x180008ada  mov     ecx, 0D8h; Size
0x180008adf  mov     rdi, rdx
0x180008ae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008ae7  mov     rbx, rax
0x180008aea  test    rax, rax
0x180008aed  jz      short loc_180008B39
0x180008aef  mov     qword ptr [rbx+8], 0
0x180008af7  lea     rax, ??_7?$CTPtrArray@U_STREAM_NAME_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@6B@; const CTPtrArray<CASFStreamPropertiesObjectEx::_STREAM_NAME_RECORD,20>::`vftable'
0x180008afe  mov     [rbx], rax
0x180008b01  lea     rcx, [rbx+20h]; void *
0x180008b05  xor     eax, eax
0x180008b07  xor     edx, edx; Val
0x180008b09  mov     [rbx+18h], ax
0x180008b0d  mov     r8d, 0A0h; Size
0x180008b13  mov     [rbx+1Ah], al
0x180008b16  call    memset_0
0x180008b1b  mov     qword ptr [rbx+0C0h], 0
0x180008b26  mov     [rbx+0C8h], rbx
0x180008b2d  mov     dword ptr [rbx+0D0h], 0
0x180008b37  jmp     short loc_180008B3B
0x180008b39  xor     ebx, ebx
0x180008b3b  xor     eax, eax
0x180008b3d  mov     [rdi], rbx
0x180008b40  test    rbx, rbx
0x180008b43  mov     ecx, 8007000Eh
0x180008b48  mov     rbx, [rsp+28h+arg_0]
0x180008b4d  cmovz   eax, ecx
0x180008b50  add     rsp, 20h
0x180008b54  pop     rdi
0x180008b55  retn
```
