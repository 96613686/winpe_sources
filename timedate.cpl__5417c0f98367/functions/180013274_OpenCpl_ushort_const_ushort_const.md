# OpenCpl(ushort const *,ushort const *)

- ea: `0x180013274`
- end: `0x1800133a9`
- name: `?OpenCpl@@YAHPEBG0@Z`
- size: `309`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800057f0`
- `0x18000a640`
- `0x180011020`
- `0x1800112a0`

## callees

- `0x180008a0c`
- `0x180012824`
- `0x1800130b4`
- `0x180013274`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800132ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800132ad`
- `SHELL32!ShellExecuteExW` at `0x180013373`
- `SHELL32!ShellExecuteExW` at `0x180013373`

## pseudocode

```c
__int64 __fastcall OpenCpl(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  HINSTANCE v5; // rax
  HINSTANCE v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+38h] [rbp-C8h] BYREF
  int v9; // [rsp+3Ch] [rbp-C4h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v12[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v4 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) && StringCchPrintfW(v12, 0x104u, L"%s\\%s", Buffer, a1) >= 0 )
  {
    v7 = 0;
    v8 = 64;
    v9 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,enum EC_HOST_UI_MODE,enum LAUNCHER_SERVICES_OPTIONS>(
      &v7,
      &v9,
      &v8);
    pExecInfo.cbSize = 112;
    pExecInfo.lpFile = v12;
    v5 = v7;
    pExecInfo.fMask = 0x8000000;
    pExecInfo.hwnd = 0;
    pExecInfo.lpVerb = 0;
    pExecInfo.lpParameters = a2;
    pExecInfo.lpDirectory = 0;
    *(_QWORD *)&pExecInfo.nShow = 1;
    if ( v7 )
      v5 = v7 + 10;
    pExecInfo.hInstApp = v5;
    memset(&pExecInfo.lpIDList, 0, 48);
    v4 = ShellExecuteExW(&pExecInfo);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  return v4;
}

```

## disassembly

```asm
0x180013274  mov     [rsp-8+arg_10], rbx
0x180013279  push    rbp
0x18001327a  push    rsi
0x18001327b  push    rdi
0x18001327c  lea     rbp, [rsp-3E0h]
0x180013284  sub     rsp, 4E0h
0x18001328b  mov     rax, cs:__security_cookie
0x180013292  xor     rax, rsp
0x180013295  mov     [rbp+3F0h+var_20], rax
0x18001329c  mov     rdi, rdx
0x18001329f  mov     rsi, rcx
0x1800132a2  mov     edx, 104h; uSize
0x1800132a7  lea     rcx, [rbp+3F0h+Buffer]; lpBuffer
0x1800132ab  xor     ebx, ebx
0x1800132ad  call    cs:__imp_GetSystemDirectoryW
0x1800132b3  test    eax, eax
0x1800132b5  jz      loc_180013385
0x1800132bb  lea     r9, [rbp+3F0h+Buffer]
0x1800132bf  mov     [rsp+4F0h+var_4D0], rsi
0x1800132c4  lea     r8, aSS; "%s\\%s"
0x1800132cb  mov     edx, 104h; unsigned __int64
0x1800132d0  lea     rcx, [rbp+3F0h+var_230]; unsigned __int16 *
0x1800132d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800132dc  test    eax, eax
0x1800132de  js      loc_180013385
0x1800132e4  lea     rcx, [rsp+4F0h+var_4C0]
0x1800132e9  mov     [rsp+4F0h+var_4C0], rbx
0x1800132ee  mov     [rsp+4F0h+var_4B8], 40h ; '@'
0x1800132f6  mov     [rsp+4F0h+var_4B4], ebx
0x1800132fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800132ff  lea     r8, [rsp+4F0h+var_4B8]
0x180013304  lea     rdx, [rsp+4F0h+var_4B4]
0x180013309  lea     rcx, [rsp+4F0h+var_4C0]
0x18001330e  call    ??$MakeAndInitialize@VCLauncherUIMode@@V1@W4EC_HOST_UI_MODE@@W4LAUNCHER_SERVICES_OPTIONS@@@Details@WRL@Microsoft@@YAJPEAPEAVCLauncherUIMode@@$$QEAW4EC_HOST_UI_MODE@@$$QEAW4LAUNCHER_SERVICES_OPTIONS@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLauncherUIMode,CLauncherUIMode,EC_HOST_UI_MODE,LAUNCHER_SERVICES_OPTIONS>(CLauncherUIMode * *,EC_HOST_UI_MODE &&,LAUNCHER_SERVICES_OPTIONS &&)
0x180013313  lea     rax, [rbp+3F0h+var_230]
0x18001331a  mov     [rsp+4F0h+pExecInfo.cbSize], 70h ; 'p'
0x180013322  mov     [rsp+4F0h+pExecInfo.lpFile], rax
0x180013327  mov     rax, [rsp+4F0h+var_4C0]
0x18001332c  mov     [rsp+4F0h+pExecInfo.fMask], 8000000h
0x180013334  mov     [rsp+4F0h+pExecInfo.hwnd], rbx
0x180013339  mov     [rsp+4F0h+pExecInfo.lpVerb], rbx
0x18001333e  mov     [rsp+4F0h+pExecInfo.lpParameters], rdi
0x180013343  mov     [rsp+4F0h+pExecInfo.lpDirectory], rbx
0x180013348  mov     qword ptr [rsp+4F0h+pExecInfo.nShow], 1
0x180013351  test    rax, rax
0x180013354  jz      short loc_18001335A
0x180013356  add     rax, 28h ; '('
0x18001335a  xorps   xmm0, xmm0
0x18001335d  mov     [rsp+4F0h+pExecInfo.hInstApp], rax
0x180013362  lea     rcx, [rsp+4F0h+pExecInfo]; pExecInfo
0x180013367  movups  xmmword ptr [rbp+3F0h+pExecInfo.lpIDList], xmm0
0x18001336b  movups  xmmword ptr [rbp+3F0h+pExecInfo.hkeyClass], xmm0
0x18001336f  movups  xmmword ptr [rbp+3F0h+pExecInfo.60h], xmm0
0x180013373  call    cs:__imp_ShellExecuteExW
0x180013379  lea     rcx, [rsp+4F0h+var_4C0]
0x18001337e  mov     ebx, eax
0x180013380  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013385  mov     eax, ebx
0x180013387  mov     rcx, [rbp+3F0h+var_20]
0x18001338e  xor     rcx, rsp; StackCookie
0x180013391  call    __security_check_cookie
0x180013396  mov     rbx, [rsp+4F0h+arg_10]
0x18001339e  add     rsp, 4E0h
0x1800133a5  pop     rdi
0x1800133a6  pop     rsi
0x1800133a7  pop     rbp
0x1800133a8  retn
```
