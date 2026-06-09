# CCMonthCal::_CreateMonthCal(HWND__ *)

- ea: `0x180011e38`
- end: `0x180011fea`
- name: `?_CreateMonthCal@CCMonthCal@@AEAAPEAUHWND__@@PEAU2@@Z`
- size: `434`
- prototype: `HWND __fastcall(CCMonthCal *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010b80`

## callees

- `0x180011e38`
- `0x18001263c`
- `0x180017c1c`
- `0x180017c50`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011efb`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011efb`
- `USER32!DestroyWindow` at `0x180011fb5`
- `USER32!DestroyWindow` at `0x180011fb5`
- `USER32!SendMessageW` at `0x180011ef1`
- `USER32!SendMessageW` at `0x180011f14`
- `USER32!SendMessageW` at `0x180011f8a`
- `USER32!SendMessageW` at `0x180011fa3`
- `USER32!SendMessageW` at `0x180011ef1`
- `USER32!SendMessageW` at `0x180011f14`
- `USER32!SendMessageW` at `0x180011f8a`
- `USER32!SendMessageW` at `0x180011fa3`

## pseudocode

```c
HWND __fastcall CCMonthCal::_CreateMonthCal(CCMonthCal *this, HWND a2, __int64 a3)
{
  HWND Window; // rax
  int DateLimits; // eax
  HWND v6; // rcx
  int v7; // eax
  WPARAM v8; // r8
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp+17h] BYREF
  struct _SYSTEMTIME lParam[2]; // [rsp+70h] [rbp+27h] BYREF

  *((_DWORD *)this + 83) = 0;
  Window = IsolationAwareCreateWindowExW((__int64)this, L"SysMonthCal32", a3, 0x50000090u, 0, 0, 0, 0, a2);
  *((_QWORD *)this + 40) = Window;
  if ( Window )
  {
    memset(lParam, 0, sizeof(lParam));
    DateLimits = GetDateLimits(0, lParam, &lParam[1]);
    v6 = (HWND)*((_QWORD *)this + 40);
    if ( !DateLimits )
    {
      DestroyWindow(v6);
      *((_QWORD *)this + 40) = 0;
      return (HWND)*((_QWORD *)this + 40);
    }
    SystemTime = 0;
    SendMessageW(v6, 0x1012u, 3u, (LPARAM)lParam);
    GetLocalTime(&SystemTime);
    SendMessageW(*((HWND *)this + 40), 0x100Cu, 0, (LPARAM)&SystemTime);
    v7 = CompareSystemTimeDates(&SystemTime, &lParam[1]);
    v8 = 1;
    if ( v7 <= 0 )
    {
      if ( (int)CompareSystemTimeDates(&SystemTime, lParam) >= 0 )
      {
LABEL_8:
        SendMessageW(*((HWND *)this + 40), 0x101Eu, v8, 0);
        SendMessageW(*((HWND *)this + 40), 0x1002u, 0, (LPARAM)&SystemTime);
        g_fUserSelected = 0;
        return (HWND)*((_QWORD *)this + 40);
      }
      SystemTime = lParam[0];
    }
    else
    {
      SystemTime = lParam[1];
    }
    *((_DWORD *)this + 82) = v8;
    goto LABEL_8;
  }
  return (HWND)*((_QWORD *)this + 40);
}

```

## disassembly

```asm
0x180011e38  mov     [rsp-8+arg_10], rbx
0x180011e3d  push    rbp
0x180011e3e  lea     rbp, [rsp-57h]
0x180011e43  sub     rsp, 0A0h
0x180011e4a  mov     rax, cs:__security_cookie
0x180011e51  xor     rax, rsp
0x180011e54  mov     [rbp+57h+var_10], rax
0x180011e58  mov     [rsp+0A0h+var_60], rdx
0x180011e5d  mov     r9d, 50000090h
0x180011e63  mov     [rsp+0A0h+var_68], 0
0x180011e6b  lea     rdx, aSysmonthcal32; "SysMonthCal32"
0x180011e72  mov     [rsp+0A0h+var_70], 0
0x180011e7a  mov     rbx, rcx
0x180011e7d  mov     [rsp+0A0h+var_78], 0
0x180011e85  mov     [rsp+0A0h+var_80], 0
0x180011e8d  mov     dword ptr [rcx+14Ch], 0
0x180011e97  call    IsolationAwareCreateWindowExW
0x180011e9c  mov     [rbx+140h], rax
0x180011ea3  test    rax, rax
0x180011ea6  jz      loc_180011FC6
0x180011eac  xorps   xmm0, xmm0
0x180011eaf  lea     r8, [rbp+57h+var_20]; struct _SYSTEMTIME *
0x180011eb3  xor     eax, eax
0x180011eb5  lea     rdx, [rbp+57h+lParam]; struct _SYSTEMTIME *
0x180011eb9  movups  xmmword ptr [rbp+29h], xmm0
0x180011ebd  xor     ecx, ecx; unsigned int
0x180011ebf  mov     word ptr [rbp+57h+lParam], ax
0x180011ec3  movups  xmmword ptr [rbp+57h+var_20.wYear], xmm0
0x180011ec7  call    ?GetDateLimits@@YAHIPEAU_SYSTEMTIME@@0@Z; GetDateLimits(uint,_SYSTEMTIME *,_SYSTEMTIME *)
0x180011ecc  mov     rcx, [rbx+140h]; hWnd
0x180011ed3  test    eax, eax
0x180011ed5  jz      loc_180011FB5
0x180011edb  xorps   xmm0, xmm0
0x180011ede  lea     r9, [rbp+57h+lParam]; lParam
0x180011ee2  mov     edx, 1012h; Msg
0x180011ee7  mov     r8d, 3; wParam
0x180011eed  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180011ef1  call    cs:__imp_SendMessageW
0x180011ef7  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180011efb  call    cs:__imp_GetLocalTime
0x180011f01  mov     rcx, [rbx+140h]; hWnd
0x180011f08  lea     r9, [rbp+57h+SystemTime]; lParam
0x180011f0c  xor     r8d, r8d; wParam
0x180011f0f  mov     edx, 100Ch; Msg
0x180011f14  call    cs:__imp_SendMessageW
0x180011f1a  lea     rdx, [rbp+57h+var_20]; struct _SYSTEMTIME *
0x180011f1e  lea     rcx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180011f22  call    ?CompareSystemTimeDates@@YAHPEBU_SYSTEMTIME@@0@Z; CompareSystemTimeDates(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x180011f27  mov     r8d, 1
0x180011f2d  test    eax, eax
0x180011f2f  jle     short loc_180011F43
0x180011f31  mov     rax, qword ptr [rbp+57h+var_20.wYear]
0x180011f35  mov     qword ptr [rbp+57h+SystemTime.wYear], rax
0x180011f39  mov     rax, qword ptr [rbp+57h+var_20.wHour]
0x180011f3d  mov     qword ptr [rbp+57h+SystemTime.wHour], rax
0x180011f41  jmp     short loc_180011F74
0x180011f43  lea     rdx, [rbp+57h+lParam]; struct _SYSTEMTIME *
0x180011f47  lea     rcx, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x180011f4b  call    ?CompareSystemTimeDates@@YAHPEBU_SYSTEMTIME@@0@Z; CompareSystemTimeDates(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x180011f50  test    eax, eax
0x180011f52  jns     short loc_180011F7B
0x180011f54  movzx   eax, word ptr [rbp+57h+lParam]
0x180011f58  movsd   xmm0, [rbp+57h+lParam+2]
0x180011f5d  mov     [rbp+57h+SystemTime.wYear], ax
0x180011f61  mov     eax, [rbp+57h+var_26]
0x180011f64  mov     dword ptr [rbp+57h+SystemTime.wMinute], eax
0x180011f67  movzx   eax, [rbp+57h+var_22]
0x180011f6b  mov     [rbp+57h+SystemTime.wMilliseconds], ax
0x180011f6f  movsd   qword ptr [rbp+57h+SystemTime.wMonth], xmm0
0x180011f74  mov     [rbx+148h], r8d
0x180011f7b  mov     rcx, [rbx+140h]; hWnd
0x180011f82  xor     r9d, r9d; lParam
0x180011f85  mov     edx, 101Eh; Msg
0x180011f8a  call    cs:__imp_SendMessageW
0x180011f90  mov     rcx, [rbx+140h]; hWnd
0x180011f97  lea     r9, [rbp+57h+SystemTime]; lParam
0x180011f9b  xor     r8d, r8d; wParam
0x180011f9e  mov     edx, 1002h; Msg
0x180011fa3  call    cs:__imp_SendMessageW
0x180011fa9  mov     cs:?g_fUserSelected@@3HA, 0; int g_fUserSelected
0x180011fb3  jmp     short loc_180011FC6
0x180011fb5  call    cs:__imp_DestroyWindow
0x180011fbb  mov     qword ptr [rbx+140h], 0
0x180011fc6  mov     rax, [rbx+140h]
0x180011fcd  mov     rcx, [rbp+57h+var_10]
0x180011fd1  xor     rcx, rsp; StackCookie
0x180011fd4  call    __security_check_cookie
0x180011fd9  mov     rbx, [rsp+0A0h+arg_10]
0x180011fe1  add     rsp, 0A0h
0x180011fe8  pop     rbp
0x180011fe9  retn
```
