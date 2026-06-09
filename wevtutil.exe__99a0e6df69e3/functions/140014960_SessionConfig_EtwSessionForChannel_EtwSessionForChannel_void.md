# SessionConfig::EtwSessionForChannel::~EtwSessionForChannel(void)

- ea: `0x140014960`
- end: `0x14001497f`
- name: `??1EtwSessionForChannel@SessionConfig@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(SessionConfig::EtwSessionForChannel *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001291c`
- `0x140013658`
- `0x1400151ec`
- `0x14001b3f8`
- `0x14002d8d4`
- `0x14002d8e4`
- `0x14002ddb0`
- `0x14002e0cc`
- `0x1400326e5`
- `0x140032787`
- `0x14003284d`
- `0x1400336de`
- `0x14003378a`
- `0x1400337e4`

## callees

- `0x140004ae0`

## pseudocode

```c
void __fastcall SessionConfig::EtwSessionForChannel::~EtwSessionForChannel(SessionConfig::EtwSessionForChannel *this)
{
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(this);
}

```

## disassembly

```asm
0x140014960  push    rbx
0x140014962  sub     rsp, 20h
0x140014966  mov     rbx, rcx
0x140014969  add     rcx, 20h ; ' '
0x14001496d  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140014972  mov     rcx, rbx
0x140014975  add     rsp, 20h
0x140014979  pop     rbx
0x14001497a  jmp     ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
```
