# PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(wchar_t const *)

- ea: `0x180009bdc`
- end: `0x180009c74`
- name: `?LookupNLoad@?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAAKPEB_W@Z`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007e78`
- `0x180008970`
- `0x180018484`
- `0x180026450`
- `0x180026ba8`

## callees

- `0x180009bdc`
- `0x18001e5c4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009c46`

## pseudocode

```c
__int64 __fastcall PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(__int64 a1, const wchar_t *a2)
{
  DWORD LastError; // edi
  void **v5; // r9
  wchar_t *v6; // rsi

  if ( *(_BYTE *)(a1 + 12) )
    return 4317;
  LastError = (***(__int64 (__fastcall ****)(_QWORD, __int64, const wchar_t *))(a1 + 16))(
                *(_QWORD *)(a1 + 16),
                a1 + 24,
                a2);
  if ( LastError == 2 )
  {
    v6 = (wchar_t *)PublisherLookupNLoader_Helper_LookupPathUsingTable(
                      *(const struct PUBLISHER_LOOKUP_ENTRY **)a1,
                      *(_DWORD *)(a1 + 8),
                      a2,
                      v5);
    if ( v6 )
    {
      LastError = (***(__int64 (__fastcall ****)(_QWORD, __int64, wchar_t *))(a1 + 16))(
                    *(_QWORD *)(a1 + 16),
                    a1 + 24,
                    v6);
      if ( v6 != a2 )
        LocalFree(v6);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  if ( !LastError )
    *(_BYTE *)(a1 + 12) = 1;
  return LastError;
}

```

## disassembly

```asm
0x180009bdc  push    rbx
0x180009bde  push    rbp
0x180009bdf  push    rsi
0x180009be0  push    rdi
0x180009be1  push    r14
0x180009be3  sub     rsp, 20h
0x180009be7  cmp     byte ptr [rcx+0Ch], 0
0x180009beb  mov     rbp, rdx
0x180009bee  mov     rbx, rcx
0x180009bf1  jnz     short loc_180009C5D
0x180009bf3  mov     rcx, [rcx+10h]
0x180009bf7  mov     r8, rdx
0x180009bfa  lea     rdx, [rbx+18h]
0x180009bfe  mov     rax, [rcx]
0x180009c01  mov     rax, [rax]
0x180009c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c09  mov     edi, eax
0x180009c0b  cmp     eax, 2
0x180009c0e  jnz     short loc_180009C4C
0x180009c10  mov     edx, [rbx+8]; unsigned int
0x180009c13  mov     r8, rbp; wchar_t *
0x180009c16  mov     rcx, [rbx]; struct PUBLISHER_LOOKUP_ENTRY *
0x180009c19  call    ?PublisherLookupNLoader_Helper_LookupPathUsingTable@@YAPEB_WPEBUPUBLISHER_LOOKUP_ENTRY@@KPEB_WAEAPEAX@Z; PublisherLookupNLoader_Helper_LookupPathUsingTable(PUBLISHER_LOOKUP_ENTRY const *,ulong,wchar_t const *,void * &)
0x180009c1e  mov     rsi, rax
0x180009c21  test    rax, rax
0x180009c24  jz      short loc_180009C64
0x180009c26  mov     rcx, [rbx+10h]
0x180009c2a  lea     rdx, [rbx+18h]
0x180009c2e  mov     r8, [rcx]
0x180009c31  mov     rax, [r8]
0x180009c34  mov     r8, rsi
0x180009c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3c  mov     edi, eax
0x180009c3e  cmp     rsi, rbp
0x180009c41  jz      short loc_180009C4C
0x180009c43  mov     rcx, rsi; hMem
0x180009c46  call    cs:__imp_LocalFree
0x180009c4c  test    edi, edi
0x180009c4e  jz      short loc_180009C6E
0x180009c50  mov     eax, edi
0x180009c52  add     rsp, 20h
0x180009c56  pop     r14
0x180009c58  pop     rdi
0x180009c59  pop     rsi
0x180009c5a  pop     rbp
0x180009c5b  pop     rbx
0x180009c5c  retn
0x180009c5d  mov     eax, 10DDh
0x180009c62  jmp     short loc_180009C52
0x180009c64  call    cs:__imp_GetLastError
0x180009c6a  mov     edi, eax
0x180009c6c  jmp     short loc_180009C4C
0x180009c6e  mov     byte ptr [rbx+0Ch], 1
0x180009c72  jmp     short loc_180009C50
```
