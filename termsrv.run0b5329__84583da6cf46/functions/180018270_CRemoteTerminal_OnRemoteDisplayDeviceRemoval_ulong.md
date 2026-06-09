# CRemoteTerminal::OnRemoteDisplayDeviceRemoval(ulong)

- ea: `0x180018270`
- end: `0x18001848c`
- name: `?OnRemoteDisplayDeviceRemoval@CRemoteTerminal@@UEAAJK@Z`
- size: `540`
- prototype: `__int64 __fastcall(CRemoteTerminal *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180042090`

## callees

- `0x180002674`
- `0x180018270`
- `0x1800321f0`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800183ba`
- `ntdll!EtwEventWriteTransfer` at `0x1800183ba`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800182c0`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800182c0`
- `ntdll!RtlReleaseResource` at `0x1800182f6`
- `ntdll!RtlReleaseResource` at `0x1800182f6`

## string_xrefs

- `0x180018329`: `Connection is already terminated`
- `0x180018402`: `ptrTempConnection->OnRemoteDisplayDeviceRemoval`

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
    if ( v7 < 0 && (unsigned int)dword_180128170 > 3 )
    {
      LODWORD(v12) = a2;
      v15 = "OnRemoteDisplayDeviceRemoval";
      v11 = v7;
      v16 = "ptrTempConnection->OnRemoteDisplayDeviceRemoval";
      v13 = (__int64)"Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_180128170,
        (unsigned int)&unk_180107EA0,
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
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v11 = a2;
      v25 = &v11;
      v26 = 4;
      v23 = "Connection is already terminated";
      v24 = 33;
      v13 = 0x20B000000LL;
      v14 = 0;
      v17 = (char *)off_180128178;
      v18 = *(unsigned __int16 *)off_180128178;
      v19 = 2;
      v20 = &dword_180107EFC;
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
0x180018270  mov     [rsp-8+arg_10], rbx
0x180018275  push    rbp
0x180018276  push    rsi
0x180018277  push    rdi
0x180018278  push    r14
0x18001827a  push    r15
0x18001827c  lea     rbp, [rsp-37h]
0x180018281  sub     rsp, 0D0h
0x180018288  mov     rax, cs:__security_cookie
0x18001828f  xor     rax, rsp
0x180018292  mov     [rbp+57h+var_30], rax
0x180018296  mov     r14d, edx
0x180018299  mov     rsi, rcx
0x18001829c  xor     r15d, r15d
0x18001829f  mov     [rbp+57h+var_98], r15
0x1800182a3  lea     rdi, [rcx+13F8h]
0x1800182aa  mov     [rbp+57h+var_90], rdi
0x1800182ae  mov     dword ptr [rbp+57h+var_88], 1
0x1800182b5  cmp     [rdi+60h], r15d
0x1800182b9  jz      short loc_1800182C7
0x1800182bb  mov     dl, 1; Wait
0x1800182bd  mov     rcx, rdi; Resource
0x1800182c0  call    cs:__imp_RtlAcquireResourceExclusive
0x1800182c6  nop
0x1800182c7  mov     rbx, [rsi+640h]
0x1800182ce  mov     [rbp+57h+var_98], rbx
0x1800182d2  test    rbx, rbx
0x1800182d5  jz      short loc_1800182E6
0x1800182d7  mov     rax, [rbx]
0x1800182da  mov     rcx, rbx
0x1800182dd  mov     rax, [rax+8]
0x1800182e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e6  mov     [rsi+694h], r15d
0x1800182ed  cmp     dword ptr [rdi+60h], 0
0x1800182f1  jz      short loc_1800182FD
0x1800182f3  mov     rcx, rdi; Resource
0x1800182f6  call    cs:__imp_RtlReleaseResource
0x1800182fc  nop
0x1800182fd  test    rbx, rbx
0x180018300  jnz     loc_1800183CA
0x180018306  mov     eax, cs:dword_180128170
0x18001830c  cmp     eax, 2
0x18001830f  jbe     loc_1800183C0
0x180018315  mov     [rbp+57h+var_A0], r14d
0x180018319  lea     rax, [rbp+57h+var_A0]
0x18001831d  mov     [rbp+57h+var_40], rax
0x180018321  mov     [rbp+57h+var_38], 4
0x180018329  lea     rax, aConnectionIsAl; "Connection is already terminated"
0x180018330  mov     [rbp+57h+var_50], rax
0x180018334  mov     [rbp+57h+var_48], 21h ; '!'
0x18001833c  mov     dword ptr [rbp+57h+var_90], 0B000000h
0x180018343  movzx   eax, cs:word_180107EF2
0x18001834a  mov     dword ptr [rbp+57h+var_90+4], eax
0x18001834d  mov     [rbp+57h+var_88], r15
0x180018351  mov     rax, cs:off_180128178
0x180018358  mov     [rbp+57h+var_70], rax
0x18001835c  movzx   eax, word ptr [rax]
0x18001835f  mov     [rbp+57h+var_68], eax
0x180018362  mov     [rbp+57h+var_64], 2
0x180018369  lea     rax, dword_180107EFC
0x180018370  mov     [rbp+57h+var_60], rax
0x180018374  mov     [rbp+57h+var_58], 2Bh ; '+'
0x18001837b  mov     [rbp+57h+var_54], 1
0x180018382  lea     rax, _TraceLoggingMetadataEnd
0x180018389  lea     rcx, _TraceLoggingMetadata
0x180018390  sub     eax, ecx
0x180018392  mov     dword ptr [rbp+57h+var_98], eax
0x180018395  mov     eax, dword ptr [rbp+57h+var_98]
0x180018398  lea     rax, [rbp+57h+var_70]
0x18001839c  mov     [rsp+0F0h+var_C8], rax
0x1800183a1  mov     dword ptr [rsp+0F0h+var_D0], 4
0x1800183a9  xor     r9d, r9d
0x1800183ac  xor     r8d, r8d
0x1800183af  lea     rdx, [rbp+57h+var_90]
0x1800183b3  mov     rcx, cs:RegHandle
0x1800183ba  call    cs:__imp_EtwEventWriteTransfer
0x1800183c0  mov     edi, 8000FFFFh
0x1800183c5  jmp     loc_180018452
0x1800183ca  mov     rax, [rbx]
0x1800183cd  mov     edx, r14d
0x1800183d0  mov     rcx, rbx
0x1800183d3  mov     rax, [rax+310h]
0x1800183da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183df  mov     edi, eax
0x1800183e1  test    eax, eax
0x1800183e3  jns     short loc_180018452
0x1800183e5  mov     ecx, cs:dword_180128170
0x1800183eb  cmp     ecx, 3
0x1800183ee  jbe     short loc_180018452
0x1800183f0  mov     dword ptr [rbp+57h+var_98], r14d
0x1800183f4  lea     rax, aOnremotedispla; "OnRemoteDisplayDeviceRemoval"
0x1800183fb  mov     [rbp+57h+var_80], rax
0x1800183ff  mov     [rbp+57h+var_A0], edi
0x180018402  lea     rax, aPtrtempconnect_0; "ptrTempConnection->OnRemoteDisplayDevic"...
0x180018409  mov     [rbp+57h+var_78], rax
0x18001840d  lea     rax, aWarningHresult; "Warning HResult failed"
0x180018414  mov     [rbp+57h+var_90], rax
0x180018418  lea     rax, [rbp+57h+var_98]
0x18001841c  mov     [rsp+0F0h+var_B0], rax
0x180018421  lea     rax, [rbp+57h+var_80]
0x180018425  mov     [rsp+0F0h+var_B8], rax
0x18001842a  lea     rax, [rbp+57h+var_A0]
0x18001842e  mov     [rsp+0F0h+var_C0], rax
0x180018433  lea     rax, [rbp+57h+var_78]
0x180018437  mov     [rsp+0F0h+var_C8], rax
0x18001843c  lea     rax, [rbp+57h+var_90]
0x180018440  mov     [rsp+0F0h+var_D0], rax
0x180018445  lea     rdx, unk_180107EA0
0x18001844c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180018451  nop
0x180018452  test    rbx, rbx
0x180018455  jz      short loc_180018467
0x180018457  mov     rax, [rbx]
0x18001845a  mov     rcx, rbx
0x18001845d  mov     rax, [rax+10h]
0x180018461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018466  nop
0x180018467  mov     eax, edi
0x180018469  mov     rcx, [rbp+57h+var_30]
0x18001846d  xor     rcx, rsp; StackCookie
0x180018470  call    __security_check_cookie
0x180018475  mov     rbx, [rsp+0F0h+arg_10]
0x18001847d  add     rsp, 0D0h
0x180018484  pop     r15
0x180018486  pop     r14
0x180018488  pop     rdi
0x180018489  pop     rsi
0x18001848a  pop     rbp
0x18001848b  retn
```
