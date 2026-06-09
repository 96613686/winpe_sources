# _dynamic_initializer_for__BrainInputDefault::nameGetSessionForBrain__

- ea: `0x180002140`
- end: `0x18000216d`
- name: `_dynamic_initializer_for__BrainInputDefault::nameGetSessionForBrain__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002829c`
- `0x180042ba4`

## string_xrefs

- `0x18000214a`: `DllGetSessionForBrain`

## pseudocode

```c
int dynamic_initializer_for__BrainInputDefault::nameGetSessionForBrain__()
{
  std::string::_Construct<1,char const *>(&BrainInputDefault::nameGetSessionForBrain, "DllGetSessionForBrain", 0x15u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__BrainInputDefault::nameGetSessionForBrain__);
}

```

## disassembly

```asm
0x180002140  sub     rsp, 28h
0x180002144  mov     r8d, 15h
0x18000214a  lea     rdx, aDllgetsessionf_1; "DllGetSessionForBrain"
0x180002151  lea     rcx, ?nameGetSessionForBrain@BrainInputDefault@@0V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const BrainInputDefault::nameGetSessionForBrain
0x180002158  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000215d  lea     rcx, _dynamic_atexit_destructor_for__BrainInputDefault__nameGetSessionForBrain__
0x180002164  add     rsp, 28h
0x180002168  jmp     atexit
```
