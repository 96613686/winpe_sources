# STATIC_WSTRING_HASH::FindKey(ushort const *,int)

- ea: `0x180005448`
- end: `0x1800054e7`
- name: `?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z`
- size: `159`
- prototype: `struct STATIC_WSTRING_HASH_RECORD *(STATIC_WSTRING_HASH *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800055e8`

## callees

- `0x1800012f0`
- `0x180001330`
- `0x180005448`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800054c1`
- `msvcrt!_wcsicmp` at `0x1800054c1`

## pseudocode

```c
struct STATIC_WSTRING_HASH_RECORD *__fastcall STATIC_WSTRING_HASH::FindKey(
        STATIC_WSTRING_HASH *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  __int64 i; // rbx
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rax
  signed __int64 v8; // rdx
  int v9; // r8d
  int v10; // ecx
  bool v11; // zf

  if ( *((_DWORD *)this + 262) )
    v4 = HashString(a2, (unsigned int)a2);
  else
    v4 = HashStringNoCase(a2, (unsigned int)a2);
  for ( i = *((_QWORD *)this + v4 % 0x83); i; i = *(_QWORD *)(i + 8) )
  {
    v6 = *(const wchar_t **)i;
    if ( *((_DWORD *)this + 262) )
    {
      v7 = a2;
      v8 = (char *)v6 - (char *)a2;
      do
      {
        v9 = *(const unsigned __int16 *)((char *)v7 + v8);
        v10 = *v7 - v9;
        if ( v10 )
          break;
        ++v7;
      }
      while ( v9 );
      v11 = v10 == 0;
    }
    else
    {
      v11 = _wcsicmp(a2, v6) == 0;
    }
    if ( v11 )
      break;
  }
  return (struct STATIC_WSTRING_HASH_RECORD *)i;
}

```

## disassembly

```asm
0x180005448  mov     [rsp+arg_0], rbx
0x18000544d  mov     [rsp+arg_8], rsi
0x180005452  push    rdi
0x180005453  sub     rsp, 20h
0x180005457  cmp     dword ptr [rcx+418h], 0
0x18000545e  mov     rdi, rcx
0x180005461  mov     rcx, rdx; unsigned __int16 *
0x180005464  mov     rsi, rdx
0x180005467  jz      short loc_180005470
0x180005469  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x18000546e  jmp     short loc_180005475
0x180005470  call    ?HashStringNoCase@@YAKPEBGK@Z; HashStringNoCase(ushort const *,ulong)
0x180005475  mov     r8d, eax
0x180005478  mov     eax, 0FA232CF3h
0x18000547d  mul     r8d
0x180005480  shr     edx, 7
0x180005483  imul    eax, edx, 83h
0x180005489  sub     r8d, eax
0x18000548c  mov     rbx, [rdi+r8*8]
0x180005490  jmp     short loc_1800054CF
0x180005492  cmp     dword ptr [rdi+418h], 0
0x180005499  mov     rdx, [rbx]; String2
0x18000549c  jz      short loc_1800054BE
0x18000549e  mov     rax, rsi
0x1800054a1  sub     rdx, rsi
0x1800054a4  movzx   ecx, word ptr [rax]
0x1800054a7  movzx   r8d, word ptr [rax+rdx]
0x1800054ac  sub     ecx, r8d
0x1800054af  jnz     short loc_1800054BA
0x1800054b1  add     rax, 2
0x1800054b5  test    r8d, r8d
0x1800054b8  jnz     short loc_1800054A4
0x1800054ba  test    ecx, ecx
0x1800054bc  jmp     short loc_1800054C9
0x1800054be  mov     rcx, rsi; String1
0x1800054c1  call    cs:__imp__wcsicmp
0x1800054c7  test    eax, eax
0x1800054c9  jz      short loc_1800054D4
0x1800054cb  mov     rbx, [rbx+8]
0x1800054cf  test    rbx, rbx
0x1800054d2  jnz     short loc_180005492
0x1800054d4  mov     rsi, [rsp+28h+arg_8]
0x1800054d9  mov     rax, rbx
0x1800054dc  mov     rbx, [rsp+28h+arg_0]
0x1800054e1  add     rsp, 20h
0x1800054e5  pop     rdi
0x1800054e6  retn
```
