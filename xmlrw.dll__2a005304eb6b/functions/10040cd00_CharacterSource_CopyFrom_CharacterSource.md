# CharacterSource::CopyFrom(CharacterSource &)

- ea: `0x10040cd00`
- end: `0x10040ce02`
- name: `?CopyFrom@CharacterSource@@MEAAXAEAV1@@Z`
- size: `258`
- prototype: `void __fastcall(CharacterSource *__hidden this, struct CharacterSource *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x10040cd00`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040cd4e`
- `KERNEL32!HeapFree` at `0x10040cd4e`

## pseudocode

```c
void __fastcall CharacterSource::CopyFrom(CharacterSource *this, struct CharacterSource *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
  }
  v6 = *(_QWORD *)this;
  v7 = (*(__int64 (__fastcall **)(struct CharacterSource *))(*(_QWORD *)a2 + 40LL))(a2);
  (*(void (__fastcall **)(CharacterSource *, __int64))(v6 + 48))(this, v7);
  *((_BYTE *)this + 24) = *((_BYTE *)a2 + 24);
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 7);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 6);
  *((_QWORD *)this + 7) = *((_QWORD *)a2 + 7);
  *((_QWORD *)this + 8) = *((_QWORD *)a2 + 8);
  *((_QWORD *)this + 9) = *((_QWORD *)a2 + 9);
  *((_QWORD *)this + 10) = *((_QWORD *)a2 + 10);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 22);
  *((_QWORD *)this + 12) = *((_QWORD *)a2 + 12);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_QWORD *)this + 14) = *((_QWORD *)a2 + 14);
  *((_DWORD *)this + 30) = *((_DWORD *)a2 + 30);
  *((_QWORD *)this + 16) = *((_QWORD *)a2 + 16);
  *((_QWORD *)a2 + 5) = 0;
}

```

## disassembly

```asm
0x10040cd00  mov     [rsp+arg_0], rbx
0x10040cd05  mov     [rsp+arg_8], rsi
0x10040cd0a  push    rdi
0x10040cd0b  sub     rsp, 20h
0x10040cd0f  mov     r8, [rcx+28h]; lpMem
0x10040cd13  mov     rsi, rdx
0x10040cd16  mov     rdi, rcx
0x10040cd19  test    r8, r8
0x10040cd1c  jz      short loc_10040CD54
0x10040cd1e  mov     rcx, [rcx+8]
0x10040cd22  test    rcx, rcx
0x10040cd25  jnz     short loc_10040CD33
0x10040cd27  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040cd2e  test    rcx, rcx
0x10040cd31  jz      short loc_10040CD45
0x10040cd33  mov     rax, [rcx]
0x10040cd36  mov     rdx, r8
0x10040cd39  mov     rax, [rax+28h]
0x10040cd3d  call    cs:__guard_dispatch_icall_fptr
0x10040cd43  jmp     short loc_10040CD54
0x10040cd45  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040cd4c  xor     edx, edx; dwFlags
0x10040cd4e  call    cs:__imp_HeapFree
0x10040cd54  mov     rax, [rsi]
0x10040cd57  mov     rcx, rsi
0x10040cd5a  mov     rbx, [rdi]
0x10040cd5d  mov     rax, [rax+28h]
0x10040cd61  call    cs:__guard_dispatch_icall_fptr
0x10040cd67  mov     rdx, rax
0x10040cd6a  mov     rcx, rdi
0x10040cd6d  mov     rax, [rbx+30h]
0x10040cd71  call    cs:__guard_dispatch_icall_fptr
0x10040cd77  movzx   eax, byte ptr [rsi+18h]
0x10040cd7b  mov     rbx, [rsp+28h+arg_0]
0x10040cd80  mov     [rdi+18h], al
0x10040cd83  mov     eax, [rsi+1Ch]
0x10040cd86  mov     [rdi+1Ch], eax
0x10040cd89  mov     eax, [rsi+20h]
0x10040cd8c  mov     [rdi+20h], eax
0x10040cd8f  mov     rax, [rsi+28h]
0x10040cd93  mov     [rdi+28h], rax
0x10040cd97  mov     rax, [rsi+30h]
0x10040cd9b  mov     [rdi+30h], rax
0x10040cd9f  mov     rax, [rsi+38h]
0x10040cda3  mov     [rdi+38h], rax
0x10040cda7  mov     rax, [rsi+40h]
0x10040cdab  mov     [rdi+40h], rax
0x10040cdaf  mov     rax, [rsi+48h]
0x10040cdb3  mov     [rdi+48h], rax
0x10040cdb7  mov     rax, [rsi+50h]
0x10040cdbb  mov     [rdi+50h], rax
0x10040cdbf  mov     eax, [rsi+58h]
0x10040cdc2  mov     [rdi+58h], eax
0x10040cdc5  mov     rax, [rsi+60h]
0x10040cdc9  mov     [rdi+60h], rax
0x10040cdcd  mov     eax, [rsi+68h]
0x10040cdd0  mov     [rdi+68h], eax
0x10040cdd3  mov     rax, [rsi+70h]
0x10040cdd7  mov     [rdi+70h], rax
0x10040cddb  mov     eax, [rsi+78h]
0x10040cdde  mov     [rdi+78h], eax
0x10040cde1  mov     rax, [rsi+80h]
0x10040cde8  mov     [rdi+80h], rax
0x10040cdef  mov     qword ptr [rsi+28h], 0
0x10040cdf7  mov     rsi, [rsp+28h+arg_8]
0x10040cdfc  add     rsp, 20h
0x10040ce00  pop     rdi
0x10040ce01  retn
```
