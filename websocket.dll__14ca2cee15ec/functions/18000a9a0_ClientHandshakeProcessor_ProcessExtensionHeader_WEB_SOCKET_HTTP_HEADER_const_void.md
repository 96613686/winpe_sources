# ClientHandshakeProcessor::ProcessExtensionHeader(_WEB_SOCKET_HTTP_HEADER * const,void *)

- ea: `0x18000a9a0`
- end: `0x18000a9c5`
- name: `?ProcessExtensionHeader@ClientHandshakeProcessor@@CAJQEAU_WEB_SOCKET_HTTP_HEADER@@PEAX@Z`
- size: `37`
- prototype: `static int(struct _WEB_SOCKET_HTTP_HEADER *const, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b88c`

## pseudocode

```c
__int64 __fastcall ClientHandshakeProcessor::ProcessExtensionHeader(struct _WEB_SOCKET_HTTP_HEADER *const a1, void *a2)
{
  return StringVerifier::VerifyExtensions(
           *((char **)a1 + 2),
           *((_DWORD *)a1 + 6),
           0xFFFFFFFF,
           (__int64 (__fastcall *)(__int64, unsigned __int64, __int64))ClientHandshakeProcessor::VerifyExtensionValue,
           a2);
}

```

## disassembly

```asm
0x18000a9a0  sub     rsp, 38h
0x18000a9a4  mov     [rsp+38h+var_18], rdx; void *
0x18000a9a9  lea     r9, ?VerifyExtensionValue@ClientHandshakeProcessor@@CAJPEBDKPEAX@Z; int (*)(const char *, unsigned int, void *)
0x18000a9b0  mov     edx, [rcx+18h]; unsigned int
0x18000a9b3  or      r8d, 0FFFFFFFFh; unsigned int
0x18000a9b7  mov     rcx, [rcx+10h]; char *
0x18000a9bb  call    ?VerifyExtensions@StringVerifier@@SAJPEADKKP6AJPEBDKPEAX@Z2@Z; StringVerifier::VerifyExtensions(char *,ulong,ulong,long (*)(char const *,ulong,void *),void *)
0x18000a9c0  add     rsp, 38h
0x18000a9c4  retn
```
