# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002b244`
- end: `0x18002b324`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18002b004`
- `0x18002b244`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v8 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v8;
  }
  if ( v7 )
  {
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18002b244  mov     rax, rsp
0x18002b247  mov     [rax+18h], r8
0x18002b24b  mov     [rax+10h], rdx
0x18002b24f  mov     [rax+8], rcx
0x18002b253  push    rbx
0x18002b254  push    rsi
0x18002b255  push    rdi
0x18002b256  sub     rsp, 30h
0x18002b25a  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18002b262  mov     rdi, r8
0x18002b265  test    r8, r8
0x18002b268  jnz     short loc_18002B274
0x18002b26a  mov     eax, 80004003h
0x18002b26f  jmp     loc_18002B31B
0x18002b274  mov     qword ptr [r8], 0
0x18002b27b  mov     esi, 8007000Eh
0x18002b280  mov     [rsp+48h+arg_8], esi
0x18002b284  mov     [rsp+48h+arg_0], 0
0x18002b28d  mov     ecx, 68h ; 'h'; Size
0x18002b292  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b297  mov     rbx, rax
0x18002b29a  mov     [rsp+48h+arg_18], rax
0x18002b29f  test    rbx, rbx
0x18002b2a2  jz      short loc_18002B2CA
0x18002b2a4  mov     rcx, rax; this
0x18002b2a7  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x18002b2ac  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002b2b3  mov     [rbx], rax
0x18002b2b6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002b2bd  mov     rax, [rcx]
0x18002b2c0  mov     rax, [rax+8]
0x18002b2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2c9  nop
0x18002b2ca  mov     [rsp+48h+arg_0], rbx
0x18002b2cf  jmp     short loc_18002B2DF
0x18002b2d1  mov     rdi, [rsp+48h+arg_10]
0x18002b2d6  mov     esi, [rsp+48h+arg_8]
0x18002b2da  mov     rbx, [rsp+48h+arg_0]
0x18002b2df  test    rbx, rbx
0x18002b2e2  jz      short loc_18002B319
0x18002b2e4  mov     rax, [rbx]
0x18002b2e7  mov     r8, rdi
0x18002b2ea  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002b2f1  mov     rcx, rbx
0x18002b2f4  mov     rax, [rax]
0x18002b2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2fc  mov     esi, eax
0x18002b2fe  test    eax, eax
0x18002b300  jz      short loc_18002B319
0x18002b302  mov     rdx, [rbx]
0x18002b305  mov     rax, [rdx+88h]
0x18002b30c  mov     edx, 1
0x18002b311  mov     rcx, rbx
0x18002b314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b319  mov     eax, esi
0x18002b31b  add     rsp, 30h
0x18002b31f  pop     rdi
0x18002b320  pop     rsi
0x18002b321  pop     rbx
0x18002b322  retn
```
