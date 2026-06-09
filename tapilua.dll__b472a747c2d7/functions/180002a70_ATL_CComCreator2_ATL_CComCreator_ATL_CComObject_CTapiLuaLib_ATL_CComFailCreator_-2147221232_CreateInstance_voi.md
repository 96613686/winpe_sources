# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTapiLuaLib>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002a70`
- end: `0x180002b35`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCTapiLuaLib@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001040`
- `0x180001494`
- `0x180002a70`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CTapiLuaLib>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _DWORD *v7; // rdi

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 0;
    *v6 = &ATL::CComObject<CTapiLuaLib>::`vftable';
    _InterlockedIncrement(&dword_18000A288);
    v5 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v7 = &ATL::CComObject<CTapiLuaLib>::`vftable';
      v7[2] = 1;
      _InterlockedDecrement(&dword_18000A288);
      operator delete(v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_8], rbx
0x180002a75  mov     [rsp+arg_10], rbp
0x180002a7a  push    rsi
0x180002a7b  push    rdi
0x180002a7c  push    r12
0x180002a7e  sub     rsp, 20h
0x180002a82  mov     rsi, r8
0x180002a85  mov     rbp, rdx
0x180002a88  test    rcx, rcx
0x180002a8b  jnz     short loc_180002B08
0x180002a8d  test    r8, r8
0x180002a90  jz      short loc_180002B0D
0x180002a92  mov     [r8], rcx
0x180002a95  mov     ebx, 8007000Eh
0x180002a9a  mov     ecx, 10h; Size
0x180002a9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002aa4  mov     [rsp+38h+arg_0], rax
0x180002aa9  mov     rdi, rax
0x180002aac  test    rax, rax
0x180002aaf  jz      short loc_180002B20
0x180002ab1  lea     r12, ??_7?$CComObject@VCTapiLuaLib@@@ATL@@6B@; const ATL::CComObject<CTapiLuaLib>::`vftable'
0x180002ab8  mov     dword ptr [rax+8], 0
0x180002abf  mov     [rax], r12
0x180002ac2  lock inc cs:dword_18000A288
0x180002ac9  test    rax, rax
0x180002acc  jz      short loc_180002B20
0x180002ace  mov     rax, [rax]
0x180002ad1  mov     r8, rsi
0x180002ad4  mov     rdx, rbp
0x180002ad7  mov     rcx, rdi
0x180002ada  mov     rax, [rax]
0x180002add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae2  mov     ebx, eax
0x180002ae4  test    eax, eax
0x180002ae6  jz      short loc_180002B20
0x180002ae8  mov     [rdi], r12
0x180002aeb  mov     edx, 10h; unsigned __int64
0x180002af0  mov     dword ptr [rdi+8], 1
0x180002af7  mov     rcx, rdi; void *
0x180002afa  lock dec cs:dword_18000A288
0x180002b01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002b06  jmp     short loc_180002B20
0x180002b08  test    rsi, rsi
0x180002b0b  jnz     short loc_180002B14
0x180002b0d  mov     ebx, 80004003h
0x180002b12  jmp     short loc_180002B20
0x180002b14  mov     qword ptr [r8], 0
0x180002b1b  mov     ebx, 80040110h
0x180002b20  mov     rbp, [rsp+38h+arg_10]
0x180002b25  mov     eax, ebx
0x180002b27  mov     rbx, [rsp+38h+arg_8]
0x180002b2c  add     rsp, 20h
0x180002b30  pop     r12
0x180002b32  pop     rdi
0x180002b33  pop     rsi
0x180002b34  retn
```
