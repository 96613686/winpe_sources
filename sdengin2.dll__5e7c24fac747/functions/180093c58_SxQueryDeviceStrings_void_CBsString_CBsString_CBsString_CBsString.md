# SxQueryDeviceStrings(void *,CBsString *,CBsString *,CBsString *,CBsString *)

- ea: `0x180093c58`
- end: `0x180094151`
- name: `?SxQueryDeviceStrings@@YAJPEAXPEAVCBsString@@111@Z`
- size: `1273`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct CBsString *this, struct CBsString *, struct CBsString *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000ffa8`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x180008240`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180093aac`
- `0x180093c58`
- `0x180099bdc`
- `0x1800c97da`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180093dcf`
- `KERNEL32!DeviceIoControl` at `0x180093dcf`
- `ole32!CoTaskMemFree` at `0x180094120`
- `ole32!CoTaskMemFree` at `0x180094129`
- `ole32!CoTaskMemFree` at `0x180094120`
- `ole32!CoTaskMemFree` at `0x180094129`
- `ole32!CoTaskMemAlloc` at `0x180093d38`
- `ole32!CoTaskMemAlloc` at `0x180093d6f`
- `ole32!CoTaskMemAlloc` at `0x180093d38`
- `ole32!CoTaskMemAlloc` at `0x180093d6f`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceStrings(
        HANDLE hDevice,
        struct CBsString *this,
        struct CBsString *a3,
        struct CBsString *a4,
        struct CBsString *a5)
{
  unsigned int *lpOutBuffer; // rbx
  _QWORD *v10; // r13
  CBsString *v11; // rsi
  __int16 v12; // ax
  __int64 v13; // rcx
  int LastFailureAsHRESULT; // eax
  __int16 v15; // ax
  bool v16; // sf
  PVOID *v17; // rcx
  DWORD v18; // eax
  int v19; // edi
  PVOID *v20; // rcx
  unsigned int v21; // ebx
  int v23; // [rsp+40h] [rbp-31h] BYREF
  __int16 v24; // [rsp+44h] [rbp-2Dh]
  __int16 v25; // [rsp+46h] [rbp-2Bh]
  DWORD BytesReturned; // [rsp+D0h] [rbp+5Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "SxQueryDeviceStrings", 874, 1);
  lpOutBuffer = 0;
  v10 = 0;
  BytesReturned = 0;
  if ( this )
    CBsString::Empty(this);
  if ( a3 )
    CBsString::Empty(a3);
  if ( a4 )
    CBsString::Empty(a4);
  v11 = a5;
  if ( a5 )
    CBsString::Empty(a5);
  v12 = 891;
  if ( hDevice == (HANDLE)-1LL )
    goto LABEL_10;
  v24 = 891;
  v12 = 893;
  if ( !this || (v24 = 893, v12 = 894, !a3) || (v24 = 894, v12 = 895, !a4) || (v24 = 895, v12 = 896, !v11) )
  {
LABEL_10:
    v23 = -2147024809;
    goto LABEL_11;
  }
  v23 = 0;
  v24 = 896;
  v10 = CoTaskMemAlloc(0x4000u);
  v12 = 899;
  if ( !v10
    || (v23 = 0,
        v24 = 899,
        memset_0(v10, 0, 0x4000u),
        lpOutBuffer = (unsigned int *)CoTaskMemAlloc(0x4000u),
        v12 = 903,
        !lpOutBuffer) )
  {
    v23 = -2147024882;
    goto LABEL_11;
  }
  v23 = 0;
  v24 = 903;
  memset_0(lpOutBuffer, 0, 0x4000u);
  *v10 = 0;
  if ( DeviceIoControl(hDevice, 0x2D1400u, v10, 0x4000u, lpOutBuffer, 0x4000u, &BytesReturned, 0) )
    goto LABEL_24;
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
  if ( LastFailureAsHRESULT == -2147024895 )
  {
    v15 = 926;
LABEL_70:
    v23 = 1;
LABEL_71:
    v24 = v15;
    goto LABEL_72;
  }
  v23 = LastFailureAsHRESULT;
  v16 = LastFailureAsHRESULT < 0;
  v12 = 929;
  if ( !v16 )
  {
    v24 = 929;
LABEL_24:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, BytesReturned);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( BytesReturned < 0x28 || lpOutBuffer[1] < 0x28 )
    {
      if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x10000000) != 0 )
        WPP_SF_(v17[2], 21, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids);
      v15 = 943;
      goto LABEL_70;
    }
    if ( v17 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
      {
        WPP_SF_d(v17[2], 22, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, *lpOutBuffer);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
        {
          WPP_SF_d(v17[2], 23, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, lpOutBuffer[1]);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
          {
            WPP_SF_d(v17[2], 24, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, *((unsigned __int8 *)lpOutBuffer + 8));
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
            {
              WPP_SF_d(
                v17[2],
                25,
                WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids,
                *((unsigned __int8 *)lpOutBuffer + 9));
              v17 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v17 != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
              {
                WPP_SF_d(
                  v17[2],
                  26,
                  WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids,
                  *((unsigned __int8 *)lpOutBuffer + 10));
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x1000000) != 0 )
                WPP_SF_d(
                  v17[2],
                  27,
                  WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids,
                  *((unsigned __int8 *)lpOutBuffer + 11));
            }
          }
        }
      }
    }
    v18 = lpOutBuffer[1];
    if ( BytesReturned < v18 )
      v18 = BytesReturned;
    v19 = v18 - 1;
    v23 = CopyDeviceString(this, v18 - 1);
    v12 = 964;
    if ( v23 >= 0 )
    {
      v24 = 964;
      v23 = CopyDeviceString(a3, v19);
      v12 = 965;
      if ( v23 >= 0 )
      {
        v24 = 965;
        v23 = CopyDeviceString(a4, v19);
        v12 = 966;
        if ( v23 >= 0 )
        {
          v24 = 966;
          v23 = CopyDeviceString(v11, v19);
          v12 = 967;
          if ( v23 >= 0 )
          {
            v24 = 967;
            v20 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  28,
                  WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids,
                  *(_QWORD *)this);
                v20 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v20 != &WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)v20 + 7) & 0x1000000) != 0 )
                {
                  WPP_SF_S(v20[2], 29, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, *(_QWORD *)a3);
                  v20 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v20 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_DWORD *)v20 + 7) & 0x1000000) != 0 )
                  {
                    WPP_SF_S(v20[2], 30, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, *(_QWORD *)a4);
                    v20 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v20 != &WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x1000000) != 0 )
                    WPP_SF_S(v20[2], 31, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids, *(_QWORD *)v11);
                }
              }
            }
            v23 = 0;
            v15 = 974;
            goto LABEL_71;
          }
        }
      }
    }
  }
LABEL_11:
  v25 = v12;
LABEL_72:
  CoTaskMemFree(v10);
  CoTaskMemFree(lpOutBuffer);
  v21 = v23;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return v21;
}

```

## disassembly

```asm
0x180093c58  push    rbp
0x180093c5a  push    rbx
0x180093c5b  push    rsi
0x180093c5c  push    rdi
0x180093c5d  push    r12
0x180093c5f  push    r13
0x180093c61  push    r14
0x180093c63  push    r15
0x180093c65  lea     rbp, [rsp-17h]
0x180093c6a  sub     rsp, 88h
0x180093c71  mov     r15, r9
0x180093c74  mov     r14, r8
0x180093c77  mov     r12, rdx
0x180093c7a  mov     rdi, rcx
0x180093c7d  mov     r9d, 1; unsigned __int16
0x180093c83  lea     rdx, aSxquerydevices; "SxQueryDeviceStrings"
0x180093c8a  mov     r8d, 36Ah; unsigned __int16
0x180093c90  lea     rcx, [rbp+4Fh+var_80]; this
0x180093c94  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180093c99  xor     ebx, ebx
0x180093c9b  xor     r13d, r13d
0x180093c9e  mov     [rbp+4Fh+BytesReturned], ebx
0x180093ca1  test    r12, r12
0x180093ca4  jz      short loc_180093CAE
0x180093ca6  mov     rcx, r12; this
0x180093ca9  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180093cae  test    r14, r14
0x180093cb1  jz      short loc_180093CBB
0x180093cb3  mov     rcx, r14; this
0x180093cb6  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180093cbb  test    r15, r15
0x180093cbe  jz      short loc_180093CC8
0x180093cc0  mov     rcx, r15; this
0x180093cc3  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180093cc8  mov     rsi, [rbp+4Fh+arg_20]
0x180093ccc  test    rsi, rsi
0x180093ccf  jz      short loc_180093CD9
0x180093cd1  mov     rcx, rsi; this
0x180093cd4  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180093cd9  mov     eax, 37Bh
0x180093cde  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180093ce2  jnz     short loc_180093CF4
0x180093ce4  mov     [rbp+4Fh+var_80], 80070057h
0x180093ceb  mov     [rbp+4Fh+var_7A], ax
0x180093cef  jmp     loc_18009411D
0x180093cf4  mov     [rbp+4Fh+var_7C], ax
0x180093cf8  mov     eax, 37Dh
0x180093cfd  test    r12, r12
0x180093d00  jz      short loc_180093CE4
0x180093d02  mov     [rbp+4Fh+var_7C], ax
0x180093d06  mov     eax, 37Eh
0x180093d0b  test    r14, r14
0x180093d0e  jz      short loc_180093CE4
0x180093d10  mov     [rbp+4Fh+var_7C], ax
0x180093d14  mov     eax, 37Fh
0x180093d19  test    r15, r15
0x180093d1c  jz      short loc_180093CE4
0x180093d1e  mov     [rbp+4Fh+var_7C], ax
0x180093d22  mov     eax, 380h
0x180093d27  test    rsi, rsi
0x180093d2a  jz      short loc_180093CE4
0x180093d2c  mov     ecx, 4000h; cb
0x180093d31  mov     [rbp+4Fh+var_80], ebx
0x180093d34  mov     [rbp+4Fh+var_7C], ax
0x180093d38  call    cs:__imp_CoTaskMemAlloc
0x180093d3e  mov     r13, rax
0x180093d41  test    rax, rax
0x180093d44  mov     eax, 383h
0x180093d49  jnz     short loc_180093D54
0x180093d4b  mov     [rbp+4Fh+var_80], 8007000Eh
0x180093d52  jmp     short loc_180093CEB
0x180093d54  mov     [rbp+4Fh+var_80], ebx
0x180093d57  xor     edx, edx; Val
0x180093d59  mov     ebx, 4000h
0x180093d5e  mov     [rbp+4Fh+var_7C], ax
0x180093d62  mov     r8d, ebx; Size
0x180093d65  mov     rcx, r13; void *
0x180093d68  call    memset_0
0x180093d6d  mov     ecx, ebx; cb
0x180093d6f  call    cs:__imp_CoTaskMemAlloc
0x180093d75  mov     rbx, rax
0x180093d78  test    rax, rax
0x180093d7b  mov     eax, 387h
0x180093d80  jz      short loc_180093D4B
0x180093d82  xor     edx, edx; Val
0x180093d84  mov     [rbp+4Fh+var_80], 0
0x180093d8b  mov     r8d, 4000h; Size
0x180093d91  mov     [rbp+4Fh+var_7C], ax
0x180093d95  mov     rcx, rbx; void *
0x180093d98  call    memset_0
0x180093d9d  xor     eax, eax
0x180093d9f  mov     r9d, 4000h; nInBufferSize
0x180093da5  mov     [rsp+0C0h+lpOverlapped], rax; lpOverlapped
0x180093daa  mov     r8, r13; lpInBuffer
0x180093dad  mov     [r13+0], rax
0x180093db1  mov     edx, 2D1400h; dwIoControlCode
0x180093db6  lea     rax, [rbp+4Fh+BytesReturned]
0x180093dba  mov     rcx, rdi; hDevice
0x180093dbd  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x180093dc2  mov     [rsp+0C0h+nOutBufferSize], 4000h; nOutBufferSize
0x180093dca  mov     [rsp+0C0h+lpOutBuffer], rbx; lpOutBuffer
0x180093dcf  call    cs:__imp_DeviceIoControl
0x180093dd5  test    eax, eax
0x180093dd7  jnz     short loc_180093E03
0x180093dd9  call    GetLastFailureAsHRESULT
0x180093dde  cmp     eax, 80070001h
0x180093de3  jnz     short loc_180093DEF
0x180093de5  mov     eax, 39Eh
0x180093dea  jmp     loc_180094112
0x180093def  mov     [rbp+4Fh+var_80], eax
0x180093df2  test    eax, eax
0x180093df4  mov     eax, 3A1h
0x180093df9  js      loc_180093CEB
0x180093dff  mov     [rbp+4Fh+var_7C], ax
0x180093e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e0a  lea     rdi, WPP_GLOBAL_Control
0x180093e11  cmp     rcx, rdi
0x180093e14  jz      short loc_180093E3F
0x180093e16  test    dword ptr [rcx+1Ch], 1000000h
0x180093e1d  jz      short loc_180093E3F
0x180093e1f  mov     r9d, [rbp+4Fh+BytesReturned]
0x180093e23  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093e2a  mov     rcx, [rcx+10h]
0x180093e2e  mov     edx, 14h
0x180093e33  call    WPP_SF_d
0x180093e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e3f  cmp     [rbp+4Fh+BytesReturned], 28h ; '('
0x180093e43  jb      loc_1800940EA
0x180093e49  cmp     dword ptr [rbx+4], 28h ; '('
0x180093e4d  jb      loc_1800940EA
0x180093e53  cmp     rcx, rdi
0x180093e56  jz      loc_180093F73
0x180093e5c  test    dword ptr [rcx+1Ch], 1000000h
0x180093e63  jz      short loc_180093E84
0x180093e65  mov     r9d, [rbx]
0x180093e68  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093e6f  mov     rcx, [rcx+10h]
0x180093e73  mov     edx, 16h
0x180093e78  call    WPP_SF_d
0x180093e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e84  cmp     rcx, rdi
0x180093e87  jz      loc_180093F73
0x180093e8d  test    dword ptr [rcx+1Ch], 1000000h
0x180093e94  jz      short loc_180093EB6
0x180093e96  mov     r9d, [rbx+4]
0x180093e9a  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093ea1  mov     rcx, [rcx+10h]
0x180093ea5  mov     edx, 17h
0x180093eaa  call    WPP_SF_d
0x180093eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180093eb6  cmp     rcx, rdi
0x180093eb9  jz      loc_180093F73
0x180093ebf  test    dword ptr [rcx+1Ch], 1000000h
0x180093ec6  jz      short loc_180093EE9
0x180093ec8  movzx   r9d, byte ptr [rbx+8]
0x180093ecd  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093ed4  mov     rcx, [rcx+10h]
0x180093ed8  mov     edx, 18h
0x180093edd  call    WPP_SF_d
0x180093ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ee9  cmp     rcx, rdi
0x180093eec  jz      loc_180093F73
0x180093ef2  test    dword ptr [rcx+1Ch], 1000000h
0x180093ef9  jz      short loc_180093F1C
0x180093efb  movzx   r9d, byte ptr [rbx+9]
0x180093f00  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093f07  mov     rcx, [rcx+10h]
0x180093f0b  mov     edx, 19h
0x180093f10  call    WPP_SF_d
0x180093f15  mov     rcx, cs:WPP_GLOBAL_Control
0x180093f1c  cmp     rcx, rdi
0x180093f1f  jz      short loc_180093F73
0x180093f21  test    dword ptr [rcx+1Ch], 1000000h
0x180093f28  jz      short loc_180093F4B
0x180093f2a  movzx   r9d, byte ptr [rbx+0Ah]
0x180093f2f  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093f36  mov     rcx, [rcx+10h]
0x180093f3a  mov     edx, 1Ah
0x180093f3f  call    WPP_SF_d
0x180093f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180093f4b  cmp     rcx, rdi
0x180093f4e  jz      short loc_180093F73
0x180093f50  test    dword ptr [rcx+1Ch], 1000000h
0x180093f57  jz      short loc_180093F73
0x180093f59  movzx   r9d, byte ptr [rbx+0Bh]
0x180093f5e  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180093f65  mov     rcx, [rcx+10h]
0x180093f69  mov     edx, 1Bh
0x180093f6e  call    WPP_SF_d
0x180093f73  mov     eax, [rbx+4]
0x180093f76  mov     rdx, rbx
0x180093f79  cmp     [rbp+4Fh+BytesReturned], eax
0x180093f7c  mov     rcx, r12; this
0x180093f7f  mov     r8d, [rbx+0Ch]
0x180093f83  cmovb   eax, [rbp+4Fh+BytesReturned]
0x180093f87  lea     edi, [rax-1]
0x180093f8a  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x180093f8e  call    CopyDeviceString
0x180093f93  mov     [rbp+4Fh+var_80], eax
0x180093f96  test    eax, eax
0x180093f98  mov     eax, 3C4h
0x180093f9d  js      loc_180093CEB
0x180093fa3  mov     [rbp+4Fh+var_7C], ax
0x180093fa7  mov     rdx, rbx
0x180093faa  mov     r8d, [rbx+10h]
0x180093fae  mov     rcx, r14; this
0x180093fb1  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x180093fb5  call    CopyDeviceString
0x180093fba  mov     [rbp+4Fh+var_80], eax
0x180093fbd  test    eax, eax
0x180093fbf  mov     eax, 3C5h
0x180093fc4  js      loc_180093CEB
0x180093fca  mov     [rbp+4Fh+var_7C], ax
0x180093fce  mov     rdx, rbx
0x180093fd1  mov     r8d, [rbx+14h]
0x180093fd5  mov     rcx, r15; this
0x180093fd8  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x180093fdc  call    CopyDeviceString
0x180093fe1  mov     [rbp+4Fh+var_80], eax
0x180093fe4  test    eax, eax
0x180093fe6  mov     eax, 3C6h
0x180093feb  js      loc_180093CEB
0x180093ff1  mov     [rbp+4Fh+var_7C], ax
0x180093ff5  mov     rdx, rbx
0x180093ff8  mov     r8d, [rbx+18h]
0x180093ffc  mov     rcx, rsi; this
0x180093fff  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x180094003  call    CopyDeviceString
0x180094008  mov     [rbp+4Fh+var_80], eax
0x18009400b  test    eax, eax
0x18009400d  mov     eax, 3C7h
0x180094012  js      loc_180093CEB
0x180094018  mov     [rbp+4Fh+var_7C], ax
0x18009401c  mov     rcx, cs:WPP_GLOBAL_Control
0x180094023  lea     rdi, WPP_GLOBAL_Control
0x18009402a  cmp     rcx, rdi
0x18009402d  jz      loc_1800940DC
0x180094033  test    dword ptr [rcx+1Ch], 1000000h
0x18009403a  jz      short loc_18009405C
0x18009403c  mov     r9, [r12]
0x180094040  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180094047  mov     rcx, [rcx+10h]
0x18009404b  mov     edx, 1Ch
0x180094050  call    WPP_SF_S
0x180094055  mov     rcx, cs:WPP_GLOBAL_Control
0x18009405c  cmp     rcx, rdi
0x18009405f  jz      short loc_1800940DC
0x180094061  test    dword ptr [rcx+1Ch], 1000000h
0x180094068  jz      short loc_180094089
0x18009406a  mov     r9, [r14]
0x18009406d  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180094074  mov     rcx, [rcx+10h]
0x180094078  mov     edx, 1Dh
0x18009407d  call    WPP_SF_S
0x180094082  mov     rcx, cs:WPP_GLOBAL_Control
0x180094089  cmp     rcx, rdi
0x18009408c  jz      short loc_1800940DC
0x18009408e  test    dword ptr [rcx+1Ch], 1000000h
0x180094095  jz      short loc_1800940B6
0x180094097  mov     r9, [r15]
0x18009409a  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x1800940a1  mov     rcx, [rcx+10h]
0x1800940a5  mov     edx, 1Eh
0x1800940aa  call    WPP_SF_S
0x1800940af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800940b6  cmp     rcx, rdi
0x1800940b9  jz      short loc_1800940DC
0x1800940bb  test    dword ptr [rcx+1Ch], 1000000h
0x1800940c2  jz      short loc_1800940DC
0x1800940c4  mov     r9, [rsi]
0x1800940c7  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x1800940ce  mov     rcx, [rcx+10h]
0x1800940d2  mov     edx, 1Fh
0x1800940d7  call    WPP_SF_S
0x1800940dc  mov     [rbp+4Fh+var_80], 0
0x1800940e3  mov     eax, 3CEh
0x1800940e8  jmp     short loc_180094119
0x1800940ea  cmp     rcx, rdi
0x1800940ed  jz      short loc_18009410D
0x1800940ef  test    dword ptr [rcx+1Ch], 10000000h
0x1800940f6  jz      short loc_18009410D
0x1800940f8  mov     rcx, [rcx+10h]
0x1800940fc  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180094103  mov     edx, 15h
0x180094108  call    WPP_SF_
0x18009410d  mov     eax, 3AFh
0x180094112  mov     [rbp+4Fh+var_80], 1
0x180094119  mov     [rbp+4Fh+var_7C], ax
0x18009411d  mov     rcx, r13; pv
0x180094120  call    cs:__imp_CoTaskMemFree
0x180094126  mov     rcx, rbx; pv
0x180094129  call    cs:__imp_CoTaskMemFree
0x18009412f  mov     ebx, [rbp+4Fh+var_80]
0x180094132  lea     rcx, [rbp+4Fh+var_80]; this
0x180094136  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009413b  mov     eax, ebx
0x18009413d  add     rsp, 88h
0x180094144  pop     r15
0x180094146  pop     r14
0x180094148  pop     r13
  ... truncated ...
```
