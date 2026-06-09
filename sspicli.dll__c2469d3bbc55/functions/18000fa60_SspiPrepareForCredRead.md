# SspiPrepareForCredRead

- ea: `0x18000fa60`
- end: `0x18000fad9`
- name: `SspiPrepareForCredRead`
- size: `121`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, PCWSTR pszTargetName, PULONG pCredmanCredentialType, PCWSTR *ppszCredmanTargetName)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000fa60`
- `0x18000fae0`
- `0x180018600`
- `0x18002205f`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiPrepareForCredRead(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        PCWSTR pszTargetName,
        PULONG pCredmanCredentialType,
        PCWSTR *ppszCredmanTargetName)
{
  SECURITY_STATUS v4; // edi
  size_t Size; // [rsp+40h] [rbp-28h] BYREF
  PVOID DataBuffer; // [rsp+48h] [rbp-20h] BYREF
  PVOID v8; // [rsp+50h] [rbp-18h] BYREF

  v8 = 0;
  DataBuffer = 0;
  LODWORD(Size) = 0;
  v4 = SspiPrepareForCredWrite(
         AuthIdentity,
         pszTargetName,
         pCredmanCredentialType,
         ppszCredmanTargetName,
         (PCWSTR *)&v8,
         (PUCHAR *)&DataBuffer,
         (PULONG)&Size);
  if ( DataBuffer )
  {
    memset_0(DataBuffer, 0, (unsigned int)Size);
    SspiLocalFree(DataBuffer);
  }
  if ( v8 )
    SspiLocalFree(v8);
  return v4;
}

```

## disassembly

```asm
0x18000fa60  mov     r11, rsp
0x18000fa63  push    rdi
0x18000fa64  sub     rsp, 60h
0x18000fa68  lea     rax, [r11-28h]
0x18000fa6c  mov     qword ptr [r11-18h], 0
0x18000fa74  mov     [r11-38h], rax
0x18000fa78  lea     rax, [r11-20h]
0x18000fa7c  mov     [r11-40h], rax
0x18000fa80  lea     rax, [r11-18h]
0x18000fa84  mov     [r11-48h], rax
0x18000fa88  mov     qword ptr [r11-20h], 0
0x18000fa90  mov     dword ptr [rsp+68h+Size], 0
0x18000fa98  call    SspiPrepareForCredWrite
0x18000fa9d  cmp     [rsp+68h+DataBuffer], 0
0x18000faa3  mov     edi, eax
0x18000faa5  jz      short loc_18000FAC2
0x18000faa7  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18000faac  xor     edx, edx; Val
0x18000faae  mov     rcx, [rsp+68h+DataBuffer]; void *
0x18000fab3  call    memset_0
0x18000fab8  mov     rcx, [rsp+68h+DataBuffer]; DataBuffer
0x18000fabd  call    SspiLocalFree
0x18000fac2  mov     rcx, [rsp+68h+var_18]; DataBuffer
0x18000fac7  test    rcx, rcx
0x18000faca  jz      short loc_18000FAD1
0x18000facc  call    SspiLocalFree
0x18000fad1  mov     eax, edi
0x18000fad3  add     rsp, 60h
0x18000fad7  pop     rdi
0x18000fad8  retn
```
