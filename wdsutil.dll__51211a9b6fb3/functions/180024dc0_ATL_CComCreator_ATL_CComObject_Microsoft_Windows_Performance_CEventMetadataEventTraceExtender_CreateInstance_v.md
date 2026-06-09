# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180024dc0`
- end: `0x180024ea0`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x180023b40`
- `0x180024dc0`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *)operator new(0x180u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x180024dc0  mov     rax, rsp
0x180024dc3  mov     [rax+18h], r8
0x180024dc7  mov     [rax+10h], rdx
0x180024dcb  mov     [rax+8], rcx
0x180024dcf  push    rbx
0x180024dd0  push    rsi
0x180024dd1  push    rdi
0x180024dd2  sub     rsp, 30h
0x180024dd6  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180024dde  mov     rdi, r8
0x180024de1  test    r8, r8
0x180024de4  jnz     short loc_180024DF0
0x180024de6  mov     eax, 80004003h
0x180024deb  jmp     loc_180024E97
0x180024df0  mov     qword ptr [r8], 0
0x180024df7  mov     esi, 8007000Eh
0x180024dfc  mov     [rsp+48h+arg_8], esi
0x180024e00  mov     [rsp+48h+arg_0], 0
0x180024e09  mov     ecx, 180h; Size
0x180024e0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024e13  mov     rbx, rax
0x180024e16  mov     [rsp+48h+arg_18], rax
0x180024e1b  test    rbx, rbx
0x180024e1e  jz      short loc_180024E46
0x180024e20  mov     rcx, rax; this
0x180024e23  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x180024e28  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x180024e2f  mov     [rbx], rax
0x180024e32  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180024e39  mov     rax, [rcx]
0x180024e3c  mov     rax, [rax+8]
0x180024e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e45  nop
0x180024e46  mov     [rsp+48h+arg_0], rbx
0x180024e4b  jmp     short loc_180024E5B
0x180024e4d  mov     rdi, [rsp+48h+arg_10]
0x180024e52  mov     esi, [rsp+48h+arg_8]
0x180024e56  mov     rbx, [rsp+48h+arg_0]
0x180024e5b  test    rbx, rbx
0x180024e5e  jz      short loc_180024E95
0x180024e60  mov     rax, [rbx]
0x180024e63  mov     r8, rdi
0x180024e66  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180024e6d  mov     rcx, rbx
0x180024e70  mov     rax, [rax]
0x180024e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e78  mov     esi, eax
0x180024e7a  test    eax, eax
0x180024e7c  jz      short loc_180024E95
0x180024e7e  mov     rdx, [rbx]
0x180024e81  mov     rax, [rdx+88h]
0x180024e88  mov     edx, 1
0x180024e8d  mov     rcx, rbx
0x180024e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e95  mov     eax, esi
0x180024e97  add     rsp, 30h
0x180024e9b  pop     rdi
0x180024e9c  pop     rsi
0x180024e9d  pop     rbx
0x180024e9e  retn
```
