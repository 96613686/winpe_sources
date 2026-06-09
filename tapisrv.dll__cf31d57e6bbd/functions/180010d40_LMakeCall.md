# LMakeCall

- ea: `0x180010d40`
- end: `0x180011089`
- name: `LMakeCall`
- size: `841`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x180003d8c`
- `0x1800072e4`
- `0x180007394`
- `0x180010d40`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c3ec`
- `0x18001eafc`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003e3b4`
- `0x180040010`

## string_xrefs

- `0x180010f19`: `LMakeCall: CreatetCallAndClient failed. LINEERR_NOMEM`

## pseudocode

```c
__int64 __fastcall LMakeCall(__int64 a1, unsigned int *a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r8d
  int v8; // eax
  __int64 v9; // r13
  int v10; // esi
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int *v13; // rbx
  _QWORD *v14; // r14
  int v15; // eax
  int v16; // r15d
  unsigned int *v17; // r9
  __int64 v18; // r15
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v26; // [rsp+50h] [rbp-51h]
  __int64 v27; // [rsp+70h] [rbp-31h] BYREF
  unsigned int *v28; // [rsp+78h] [rbp-29h]
  __int64 v29; // [rsp+80h] [rbp-21h] BYREF
  __int64 v30; // [rsp+88h] [rbp-19h] BYREF
  __int64 v31; // [rsp+90h] [rbp-11h] BYREF
  int v32[2]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-1h] BYREF
  HANDLE TargetHandle; // [rsp+A8h] [rbp+7h] BYREF
  __int64 v35; // [rsp+108h] [rbp+67h] BYREF

  v5 = a2[4];
  v26 = a2[2];
  TargetHandle = 0;
  *(_QWORD *)v32 = 0;
  v33 = 0;
  v27 = 0;
  v30 = 0;
  v35 = 0;
  v8 = LineProlog(
         a1,
         2,
         v5,
         (unsigned int *)v32,
         0,
         &TargetHandle,
         (_DWORD *)&v27 + 1,
         0x24u,
         &v33,
         &v35,
         v26,
         (unsigned int *)&v27,
         (char **)&v30);
  v9 = v35;
  v10 = v8;
  if ( v8 > 0 )
  {
    v29 = 0;
    LODWORD(v35) = 0;
    v31 = 0;
    v28 = 0;
    TRACELogPrint(262146, "LMakeCall: LINEPROLOG succeeded .");
    v11 = a2[6];
    if ( (v11 == -1 || !IsBadStringParam(a3, a4, v11))
      && ((v12 = a2[8], v12 == -1) || !(unsigned int)IsBadStructParam(a3, a4, v12)) )
    {
      if ( a2[8] == -1 )
        v13 = 0;
      else
        v13 = (unsigned int *)(a4 + a2[8]);
      TRACELogPrint(262146, "LMakeCall: pCallParamsApp %p.", v13);
      v14 = (_QWORD *)v30;
      if ( v13 )
      {
        if ( *(_DWORD *)v30 != 1229734732 )
        {
          TRACELogPrint(65538, "LMakeCall: GetLineVersions failed. LINEERR_INVALLINEHANDLE");
          v10 = -2147483605;
          goto LABEL_30;
        }
        v15 = ValidateCallParams(v13, a2[9]);
        v16 = v15;
        if ( v15 )
        {
          TRACELogPrint(65538, "LMakeCall: ValidateCallParams failed. %lx", v15);
          v10 = v16;
          goto LABEL_30;
        }
        v17 = v28;
      }
      else
      {
        v17 = 0;
        v28 = 0;
      }
      if ( (unsigned int)CreatetCallAndClient(v14, &v29, (__int64)&v31, v17, &v35) )
      {
        TRACELogPrint(65538, "LMakeCall: CreatetCallAndClient failed. LINEERR_NOMEM");
        v10 = -2147483580;
      }
      else
      {
        v18 = (unsigned int)v35;
        *(_QWORD *)(v9 + 48) = LMakeCall_PostProcess;
        v19 = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v31 + 16) + 32LL) + 208LL);
        v20 = v29;
        *(_QWORD *)(v9 + 24) = v19;
        *(_QWORD *)(v9 + 80) = v20;
        *(_QWORD *)(v9 + 88) = a2[5];
        *(_QWORD *)(v9 + 112) = v18;
        ReferenceObject(v19, (unsigned int)v18, 1279345481);
        *(_DWORD *)(v9 + 68) = a2[3];
        if ( a2[6] == -1 )
        {
          TRACELogPrint(65538, "LMakeCall: pParams->dwDestAddressOffset == TAPI_NO_DATA");
          v21 = 0;
        }
        else
        {
          v21 = a4 + a2[6];
        }
        TRACELogPrint(524290, "LMakeCall: calling CallSP7");
        v22 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, __int64, unsigned int, unsigned int *))v33)(
                *(unsigned int *)(v9 + 72),
                *(_QWORD *)v32,
                v18,
                v29 + 40,
                v21,
                a2[7],
                v28);
        *a2 = v22;
        TRACELogPrint(262146, "LMakeCall: CallSP7 returnded %lx", v22);
        v23 = *a2;
        if ( (*a2 & 0x80000000) != 0 || v23 > 0x80000061 && v23 + 1879048191 > 0x24 )
          v24 = 1;
        else
          v24 = 3;
        SetDrvCallFlags((unsigned int)v18, v24);
      }
      if ( v28 != v13 )
        ServerFree(v28);
    }
    else
    {
      TRACELogPrint(262146, "LMakeCall: LINEERR_STRUCTURETOOSMALL.");
      v10 = -2147483571;
    }
  }
LABEL_30:
  TRACELogPrint(524290, "LMakeCall: calling LINEEPILOGASYNC");
  LineEpilogAsync(a2, v10, (__int64)TargetHandle, HIDWORD(v27), v9, v27);
  return TRACELogPrint(524290, "LMakeCall: LINEEPILOGASYNC returned");
}

```

## disassembly

```asm
0x180010d40  push    rbp
0x180010d42  push    rbx
0x180010d43  push    rsi
0x180010d44  push    rdi
0x180010d45  push    r12
0x180010d47  push    r13
0x180010d49  push    r14
0x180010d4b  push    r15
0x180010d4d  lea     rbp, [rsp-17h]
0x180010d52  sub     rsp, 0B8h
0x180010d59  xor     r15d, r15d
0x180010d5c  lea     rax, [rbp+4Fh+var_68]
0x180010d60  mov     [rsp+0F0h+var_90], rax; __int64
0x180010d65  mov     ebx, r8d
0x180010d68  mov     r8d, [rdx+10h]; int
0x180010d6c  lea     rax, [rbp+4Fh+var_80]
0x180010d70  mov     [rsp+0F0h+var_98], rax; __int64
0x180010d75  mov     r12, r9
0x180010d78  mov     eax, [rdx+8]
0x180010d7b  lea     r9, [rbp+4Fh+var_58]; int
0x180010d7f  mov     [rsp+0F0h+var_A0], eax; int
0x180010d83  mov     rdi, rdx
0x180010d86  lea     rax, [rbp+4Fh+arg_8]
0x180010d8a  mov     dword ptr [rbp+4Fh+var_80+4], r15d
0x180010d8e  mov     [rsp+0F0h+var_A8], rax; __int64
0x180010d93  lea     edx, [r15+2]; int
0x180010d97  lea     rax, [rbp+4Fh+var_50]
0x180010d9b  mov     [rbp+4Fh+TargetHandle], r15
0x180010d9f  mov     [rsp+0F0h+var_B0], rax; __int64
0x180010da4  lea     rax, [rbp+4Fh+var_80+4]
0x180010da8  mov     [rsp+0F0h+var_B8], 24h ; '$'; int
0x180010db0  mov     [rsp+0F0h+var_C0], rax; __int64
0x180010db5  lea     rax, [rbp+4Fh+TargetHandle]
0x180010db9  mov     [rsp+0F0h+lpTargetHandle], rax; lpTargetHandle
0x180010dbe  mov     [rsp+0F0h+CodePage], r15d; int
0x180010dc3  mov     qword ptr [rbp+4Fh+var_58], r15
0x180010dc7  mov     [rbp+4Fh+var_50], r15
0x180010dcb  mov     dword ptr [rbp+4Fh+var_80], r15d
0x180010dcf  mov     [rbp+4Fh+var_68], r15
0x180010dd3  mov     [rbp+4Fh+arg_8], r15
0x180010dd7  call    LineProlog
0x180010ddc  mov     r13, [rbp+4Fh+arg_8]
0x180010de0  mov     esi, eax
0x180010de2  test    eax, eax
0x180010de4  jle     loc_180011035
0x180010dea  lea     rdx, aLmakecallLinep; "LMakeCall: LINEPROLOG succeeded ."
0x180010df1  mov     [rbp+4Fh+var_70], r15
0x180010df5  mov     ecx, 40002h
0x180010dfa  mov     dword ptr [rbp+4Fh+arg_8], r15d
0x180010dfe  mov     [rbp+4Fh+var_60], r15
0x180010e02  mov     [rbp+4Fh+var_78], r15
0x180010e06  call    TRACELogPrint
0x180010e0b  mov     r8d, [rdi+18h]
0x180010e0f  or      r14d, 0FFFFFFFFh
0x180010e13  cmp     r8d, r14d
0x180010e16  jz      short loc_180010E26
0x180010e18  mov     rdx, r12
0x180010e1b  mov     ecx, ebx
0x180010e1d  call    IsBadStringParam
0x180010e22  test    eax, eax
0x180010e24  jnz     short loc_180010E3D
0x180010e26  mov     r8d, [rdi+20h]
0x180010e2a  cmp     r8d, r14d
0x180010e2d  jz      short loc_180010E58
0x180010e2f  mov     rdx, r12
0x180010e32  mov     ecx, ebx
0x180010e34  call    IsBadStructParam
0x180010e39  test    eax, eax
0x180010e3b  jz      short loc_180010E58
0x180010e3d  lea     rdx, aLmakecallLinee_0; "LMakeCall: LINEERR_STRUCTURETOOSMALL."
0x180010e44  mov     ecx, 40002h
0x180010e49  call    TRACELogPrint
0x180010e4e  mov     esi, 8000004Dh
0x180010e53  jmp     loc_180011035
0x180010e58  cmp     [rdi+20h], r14d
0x180010e5c  jnz     short loc_180010E63
0x180010e5e  mov     rbx, r15
0x180010e61  jmp     short loc_180010E69
0x180010e63  mov     ebx, [rdi+20h]
0x180010e66  add     rbx, r12
0x180010e69  mov     r8, rbx
0x180010e6c  lea     rdx, aLmakecallPcall; "LMakeCall: pCallParamsApp %p."
0x180010e73  mov     ecx, 40002h
0x180010e78  call    TRACELogPrint
0x180010e7d  mov     r14, [rbp+4Fh+var_68]
0x180010e81  test    rbx, rbx
0x180010e84  jz      short loc_180010EF5
0x180010e86  cmp     dword ptr [r14], 494C434Ch
0x180010e8d  jz      short loc_180010EAA
0x180010e8f  lea     rdx, aLmakecallGetli; "LMakeCall: GetLineVersions failed. LINE"...
0x180010e96  mov     ecx, 10002h
0x180010e9b  call    TRACELogPrint
0x180010ea0  mov     esi, 8000002Bh
0x180010ea5  jmp     loc_180011035
0x180010eaa  mov     r9, [r14+20h]
0x180010eae  lea     rdx, [rbp+4Fh+var_78]
0x180010eb2  mov     eax, [rdi+24h]
0x180010eb5  mov     rcx, rbx; Src
0x180010eb8  mov     r8d, [r14+3Ch]
0x180010ebc  mov     [rsp+0F0h+CodePage], eax; CodePage
0x180010ec0  mov     r9d, [r9+0D8h]
0x180010ec7  call    ValidateCallParams
0x180010ecc  mov     r15d, eax
0x180010ecf  test    eax, eax
0x180010ed1  jz      short loc_180010EEF
0x180010ed3  mov     r8d, eax
0x180010ed6  lea     rdx, aLmakecallValid; "LMakeCall: ValidateCallParams failed. %"...
0x180010edd  mov     ecx, 10002h
0x180010ee2  call    TRACELogPrint
0x180010ee7  mov     esi, r15d
0x180010eea  jmp     loc_180011035
0x180010eef  mov     r9, [rbp+4Fh+var_78]
0x180010ef3  jmp     short loc_180010EFC
0x180010ef5  mov     r9, r15
0x180010ef8  mov     [rbp+4Fh+var_78], r15
0x180010efc  lea     rax, [rbp+4Fh+arg_8]
0x180010f00  mov     rcx, r14
0x180010f03  lea     r8, [rbp+4Fh+var_60]
0x180010f07  mov     qword ptr [rsp+0F0h+CodePage], rax
0x180010f0c  lea     rdx, [rbp+4Fh+var_70]
0x180010f10  call    CreatetCallAndClient
0x180010f15  test    eax, eax
0x180010f17  jz      short loc_180010F34
0x180010f19  lea     rdx, aLmakecallCreat; "LMakeCall: CreatetCallAndClient failed."...
0x180010f20  mov     ecx, 10002h
0x180010f25  call    TRACELogPrint
0x180010f2a  mov     esi, 80000044h
0x180010f2f  jmp     loc_180011027
0x180010f34  mov     r15d, dword ptr [rbp+4Fh+arg_8]
0x180010f38  lea     rax, LMakeCall_PostProcess
0x180010f3f  mov     [r13+30h], rax
0x180010f43  mov     rax, [rbp+4Fh+var_60]
0x180010f47  mov     rcx, [rax+10h]
0x180010f4b  mov     rax, [rcx+20h]
0x180010f4f  mov     ecx, [rax+0D0h]
0x180010f55  mov     rax, [rbp+4Fh+var_70]
0x180010f59  mov     [r13+18h], rcx
0x180010f5d  mov     [r13+50h], rax
0x180010f61  mov     eax, [rdi+14h]
0x180010f64  mov     [r13+58h], rax
0x180010f68  mov     [r13+70h], r15
0x180010f6c  mov     r8d, 4C414349h
0x180010f72  mov     edx, r15d
0x180010f75  call    ReferenceObject
0x180010f7a  mov     eax, [rdi+0Ch]
0x180010f7d  mov     [r13+44h], eax
0x180010f81  cmp     dword ptr [rdi+18h], 0FFFFFFFFh
0x180010f85  jnz     short loc_180010F9D
0x180010f87  lea     rdx, aLmakecallPpara; "LMakeCall: pParams->dwDestAddressOffset"...
0x180010f8e  mov     ecx, 10002h
0x180010f93  call    TRACELogPrint
0x180010f98  xor     r14d, r14d
0x180010f9b  jmp     short loc_180010FA4
0x180010f9d  mov     r14d, [rdi+18h]
0x180010fa1  add     r14, r12
0x180010fa4  lea     rdx, aLmakecallCalli_0; "LMakeCall: calling CallSP7"
0x180010fab  mov     ecx, 80002h
0x180010fb0  call    TRACELogPrint
0x180010fb5  mov     rcx, [rbp+4Fh+var_78]
0x180010fb9  mov     r8, r15
0x180010fbc  mov     r9, [rbp+4Fh+var_70]
0x180010fc0  mov     rdx, qword ptr [rbp+4Fh+var_58]
0x180010fc4  add     r9, 28h ; '('
0x180010fc8  mov     rax, [rbp+4Fh+var_50]
0x180010fcc  mov     [rsp+0F0h+var_C0], rcx
0x180010fd1  mov     ecx, [rdi+1Ch]
0x180010fd4  mov     dword ptr [rsp+0F0h+lpTargetHandle], ecx
0x180010fd8  mov     ecx, [r13+48h]
0x180010fdc  mov     qword ptr [rsp+0F0h+CodePage], r14
0x180010fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe6  mov     r8d, eax
0x180010fe9  mov     [rdi], eax
0x180010feb  lea     rdx, aLmakecallCalls; "LMakeCall: CallSP7 returnded %lx"
0x180010ff2  mov     ecx, 40002h
0x180010ff7  call    TRACELogPrint
0x180010ffc  mov     eax, [rdi]
0x180010ffe  test    eax, eax
0x180011000  js      short loc_18001101A
0x180011002  cmp     eax, 80000061h
0x180011007  jbe     short loc_180011013
0x180011009  add     eax, 6FFFFFFFh
0x18001100e  cmp     eax, 24h ; '$'
0x180011011  ja      short loc_18001101A
0x180011013  mov     edx, 3
0x180011018  jmp     short loc_18001101F
0x18001101a  mov     edx, 1
0x18001101f  mov     ecx, r15d
0x180011022  call    SetDrvCallFlags
0x180011027  mov     rcx, [rbp+4Fh+var_78]; lpMem
0x18001102b  cmp     rcx, rbx
0x18001102e  jz      short loc_180011035
0x180011030  call    ServerFree
0x180011035  lea     rdx, aLmakecallCalli; "LMakeCall: calling LINEEPILOGASYNC"
0x18001103c  mov     ecx, 80002h
0x180011041  call    TRACELogPrint
0x180011046  mov     eax, dword ptr [rbp+4Fh+var_80]
0x180011049  mov     edx, esi
0x18001104b  mov     r9d, dword ptr [rbp+4Fh+var_80+4]
0x18001104f  mov     rcx, rdi
0x180011052  mov     r8, [rbp+4Fh+TargetHandle]
0x180011056  mov     dword ptr [rsp+0F0h+lpTargetHandle], eax
0x18001105a  mov     qword ptr [rsp+0F0h+CodePage], r13
0x18001105f  call    LineEpilogAsync
0x180011064  lea     rdx, aLmakecallLinee; "LMakeCall: LINEEPILOGASYNC returned"
0x18001106b  mov     ecx, 80002h
0x180011070  call    TRACELogPrint
0x180011075  add     rsp, 0B8h
0x18001107c  pop     r15
0x18001107e  pop     r14
0x180011080  pop     r13
0x180011082  pop     r12
0x180011084  pop     rdi
0x180011085  pop     rsi
0x180011086  pop     rbx
0x180011087  pop     rbp
0x180011088  retn
```
