# ContainsSID(void * *,ulong,void *)

- ea: `0x18000fbdc`
- end: `0x18000fc23`
- name: `?ContainsSID@@YAHPEAPEAXKPEAX@Z`
- size: `71`
- prototype: `int(void **, unsigned int, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f918`

## callees

- `0x18000fbdc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc03`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc03`

## pseudocode

```c
__int64 __fastcall ContainsSID(void **a1, unsigned int a2, void *a3)
{
  unsigned int v3; // edi
  __int64 i; // rbx
  void *v8; // rcx

  v3 = 0;
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v8 = a1[i];
    if ( v8 && EqualSid(v8, a3) )
      return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x18000fbdc  push    rbx
0x18000fbde  push    rbp
0x18000fbdf  push    rsi
0x18000fbe0  push    rdi
0x18000fbe1  push    r14
0x18000fbe3  sub     rsp, 20h
0x18000fbe7  xor     edi, edi
0x18000fbe9  mov     rbp, r8
0x18000fbec  xor     ebx, ebx
0x18000fbee  mov     esi, edx
0x18000fbf0  mov     r14, rcx
0x18000fbf3  cmp     ebx, esi
0x18000fbf5  jnb     short loc_18000FC16
0x18000fbf7  mov     rcx, [r14+rbx*8]; pSid1
0x18000fbfb  test    rcx, rcx
0x18000fbfe  jz      short loc_18000FC0D
0x18000fc00  mov     rdx, rbp; pSid2
0x18000fc03  call    cs:__imp_EqualSid
0x18000fc09  test    eax, eax
0x18000fc0b  jnz     short loc_18000FC11
0x18000fc0d  inc     ebx
0x18000fc0f  jmp     short loc_18000FBF3
0x18000fc11  mov     edi, 1
0x18000fc16  mov     eax, edi
0x18000fc18  add     rsp, 20h
0x18000fc1c  pop     r14
0x18000fc1e  pop     rdi
0x18000fc1f  pop     rsi
0x18000fc20  pop     rbp
0x18000fc21  pop     rbx
0x18000fc22  retn
```
