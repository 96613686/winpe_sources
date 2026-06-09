# WfpAleEndpointCreationHandler

- ea: `0x140019480`
- end: `0x14001988b`
- name: `WfpAleEndpointCreationHandler`
- size: `1035`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400175b0`
- `0x140018bd0`
- `0x140018ee0`
- `0x140019330`
- `0x140118220`
- `0x1401821e0`
- `0x14019ed40`
- `0x1401a2450`

## callees

- `0x140019480`
- `0x140053910`
- `0x140055780`
- `0x1400774f0`
- `0x140077574`
- `0x14008a370`
- `0x1400ba5dc`
- `0x140136370`
- `0x14014cdc4`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeIsExecutingDpc` at `0x140019595`
- `ntoskrnl!KeIsExecutingDpc` at `0x140019595`
- `ntoskrnl!KeInitializeSpinLock` at `0x140019736`
- `ntoskrnl!KeInitializeSpinLock` at `0x140019736`
- `ntoskrnl!PsGetProcessSessionId` at `0x14001954f`
- `ntoskrnl!PsGetProcessSessionId` at `0x14001954f`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x140019561`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x140019561`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400195bf`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400195bf`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140019587`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400195ae`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140019587`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400195ae`

## pseudocode

```c
__int64 __fastcall WfpAleEndpointCreationHandler(
        _DWORD *a1,
        unsigned __int16 a2,
        __int16 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        KSPIN_LOCK a7,
        KSPIN_LOCK a8,
        PKSPIN_LOCK *a9)
{
  __int64 v13; // rax
  PKSPIN_LOCK v14; // rbx
  unsigned int v15; // edi
  __int64 v16; // rax
  int ThreadObjectCompartmentId; // eax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int i; // edx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  char v23; // bp
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  bool v28; // zf
  KSPIN_LOCK v29; // rax
  __int64 result; // rax
  PKSPIN_LOCK SpinLock[11]; // [rsp+30h] [rbp-58h] BYREF

  SpinLock[0] = 0;
  *a9 = 0;
  v13 = WfpAllocateFromPerProcessorLookasideList(endpointPPLookasideList, SpinLock);
  v14 = SpinLock[0];
  v15 = v13;
  if ( !v13 )
  {
    memset(SpinLock[0], 0, 0x2F0u);
    v14[44] = a8;
    if ( a1 )
    {
      *((_WORD *)v14 + 30) = a2;
      *((_DWORD *)v14 + 10) = a4;
      if ( (unsigned __int8)WfpAleReferenceEndpoint_0(a1, 2) )
      {
        v14[68] = (KSPIN_LOCK)a1;
        v23 = 0;
        *((_DWORD *)v14 + 152) = a1[152];
        *((_DWORD *)v14 + 153) = a1[153];
        *((_DWORD *)v14 + 12) = 0;
        if ( (Feature_5988_5730__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline(v25, v24, v26);
        if ( IsEnabledDeviceUsageNoInline && (a1[14] & 8) != 0 )
          _InterlockedOr((volatile signed __int32 *)v14 + 14, 8u);
        goto LABEL_34;
      }
      v15 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAleEndpointCreationHandler",
          1);
      }
    }
    else
    {
      v16 = WfpAleInitializeEpochContext(a2, a4, a3 == 3, 0, 0, (__int64)(v14 + 45));
      v15 = v16;
      if ( !v16 )
      {
        _InterlockedOr((volatile signed __int32 *)v14 + 12, 0x1000u);
        *((_WORD *)v14 + 30) = a2;
        *((_DWORD *)v14 + 10) = a4;
        *((_DWORD *)v14 + 126) = PsGetProcessSessionId(a5);
        *((_DWORD *)v14 + 152) = NdisGetSessionToCompartmentMappingEpochAndZero() & 0x7FFFFFFF;
        if ( a6 )
        {
          ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(a6);
        }
        else if ( (unsigned int)KeIsExecutingDpc() )
        {
          ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(a5);
        }
        else
        {
          ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
        }
        *((_DWORD *)v14 + 153) = ThreadObjectCompartmentId;
        if ( a4 != 6 || (v14[6] & 0x10) != 0 )
        {
          if ( (v14[6] & 0x40) != 0 )
            _InterlockedAnd((volatile signed __int32 *)v14 + 12, 0xFFFFFFBF);
          if ( (*((_DWORD *)v14 + 12) & 0x80u) != 0 )
            _InterlockedAnd((volatile signed __int32 *)v14 + 12, 0xFFFFFF7F);
          if ( (*((_DWORD *)v14 + 13) & 0x40000) != 0 )
            _InterlockedAnd((volatile signed __int32 *)v14 + 13, 0xFFFBFFFF);
        }
        if ( a3 == 3 )
          _InterlockedOr((volatile signed __int32 *)v14 + 12, 0x10u);
        v18 = WfpAleCaptureSecurityInformation(v14, a5, a6);
        v15 = v18;
        if ( !v18 )
        {
          v14[75] = a7;
          if ( a4 == 6 && (v14[6] & 0x10) == 0 )
          {
LABEL_26:
            v23 = 1;
LABEL_34:
            *((_DWORD *)v14 + 50) = 0;
            KeInitializeSpinLock(v14);
            v28 = gAleDebugEnabled == 0;
            *((_DWORD *)v14 + 2) = 0;
            v14[2] = 0;
            v14[3] = 0;
            v14[18] = (KSPIN_LOCK)WfpAlepEndpointCleanup;
            *((_DWORD *)v14 + 32) = 1;
            *((_WORD *)v14 + 66) = 0;
            v14[17] = (KSPIN_LOCK)v14;
            if ( v28 )
            {
              v14[19] = 0xBADBADFABADBADFAuLL;
            }
            else
            {
              if ( WfpPoolAllocNonPaged(80, 1919247937, v14 + 19) )
                v14[19] = 0xBADBADFABADBADFAuLL;
              if ( gAleDebugEnabled )
              {
                v29 = v14[19];
                if ( v29 != 0xBADBADFABADBADFAuLL )
                  _InterlockedIncrement((volatile signed __int32 *)(v29 + 4));
              }
            }
            *((_DWORD *)v14 + 32) = (*((_DWORD *)v14 + 32) + 4)
                                  ^ ((unsigned __int8)*((_DWORD *)v14 + 32)
                                   ^ (unsigned __int8)(*((_DWORD *)v14 + 32) + 4))
                                  & 3;
            if ( v23 )
              _InterlockedOr((volatile signed __int32 *)v14 + 12, 0x200u);
            _InterlockedOr((volatile signed __int32 *)v14 + 12, 1u);
            v14[78] = 0;
            result = 0;
            *a9 = v14;
            return result;
          }
          v19 = WfpPoolAllocNonPaged(16LL * *(unsigned int *)(pRemoteEndpointTable + 4), 1416850497, v14 + 69);
          v15 = v19;
          if ( !v19 )
          {
            for ( i = 0; i < *(_DWORD *)(pRemoteEndpointTable + 4); *v22 = v22 )
            {
              v21 = i++;
              v22 = (_QWORD *)(v14[69] + 16 * v21);
              v22[1] = v22;
            }
            v14[74] = (KSPIN_LOCK)(v14 + 73);
            v14[73] = (KSPIN_LOCK)(v14 + 73);
            goto LABEL_26;
          }
        }
      }
    }
  }
  if ( v14 )
    WfpAlepEndpointCleanup(v14);
  return v15;
}

```

## disassembly

```asm
0x140019480  push    rbx
0x140019482  push    rbp
0x140019483  push    rsi
0x140019484  push    rdi
0x140019485  push    r12
0x140019487  push    r13
0x140019489  push    r14
0x14001948b  push    r15
0x14001948d  sub     rsp, 48h
0x140019491  mov     r12, [rsp+88h+arg_40]
0x140019499  xor     r13d, r13d
0x14001949c  movzx   r14d, dx
0x1400194a0  mov     [rsp+88h+SpinLock], r13
0x1400194a5  mov     rsi, rcx
0x1400194a8  lea     rdx, [rsp+88h+SpinLock]
0x1400194ad  mov     ebp, r9d
0x1400194b0  movzx   r15d, r8w
0x1400194b4  mov     [r12], r13
0x1400194b8  mov     rcx, cs:endpointPPLookasideList
0x1400194bf  call    WfpAllocateFromPerProcessorLookasideList
0x1400194c4  mov     rbx, [rsp+88h+SpinLock]
0x1400194c9  mov     rdi, rax
0x1400194cc  test    rax, rax
0x1400194cf  jnz     loc_14001986A
0x1400194d5  xor     edx, edx; Val
0x1400194d7  mov     r8d, 2F0h; Size
0x1400194dd  mov     rcx, rbx; void *
0x1400194e0  call    memset
0x1400194e5  mov     rax, [rsp+88h+arg_38]
0x1400194ed  mov     [rbx+160h], rax
0x1400194f4  test    rsi, rsi
0x1400194f7  jnz     loc_1400196C5
0x1400194fd  xor     r9d, r9d
0x140019500  lea     rax, [rbx+168h]
0x140019507  mov     r8d, r13d
0x14001950a  mov     [rsp+88h+var_60], rax
0x14001950f  cmp     r15w, 3
0x140019514  mov     [rsp+88h+var_68], r13d
0x140019519  mov     edx, ebp
0x14001951b  movzx   ecx, r14w
0x14001951f  setz    r8b
0x140019523  call    WfpAleInitializeEpochContext
0x140019528  mov     rdi, rax
0x14001952b  test    rax, rax
0x14001952e  jnz     loc_14001986A
0x140019534  lock or dword ptr [rbx+30h], 1000h
0x14001953c  mov     rdi, [rsp+88h+arg_20]
0x140019544  mov     [rbx+3Ch], r14w
0x140019549  mov     rcx, rdi
0x14001954c  mov     [rbx+28h], ebp
0x14001954f  call    cs:__imp_PsGetProcessSessionId
0x140019556  nop     dword ptr [rax+rax+00h]
0x14001955b  mov     [rbx+1F8h], eax
0x140019561  call    cs:__imp_NdisGetSessionToCompartmentMappingEpochAndZero
0x140019568  nop     dword ptr [rax+rax+00h]
0x14001956d  mov     rsi, [rsp+88h+arg_28]
0x140019575  btr     eax, 1Fh
0x140019579  mov     [rbx+260h], eax
0x14001957f  test    rsi, rsi
0x140019582  jz      short loc_140019595
0x140019584  mov     rcx, rsi
0x140019587  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001958e  nop     dword ptr [rax+rax+00h]
0x140019593  jmp     short loc_1400195CB
0x140019595  call    cs:__imp_KeIsExecutingDpc
0x14001959c  nop     dword ptr [rax+rax+00h]
0x1400195a1  test    eax, eax
0x1400195a3  jnz     short loc_1400195BC
0x1400195a5  mov     rcx, gs:188h
0x1400195ae  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400195b5  nop     dword ptr [rax+rax+00h]
0x1400195ba  jmp     short loc_1400195CB
0x1400195bc  mov     rcx, rdi
0x1400195bf  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1400195c6  nop     dword ptr [rax+rax+00h]
0x1400195cb  mov     [rbx+264h], eax
0x1400195d1  cmp     ebp, 6
0x1400195d4  jnz     short loc_1400195DD
0x1400195d6  mov     eax, [rbx+30h]
0x1400195d9  test    al, 10h
0x1400195db  jz      short loc_140019609
0x1400195dd  mov     eax, [rbx+30h]
0x1400195e0  test    al, 40h
0x1400195e2  jz      short loc_1400195E9
0x1400195e4  lock and dword ptr [rbx+30h], 0FFFFFFBFh
0x1400195e9  mov     eax, [rbx+30h]
0x1400195ec  test    al, al
0x1400195ee  jns     short loc_1400195F8
0x1400195f0  lock and dword ptr [rbx+30h], 0FFFFFF7Fh
0x1400195f8  mov     eax, [rbx+34h]
0x1400195fb  bt      eax, 12h
0x1400195ff  jnb     short loc_140019609
0x140019601  lock and dword ptr [rbx+34h], 0FFFBFFFFh
0x140019609  cmp     r15w, 3
0x14001960e  jnz     short loc_140019615
0x140019610  lock or dword ptr [rbx+30h], 10h
0x140019615  mov     r8, rsi
0x140019618  mov     rdx, rdi
0x14001961b  mov     rcx, rbx
0x14001961e  call    WfpAleCaptureSecurityInformation
0x140019623  mov     rdi, rax
0x140019626  test    rax, rax
0x140019629  jnz     loc_14001986A
0x14001962f  mov     rax, [rsp+88h+arg_30]
0x140019637  mov     [rbx+258h], rax
0x14001963e  cmp     ebp, 6
0x140019641  jnz     short loc_14001964A
0x140019643  mov     eax, [rbx+30h]
0x140019646  test    al, 10h
0x140019648  jz      short loc_1400196C0
0x14001964a  mov     rax, cs:pRemoteEndpointTable
0x140019651  lea     r8, [rbx+228h]
0x140019658  mov     edx, 54736C41h
0x14001965d  mov     ecx, [rax+4]
0x140019660  shl     rcx, 4
0x140019664  call    WfpPoolAllocNonPaged
0x140019669  mov     rdi, rax
0x14001966c  test    rax, rax
0x14001966f  jnz     loc_14001986A
0x140019675  mov     rax, cs:pRemoteEndpointTable
0x14001967c  mov     edx, r13d
0x14001967f  cmp     [rax+4], r13d
0x140019683  jbe     short loc_1400196B2
0x140019685  nop     word ptr [rax+rax+00000000h]
0x140019690  mov     ecx, edx
0x140019692  inc     edx
0x140019694  shl     rcx, 4
0x140019698  add     rcx, [rbx+228h]
0x14001969f  mov     [rcx+8], rcx
0x1400196a3  mov     [rcx], rcx
0x1400196a6  mov     rax, cs:pRemoteEndpointTable
0x1400196ad  cmp     edx, [rax+4]
0x1400196b0  jb      short loc_140019690
0x1400196b2  lea     rax, [rbx+248h]
0x1400196b9  mov     [rax+8], rax
0x1400196bd  mov     [rax], rax
0x1400196c0  mov     bpl, 1
0x1400196c3  jmp     short loc_14001972C
0x1400196c5  mov     [rbx+3Ch], r14w
0x1400196ca  mov     edx, 2
0x1400196cf  mov     rcx, rsi
0x1400196d2  mov     [rbx+28h], ebp
0x1400196d5  call    WfpAleReferenceEndpoint_0
0x1400196da  test    al, al
0x1400196dc  jz      loc_140019821
0x1400196e2  mov     [rbx+220h], rsi
0x1400196e9  xor     bpl, bpl
0x1400196ec  mov     eax, [rsi+260h]
0x1400196f2  mov     [rbx+260h], eax
0x1400196f8  mov     eax, [rsi+264h]
0x1400196fe  mov     [rbx+264h], eax
0x140019704  mov     [rbx+30h], r13d
0x140019708  mov     eax, cs:Feature_5988_5730__private_featureState
0x14001970e  test    al, 10h
0x140019710  jz      short loc_140019717
0x140019712  and     eax, 1
0x140019715  jmp     short loc_14001971C
0x140019717  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x14001971c  test    eax, eax
0x14001971e  jz      short loc_14001972C
0x140019720  mov     eax, [rsi+38h]
0x140019723  test    al, 8
0x140019725  jz      short loc_14001972C
0x140019727  lock or dword ptr [rbx+38h], 8
0x14001972c  mov     rcx, rbx; SpinLock
0x14001972f  mov     [rbx+0C8h], r13d
0x140019736  call    cs:__imp_KeInitializeSpinLock
0x14001973d  nop     dword ptr [rax+rax+00h]
0x140019742  cmp     cs:gAleDebugEnabled, r13b
0x140019749  lea     rax, WfpAlepEndpointCleanup
0x140019750  mov     [rbx+8], r13d
0x140019754  mov     [rbx+10h], r13
0x140019758  mov     [rbx+18h], r13
0x14001975c  mov     [rbx+90h], rax
0x140019763  mov     dword ptr [rbx+80h], 1
0x14001976d  mov     [rbx+84h], r13w
0x140019775  mov     [rbx+88h], rbx
0x14001977c  jz      short loc_1400197C5
0x14001977e  lea     r8, [rbx+98h]
0x140019785  mov     edx, 72656641h
0x14001978a  mov     ecx, 50h ; 'P'
0x14001978f  call    WfpPoolAllocNonPaged
0x140019794  mov     rcx, 0BADBADFABADBADFAh
0x14001979e  test    rax, rax
0x1400197a1  jz      short loc_1400197AA
0x1400197a3  mov     [rbx+98h], rcx
0x1400197aa  cmp     cs:gAleDebugEnabled, r13b
0x1400197b1  jz      short loc_1400197D6
0x1400197b3  mov     rax, [rbx+98h]
0x1400197ba  cmp     rax, rcx
0x1400197bd  jz      short loc_1400197D6
0x1400197bf  lock inc dword ptr [rax+4]
0x1400197c3  jmp     short loc_1400197D6
0x1400197c5  mov     rcx, 0BADBADFABADBADFAh
0x1400197cf  mov     [rbx+98h], rcx
0x1400197d6  lea     rax, [rbx+80h]
0x1400197dd  mov     [rsp+88h+arg_40], rax
0x1400197e5  mov     r8, [rsp+88h+arg_40]
0x1400197ed  mov     eax, [r8]
0x1400197f0  lea     ecx, [rax+4]
0x1400197f3  mov     edx, ecx
0x1400197f5  xor     edx, eax
0x1400197f7  and     edx, 3
0x1400197fa  xor     edx, ecx
0x1400197fc  mov     [r8], edx
0x1400197ff  test    bpl, bpl
0x140019802  jz      short loc_14001980C
0x140019804  lock or dword ptr [rbx+30h], 200h
0x14001980c  lock or dword ptr [rbx+30h], 1
0x140019811  mov     [rbx+270h], r13
0x140019818  mov     eax, r13d
0x14001981b  mov     [r12], rbx
0x14001981f  jmp     short loc_140019879
0x140019821  mov     rcx, cs:WPP_GLOBAL_Control
0x140019828  lea     rax, WPP_GLOBAL_Control
0x14001982f  mov     rdi, 0FFFFFFFFC0000001h
0x140019836  cmp     rcx, rax
0x140019839  jz      short loc_14001986A
0x14001983b  cmp     byte ptr [rcx+29h], 2
0x14001983f  jb      short loc_14001986A
0x140019841  test    dword ptr [rcx+2Ch], 1000h
0x140019848  jz      short loc_14001986A
0x14001984a  mov     rcx, [rcx+18h]
0x14001984e  lea     r9, aWfpaleendpoint; "WfpAleEndpointCreationHandler"
0x140019855  mov     edx, 0Ah
0x14001985a  mov     [rsp+88h+var_68], edi
0x14001985e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140019865  call    WPP_SF_sd
0x14001986a  test    rbx, rbx
0x14001986d  jz      short loc_140019877
0x14001986f  mov     rcx, rbx; SpinLock
0x140019872  call    WfpAlepEndpointCleanup
0x140019877  mov     eax, edi
0x140019879  add     rsp, 48h
0x14001987d  pop     r15
0x14001987f  pop     r14
0x140019881  pop     r13
0x140019883  pop     r12
0x140019885  pop     rdi
0x140019886  pop     rsi
0x140019887  pop     rbp
0x140019888  pop     rbx
0x140019889  retn
```
