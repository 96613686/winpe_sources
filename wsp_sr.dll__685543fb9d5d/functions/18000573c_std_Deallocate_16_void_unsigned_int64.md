# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x18000573c`
- end: `0x180005774`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `61`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800057e0`
- `0x1800066d0`
- `0x180006724`
- `0x180007a68`
- `0x180007f1c`
- `0x18000898c`
- `0x1800089f0`
- `0x180008a18`
- `0x18000d2d8`
- `0x18000d6e8`
- `0x18000d7b0`
- `0x18000d7d0`
- `0x18000da30`
- `0x18000daf0`
- `0x18000dd40`
- `0x1800100a8`
- `0x180010354`
- `0x1800104f0`
- `0x18001075c`
- `0x180010998`
- `0x180010b34`
- `0x180010d90`
- `0x1800134d4`
- `0x180015a90`
- `0x180015c34`
- `0x180017050`
- `0x180017140`
- `0x180017270`
- `0x180017564`
- `0x180017728`
- `0x18001774c`
- `0x1800177bc`
- `0x180017804`
- `0x18001790c`
- `0x180017930`
- `0x180018edc`
- `0x180018f28`
- `0x18001919c`
- `0x18001a4dc`
- `0x18001a598`
- `0x18001cfe8`
- `0x18001d38c`
- `0x18001d3f0`
- `0x18001d42c`
- `0x18001fe00`
- `0x18001fe20`
- `0x1800207dc`
- `0x180021100`
- `0x180021a08`
- `0x180021d34`

## callees

- `0x180002540`
- `0x18000573c`
- `0x1800065d0`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    a1 = v2;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x18000573c  mov     rax, rsp
0x18000573f  mov     [rax+10h], rdx
0x180005743  mov     [rax+8], rcx
0x180005747  sub     rsp, 28h
0x18000574b  cmp     rdx, 1000h
0x180005752  jb      short loc_18000576B
0x180005754  lea     rdx, [rax+10h]; unsigned __int64 *
0x180005758  lea     rcx, [rax+8]; void **
0x18000575c  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180005761  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x180005766  mov     rcx, [rsp+28h+arg_0]; void *
0x18000576b  add     rsp, 28h
0x18000576f  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
