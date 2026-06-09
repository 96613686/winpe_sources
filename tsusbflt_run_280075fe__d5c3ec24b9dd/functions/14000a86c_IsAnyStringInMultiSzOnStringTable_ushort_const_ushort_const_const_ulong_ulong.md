# IsAnyStringInMultiSzOnStringTable(ushort const *,ushort const * * const,ulong,ulong *)

- ea: `0x14000a86c`
- end: `0x14000a903`
- name: `?IsAnyStringInMultiSzOnStringTable@@YAEPEBGQEAPEBGKPEAK@Z`
- size: `151`
- prototype: `unsigned __int8 __fastcall(wchar_t *Str1, const unsigned __int16 **const, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001e80`
- `0x1400092a4`
- `0x140012010`

## callees

- `0x14000a86c`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x14000a899`
- `ntoskrnl!_wcsicmp` at `0x14000a899`

## pseudocode

```c
unsigned __int8 __fastcall IsAnyStringInMultiSzOnStringTable(
        wchar_t *Str1,
        const unsigned __int16 **const a2,
        unsigned int a3,
        unsigned int *a4)
{
  wchar_t *v6; // rdi
  char v7; // r9
  int v8; // ebx
  __int64 v9; // rdx
  wchar_t *v10; // rax

  v6 = Str1;
  v7 = 0;
  if ( *Str1 )
  {
    while ( 1 )
    {
      v8 = 0;
      if ( a3 )
        break;
LABEL_5:
      v7 = 0;
      v9 = 0xFFFF;
      v10 = v6;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v9;
      }
      while ( v9 );
      if ( v9 )
      {
        v6 += ((0xFFFF - v9) & -(__int64)(v9 != 0)) + 1;
        if ( *v6 )
          continue;
      }
      return v7;
    }
    while ( _wcsicmp(v6, a2[v8]) )
    {
      if ( ++v8 >= a3 )
        goto LABEL_5;
    }
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x14000a86c  push    rbx
0x14000a86e  push    rbp
0x14000a86f  push    rsi
0x14000a870  push    rdi
0x14000a871  push    r14
0x14000a873  sub     rsp, 20h
0x14000a877  xor     ebp, ebp
0x14000a879  mov     esi, r8d
0x14000a87c  mov     r14, rdx
0x14000a87f  mov     rdi, rcx
0x14000a882  mov     r9b, bpl
0x14000a885  cmp     [rcx], bp
0x14000a888  jz      short loc_14000A8F4
0x14000a88a  mov     ebx, ebp
0x14000a88c  test    esi, esi
0x14000a88e  jz      short loc_14000A8AF
0x14000a890  mov     edx, ebx
0x14000a892  mov     rcx, rdi; Str1
0x14000a895  mov     rdx, [r14+rdx*8]; Str2
0x14000a899  call    cs:__imp__wcsicmp
0x14000a8a0  nop     dword ptr [rax+rax+00h]
0x14000a8a5  test    eax, eax
0x14000a8a7  jz      short loc_14000A8F1
0x14000a8a9  inc     ebx
0x14000a8ab  cmp     ebx, esi
0x14000a8ad  jb      short loc_14000A890
0x14000a8af  mov     r9b, bpl
0x14000a8b2  mov     edx, 0FFFFh
0x14000a8b7  mov     rax, rdi
0x14000a8ba  cmp     [rax], bp
0x14000a8bd  jz      short loc_14000A8C9
0x14000a8bf  add     rax, 2
0x14000a8c3  sub     rdx, 1
0x14000a8c7  jnz     short loc_14000A8BA
0x14000a8c9  mov     ecx, 0FFFFh
0x14000a8ce  mov     rax, rdx
0x14000a8d1  sub     rcx, rdx
0x14000a8d4  neg     rax
0x14000a8d7  sbb     r8, r8
0x14000a8da  and     r8, rcx
0x14000a8dd  test    rdx, rdx
0x14000a8e0  jz      short loc_14000A8F4
0x14000a8e2  lea     rdi, [rdi+r8*2]
0x14000a8e6  add     rdi, 2
0x14000a8ea  cmp     [rdi], bp
0x14000a8ed  jnz     short loc_14000A88A
0x14000a8ef  jmp     short loc_14000A8F4
0x14000a8f1  mov     r9b, 1
0x14000a8f4  mov     al, r9b
0x14000a8f7  add     rsp, 20h
0x14000a8fb  pop     r14
0x14000a8fd  pop     rdi
0x14000a8fe  pop     rsi
0x14000a8ff  pop     rbp
0x14000a900  pop     rbx
0x14000a901  retn
```
