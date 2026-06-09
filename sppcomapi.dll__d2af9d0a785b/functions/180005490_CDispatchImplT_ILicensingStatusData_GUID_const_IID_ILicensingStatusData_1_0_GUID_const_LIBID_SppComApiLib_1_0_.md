# CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180005490`
- end: `0x180005557`
- name: `?Invoke@?$CDispatchImplT@UILicensingStatusData@@$1?IID_ILicensingStatusData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180005490`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::Invoke(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v9; // rax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF

  v9 = *a1;
  v16 = 0;
  if ( (*(int (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *))(v9 + 32))(a1, 0, a4, &v16) >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v16 + 88LL))(
            v16,
            a1,
            a2,
            a5,
            a6,
            a7,
            a8,
            a9);
    v12 = v14;
    if ( v14 >= 0 )
      goto LABEL_6;
    v13 = (unsigned int)v14;
  }
  else
  {
    v12 = -2147352573;
    v13 = 2147614723LL;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_6:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v12;
}

```

## disassembly

```asm
0x180005490  mov     [rsp+arg_8], rbx
0x180005495  push    rdi
0x180005496  sub     rsp, 50h
0x18000549a  mov     rax, [rcx]
0x18000549d  mov     r8d, r9d
0x1800054a0  mov     edi, edx
0x1800054a2  mov     [rsp+58h+arg_0], 0
0x1800054ab  lea     r9, [rsp+58h+arg_0]
0x1800054b0  xor     edx, edx
0x1800054b2  mov     rbx, rcx
0x1800054b5  mov     rax, [rax+20h]
0x1800054b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054be  test    eax, eax
0x1800054c0  jns     short loc_1800054CB
0x1800054c2  mov     ebx, 80020003h
0x1800054c7  mov     ecx, ebx
0x1800054c9  jmp     short loc_180005527
0x1800054cb  mov     rdx, [rsp+58h+arg_40]
0x1800054d3  mov     r8d, edi
0x1800054d6  mov     rcx, [rsp+58h+arg_0]
0x1800054db  movzx   r9d, [rsp+58h+arg_20]
0x1800054e4  mov     [rsp+58h+var_20], rdx
0x1800054e9  mov     rdx, [rsp+58h+arg_38]
0x1800054f1  mov     rax, [rcx]
0x1800054f4  mov     [rsp+58h+var_28], rdx
0x1800054f9  mov     rdx, [rsp+58h+arg_30]
0x180005501  mov     [rsp+58h+var_30], rdx
0x180005506  mov     rdx, [rsp+58h+arg_28]
0x18000550e  mov     rax, [rax+58h]
0x180005512  mov     [rsp+58h+var_38], rdx
0x180005517  mov     rdx, rbx
0x18000551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551f  mov     ebx, eax
0x180005521  test    eax, eax
0x180005523  jns     short loc_18000552C
0x180005525  mov     ecx, eax
0x180005527  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000552c  mov     ecx, ebx
0x18000552e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180005533  mov     rcx, [rsp+58h+arg_0]
0x180005538  test    rcx, rcx
0x18000553b  jz      short loc_180005549
0x18000553d  mov     rax, [rcx]
0x180005540  mov     rax, [rax+10h]
0x180005544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005549  mov     eax, ebx
0x18000554b  mov     rbx, [rsp+58h+arg_8]
0x180005550  add     rsp, 50h
0x180005554  pop     rdi
0x180005555  retn
```
