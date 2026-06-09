# SxQueryDeviceStrings(void *,CBsString *,CBsString *,CBsString *,CBsString *)

- ea: `0x180097f10`
- end: `0x180098428`
- name: `?SxQueryDeviceStrings@@YAJPEAXPEAVCBsString@@111@Z`
- size: `1304`
- prototype: `__int64 __fastcall(HANDLE hDevice, struct CBsString *this, struct CBsString *, struct CBsString *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18001061c`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x1800083e4`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180097d60`
- `0x180097f10`
- `0x18009e234`
- `0x1800cf56a`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180098093`
- `KERNEL32!DeviceIoControl` at `0x180098093`
- `ole32!CoTaskMemFree` at `0x1800983ea`
- `ole32!CoTaskMemFree` at `0x1800983f9`
- `ole32!CoTaskMemFree` at `0x1800983ea`
- `ole32!CoTaskMemFree` at `0x1800983f9`
- `ole32!CoTaskMemAlloc` at `0x180097ff0`
- `ole32!CoTaskMemAlloc` at `0x18009802d`
- `ole32!CoTaskMemAlloc` at `0x180097ff0`
- `ole32!CoTaskMemAlloc` at `0x18009802d`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "SxQueryDeviceStrings", 0x36Au, 1u);
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
0x180097f10  push    rbp
0x180097f12  push    rbx
0x180097f13  push    rsi
0x180097f14  push    rdi
0x180097f15  push    r12
0x180097f17  push    r13
0x180097f19  push    r14
0x180097f1b  push    r15
0x180097f1d  lea     rbp, [rsp-17h]
0x180097f22  sub     rsp, 88h
0x180097f29  mov     r15, r9
0x180097f2c  mov     r14, r8
0x180097f2f  mov     r12, rdx
0x180097f32  mov     rdi, rcx
0x180097f35  mov     r9d, 1; unsigned __int16
0x180097f3b  lea     rdx, aSxquerydevices; "SxQueryDeviceStrings"
0x180097f42  mov     r8d, 36Ah; unsigned __int16
0x180097f48  lea     rcx, [rbp+4Fh+var_80]; this
0x180097f4c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180097f51  xor     ebx, ebx
0x180097f53  xor     r13d, r13d
0x180097f56  mov     [rbp+4Fh+BytesReturned], ebx
0x180097f59  test    r12, r12
0x180097f5c  jz      short loc_180097F66
0x180097f5e  mov     rcx, r12; this
0x180097f61  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180097f66  test    r14, r14
0x180097f69  jz      short loc_180097F73
0x180097f6b  mov     rcx, r14; this
0x180097f6e  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180097f73  test    r15, r15
0x180097f76  jz      short loc_180097F80
0x180097f78  mov     rcx, r15; this
0x180097f7b  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180097f80  mov     rsi, [rbp+4Fh+arg_20]
0x180097f84  test    rsi, rsi
0x180097f87  jz      short loc_180097F91
0x180097f89  mov     rcx, rsi; this
0x180097f8c  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180097f91  mov     eax, 37Bh
0x180097f96  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180097f9a  jnz     short loc_180097FAC
0x180097f9c  mov     [rbp+4Fh+var_80], 80070057h
0x180097fa3  mov     [rbp+4Fh+var_7A], ax
0x180097fa7  jmp     loc_1800983E7
0x180097fac  mov     [rbp+4Fh+var_7C], ax
0x180097fb0  mov     eax, 37Dh
0x180097fb5  test    r12, r12
0x180097fb8  jz      short loc_180097F9C
0x180097fba  mov     [rbp+4Fh+var_7C], ax
0x180097fbe  mov     eax, 37Eh
0x180097fc3  test    r14, r14
0x180097fc6  jz      short loc_180097F9C
0x180097fc8  mov     [rbp+4Fh+var_7C], ax
0x180097fcc  mov     eax, 37Fh
0x180097fd1  test    r15, r15
0x180097fd4  jz      short loc_180097F9C
0x180097fd6  mov     [rbp+4Fh+var_7C], ax
0x180097fda  mov     eax, 380h
0x180097fdf  test    rsi, rsi
0x180097fe2  jz      short loc_180097F9C
0x180097fe4  mov     ecx, 4000h; cb
0x180097fe9  mov     [rbp+4Fh+var_80], ebx
0x180097fec  mov     [rbp+4Fh+var_7C], ax
0x180097ff0  call    cs:__imp_CoTaskMemAlloc
0x180097ff7  nop     dword ptr [rax+rax+00h]
0x180097ffc  mov     r13, rax
0x180097fff  test    rax, rax
0x180098002  mov     eax, 383h
0x180098007  jnz     short loc_180098012
0x180098009  mov     [rbp+4Fh+var_80], 8007000Eh
0x180098010  jmp     short loc_180097FA3
0x180098012  mov     [rbp+4Fh+var_80], ebx
0x180098015  xor     edx, edx; Val
0x180098017  mov     ebx, 4000h
0x18009801c  mov     [rbp+4Fh+var_7C], ax
0x180098020  mov     r8d, ebx; Size
0x180098023  mov     rcx, r13; void *
0x180098026  call    memset_0
0x18009802b  mov     ecx, ebx; cb
0x18009802d  call    cs:__imp_CoTaskMemAlloc
0x180098034  nop     dword ptr [rax+rax+00h]
0x180098039  mov     rbx, rax
0x18009803c  test    rax, rax
0x18009803f  mov     eax, 387h
0x180098044  jz      short loc_180098009
0x180098046  xor     edx, edx; Val
0x180098048  mov     [rbp+4Fh+var_80], 0
0x18009804f  mov     r8d, 4000h; Size
0x180098055  mov     [rbp+4Fh+var_7C], ax
0x180098059  mov     rcx, rbx; void *
0x18009805c  call    memset_0
0x180098061  xor     eax, eax
0x180098063  mov     r9d, 4000h; nInBufferSize
0x180098069  mov     [rsp+0C0h+lpOverlapped], rax; lpOverlapped
0x18009806e  mov     r8, r13; lpInBuffer
0x180098071  mov     [r13+0], rax
0x180098075  mov     edx, 2D1400h; dwIoControlCode
0x18009807a  lea     rax, [rbp+4Fh+BytesReturned]
0x18009807e  mov     rcx, rdi; hDevice
0x180098081  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x180098086  mov     [rsp+0C0h+nOutBufferSize], 4000h; nOutBufferSize
0x18009808e  mov     [rsp+0C0h+lpOutBuffer], rbx; lpOutBuffer
0x180098093  call    cs:__imp_DeviceIoControl
0x18009809a  nop     dword ptr [rax+rax+00h]
0x18009809f  test    eax, eax
0x1800980a1  jnz     short loc_1800980CD
0x1800980a3  call    GetLastFailureAsHRESULT
0x1800980a8  cmp     eax, 80070001h
0x1800980ad  jnz     short loc_1800980B9
0x1800980af  mov     eax, 39Eh
0x1800980b4  jmp     loc_1800983DC
0x1800980b9  mov     [rbp+4Fh+var_80], eax
0x1800980bc  test    eax, eax
0x1800980be  mov     eax, 3A1h
0x1800980c3  js      loc_180097FA3
0x1800980c9  mov     [rbp+4Fh+var_7C], ax
0x1800980cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980d4  lea     rdi, WPP_GLOBAL_Control
0x1800980db  cmp     rcx, rdi
0x1800980de  jz      short loc_180098109
0x1800980e0  test    dword ptr [rcx+1Ch], 1000000h
0x1800980e7  jz      short loc_180098109
0x1800980e9  mov     r9d, [rbp+4Fh+BytesReturned]
0x1800980ed  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x1800980f4  mov     rcx, [rcx+10h]
0x1800980f8  mov     edx, 14h
0x1800980fd  call    WPP_SF_d
0x180098102  mov     rcx, cs:WPP_GLOBAL_Control
0x180098109  cmp     [rbp+4Fh+BytesReturned], 28h ; '('
0x18009810d  jb      loc_1800983B4
0x180098113  cmp     dword ptr [rbx+4], 28h ; '('
0x180098117  jb      loc_1800983B4
0x18009811d  cmp     rcx, rdi
0x180098120  jz      loc_18009823D
0x180098126  test    dword ptr [rcx+1Ch], 1000000h
0x18009812d  jz      short loc_18009814E
0x18009812f  mov     r9d, [rbx]
0x180098132  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180098139  mov     rcx, [rcx+10h]
0x18009813d  mov     edx, 16h
0x180098142  call    WPP_SF_d
0x180098147  mov     rcx, cs:WPP_GLOBAL_Control
0x18009814e  cmp     rcx, rdi
0x180098151  jz      loc_18009823D
0x180098157  test    dword ptr [rcx+1Ch], 1000000h
0x18009815e  jz      short loc_180098180
0x180098160  mov     r9d, [rbx+4]
0x180098164  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18009816b  mov     rcx, [rcx+10h]
0x18009816f  mov     edx, 17h
0x180098174  call    WPP_SF_d
0x180098179  mov     rcx, cs:WPP_GLOBAL_Control
0x180098180  cmp     rcx, rdi
0x180098183  jz      loc_18009823D
0x180098189  test    dword ptr [rcx+1Ch], 1000000h
0x180098190  jz      short loc_1800981B3
0x180098192  movzx   r9d, byte ptr [rbx+8]
0x180098197  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18009819e  mov     rcx, [rcx+10h]
0x1800981a2  mov     edx, 18h
0x1800981a7  call    WPP_SF_d
0x1800981ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800981b3  cmp     rcx, rdi
0x1800981b6  jz      loc_18009823D
0x1800981bc  test    dword ptr [rcx+1Ch], 1000000h
0x1800981c3  jz      short loc_1800981E6
0x1800981c5  movzx   r9d, byte ptr [rbx+9]
0x1800981ca  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x1800981d1  mov     rcx, [rcx+10h]
0x1800981d5  mov     edx, 19h
0x1800981da  call    WPP_SF_d
0x1800981df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800981e6  cmp     rcx, rdi
0x1800981e9  jz      short loc_18009823D
0x1800981eb  test    dword ptr [rcx+1Ch], 1000000h
0x1800981f2  jz      short loc_180098215
0x1800981f4  movzx   r9d, byte ptr [rbx+0Ah]
0x1800981f9  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180098200  mov     rcx, [rcx+10h]
0x180098204  mov     edx, 1Ah
0x180098209  call    WPP_SF_d
0x18009820e  mov     rcx, cs:WPP_GLOBAL_Control
0x180098215  cmp     rcx, rdi
0x180098218  jz      short loc_18009823D
0x18009821a  test    dword ptr [rcx+1Ch], 1000000h
0x180098221  jz      short loc_18009823D
0x180098223  movzx   r9d, byte ptr [rbx+0Bh]
0x180098228  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18009822f  mov     rcx, [rcx+10h]
0x180098233  mov     edx, 1Bh
0x180098238  call    WPP_SF_d
0x18009823d  mov     eax, [rbx+4]
0x180098240  mov     rdx, rbx
0x180098243  cmp     [rbp+4Fh+BytesReturned], eax
0x180098246  mov     rcx, r12; this
0x180098249  mov     r8d, [rbx+0Ch]
0x18009824d  cmovb   eax, [rbp+4Fh+BytesReturned]
0x180098251  lea     edi, [rax-1]
0x180098254  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x180098258  call    CopyDeviceString
0x18009825d  mov     [rbp+4Fh+var_80], eax
0x180098260  test    eax, eax
0x180098262  mov     eax, 3C4h
0x180098267  js      loc_180097FA3
0x18009826d  mov     [rbp+4Fh+var_7C], ax
0x180098271  mov     rdx, rbx
0x180098274  mov     r8d, [rbx+10h]
0x180098278  mov     rcx, r14; this
0x18009827b  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x18009827f  call    CopyDeviceString
0x180098284  mov     [rbp+4Fh+var_80], eax
0x180098287  test    eax, eax
0x180098289  mov     eax, 3C5h
0x18009828e  js      loc_180097FA3
0x180098294  mov     [rbp+4Fh+var_7C], ax
0x180098298  mov     rdx, rbx
0x18009829b  mov     r8d, [rbx+14h]
0x18009829f  mov     rcx, r15; this
0x1800982a2  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x1800982a6  call    CopyDeviceString
0x1800982ab  mov     [rbp+4Fh+var_80], eax
0x1800982ae  test    eax, eax
0x1800982b0  mov     eax, 3C6h
0x1800982b5  js      loc_180097FA3
0x1800982bb  mov     [rbp+4Fh+var_7C], ax
0x1800982bf  mov     rdx, rbx
0x1800982c2  mov     r8d, [rbx+18h]
0x1800982c6  mov     rcx, rsi; this
0x1800982c9  mov     dword ptr [rsp+0C0h+lpOutBuffer], edi; int
0x1800982cd  call    CopyDeviceString
0x1800982d2  mov     [rbp+4Fh+var_80], eax
0x1800982d5  test    eax, eax
0x1800982d7  mov     eax, 3C7h
0x1800982dc  js      loc_180097FA3
0x1800982e2  mov     [rbp+4Fh+var_7C], ax
0x1800982e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800982ed  lea     rdi, WPP_GLOBAL_Control
0x1800982f4  cmp     rcx, rdi
0x1800982f7  jz      loc_1800983A6
0x1800982fd  test    dword ptr [rcx+1Ch], 1000000h
0x180098304  jz      short loc_180098326
0x180098306  mov     r9, [r12]
0x18009830a  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180098311  mov     rcx, [rcx+10h]
0x180098315  mov     edx, 1Ch
0x18009831a  call    WPP_SF_S
0x18009831f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098326  cmp     rcx, rdi
0x180098329  jz      short loc_1800983A6
0x18009832b  test    dword ptr [rcx+1Ch], 1000000h
0x180098332  jz      short loc_180098353
0x180098334  mov     r9, [r14]
0x180098337  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18009833e  mov     rcx, [rcx+10h]
0x180098342  mov     edx, 1Dh
0x180098347  call    WPP_SF_S
0x18009834c  mov     rcx, cs:WPP_GLOBAL_Control
0x180098353  cmp     rcx, rdi
0x180098356  jz      short loc_1800983A6
0x180098358  test    dword ptr [rcx+1Ch], 1000000h
0x18009835f  jz      short loc_180098380
0x180098361  mov     r9, [r15]
0x180098364  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x18009836b  mov     rcx, [rcx+10h]
0x18009836f  mov     edx, 1Eh
0x180098374  call    WPP_SF_S
0x180098379  mov     rcx, cs:WPP_GLOBAL_Control
0x180098380  cmp     rcx, rdi
0x180098383  jz      short loc_1800983A6
0x180098385  test    dword ptr [rcx+1Ch], 1000000h
0x18009838c  jz      short loc_1800983A6
0x18009838e  mov     r9, [rsi]
0x180098391  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x180098398  mov     rcx, [rcx+10h]
0x18009839c  mov     edx, 1Fh
0x1800983a1  call    WPP_SF_S
0x1800983a6  mov     [rbp+4Fh+var_80], 0
0x1800983ad  mov     eax, 3CEh
0x1800983b2  jmp     short loc_1800983E3
0x1800983b4  cmp     rcx, rdi
0x1800983b7  jz      short loc_1800983D7
0x1800983b9  test    dword ptr [rcx+1Ch], 10000000h
0x1800983c0  jz      short loc_1800983D7
0x1800983c2  mov     rcx, [rcx+10h]
0x1800983c6  lea     r8, WPP_24b4ab97cee234c31b904b9e143af9a8_Traceguids
0x1800983cd  mov     edx, 15h
0x1800983d2  call    WPP_SF_
0x1800983d7  mov     eax, 3AFh
0x1800983dc  mov     [rbp+4Fh+var_80], 1
0x1800983e3  mov     [rbp+4Fh+var_7C], ax
0x1800983e7  mov     rcx, r13; pv
0x1800983ea  call    cs:__imp_CoTaskMemFree
0x1800983f1  nop     dword ptr [rax+rax+00h]
0x1800983f6  mov     rcx, rbx; pv
0x1800983f9  call    cs:__imp_CoTaskMemFree
0x180098400  nop     dword ptr [rax+rax+00h]
0x180098405  mov     ebx, [rbp+4Fh+var_80]
0x180098408  lea     rcx, [rbp+4Fh+var_80]; this
0x18009840c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
  ... truncated ...
```
