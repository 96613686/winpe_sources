# ShutdownIssuerCache(void)

- ea: `0x180077bbc`
- end: `0x180077c50`
- name: `?ShutdownIssuerCache@@YAXXZ`
- size: `148`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180054884`
- `0x180077854`

## callees

- `0x180014240`
- `0x180056dd0`
- `0x180077bbc`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180077c35`
- `ntdll!RtlDeleteResource` at `0x180077c35`
- `ntdll!RtlAcquireResourceExclusive` at `0x180077bd8`
- `ntdll!RtlAcquireResourceExclusive` at `0x180077bd8`

## pseudocode

```c
void ShutdownIssuerCache(void)
{
  void *v0; // rcx
  __int64 *v1; // rbx
  struct ISSUER_CACHE_ENTRY *v2; // rcx

  if ( dword_1800AE408 )
    RtlAcquireResourceExclusive(&stru_1800AE3A8, 1u);
  v0 = IssuerCache;
  if ( IssuerCache )
  {
    v1 = (__int64 *)qword_1800AE398;
    if ( (__int64 *)qword_1800AE398 != &qword_1800AE398 )
    {
      do
      {
        v2 = (struct ISSUER_CACHE_ENTRY *)(v1 - 5);
        v1 = (__int64 *)*v1;
        SPDeleteIssuerEntry(v2);
      }
      while ( v1 != &qword_1800AE398 );
      v0 = IssuerCache;
    }
    SPExternalFree(v0);
    IssuerCache = 0;
  }
  if ( dword_1800AE408 )
  {
    RtlDeleteResource(&stru_1800AE3A8);
    dword_1800AE408 = 0;
  }
}

```

## disassembly

```asm
0x180077bbc  mov     [rsp+arg_0], rbx
0x180077bc1  push    rsi
0x180077bc2  sub     rsp, 20h
0x180077bc6  cmp     cs:dword_1800AE408, 0
0x180077bcd  jz      short loc_180077BDE
0x180077bcf  mov     dl, 1; Wait
0x180077bd1  lea     rcx, stru_1800AE3A8; Resource
0x180077bd8  call    cs:__imp_RtlAcquireResourceExclusive
0x180077bde  mov     rcx, cs:?IssuerCache@@3UISSUER_CACHE@@A; ISSUER_CACHE IssuerCache
0x180077be5  test    rcx, rcx
0x180077be8  jz      short loc_180077C25
0x180077bea  mov     rbx, cs:qword_1800AE398
0x180077bf1  lea     rsi, qword_1800AE398
0x180077bf8  cmp     rbx, rsi
0x180077bfb  jz      short loc_180077C15
0x180077bfd  lea     rcx, [rbx-28h]; struct ISSUER_CACHE_ENTRY *
0x180077c01  mov     rbx, [rbx]
0x180077c04  call    ?SPDeleteIssuerEntry@@YAXPEAUISSUER_CACHE_ENTRY@@@Z; SPDeleteIssuerEntry(ISSUER_CACHE_ENTRY *)
0x180077c09  cmp     rbx, rsi
0x180077c0c  jnz     short loc_180077BFD
0x180077c0e  mov     rcx, cs:?IssuerCache@@3UISSUER_CACHE@@A; void *
0x180077c15  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180077c1a  mov     cs:?IssuerCache@@3UISSUER_CACHE@@A, 0; ISSUER_CACHE IssuerCache
0x180077c25  cmp     cs:dword_1800AE408, 0
0x180077c2c  jz      short loc_180077C45
0x180077c2e  lea     rcx, stru_1800AE3A8; Resource
0x180077c35  call    cs:__imp_RtlDeleteResource
0x180077c3b  mov     cs:dword_1800AE408, 0
0x180077c45  mov     rbx, [rsp+28h+arg_0]
0x180077c4a  add     rsp, 20h
0x180077c4e  pop     rsi
0x180077c4f  retn
```
