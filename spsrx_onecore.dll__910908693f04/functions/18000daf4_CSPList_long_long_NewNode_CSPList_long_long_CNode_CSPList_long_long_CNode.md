# CSPList<long,long>::NewNode(CSPList<long,long>::CNode *,CSPList<long,long>::CNode *)

- ea: `0x18000daf4`
- end: `0x18000db85`
- name: `?NewNode@?$CSPList@JJ@@IEAAPEAUCNode@1@PEAU21@0@Z`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000978c`
- `0x180009878`
- `0x18000b208`
- `0x18000d49c`

## callees

- `0x18000ac44`
- `0x18000daf4`

## pseudocode

```c
__int64 __fastcall CSPList<long,long>::NewNode(__int64 a1, __int64 a2, __int64 a3)
{
  struct CSPPlex *v6; // rax
  int v7; // r8d
  _QWORD *i; // rcx
  __int64 result; // rax

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
  result = *(_QWORD *)(a1 + 24);
  if ( result )
  {
    *(_DWORD *)(result + 16) = 0;
    *(_QWORD *)(a1 + 24) = **(_QWORD **)(a1 + 24);
    *(_QWORD *)(result + 8) = a2;
    *(_QWORD *)result = a3;
    ++*(_DWORD *)(a1 + 16);
  }
  return result;
}

```

## disassembly

```asm
0x18000daf4  mov     [rsp+arg_0], rbx
0x18000daf9  mov     [rsp+arg_8], rsi
0x18000dafe  push    rdi
0x18000daff  sub     rsp, 20h
0x18000db03  cmp     qword ptr [rcx+18h], 0
0x18000db08  mov     rdi, r8
0x18000db0b  mov     rsi, rdx
0x18000db0e  mov     rbx, rcx
0x18000db11  jnz     short loc_18000DB52
0x18000db13  mov     edx, [rbx+28h]; unsigned int
0x18000db16  add     rcx, 20h ; ' '; struct CSPPlex **
0x18000db1a  call    ?Create@CSPPlex@@SAPEAU1@AEAPEAU1@II@Z; CSPPlex::Create(CSPPlex * &,uint,uint)
0x18000db1f  test    rax, rax
0x18000db22  jz      short loc_18000DB52
0x18000db24  mov     r8d, [rbx+28h]
0x18000db28  sub     r8d, 1
0x18000db2c  movsxd  rcx, r8d
0x18000db2f  lea     rcx, [rcx+rcx*2]
0x18000db33  lea     rcx, [rcx+2]
0x18000db37  lea     rcx, [rax+rcx*8]
0x18000db3b  js      short loc_18000DB52
0x18000db3d  mov     rax, [rbx+18h]
0x18000db41  mov     [rcx], rax
0x18000db44  mov     [rbx+18h], rcx
0x18000db48  sub     rcx, 18h
0x18000db4c  sub     r8d, 1
0x18000db50  jns     short loc_18000DB3D
0x18000db52  mov     rax, [rbx+18h]
0x18000db56  test    rax, rax
0x18000db59  jz      short loc_18000DB75
0x18000db5b  xor     ecx, ecx
0x18000db5d  mov     [rax+10h], ecx
0x18000db60  mov     rcx, [rbx+18h]
0x18000db64  mov     rdx, [rcx]
0x18000db67  mov     [rbx+18h], rdx
0x18000db6b  mov     [rax+8], rsi
0x18000db6f  mov     [rax], rdi
0x18000db72  inc     dword ptr [rbx+10h]
0x18000db75  mov     rbx, [rsp+28h+arg_0]
0x18000db7a  mov     rsi, [rsp+28h+arg_8]
0x18000db7f  add     rsp, 20h
0x18000db83  pop     rdi
0x18000db84  retn
```
