# TimezoneDeterminer::TimezoneDeterminer(Cache &,std::vector<std::unique_ptr<Finder,std::default_delete<Finder>>,std::allocator<std::unique_ptr<Finder,std::default_delete<Finder>>>> &&,void *)

- ea: `0x180014c60`
- end: `0x180014df2`
- name: `??0TimezoneDeterminer@@QEAA@AEAVCache@@$$QEAV?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@PEAX@Z`
- size: `402`
- prototype: `__int64 *__fastcall(__int64 *pv, __int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180004018`

## callees

- `0x180002050`
- `0x1800021f8`
- `0x180004528`
- `0x18000ae64`
- `0x180014a28`
- `0x180014b8c`
- `0x180014c60`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014cd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014cd1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014d25`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014d25`

## string_xrefs

- `0x180014d17`: `SYSTEM\CurrentControlSet\Services\tzautoupdate\Config`
- `0x180014d10`: `ServiceInactivityTimeoutMs`

## pseudocode

```c
__int64 *__fastcall TimezoneDeterminer::TimezoneDeterminer(__int64 *pv, __int64 a2, __int64 *a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rsi
  _QWORD *v9; // r11
  _BYTE *v10; // r11
  __int64 v11; // rbx
  __int64 v12; // rdx
  _BYTE v14[24]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v15[24]; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE *v16; // [rsp+70h] [rbp+27h]
  DWORD pcbData; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 *v18; // [rsp+C0h] [rbp+77h] BYREF
  _BYTE *v19; // [rsp+C8h] [rbp+7Fh]

  *pv = a2;
  pv[1] = 0;
  pv[2] = 0;
  pv[3] = 0;
  pv[1] = *a3;
  pv[2] = a3[1];
  pv[3] = a3[2];
  *a3 = 0;
  a3[1] = 0;
  a3[2] = 0;
  pv[5] = (__int64)CreateThreadpoolTimer(TimezoneDeterminer::StopServiceTimerCallback, pv, 0);
  pv[6] = a4;
  *((_BYTE *)pv + 56) = a4 == 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\tzautoupdate\\Config",
         L"ServiceInactivityTimeoutMs",
         0x10u,
         0,
         pv + 4,
         &pcbData) )
  {
    *((_DWORD *)pv + 8) = 60000;
  }
  v7 = *pv;
  v19 = v15;
  v18 = pv;
  v8 = std::bind<void,TimezoneDeterminer,Cache::Proxy &,TimezoneDeterminer *,std::_Ph<1> &>(v14, v6, &v18);
  v16 = 0;
  v9 = operator new(0x28u);
  if ( !v9 )
    std::_Xbad_alloc();
  *v9 = &std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(
    v9 + 1,
    v8);
  v16 = v10;
  v18 = (__int64 *)v15;
  v11 = v7 + 8;
  if ( (_BYTE *)v11 != v15 )
  {
    std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(v11);
    if ( v16 )
    {
      if ( v16 == v15 )
        v12 = v11;
      else
        v12 = 0;
      *(_QWORD *)(v11 + 24) = (**(__int64 (__fastcall ***)(_BYTE *, __int64))v16)(v16, v12);
    }
    else
    {
      *(_QWORD *)(v11 + 24) = 0;
    }
  }
  std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>(v15);
  return pv;
}

```

## disassembly

```asm
0x180014c60  mov     [rsp-8+arg_0], rcx
0x180014c65  push    rbp
0x180014c66  push    rbx
0x180014c67  push    rsi
0x180014c68  push    rdi
0x180014c69  lea     rbp, [rsp-3Fh]
0x180014c6e  sub     rsp, 88h
0x180014c75  mov     rbx, r9
0x180014c78  mov     rdi, rcx
0x180014c7b  mov     [rcx], rdx
0x180014c7e  mov     qword ptr [rcx+8], 0
0x180014c86  mov     qword ptr [rcx+10h], 0
0x180014c8e  mov     qword ptr [rcx+18h], 0
0x180014c96  mov     rax, [r8]
0x180014c99  mov     [rcx+8], rax
0x180014c9d  mov     rax, [r8+8]
0x180014ca1  mov     [rcx+10h], rax
0x180014ca5  mov     rax, [r8+10h]
0x180014ca9  mov     [rcx+18h], rax
0x180014cad  mov     qword ptr [r8], 0
0x180014cb4  mov     qword ptr [r8+8], 0
0x180014cbc  mov     qword ptr [r8+10h], 0
0x180014cc4  xor     r8d, r8d; pcbe
0x180014cc7  mov     rdx, rcx; pv
0x180014cca  lea     rcx, ?StopServiceTimerCallback@TimezoneDeterminer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014cd1  call    cs:__imp_CreateThreadpoolTimer
0x180014cd7  mov     [rdi+28h], rax
0x180014cdb  mov     [rdi+30h], rbx
0x180014cdf  test    rbx, rbx
0x180014ce2  setz    al
0x180014ce5  mov     [rdi+38h], al
0x180014ce8  mov     [rbp+57h+arg_8], 4
0x180014cef  lea     rbx, [rdi+20h]
0x180014cf3  lea     rax, [rbp+57h+arg_8]
0x180014cf7  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180014cfc  mov     [rsp+0A0h+pvData], rbx; pvData
0x180014d01  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180014d0a  mov     r9d, 10h; dwFlags
0x180014d10  lea     r8, aServiceinactiv; "ServiceInactivityTimeoutMs"
0x180014d17  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\tz"...
0x180014d1e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180014d25  call    cs:__imp_RegGetValueW
0x180014d2b  test    eax, eax
0x180014d2d  jz      short loc_180014D35
0x180014d2f  mov     dword ptr [rbx], 0EA60h
0x180014d35  mov     rbx, [rdi]
0x180014d38  lea     rax, [rbp+57h+var_48]
0x180014d3c  mov     [rbp+57h+arg_18], rax
0x180014d40  mov     [rbp+57h+arg_10], rdi
0x180014d44  lea     r8, [rbp+57h+arg_10]
0x180014d48  lea     rcx, [rbp+57h+var_60]
0x180014d4c  call    ??$bind@XVTimezoneDeterminer@@AEAVProxy@Cache@@PEAV1@AEAV?$_Ph@$00@std@@@std@@YA?AV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@0@Q8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@Z$$QEAPEAV2@AEAV?$_Ph@$00@0@@Z; std::bind<void,TimezoneDeterminer,Cache::Proxy &,TimezoneDeterminer *,std::_Ph<1> &>(void (TimezoneDeterminer::*const)(Cache::Proxy &),TimezoneDeterminer * &&,std::_Ph<1> &)
0x180014d51  mov     rsi, rax
0x180014d54  mov     [rbp+57h+var_30], 0
0x180014d5c  mov     ecx, 28h ; '('; Size
0x180014d61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014d66  mov     r11, rax
0x180014d69  test    rax, rax
0x180014d6c  jnz     short loc_180014D74
0x180014d6e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180014d74  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@V?$allocator@V?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@@2@XAEAVProxy@Cache@@U_Nil@2@U62@U62@U62@U62@U62@U62@U62@U62@@std@@6B@; const std::_Func_impl<std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>,std::allocator<std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x180014d7b  mov     [r11], rax
0x180014d7e  lea     rcx, [r11+8]
0x180014d82  mov     rdx, rsi
0x180014d85  call    ??$?0V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@@?$_Callable_obj@V?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@std@@$0A@@std@@QEAA@$$QEAV?$_Bind@$00XU?$_Pmf_wrap@P8TimezoneDeterminer@@EAAXAEAVProxy@Cache@@@ZXV1@AEAV23@U_Nil@std@@U45@U45@U45@U45@U45@U45@U45@U45@@std@@PEAVTimezoneDeterminer@@AEAV?$_Ph@$00@2@U_Nil@2@U52@U52@U52@U52@U52@U52@U52@@1@@Z; std::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>::_Callable_obj<std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,0>(std::_Bind<1,void,std::_Pmf_wrap<void (TimezoneDeterminer::*)(Cache::Proxy &),void,TimezoneDeterminer,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>,TimezoneDeterminer *,std::_Ph<1> &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil> &&)
0x180014d8a  mov     [rbp+57h+var_30], r11
0x180014d8e  lea     rax, [rbp+57h+var_48]
0x180014d92  mov     [rbp+57h+arg_10], rax
0x180014d96  add     rbx, 8
0x180014d9a  lea     rax, [rbp+57h+var_48]
0x180014d9e  cmp     rbx, rax
0x180014da1  jz      short loc_180014DD9
0x180014da3  mov     rcx, rbx
0x180014da6  call    ?_Tidy@?$_Func_class@XAEAVProxy@Cache@@U_Nil@std@@U34@U34@U34@U34@U34@U34@U34@U34@@std@@IEAAXXZ; std::_Func_class<void,Cache::Proxy &,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Tidy(void)
0x180014dab  mov     rcx, [rbp+57h+var_30]
0x180014daf  test    rcx, rcx
0x180014db2  jnz     short loc_180014DBA
0x180014db4  mov     [rbx+18h], rcx
0x180014db8  jmp     short loc_180014DD9
0x180014dba  mov     rax, [rcx]
0x180014dbd  mov     rax, [rax]
0x180014dc0  lea     rdx, [rbp+57h+var_48]
0x180014dc4  cmp     rcx, rdx
0x180014dc7  jnz     short loc_180014DCE
0x180014dc9  mov     rdx, rbx
0x180014dcc  jmp     short loc_180014DD0
0x180014dce  xor     edx, edx
0x180014dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd5  mov     [rbx+18h], rax
0x180014dd9  lea     rcx, [rbp+57h+var_48]
0x180014ddd  call    ??1?$function@$$A6AXAEAVProxy@Cache@@@Z@std@@QEAA@XZ; std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>(void)
0x180014de2  nop
0x180014de3  mov     rax, rdi
0x180014de6  add     rsp, 88h
0x180014ded  pop     rdi
0x180014dee  pop     rsi
0x180014def  pop     rbx
0x180014df0  pop     rbp
0x180014df1  retn
```
