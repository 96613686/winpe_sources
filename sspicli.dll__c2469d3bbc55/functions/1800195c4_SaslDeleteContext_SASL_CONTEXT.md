# SaslDeleteContext(_SASL_CONTEXT *)

- ea: `0x1800195c4`
- end: `0x18001962b`
- name: `?SaslDeleteContext@@YAXPEAU_SASL_CONTEXT@@@Z`
- size: `103`
- prototype: `void __fastcall(struct _SASL_CONTEXT *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b70`
- `0x1800199c0`
- `0x180019eb0`
- `0x18001a060`

## callees

- `0x1800195c4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180019600`
- `ntdll!RtlLeaveCriticalSection` at `0x180019600`
- `ntdll!RtlEnterCriticalSection` at `0x1800195da`
- `ntdll!RtlEnterCriticalSection` at `0x1800195da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001960f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001960f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001961d`

## pseudocode

```c
void __fastcall SaslDeleteContext(struct _SASL_CONTEXT ***a1)
{
  struct _SASL_CONTEXT **v2; // rdx
  struct _SASL_CONTEXT **v3; // rax
  struct _SASL_CONTEXT **v4; // rcx

  if ( *a1 )
  {
    RtlEnterCriticalSection(&SaslLock);
    v2 = *a1;
    if ( (*a1)[1] != (struct _SASL_CONTEXT *)a1 || (v3 = a1[1], *v3 != (struct _SASL_CONTEXT *)a1) )
      __fastfail(3u);
    *v3 = (struct _SASL_CONTEXT *)v2;
    v2[1] = (struct _SASL_CONTEXT *)v3;
    RtlLeaveCriticalSection(&SaslLock);
  }
  v4 = a1[8];
  if ( v4 )
    LocalFree(v4);
  LocalFree(a1);
}

```

## disassembly

```asm
0x1800195c4  push    rbx
0x1800195c6  sub     rsp, 20h
0x1800195ca  cmp     qword ptr [rcx], 0
0x1800195ce  mov     rbx, rcx
0x1800195d1  jz      short loc_180019606
0x1800195d3  lea     rcx, SaslLock; CriticalSection
0x1800195da  call    cs:__imp_RtlEnterCriticalSection
0x1800195e0  mov     rdx, [rbx]
0x1800195e3  cmp     [rdx+8], rbx
0x1800195e7  jnz     short loc_180019624
0x1800195e9  mov     rax, [rbx+8]
0x1800195ed  cmp     [rax], rbx
0x1800195f0  jnz     short loc_180019624
0x1800195f2  mov     [rax], rdx
0x1800195f5  lea     rcx, SaslLock; CriticalSection
0x1800195fc  mov     [rdx+8], rax
0x180019600  call    cs:__imp_RtlLeaveCriticalSection
0x180019606  mov     rcx, [rbx+40h]; hMem
0x18001960a  test    rcx, rcx
0x18001960d  jz      short loc_180019615
0x18001960f  call    cs:__imp_LocalFree
0x180019615  mov     rcx, rbx
0x180019618  add     rsp, 20h
0x18001961c  pop     rbx
0x18001961d  jmp     cs:__imp_LocalFree
0x180019624  mov     ecx, 3
0x180019629  int     29h; Win8: RtlFailFast(ecx)
```
