# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001ee4c`
- end: `0x18001ef2c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18001dc54`
- `0x18001ee4c`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)operator new(0xB8u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18001ee4c  mov     rax, rsp
0x18001ee4f  mov     [rax+18h], r8
0x18001ee53  mov     [rax+10h], rdx
0x18001ee57  mov     [rax+8], rcx
0x18001ee5b  push    rbx
0x18001ee5c  push    rsi
0x18001ee5d  push    rdi
0x18001ee5e  sub     rsp, 30h
0x18001ee62  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001ee6a  mov     rdi, r8
0x18001ee6d  test    r8, r8
0x18001ee70  jnz     short loc_18001EE7C
0x18001ee72  mov     eax, 80004003h
0x18001ee77  jmp     loc_18001EF23
0x18001ee7c  mov     qword ptr [r8], 0
0x18001ee83  mov     esi, 8007000Eh
0x18001ee88  mov     [rsp+48h+arg_8], esi
0x18001ee8c  mov     [rsp+48h+arg_0], 0
0x18001ee95  mov     ecx, 0B8h; Size
0x18001ee9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee9f  mov     rbx, rax
0x18001eea2  mov     [rsp+48h+arg_18], rax
0x18001eea7  test    rbx, rbx
0x18001eeaa  jz      short loc_18001EED2
0x18001eeac  mov     rcx, rax; this
0x18001eeaf  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x18001eeb4  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x18001eebb  mov     [rbx], rax
0x18001eebe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001eec5  mov     rax, [rcx]
0x18001eec8  mov     rax, [rax+8]
0x18001eecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eed1  nop
0x18001eed2  mov     [rsp+48h+arg_0], rbx
0x18001eed7  jmp     short loc_18001EEE7
0x18001eed9  mov     rdi, [rsp+48h+arg_10]
0x18001eede  mov     esi, [rsp+48h+arg_8]
0x18001eee2  mov     rbx, [rsp+48h+arg_0]
0x18001eee7  test    rbx, rbx
0x18001eeea  jz      short loc_18001EF21
0x18001eeec  mov     rax, [rbx]
0x18001eeef  mov     r8, rdi
0x18001eef2  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001eef9  mov     rcx, rbx
0x18001eefc  mov     rax, [rax]
0x18001eeff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef04  mov     esi, eax
0x18001ef06  test    eax, eax
0x18001ef08  jz      short loc_18001EF21
0x18001ef0a  mov     rdx, [rbx]
0x18001ef0d  mov     rax, [rdx+88h]
0x18001ef14  mov     edx, 1
0x18001ef19  mov     rcx, rbx
0x18001ef1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef21  mov     eax, esi
0x18001ef23  add     rsp, 30h
0x18001ef27  pop     rdi
0x18001ef28  pop     rsi
0x18001ef29  pop     rbx
0x18001ef2a  retn
```
