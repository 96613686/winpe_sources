# OpenProcessTokenHelper(ulong,int,ulong)

- ea: `0x1800946c0`
- end: `0x1800948b1`
- name: `?OpenProcessTokenHelper@@YAPEAXKHK@Z`
- size: `497`
- prototype: `void *(unsigned int, int, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180093cfc`
- `0x1800940c4`
- `0x180094d28`
- `0x180134444`
- `0x1802bf610`
- `0x1802bfb48`

## callees

- `0x180091b98`
- `0x180092df4`
- `0x1800946c0`
- `0x1801345f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800947c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800947c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800947da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800947da`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800947ee`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180094842`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800947ee`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180094842`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180094757`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180094757`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180094783`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800947a4`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180094783`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800947a4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180094887`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180094887`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18009481f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18009481f`

## pseudocode

```c
void *__fastcall OpenProcessTokenHelper(__int64 a1, int a2, DWORD a3)
{
  char *v4; // rbx
  void *TokenHandle[2]; // [rsp+20h] [rbp-10h] BYREF
  int v7; // [rsp+48h] [rbp+18h] BYREF
  char *v8; // [rsp+58h] [rbp+28h] BYREF

  v7 = a2;
  TokenHandle[0] = 0;
  if ( !BasicUiaUtils::s_isHoloLensDetermined )
  {
    v7 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
    BasicUiaUtils::s_isHoloLens = v7 == 10;
    BasicUiaUtils::s_isHoloLensDetermined = 1;
  }
  if ( BasicUiaUtils::s_isHoloLens )
    goto LABEL_21;
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop && !BasicUiaUtils::IsWinPE() )
  {
LABEL_21:
    if ( (int)UMgrOpenProcessTokenForQuery(a3, TokenHandle) < 0 )
      TokenHandle[0] = 0;
  }
  if ( !TokenHandle[0] )
  {
    if ( !BasicUiaUtils::s_isHoloLensDetermined )
    {
      v7 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
      BasicUiaUtils::s_isHoloLens = v7 == 10;
      BasicUiaUtils::s_isHoloLensDetermined = 1;
    }
    if ( BasicUiaUtils::s_isHoloLens )
      goto LABEL_24;
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( !BasicUiaUtils::s_isDesktop && !BasicUiaUtils::IsWinPE() )
    {
LABEL_24:
      v8 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v8,
        0);
      if ( (int)UMgrOpenProcessHandleForAccess(4096, a3, &v8) >= 0 )
      {
        v4 = v8;
        v8 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
LABEL_15:
        if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          if ( !OpenProcessToken(v4, 8u, TokenHandle) )
            TokenHandle[0] = 0;
          CloseHandle(v4);
        }
        return TokenHandle[0];
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
    }
    v4 = (char *)OpenProcess(0x1000u, 0, a3);
    goto LABEL_15;
  }
  return TokenHandle[0];
}

```

## disassembly

```asm
0x1800946c0  mov     [rsp-8+arg_0], rbx
0x1800946c5  mov     [rsp-8+arg_10], rdi
0x1800946ca  mov     [rsp-8+arg_8], edx
0x1800946ce  push    rbp
0x1800946cf  mov     rbp, rsp
0x1800946d2  sub     rsp, 30h
0x1800946d6  mov     al, cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x1800946dc  xor     edi, edi
0x1800946de  mov     [rbp+TokenHandle], rdi
0x1800946e2  nop
0x1800946e3  mov     ebx, r8d
0x1800946e6  test    al, al
0x1800946e8  jz      loc_1800947E2
0x1800946ee  cmp     cs:?s_isHoloLens@BasicUiaUtils@@2_NA, dil; bool BasicUiaUtils::s_isHoloLens
0x1800946f5  jnz     loc_180094819
0x1800946fb  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180094701  nop
0x180094702  test    al, al
0x180094704  jz      short loc_18009477E
0x180094706  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, dil; bool BasicUiaUtils::s_isDesktop
0x18009470d  jz      loc_18009480C
0x180094713  cmp     [rbp+TokenHandle], rdi
0x180094717  jnz     short loc_18009476A
0x180094719  mov     al, cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18009471f  nop
0x180094720  test    al, al
0x180094722  jz      loc_180094836
0x180094728  cmp     cs:?s_isHoloLens@BasicUiaUtils@@2_NA, dil; bool BasicUiaUtils::s_isHoloLens
0x18009472f  jnz     loc_18009486D
0x180094735  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18009473b  nop
0x18009473c  test    al, al
0x18009473e  jz      short loc_18009479F
0x180094740  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, dil; bool BasicUiaUtils::s_isDesktop
0x180094747  jz      loc_180094860
0x18009474d  mov     r8d, ebx; dwProcessId
0x180094750  xor     edx, edx; bInheritHandle
0x180094752  mov     ecx, 1000h; dwDesiredAccess
0x180094757  call    cs:__imp_OpenProcess
0x18009475d  mov     rbx, rax
0x180094760  lea     rax, [rbx-1]
0x180094764  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180094768  jbe     short loc_1800947BD
0x18009476a  mov     rax, [rbp+TokenHandle]
0x18009476e  mov     rbx, [rsp+30h+arg_0]
0x180094773  mov     rdi, [rsp+30h+arg_10]
0x180094778  add     rsp, 30h
0x18009477c  pop     rbp
0x18009477d  retn
0x18009477e  mov     ecx, 1800h; nIndex
0x180094783  call    cs:__imp_GetSystemMetrics
0x180094789  test    eax, eax
0x18009478b  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x180094792  nop
0x180094793  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18009479a  jmp     loc_180094706
0x18009479f  mov     ecx, 1800h; nIndex
0x1800947a4  call    cs:__imp_GetSystemMetrics
0x1800947aa  test    eax, eax
0x1800947ac  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x1800947b3  nop
0x1800947b4  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x1800947bb  jmp     short loc_180094740
0x1800947bd  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800947c1  mov     edx, 8; DesiredAccess
0x1800947c6  mov     rcx, rbx; ProcessHandle
0x1800947c9  call    cs:__imp_OpenProcessToken
0x1800947cf  test    eax, eax
0x1800947d1  jnz     short loc_1800947D7
0x1800947d3  mov     [rbp+TokenHandle], rdi
0x1800947d7  mov     rcx, rbx; hObject
0x1800947da  call    cs:__imp_CloseHandle
0x1800947e0  jmp     short loc_18009476A
0x1800947e2  xor     r8d, r8d
0x1800947e5  mov     [rbp+arg_8], edi
0x1800947e8  lea     rdx, [rbp+arg_8]
0x1800947ec  xor     ecx, ecx
0x1800947ee  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800947f4  cmp     [rbp+arg_8], 0Ah
0x1800947f8  setz    cs:?s_isHoloLens@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isHoloLens
0x1800947ff  nop
0x180094800  mov     cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x180094807  jmp     loc_1800946EE
0x18009480c  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x180094811  test    al, al
0x180094813  jnz     loc_180094713
0x180094819  lea     rdx, [rbp+TokenHandle]
0x18009481d  mov     ecx, ebx
0x18009481f  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180094825  test    eax, eax
0x180094827  jns     loc_180094713
0x18009482d  mov     [rbp+TokenHandle], rdi
0x180094831  jmp     loc_180094713
0x180094836  xor     r8d, r8d
0x180094839  mov     [rbp+arg_8], edi
0x18009483c  lea     rdx, [rbp+arg_8]
0x180094840  xor     ecx, ecx
0x180094842  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180094848  cmp     [rbp+arg_8], 0Ah
0x18009484c  setz    cs:?s_isHoloLens@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isHoloLens
0x180094853  nop
0x180094854  mov     cs:?s_isHoloLensDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isHoloLensDetermined
0x18009485b  jmp     loc_180094728
0x180094860  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x180094865  test    al, al
0x180094867  jnz     loc_18009474D
0x18009486d  xor     edx, edx
0x18009486f  mov     [rbp+arg_18], rdi
0x180094873  lea     rcx, [rbp+arg_18]
0x180094877  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009487c  lea     r8, [rbp+arg_18]
0x180094880  mov     edx, ebx
0x180094882  mov     ecx, 1000h
0x180094887  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x18009488d  lea     rcx, [rbp+arg_18]
0x180094891  test    eax, eax
0x180094893  js      short loc_1800948A7
0x180094895  mov     rbx, [rbp+arg_18]
0x180094899  mov     [rbp+arg_18], rdi
0x18009489d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800948a2  jmp     loc_180094760
0x1800948a7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800948ac  jmp     loc_18009474D
```
