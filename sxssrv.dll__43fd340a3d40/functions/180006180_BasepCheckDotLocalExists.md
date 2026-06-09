# BasepCheckDotLocalExists

- ea: `0x180006180`
- end: `0x180006264`
- name: `BasepCheckDotLocalExists`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002d40`

## callees

- `0x180006180`
- `0x18000663c`
- `0x180006648`
- `0x180006690`
- `0x180006cc1`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180006229`
- `ntdll!RtlDoesFileExists_U` at `0x180006229`

## pseudocode

```c
__int64 __fastcall BasepCheckDotLocalExists(__int64 a1, __int64 a2, _DWORD *a3)
{
  USHORT v3; // ax
  WCHAR *Heap_0; // rax
  WCHAR *v8; // rsi
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-18h] BYREF

  v3 = *(_WORD *)a1;
  Destination = 0;
  Destination.Length = v3;
  if ( v3 > 0xFFF1u )
    return 3221225734LL;
  Destination.MaximumLength = v3 + 14;
  Heap_0 = (WCHAR *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(v3 + 14));
  v8 = Heap_0;
  if ( !Heap_0 )
    return 3221225495LL;
  memcpy_0(Heap_0, *(const void **)(a1 + 8), Destination.Length);
  Destination.Buffer = v8;
  appended = RtlAppendUnicodeToString_0(&Destination, L".Local");
  if ( appended >= 0 )
  {
    v8[(unsigned __int64)Destination.Length >> 1] = 0;
    *a3 = RtlDoesFileExists_U(v8);
  }
  RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180006180  mov     [rsp+arg_8], rbx
0x180006185  push    rdi
0x180006186  sub     rsp, 30h
0x18000618a  movzx   eax, word ptr [rcx]
0x18000618d  mov     rbx, rcx
0x180006190  mov     ecx, 0FFF1h
0x180006195  xorps   xmm0, xmm0
0x180006198  mov     rdi, r8
0x18000619b  movups  xmmword ptr [rsp+38h+Destination.Length], xmm0
0x1800061a0  mov     [rsp+38h+Destination.Length], ax
0x1800061a5  cmp     ax, cx
0x1800061a8  jbe     short loc_1800061B4
0x1800061aa  mov     eax, 0C0000106h
0x1800061af  jmp     loc_180006258
0x1800061b4  add     ax, 0Eh
0x1800061b8  mov     [rsp+38h+arg_0], rsi
0x1800061bd  movzx   r8d, ax; Size
0x1800061c1  xor     edx, edx; Flags
0x1800061c3  mov     [rsp+38h+Destination.MaximumLength], r8w
0x1800061c9  mov     rcx, gs:60h
0x1800061d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800061d6  call    RtlAllocateHeap_0
0x1800061db  mov     rsi, rax
0x1800061de  test    rax, rax
0x1800061e1  jnz     short loc_1800061EA
0x1800061e3  mov     eax, 0C0000017h
0x1800061e8  jmp     short loc_180006253
0x1800061ea  movzx   r8d, [rsp+38h+Destination.Length]; Size
0x1800061f0  mov     rcx, rsi; void *
0x1800061f3  mov     rdx, [rbx+8]; Src
0x1800061f7  call    memcpy_0
0x1800061fc  lea     rdx, aLocal; ".Local"
0x180006203  mov     [rsp+38h+Destination.Buffer], rsi
0x180006208  lea     rcx, [rsp+38h+Destination]; Destination
0x18000620d  call    RtlAppendUnicodeToString_0
0x180006212  mov     ebx, eax
0x180006214  test    eax, eax
0x180006216  js      short loc_18000623A
0x180006218  movzx   eax, [rsp+38h+Destination.Length]
0x18000621d  xor     ecx, ecx
0x18000621f  shr     rax, 1
0x180006222  mov     [rsi+rax*2], cx
0x180006226  mov     rcx, rsi; FileName
0x180006229  call    cs:__imp_RtlDoesFileExists_U
0x180006230  nop     dword ptr [rax+rax+00h]
0x180006235  movzx   eax, al
0x180006238  mov     [rdi], eax
0x18000623a  mov     rcx, gs:60h
0x180006243  mov     r8, rsi; P
0x180006246  xor     edx, edx; Flags
0x180006248  mov     rcx, [rcx+30h]; HeapHandle
0x18000624c  call    RtlFreeHeap_0
0x180006251  mov     eax, ebx
0x180006253  mov     rsi, [rsp+38h+arg_0]
0x180006258  mov     rbx, [rsp+38h+arg_8]
0x18000625d  add     rsp, 30h
0x180006261  pop     rdi
0x180006262  retn
```
