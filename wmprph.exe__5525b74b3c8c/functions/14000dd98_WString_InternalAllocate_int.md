# WString::InternalAllocate(int)

- ea: `0x14000dd98`
- end: `0x14000de44`
- name: `?InternalAllocate@WString@@IEBAPEAGH@Z`
- size: `172`
- prototype: `unsigned __int16 *__fastcall(WString *__hidden this, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000da00`
- `0x14000dcf8`
- `0x14000dee0`
- `0x14000e078`

## callees

- `0x140001054`
- `0x14000dd98`
- `0x14000f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000ddba`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14000ddba`

## pseudocode

```c
BSTR __fastcall WString::InternalAllocate(WString *this, int a2)
{
  UINT v3; // edx
  __int64 v5; // rdi
  int v6; // eax
  _WORD *v7; // rax

  if ( (*((_BYTE *)this + 12) & 4) != 0 )
  {
    v3 = a2 - 1;
    if ( a2 <= 0 )
      v3 = 0;
    return SysAllocStringLen(0, v3);
  }
  else
  {
    v5 = 0;
    if ( g_pStringHeap
      && (v5 = (*(__int64 (__fastcall **)(struct IStringHeap *))(*(_QWORD *)g_pStringHeap + 24LL))(g_pStringHeap)) != 0 )
    {
      (*(void (__fastcall **)(struct IStringHeap *))(*(_QWORD *)g_pStringHeap + 8LL))(g_pStringHeap);
    }
    else
    {
      v6 = 1;
      if ( a2 )
        v6 = a2;
      if ( v6 > 0 )
      {
        v7 = operator new[](saturated_mul(v6, 2u));
        v5 = (__int64)v7;
        if ( v7 )
          *v7 = 0;
      }
    }
    return (BSTR)v5;
  }
}

```

## disassembly

```asm
0x14000dd98  mov     [rsp+arg_0], rbx
0x14000dd9d  mov     [rsp+arg_8], rsi
0x14000dda2  push    rdi
0x14000dda3  sub     rsp, 20h
0x14000dda7  xor     ebx, ebx
0x14000dda9  mov     esi, edx
0x14000ddab  test    byte ptr [rcx+0Ch], 4
0x14000ddaf  jz      short loc_14000DDC2
0x14000ddb1  dec     edx
0x14000ddb3  test    esi, esi
0x14000ddb5  cmovle  edx, ebx; ui
0x14000ddb8  xor     ecx, ecx; strIn
0x14000ddba  call    cs:__imp_SysAllocStringLen
0x14000ddc0  jmp     short loc_14000DE34
0x14000ddc2  mov     rcx, cs:?g_pStringHeap@@3PEAVIStringHeap@@EA; IStringHeap * g_pStringHeap
0x14000ddc9  mov     rdi, rbx
0x14000ddcc  test    rcx, rcx
0x14000ddcf  jz      short loc_14000DDFA
0x14000ddd1  mov     rax, [rcx]
0x14000ddd4  mov     rax, [rax+18h]
0x14000ddd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dddd  mov     rdi, rax
0x14000dde0  test    rax, rax
0x14000dde3  jz      short loc_14000DDFA
0x14000dde5  mov     rcx, cs:?g_pStringHeap@@3PEAVIStringHeap@@EA; IStringHeap * g_pStringHeap
0x14000ddec  mov     rdx, [rcx]
0x14000ddef  mov     rax, [rdx+8]
0x14000ddf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddf8  jmp     short loc_14000DE31
0x14000ddfa  test    esi, esi
0x14000ddfc  mov     eax, 1
0x14000de01  cmovnz  eax, esi
0x14000de04  test    eax, eax
0x14000de06  jle     short loc_14000DE31
0x14000de08  movsxd  rcx, eax
0x14000de0b  mov     eax, 2
0x14000de10  mul     rcx
0x14000de13  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000de1a  cmovb   rax, rcx
0x14000de1e  mov     rcx, rax; unsigned __int64
0x14000de21  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000de26  mov     rdi, rax
0x14000de29  test    rax, rax
0x14000de2c  jz      short loc_14000DE31
0x14000de2e  mov     [rax], bx
0x14000de31  mov     rax, rdi
0x14000de34  mov     rbx, [rsp+28h+arg_0]
0x14000de39  mov     rsi, [rsp+28h+arg_8]
0x14000de3e  add     rsp, 20h
0x14000de42  pop     rdi
0x14000de43  retn
```
