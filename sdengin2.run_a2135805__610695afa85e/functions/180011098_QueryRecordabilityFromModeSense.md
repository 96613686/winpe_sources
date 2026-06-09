# QueryRecordabilityFromModeSense

- ea: `0x180011098`
- end: `0x1800113c8`
- name: `QueryRecordabilityFromModeSense`
- size: `816`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180011820`

## callees

- `0x1800083a0`
- `0x180011098`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180011166`
- `KERNEL32!DeviceIoControl` at `0x1800112ac`
- `KERNEL32!DeviceIoControl` at `0x180011166`
- `KERNEL32!DeviceIoControl` at `0x1800112ac`
- `ole32!CoTaskMemFree` at `0x1800111db`
- `ole32!CoTaskMemFree` at `0x180011378`
- `ole32!CoTaskMemFree` at `0x1800111db`
- `ole32!CoTaskMemFree` at `0x180011378`
- `ole32!CoTaskMemAlloc` at `0x1800111ea`
- `ole32!CoTaskMemAlloc` at `0x1800111ea`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "QueryRecordabilityFromModeSense", 0x63Fu, 1u);
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
0x180011098  mov     [rsp-8+arg_10], rbx
0x18001109d  push    rbp
0x18001109e  push    rsi
0x18001109f  push    rdi
0x1800110a0  push    r12
0x1800110a2  push    r13
0x1800110a4  push    r14
0x1800110a6  push    r15
0x1800110a8  lea     rbp, [rsp-27h]
0x1800110ad  sub     rsp, 0C0h
0x1800110b4  mov     rax, cs:__security_cookie
0x1800110bb  xor     rax, rsp
0x1800110be  mov     [rbp+57h+var_38], rax
0x1800110c2  mov     r14, rdx
0x1800110c5  mov     rbx, rcx
0x1800110c8  mov     [rbp+57h+hDevice], rcx
0x1800110cc  mov     r9d, 1; unsigned __int16
0x1800110d2  mov     r8d, 63Fh; unsigned __int16
0x1800110d8  lea     rdx, aQueryrecordabi; "QueryRecordabilityFromModeSense"
0x1800110df  lea     rcx, [rbp+57h+var_A8]; this
0x1800110e3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800110e8  xor     r15d, r15d
0x1800110eb  mov     [rbp+57h+BytesReturned], r15d
0x1800110ef  xor     eax, eax
0x1800110f1  mov     [rbp+57h+InBuffer], rax
0x1800110f5  mov     [rbp+57h+var_60], eax
0x1800110f8  xorps   xmm0, xmm0
0x1800110fb  movups  [rbp+57h+OutBuffer], xmm0
0x1800110ff  movups  [rbp+57h+var_48], xmm0
0x180011103  mov     eax, 64Eh
0x180011108  test    r14, r14
0x18001110b  jz      loc_180011389
0x180011111  mov     [r14], r15d
0x180011114  mov     [rbp+57h+var_A8], r15d
0x180011118  mov     [rbp+57h+var_A4], ax
0x18001111c  lea     r9d, [r15+0Ch]; nInBufferSize
0x180011120  mov     ecx, r9d
0x180011123  lea     rax, [rbp+57h+InBuffer]
0x180011127  mov     [rax], r15b
0x18001112a  inc     rax
0x18001112d  sub     rcx, 1
0x180011131  jnz     short loc_180011127
0x180011133  mov     [rbp+57h+InBuffer], 1
0x18001113b  mov     [rsp+0F0h+lpOverlapped], r15; lpOverlapped
0x180011140  lea     rax, [rbp+57h+BytesReturned]
0x180011144  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x180011149  mov     [rsp+0F0h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x180011151  lea     rax, [rbp+57h+OutBuffer]
0x180011155  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x18001115a  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18001115e  mov     edx, 2D1400h; dwIoControlCode
0x180011163  mov     rcx, rbx; hDevice
0x180011166  call    cs:__imp_DeviceIoControl
0x18001116d  nop     dword ptr [rax+rax+00h]
0x180011172  test    eax, eax
0x180011174  jnz     short loc_18001118A
0x180011176  call    GetLastFailureAsHRESULT
0x18001117b  mov     edi, eax
0x18001117d  mov     [rbp+57h+var_A8], eax
0x180011180  mov     eax, 65Eh
0x180011185  jmp     loc_180011391
0x18001118a  mov     rbx, r15
0x18001118d  mov     eax, 65Eh
0x180011192  mov     [rbp+57h+var_A4], ax
0x180011196  mov     ecx, dword ptr [rbp+57h+var_48]
0x180011199  lea     r13d, [rcx+50h]
0x18001119d  mov     eax, ecx
0x18001119f  not     eax
0x1800111a1  and     r13d, eax
0x1800111a4  mov     esi, r15d
0x1800111a7  mov     edx, 672h
0x1800111ac  mov     eax, esi
0x1800111ae  neg     eax
0x1800111b0  sbb     edi, edi
0x1800111b2  and     edi, 4
0x1800111b5  add     edi, 1Ch
0x1800111b8  cmp     ecx, 2000h
0x1800111be  ja      loc_180011364
0x1800111c4  mov     [rbp+57h+var_A8], r15d
0x1800111c8  mov     [rbp+57h+var_A4], dx
0x1800111cc  lea     r12d, [rcx+50h]
0x1800111d0  add     r12d, edi
0x1800111d3  test    rbx, rbx
0x1800111d6  jz      short loc_1800111E7
0x1800111d8  mov     rcx, rbx; pv
0x1800111db  call    cs:__imp_CoTaskMemFree
0x1800111e2  nop     dword ptr [rax+rax+00h]
0x1800111e7  mov     ecx, r12d; cb
0x1800111ea  call    cs:__imp_CoTaskMemAlloc
0x1800111f1  nop     dword ptr [rax+rax+00h]
0x1800111f6  mov     rbx, rax
0x1800111f9  test    rax, rax
0x1800111fc  mov     eax, 67Ch
0x180011201  jz      loc_18001135D
0x180011207  mov     [rbp+57h+var_A8], r15d
0x18001120b  mov     [rbp+57h+var_A4], ax
0x18001120f  mov     ecx, 58h ; 'X'
0x180011214  mov     rax, rbx
0x180011217  mov     [rax], r15b
0x18001121a  inc     rax
0x18001121d  sub     rcx, 1
0x180011221  jnz     short loc_180011217
0x180011223  lea     eax, [rcx+38h]
0x180011226  mov     [rbx], ax
0x180011229  mov     word ptr [rbx+7], 112h
0x18001122f  mov     [rbx+0Ch], edi
0x180011232  mov     dword ptr [rbx+10h], 14h
0x180011239  mov     [rbx+20h], eax
0x18001123c  mov     r15d, r13d
0x18001123f  mov     [rbx+18h], r15
0x180011243  mov     eax, esi
0x180011245  neg     eax
0x180011247  sbb     cl, cl
0x180011249  and     cl, 4
0x18001124c  add     cl, 6
0x18001124f  mov     [rbx+6], cl
0x180011252  or      byte ptr [rbx+25h], 8
0x180011256  test    esi, esi
0x180011258  jnz     short loc_180011265
0x18001125a  mov     [rbx+28h], dil
0x18001125e  mov     cl, 1Ah
0x180011260  lea     edi, [rsi+7]
0x180011263  jmp     short loc_180011274
0x180011265  mov     byte ptr [rbx+2Bh], 0
0x180011269  mov     [rbx+2Ch], dil
0x18001126d  mov     cl, 5Ah ; 'Z'
0x18001126f  mov     edi, 0Bh
0x180011274  mov     al, [rbx+26h]
0x180011277  and     al, 0EAh
0x180011279  or      al, 2Ah
0x18001127b  mov     [rbx+24h], cl
0x18001127e  mov     [rbx+26h], al
0x180011281  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x18001128a  lea     rax, [rbp+57h+BytesReturned]
0x18001128e  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x180011293  mov     [rsp+0F0h+nOutBufferSize], r12d; nOutBufferSize
0x180011298  mov     [rsp+0F0h+lpOutBuffer], rbx; lpOutBuffer
0x18001129d  mov     r9d, r12d; nInBufferSize
0x1800112a0  mov     r8, rbx; lpInBuffer
0x1800112a3  mov     edx, 4D004h; dwIoControlCode
0x1800112a8  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1800112ac  call    cs:__imp_DeviceIoControl
0x1800112b3  nop     dword ptr [rax+rax+00h]
0x1800112b8  test    eax, eax
0x1800112ba  jz      loc_18001134A
0x1800112c0  mov     [rbp+57h+var_A8], 0
0x1800112c7  mov     eax, 6A3h
0x1800112cc  mov     [rbp+57h+var_A4], ax
0x1800112d0  test    byte ptr [rbx+3Ah], 0Fh
0x1800112d4  jnz     short loc_1800112E0
0x1800112d6  lea     rax, [rdi+r13]
0x1800112da  test    byte ptr [rax+rbx], 33h
0x1800112de  jnz     short loc_1800112F6
0x1800112e0  inc     esi
0x1800112e2  cmp     esi, 2
0x1800112e5  jnb     loc_180011375
0x1800112eb  mov     ecx, dword ptr [rbp+57h+var_48]
0x1800112ee  xor     r15d, r15d
0x1800112f1  jmp     loc_1800111A7
0x1800112f6  lea     rax, WPP_GLOBAL_Control
0x1800112fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180011304  cmp     rcx, rax
0x180011307  jz      short loc_180011331
0x180011309  test    byte ptr [rcx+1Ch], 40h
0x18001130d  jz      short loc_180011331
0x18001130f  neg     esi
0x180011311  sbb     r9d, r9d
0x180011314  and     r9d, 4
0x180011318  add     r9d, 6
0x18001131c  mov     edx, 13h
0x180011321  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x180011328  mov     rcx, [rcx+10h]
0x18001132c  call    WPP_SF_d
0x180011331  mov     dword ptr [r14], 1
0x180011338  mov     [rbp+57h+var_A8], 0
0x18001133f  mov     eax, 6AAh
0x180011344  mov     [rbp+57h+var_A4], ax
0x180011348  jmp     short loc_180011375
0x18001134a  call    GetLastFailureAsHRESULT
0x18001134f  mov     [rbp+57h+var_A8], eax
0x180011352  mov     eax, 6A3h
0x180011357  mov     [rbp+57h+var_A2], ax
0x18001135b  jmp     short loc_180011375
0x18001135d  mov     edi, 8007000Eh
0x180011362  jmp     short loc_18001138E
0x180011364  mov     edi, 80004005h
0x180011369  mov     [rbp+57h+var_A8], edi
0x18001136c  mov     [rbp+57h+var_A2], dx
0x180011370  test    rbx, rbx
0x180011373  jz      short loc_180011395
0x180011375  mov     rcx, rbx; pv
0x180011378  call    cs:__imp_CoTaskMemFree
0x18001137f  nop     dword ptr [rax+rax+00h]
0x180011384  mov     edi, [rbp+57h+var_A8]
0x180011387  jmp     short loc_180011395
0x180011389  mov     edi, 80070057h
0x18001138e  mov     [rbp+57h+var_A8], edi
0x180011391  mov     [rbp+57h+var_A2], ax
0x180011395  lea     rcx, [rbp+57h+var_A8]; this
0x180011399  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001139e  mov     eax, edi
0x1800113a0  mov     rcx, [rbp+57h+var_38]
0x1800113a4  xor     rcx, rsp; StackCookie
0x1800113a7  call    __security_check_cookie
0x1800113ac  mov     rbx, [rsp+0F0h+arg_10]
0x1800113b4  add     rsp, 0C0h
0x1800113bb  pop     r15
0x1800113bd  pop     r14
0x1800113bf  pop     r13
0x1800113c1  pop     r12
0x1800113c3  pop     rdi
0x1800113c4  pop     rsi
0x1800113c5  pop     rbp
0x1800113c6  retn
```
