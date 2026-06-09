# TSUnloadCredTable(void)

- ea: `0x18001528c`
- end: `0x1800152fc`
- name: `?TSUnloadCredTable@@YAXXZ`
- size: `112`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800146c0`
- `0x180017b70`

## callees

- `0x1800053d0`
- `0x18001528c`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800152de`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x1800152de`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180015299`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180015299`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800152c3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800152c3`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800152ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800152ac`
- `ntdll!RtlReleaseResource` at `0x1800152f0`
- `ntdll!RtlReleaseResource` at `0x1800152f0`

## pseudocode

```c
void TSUnloadCredTable(void)
{
  BOOLEAN i; // dl
  struct _TS_CREDENTIAL *v1; // rbx
  struct _TS_CREDENTIAL **v2; // rax

  if ( RtlNumberGenericTableElementsAvl(&TSGlobalCredTable) )
  {
    RtlAcquireResourceExclusive(&TSGlobalCredTableLock, 1u);
    for ( i = 1; ; i = 0 )
    {
      v2 = (struct _TS_CREDENTIAL **)RtlEnumerateGenericTableAvl(&TSGlobalCredTable, i);
      if ( !v2 )
        break;
      v1 = *v2;
      if ( !RtlDeleteElementGenericTableAvl(&TSGlobalCredTable, v2) )
        break;
      TSDereferenceCredential(v1);
    }
    RtlReleaseResource(&TSGlobalCredTableLock);
  }
}

```

## disassembly

```asm
0x18001528c  push    rbx
0x18001528e  sub     rsp, 20h
0x180015292  lea     rcx, ?TSGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x180015299  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18001529f  test    eax, eax
0x1800152a1  jz      short loc_1800152F6
0x1800152a3  mov     dl, 1; Wait
0x1800152a5  lea     rcx, ?TSGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x1800152ac  call    cs:__imp_RtlAcquireResourceExclusive
0x1800152b2  mov     dl, 1
0x1800152b4  jmp     short loc_1800152D7
0x1800152b6  mov     rbx, [rax]
0x1800152b9  lea     rcx, ?TSGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x1800152c0  mov     rdx, rax; Buffer
0x1800152c3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800152c9  test    al, al
0x1800152cb  jz      short loc_1800152E9
0x1800152cd  mov     rcx, rbx; struct _TS_CREDENTIAL *
0x1800152d0  call    ?TSDereferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSDereferenceCredential(_TS_CREDENTIAL *)
0x1800152d5  xor     edx, edx; Restart
0x1800152d7  lea     rcx, ?TSGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x1800152de  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1800152e4  test    rax, rax
0x1800152e7  jnz     short loc_1800152B6
0x1800152e9  lea     rcx, ?TSGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x1800152f0  call    cs:__imp_RtlReleaseResource
0x1800152f6  add     rsp, 20h
0x1800152fa  pop     rbx
0x1800152fb  retn
```
