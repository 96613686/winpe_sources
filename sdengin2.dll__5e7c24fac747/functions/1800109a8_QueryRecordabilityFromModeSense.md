# QueryRecordabilityFromModeSense

- ea: `0x1800109a8`
- end: `0x180010cb9`
- name: `QueryRecordabilityFromModeSense`
- size: `785`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800110e0`

## callees

- `0x180008200`
- `0x1800109a8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180010a76`
- `KERNEL32!DeviceIoControl` at `0x180010baa`
- `KERNEL32!DeviceIoControl` at `0x180010a76`
- `KERNEL32!DeviceIoControl` at `0x180010baa`
- `ole32!CoTaskMemFree` at `0x180010ae5`
- `ole32!CoTaskMemFree` at `0x180010c70`
- `ole32!CoTaskMemFree` at `0x180010ae5`
- `ole32!CoTaskMemFree` at `0x180010c70`
- `ole32!CoTaskMemAlloc` at `0x180010aee`
- `ole32!CoTaskMemAlloc` at `0x180010aee`

## pseudocode

```c
__int64 __fastcall QueryRecordabilityFromModeSense(HANDLE hDevice, _DWORD *a2)
{
  __int16 v4; // ax
  __int64 v5; // rcx
  __int64 *p_InBuffer; // rax
  __int64 v7; // rcx
  unsigned int LastFailureAsHRESULT; // edi
  _WORD *lpOutBuffer; // rbx
  unsigned int v10; // ecx
  __int64 v11; // r13
  int v12; // esi
  int v13; // edi
  DWORD nOutBufferSize; // r12d
  __int64 v15; // rcx
  _BYTE *v16; // rax
  char v17; // cl
  __int64 v18; // rdi
  char v19; // al
  __int64 v20; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-59h] BYREF
  int v23; // [rsp+48h] [rbp-51h] BYREF
  __int16 v24; // [rsp+4Ch] [rbp-4Dh]
  __int16 v25; // [rsp+4Eh] [rbp-4Bh]
  HANDLE hDevicea; // [rsp+80h] [rbp-19h]
  __int64 InBuffer; // [rsp+88h] [rbp-11h] BYREF
  int v28; // [rsp+90h] [rbp-9h]
  __int128 OutBuffer; // [rsp+98h] [rbp-1h] BYREF
  __int128 v30; // [rsp+A8h] [rbp+Fh]

  hDevicea = hDevice;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "QueryRecordabilityFromModeSense", 1599, 1);
  BytesReturned = 0;
  InBuffer = 0;
  v28 = 0;
  OutBuffer = 0;
  v30 = 0;
  v4 = 1614;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_30:
    v23 = LastFailureAsHRESULT;
    goto LABEL_31;
  }
  *a2 = 0;
  v23 = 0;
  v24 = 1614;
  v5 = 12;
  p_InBuffer = &InBuffer;
  do
  {
    *(_BYTE *)p_InBuffer = 0;
    p_InBuffer = (__int64 *)((char *)p_InBuffer + 1);
    --v5;
  }
  while ( v5 );
  InBuffer = 1;
  if ( !DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v23 = LastFailureAsHRESULT;
    v4 = 1630;
LABEL_31:
    v25 = v4;
    goto LABEL_32;
  }
  lpOutBuffer = 0;
  v24 = 1630;
  v10 = v30;
  v11 = ~(_DWORD)v30 & (unsigned int)(v30 + 80);
  v12 = 0;
  while ( 1 )
  {
    v13 = v12 != 0 ? 32 : 28;
    if ( v10 > 0x2000 )
      break;
    v23 = 0;
    v24 = 1650;
    nOutBufferSize = v13 + v10 + 80;
    if ( lpOutBuffer )
      CoTaskMemFree(lpOutBuffer);
    lpOutBuffer = CoTaskMemAlloc(nOutBufferSize);
    v4 = 1660;
    if ( !lpOutBuffer )
    {
      LastFailureAsHRESULT = -2147024882;
      goto LABEL_30;
    }
    v23 = 0;
    v24 = 1660;
    v15 = 88;
    v16 = lpOutBuffer;
    do
    {
      *v16++ = 0;
      --v15;
    }
    while ( v15 );
    *lpOutBuffer = 56;
    *(_WORD *)((char *)lpOutBuffer + 7) = 274;
    *((_DWORD *)lpOutBuffer + 3) = v13;
    *((_DWORD *)lpOutBuffer + 4) = 20;
    *((_DWORD *)lpOutBuffer + 8) = 56;
    *((_QWORD *)lpOutBuffer + 3) = (unsigned int)v11;
    *((_BYTE *)lpOutBuffer + 6) = v12 != 0 ? 10 : 6;
    *((_BYTE *)lpOutBuffer + 37) |= 8u;
    if ( v12 )
    {
      *((_BYTE *)lpOutBuffer + 43) = 0;
      *((_BYTE *)lpOutBuffer + 44) = v13;
      v17 = 90;
      v18 = 11;
    }
    else
    {
      *((_BYTE *)lpOutBuffer + 40) = v13;
      v17 = 26;
      v18 = 7;
    }
    v19 = lpOutBuffer[19] & 0xC0 | 0x2A;
    *((_BYTE *)lpOutBuffer + 36) = v17;
    *((_BYTE *)lpOutBuffer + 38) = v19;
    if ( !DeviceIoControl(
            hDevicea,
            0x4D004u,
            lpOutBuffer,
            nOutBufferSize,
            lpOutBuffer,
            nOutBufferSize,
            &BytesReturned,
            0) )
    {
      v23 = GetLastFailureAsHRESULT(v20);
      v25 = 1699;
      goto LABEL_28;
    }
    v23 = 0;
    v24 = 1699;
    if ( (lpOutBuffer[29] & 0xF) == 0 && (*((_BYTE *)lpOutBuffer + v18 + v11) & 0x33) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids,
          v12 != 0 ? 10 : 6);
      *a2 = 1;
      v23 = 0;
      v24 = 1706;
      goto LABEL_28;
    }
    if ( (unsigned int)++v12 >= 2 )
      goto LABEL_28;
    v10 = v30;
  }
  LastFailureAsHRESULT = -2147467259;
  v23 = -2147467259;
  v25 = 1650;
  if ( !lpOutBuffer )
    goto LABEL_32;
LABEL_28:
  CoTaskMemFree(lpOutBuffer);
  LastFailureAsHRESULT = v23;
LABEL_32:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800109a8  mov     [rsp-8+arg_10], rbx
0x1800109ad  push    rbp
0x1800109ae  push    rsi
0x1800109af  push    rdi
0x1800109b0  push    r12
0x1800109b2  push    r13
0x1800109b4  push    r14
0x1800109b6  push    r15
0x1800109b8  lea     rbp, [rsp-27h]
0x1800109bd  sub     rsp, 0C0h
0x1800109c4  mov     rax, cs:__security_cookie
0x1800109cb  xor     rax, rsp
0x1800109ce  mov     [rbp+57h+var_38], rax
0x1800109d2  mov     r14, rdx
0x1800109d5  mov     rbx, rcx
0x1800109d8  mov     [rbp+57h+hDevice], rcx
0x1800109dc  mov     r9d, 1; unsigned __int16
0x1800109e2  mov     r8d, 63Fh; unsigned __int16
0x1800109e8  lea     rdx, aQueryrecordabi; "QueryRecordabilityFromModeSense"
0x1800109ef  lea     rcx, [rbp+57h+var_A8]; this
0x1800109f3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800109f8  xor     r15d, r15d
0x1800109fb  mov     [rbp+57h+BytesReturned], r15d
0x1800109ff  xor     eax, eax
0x180010a01  mov     [rbp+57h+InBuffer], rax
0x180010a05  mov     [rbp+57h+var_60], eax
0x180010a08  xorps   xmm0, xmm0
0x180010a0b  movups  [rbp+57h+OutBuffer], xmm0
0x180010a0f  movups  [rbp+57h+var_48], xmm0
0x180010a13  mov     eax, 64Eh
0x180010a18  test    r14, r14
0x180010a1b  jz      loc_180010C7B
0x180010a21  mov     [r14], r15d
0x180010a24  mov     [rbp+57h+var_A8], r15d
0x180010a28  mov     [rbp+57h+var_A4], ax
0x180010a2c  lea     r9d, [r15+0Ch]; nInBufferSize
0x180010a30  mov     ecx, r9d
0x180010a33  lea     rax, [rbp+57h+InBuffer]
0x180010a37  mov     [rax], r15b
0x180010a3a  inc     rax
0x180010a3d  sub     rcx, 1
0x180010a41  jnz     short loc_180010A37
0x180010a43  mov     [rbp+57h+InBuffer], 1
0x180010a4b  mov     [rsp+0F0h+lpOverlapped], r15; lpOverlapped
0x180010a50  lea     rax, [rbp+57h+BytesReturned]
0x180010a54  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x180010a59  mov     [rsp+0F0h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x180010a61  lea     rax, [rbp+57h+OutBuffer]
0x180010a65  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x180010a6a  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180010a6e  mov     edx, 2D1400h; dwIoControlCode
0x180010a73  mov     rcx, rbx; hDevice
0x180010a76  call    cs:__imp_DeviceIoControl
0x180010a7c  test    eax, eax
0x180010a7e  jnz     short loc_180010A94
0x180010a80  call    GetLastFailureAsHRESULT
0x180010a85  mov     edi, eax
0x180010a87  mov     [rbp+57h+var_A8], eax
0x180010a8a  mov     eax, 65Eh
0x180010a8f  jmp     loc_180010C83
0x180010a94  mov     rbx, r15
0x180010a97  mov     eax, 65Eh
0x180010a9c  mov     [rbp+57h+var_A4], ax
0x180010aa0  mov     ecx, dword ptr [rbp+57h+var_48]
0x180010aa3  lea     r13d, [rcx+50h]
0x180010aa7  mov     eax, ecx
0x180010aa9  not     eax
0x180010aab  and     r13d, eax
0x180010aae  mov     esi, r15d
0x180010ab1  mov     edx, 672h
0x180010ab6  mov     eax, esi
0x180010ab8  neg     eax
0x180010aba  sbb     edi, edi
0x180010abc  and     edi, 4
0x180010abf  add     edi, 1Ch
0x180010ac2  cmp     ecx, 2000h
0x180010ac8  ja      loc_180010C5C
0x180010ace  mov     [rbp+57h+var_A8], r15d
0x180010ad2  mov     [rbp+57h+var_A4], dx
0x180010ad6  lea     r12d, [rcx+50h]
0x180010ada  add     r12d, edi
0x180010add  test    rbx, rbx
0x180010ae0  jz      short loc_180010AEB
0x180010ae2  mov     rcx, rbx; pv
0x180010ae5  call    cs:__imp_CoTaskMemFree
0x180010aeb  mov     ecx, r12d; cb
0x180010aee  call    cs:__imp_CoTaskMemAlloc
0x180010af4  mov     rbx, rax
0x180010af7  test    rax, rax
0x180010afa  mov     eax, 67Ch
0x180010aff  jz      loc_180010C55
0x180010b05  mov     [rbp+57h+var_A8], r15d
0x180010b09  mov     [rbp+57h+var_A4], ax
0x180010b0d  mov     ecx, 58h ; 'X'
0x180010b12  mov     rax, rbx
0x180010b15  mov     [rax], r15b
0x180010b18  inc     rax
0x180010b1b  sub     rcx, 1
0x180010b1f  jnz     short loc_180010B15
0x180010b21  lea     eax, [rcx+38h]
0x180010b24  mov     [rbx], ax
0x180010b27  mov     word ptr [rbx+7], 112h
0x180010b2d  mov     [rbx+0Ch], edi
0x180010b30  mov     dword ptr [rbx+10h], 14h
0x180010b37  mov     [rbx+20h], eax
0x180010b3a  mov     r15d, r13d
0x180010b3d  mov     [rbx+18h], r15
0x180010b41  mov     eax, esi
0x180010b43  neg     eax
0x180010b45  sbb     cl, cl
0x180010b47  and     cl, 4
0x180010b4a  add     cl, 6
0x180010b4d  mov     [rbx+6], cl
0x180010b50  or      byte ptr [rbx+25h], 8
0x180010b54  test    esi, esi
0x180010b56  jnz     short loc_180010B63
0x180010b58  mov     [rbx+28h], dil
0x180010b5c  mov     cl, 1Ah
0x180010b5e  lea     edi, [rsi+7]
0x180010b61  jmp     short loc_180010B72
0x180010b63  mov     byte ptr [rbx+2Bh], 0
0x180010b67  mov     [rbx+2Ch], dil
0x180010b6b  mov     cl, 5Ah ; 'Z'
0x180010b6d  mov     edi, 0Bh
0x180010b72  mov     al, [rbx+26h]
0x180010b75  and     al, 0EAh
0x180010b77  or      al, 2Ah
0x180010b79  mov     [rbx+24h], cl
0x180010b7c  mov     [rbx+26h], al
0x180010b7f  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x180010b88  lea     rax, [rbp+57h+BytesReturned]
0x180010b8c  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x180010b91  mov     [rsp+0F0h+nOutBufferSize], r12d; nOutBufferSize
0x180010b96  mov     [rsp+0F0h+lpOutBuffer], rbx; lpOutBuffer
0x180010b9b  mov     r9d, r12d; nInBufferSize
0x180010b9e  mov     r8, rbx; lpInBuffer
0x180010ba1  mov     edx, 4D004h; dwIoControlCode
0x180010ba6  mov     rcx, [rbp+57h+hDevice]; hDevice
0x180010baa  call    cs:__imp_DeviceIoControl
0x180010bb0  test    eax, eax
0x180010bb2  jz      loc_180010C42
0x180010bb8  mov     [rbp+57h+var_A8], 0
0x180010bbf  mov     eax, 6A3h
0x180010bc4  mov     [rbp+57h+var_A4], ax
0x180010bc8  test    byte ptr [rbx+3Ah], 0Fh
0x180010bcc  jnz     short loc_180010BD8
0x180010bce  lea     rax, [rdi+r13]
0x180010bd2  test    byte ptr [rax+rbx], 33h
0x180010bd6  jnz     short loc_180010BEE
0x180010bd8  inc     esi
0x180010bda  cmp     esi, 2
0x180010bdd  jnb     loc_180010C6D
0x180010be3  mov     ecx, dword ptr [rbp+57h+var_48]
0x180010be6  xor     r15d, r15d
0x180010be9  jmp     loc_180010AB1
0x180010bee  lea     rax, WPP_GLOBAL_Control
0x180010bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bfc  cmp     rcx, rax
0x180010bff  jz      short loc_180010C29
0x180010c01  test    byte ptr [rcx+1Ch], 40h
0x180010c05  jz      short loc_180010C29
0x180010c07  neg     esi
0x180010c09  sbb     r9d, r9d
0x180010c0c  and     r9d, 4
0x180010c10  add     r9d, 6
0x180010c14  mov     edx, 13h
0x180010c19  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x180010c20  mov     rcx, [rcx+10h]
0x180010c24  call    WPP_SF_d
0x180010c29  mov     dword ptr [r14], 1
0x180010c30  mov     [rbp+57h+var_A8], 0
0x180010c37  mov     eax, 6AAh
0x180010c3c  mov     [rbp+57h+var_A4], ax
0x180010c40  jmp     short loc_180010C6D
0x180010c42  call    GetLastFailureAsHRESULT
0x180010c47  mov     [rbp+57h+var_A8], eax
0x180010c4a  mov     eax, 6A3h
0x180010c4f  mov     [rbp+57h+var_A2], ax
0x180010c53  jmp     short loc_180010C6D
0x180010c55  mov     edi, 8007000Eh
0x180010c5a  jmp     short loc_180010C80
0x180010c5c  mov     edi, 80004005h
0x180010c61  mov     [rbp+57h+var_A8], edi
0x180010c64  mov     [rbp+57h+var_A2], dx
0x180010c68  test    rbx, rbx
0x180010c6b  jz      short loc_180010C87
0x180010c6d  mov     rcx, rbx; pv
0x180010c70  call    cs:__imp_CoTaskMemFree
0x180010c76  mov     edi, [rbp+57h+var_A8]
0x180010c79  jmp     short loc_180010C87
0x180010c7b  mov     edi, 80070057h
0x180010c80  mov     [rbp+57h+var_A8], edi
0x180010c83  mov     [rbp+57h+var_A2], ax
0x180010c87  lea     rcx, [rbp+57h+var_A8]; this
0x180010c8b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010c90  mov     eax, edi
0x180010c92  mov     rcx, [rbp+57h+var_38]
0x180010c96  xor     rcx, rsp; StackCookie
0x180010c99  call    __security_check_cookie
0x180010c9e  mov     rbx, [rsp+0F0h+arg_10]
0x180010ca6  add     rsp, 0C0h
0x180010cad  pop     r15
0x180010caf  pop     r14
0x180010cb1  pop     r13
0x180010cb3  pop     r12
0x180010cb5  pop     rdi
0x180010cb6  pop     rsi
0x180010cb7  pop     rbp
0x180010cb8  retn
```
