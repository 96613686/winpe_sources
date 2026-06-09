# BasepCheckDotLocalExists

- ea: `0x1800060c0`
- end: `0x1800061a4`
- name: `BasepCheckDotLocalExists`
- size: `228`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002c50`

## callees

- `0x1800060c0`
- `0x180006568`
- `0x180006574`
- `0x1800065bc`
- `0x180006c07`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180006169`
- `ntdll!RtlDoesFileExists_U` at `0x180006169`

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
0x1800060c0  mov     [rsp+arg_8], rbx
0x1800060c5  push    rdi
0x1800060c6  sub     rsp, 30h
0x1800060ca  movzx   eax, word ptr [rcx]
0x1800060cd  mov     rbx, rcx
0x1800060d0  mov     ecx, 0FFF1h
0x1800060d5  xorps   xmm0, xmm0
0x1800060d8  mov     rdi, r8
0x1800060db  movups  xmmword ptr [rsp+38h+Destination.Length], xmm0
0x1800060e0  mov     [rsp+38h+Destination.Length], ax
0x1800060e5  cmp     ax, cx
0x1800060e8  jbe     short loc_1800060F4
0x1800060ea  mov     eax, 0C0000106h
0x1800060ef  jmp     loc_180006198
0x1800060f4  add     ax, 0Eh
0x1800060f8  mov     [rsp+38h+arg_0], rsi
0x1800060fd  movzx   r8d, ax; Size
0x180006101  xor     edx, edx; Flags
0x180006103  mov     [rsp+38h+Destination.MaximumLength], r8w
0x180006109  mov     rcx, gs:60h
0x180006112  mov     rcx, [rcx+30h]; HeapHandle
0x180006116  call    RtlAllocateHeap_0
0x18000611b  mov     rsi, rax
0x18000611e  test    rax, rax
0x180006121  jnz     short loc_18000612A
0x180006123  mov     eax, 0C0000017h
0x180006128  jmp     short loc_180006193
0x18000612a  movzx   r8d, [rsp+38h+Destination.Length]; Size
0x180006130  mov     rcx, rsi; void *
0x180006133  mov     rdx, [rbx+8]; Src
0x180006137  call    memcpy_0
0x18000613c  lea     rdx, aLocal; ".Local"
0x180006143  mov     [rsp+38h+Destination.Buffer], rsi
0x180006148  lea     rcx, [rsp+38h+Destination]; Destination
0x18000614d  call    RtlAppendUnicodeToString_0
0x180006152  mov     ebx, eax
0x180006154  test    eax, eax
0x180006156  js      short loc_18000617A
0x180006158  movzx   ecx, [rsp+38h+Destination.Length]
0x18000615d  xor     eax, eax
0x18000615f  shr     rcx, 1
0x180006162  mov     [rsi+rcx*2], ax
0x180006166  mov     rcx, rsi; FileName
0x180006169  call    cs:__imp_RtlDoesFileExists_U
0x180006170  nop     dword ptr [rax+rax+00h]
0x180006175  movzx   ecx, al
0x180006178  mov     [rdi], ecx
0x18000617a  mov     rcx, gs:60h
0x180006183  mov     r8, rsi; P
0x180006186  xor     edx, edx; Flags
0x180006188  mov     rcx, [rcx+30h]; HeapHandle
0x18000618c  call    RtlFreeHeap_0
0x180006191  mov     eax, ebx
0x180006193  mov     rsi, [rsp+38h+arg_0]
0x180006198  mov     rbx, [rsp+38h+arg_8]
0x18000619d  add     rsp, 30h
0x1800061a1  pop     rdi
0x1800061a2  retn
```
