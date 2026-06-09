# SubmitControlRequest

- ea: `0x140008640`
- end: `0x140008d80`
- name: `SubmitControlRequest`
- size: `1856`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned __int8, unsigned __int16, unsigned __int8, int, unsigned __int8 *, size_t Size, __int64, __int64)`
- caller_count: `96`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x140006640`
- `0x1400068c0`
- `0x1400069d0`
- `0x140006fb4`
- `0x1400072e8`
- `0x140007570`
- `0x14000765c`
- `0x1400079a0`
- `0x140007aa0`
- `0x140007bb0`
- `0x140007e70`
- `0x140008500`
- `0x14000a130`
- `0x14000a370`
- `0x140012b70`
- `0x140014080`
- `0x140014370`
- `0x140019570`
- `0x140019690`
- `0x140019850`
- `0x140019a90`
- `0x14001d244`
- `0x14001d4e0`
- `0x14002544c`
- `0x1400257c0`
- `0x1400259f4`
- `0x140025f90`
- `0x140026090`
- `0x140026170`
- `0x140026270`
- `0x140026380`
- `0x140026470`
- `0x140026560`
- `0x140026640`
- `0x140026720`
- `0x140026820`
- `0x140026980`
- `0x140026c30`
- `0x140026d90`
- `0x140026e90`
- `0x140026fa0`
- `0x1400271c0`
- `0x1400272f0`
- `0x140027410`
- `0x1400276e0`
- `0x140027970`
- `0x140027e00`
- `0x140028f64`
- `0x1400291e0`
- `0x140029590`

## callees

- `0x140004bac`
- `0x140005308`
- `0x140008640`
- `0x140008d90`
- `0x14000a288`
- `0x1400170d8`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d0cc`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140008947`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008947`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400087c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140008691`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140008691`

## pseudocode

```c
__int64 __fastcall SubmitControlRequest(
        unsigned __int8 a1,
        unsigned __int8 a2,
        unsigned __int16 a3,
        unsigned __int8 a4,
        int a5,
        unsigned __int8 *a6,
        size_t Size,
        __int64 a8,
        __int64 a9)
{
  unsigned int v9; // esi
  unsigned __int64 v10; // r12
  unsigned int v11; // ebp
  int v12; // r13d
  BOOL v13; // edi
  _QWORD *PoolWithTag; // rax
  _QWORD *v15; // rbx
  __int16 v16; // ax
  __int64 v17; // r15
  int v18; // edx
  __int64 v19; // r15
  int v20; // eax
  __int64 v21; // r8
  int v22; // edi
  unsigned int v23; // r15d
  unsigned int v24; // esi
  __int64 v26; // r15
  int v27; // ebp
  NTSTATUS v28; // eax
  _BYTE *v29; // rax
  char v30; // dl
  PDEVICE_OBJECT v31; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+30h] [rbp-58h] BYREF
  int v33; // [rsp+90h] [rbp+8h] BYREF

  v9 = a1;
  v10 = a3;
  v11 = a2;
  v12 = a4;
  v33 = -1073741823;
  Timeout.QuadPart = 0;
  v13 = a1 != 33;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x88u, 0x56425355u);
  v15 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x88u);
      goto LABEL_3;
    }
LABEL_16:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, a9);
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    goto LABEL_16;
LABEL_3:
  v16 = (unsigned __int8)a5;
  v17 = a9;
  v18 = v12 << 8;
  *(_DWORD *)v15 = 1769608;
  v15[6] = 0;
  *((_BYTE *)v15 + 128) = 0;
  *((_BYTE *)v15 + 129) = v11;
  LOWORD(v18) = v16 + ((_WORD)v12 << 8);
  *((_WORD *)v15 + 65) = v10;
  *((_DWORD *)v15 + 9) = Size;
  v15[5] = a6;
  *((_WORD *)v15 + 66) = v18;
  *((_DWORD *)v15 + 8) = v13;
  v15[7] = 0;
  v19 = *(_QWORD *)(v17 + 24);
  a5 = v18;
  if ( (unsigned int)Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline() )
  {
    v20 = USBVideoCallUSBD(v19, v15, 0, 0);
    v22 = v20;
    if ( v20 < 0 && *((_DWORD *)v15 + 1) == -2147481856 )
    {
      v22 = -1071710207;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))WPP_SF_qDD)(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
          *(_QWORD *)(v19 + 16),
          v20,
          -1071710207,
          (union _LARGE_INTEGER)Timeout.QuadPart);
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 8) != 0 )
        McTemplateK0p_EtwWriteTransfer(v31, USBVideo_InsufficientBandwidth, v21, 0);
    }
  }
  else
  {
    v22 = USBVideoCallUSBD(v19, v15, 0, 0);
  }
  if ( v22 >= 0 && v22 != 258 || (v23 = 0, (_BYTE)v9 == 33) )
  {
    switch ( (_DWORD)Size )
    {
      case 1:
        v23 = *a6;
        break;
      case 2:
        v23 = *(unsigned __int16 *)a6;
        break;
      case 4:
        v23 = *(_DWORD *)a6;
        break;
      default:
        v23 = 0;
        break;
    }
  }
  if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v9);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v11);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, (unsigned int)v10);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      39,
      WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids,
      (unsigned __int16)a5);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v23);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
LABEL_11:
    v24 = Size;
  }
  else
  {
    v24 = Size;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids,
        (unsigned int)Size);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids);
  }
  if ( v22 < 0 )
  {
    if ( *((_DWORD *)v15 + 1) == -1073741820 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, a9);
      v22 = RequestErrorCodeControl(
              *(_QWORD *)(a9 + 24),
              *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(a9 + 664) + 8LL) + 48LL * *(unsigned __int8 *)(a9 + 355) + 2),
              &v33);
      if ( v22 >= 0 )
        v22 = v33;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, a9, v22);
    }
  }
  else if ( v22 == 258 )
  {
    v22 = -1073741643;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids,
        a9,
        -1073741643);
  }
  else
  {
    if ( (_BYTE)v11 != 1 || (*(_BYTE *)((v10 >> 8) + a8 + 440) & 0x10) == 0 )
      goto LABEL_15;
    v26 = a9;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, a9);
    Timeout.QuadPart = -50000000;
    v27 = 0;
    while ( 1 )
    {
      v28 = KeWaitForSingleObject(*(PVOID *)(v26 + 656), Executive, 0, 0, &Timeout);
      v22 = v28;
      if ( v28 < 0 )
        goto LABEL_15;
      if ( v28 == 258 )
        break;
      v29 = *(_BYTE **)(*(_QWORD *)(v26 + 648) + 16LL);
      if ( v29[1] == (_BYTE)v12 && v29[3] == BYTE1(v10) )
      {
        v30 = v29[4];
        if ( !v30 )
        {
          memmove(a6, v29 + 5, v24);
          v22 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v26);
          goto LABEL_15;
        }
        if ( v30 != 2 )
          goto LABEL_15;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            50,
            WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids,
            v26,
            v29 + 5);
LABEL_93:
        v22 = -1073741823;
        goto LABEL_15;
      }
      if ( ++v27 >= 100 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v26);
          v22 = -1073741823;
          goto LABEL_15;
        }
        goto LABEL_93;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids, v26);
    v22 = -1073741643;
  }
LABEL_15:
  ExFreePoolWithTag(v15, 0x56425355u);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140008640  push    rbx
0x140008642  push    rbp
0x140008643  push    rsi
0x140008644  push    rdi
0x140008645  push    r12
0x140008647  push    r13
0x140008649  push    r14
0x14000864b  push    r15
0x14000864d  sub     rsp, 48h
0x140008651  movzx   esi, cl
0x140008654  xor     r14d, r14d
0x140008657  movzx   r12d, r8w
0x14000865b  cmp     sil, 21h ; '!'
0x14000865f  movzx   ebp, dl
0x140008662  mov     r15d, 88h
0x140008668  mov     edi, r14d
0x14000866b  movzx   r13d, r9b
0x14000866f  mov     r8d, 56425355h; Tag
0x140008675  mov     [rsp+88h+arg_0], 0C0000001h
0x140008680  mov     edx, r15d; NumberOfBytes
0x140008683  mov     qword ptr [rsp+88h+var_58], r14
0x140008688  mov     ecx, 600h; PoolType
0x14000868d  setnz   dil
0x140008691  call    cs:__imp_ExAllocatePoolWithTag
0x140008698  nop     dword ptr [rax+rax+00h]
0x14000869d  cmp     cs:ExPoolZeroingNativelySupported, r14b
0x1400086a4  mov     rbx, rax
0x1400086a7  jz      loc_1400089F7
0x1400086ad  test    rax, rax
0x1400086b0  jz      loc_1400087E5
0x1400086b6  movzx   eax, byte ptr [rsp+88h+arg_20]
0x1400086be  mov     edx, r13d
0x1400086c1  mov     r15, [rsp+88h+arg_40]
0x1400086c9  mov     ecx, 100h
0x1400086ce  imul    edx, ecx
0x1400086d1  mov     dword ptr [rbx], 1B0088h
0x1400086d7  mov     [rbx+30h], r14
0x1400086db  mov     [rbx+80h], r14b
0x1400086e2  mov     [rbx+81h], bpl
0x1400086e9  add     dx, ax
0x1400086ec  mov     [rbx+82h], r12w
0x1400086f4  mov     eax, dword ptr [rsp+88h+Size]
0x1400086fb  mov     [rbx+24h], eax
0x1400086fe  mov     rax, [rsp+88h+arg_28]
0x140008706  mov     [rbx+28h], rax
0x14000870a  mov     [rbx+84h], dx
0x140008711  mov     [rbx+20h], edi
0x140008714  mov     [rbx+38h], r14
0x140008718  mov     r15, [r15+18h]
0x14000871c  mov     [rsp+88h+arg_20], edx
0x140008723  call    Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline
0x140008728  xor     r9d, r9d
0x14000872b  lea     r14, WPP_GLOBAL_Control
0x140008732  xor     r8d, r8d
0x140008735  mov     rdx, rbx
0x140008738  mov     rcx, r15
0x14000873b  test    eax, eax
0x14000873d  jz      loc_140008A3E
0x140008743  call    USBVideoCallUSBD
0x140008748  mov     edi, eax
0x14000874a  test    eax, eax
0x14000874c  js      loc_140008A4A
0x140008752  test    edi, edi
0x140008754  js      loc_140008803
0x14000875a  cmp     edi, 102h
0x140008760  jz      loc_140008803
0x140008766  mov     eax, dword ptr [rsp+88h+Size]
0x14000876d  cmp     eax, 1
0x140008770  jz      loc_1400088C3
0x140008776  cmp     eax, 2
0x140008779  jnz     loc_1400088B2
0x14000877f  mov     rax, [rsp+88h+arg_28]
0x140008787  movzx   r15d, word ptr [rax]
0x14000878b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008792  cmp     byte ptr [rcx+29h], 5
0x140008796  jnb     loc_140008AB4
0x14000879c  mov     esi, dword ptr [rsp+88h+Size]
0x1400087a3  test    edi, edi
0x1400087a5  js      short loc_140008815
0x1400087a7  cmp     edi, 102h
0x1400087ad  jz      loc_140008C7E
0x1400087b3  cmp     bpl, 1
0x1400087b7  jz      loc_1400088D4
0x1400087bd  mov     edx, 56425355h; Tag
0x1400087c2  mov     rcx, rbx; P
0x1400087c5  call    cs:__imp_ExFreePoolWithTag
0x1400087cc  nop     dword ptr [rax+rax+00h]
0x1400087d1  mov     eax, edi
0x1400087d3  add     rsp, 48h
0x1400087d7  pop     r15
0x1400087d9  pop     r14
0x1400087db  pop     r13
0x1400087dd  pop     r12
0x1400087df  pop     rdi
0x1400087e0  pop     rsi
0x1400087e1  pop     rbp
0x1400087e2  pop     rbx
0x1400087e3  retn
0x1400087e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087ec  lea     r14, WPP_GLOBAL_Control
0x1400087f3  cmp     rcx, r14
0x1400087f6  jnz     loc_140008A12
0x1400087fc  mov     eax, 0C000009Ah
0x140008801  jmp     short loc_1400087D3
0x140008803  xor     r15d, r15d
0x140008806  cmp     sil, 21h ; '!'
0x14000880a  jnz     loc_14000878B
0x140008810  jmp     loc_140008766
0x140008815  cmp     dword ptr [rbx+4], 0C0000004h
0x14000881c  jnz     short loc_1400087BD
0x14000881e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008825  cmp     rcx, r14
0x140008828  jnz     loc_140008C52
0x14000882e  mov     r9, [rsp+88h+arg_40]
0x140008836  lea     r8, [rsp+88h+arg_0]
0x14000883e  movzx   eax, byte ptr [r9+163h]
0x140008846  lea     rcx, [rax+rax*2]
0x14000884a  mov     rax, [r9+298h]
0x140008851  add     rcx, rcx
0x140008854  mov     rdx, [rax+8]
0x140008858  movzx   edx, byte ptr [rdx+rcx*8+2]
0x14000885d  mov     rcx, [r9+18h]
0x140008861  call    RequestErrorCodeControl
0x140008866  test    eax, eax
0x140008868  mov     edi, eax
0x14000886a  cmovns  edi, [rsp+88h+arg_0]
0x140008872  mov     rcx, cs:WPP_GLOBAL_Control
0x140008879  cmp     rcx, r14
0x14000887c  jz      loc_1400087BD
0x140008882  cmp     byte ptr [rcx+29h], 5
0x140008886  jb      loc_1400087BD
0x14000888c  mov     r9, [rsp+88h+arg_40]
0x140008894  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x14000889b  mov     rcx, [rcx+18h]
0x14000889f  mov     edx, 2Dh ; '-'
0x1400088a4  mov     dword ptr [rsp+88h+Timeout], edi
0x1400088a8  call    WPP_SF_qD
0x1400088ad  jmp     loc_1400087BD
0x1400088b2  cmp     eax, 4
0x1400088b5  jz      loc_1400089E7
0x1400088bb  xor     r15d, r15d
0x1400088be  jmp     loc_14000878B
0x1400088c3  mov     rax, [rsp+88h+arg_28]
0x1400088cb  movzx   r15d, byte ptr [rax]
0x1400088cf  jmp     loc_14000878B
0x1400088d4  mov     rax, [rsp+88h+arg_38]
0x1400088dc  mov     rcx, r12
0x1400088df  shr     rcx, 8
0x1400088e3  test    byte ptr [rcx+rax+1B8h], 10h
0x1400088eb  jz      loc_1400087BD
0x1400088f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088f8  mov     r15, [rsp+88h+arg_40]
0x140008900  cmp     rcx, r14
0x140008903  jz      short loc_140008923
0x140008905  cmp     byte ptr [rcx+29h], 5
0x140008909  jb      short loc_140008923
0x14000890b  mov     rcx, [rcx+18h]
0x14000890f  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008916  mov     edx, 2Fh ; '/'
0x14000891b  mov     r9, r15
0x14000891e  call    WPP_SF_q
0x140008923  mov     qword ptr [rsp+88h+var_58], 0FFFFFFFFFD050F80h
0x14000892c  xor     ebp, ebp
0x14000892e  mov     rcx, [r15+290h]; Object
0x140008935  lea     rax, [rsp+88h+var_58]
0x14000893a  xor     r9d, r9d; Alertable
0x14000893d  mov     [rsp+88h+Timeout], rax; Timeout
0x140008942  xor     r8d, r8d; WaitMode
0x140008945  xor     edx, edx; WaitReason
0x140008947  call    cs:__imp_KeWaitForSingleObject
0x14000894e  nop     dword ptr [rax+rax+00h]
0x140008953  mov     edi, eax
0x140008955  test    eax, eax
0x140008957  js      loc_1400087BD
0x14000895d  cmp     eax, 102h
0x140008962  jz      loc_140008D4C
0x140008968  mov     rcx, [r15+288h]
0x14000896f  mov     rax, [rcx+10h]
0x140008973  cmp     [rax+1], r13b
0x140008977  jnz     loc_140008CC7
0x14000897d  movzx   ecx, r12w
0x140008981  shr     cx, 8
0x140008985  cmp     [rax+3], cl
0x140008988  jnz     loc_140008CC7
0x14000898e  movzx   edx, byte ptr [rax+4]
0x140008992  test    dl, dl
0x140008994  jnz     loc_140008D06
0x14000899a  mov     rcx, [rsp+88h+arg_28]; void *
0x1400089a2  lea     rdx, [rax+5]; Src
0x1400089a6  mov     r8d, esi; Size
0x1400089a9  call    memmove
0x1400089ae  xor     edi, edi
0x1400089b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089b7  cmp     rcx, r14
0x1400089ba  jz      loc_1400087BD
0x1400089c0  cmp     byte ptr [rcx+29h], 5
0x1400089c4  jb      loc_1400087BD
0x1400089ca  mov     rcx, [rcx+18h]
0x1400089ce  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x1400089d5  mov     edx, 31h ; '1'
0x1400089da  mov     r9, r15
0x1400089dd  call    WPP_SF_q
0x1400089e2  jmp     loc_1400087BD
0x1400089e7  mov     rax, [rsp+88h+arg_28]
0x1400089ef  mov     r15d, [rax]
0x1400089f2  jmp     loc_14000878B
0x1400089f7  test    rbx, rbx
0x1400089fa  jz      loc_1400087E5
0x140008a00  mov     r8, r15; Size
0x140008a03  xor     edx, edx; Val
0x140008a05  mov     rcx, rbx; void *
0x140008a08  call    memset
0x140008a0d  jmp     loc_1400086B6
0x140008a12  cmp     byte ptr [rcx+29h], 2
0x140008a16  jb      loc_1400087FC
0x140008a1c  mov     r9, [rsp+88h+arg_40]
0x140008a24  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008a2b  mov     rcx, [rcx+18h]
0x140008a2f  mov     edx, 22h ; '"'
0x140008a34  call    WPP_SF_q
0x140008a39  jmp     loc_1400087FC
0x140008a3e  call    USBVideoCallUSBD
0x140008a43  mov     edi, eax
0x140008a45  jmp     loc_140008752
0x140008a4a  cmp     dword ptr [rbx+4], 80000700h
0x140008a51  jnz     loc_140008752
0x140008a57  mov     edi, 0C01F0001h
0x140008a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a63  cmp     rcx, r14
0x140008a66  jz      short loc_140008A93
0x140008a68  cmp     byte ptr [rcx+29h], 2
0x140008a6c  jb      short loc_140008A93
0x140008a6e  mov     r9, [r15+10h]
0x140008a72  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140008a79  mov     rcx, [rcx+18h]
0x140008a7d  mov     edx, 15h
0x140008a82  mov     [rsp+88h+var_60], 0C01F0001h
0x140008a8a  mov     dword ptr [rsp+88h+Timeout], eax
0x140008a8e  call    WPP_SF_qDD
0x140008a93  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 8
0x140008a9a  jz      loc_140008752
0x140008aa0  xor     r9d, r9d
0x140008aa3  lea     rdx, USBVideo_InsufficientBandwidth
0x140008aaa  call    McTemplateK0p_EtwWriteTransfer
0x140008aaf  jmp     loc_140008752
0x140008ab4  cmp     rcx, r14
0x140008ab7  jz      loc_14000879C
0x140008abd  mov     rcx, [rcx+18h]
0x140008ac1  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008ac8  mov     edx, 23h ; '#'
0x140008acd  call    WPP_SF_
0x140008ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ad9  cmp     rcx, r14
0x140008adc  jz      loc_14000879C
0x140008ae2  cmp     byte ptr [rcx+29h], 5
0x140008ae6  jb      short loc_140008B00
0x140008ae8  mov     rcx, [rcx+18h]
0x140008aec  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008af3  mov     r9d, esi
0x140008af6  mov     edx, 24h ; '$'
0x140008afb  call    WPP_SF_d
0x140008b00  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b07  cmp     rcx, r14
0x140008b0a  jz      loc_14000879C
0x140008b10  cmp     byte ptr [rcx+29h], 5
0x140008b14  jb      short loc_140008B2E
0x140008b16  mov     rcx, [rcx+18h]
0x140008b1a  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008b21  mov     r9d, ebp
0x140008b24  mov     edx, 25h ; '%'
0x140008b29  call    WPP_SF_d
0x140008b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b35  cmp     rcx, r14
0x140008b38  jz      loc_14000879C
0x140008b3e  cmp     byte ptr [rcx+29h], 5
0x140008b42  jb      short loc_140008B5C
0x140008b44  mov     rcx, [rcx+18h]
0x140008b48  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008b4f  mov     r9d, r12d
0x140008b52  mov     edx, 26h ; '&'
0x140008b57  call    WPP_SF_d
0x140008b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b63  cmp     rcx, r14
0x140008b66  jz      loc_14000879C
0x140008b6c  cmp     byte ptr [rcx+29h], 5
0x140008b70  jb      short loc_140008B90
0x140008b72  movzx   r9d, word ptr [rsp+88h+arg_20]
0x140008b7b  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008b82  mov     rcx, [rcx+18h]
0x140008b86  mov     edx, 27h ; '''
0x140008b8b  call    WPP_SF_d
0x140008b90  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b97  cmp     rcx, r14
0x140008b9a  jz      loc_14000879C
0x140008ba0  cmp     byte ptr [rcx+29h], 5
0x140008ba4  jb      short loc_140008BBE
0x140008ba6  mov     rcx, [rcx+18h]
0x140008baa  lea     r8, WPP_8f241381ac4c358e230570bdc13f0fd6_Traceguids
0x140008bb1  mov     edx, 28h ; '('
0x140008bb6  mov     r9d, r15d
  ... truncated ...
```
