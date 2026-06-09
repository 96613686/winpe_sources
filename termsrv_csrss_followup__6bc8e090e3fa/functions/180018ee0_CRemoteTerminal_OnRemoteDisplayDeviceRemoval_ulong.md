# CRemoteTerminal::OnRemoteDisplayDeviceRemoval(ulong)

- ea: `0x180018ee0`
- end: `0x18001910f`
- name: `?OnRemoteDisplayDeviceRemoval@CRemoteTerminal@@UEAAJK@Z`
- size: `559`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180044300`

## callees

- `0x1800026a0`
- `0x180018ee0`
- `0x180033f60`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180019036`
- `ntdll!EtwEventWriteTransfer` at `0x180019036`
- `ntdll!RtlAcquireResourceExclusive` at `0x180018f30`
- `ntdll!RtlAcquireResourceExclusive` at `0x180018f30`
- `ntdll!RtlReleaseResource` at `0x180018f6c`
- `ntdll!RtlReleaseResource` at `0x180018f6c`

## string_xrefs

- `0x180018fa5`: `Connection is already terminated`
- `0x180019084`: `ptrTempConnection->OnRemoteDisplayDeviceRemoval`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRemoteTerminal::OnRemoteDisplayDeviceRemoval(CRemoteTerminal *this, unsigned int a2)
{
  struct _RTL_RESOURCE *v4; // rdi
  __int64 v5; // rbx
  unsigned int v6; // edi
  int v7; // eax
  int v8; // r8d
  int v9; // r9d
  int v11; // [rsp+50h] [rbp-49h] BYREF
  __int64 v12; // [rsp+58h] [rbp-41h] BYREF
  __int64 v13; // [rsp+60h] [rbp-39h] BYREF
  __int64 v14; // [rsp+68h] [rbp-31h]
  const char *v15; // [rsp+70h] [rbp-29h] BYREF
  const char *v16; // [rsp+78h] [rbp-21h] BYREF
  char *v17; // [rsp+80h] [rbp-19h] BYREF
  int v18; // [rsp+88h] [rbp-11h]
  int v19; // [rsp+8Ch] [rbp-Dh]
  int *v20; // [rsp+90h] [rbp-9h]
  int v21; // [rsp+98h] [rbp-1h]
  int v22; // [rsp+9Ch] [rbp+3h]
  const char *v23; // [rsp+A0h] [rbp+7h]
  __int64 v24; // [rsp+A8h] [rbp+Fh]
  int *v25; // [rsp+B0h] [rbp+17h]
  __int64 v26; // [rsp+B8h] [rbp+1Fh]

  v12 = 0;
  v4 = (struct _RTL_RESOURCE *)((char *)this + 5112);
  v13 = (__int64)this + 5112;
  LODWORD(v14) = 1;
  if ( *((_DWORD *)this + 1302) )
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 5112), 1u);
  v5 = *((_QWORD *)this + 200);
  v12 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  *((_DWORD *)this + 421) = 0;
  if ( LODWORD(v4[1].Lock.DebugInfo) )
    RtlReleaseResource(v4);
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 784LL))(v5, a2);
    v6 = v7;
    if ( v7 < 0 && (unsigned int)dword_18012E170 > 3 )
    {
      LODWORD(v12) = a2;
      v15 = "OnRemoteDisplayDeviceRemoval";
      v11 = v7;
      v16 = "ptrTempConnection->OnRemoteDisplayDeviceRemoval";
      v13 = (__int64)"Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_18012E170,
        (unsigned int)&unk_18010DF20,
        v8,
        v9,
        (__int64)&v13,
        (__int64)&v16,
        (__int64)&v11,
        (__int64)&v15,
        (__int64)&v12);
    }
  }
  else
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v11 = a2;
      v25 = &v11;
      v26 = 4;
      v23 = "Connection is already terminated";
      v24 = 33;
      v13 = 0x20B000000LL;
      v14 = 0;
      v17 = (char *)off_18012E178;
      v18 = *(unsigned __int16 *)off_18012E178;
      v19 = 2;
      v20 = &dword_18010DF7C;
      v21 = 43;
      v22 = 1;
      LODWORD(v12) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v13, 0, 0, 4, &v17);
    }
    v6 = -2147418113;
  }
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x180018ee0  mov     [rsp-8+arg_10], rbx
0x180018ee5  push    rbp
0x180018ee6  push    rsi
0x180018ee7  push    rdi
0x180018ee8  push    r14
0x180018eea  push    r15
0x180018eec  lea     rbp, [rsp-37h]
0x180018ef1  sub     rsp, 0D0h
0x180018ef8  mov     rax, cs:__security_cookie
0x180018eff  xor     rax, rsp
0x180018f02  mov     [rbp+57h+var_30], rax
0x180018f06  mov     r14d, edx
0x180018f09  mov     rsi, rcx
0x180018f0c  xor     r15d, r15d
0x180018f0f  mov     [rbp+57h+var_98], r15
0x180018f13  lea     rdi, [rcx+13F8h]
0x180018f1a  mov     [rbp+57h+var_90], rdi
0x180018f1e  mov     dword ptr [rbp+57h+var_88], 1
0x180018f25  cmp     [rdi+60h], r15d
0x180018f29  jz      short loc_180018F3D
0x180018f2b  mov     dl, 1; Wait
0x180018f2d  mov     rcx, rdi; Resource
0x180018f30  call    cs:__imp_RtlAcquireResourceExclusive
0x180018f37  nop     dword ptr [rax+rax+00h]
0x180018f3c  nop
0x180018f3d  mov     rbx, [rsi+640h]
0x180018f44  mov     [rbp+57h+var_98], rbx
0x180018f48  test    rbx, rbx
0x180018f4b  jz      short loc_180018F5C
0x180018f4d  mov     rax, [rbx]
0x180018f50  mov     rcx, rbx
0x180018f53  mov     rax, [rax+8]
0x180018f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f5c  mov     [rsi+694h], r15d
0x180018f63  cmp     dword ptr [rdi+60h], 0
0x180018f67  jz      short loc_180018F79
0x180018f69  mov     rcx, rdi; Resource
0x180018f6c  call    cs:__imp_RtlReleaseResource
0x180018f73  nop     dword ptr [rax+rax+00h]
0x180018f78  nop
0x180018f79  test    rbx, rbx
0x180018f7c  jnz     loc_18001904C
0x180018f82  mov     eax, cs:dword_18012E170
0x180018f88  cmp     eax, 2
0x180018f8b  jbe     loc_180019042
0x180018f91  mov     [rbp+57h+var_A0], r14d
0x180018f95  lea     rax, [rbp+57h+var_A0]
0x180018f99  mov     [rbp+57h+var_40], rax
0x180018f9d  mov     [rbp+57h+var_38], 4
0x180018fa5  lea     rax, aConnectionIsAl; "Connection is already terminated"
0x180018fac  mov     [rbp+57h+var_50], rax
0x180018fb0  mov     [rbp+57h+var_48], 21h ; '!'
0x180018fb8  mov     dword ptr [rbp+57h+var_90], 0B000000h
0x180018fbf  movzx   eax, cs:word_18010DF72
0x180018fc6  mov     dword ptr [rbp+57h+var_90+4], eax
0x180018fc9  mov     [rbp+57h+var_88], r15
0x180018fcd  mov     rax, cs:off_18012E178
0x180018fd4  mov     [rbp+57h+var_70], rax
0x180018fd8  movzx   eax, word ptr [rax]
0x180018fdb  mov     [rbp+57h+var_68], eax
0x180018fde  mov     [rbp+57h+var_64], 2
0x180018fe5  lea     rax, dword_18010DF7C
0x180018fec  mov     [rbp+57h+var_60], rax
0x180018ff0  mov     [rbp+57h+var_58], 2Bh ; '+'
0x180018ff7  mov     [rbp+57h+var_54], 1
0x180018ffe  lea     rax, _TraceLoggingMetadataEnd
0x180019005  lea     rcx, _TraceLoggingMetadata
0x18001900c  sub     eax, ecx
0x18001900e  mov     dword ptr [rbp+57h+var_98], eax
0x180019011  mov     eax, dword ptr [rbp+57h+var_98]
0x180019014  lea     rax, [rbp+57h+var_70]
0x180019018  mov     [rsp+0F0h+var_C8], rax
0x18001901d  mov     dword ptr [rsp+0F0h+var_D0], 4
0x180019025  xor     r9d, r9d
0x180019028  xor     r8d, r8d
0x18001902b  lea     rdx, [rbp+57h+var_90]
0x18001902f  mov     rcx, cs:RegHandle
0x180019036  call    cs:__imp_EtwEventWriteTransfer
0x18001903d  nop     dword ptr [rax+rax+00h]
0x180019042  mov     edi, 8000FFFFh
0x180019047  jmp     loc_1800190D4
0x18001904c  mov     rax, [rbx]
0x18001904f  mov     edx, r14d
0x180019052  mov     rcx, rbx
0x180019055  mov     rax, [rax+310h]
0x18001905c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019061  mov     edi, eax
0x180019063  test    eax, eax
0x180019065  jns     short loc_1800190D4
0x180019067  mov     ecx, cs:dword_18012E170
0x18001906d  cmp     ecx, 3
0x180019070  jbe     short loc_1800190D4
0x180019072  mov     dword ptr [rbp+57h+var_98], r14d
0x180019076  lea     rax, aOnremotedispla; "OnRemoteDisplayDeviceRemoval"
0x18001907d  mov     [rbp+57h+var_80], rax
0x180019081  mov     [rbp+57h+var_A0], edi
0x180019084  lea     rax, aPtrtempconnect_0; "ptrTempConnection->OnRemoteDisplayDevic"...
0x18001908b  mov     [rbp+57h+var_78], rax
0x18001908f  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019096  mov     [rbp+57h+var_90], rax
0x18001909a  lea     rax, [rbp+57h+var_98]
0x18001909e  mov     [rsp+0F0h+var_B0], rax
0x1800190a3  lea     rax, [rbp+57h+var_80]
0x1800190a7  mov     [rsp+0F0h+var_B8], rax
0x1800190ac  lea     rax, [rbp+57h+var_A0]
0x1800190b0  mov     [rsp+0F0h+var_C0], rax
0x1800190b5  lea     rax, [rbp+57h+var_78]
0x1800190b9  mov     [rsp+0F0h+var_C8], rax
0x1800190be  lea     rax, [rbp+57h+var_90]
0x1800190c2  mov     [rsp+0F0h+var_D0], rax
0x1800190c7  lea     rdx, unk_18010DF20
0x1800190ce  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800190d3  nop
0x1800190d4  test    rbx, rbx
0x1800190d7  jz      short loc_1800190E9
0x1800190d9  mov     rax, [rbx]
0x1800190dc  mov     rcx, rbx
0x1800190df  mov     rax, [rax+10h]
0x1800190e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190e8  nop
0x1800190e9  mov     eax, edi
0x1800190eb  mov     rcx, [rbp+57h+var_30]
0x1800190ef  xor     rcx, rsp; StackCookie
0x1800190f2  call    __security_check_cookie
0x1800190f7  mov     rbx, [rsp+0F0h+arg_10]
0x1800190ff  add     rsp, 0D0h
0x180019106  pop     r15
0x180019108  pop     r14
0x18001910a  pop     rdi
0x18001910b  pop     rsi
0x18001910c  pop     rbp
0x18001910d  retn
```
