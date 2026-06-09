# EnsureUriPathIsSlashTerminated(STRU *)

- ea: `0x180019d58`
- end: `0x180019d8c`
- name: `?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(struct STRU *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002740`
- `0x180003c4c`
- `0x180006940`
- `0x18001b368`
- `0x18001b8c0`
- `0x18001c854`
- `0x18001cdd0`
- `0x18001f128`
- `0x18001fc18`

## callees

- `0x180019d58`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019d7b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180019d7b`

## pseudocode

```c
__int64 __fastcall EnsureUriPathIsSlashTerminated(struct STRU *a1)
{
  int v1; // eax
  unsigned int v2; // r8d

  v1 = *((_DWORD *)a1 + 12);
  v2 = 0;
  if ( v1 && *(_WORD *)(*((_QWORD *)a1 + 4) + 2LL * (unsigned int)(v1 - 1)) != 47 )
    return (unsigned int)STRU::Append(a1, L"/");
  return v2;
}

```

## disassembly

```asm
0x180019d58  sub     rsp, 28h
0x180019d5c  mov     eax, [rcx+30h]
0x180019d5f  xor     r8d, r8d
0x180019d62  test    eax, eax
0x180019d64  jz      short loc_180019D84
0x180019d66  lea     edx, [rax-1]
0x180019d69  mov     rax, [rcx+20h]
0x180019d6d  cmp     word ptr [rax+rdx*2], 2Fh ; '/'
0x180019d72  jz      short loc_180019D84
0x180019d74  lea     rdx, asc_180025EA4; "/"
0x180019d7b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180019d81  mov     r8d, eax
0x180019d84  mov     eax, r8d
0x180019d87  add     rsp, 28h
0x180019d8b  retn
```
