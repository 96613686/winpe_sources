# SclProcessObjectSecurity

- ea: `0x1800121d4`
- end: `0x1800123ab`
- name: `SclProcessObjectSecurity`
- size: `471`
- prototype: `__int64 __fastcall(__int64, void *, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000acec`

## callees

- `0x180001b98`
- `0x180001bc0`
- `0x18000a524`
- `0x1800121d4`
- `0x1800123b4`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180012268`
- `ntdll!RtlAllocateHeap` at `0x180012268`
- `ntdll!RtlFreeHeap` at `0x18001237c`
- `ntdll!RtlFreeHeap` at `0x18001237c`

## string_xrefs

- `0x1800122a9`: `(%lx): Failed to query object security!`
- `0x1800122bc`: `SclProcessObjectSecurity`
- `0x180012341`: `(%lx): Failed to set security info.`

## pseudocode

```c
__int64 __fastcall SclProcessObjectSecurity(__int64 a1, void *a2, _BYTE *a3)
{
  _BYTE *v4; // rsi
  int Descriptor; // ebx
  unsigned int v8; // ebx
  _BYTE *Heap; // rax
  __int64 v10; // rcx
  char v11; // bp
  int v12; // eax
  _BYTE v14[4]; // [rsp+40h] [rbp-448h] BYREF
  SIZE_T Size; // [rsp+44h] [rbp-444h] BYREF
  _BYTE P[1024]; // [rsp+50h] [rbp-438h] BYREF

  LODWORD(Size) = 0;
  v14[0] = 0;
  v4 = P;
  if ( a1 != -1240 )
    ++*(_QWORD *)(a1 + 1240);
  Descriptor = SclSecurityGetDescriptor(a2, P, 1024, &Size);
  if ( Descriptor == -1073741789 )
  {
    v8 = Size;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    v4 = Heap;
    if ( !Heap )
    {
      Descriptor = -1073741801;
      goto LABEL_7;
    }
    Descriptor = SclSecurityGetDescriptor(a2, Heap, v8, &Size);
  }
  if ( Descriptor < 0 )
  {
LABEL_7:
    v10 = a1 + 1152;
    if ( !a1 )
      v10 = 0;
    SclLogGenericMessage(
      v10,
      3,
      (int)SclEvent_Generic_Error,
      106,
      (__int64)"SclProcessObjectSecurity",
      "(%lx): Failed to query object security!",
      Descriptor);
    goto LABEL_21;
  }
  Descriptor = SclProcessSecurityBlob(a1, v4, (unsigned int)Size, v14);
  if ( Descriptor >= 0 )
  {
    v11 = v14[0];
    if ( !v14[0] )
      goto LABEL_19;
    if ( a1 != -1232 )
      ++*(_QWORD *)(a1 + 1232);
    if ( *(_BYTE *)a1 && (v12 = SclSecuritySetDescriptor(a2, v4), Descriptor = v12, v12 < 0) )
    {
      SclLogGenericMessage(
        a1 + 1152,
        3,
        (int)SclEvent_Generic_Error,
        147,
        (__int64)"SclProcessObjectSecurity",
        "(%lx): Failed to set security info.",
        v12);
    }
    else
    {
LABEL_19:
      if ( a3 )
        *a3 = v11;
    }
  }
LABEL_21:
  if ( v4 != P && v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)Descriptor;
}

```

## disassembly

```asm
0x1800121d4  mov     [rsp+arg_18], rbx
0x1800121d9  push    rbp
0x1800121da  push    rsi
0x1800121db  push    rdi
0x1800121dc  push    r14
0x1800121de  push    r15
0x1800121e0  sub     rsp, 460h
0x1800121e7  mov     rax, cs:__security_cookie
0x1800121ee  xor     rax, rsp
0x1800121f1  mov     [rsp+488h+var_38], rax
0x1800121f9  lea     rax, [rcx+4D8h]
0x180012200  mov     dword ptr [rsp+488h+Size], 0
0x180012208  mov     [rsp+488h+var_448], 0
0x18001220d  mov     r14, r8
0x180012210  lea     rsi, [rsp+488h+P]
0x180012215  mov     r15, rdx
0x180012218  mov     rdi, rcx
0x18001221b  test    rax, rax
0x18001221e  jz      short loc_180012231
0x180012220  mov     rax, [rcx+4D8h]
0x180012227  inc     rax
0x18001222a  mov     [rcx+4D8h], rax
0x180012231  lea     r9, [rsp+488h+Size]
0x180012236  mov     r8d, 400h
0x18001223c  lea     rdx, [rsp+488h+P]
0x180012241  mov     rcx, r15
0x180012244  call    SclSecurityGetDescriptor
0x180012249  mov     ebx, eax
0x18001224b  cmp     eax, 0C0000023h
0x180012250  jnz     short loc_18001228B
0x180012252  mov     rcx, gs:60h
0x18001225b  xor     edx, edx; Flags
0x18001225d  mov     ebx, dword ptr [rsp+488h+Size]
0x180012261  mov     r8d, ebx; Size
0x180012264  mov     rcx, [rcx+30h]; HeapHandle
0x180012268  call    cs:__imp_RtlAllocateHeap
0x18001226e  mov     rsi, rax
0x180012271  test    rax, rax
0x180012274  jz      short loc_1800122D7
0x180012276  lea     r9, [rsp+488h+Size]
0x18001227b  mov     r8d, ebx
0x18001227e  mov     rdx, rax
0x180012281  mov     rcx, r15
0x180012284  call    SclSecurityGetDescriptor
0x180012289  mov     ebx, eax
0x18001228b  test    ebx, ebx
0x18001228d  jns     short loc_1800122DE
0x18001228f  xor     eax, eax
0x180012291  mov     [rsp+488h+var_458], ebx
0x180012295  test    rdi, rdi
0x180012298  lea     rcx, [rdi+480h]
0x18001229f  mov     r9d, 6Ah ; 'j'
0x1800122a5  cmovz   rcx, rax
0x1800122a9  lea     rax, aLxFailedToQuer_0; "(%lx): Failed to query object security!"
0x1800122b0  mov     [rsp+488h+var_460], rax
0x1800122b5  lea     r8, SclEvent_Generic_Error
0x1800122bc  lea     rax, aSclprocessobje; "SclProcessObjectSecurity"
0x1800122c3  mov     edx, 3
0x1800122c8  mov     [rsp+488h+var_468], rax
0x1800122cd  call    SclLogGenericMessage
0x1800122d2  jmp     loc_18001235B
0x1800122d7  mov     ebx, 0C0000017h
0x1800122dc  jmp     short loc_18001228F
0x1800122de  mov     r8d, dword ptr [rsp+488h+Size]
0x1800122e3  lea     r9, [rsp+488h+var_448]
0x1800122e8  mov     rdx, rsi
0x1800122eb  mov     rcx, rdi
0x1800122ee  call    SclProcessSecurityBlob
0x1800122f3  mov     ebx, eax
0x1800122f5  test    eax, eax
0x1800122f7  js      short loc_18001235B
0x1800122f9  mov     bpl, [rsp+488h+var_448]
0x1800122fe  test    bpl, bpl
0x180012301  jz      short loc_180012353
0x180012303  lea     rax, [rdi+4D0h]
0x18001230a  test    rax, rax
0x18001230d  jz      short loc_180012320
0x18001230f  mov     rax, [rdi+4D0h]
0x180012316  inc     rax
0x180012319  mov     [rdi+4D0h], rax
0x180012320  cmp     byte ptr [rdi], 0
0x180012323  jz      short loc_180012353
0x180012325  mov     rdx, rsi; SecurityDescriptor
0x180012328  mov     rcx, r15; Handle
0x18001232b  call    SclSecuritySetDescriptor
0x180012330  mov     ebx, eax
0x180012332  test    eax, eax
0x180012334  jns     short loc_180012353
0x180012336  mov     [rsp+488h+var_458], eax
0x18001233a  lea     rcx, [rdi+480h]
0x180012341  lea     rax, aLxFailedToSetS; "(%lx): Failed to set security info."
0x180012348  mov     r9d, 93h
0x18001234e  jmp     loc_1800122B0
0x180012353  test    r14, r14
0x180012356  jz      short loc_18001235B
0x180012358  mov     [r14], bpl
0x18001235b  lea     rax, [rsp+488h+P]
0x180012360  cmp     rsi, rax
0x180012363  jz      short loc_180012382
0x180012365  test    rsi, rsi
0x180012368  jz      short loc_180012382
0x18001236a  mov     rcx, gs:60h
0x180012373  mov     r8, rsi; P
0x180012376  xor     edx, edx; Flags
0x180012378  mov     rcx, [rcx+30h]; HeapHandle
0x18001237c  call    cs:__imp_RtlFreeHeap
0x180012382  mov     eax, ebx
0x180012384  mov     rcx, [rsp+488h+var_38]
0x18001238c  xor     rcx, rsp; StackCookie
0x18001238f  call    __security_check_cookie
0x180012394  mov     rbx, [rsp+488h+arg_18]
0x18001239c  add     rsp, 460h
0x1800123a3  pop     r15
0x1800123a5  pop     r14
0x1800123a7  pop     rdi
0x1800123a8  pop     rsi
0x1800123a9  pop     rbp
0x1800123aa  retn
```
