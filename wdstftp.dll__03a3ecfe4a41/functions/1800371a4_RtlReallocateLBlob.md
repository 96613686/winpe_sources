# RtlReallocateLBlob

- ea: `0x1800371a4`
- end: `0x180037331`
- name: `RtlReallocateLBlob`
- size: `397`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800377a0`
- `0x180037bb8`
- `0x1800395f8`
- `0x1800551a4`

## callees

- `0x1800370f4`
- `0x1800371a4`
- `0x180037ab4`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180037266`
- `ntdll!RtlReAllocateHeap` at `0x180037266`
- `ntdll!RtlAllocateHeap` at `0x1800372cb`
- `ntdll!RtlAllocateHeap` at `0x1800372cb`

## string_xrefs

- `0x18003729c`: `Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)`
- `0x1800372fd`: `Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))`

## pseudocode

```c
__int64 __fastcall RtlReallocateLBlob(__int64 a1, SIZE_T a2, SIZE_T *a3)
{
  _QWORD *v5; // rcx
  __int64 v7; // r8
  void *v8; // r8
  PVOID Heap; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-29h] BYREF
  int v13; // [rsp+30h] [rbp-19h]
  const char *v14; // [rsp+38h] [rbp-11h]
  _QWORD v15[2]; // [rsp+40h] [rbp-9h] BYREF
  int v16; // [rsp+50h] [rbp+7h]
  const char *v17; // [rsp+58h] [rbp+Fh]
  _QWORD v18[2]; // [rsp+60h] [rbp+17h] BYREF
  int v19; // [rsp+70h] [rbp+27h]
  const char *v20; // [rsp+78h] [rbp+2Fh]
  _QWORD v21[2]; // [rsp+80h] [rbp+37h] BYREF
  int v22; // [rsp+90h] [rbp+47h]
  const char *v23; // [rsp+98h] [rbp+4Fh]

  if ( !a3 )
  {
    v13 = 128;
    v12[0] = "onecore\\base\\lstring\\lblob.cpp";
    v5 = v12;
    v12[1] = "RtlReallocateLBlob";
    v14 = "Not-null check failed: Blob";
LABEL_3:
    RtlReportErrorOrigination(v5, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( !(unsigned __int8)RtlIsLBlobValid(a3) )
  {
    v16 = 129;
    v15[0] = "onecore\\base\\lstring\\lblob.cpp";
    v5 = v15;
    v15[1] = "RtlReallocateLBlob";
    v17 = "::RtlIsLBlobValid(Blob)";
    goto LABEL_3;
  }
  v8 = *(void **)(v7 + 16);
  if ( !v8 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a2);
    if ( !Heap )
    {
      v22 = 151;
      v21[0] = "onecore\\base\\lstring\\lblob.cpp";
      v11 = v21;
      v21[1] = "RtlReallocateLBlob";
      v23 = "Temp = (PUCHAR)((*RtlAllocateStringRoutine)(Bytes))";
      goto LABEL_10;
    }
    goto LABEL_13;
  }
  if ( a3[1] < a2 )
  {
    Heap = RtlReAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8, a2);
    if ( !Heap )
    {
      v19 = 146;
      v18[0] = "onecore\\base\\lstring\\lblob.cpp";
      v11 = v18;
      v18[1] = "RtlReallocateLBlob";
      v20 = "Temp = (*RtlReallocateStringRoutine)(Bytes, Blob->Buffer)";
LABEL_10:
      RtlReportErrorOrigination(v11, v10, 3221225495LL);
      return 3221225495LL;
    }
LABEL_13:
    a3[2] = (SIZE_T)Heap;
    a3[1] = a2;
    if ( *a3 > a2 )
      *a3 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x1800371a4  mov     [rsp-8+arg_0], rbx
0x1800371a9  mov     [rsp-8+arg_18], rdi
0x1800371ae  push    rbp
0x1800371af  lea     rbp, [rsp-57h]
0x1800371b4  sub     rsp, 0A0h
0x1800371bb  mov     rbx, r8
0x1800371be  mov     rdi, rdx
0x1800371c1  test    r8, r8
0x1800371c4  jnz     short loc_180037207
0x1800371c6  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1800371cd  mov     [rbp+57h+var_70], 80h
0x1800371d4  mov     [rbp+57h+var_80], rax
0x1800371d8  lea     rcx, [rbp+57h+var_80]
0x1800371dc  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x1800371e3  mov     [rbp+57h+var_78], rax
0x1800371e7  lea     rax, aNotNullCheckFa_32; "Not-null check failed: Blob"
0x1800371ee  mov     [rbp+57h+var_68], rax
0x1800371f2  mov     r8d, 0C000000Dh
0x1800371f8  call    RtlReportErrorOrigination
0x1800371fd  mov     eax, 0C000000Dh
0x180037202  jmp     loc_18003731C
0x180037207  mov     rcx, rbx
0x18003720a  call    RtlIsLBlobValid
0x18003720f  test    al, al
0x180037211  jnz     short loc_180037241
0x180037213  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x18003721a  mov     [rbp+57h+var_50], 81h
0x180037221  mov     [rbp+57h+var_60], rax
0x180037225  lea     rcx, [rbp+57h+var_60]
0x180037229  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x180037230  mov     [rbp+57h+var_58], rax
0x180037234  lea     rax, aRtlislblobvali_3; "::RtlIsLBlobValid(Blob)"
0x18003723b  mov     [rbp+57h+var_48], rax
0x18003723f  jmp     short loc_1800371F2
0x180037241  mov     r8, [r8+10h]; Ptr
0x180037245  test    r8, r8
0x180037248  jz      short loc_1800372B9
0x18003724a  cmp     [rbx+8], rdi
0x18003724e  jnb     loc_18003731A
0x180037254  mov     rcx, gs:60h
0x18003725d  mov     r9, rdi; Size
0x180037260  xor     edx, edx; Flags
0x180037262  mov     rcx, [rcx+30h]; Heap
0x180037266  call    cs:__imp_RtlReAllocateHeap
0x18003726d  nop     dword ptr [rax+rax+00h]
0x180037272  test    rax, rax
0x180037275  jnz     loc_18003730A
0x18003727b  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x180037282  mov     [rbp+57h+var_30], 92h
0x180037289  mov     [rbp+57h+var_40], rax
0x18003728d  lea     rcx, [rbp+57h+var_40]
0x180037291  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x180037298  mov     [rbp+57h+var_38], rax
0x18003729c  lea     rax, aTempRtlrealloc; "Temp = (*RtlReallocateStringRoutine)(By"...
0x1800372a3  mov     [rbp+57h+var_28], rax
0x1800372a7  mov     r8d, 0C0000017h
0x1800372ad  call    RtlReportErrorOrigination
0x1800372b2  mov     eax, 0C0000017h
0x1800372b7  jmp     short loc_18003731C
0x1800372b9  mov     rcx, gs:60h
0x1800372c2  mov     r8, rdi; Size
0x1800372c5  xor     edx, edx; Flags
0x1800372c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800372cb  call    cs:__imp_RtlAllocateHeap
0x1800372d2  nop     dword ptr [rax+rax+00h]
0x1800372d7  test    rax, rax
0x1800372da  jnz     short loc_18003730A
0x1800372dc  lea     rax, aOnecoreBaseLst_0; "onecore\\base\\lstring\\lblob.cpp"
0x1800372e3  mov     [rbp+57h+var_10], 97h
0x1800372ea  mov     [rbp+57h+var_20], rax
0x1800372ee  lea     rcx, [rbp+57h+var_20]
0x1800372f2  lea     rax, aRtlreallocatel_0; "RtlReallocateLBlob"
0x1800372f9  mov     [rbp+57h+var_18], rax
0x1800372fd  lea     rax, aTempPucharRtla; "Temp = (PUCHAR)((*RtlAllocateStringRout"...
0x180037304  mov     [rbp+57h+var_8], rax
0x180037308  jmp     short loc_1800372A7
0x18003730a  mov     [rbx+10h], rax
0x18003730e  mov     [rbx+8], rdi
0x180037312  cmp     [rbx], rdi
0x180037315  jbe     short loc_18003731A
0x180037317  mov     [rbx], rdi
0x18003731a  xor     eax, eax
0x18003731c  lea     r11, [rsp+0A0h+var_s0]
0x180037324  mov     rbx, [r11+10h]
0x180037328  mov     rdi, [r11+28h]
0x18003732c  mov     rsp, r11
0x18003732f  pop     rbp
0x180037330  retn
```
