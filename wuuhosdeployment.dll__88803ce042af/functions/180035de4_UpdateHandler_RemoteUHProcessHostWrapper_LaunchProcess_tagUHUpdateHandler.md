# UpdateHandler::RemoteUHProcessHostWrapper::LaunchProcess(tagUHUpdateHandler)

- ea: `0x180035de4`
- end: `0x180035f96`
- name: `?LaunchProcess@RemoteUHProcessHostWrapper@UpdateHandler@@AEAAJW4tagUHUpdateHandler@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180035a94`

## callees

- `0x180001e8c`
- `0x180003950`
- `0x18003543c`
- `0x180035de4`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035f51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035ef6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035eee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035f62`

## pseudocode

```c
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::LaunchProcess(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rdx
  void *v5; // rsi
  DWORD LastError; // ebx
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  int v10; // [rsp+28h] [rbp-E0h]
  LPVOID lpMem; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  pv = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 56LL))(a1, &pv);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v2,
      v10);
    goto LABEL_16;
  }
  lpMem = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)a1 + 64LL))(a1, 12, &lpMem);
  if ( v3 < 0 )
  {
    v4 = 342;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v3,
      v10);
    goto LABEL_14;
  }
  memset(Buffer, 0, 520);
  v10 = (int)lpMem;
  v3 = StringCchPrintfW(Buffer, 0x104u, L"%ws %ws", pv);
  if ( v3 < 0 )
  {
    v4 = 348;
    goto LABEL_12;
  }
  v5 = *(void **)(a1 + 64);
  if ( v5 && v5 != (void *)-1LL )
  {
    LastError = GetLastError();
    CloseHandle(v5);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 64) = 0;
  v3 = LaunchProcess(Buffer, *(_BYTE *)(a1 + 56), (HANDLE *)(a1 + 64), (DWORD *)(a1 + 72));
  if ( v3 < 0 )
  {
    v4 = 351;
    goto LABEL_12;
  }
  v3 = 0;
LABEL_14:
  v7 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
LABEL_16:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180035de4  mov     rax, rsp
0x180035de7  mov     [rax+10h], rbx
0x180035deb  mov     [rax+18h], rsi
0x180035def  mov     [rax+20h], rdi
0x180035df3  push    rbp
0x180035df4  push    r14
0x180035df6  push    r15
0x180035df8  lea     rbp, [rax-178h]
0x180035dff  sub     rsp, 260h
0x180035e06  mov     rax, cs:__security_cookie
0x180035e0d  xor     rax, rsp
0x180035e10  mov     [rbp+170h+var_20], rax
0x180035e17  mov     rdi, rcx
0x180035e1a  xor     r15d, r15d
0x180035e1d  mov     [rsp+270h+pv], r15
0x180035e22  mov     rax, [rcx]
0x180035e25  lea     rdx, [rsp+270h+pv]
0x180035e2a  mov     rax, [rax+38h]
0x180035e2e  call    _guard_dispatch_icall
0x180035e33  mov     ebx, eax
0x180035e35  test    eax, eax
0x180035e37  jns     short loc_180035E59
0x180035e39  mov     rcx, [rbp+178h]; this
0x180035e40  mov     r9d, eax; char *
0x180035e43  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035e4a  mov     edx, 153h; void *
0x180035e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035e54  jmp     loc_180035F58
0x180035e59  mov     [rsp+270h+lpMem], r15
0x180035e5e  mov     rax, [rdi]
0x180035e61  lea     r8, [rsp+270h+lpMem]
0x180035e66  mov     edx, 0Ch
0x180035e6b  mov     rcx, rdi
0x180035e6e  mov     rax, [rax+40h]
0x180035e72  call    _guard_dispatch_icall
0x180035e77  mov     ebx, eax
0x180035e79  test    eax, eax
0x180035e7b  jns     short loc_180035E87
0x180035e7d  mov     edx, 156h
0x180035e82  jmp     loc_180035F1E
0x180035e87  mov     [rsp+270h+Buffer], r15w
0x180035e8d  xor     edx, edx; Val
0x180035e8f  mov     r8d, 206h; Size
0x180035e95  lea     rcx, [rsp+270h+var_22E]; void *
0x180035e9a  call    memset
0x180035e9f  mov     rax, [rsp+270h+lpMem]
0x180035ea4  mov     qword ptr [rsp+270h+var_250], rax; int
0x180035ea9  mov     r9, [rsp+270h+pv]
0x180035eae  lea     r8, aWsWs_0; "%ws %ws"
0x180035eb5  mov     edx, 104h; unsigned __int64
0x180035eba  lea     rcx, [rsp+270h+Buffer]; Buffer
0x180035ebf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180035ec4  mov     ebx, eax
0x180035ec6  test    eax, eax
0x180035ec8  jns     short loc_180035ED1
0x180035eca  mov     edx, 15Ch
0x180035ecf  jmp     short loc_180035F1E
0x180035ed1  lea     r14, [rdi+40h]
0x180035ed5  mov     rsi, [r14]
0x180035ed8  test    rsi, rsi
0x180035edb  jz      short loc_180035EFC
0x180035edd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180035ee1  jz      short loc_180035EFC
0x180035ee3  call    cs:__imp_GetLastError
0x180035ee9  mov     ebx, eax
0x180035eeb  mov     rcx, rsi; hObject
0x180035eee  call    cs:__imp_CloseHandle
0x180035ef4  mov     ecx, ebx; dwErrCode
0x180035ef6  call    cs:__imp_SetLastError
0x180035efc  mov     [r14], r15
0x180035eff  lea     r9, [rdi+48h]
0x180035f03  mov     r8, r14
0x180035f06  mov     dl, [rdi+38h]
0x180035f09  lea     rcx, [rsp+270h+Buffer]; lpCommandLine
0x180035f0e  call    LaunchProcess
0x180035f13  mov     ebx, eax
0x180035f15  test    eax, eax
0x180035f17  jns     short loc_180035F36
0x180035f19  mov     edx, 15Fh; void *
0x180035f1e  mov     rcx, [rbp+178h]; this
0x180035f25  mov     r9d, ebx; char *
0x180035f28  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180035f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f34  jmp     short loc_180035F39
0x180035f36  mov     ebx, r15d
0x180035f39  mov     rdi, [rsp+270h+lpMem]
0x180035f3e  test    rdi, rdi
0x180035f41  jz      short loc_180035F58
0x180035f43  call    cs:__imp_GetProcessHeap
0x180035f49  mov     rcx, rax; hHeap
0x180035f4c  mov     r8, rdi; lpMem
0x180035f4f  xor     edx, edx; dwFlags
0x180035f51  call    cs:__imp_HeapFree
0x180035f57  nop
0x180035f58  mov     rcx, [rsp+270h+pv]; pv
0x180035f5d  test    rcx, rcx
0x180035f60  jz      short loc_180035F68
0x180035f62  call    cs:__imp_CoTaskMemFree
0x180035f68  mov     eax, ebx
0x180035f6a  mov     rcx, [rbp+170h+var_20]
0x180035f71  xor     rcx, rsp; StackCookie
0x180035f74  call    __security_check_cookie
0x180035f79  lea     r11, [rsp+270h+var_10]
0x180035f81  mov     rbx, [r11+28h]
0x180035f85  mov     rsi, [r11+30h]
0x180035f89  mov     rdi, [r11+38h]
0x180035f8d  mov     rsp, r11
0x180035f90  pop     r15
0x180035f92  pop     r14
0x180035f94  pop     rbp
0x180035f95  retn
```
