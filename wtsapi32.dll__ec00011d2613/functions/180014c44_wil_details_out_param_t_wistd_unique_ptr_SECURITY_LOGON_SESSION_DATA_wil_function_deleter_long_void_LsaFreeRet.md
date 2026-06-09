# wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>(void)

- ea: `0x180014c44`
- end: `0x180014c6e`
- name: `??1?$out_param_t@V?$unique_ptr@U_SECURITY_LOGON_SESSION_DATA@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014c74`

## callees

- `0x180014c44`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x180014c63`
- `SspiCli!LsaFreeReturnBuffer` at `0x180014c63`

## pseudocode

```c
int __fastcall wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>(
        __int64 a1)
{
  __int64 v1; // rax
  void *v2; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = *(_QWORD *)(a1 + 8);
    v2 = **(void ***)a1;
    **(_QWORD **)a1 = v1;
    if ( v2 )
      LODWORD(v1) = LsaFreeReturnBuffer(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x180014c44  sub     rsp, 28h
0x180014c48  cmp     byte ptr [rcx+10h], 0
0x180014c4c  jz      short loc_180014C69
0x180014c4e  mov     rdx, [rcx]
0x180014c51  mov     rax, [rcx+8]
0x180014c55  mov     r8, [rdx]
0x180014c58  mov     [rdx], rax
0x180014c5b  test    r8, r8
0x180014c5e  jz      short loc_180014C69
0x180014c60  mov     rcx, r8; Buffer
0x180014c63  call    cs:__imp_LsaFreeReturnBuffer
0x180014c69  add     rsp, 28h
0x180014c6d  retn
```
