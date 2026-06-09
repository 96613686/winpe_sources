# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002d8e4`
- end: `0x18002d9c4`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18002d478`
- `0x18002d8e4`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CElfImageEventTraceExtender *)operator new(0x50u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64))(*(_QWORD *)v7 + 160LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x18002d8e4  mov     rax, rsp
0x18002d8e7  mov     [rax+18h], r8
0x18002d8eb  mov     [rax+10h], rdx
0x18002d8ef  mov     [rax+8], rcx
0x18002d8f3  push    rbx
0x18002d8f4  push    rsi
0x18002d8f5  push    rdi
0x18002d8f6  sub     rsp, 30h
0x18002d8fa  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18002d902  mov     rdi, r8
0x18002d905  test    r8, r8
0x18002d908  jnz     short loc_18002D914
0x18002d90a  mov     eax, 80004003h
0x18002d90f  jmp     loc_18002D9BB
0x18002d914  mov     qword ptr [r8], 0
0x18002d91b  mov     esi, 8007000Eh
0x18002d920  mov     [rsp+48h+arg_8], esi
0x18002d924  mov     [rsp+48h+arg_0], 0
0x18002d92d  mov     ecx, 50h ; 'P'; Size
0x18002d932  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d937  mov     rbx, rax
0x18002d93a  mov     [rsp+48h+arg_18], rax
0x18002d93f  test    rbx, rbx
0x18002d942  jz      short loc_18002D96A
0x18002d944  mov     rcx, rax; this
0x18002d947  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x18002d94c  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x18002d953  mov     [rbx], rax
0x18002d956  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002d95d  mov     rax, [rcx]
0x18002d960  mov     rax, [rax+8]
0x18002d964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d969  nop
0x18002d96a  mov     [rsp+48h+arg_0], rbx
0x18002d96f  jmp     short loc_18002D97F
0x18002d971  mov     rdi, [rsp+48h+arg_10]
0x18002d976  mov     esi, [rsp+48h+arg_8]
0x18002d97a  mov     rbx, [rsp+48h+arg_0]
0x18002d97f  test    rbx, rbx
0x18002d982  jz      short loc_18002D9B9
0x18002d984  mov     rax, [rbx]
0x18002d987  mov     r8, rdi
0x18002d98a  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002d991  mov     rcx, rbx
0x18002d994  mov     rax, [rax]
0x18002d997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d99c  mov     esi, eax
0x18002d99e  test    eax, eax
0x18002d9a0  jz      short loc_18002D9B9
0x18002d9a2  mov     rdx, [rbx]
0x18002d9a5  mov     rax, [rdx+0A0h]
0x18002d9ac  mov     edx, 1
0x18002d9b1  mov     rcx, rbx
0x18002d9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9b9  mov     eax, esi
0x18002d9bb  add     rsp, 30h
0x18002d9bf  pop     rdi
0x18002d9c0  pop     rsi
0x18002d9c1  pop     rbx
0x18002d9c2  retn
```
