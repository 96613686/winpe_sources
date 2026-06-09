# TmpDeleteProtocol

- ea: `0x140018f84`
- end: `0x140019046`
- name: `TmpDeleteProtocol`
- size: `194`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020b50`

## callees

- `0x140018f84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019010`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001902c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019010`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001902c`
- `ntoskrnl!ObfDereferenceObject` at `0x140018ff6`
- `ntoskrnl!ObfDereferenceObject` at `0x140018ff6`

## pseudocode

```c
void __fastcall TmpDeleteProtocol(_QWORD *P)
{
  char *v2; // rax
  __int64 v3; // rcx
  char **v4; // rdx
  _QWORD **v5; // rdx
  PVOID *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  if ( P == (_QWORD *)TmpPromotingProtocolRegistered )
    TmpPromotingProtocolRegistered = 0;
  v2 = (char *)(P + 10);
  v3 = P[10];
  if ( *(char **)(v3 + 8) != v2
    || (v4 = (char **)*((_QWORD *)v2 + 1), *v4 != v2)
    || (*v4 = (char *)v3, *(_QWORD *)(v3 + 8) = v4, v5 = (_QWORD **)P[12], v5[1] != P + 12)
    || (v6 = (PVOID *)P[13], *v6 != P + 12) )
  {
    __fastfail(3u);
  }
  --LODWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
  *v6 = v5;
  v5[1] = v6;
  v7 = (void *)P[14];
  TmpAllProtocolsStaticInfoLength -= *((_DWORD *)P + 30);
  ObfDereferenceObject(v7);
  v8 = (void *)P[16];
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    P[16] = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140018f84  push    rbx
0x140018f86  sub     rsp, 20h
0x140018f8a  cmp     rcx, cs:TmpPromotingProtocolRegistered
0x140018f91  mov     rbx, rcx
0x140018f94  jnz     short loc_140018FA1
0x140018f96  mov     cs:TmpPromotingProtocolRegistered, 0
0x140018fa1  lea     rax, [rcx+50h]
0x140018fa5  mov     rcx, [rax]
0x140018fa8  cmp     [rcx+8], rax
0x140018fac  jnz     loc_14001903F
0x140018fb2  mov     rdx, [rax+8]
0x140018fb6  cmp     [rdx], rax
0x140018fb9  jnz     loc_14001903F
0x140018fbf  mov     [rdx], rcx
0x140018fc2  lea     rax, [rbx+60h]
0x140018fc6  mov     [rcx+8], rdx
0x140018fca  mov     rdx, [rax]
0x140018fcd  cmp     [rdx+8], rax
0x140018fd1  jnz     short loc_14001903F
0x140018fd3  mov     rcx, [rax+8]
0x140018fd7  cmp     [rcx], rax
0x140018fda  jnz     short loc_14001903F
0x140018fdc  dec     dword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018fe2  mov     [rcx], rdx
0x140018fe5  mov     [rdx+8], rcx
0x140018fe9  mov     eax, [rbx+78h]
0x140018fec  mov     rcx, [rbx+70h]; Object
0x140018ff0  sub     cs:TmpAllProtocolsStaticInfoLength, eax
0x140018ff6  call    cs:__imp_ObfDereferenceObject
0x140018ffd  nop     dword ptr [rax+rax+00h]
0x140019002  mov     rcx, [rbx+80h]; P
0x140019009  test    rcx, rcx
0x14001900c  jz      short loc_140019027
0x14001900e  xor     edx, edx; Tag
0x140019010  call    cs:__imp_ExFreePoolWithTag
0x140019017  nop     dword ptr [rax+rax+00h]
0x14001901c  mov     qword ptr [rbx+80h], 0
0x140019027  xor     edx, edx; Tag
0x140019029  mov     rcx, rbx; P
0x14001902c  call    cs:__imp_ExFreePoolWithTag
0x140019033  nop     dword ptr [rax+rax+00h]
0x140019038  add     rsp, 20h
0x14001903c  pop     rbx
0x14001903d  retn
0x14001903f  mov     ecx, 3
0x140019044  int     29h; Win8: RtlFailFast(ecx)
```
