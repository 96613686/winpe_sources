# RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180015194`
- end: `0x1800151ec`
- name: `?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `88`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004dd0`

## callees

- `0x180015194`

## pseudocode

```c
__int64 __fastcall RtlStringCchCopyW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v3; // rax
  const wchar_t *v4; // rdx
  __int64 v5; // r8
  unsigned __int16 *v6; // rdx
  __int64 result; // rax

  v3 = 2147483646;
  v4 = L"<unknown>";
  v5 = 270;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *a1++ = *v4++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  result = v5 == 0 ? 0x80000005 : 0;
  if ( v5 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180015194  mov     eax, 7FFFFFFEh
0x180015199  lea     rdx, aUnknown; "<unknown>"
0x1800151a0  mov     r8d, 10Eh
0x1800151a6  xor     r10d, r10d
0x1800151a9  test    rax, rax
0x1800151ac  jz      short loc_1800151CD
0x1800151ae  movzx   r9d, word ptr [rdx]
0x1800151b2  test    r9w, r9w
0x1800151b6  jz      short loc_1800151CD
0x1800151b8  mov     [rcx], r9w
0x1800151bc  add     rdx, 2
0x1800151c0  add     rcx, 2
0x1800151c4  dec     rax
0x1800151c7  sub     r8, 1
0x1800151cb  jnz     short loc_1800151A9
0x1800151cd  mov     rax, r8
0x1800151d0  lea     rdx, [rcx-2]
0x1800151d4  neg     rax
0x1800151d7  sbb     eax, eax
0x1800151d9  not     eax
0x1800151db  and     eax, 80000005h
0x1800151e0  test    r8, r8
0x1800151e3  cmovnz  rdx, rcx
0x1800151e7  mov     [rdx], r10w
0x1800151eb  retn
```
