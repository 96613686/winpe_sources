# OSF_CCONNECTION::OSF_CCONNECTION(OSF_CASSOCIATION *,RPC_CONNECTION_TRANSPORT *,uint,CLIENT_AUTH_INFO *,int,int,OSF_CCALL *,long *)

- ea: `0x180052a04`
- end: `0x180052db1`
- name: `??0OSF_CCONNECTION@@QEAA@PEAVOSF_CASSOCIATION@@PEAURPC_CONNECTION_TRANSPORT@@IPEAUCLIENT_AUTH_INFO@@HHPEAVOSF_CCALL@@PEAJ@Z`
- size: `941`
- prototype: `OSF_CCONNECTION *__usercall@<rax>(OSF_CCONNECTION *__hidden this@<rcx>, struct OSF_CASSOCIATION *@<rdx>, struct RPC_CONNECTION_TRANSPORT *@<r8>, unsigned int@<r9d>, struct CLIENT_AUTH_INFO *, int, int, struct OSF_CCALL *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800527e8`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x18002b7c0`
- `0x180049064`
- `0x18004f480`
- `0x180052a04`
- `0x180053770`
- `0x180053bc0`
- `0x180053ca4`
- `0x180053d08`
- `0x1800ab510`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180052a77`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180052a77`
- `ntdll!RtlLeaveCriticalSection` at `0x180052c62`
- `ntdll!RtlLeaveCriticalSection` at `0x180052c62`
- `ntdll!RtlEnterCriticalSection` at `0x180052c39`
- `ntdll!RtlEnterCriticalSection` at `0x180052c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052d3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052d3c`

## pseudocode

```c
OSF_CCONNECTION *__fastcall OSF_CCONNECTION::OSF_CCONNECTION(
        OSF_CCONNECTION *this,
        struct OSF_CASSOCIATION *a2,
        struct RPC_CONNECTION_TRANSPORT *a3,
        int a4,
        struct CLIENT_AUTH_INFO *a5,
        int a6,
        int a7,
        struct OSF_CCALL *a8,
        int *a9)
{
  __int64 v13; // rcx
  char *v14; // rcx
  OSF_CCALL *v15; // rbx
  __int64 (__fastcall *v16)(char *, _QWORD, _QWORD, _QWORD); // rax
  int v17; // ecx
  int v18; // eax
  CSECURITY_CONTEXT *v19; // rax
  unsigned int v20; // r8d
  int v21; // r9d
  CSECURITY_CONTEXT *v22; // rax
  unsigned int v23; // edx
  CSECURITY_CONTEXT *v24; // rcx
  SIZE_T v25; // rcx
  OSF_CCALL *v26; // rax
  OSF_CCONNECTION *result; // rax
  DWORD CurrentThreadId; // edx
  OSF_CCALL *v29; // rax
  signed __int32 v30[8]; // [rsp+0h] [rbp-78h] BYREF
  int *v31; // [rsp+20h] [rbp-58h]
  int v32; // [rsp+28h] [rbp-50h]
  int v33; // [rsp+30h] [rbp-48h]

  *((_DWORD *)this + 2) = -1985229329;
  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)this = &OSF_CCONNECTION::`vftable';
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = (char *)this + 132;
  *((_DWORD *)this + 33) = 0;
  *((_DWORD *)this + 32) = 1;
  *((_QWORD *)this + 17) = (char *)this + 152;
  *((_QWORD *)this + 18) = 4;
  RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 216), 0);
  SIMPLE_DICT2::SIMPLE_DICT2((OSF_CCONNECTION *)((char *)this + 256));
  *(_DWORD *)(v13 + 88) = 0;
  *((_QWORD *)this + 46) = 4;
  *((_QWORD *)this + 45) = (char *)this + 376;
  *(_OWORD *)((char *)this + 376) = 0;
  v31 = 0;
  *(_OWORD *)((char *)this + 392) = 0;
  LogEvent(0x6Eu, 0x43u, this, 0, (unsigned __int64)v31, v32, v33);
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 28) = *((_DWORD *)this + 28);
  *((_QWORD *)this + 3) = a2;
  REFERENCED_OBJECT::AddReference(a2);
  *((_DWORD *)this + 3) = 128;
  *((_QWORD *)this + 51) = a3;
  *((_DWORD *)this + 11) = 0;
  *((_DWORD *)this + 21) = a4;
  v14 = (char *)this + *((unsigned int *)a3 + 15) + 480;
  *((_QWORD *)this + 52) = v14;
  *((_QWORD *)v14 - 1) = this;
  *((_WORD *)this + 24) = 512;
  *((_DWORD *)this + 10) = -1;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 117) = 0;
  if ( a7 )
    *((_DWORD *)this + 28) |= 0x20u;
  v15 = a8;
  if ( a6 )
  {
    *((_DWORD *)this + 28) |= 0x40u;
    if ( !a7 )
    {
      if ( a8 )
        CurrentThreadId = *(_DWORD *)(*((_QWORD *)a8 + 78) + 328LL);
      else
        CurrentThreadId = GetCurrentThreadId();
      OSF_CCONNECTION::AcquireCausalOrder(this, CurrentThreadId);
    }
  }
  *((_DWORD *)this + 27) = 1;
  *((_DWORD *)this + 4) = 2;
  _InterlockedOr(v30, 0);
  *((_QWORD *)this + 54) = 0;
  if ( *a9 )
    goto LABEL_21;
  v16 = *(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 51) + 80LL);
  if ( v16 )
    v17 = v16(
            (char *)this + 472,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL) + 8LL),
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL) + 24LL),
            *((_DWORD *)this + 28) & 0x40);
  else
    v17 = 0;
  v18 = *((_DWORD *)this + 28) | 8;
  *a9 = v17;
  *((_DWORD *)this + 28) = v18;
  if ( v17 )
    goto LABEL_13;
  v19 = (CSECURITY_CONTEXT *)AllocWrapper(0x138u);
  if ( !v19 )
  {
    *((_QWORD *)this + 44) = 0;
    goto LABEL_24;
  }
  v22 = CSECURITY_CONTEXT::CSECURITY_CONTEXT(v19, a5, v20, v21, a9);
  *((_QWORD *)this + 44) = v22;
  if ( !v22 )
LABEL_24:
    *a9 = 14;
  if ( *a9 )
  {
LABEL_21:
    *((_QWORD *)this + 9) = 0;
LABEL_22:
    v15 = 0;
    goto LABEL_19;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 3) + 184LL));
  *(_DWORD *)(*((_QWORD *)this + 44) + 208LL) = SIMPLE_DICT::Insert(
                                                  (OSF_CCONNECTION *)((char *)this + 360),
                                                  *((void **)this + 44));
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)this + 3) + 184LL));
  v24 = (CSECURITY_CONTEXT *)*((_QWORD *)this + 44);
  if ( *((_DWORD *)v24 + 52) == -1 )
  {
    if ( v24 )
      CSECURITY_CONTEXT::`scalar deleting destructor'(v24, v23);
    *((_QWORD *)this + 44) = 0;
    *a9 = 14;
    goto LABEL_21;
  }
  CSECURITY_CONTEXT::Lock(v24);
LABEL_13:
  if ( *a9 )
    goto LABEL_21;
  if ( a8 )
  {
    *((_QWORD *)this + 9) = a8;
    goto LABEL_19;
  }
  v25 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 51) + 68LL) + 8) + 640LL;
  if ( !gfRPCVerifierEnabled )
  {
    v26 = (OSF_CCALL *)AllocWrapper(v25);
    if ( v26 )
    {
      v15 = OSF_CCALL::OSF_CCALL(v26, a9);
      goto LABEL_18;
    }
    goto LABEL_20;
  }
  v29 = (OSF_CCALL *)AllocWrapper(v25);
  v15 = v29;
  if ( !v29 )
  {
LABEL_20:
    v15 = 0;
    goto LABEL_18;
  }
  OSF_CCALL::OSF_CCALL(v29, a9);
  *(_QWORD *)v15 = &OSF_CCALL_AVRF::`vftable';
LABEL_18:
  *((_QWORD *)this + 9) = v15;
  if ( !v15 )
  {
    *a9 = 14;
    goto LABEL_22;
  }
LABEL_19:
  *((_DWORD *)this + 16) = 0;
  result = this;
  *((_QWORD *)this + 4) = v15;
  *((_DWORD *)this + 116) = 0;
  return result;
}

```

## disassembly

```asm
0x180052a04  push    rbx
0x180052a06  push    rsi
0x180052a07  push    rdi
0x180052a08  push    r12
0x180052a0a  push    r14
0x180052a0c  push    r15
0x180052a0e  sub     rsp, 48h
0x180052a12  mov     dword ptr [rcx+8], 89ABCDEFh
0x180052a19  lea     rax, ??_7OSF_CCONNECTION@@6B@; const OSF_CCONNECTION::`vftable'
0x180052a20  mov     dword ptr [rcx+10h], 1
0x180052a27  xor     r12d, r12d
0x180052a2a  mov     [rcx], rax
0x180052a2d  mov     rbx, rdx
0x180052a30  mov     [rcx+70h], r12d
0x180052a34  lea     rax, [rcx+84h]
0x180052a3b  mov     [rcx+78h], rax
0x180052a3f  mov     r14, rcx
0x180052a42  mov     [rax], r12d
0x180052a45  xor     edx, edx; SpinCount
0x180052a47  mov     dword ptr [rcx+80h], 1
0x180052a51  lea     rax, [rcx+98h]
0x180052a58  mov     [rcx+88h], rax
0x180052a5f  mov     edi, r9d
0x180052a62  mov     qword ptr [rcx+90h], 4
0x180052a6d  mov     rsi, r8
0x180052a70  add     rcx, 0D8h; CriticalSection
0x180052a77  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180052a7d  lea     rcx, [r14+100h]; this
0x180052a84  call    ??0SIMPLE_DICT2@@QEAA@XZ; SIMPLE_DICT2::SIMPLE_DICT2(void)
0x180052a89  mov     [rcx+58h], r12d
0x180052a8d  lea     r15, [r14+168h]
0x180052a94  lea     rax, [r15+10h]
0x180052a98  mov     qword ptr [r15+8], 4
0x180052aa0  xorps   xmm0, xmm0
0x180052aa3  mov     [r15], rax
0x180052aa6  movups  xmmword ptr [rax], xmm0
0x180052aa9  xor     r9d, r9d; void *
0x180052aac  mov     [rsp+78h+var_58], r12; unsigned __int64
0x180052ab1  mov     r8, r14; void *
0x180052ab4  mov     dl, 43h ; 'C'; unsigned __int8
0x180052ab6  mov     cl, 6Eh ; 'n'; unsigned __int8
0x180052ab8  movups  xmmword ptr [rax+10h], xmm0
0x180052abc  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x180052ac1  mov     [r14+70h], r12d
0x180052ac5  mov     rcx, rbx; this
0x180052ac8  mov     eax, [r14+70h]
0x180052acc  mov     [r14+70h], eax
0x180052ad0  mov     [r14+18h], rbx
0x180052ad4  call    ?AddReference@REFERENCED_OBJECT@@QEAAHXZ; REFERENCED_OBJECT::AddReference(void)
0x180052ad9  mov     dword ptr [r14+0Ch], 80h
0x180052ae1  lea     rcx, [r14+1E0h]
0x180052ae8  mov     [r14+198h], rsi
0x180052aef  mov     [r14+2Ch], r12d
0x180052af3  mov     [r14+54h], edi
0x180052af7  mov     eax, [rsi+3Ch]
0x180052afa  add     rcx, rax
0x180052afd  mov     [r14+1A0h], rcx
0x180052b04  mov     [rcx-8], r14
0x180052b08  mov     ecx, [rsp+78h+arg_30]
0x180052b0f  mov     word ptr [r14+30h], 200h
0x180052b16  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x180052b1e  mov     [r14+60h], r12
0x180052b22  mov     [r14+58h], r12
0x180052b26  mov     [r14+50h], r12d
0x180052b2a  mov     [r14+44h], r12d
0x180052b2e  mov     [r14+1C8h], r12
0x180052b35  mov     [r14+160h], r12
0x180052b3c  mov     [r14+68h], r12d
0x180052b40  mov     [r14+38h], r12
0x180052b44  mov     [r14+1D4h], r12d
0x180052b4b  test    ecx, ecx
0x180052b4d  jz      short loc_180052B5A
0x180052b4f  mov     eax, [r14+70h]
0x180052b53  or      eax, 20h
0x180052b56  mov     [r14+70h], eax
0x180052b5a  mov     rbx, [rsp+78h+arg_38]
0x180052b62  cmp     [rsp+78h+arg_28], r12d
0x180052b6a  jnz     loc_180052D15
0x180052b70  mov     dword ptr [r14+6Ch], 1
0x180052b78  mov     dword ptr [r14+10h], 2
0x180052b80  lock or [rsp+78h+var_78], r12d
0x180052b85  mov     rdi, [rsp+78h+arg_40]
0x180052b8d  mov     [r14+1B0h], r12
0x180052b94  cmp     [rdi], r12d
0x180052b97  jnz     loc_180052CFA
0x180052b9d  mov     rax, [r14+198h]
0x180052ba4  mov     rax, [rax+50h]
0x180052ba8  test    rax, rax
0x180052bab  jz      loc_180052D51
0x180052bb1  mov     rcx, [r14+18h]
0x180052bb5  mov     r9d, [r14+70h]
0x180052bb9  and     r9d, 40h
0x180052bbd  mov     rdx, [rcx+18h]
0x180052bc1  lea     rcx, [r14+1D8h]
0x180052bc8  mov     r8, [rdx+18h]
0x180052bcc  mov     rdx, [rdx+8]
0x180052bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052bd5  mov     ecx, eax
0x180052bd7  mov     eax, [r14+70h]
0x180052bdb  or      eax, 8
0x180052bde  mov     [rdi], ecx
0x180052be0  mov     [r14+70h], eax
0x180052be4  test    ecx, ecx
0x180052be6  jnz     loc_180052C81
0x180052bec  mov     ecx, 138h; dwBytes
0x180052bf1  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180052bf6  test    rax, rax
0x180052bf9  jz      loc_180052D03
0x180052bff  mov     rdx, [rsp+78h+arg_20]; struct CLIENT_AUTH_INFO *
0x180052c07  mov     rcx, rax; this
0x180052c0a  mov     [rsp+78h+var_58], rdi; int *
0x180052c0f  call    ??0CSECURITY_CONTEXT@@QEAA@PEAUCLIENT_AUTH_INFO@@IHPEAJ@Z; CSECURITY_CONTEXT::CSECURITY_CONTEXT(CLIENT_AUTH_INFO *,uint,int,long *)
0x180052c14  mov     [r14+160h], rax
0x180052c1b  test    rax, rax
0x180052c1e  jz      loc_180052D0A
0x180052c24  cmp     [rdi], r12d
0x180052c27  jnz     loc_180052CFA
0x180052c2d  mov     rcx, [r14+18h]
0x180052c31  mov     esi, 0B8h
0x180052c36  add     rcx, rsi; CriticalSection
0x180052c39  call    cs:__imp_RtlEnterCriticalSection
0x180052c3f  mov     rdx, [r14+160h]; void *
0x180052c46  mov     rcx, r15; this
0x180052c49  call    ?Insert@SIMPLE_DICT@@QEAAIPEAX@Z; SIMPLE_DICT::Insert(void *)
0x180052c4e  mov     rcx, [r14+160h]
0x180052c55  mov     [rcx+0D0h], eax
0x180052c5b  mov     rcx, [r14+18h]
0x180052c5f  add     rcx, rsi; CriticalSection
0x180052c62  call    cs:__imp_RtlLeaveCriticalSection
0x180052c68  mov     rcx, [r14+160h]; this
0x180052c6f  cmp     dword ptr [rcx+0D0h], 0FFFFFFFFh
0x180052c76  jz      loc_180052D59
0x180052c7c  call    ?Lock@CSECURITY_CONTEXT@@QEAAXXZ; CSECURITY_CONTEXT::Lock(void)
0x180052c81  cmp     [rdi], r12d
0x180052c84  jnz     short loc_180052CFA
0x180052c86  test    rbx, rbx
0x180052c89  jnz     loc_180052D72
0x180052c8f  mov     rax, [r14+198h]
0x180052c96  mov     ecx, [rax+44h]
0x180052c99  add     ecx, 8
0x180052c9c  add     rcx, 280h; dwBytes
0x180052ca3  cmp     cs:?gfRPCVerifierEnabled@@3HA, r12d; int gfRPCVerifierEnabled
0x180052caa  jnz     loc_180052D7B
0x180052cb0  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180052cb5  test    rax, rax
0x180052cb8  jz      short loc_180052CF5
0x180052cba  mov     rdx, rdi; int *
0x180052cbd  mov     rcx, rax; this
0x180052cc0  call    ??0OSF_CCALL@@AEAA@PEAJ@Z; OSF_CCALL::OSF_CCALL(long *)
0x180052cc5  mov     rbx, rax
0x180052cc8  mov     [r14+48h], rbx
0x180052ccc  test    rbx, rbx
0x180052ccf  jz      loc_180052DA6
0x180052cd5  mov     [r14+40h], r12d
0x180052cd9  mov     rax, r14
0x180052cdc  mov     [r14+20h], rbx
0x180052ce0  mov     [r14+1D0h], r12d
0x180052ce7  add     rsp, 48h
0x180052ceb  pop     r15
0x180052ced  pop     r14
0x180052cef  pop     r12
0x180052cf1  pop     rdi
0x180052cf2  pop     rsi
0x180052cf3  pop     rbx
0x180052cf4  retn
0x180052cf5  mov     rbx, r12
0x180052cf8  jmp     short loc_180052CC8
0x180052cfa  mov     [r14+48h], r12
0x180052cfe  mov     rbx, r12
0x180052d01  jmp     short loc_180052CD5
0x180052d03  mov     [r14+160h], r12
0x180052d0a  mov     dword ptr [rdi], 0Eh
0x180052d10  jmp     loc_180052C24
0x180052d15  mov     eax, [r14+70h]
0x180052d19  or      eax, 40h
0x180052d1c  mov     [r14+70h], eax
0x180052d20  test    ecx, ecx
0x180052d22  jnz     loc_180052B70
0x180052d28  test    rbx, rbx
0x180052d2b  jz      short loc_180052D3C
0x180052d2d  mov     rdx, [rbx+270h]
0x180052d34  mov     edx, [rdx+148h]
0x180052d3a  jmp     short loc_180052D44
0x180052d3c  call    cs:__imp_GetCurrentThreadId
0x180052d42  mov     edx, eax; unsigned int
0x180052d44  mov     rcx, r14; this
0x180052d47  call    ?AcquireCausalOrder@OSF_CCONNECTION@@QEAAHK@Z; OSF_CCONNECTION::AcquireCausalOrder(ulong)
0x180052d4c  jmp     loc_180052B70
0x180052d51  mov     ecx, r12d
0x180052d54  jmp     loc_180052BD7
0x180052d59  test    rcx, rcx
0x180052d5c  jz      short loc_180052D63
0x180052d5e  call    ??_GCSECURITY_CONTEXT@@QEAAPEAXI@Z; CSECURITY_CONTEXT::`scalar deleting destructor'(uint)
0x180052d63  mov     [r14+160h], r12
0x180052d6a  mov     dword ptr [rdi], 0Eh
0x180052d70  jmp     short loc_180052CFA
0x180052d72  mov     [r14+48h], rbx
0x180052d76  jmp     loc_180052CD5
0x180052d7b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180052d80  mov     rbx, rax
0x180052d83  test    rax, rax
0x180052d86  jz      loc_180052CF5
0x180052d8c  mov     rdx, rdi; int *
0x180052d8f  mov     rcx, rax; this
0x180052d92  call    ??0OSF_CCALL@@AEAA@PEAJ@Z; OSF_CCALL::OSF_CCALL(long *)
0x180052d97  lea     rax, ??_7OSF_CCALL_AVRF@@6B@; const OSF_CCALL_AVRF::`vftable'
0x180052d9e  mov     [rbx], rax
0x180052da1  jmp     loc_180052CC8
0x180052da6  mov     dword ptr [rdi], 0Eh
0x180052dac  jmp     loc_180052CFE
```
