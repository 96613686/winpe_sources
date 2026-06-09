# std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil> &&)

- ea: `0x180014a28`
- end: `0x180014a3c`
- name: `??$?0V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@@?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@QEAA@$$QEAV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@1@@Z`
- size: `20`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014c60`
- `0x1800157a0`

## callees

- `0x1800149d0`

## pseudocode

```c
__int64 __fastcall std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r10

  std::_Callable_base<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_base<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(
    a1,
    a2,
    a3);
  return v3;
}

```

## disassembly

```asm
0x180014a28  sub     rsp, 28h
0x180014a2c  mov     r10, rcx
0x180014a2f  call    ??$?0AEAV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@@?$_Callable_base@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@QEAA@AEAV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@1@@Z; std::_Callable_base<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_base<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil> &)
0x180014a34  mov     rax, r10
0x180014a37  add     rsp, 28h
0x180014a3b  retn
```
