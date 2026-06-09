# CleanupFormatPluginList

- ea: `0x14001876c`
- end: `0x1400187d6`
- name: `CleanupFormatPluginList`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400110f0`

## callees

- `0x14001876c`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400187b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400187b3`

## pseudocode

```c
__int64 __fastcall CleanupFormatPluginList(__int64 a1)
{
  void **v1; // rdi
  void ***v2; // rbx
  void **v3; // rax

  v1 = (void **)(a1 + 592);
  while ( 1 )
  {
    v2 = (void ***)*v1;
    if ( *v1 == v1 )
      break;
    if ( v2[1] != v1 || (v3 = *v2, (*v2)[1] != v2) )
      __fastfail(3u);
    *v1 = v3;
    v3[1] = v1;
    (*((void (__fastcall **)(void **))*v2[4] + 2))(v2[4]);
    ExFreePoolWithTag(v2, 0x56425355u);
  }
  return 0;
}

```

## disassembly

```asm
0x14001876c  mov     [rsp+arg_0], rbx
0x140018771  push    rdi
0x140018772  sub     rsp, 20h
0x140018776  lea     rdi, [rcx+250h]
0x14001877d  mov     rbx, [rdi]
0x140018780  cmp     rbx, rdi
0x140018783  jz      short loc_1400187C8
0x140018785  cmp     [rbx+8], rdi
0x140018789  jnz     short loc_1400187C1
0x14001878b  mov     rax, [rbx]
0x14001878e  cmp     [rax+8], rbx
0x140018792  jnz     short loc_1400187C1
0x140018794  mov     [rdi], rax
0x140018797  mov     [rax+8], rdi
0x14001879b  mov     rcx, [rbx+20h]
0x14001879f  mov     rax, [rcx]
0x1400187a2  mov     rax, [rax+10h]
0x1400187a6  call    _guard_dispatch_icall
0x1400187ab  mov     edx, 56425355h; Tag
0x1400187b0  mov     rcx, rbx; P
0x1400187b3  call    cs:__imp_ExFreePoolWithTag
0x1400187ba  nop     dword ptr [rax+rax+00h]
0x1400187bf  jmp     short loc_14001877D
0x1400187c1  mov     ecx, 3
0x1400187c6  int     29h; Win8: RtlFailFast(ecx)
0x1400187c8  mov     rbx, [rsp+28h+arg_0]
0x1400187cd  xor     eax, eax
0x1400187cf  add     rsp, 20h
0x1400187d3  pop     rdi
0x1400187d4  retn
```
