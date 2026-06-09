# WinNatFindBindingUnderLock

- ea: `0x140004a80`
- end: `0x140004c2f`
- name: `WinNatFindBindingUnderLock`
- size: `431`
- prototype: `struct _LIST_ENTRY **__fastcall(__int64, int, _WORD *, __int64, char, char, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003830`
- `0x140004648`
- `0x14001a2e0`
- `0x14001a398`
- `0x14001a954`
- `0x14001d5bc`

## callees

- `0x140004a80`
- `0x1400061d0`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004b4e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140004b4e`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140004c15`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140004c15`
- `NETIO!RtlComputeToeplitzHash` at `0x140004b06`
- `NETIO!RtlComputeToeplitzHash` at `0x140004b29`
- `NETIO!RtlComputeToeplitzHash` at `0x140004b06`
- `NETIO!RtlComputeToeplitzHash` at `0x140004b29`

## pseudocode

```c
struct _LIST_ENTRY **__fastcall WinNatFindBindingUnderLock(
        __int64 a1,
        int a2,
        _WORD *a3,
        __int64 a4,
        char a5,
        char a6,
        int a7)
{
  struct _LIST_ENTRY **p_Blink; // rbx
  __int64 v11; // r10
  __int64 v12; // r8
  bool v13; // zf
  __int16 v15; // cx
  __int64 v16; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v17; // r15
  int v18; // edi
  int v19; // eax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  int v22; // esi
  char v23; // di
  int v24; // eax
  int Flink_high; // eax
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  __int16 v27; // [rsp+70h] [rbp+8h] BYREF

  p_Blink = 0;
  v11 = 2;
  v12 = 4;
  v13 = *a3 == 2;
  *(_OWORD *)&Context.ChainHead = 0;
  if ( !v13 )
    v12 = 16;
  if ( !v13 )
    v11 = 4;
  v15 = a3[1];
  Context.Signature = 0;
  v16 = 392;
  if ( a6 )
    v16 = 384;
  v17 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(v16 + a1);
  v27 = v15;
  v18 = RtlComputeToeplitzHash(a1 + 400, &a3[v11], v12, 0);
  v19 = RtlComputeToeplitzHash(a1 + 400, &v27, 2, 0);
  *(_OWORD *)&Context.ChainHead = 0;
  NextEntryHashTable = RtlLookupEntryHashTable(v17, v18 ^ v19 | 0x80000000, &Context);
  if ( NextEntryHashTable )
  {
    v22 = a7;
    v23 = a5;
    do
    {
      if ( a6 )
      {
        p_Blink = &NextEntryHashTable[-1].Linkage.Blink;
        if ( (unsigned __int8)WinNatCompareTransportAndSockAddr(NextEntryHashTable[3].Linkage.Blink, a3, 0) )
        {
          if ( *((_BYTE *)p_Blink + 68) == v23 && *((_DWORD *)p_Blink + 23) == a2 )
          {
            v24 = *((_DWORD *)p_Blink + 29);
            if ( (!v24 || v24 == v22) && (!a4 || (unsigned __int8)WinNatCompareTransportAndSockAddr(p_Blink[13], a4, 0)) )
              return p_Blink;
          }
        }
      }
      else
      {
        p_Blink = &NextEntryHashTable[-2].Linkage.Blink;
        Flink_high = HIDWORD(NextEntryHashTable[3].Linkage.Flink);
        if ( (!Flink_high || Flink_high == v22)
          && (unsigned __int8)WinNatCompareTransportAndSockAddr(p_Blink[13], a3, 0)
          && *((_BYTE *)p_Blink + 68) == v23 )
        {
          return p_Blink;
        }
      }
      p_Blink = 0;
      NextEntryHashTable = RtlGetNextEntryHashTable(v17, &Context);
    }
    while ( NextEntryHashTable );
  }
  return p_Blink;
}

```

## disassembly

```asm
0x140004a80  mov     [rsp+arg_8], rbx
0x140004a85  mov     [rsp+arg_10], rsi
0x140004a8a  push    rdi
0x140004a8b  push    r12
0x140004a8d  push    r13
0x140004a8f  push    r14
0x140004a91  push    r15
0x140004a93  sub     rsp, 40h
0x140004a97  mov     r14, r8
0x140004a9a  mov     rsi, rcx
0x140004a9d  mov     r12, r9
0x140004aa0  xor     ebx, ebx
0x140004aa2  mov     r9d, 180h
0x140004aa8  mov     r10d, 4
0x140004aae  mov     r8d, r10d
0x140004ab1  mov     ecx, 10h
0x140004ab6  cmp     word ptr [r14], 2
0x140004abb  xorps   xmm0, xmm0
0x140004abe  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x140004ac3  cmovnz  r8d, ecx
0x140004ac7  mov     r13d, edx
0x140004aca  mov     ecx, 8
0x140004acf  cmovnz  r10d, ecx
0x140004ad3  movzx   ecx, word ptr [r14+2]
0x140004ad8  xor     eax, eax
0x140004ada  cmp     [rsp+68h+arg_28], bl
0x140004ae1  mov     [rsp+68h+Context.Signature], rax
0x140004ae6  mov     eax, 188h
0x140004aeb  cmovnz  eax, r9d
0x140004aef  lea     rdx, [r10+r14]
0x140004af3  xor     r9d, r9d
0x140004af6  mov     r15, [rax+rsi]
0x140004afa  mov     [rsp+68h+arg_0], cx
0x140004aff  lea     rcx, [rsi+190h]
0x140004b06  call    cs:__imp_RtlComputeToeplitzHash
0x140004b0d  nop     dword ptr [rax+rax+00h]
0x140004b12  xor     r9d, r9d
0x140004b15  lea     rdx, [rsp+68h+arg_0]
0x140004b1a  mov     r8d, 2
0x140004b20  lea     rcx, [rsi+190h]
0x140004b27  mov     edi, eax
0x140004b29  call    cs:__imp_RtlComputeToeplitzHash
0x140004b30  nop     dword ptr [rax+rax+00h]
0x140004b35  xorps   xmm0, xmm0
0x140004b38  lea     r8, [rsp+68h+Context]; Context
0x140004b3d  xor     eax, edi
0x140004b3f  mov     rcx, r15; HashTable
0x140004b42  bts     eax, 1Fh
0x140004b46  mov     edx, eax; Signature
0x140004b48  movdqu  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x140004b4e  call    cs:__imp_RtlLookupEntryHashTable
0x140004b55  nop     dword ptr [rax+rax+00h]
0x140004b5a  test    rax, rax
0x140004b5d  jnz     short loc_140004B7E
0x140004b5f  mov     rsi, [rsp+68h+arg_10]
0x140004b67  mov     rax, rbx
0x140004b6a  mov     rbx, [rsp+68h+arg_8]
0x140004b6f  add     rsp, 40h
0x140004b73  pop     r15
0x140004b75  pop     r14
0x140004b77  pop     r13
0x140004b79  pop     r12
0x140004b7b  pop     rdi
0x140004b7c  retn
0x140004b7e  mov     esi, [rsp+68h+arg_30]
0x140004b85  movzx   edi, [rsp+68h+arg_20]
0x140004b8d  cmp     [rsp+68h+arg_28], 0
0x140004b95  jz      short loc_140004BDF
0x140004b97  mov     rcx, [rax+50h]
0x140004b9b  lea     rbx, [rax-10h]
0x140004b9f  xor     r8d, r8d
0x140004ba2  mov     rdx, r14
0x140004ba5  call    WinNatCompareTransportAndSockAddr
0x140004baa  test    al, al
0x140004bac  jz      short loc_140004C0B
0x140004bae  cmp     [rbx+44h], dil
0x140004bb2  jnz     short loc_140004C0B
0x140004bb4  cmp     [rbx+5Ch], r13d
0x140004bb8  jnz     short loc_140004C0B
0x140004bba  mov     eax, [rbx+74h]
0x140004bbd  test    eax, eax
0x140004bbf  jz      short loc_140004BC5
0x140004bc1  cmp     eax, esi
0x140004bc3  jnz     short loc_140004C0B
0x140004bc5  test    r12, r12
0x140004bc8  jz      short loc_140004B5F
0x140004bca  mov     rcx, [rbx+68h]
0x140004bce  xor     r8d, r8d
0x140004bd1  mov     rdx, r12
0x140004bd4  call    WinNatCompareTransportAndSockAddr
0x140004bd9  test    al, al
0x140004bdb  jnz     short loc_140004B5F
0x140004bdd  jmp     short loc_140004C0B
0x140004bdf  lea     rbx, [rax-28h]
0x140004be3  mov     eax, [rax+4Ch]
0x140004be6  test    eax, eax
0x140004be8  jz      short loc_140004BEE
0x140004bea  cmp     eax, esi
0x140004bec  jnz     short loc_140004C0B
0x140004bee  mov     rcx, [rbx+68h]
0x140004bf2  xor     r8d, r8d
0x140004bf5  mov     rdx, r14
0x140004bf8  call    WinNatCompareTransportAndSockAddr
0x140004bfd  test    al, al
0x140004bff  jz      short loc_140004C0B
0x140004c01  cmp     [rbx+44h], dil
0x140004c05  jz      loc_140004B5F
0x140004c0b  lea     rdx, [rsp+68h+Context]; Context
0x140004c10  mov     rcx, r15; HashTable
0x140004c13  xor     ebx, ebx
0x140004c15  call    cs:__imp_RtlGetNextEntryHashTable
0x140004c1c  nop     dword ptr [rax+rax+00h]
0x140004c21  test    rax, rax
0x140004c24  jnz     loc_140004B8D
0x140004c2a  jmp     loc_140004B5F
```
