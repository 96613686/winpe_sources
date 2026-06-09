# IDispatchInvoke2(CSession *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180008cc0`
- end: `0x180008fba`
- name: `?IDispatchInvoke2@@YAJPEAVCSession@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `762`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, struct IDispatch *@<rdx>, int@<r8d>, const struct _GUID *@<r9>, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180006550`

## callees

- `0x180004638`
- `0x180008cc0`
- `0x180008fc0`
- `0x180009020`
- `0x180022e04`
- `0x1800238b0`
- `0x18005bda8`
- `0x1800665f0`
- `0x18007552c`
- `0x180077010`

## import_xrefs

- `msvcrt!_statusfp` at `0x180008d3f`
- `msvcrt!_statusfp` at `0x180008dd4`
- `msvcrt!_statusfp` at `0x180008d3f`
- `msvcrt!_statusfp` at `0x180008dd4`
- `msvcrt!_clearfp` at `0x180008f34`
- `msvcrt!_clearfp` at `0x180008f3f`
- `msvcrt!_clearfp` at `0x180008f34`
- `msvcrt!_clearfp` at `0x180008f3f`
- `msvcrt!_controlfp` at `0x180008dec`
- `msvcrt!_controlfp` at `0x180008dec`
- `KERNEL32!TlsGetValue` at `0x180008d1e`
- `KERNEL32!TlsGetValue` at `0x180008d1e`
- `KERNEL32!GetCurrentThreadId` at `0x180008ed0`
- `KERNEL32!GetCurrentThreadId` at `0x180008ed0`
- `KERNEL32!LeaveCriticalSection` at `0x180008f21`
- `KERNEL32!LeaveCriticalSection` at `0x180008f21`

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
0x180008cc0  mov     [rsp+arg_18], r9
0x180008cc5  push    rdi
0x180008cc6  push    r12
0x180008cc8  push    r15
0x180008cca  sub     rsp, 60h
0x180008cce  mov     rdi, rcx
0x180008cd1  mov     r12d, r8d
0x180008cd4  mov     ecx, 10000h; unsigned int
0x180008cd9  mov     r15, rdx
0x180008cdc  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180008ce1  test    eax, eax
0x180008ce3  jz      loc_180008F9B
0x180008ce9  mov     rax, [rdi+20h]
0x180008ced  mov     [rsp+78h+arg_0], rbx
0x180008cf5  mov     [rsp+78h+var_28], r14
0x180008cfa  mov     r14, [rsp+78h+arg_30]
0x180008d02  test    rax, rax
0x180008d05  jnz     loc_180008E19
0x180008d0b  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180008d11  mov     [rsp+78h+arg_8], rbp
0x180008d19  mov     [rsp+78h+var_20], rsi
0x180008d1e  call    cs:__imp_TlsGetValue
0x180008d24  mov     rbx, rax
0x180008d27  test    rax, rax
0x180008d2a  jz      loc_180008FA5
0x180008d30  mov     rsi, [rax+18h]
0x180008d34  xor     ebp, ebp
0x180008d36  test    rsi, rsi
0x180008d39  jz      short loc_180008D3F
0x180008d3b  mov     [rax+18h], rbp
0x180008d3f  call    cs:__imp__statusfp
0x180008d45  test    eax, eax
0x180008d47  jnz     loc_180008F34
0x180008d4d  cmp     dword ptr [rdi+58h], 0
0x180008d51  jl      loc_180008F4A
0x180008d57  test    rsi, rsi
0x180008d5a  jnz     loc_180008E66
0x180008d60  mov     rcx, [rsp+78h+arg_48]
0x180008d68  lea     r8, GUID_NULL
0x180008d6f  mov     rax, [r15]
0x180008d72  mov     edx, r12d
0x180008d75  mov     r9d, [rsp+78h+arg_20]
0x180008d7d  mov     [rsp+78h+var_38], rcx
0x180008d82  mov     rcx, [rsp+78h+arg_40]
0x180008d8a  mov     rax, [rax+30h]
0x180008d8e  mov     [rsp+78h+var_40], rcx
0x180008d93  mov     rcx, [rsp+78h+arg_38]
0x180008d9b  mov     [rsp+78h+var_48], rcx
0x180008da0  movzx   ecx, [rsp+78h+arg_28]
0x180008da8  mov     [rsp+78h+var_50], r14
0x180008dad  mov     word ptr [rsp+78h+var_58], cx
0x180008db2  mov     rcx, r15
0x180008db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dba  mov     r14d, eax
0x180008dbd  test    rbx, rbx
0x180008dc0  jz      short loc_180008DF2
0x180008dc2  cmp     rsi, rbp
0x180008dc5  jz      short loc_180008DD0
0x180008dc7  test    rbp, rbp
0x180008dca  jnz     loc_180008ECA
0x180008dd0  mov     [rbx+18h], rsi
0x180008dd4  call    cs:__imp__statusfp
0x180008dda  test    eax, eax
0x180008ddc  jnz     loc_180008F3F
0x180008de2  mov     edx, 30F031Fh; Mask
0x180008de7  mov     ecx, 1Fh; NewValue
0x180008dec  call    cs:__imp__controlfp
0x180008df2  mov     rsi, [rsp+78h+var_20]
0x180008df7  mov     eax, r14d
0x180008dfa  mov     rbp, [rsp+78h+arg_8]
0x180008e02  mov     rbx, [rsp+78h+arg_0]
0x180008e0a  mov     r14, [rsp+78h+var_28]
0x180008e0f  add     rsp, 60h
0x180008e13  pop     r15
0x180008e15  pop     r12
0x180008e17  pop     rdi
0x180008e18  retn
0x180008e19  lea     rcx, [rax+0C8h]; this
0x180008e20  test    rcx, rcx
0x180008e23  jz      loc_180008D0B
0x180008e29  cmp     dword ptr [rcx+4], 1
0x180008e2d  jnz     loc_180008D0B
0x180008e33  mov     r9, r14; struct tagDISPPARAMS *
0x180008e36  mov     [rsp+78h+var_58], rdi; struct CSession *
0x180008e3b  mov     r8d, r12d; int
0x180008e3e  mov     rdx, r15; struct IDispatch *
0x180008e41  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x180008e46  mov     ebx, eax
0x180008e48  test    eax, eax
0x180008e4a  jns     loc_180008D0B
0x180008e50  mov     edx, eax; int
0x180008e52  mov     rcx, rdi; this
0x180008e55  call    ?ReportError@CSession@@QEAAJJ@Z; CSession::ReportError(long)
0x180008e5a  mov     rcx, rdi
0x180008e5d  call    VBScriptClass_Report_Unexpected_Fatal_Error
0x180008e62  mov     eax, ebx
0x180008e64  jmp     short loc_180008E02
0x180008e66  mov     rcx, [rsi+298h]; struct GL *
0x180008e6d  test    rcx, rcx
0x180008e70  jz      loc_180008D60
0x180008e76  mov     rax, [rsp+78h+arg_48]
0x180008e7e  mov     r8d, r12d; int
0x180008e81  mov     [rsp+78h+var_30], rax; unsigned int *
0x180008e86  mov     rdx, r15; struct IDispatch *
0x180008e89  mov     rax, [rsp+78h+arg_40]
0x180008e91  mov     [rsp+78h+var_38], rax; struct tagEXCEPINFO *
0x180008e96  mov     rax, [rsp+78h+arg_38]
0x180008e9e  mov     [rsp+78h+var_40], rax; struct tagVARIANT *
0x180008ea3  movzx   eax, [rsp+78h+arg_28]
0x180008eab  mov     [rsp+78h+var_48], r14; struct tagDISPPARAMS *
0x180008eb0  mov     word ptr [rsp+78h+var_50], ax; unsigned __int16
0x180008eb5  mov     eax, [rsp+78h+arg_20]
0x180008ebc  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180008ec0  call    ?CatchIDispatchInvoke@@YAJPEAVGL@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; CatchIDispatchInvoke(GL *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180008ec5  jmp     loc_180008DBA
0x180008eca  mov     edi, [rbp+0F4h]
0x180008ed0  call    cs:__imp_GetCurrentThreadId
0x180008ed6  cmp     eax, edi
0x180008ed8  jnz     short loc_180008F27
0x180008eda  mov     rcx, [rbp+0A0h]
0x180008ee1  test    rcx, rcx
0x180008ee4  jz      short loc_180008EF2
0x180008ee6  mov     rax, [rcx]
0x180008ee9  mov     rax, [rax+50h]
0x180008eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef2  mov     rcx, rbp; this
0x180008ef5  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x180008efa  test    eax, eax
0x180008efc  jz      short loc_180008F27
0x180008efe  add     dword ptr [rbp+110h], 0FFFFFFFFh
0x180008f05  jnz     short loc_180008F11
0x180008f07  mov     dword ptr [rbp+10Ch], 0
0x180008f11  cmp     dword ptr [rbp+210h], 0
0x180008f18  jz      short loc_180008F27
0x180008f1a  lea     rcx, [rbp+218h]; lpCriticalSection
0x180008f21  call    cs:__imp_LeaveCriticalSection
0x180008f27  mov     rcx, rbp; this
0x180008f2a  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180008f2f  jmp     loc_180008DD0
0x180008f34  call    cs:__imp__clearfp
0x180008f3a  jmp     loc_180008D4D
0x180008f3f  call    cs:__imp__clearfp
0x180008f45  jmp     loc_180008DE2
0x180008f4a  mov     rax, [rsp+78h+arg_48]
0x180008f52  mov     edx, r12d; int
0x180008f55  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x180008f5d  mov     rcx, r15; struct IDispatch *
0x180008f60  mov     [rsp+78h+var_38], rax; unsigned int *
0x180008f65  mov     rax, [rsp+78h+arg_40]
0x180008f6d  mov     [rsp+78h+var_40], rax; struct tagEXCEPINFO *
0x180008f72  mov     rax, [rsp+78h+arg_38]
0x180008f7a  mov     [rsp+78h+var_48], rax; struct tagVARIANT *
0x180008f7f  movzx   eax, [rsp+78h+arg_28]
0x180008f87  mov     [rsp+78h+var_50], r14; struct tagDISPPARAMS *
0x180008f8c  mov     word ptr [rsp+78h+var_58], ax; unsigned __int16
0x180008f91  call    ?TrapIDispatchInvoke@@YAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; TrapIDispatchInvoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x180008f96  jmp     loc_180008DBA
0x180008f9b  mov     eax, 8007000Eh
0x180008fa0  jmp     loc_180008E0F
0x180008fa5  mov     rsi, [rsp+78h+arg_18]
0x180008fad  mov     rbp, [rsp+78h+arg_18]
0x180008fb5  jmp     loc_180008D4D
```
