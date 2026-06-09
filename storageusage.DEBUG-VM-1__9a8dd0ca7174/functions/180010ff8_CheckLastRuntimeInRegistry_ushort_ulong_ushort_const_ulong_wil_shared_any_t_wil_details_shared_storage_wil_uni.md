# CheckLastRuntimeInRegistry(ushort *,ulong,ushort const *,ulong,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &,__int64 &)

- ea: `0x180010ff8`
- end: `0x1800111b2`
- name: `?CheckLastRuntimeInRegistry@@YAJPEAGKPEBGKAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEA_J@Z`
- size: `442`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSubKey@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010890`

## callees

- `0x18000f9e8`
- `0x180010810`
- `0x180010ff8`
- `0x1800152d4`
- `0x18001f584`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800110cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800110cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011141`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011141`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001118e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001118e`

## pseudocode

```c
__int64 __fastcall CheckLastRuntimeInRegistry(
        LPCWSTR lpSubKey,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        _QWORD *a5,
        _QWORD *a6)
{
  _QWORD *v9; // rdi
  volatile signed __int32 *v10; // rbx
  HKEY *phkResult; // rax
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  HKEY v15; // rcx
  int v16; // eax
  int dwOptions; // [rsp+20h] [rbp-49h]
  DWORD cbData; // [rsp+50h] [rbp-19h] BYREF
  DWORD Type; // [rsp+54h] [rbp-15h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-11h] BYREF
  FILETIME FileTime2; // [rsp+60h] [rbp-9h] BYREF
  FILETIME FileTime1[2]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+4Fh]
  DWORD dwDisposition; // [rsp+C8h] [rbp+5Fh] BYREF

  dwDisposition = 0;
  *(_QWORD *)Data = 0;
  cbData = 8;
  Type = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  v9 = a5;
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::operator=(
    a5,
    FileTime1);
  v10 = (volatile signed __int32 *)FileTime1[1];
  if ( FileTime1[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&FileTime1[1] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  phkResult = (HKEY *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v9);
  v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20007u, 0, phkResult, &dwDisposition);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( (v13 & 0x80000000) == 0 )
  {
    if ( dwDisposition == 1 )
      return 0;
    if ( dwDisposition == 2 )
    {
      v15 = *v9 ? *(HKEY *)*v9 : 0LL;
      v16 = RegQueryValueExW(v15, a3, 0, &Type, Data, &cbData);
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 == -2147024894 )
        return 0;
    }
    FileTime2 = 0;
    FileTime1[0] = *(FILETIME *)Data;
    CreateTimeThreshold(a4, &FileTime2);
    *a6 = *(_QWORD *)FileTime1 - *(_QWORD *)&FileTime2;
    if ( CompareFileTime(FileTime1, &FileTime2) == -1 )
      return 0;
    else
      return 2147943623LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)v13,
      dwOptions);
    return v13;
  }
}

```

## disassembly

```asm
0x180010ff8  mov     [rsp-8+dwDisposition], edx
0x180010ffc  push    rbp
0x180010ffd  push    rbx
0x180010ffe  push    rsi
0x180010fff  push    rdi
0x180011000  push    r14
0x180011002  push    r15
0x180011004  lea     rbp, [rsp-1Fh]
0x180011009  sub     rsp, 88h
0x180011010  mov     r15d, r9d
0x180011013  mov     r14, r8
0x180011016  mov     rsi, rcx
0x180011019  mov     [rbp+47h+dwDisposition], 0
0x180011020  mov     qword ptr [rbp+47h+Data], 0
0x180011028  mov     [rbp+47h+cbData], 8
0x18001102f  mov     [rbp+47h+Type], 0
0x180011036  xorps   xmm0, xmm0
0x180011039  movdqu  xmmword ptr [rbp+47h+FileTime1.dwLowDateTime], xmm0
0x18001103e  lea     rdx, [rbp+47h+FileTime1]
0x180011042  mov     rdi, [rbp+47h+arg_20]
0x180011046  mov     rcx, rdi
0x180011049  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>> &&)
0x18001104e  mov     rbx, qword ptr [rbp+47h+FileTime1.dwLowDateTime+8]
0x180011052  test    rbx, rbx
0x180011055  jz      short loc_18001108E
0x180011057  or      eax, 0FFFFFFFFh
0x18001105a  lock xadd [rbx+8], eax
0x18001105f  cmp     eax, 1
0x180011062  jnz     short loc_18001108E
0x180011064  mov     rax, [rbx]
0x180011067  mov     rcx, rbx
0x18001106a  mov     rax, [rax]
0x18001106d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011072  or      eax, 0FFFFFFFFh
0x180011075  lock xadd [rbx+0Ch], eax
0x18001107a  cmp     eax, 1
0x18001107d  jnz     short loc_18001108E
0x18001107f  mov     rax, [rbx]
0x180011082  mov     rcx, rbx
0x180011085  mov     rax, [rax+8]
0x180011089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108e  mov     rcx, rdi
0x180011091  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x180011096  lea     rcx, [rbp+47h+dwDisposition]
0x18001109a  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x18001109f  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800110a4  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800110ad  mov     [rsp+0B0h+samDesired], 20007h; samDesired
0x1800110b5  mov     [rsp+0B0h+dwOptions], 0; int
0x1800110bd  xor     r9d, r9d; lpClass
0x1800110c0  xor     r8d, r8d; Reserved
0x1800110c3  mov     rdx, rsi; lpSubKey
0x1800110c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800110cd  call    cs:__imp_RegCreateKeyExW
0x1800110d3  mov     ebx, eax
0x1800110d5  mov     esi, 80070000h
0x1800110da  test    eax, eax
0x1800110dc  jle     short loc_1800110E3
0x1800110de  movzx   ebx, ax
0x1800110e1  or      ebx, esi
0x1800110e3  test    ebx, ebx
0x1800110e5  jns     short loc_180011106
0x1800110e7  mov     rcx, [rbp+4Fh]; this
0x1800110eb  mov     r9d, ebx; char *
0x1800110ee  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800110f5  mov     edx, 444h; void *
0x1800110fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110ff  mov     eax, ebx
0x180011101  jmp     loc_1800111A2
0x180011106  cmp     [rbp+47h+dwDisposition], 1
0x18001110a  jz      loc_1800111A0
0x180011110  cmp     [rbp+47h+dwDisposition], 2
0x180011114  jnz     short loc_180011157
0x180011116  mov     rax, [rdi]
0x180011119  test    rax, rax
0x18001111c  jz      short loc_180011123
0x18001111e  mov     rcx, [rax]
0x180011121  jmp     short loc_180011125
0x180011123  xor     ecx, ecx; hKey
0x180011125  lea     rax, [rbp+47h+cbData]
0x180011129  mov     qword ptr [rsp+0B0h+samDesired], rax; lpcbData
0x18001112e  lea     rax, [rbp+47h+Data]
0x180011132  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x180011137  lea     r9, [rbp+47h+Type]; lpType
0x18001113b  xor     r8d, r8d; lpReserved
0x18001113e  mov     rdx, r14; lpValueName
0x180011141  call    cs:__imp_RegQueryValueExW
0x180011147  test    eax, eax
0x180011149  jle     short loc_180011150
0x18001114b  movzx   eax, ax
0x18001114e  or      eax, esi
0x180011150  cmp     eax, 80070002h
0x180011155  jz      short loc_1800111A0
0x180011157  mov     ecx, dword ptr [rbp+47h+Data]
0x18001115a  mov     eax, dword ptr [rbp+47h+Data+4]
0x18001115d  mov     qword ptr [rbp+47h+FileTime2.dwLowDateTime], 0
0x180011165  mov     [rbp+47h+FileTime1.dwHighDateTime], eax
0x180011168  mov     [rbp+47h+FileTime1.dwLowDateTime], ecx
0x18001116b  lea     rdx, [rbp+47h+FileTime2]; struct _FILETIME *
0x18001116f  mov     ecx, r15d; unsigned int
0x180011172  call    ?CreateTimeThreshold@@YAXKPEAU_FILETIME@@@Z; CreateTimeThreshold(ulong,_FILETIME *)
0x180011177  mov     rcx, qword ptr [rbp+47h+FileTime1.dwLowDateTime]
0x18001117b  sub     rcx, qword ptr [rbp+47h+FileTime2.dwLowDateTime]
0x18001117f  mov     rax, [rbp+47h+arg_28]
0x180011183  mov     [rax], rcx
0x180011186  lea     rdx, [rbp+47h+FileTime2]; lpFileTime2
0x18001118a  lea     rcx, [rbp+47h+FileTime1]; lpFileTime1
0x18001118e  call    cs:__imp_CompareFileTime
0x180011194  cmp     eax, 0FFFFFFFFh
0x180011197  jz      short loc_1800111A0
0x180011199  mov     eax, 800704C7h
0x18001119e  jmp     short loc_1800111A2
0x1800111a0  xor     eax, eax
0x1800111a2  add     rsp, 88h
0x1800111a9  pop     r15
0x1800111ab  pop     r14
0x1800111ad  pop     rdi
0x1800111ae  pop     rsi
0x1800111af  pop     rbx
0x1800111b0  pop     rbp
0x1800111b1  retn
```
