# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800374ec`
- end: `0x18003753b`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800375d0`

## callees

- `0x1800374ec`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v4; // r9
  unsigned __int16 *v5; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = a1 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = a1;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x1800374ec  mov     eax, 7FFFFFFEh
0x1800374f1  mov     r9d, 104h
0x1800374f7  xor     r10d, r10d
0x1800374fa  test    rax, rax
0x1800374fd  jz      short loc_18003751C
0x1800374ff  movzx   edx, word ptr [r8]
0x180037503  test    dx, dx
0x180037506  jz      short loc_18003751C
0x180037508  mov     [rcx], dx
0x18003750b  add     r8, 2
0x18003750f  add     rcx, 2
0x180037513  dec     rax
0x180037516  sub     r9, 1
0x18003751a  jnz     short loc_1800374FA
0x18003751c  mov     rax, r9
0x18003751f  lea     rdx, [rcx-2]
0x180037523  neg     rax
0x180037526  sbb     eax, eax
0x180037528  not     eax
0x18003752a  and     eax, 8007007Ah
0x18003752f  test    r9, r9
0x180037532  cmovnz  rdx, rcx
0x180037536  mov     [rdx], r10w
0x18003753a  retn
```
