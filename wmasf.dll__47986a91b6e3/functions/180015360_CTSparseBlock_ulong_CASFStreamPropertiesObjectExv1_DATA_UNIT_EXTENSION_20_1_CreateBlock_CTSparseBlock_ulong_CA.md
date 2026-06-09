# CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::CreateBlock(CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1> * *)

- ea: `0x180015360`
- end: `0x1800153e6`
- name: `?CreateBlock@?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@MEAAJPEAPEAV1@@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001174`
- `0x180001ee8`
- `0x180015360`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::CreateBlock(
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
    *v3 = &CTPtrArray<CASFStreamPropertiesObjectExv1::_STREAM_NAME,20>::`vftable';
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
0x180015360  mov     [rsp+arg_0], rbx
0x180015365  push    rdi
0x180015366  sub     rsp, 20h
0x18001536a  mov     ecx, 0D8h; Size
0x18001536f  mov     rdi, rdx
0x180015372  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015377  mov     rbx, rax
0x18001537a  test    rax, rax
0x18001537d  jz      short loc_1800153C9
0x18001537f  mov     qword ptr [rbx+8], 0
0x180015387  lea     rax, ??_7?$CTPtrArray@U_STREAM_NAME@CASFStreamPropertiesObjectExv1@@$0BE@@@6B@; const CTPtrArray<CASFStreamPropertiesObjectExv1::_STREAM_NAME,20>::`vftable'
0x18001538e  mov     [rbx], rax
0x180015391  lea     rcx, [rbx+20h]; void *
0x180015395  xor     eax, eax
0x180015397  xor     edx, edx; Val
0x180015399  mov     [rbx+18h], ax
0x18001539d  mov     r8d, 0A0h; Size
0x1800153a3  mov     [rbx+1Ah], al
0x1800153a6  call    memset_0
0x1800153ab  mov     qword ptr [rbx+0C0h], 0
0x1800153b6  mov     [rbx+0C8h], rbx
0x1800153bd  mov     dword ptr [rbx+0D0h], 0
0x1800153c7  jmp     short loc_1800153CB
0x1800153c9  xor     ebx, ebx
0x1800153cb  xor     eax, eax
0x1800153cd  mov     [rdi], rbx
0x1800153d0  test    rbx, rbx
0x1800153d3  mov     ecx, 8007000Eh
0x1800153d8  mov     rbx, [rsp+28h+arg_0]
0x1800153dd  cmovz   eax, ecx
0x1800153e0  add     rsp, 20h
0x1800153e4  pop     rdi
0x1800153e5  retn
```
