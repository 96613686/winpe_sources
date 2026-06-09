# WfpAleEndpointCreationHandler

- ea: `0x14001fdc0`
- end: `0x1400201cb`
- name: `WfpAleEndpointCreationHandler`
- size: `1035`
- prototype: ``
- caller_count: `9`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001ebd0`
- `0x14001f030`
- `0x14001f820`
- `0x14001fc70`
- `0x140021b50`
- `0x1401224a0`
- `0x140183e90`
- `0x1401a0b00`
- `0x1401a4210`

## callees

- `0x140014480`
- `0x1400162f0`
- `0x14001fdc0`
- `0x140063930`
- `0x1400639b4`
- `0x1400ad6a0`
- `0x1400c3d2c`
- `0x14013b610`
- `0x14014eafc`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeIsExecutingDpc` at `0x14001fed5`
- `ntoskrnl!KeIsExecutingDpc` at `0x14001fed5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140020076`
- `ntoskrnl!KeInitializeSpinLock` at `0x140020076`
- `ntoskrnl!PsGetProcessSessionId` at `0x14001fe8f`
- `ntoskrnl!PsGetProcessSessionId` at `0x14001fe8f`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x14001fea1`
- `NDIS!NdisGetSessionToCompartmentMappingEpochAndZero` at `0x14001fea1`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14001feff`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14001feff`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001fec7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001feee`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001fec7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001feee`

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
  int IsEnabledDeviceUsageNoInline; // eax
  bool v25; // zf
  KSPIN_LOCK v26; // rax
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
          IsEnabledDeviceUsageNoInline = Feature_5988_5730__private_IsEnabledDeviceUsageNoInline();
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
            v25 = gAleDebugEnabled == 0;
            *((_DWORD *)v14 + 2) = 0;
            v14[2] = 0;
            v14[3] = 0;
            v14[18] = (KSPIN_LOCK)WfpAlepEndpointCleanup;
            *((_DWORD *)v14 + 32) = 1;
            *((_WORD *)v14 + 66) = 0;
            v14[17] = (KSPIN_LOCK)v14;
            if ( v25 )
            {
              v14[19] = 0xBADBADFABADBADFAuLL;
            }
            else
            {
              if ( WfpPoolAllocNonPaged(80, 1919247937, v14 + 19) )
                v14[19] = 0xBADBADFABADBADFAuLL;
              if ( gAleDebugEnabled )
              {
                v26 = v14[19];
                if ( v26 != 0xBADBADFABADBADFAuLL )
                  _InterlockedIncrement((volatile signed __int32 *)(v26 + 4));
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
0x14001fdc0  push    rbx
0x14001fdc2  push    rbp
0x14001fdc3  push    rsi
0x14001fdc4  push    rdi
0x14001fdc5  push    r12
0x14001fdc7  push    r13
0x14001fdc9  push    r14
0x14001fdcb  push    r15
0x14001fdcd  sub     rsp, 48h
0x14001fdd1  mov     r12, [rsp+88h+arg_40]
0x14001fdd9  xor     r13d, r13d
0x14001fddc  movzx   r14d, dx
0x14001fde0  mov     [rsp+88h+SpinLock], r13
0x14001fde5  mov     rsi, rcx
0x14001fde8  lea     rdx, [rsp+88h+SpinLock]
0x14001fded  mov     ebp, r9d
0x14001fdf0  movzx   r15d, r8w
0x14001fdf4  mov     [r12], r13
0x14001fdf8  mov     rcx, cs:endpointPPLookasideList
0x14001fdff  call    WfpAllocateFromPerProcessorLookasideList
0x14001fe04  mov     rbx, [rsp+88h+SpinLock]
0x14001fe09  mov     rdi, rax
0x14001fe0c  test    rax, rax
0x14001fe0f  jnz     loc_1400201AA
0x14001fe15  xor     edx, edx; Val
0x14001fe17  mov     r8d, 2F0h; Size
0x14001fe1d  mov     rcx, rbx; void *
0x14001fe20  call    memset
0x14001fe25  mov     rax, [rsp+88h+arg_38]
0x14001fe2d  mov     [rbx+160h], rax
0x14001fe34  test    rsi, rsi
0x14001fe37  jnz     loc_140020005
0x14001fe3d  xor     r9d, r9d
0x14001fe40  lea     rax, [rbx+168h]
0x14001fe47  mov     r8d, r13d
0x14001fe4a  mov     [rsp+88h+var_60], rax
0x14001fe4f  cmp     r15w, 3
0x14001fe54  mov     [rsp+88h+var_68], r13d
0x14001fe59  mov     edx, ebp
0x14001fe5b  movzx   ecx, r14w
0x14001fe5f  setz    r8b
0x14001fe63  call    WfpAleInitializeEpochContext
0x14001fe68  mov     rdi, rax
0x14001fe6b  test    rax, rax
0x14001fe6e  jnz     loc_1400201AA
0x14001fe74  lock or dword ptr [rbx+30h], 1000h
0x14001fe7c  mov     rdi, [rsp+88h+arg_20]
0x14001fe84  mov     [rbx+3Ch], r14w
0x14001fe89  mov     rcx, rdi
0x14001fe8c  mov     [rbx+28h], ebp
0x14001fe8f  call    cs:__imp_PsGetProcessSessionId
0x14001fe96  nop     dword ptr [rax+rax+00h]
0x14001fe9b  mov     [rbx+1F8h], eax
0x14001fea1  call    cs:__imp_NdisGetSessionToCompartmentMappingEpochAndZero
0x14001fea8  nop     dword ptr [rax+rax+00h]
0x14001fead  mov     rsi, [rsp+88h+arg_28]
0x14001feb5  btr     eax, 1Fh
0x14001feb9  mov     [rbx+260h], eax
0x14001febf  test    rsi, rsi
0x14001fec2  jz      short loc_14001FED5
0x14001fec4  mov     rcx, rsi
0x14001fec7  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001fece  nop     dword ptr [rax+rax+00h]
0x14001fed3  jmp     short loc_14001FF0B
0x14001fed5  call    cs:__imp_KeIsExecutingDpc
0x14001fedc  nop     dword ptr [rax+rax+00h]
0x14001fee1  test    eax, eax
0x14001fee3  jnz     short loc_14001FEFC
0x14001fee5  mov     rcx, gs:188h
0x14001feee  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001fef5  nop     dword ptr [rax+rax+00h]
0x14001fefa  jmp     short loc_14001FF0B
0x14001fefc  mov     rcx, rdi
0x14001feff  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x14001ff06  nop     dword ptr [rax+rax+00h]
0x14001ff0b  mov     [rbx+264h], eax
0x14001ff11  cmp     ebp, 6
0x14001ff14  jnz     short loc_14001FF1D
0x14001ff16  mov     eax, [rbx+30h]
0x14001ff19  test    al, 10h
0x14001ff1b  jz      short loc_14001FF49
0x14001ff1d  mov     eax, [rbx+30h]
0x14001ff20  test    al, 40h
0x14001ff22  jz      short loc_14001FF29
0x14001ff24  lock and dword ptr [rbx+30h], 0FFFFFFBFh
0x14001ff29  mov     eax, [rbx+30h]
0x14001ff2c  test    al, al
0x14001ff2e  jns     short loc_14001FF38
0x14001ff30  lock and dword ptr [rbx+30h], 0FFFFFF7Fh
0x14001ff38  mov     eax, [rbx+34h]
0x14001ff3b  bt      eax, 12h
0x14001ff3f  jnb     short loc_14001FF49
0x14001ff41  lock and dword ptr [rbx+34h], 0FFFBFFFFh
0x14001ff49  cmp     r15w, 3
0x14001ff4e  jnz     short loc_14001FF55
0x14001ff50  lock or dword ptr [rbx+30h], 10h
0x14001ff55  mov     r8, rsi
0x14001ff58  mov     rdx, rdi
0x14001ff5b  mov     rcx, rbx
0x14001ff5e  call    WfpAleCaptureSecurityInformation
0x14001ff63  mov     rdi, rax
0x14001ff66  test    rax, rax
0x14001ff69  jnz     loc_1400201AA
0x14001ff6f  mov     rax, [rsp+88h+arg_30]
0x14001ff77  mov     [rbx+258h], rax
0x14001ff7e  cmp     ebp, 6
0x14001ff81  jnz     short loc_14001FF8A
0x14001ff83  mov     eax, [rbx+30h]
0x14001ff86  test    al, 10h
0x14001ff88  jz      short loc_140020000
0x14001ff8a  mov     rax, cs:pRemoteEndpointTable
0x14001ff91  lea     r8, [rbx+228h]
0x14001ff98  mov     edx, 54736C41h
0x14001ff9d  mov     ecx, [rax+4]
0x14001ffa0  shl     rcx, 4
0x14001ffa4  call    WfpPoolAllocNonPaged
0x14001ffa9  mov     rdi, rax
0x14001ffac  test    rax, rax
0x14001ffaf  jnz     loc_1400201AA
0x14001ffb5  mov     rax, cs:pRemoteEndpointTable
0x14001ffbc  mov     edx, r13d
0x14001ffbf  cmp     [rax+4], r13d
0x14001ffc3  jbe     short loc_14001FFF2
0x14001ffc5  nop     word ptr [rax+rax+00000000h]
0x14001ffd0  mov     ecx, edx
0x14001ffd2  inc     edx
0x14001ffd4  shl     rcx, 4
0x14001ffd8  add     rcx, [rbx+228h]
0x14001ffdf  mov     [rcx+8], rcx
0x14001ffe3  mov     [rcx], rcx
0x14001ffe6  mov     rax, cs:pRemoteEndpointTable
0x14001ffed  cmp     edx, [rax+4]
0x14001fff0  jb      short loc_14001FFD0
0x14001fff2  lea     rax, [rbx+248h]
0x14001fff9  mov     [rax+8], rax
0x14001fffd  mov     [rax], rax
0x140020000  mov     bpl, 1
0x140020003  jmp     short loc_14002006C
0x140020005  mov     [rbx+3Ch], r14w
0x14002000a  mov     edx, 2
0x14002000f  mov     rcx, rsi
0x140020012  mov     [rbx+28h], ebp
0x140020015  call    WfpAleReferenceEndpoint_0
0x14002001a  test    al, al
0x14002001c  jz      loc_140020161
0x140020022  mov     [rbx+220h], rsi
0x140020029  xor     bpl, bpl
0x14002002c  mov     eax, [rsi+260h]
0x140020032  mov     [rbx+260h], eax
0x140020038  mov     eax, [rsi+264h]
0x14002003e  mov     [rbx+264h], eax
0x140020044  mov     [rbx+30h], r13d
0x140020048  mov     eax, cs:Feature_5988_5730__private_featureState
0x14002004e  test    al, 10h
0x140020050  jz      short loc_140020057
0x140020052  and     eax, 1
0x140020055  jmp     short loc_14002005C
0x140020057  call    Feature_5988_5730__private_IsEnabledDeviceUsageNoInline
0x14002005c  test    eax, eax
0x14002005e  jz      short loc_14002006C
0x140020060  mov     eax, [rsi+38h]
0x140020063  test    al, 8
0x140020065  jz      short loc_14002006C
0x140020067  lock or dword ptr [rbx+38h], 8
0x14002006c  mov     rcx, rbx; SpinLock
0x14002006f  mov     [rbx+0C8h], r13d
0x140020076  call    cs:__imp_KeInitializeSpinLock
0x14002007d  nop     dword ptr [rax+rax+00h]
0x140020082  cmp     cs:gAleDebugEnabled, r13b
0x140020089  lea     rax, WfpAlepEndpointCleanup
0x140020090  mov     [rbx+8], r13d
0x140020094  mov     [rbx+10h], r13
0x140020098  mov     [rbx+18h], r13
0x14002009c  mov     [rbx+90h], rax
0x1400200a3  mov     dword ptr [rbx+80h], 1
0x1400200ad  mov     [rbx+84h], r13w
0x1400200b5  mov     [rbx+88h], rbx
0x1400200bc  jz      short loc_140020105
0x1400200be  lea     r8, [rbx+98h]
0x1400200c5  mov     edx, 72656641h
0x1400200ca  mov     ecx, 50h ; 'P'
0x1400200cf  call    WfpPoolAllocNonPaged
0x1400200d4  mov     rcx, 0BADBADFABADBADFAh
0x1400200de  test    rax, rax
0x1400200e1  jz      short loc_1400200EA
0x1400200e3  mov     [rbx+98h], rcx
0x1400200ea  cmp     cs:gAleDebugEnabled, r13b
0x1400200f1  jz      short loc_140020116
0x1400200f3  mov     rax, [rbx+98h]
0x1400200fa  cmp     rax, rcx
0x1400200fd  jz      short loc_140020116
0x1400200ff  lock inc dword ptr [rax+4]
0x140020103  jmp     short loc_140020116
0x140020105  mov     rcx, 0BADBADFABADBADFAh
0x14002010f  mov     [rbx+98h], rcx
0x140020116  lea     rax, [rbx+80h]
0x14002011d  mov     [rsp+88h+arg_40], rax
0x140020125  mov     r8, [rsp+88h+arg_40]
0x14002012d  mov     eax, [r8]
0x140020130  lea     ecx, [rax+4]
0x140020133  mov     edx, ecx
0x140020135  xor     edx, eax
0x140020137  and     edx, 3
0x14002013a  xor     edx, ecx
0x14002013c  mov     [r8], edx
0x14002013f  test    bpl, bpl
0x140020142  jz      short loc_14002014C
0x140020144  lock or dword ptr [rbx+30h], 200h
0x14002014c  lock or dword ptr [rbx+30h], 1
0x140020151  mov     [rbx+270h], r13
0x140020158  mov     eax, r13d
0x14002015b  mov     [r12], rbx
0x14002015f  jmp     short loc_1400201B9
0x140020161  mov     rcx, cs:WPP_GLOBAL_Control
0x140020168  lea     rax, WPP_GLOBAL_Control
0x14002016f  mov     rdi, 0FFFFFFFFC0000001h
0x140020176  cmp     rcx, rax
0x140020179  jz      short loc_1400201AA
0x14002017b  cmp     byte ptr [rcx+29h], 2
0x14002017f  jb      short loc_1400201AA
0x140020181  test    dword ptr [rcx+2Ch], 1000h
0x140020188  jz      short loc_1400201AA
0x14002018a  mov     rcx, [rcx+18h]
0x14002018e  lea     r9, aWfpaleendpoint; "WfpAleEndpointCreationHandler"
0x140020195  mov     edx, 0Ah
0x14002019a  mov     [rsp+88h+var_68], edi
0x14002019e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400201a5  call    WPP_SF_sd
0x1400201aa  test    rbx, rbx
0x1400201ad  jz      short loc_1400201B7
0x1400201af  mov     rcx, rbx; SpinLock
0x1400201b2  call    WfpAlepEndpointCleanup
0x1400201b7  mov     eax, edi
0x1400201b9  add     rsp, 48h
0x1400201bd  pop     r15
0x1400201bf  pop     r14
0x1400201c1  pop     r13
0x1400201c3  pop     r12
0x1400201c5  pop     rdi
0x1400201c6  pop     rsi
0x1400201c7  pop     rbp
0x1400201c8  pop     rbx
0x1400201c9  retn
```
