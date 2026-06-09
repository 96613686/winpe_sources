# VmpQueryRootId(VM_ROOT_EXTENSION *,_IRP *)

- ea: `0x140013428`
- end: `0x1400134c0`
- name: `?VmpQueryRootId@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_IRP@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140016aa0`

## callees

- `0x140005240`
- `0x140013428`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140013480`
- `ntoskrnl!ExAllocatePool2` at `0x140013480`

## pseudocode

```c
__int64 __fastcall VmpQueryRootId(struct VM_ROOT_EXTENSION *a1, struct _IRP *a2)
{
  ULONG Length; // r8d
  ULONG v4; // r8d
  __int64 result; // rax
  const wchar_t *v6; // rdi
  size_t v7; // rbx
  void *Pool2; // rax
  ULONG_PTR v9; // rsi

  Length = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( Length && (v4 = Length - 1) != 0 )
  {
    if ( v4 != 2 )
      return 3221225659LL;
    v6 = L"0000";
    v7 = 10;
  }
  else
  {
    v6 = L"ROOT\\VOLMGR";
    v7 = 24;
  }
  Pool2 = (void *)ExAllocatePool2(258, v7 + 2, 538987862);
  v9 = (ULONG_PTR)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memmove(Pool2, v6, v7);
  result = 0;
  a2->IoStatus.Information = v9;
  *(_WORD *)(v9 + 2 * (v7 >> 1)) = 0;
  return result;
}

```

## disassembly

```asm
0x140013428  push    rbx
0x14001342a  push    rbp
0x14001342b  push    rsi
0x14001342c  push    rdi
0x14001342d  sub     rsp, 28h
0x140013431  mov     rcx, [rdx+0B8h]
0x140013438  mov     rbp, rdx
0x14001343b  mov     r8d, [rcx+8]
0x14001343f  test    r8d, r8d
0x140013442  jz      short loc_140013465
0x140013444  sub     r8d, 1
0x140013448  jz      short loc_140013465
0x14001344a  cmp     r8d, 2
0x14001344e  jz      short loc_140013457
0x140013450  mov     eax, 0C00000BBh
0x140013455  jmp     short loc_1400134B6
0x140013457  lea     rdi, a0000; "0000"
0x14001345e  mov     ebx, 0Ah
0x140013463  jmp     short loc_140013471
0x140013465  lea     rdi, aRootVolmgr; "ROOT\\VOLMGR"
0x14001346c  mov     ebx, 18h
0x140013471  lea     rdx, [rbx+2]
0x140013475  mov     ecx, 102h
0x14001347a  mov     r8d, 20204D56h
0x140013480  call    cs:__imp_ExAllocatePool2
0x140013487  nop     dword ptr [rax+rax+00h]
0x14001348c  mov     rsi, rax
0x14001348f  test    rax, rax
0x140013492  jnz     short loc_14001349B
0x140013494  mov     eax, 0C000009Ah
0x140013499  jmp     short loc_1400134B6
0x14001349b  mov     r8, rbx; Size
0x14001349e  mov     rdx, rdi; Src
0x1400134a1  mov     rcx, rsi; void *
0x1400134a4  call    memmove
0x1400134a9  shr     rbx, 1
0x1400134ac  xor     eax, eax
0x1400134ae  mov     [rbp+38h], rsi
0x1400134b2  mov     [rsi+rbx*2], ax
0x1400134b6  add     rsp, 28h
0x1400134ba  pop     rdi
0x1400134bb  pop     rsi
0x1400134bc  pop     rbp
0x1400134bd  pop     rbx
0x1400134be  retn
```
