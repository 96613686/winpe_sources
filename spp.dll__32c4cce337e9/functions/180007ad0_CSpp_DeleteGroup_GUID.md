# CSpp::DeleteGroup(_GUID)

- ea: `0x180007ad0`
- end: `0x180007ca1`
- name: `?DeleteGroup@CSpp@@UEAAJU_GUID@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180007ad0`
- `0x18000f888`
- `0x18001e2dc`
- `0x1800211a4`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d1e0`
- `0x180035b00`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180007af2`
- `ntdll!RtlGetCurrentTransaction` at `0x180007af2`
- `ntdll!RtlSetCurrentTransaction` at `0x180007afd`
- `ntdll!RtlSetCurrentTransaction` at `0x180007c81`
- `ntdll!RtlSetCurrentTransaction` at `0x180007afd`
- `ntdll!RtlSetCurrentTransaction` at `0x180007c81`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180007ba5`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180007ba5`

## string_xrefs

- `0x180007b36`: `CSpp::DeleteGroup`

## pseudocode

```c
__int64 __fastcall CSpp::DeleteGroup(CSpp *this, struct _GUID *a2)
{
  __int64 CurrentTransaction; // rbx
  __int64 v4; // r8
  __int64 v5; // rdx
  int v6; // edi
  __int16 v7; // ax
  CSpp *v8; // rcx
  struct _GUID v9; // xmm0
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  struct IVssBackupComponents *v14; // [rsp+40h] [rbp-59h] BYREF
  int v15; // [rsp+48h] [rbp-51h]
  int v16; // [rsp+50h] [rbp-49h] BYREF
  __int16 v17; // [rsp+54h] [rbp-45h]
  __int16 v18; // [rsp+56h] [rbp-43h]
  unsigned __int16 *v19[3]; // [rsp+88h] [rbp-11h] BYREF
  _OWORD v20[2]; // [rsp+A0h] [rbp+7h] BYREF

  CurrentTransaction = RtlGetCurrentTransaction(this);
  RtlSetCurrentTransaction(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, v4, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CSpp::DeleteGroup", 9981, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v14);
  v15 = 0;
  v19[0] = (unsigned __int16 *)&FileName;
  v20[1] = GUID_NULL;
  v19[1] = 0;
  if ( (unsigned int)SxIsSafeMode() || (unsigned int)SxIsWinPE() )
  {
    v6 = -2147023812;
    v7 = 9988;
    v16 = -2147023812;
LABEL_12:
    v18 = v7;
    goto LABEL_13;
  }
  v16 = 0;
  v17 = 9988;
  v6 = CreateVssBackupComponentsInternal(&v14, v5);
  v16 = v6;
  v7 = 9990;
  if ( v6 < 0 )
    goto LABEL_12;
  v17 = 9990;
  v6 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v14 + 40LL))(v14, 0);
  v16 = v6;
  v7 = 9992;
  if ( v6 < 0 )
    goto LABEL_12;
  v17 = 9992;
  v6 = CSpp::_SetSnapshotContext(v8, v14, 0);
  v16 = v6;
  v7 = 9994;
  if ( v6 < 0 )
    goto LABEL_12;
  v9 = *a2;
  v17 = 9994;
  v10 = *(_QWORD *)v14;
  v20[0] = v9;
  v6 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _OWORD *, __int64))(v10 + 312))(v14, v20, 2);
  v16 = v6;
  v7 = 9996;
  if ( v6 < 0 )
    goto LABEL_12;
  v17 = 9996;
LABEL_13:
  CBsString::_Release(v19);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16, v11, v12);
  RtlSetCurrentTransaction(CurrentTransaction);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007ad0  push    rbp
0x180007ad2  push    rbx
0x180007ad3  push    rsi
0x180007ad4  push    rdi
0x180007ad5  lea     rbp, [rsp-3Fh]
0x180007ada  sub     rsp, 0D8h
0x180007ae1  mov     rax, cs:__security_cookie
0x180007ae8  xor     rax, rsp
0x180007aeb  mov     [rbp+57h+var_30], rax
0x180007aef  mov     rsi, rdx
0x180007af2  call    cs:__imp_RtlGetCurrentTransaction
0x180007af8  xor     ecx, ecx
0x180007afa  mov     rbx, rax
0x180007afd  call    cs:__imp_RtlSetCurrentTransaction
0x180007b03  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b0a  lea     rax, WPP_GLOBAL_Control
0x180007b11  cmp     rcx, rax
0x180007b14  jz      short loc_180007B30
0x180007b16  test    dword ptr [rcx+1Ch], 20000000h
0x180007b1d  jz      short loc_180007B30
0x180007b1f  mov     rcx, [rcx+10h]
0x180007b23  mov     edx, 0ACh
0x180007b28  mov     r9, rsi
0x180007b2b  call    WPP_SF__guid_
0x180007b30  mov     r9d, 1; unsigned __int16
0x180007b36  lea     rdx, aCsppDeletegrou_0; "CSpp::DeleteGroup"
0x180007b3d  mov     r8d, 26FDh; unsigned __int16
0x180007b43  lea     rcx, [rbp+57h+var_A0]; this
0x180007b47  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180007b4c  lea     rcx, [rbp+57h+var_B0]
0x180007b50  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180007b55  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180007b5c  lea     rax, FileName
0x180007b63  mov     [rbp+57h+var_A8], 0
0x180007b6a  mov     [rbp+57h+var_68], rax
0x180007b6e  movdqu  [rbp+57h+var_40], xmm0
0x180007b73  mov     [rbp+57h+var_60], 0
0x180007b7b  call    ?SxIsSafeMode@@YAHXZ; SxIsSafeMode(void)
0x180007b80  test    eax, eax
0x180007b82  jnz     loc_180007C52
0x180007b88  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x180007b8d  test    eax, eax
0x180007b8f  jnz     loc_180007C52
0x180007b95  mov     [rbp+57h+var_A0], eax
0x180007b98  lea     rcx, [rbp+57h+var_B0]
0x180007b9c  mov     eax, 2704h
0x180007ba1  mov     [rbp+57h+var_9C], ax
0x180007ba5  call    cs:__imp_CreateVssBackupComponentsInternal
0x180007bab  mov     edi, eax
0x180007bad  mov     [rbp+57h+var_A0], eax
0x180007bb0  test    eax, eax
0x180007bb2  mov     eax, 2706h
0x180007bb7  js      loc_180007C5F
0x180007bbd  mov     rcx, [rbp+57h+var_B0]
0x180007bc1  xor     edx, edx
0x180007bc3  mov     [rbp+57h+var_9C], ax
0x180007bc7  mov     rax, [rcx]
0x180007bca  mov     rax, [rax+28h]
0x180007bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd3  mov     edi, eax
0x180007bd5  mov     [rbp+57h+var_A0], eax
0x180007bd8  test    eax, eax
0x180007bda  mov     eax, 2708h
0x180007bdf  js      short loc_180007C5F
0x180007be1  mov     rdx, [rbp+57h+var_B0]; struct IVssBackupComponents *
0x180007be5  xor     r8d, r8d; unsigned int
0x180007be8  mov     [rbp+57h+var_9C], ax
0x180007bec  call    ?_SetSnapshotContext@CSpp@@AEAAJPEAVIVssBackupComponents@@K@Z; CSpp::_SetSnapshotContext(IVssBackupComponents *,ulong)
0x180007bf1  mov     edi, eax
0x180007bf3  mov     [rbp+57h+var_A0], eax
0x180007bf6  test    eax, eax
0x180007bf8  mov     eax, 270Ah
0x180007bfd  js      short loc_180007C5F
0x180007bff  mov     rcx, [rbp+57h+var_B0]
0x180007c03  lea     rdx, [rbp+57h+var_40]
0x180007c07  movups  xmm0, xmmword ptr [rsi]
0x180007c0a  mov     [rsp+0F0h+var_C8], rdx
0x180007c0f  mov     r9d, 1
0x180007c15  mov     [rbp+57h+var_9C], ax
0x180007c19  lea     rdx, [rbp+57h+var_A8]
0x180007c1d  mov     rax, [rcx]
0x180007c20  mov     [rsp+0F0h+var_D0], rdx
0x180007c25  lea     rdx, [rbp+57h+var_50]
0x180007c29  lea     r8d, [r9+1]
0x180007c2d  movdqu  [rbp+57h+var_50], xmm0
0x180007c32  mov     rax, [rax+138h]
0x180007c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c3e  mov     edi, eax
0x180007c40  mov     [rbp+57h+var_A0], eax
0x180007c43  test    eax, eax
0x180007c45  mov     eax, 270Ch
0x180007c4a  js      short loc_180007C5F
0x180007c4c  mov     [rbp+57h+var_9C], ax
0x180007c50  jmp     short loc_180007C63
0x180007c52  mov     edi, 8007043Ch
0x180007c57  mov     eax, 2704h
0x180007c5c  mov     [rbp+57h+var_A0], edi
0x180007c5f  mov     [rbp+57h+var_9A], ax
0x180007c63  lea     rcx, [rbp+57h+var_68]; this
0x180007c67  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180007c6c  lea     rcx, [rbp+57h+var_B0]
0x180007c70  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180007c75  lea     rcx, [rbp+57h+var_A0]; this
0x180007c79  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180007c7e  mov     rcx, rbx
0x180007c81  call    cs:__imp_RtlSetCurrentTransaction
0x180007c87  mov     eax, edi
0x180007c89  mov     rcx, [rbp+57h+var_30]
0x180007c8d  xor     rcx, rsp; StackCookie
0x180007c90  call    __security_check_cookie
0x180007c95  add     rsp, 0D8h
0x180007c9c  pop     rdi
0x180007c9d  pop     rsi
0x180007c9e  pop     rbx
0x180007c9f  pop     rbp
0x180007ca0  retn
```
