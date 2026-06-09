# FilterSetVirtualAdapter

- ea: `0x140004568`
- end: `0x140004c47`
- name: `FilterSetVirtualAdapter`
- size: `1759`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400038f0`
- `0x14000448c`
- `0x140005bf0`

## callees

- `0x140003354`
- `0x140003854`
- `0x1400040d8`
- `0x140004568`
- `0x140004c50`
- `0x140004d70`
- `0x14000ada8`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140004693`
- `ntoskrnl!KeReleaseMutex` at `0x140004693`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400045ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400045ea`
- `NDIS!NdisWaitEvent` at `0x140004820`
- `NDIS!NdisWaitEvent` at `0x140004820`

## string_xrefs

- `0x140004bd0`: `pFilter->ConfigurableMpCtxCount <= pFilter->MpCtxCount - WFD_DEVICE_ADAPTER_INDEX - 1`
- `0x140004bdf`: `pFilter->ConfigurableMpCtxCount <= pFilter->MpCtxCount - 1`

## pseudocode

```c
__int64 __fastcall FilterSetVirtualAdapter(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int ConfigurableMpCtx; // edi
  int v4; // r15d
  char v5; // r12
  unsigned int v6; // esi
  int v8; // ecx
  __int64 v9; // rbp
  char v10; // al
  unsigned int v11; // r15d
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // r8
  const char *v22; // rcx
  int v23; // eax
  unsigned int v24; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+18h] BYREF

  v24 = a2;
  ConfigurableMpCtx = 0;
  v4 = (unsigned __int8)a3;
  v5 = 0;
  v25 = 0;
  v6 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 54, a3, v6, v4);
  }
  if ( !v6 )
    TraceAssert("ulAdapterIndex != PHYSICAL_ADAPTER_INDEX", "onecoreuap\\net\\vwifi\\filter\\filter.c", 695);
  if ( !(_BYTE)v4 )
    goto LABEL_5;
  if ( v6 == 1 )
  {
    v19 = *(_QWORD *)(a1 + 2520);
    if ( !v19 || (*(_DWORD *)(v19 + 4) & 8) == 0 )
    {
      ConfigurableMpCtx = -1073741637;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return ConfigurableMpCtx;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_18;
      v17 = 55;
      goto LABEL_62;
    }
  }
  else if ( v6 == -1 )
  {
    if ( !*(_DWORD *)(a1 + 2688) )
    {
      ConfigurableMpCtx = -1073741823;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return ConfigurableMpCtx;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_18;
      v17 = 56;
      goto LABEL_62;
    }
    ConfigurableMpCtx = FilterFindConfigurableMpCtx(a1, &v24);
    if ( ConfigurableMpCtx )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return ConfigurableMpCtx;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_18;
      v17 = 57;
      goto LABEL_62;
    }
    v6 = v24;
    v5 = 1;
    if ( v24 >= *(_DWORD *)(a1 + 2684) )
    {
      TraceAssert("ulAdapterIndex < pFilter->MpCtxCount", "onecoreuap\\net\\vwifi\\filter\\filter.c", 722);
      if ( v6 >= *(_DWORD *)(a1 + 2684) )
      {
        ConfigurableMpCtx = -1073741823;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return ConfigurableMpCtx;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_18;
        v17 = 58;
        goto LABEL_62;
      }
    }
  }
  if ( NdisWaitEvent((PNDIS_EVENT)(a1 + 2544), 0xEA60u) )
  {
LABEL_5:
    if ( v6 != -1 )
    {
      KeWaitForSingleObject((PVOID)(a1 + 2576), Executive, 0, 0, 0);
      v9 = *(_QWORD *)(a1 + 3120);
      v10 = *(_BYTE *)(v9 + 144LL * v6);
      if ( (_BYTE)v4 )
      {
        if ( v10 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
            goto LABEL_17;
          }
          v13 = 64;
        }
        else
        {
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
            McTemplateK0jz_EtwWriteTransfer(v8, (unsigned int)VWiFiEnableRequest, a1 + 2248, a1 + 2248, a1 + 160);
          if ( *(_DWORD *)(v9 + 144LL * v6 + 16) != -1 )
            TraceAssert(
              "INVALID_SERIAL_NUMBER == pFilterMpCtx->MpInfo.MpSerialNo",
              "onecoreuap\\net\\vwifi\\filter\\filter.c",
              764);
          ConfigurableMpCtx = FilterReadSerialNumber(a1, v6, &v25);
          if ( ConfigurableMpCtx )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_17;
            }
            v13 = 61;
          }
          else
          {
            v15 = v25;
            *(_DWORD *)(v9 + 144LL * v6 + 16) = v25;
            ConfigurableMpCtx = AddDevice(a1, a1 + 2640, v15, v6);
            if ( ConfigurableMpCtx )
            {
              *(_DWORD *)(v9 + 144LL * v6 + 16) = -1;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_17;
              }
              v13 = 62;
            }
            else
            {
              *(_BYTE *)(v9 + 144LL * v6) = 1;
              if ( v5 )
                --*(_DWORD *)(a1 + 2688);
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_17;
              }
              v13 = 63;
            }
          }
        }
      }
      else if ( v10 )
      {
        v11 = *(_DWORD *)(v9 + 144LL * v6 + 16);
        if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
          McTemplateK0jz_EtwWriteTransfer(v8, (unsigned int)VWiFiDisableRequest, a1 + 2248, a1 + 2248, a1 + 160);
        if ( v11 == -1 )
          TraceAssert("INVALID_SERIAL_NUMBER != ulSerialNo", "onecoreuap\\net\\vwifi\\filter\\filter.c", 806);
        ConfigurableMpCtx = RemoveDevice(a1, v11);
        if ( ConfigurableMpCtx )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_17;
          }
          v13 = 65;
          goto LABEL_76;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
        *(_DWORD *)(v9 + 144LL * v6 + 16) = -1;
        *(_BYTE *)(v9 + 144LL * v6) = 0;
        v18 = *(_DWORD *)(a1 + 2692);
        if ( v18 == 16 )
        {
          if ( v6 <= 3 )
            goto LABEL_17;
          v20 = *(_DWORD *)(a1 + 2684);
          if ( ++*(_DWORD *)(a1 + 2688) <= (unsigned int)(v20 - 4) )
            goto LABEL_17;
          v21 = 822;
          v22 = "pFilter->ConfigurableMpCtxCount <= pFilter->MpCtxCount - WFD_DEVICE_ADAPTER_INDEX - 1";
LABEL_87:
          TraceAssert(v22, "onecoreuap\\net\\vwifi\\filter\\filter.c", v21);
          goto LABEL_17;
        }
        if ( v18 == 9 )
        {
          v23 = *(_DWORD *)(a1 + 2684);
          if ( ++*(_DWORD *)(a1 + 2688) <= (unsigned int)(v23 - 1) )
            goto LABEL_17;
          v21 = 828;
          v22 = "pFilter->ConfigurableMpCtxCount <= pFilter->MpCtxCount - 1";
          goto LABEL_87;
        }
        ConfigurableMpCtx = -1073741823;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_17;
        v13 = 67;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_17;
        v13 = 68;
      }
LABEL_76:
      WPP_SF_d(v12->AttachedDevice, v13, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_17:
      KeReleaseMutex((PRKMUTEX)(a1 + 2576), 0);
      goto LABEL_18;
    }
    TraceAssert("ulAdapterIndex != NEXT_AVAILABLE_ADAPTER", "onecoreuap\\net\\vwifi\\filter\\filter.c", 741);
    ConfigurableMpCtx = -1073741811;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return ConfigurableMpCtx;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_18;
    v17 = 60;
LABEL_62:
    WPP_SF_(v16->AttachedDevice, v17, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    goto LABEL_18;
  }
  TraceAssert("FALSE", "onecoreuap\\net\\vwifi\\filter\\filter.c", 735);
  ConfigurableMpCtx = -1073676271;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return ConfigurableMpCtx;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v17 = 59;
    goto LABEL_62;
  }
LABEL_18:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return ConfigurableMpCtx;
}

```

## disassembly

```asm
0x140004568  mov     rax, rsp
0x14000456b  mov     [rax+8], rbx
0x14000456f  mov     [rax+10h], edx
0x140004572  push    rbp
0x140004573  push    rsi
0x140004574  push    rdi
0x140004575  push    r12
0x140004577  push    r13
0x140004579  push    r14
0x14000457b  push    r15
0x14000457d  sub     rsp, 30h
0x140004581  xor     edi, edi
0x140004583  movzx   r15d, r8b
0x140004587  xor     r12b, r12b
0x14000458a  mov     [rax+18h], edi
0x14000458d  mov     esi, edx
0x14000458f  mov     rbx, rcx
0x140004592  mov     rcx, cs:WPP_GLOBAL_Control
0x140004599  lea     r14, WPP_GLOBAL_Control
0x1400045a0  lea     r13, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400045a7  cmp     rcx, r14
0x1400045aa  jnz     loc_1400046E7
0x1400045b0  test    esi, esi
0x1400045b2  jz      loc_140004940
0x1400045b8  mov     ebp, 1
0x1400045bd  test    r15b, r15b
0x1400045c0  jnz     loc_1400047D1
0x1400045c6  cmp     esi, 0FFFFFFFFh
0x1400045c9  jz      loc_140004A4E
0x1400045cf  lea     r13, [rbx+0A10h]
0x1400045d6  mov     [rsp+68h+Timeout], 0; Timeout
0x1400045df  mov     rcx, r13; Object
0x1400045e2  xor     r9d, r9d; Alertable
0x1400045e5  xor     r8d, r8d; WaitMode
0x1400045e8  xor     edx, edx; WaitReason
0x1400045ea  call    cs:__imp_KeWaitForSingleObject
0x1400045f1  nop     dword ptr [rax+rax+00h]
0x1400045f6  mov     rbp, [rbx+0C30h]
0x1400045fd  mov     eax, esi
0x1400045ff  lea     r14, [rax+rax*8]
0x140004603  add     r14, r14
0x140004606  mov     al, [rbp+r14*8+0]
0x14000460b  test    r15b, r15b
0x14000460e  jnz     loc_140004728
0x140004614  test    al, al
0x140004616  jz      short loc_140004677
0x140004618  mov     r15d, [rbp+r14*8+10h]
0x14000461d  mov     r12d, 1
0x140004623  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, r12b
0x14000462a  jnz     loc_140004B41
0x140004630  cmp     r15d, 0FFFFFFFFh
0x140004634  jz      loc_140004B68
0x14000463a  mov     edx, r15d
0x14000463d  mov     rcx, rbx
0x140004640  call    RemoveDevice
0x140004645  mov     edi, eax
0x140004647  test    eax, eax
0x140004649  jz      loc_1400048A4
0x14000464f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004656  lea     r14, WPP_GLOBAL_Control
0x14000465d  cmp     rcx, r14
0x140004660  jz      short loc_14000468E
0x140004662  mov     eax, [rcx+2Ch]
0x140004665  test    r12b, al
0x140004668  jz      short loc_14000468E
0x14000466a  mov     edx, 41h ; 'A'
0x14000466f  mov     r9d, edi
0x140004672  jmp     loc_140004AB6
0x140004677  mov     rcx, cs:WPP_GLOBAL_Control
0x14000467e  lea     r14, WPP_GLOBAL_Control
0x140004685  cmp     rcx, r14
0x140004688  jnz     loc_140004915
0x14000468e  xor     edx, edx; Wait
0x140004690  mov     rcx, r13; Mutex
0x140004693  call    cs:__imp_KeReleaseMutex
0x14000469a  nop     dword ptr [rax+rax+00h]
0x14000469f  lea     r13, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400046a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ad  cmp     rcx, r14
0x1400046b0  jnz     short loc_1400046CA
0x1400046b2  mov     rbx, [rsp+68h+arg_0]
0x1400046b7  mov     eax, edi
0x1400046b9  add     rsp, 30h
0x1400046bd  pop     r15
0x1400046bf  pop     r14
0x1400046c1  pop     r13
0x1400046c3  pop     r12
0x1400046c5  pop     rdi
0x1400046c6  pop     rsi
0x1400046c7  pop     rbp
0x1400046c8  retn
0x1400046ca  mov     eax, [rcx+2Ch]
0x1400046cd  test    al, 20h
0x1400046cf  jz      short loc_1400046B2
0x1400046d1  mov     rcx, [rcx+18h]
0x1400046d5  mov     edx, 45h ; 'E'
0x1400046da  mov     r9d, edi
0x1400046dd  mov     r8, r13
0x1400046e0  call    WPP_SF_d
0x1400046e5  jmp     short loc_1400046B2
0x1400046e7  mov     eax, [rcx+2Ch]
0x1400046ea  test    al, 20h
0x1400046ec  jnz     loc_14000492A
0x1400046f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046f9  cmp     rcx, r14
0x1400046fc  jz      loc_1400045B0
0x140004702  mov     eax, [rcx+2Ch]
0x140004705  test    al, 20h
0x140004707  jz      loc_1400045B0
0x14000470d  mov     rcx, [rcx+18h]
0x140004711  mov     edx, 36h ; '6'
0x140004716  mov     r9d, esi
0x140004719  mov     dword ptr [rsp+68h+Timeout], r15d
0x14000471e  call    WPP_SF_Dd
0x140004723  jmp     loc_1400045B0
0x140004728  test    al, al
0x14000472a  jnz     loc_140004B1D
0x140004730  test    byte ptr cs:WPP_MAIN_CB.Dpc.SystemArgument1, 1
0x140004737  jnz     loc_1400048EE
0x14000473d  cmp     dword ptr [rbp+r14*8+10h], 0FFFFFFFFh
0x140004743  jnz     loc_140004A8D
0x140004749  lea     r8, [rsp+68h+arg_10]
0x140004751  mov     edx, esi
0x140004753  mov     rcx, rbx
0x140004756  call    FilterReadSerialNumber
0x14000475b  mov     edi, eax
0x14000475d  test    eax, eax
0x14000475f  jnz     loc_140004878
0x140004765  mov     r15d, [rsp+68h+arg_10]
0x14000476d  lea     rdx, [rbx+0A50h]
0x140004774  mov     r8d, r15d
0x140004777  mov     [rbp+r14*8+10h], r15d
0x14000477c  mov     r9d, esi
0x14000477f  mov     rcx, rbx
0x140004782  call    AddDevice
0x140004787  mov     edi, eax
0x140004789  test    eax, eax
0x14000478b  jnz     loc_140004ACB
0x140004791  mov     byte ptr [rbp+r14*8+0], 1
0x140004797  test    r12b, r12b
0x14000479a  jz      short loc_1400047A2
0x14000479c  dec     dword ptr [rbx+0A80h]
0x1400047a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047a9  lea     r14, WPP_GLOBAL_Control
0x1400047b0  cmp     rcx, r14
0x1400047b3  jz      loc_14000468E
0x1400047b9  mov     eax, [rcx+2Ch]
0x1400047bc  test    al, 4
0x1400047be  jz      loc_14000468E
0x1400047c4  mov     edx, 3Fh ; '?'
0x1400047c9  mov     r9d, r15d
0x1400047cc  jmp     loc_140004B08
0x1400047d1  cmp     esi, ebp
0x1400047d3  jz      loc_14000495E
0x1400047d9  cmp     esi, 0FFFFFFFFh
0x1400047dc  jnz     short loc_140004814
0x1400047de  cmp     [rbx+0A80h], edi
0x1400047e4  jz      loc_1400049B3
0x1400047ea  lea     rdx, [rsp+68h+arg_8]
0x1400047ef  mov     rcx, rbx
0x1400047f2  call    FilterFindConfigurableMpCtx
0x1400047f7  mov     edi, eax
0x1400047f9  test    eax, eax
0x1400047fb  jnz     loc_1400049DB
0x140004801  mov     esi, [rsp+68h+arg_8]
0x140004805  mov     r12b, bpl
0x140004808  cmp     esi, [rbx+0A7Ch]
0x14000480e  jnb     loc_1400049FE
0x140004814  lea     rcx, [rbx+9F0h]; Event
0x14000481b  mov     edx, 0EA60h; MsToWait
0x140004820  call    cs:__imp_NdisWaitEvent
0x140004827  nop     dword ptr [rax+rax+00h]
0x14000482c  test    al, al
0x14000482e  jnz     loc_1400045C6
0x140004834  mov     r8d, 2DFh
0x14000483a  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140004841  lea     rcx, aFalse; "FALSE"
0x140004848  call    TraceAssert
0x14000484d  mov     edi, 0C0010011h
0x140004852  mov     rcx, cs:WPP_GLOBAL_Control
0x140004859  cmp     rcx, r14
0x14000485c  jz      loc_1400046B2
0x140004862  mov     eax, [rcx+2Ch]
0x140004865  test    bpl, al
0x140004868  jz      loc_1400046A6
0x14000486e  mov     edx, 3Bh ; ';'
0x140004873  jmp     loc_1400049A2
0x140004878  mov     rcx, cs:WPP_GLOBAL_Control
0x14000487f  lea     r14, WPP_GLOBAL_Control
0x140004886  cmp     rcx, r14
0x140004889  jz      loc_14000468E
0x14000488f  mov     eax, [rcx+2Ch]
0x140004892  test    al, 1
0x140004894  jz      loc_14000468E
0x14000489a  mov     edx, 3Dh ; '='
0x14000489f  jmp     loc_14000466F
0x1400048a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048ab  lea     rax, WPP_GLOBAL_Control
0x1400048b2  cmp     rcx, rax
0x1400048b5  jnz     loc_140004B86
0x1400048bb  mov     dword ptr [rbp+r14*8+10h], 0FFFFFFFFh
0x1400048c4  mov     byte ptr [rbp+r14*8+0], 0
0x1400048ca  mov     eax, [rbx+0A84h]
0x1400048d0  cmp     eax, 10h
0x1400048d3  jnz     loc_140004BF7
0x1400048d9  cmp     esi, 3
0x1400048dc  ja      loc_140004BAE
0x1400048e2  lea     r14, WPP_GLOBAL_Control
0x1400048e9  jmp     loc_14000468E
0x1400048ee  lea     r8, [rbx+8C8h]
0x1400048f5  lea     rax, [rbx+0A0h]
0x1400048fc  mov     r9, r8
0x1400048ff  lea     rdx, VWiFiEnableRequest
0x140004906  mov     [rsp+68h+Timeout], rax
0x14000490b  call    McTemplateK0jz_EtwWriteTransfer
0x140004910  jmp     loc_14000473D
0x140004915  mov     eax, [rcx+2Ch]
0x140004918  test    al, 4
0x14000491a  jz      loc_14000468E
0x140004920  mov     edx, 44h ; 'D'
0x140004925  jmp     loc_140004B05
0x14000492a  mov     rcx, [rcx+18h]
0x14000492e  mov     edx, 35h ; '5'
0x140004933  mov     r8, r13
0x140004936  call    WPP_SF_
0x14000493b  jmp     loc_1400046F2
0x140004940  mov     r8d, 2B7h
0x140004946  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000494d  lea     rcx, aUladapterindex; "ulAdapterIndex != PHYSICAL_ADAPTER_INDE"...
0x140004954  call    TraceAssert
0x140004959  jmp     loc_1400045B8
0x14000495e  mov     rax, [rbx+9D8h]
0x140004965  test    rax, rax
0x140004968  jz      short loc_140004975
0x14000496a  mov     eax, [rax+4]
0x14000496d  test    al, 8
0x14000496f  jnz     loc_140004814
0x140004975  mov     edi, 0C00000BBh
0x14000497a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004981  cmp     rcx, r14
0x140004984  jz      loc_1400046B2
0x14000498a  mov     eax, [rcx+2Ch]
0x14000498d  test    bpl, al
0x140004990  jz      loc_1400046A6
0x140004996  mov     edx, 37h ; '7'
0x14000499b  jmp     short loc_1400049A2
0x14000499d  mov     edx, 3Ch ; '<'
0x1400049a2  mov     rcx, [rcx+18h]
0x1400049a6  mov     r8, r13
0x1400049a9  call    WPP_SF_
0x1400049ae  jmp     loc_1400046A6
0x1400049b3  mov     edi, 0C0000001h
0x1400049b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049bf  cmp     rcx, r14
0x1400049c2  jz      loc_1400046B2
0x1400049c8  mov     eax, [rcx+2Ch]
0x1400049cb  test    bpl, al
0x1400049ce  jz      loc_1400046A6
0x1400049d4  mov     edx, 38h ; '8'
0x1400049d9  jmp     short loc_1400049A2
0x1400049db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049e2  cmp     rcx, r14
0x1400049e5  jz      loc_1400046B2
0x1400049eb  mov     edx, [rcx+2Ch]
0x1400049ee  test    bpl, dl
0x1400049f1  jz      loc_1400046A6
0x1400049f7  mov     edx, 39h ; '9'
0x1400049fc  jmp     short loc_1400049A2
0x1400049fe  mov     r8d, 2D2h
0x140004a04  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140004a0b  lea     rcx, aUladapterindex_0; "ulAdapterIndex < pFilter->MpCtxCount"
0x140004a12  call    TraceAssert
0x140004a17  cmp     esi, [rbx+0A7Ch]
0x140004a1d  jb      loc_140004814
0x140004a23  mov     edi, 0C0000001h
0x140004a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a2f  cmp     rcx, r14
0x140004a32  jz      loc_1400046B2
0x140004a38  mov     eax, [rcx+2Ch]
0x140004a3b  test    bpl, al
0x140004a3e  jz      loc_1400046A6
0x140004a44  mov     edx, 3Ah ; ':'
0x140004a49  jmp     loc_1400049A2
0x140004a4e  mov     r8d, 2E5h
0x140004a54  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140004a5b  lea     rcx, aUladapterindex_1; "ulAdapterIndex != NEXT_AVAILABLE_ADAPTE"...
0x140004a62  call    TraceAssert
0x140004a67  mov     edi, 0C000000Dh
0x140004a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a73  cmp     rcx, r14
0x140004a76  jz      loc_1400046B2
0x140004a7c  mov     eax, [rcx+2Ch]
0x140004a7f  test    bpl, al
0x140004a82  jz      loc_1400046A6
0x140004a88  jmp     loc_14000499D
0x140004a8d  mov     r8d, 2FCh
0x140004a93  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x140004a9a  lea     rcx, aInvalidSerialN_1; "INVALID_SERIAL_NUMBER == pFilterMpCtx->"...
0x140004aa1  call    TraceAssert
0x140004aa6  jmp     loc_140004749
  ... truncated ...
```
