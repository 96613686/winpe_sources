# p9fs::Plan9DeviceHost::Plan9DeviceHost(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::com_ptr_t<IUnknown,wil::err_exception_policy> const &,p9fs::IShareList &)

- ea: `0x18002d05c`
- end: `0x18002d244`
- name: `??0Plan9DeviceHost@p9fs@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@AEAVIShareList@1@@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025570`

## callees

- `0x180004120`
- `0x180004c98`
- `0x18001c75c`
- `0x18001d8b4`
- `0x180028718`
- `0x18002d05c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d198`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d17e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d17e`
- `ntdll!RtlGUIDFromString` at `0x18002d164`
- `ntdll!RtlGUIDFromString` at `0x18002d164`
- `vmdevicehost!HdvInitializeDeviceHostForProxy` at `0x18002d1af`
- `vmdevicehost!HdvInitializeDeviceHostForProxy` at `0x18002d1af`
- `vmdevicehost!HdvTeardownDeviceHost` at `0x18002d189`

## string_xrefs

- `0x18002d21d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002d1e4`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`
- `0x18002d232`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall p9fs::Plan9DeviceHost::Plan9DeviceHost(_QWORD *a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rdx
  USHORT v13; // cx
  NTSTATUS v14; // eax
  __int64 v15; // rsi
  DWORD LastError; // ebx
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h]
  _QWORD *v22; // [rsp+40h] [rbp-30h]
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-28h] BYREF
  GUID Guid; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v22 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = a4;
  a1[6] = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a3;
  v19 = 0;
  v8 = (**v7)(v7, &GUID_8434f839_ca86_495d_8a75_7eb36d073ffe, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v8,
      v19);
  v9 = v19;
  v10 = 0;
  v19 = 0;
  v11 = a1[1];
  a1[1] = v9;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v10 = v19;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v12 = (WCHAR *)a2;
  else
    v12 = *(WCHAR **)a2;
  v13 = 2 * *(_WORD *)(a2 + 16);
  if ( v13 != 2LL * *(_QWORD *)(a2 + 16) )
  {
    pExceptionObject = 0;
    v21 = 0;
    gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
    throw (gsl::narrowing_error *)&pExceptionObject;
  }
  GuidString.Length = 2 * *(_WORD *)(a2 + 16);
  GuidString.MaximumLength = v13;
  *(_DWORD *)(&GuidString.MaximumLength + 1) = 0;
  GuidString.Buffer = v12;
  Guid = 0;
  v14 = RtlGUIDFromString(&GuidString, &Guid);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v14,
      v19);
  v15 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    ((void (__fastcall *)(__int64))HdvTeardownDeviceHost)(v15);
    SetLastError(LastError);
  }
  *a1 = 0;
  v17 = HdvInitializeDeviceHostForProxy(&Guid, *a3, a1);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v17,
      v19);
  return a1;
}

```

## disassembly

```asm
0x18002d05c  mov     [rsp-18h+arg_8], rbx
0x18002d061  mov     [rsp-18h+arg_18], rsi
0x18002d066  push    rbp
0x18002d067  push    rdi
0x18002d068  push    r14
0x18002d06a  mov     rbp, rsp
0x18002d06d  sub     rsp, 70h
0x18002d071  mov     rax, cs:__security_cookie
0x18002d078  xor     rax, rsp
0x18002d07b  mov     [rbp+var_8], rax
0x18002d07f  mov     r14, r8
0x18002d082  mov     rbx, rdx
0x18002d085  mov     rdi, rcx
0x18002d088  mov     [rbp+var_30], rcx
0x18002d08c  mov     qword ptr [rcx], 0
0x18002d093  mov     qword ptr [rcx+8], 0
0x18002d09b  mov     qword ptr [rcx+10h], 0
0x18002d0a3  mov     qword ptr [rcx+18h], 0
0x18002d0ab  mov     qword ptr [rcx+20h], 0
0x18002d0b3  mov     [rcx+28h], r9
0x18002d0b7  xor     eax, eax
0x18002d0b9  mov     [rcx+30h], rax
0x18002d0bd  mov     rcx, [r8]
0x18002d0c0  mov     [rbp+var_50], rax
0x18002d0c4  mov     rax, [rcx]
0x18002d0c7  lea     r8, [rbp+var_50]
0x18002d0cb  lea     rdx, _GUID_8434f839_ca86_495d_8a75_7eb36d073ffe
0x18002d0d2  mov     rax, [rax]
0x18002d0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0da  mov     rcx, [rbp+18h]; this
0x18002d0de  test    eax, eax
0x18002d0e0  js      loc_18002D21A
0x18002d0e6  mov     rax, [rbp+var_50]
0x18002d0ea  xor     ecx, ecx
0x18002d0ec  mov     [rbp+var_50], rcx
0x18002d0f0  mov     rdx, [rdi+8]
0x18002d0f4  mov     [rdi+8], rax
0x18002d0f8  test    rdx, rdx
0x18002d0fb  jz      short loc_18002D110
0x18002d0fd  mov     rax, [rdx]
0x18002d100  mov     rcx, rdx
0x18002d103  mov     rax, [rax+10h]
0x18002d107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d10c  mov     rcx, [rbp+var_50]
0x18002d110  test    rcx, rcx
0x18002d113  jz      short loc_18002D122
0x18002d115  mov     rax, [rcx]
0x18002d118  mov     rax, [rax+10h]
0x18002d11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d121  nop
0x18002d122  cmp     qword ptr [rbx+18h], 7
0x18002d127  jbe     short loc_18002D12E
0x18002d129  mov     rdx, [rbx]
0x18002d12c  jmp     short loc_18002D131
0x18002d12e  mov     rdx, rbx
0x18002d131  mov     rax, [rbx+10h]
0x18002d135  add     rax, rax
0x18002d138  movzx   ecx, ax
0x18002d13b  xorps   xmm0, xmm0
0x18002d13e  cmp     rcx, rax
0x18002d141  jnz     loc_18002D1F6
0x18002d147  xor     eax, eax
0x18002d149  mov     [rbp+GuidString.Length], cx
0x18002d14d  mov     [rbp+GuidString.MaximumLength], cx
0x18002d151  mov     dword ptr [rbp+GuidString+4], eax
0x18002d154  mov     [rbp+GuidString.Buffer], rdx
0x18002d158  movups  xmmword ptr [rbp+Guid.Data1], xmm0
0x18002d15c  lea     rdx, [rbp+Guid]; Guid
0x18002d160  lea     rcx, [rbp+GuidString]; GuidString
0x18002d164  call    cs:__imp_RtlGUIDFromString
0x18002d16a  mov     rcx, [rbp+18h]; this
0x18002d16e  test    eax, eax
0x18002d170  js      loc_18002D22F
0x18002d176  mov     rsi, [rdi]
0x18002d179  test    rsi, rsi
0x18002d17c  jz      short loc_18002D19E
0x18002d17e  call    cs:__imp_GetLastError
0x18002d184  mov     ebx, eax
0x18002d186  mov     rcx, rsi
0x18002d189  mov     rax, cs:__imp_HdvTeardownDeviceHost
0x18002d190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d195  nop
0x18002d196  mov     ecx, ebx; dwErrCode
0x18002d198  call    cs:__imp_SetLastError
0x18002d19e  mov     qword ptr [rdi], 0
0x18002d1a5  mov     r8, rdi
0x18002d1a8  mov     rdx, [r14]
0x18002d1ab  lea     rcx, [rbp+Guid]
0x18002d1af  call    cs:__imp_HdvInitializeDeviceHostForProxy
0x18002d1b5  mov     rcx, [rbp+18h]; this
0x18002d1b9  test    eax, eax
0x18002d1bb  js      short loc_18002D1E1
0x18002d1bd  mov     rax, rdi
0x18002d1c0  mov     rcx, [rbp+var_8]
0x18002d1c4  xor     rcx, rsp; StackCookie
0x18002d1c7  call    __security_check_cookie
0x18002d1cc  lea     r11, [rsp+70h+var_s0]
0x18002d1d1  mov     rbx, [r11+28h]
0x18002d1d5  mov     rsi, [r11+38h]
0x18002d1d9  mov     rsp, r11
0x18002d1dc  pop     r14
0x18002d1de  pop     rdi
0x18002d1df  pop     rbp
0x18002d1e0  retn
0x18002d1e1  mov     r9d, eax; char *
0x18002d1e4  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002d1eb  mov     edx, 256h; void *
0x18002d1f0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d1f6  xor     eax, eax
0x18002d1f8  movups  [rbp+pExceptionObject], xmm0
0x18002d1fc  mov     [rbp+var_38], rax
0x18002d200  lea     rcx, [rbp+pExceptionObject]; this
0x18002d204  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002d209  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002d210  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002d214  call    _CxxThrowException_0
0x18002d21a  mov     r9d, eax; char *
0x18002d21d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002d224  mov     edx, 1CBEh; void *
0x18002d229  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d22f  mov     r9d, eax; char *
0x18002d232  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002d239  mov     edx, 255h; void *
0x18002d23e  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
