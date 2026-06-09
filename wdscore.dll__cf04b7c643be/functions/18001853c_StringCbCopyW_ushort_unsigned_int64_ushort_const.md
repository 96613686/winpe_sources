# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18001853c`
- end: `0x1800185a9`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800142c8`
- `0x18001eef4`
- `0x18001f020`
- `0x18001fe98`
- `0x180020088`
- `0x180021ed8`
- `0x180023c00`

## callees

- `0x18001853c`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int64 v3; // rdx
  __int64 result; // rax
  __int64 v5; // rax
  unsigned __int16 *v6; // rax

  v3 = a2 >> 1;
  if ( !v3 )
    return 2147942487LL;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *a1++ = *a3++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = a1 - 1;
    if ( v3 )
      v6 = a1;
    *v6 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001853c  xor     r9d, r9d
0x18001853f  shr     rdx, 1
0x180018542  jz      short loc_18001859A
0x180018544  cmp     rdx, 7FFFFFFFh
0x18001854b  jbe     short loc_180018554
0x18001854d  mov     eax, 80070057h
0x180018552  jmp     short loc_1800185A4
0x180018554  mov     eax, 7FFFFFFEh
0x180018559  test    rax, rax
0x18001855c  jz      short loc_18001857D
0x18001855e  movzx   r10d, word ptr [r8]
0x180018562  test    r10w, r10w
0x180018566  jz      short loc_18001857D
0x180018568  mov     [rcx], r10w
0x18001856c  add     r8, 2
0x180018570  add     rcx, 2
0x180018574  dec     rax
0x180018577  sub     rdx, 1
0x18001857b  jnz     short loc_180018559
0x18001857d  test    rdx, rdx
0x180018580  lea     rax, [rcx-2]
0x180018584  cmovnz  rax, rcx
0x180018588  neg     rdx
0x18001858b  mov     [rax], r9w
0x18001858f  sbb     eax, eax
0x180018591  not     eax
0x180018593  and     eax, 8007007Ah
0x180018598  retn
0x18001859a  mov     eax, 80070057h
0x18001859f  test    rdx, rdx
0x1800185a2  jz      short locret_1800185A8
0x1800185a4  mov     [rcx], r9w
0x1800185a8  retn
```
