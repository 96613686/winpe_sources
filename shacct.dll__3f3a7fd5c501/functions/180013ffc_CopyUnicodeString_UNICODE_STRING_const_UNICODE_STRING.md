# _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x180013ffc`
- end: `0x180014029`
- name: `?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `45`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013de0`

## callees

- `0x180003a60`
- `0x180013ffc`

## pseudocode

```c
__int64 __fastcall _CopyUnicodeString(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  unsigned int v2; // ecx

  if ( a1->Length && a1->Buffer )
  {
    return (unsigned int)CopyUnicodeStringAlloc(a1, a2);
  }
  else
  {
    v2 = 0;
    *(_DWORD *)&a2->Length = 0;
    a2->Buffer = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180013ffc  sub     rsp, 28h
0x180014000  xor     r8d, r8d
0x180014003  cmp     [rcx], r8w
0x180014007  jbe     short loc_180014018
0x180014009  cmp     [rcx+8], r8
0x18001400d  jz      short loc_180014018
0x18001400f  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180014014  mov     ecx, eax
0x180014016  jmp     short loc_180014022
0x180014018  mov     ecx, r8d
0x18001401b  mov     [rdx], r8d
0x18001401e  mov     [rdx+8], r8
0x180014022  mov     eax, ecx
0x180014024  add     rsp, 28h
0x180014028  retn
```
