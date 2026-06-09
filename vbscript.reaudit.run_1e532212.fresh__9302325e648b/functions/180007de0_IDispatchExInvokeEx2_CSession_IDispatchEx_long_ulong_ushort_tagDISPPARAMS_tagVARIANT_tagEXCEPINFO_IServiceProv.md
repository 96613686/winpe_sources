# IDispatchExInvokeEx2(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180007de0`
- end: `0x180008034`
- name: `?IDispatchExInvokeEx2@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(struct CSession *, struct IDispatchEx *, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180006550`

## callees

- `0x18000516c`
- `0x180007de0`
- `0x180008fc0`
- `0x180009020`
- `0x1800238b0`
- `0x18003fd00`
- `0x18005bcfc`
- `0x180077010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180007e8a`
- `msvcrt!_statusfp` at `0x180007f16`
- `msvcrt!_statusfp` at `0x180007e8a`
- `msvcrt!_statusfp` at `0x180007f16`
- `msvcrt!_clearfp` at `0x180007fb9`
- `msvcrt!_clearfp` at `0x180007fc4`
- `msvcrt!_clearfp` at `0x180007fb9`
- `msvcrt!_clearfp` at `0x180007fc4`
- `msvcrt!_controlfp` at `0x180007f2e`
- `msvcrt!_controlfp` at `0x180007f2e`
- `KERNEL32!TlsGetValue` at `0x180007e68`
- `KERNEL32!TlsGetValue` at `0x180007e68`

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
0x180007de0  push    rdi
0x180007de2  push    r13
0x180007de4  push    r14
0x180007de6  push    r15
0x180007de8  sub     rsp, 68h
0x180007dec  mov     rdi, rcx
0x180007def  mov     r13d, r9d
0x180007df2  mov     ecx, 10000h; unsigned int
0x180007df7  mov     r15d, r8d
0x180007dfa  mov     r14, rdx
0x180007dfd  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180007e02  test    eax, eax
0x180007e04  jz      loc_180007FCF
0x180007e0a  mov     rcx, [rdi+20h]
0x180007e0e  mov     [rsp+88h+arg_8], rbp
0x180007e16  mov     rbp, [rsp+88h+arg_28]
0x180007e1e  test    rcx, rcx
0x180007e21  jz      short loc_180007E4D
0x180007e23  add     rcx, 0C8h; this
0x180007e2a  jz      short loc_180007E4D
0x180007e2c  cmp     dword ptr [rcx+4], 1
0x180007e30  jnz     short loc_180007E4D
0x180007e32  mov     r9, rbp; struct tagDISPPARAMS *
0x180007e35  mov     [rsp+88h+var_68], rdi; struct CSession *
0x180007e3a  mov     r8d, r15d; int
0x180007e3d  mov     rdx, r14; struct IDispatch *
0x180007e40  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x180007e45  test    eax, eax
0x180007e47  js      loc_180007F4B
0x180007e4d  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180007e53  mov     [rsp+88h+arg_0], rbx
0x180007e5b  mov     [rsp+88h+arg_10], rsi
0x180007e63  mov     [rsp+88h+var_28], r12
0x180007e68  call    cs:__imp_TlsGetValue
0x180007e6e  mov     rbx, rax
0x180007e71  test    rax, rax
0x180007e74  jz      loc_180007FD9
0x180007e7a  mov     rsi, [rax+18h]
0x180007e7e  xor     r12d, r12d
0x180007e81  test    rsi, rsi
0x180007e84  jz      short loc_180007E8A
0x180007e86  mov     [rax+18h], r12
0x180007e8a  call    cs:__imp__statusfp
0x180007e90  test    eax, eax
0x180007e92  jnz     loc_180007FB9
0x180007e98  cmp     dword ptr [rdi+58h], 0
0x180007e9c  jl      loc_180007F71
0x180007ea2  test    rsi, rsi
0x180007ea5  jz      short loc_180007EB7
0x180007ea7  mov     rcx, [rsi+298h]; struct GL *
0x180007eae  test    rcx, rcx
0x180007eb1  jnz     loc_180007FE8
0x180007eb7  mov     rcx, [rsp+88h+arg_40]
0x180007ebf  mov     r8d, r13d
0x180007ec2  mov     rax, [r14]
0x180007ec5  mov     edx, r15d
0x180007ec8  movzx   r9d, [rsp+88h+arg_20]
0x180007ed1  mov     [rsp+88h+var_50], rcx
0x180007ed6  mov     rcx, [rsp+88h+arg_38]
0x180007ede  mov     rax, [rax+40h]
0x180007ee2  mov     [rsp+88h+var_58], rcx
0x180007ee7  mov     rcx, [rsp+88h+arg_30]
0x180007eef  mov     [rsp+88h+var_60], rcx
0x180007ef4  mov     rcx, r14
0x180007ef7  mov     [rsp+88h+var_68], rbp
0x180007efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f01  mov     edi, eax
0x180007f03  test    rbx, rbx
0x180007f06  jz      short loc_180007F34
0x180007f08  cmp     rsi, r12
0x180007f0b  jz      short loc_180007F12
0x180007f0d  test    r12, r12
0x180007f10  jnz     short loc_180007F5F
0x180007f12  mov     [rbx+18h], rsi
0x180007f16  call    cs:__imp__statusfp
0x180007f1c  test    eax, eax
0x180007f1e  jnz     loc_180007FC4
0x180007f24  mov     edx, 30F031Fh; Mask
0x180007f29  mov     ecx, 1Fh; NewValue
0x180007f2e  call    cs:__imp__controlfp
0x180007f34  mov     r12, [rsp+88h+var_28]
0x180007f39  mov     eax, edi
0x180007f3b  mov     rsi, [rsp+88h+arg_10]
0x180007f43  mov     rbx, [rsp+88h+arg_0]
0x180007f4b  mov     rbp, [rsp+88h+arg_8]
0x180007f53  add     rsp, 68h
0x180007f57  pop     r15
0x180007f59  pop     r14
0x180007f5b  pop     r13
0x180007f5d  pop     rdi
0x180007f5e  retn
0x180007f5f  mov     rcx, r12; this
0x180007f62  call    ?OnLeaveScript@COleScript@@QEAAXXZ; COleScript::OnLeaveScript(void)
0x180007f67  mov     rcx, r12; this
0x180007f6a  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180007f6f  jmp     short loc_180007F12
0x180007f71  mov     rax, [rsp+88h+arg_40]
0x180007f79  mov     r8d, r13d; unsigned int
0x180007f7c  movzx   r9d, [rsp+88h+arg_20]; unsigned __int16
0x180007f85  mov     edx, r15d; int
0x180007f88  mov     [rsp+88h+var_50], rax; struct IServiceProvider *
0x180007f8d  mov     rcx, r14; struct IDispatchEx *
0x180007f90  mov     rax, [rsp+88h+arg_38]
0x180007f98  mov     [rsp+88h+var_58], rax; struct tagEXCEPINFO *
0x180007f9d  mov     rax, [rsp+88h+arg_30]
0x180007fa5  mov     [rsp+88h+var_60], rax; struct tagVARIANT *
0x180007faa  mov     [rsp+88h+var_68], rbp; struct tagDISPPARAMS *
0x180007faf  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x180007fb4  jmp     loc_180007F01
0x180007fb9  call    cs:__imp__clearfp
0x180007fbf  jmp     loc_180007E98
0x180007fc4  call    cs:__imp__clearfp
0x180007fca  jmp     loc_180007F24
0x180007fcf  mov     eax, 8007000Eh
0x180007fd4  jmp     loc_180007F53
0x180007fd9  mov     r12, [rsp+88h+var_38]
0x180007fde  mov     rsi, [rsp+88h+var_38]
0x180007fe3  jmp     loc_180007E98
0x180007fe8  mov     rax, [rsp+88h+arg_40]
0x180007ff0  mov     r9d, r13d; unsigned int
0x180007ff3  mov     [rsp+88h+var_48], rax; struct IServiceProvider *
0x180007ff8  mov     r8d, r15d; int
0x180007ffb  mov     rax, [rsp+88h+arg_38]
0x180008003  mov     rdx, r14; struct IDispatchEx *
0x180008006  mov     [rsp+88h+var_50], rax; struct tagEXCEPINFO *
0x18000800b  mov     rax, [rsp+88h+arg_30]
0x180008013  mov     [rsp+88h+var_58], rax; struct tagVARIANT *
0x180008018  movzx   eax, [rsp+88h+arg_20]
0x180008020  mov     [rsp+88h+var_60], rbp; struct tagDISPPARAMS *
0x180008025  mov     word ptr [rsp+88h+var_68], ax; unsigned __int16
0x18000802a  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x18000802f  jmp     loc_180007F01
```
