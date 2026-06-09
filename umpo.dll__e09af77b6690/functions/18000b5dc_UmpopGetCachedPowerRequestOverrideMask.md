# UmpopGetCachedPowerRequestOverrideMask

- ea: `0x18000b5dc`
- end: `0x18000b681`
- name: `UmpopGetCachedPowerRequestOverrideMask`
- size: `165`
- prototype: `char __fastcall(const wchar_t *, int, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180004170`

## callees

- `0x18000b5dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b66c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000b66c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b607`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b607`

## pseudocode

```c
char __fastcall UmpopGetCachedPowerRequestOverrideMask(const wchar_t *a1, int a2, _DWORD *a3)
{
  int v3; // r15d
  char v4; // bp
  __int64 *v7; // rdi
  wchar_t *v8; // rax
  const wchar_t *v9; // rbx
  unsigned int i; // esi
  int v12; // edx

  v3 = 0;
  v4 = 0;
  if ( a2 )
  {
    v12 = a2 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
        goto LABEL_9;
      v7 = &UmpoServiceOverrideCacheArray;
    }
    else
    {
      v7 = UmpoProcessOverrideCacheArray;
    }
  }
  else
  {
    v7 = UmpoDriverOverrideCacheArray;
  }
  v8 = wcsrchr(a1, 0x5Cu);
  if ( v8 )
    v9 = v8 + 1;
  else
    v9 = a1;
  for ( i = 0; i < 0xA; ++i )
  {
    if ( !v7[2 * i] )
      goto LABEL_8;
    if ( !(unsigned int)_o__wcsicmp(v9) )
    {
      v3 = v7[2 * i + 1];
LABEL_8:
      v4 = 1;
      break;
    }
  }
LABEL_9:
  *a3 = v3;
  return v4;
}

```

## disassembly

```asm
0x18000b5dc  push    rbx
0x18000b5de  push    rbp
0x18000b5df  push    rsi
0x18000b5e0  push    rdi
0x18000b5e1  push    r12
0x18000b5e3  push    r14
0x18000b5e5  push    r15
0x18000b5e7  sub     rsp, 20h
0x18000b5eb  xor     r15d, r15d
0x18000b5ee  xor     bpl, bpl
0x18000b5f1  mov     r12, r8
0x18000b5f4  mov     rsi, rcx
0x18000b5f7  test    edx, edx
0x18000b5f9  jnz     short loc_18000B648
0x18000b5fb  lea     rdi, UmpoDriverOverrideCacheArray
0x18000b602  mov     edx, 5Ch ; '\'; Ch
0x18000b607  call    cs:__imp_wcsrchr
0x18000b60d  mov     rbx, rax
0x18000b610  test    rax, rax
0x18000b613  jz      short loc_18000B65B
0x18000b615  add     rbx, 2
0x18000b619  xor     esi, esi
0x18000b61b  cmp     esi, 0Ah
0x18000b61e  jnb     short loc_18000B632
0x18000b620  mov     r14d, esi
0x18000b623  add     r14, r14
0x18000b626  mov     rdx, [rdi+r14*8]
0x18000b62a  test    rdx, rdx
0x18000b62d  jnz     short loc_18000B669
0x18000b62f  mov     bpl, 1
0x18000b632  mov     [r12], r15d
0x18000b636  mov     al, bpl
0x18000b639  add     rsp, 20h
0x18000b63d  pop     r15
0x18000b63f  pop     r14
0x18000b641  pop     r12
0x18000b643  pop     rdi
0x18000b644  pop     rsi
0x18000b645  pop     rbp
0x18000b646  pop     rbx
0x18000b647  retn
0x18000b648  sub     edx, 1
0x18000b64b  jz      short loc_18000B660
0x18000b64d  cmp     edx, 1
0x18000b650  jnz     short loc_18000B632
0x18000b652  lea     rdi, UmpoServiceOverrideCacheArray
0x18000b659  jmp     short loc_18000B602
0x18000b65b  mov     rbx, rsi
0x18000b65e  jmp     short loc_18000B619
0x18000b660  lea     rdi, UmpoProcessOverrideCacheArray
0x18000b667  jmp     short loc_18000B602
0x18000b669  mov     rcx, rbx
0x18000b66c  call    cs:__imp__o__wcsicmp
0x18000b672  test    eax, eax
0x18000b674  jz      short loc_18000B67A
0x18000b676  inc     esi
0x18000b678  jmp     short loc_18000B61B
0x18000b67a  mov     r15d, [rdi+r14*8+8]
0x18000b67f  jmp     short loc_18000B62F
```
