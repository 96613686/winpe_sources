# ATL::CComCreator<ATL::CComObject<CUpdatePolicyPublisher>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004e04`
- end: `0x180004f43`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCUpdatePolicyPublisher@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004c80`

## callees

- `0x180004e04`
- `0x180030734`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004ecb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ed5`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CUpdatePolicyPublisher>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed int v9; // edi
  signed int LastError; // eax
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CUpdatePolicyPublisher>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 2);
    v9 = 0;
    if ( InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 4), 0, 0) )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    if ( v9 >= 0 )
LABEL_11:
      *((_BYTE *)v8 + 56) = 1;
    v11 = 0;
    if ( v9 < 0 )
      v11 = v9;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    _InterlockedDecrement(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004e04  mov     [rsp+arg_10], r8
0x180004e09  mov     [rsp+arg_8], rdx
0x180004e0e  mov     [rsp+arg_0], rcx
0x180004e13  push    rbx
0x180004e14  push    rsi
0x180004e15  push    rdi
0x180004e16  push    r14
0x180004e18  push    r15
0x180004e1a  sub     rsp, 20h
0x180004e1e  mov     rsi, r8
0x180004e21  mov     r14, rdx
0x180004e24  test    r8, r8
0x180004e27  jnz     short loc_180004E33
0x180004e29  mov     eax, 80004003h
0x180004e2e  jmp     loc_180004F37
0x180004e33  mov     qword ptr [r8], 0
0x180004e3a  mov     edi, 8007000Eh
0x180004e3f  mov     dword ptr [rsp+48h+arg_0], edi
0x180004e43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004e4a  mov     ecx, 40h ; '@'; unsigned __int64
0x180004e4f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004e54  mov     rbx, rax
0x180004e57  mov     [rsp+48h+arg_18], rax
0x180004e5c  test    rax, rax
0x180004e5f  jz      short loc_180004E9B
0x180004e61  mov     dword ptr [rax+8], 0
0x180004e68  xorps   xmm0, xmm0
0x180004e6b  xor     eax, eax
0x180004e6d  movups  xmmword ptr [rbx+10h], xmm0
0x180004e71  movups  xmmword ptr [rbx+20h], xmm0
0x180004e75  mov     [rbx+30h], rax
0x180004e79  mov     [rbx+38h], al
0x180004e7c  lea     rax, ??_7?$CComObject@VCUpdatePolicyPublisher@@@ATL@@6B@; const ATL::CComObject<CUpdatePolicyPublisher>::`vftable'
0x180004e83  mov     [rbx], rax
0x180004e86  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004e8d  mov     rax, [rcx]
0x180004e90  mov     rax, [rax+8]
0x180004e94  call    _guard_dispatch_icall
0x180004e99  jmp     short loc_180004E9D
0x180004e9b  xor     ebx, ebx
0x180004e9d  mov     [rsp+48h+arg_18], rbx
0x180004ea2  jmp     short loc_180004EB7
0x180004ea4  mov     rsi, [rsp+48h+arg_10]
0x180004ea9  mov     r14, [rsp+48h+arg_8]
0x180004eae  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004eb2  mov     rbx, [rsp+48h+arg_18]
0x180004eb7  test    rbx, rbx
0x180004eba  jz      short loc_180004F35
0x180004ebc  lock inc dword ptr [rbx+8]
0x180004ec0  xor     edi, edi
0x180004ec2  xor     r8d, r8d; Flags
0x180004ec5  xor     edx, edx; dwSpinCount
0x180004ec7  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004ecb  call    cs:__imp_InitializeCriticalSectionEx
0x180004ed1  test    eax, eax
0x180004ed3  jnz     short loc_180004EED
0x180004ed5  call    cs:__imp_GetLastError
0x180004edb  movzx   edi, ax
0x180004ede  or      edi, 80070000h
0x180004ee4  test    eax, eax
0x180004ee6  cmovle  edi, eax
0x180004ee9  test    edi, edi
0x180004eeb  js      short loc_180004EF1
0x180004eed  mov     byte ptr [rbx+38h], 1
0x180004ef1  xor     eax, eax
0x180004ef3  test    edi, edi
0x180004ef5  cmovs   eax, edi
0x180004ef8  xor     edi, edi
0x180004efa  test    eax, eax
0x180004efc  cmovs   edi, eax
0x180004eff  lock dec dword ptr [rbx+8]
0x180004f03  test    edi, edi
0x180004f05  jnz     short loc_180004F21
0x180004f07  mov     rax, [rbx]
0x180004f0a  mov     r8, rsi
0x180004f0d  mov     rdx, r14
0x180004f10  mov     rcx, rbx
0x180004f13  mov     rax, [rax]
0x180004f16  call    _guard_dispatch_icall
0x180004f1b  mov     edi, eax
0x180004f1d  test    eax, eax
0x180004f1f  jz      short loc_180004F35
0x180004f21  mov     r8, [rbx]
0x180004f24  mov     edx, 1
0x180004f29  mov     rcx, rbx
0x180004f2c  mov     rax, [r8+28h]
0x180004f30  call    _guard_dispatch_icall
0x180004f35  mov     eax, edi
0x180004f37  add     rsp, 20h
0x180004f3b  pop     r15
0x180004f3d  pop     r14
0x180004f3f  pop     rdi
0x180004f40  pop     rsi
0x180004f41  pop     rbx
0x180004f42  retn
```
