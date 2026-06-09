# IDispatchExInvokeEx(CSession *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180008040`
- end: `0x1800083de`
- name: `?IDispatchExInvokeEx@@YAJPEAVCSession@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(struct CSession *, struct IDispatchEx *, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800040d4`
- `0x180021540`

## callees

- `0x180003930`
- `0x18000516c`
- `0x180008040`
- `0x180008fc0`
- `0x180009020`
- `0x1800238b0`
- `0x180035468`
- `0x18003fd00`
- `0x18005bcfc`
- `0x1800663d8`
- `0x180077010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180008106`
- `msvcrt!_statusfp` at `0x18000819c`
- `msvcrt!_statusfp` at `0x180008106`
- `msvcrt!_statusfp` at `0x18000819c`
- `msvcrt!_clearfp` at `0x1800082a7`
- `msvcrt!_clearfp` at `0x1800082b2`
- `msvcrt!_clearfp` at `0x1800082a7`
- `msvcrt!_clearfp` at `0x1800082b2`
- `msvcrt!_controlfp` at `0x1800081b4`
- `msvcrt!_controlfp` at `0x1800081b4`
- `KERNEL32!TlsGetValue` at `0x1800080e0`
- `KERNEL32!TlsGetValue` at `0x1800080e0`

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
0x180008040  mov     [rsp+arg_18], r9d
0x180008045  push    rbx
0x180008046  push    rsi
0x180008047  push    rdi
0x180008048  push    r14
0x18000804a  push    r15
0x18000804c  sub     rsp, 70h
0x180008050  xor     dil, dil
0x180008053  mov     [rsp+98h+var_38], r13
0x180008058  mov     byte ptr [rsp+98h+arg_0], dil
0x180008060  mov     r14d, r9d
0x180008063  mov     r13d, r8d
0x180008066  mov     r15, rdx
0x180008069  mov     rbx, rcx
0x18000806c  test    rcx, rcx
0x18000806f  jnz     loc_180008206
0x180008075  mov     ecx, 10000h; unsigned int
0x18000807a  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18000807f  test    eax, eax
0x180008081  jz      loc_1800082BD
0x180008087  mov     rcx, [rbx+20h]
0x18000808b  mov     [rsp+98h+var_30], r12
0x180008090  mov     r12, [rsp+98h+arg_28]
0x180008098  test    rcx, rcx
0x18000809b  jz      short loc_1800080D2
0x18000809d  add     rcx, 0C8h; this
0x1800080a4  jz      short loc_1800080D2
0x1800080a6  cmp     dword ptr [rcx+4], 1
0x1800080aa  jnz     short loc_1800080D2
0x1800080ac  mov     r9, r12; struct tagDISPPARAMS *
0x1800080af  mov     [rsp+98h+var_78], rbx; struct CSession *
0x1800080b4  mov     r8d, r13d; int
0x1800080b7  mov     rdx, r15; struct IDispatch *
0x1800080ba  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x1800080bf  mov     r14d, eax
0x1800080c2  test    eax, eax
0x1800080c4  js      loc_1800081CA
0x1800080ca  mov     r14d, [rsp+98h+arg_18]
0x1800080d2  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800080d8  mov     [rsp+98h+arg_8], rbp
0x1800080e0  call    cs:__imp_TlsGetValue
0x1800080e6  mov     rdi, rax
0x1800080e9  test    rax, rax
0x1800080ec  jz      loc_1800082C8
0x1800080f2  mov     rbp, [rax+18h]
0x1800080f6  xor     eax, eax
0x1800080f8  mov     [rsp+98h+var_48], rax
0x1800080fd  test    rbp, rbp
0x180008100  jz      short loc_180008106
0x180008102  mov     [rdi+18h], rax
0x180008106  call    cs:__imp__statusfp
0x18000810c  test    eax, eax
0x18000810e  jnz     loc_1800082A7
0x180008114  cmp     dword ptr [rbx+58h], 0
0x180008118  jl      loc_18000825F
0x18000811e  test    rbp, rbp
0x180008121  jz      short loc_180008133
0x180008123  mov     rcx, [rbp+298h]; struct GL *
0x18000812a  test    rcx, rcx
0x18000812d  jnz     loc_1800082E2
0x180008133  mov     rcx, [rsp+98h+arg_40]
0x18000813b  mov     r8d, r14d
0x18000813e  mov     rax, [r15]
0x180008141  mov     edx, r13d
0x180008144  movzx   r9d, [rsp+98h+arg_20]
0x18000814d  mov     [rsp+98h+var_60], rcx
0x180008152  mov     rcx, [rsp+98h+arg_38]
0x18000815a  mov     rax, [rax+40h]
0x18000815e  mov     [rsp+98h+var_68], rcx
0x180008163  mov     rcx, [rsp+98h+arg_30]
0x18000816b  mov     [rsp+98h+var_70], rcx
0x180008170  mov     rcx, r15
0x180008173  mov     [rsp+98h+var_78], r12
0x180008178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000817d  mov     r14d, eax
0x180008180  test    rdi, rdi
0x180008183  jz      short loc_1800081BA
0x180008185  mov     r15, [rsp+98h+var_48]
0x18000818a  cmp     rbp, r15
0x18000818d  jz      short loc_180008198
0x18000818f  test    r15, r15
0x180008192  jnz     loc_18000824A
0x180008198  mov     [rdi+18h], rbp
0x18000819c  call    cs:__imp__statusfp
0x1800081a2  test    eax, eax
0x1800081a4  jnz     loc_1800082B2
0x1800081aa  mov     edx, 30F031Fh; Mask
0x1800081af  mov     ecx, 1Fh; NewValue
0x1800081b4  call    cs:__imp__controlfp
0x1800081ba  movzx   edi, byte ptr [rsp+98h+arg_0]
0x1800081c2  mov     rbp, [rsp+98h+arg_8]
0x1800081ca  mov     r12, [rsp+98h+var_30]
0x1800081cf  mov     r13, [rsp+98h+var_38]
0x1800081d4  test    rbx, rbx
0x1800081d7  jz      short loc_1800081F7
0x1800081d9  test    dil, dil
0x1800081dc  jnz     short loc_1800081F7
0x1800081de  mov     r10, [rbx+20h]
0x1800081e2  test    r10, r10
0x1800081e5  jz      short loc_1800081F7
0x1800081e7  mov     r11, [r10+388h]
0x1800081ee  test    r11, r11
0x1800081f1  jnz     loc_18000832E
0x1800081f7  mov     eax, r14d
0x1800081fa  add     rsp, 70h
0x1800081fe  pop     r15
0x180008200  pop     r14
0x180008202  pop     rdi
0x180008203  pop     rsi
0x180008204  pop     rbx
0x180008205  retn
0x180008206  mov     rax, [rcx+20h]
0x18000820a  test    rax, rax
0x18000820d  jz      loc_180008075
0x180008213  cmp     qword ptr [rax+388h], 0
0x18000821b  jz      loc_180008075
0x180008221  call    ?IsResponseDotWrite@CSession@@QEAA_NPEAUIDispatch@@J@Z; CSession::IsResponseDotWrite(IDispatch *,long)
0x180008226  mov     byte ptr [rsp+98h+arg_0], al
0x18000822d  movzx   edi, al
0x180008230  test    al, al
0x180008232  jnz     loc_180008075
0x180008238  mov     edx, 2; enum tagSCRIPTTRACEINFO
0x18000823d  mov     rcx, rbx; this
0x180008240  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x180008245  jmp     loc_180008075
0x18000824a  mov     rcx, r15; this
0x18000824d  call    ?OnLeaveScript@COleScript@@QEAAXXZ; COleScript::OnLeaveScript(void)
0x180008252  mov     rcx, r15; this
0x180008255  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x18000825a  jmp     loc_180008198
0x18000825f  mov     rax, [rsp+98h+arg_40]
0x180008267  mov     r8d, r14d; unsigned int
0x18000826a  movzx   r9d, [rsp+98h+arg_20]; unsigned __int16
0x180008273  mov     edx, r13d; int
0x180008276  mov     [rsp+98h+var_60], rax; struct IServiceProvider *
0x18000827b  mov     rcx, r15; struct IDispatchEx *
0x18000827e  mov     rax, [rsp+98h+arg_38]
0x180008286  mov     [rsp+98h+var_68], rax; struct tagEXCEPINFO *
0x18000828b  mov     rax, [rsp+98h+arg_30]
0x180008293  mov     [rsp+98h+var_70], rax; struct tagVARIANT *
0x180008298  mov     [rsp+98h+var_78], r12; struct tagDISPPARAMS *
0x18000829d  call    ?TrapIDispatchExInvokeEx@@YAJPEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; TrapIDispatchExInvokeEx(IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x1800082a2  jmp     loc_18000817D
0x1800082a7  call    cs:__imp__clearfp
0x1800082ad  jmp     loc_180008114
0x1800082b2  call    cs:__imp__clearfp
0x1800082b8  jmp     loc_1800081AA
0x1800082bd  mov     r14d, 8007000Eh
0x1800082c3  jmp     loc_1800081CF
0x1800082c8  mov     rax, [rsp+98h+arg_0]
0x1800082d0  mov     rbp, [rsp+98h+arg_0]
0x1800082d8  mov     [rsp+98h+var_48], rax
0x1800082dd  jmp     loc_180008114
0x1800082e2  mov     rax, [rsp+98h+arg_40]
0x1800082ea  mov     r9d, r14d; unsigned int
0x1800082ed  mov     [rsp+98h+var_58], rax; struct IServiceProvider *
0x1800082f2  mov     r8d, r13d; int
0x1800082f5  mov     rax, [rsp+98h+arg_38]
0x1800082fd  mov     rdx, r15; struct IDispatchEx *
0x180008300  mov     [rsp+98h+var_60], rax; struct tagEXCEPINFO *
0x180008305  mov     rax, [rsp+98h+arg_30]
0x18000830d  mov     [rsp+98h+var_68], rax; struct tagVARIANT *
0x180008312  movzx   eax, [rsp+98h+arg_20]
0x18000831a  mov     [rsp+98h+var_70], r12; struct tagDISPPARAMS *
0x18000831f  mov     word ptr [rsp+98h+var_78], ax; unsigned __int16
0x180008324  call    ?CatchIDispatchExInvokeEx@@YAJPEAVGL@@PEAUIDispatchEx@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z; CatchIDispatchExInvokeEx(GL *,IDispatchEx *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)
0x180008329  jmp     loc_18000817D
0x18000832e  mov     rdx, [rbx+48h]
0x180008332  xor     edi, edi
0x180008334  xor     ebx, ebx
0x180008336  xor     r9d, r9d
0x180008339  test    rdx, rdx
0x18000833c  jz      short loc_18000839E
0x18000833e  cmp     [rdx+1D0h], rbx
0x180008345  jz      short loc_18000839E
0x180008347  mov     rcx, [rdx+28h]; this
0x18000834b  test    rcx, rcx
0x18000834e  jz      short loc_18000839E
0x180008350  mov     rax, [rcx]
0x180008353  test    rax, rax
0x180008356  jz      short loc_18000839E
0x180008358  mov     rsi, [rax+40h]
0x18000835c  mov     r15, [rax+48h]
0x180008360  movsxd  r8, dword ptr [rsi]
0x180008363  add     r15, r8
0x180008366  jz      short loc_18000839E
0x180008368  cmp     dword ptr [rsi+4], 20h ; ' '
0x18000836c  jnz     short loc_18000839E
0x18000836e  mov     edx, [rdx+1E8h]; int
0x180008374  lea     r8, [rsp+98h+arg_0]; struct BOS *
0x18000837c  mov     [rsp+98h+arg_0], rbx
0x180008384  call    ?GetBos@FncInfo@@QEAAXJPEAUBOS@@@Z; FncInfo::GetBos(long,BOS *)
0x180008389  mov     edi, dword ptr [rsp+98h+arg_0+4]
0x180008390  mov     r9d, dword ptr [rsp+98h+arg_0]
0x180008398  add     edi, r9d
0x18000839b  mov     ebx, [r15]
0x18000839e  mov     rdx, [r11]
0x1800083a1  lea     r8, [rsp+98h+var_48]
0x1800083a6  movups  xmm0, xmmword ptr [r10+390h]
0x1800083ae  mov     [rsp+98h+var_68], 0
0x1800083b7  mov     rcx, r11
0x1800083ba  mov     dword ptr [rsp+98h+var_70], edi
0x1800083be  mov     rax, [rdx+18h]
0x1800083c2  mov     edx, 3
0x1800083c7  mov     dword ptr [rsp+98h+var_78], r9d
0x1800083cc  mov     r9d, ebx
0x1800083cf  movaps  xmmword ptr [rsp+98h+var_48], xmm0
0x1800083d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d9  jmp     loc_1800081F7
```
