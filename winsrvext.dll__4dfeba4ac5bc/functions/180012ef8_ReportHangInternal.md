# ReportHangInternal

- ea: `0x180012ef8`
- end: `0x180013282`
- name: `ReportHangInternal`
- size: `906`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a914`

## callees

- `0x180001a34`
- `0x180001a40`
- `0x180001a4c`
- `0x180001ae3`
- `0x180001aef`
- `0x180001f8c`
- `0x180001fe0`
- `0x180002034`
- `0x180002088`
- `0x180012ef8`
- `0x180013288`
- `0x1800133e4`
- `0x180013806`
- `0x1800138ad`
- `0x1800138c5`
- `0x1800138f0`
- `0x180014010`

## import_xrefs

- `ntdll!PssNtFreeSnapshot` at `0x1800130ce`
- `ntdll!PssNtFreeSnapshot` at `0x1800130ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800131a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800131a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013221`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013221`
- `USER32!RegisterWindowMessageW` at `0x1800131d4`
- `USER32!RegisterWindowMessageW` at `0x1800131d4`
- `USER32!GetThreadDesktop` at `0x180013031`
- `USER32!GetThreadDesktop` at `0x180013031`
- `USER32!ChangeWindowMessageFilterEx` at `0x1800131f0`
- `USER32!ChangeWindowMessageFilterEx` at `0x1800131f0`
- `USER32!GetWindowThreadProcessId` at `0x180012f93`
- `USER32!GetWindowThreadProcessId` at `0x180012f93`
- `USER32!GetUserObjectInformationW` at `0x180013061`
- `USER32!GetUserObjectInformationW` at `0x180013061`

## string_xrefs

- `0x180013196`: `user32.dll`

## pseudocode

```c
__int64 __fastcall ReportHangInternal(HWND a1)
{
  int v2; // ebx
  DWORD WindowThreadProcessId; // ebx
  int v4; // r9d
  DWORD CurrentThreadId_0; // eax
  HDESK ThreadDesktop; // rax
  const wchar_t *v7; // rcx
  unsigned int v8; // r9d
  __int64 i; // rdi
  __int64 v10; // rax
  HWND v11; // rbx
  DWORD v12; // esi
  HMODULE Library; // rdi
  DWORD v14; // ecx
  UINT v15; // eax
  FARPROC RegisterErrorReportingDialog; // rax
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  DWORD nLengthNeeded; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h]
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v22; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v23[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v24; // [rsp+5F8h] [rbp+4F8h]
  int v25; // [rsp+5FCh] [rbp+4FCh]
  HWND hwnd; // [rsp+600h] [rbp+500h]
  HANDLE hObject; // [rsp+B38h] [rbp+A38h]
  HANDLE v28; // [rsp+B40h] [rbp+A40h]
  _DWORD v29[12]; // [rsp+B50h] [rbp+A50h] BYREF
  _DWORD v30[18]; // [rsp+B80h] [rbp+A80h] BYREF
  _QWORD v31[16]; // [rsp+BC8h] [rbp+AC8h] BYREF
  char v32; // [rsp+C48h] [rbp+B48h] BYREF
  char v33; // [rsp+C58h] [rbp+B58h] BYREF
  HWND v34; // [rsp+C98h] [rbp+B98h]
  _WORD pvInfo[520]; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v36; // [rsp+10B0h] [rbp+FB0h]
  DWORD TickCount_0; // [rsp+10B4h] [rbp+FB4h]

  dwProcessId = 0;
  LOWORD(v29[0]) = 0;
  memset_0((char *)v29 + 2, 0, 0x576u);
  v22 = 0;
  memset_0(v23, 0, 0x576u);
  v20 = 0;
  if ( !a1 )
    goto LABEL_41;
  if ( !(unsigned __int8)IsGetWindowThreadProcessIdPresent() )
  {
    v2 = -1073741637;
    goto LABEL_42;
  }
  WindowThreadProcessId = GetWindowThreadProcessId(a1, &dwProcessId);
  if ( WindowThreadProcessId )
  {
    memset_0(Src, 0, 0x578u);
    memcpy_0(v29, Src, 0x578u);
    v29[0] = 91751760;
    v29[10] = 0x10000000;
    v30[16] = WindowThreadProcessId;
    v34 = a1;
    TickCount_0 = GetTickCount_0();
    v30[0] = dwProcessId;
    pvInfo[0] = 0;
    nLengthNeeded = 0;
    if ( !(unsigned __int8)IsGetThreadDesktopPresent()
      || !(unsigned __int8)IsGetThreadDesktopPresent()
      || (CurrentThreadId_0 = GetCurrentThreadId_0(), (ThreadDesktop = GetThreadDesktop(CurrentThreadId_0)) == 0)
      || !GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, &nLengthNeeded) )
    {
      pvInfo[0] = 0;
    }
    v36 = 0x2000;
    RhpCaptureSnapshots((unsigned int)v31, (unsigned int)&v32, (unsigned int)&v33, v4, (__int64)v30);
    v2 = WersvcSendMessage(v7, (struct _WERSVC_MSG *)v29, (struct _WERSVC_MSG *)&v22, v8);
    for ( i = 0; i != 16; ++i )
    {
      if ( v31[i] )
        PssNtFreeSnapshot();
    }
    if ( v2 >= 0 )
    {
      if ( v2 == 258 )
      {
        v2 = -1073741248;
        goto LABEL_42;
      }
      if ( v24 != 268435457 )
      {
        if ( v24 == 268435458 )
        {
          v2 = v25;
          if ( v25 < 0 )
            goto LABEL_42;
        }
        else if ( v24 == 268435461 )
        {
          goto LABEL_20;
        }
        v2 = -1073741823;
        goto LABEL_42;
      }
LABEL_20:
      v10 = 0;
      if ( hObject )
      {
        *(_QWORD *)&v20 = hObject;
        v10 = 1;
      }
      if ( v28 )
        *(_QWORD *)&Src[8 * v10 - 8] = v28;
      v11 = hwnd;
      if ( !hwnd )
        goto LABEL_40;
      if ( v24 != 268435461 )
        goto LABEL_40;
      v12 = dwProcessId;
      if ( !dwProcessId )
        goto LABEL_40;
      if ( (unsigned __int8)IsRegisterWindowMessageWPresent() && (unsigned __int8)IsChangeWindowMessageFilterExPresent() )
      {
        Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
        if ( Library )
        {
          v15 = RegisterWindowMessageW(L"WerHangRepMessage");
          if ( v15 )
          {
            if ( ChangeWindowMessageFilterEx(v11, v15, 1u, 0) )
            {
              RegisterErrorReportingDialog = GetProcAddress_0(Library, "RegisterErrorReportingDialog");
              if ( RegisterErrorReportingDialog )
                ((void (__fastcall *)(HWND, _QWORD))RegisterErrorReportingDialog)(v11, v12);
            }
          }
          FreeLibrary(Library);
          goto LABEL_40;
        }
        v14 = 126;
      }
      else
      {
        v14 = 127;
      }
      SetLastError_0(v14);
LABEL_40:
      v2 = 0;
    }
  }
  else
  {
LABEL_41:
    v2 = -1073741811;
  }
LABEL_42:
  if ( hObject )
    CloseHandle_0(hObject);
  if ( v28 )
    CloseHandle_0(v28);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012ef8  push    rbp
0x180012efa  push    rbx
0x180012efb  push    rsi
0x180012efc  push    rdi
0x180012efd  lea     rbp, [rsp-0FE8h]
0x180012f05  mov     eax, 10E8h
0x180012f0a  call    __chkstk_0
0x180012f0f  sub     rsp, rax
0x180012f12  mov     rax, cs:__security_cookie
0x180012f19  xor     rax, rsp
0x180012f1c  mov     [rbp+1000h+var_30], rax
0x180012f23  mov     rdi, rcx
0x180012f26  mov     [rsp+1100h+dwProcessId], 0
0x180012f2e  xor     eax, eax
0x180012f30  lea     rcx, [rbp+1000h+var_5B0+2]; void *
0x180012f37  mov     ebx, 576h
0x180012f3c  mov     word ptr [rbp+1000h+var_5B0], ax
0x180012f43  mov     r8d, ebx; Size
0x180012f46  xor     edx, edx; Val
0x180012f48  call    memset_0
0x180012f4d  xor     eax, eax
0x180012f4f  lea     rcx, [rbp+1000h+var_B2E]; void *
0x180012f56  mov     r8d, ebx; Size
0x180012f59  mov     [rbp+1000h+var_B30], ax
0x180012f60  xor     edx, edx; Val
0x180012f62  call    memset_0
0x180012f67  xorps   xmm0, xmm0
0x180012f6a  movups  [rsp+1100h+var_10C8], xmm0
0x180012f6f  test    rdi, rdi
0x180012f72  jz      loc_18001323D
0x180012f78  call    IsGetWindowThreadProcessIdPresent
0x180012f7d  test    al, al
0x180012f7f  jnz     short loc_180012F8B
0x180012f81  mov     ebx, 0C00000BBh
0x180012f86  jmp     loc_180013242
0x180012f8b  lea     rdx, [rsp+1100h+dwProcessId]; lpdwProcessId
0x180012f90  mov     rcx, rdi; hWnd
0x180012f93  call    cs:__imp_GetWindowThreadProcessId
0x180012f9a  nop     dword ptr [rax+rax+00h]
0x180012f9f  mov     ebx, eax
0x180012fa1  test    eax, eax
0x180012fa3  jz      loc_18001323D
0x180012fa9  mov     esi, 578h
0x180012fae  lea     rcx, [rsp+1100h+Src]; void *
0x180012fb3  mov     r8d, esi; Size
0x180012fb6  xor     edx, edx; Val
0x180012fb8  call    memset_0
0x180012fbd  lea     rcx, [rbp+1000h+var_5B0]; void *
0x180012fc4  mov     r8d, esi; Size
0x180012fc7  lea     rdx, [rsp+1100h+Src]; Src
0x180012fcc  call    memcpy_0
0x180012fd1  mov     [rbp+1000h+var_5B0], 5780550h
0x180012fdb  mov     [rbp+1000h+var_588], 10000000h
0x180012fe5  mov     [rbp+1000h+var_540], ebx
0x180012feb  mov     [rbp+1000h+var_468], rdi
0x180012ff2  call    GetTickCount_0
0x180012ff7  mov     [rbp+1000h+var_4C], eax
0x180012ffd  mov     eax, [rsp+1100h+dwProcessId]
0x180013001  mov     [rbp+1000h+var_580], eax
0x180013007  xor     eax, eax
0x180013009  mov     [rbp+1000h+pvInfo], ax
0x180013010  mov     [rsp+1100h+nLengthNeeded], 0
0x180013018  call    IsGetThreadDesktopPresent
0x18001301d  test    al, al
0x18001301f  jz      short loc_180013071
0x180013021  call    IsGetThreadDesktopPresent
0x180013026  test    al, al
0x180013028  jz      short loc_180013071
0x18001302a  call    GetCurrentThreadId_0
0x18001302f  mov     ecx, eax; dwThreadId
0x180013031  call    cs:__imp_GetThreadDesktop
0x180013038  nop     dword ptr [rax+rax+00h]
0x18001303d  test    rax, rax
0x180013040  jz      short loc_180013071
0x180013042  lea     rcx, [rsp+1100h+nLengthNeeded]
0x180013047  mov     r9d, 208h; nLength
0x18001304d  mov     [rsp+1100h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180013052  lea     r8, [rbp+1000h+pvInfo]; pvInfo
0x180013059  mov     rcx, rax; hObj
0x18001305c  mov     edx, 2; nIndex
0x180013061  call    cs:__imp_GetUserObjectInformationW
0x180013068  nop     dword ptr [rax+rax+00h]
0x18001306d  test    eax, eax
0x18001306f  jnz     short loc_18001307A
0x180013071  xor     eax, eax
0x180013073  mov     [rbp+1000h+pvInfo], ax
0x18001307a  lea     rax, [rbp+1000h+var_580]
0x180013081  mov     [rbp+1000h+var_50], 2000h
0x18001308b  lea     r8, [rbp+1000h+var_4A8]
0x180013092  mov     [rsp+1100h+lpnLengthNeeded], rax
0x180013097  lea     rdx, [rbp+1000h+var_4B8]
0x18001309e  lea     rcx, [rbp+1000h+var_538]
0x1800130a5  call    RhpCaptureSnapshots
0x1800130aa  lea     r8, [rbp+1000h+var_B30]; struct _WERSVC_MSG *
0x1800130b1  lea     rdx, [rbp+1000h+var_5B0]; struct _WERSVC_MSG *
0x1800130b8  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x1800130bd  mov     ebx, eax
0x1800130bf  xor     edi, edi
0x1800130c1  mov     rcx, [rbp+rdi*8+1000h+var_538]
0x1800130c9  test    rcx, rcx
0x1800130cc  jz      short loc_1800130DA
0x1800130ce  call    cs:__imp_PssNtFreeSnapshot
0x1800130d5  nop     dword ptr [rax+rax+00h]
0x1800130da  inc     rdi
0x1800130dd  cmp     rdi, 10h
0x1800130e1  jnz     short loc_1800130C1
0x1800130e3  test    ebx, ebx
0x1800130e5  js      loc_180013242
0x1800130eb  cmp     ebx, 102h
0x1800130f1  jnz     short loc_1800130FD
0x1800130f3  mov     ebx, 0C0000240h
0x1800130f8  jmp     loc_180013242
0x1800130fd  mov     eax, [rbp+1000h+var_B08]
0x180013103  sub     eax, 10000001h
0x180013108  jz      short loc_18001311C
0x18001310a  sub     eax, 1
0x18001310d  jz      loc_1800131BC
0x180013113  cmp     eax, 3
0x180013116  jnz     loc_1800131C6
0x18001311c  mov     rcx, [rbp+1000h+hObject]
0x180013123  xor     eax, eax
0x180013125  test    rcx, rcx
0x180013128  jz      short loc_180013134
0x18001312a  mov     qword ptr [rsp+1100h+var_10C8], rcx
0x18001312f  mov     eax, 1
0x180013134  mov     rcx, [rbp+1000h+var_5C0]
0x18001313b  test    rcx, rcx
0x18001313e  jz      short loc_180013145
0x180013140  mov     qword ptr [rsp+rax*8+1100h+var_10C8], rcx
0x180013145  mov     rbx, [rbp+1000h+hwnd]
0x18001314c  test    rbx, rbx
0x18001314f  jz      loc_180013239
0x180013155  cmp     [rbp+1000h+var_B08], 10000005h
0x18001315f  jnz     loc_180013239
0x180013165  test    rbx, rbx
0x180013168  jz      loc_180013239
0x18001316e  mov     esi, [rsp+1100h+dwProcessId]
0x180013172  test    esi, esi
0x180013174  jz      loc_180013239
0x18001317a  call    IsRegisterWindowMessageWPresent
0x18001317f  test    al, al
0x180013181  jz      loc_18001322F
0x180013187  call    IsChangeWindowMessageFilterExPresent
0x18001318c  test    al, al
0x18001318e  jz      loc_18001322F
0x180013194  xor     edx, edx; hFile
0x180013196  lea     rcx, LibFileName; "user32.dll"
0x18001319d  mov     r8d, 800h; dwFlags
0x1800131a3  call    cs:__imp_LoadLibraryExW
0x1800131aa  nop     dword ptr [rax+rax+00h]
0x1800131af  mov     rdi, rax
0x1800131b2  test    rax, rax
0x1800131b5  jnz     short loc_1800131CD
0x1800131b7  lea     ecx, [rax+7Eh]
0x1800131ba  jmp     short loc_180013234
0x1800131bc  mov     ebx, [rbp+1000h+var_B04]
0x1800131c2  test    ebx, ebx
0x1800131c4  js      short loc_180013242
0x1800131c6  mov     ebx, 0C0000001h
0x1800131cb  jmp     short loc_180013242
0x1800131cd  lea     rcx, aWerhangrepmess; "WerHangRepMessage"
0x1800131d4  call    cs:__imp_RegisterWindowMessageW
0x1800131db  nop     dword ptr [rax+rax+00h]
0x1800131e0  test    eax, eax
0x1800131e2  jz      short loc_18001321E
0x1800131e4  xor     r9d, r9d; pChangeFilterStruct
0x1800131e7  mov     edx, eax; message
0x1800131e9  mov     rcx, rbx; hwnd
0x1800131ec  lea     r8d, [r9+1]; action
0x1800131f0  call    cs:__imp_ChangeWindowMessageFilterEx
0x1800131f7  nop     dword ptr [rax+rax+00h]
0x1800131fc  test    eax, eax
0x1800131fe  jz      short loc_18001321E
0x180013200  lea     rdx, aRegistererrorr; "RegisterErrorReportingDialog"
0x180013207  mov     rcx, rdi; hModule
0x18001320a  call    GetProcAddress_0
0x18001320f  test    rax, rax
0x180013212  jz      short loc_18001321E
0x180013214  mov     edx, esi
0x180013216  mov     rcx, rbx
0x180013219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001321e  mov     rcx, rdi; hLibModule
0x180013221  call    cs:__imp_FreeLibrary
0x180013228  nop     dword ptr [rax+rax+00h]
0x18001322d  jmp     short loc_180013239
0x18001322f  mov     ecx, 7Fh; dwErrCode
0x180013234  call    SetLastError_0
0x180013239  xor     ebx, ebx
0x18001323b  jmp     short loc_180013242
0x18001323d  mov     ebx, 0C000000Dh
0x180013242  mov     rcx, [rbp+1000h+hObject]; hObject
0x180013249  test    rcx, rcx
0x18001324c  jz      short loc_180013253
0x18001324e  call    CloseHandle_0
0x180013253  mov     rcx, [rbp+1000h+var_5C0]; hObject
0x18001325a  test    rcx, rcx
0x18001325d  jz      short loc_180013264
0x18001325f  call    CloseHandle_0
0x180013264  mov     eax, ebx
0x180013266  mov     rcx, [rbp+1000h+var_30]
0x18001326d  xor     rcx, rsp; StackCookie
0x180013270  call    __security_check_cookie
0x180013275  add     rsp, 10E8h
0x18001327c  pop     rdi
0x18001327d  pop     rsi
0x18001327e  pop     rbx
0x18001327f  pop     rbp
0x180013280  retn
```
