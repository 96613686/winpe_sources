# SC_BUFFER::~SC_BUFFER(void)

- ea: `0x14000fcd0`
- end: `0x14000fd85`
- name: `??1SC_BUFFER@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(SC_BUFFER *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400264f0`
- `0x140032e80`
- `0x1400391c8`
- `0x14003b2ec`
- `0x14005417c`
- `0x1400594e0`
- `0x140059c9c`
- `0x14005b76c`
- `0x14005bd7c`
- `0x14005bda0`
- `0x1400b0a44`

## callees

- `0x14000fcd0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000fd2e`
- `ntoskrnl!IoFreeMdl` at `0x14000fd2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fd77`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fd1a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000fd1a`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000fd64`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000fd64`

## pseudocode

```c
void __fastcall SC_BUFFER::~SC_BUFFER(SC_BUFFER *this)
{
  int v1; // eax
  struct _MDL *v3; // rdi

  v1 = *(_DWORD *)this;
  v3 = (struct _MDL *)*((_QWORD *)this + 1);
  if ( *(_DWORD *)this == 3 )
  {
    if ( *((_WORD *)this + 2) == 0xFFFF )
      ExFreePoolWithTag((char *)v3->StartVa + v3->ByteOffset, 0);
    else
      ExFreeToNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                               + ((unsigned __int64)*((unsigned __int16 *)this + 2) << 7)),
        (char *)v3->StartVa + v3->ByteOffset);
  }
  else if ( v1 != 2 )
  {
    if ( v1 != 4 )
      goto LABEL_6;
    MmFreePagesFromMdl(v3);
  }
  if ( v3 )
    IoFreeMdl(v3);
LABEL_6:
  *((_WORD *)this + 2) = -1;
  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x14000fcd0  mov     [rsp+arg_0], rbx
0x14000fcd5  mov     [rsp+arg_8], rsi
0x14000fcda  push    rdi
0x14000fcdb  sub     rsp, 20h
0x14000fcdf  mov     eax, [rcx]
0x14000fce1  mov     rbx, rcx
0x14000fce4  mov     rdi, [rcx+8]
0x14000fce8  mov     esi, 0FFFFh
0x14000fced  cmp     eax, 3
0x14000fcf0  jnz     short loc_14000FD57
0x14000fcf2  mov     r8d, [rdi+2Ch]
0x14000fcf6  add     r8, [rdi+20h]
0x14000fcfa  movzx   edx, word ptr [rcx+4]
0x14000fcfe  cmp     dx, si
0x14000fd01  jz      short loc_14000FD72
0x14000fd03  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000fd0a  mov     ecx, edx
0x14000fd0c  shl     rcx, 7
0x14000fd10  mov     rdx, r8; Entry
0x14000fd13  add     rcx, [rax+168h]; Lookaside
0x14000fd1a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000fd21  nop     dword ptr [rax+rax+00h]
0x14000fd26  test    rdi, rdi
0x14000fd29  jz      short loc_14000FD3A
0x14000fd2b  mov     rcx, rdi; Mdl
0x14000fd2e  call    cs:__imp_IoFreeMdl
0x14000fd35  nop     dword ptr [rax+rax+00h]
0x14000fd3a  xor     eax, eax
0x14000fd3c  mov     [rbx+4], si
0x14000fd40  mov     rsi, [rsp+28h+arg_8]
0x14000fd45  mov     [rbx], eax
0x14000fd47  mov     [rbx+8], rax
0x14000fd4b  mov     rbx, [rsp+28h+arg_0]
0x14000fd50  add     rsp, 20h
0x14000fd54  pop     rdi
0x14000fd55  retn
0x14000fd57  cmp     eax, 2
0x14000fd5a  jz      short loc_14000FD26
0x14000fd5c  cmp     eax, 4
0x14000fd5f  jnz     short loc_14000FD3A
0x14000fd61  mov     rcx, rdi; MemoryDescriptorList
0x14000fd64  call    cs:__imp_MmFreePagesFromMdl
0x14000fd6b  nop     dword ptr [rax+rax+00h]
0x14000fd70  jmp     short loc_14000FD26
0x14000fd72  xor     edx, edx; Tag
0x14000fd74  mov     rcx, r8; P
0x14000fd77  call    cs:__imp_ExFreePoolWithTag
0x14000fd7e  nop     dword ptr [rax+rax+00h]
0x14000fd83  jmp     short loc_14000FD26
```
