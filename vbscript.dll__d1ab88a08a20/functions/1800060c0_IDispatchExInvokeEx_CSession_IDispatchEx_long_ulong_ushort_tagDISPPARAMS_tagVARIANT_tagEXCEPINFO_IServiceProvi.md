# IDispatchExInvokeEx(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x1800060c0`
- end: `0x180006483`
- name: `?IDispatchExInvokeEx@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(struct CSession *, struct IDispatchEx *, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001cb70`
- `0x1800252c0`

## callees

- `0x1800060c0`
- `0x1800070c0`
- `0x180007130`
- `0x18001c3c8`
- `0x18001ecc0`
- `0x180025cf0`
- `0x180036970`
- `0x1800413d8`
- `0x18005d884`
- `0x1800682b8`
- `0x18007a010`

## import_xrefs

- `msvcrt!_statusfp` at `0x18000618c`
- `msvcrt!_statusfp` at `0x180006228`
- `msvcrt!_statusfp` at `0x18000618c`
- `msvcrt!_statusfp` at `0x180006228`
- `msvcrt!_clearfp` at `0x180006340`
- `msvcrt!_clearfp` at `0x180006351`
- `msvcrt!_clearfp` at `0x180006340`
- `msvcrt!_clearfp` at `0x180006351`
- `msvcrt!_controlfp` at `0x180006246`
- `msvcrt!_controlfp` at `0x180006246`
- `KERNEL32!TlsGetValue` at `0x180006160`
- `KERNEL32!TlsGetValue` at `0x180006160`

## pseudocode

```c
__int64 __fastcall IDispatchExInvokeEx(
        struct CSession *a1,
        struct IDispatch *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        struct IServiceProvider *a9)
{
  char v9; // di
  unsigned int v10; // r14d
  __int64 v14; // rcx
  struct tagDISPPARAMS *v15; // r12
  JAmsi *v16; // rcx
  int v17; // r14d
  _QWORD *Value; // rax
  _QWORD *v19; // rdi
  COleScript *v20; // rbp
  struct GL *v21; // rcx
  int v22; // eax
  __int64 v23; // r10
  __int64 v24; // r11
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // edi
  unsigned int v29; // ebx
  int v30; // r9d
  FncInfo *v31; // rcx
  __int64 v32; // rax
  int *v33; // rsi
  unsigned int *v34; // r15
  int v35; // edx
  void (__fastcall *v36)(__int64, __int64, COleScript **, _QWORD, int, int, _QWORD); // rax
  COleScript *v37[2]; // [rsp+50h] [rbp-48h] BYREF
  COleScript *v38; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v39; // [rsp+B8h] [rbp+20h]

  v39 = a4;
  v9 = 0;
  LOBYTE(v38) = 0;
  v10 = a4;
  if ( a1 )
  {
    v26 = *((_QWORD *)a1 + 4);
    if ( v26 )
    {
      if ( *(_QWORD *)(v26 + 904) )
      {
        LOBYTE(v38) = CSession::IsResponseDotWrite(a1, a2, a3);
        v9 = (char)v38;
        if ( !(_BYTE)v38 )
          CSession::SendRuntimeScriptInfoToHost(a1, SCRIPTTRACEINFO_COMCALLSTART);
      }
    }
  }
  if ( !(unsigned int)FStackAvailable(0x10000u) )
  {
    v17 = -2147024882;
    goto LABEL_25;
  }
  v14 = *((_QWORD *)a1 + 4);
  v15 = a6;
  if ( v14 )
  {
    v16 = (JAmsi *)(v14 + 200);
    if ( v16 )
    {
      if ( *((_DWORD *)v16 + 1) == 1 )
      {
        v17 = JAmsi::JAmsiProcessor(v16, a2, a3, a6, a1);
        if ( v17 < 0 )
          goto LABEL_25;
        v10 = v39;
      }
    }
  }
  Value = TlsGetValue(g_luTls);
  v19 = Value;
  if ( Value )
  {
    v20 = (COleScript *)Value[3];
    v37[0] = 0;
    if ( v20 )
      Value[3] = 0;
    if ( _statusfp() )
      _clearfp();
  }
  else
  {
    v20 = v38;
    v37[0] = v38;
  }
  if ( *((int *)a1 + 22) < 0 )
  {
    v22 = TrapIDispatchExInvokeEx((struct IDispatchEx *)a2, a3, v10, a5, v15, a7, a8, a9);
  }
  else if ( v20 && (v21 = (struct GL *)*((_QWORD *)v20 + 83)) != 0 )
  {
    v22 = CatchIDispatchExInvokeEx(v21, (struct IDispatchEx *)a2, a3, v10, a5, v15, a7, a8, a9);
  }
  else
  {
    v22 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *))a2->lpVtbl[1].AddRef)(
            a2,
            a3,
            v10,
            a5,
            v15,
            a7,
            a8,
            a9);
  }
  v17 = v22;
  if ( v19 )
  {
    if ( v20 != v37[0] && v37[0] )
    {
      COleScript::OnLeaveScript(v37[0]);
      COleScript::Release(v37[0]);
    }
    v19[3] = v20;
    if ( _statusfp() )
      _clearfp();
    _controlfp(0x1Fu, 0x30F031Fu);
  }
  v9 = (char)v38;
LABEL_25:
  if ( a1 )
  {
    if ( !v9 )
    {
      v23 = *((_QWORD *)a1 + 4);
      if ( v23 )
      {
        v24 = *(_QWORD *)(v23 + 904);
        if ( v24 )
        {
          v27 = *((_QWORD *)a1 + 9);
          v28 = 0;
          v29 = 0;
          v30 = 0;
          if ( v27 )
          {
            if ( *(_QWORD *)(v27 + 464) )
            {
              v31 = *(FncInfo **)(v27 + 40);
              if ( v31 )
              {
                v32 = *(_QWORD *)v31;
                if ( *(_QWORD *)v31 )
                {
                  v33 = *(int **)(v32 + 64);
                  v34 = (unsigned int *)(*v33 + *(_QWORD *)(v32 + 72));
                  if ( v34 )
                  {
                    if ( v33[1] == 32 )
                    {
                      v35 = *(_DWORD *)(v27 + 488);
                      v38 = 0;
                      FncInfo::GetBos(v31, v35, (struct BOS *)&v38);
                      v30 = (int)v38;
                      v28 = (_DWORD)v38 + HIDWORD(v38);
                      v29 = *v34;
                    }
                  }
                }
              }
            }
          }
          v36 = *(void (__fastcall **)(__int64, __int64, COleScript **, _QWORD, int, int, _QWORD))(*(_QWORD *)v24 + 24LL);
          *(_OWORD *)v37 = *(_OWORD *)(v23 + 912);
          v36(v24, 3, v37, v29, v30, v28, 0);
        }
      }
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800060c0  mov     [rsp+arg_18], r9d
0x1800060c5  push    rbx
0x1800060c6  push    rsi
0x1800060c7  push    rdi
0x1800060c8  push    r14
0x1800060ca  push    r15
0x1800060cc  sub     rsp, 70h
0x1800060d0  xor     dil, dil
0x1800060d3  mov     [rsp+98h+var_38], r13
0x1800060d8  mov     byte ptr [rsp+98h+arg_0], dil
0x1800060e0  mov     r14d, r9d
0x1800060e3  mov     r13d, r8d
0x1800060e6  mov     r15, rdx
0x1800060e9  mov     rbx, rcx
0x1800060ec  test    rcx, rcx
0x1800060ef  jnz     loc_18000629F
0x1800060f5  mov     ecx, 10000h; unsigned int
0x1800060fa  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x1800060ff  test    eax, eax
0x180006101  jz      loc_180006362
0x180006107  mov     rcx, [rbx+20h]
0x18000610b  mov     [rsp+98h+var_30], r12
0x180006110  mov     r12, [rsp+98h+arg_28]
0x180006118  test    rcx, rcx
0x18000611b  jz      short loc_180006152
0x18000611d  add     rcx, 0C8h; this
0x180006124  jz      short loc_180006152
0x180006126  cmp     dword ptr [rcx+4], 1
0x18000612a  jnz     short loc_180006152
0x18000612c  mov     r9, r12; struct tagDISPPARAMS *
0x18000612f  mov     [rsp+98h+var_78], rbx; struct CSession *
0x180006134  mov     r8d, r13d; int
0x180006137  mov     rdx, r15; struct IDispatch *
0x18000613a  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x18000613f  mov     r14d, eax
0x180006142  test    eax, eax
0x180006144  js      loc_180006262
0x18000614a  mov     r14d, [rsp+98h+arg_18]
0x180006152  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180006158  mov     [rsp+98h+arg_8], rbp
0x180006160  call    cs:__imp_TlsGetValue
0x180006167  nop     dword ptr [rax+rax+00h]
0x18000616c  mov     rdi, rax
0x18000616f  test    rax, rax
0x180006172  jz      loc_18000636D
0x180006178  mov     rbp, [rax+18h]
0x18000617c  xor     eax, eax
0x18000617e  mov     [rsp+98h+var_48], rax
0x180006183  test    rbp, rbp
0x180006186  jz      short loc_18000618C
0x180006188  mov     [rdi+18h], rax
0x18000618c  call    cs:__imp__statusfp
0x180006193  nop     dword ptr [rax+rax+00h]
0x180006198  test    eax, eax
0x18000619a  jnz     loc_180006340
0x1800061a0  cmp     dword ptr [rbx+58h], 0
0x1800061a4  jl      loc_1800062F8
0x1800061aa  test    rbp, rbp
0x1800061ad  jz      short loc_1800061BF
0x1800061af  mov     rcx, [rbp+298h]; struct GL *
0x1800061b6  test    rcx, rcx
0x1800061b9  jnz     loc_180006387
0x1800061bf  mov     rcx, [rsp+98h+arg_40]
0x1800061c7  mov     r8d, r14d
0x1800061ca  mov     rax, [r15]
0x1800061cd  mov     edx, r13d
0x1800061d0  movzx   r9d, [rsp+98h+arg_20]
0x1800061d9  mov     [rsp+98h+var_60], rcx
0x1800061de  mov     rcx, [rsp+98h+arg_38]
0x1800061e6  mov     rax, [rax+40h]
0x1800061ea  mov     [rsp+98h+var_68], rcx
0x1800061ef  mov     rcx, [rsp+98h+arg_30]
0x1800061f7  mov     [rsp+98h+var_70], rcx
0x1800061fc  mov     rcx, r15
0x1800061ff  mov     [rsp+98h+var_78], r12
0x180006204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006209  mov     r14d, eax
0x18000620c  test    rdi, rdi
0x18000620f  jz      short loc_180006252
0x180006211  mov     r15, [rsp+98h+var_48]
0x180006216  cmp     rbp, r15
0x180006219  jz      short loc_180006224
0x18000621b  test    r15, r15
0x18000621e  jnz     loc_1800062E3
0x180006224  mov     [rdi+18h], rbp
0x180006228  call    cs:__imp__statusfp
0x18000622f  nop     dword ptr [rax+rax+00h]
0x180006234  test    eax, eax
0x180006236  jnz     loc_180006351
0x18000623c  mov     edx, 30F031Fh; Mask
0x180006241  mov     ecx, 1Fh; NewValue
0x180006246  call    cs:__imp__controlfp
0x18000624d  nop     dword ptr [rax+rax+00h]
0x180006252  movzx   edi, byte ptr [rsp+98h+arg_0]
0x18000625a  mov     rbp, [rsp+98h+arg_8]
0x180006262  mov     r12, [rsp+98h+var_30]
0x180006267  mov     r13, [rsp+98h+var_38]
0x18000626c  test    rbx, rbx
0x18000626f  jz      short loc_18000628F
0x180006271  test    dil, dil
0x180006274  jnz     short loc_18000628F
0x180006276  mov     r10, [rbx+20h]
0x18000627a  test    r10, r10
0x18000627d  jz      short loc_18000628F
0x18000627f  mov     r11, [r10+388h]
0x180006286  test    r11, r11
0x180006289  jnz     loc_1800063D3
0x18000628f  mov     eax, r14d
0x180006292  add     rsp, 70h
0x180006296  pop     r15
0x180006298  pop     r14
0x18000629a  pop     rdi
0x18000629b  pop     rsi
0x18000629c  pop     rbx
0x18000629d  retn
0x18000629f  mov     rax, [rcx+20h]
0x1800062a3  test    rax, rax
0x1800062a6  jz      loc_1800060F5
0x1800062ac  cmp     qword ptr [rax+388h], 0
0x1800062b4  jz      loc_1800060F5
0x1800062ba  call    ?IsResponseDotWrite@CSession@@QEAA_NPEAUIDispatch@@J@Z; CSession::IsResponseDotWrite(IDispatch *,long)
0x1800062bf  mov     byte ptr [rsp+98h+arg_0], al
0x1800062c6  movzx   edi, al
0x1800062c9  test    al, al
0x1800062cb  jnz     loc_1800060F5
0x1800062d1  mov     edx, 2; enum tagSCRIPTTRACEINFO
0x1800062d6  mov     rcx, rbx; this
0x1800062d9  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x1800062de  jmp     loc_1800060F5
0x1800062e3  mov     rcx, r15; this
0x1800062e6  call    ?OnLeaveScript@COleScript@@QEAAXXZ; COleScript::OnLeaveScript(void)
0x1800062eb  mov     rcx, r15; this
0x1800062ee  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x1800062f3  jmp     loc_180006224
0x1800062f8  mov     rax, [rsp+98h+arg_40]
0x180006300  mov     r8d, r14d; unsigned int
0x180006303  movzx   r9d, [rsp+98h+arg_20]; unsigned __int16
0x18000630c  mov     edx, r13d; int
0x18000630f  mov     [rsp+98h+var_60], rax; struct IServiceProvider *
0x180006314  mov     rcx, r15; struct IDispatchEx *
0x180006317  mov     rax, [rsp+98h+arg_38]
0x18000631f  mov     [rsp+98h+var_68], rax; struct tagEXCEPINFO *
0x180006324  mov     rax, [rsp+98h+arg_30]
0x18000632c  mov     [rsp+98h+var_70], rax; struct tagVARIANT *
0x180006331  mov     [rsp+98h+var_78], r12; struct tagDISPPARAMS *
0x180006336  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x18000633b  jmp     loc_180006209
0x180006340  call    cs:__imp__clearfp
0x180006347  nop     dword ptr [rax+rax+00h]
0x18000634c  jmp     loc_1800061A0
0x180006351  call    cs:__imp__clearfp
0x180006358  nop     dword ptr [rax+rax+00h]
0x18000635d  jmp     loc_18000623C
0x180006362  mov     r14d, 8007000Eh
0x180006368  jmp     loc_180006267
0x18000636d  mov     rax, [rsp+98h+arg_0]
0x180006375  mov     rbp, [rsp+98h+arg_0]
0x18000637d  mov     [rsp+98h+var_48], rax
0x180006382  jmp     loc_1800061A0
0x180006387  mov     rax, [rsp+98h+arg_40]
0x18000638f  mov     r9d, r14d; unsigned int
0x180006392  mov     [rsp+98h+var_58], rax; struct IServiceProvider *
0x180006397  mov     r8d, r13d; int
0x18000639a  mov     rax, [rsp+98h+arg_38]
0x1800063a2  mov     rdx, r15; struct IDispatchEx *
0x1800063a5  mov     [rsp+98h+var_60], rax; struct tagEXCEPINFO *
0x1800063aa  mov     rax, [rsp+98h+arg_30]
0x1800063b2  mov     [rsp+98h+var_68], rax; struct tagVARIANT *
0x1800063b7  movzx   eax, [rsp+98h+arg_20]
0x1800063bf  mov     [rsp+98h+var_70], r12; struct tagDISPPARAMS *
0x1800063c4  mov     word ptr [rsp+98h+var_78], ax; unsigned __int16
0x1800063c9  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x1800063ce  jmp     loc_180006209
0x1800063d3  mov     rdx, [rbx+48h]
0x1800063d7  xor     edi, edi
0x1800063d9  xor     ebx, ebx
0x1800063db  xor     r9d, r9d
0x1800063de  test    rdx, rdx
0x1800063e1  jz      short loc_180006443
0x1800063e3  cmp     [rdx+1D0h], rbx
0x1800063ea  jz      short loc_180006443
0x1800063ec  mov     rcx, [rdx+28h]; this
0x1800063f0  test    rcx, rcx
0x1800063f3  jz      short loc_180006443
0x1800063f5  mov     rax, [rcx]
0x1800063f8  test    rax, rax
0x1800063fb  jz      short loc_180006443
0x1800063fd  mov     rsi, [rax+40h]
0x180006401  mov     r15, [rax+48h]
0x180006405  movsxd  r8, dword ptr [rsi]
0x180006408  add     r15, r8
0x18000640b  jz      short loc_180006443
0x18000640d  cmp     dword ptr [rsi+4], 20h ; ' '
0x180006411  jnz     short loc_180006443
0x180006413  mov     edx, [rdx+1E8h]; int
0x180006419  lea     r8, [rsp+98h+arg_0]; struct BOS *
0x180006421  mov     [rsp+98h+arg_0], rbx
0x180006429  call    ?GetBos@FncInfo@@QEAAXJPEAUBOS@@@Z; FncInfo::GetBos(long,BOS *)
0x18000642e  mov     edi, dword ptr [rsp+98h+arg_0+4]
0x180006435  mov     r9d, dword ptr [rsp+98h+arg_0]
0x18000643d  add     edi, r9d
0x180006440  mov     ebx, [r15]
0x180006443  mov     rdx, [r11]
0x180006446  lea     r8, [rsp+98h+var_48]
0x18000644b  movups  xmm0, xmmword ptr [r10+390h]
0x180006453  mov     [rsp+98h+var_68], 0
0x18000645c  mov     rcx, r11
0x18000645f  mov     dword ptr [rsp+98h+var_70], edi
0x180006463  mov     rax, [rdx+18h]
0x180006467  mov     edx, 3
0x18000646c  mov     dword ptr [rsp+98h+var_78], r9d
0x180006471  mov     r9d, ebx
0x180006474  movaps  xmmword ptr [rsp+98h+var_48], xmm0
0x180006479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647e  jmp     loc_18000628F
```
