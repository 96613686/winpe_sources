# UninitializeEvents

- ea: `0x18000bc88`
- end: `0x18000bcda`
- name: `UninitializeEvents`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b5f4`
- `0x18000be58`

## callees

- `0x18000bc88`
- `0x18000bce0`
- `0x18003dd2c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000bcad`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bcad`

## pseudocode

```c
unsigned __int8 UninitializeEvents()
{
  unsigned __int8 result; // al

  CEventUnregister();
  result = byte_1800A5340;
  _W32TimeRegistrationHandle = 0;
  if ( byte_1800A5340 )
  {
    RtlDeleteCriticalSection(&stru_1800A52B0);
    byte_1800A5340 = 0;
    return (unsigned __int8)memset_0(&stru_1800A52B0, 0, 0x98u);
  }
  return result;
}

```

## disassembly

```asm
0x18000bc88  sub     rsp, 28h
0x18000bc8c  call    CEventUnregister
0x18000bc91  mov     al, cs:byte_1800A5340
0x18000bc97  mov     cs:?_W32TimeRegistrationHandle@@3_KA, 0; unsigned __int64 _W32TimeRegistrationHandle
0x18000bca2  test    al, al
0x18000bca4  jz      short loc_18000BCD4
0x18000bca6  lea     rcx, stru_1800A52B0; CriticalSection
0x18000bcad  call    cs:__imp_RtlDeleteCriticalSection
0x18000bcb4  nop     dword ptr [rax+rax+00h]
0x18000bcb9  xor     edx, edx; Val
0x18000bcbb  mov     cs:byte_1800A5340, 0
0x18000bcc2  mov     r8d, 98h; Size
0x18000bcc8  lea     rcx, stru_1800A52B0; void *
0x18000bccf  call    memset_0
0x18000bcd4  add     rsp, 28h
0x18000bcd8  retn
```
