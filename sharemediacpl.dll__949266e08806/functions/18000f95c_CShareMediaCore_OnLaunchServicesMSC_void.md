# CShareMediaCore::_OnLaunchServicesMSC(void)

- ea: `0x18000f95c`
- end: `0x18000fae1`
- name: `?_OnLaunchServicesMSC@CShareMediaCore@@AEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000b78c`

## callees

- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x18000a5ec`
- `0x18000f95c`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x18000f9cd`
- `KERNEL32!GetSystemDirectoryW` at `0x18000f9cd`
- `KERNEL32!GetLastError` at `0x18000fa46`
- `KERNEL32!GetLastError` at `0x18000fa84`
- `KERNEL32!GetLastError` at `0x18000fa46`
- `KERNEL32!GetLastError` at `0x18000fa84`
- `SHELL32!ShellExecuteExW` at `0x18000fa3c`
- `SHELL32!ShellExecuteExW` at `0x18000fa3c`

## string_xrefs

- `0x18000fa10`: `services.msc`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_OnLaunchServicesMSC(CShareMediaCore *this)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  _QWORD *v4; // rcx
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_13;
  }
  v2 = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.lpVerb = L"runas";
  pExecInfo.lpFile = L"mmc.exe";
  pExecInfo.lpParameters = L"services.msc";
  pExecInfo.lpDirectory = Buffer;
  pExecInfo.hwnd = CShareMediaCore::GetParentWindow(this);
  pExecInfo.nShow = 5;
  if ( ShellExecuteExW(&pExecInfo) )
  {
LABEL_13:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v3 = GetLastError();
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_14:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
        WPP_SF_d(v4[2], 74, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v2);
      return v2;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    goto LABEL_13;
  }
  return v2;
}

```

## disassembly

```asm
0x18000f95c  push    rbp
0x18000f95e  push    rbx
0x18000f95f  push    rdi
0x18000f960  push    r14
0x18000f962  lea     rbp, [rsp-1B8h]
0x18000f96a  sub     rsp, 2B8h
0x18000f971  mov     rax, cs:__security_cookie
0x18000f978  xor     rax, rsp
0x18000f97b  mov     [rbp+1D0h+var_30], rax
0x18000f982  mov     rdi, rcx
0x18000f985  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f98c  lea     r14, WPP_GLOBAL_Control
0x18000f993  cmp     rcx, r14
0x18000f996  jz      short loc_18000F9B3
0x18000f998  test    byte ptr [rcx+1Ch], 20h
0x18000f99c  jz      short loc_18000F9B3
0x18000f99e  mov     rcx, [rcx+10h]
0x18000f9a2  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000f9a9  mov     edx, 48h ; 'H'
0x18000f9ae  call    WPP_SF_
0x18000f9b3  xor     edx, edx; Val
0x18000f9b5  lea     rcx, [rbp+1D0h+Buffer]; void *
0x18000f9b9  mov     r8d, 208h; Size
0x18000f9bf  call    memset_0
0x18000f9c4  mov     edx, 104h; uSize
0x18000f9c9  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x18000f9cd  call    cs:__imp_GetSystemDirectoryW
0x18000f9d3  test    eax, eax
0x18000f9d5  jz      loc_18000FA84
0x18000f9db  xor     ebx, ebx
0x18000f9dd  lea     rcx, [rsp+2D0h+pExecInfo]; void *
0x18000f9e2  xor     edx, edx; Val
0x18000f9e4  lea     r8d, [rbx+70h]; Size
0x18000f9e8  call    memset_0
0x18000f9ed  lea     rax, aRunas; "runas"
0x18000f9f4  mov     [rsp+2D0h+pExecInfo.cbSize], 70h ; 'p'
0x18000f9fc  mov     [rsp+2D0h+pExecInfo.lpVerb], rax
0x18000fa01  mov     rcx, rdi; this
0x18000fa04  lea     rax, aMmcExe; "mmc.exe"
0x18000fa0b  mov     [rsp+2D0h+pExecInfo.lpFile], rax
0x18000fa10  lea     rax, aServicesMsc; "services.msc"
0x18000fa17  mov     [rsp+2D0h+pExecInfo.lpParameters], rax
0x18000fa1c  lea     rax, [rbp+1D0h+Buffer]
0x18000fa20  mov     [rsp+2D0h+pExecInfo.lpDirectory], rax
0x18000fa25  call    ?GetParentWindow@CShareMediaCore@@QEAAPEAUHWND__@@XZ; CShareMediaCore::GetParentWindow(void)
0x18000fa2a  lea     rcx, [rsp+2D0h+pExecInfo]; pExecInfo
0x18000fa2f  mov     [rsp+2D0h+pExecInfo.hwnd], rax
0x18000fa34  mov     [rsp+2D0h+pExecInfo.nShow], 5
0x18000fa3c  call    cs:__imp_ShellExecuteExW
0x18000fa42  test    eax, eax
0x18000fa44  jnz     short loc_18000FA99
0x18000fa46  call    cs:__imp_GetLastError
0x18000fa4c  mov     ebx, eax
0x18000fa4e  test    eax, eax
0x18000fa50  jle     short loc_18000FA5B
0x18000fa52  movzx   ebx, ax
0x18000fa55  or      ebx, 80070000h
0x18000fa5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa62  cmp     rcx, r14
0x18000fa65  jz      short loc_18000FAC3
0x18000fa67  test    byte ptr [rcx+1Ch], 8
0x18000fa6b  jz      short loc_18000FAA0
0x18000fa6d  mov     rcx, [rcx+10h]
0x18000fa71  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fa78  mov     edx, 49h ; 'I'
0x18000fa7d  call    WPP_SF_
0x18000fa82  jmp     short loc_18000FA99
0x18000fa84  call    cs:__imp_GetLastError
0x18000fa8a  mov     ebx, eax
0x18000fa8c  test    eax, eax
0x18000fa8e  jle     short loc_18000FA99
0x18000fa90  movzx   ebx, ax
0x18000fa93  or      ebx, 80070000h
0x18000fa99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faa0  cmp     rcx, r14
0x18000faa3  jz      short loc_18000FAC3
0x18000faa5  test    byte ptr [rcx+1Ch], 20h
0x18000faa9  jz      short loc_18000FAC3
0x18000faab  mov     rcx, [rcx+10h]
0x18000faaf  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fab6  mov     edx, 4Ah ; 'J'
0x18000fabb  mov     r9d, ebx
0x18000fabe  call    WPP_SF_d
0x18000fac3  mov     eax, ebx
0x18000fac5  mov     rcx, [rbp+1D0h+var_30]
0x18000facc  xor     rcx, rsp; StackCookie
0x18000facf  call    __security_check_cookie
0x18000fad4  add     rsp, 2B8h
0x18000fadb  pop     r14
0x18000fadd  pop     rdi
0x18000fade  pop     rbx
0x18000fadf  pop     rbp
0x18000fae0  retn
```
