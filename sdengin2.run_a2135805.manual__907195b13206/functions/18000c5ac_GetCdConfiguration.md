# GetCdConfiguration

- ea: `0x18000c5ac`
- end: `0x18000c993`
- name: `GetCdConfiguration`
- size: `999`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180010e7c`

## callees

- `0x18000c5ac`
- `0x180014d98`
- `0x180014dec`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf552`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000c681`
- `KERNEL32!DeviceIoControl` at `0x18000c7ac`
- `KERNEL32!DeviceIoControl` at `0x18000c681`
- `KERNEL32!DeviceIoControl` at `0x18000c7ac`
- `ole32!CoTaskMemFree` at `0x18000c6f6`
- `ole32!CoTaskMemFree` at `0x18000c943`
- `ole32!CoTaskMemFree` at `0x18000c6f6`
- `ole32!CoTaskMemFree` at `0x18000c943`
- `ole32!CoTaskMemAlloc` at `0x18000c704`
- `ole32!CoTaskMemAlloc` at `0x18000c832`
- `ole32!CoTaskMemAlloc` at `0x18000c704`
- `ole32!CoTaskMemAlloc` at `0x18000c832`

## string_xrefs

- `0x18000c5f2`: `GetCdConfiguration`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "GetCdConfiguration", 0x6C2u, 1u);
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
0x18000c5ac  mov     [rsp-8+arg_8], rbx
0x18000c5b1  push    rbp
0x18000c5b2  push    rsi
0x18000c5b3  push    rdi
0x18000c5b4  push    r12
0x18000c5b6  push    r13
0x18000c5b8  push    r14
0x18000c5ba  push    r15
0x18000c5bc  lea     rbp, [rsp-27h]
0x18000c5c1  sub     rsp, 0C0h
0x18000c5c8  mov     rax, cs:__security_cookie
0x18000c5cf  xor     rax, rsp
0x18000c5d2  mov     [rbp+57h+var_38], rax
0x18000c5d6  mov     r12, r8
0x18000c5d9  mov     r15d, edx
0x18000c5dc  mov     [rbp+57h+var_AC], edx
0x18000c5df  mov     rbx, rcx
0x18000c5e2  mov     [rbp+57h+hDevice], rcx
0x18000c5e6  mov     r9d, 1; unsigned __int16
0x18000c5ec  mov     r8d, 6C2h; unsigned __int16
0x18000c5f2  lea     rdx, aGetcdconfigura; "GetCdConfiguration"
0x18000c5f9  lea     rcx, [rbp+57h+var_A8]; this
0x18000c5fd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c602  xor     eax, eax
0x18000c604  mov     [rbp+57h+InBuffer], rax
0x18000c608  mov     [rbp+57h+var_60], eax
0x18000c60b  xorps   xmm0, xmm0
0x18000c60e  movups  [rbp+57h+OutBuffer], xmm0
0x18000c612  movups  [rbp+57h+var_48], xmm0
0x18000c616  xor     r14d, r14d
0x18000c619  mov     [rbp+57h+BytesReturned], r14d
0x18000c61d  mov     eax, 6D2h
0x18000c622  test    r12, r12
0x18000c625  jz      loc_18000C954
0x18000c62b  mov     [r12], r14
0x18000c62f  mov     [rbp+57h+var_A8], r14d
0x18000c633  mov     [rbp+57h+var_A4], ax
0x18000c637  lea     r9d, [r14+0Ch]; nInBufferSize
0x18000c63b  mov     ecx, r9d
0x18000c63e  lea     rax, [rbp+57h+InBuffer]
0x18000c642  mov     [rax], r14b
0x18000c645  inc     rax
0x18000c648  sub     rcx, 1
0x18000c64c  jnz     short loc_18000C642
0x18000c64e  mov     [rbp+57h+InBuffer], 1
0x18000c656  mov     [rsp+0F0h+lpOverlapped], r14; lpOverlapped
0x18000c65b  lea     rax, [rbp+57h+BytesReturned]
0x18000c65f  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x18000c664  mov     [rsp+0F0h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x18000c66c  lea     rax, [rbp+57h+OutBuffer]
0x18000c670  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x18000c675  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000c679  mov     edx, 2D1400h; dwIoControlCode
0x18000c67e  mov     rcx, rbx; hDevice
0x18000c681  call    cs:__imp_DeviceIoControl
0x18000c688  nop     dword ptr [rax+rax+00h]
0x18000c68d  test    eax, eax
0x18000c68f  jnz     short loc_18000C6A5
0x18000c691  call    GetLastFailureAsHRESULT
0x18000c696  mov     ebx, eax
0x18000c698  mov     [rbp+57h+var_A8], eax
0x18000c69b  mov     eax, 6E2h
0x18000c6a0  jmp     loc_18000C95C
0x18000c6a5  mov     rdi, r14
0x18000c6a8  mov     eax, 6E2h
0x18000c6ad  mov     [rbp+57h+var_A4], ax
0x18000c6b1  mov     ecx, dword ptr [rbp+57h+var_48]
0x18000c6b4  lea     r13d, [rcx+50h]
0x18000c6b8  mov     eax, ecx
0x18000c6ba  not     eax
0x18000c6bc  and     r13d, eax
0x18000c6bf  mov     esi, 108h
0x18000c6c4  mov     eax, 6F2h
0x18000c6c9  cmp     ecx, 2000h
0x18000c6cf  ja      loc_18000C92F
0x18000c6d5  cmp     esi, 100000h
0x18000c6db  ja      loc_18000C92F
0x18000c6e1  mov     [rbp+57h+var_A8], r14d
0x18000c6e5  mov     [rbp+57h+var_A4], ax
0x18000c6e9  lea     ebx, [rsi+50h]
0x18000c6ec  add     ebx, ecx
0x18000c6ee  test    rdi, rdi
0x18000c6f1  jz      short loc_18000C702
0x18000c6f3  mov     rcx, rdi; pv
0x18000c6f6  call    cs:__imp_CoTaskMemFree
0x18000c6fd  nop     dword ptr [rax+rax+00h]
0x18000c702  mov     ecx, ebx; cb
0x18000c704  call    cs:__imp_CoTaskMemAlloc
0x18000c70b  nop     dword ptr [rax+rax+00h]
0x18000c710  mov     rdi, rax
0x18000c713  test    rax, rax
0x18000c716  mov     eax, 6FCh
0x18000c71b  jz      loc_18000C928
0x18000c721  mov     [rbp+57h+var_A8], r14d
0x18000c725  mov     [rbp+57h+var_A4], ax
0x18000c729  mov     ecx, 58h ; 'X'
0x18000c72e  mov     rax, rdi
0x18000c731  mov     [rax], r14b
0x18000c734  inc     rax
0x18000c737  sub     rcx, 1
0x18000c73b  jnz     short loc_18000C731
0x18000c73d  lea     eax, [rcx+38h]
0x18000c740  mov     [rdi], ax
0x18000c743  mov     word ptr [rdi+7], 112h
0x18000c749  mov     [rdi+0Ch], esi
0x18000c74c  mov     dword ptr [rdi+10h], 14h
0x18000c753  mov     [rdi+20h], eax
0x18000c756  mov     r14d, r13d
0x18000c759  mov     [rdi+18h], r14
0x18000c75d  mov     byte ptr [rdi+6], 0Ah
0x18000c761  mov     byte ptr [rdi+24h], 46h ; 'F'
0x18000c765  and     byte ptr [rdi+25h], 0FEh
0x18000c769  or      byte ptr [rdi+25h], 2
0x18000c76d  mov     eax, r15d
0x18000c770  sar     eax, 8
0x18000c773  mov     [rdi+26h], al
0x18000c776  mov     [rdi+27h], r15b
0x18000c77a  mov     eax, esi
0x18000c77c  shr     eax, 8
0x18000c77f  mov     [rdi+2Bh], al
0x18000c782  mov     [rdi+2Ch], sil
0x18000c786  mov     [rsp+0F0h+lpOverlapped], rcx; lpOverlapped
0x18000c78b  lea     rax, [rbp+57h+BytesReturned]
0x18000c78f  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x18000c794  mov     [rsp+0F0h+nOutBufferSize], ebx; nOutBufferSize
0x18000c798  mov     [rsp+0F0h+lpOutBuffer], rdi; lpOutBuffer
0x18000c79d  mov     r9d, ebx; nInBufferSize
0x18000c7a0  mov     r8, rdi; lpInBuffer
0x18000c7a3  mov     edx, 4D004h; dwIoControlCode
0x18000c7a8  mov     rcx, [rbp+57h+hDevice]; hDevice
0x18000c7ac  call    cs:__imp_DeviceIoControl
0x18000c7b3  nop     dword ptr [rax+rax+00h]
0x18000c7b8  test    eax, eax
0x18000c7ba  jz      loc_18000C915
0x18000c7c0  mov     [rbp+57h+var_A8], 0
0x18000c7c7  mov     eax, 716h
0x18000c7cc  mov     [rbp+57h+var_A4], ax
0x18000c7d0  test    byte ptr [rdi+3Ah], 0Fh
0x18000c7d4  jnz     loc_18000C8C8
0x18000c7da  lea     r15, [rdi+r13]
0x18000c7de  movzx   ecx, byte ptr [r15+1]
0x18000c7e3  movzx   eax, byte ptr [r15]
0x18000c7e7  shl     eax, 8
0x18000c7ea  or      ecx, eax
0x18000c7ec  shl     ecx, 8
0x18000c7ef  movzx   eax, byte ptr [r15+2]
0x18000c7f4  or      ecx, eax
0x18000c7f6  shl     ecx, 8
0x18000c7f9  movzx   eax, byte ptr [r15+3]
0x18000c7fe  or      ecx, eax
0x18000c800  mov     eax, 72Bh
0x18000c805  cmp     ecx, 100000h
0x18000c80b  jnb     loc_18000C8BE
0x18000c811  mov     [rbp+57h+var_A4], ax
0x18000c815  lea     ebx, [rcx+4]
0x18000c818  cmp     ebx, esi
0x18000c81a  jbe     short loc_18000C82D
0x18000c81c  mov     esi, ebx
0x18000c81e  mov     ecx, dword ptr [rbp+57h+var_48]
0x18000c821  mov     r15d, [rbp+57h+var_AC]
0x18000c825  xor     r14d, r14d
0x18000c828  jmp     loc_18000C6C4
0x18000c82d  mov     r14d, ebx
0x18000c830  mov     ecx, ebx; cb
0x18000c832  call    cs:__imp_CoTaskMemAlloc
0x18000c839  nop     dword ptr [rax+rax+00h]
0x18000c83e  mov     rsi, rax
0x18000c841  mov     ecx, 739h
0x18000c846  test    rax, rax
0x18000c849  jz      short loc_18000C8AD
0x18000c84b  mov     [rbp+57h+var_A8], 0
0x18000c852  mov     [rbp+57h+var_A4], cx
0x18000c856  mov     r8d, r14d; Size
0x18000c859  mov     rdx, r15; Src
0x18000c85c  mov     rcx, rax; void *
0x18000c85f  call    memcpy_0
0x18000c864  mov     [r12], rsi
0x18000c868  lea     rax, WPP_GLOBAL_Control
0x18000c86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c876  cmp     rcx, rax
0x18000c879  jz      loc_18000C940
0x18000c87f  test    byte ptr [rcx+1Ch], 2
0x18000c883  jz      loc_18000C940
0x18000c889  mov     edx, 15h
0x18000c88e  mov     eax, [rbp+57h+var_AC]
0x18000c891  mov     dword ptr [rsp+0F0h+lpOutBuffer], eax
0x18000c895  mov     r9d, ebx
0x18000c898  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000c89f  mov     rcx, [rcx+10h]
0x18000c8a3  call    WPP_SF_dd
0x18000c8a8  jmp     loc_18000C940
0x18000c8ad  mov     ebx, 8007000Eh
0x18000c8b2  mov     [rbp+57h+var_A8], ebx
0x18000c8b5  mov     [rbp+57h+var_A2], cx
0x18000c8b9  jmp     loc_18000C940
0x18000c8be  mov     ebx, 80004005h
0x18000c8c3  mov     [rbp+57h+var_A8], ebx
0x18000c8c6  jmp     short loc_18000C922
0x18000c8c8  lea     rax, WPP_GLOBAL_Control
0x18000c8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8d6  cmp     rcx, rax
0x18000c8d9  jz      short loc_18000C903
0x18000c8db  test    byte ptr [rcx+1Ch], 40h
0x18000c8df  jz      short loc_18000C903
0x18000c8e1  movzx   eax, byte ptr [rdi+45h]
0x18000c8e5  movzx   edx, byte ptr [rdi+44h]
0x18000c8e9  movzx   r9d, byte ptr [rdi+3Ah]
0x18000c8ee  and     r9d, 0Fh
0x18000c8f2  mov     [rsp+0F0h+nOutBufferSize], eax
0x18000c8f6  mov     dword ptr [rsp+0F0h+lpOutBuffer], edx
0x18000c8fa  mov     rcx, [rcx+10h]
0x18000c8fe  call    WPP_SF_ddd
0x18000c903  mov     [rbp+57h+var_A8], 1
0x18000c90a  mov     eax, 71Fh
0x18000c90f  mov     [rbp+57h+var_A4], ax
0x18000c913  jmp     short loc_18000C940
0x18000c915  call    GetLastFailureAsHRESULT
0x18000c91a  mov     [rbp+57h+var_A8], eax
0x18000c91d  mov     eax, 716h
0x18000c922  mov     [rbp+57h+var_A2], ax
0x18000c926  jmp     short loc_18000C940
0x18000c928  mov     ebx, 8007000Eh
0x18000c92d  jmp     short loc_18000C959
0x18000c92f  mov     ebx, 80004005h
0x18000c934  mov     [rbp+57h+var_A8], ebx
0x18000c937  mov     [rbp+57h+var_A2], ax
0x18000c93b  test    rdi, rdi
0x18000c93e  jz      short loc_18000C960
0x18000c940  mov     rcx, rdi; pv
0x18000c943  call    cs:__imp_CoTaskMemFree
0x18000c94a  nop     dword ptr [rax+rax+00h]
0x18000c94f  mov     ebx, [rbp+57h+var_A8]
0x18000c952  jmp     short loc_18000C960
0x18000c954  mov     ebx, 80070057h
0x18000c959  mov     [rbp+57h+var_A8], ebx
0x18000c95c  mov     [rbp+57h+var_A2], ax
0x18000c960  lea     rcx, [rbp+57h+var_A8]; this
0x18000c964  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c969  mov     eax, ebx
0x18000c96b  mov     rcx, [rbp+57h+var_38]
0x18000c96f  xor     rcx, rsp; StackCookie
0x18000c972  call    __security_check_cookie
0x18000c977  mov     rbx, [rsp+0F0h+arg_8]
0x18000c97f  add     rsp, 0C0h
0x18000c986  pop     r15
0x18000c988  pop     r14
0x18000c98a  pop     r13
0x18000c98c  pop     r12
0x18000c98e  pop     rdi
0x18000c98f  pop     rsi
0x18000c990  pop     rbp
0x18000c991  retn
```
