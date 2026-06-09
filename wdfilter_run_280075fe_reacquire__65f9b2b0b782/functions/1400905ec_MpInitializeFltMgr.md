# MpInitializeFltMgr

- ea: `0x1400905ec`
- end: `0x1400907b8`
- name: `MpInitializeFltMgr`
- size: `460`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT Driver)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14008f314`

## callees

- `0x1400049dc`
- `0x1400051bc`
- `0x14008c1c8`
- `0x1400905ec`

## import_xrefs

- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140090799`
- `FLTMGR!FltInitExtraCreateParameterLookasideList` at `0x140090799`
- `FLTMGR!FltRegisterFilter` at `0x1400906c3`
- `FLTMGR!FltRegisterFilter` at `0x1400906c3`
- `FLTMGR!FltUnregisterFilter` at `0x140090725`
- `FLTMGR!FltUnregisterFilter` at `0x140090725`

## pseudocode

```c
__int64 __fastcall MpInitializeFltMgr(PDRIVER_OBJECT Driver, __int64 a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  struct _FLT_FILTER *v5; // rcx
  int v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 0x100) != 0 )
  {
    if ( !(unsigned int)MpQueryRegDword(Driver, a2, &v7) && v7 == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_b960013237753183ac7a6d55d666ce86_Traceguids);
      dword_140098074 &= ~8u;
    }
    FilterRegistration.OperationRegistration = (const FLT_OPERATION_REGISTRATION *)CallbacksRs3;
  }
  if ( dword_140026A14 )
  {
    FilterRegistration.TransactionNotificationCallback = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_b960013237753183ac7a6d55d666ce86_Traceguids);
  }
  v3 = FltRegisterFilter(Driver, &FilterRegistration, (PFLT_FILTER *)(MpData + 16));
  v4 = v3;
  if ( v3 >= 0 )
  {
    *(_QWORD *)(MpData + 3920) = Driver->DriverUnload;
    *(_BYTE *)(MpData + 3932) = 0;
    *(_DWORD *)(MpData + 1920) = 36;
    FltInitExtraCreateParameterLookasideList(
      *(PFLT_FILTER *)(MpData + 16),
      (PVOID)(MpData + 1984),
      0,
      *(unsigned int *)(MpData + 1920),
      0x3162504Du);
    return 0;
  }
  else
  {
    _mm_lfence();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        86,
        WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
        KeGetCurrentThread(),
        v3);
    v5 = *(struct _FLT_FILTER **)(MpData + 16);
    if ( v5 )
    {
      FltUnregisterFilter(v5);
      *(_QWORD *)(MpData + 16) = 0;
    }
    return v4;
  }
}

```

## disassembly

```asm
0x1400905ec  mov     [rsp+arg_0], rbx
0x1400905f1  mov     [rsp+arg_10], rbp
0x1400905f6  push    rdi
0x1400905f7  sub     rsp, 30h
0x1400905fb  mov     rax, cs:MpData
0x140090602  lea     rbp, WPP_GLOBAL_Control
0x140090609  mov     rdi, rcx
0x14009060c  mov     [rsp+38h+arg_8], 0
0x140090614  test    dword ptr [rax+360h], 100h
0x14009061e  jz      short loc_140090672
0x140090620  lea     r8, [rsp+38h+arg_8]
0x140090625  call    MpQueryRegDword
0x14009062a  test    eax, eax
0x14009062c  jnz     short loc_140090664
0x14009062e  cmp     [rsp+38h+arg_8], 1
0x140090633  jnz     short loc_140090664
0x140090635  mov     rcx, cs:WPP_GLOBAL_Control
0x14009063c  cmp     rcx, rbp
0x14009063f  jz      short loc_14009065D
0x140090641  mov     eax, [rcx+2Ch]
0x140090644  test    al, 2
0x140090646  jz      short loc_14009065D
0x140090648  mov     rcx, [rcx+18h]
0x14009064c  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x140090653  mov     edx, 54h ; 'T'
0x140090658  call    WPP_SF_
0x14009065d  and     cs:dword_140098074, 0FFFFFFF7h
0x140090664  lea     rax, CallbacksRs3
0x14009066b  mov     cs:FilterRegistration.OperationRegistration, rax
0x140090672  cmp     cs:dword_140026A14, 0
0x140090679  jz      short loc_1400906AE
0x14009067b  mov     cs:FilterRegistration.TransactionNotificationCallback, 0
0x140090686  mov     rcx, cs:WPP_GLOBAL_Control
0x14009068d  cmp     rcx, rbp
0x140090690  jz      short loc_1400906AE
0x140090692  mov     eax, [rcx+2Ch]
0x140090695  test    al, 2
0x140090697  jz      short loc_1400906AE
0x140090699  mov     rcx, [rcx+18h]
0x14009069d  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x1400906a4  mov     edx, 55h ; 'U'
0x1400906a9  call    WPP_SF_
0x1400906ae  mov     r8, cs:MpData
0x1400906b5  lea     rdx, FilterRegistration; Registration
0x1400906bc  add     r8, 10h; RetFilter
0x1400906c0  mov     rcx, rdi; Driver
0x1400906c3  call    cs:__imp_FltRegisterFilter
0x1400906ca  nop     dword ptr [rax+rax+00h]
0x1400906cf  mov     ebx, eax
0x1400906d1  test    eax, eax
0x1400906d3  jns     short loc_140090744
0x1400906d5  lfence
0x1400906d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400906df  cmp     rcx, rbp
0x1400906e2  jz      short loc_140090715
0x1400906e4  mov     ecx, [rcx+2Ch]
0x1400906e7  test    cl, 1
0x1400906ea  jz      short loc_140090715
0x1400906ec  mov     r9, gs:188h
0x1400906f5  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x1400906fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140090703  mov     edx, 56h ; 'V'
0x140090708  mov     [rsp+38h+Tag], eax
0x14009070c  mov     rcx, [rcx+18h]
0x140090710  call    WPP_SF_qD
0x140090715  mov     rax, cs:MpData
0x14009071c  mov     rcx, [rax+10h]; Filter
0x140090720  test    rcx, rcx
0x140090723  jz      short loc_140090740
0x140090725  call    cs:__imp_FltUnregisterFilter
0x14009072c  nop     dword ptr [rax+rax+00h]
0x140090731  mov     rax, cs:MpData
0x140090738  mov     qword ptr [rax+10h], 0
0x140090740  mov     eax, ebx
0x140090742  jmp     short loc_1400907A7
0x140090744  mov     rax, cs:MpData
0x14009074b  xor     r8d, r8d; Flags
0x14009074e  mov     rcx, [rdi+68h]
0x140090752  mov     [rsp+38h+Tag], 3162504Dh; Tag
0x14009075a  mov     [rax+0F50h], rcx
0x140090761  mov     rax, cs:MpData
0x140090768  mov     byte ptr [rax+0F5Ch], 0
0x14009076f  mov     rax, cs:MpData
0x140090776  mov     dword ptr [rax+780h], 24h ; '$'
0x140090780  mov     rcx, cs:MpData
0x140090787  mov     r9d, [rcx+780h]; Size
0x14009078e  lea     rdx, [rcx+7C0h]; Lookaside
0x140090795  mov     rcx, [rcx+10h]; Filter
0x140090799  call    cs:__imp_FltInitExtraCreateParameterLookasideList
0x1400907a0  nop     dword ptr [rax+rax+00h]
0x1400907a5  xor     eax, eax
0x1400907a7  mov     rbx, [rsp+38h+arg_0]
0x1400907ac  mov     rbp, [rsp+38h+arg_10]
0x1400907b1  add     rsp, 30h
0x1400907b5  pop     rdi
0x1400907b6  retn
```
