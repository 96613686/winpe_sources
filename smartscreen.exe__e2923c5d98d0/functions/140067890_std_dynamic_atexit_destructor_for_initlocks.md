# std::_dynamic_atexit_destructor_for__initlocks__

- ea: `0x140067890`
- end: `0x1400678cc`
- name: `std::_dynamic_atexit_destructor_for__initlocks__`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140067890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400678b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400678b0`

## pseudocode

```c
char *std::_dynamic_atexit_destructor_for__initlocks__()
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
0x140067890  push    rbx
0x140067892  sub     rsp, 20h
0x140067896  or      eax, 0FFFFFFFFh
0x140067899  lock xadd cs:dword_140085AE0, eax
0x1400678a1  cmp     eax, 1
0x1400678a4  jns     short loc_1400678C6
0x1400678a6  lea     rbx, CriticalSection
0x1400678ad  mov     rcx, rbx; lpCriticalSection
0x1400678b0  call    cs:__imp_DeleteCriticalSection
0x1400678b6  lea     rax, ?isInitialized@?$Module@$00V?$DefaultModule@$01@Details@WRL@Microsoft@@@WRL@Microsoft@@0_NA; bool Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized
0x1400678bd  add     rbx, 28h ; '('
0x1400678c1  cmp     rbx, rax
0x1400678c4  jnz     short loc_1400678AD
0x1400678c6  add     rsp, 20h
0x1400678ca  pop     rbx
0x1400678cb  retn
```
