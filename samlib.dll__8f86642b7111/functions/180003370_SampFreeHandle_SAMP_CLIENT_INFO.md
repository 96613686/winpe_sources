# SampFreeHandle(_SAMP_CLIENT_INFO * *)

- ea: `0x180003370`
- end: `0x1800033b9`
- name: `?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z`
- size: `73`
- prototype: `void __fastcall(struct _SAMP_CLIENT_INFO **)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001800`
- `0x18000d330`
- `0x18000d630`
- `0x18000d930`
- `0x18000dde0`
- `0x18000e0e0`
- `0x18000e2e0`
- `0x18000e4e0`
- `0x18000fed0`
- `0x180010170`

## callees

- `0x180003370`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033b1`

## pseudocode

```c
void __fastcall SampFreeHandle(HLOCAL *a1)
{
  void *v2; // rcx
  _QWORD *v3; // rax

  if ( *a1 )
  {
    v2 = (void *)*((_QWORD *)*a1 + 2);
    if ( v2 )
      LocalFree(v2);
    v3 = *a1;
    *(_OWORD *)v3 = 0;
    v3[2] = 0;
    LocalFree(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180003370  push    rbx
0x180003372  sub     rsp, 20h
0x180003376  mov     rax, [rcx]
0x180003379  mov     rbx, rcx
0x18000337c  test    rax, rax
0x18000337f  jnz     short loc_180003387
0x180003381  add     rsp, 20h
0x180003385  pop     rbx
0x180003386  retn
0x180003387  mov     rcx, [rax+10h]; hMem
0x18000338b  test    rcx, rcx
0x18000338e  jnz     short loc_1800033B1
0x180003390  mov     rax, [rbx]
0x180003393  xor     ecx, ecx
0x180003395  xorps   xmm0, xmm0
0x180003398  movups  xmmword ptr [rax], xmm0
0x18000339b  mov     [rax+10h], rcx
0x18000339f  mov     rcx, [rbx]; hMem
0x1800033a2  call    cs:__imp_LocalFree
0x1800033a8  mov     qword ptr [rbx], 0
0x1800033af  jmp     short loc_180003381
0x1800033b1  call    cs:__imp_LocalFree
0x1800033b7  jmp     short loc_180003390
```
