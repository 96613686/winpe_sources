# MpDlpQueryEaByName

- ea: `0x140086418`
- end: `0x14008689e`
- name: `MpDlpQueryEaByName`
- size: `1158`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400408b0`

## callees

- `0x1400018a4`
- `0x140004da8`
- `0x1400118d0`
- `0x140043190`
- `0x14005e390`
- `0x140086418`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400867fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400867fe`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400867d7`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400867d7`
- `ntoskrnl!KeBugCheck` at `0x14008683b`
- `ntoskrnl!KeBugCheck` at `0x14008683b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400867a7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400867a7`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140086826`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x140086826`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140086504`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x140086504`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400865ee`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x1400865ee`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14008660f`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14008660f`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140086710`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140086710`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140086593`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x140086593`
- `FLTMGR!FltClose` at `0x140086792`
- `FLTMGR!FltClose` at `0x140086792`
- `FLTMGR!FltObjectDereference` at `0x140086779`
- `FLTMGR!FltObjectDereference` at `0x140086779`

## pseudocode

```c
__int64 __fastcall MpDlpQueryEaByName(__int64 a1, __int64 a2, _BYTE *a3)
{
  NTSTATUS Parameter; // ebx
  __int64 v6; // rdx
  __int64 *v7; // rax
  _DWORD *v8; // rcx
  _QWORD *v9; // rcx
  _DWORD *v10; // rax
  int v12; // [rsp+38h] [rbp-C8h]
  int v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+60h] [rbp-A0h]
  int v16; // [rsp+68h] [rbp-98h]
  PVOID EcpContext; // [rsp+80h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp-78h] BYREF
  PVOID FltObject; // [rsp+90h] [rbp-70h] BYREF
  PVOID Object; // [rsp+98h] [rbp-68h] BYREF
  HANDLE FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v22; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v23; // [rsp+B8h] [rbp-48h]
  __int64 v24[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v25; // [rsp+D8h] [rbp-28h]
  __int64 v26; // [rsp+E8h] [rbp-18h]
  __int64 v27; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int64 v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+10Ch] [rbp+Ch]
  __int128 v32; // [rsp+110h] [rbp+10h]
  __int64 v33[2]; // [rsp+120h] [rbp+20h] BYREF

  EcpContext = 0;
  HIDWORD(v27) = 0;
  v31 = 0;
  EcpList = 0;
  LOWORD(v26) = 0;
  *(_QWORD *)&v23 = 0;
  WORD4(v23) = 0;
  Object = 0;
  FileHandle = 0;
  *(_OWORD *)v33 = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( a1 && a2 && a3 )
  {
    *a3 = 0;
    *(_DWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 )
    {
      v26 = 1;
      *(_OWORD *)v24 = 0;
      LOWORD(v24[0]) = 40;
      v25 = 0;
    }
    else
    {
      v22 = 0;
      LOWORD(v22) = 32;
      v23 = 0;
    }
    v29 = a1;
    LODWORD(v27) = 48;
    v28 = 0;
    v30 = 576;
    v32 = 0;
    Parameter = FltAllocateExtraCreateParameterList(*(PFLT_FILTER *)(MpData + 16), 0, &EcpList);
    if ( Parameter >= 0 )
    {
      Parameter = FltAllocateExtraCreateParameterFromLookasideList(
                    *(PFLT_FILTER *)(MpData + 16),
                    &GUID_MP_ECP_QUERY_EA,
                    0x10u,
                    0,
                    0,
                    (PVOID)(MpData + 1984),
                    &EcpContext);
      if ( Parameter >= 0 )
      {
        *(_OWORD *)EcpContext = 0;
        Parameter = FltInsertExtraCreateParameter(*(PFLT_FILTER *)(MpData + 16), EcpList, EcpContext);
        if ( Parameter >= 0 )
        {
          if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 )
            v24[1] = (__int64)EcpList;
          else
            *((_QWORD *)&v22 + 1) = EcpList;
          v7 = (__int64 *)&v22;
          if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 )
            v7 = v24;
          Parameter = MpFltCreateFileEx2(
                        *(_QWORD *)(MpData + 16),
                        0,
                        (int)&FileHandle,
                        (int)&Object,
                        0x80u,
                        (__int64)&v27,
                        (__int64)v33,
                        v12,
                        v13,
                        7u,
                        v14,
                        0,
                        v15,
                        v16,
                        0,
                        (__int64)v7);
          if ( Parameter >= 0 )
          {
            if ( (*(_DWORD *)(MpData + 864) & 0x800) != 0 && *(_QWORD *)(MpData + 96) && *(_QWORD *)(MpData + 88) )
            {
              if ( FltIsEcpAcknowledged(*(PFLT_FILTER *)(MpData + 16), EcpContext) )
              {
                v8 = EcpContext;
                *(_DWORD *)a2 = *((_DWORD *)EcpContext + 2);
                v8[2] = 0;
                v9 = EcpContext;
                *(_QWORD *)(a2 + 8) = *(_QWORD *)EcpContext;
                *v9 = 0;
                *a3 = 1;
              }
              else
              {
                *a3 = 0;
              }
            }
            else
            {
              FltObject = 0;
              Parameter = MpGetInstanceFromFileObject((PFILE_OBJECT)Object, (PFLT_INSTANCE *)&FltObject);
              if ( Parameter >= 0 )
              {
                Parameter = MpDlpQueryEa(0, FltObject, Object, a2, a3);
                FltObjectDereference(FltObject);
                FltObject = 0;
              }
            }
            goto LABEL_37;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
LABEL_37:
            if ( FileHandle )
              FltClose(FileHandle);
            if ( Object )
            {
              ObfDereferenceObject(Object);
              if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
              {
                if ( KdRefreshDebuggerNotPresent() )
                  KeBugCheck(1u);
                __debugbreak();
              }
            }
            v10 = EcpContext;
            if ( EcpContext )
            {
              if ( *(_QWORD *)EcpContext )
              {
                ExFreePoolWithTag(*(PVOID *)EcpContext, 0x6165504Du);
                v10 = EcpContext;
              }
              v10[2] = 0;
            }
            if ( EcpList )
              FltFreeExtraCreateParameterList(*(PFLT_FILTER *)(MpData + 16), EcpList);
            return (unsigned int)Parameter;
          }
          v6 = 81;
        }
        else
        {
          FltFreeExtraCreateParameter(*(PFLT_FILTER *)(MpData + 16), EcpContext);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_37;
          }
          v6 = 80;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_37;
        v6 = 79;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_37;
      v6 = 78;
    }
    _mm_lfence();
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      WPP_4c1363a434f0368aee73563b7bc19017_Traceguids,
      (unsigned int)Parameter);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids, 3221225485LL);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140086418  push    rbp
0x14008641a  push    rbx
0x14008641b  push    rsi
0x14008641c  push    rdi
0x14008641d  push    r14
0x14008641f  lea     rbp, [rsp-40h]
0x140086424  sub     rsp, 140h
0x14008642b  mov     rax, cs:__security_cookie
0x140086432  xor     rax, rsp
0x140086435  mov     [rbp+60h+var_30], rax
0x140086439  xor     r14d, r14d
0x14008643c  xor     eax, eax
0x14008643e  mov     [rbp+60h+var_E0], r14
0x140086442  xorps   xmm0, xmm0
0x140086445  mov     dword ptr [rbp+60h+var_70+4], r14d
0x140086449  mov     rdi, rdx
0x14008644c  mov     [rbp+60h+var_54], r14d
0x140086450  mov     rsi, r8
0x140086453  mov     [rbp+60h+EcpList], r14
0x140086457  mov     rdx, rcx
0x14008645a  mov     word ptr [rbp+60h+var_78], ax
0x14008645e  mov     qword ptr [rbp+60h+var_A8], rax
0x140086462  mov     word ptr [rbp+60h+var_A8+8], ax
0x140086466  mov     [rbp+60h+Object], r14
0x14008646a  mov     [rbp+60h+FileHandle], r14
0x14008646e  movups  xmmword ptr [rbp+60h+var_40], xmm0
0x140086472  movups  xmmword ptr [rbp+60h+var_98], xmm0
0x140086476  movups  [rbp+60h+var_88], xmm0
0x14008647a  movups  [rbp+60h+var_B8], xmm0
0x14008647e  test    rcx, rcx
0x140086481  jz      loc_140086848
0x140086487  test    rdi, rdi
0x14008648a  jz      loc_140086848
0x140086490  test    r8, r8
0x140086493  jz      loc_140086848
0x140086499  mov     [r8], r14b
0x14008649c  mov     [rdi], r14d
0x14008649f  mov     [rdi+8], r14
0x1400864a3  mov     rcx, cs:MpData
0x1400864aa  mov     eax, [rcx+360h]
0x1400864b0  test    al, 40h
0x1400864b2  jz      short loc_1400864CE
0x1400864b4  lea     eax, [r14+28h]
0x1400864b8  mov     [rbp+60h+var_78], 1
0x1400864c0  movups  xmmword ptr [rbp+60h+var_98], xmm0
0x1400864c4  mov     word ptr [rbp+60h+var_98], ax
0x1400864c8  movups  [rbp+60h+var_88], xmm0
0x1400864cc  jmp     short loc_1400864DF
0x1400864ce  mov     eax, 20h ; ' '
0x1400864d3  movups  [rbp+60h+var_B8], xmm0
0x1400864d7  mov     word ptr [rbp+60h+var_B8], ax
0x1400864db  movups  [rbp+60h+var_A8], xmm0
0x1400864df  mov     [rbp+60h+var_60], rdx
0x1400864e3  lea     r8, [rbp+60h+EcpList]; EcpList
0x1400864e7  mov     dword ptr [rbp+60h+var_70], 30h ; '0'
0x1400864ee  xor     edx, edx; Flags
0x1400864f0  mov     [rbp+60h+var_68], r14
0x1400864f4  mov     [rbp+60h+var_58], 240h
0x1400864fb  movdqu  [rbp+60h+var_50], xmm0
0x140086500  mov     rcx, [rcx+10h]; Filter
0x140086504  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14008650b  nop     dword ptr [rax+rax+00h]
0x140086510  mov     ebx, eax
0x140086512  test    eax, eax
0x140086514  jns     short loc_140086560
0x140086516  mov     rax, cs:WPP_GLOBAL_Control
0x14008651d  lea     rcx, WPP_GLOBAL_Control
0x140086524  cmp     rax, rcx
0x140086527  jz      loc_140086789
0x14008652d  mov     ecx, [rax+2Ch]
0x140086530  test    cl, 1
0x140086533  jz      loc_140086789
0x140086539  mov     edx, 4Eh ; 'N'
0x14008653e  lfence
0x140086541  mov     rcx, cs:WPP_GLOBAL_Control
0x140086548  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14008654f  mov     r9d, ebx
0x140086552  mov     rcx, [rcx+18h]
0x140086556  call    WPP_SF_d
0x14008655b  jmp     loc_140086789
0x140086560  mov     rcx, cs:MpData
0x140086567  lea     rdx, [rbp+60h+var_E0]
0x14008656b  mov     [rsp+160h+EcpContext], rdx; EcpContext
0x140086570  xor     r9d, r9d; Flags
0x140086573  lea     rdx, GUID_MP_ECP_QUERY_EA; EcpType
0x14008657a  lea     rax, [rcx+7C0h]
0x140086581  mov     rcx, [rcx+10h]; Filter
0x140086585  mov     [rsp+160h+LookasideList], rax; LookasideList
0x14008658a  lea     r8d, [r9+10h]; SizeOfContext
0x14008658e  mov     [rsp+160h+CleanupCallback], r14; CleanupCallback
0x140086593  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14008659a  nop     dword ptr [rax+rax+00h]
0x14008659f  mov     ebx, eax
0x1400865a1  test    eax, eax
0x1400865a3  jns     short loc_1400865D1
0x1400865a5  mov     rax, cs:WPP_GLOBAL_Control
0x1400865ac  lea     rcx, WPP_GLOBAL_Control
0x1400865b3  cmp     rax, rcx
0x1400865b6  jz      loc_140086789
0x1400865bc  mov     eax, [rax+2Ch]
0x1400865bf  test    al, 1
0x1400865c1  jz      loc_140086789
0x1400865c7  mov     edx, 4Fh ; 'O'
0x1400865cc  jmp     loc_14008653E
0x1400865d1  mov     rax, [rbp+60h+var_E0]
0x1400865d5  xorps   xmm0, xmm0
0x1400865d8  movups  xmmword ptr [rax], xmm0
0x1400865db  mov     rcx, cs:MpData
0x1400865e2  mov     r8, [rbp+60h+var_E0]; EcpContext
0x1400865e6  mov     rdx, [rbp+60h+EcpList]; EcpList
0x1400865ea  mov     rcx, [rcx+10h]; Filter
0x1400865ee  call    cs:__imp_FltInsertExtraCreateParameter
0x1400865f5  nop     dword ptr [rax+rax+00h]
0x1400865fa  mov     rcx, cs:MpData
0x140086601  mov     ebx, eax
0x140086603  test    eax, eax
0x140086605  jns     short loc_140086647
0x140086607  mov     rdx, [rbp+60h+var_E0]; EcpContext
0x14008660b  mov     rcx, [rcx+10h]; Filter
0x14008660f  call    cs:__imp_FltFreeExtraCreateParameter
0x140086616  nop     dword ptr [rax+rax+00h]
0x14008661b  mov     rax, cs:WPP_GLOBAL_Control
0x140086622  lea     rcx, WPP_GLOBAL_Control
0x140086629  cmp     rax, rcx
0x14008662c  jz      loc_140086789
0x140086632  mov     eax, [rax+2Ch]
0x140086635  test    al, 1
0x140086637  jz      loc_140086789
0x14008663d  mov     edx, 50h ; 'P'
0x140086642  jmp     loc_14008653E
0x140086647  mov     eax, [rcx+360h]
0x14008664d  test    al, 40h
0x14008664f  mov     rax, [rbp+60h+EcpList]
0x140086653  jz      short loc_14008665B
0x140086655  mov     [rbp+60h+var_98+8], rax
0x140086659  jmp     short loc_14008665F
0x14008665b  mov     qword ptr [rbp+60h+var_B8+8], rax
0x14008665f  mov     eax, [rcx+360h]
0x140086665  lea     rdx, [rbp+60h+var_98]
0x140086669  mov     rcx, [rcx+10h]; int
0x14008666d  lea     r9, [rbp+60h+Object]; int
0x140086671  test    al, 40h
0x140086673  lea     r8, [rbp+60h+FileHandle]; int
0x140086677  lea     rax, [rbp+60h+var_B8]
0x14008667b  cmovnz  rax, rdx
0x14008667f  xor     edx, edx; int
0x140086681  mov     [rsp+160h+var_E8], rax; __int64
0x140086686  lea     rax, [rbp+60h+var_40]
0x14008668a  mov     [rsp+160h+var_F0], r14d; ULONG
0x14008668f  mov     [rsp+160h+var_108], r14d; ULONG
0x140086694  mov     [rsp+160h+var_118], 7; ULONG
0x14008669c  mov     [rsp+160h+EcpContext], rax; __int64
0x1400866a1  lea     rax, [rbp+60h+var_70]
0x1400866a5  mov     [rsp+160h+LookasideList], rax; __int64
0x1400866aa  mov     dword ptr [rsp+160h+CleanupCallback], 80h; ACCESS_MASK
0x1400866b2  call    MpFltCreateFileEx2
0x1400866b7  mov     ebx, eax
0x1400866b9  test    eax, eax
0x1400866bb  jns     short loc_1400866E9
0x1400866bd  mov     rax, cs:WPP_GLOBAL_Control
0x1400866c4  lea     rcx, WPP_GLOBAL_Control
0x1400866cb  cmp     rax, rcx
0x1400866ce  jz      loc_140086789
0x1400866d4  mov     eax, [rax+2Ch]
0x1400866d7  test    al, 1
0x1400866d9  jz      loc_140086789
0x1400866df  mov     edx, 51h ; 'Q'
0x1400866e4  jmp     loc_14008653E
0x1400866e9  mov     rcx, cs:MpData
0x1400866f0  test    dword ptr [rcx+360h], 800h
0x1400866fa  jz      short loc_140086745
0x1400866fc  cmp     [rcx+60h], r14
0x140086700  jz      short loc_140086745
0x140086702  cmp     [rcx+58h], r14
0x140086706  jz      short loc_140086745
0x140086708  mov     rdx, [rbp+60h+var_E0]; EcpContext
0x14008670c  mov     rcx, [rcx+10h]; Filter
0x140086710  call    cs:__imp_FltIsEcpAcknowledged
0x140086717  nop     dword ptr [rax+rax+00h]
0x14008671c  test    al, al
0x14008671e  jz      short loc_140086740
0x140086720  mov     rcx, [rbp+60h+var_E0]
0x140086724  mov     eax, [rcx+8]
0x140086727  mov     [rdi], eax
0x140086729  mov     [rcx+8], r14d
0x14008672d  mov     rcx, [rbp+60h+var_E0]
0x140086731  mov     rax, [rcx]
0x140086734  mov     [rdi+8], rax
0x140086738  mov     [rcx], r14
0x14008673b  mov     byte ptr [rsi], 1
0x14008673e  jmp     short loc_140086789
0x140086740  mov     [rsi], r14b
0x140086743  jmp     short loc_140086789
0x140086745  mov     rcx, [rbp+60h+Object]; FileObject
0x140086749  lea     rdx, [rbp+60h+FltObject]; RetInstance
0x14008674d  mov     [rbp+60h+FltObject], r14
0x140086751  call    MpGetInstanceFromFileObject
0x140086756  mov     ebx, eax
0x140086758  test    eax, eax
0x14008675a  js      short loc_140086789
0x14008675c  mov     r8, [rbp+60h+Object]
0x140086760  mov     r9, rdi
0x140086763  mov     rdx, [rbp+60h+FltObject]
0x140086767  xor     ecx, ecx
0x140086769  mov     [rsp+160h+CleanupCallback], rsi
0x14008676e  call    MpDlpQueryEa
0x140086773  mov     rcx, [rbp+60h+FltObject]; FltObject
0x140086777  mov     ebx, eax
0x140086779  call    cs:__imp_FltObjectDereference
0x140086780  nop     dword ptr [rax+rax+00h]
0x140086785  mov     [rbp+60h+FltObject], r14
0x140086789  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x14008678d  test    rcx, rcx
0x140086790  jz      short loc_14008679E
0x140086792  call    cs:__imp_FltClose
0x140086799  nop     dword ptr [rax+rax+00h]
0x14008679e  mov     rcx, [rbp+60h+Object]; Object
0x1400867a2  test    rcx, rcx
0x1400867a5  jz      short loc_1400867E8
0x1400867a7  call    cs:__imp_ObfDereferenceObject
0x1400867ae  nop     dword ptr [rax+rax+00h]
0x1400867b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400867b7  lock xadd cs:ObTotalReferences, rax
0x1400867c0  cmp     rax, 1
0x1400867c4  jns     short loc_1400867E8
0x1400867c6  mov     rax, cs:MpData
0x1400867cd  mov     ecx, [rax+364h]
0x1400867d3  test    ecx, ecx
0x1400867d5  jns     short loc_1400867E8
0x1400867d7  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400867de  nop     dword ptr [rax+rax+00h]
0x1400867e3  test    al, al
0x1400867e5  jnz     short loc_140086836
0x1400867e7  int     3; Trap to Debugger
0x1400867e8  mov     rax, [rbp+60h+var_E0]
0x1400867ec  test    rax, rax
0x1400867ef  jz      short loc_140086812
0x1400867f1  mov     rcx, [rax]; P
0x1400867f4  test    rcx, rcx
0x1400867f7  jz      short loc_14008680E
0x1400867f9  mov     edx, 6165504Dh; Tag
0x1400867fe  call    cs:__imp_ExFreePoolWithTag
0x140086805  nop     dword ptr [rax+rax+00h]
0x14008680a  mov     rax, [rbp+60h+var_E0]
0x14008680e  mov     [rax+8], r14d
0x140086812  mov     rdx, [rbp+60h+EcpList]; EcpList
0x140086816  test    rdx, rdx
0x140086819  jz      short loc_140086832
0x14008681b  mov     rcx, cs:MpData
0x140086822  mov     rcx, [rcx+10h]; Filter
0x140086826  call    cs:__imp_FltFreeExtraCreateParameterList
0x14008682d  nop     dword ptr [rax+rax+00h]
0x140086832  mov     eax, ebx
0x140086834  jmp     short loc_140086883
0x140086836  mov     ecx, 1; BugCheckCode
0x14008683b  call    cs:__imp_KeBugCheck
0x140086848  mov     r10, cs:WPP_GLOBAL_Control
0x14008684f  lea     rcx, WPP_GLOBAL_Control
0x140086856  cmp     r10, rcx
0x140086859  jz      short loc_14008687E
0x14008685b  mov     eax, [r10+2Ch]
0x14008685f  test    al, 1
0x140086861  jz      short loc_14008687E
0x140086863  mov     rcx, [r10+18h]
0x140086867  lea     r8, WPP_4c1363a434f0368aee73563b7bc19017_Traceguids
0x14008686e  mov     edx, 4Dh ; 'M'
0x140086873  mov     r9d, 0C000000Dh
0x140086879  call    WPP_SF_d
0x14008687e  mov     eax, 0C000000Dh
0x140086883  mov     rcx, [rbp+60h+var_30]
0x140086887  xor     rcx, rsp; StackCookie
0x14008688a  call    __security_check_cookie
0x14008688f  add     rsp, 140h
0x140086896  pop     r14
0x140086898  pop     rdi
0x140086899  pop     rsi
0x14008689a  pop     rbx
0x14008689b  pop     rbp
0x14008689c  retn
```
