# ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002671c`
- end: `0x180026806`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VTpmVCardManagerImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `234`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026620`

## callees

- `0x1800023c0`
- `0x18002671c`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<TpmVCardManagerImpl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v6; // rbx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  _DWORD *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v9 = -2147024882;
    v6 = operator new(0x10u);
    v6[2] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<TpmVCardManagerImpl>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v12 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v9 = -2147024882;
    v6 = v12;
  }
  if ( v6 )
  {
    v7 = v6[2];
    if ( v7 != 0x7FFFFFFF )
    {
      v8 = v7 + 1;
      v6[2] = v8;
      if ( v8 != 0x7FFFFFFF )
        v6[2] = v8 - 1;
    }
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v6)(v6, v4, v3);
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
  }
  return v9;
}

```

## disassembly

```asm
0x18002671c  mov     [rsp+arg_10], r8
0x180026721  mov     [rsp+arg_8], rdx
0x180026726  mov     [rsp+arg_0], rcx
0x18002672b  push    rbx
0x18002672c  push    rsi
0x18002672d  push    rdi
0x18002672e  push    r14
0x180026730  sub     rsp, 28h
0x180026734  mov     rsi, r8
0x180026737  mov     r14, rdx
0x18002673a  test    r8, r8
0x18002673d  jnz     short loc_180026749
0x18002673f  mov     eax, 80004003h
0x180026744  jmp     loc_1800267FC
0x180026749  mov     qword ptr [r8], 0
0x180026750  mov     edi, 8007000Eh
0x180026755  mov     dword ptr [rsp+48h+arg_0], edi
0x180026759  mov     [rsp+48h+arg_18], 0
0x180026762  mov     ecx, 10h; Size
0x180026767  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002676c  mov     rbx, rax
0x18002676f  mov     dword ptr [rax+8], 0
0x180026776  lea     rax, ??_7?$CComObject@VTpmVCardManagerImpl@@@ATL@@6B@; const ATL::CComObject<TpmVCardManagerImpl>::`vftable'
0x18002677d  mov     [rbx], rax
0x180026780  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180026787  mov     rax, [rcx]
0x18002678a  mov     rax, [rax+8]
0x18002678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026793  mov     [rsp+48h+arg_18], rbx
0x180026798  jmp     short loc_1800267AD
0x18002679a  mov     rsi, [rsp+48h+arg_10]
0x18002679f  mov     r14, [rsp+48h+arg_8]
0x1800267a4  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800267a8  mov     rbx, [rsp+48h+arg_18]
0x1800267ad  test    rbx, rbx
0x1800267b0  jz      short loc_1800267FA
0x1800267b2  mov     eax, [rbx+8]
0x1800267b5  mov     ecx, 7FFFFFFFh
0x1800267ba  cmp     eax, ecx
0x1800267bc  jz      short loc_1800267CC
0x1800267be  inc     eax
0x1800267c0  mov     [rbx+8], eax
0x1800267c3  cmp     eax, ecx
0x1800267c5  jz      short loc_1800267CC
0x1800267c7  dec     eax
0x1800267c9  mov     [rbx+8], eax
0x1800267cc  mov     rax, [rbx]
0x1800267cf  mov     r8, rsi
0x1800267d2  mov     rdx, r14
0x1800267d5  mov     rcx, rbx
0x1800267d8  mov     rax, [rax]
0x1800267db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267e0  mov     edi, eax
0x1800267e2  test    eax, eax
0x1800267e4  jz      short loc_1800267FA
0x1800267e6  mov     rdx, [rbx]
0x1800267e9  mov     rax, [rdx+28h]
0x1800267ed  mov     edx, 1
0x1800267f2  mov     rcx, rbx
0x1800267f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267fa  mov     eax, edi
0x1800267fc  add     rsp, 28h
0x180026800  pop     r14
0x180026802  pop     rdi
0x180026803  pop     rsi
0x180026804  pop     rbx
0x180026805  retn
```
