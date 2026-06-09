# GetCdConfiguration

- ea: `0x18000c220`
- end: `0x18000c5e2`
- name: `GetCdConfiguration`
- size: `962`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180010798`

## callees

- `0x18000c220`
- `0x1800144f0`
- `0x18001453c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97c2`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000c2f5`
- `KERNEL32!DeviceIoControl` at `0x18000c40e`
- `KERNEL32!DeviceIoControl` at `0x18000c2f5`
- `KERNEL32!DeviceIoControl` at `0x18000c40e`
- `ole32!CoTaskMemFree` at `0x18000c364`
- `ole32!CoTaskMemFree` at `0x18000c599`
- `ole32!CoTaskMemFree` at `0x18000c364`
- `ole32!CoTaskMemFree` at `0x18000c599`
- `ole32!CoTaskMemAlloc` at `0x18000c36c`
- `ole32!CoTaskMemAlloc` at `0x18000c48e`
- `ole32!CoTaskMemAlloc` at `0x18000c36c`
- `ole32!CoTaskMemAlloc` at `0x18000c48e`

## string_xrefs

- `0x18000c266`: `GetCdConfiguration`

## pseudocode

```c
__int64 __fastcall GetCdConfiguration(HANDLE hDevice, int a2, _QWORD *a3)
{
  __int16 v4; // r15
  __int16 v6; // ax
  __int64 v7; // rcx
  __int64 *p_InBuffer; // rax
  __int64 v9; // rcx
  unsigned int LastFailureAsHRESULT; // ebx
  _WORD *lpOutBuffer; // rdi
  unsigned int v12; // ecx
  __int64 v13; // r13
  unsigned int v14; // esi
  DWORD nOutBufferSize; // ebx
  __int64 v16; // rcx
  _BYTE *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // ecx
  __int16 v21; // ax
  unsigned int v22; // ebx
  void *v23; // rax
  void *v24; // rsi
  DWORD BytesReturned; // [rsp+40h] [rbp-59h] BYREF
  int v27; // [rsp+44h] [rbp-55h]
  int v28; // [rsp+48h] [rbp-51h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-4Dh]
  __int16 v30; // [rsp+4Eh] [rbp-4Bh]
  HANDLE hDevicea; // [rsp+80h] [rbp-19h]
  __int64 InBuffer; // [rsp+88h] [rbp-11h] BYREF
  int v33; // [rsp+90h] [rbp-9h]
  __int128 OutBuffer; // [rsp+98h] [rbp-1h] BYREF
  __int128 v35; // [rsp+A8h] [rbp+Fh]

  v4 = a2;
  v27 = a2;
  hDevicea = hDevice;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "GetCdConfiguration", 1730, 1);
  InBuffer = 0;
  v33 = 0;
  OutBuffer = 0;
  v35 = 0;
  BytesReturned = 0;
  v6 = 1746;
  if ( !a3 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_35:
    v28 = LastFailureAsHRESULT;
    goto LABEL_36;
  }
  *a3 = 0;
  v28 = 0;
  v29 = 1746;
  v7 = 12;
  p_InBuffer = &InBuffer;
  do
  {
    *(_BYTE *)p_InBuffer = 0;
    p_InBuffer = (__int64 *)((char *)p_InBuffer + 1);
    --v7;
  }
  while ( v7 );
  InBuffer = 1;
  if ( !DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v28 = LastFailureAsHRESULT;
    v6 = 1762;
LABEL_36:
    v30 = v6;
    goto LABEL_37;
  }
  lpOutBuffer = 0;
  v29 = 1762;
  v12 = v35;
  v13 = ~(_DWORD)v35 & (unsigned int)(v35 + 80);
  v14 = 264;
  while ( v12 <= 0x2000 && v14 <= 0x100000 )
  {
    v28 = 0;
    v29 = 1778;
    nOutBufferSize = v12 + v14 + 80;
    if ( lpOutBuffer )
      CoTaskMemFree(lpOutBuffer);
    lpOutBuffer = CoTaskMemAlloc(nOutBufferSize);
    v6 = 1788;
    if ( !lpOutBuffer )
    {
      LastFailureAsHRESULT = -2147024882;
      goto LABEL_35;
    }
    v28 = 0;
    v29 = 1788;
    v16 = 88;
    v17 = lpOutBuffer;
    do
    {
      *v17++ = 0;
      --v16;
    }
    while ( v16 );
    *lpOutBuffer = 56;
    *(_WORD *)((char *)lpOutBuffer + 7) = 274;
    *((_DWORD *)lpOutBuffer + 3) = v14;
    *((_DWORD *)lpOutBuffer + 4) = 20;
    *((_DWORD *)lpOutBuffer + 8) = 56;
    *((_QWORD *)lpOutBuffer + 3) = (unsigned int)v13;
    *((_BYTE *)lpOutBuffer + 6) = 10;
    *((_BYTE *)lpOutBuffer + 36) = 70;
    *((_BYTE *)lpOutBuffer + 37) &= ~1u;
    *((_BYTE *)lpOutBuffer + 37) |= 2u;
    *((_BYTE *)lpOutBuffer + 38) = HIBYTE(v4);
    *((_BYTE *)lpOutBuffer + 39) = v4;
    *((_BYTE *)lpOutBuffer + 43) = BYTE1(v14);
    *((_BYTE *)lpOutBuffer + 44) = v14;
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
      v28 = GetLastFailureAsHRESULT(v18);
      v21 = 1814;
      goto LABEL_30;
    }
    v28 = 0;
    v29 = 1814;
    if ( (lpOutBuffer[29] & 0xF) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((unsigned __int8 *)lpOutBuffer + 68),
          v19,
          lpOutBuffer[29] & 0xF,
          *((unsigned __int8 *)lpOutBuffer + 68),
          *((unsigned __int8 *)lpOutBuffer + 69));
      v28 = 1;
      v29 = 1823;
      goto LABEL_33;
    }
    v20 = *((unsigned __int8 *)lpOutBuffer + v13 + 3)
        | ((*((unsigned __int8 *)lpOutBuffer + v13 + 2)
          | (((*((unsigned __int8 *)lpOutBuffer + v13) << 8) | *((unsigned __int8 *)lpOutBuffer + v13 + 1)) << 8)) << 8);
    v21 = 1835;
    if ( v20 >= 0x100000 )
    {
      v28 = -2147467259;
LABEL_30:
      v30 = v21;
      goto LABEL_33;
    }
    v29 = 1835;
    v22 = v20 + 4;
    if ( v20 + 4 <= v14 )
    {
      v23 = CoTaskMemAlloc(v22);
      v24 = v23;
      if ( v23 )
      {
        v28 = 0;
        v29 = 1849;
        memcpy_0(v23, (char *)lpOutBuffer + v13, v22);
        *a3 = v24;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids, v22, v27);
      }
      else
      {
        v28 = -2147024882;
        v30 = 1849;
      }
      goto LABEL_33;
    }
    v14 = v20 + 4;
    v12 = v35;
    v4 = v27;
  }
  LastFailureAsHRESULT = -2147467259;
  v28 = -2147467259;
  v30 = 1778;
  if ( !lpOutBuffer )
    goto LABEL_37;
LABEL_33:
  CoTaskMemFree(lpOutBuffer);
  LastFailureAsHRESULT = v28;
LABEL_37:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000c220  mov     [rsp-8+arg_8], rbx
0x18000c225  push    rbp
0x18000c226  push    rsi
0x18000c227  push    rdi
0x18000c228  push    r12
0x18000c22a  push    r13
0x18000c22c  push    r14
0x18000c22e  push    r15
0x18000c230  lea     rbp, [rsp-27h]
0x18000c235  sub     rsp, 0C0h
0x18000c23c  mov     rax, cs:__security_cookie
0x18000c243  xor     rax, rsp
0x18000c246  mov     [rbp+57h+var_38], rax
0x18000c24a  mov     r12, r8
0x18000c24d  mov     r15d, edx
0x18000c250  mov     [rbp+57h+var_AC], edx
0x18000c253  mov     rbx, rcx
0x18000c256  mov     [rbp+57h+hDevice], rcx
0x18000c25a  mov     r9d, 1; unsigned __int16
0x18000c260  mov     r8d, 6C2h; unsigned __int16
0x18000c266  lea     rdx, aGetcdconfigura; "GetCdConfiguration"
0x18000c26d  lea     rcx, [rbp+57h+var_A8]; this
0x18000c271  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c276  xor     eax, eax
0x18000c278  mov     [rbp+57h+InBuffer], rax
0x18000c27c  mov     [rbp+57h+var_60], eax
0x18000c27f  xorps   xmm0, xmm0
0x18000c282  movups  [rbp+57h+OutBuffer], xmm0
0x18000c286  movups  [rbp+57h+var_48], xmm0
0x18000c28a  xor     r14d, r14d
0x18000c28d  mov     [rbp+57h+BytesReturned], r14d
0x18000c291  mov     eax, 6D2h
0x18000c296  test    r12, r12
0x18000c299  jz      loc_18000C5A4
0x18000c29f  mov     [r12], r14
0x18000c2a3  mov     [rbp+57h+var_A8], r14d
0x18000c2a7  mov     [rbp+57h+var_A4], ax
0x18000c2ab  lea     r9d, [r14+0Ch]; nInBufferSize
0x18000c2af  mov     ecx, r9d
0x18000c2b2  lea     rax, [rbp+57h+InBuffer]
0x18000c2b6  mov     [rax], r14b
0x18000c2b9  inc     rax
0x18000c2bc  sub     rcx, 1
0x18000c2c0  jnz     short loc_18000C2B6
0x18000c2c2  mov     [rbp+57h+InBuffer], 1
0x18000c2ca  mov     [rsp+0F0h+lpOverlapped], r14; lpOverlapped
0x18000c2cf  lea     rax, [rbp+57h+BytesReturned]
0x18000c2d3  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x18000c2d8  mov     [rsp+0F0h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x18000c2e0  lea     rax, [rbp+57h+OutBuffer]
0x18000c2e4  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x18000c2e9  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000c2ed  mov     edx, 2D1400h; dwIoControlCode
0x18000c2f2  mov     rcx, rbx; hDevice
0x18000c2f5  call    cs:__imp_DeviceIoControl
0x18000c2fb  test    eax, eax
0x18000c2fd  jnz     short loc_18000C313
0x18000c2ff  call    GetLastFailureAsHRESULT
0x18000c304  mov     ebx, eax
0x18000c306  mov     [rbp+57h+var_A8], eax
0x18000c309  mov     eax, 6E2h
0x18000c30e  jmp     loc_18000C5AC
0x18000c313  mov     rdi, r14
0x18000c316  mov     eax, 6E2h
0x18000c31b  mov     [rbp+57h+var_A4], ax
0x18000c31f  mov     ecx, dword ptr [rbp+57h+var_48]
0x18000c322  lea     r13d, [rcx+50h]
0x18000c326  mov     eax, ecx
0x18000c328  not     eax
0x18000c32a  and     r13d, eax
0x18000c32d  mov     esi, 108h
0x18000c332  mov     eax, 6F2h
0x18000c337  cmp     ecx, 2000h
0x18000c33d  ja      loc_18000C585
0x18000c343  cmp     esi, 100000h
0x18000c349  ja      loc_18000C585
0x18000c34f  mov     [rbp+57h+var_A8], r14d
0x18000c353  mov     [rbp+57h+var_A4], ax
0x18000c357  lea     ebx, [rsi+50h]
0x18000c35a  add     ebx, ecx
0x18000c35c  test    rdi, rdi
0x18000c35f  jz      short loc_18000C36A
0x18000c361  mov     rcx, rdi; pv
0x18000c364  call    cs:__imp_CoTaskMemFree
0x18000c36a  mov     ecx, ebx; cb
0x18000c36c  call    cs:__imp_CoTaskMemAlloc
0x18000c372  mov     rdi, rax
0x18000c375  test    rax, rax
0x18000c378  mov     eax, 6FCh
0x18000c37d  jz      loc_18000C57E
0x18000c383  mov     [rbp+57h+var_A8], r14d
0x18000c387  mov     [rbp+57h+var_A4], ax
0x18000c38b  mov     ecx, 58h ; 'X'
0x18000c390  mov     rax, rdi
0x18000c393  mov     [rax], r14b
0x18000c396  inc     rax
0x18000c399  sub     rcx, 1
0x18000c39d  jnz     short loc_18000C393
0x18000c39f  lea     eax, [rcx+38h]
0x18000c3a2  mov     [rdi], ax
0x18000c3a5  mov     word ptr [rdi+7], 112h
0x18000c3ab  mov     [rdi+0Ch], esi
0x18000c3ae  mov     dword ptr [rdi+10h], 14h
0x18000c3b5  mov     [rdi+20h], eax
0x18000c3b8  mov     r14d, r13d
0x18000c3bb  mov     [rdi+18h], r14
0x18000c3bf  mov     byte ptr [rdi+6], 0Ah
0x18000c3c3  mov     byte ptr [rdi+24h], 46h ; 'F'
0x18000c3c7  and     byte ptr [rdi+25h], 0FEh
0x18000c3cb  or      byte ptr [rdi+25h], 2
0x18000c3cf  mov     eax, r15d
0x18000c3d2  sar     eax, 8
0x18000c3d5  mov     [rdi+26h], al
0x18000c3d8  mov     [rdi+27h], r15b
0x18000c3dc  mov     eax, esi
0x18000c3de  shr     eax, 8
0x18000c3e1  mov     [rdi+2Bh], al
0x18000c3e4  mov     [rdi+2Ch], sil
0x18000c3e8  mov     [rsp+0F0h+lpOverlapped], rcx; lpOverlapped
0x18000c3ed  lea     rax, [rbp+57h+BytesReturned]
0x18000c3f1  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x18000c3f6  mov     [rsp+0F0h+nOutBufferSize], ebx; nOutBufferSize
0x18000c3fa  mov     [rsp+0F0h+lpOutBuffer], rdi; lpOutBuffer
0x18000c3ff  mov     r9d, ebx; nInBufferSize
0x18000c402  mov     r8, rdi; lpInBuffer
0x18000c405  mov     edx, 4D004h; dwIoControlCode
0x18000c40a  mov     rcx, [rbp+57h+hDevice]; hDevice
0x18000c40e  call    cs:__imp_DeviceIoControl
0x18000c414  test    eax, eax
0x18000c416  jz      loc_18000C56B
0x18000c41c  mov     [rbp+57h+var_A8], 0
0x18000c423  mov     eax, 716h
0x18000c428  mov     [rbp+57h+var_A4], ax
0x18000c42c  test    byte ptr [rdi+3Ah], 0Fh
0x18000c430  jnz     loc_18000C51E
0x18000c436  lea     r15, [rdi+r13]
0x18000c43a  movzx   ecx, byte ptr [r15+1]
0x18000c43f  movzx   eax, byte ptr [r15]
0x18000c443  shl     eax, 8
0x18000c446  or      ecx, eax
0x18000c448  shl     ecx, 8
0x18000c44b  movzx   eax, byte ptr [r15+2]
0x18000c450  or      ecx, eax
0x18000c452  shl     ecx, 8
0x18000c455  movzx   eax, byte ptr [r15+3]
0x18000c45a  or      ecx, eax
0x18000c45c  mov     eax, 72Bh
0x18000c461  cmp     ecx, 100000h
0x18000c467  jnb     loc_18000C514
0x18000c46d  mov     [rbp+57h+var_A4], ax
0x18000c471  lea     ebx, [rcx+4]
0x18000c474  cmp     ebx, esi
0x18000c476  jbe     short loc_18000C489
0x18000c478  mov     esi, ebx
0x18000c47a  mov     ecx, dword ptr [rbp+57h+var_48]
0x18000c47d  mov     r15d, [rbp+57h+var_AC]
0x18000c481  xor     r14d, r14d
0x18000c484  jmp     loc_18000C332
0x18000c489  mov     r14d, ebx
0x18000c48c  mov     ecx, ebx; cb
0x18000c48e  call    cs:__imp_CoTaskMemAlloc
0x18000c494  mov     rsi, rax
0x18000c497  mov     ecx, 739h
0x18000c49c  test    rax, rax
0x18000c49f  jz      short loc_18000C503
0x18000c4a1  mov     [rbp+57h+var_A8], 0
0x18000c4a8  mov     [rbp+57h+var_A4], cx
0x18000c4ac  mov     r8d, r14d; Size
0x18000c4af  mov     rdx, r15; Src
0x18000c4b2  mov     rcx, rax; void *
0x18000c4b5  call    memcpy_0
0x18000c4ba  mov     [r12], rsi
0x18000c4be  lea     rax, WPP_GLOBAL_Control
0x18000c4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4cc  cmp     rcx, rax
0x18000c4cf  jz      loc_18000C596
0x18000c4d5  test    byte ptr [rcx+1Ch], 2
0x18000c4d9  jz      loc_18000C596
0x18000c4df  mov     edx, 15h
0x18000c4e4  mov     eax, [rbp+57h+var_AC]
0x18000c4e7  mov     dword ptr [rsp+0F0h+lpOutBuffer], eax
0x18000c4eb  mov     r9d, ebx
0x18000c4ee  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000c4f5  mov     rcx, [rcx+10h]
0x18000c4f9  call    WPP_SF_dd
0x18000c4fe  jmp     loc_18000C596
0x18000c503  mov     ebx, 8007000Eh
0x18000c508  mov     [rbp+57h+var_A8], ebx
0x18000c50b  mov     [rbp+57h+var_A2], cx
0x18000c50f  jmp     loc_18000C596
0x18000c514  mov     ebx, 80004005h
0x18000c519  mov     [rbp+57h+var_A8], ebx
0x18000c51c  jmp     short loc_18000C578
0x18000c51e  lea     rax, WPP_GLOBAL_Control
0x18000c525  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52c  cmp     rcx, rax
0x18000c52f  jz      short loc_18000C559
0x18000c531  test    byte ptr [rcx+1Ch], 40h
0x18000c535  jz      short loc_18000C559
0x18000c537  movzx   eax, byte ptr [rdi+45h]
0x18000c53b  movzx   edx, byte ptr [rdi+44h]
0x18000c53f  movzx   r9d, byte ptr [rdi+3Ah]
0x18000c544  and     r9d, 0Fh
0x18000c548  mov     [rsp+0F0h+nOutBufferSize], eax
0x18000c54c  mov     dword ptr [rsp+0F0h+lpOutBuffer], edx
0x18000c550  mov     rcx, [rcx+10h]
0x18000c554  call    WPP_SF_ddd
0x18000c559  mov     [rbp+57h+var_A8], 1
0x18000c560  mov     eax, 71Fh
0x18000c565  mov     [rbp+57h+var_A4], ax
0x18000c569  jmp     short loc_18000C596
0x18000c56b  call    GetLastFailureAsHRESULT
0x18000c570  mov     [rbp+57h+var_A8], eax
0x18000c573  mov     eax, 716h
0x18000c578  mov     [rbp+57h+var_A2], ax
0x18000c57c  jmp     short loc_18000C596
0x18000c57e  mov     ebx, 8007000Eh
0x18000c583  jmp     short loc_18000C5A9
0x18000c585  mov     ebx, 80004005h
0x18000c58a  mov     [rbp+57h+var_A8], ebx
0x18000c58d  mov     [rbp+57h+var_A2], ax
0x18000c591  test    rdi, rdi
0x18000c594  jz      short loc_18000C5B0
0x18000c596  mov     rcx, rdi; pv
0x18000c599  call    cs:__imp_CoTaskMemFree
0x18000c59f  mov     ebx, [rbp+57h+var_A8]
0x18000c5a2  jmp     short loc_18000C5B0
0x18000c5a4  mov     ebx, 80070057h
0x18000c5a9  mov     [rbp+57h+var_A8], ebx
0x18000c5ac  mov     [rbp+57h+var_A2], ax
0x18000c5b0  lea     rcx, [rbp+57h+var_A8]; this
0x18000c5b4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c5b9  mov     eax, ebx
0x18000c5bb  mov     rcx, [rbp+57h+var_38]
0x18000c5bf  xor     rcx, rsp; StackCookie
0x18000c5c2  call    __security_check_cookie
0x18000c5c7  mov     rbx, [rsp+0F0h+arg_8]
0x18000c5cf  add     rsp, 0C0h
0x18000c5d6  pop     r15
0x18000c5d8  pop     r14
0x18000c5da  pop     r13
0x18000c5dc  pop     r12
0x18000c5de  pop     rdi
0x18000c5df  pop     rsi
0x18000c5e0  pop     rbp
0x18000c5e1  retn
```
