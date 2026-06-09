# std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Delete_this(bool)

- ea: `0x1800157f0`
- end: `0x180015825`
- name: `?_Delete_this@?$_Func_impl@U?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@V?$allocator@V?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@@2@XAEAVProxy@Cache@@U_Nil@2@U62@U62@U62@U62@U62@U62@U62@U62@@std@@EEAAX_N@Z`
- size: `53`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800157f0`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015814`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015814`

## pseudocode

```c
void __fastcall std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x1800157f0  mov     [rsp+arg_0], rbx
0x1800157f5  push    rdi
0x1800157f6  sub     rsp, 20h
0x1800157fa  mov     rax, [rcx]
0x1800157fd  mov     bl, dl
0x1800157ff  xor     edx, edx
0x180015801  mov     rdi, rcx
0x180015804  mov     rax, [rax+28h]
0x180015808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580d  test    bl, bl
0x18001580f  jz      short loc_18001581A
0x180015811  mov     rcx, rdi
0x180015814  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001581a  mov     rbx, [rsp+28h+arg_0]
0x18001581f  add     rsp, 20h
0x180015823  pop     rdi
0x180015824  retn
```
