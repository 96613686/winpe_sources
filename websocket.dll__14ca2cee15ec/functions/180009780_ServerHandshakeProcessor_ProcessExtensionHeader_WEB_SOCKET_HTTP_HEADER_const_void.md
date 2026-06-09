# ServerHandshakeProcessor::ProcessExtensionHeader(_WEB_SOCKET_HTTP_HEADER * const,void *)

- ea: `0x180009780`
- end: `0x1800097bc`
- name: `?ProcessExtensionHeader@ServerHandshakeProcessor@@CAJQEAU_WEB_SOCKET_HTTP_HEADER@@PEAX@Z`
- size: `60`
- prototype: `__int64 __fastcall(struct _WEB_SOCKET_HTTP_HEADER *const, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002578`
- `0x180009780`
- `0x18000b88c`

## pseudocode

```c
__int64 __fastcall ServerHandshakeProcessor::ProcessExtensionHeader(struct _WEB_SOCKET_HTTP_HEADER *const a1, void *a2)
{
  int v2; // eax
  unsigned int v3; // ebx

  v2 = StringVerifier::VerifyExtensions(
         *((char **)a1 + 2),
         *((_DWORD *)a1 + 6),
         0xFFFFFFFF,
         (int (*)(const char *, unsigned int, void *))ServerHandshakeProcessor::VerifyExtensionValue,
         a2);
  v3 = v2;
  if ( v2 < 0 )
    Trace::Error(v2, 0xD0000011);
  return v3;
}

```

## disassembly

```asm
0x180009780  push    rbx
0x180009782  sub     rsp, 30h
0x180009786  mov     [rsp+38h+var_18], rdx; void *
0x18000978b  lea     r9, ?VerifyExtensionValue@ServerHandshakeProcessor@@CAJPEBDKPEAX@Z; int (*)(const char *, unsigned int, void *)
0x180009792  mov     edx, [rcx+18h]; unsigned int
0x180009795  or      r8d, 0FFFFFFFFh; unsigned int
0x180009799  mov     rcx, [rcx+10h]; char *
0x18000979d  call    ?VerifyExtensions@StringVerifier@@SAJPEADKKP6AJPEBDKPEAX@Z2@Z; StringVerifier::VerifyExtensions(char *,ulong,ulong,long (*)(char const *,ulong,void *),void *)
0x1800097a2  mov     ebx, eax
0x1800097a4  test    eax, eax
0x1800097a6  jns     short loc_1800097B4
0x1800097a8  mov     edx, 0D0000011h; unsigned int
0x1800097ad  mov     ecx, eax; int
0x1800097af  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x1800097b4  mov     eax, ebx
0x1800097b6  add     rsp, 30h
0x1800097ba  pop     rbx
0x1800097bb  retn
```
