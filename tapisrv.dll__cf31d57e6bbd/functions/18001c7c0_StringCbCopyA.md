# StringCbCopyA

- ea: `0x18001c7c0`
- end: `0x18001c809`
- name: `StringCbCopyA`
- size: `73`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fcc`
- `0x1800068ac`
- `0x180010750`
- `0x180017be0`
- `0x18001fb28`
- `0x180020db4`
- `0x180023060`
- `0x180023910`
- `0x180024fc8`
- `0x180026730`
- `0x180026d60`
- `0x180028b00`
- `0x18002d6d0`
- `0x18002e9b0`
- `0x180030218`
- `0x1800319fc`
- `0x180034540`
- `0x180034a80`
- `0x180034fa0`
- `0x180035050`
- `0x180035280`
- `0x18003ce2c`
- `0x18003cf88`
- `0x18003d1ac`
- `0x18003d234`

## callees

- `0x18001c7c0`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  STRSAFE_LPSTR v6; // rcx
  HRESULT result; // eax

  v4 = 2147483646;
  v5 = 16;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x18001c7c0  mov     r9, rcx
0x18001c7c3  mov     eax, 7FFFFFFEh
0x18001c7c8  mov     edx, 10h
0x18001c7cd  test    rax, rax
0x18001c7d0  jz      short loc_18001C7EB
0x18001c7d2  mov     cl, [r8]
0x18001c7d5  test    cl, cl
0x18001c7d7  jz      short loc_18001C7EB
0x18001c7d9  mov     [r9], cl
0x18001c7dc  inc     r8
0x18001c7df  inc     r9
0x18001c7e2  dec     rax
0x18001c7e5  sub     rdx, 1
0x18001c7e9  jnz     short loc_18001C7CD
0x18001c7eb  mov     rax, rdx
0x18001c7ee  lea     rcx, [r9-1]
0x18001c7f2  neg     rax
0x18001c7f5  sbb     eax, eax
0x18001c7f7  not     eax
0x18001c7f9  and     eax, 8007007Ah
0x18001c7fe  test    rdx, rdx
0x18001c801  cmovnz  rcx, r9
0x18001c805  mov     byte ptr [rcx], 0
0x18001c808  retn
```
