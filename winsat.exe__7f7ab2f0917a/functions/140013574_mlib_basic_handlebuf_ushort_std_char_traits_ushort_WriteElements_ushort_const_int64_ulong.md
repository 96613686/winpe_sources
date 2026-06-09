# mlib::basic_handlebuf<ushort,std::char_traits<ushort>>::WriteElements(ushort const *,__int64,ulong *)

- ea: `0x140013574`
- end: `0x140013624`
- name: `?WriteElements@?$basic_handlebuf@GU?$char_traits@G@std@@@mlib@@AEAAKPEBG_JPEAK@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140013824`

## callees

- `0x1400049bc`
- `0x140013574`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x1400135ed`
- `KERNEL32!WriteConsoleW` at `0x1400135ed`
- `KERNEL32!WriteFile` at `0x1400135c5`
- `KERNEL32!WriteFile` at `0x140013607`
- `KERNEL32!WriteFile` at `0x1400135c5`
- `KERNEL32!WriteFile` at `0x140013607`
- `KERNEL32!WriteConsoleA` at `0x1400135bd`
- `KERNEL32!WriteConsoleA` at `0x1400135bd`

## pseudocode

```c
BOOL __fastcall mlib::basic_handlebuf<unsigned short,std::char_traits<unsigned short>>::WriteElements(
        __int64 a1,
        const void *a2,
        DWORD a3,
        DWORD *a4)
{
  __int64 v6; // rax
  const void *v7; // rdx
  void *v8; // rcx
  bool v10; // zf
  void *v11; // rcx
  BOOL v12; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 204) )
  {
    v6 = mlib::basic_handlebuf<unsigned short,std::char_traits<unsigned short>>::TranscodeBuffer<unsigned short>();
    if ( v6 )
    {
      v7 = *(const void **)(a1 + 208);
      v8 = *(void **)(a1 + 136);
      if ( *(_BYTE *)(a1 + 192) )
        return WriteConsoleA(v8, v7, v6, a4, 0);
      else
        return WriteFile(v8, v7, v6, a4, 0);
    }
    else
    {
      return 1;
    }
  }
  else
  {
    v10 = *(_BYTE *)(a1 + 192) == 0;
    v11 = *(void **)(a1 + 136);
    if ( !v10 )
      return WriteConsoleW(v11, a2, a3, a4, 0);
    NumberOfBytesWritten = 0;
    v12 = WriteFile(v11, a2, 2 * a3, &NumberOfBytesWritten, 0);
    *a4 = NumberOfBytesWritten >> 1;
    return v12;
  }
}

```

## disassembly

```asm
0x140013574  mov     [rsp+arg_8], rbx
0x140013579  push    rdi
0x14001357a  sub     rsp, 30h
0x14001357e  cmp     dword ptr [rcx+0CCh], 0
0x140013585  mov     rdi, r9
0x140013588  mov     rbx, rcx
0x14001358b  jz      short loc_1400135D4
0x14001358d  call    ??$TranscodeBuffer@G@?$basic_handlebuf@GU?$char_traits@G@std@@@mlib@@AEAA_KPEBG_J@Z; mlib::basic_handlebuf<ushort,std::char_traits<ushort>>::TranscodeBuffer<ushort>(ushort const *,__int64)
0x140013592  test    rax, rax
0x140013595  jz      short loc_1400135CD
0x140013597  cmp     byte ptr [rbx+0C0h], 0
0x14001359e  mov     r9, rdi; lpNumberOfBytesWritten
0x1400135a1  mov     rdx, [rbx+0D0h]; lpBuffer
0x1400135a8  mov     r8d, eax; nNumberOfBytesToWrite
0x1400135ab  mov     rcx, [rbx+88h]; hFile
0x1400135b2  mov     [rsp+38h+lpReserved], 0; lpOverlapped
0x1400135bb  jz      short loc_1400135C5
0x1400135bd  call    cs:__imp_WriteConsoleA
0x1400135c3  jmp     short loc_140013619
0x1400135c5  call    cs:__imp_WriteFile
0x1400135cb  jmp     short loc_140013619
0x1400135cd  mov     eax, 1
0x1400135d2  jmp     short loc_140013619
0x1400135d4  cmp     byte ptr [rbx+0C0h], 0
0x1400135db  mov     rcx, [rcx+88h]; hFile
0x1400135e2  mov     [rsp+38h+lpReserved], 0; lpOverlapped
0x1400135eb  jz      short loc_1400135F7
0x1400135ed  call    cs:__imp_WriteConsoleW
0x1400135f3  mov     ecx, eax
0x1400135f5  jmp     short loc_140013617
0x1400135f7  add     r8d, r8d; nNumberOfBytesToWrite
0x1400135fa  mov     [rsp+38h+NumberOfBytesWritten], 0
0x140013602  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140013607  call    cs:__imp_WriteFile
0x14001360d  mov     ecx, eax
0x14001360f  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x140013613  shr     eax, 1
0x140013615  mov     [rdi], eax
0x140013617  mov     eax, ecx
0x140013619  mov     rbx, [rsp+38h+arg_8]
0x14001361e  add     rsp, 30h
0x140013622  pop     rdi
0x140013623  retn
```
