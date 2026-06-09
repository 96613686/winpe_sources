# minFileTime(_FILETIME,_FILETIME)

- ea: `0x180023fa4`
- end: `0x180023fd4`
- name: `?minFileTime@@YA?AU_FILETIME@@U1@0@Z`
- size: `48`
- prototype: `struct _FILETIME __fastcall(struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001f20`

## callees

- `0x180023fa4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023fbb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180023fbb`

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
0x180023fa4  mov     rax, rsp
0x180023fa7  mov     [rax+10h], rdx
0x180023fab  mov     [rax+8], rcx
0x180023faf  sub     rsp, 28h
0x180023fb3  lea     rdx, [rax+10h]; lpFileTime2
0x180023fb7  lea     rcx, [rax+8]; lpFileTime1
0x180023fbb  call    cs:__imp_CompareFileTime
0x180023fc1  test    eax, eax
0x180023fc3  mov     rax, [rsp+28h+arg_0]
0x180023fc8  js      short loc_180023FCF
0x180023fca  mov     rax, [rsp+28h+arg_8]
0x180023fcf  add     rsp, 28h
0x180023fd3  retn
```
