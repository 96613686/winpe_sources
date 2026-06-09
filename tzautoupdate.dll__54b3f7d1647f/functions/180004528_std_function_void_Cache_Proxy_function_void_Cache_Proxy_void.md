# std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>(void)

- ea: `0x180004528`
- end: `0x180004546`
- name: `??1?$function@$$A6AXAEAVProxy@Cache@@@Z@std@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004738`
- `0x1800049c8`
- `0x180014c60`
- `0x18001c52c`

## callees

- `0x18000ae64`

## pseudocode

```c
__int64 __fastcall std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>(__int64 a1)
{
  std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(a1);
  return std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(a1);
}

```

## disassembly

```asm
0x180004528  push    rbx
0x18000452a  sub     rsp, 20h
0x18000452e  mov     rbx, rcx
0x180004531  call    ?_Tidy@?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@IEAAXXZ; std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(void)
0x180004536  nop
0x180004537  mov     rcx, rbx
0x18000453a  call    ?_Tidy@?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@IEAAXXZ; std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(void)
0x18000453f  nop
0x180004540  add     rsp, 20h
0x180004544  pop     rbx
0x180004545  retn
```
