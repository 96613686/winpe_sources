# std::_dynamic_atexit_destructor_for__initlocks__

- ea: `0x1400696d0`
- end: `0x140069713`
- name: `std::_dynamic_atexit_destructor_for__initlocks__`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400696d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400696f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400696f0`

## pseudocode

```c
char *std::_dynamic_atexit_destructor_for__initlocks__()
{
  char *result; // rax
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  result = (char *)(unsigned int)_InterlockedExchangeAdd(&dword_140087AE0, 0xFFFFFFFF);
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
0x1400696d0  push    rbx
0x1400696d2  sub     rsp, 20h
0x1400696d6  or      eax, 0FFFFFFFFh
0x1400696d9  lock xadd cs:dword_140087AE0, eax
0x1400696e1  cmp     eax, 1
0x1400696e4  jns     short loc_14006970C
0x1400696e6  lea     rbx, CriticalSection
0x1400696ed  mov     rcx, rbx; lpCriticalSection
0x1400696f0  call    cs:__imp_DeleteCriticalSection
0x1400696f7  nop     dword ptr [rax+rax+00h]
0x1400696fc  lea     rax, ?isInitialized@?$Module@$00V?$DefaultModule@$01@Details@WRL@Microsoft@@@WRL@Microsoft@@0_NA; bool Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<2>>::isInitialized
0x140069703  add     rbx, 28h ; '('
0x140069707  cmp     rbx, rax
0x14006970a  jnz     short loc_1400696ED
0x14006970c  add     rsp, 20h
0x140069710  pop     rbx
0x140069711  retn
```
