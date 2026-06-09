# WerpGetRegistryTimeoutValue

- ea: `0x14000f54c`
- end: `0x14000f5ae`
- name: `WerpGetRegistryTimeoutValue`
- size: `98`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, unsigned int, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000f6d8`
- `0x14000fba0`
- `0x140012588`

## callees

- `0x14000f54c`
- `0x14000f5b4`

## pseudocode

```c
__int64 __fastcall WerpGetRegistryTimeoutValue(void *a1, struct _UNICODE_STRING *a2, unsigned int a3, __int64 *a4)
{
  __int64 v4; // rbx
  __int64 result; // rax
  __int64 v7; // rcx
  unsigned int v8; // [rsp+48h] [rbp+20h] BYREF

  v4 = a3;
  v8 = 0;
  if ( !a4 )
    return 3221225485LL;
  result = WerpGetRegistryUlongValue(a1, a2, a3, &v8);
  if ( (int)result < 0 || (v7 = 36000000000LL * v8, v7 < 0) )
    v7 = 36000000000LL * v4;
  *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x14000f54c  mov     [rsp+arg_0], rbx
0x14000f551  push    rdi
0x14000f552  sub     rsp, 20h
0x14000f556  mov     ebx, r8d
0x14000f559  mov     rdi, r9
0x14000f55c  mov     [rsp+28h+arg_18], 0
0x14000f564  test    r9, r9
0x14000f567  jnz     short loc_14000F570
0x14000f569  mov     eax, 0C000000Dh
0x14000f56e  jmp     short loc_14000F5A2
0x14000f570  lea     r9, [rsp+28h+arg_18]
0x14000f575  mov     r8d, ebx
0x14000f578  call    WerpGetRegistryUlongValue
0x14000f57d  mov     rdx, 861C46800h
0x14000f587  test    eax, eax
0x14000f589  js      short loc_14000F598
0x14000f58b  mov     ecx, [rsp+28h+arg_18]
0x14000f58f  imul    rcx, rdx
0x14000f593  test    rcx, rcx
0x14000f596  jns     short loc_14000F59F
0x14000f598  mov     rcx, rbx
0x14000f59b  imul    rcx, rdx
0x14000f59f  mov     [rdi], rcx
0x14000f5a2  mov     rbx, [rsp+28h+arg_0]
0x14000f5a7  add     rsp, 20h
0x14000f5ab  pop     rdi
0x14000f5ac  retn
```
