# DynLib::DynLib(IO::Path const &,bool)

- ea: `0x140083658`
- end: `0x1400837d1`
- name: `??0DynLib@@QEAA@AEBVPath@IO@@_N@Z`
- size: `377`
- prototype: `DynLib *__fastcall(DynLib *this, const WCHAR *, char)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140002a80`
- `0x140032ad0`
- `0x14004cd88`
- `0x14005a4b8`
- `0x14005a5c0`
- `0x140088c2c`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14001c804`
- `0x140060f58`
- `0x14007aaf4`
- `0x140083658`
- `0x140083978`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140083764`
- `KERNEL32!GetLastError` at `0x140083764`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400836a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400836a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
DynLib *__fastcall DynLib::DynLib(DynLib *this, const WCHAR *a2, char a3)
{
  const WCHAR *v5; // rcx
  HMODULE Library; // rax
  HMODULE v7; // rbx
  volatile signed __int32 *v8; // rbx
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r8d
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-38h] BYREF
  char v17; // [rsp+40h] [rbp-28h]
  _DWORD *v18; // [rsp+70h] [rbp+8h]
  char v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = a3;
  *(_QWORD *)this = &DynLib::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v5 = a2;
  else
    v5 = *(const WCHAR **)a2;
  Library = LoadLibraryExW(v5, 0, 2u);
  v7 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v12 = std::array<unsigned short,16>::data(a2);
      v13 = std::wstring::c_str(v12);
      WPP_SF_Sld(*(_QWORD *)(v14 + 16), v14, v15, v13);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v19 = 0;
  pExceptionObject[0] = Library;
  pExceptionObject[1] = &v19;
  v17 = 1;
  v18 = operator new(0x18u);
  *(_OWORD *)v18 = 0;
  v18[2] = 1;
  v18[3] = 1;
  *(_QWORD *)v18 = &std::_Ref_count_resource<HINSTANCE__ *,_lambda_6bfbb92090c379a9aabfb7129ba6d39d_>::`vftable';
  *((_QWORD *)v18 + 2) = v7;
  *((_QWORD *)this + 1) = v7;
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = v18;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return this;
}

```

## disassembly

```asm
0x140083658  mov     rax, rsp
0x14008365b  mov     [rax+10h], rbx
0x14008365f  mov     [rax+20h], rsi
0x140083663  mov     [rax+18h], r8b
0x140083667  mov     [rax+8], rcx
0x14008366b  push    rdi
0x14008366c  sub     rsp, 60h
0x140083670  mov     rsi, rdx
0x140083673  mov     rdi, rcx
0x140083676  lea     rax, ??_7DynLib@@6B@; const DynLib::`vftable'
0x14008367d  mov     [rcx], rax
0x140083680  mov     qword ptr [rcx+8], 0
0x140083688  mov     qword ptr [rcx+10h], 0
0x140083690  cmp     qword ptr [rdx+18h], 7
0x140083695  jbe     short loc_14008369C
0x140083697  mov     rcx, [rdx]
0x14008369a  jmp     short loc_14008369F
0x14008369c  mov     rcx, rsi; lpLibFileName
0x14008369f  xor     edx, edx; hFile
0x1400836a1  lea     r8d, [rdx+2]; dwFlags
0x1400836a5  call    cs:__imp_LoadLibraryExW
0x1400836ab  mov     rbx, rax
0x1400836ae  test    rax, rax
0x1400836b1  jz      loc_140083764
0x1400836b7  mov     [rsp+68h+arg_10], 0
0x1400836bf  mov     [rsp+68h+pExceptionObject], rax
0x1400836c4  lea     rax, [rsp+68h+arg_10]
0x1400836cc  mov     [rsp+68h+var_30], rax
0x1400836d1  mov     [rsp+68h+var_28], 1
0x1400836d6  mov     ecx, 18h; Size
0x1400836db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400836e0  mov     [rsp+68h+arg_0], rax
0x1400836e5  xorps   xmm0, xmm0
0x1400836e8  movups  xmmword ptr [rax], xmm0
0x1400836eb  mov     dword ptr [rax+8], 1
0x1400836f2  mov     dword ptr [rax+0Ch], 1
0x1400836f9  lea     rcx, ??_7?$_Ref_count_resource@PEAUHINSTANCE__@@V_lambda_6bfbb92090c379a9aabfb7129ba6d39d_@@@std@@6B@; const std::_Ref_count_resource<HINSTANCE__ *,_lambda_6bfbb92090c379a9aabfb7129ba6d39d_>::`vftable'
0x140083700  mov     [rax], rcx
0x140083703  mov     [rax+10h], rbx
0x140083707  mov     [rdi+8], rbx
0x14008370b  mov     rbx, [rdi+10h]
0x14008370f  mov     [rdi+10h], rax
0x140083713  test    rbx, rbx
0x140083716  jz      short loc_14008374F
0x140083718  or      esi, 0FFFFFFFFh
0x14008371b  mov     eax, esi
0x14008371d  lock xadd [rbx+8], eax
0x140083722  add     eax, esi
0x140083724  jnz     short loc_14008374F
0x140083726  mov     rax, [rbx]
0x140083729  mov     rcx, rbx
0x14008372c  mov     rax, [rax]
0x14008372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083734  mov     eax, esi
0x140083736  lock xadd [rbx+0Ch], eax
0x14008373b  add     eax, esi
0x14008373d  jnz     short loc_14008374F
0x14008373f  mov     rax, [rbx]
0x140083742  mov     rcx, rbx
0x140083745  mov     rax, [rax+8]
0x140083749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008374e  nop
0x14008374f  mov     rax, rdi
0x140083752  lea     r11, [rsp+68h+var_8]
0x140083757  mov     rbx, [r11+18h]
0x14008375b  mov     rsi, [r11+28h]
0x14008375f  mov     rsp, r11
0x140083762  pop     rdi
0x140083763  retn
0x140083764  call    cs:__imp_GetLastError
0x14008376a  nop
0x14008376b  mov     ebx, eax
0x14008376d  test    eax, eax
0x14008376f  jle     short loc_14008377A
0x140083771  movzx   ebx, ax
0x140083774  or      ebx, 80070000h
0x14008377a  lea     rax, WPP_GLOBAL_Control
0x140083781  mov     rdx, cs:WPP_GLOBAL_Control
0x140083788  cmp     rdx, rax
0x14008378b  jz      short loc_1400837B3
0x14008378d  test    byte ptr [rdx+1Ch], 1
0x140083791  jz      short loc_1400837B3
0x140083793  mov     rcx, rsi
0x140083796  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x14008379b  mov     rcx, rax
0x14008379e  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400837a3  mov     [rsp+68h+var_40], ebx
0x1400837a7  mov     r9, rax
0x1400837aa  mov     rcx, [rdx+10h]
0x1400837ae  call    WPP_SF_Sld
0x1400837b3  mov     edx, ebx; int
0x1400837b5  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400837ba  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400837bf  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400837c6  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400837cb  call    _CxxThrowException_0
```
