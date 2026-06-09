# CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)

- ea: `0x18000b290`
- end: `0x18000b2ff`
- name: `?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z`
- size: `111`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *const, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e20`
- `0x18000fce4`
- `0x180010ce4`
- `0x180011150`
- `0x180011ca4`

## callees

- `0x18000b290`

## pseudocode

```c
__int64 __fastcall CopyUstrToPstr(struct _UNICODE_STRING *const a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 *v3; // r9
  unsigned __int64 v4; // r8
  PWSTR Buffer; // rdx
  unsigned __int64 v6; // rax
  unsigned int v7; // r10d

  v3 = a2;
  if ( !a1 || !a2 )
    return 2147500035LL;
  v4 = (unsigned __int64)a3 >> 1;
  if ( !v4 )
    return 2147942487LL;
  Buffer = a1->Buffer;
  v6 = (unsigned __int64)a1->Length >> 1;
  v7 = 0;
  while ( v6 && *Buffer )
  {
    *v3++ = *Buffer++;
    --v6;
    if ( !--v4 )
    {
      --v3;
      v7 = -2147024774;
      break;
    }
  }
  *v3 = 0;
  return v7;
}

```

## disassembly

```asm
0x18000b290  mov     r9, rdx
0x18000b293  test    rcx, rcx
0x18000b296  jz      short loc_18000B2F9
0x18000b298  test    rdx, rdx
0x18000b29b  jz      short loc_18000B2F9
0x18000b29d  mov     r8d, r8d
0x18000b2a0  shr     r8, 1
0x18000b2a3  jz      short loc_18000B2EF
0x18000b2a5  movzx   eax, word ptr [rcx]
0x18000b2a8  mov     rdx, [rcx+8]
0x18000b2ac  shr     rax, 1
0x18000b2af  xor     r10d, r10d
0x18000b2b2  test    rax, rax
0x18000b2b5  jz      short loc_18000B2E5
0x18000b2b7  movzx   ecx, word ptr [rdx]
0x18000b2ba  test    cx, cx
0x18000b2bd  jz      short loc_18000B2D6
0x18000b2bf  mov     [r9], cx
0x18000b2c3  add     rdx, 2
0x18000b2c7  add     r9, 2
0x18000b2cb  dec     rax
0x18000b2ce  sub     r8, 1
0x18000b2d2  jnz     short loc_18000B2B2
0x18000b2d4  jmp     short loc_18000B2DB
0x18000b2d6  test    r8, r8
0x18000b2d9  jnz     short loc_18000B2E5
0x18000b2db  sub     r9, 2
0x18000b2df  mov     r10d, 8007007Ah
0x18000b2e5  xor     eax, eax
0x18000b2e7  mov     [r9], ax
0x18000b2eb  mov     eax, r10d
0x18000b2ee  retn
0x18000b2ef  mov     r10d, 80070057h
0x18000b2f5  mov     eax, r10d
0x18000b2f8  retn
0x18000b2f9  mov     eax, 80004003h
0x18000b2fe  retn
```
