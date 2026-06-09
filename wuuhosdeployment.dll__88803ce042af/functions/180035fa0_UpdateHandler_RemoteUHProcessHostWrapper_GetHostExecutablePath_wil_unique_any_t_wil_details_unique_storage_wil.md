# UpdateHandler::RemoteUHProcessHostWrapper::GetHostExecutablePath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x180035fa0`
- end: `0x1800360f3`
- name: `?GetHostExecutablePath@RemoteUHProcessHostWrapper@UpdateHandler@@MEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x18000956c`
- `0x1800346d8`
- `0x180035fa0`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003608f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003608f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003607c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003607c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800360c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800360c8`

## string_xrefs

- `0x18003603e`: `Host process executable path: %ws`

## pseudocode

```c
__int64 __fastcall UpdateHandler::RemoteUHProcessHostWrapper::GetHostExecutablePath(__int64 a1, void **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID v5; // rbp
  void *v6; // rsi
  DWORD LastError; // ebx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  int v10; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  void (__fastcall ***v12)(_QWORD, __int64); // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12 = 0;
  pv = 0;
  v3 = UndockedModuleLoader::Load(
         (unsigned int)L"wu.wuaucltcore",
         (unsigned int)L"wuaucltcore.exe",
         1,
         (unsigned int)&v12,
         0,
         0,
         (__int64)&pv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    WUTrace(0, 0, 4096, 4);
    v5 = pv;
    pv = 0;
    v6 = *a2;
    if ( *a2 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v6);
      SetLastError(LastError);
    }
    *a2 = v5;
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\RemoteUHProcessHostWrapper.cpp",
      (const char *)(unsigned int)v3,
      v10);
  }
  v8 = v12;
  v12 = 0;
  if ( v8 )
    (**v8)(v8, 1);
  if ( pv )
    CoTaskMemFree(pv);
  return v4;
}

```

## disassembly

```asm
0x180035fa0  mov     r11, rsp
0x180035fa3  mov     [r11+8], rbx
0x180035fa7  mov     [r11+18h], rbp
0x180035fab  mov     [r11+20h], rsi
0x180035faf  push    rdi
0x180035fb0  sub     rsp, 60h
0x180035fb4  mov     rax, cs:__security_cookie
0x180035fbb  xor     rax, rsp
0x180035fbe  mov     [rsp+68h+var_18], rax
0x180035fc3  mov     rdi, rdx
0x180035fc6  mov     qword ptr [r11-20h], 0
0x180035fce  mov     qword ptr [r11-28h], 0
0x180035fd6  mov     qword ptr [r11-30h], 0
0x180035fde  lea     rax, [r11-28h]
0x180035fe2  mov     [r11-38h], rax
0x180035fe6  mov     qword ptr [r11-40h], 0
0x180035fee  mov     qword ptr [r11-48h], 0
0x180035ff6  lea     r9, [r11-20h]
0x180035ffa  mov     r8d, 1
0x180036000  lea     rdx, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x180036007  lea     rcx, aWuWuaucltcore; "wu.wuaucltcore"
0x18003600e  call    UndockedModuleLoader__Load
0x180036013  mov     ebx, eax
0x180036015  test    eax, eax
0x180036017  jns     short loc_180036034
0x180036019  mov     rcx, [rsp+68h]; this
0x18003601e  mov     r9d, eax; char *
0x180036021  lea     r8, aCW1SSrcClientE_8; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180036028  mov     edx, 190h; void *
0x18003602d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036032  jmp     short loc_18003609A
0x180036034  mov     rax, [rsp+68h+pv]
0x180036039  mov     [rsp+68h+var_38], rax
0x18003603e  lea     rax, aHostProcessExe; "Host process executable path: %ws"
0x180036045  mov     [rsp+68h+var_40], rax
0x18003604a  mov     [rsp+68h+var_48], 0
0x180036053  xor     edx, edx
0x180036055  xor     ecx, ecx
0x180036057  lea     r9d, [rdx+4]
0x18003605b  mov     r8d, 1000h
0x180036061  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180036066  mov     rbp, [rsp+68h+pv]
0x18003606b  mov     [rsp+68h+pv], 0
0x180036074  mov     rsi, [rdi]
0x180036077  test    rsi, rsi
0x18003607a  jz      short loc_180036095
0x18003607c  call    cs:__imp_GetLastError
0x180036082  mov     ebx, eax
0x180036084  mov     rcx, rsi; pv
0x180036087  call    cs:__imp_CoTaskMemFree
0x18003608d  mov     ecx, ebx; dwErrCode
0x18003608f  call    cs:__imp_SetLastError
0x180036095  mov     [rdi], rbp
0x180036098  xor     ebx, ebx
0x18003609a  mov     rcx, [rsp+68h+var_20]
0x18003609f  mov     [rsp+68h+var_20], 0
0x1800360a8  test    rcx, rcx
0x1800360ab  jz      short loc_1800360BE
0x1800360ad  mov     rax, [rcx]
0x1800360b0  mov     edx, 1
0x1800360b5  mov     rax, [rax]
0x1800360b8  call    _guard_dispatch_icall
0x1800360bd  nop
0x1800360be  mov     rcx, [rsp+68h+pv]; pv
0x1800360c3  test    rcx, rcx
0x1800360c6  jz      short loc_1800360CE
0x1800360c8  call    cs:__imp_CoTaskMemFree
0x1800360ce  mov     eax, ebx
0x1800360d0  mov     rcx, [rsp+68h+var_18]
0x1800360d5  xor     rcx, rsp; StackCookie
0x1800360d8  call    __security_check_cookie
0x1800360dd  lea     r11, [rsp+68h+var_8]
0x1800360e2  mov     rbx, [r11+10h]
0x1800360e6  mov     rbp, [r11+20h]
0x1800360ea  mov     rsi, [r11+28h]
0x1800360ee  mov     rsp, r11
0x1800360f1  pop     rdi
0x1800360f2  retn
```
