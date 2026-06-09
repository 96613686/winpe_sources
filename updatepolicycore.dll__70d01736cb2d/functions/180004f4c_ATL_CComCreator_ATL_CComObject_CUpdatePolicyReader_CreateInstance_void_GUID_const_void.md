# ATL::CComCreator<ATL::CComObject<CUpdatePolicyReader>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004f4c`
- end: `0x180005096`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCUpdatePolicyReader@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004cc0`

## callees

- `0x180004f4c`
- `0x180030734`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000501e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000501e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005028`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CUpdatePolicyReader>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  char *v7; // rax
  char *v8; // rbx
  signed int v9; // edi
  signed int LastError; // eax
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 0;
    *(_OWORD *)(v7 + 24) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *((_QWORD *)v7 + 7) = 0;
    v7[64] = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `IUpdatePolicyReader'};
    *((_QWORD *)v7 + 1) = &ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `ITaskHandler'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v8 + 4);
    v9 = 0;
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 24), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
LABEL_11:
      v8[64] = 1;
    v11 = 0;
    if ( v9 < 0 )
      v11 = v9;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    _InterlockedDecrement((volatile signed __int32 *)v8 + 4);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 88LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004f4c  mov     [rsp+arg_10], r8
0x180004f51  mov     [rsp+arg_8], rdx
0x180004f56  mov     [rsp+arg_0], rcx
0x180004f5b  push    rbx
0x180004f5c  push    rsi
0x180004f5d  push    rdi
0x180004f5e  push    r14
0x180004f60  push    r15
0x180004f62  sub     rsp, 20h
0x180004f66  mov     rsi, r8
0x180004f69  mov     r14, rdx
0x180004f6c  test    r8, r8
0x180004f6f  jnz     short loc_180004F7B
0x180004f71  mov     eax, 80004003h
0x180004f76  jmp     loc_18000508A
0x180004f7b  mov     qword ptr [r8], 0
0x180004f82  mov     edi, 8007000Eh
0x180004f87  mov     dword ptr [rsp+48h+arg_0], edi
0x180004f8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004f92  mov     ecx, 48h ; 'H'; unsigned __int64
0x180004f97  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004f9c  mov     rbx, rax
0x180004f9f  mov     [rsp+48h+arg_18], rax
0x180004fa4  test    rax, rax
0x180004fa7  jz      short loc_180004FEE
0x180004fa9  mov     dword ptr [rax+10h], 0
0x180004fb0  xorps   xmm0, xmm0
0x180004fb3  xor     eax, eax
0x180004fb5  movups  xmmword ptr [rbx+18h], xmm0
0x180004fb9  movups  xmmword ptr [rbx+28h], xmm0
0x180004fbd  mov     [rbx+38h], rax
0x180004fc1  mov     [rbx+40h], al
0x180004fc4  lea     rax, ??_7?$CComObject@VCUpdatePolicyReader@@@ATL@@6BIUpdatePolicyReader@@@; const ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `IUpdatePolicyReader'}
0x180004fcb  mov     [rbx], rax
0x180004fce  lea     rax, ??_7?$CComObject@VCUpdatePolicyReader@@@ATL@@6BITaskHandler@@@; const ATL::CComObject<CUpdatePolicyReader>::`vftable'{for `ITaskHandler'}
0x180004fd5  mov     [rbx+8], rax
0x180004fd9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004fe0  mov     rax, [rcx]
0x180004fe3  mov     rax, [rax+8]
0x180004fe7  call    _guard_dispatch_icall
0x180004fec  jmp     short loc_180004FF0
0x180004fee  xor     ebx, ebx
0x180004ff0  mov     [rsp+48h+arg_18], rbx
0x180004ff5  jmp     short loc_18000500A
0x180004ff7  mov     rsi, [rsp+48h+arg_10]
0x180004ffc  mov     r14, [rsp+48h+arg_8]
0x180005001  mov     edi, dword ptr [rsp+48h+arg_0]
0x180005005  mov     rbx, [rsp+48h+arg_18]
0x18000500a  test    rbx, rbx
0x18000500d  jz      short loc_180005088
0x18000500f  lock inc dword ptr [rbx+10h]
0x180005013  xor     edi, edi
0x180005015  xor     r8d, r8d; Flags
0x180005018  xor     edx, edx; dwSpinCount
0x18000501a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000501e  call    cs:__imp_InitializeCriticalSectionEx
0x180005024  test    eax, eax
0x180005026  jnz     short loc_180005040
0x180005028  call    cs:__imp_GetLastError
0x18000502e  movzx   edi, ax
0x180005031  or      edi, 80070000h
0x180005037  test    eax, eax
0x180005039  cmovle  edi, eax
0x18000503c  test    edi, edi
0x18000503e  js      short loc_180005044
0x180005040  mov     byte ptr [rbx+40h], 1
0x180005044  xor     eax, eax
0x180005046  test    edi, edi
0x180005048  cmovs   eax, edi
0x18000504b  xor     edi, edi
0x18000504d  test    eax, eax
0x18000504f  cmovs   edi, eax
0x180005052  lock dec dword ptr [rbx+10h]
0x180005056  test    edi, edi
0x180005058  jnz     short loc_180005074
0x18000505a  mov     rax, [rbx]
0x18000505d  mov     r8, rsi
0x180005060  mov     rdx, r14
0x180005063  mov     rcx, rbx
0x180005066  mov     rax, [rax]
0x180005069  call    _guard_dispatch_icall
0x18000506e  mov     edi, eax
0x180005070  test    eax, eax
0x180005072  jz      short loc_180005088
0x180005074  mov     r8, [rbx]
0x180005077  mov     edx, 1
0x18000507c  mov     rcx, rbx
0x18000507f  mov     rax, [r8+58h]
0x180005083  call    _guard_dispatch_icall
0x180005088  mov     eax, edi
0x18000508a  add     rsp, 20h
0x18000508e  pop     r15
0x180005090  pop     r14
0x180005092  pop     rdi
0x180005093  pop     rsi
0x180005094  pop     rbx
0x180005095  retn
```
