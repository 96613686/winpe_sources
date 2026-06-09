# WfpAleEndpointCreationHandler

- ea: `0x140019720`
- end: `0x140019b2b`
- name: `WfpAleEndpointCreationHandler`
- size: `1035`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400175b0`
- `0x140018e70`
- `0x140019180`
- `0x1400195d0`
- `0x140118360`
- `0x140182320`
- `0x14019ee80`
- `0x1401a2590`

## callees

- `0x140019720`
- `0x140053bb0`
- `0x140055a20`
- `0x140077790`
- `0x140077814`
- `0x14008b220`
- `0x1400ba1fc`
- `0x1401364b0`
- `0x14014cf54`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeIsExecutingDpc` at `0x140019835`
- `ntoskrnl!KeIsExecutingDpc` at `0x140019835`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400199d6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400199d6`
- `ntoskrnl!PsGetProcessSessionId` at `0x1400197ef`
- `ntoskrnl!PsGetProcessSessionId` at `0x1400197ef`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x140019801`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x140019801`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14001985f`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14001985f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140019827`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001984e`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140019827`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001984e`

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
          (unsigned int)&WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
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
0x140019720  push    rbx
0x140019722  push    rbp
0x140019723  push    rsi
0x140019724  push    rdi
0x140019725  push    r12
0x140019727  push    r13
0x140019729  push    r14
0x14001972b  push    r15
0x14001972d  sub     rsp, 48h
0x140019731  mov     r12, [rsp+88h+arg_40]
0x140019739  xor     r13d, r13d
0x14001973c  movzx   r14d, dx
0x140019740  mov     [rsp+88h+SpinLock], r13
0x140019745  mov     rsi, rcx
0x140019748  lea     rdx, [rsp+88h+SpinLock]
0x14001974d  mov     ebp, r9d
0x140019750  movzx   r15d, r8w
0x140019754  mov     [r12], r13
0x140019758  mov     rcx, cs:endpointPPLookasideList
0x14001975f  call    WfpAllocateFromPerProcessorLookasideList
0x140019764  mov     rbx, [rsp+88h+SpinLock]
0x140019769  mov     rdi, rax
0x14001976c  test    rax, rax
0x14001976f  jnz     loc_140019B0A
0x140019775  xor     edx, edx; Val
0x140019777  mov     r8d, 2F0h; Size
0x14001977d  mov     rcx, rbx; void *
0x140019780  call    memset
0x140019785  mov     rax, [rsp+88h+arg_38]
0x14001978d  mov     [rbx+160h], rax
0x140019794  test    rsi, rsi
0x140019797  jnz     loc_140019965
0x14001979d  xor     r9d, r9d
0x1400197a0  lea     rax, [rbx+168h]
0x1400197a7  mov     r8d, r13d
0x1400197aa  mov     [rsp+88h+var_60], rax
0x1400197af  cmp     r15w, 3
0x1400197b4  mov     [rsp+88h+var_68], r13d
0x1400197b9  mov     edx, ebp
0x1400197bb  movzx   ecx, r14w
0x1400197bf  setz    r8b
0x1400197c3  call    WfpAleInitializeEpochContext
0x1400197c8  mov     rdi, rax
0x1400197cb  test    rax, rax
0x1400197ce  jnz     loc_140019B0A
0x1400197d4  lock or dword ptr [rbx+30h], 1000h
0x1400197dc  mov     rdi, [rsp+88h+arg_20]
0x1400197e4  mov     [rbx+3Ch], r14w
0x1400197e9  mov     rcx, rdi
0x1400197ec  mov     [rbx+28h], ebp
0x1400197ef  call    cs:__imp_PsGetProcessSessionId
0x1400197f6  nop     dword ptr [rax+rax+00h]
0x1400197fb  mov     [rbx+1F8h], eax
0x140019801  call    cs:__imp_NdisGetSessionToCompartmentMappingEpochAndZero
0x140019808  nop     dword ptr [rax+rax+00h]
0x14001980d  mov     rsi, [rsp+88h+arg_28]
0x140019815  btr     eax, 1Fh
0x140019819  mov     [rbx+260h], eax
0x14001981f  test    rsi, rsi
0x140019822  jz      short loc_140019835
0x140019824  mov     rcx, rsi
0x140019827  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001982e  nop     dword ptr [rax+rax+00h]
0x140019833  jmp     short loc_14001986B
0x140019835  call    cs:__imp_KeIsExecutingDpc
0x14001983c  nop     dword ptr [rax+rax+00h]
0x140019841  test    eax, eax
0x140019843  jnz     short loc_14001985C
0x140019845  mov     rcx, gs:188h
0x14001984e  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140019855  nop     dword ptr [rax+rax+00h]
0x14001985a  jmp     short loc_14001986B
0x14001985c  mov     rcx, rdi
0x14001985f  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x140019866  nop     dword ptr [rax+rax+00h]
0x14001986b  mov     [rbx+264h], eax
0x140019871  cmp     ebp, 6
0x140019874  jnz     short loc_14001987D
0x140019876  mov     eax, [rbx+30h]
0x140019879  test    al, 10h
0x14001987b  jz      short loc_1400198A9
0x14001987d  mov     eax, [rbx+30h]
0x140019880  test    al, 40h
0x140019882  jz      short loc_140019889
0x140019884  lock and dword ptr [rbx+30h], 0FFFFFFBFh
0x140019889  mov     eax, [rbx+30h]
0x14001988c  test    al, al
0x14001988e  jns     short loc_140019898
0x140019890  lock and dword ptr [rbx+30h], 0FFFFFF7Fh
0x140019898  mov     eax, [rbx+34h]
0x14001989b  bt      eax, 12h
0x14001989f  jnb     short loc_1400198A9
0x1400198a1  lock and dword ptr [rbx+34h], 0FFFBFFFFh
0x1400198a9  cmp     r15w, 3
0x1400198ae  jnz     short loc_1400198B5
0x1400198b0  lock or dword ptr [rbx+30h], 10h
0x1400198b5  mov     r8, rsi
0x1400198b8  mov     rdx, rdi
0x1400198bb  mov     rcx, rbx
0x1400198be  call    WfpAleCaptureSecurityInformation
0x1400198c3  mov     rdi, rax
0x1400198c6  test    rax, rax
0x1400198c9  jnz     loc_140019B0A
0x1400198cf  mov     rax, [rsp+88h+arg_30]
0x1400198d7  mov     [rbx+258h], rax
0x1400198de  cmp     ebp, 6
0x1400198e1  jnz     short loc_1400198EA
0x1400198e3  mov     eax, [rbx+30h]
0x1400198e6  test    al, 10h
0x1400198e8  jz      short loc_140019960
0x1400198ea  mov     rax, cs:pRemoteEndpointTable
0x1400198f1  lea     r8, [rbx+228h]
0x1400198f8  mov     edx, 54736C41h
0x1400198fd  mov     ecx, [rax+4]
0x140019900  shl     rcx, 4
0x140019904  call    WfpPoolAllocNonPaged
0x140019909  mov     rdi, rax
0x14001990c  test    rax, rax
0x14001990f  jnz     loc_140019B0A
0x140019915  mov     rax, cs:pRemoteEndpointTable
0x14001991c  mov     edx, r13d
0x14001991f  cmp     [rax+4], r13d
0x140019923  jbe     short loc_140019952
0x140019925  nop     word ptr [rax+rax+00000000h]
0x140019930  mov     ecx, edx
0x140019932  inc     edx
0x140019934  shl     rcx, 4
0x140019938  add     rcx, [rbx+228h]
0x14001993f  mov     [rcx+8], rcx
0x140019943  mov     [rcx], rcx
0x140019946  mov     rax, cs:pRemoteEndpointTable
0x14001994d  cmp     edx, [rax+4]
0x140019950  jb      short loc_140019930
0x140019952  lea     rax, [rbx+248h]
0x140019959  mov     [rax+8], rax
0x14001995d  mov     [rax], rax
0x140019960  mov     bpl, 1
0x140019963  jmp     short loc_1400199CC
0x140019965  mov     [rbx+3Ch], r14w
0x14001996a  mov     edx, 2
0x14001996f  mov     rcx, rsi
0x140019972  mov     [rbx+28h], ebp
0x140019975  call    WfpAleReferenceEndpoint_0
0x14001997a  test    al, al
0x14001997c  jz      loc_140019AC1
0x140019982  mov     [rbx+220h], rsi
0x140019989  xor     bpl, bpl
0x14001998c  mov     eax, [rsi+260h]
0x140019992  mov     [rbx+260h], eax
0x140019998  mov     eax, [rsi+264h]
0x14001999e  mov     [rbx+264h], eax
0x1400199a4  mov     [rbx+30h], r13d
0x1400199a8  mov     eax, cs:Feature_5988_5730__private_featureState
0x1400199ae  test    al, 10h
0x1400199b0  jz      short loc_1400199B7
0x1400199b2  and     eax, 1
0x1400199b5  jmp     short loc_1400199BC
0x1400199b7  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x1400199bc  test    eax, eax
0x1400199be  jz      short loc_1400199CC
0x1400199c0  mov     eax, [rsi+38h]
0x1400199c3  test    al, 8
0x1400199c5  jz      short loc_1400199CC
0x1400199c7  lock or dword ptr [rbx+38h], 8
0x1400199cc  mov     rcx, rbx; SpinLock
0x1400199cf  mov     [rbx+0C8h], r13d
0x1400199d6  call    cs:__imp_KeInitializeSpinLock
0x1400199dd  nop     dword ptr [rax+rax+00h]
0x1400199e2  cmp     cs:gAleDebugEnabled, r13b
0x1400199e9  lea     rax, WfpAlepEndpointCleanup
0x1400199f0  mov     [rbx+8], r13d
0x1400199f4  mov     [rbx+10h], r13
0x1400199f8  mov     [rbx+18h], r13
0x1400199fc  mov     [rbx+90h], rax
0x140019a03  mov     dword ptr [rbx+80h], 1
0x140019a0d  mov     [rbx+84h], r13w
0x140019a15  mov     [rbx+88h], rbx
0x140019a1c  jz      short loc_140019A65
0x140019a1e  lea     r8, [rbx+98h]
0x140019a25  mov     edx, 72656641h
0x140019a2a  mov     ecx, 50h ; 'P'
0x140019a2f  call    WfpPoolAllocNonPaged
0x140019a34  mov     rcx, 0BADBADFABADBADFAh
0x140019a3e  test    rax, rax
0x140019a41  jz      short loc_140019A4A
0x140019a43  mov     [rbx+98h], rcx
0x140019a4a  cmp     cs:gAleDebugEnabled, r13b
0x140019a51  jz      short loc_140019A76
0x140019a53  mov     rax, [rbx+98h]
0x140019a5a  cmp     rax, rcx
0x140019a5d  jz      short loc_140019A76
0x140019a5f  lock inc dword ptr [rax+4]
0x140019a63  jmp     short loc_140019A76
0x140019a65  mov     rcx, 0BADBADFABADBADFAh
0x140019a6f  mov     [rbx+98h], rcx
0x140019a76  lea     rax, [rbx+80h]
0x140019a7d  mov     [rsp+88h+arg_40], rax
0x140019a85  mov     r8, [rsp+88h+arg_40]
0x140019a8d  mov     eax, [r8]
0x140019a90  lea     ecx, [rax+4]
0x140019a93  mov     edx, ecx
0x140019a95  xor     edx, eax
0x140019a97  and     edx, 3
0x140019a9a  xor     edx, ecx
0x140019a9c  mov     [r8], edx
0x140019a9f  test    bpl, bpl
0x140019aa2  jz      short loc_140019AAC
0x140019aa4  lock or dword ptr [rbx+30h], 200h
0x140019aac  lock or dword ptr [rbx+30h], 1
0x140019ab1  mov     [rbx+270h], r13
0x140019ab8  mov     eax, r13d
0x140019abb  mov     [r12], rbx
0x140019abf  jmp     short loc_140019B19
0x140019ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ac8  lea     rax, WPP_GLOBAL_Control
0x140019acf  mov     rdi, 0FFFFFFFFC0000001h
0x140019ad6  cmp     rcx, rax
0x140019ad9  jz      short loc_140019B0A
0x140019adb  cmp     byte ptr [rcx+29h], 2
0x140019adf  jb      short loc_140019B0A
0x140019ae1  test    dword ptr [rcx+2Ch], 1000h
0x140019ae8  jz      short loc_140019B0A
0x140019aea  mov     rcx, [rcx+18h]
0x140019aee  lea     r9, aWfpaleendpoint; "WfpAleEndpointCreationHandler"
0x140019af5  mov     edx, 0Ah
0x140019afa  mov     [rsp+88h+var_68], edi
0x140019afe  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140019b05  call    WPP_SF_sd
0x140019b0a  test    rbx, rbx
0x140019b0d  jz      short loc_140019B17
0x140019b0f  mov     rcx, rbx; SpinLock
0x140019b12  call    WfpAlepEndpointCleanup
0x140019b17  mov     eax, edi
0x140019b19  add     rsp, 48h
0x140019b1d  pop     r15
0x140019b1f  pop     r14
0x140019b21  pop     r13
0x140019b23  pop     r12
0x140019b25  pop     rdi
0x140019b26  pop     rsi
0x140019b27  pop     rbp
0x140019b28  pop     rbx
0x140019b29  retn
```
