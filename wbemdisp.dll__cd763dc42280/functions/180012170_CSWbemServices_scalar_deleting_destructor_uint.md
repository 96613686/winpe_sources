# CSWbemServices::`scalar deleting destructor'(uint)

- ea: `0x180012170`
- end: `0x180012284`
- name: `??_GCSWbemServices@@QEAAPEAXI@Z`
- size: `276`
- prototype: `void *__fastcall(CSWbemServices *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003cb0`
- `0x180012130`

## callees

- `0x180012170`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180012211`
- `OLEAUT32!__imp_SysFreeString` at `0x18001221c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001224d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012211`
- `OLEAUT32!__imp_SysFreeString` at `0x18001221c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001224d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012226`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180012226`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSWbemServices *__fastcall CSWbemServices::`scalar deleting destructor'(CSWbemServices *this)
{
  __int64 v2; // rcx
  OLECHAR *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &CSWbemServices::`vftable'{for `ISWbemServicesEx'};
  *((_QWORD *)this + 1) = &CSWbemServices::`vftable'{for `IDispatchEx'};
  *((_QWORD *)this + 2) = &CSWbemServices::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &CSWbemServices::`vftable'{for `ISWbemInternalServices'};
  *((_QWORD *)this + 4) = &CSWbemServices::`vftable'{for `IProvideClassInfo'};
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 17) = 0;
  }
  v3 = (OLECHAR *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    SysFreeString(v3);
    *((_QWORD *)this + 6) = 0;
  }
  v4 = *((_QWORD *)this + 19);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 19) = 0;
  }
  _InterlockedDecrement(&g_cObj);
  *((_QWORD *)this + 7) = &CDispatchHelp::`vftable';
  v5 = *((_QWORD *)this + 10);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 10) = 0;
  }
  v6 = *((_QWORD *)this + 11);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 11) = 0;
  }
  SysFreeString(*((BSTR *)this + 8));
  SysFreeString(*((BSTR *)this + 5));
  CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180012170  mov     [rsp+arg_0], rbx
0x180012175  push    rdi
0x180012176  sub     rsp, 20h
0x18001217a  mov     rbx, rcx
0x18001217d  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x180012184  mov     [rcx], rax
0x180012187  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x18001218e  mov     [rcx+8], rax
0x180012192  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x180012199  mov     [rcx+10h], rax
0x18001219d  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x1800121a4  mov     [rcx+18h], rax
0x1800121a8  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x1800121af  mov     [rcx+20h], rax
0x1800121b3  mov     rcx, [rcx+88h]
0x1800121ba  xor     edi, edi
0x1800121bc  test    rcx, rcx
0x1800121bf  jz      short loc_1800121D4
0x1800121c1  mov     rax, [rcx]
0x1800121c4  mov     rax, [rax+10h]
0x1800121c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121cd  mov     [rbx+88h], rdi
0x1800121d4  mov     rcx, [rbx+30h]; bstrString
0x1800121d8  test    rcx, rcx
0x1800121db  jnz     short loc_18001224D
0x1800121dd  mov     rcx, [rbx+98h]
0x1800121e4  test    rcx, rcx
0x1800121e7  jnz     short loc_180012259
0x1800121e9  lock dec cs:?g_cObj@@3JA; long g_cObj
0x1800121f0  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x1800121f7  mov     [rbx+38h], rax
0x1800121fb  mov     rcx, [rbx+50h]
0x1800121ff  test    rcx, rcx
0x180012202  jnz     short loc_18001223B
0x180012204  mov     rcx, [rbx+58h]
0x180012208  test    rcx, rcx
0x18001220b  jnz     short loc_180012271
0x18001220d  mov     rcx, [rbx+40h]; bstrString
0x180012211  call    cs:__imp_SysFreeString
0x180012217  nop
0x180012218  mov     rcx, [rbx+28h]; bstrString
0x18001221c  call    cs:__imp_SysFreeString
0x180012222  nop
0x180012223  mov     rcx, rbx
0x180012226  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001222c  nop
0x18001222d  mov     rax, rbx
0x180012230  mov     rbx, [rsp+28h+arg_0]
0x180012235  add     rsp, 20h
0x180012239  pop     rdi
0x18001223a  retn
0x18001223b  mov     rax, [rcx]
0x18001223e  mov     rax, [rax+10h]
0x180012242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012247  mov     [rbx+50h], rdi
0x18001224b  jmp     short loc_180012204
0x18001224d  call    cs:__imp_SysFreeString
0x180012253  mov     [rbx+30h], rdi
0x180012257  jmp     short loc_1800121DD
0x180012259  mov     rax, [rcx]
0x18001225c  mov     rax, [rax+10h]
0x180012260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012265  mov     [rbx+98h], rdi
0x18001226c  jmp     loc_1800121E9
0x180012271  mov     rax, [rcx]
0x180012274  mov     rax, [rax+10h]
0x180012278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001227d  mov     [rbx+58h], rdi
0x180012281  jmp     short loc_18001220D
```
