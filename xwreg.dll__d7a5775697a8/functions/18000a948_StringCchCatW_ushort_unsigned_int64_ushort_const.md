# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000a948`
- end: `0x18000a9cd`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `133`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180007860`
- `0x180007b28`
- `0x180008b4c`
- `0x1800095c0`
- `0x1800099b4`
- `0x18000a168`
- `0x18000af74`
- `0x18000b114`
- `0x18000b4b8`
- `0x18000bac8`
- `0x18000c240`
- `0x18000c428`
- `0x18000c5c8`
- `0x18000ca6c`
- `0x18000ded4`
- `0x18000e140`
- `0x18000e40c`
- `0x18000e61c`
- `0x18000ee04`
- `0x18000f238`
- `0x18000f484`
- `0x18000f7c4`
- `0x180010dcc`
- `0x180010ff4`
- `0x180011c8c`

## callees

- `0x18000a948`
- `0x18000aa18`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // r9
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // r8
  size_t v10; // [rsp+20h] [rbp-18h]

  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    if ( v5 )
    {
      v8 = (a2 - v5) & -(__int64)(v5 != 0);
      return (unsigned int)StringCopyWorkerW(&a1[v8], a2 - v8, (size_t *)v8, a3, v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000a948  mov     [rsp+arg_0], rbx
0x18000a94d  push    rdi
0x18000a94e  sub     rsp, 30h
0x18000a952  lea     rax, [rdx-1]
0x18000a956  mov     rbx, r8
0x18000a959  mov     r10, rdx
0x18000a95c  mov     r11, rcx
0x18000a95f  cmp     rax, 7FFFFFFEh
0x18000a965  ja      short loc_18000A9BB
0x18000a967  mov     r9, rdx
0x18000a96a  mov     rax, rcx
0x18000a96d  xor     edi, edi
0x18000a96f  cmp     [rax], di
0x18000a972  jz      short loc_18000A97E
0x18000a974  add     rax, 2
0x18000a978  sub     r9, 1
0x18000a97c  jnz     short loc_18000A96F
0x18000a97e  mov     rax, r9
0x18000a981  mov     rcx, r10
0x18000a984  neg     rax
0x18000a987  mov     rax, r9
0x18000a98a  sbb     edx, edx
0x18000a98c  sub     rcx, r9
0x18000a98f  not     edx
0x18000a991  and     edx, 80070057h
0x18000a997  neg     rax
0x18000a99a  sbb     r8, r8
0x18000a99d  and     r8, rcx; pcchNewDestLength
0x18000a9a0  test    r9, r9
0x18000a9a3  jz      short loc_18000A9C0
0x18000a9a5  sub     r10, r8
0x18000a9a8  lea     rcx, [r11+r8*2]; pszDest
0x18000a9ac  mov     rdx, r10; cchDest
0x18000a9af  mov     r9, rbx; pszSrc
0x18000a9b2  call    StringCopyWorkerW
0x18000a9b7  mov     edx, eax
0x18000a9b9  jmp     short loc_18000A9C0
0x18000a9bb  mov     edx, 80070057h
0x18000a9c0  mov     rbx, [rsp+38h+arg_0]
0x18000a9c5  mov     eax, edx
0x18000a9c7  add     rsp, 30h
0x18000a9cb  pop     rdi
0x18000a9cc  retn
```
