# CreateRegistryLinksForMachine

- ea: `0x14000b21c`
- end: `0x14000b3de`
- name: `CreateRegistryLinksForMachine`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x14000b110`

## callees

- `0x1400094c0`
- `0x14000b21c`
- `0x140018ebc`
- `0x140019128`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000b2c4`
- `ntdll!RtlAllocateHeap` at `0x14000b2eb`
- `ntdll!RtlAllocateHeap` at `0x14000b2c4`
- `ntdll!RtlAllocateHeap` at `0x14000b2eb`
- `ntdll!RtlFreeHeap` at `0x14000b381`
- `ntdll!RtlFreeHeap` at `0x14000b39a`
- `ntdll!RtlFreeHeap` at `0x14000b3be`
- `ntdll!RtlFreeHeap` at `0x14000b381`
- `ntdll!RtlFreeHeap` at `0x14000b39a`
- `ntdll!RtlFreeHeap` at `0x14000b3be`
- `ntdll!RtlCopyUnicodeString` at `0x14000b31b`
- `ntdll!RtlCopyUnicodeString` at `0x14000b328`
- `ntdll!RtlCopyUnicodeString` at `0x14000b31b`
- `ntdll!RtlCopyUnicodeString` at `0x14000b328`

## pseudocode

```c
__int64 __fastcall CreateRegistryLinksForMachine(__int16 a1)
{
  char v1; // r12
  unsigned __int16 *v2; // r13
  int MergeLink; // ebx
  unsigned int i; // esi
  __int64 v5; // rax
  struct _UNICODE_STRING *v6; // r15
  struct _UNICODE_STRING *p_DestinationString; // r14
  int v8; // eax
  __int16 v9; // dx
  __int16 v10; // dx
  USHORT v11; // bx
  unsigned int v12; // edi
  WCHAR *Heap; // rax
  WCHAR *v14; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v17; // [rsp+30h] [rbp-18h] BYREF

  if ( a1 == 332 )
  {
    v2 = 0;
    v1 = 0;
  }
  else
  {
    v1 = 1;
    v2 = (unsigned __int16 *)Wow64SelectWowNodePathInternal();
  }
  MergeLink = 0;
  for ( i = 0; i < 0x4E; ++i )
  {
    v5 = 16LL * i;
    DestinationString = 0;
    v17 = 0;
    v6 = (struct _UNICODE_STRING *)&RegistrySymbolicLinks[v5 + 8];
    p_DestinationString = (struct _UNICODE_STRING *)&RegistrySymbolicLinks[v5];
    if ( v1 )
    {
      v8 = *v2;
      v9 = v8 - 24;
      if ( v8 - 24 < 0 )
        v9 = 24 - v8;
      v10 = 2 * v9;
      v11 = p_DestinationString->MaximumLength + v10;
      v12 = (unsigned __int16)(v6->MaximumLength + v10);
      Heap = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v11);
      *(_QWORD *)&DestinationString.Length = 0;
      DestinationString.MaximumLength = v11;
      DestinationString.Buffer = Heap;
      v14 = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v12);
      *(_QWORD *)&v17.Length = 0;
      v17.MaximumLength = v12;
      v17.Buffer = v14;
      if ( !DestinationString.Buffer )
        return 3221225495LL;
      if ( !v14 )
      {
        RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, DestinationString.Buffer);
        return 3221225495LL;
      }
      RtlCopyUnicodeString(&DestinationString, p_DestinationString);
      RtlCopyUnicodeString(&v17, v6);
      PathReplaceGreedy(&Wowx86NodeString, v2, &DestinationString);
      PathReplaceGreedy(&Wowx86NodeString, v2, &v17);
      p_DestinationString = &DestinationString;
      v6 = &v17;
    }
    MergeLink = CreateMergeLink(p_DestinationString, v6);
    if ( v1 )
    {
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, p_DestinationString->Buffer);
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v6->Buffer);
    }
    if ( MergeLink < 0 )
      return (unsigned int)MergeLink;
  }
  return (unsigned int)MergeLink;
}

```

## disassembly

```asm
0x14000b21c  push    rbp
0x14000b21e  push    rbx
0x14000b21f  push    rsi
0x14000b220  push    rdi
0x14000b221  push    r12
0x14000b223  push    r13
0x14000b225  push    r14
0x14000b227  push    r15
0x14000b229  mov     rbp, rsp
0x14000b22c  sub     rsp, 48h
0x14000b230  mov     eax, 14Ch
0x14000b235  cmp     cx, ax
0x14000b238  jz      short loc_14000B247
0x14000b23a  mov     r12b, 1
0x14000b23d  call    Wow64SelectWowNodePathInternal
0x14000b242  mov     r13, rax
0x14000b245  jmp     short loc_14000B24D
0x14000b247  xor     r13d, r13d
0x14000b24a  xor     r12b, r12b
0x14000b24d  xor     ebx, ebx
0x14000b24f  xor     esi, esi
0x14000b251  lea     rcx, RegistrySymbolicLinks; "\\^"
0x14000b258  cmp     esi, 4Eh ; 'N'
0x14000b25b  jnb     loc_14000B3CB
0x14000b261  mov     eax, esi
0x14000b263  xorps   xmm0, xmm0
0x14000b266  shl     rax, 5
0x14000b26a  xorps   xmm1, xmm1
0x14000b26d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b271  movups  xmmword ptr [rbp+var_18.Length], xmm1
0x14000b275  lea     r15, [rax+10h]
0x14000b279  add     r15, rcx
0x14000b27c  lea     r14, [rax+rcx]
0x14000b280  test    r12b, r12b
0x14000b283  jz      loc_14000B35C
0x14000b289  movzx   eax, word ptr [r13+0]
0x14000b28e  mov     ecx, 18h
0x14000b293  sub     ecx, eax
0x14000b295  mov     edx, ecx
0x14000b297  neg     edx
0x14000b299  cmovs   edx, ecx
0x14000b29c  mov     rcx, gs:60h
0x14000b2a5  add     dx, dx
0x14000b2a8  movzx   eax, dx
0x14000b2ab  add     dx, [r15+2]
0x14000b2b0  add     ax, [r14+2]
0x14000b2b5  mov     rcx, [rcx+30h]; HeapHandle
0x14000b2b9  movzx   ebx, ax
0x14000b2bc  movzx   edi, dx
0x14000b2bf  mov     r8d, ebx; Size
0x14000b2c2  xor     edx, edx; Flags
0x14000b2c4  call    cs:__imp_RtlAllocateHeap
0x14000b2ca  xorps   xmm0, xmm0
0x14000b2cd  mov     r8d, edi; Size
0x14000b2d0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b2d4  mov     [rbp+DestinationString.MaximumLength], bx
0x14000b2d8  xor     edx, edx; Flags
0x14000b2da  mov     [rbp+DestinationString.Buffer], rax
0x14000b2de  mov     rcx, gs:60h
0x14000b2e7  mov     rcx, [rcx+30h]; HeapHandle
0x14000b2eb  call    cs:__imp_RtlAllocateHeap
0x14000b2f1  cmp     [rbp+DestinationString.Buffer], 0
0x14000b2f6  xorps   xmm0, xmm0
0x14000b2f9  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x14000b2fd  mov     [rbp+var_18.MaximumLength], di
0x14000b301  mov     [rbp+var_18.Buffer], rax
0x14000b305  jz      loc_14000B3C4
0x14000b30b  test    rax, rax
0x14000b30e  jz      loc_14000B3AB
0x14000b314  mov     rdx, r14; SourceString
0x14000b317  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b31b  call    cs:__imp_RtlCopyUnicodeString
0x14000b321  mov     rdx, r15; SourceString
0x14000b324  lea     rcx, [rbp+var_18]; DestinationString
0x14000b328  call    cs:__imp_RtlCopyUnicodeString
0x14000b32e  lea     r8, [rbp+DestinationString]
0x14000b332  mov     rdx, r13
0x14000b335  lea     rcx, Wowx86NodeString
0x14000b33c  call    PathReplaceGreedy
0x14000b341  lea     r8, [rbp+var_18]
0x14000b345  mov     rdx, r13
0x14000b348  lea     rcx, Wowx86NodeString
0x14000b34f  call    PathReplaceGreedy
0x14000b354  lea     r14, [rbp+DestinationString]
0x14000b358  lea     r15, [rbp+var_18]
0x14000b35c  mov     rdx, r15
0x14000b35f  mov     rcx, r14
0x14000b362  call    CreateMergeLink
0x14000b367  mov     ebx, eax
0x14000b369  test    r12b, r12b
0x14000b36c  jz      short loc_14000B3A0
0x14000b36e  mov     rcx, gs:60h
0x14000b377  xor     edx, edx; Flags
0x14000b379  mov     r8, [r14+8]; BaseAddress
0x14000b37d  mov     rcx, [rcx+30h]; HeapHandle
0x14000b381  call    cs:__imp_RtlFreeHeap
0x14000b387  mov     rcx, gs:60h
0x14000b390  xor     edx, edx; Flags
0x14000b392  mov     r8, [r15+8]; BaseAddress
0x14000b396  mov     rcx, [rcx+30h]; HeapHandle
0x14000b39a  call    cs:__imp_RtlFreeHeap
0x14000b3a0  test    ebx, ebx
0x14000b3a2  js      short loc_14000B3CB
0x14000b3a4  inc     esi
0x14000b3a6  jmp     loc_14000B251
0x14000b3ab  mov     rcx, gs:60h
0x14000b3b4  xor     edx, edx; Flags
0x14000b3b6  mov     r8, [rbp+DestinationString.Buffer]; BaseAddress
0x14000b3ba  mov     rcx, [rcx+30h]; HeapHandle
0x14000b3be  call    cs:__imp_RtlFreeHeap
0x14000b3c4  mov     eax, 0C0000017h
0x14000b3c9  jmp     short loc_14000B3CD
0x14000b3cb  mov     eax, ebx
0x14000b3cd  add     rsp, 48h
0x14000b3d1  pop     r15
0x14000b3d3  pop     r14
0x14000b3d5  pop     r13
0x14000b3d7  pop     r12
0x14000b3d9  pop     rdi
0x14000b3da  pop     rsi
0x14000b3db  pop     rbx
0x14000b3dc  pop     rbp
0x14000b3dd  retn
```
