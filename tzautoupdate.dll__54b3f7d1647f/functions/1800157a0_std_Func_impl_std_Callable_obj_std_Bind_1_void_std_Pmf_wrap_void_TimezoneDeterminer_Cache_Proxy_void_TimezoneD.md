# std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Copy(void *)

- ea: `0x1800157a0`
- end: `0x1800157e7`
- name: `?_Copy@?$_Func_impl@U?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@V?$allocator@V?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@@2@XAEAVProxy@Cache@@U_Nil@2@U62@U62@U62@U62@U62@U62@U62@U62@@std@@UEAAPEAV?$_Func_base@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@2@PEAX@Z`
- size: `71`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002050`
- `0x1800021f8`
- `0x180014a28`
- `0x1800157a0`

## pseudocode

```c
__int64 __fastcall std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Copy(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v3; // r11
  __int64 v5; // r11

  v3 = a2;
  if ( !a2 )
  {
    v3 = operator new(0x28u);
    if ( !v3 )
      std::_Xbad_alloc();
  }
  *v3 = &std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(
    (__int64)(v3 + 1),
    a1 + 8,
    a3);
  return v5;
}

```

## disassembly

```asm
0x1800157a0  push    rbx
0x1800157a2  sub     rsp, 20h
0x1800157a6  mov     r11, rdx
0x1800157a9  mov     rbx, rcx
0x1800157ac  test    rdx, rdx
0x1800157af  jnz     short loc_1800157C7
0x1800157b1  lea     ecx, [rdx+28h]; Size
0x1800157b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800157b9  mov     r11, rax
0x1800157bc  test    rax, rax
0x1800157bf  jnz     short loc_1800157C7
0x1800157c1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800157c7  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@V?$allocator@V?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@@2@XAEAVProxy@Cache@@U_Nil@2@U62@U62@U62@U62@U62@U62@U62@U62@@std@@6B@; const std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x1800157ce  lea     rdx, [rbx+8]
0x1800157d2  mov     [r11], rax
0x1800157d5  lea     rcx, [r11+8]
0x1800157d9  call    ??$?0V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@@?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@QEAA@$$QEAV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@1@@Z; std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil> &&)
0x1800157de  mov     rax, r11
0x1800157e1  add     rsp, 20h
0x1800157e5  pop     rbx
0x1800157e6  retn
```
