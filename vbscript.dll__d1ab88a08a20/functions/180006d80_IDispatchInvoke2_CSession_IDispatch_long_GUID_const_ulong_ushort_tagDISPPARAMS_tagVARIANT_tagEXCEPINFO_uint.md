# IDispatchInvoke2(CSession *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180006d80`
- end: `0x1800070ab`
- name: `?IDispatchInvoke2@@YAJPEAVCSession@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `811`
- prototype: `__int64 __fastcall(struct CSession *, struct IDispatch *, unsigned int, struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180004400`

## callees

- `0x180006d80`
- `0x1800070c0`
- `0x180007130`
- `0x18001e2e4`
- `0x18001ecc0`
- `0x180041448`
- `0x18005d930`
- `0x1800684dc`
- `0x180078100`
- `0x18007a010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180006e05`
- `msvcrt!_statusfp` at `0x180006ea0`
- `msvcrt!_statusfp` at `0x180006e05`
- `msvcrt!_statusfp` at `0x180006ea0`
- `msvcrt!_clearfp` at `0x180007019`
- `msvcrt!_clearfp` at `0x18000702a`
- `msvcrt!_clearfp` at `0x180007019`
- `msvcrt!_clearfp` at `0x18000702a`
- `msvcrt!_controlfp` at `0x180006ebe`
- `msvcrt!_controlfp` at `0x180006ebe`
- `KERNEL32!TlsGetValue` at `0x180006dde`
- `KERNEL32!TlsGetValue` at `0x180006dde`
- `KERNEL32!GetCurrentThreadId` at `0x180006fa9`
- `KERNEL32!GetCurrentThreadId` at `0x180006fa9`
- `KERNEL32!LeaveCriticalSection` at `0x180007000`
- `KERNEL32!LeaveCriticalSection` at `0x180007000`

## pseudocode

```c
__int64 __fastcall IDispatchInvoke2(
        struct CSession *a1,
        struct IDispatch *a2,
        unsigned int a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  __int64 v13; // rax
  const struct _GUID **Value; // rax
  const struct _GUID *v15; // r8
  const struct _GUID *v16; // r9
  const struct _GUID **v17; // rbx
  const struct _GUID *v18; // rsi
  struct _GUID *v19; // rbp
  unsigned int v20; // eax
  unsigned int v21; // r14d
  int v23; // eax
  unsigned int v24; // ebx
  struct GL *v25; // rcx
  int v26; // edi
  __int64 v27; // rcx
  int v29; // [rsp+20h] [rbp-58h]

  if ( !(unsigned int)FStackAvailable(0x10000u) )
    return 2147942414LL;
  v13 = *((_QWORD *)a1 + 4);
  if ( v13
    && v13 != -200
    && *(_DWORD *)(v13 + 204) == 1
    && (v23 = JAmsi::JAmsiProcessor((JAmsi *)(v13 + 200), a2, a3, a7, a1), v24 = v23, v23 < 0) )
  {
    CSession::ReportError(a1, v23);
    VBScriptClass_Report_Unexpected_Fatal_Error(a1);
    return v24;
  }
  else
  {
    Value = (const struct _GUID **)TlsGetValue(g_luTls);
    v17 = Value;
    if ( Value )
    {
      v18 = Value[3];
      v19 = 0;
      if ( v18 )
        Value[3] = 0;
      if ( _statusfp() )
        _clearfp();
    }
    else
    {
      v18 = a4;
      v19 = a4;
    }
    if ( *((int *)a1 + 22) < 0 )
    {
      v20 = TrapIDispatchInvoke(a2, a3, v15, a5, a6, a7, a8, a9, a10);
    }
    else if ( v18 && (v25 = *(struct GL **)v18[41].Data4) != 0 )
    {
      v20 = CatchIDispatchInvoke(v25, a2, a3, v16, a5, a6, a7, a8, a9, a10);
    }
    else
    {
      LOWORD(v29) = a6;
      v20 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, _QWORD, int, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))a2->lpVtbl->Invoke)(
              a2,
              a3,
              &GUID_NULL,
              a5,
              v29,
              a7,
              a8,
              a9,
              a10);
    }
    v21 = v20;
    if ( v17 )
    {
      if ( v18 != v19 && v19 )
      {
        v26 = *(_DWORD *)&v19[15].Data2;
        if ( GetCurrentThreadId() == v26 )
        {
          v27 = *(_QWORD *)&v19[10].Data1;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 80LL))(v27);
          if ( (unsigned int)COleScript::DisableInterrupts((COleScript *)v19) )
          {
            if ( v19[17].Data1-- == 1 )
              *(_DWORD *)&v19[16].Data4[4] = 0;
            if ( v19[33].Data1 )
              LeaveCriticalSection((LPCRITICAL_SECTION)v19[33].Data4);
          }
        }
        COleScript::Release((COleScript *)v19);
      }
      v17[3] = v18;
      if ( _statusfp() )
        _clearfp();
      _controlfp(0x1Fu, 0x30F031Fu);
    }
    return v21;
  }
}

```

## disassembly

```asm
0x180006d80  mov     [rsp+arg_18], r9
0x180006d85  push    rdi
0x180006d86  push    r12
0x180006d88  push    r15
0x180006d8a  sub     rsp, 60h
0x180006d8e  mov     rdi, rcx
0x180006d91  mov     r12d, r8d
0x180006d94  mov     ecx, 10000h; unsigned int
0x180006d99  mov     r15, rdx
0x180006d9c  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180006da1  test    eax, eax
0x180006da3  jz      loc_18000708C
0x180006da9  mov     rax, [rdi+20h]
0x180006dad  mov     [rsp+78h+arg_0], rbx
0x180006db5  mov     [rsp+78h+var_28], r14
0x180006dba  mov     r14, [rsp+78h+arg_30]
0x180006dc2  test    rax, rax
0x180006dc5  jnz     loc_180006EF2
0x180006dcb  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180006dd1  mov     [rsp+78h+arg_8], rbp
0x180006dd9  mov     [rsp+78h+var_20], rsi
0x180006dde  call    cs:__imp_TlsGetValue
0x180006de5  nop     dword ptr [rax+rax+00h]
0x180006dea  mov     rbx, rax
0x180006ded  test    rax, rax
0x180006df0  jz      loc_180007096
0x180006df6  mov     rsi, [rax+18h]
0x180006dfa  xor     ebp, ebp
0x180006dfc  test    rsi, rsi
0x180006dff  jz      short loc_180006E05
0x180006e01  mov     [rax+18h], rbp
0x180006e05  call    cs:__imp__statusfp
0x180006e0c  nop     dword ptr [rax+rax+00h]
0x180006e11  test    eax, eax
0x180006e13  jnz     loc_180007019
0x180006e19  cmp     dword ptr [rdi+58h], 0
0x180006e1d  jl      loc_18000703B
0x180006e23  test    rsi, rsi
0x180006e26  jnz     loc_180006F3F
0x180006e2c  mov     rcx, [rsp+78h+arg_48]
0x180006e34  lea     r8, GUID_NULL
0x180006e3b  mov     rax, [r15]
0x180006e3e  mov     edx, r12d
0x180006e41  mov     r9d, [rsp+78h+arg_20]
0x180006e49  mov     [rsp+78h+var_38], rcx
0x180006e4e  mov     rcx, [rsp+78h+arg_40]
0x180006e56  mov     rax, [rax+30h]
0x180006e5a  mov     [rsp+78h+var_40], rcx
0x180006e5f  mov     rcx, [rsp+78h+arg_38]
0x180006e67  mov     [rsp+78h+var_48], rcx
0x180006e6c  movzx   ecx, [rsp+78h+arg_28]
0x180006e74  mov     [rsp+78h+var_50], r14
0x180006e79  mov     word ptr [rsp+78h+var_58], cx
0x180006e7e  mov     rcx, r15
0x180006e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e86  mov     r14d, eax
0x180006e89  test    rbx, rbx
0x180006e8c  jz      short loc_180006ECA
0x180006e8e  cmp     rsi, rbp
0x180006e91  jz      short loc_180006E9C
0x180006e93  test    rbp, rbp
0x180006e96  jnz     loc_180006FA3
0x180006e9c  mov     [rbx+18h], rsi
0x180006ea0  call    cs:__imp__statusfp
0x180006ea7  nop     dword ptr [rax+rax+00h]
0x180006eac  test    eax, eax
0x180006eae  jnz     loc_18000702A
0x180006eb4  mov     edx, 30F031Fh; Mask
0x180006eb9  mov     ecx, 1Fh; NewValue
0x180006ebe  call    cs:__imp__controlfp
0x180006ec5  nop     dword ptr [rax+rax+00h]
0x180006eca  mov     rsi, [rsp+78h+var_20]
0x180006ecf  mov     eax, r14d
0x180006ed2  mov     rbp, [rsp+78h+arg_8]
0x180006eda  mov     rbx, [rsp+78h+arg_0]
0x180006ee2  mov     r14, [rsp+78h+var_28]
0x180006ee7  add     rsp, 60h
0x180006eeb  pop     r15
0x180006eed  pop     r12
0x180006eef  pop     rdi
0x180006ef0  retn
0x180006ef2  lea     rcx, [rax+0C8h]; this
0x180006ef9  test    rcx, rcx
0x180006efc  jz      loc_180006DCB
0x180006f02  cmp     dword ptr [rcx+4], 1
0x180006f06  jnz     loc_180006DCB
0x180006f0c  mov     r9, r14; struct tagDISPPARAMS *
0x180006f0f  mov     [rsp+78h+var_58], rdi; struct CSession *
0x180006f14  mov     r8d, r12d; int
0x180006f17  mov     rdx, r15; struct IDispatch *
0x180006f1a  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x180006f1f  mov     ebx, eax
0x180006f21  test    eax, eax
0x180006f23  jns     loc_180006DCB
0x180006f29  mov     edx, eax; int
0x180006f2b  mov     rcx, rdi; this
0x180006f2e  call    ?ReportError@CSession@@QEAAJJ@Z; CSession::ReportError(long)
0x180006f33  mov     rcx, rdi
0x180006f36  call    VBScriptClass_Report_Unexpected_Fatal_Error
0x180006f3b  mov     eax, ebx
0x180006f3d  jmp     short loc_180006EDA
0x180006f3f  mov     rcx, [rsi+298h]; struct GL *
0x180006f46  test    rcx, rcx
0x180006f49  jz      loc_180006E2C
0x180006f4f  mov     rax, [rsp+78h+arg_48]
0x180006f57  mov     r8d, r12d; int
0x180006f5a  mov     [rsp+78h+var_30], rax; unsigned int *
0x180006f5f  mov     rdx, r15; struct IDispatch *
0x180006f62  mov     rax, [rsp+78h+arg_40]
0x180006f6a  mov     [rsp+78h+var_38], rax; struct tagEXCEPINFO *
0x180006f6f  mov     rax, [rsp+78h+arg_38]
0x180006f77  mov     [rsp+78h+var_40], rax; struct tagVARIANT *
0x180006f7c  movzx   eax, [rsp+78h+arg_28]
0x180006f84  mov     [rsp+78h+var_48], r14; struct tagDISPPARAMS *
0x180006f89  mov     word ptr [rsp+78h+var_50], ax; unsigned __int16
0x180006f8e  mov     eax, [rsp+78h+arg_20]
0x180006f95  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180006f99  call    ?CatchIDispatchInvoke@@YAJPEAVGL@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; CatchIDispatchInvoke(GL *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180006f9e  jmp     loc_180006E86
0x180006fa3  mov     edi, [rbp+0F4h]
0x180006fa9  call    cs:__imp_GetCurrentThreadId
0x180006fb0  nop     dword ptr [rax+rax+00h]
0x180006fb5  cmp     eax, edi
0x180006fb7  jnz     short loc_18000700C
0x180006fb9  mov     rcx, [rbp+0A0h]
0x180006fc0  test    rcx, rcx
0x180006fc3  jz      short loc_180006FD1
0x180006fc5  mov     rax, [rcx]
0x180006fc8  mov     rax, [rax+50h]
0x180006fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd1  mov     rcx, rbp; this
0x180006fd4  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180006fd9  test    eax, eax
0x180006fdb  jz      short loc_18000700C
0x180006fdd  add     dword ptr [rbp+110h], 0FFFFFFFFh
0x180006fe4  jnz     short loc_180006FF0
0x180006fe6  mov     dword ptr [rbp+10Ch], 0
0x180006ff0  cmp     dword ptr [rbp+210h], 0
0x180006ff7  jz      short loc_18000700C
0x180006ff9  lea     rcx, [rbp+218h]; lpCriticalSection
0x180007000  call    cs:__imp_LeaveCriticalSection
0x180007007  nop     dword ptr [rax+rax+00h]
0x18000700c  mov     rcx, rbp; this
0x18000700f  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180007014  jmp     loc_180006E9C
0x180007019  call    cs:__imp__clearfp
0x180007020  nop     dword ptr [rax+rax+00h]
0x180007025  jmp     loc_180006E19
0x18000702a  call    cs:__imp__clearfp
0x180007031  nop     dword ptr [rax+rax+00h]
0x180007036  jmp     loc_180006EB4
0x18000703b  mov     rax, [rsp+78h+arg_48]
0x180007043  mov     edx, r12d; int
0x180007046  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x18000704e  mov     rcx, r15; struct IDispatch *
0x180007051  mov     [rsp+78h+var_38], rax; unsigned int *
0x180007056  mov     rax, [rsp+78h+arg_40]
0x18000705e  mov     [rsp+78h+var_40], rax; struct tagEXCEPINFO *
0x180007063  mov     rax, [rsp+78h+arg_38]
0x18000706b  mov     [rsp+78h+var_48], rax; struct tagVARIANT *
0x180007070  movzx   eax, [rsp+78h+arg_28]
0x180007078  mov     [rsp+78h+var_50], r14; struct tagDISPPARAMS *
0x18000707d  mov     word ptr [rsp+78h+var_58], ax; unsigned __int16
0x180007082  call    ?TrapIDispatchInvoke@@YAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; TrapIDispatchInvoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180007087  jmp     loc_180006E86
0x18000708c  mov     eax, 8007000Eh
0x180007091  jmp     loc_180006EE7
0x180007096  mov     rsi, [rsp+78h+arg_18]
0x18000709e  mov     rbp, [rsp+78h+arg_18]
0x1800070a6  jmp     loc_180006E19
```
