# std::_dynamic_atexit_destructor_for__initlocks___0

- ea: `0x140067940`
- end: `0x14006797c`
- name: `std::_dynamic_atexit_destructor_for__initlocks___0`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140067940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067960`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067960`

## pseudocode

```c
char *std::_dynamic_atexit_destructor_for__initlocks___0()
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
0x140067940  push    rbx
0x140067942  sub     rsp, 20h
0x140067946  or      eax, 0FFFFFFFFh
0x140067949  lock xadd cs:dword_140085AE0, eax
0x140067951  cmp     eax, 1
0x140067954  jns     short loc_140067976
0x140067956  lea     rbx, CriticalSection
0x14006795d  mov     rcx, rbx; lpCriticalSection
0x140067960  call    cs:__imp_DeleteCriticalSection
0x140067966  lea     rax, ?isInitialized@?$Module@$00V?$DefaultModule@$01@Details@WRL@Microsoft@@@WRL@Microsoft@@0_NA; bool Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized
0x14006796d  add     rbx, 28h ; '('
0x140067971  cmp     rbx, rax
0x140067974  jnz     short loc_14006795D
0x140067976  add     rsp, 20h
0x14006797a  pop     rbx
0x14006797b  retn
```
