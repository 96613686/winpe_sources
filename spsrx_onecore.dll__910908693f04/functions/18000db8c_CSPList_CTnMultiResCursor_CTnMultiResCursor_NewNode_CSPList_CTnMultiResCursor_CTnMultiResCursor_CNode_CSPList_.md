# CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *)

- ea: `0x18000db8c`
- end: `0x18000dc1e`
- name: `?NewNode@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z`
- size: `146`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800098e0`
- `0x180009c04`
- `0x180009ed4`
- `0x18000d348`
- `0x18000d3ac`
- `0x18000d434`
- `0x18000dc24`

## callees

- `0x18000ac44`
- `0x18000db8c`

## pseudocode

```c
_QWORD *__fastcall CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(__int64 a1, __int64 a2, __int64 a3)
{
  struct CSPPlex *v6; // rax
  int v7; // r8d
  _QWORD *i; // rcx
  _QWORD *result; // rax

  if ( !*(_QWORD *)(a1 + 24) )
  {
    v6 = CSPPlex::Create((struct CSPPlex **)(a1 + 32), *(_DWORD *)(a1 + 40));
    if ( v6 )
    {
      v7 = *(_DWORD *)(a1 + 40) - 1;
      for ( i = (_QWORD *)((char *)v6 + 24 * v7 + 16); v7 >= 0; --v7 )
      {
        *i = *(_QWORD *)(a1 + 24);
        *(_QWORD *)(a1 + 24) = i;
        i -= 3;
      }
    }
  }
  result = *(_QWORD **)(a1 + 24);
  if ( result )
  {
    result[2] = 0;
    *(_QWORD *)(a1 + 24) = **(_QWORD **)(a1 + 24);
    result[1] = a2;
    *result = a3;
    ++*(_DWORD *)(a1 + 16);
  }
  return result;
}

```

## disassembly

```asm
0x18000db8c  mov     [rsp+arg_0], rbx
0x18000db91  mov     [rsp+arg_8], rsi
0x18000db96  push    rdi
0x18000db97  sub     rsp, 20h
0x18000db9b  cmp     qword ptr [rcx+18h], 0
0x18000dba0  mov     rdi, r8
0x18000dba3  mov     rsi, rdx
0x18000dba6  mov     rbx, rcx
0x18000dba9  jnz     short loc_18000DBEA
0x18000dbab  mov     edx, [rbx+28h]; unsigned int
0x18000dbae  add     rcx, 20h ; ' '; struct CSPPlex **
0x18000dbb2  call    ?Create@CSPPlex@@SAPEAU1@AEAPEAU1@II@Z; CSPPlex::Create(CSPPlex * &,uint,uint)
0x18000dbb7  test    rax, rax
0x18000dbba  jz      short loc_18000DBEA
0x18000dbbc  mov     r8d, [rbx+28h]
0x18000dbc0  sub     r8d, 1
0x18000dbc4  movsxd  rcx, r8d
0x18000dbc7  lea     rcx, [rcx+rcx*2]
0x18000dbcb  lea     rcx, [rcx+2]
0x18000dbcf  lea     rcx, [rax+rcx*8]
0x18000dbd3  js      short loc_18000DBEA
0x18000dbd5  mov     rax, [rbx+18h]
0x18000dbd9  mov     [rcx], rax
0x18000dbdc  mov     [rbx+18h], rcx
0x18000dbe0  sub     rcx, 18h
0x18000dbe4  sub     r8d, 1
0x18000dbe8  jns     short loc_18000DBD5
0x18000dbea  mov     rax, [rbx+18h]
0x18000dbee  test    rax, rax
0x18000dbf1  jz      short loc_18000DC0E
0x18000dbf3  xor     ecx, ecx
0x18000dbf5  mov     [rax+10h], rcx
0x18000dbf9  mov     rcx, [rbx+18h]
0x18000dbfd  mov     rdx, [rcx]
0x18000dc00  mov     [rbx+18h], rdx
0x18000dc04  mov     [rax+8], rsi
0x18000dc08  mov     [rax], rdi
0x18000dc0b  inc     dword ptr [rbx+10h]
0x18000dc0e  mov     rbx, [rsp+28h+arg_0]
0x18000dc13  mov     rsi, [rsp+28h+arg_8]
0x18000dc18  add     rsp, 20h
0x18000dc1c  pop     rdi
0x18000dc1d  retn
```
