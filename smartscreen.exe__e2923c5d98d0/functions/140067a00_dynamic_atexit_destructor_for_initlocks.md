# _dynamic_atexit_destructor_for__initlocks__

- ea: `0x140067a00`
- end: `0x140067a3c`
- name: `_dynamic_atexit_destructor_for__initlocks__`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140067a00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067a20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067a20`

## pseudocode

```c
char *dynamic_atexit_destructor_for__initlocks__()
{
  char *result; // rax
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  result = (char *)(unsigned int)_InterlockedExchangeAdd(&dword_140085AE0, 0xFFFFFFFF);
  if ( (int)result - 1 < 0 )
  {
    v1 = &CriticalSection;
    do
    {
      DeleteCriticalSection(v1);
      result = &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized;
      ++v1;
    }
    while ( v1 != (struct _RTL_CRITICAL_SECTION *)&Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized );
  }
  return result;
}

```

## disassembly

```asm
0x140067a00  push    rbx
0x140067a02  sub     rsp, 20h
0x140067a06  or      eax, 0FFFFFFFFh
0x140067a09  lock xadd cs:dword_140085AE0, eax
0x140067a11  cmp     eax, 1
0x140067a14  jns     short loc_140067A36
0x140067a16  lea     rbx, CriticalSection
0x140067a1d  mov     rcx, rbx; lpCriticalSection
0x140067a20  call    cs:__imp_DeleteCriticalSection
0x140067a26  lea     rax, ?isInitialized@?$Module@$00V?$DefaultModule@$01@Details@WRL@Microsoft@@@WRL@Microsoft@@0_NA; bool Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized
0x140067a2d  add     rbx, 28h ; '('
0x140067a31  cmp     rbx, rax
0x140067a34  jnz     short loc_140067A1D
0x140067a36  add     rsp, 20h
0x140067a3a  pop     rbx
0x140067a3b  retn
```
