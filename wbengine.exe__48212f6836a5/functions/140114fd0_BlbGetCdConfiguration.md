# BlbGetCdConfiguration

- ea: `0x140114fd0`
- end: `0x14011540b`
- name: `BlbGetCdConfiguration`
- size: `1083`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x140115ffc`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x14003c434`
- `0x14007f520`
- `0x140114fd0`
- `0x140134cd2`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14011509b`
- `KERNEL32!GetLastError` at `0x140115342`
- `KERNEL32!GetLastError` at `0x14011509b`
- `KERNEL32!GetLastError` at `0x140115342`
- `KERNEL32!DeviceIoControl` at `0x14011508a`
- `KERNEL32!DeviceIoControl` at `0x1401151bd`
- `KERNEL32!DeviceIoControl` at `0x14011508a`
- `KERNEL32!DeviceIoControl` at `0x1401151bd`
- `ole32!CoTaskMemAlloc` at `0x14011512a`
- `ole32!CoTaskMemAlloc` at `0x140115226`
- `ole32!CoTaskMemAlloc` at `0x14011512a`
- `ole32!CoTaskMemAlloc` at `0x140115226`
- `ole32!CoTaskMemFree` at `0x140115121`
- `ole32!CoTaskMemFree` at `0x140115391`
- `ole32!CoTaskMemFree` at `0x140115121`
- `ole32!CoTaskMemFree` at `0x140115391`

## pseudocode

```c
__int64 __fastcall BlbGetCdConfiguration(HANDLE hDevice, int a2, _QWORD *a3)
{
  signed int LastError; // ebx
  PVOID *v6; // rcx
  int v7; // ecx
  _WORD *lpOutBuffer; // rdi
  unsigned int v9; // r15d
  unsigned int v10; // r14d
  DWORD nOutBufferSize; // r12d
  _WORD *v12; // rax
  __int16 v13; // cx
  HANDLE v14; // rcx
  unsigned __int8 *v15; // r12
  unsigned int v16; // ecx
  unsigned int v17; // r14d
  void *v18; // rax
  void *v19; // r15
  DWORD BytesReturned; // [rsp+40h] [rbp-19h] BYREF
  int v22; // [rsp+44h] [rbp-15h]
  unsigned int i; // [rsp+48h] [rbp-11h]
  HANDLE hDevicea; // [rsp+50h] [rbp-9h]
  _QWORD InBuffer[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 OutBuffer; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v27; // [rsp+78h] [rbp+1Fh]

  v22 = a2;
  hDevicea = hDevice;
  memset(InBuffer, 0, 12);
  BytesReturned = 0;
  OutBuffer = 0;
  v27 = 0;
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbdeviceutils.cpp", 0x457u, "ppHeader");
  *a3 = 0;
  *(_QWORD *)((char *)InBuffer + 4) = 0;
  LODWORD(InBuffer[0]) = 1;
  if ( DeviceIoControl(hDevice, 0x2D1400u, InBuffer, 0xCu, &OutBuffer, 0x20u, &BytesReturned, 0) )
  {
    v7 = v27;
    lpOutBuffer = 0;
    v9 = 264;
    v10 = ~(_DWORD)v27 & (v27 + 80);
    for ( i = v10; ; v10 = i )
    {
      nOutBufferSize = v7 + v9 + 80;
      if ( lpOutBuffer )
        CoTaskMemFree(lpOutBuffer);
      v12 = CoTaskMemAlloc(nOutBufferSize);
      lpOutBuffer = v12;
      if ( !v12 )
        break;
      memset_0(v12, 0, nOutBufferSize);
      v13 = v22;
      *((_BYTE *)lpOutBuffer + 37) &= ~1u;
      *((_BYTE *)lpOutBuffer + 37) |= 2u;
      *((_BYTE *)lpOutBuffer + 38) = HIBYTE(v13);
      *((_BYTE *)lpOutBuffer + 43) = BYTE1(v9);
      *lpOutBuffer = 56;
      *((_DWORD *)lpOutBuffer + 8) = 56;
      *((_BYTE *)lpOutBuffer + 39) = v13;
      v14 = hDevicea;
      *(_WORD *)((char *)lpOutBuffer + 7) = 274;
      *((_DWORD *)lpOutBuffer + 3) = v9;
      *((_DWORD *)lpOutBuffer + 4) = 20;
      *((_QWORD *)lpOutBuffer + 3) = v10;
      *((_BYTE *)lpOutBuffer + 6) = 10;
      *((_BYTE *)lpOutBuffer + 36) = 70;
      *((_BYTE *)lpOutBuffer + 44) = v9;
      if ( !DeviceIoControl(v14, 0x4D004u, lpOutBuffer, nOutBufferSize, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_42;
      }
      if ( (lpOutBuffer[29] & 0xF) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ddD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            &WPP_f71243d0ae613dd472d921e654574465_Traceguids,
            lpOutBuffer[29] & 0xF,
            *((unsigned __int8 *)lpOutBuffer + 68),
            *((unsigned __int8 *)lpOutBuffer + 69));
        }
        LastError = 1;
        goto LABEL_42;
      }
      v15 = (unsigned __int8 *)lpOutBuffer + v10;
      v16 = v15[3] | ((v15[2] | (((*v15 << 8) | v15[1]) << 8)) << 8);
      v17 = v16 + 4;
      if ( v16 >= 0xFFFFFFFC )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
        }
        LastError = -2147418113;
        goto LABEL_42;
      }
      LastError = 0;
      if ( v17 <= v9 )
      {
        v18 = CoTaskMemAlloc(v17);
        v19 = v18;
        if ( v18 )
        {
          memcpy_0(v18, v15, v17);
          *a3 = v19;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
          }
        }
        else
        {
          LastError = -2147024882;
        }
LABEL_42:
        CoTaskMemFree(lpOutBuffer);
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_43;
      }
      v7 = v27;
      v9 = v17;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    LastError = -2147024882;
    goto LABEL_46;
  }
  LastError = GetLastError();
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_43:
  if ( LastError < 0 )
  {
LABEL_46:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_d(v6[2], 62, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140114fd0  mov     [rsp-8+arg_8], rbx
0x140114fd5  mov     [rsp-8+arg_18], rdi
0x140114fda  push    rbp
0x140114fdb  push    r12
0x140114fdd  push    r13
0x140114fdf  push    r14
0x140114fe1  push    r15
0x140114fe3  lea     rbp, [rsp-37h]
0x140114fe8  sub     rsp, 90h
0x140114fef  mov     rax, cs:__security_cookie
0x140114ff6  xor     rax, rsp
0x140114ff9  mov     [rbp+57h+var_28], rax
0x140114ffd  xor     eax, eax
0x140114fff  mov     [rbp+57h+var_6C], edx
0x140115002  mov     [rbp+57h+hDevice], rcx
0x140115006  xorps   xmm0, xmm0
0x140115009  mov     [rbp+57h+InBuffer], rax
0x14011500d  mov     r13, r8
0x140115010  mov     [rbp+57h+var_50], eax
0x140115013  mov     rbx, rcx
0x140115016  mov     [rbp+57h+BytesReturned], eax
0x140115019  movups  [rbp+57h+OutBuffer], xmm0
0x14011501d  movups  [rbp+57h+var_38], xmm0
0x140115021  test    r8, r8
0x140115024  jnz     short loc_14011503E
0x140115026  lea     r8, aPpheader; "ppHeader"
0x14011502d  mov     edx, 457h; unsigned int
0x140115032  lea     rcx, aBaseStorBlbEng_29; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x140115039  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011503e  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x140115047  lea     rax, [rbp+57h+BytesReturned]
0x14011504b  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x140115050  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x140115054  lea     rax, [rbp+57h+OutBuffer]
0x140115058  mov     [rsp+0B0h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x140115060  mov     r9d, 0Ch; nInBufferSize
0x140115066  mov     [rsp+0B0h+lpOutBuffer], rax; lpOutBuffer
0x14011506b  mov     edx, 2D1400h; dwIoControlCode
0x140115070  mov     qword ptr [r13+0], 0
0x140115078  mov     rcx, rbx; hDevice
0x14011507b  mov     [rbp+57h+InBuffer+4], 0
0x140115083  mov     dword ptr [rbp+57h+InBuffer], 1
0x14011508a  call    cs:__imp_DeviceIoControl
0x140115090  lea     rdi, WPP_GLOBAL_Control
0x140115097  test    eax, eax
0x140115099  jnz     short loc_1401150F3
0x14011509b  call    cs:__imp_GetLastError
0x1401150a1  mov     ebx, eax
0x1401150a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401150aa  cmp     rcx, rdi
0x1401150ad  jz      short loc_1401150DA
0x1401150af  test    byte ptr [rcx+1Ch], 1
0x1401150b3  jz      short loc_1401150DA
0x1401150b5  cmp     byte ptr [rcx+19h], 2
0x1401150b9  jb      short loc_1401150DA
0x1401150bb  mov     rcx, [rcx+10h]
0x1401150bf  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x1401150c6  mov     edx, 38h ; '8'
0x1401150cb  mov     r9d, eax
0x1401150ce  call    WPP_SF_d
0x1401150d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401150da  test    ebx, ebx
0x1401150dc  jle     short loc_1401150E7
0x1401150de  movzx   ebx, bx
0x1401150e1  or      ebx, 80070000h
0x1401150e7  lea     r15, WPP_GLOBAL_Control
0x1401150ee  jmp     loc_14011539E
0x1401150f3  mov     ecx, dword ptr [rbp+57h+var_38]
0x1401150f6  xor     edi, edi
0x1401150f8  mov     eax, ecx
0x1401150fa  mov     r15d, 108h
0x140115100  not     eax
0x140115102  lea     r14d, [rcx+50h]
0x140115106  and     r14d, eax
0x140115109  mov     [rbp+57h+var_68], r14d
0x14011510d  lea     r12d, [r15+50h]
0x140115111  mov     ebx, 38h ; '8'
0x140115116  add     r12d, ecx
0x140115119  test    rdi, rdi
0x14011511c  jz      short loc_140115127
0x14011511e  mov     rcx, rdi; pv
0x140115121  call    cs:__imp_CoTaskMemFree
0x140115127  mov     ecx, r12d; cb
0x14011512a  call    cs:__imp_CoTaskMemAlloc
0x140115130  mov     rdi, rax
0x140115133  test    rax, rax
0x140115136  jz      loc_1401153A4
0x14011513c  mov     r8d, r12d; Size
0x14011513f  xor     edx, edx; Val
0x140115141  mov     rcx, rax; void *
0x140115144  call    memset_0
0x140115149  mov     ecx, [rbp+57h+var_6C]
0x14011514c  mov     r9d, r12d; nInBufferSize
0x14011514f  and     byte ptr [rdi+25h], 0FEh
0x140115153  mov     eax, ecx
0x140115155  or      byte ptr [rdi+25h], 2
0x140115159  mov     r8, rdi; lpInBuffer
0x14011515c  sar     eax, 8
0x14011515f  mov     edx, 4D004h; dwIoControlCode
0x140115164  mov     [rdi+26h], al
0x140115167  mov     eax, r15d
0x14011516a  shr     eax, 8
0x14011516d  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x140115176  mov     [rdi+2Bh], al
0x140115179  lea     rax, [rbp+57h+BytesReturned]
0x14011517d  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x140115182  mov     [rdi], bx
0x140115185  mov     [rdi+20h], ebx
0x140115188  mov     [rdi+27h], cl
0x14011518b  mov     rcx, [rbp+57h+hDevice]; hDevice
0x14011518f  mov     ebx, r14d
0x140115192  mov     [rsp+0B0h+nOutBufferSize], r12d; nOutBufferSize
0x140115197  mov     [rsp+0B0h+lpOutBuffer], rdi; lpOutBuffer
0x14011519c  mov     word ptr [rdi+7], 112h
0x1401151a2  mov     [rdi+0Ch], r15d
0x1401151a6  mov     dword ptr [rdi+10h], 14h
0x1401151ad  mov     [rdi+18h], rbx
0x1401151b1  mov     byte ptr [rdi+6], 0Ah
0x1401151b5  mov     byte ptr [rdi+24h], 46h ; 'F'
0x1401151b9  mov     [rdi+2Ch], r15b
0x1401151bd  call    cs:__imp_DeviceIoControl
0x1401151c3  test    eax, eax
0x1401151c5  jz      loc_140115342
0x1401151cb  test    byte ptr [rdi+3Ah], 0Fh
0x1401151cf  jnz     loc_1401152EC
0x1401151d5  lea     r12, [rbx+rdi]
0x1401151d9  movzx   eax, byte ptr [r12]
0x1401151de  movzx   ecx, byte ptr [r12+1]
0x1401151e4  shl     eax, 8
0x1401151e7  or      ecx, eax
0x1401151e9  movzx   eax, byte ptr [r12+2]
0x1401151ef  shl     ecx, 8
0x1401151f2  or      ecx, eax
0x1401151f4  movzx   eax, byte ptr [r12+3]
0x1401151fa  shl     ecx, 8
0x1401151fd  or      ecx, eax
0x1401151ff  lea     r14d, [rcx+4]
0x140115203  cmp     r14d, 4
0x140115207  jb      loc_1401152A6
0x14011520d  xor     ebx, ebx
0x14011520f  cmp     r14d, r15d
0x140115212  jbe     short loc_140115223
0x140115214  mov     ecx, dword ptr [rbp+57h+var_38]
0x140115217  mov     r15d, r14d
0x14011521a  mov     r14d, [rbp+57h+var_68]
0x14011521e  jmp     loc_14011510D
0x140115223  mov     ecx, r14d; cb
0x140115226  call    cs:__imp_CoTaskMemAlloc
0x14011522c  mov     r15, rax
0x14011522f  test    rax, rax
0x140115232  jnz     short loc_140115245
0x140115234  mov     ebx, 8007000Eh
0x140115239  lea     r15, WPP_GLOBAL_Control
0x140115240  jmp     loc_14011538E
0x140115245  mov     r8d, r14d; Size
0x140115248  mov     rdx, r12; Src
0x14011524b  mov     rcx, r15; void *
0x14011524e  call    memcpy_0
0x140115253  mov     [r13+0], r15
0x140115257  mov     rcx, cs:WPP_GLOBAL_Control
0x14011525e  lea     r15, WPP_GLOBAL_Control
0x140115265  cmp     rcx, r15
0x140115268  jz      loc_14011538E
0x14011526e  test    byte ptr [rcx+1Ch], 1
0x140115272  jz      loc_14011538E
0x140115278  cmp     byte ptr [rcx+19h], 5
0x14011527c  jb      loc_14011538E
0x140115282  mov     eax, [rbp+57h+var_6C]
0x140115285  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x14011528c  mov     rcx, [rcx+10h]
0x140115290  mov     edx, 3Dh ; '='
0x140115295  mov     r9d, r14d
0x140115298  mov     dword ptr [rsp+0B0h+lpOutBuffer], eax
0x14011529c  call    WPP_SF_dd
0x1401152a1  jmp     loc_14011538E
0x1401152a6  mov     rax, cs:WPP_GLOBAL_Control
0x1401152ad  lea     r15, WPP_GLOBAL_Control
0x1401152b4  cmp     rax, r15
0x1401152b7  jz      short loc_1401152E2
0x1401152b9  test    byte ptr [rax+1Ch], 1
0x1401152bd  jz      short loc_1401152E2
0x1401152bf  cmp     byte ptr [rax+19h], 2
0x1401152c3  jb      short loc_1401152E2
0x1401152c5  mov     edx, 3Bh ; ';'
0x1401152ca  mov     dword ptr [rsp+0B0h+lpOutBuffer], ecx
0x1401152ce  mov     rcx, [rax+10h]
0x1401152d2  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x1401152d9  lea     r9d, [rdx-37h]
0x1401152dd  call    WPP_SF_dd
0x1401152e2  mov     ebx, 8000FFFFh
0x1401152e7  jmp     loc_14011538E
0x1401152ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1401152f3  lea     r15, WPP_GLOBAL_Control
0x1401152fa  cmp     rcx, r15
0x1401152fd  jz      short loc_14011533B
0x1401152ff  test    byte ptr [rcx+1Ch], 1
0x140115303  jz      short loc_14011533B
0x140115305  cmp     byte ptr [rcx+19h], 2
0x140115309  jb      short loc_14011533B
0x14011530b  movzx   r8d, byte ptr [rdi+44h]
0x140115310  mov     edx, 3Ah ; ':'
0x140115315  movzx   eax, byte ptr [rdi+45h]
0x140115319  movzx   r9d, byte ptr [rdi+3Ah]
0x14011531e  mov     rcx, [rcx+10h]
0x140115322  and     r9d, 0Fh
0x140115326  mov     [rsp+0B0h+nOutBufferSize], eax
0x14011532a  mov     dword ptr [rsp+0B0h+lpOutBuffer], r8d
0x14011532f  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115336  call    WPP_SF_ddD
0x14011533b  mov     ebx, 1
0x140115340  jmp     short loc_14011538E
0x140115342  call    cs:__imp_GetLastError
0x140115348  mov     ebx, eax
0x14011534a  mov     rcx, cs:WPP_GLOBAL_Control
0x140115351  lea     r15, WPP_GLOBAL_Control
0x140115358  cmp     rcx, r15
0x14011535b  jz      short loc_140115381
0x14011535d  test    byte ptr [rcx+1Ch], 1
0x140115361  jz      short loc_140115381
0x140115363  cmp     byte ptr [rcx+19h], 2
0x140115367  jb      short loc_140115381
0x140115369  mov     rcx, [rcx+10h]
0x14011536d  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115374  mov     edx, 39h ; '9'
0x140115379  mov     r9d, eax
0x14011537c  call    WPP_SF_d
0x140115381  test    ebx, ebx
0x140115383  jle     short loc_14011538E
0x140115385  movzx   ebx, bx
0x140115388  or      ebx, 80070000h
0x14011538e  mov     rcx, rdi; pv
0x140115391  call    cs:__imp_CoTaskMemFree
0x140115397  mov     rcx, cs:WPP_GLOBAL_Control
0x14011539e  test    ebx, ebx
0x1401153a0  jns     short loc_1401153E0
0x1401153a2  jmp     short loc_1401153B7
0x1401153a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401153ab  lea     r15, WPP_GLOBAL_Control
0x1401153b2  mov     ebx, 8007000Eh
0x1401153b7  cmp     rcx, r15
0x1401153ba  jz      short loc_1401153E0
0x1401153bc  test    byte ptr [rcx+1Ch], 1
0x1401153c0  jz      short loc_1401153E0
0x1401153c2  cmp     byte ptr [rcx+19h], 2
0x1401153c6  jb      short loc_1401153E0
0x1401153c8  mov     rcx, [rcx+10h]
0x1401153cc  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x1401153d3  mov     edx, 3Eh ; '>'
0x1401153d8  mov     r9d, ebx
0x1401153db  call    WPP_SF_d
0x1401153e0  mov     eax, ebx
0x1401153e2  mov     rcx, [rbp+57h+var_28]
0x1401153e6  xor     rcx, rsp; StackCookie
0x1401153e9  call    __security_check_cookie
0x1401153ee  lea     r11, [rsp+0B0h+var_20]
0x1401153f6  mov     rbx, [r11+38h]
0x1401153fa  mov     rdi, [r11+48h]
0x1401153fe  mov     rsp, r11
0x140115401  pop     r15
0x140115403  pop     r14
0x140115405  pop     r13
0x140115407  pop     r12
0x140115409  pop     rbp
0x14011540a  retn
```
