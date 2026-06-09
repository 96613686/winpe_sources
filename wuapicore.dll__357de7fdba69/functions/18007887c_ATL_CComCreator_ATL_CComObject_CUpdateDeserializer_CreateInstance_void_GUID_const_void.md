# ATL::CComCreator<ATL::CComObject<CUpdateDeserializer>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18007887c`
- end: `0x180078a5e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCUpdateDeserializer@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800776b0`

## callees

- `0x180006ac4`
- `0x18007887c`
- `0x18008d284`
- `0x18009ae75`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007897b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007897b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800789d1`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800789d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078985`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800788ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800788ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788bb`

## string_xrefs

- `0x1800789ea`: `C:\__w\1\s\src\Client\comapi\UpdateDeserializer.cpp`
- `0x1800789fe`: `C:\__w\1\s\src\Client\comapi\UpdateDeserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CUpdateDeserializer>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rdi
  __int64 v10; // rdx
  void *v11; // r8
  signed int LastError; // eax
  int FreeThreadedMarshaler; // ebx
  int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  IUnknown *v17; // rax
  int v18; // [rsp+20h] [rbp-28h]
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 0, 0x60u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x60u);
    *((_DWORD *)v9 + 8) = 0;
    *(_OWORD *)(v9 + 40) = 0;
    *(_OWORD *)(v9 + 56) = 0;
    *((_QWORD *)v9 + 9) = 0;
    v9[80] = 0;
    *((_DWORD *)v9 + 6) = -1;
    *((_QWORD *)v9 + 11) = 0;
    *(_QWORD *)v9 = &ATL::CComObject<CUpdateDeserializer>::`vftable'{for `CSusBaseAllocTag<1970300019>'};
    *((_QWORD *)v9 + 1) = &ATL::CComObject<CUpdateDeserializer>::`vftable'{for `IUpdateDeserializer'};
    *((_QWORD *)v9 + 2) = &ATL::CComObject<CUpdateDeserializer>::`vftable'{for `CUpdateLockdown'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v9 + 8);
    if ( !InitializeCriticalSectionEx((LPCRITICAL_SECTION)v9 + 1, 0, 0) )
    {
      LastError = GetLastError();
      FreeThreadedMarshaler = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        FreeThreadedMarshaler = LastError;
      if ( FreeThreadedMarshaler < 0 )
        goto LABEL_17;
    }
    v9[80] = 1;
    v14 = SecurityCheck(-2147483646, v10, v11);
    FreeThreadedMarshaler = v14;
    if ( v14 >= 0 )
    {
      v17 = (IUnknown *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v17, (LPUNKNOWN *)v9 + 11);
      v16 = (unsigned int)FreeThreadedMarshaler;
      if ( FreeThreadedMarshaler >= 0 )
      {
        FreeThreadedMarshaler = 0;
        goto LABEL_17;
      }
      v15 = 33;
    }
    else
    {
      v15 = 30;
      v16 = (unsigned int)v14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDeserializer.cpp",
      (const char *)v16,
      v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateDeserializer.cpp",
      (const char *)(unsigned int)FreeThreadedMarshaler,
      v19);
LABEL_17:
    v6 = 0;
    if ( FreeThreadedMarshaler < 0 )
      v6 = FreeThreadedMarshaler;
    _InterlockedDecrement((volatile signed __int32 *)v9 + 8);
    if ( v6 || (v6 = (**((__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v9 + 1))((__int64)(v9 + 8), a2, a3)) != 0 )
      (**(void (__fastcall ***)(void *, __int64))v9)(v9, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18007887c  mov     [rsp+arg_10], r8
0x180078881  mov     [rsp+arg_8], rdx
0x180078886  mov     [rsp+arg_0], rcx
0x18007888b  push    rbx
0x18007888c  push    rsi
0x18007888d  push    rdi
0x18007888e  push    r14
0x180078890  push    r15
0x180078892  sub     rsp, 20h
0x180078896  mov     r14, r8
0x180078899  mov     r15, rdx
0x18007889c  test    r8, r8
0x18007889f  jnz     short loc_1800788AB
0x1800788a1  mov     eax, 80004003h
0x1800788a6  jmp     loc_180078A52
0x1800788ab  mov     qword ptr [r8], 0
0x1800788b2  mov     esi, 8007000Eh
0x1800788b7  mov     dword ptr [rsp+48h+arg_0], esi
0x1800788bb  call    cs:__imp_GetProcessHeap
0x1800788c1  mov     ebx, 60h ; '`'
0x1800788c6  mov     r8d, ebx; dwBytes
0x1800788c9  xor     edx, edx; dwFlags
0x1800788cb  mov     rcx, rax; hHeap
0x1800788ce  call    cs:__imp_HeapAlloc
0x1800788d4  mov     rdi, rax
0x1800788d7  mov     [rsp+48h+arg_18], rax
0x1800788dc  test    rax, rax
0x1800788df  jz      short loc_180078949
0x1800788e1  mov     r8d, ebx; Size
0x1800788e4  xor     edx, edx; Val
0x1800788e6  mov     rcx, rax; void *
0x1800788e9  call    memset_0
0x1800788ee  mov     dword ptr [rdi+20h], 0
0x1800788f5  xorps   xmm0, xmm0
0x1800788f8  xor     eax, eax
0x1800788fa  movups  xmmword ptr [rdi+28h], xmm0
0x1800788fe  movups  xmmword ptr [rdi+38h], xmm0
0x180078902  mov     [rdi+48h], rax
0x180078906  mov     [rdi+50h], al
0x180078909  mov     dword ptr [rdi+18h], 0FFFFFFFFh
0x180078910  mov     [rdi+58h], rax
0x180078914  lea     rax, ??_7?$CComObject@VCUpdateDeserializer@@@ATL@@6B?$CSusBaseAllocTag@$0HFHAGEHD@@@@; const ATL::CComObject<CUpdateDeserializer>::`vftable'{for `CSusBaseAllocTag<1970300019>'}
0x18007891b  mov     [rdi], rax
0x18007891e  lea     rax, ??_7?$CComObject@VCUpdateDeserializer@@@ATL@@6BIUpdateDeserializer@@@; const ATL::CComObject<CUpdateDeserializer>::`vftable'{for `IUpdateDeserializer'}
0x180078925  mov     [rdi+8], rax
0x180078929  lea     rax, ??_7?$CComObject@VCUpdateDeserializer@@@ATL@@6BCUpdateLockdown@@@; const ATL::CComObject<CUpdateDeserializer>::`vftable'{for `CUpdateLockdown'}
0x180078930  mov     [rdi+10h], rax
0x180078934  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18007893b  mov     rax, [rcx]
0x18007893e  mov     rax, [rax+8]
0x180078942  call    _guard_dispatch_icall
0x180078947  jmp     short loc_18007894B
0x180078949  xor     edi, edi
0x18007894b  mov     [rsp+48h+arg_18], rdi
0x180078950  jmp     short loc_180078965
0x180078952  mov     r14, [rsp+48h+arg_10]
0x180078957  mov     r15, [rsp+48h+arg_8]
0x18007895c  mov     esi, dword ptr [rsp+48h+arg_0]
0x180078960  mov     rdi, [rsp+48h+arg_18]
0x180078965  test    rdi, rdi
0x180078968  jz      loc_180078A50
0x18007896e  lock inc dword ptr [rdi+20h]
0x180078972  xor     r8d, r8d; Flags
0x180078975  xor     edx, edx; dwSpinCount
0x180078977  lea     rcx, [rdi+28h]; lpCriticalSection
0x18007897b  call    cs:__imp_InitializeCriticalSectionEx
0x180078981  test    eax, eax
0x180078983  jnz     short loc_18007899D
0x180078985  call    cs:__imp_GetLastError
0x18007898b  movzx   ebx, ax
0x18007898e  or      ebx, 80070000h
0x180078994  test    eax, eax
0x180078996  cmovle  ebx, eax
0x180078999  test    ebx, ebx
0x18007899b  js      short loc_180078A13
0x18007899d  mov     byte ptr [rdi+50h], 1
0x1800789a1  mov     ecx, 80000002h; unsigned int
0x1800789a6  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x1800789ab  mov     ebx, eax
0x1800789ad  test    eax, eax
0x1800789af  jns     short loc_1800789BB
0x1800789b1  mov     edx, 1Eh
0x1800789b6  mov     r9d, eax
0x1800789b9  jmp     short loc_1800789E5
0x1800789bb  mov     rax, [rdi]
0x1800789be  mov     rcx, rdi
0x1800789c1  mov     rax, [rax+8]
0x1800789c5  call    _guard_dispatch_icall
0x1800789ca  mov     rcx, rax; punkOuter
0x1800789cd  lea     rdx, [rdi+58h]; ppunkMarshal
0x1800789d1  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800789d7  mov     ebx, eax
0x1800789d9  mov     r9d, eax; char *
0x1800789dc  test    eax, eax
0x1800789de  jns     short loc_180078A11
0x1800789e0  mov     edx, 21h ; '!'; void *
0x1800789e5  mov     rcx, [rsp+48h]; this
0x1800789ea  lea     r8, aCW1SSrcClientC_2; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800789f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800789f6  mov     rcx, [rsp+48h]; this
0x1800789fb  mov     r9d, ebx; char *
0x1800789fe  lea     r8, aCW1SSrcClientC_2; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180078a05  mov     edx, 16h; void *
0x180078a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078a0f  jmp     short loc_180078A13
0x180078a11  xor     ebx, ebx
0x180078a13  xor     esi, esi
0x180078a15  test    ebx, ebx
0x180078a17  cmovs   esi, ebx
0x180078a1a  lock dec dword ptr [rdi+20h]
0x180078a1e  test    esi, esi
0x180078a20  jnz     short loc_180078A3D
0x180078a22  lea     rcx, [rdi+8]
0x180078a26  mov     rax, [rcx]
0x180078a29  mov     r8, r14
0x180078a2c  mov     rdx, r15
0x180078a2f  mov     rax, [rax]
0x180078a32  call    _guard_dispatch_icall
0x180078a37  mov     esi, eax
0x180078a39  test    eax, eax
0x180078a3b  jz      short loc_180078A50
0x180078a3d  mov     r8, [rdi]
0x180078a40  mov     edx, 1
0x180078a45  mov     rcx, rdi
0x180078a48  mov     rax, [r8]
0x180078a4b  call    _guard_dispatch_icall
0x180078a50  mov     eax, esi
0x180078a52  add     rsp, 20h
0x180078a56  pop     r15
0x180078a58  pop     r14
0x180078a5a  pop     rdi
0x180078a5b  pop     rsi
0x180078a5c  pop     rbx
0x180078a5d  retn
```
