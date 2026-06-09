# IDispatchExInvokeEx2(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180005e40`
- end: `0x1800060b9`
- name: `?IDispatchExInvokeEx2@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(struct CSession *, struct IDispatchEx *, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180004400`

## callees

- `0x180005e40`
- `0x1800070c0`
- `0x180007130`
- `0x18001c3c8`
- `0x18001ecc0`
- `0x1800413d8`
- `0x18005d884`
- `0x18007a010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180005ef0`
- `msvcrt!_statusfp` at `0x180005f82`
- `msvcrt!_statusfp` at `0x180005ef0`
- `msvcrt!_statusfp` at `0x180005f82`
- `msvcrt!_clearfp` at `0x180006032`
- `msvcrt!_clearfp` at `0x180006043`
- `msvcrt!_clearfp` at `0x180006032`
- `msvcrt!_clearfp` at `0x180006043`
- `msvcrt!_controlfp` at `0x180005fa0`
- `msvcrt!_controlfp` at `0x180005fa0`
- `KERNEL32!TlsGetValue` at `0x180005ec8`
- `KERNEL32!TlsGetValue` at `0x180005ec8`

## pseudocode

```c
__int64 __fastcall IDispatchExInvokeEx2(
        struct CSession *a1,
        struct IDispatchEx *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        struct IServiceProvider *a9)
{
  __int64 v13; // rcx
  JAmsi *v14; // rcx
  __int64 result; // rax
  _QWORD *Value; // rax
  _QWORD *v17; // rbx
  struct GL **v18; // rsi
  COleScript *v19; // r12
  struct GL *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // edi
  COleScript *v23; // [rsp+50h] [rbp-38h]

  if ( !(unsigned int)FStackAvailable(0x10000u) )
    return 2147942414LL;
  v13 = *((_QWORD *)a1 + 4);
  if ( !v13
    || (v14 = (JAmsi *)(v13 + 200)) == 0
    || *((_DWORD *)v14 + 1) != 1
    || (result = JAmsi::JAmsiProcessor(v14, (struct IDispatch *)a2, a3, a6, a1), (int)result >= 0) )
  {
    Value = TlsGetValue(g_luTls);
    v17 = Value;
    if ( Value )
    {
      v18 = (struct GL **)Value[3];
      v19 = 0;
      if ( v18 )
        Value[3] = 0;
      if ( _statusfp() )
        _clearfp();
    }
    else
    {
      v19 = v23;
      v18 = (struct GL **)v23;
    }
    if ( *((int *)a1 + 22) < 0 )
    {
      v21 = TrapIDispatchExInvokeEx(a2, a3, a4, a5, a6, a7, a8, a9);
    }
    else if ( v18 && (v20 = v18[83]) != 0 )
    {
      v21 = CatchIDispatchExInvokeEx(v20, a2, a3, a4, a5, a6, a7, a8, a9);
    }
    else
    {
      v21 = ((__int64 (__fastcall *)(struct IDispatchEx *, _QWORD, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *))a2->lpVtbl->InvokeEx)(
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              a9);
    }
    v22 = v21;
    if ( v17 )
    {
      if ( v18 != (struct GL **)v19 && v19 )
      {
        COleScript::OnLeaveScript(v19);
        COleScript::Release(v19);
      }
      v17[3] = v18;
      if ( _statusfp() )
        _clearfp();
      _controlfp(0x1Fu, 0x30F031Fu);
    }
    return v22;
  }
  return result;
}

```

## disassembly

```asm
0x180005e40  push    rdi
0x180005e42  push    r13
0x180005e44  push    r14
0x180005e46  push    r15
0x180005e48  sub     rsp, 68h
0x180005e4c  mov     rdi, rcx
0x180005e4f  mov     r13d, r9d
0x180005e52  mov     ecx, 10000h; unsigned int
0x180005e57  mov     r15d, r8d
0x180005e5a  mov     r14, rdx
0x180005e5d  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180005e62  test    eax, eax
0x180005e64  jz      loc_180006054
0x180005e6a  mov     rcx, [rdi+20h]
0x180005e6e  mov     [rsp+88h+arg_8], rbp
0x180005e76  mov     rbp, [rsp+88h+arg_28]
0x180005e7e  test    rcx, rcx
0x180005e81  jz      short loc_180005EAD
0x180005e83  add     rcx, 0C8h; this
0x180005e8a  jz      short loc_180005EAD
0x180005e8c  cmp     dword ptr [rcx+4], 1
0x180005e90  jnz     short loc_180005EAD
0x180005e92  mov     r9, rbp; struct tagDISPPARAMS *
0x180005e95  mov     [rsp+88h+var_68], rdi; struct CSession *
0x180005e9a  mov     r8d, r15d; int
0x180005e9d  mov     rdx, r14; struct IDispatch *
0x180005ea0  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x180005ea5  test    eax, eax
0x180005ea7  js      loc_180005FC3
0x180005ead  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180005eb3  mov     [rsp+88h+arg_0], rbx
0x180005ebb  mov     [rsp+88h+arg_10], rsi
0x180005ec3  mov     [rsp+88h+var_28], r12
0x180005ec8  call    cs:__imp_TlsGetValue
0x180005ecf  nop     dword ptr [rax+rax+00h]
0x180005ed4  mov     rbx, rax
0x180005ed7  test    rax, rax
0x180005eda  jz      loc_18000605E
0x180005ee0  mov     rsi, [rax+18h]
0x180005ee4  xor     r12d, r12d
0x180005ee7  test    rsi, rsi
0x180005eea  jz      short loc_180005EF0
0x180005eec  mov     [rax+18h], r12
0x180005ef0  call    cs:__imp__statusfp
0x180005ef7  nop     dword ptr [rax+rax+00h]
0x180005efc  test    eax, eax
0x180005efe  jnz     loc_180006032
0x180005f04  cmp     dword ptr [rdi+58h], 0
0x180005f08  jl      loc_180005FEA
0x180005f0e  test    rsi, rsi
0x180005f11  jz      short loc_180005F23
0x180005f13  mov     rcx, [rsi+298h]; struct GL *
0x180005f1a  test    rcx, rcx
0x180005f1d  jnz     loc_18000606D
0x180005f23  mov     rcx, [rsp+88h+arg_40]
0x180005f2b  mov     r8d, r13d
0x180005f2e  mov     rax, [r14]
0x180005f31  mov     edx, r15d
0x180005f34  movzx   r9d, [rsp+88h+arg_20]
0x180005f3d  mov     [rsp+88h+var_50], rcx
0x180005f42  mov     rcx, [rsp+88h+arg_38]
0x180005f4a  mov     rax, [rax+40h]
0x180005f4e  mov     [rsp+88h+var_58], rcx
0x180005f53  mov     rcx, [rsp+88h+arg_30]
0x180005f5b  mov     [rsp+88h+var_60], rcx
0x180005f60  mov     rcx, r14
0x180005f63  mov     [rsp+88h+var_68], rbp
0x180005f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f6d  mov     edi, eax
0x180005f6f  test    rbx, rbx
0x180005f72  jz      short loc_180005FAC
0x180005f74  cmp     rsi, r12
0x180005f77  jz      short loc_180005F7E
0x180005f79  test    r12, r12
0x180005f7c  jnz     short loc_180005FD8
0x180005f7e  mov     [rbx+18h], rsi
0x180005f82  call    cs:__imp__statusfp
0x180005f89  nop     dword ptr [rax+rax+00h]
0x180005f8e  test    eax, eax
0x180005f90  jnz     loc_180006043
0x180005f96  mov     edx, 30F031Fh; Mask
0x180005f9b  mov     ecx, 1Fh; NewValue
0x180005fa0  call    cs:__imp__controlfp
0x180005fa7  nop     dword ptr [rax+rax+00h]
0x180005fac  mov     r12, [rsp+88h+var_28]
0x180005fb1  mov     eax, edi
0x180005fb3  mov     rsi, [rsp+88h+arg_10]
0x180005fbb  mov     rbx, [rsp+88h+arg_0]
0x180005fc3  mov     rbp, [rsp+88h+arg_8]
0x180005fcb  add     rsp, 68h
0x180005fcf  pop     r15
0x180005fd1  pop     r14
0x180005fd3  pop     r13
0x180005fd5  pop     rdi
0x180005fd6  retn
0x180005fd8  mov     rcx, r12; this
0x180005fdb  call    ?OnLeaveScript@COleScript@@QEAAXXZ; COleScript::OnLeaveScript(void)
0x180005fe0  mov     rcx, r12; this
0x180005fe3  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180005fe8  jmp     short loc_180005F7E
0x180005fea  mov     rax, [rsp+88h+arg_40]
0x180005ff2  mov     r8d, r13d; unsigned int
0x180005ff5  movzx   r9d, [rsp+88h+arg_20]; unsigned __int16
0x180005ffe  mov     edx, r15d; int
0x180006001  mov     [rsp+88h+var_50], rax; struct IServiceProvider *
0x180006006  mov     rcx, r14; struct IDispatchEx *
0x180006009  mov     rax, [rsp+88h+arg_38]
0x180006011  mov     [rsp+88h+var_58], rax; struct tagEXCEPINFO *
0x180006016  mov     rax, [rsp+88h+arg_30]
0x18000601e  mov     [rsp+88h+var_60], rax; struct tagVARIANT *
0x180006023  mov     [rsp+88h+var_68], rbp; struct tagDISPPARAMS *
0x180006028  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x18000602d  jmp     loc_180005F6D
0x180006032  call    cs:__imp__clearfp
0x180006039  nop     dword ptr [rax+rax+00h]
0x18000603e  jmp     loc_180005F04
0x180006043  call    cs:__imp__clearfp
0x18000604a  nop     dword ptr [rax+rax+00h]
0x18000604f  jmp     loc_180005F96
0x180006054  mov     eax, 8007000Eh
0x180006059  jmp     loc_180005FCB
0x18000605e  mov     r12, [rsp+88h+var_38]
0x180006063  mov     rsi, [rsp+88h+var_38]
0x180006068  jmp     loc_180005F04
0x18000606d  mov     rax, [rsp+88h+arg_40]
0x180006075  mov     r9d, r13d; unsigned int
0x180006078  mov     [rsp+88h+var_48], rax; struct IServiceProvider *
0x18000607d  mov     r8d, r15d; int
0x180006080  mov     rax, [rsp+88h+arg_38]
0x180006088  mov     rdx, r14; struct IDispatchEx *
0x18000608b  mov     [rsp+88h+var_50], rax; struct tagEXCEPINFO *
0x180006090  mov     rax, [rsp+88h+arg_30]
0x180006098  mov     [rsp+88h+var_58], rax; struct tagVARIANT *
0x18000609d  movzx   eax, [rsp+88h+arg_20]
0x1800060a5  mov     [rsp+88h+var_60], rbp; struct tagDISPPARAMS *
0x1800060aa  mov     word ptr [rsp+88h+var_68], ax; unsigned __int16
0x1800060af  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x1800060b4  jmp     loc_180005F6D
```
