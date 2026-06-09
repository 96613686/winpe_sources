# CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(ulong,ulong)

- ea: `0x18001fcf0`
- end: `0x18001fd45`
- name: `?RemoveAt@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAHKK@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800177dc`

## callees

- `0x18001fcf0`
- `0x180020030`

## pseudocode

```c
_BOOL8 __fastcall CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::RemoveAt(__int64 a1, unsigned int a2)
{
  int v5; // edi
  int v6; // eax

  if ( a2 + 1 > *(_DWORD *)(a1 + 592) )
    return 0;
  v5 = 0;
  do
  {
    v6 = CTSparseBlock<unsigned long,CASFV1MetadataObject::METADATA_REC,20,0>::RemoveValue(a1, a2);
    if ( v6 < 0 )
      break;
    --*(_DWORD *)(a1 + 592);
    ++v5;
  }
  while ( !v5 );
  return v6 >= 0;
}

```

## disassembly

```asm
0x18001fcf0  mov     [rsp+arg_0], rbx
0x18001fcf5  mov     [rsp+arg_8], rsi
0x18001fcfa  push    rdi
0x18001fcfb  sub     rsp, 20h
0x18001fcff  lea     eax, [rdx+1]
0x18001fd02  mov     esi, edx
0x18001fd04  mov     rbx, rcx
0x18001fd07  cmp     eax, [rcx+250h]
0x18001fd0d  jbe     short loc_18001FD13
0x18001fd0f  xor     eax, eax
0x18001fd11  jmp     short loc_18001FD35
0x18001fd13  xor     edi, edi
0x18001fd15  mov     edx, esi
0x18001fd17  mov     rcx, rbx
0x18001fd1a  call    ?RemoveValue@?$CTSparseBlock@KUMETADATA_REC@CASFV1MetadataObject@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFV1MetadataObject::METADATA_REC,20,0>::RemoveValue(ulong)
0x18001fd1f  test    eax, eax
0x18001fd21  js      short loc_18001FD30
0x18001fd23  dec     dword ptr [rbx+250h]
0x18001fd29  inc     edi
0x18001fd2b  cmp     edi, 1
0x18001fd2e  jb      short loc_18001FD15
0x18001fd30  not     eax
0x18001fd32  shr     eax, 1Fh
0x18001fd35  mov     rbx, [rsp+28h+arg_0]
0x18001fd3a  mov     rsi, [rsp+28h+arg_8]
0x18001fd3f  add     rsp, 20h
0x18001fd43  pop     rdi
0x18001fd44  retn
```
