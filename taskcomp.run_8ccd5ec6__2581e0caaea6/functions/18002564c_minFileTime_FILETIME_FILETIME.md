# minFileTime(_FILETIME,_FILETIME)

- ea: `0x18002564c`
- end: `0x180025683`
- name: `?minFileTime@@YA?AU_FILETIME@@U1@0@Z`
- size: `55`
- prototype: `struct _FILETIME __fastcall(struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001fc0`

## callees

- `0x18002564c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025663`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025663`

## pseudocode

```c
struct _FILETIME __fastcall minFileTime(FILETIME a1, FILETIME a2)
{
  bool v2; // sf
  struct _FILETIME result; // rax
  FILETIME v4; // [rsp+30h] [rbp+8h] BYREF
  FILETIME v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  v4 = a1;
  v2 = CompareFileTime(&v4, &v5) < 0;
  result = v4;
  if ( !v2 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x18002564c  mov     rax, rsp
0x18002564f  mov     [rax+10h], rdx
0x180025653  mov     [rax+8], rcx
0x180025657  sub     rsp, 28h
0x18002565b  lea     rdx, [rax+10h]; lpFileTime2
0x18002565f  lea     rcx, [rax+8]; lpFileTime1
0x180025663  call    cs:__imp_CompareFileTime
0x18002566a  nop     dword ptr [rax+rax+00h]
0x18002566f  test    eax, eax
0x180025671  mov     rax, [rsp+28h+arg_0]
0x180025676  js      short loc_18002567D
0x180025678  mov     rax, [rsp+28h+arg_8]
0x18002567d  add     rsp, 28h
0x180025681  retn
```
