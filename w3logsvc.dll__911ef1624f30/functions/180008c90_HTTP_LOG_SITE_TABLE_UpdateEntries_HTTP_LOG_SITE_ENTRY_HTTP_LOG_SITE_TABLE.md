# HTTP_LOG_SITE_TABLE::UpdateEntries(HTTP_LOG_SITE_ENTRY *,HTTP_LOG_SITE_TABLE *)

- ea: `0x180008c90`
- end: `0x180008cec`
- name: `?UpdateEntries@HTTP_LOG_SITE_TABLE@@CAJPEAVHTTP_LOG_SITE_ENTRY@@PEAV1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(struct HTTP_LOG_SITE_ENTRY *, struct HTTP_LOG_SITE_TABLE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180007fc8`
- `0x180008c90`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_TABLE::UpdateEntries(struct HTTP_LOG_SITE_ENTRY *a1, struct HTTP_LOG_SITE_TABLE *a2)
{
  struct STATIC_WSTRING_HASH_RECORD *Key; // rax
  __int64 v4; // rcx

  if ( (unsigned int)(*((_DWORD *)a1 + 28) - 1) <= 1 )
  {
    *((_DWORD *)a1 + 28) = 0;
  }
  else
  {
    Key = STATIC_WSTRING_HASH::FindKey((struct HTTP_LOG_SITE_TABLE *)((char *)a2 + 8), *((wchar_t **)a1 + 1), 1);
    v4 = ((unsigned __int64)Key - 8) & -(__int64)(Key != 0);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      --*((_DWORD *)a2 + 266);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008c90  push    rbx
0x180008c92  sub     rsp, 20h
0x180008c96  mov     eax, [rcx+70h]
0x180008c99  mov     r8d, 1; int
0x180008c9f  sub     eax, r8d
0x180008ca2  mov     rbx, rdx
0x180008ca5  mov     r9, rcx
0x180008ca8  cmp     eax, r8d
0x180008cab  jbe     short loc_180008CDD
0x180008cad  lea     rcx, [rdx+8]; this
0x180008cb1  mov     rdx, [r9+8]; unsigned __int16 *
0x180008cb5  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180008cba  lea     rdx, [rax-8]
0x180008cbe  neg     rax
0x180008cc1  sbb     rcx, rcx
0x180008cc4  and     rcx, rdx
0x180008cc7  jz      short loc_180008CE4
0x180008cc9  mov     rax, [rcx]
0x180008ccc  mov     rax, [rax+8]
0x180008cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cd5  dec     dword ptr [rbx+428h]
0x180008cdb  jmp     short loc_180008CE4
0x180008cdd  mov     dword ptr [rcx+70h], 0
0x180008ce4  xor     eax, eax
0x180008ce6  add     rsp, 20h
0x180008cea  pop     rbx
0x180008ceb  retn
```
