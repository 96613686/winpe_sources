# PlugIn::Load(void)

- ea: `0x18006a738`
- end: `0x18006a881`
- name: `?Load@PlugIn@@QEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(PlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f190`

## callees

- `0x1800398d8`
- `0x18005b124`
- `0x18006a6d4`
- `0x18006a738`
- `0x18006a888`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a83c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a854`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a766`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a766`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a804`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a7eb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006a7eb`

## string_xrefs

- `0x18006a7e4`: `%windir%\system32\taskcomp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PlugIn::Load(struct _RTL_CRITICAL_SECTION *this)
{
  signed int FunctionPointers; // ebx
  JobStore *v3; // rsi
  int v4; // ebx
  unsigned int v5; // esi
  HMODULE Library; // rax
  signed int LastError; // eax
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  FunctionPointers = 0;
  EnterCriticalSection(this);
  if ( !this[1].DebugInfo )
  {
    v3 = JobStore::m_pCommonStore;
    JobStore::WaitForConfiguration(JobStore::m_pCommonStore);
    v4 = *(_DWORD *)(*((_QWORD *)v3 + 10) + 64LL);
    JobStore::WaitForConfiguration(v3);
    if ( v4 )
    {
      v5 = *(_DWORD *)(*((_QWORD *)v3 + 10) + 40LL);
      if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\taskcomp.dll", Dst, 0x105u) - 1 <= 0x104
        && (Library = LoadLibraryExW(Dst, 0, 0), (this[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)Library) != 0) )
      {
        FunctionPointers = PlugIn::LoadFunctionPointers((PlugIn *)this);
        if ( FunctionPointers < 0
          || (FunctionPointers = (*(__int64 (__fastcall **)(_QWORD))&this[1].LockCount)(v5), FunctionPointers < 0) )
        {
          PlugIn::Internal_Unload((PlugIn *)this);
        }
      }
      else
      {
        LastError = GetLastError();
        FunctionPointers = LastError;
        if ( LastError > 0 )
          FunctionPointers = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3bd1f756d1cf3533ff3385535c09a7f6_Traceguids);
      }
      FunctionPointers = -2147023838;
    }
  }
  LeaveCriticalSection(this);
  return (unsigned int)FunctionPointers;
}

```

## disassembly

```asm
0x18006a738  mov     [rsp+arg_8], rbx
0x18006a73d  mov     [rsp+arg_10], rsi
0x18006a742  push    rdi
0x18006a743  sub     rsp, 250h
0x18006a74a  mov     rax, cs:__security_cookie
0x18006a751  xor     rax, rsp
0x18006a754  mov     [rsp+258h+var_18], rax
0x18006a75c  mov     rdi, rcx
0x18006a75f  xor     ebx, ebx
0x18006a761  mov     [rsp+258h+var_238], rcx
0x18006a766  call    cs:__imp_EnterCriticalSection
0x18006a76c  nop
0x18006a76d  cmp     [rdi+28h], rbx
0x18006a771  jnz     loc_18006A851
0x18006a777  mov     rsi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18006a77e  mov     rcx, rsi; this
0x18006a781  call    ?WaitForConfiguration@JobStore@@AEBAXXZ; JobStore::WaitForConfiguration(void)
0x18006a786  mov     rax, [rsi+50h]
0x18006a78a  mov     ebx, [rax+40h]
0x18006a78d  mov     rcx, rsi; this
0x18006a790  call    ?WaitForConfiguration@JobStore@@AEBAXXZ; JobStore::WaitForConfiguration(void)
0x18006a795  test    ebx, ebx
0x18006a797  jnz     short loc_18006A7D2
0x18006a799  lea     rax, WPP_GLOBAL_Control
0x18006a7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a7a7  cmp     rcx, rax
0x18006a7aa  jz      short loc_18006A7CB
0x18006a7ac  test    byte ptr [rcx+1Ch], 2
0x18006a7b0  jz      short loc_18006A7CB
0x18006a7b2  cmp     byte ptr [rcx+19h], 3
0x18006a7b6  jb      short loc_18006A7CB
0x18006a7b8  lea     edx, [rbx+0Ah]
0x18006a7bb  lea     r8, WPP_3bd1f756d1cf3533ff3385535c09a7f6_Traceguids
0x18006a7c2  mov     rcx, [rcx+10h]
0x18006a7c6  call    WPP_SF_
0x18006a7cb  mov     ebx, 80070422h
0x18006a7d0  jmp     short loc_18006A851
0x18006a7d2  mov     rax, [rsi+50h]
0x18006a7d6  mov     esi, [rax+28h]
0x18006a7d9  mov     r8d, 105h; nSize
0x18006a7df  lea     rdx, [rsp+258h+Dst]; lpDst
0x18006a7e4  lea     rcx, aWindirSystem32; "%windir%\\system32\\taskcomp.dll"
0x18006a7eb  call    cs:__imp_ExpandEnvironmentStringsW
0x18006a7f1  dec     eax
0x18006a7f3  cmp     eax, 104h
0x18006a7f8  ja      short loc_18006A83C
0x18006a7fa  xor     r8d, r8d; dwFlags
0x18006a7fd  xor     edx, edx; hFile
0x18006a7ff  lea     rcx, [rsp+258h+Dst]; lpLibFileName
0x18006a804  call    cs:__imp_LoadLibraryExW
0x18006a80a  mov     [rdi+28h], rax
0x18006a80e  test    rax, rax
0x18006a811  jz      short loc_18006A83C
0x18006a813  mov     rcx, rdi; this
0x18006a816  call    ?LoadFunctionPointers@PlugIn@@AEAAJXZ; PlugIn::LoadFunctionPointers(void)
0x18006a81b  mov     ebx, eax
0x18006a81d  test    eax, eax
0x18006a81f  js      short loc_18006A832
0x18006a821  mov     ecx, esi
0x18006a823  mov     rax, [rdi+30h]
0x18006a827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a82c  mov     ebx, eax
0x18006a82e  test    eax, eax
0x18006a830  jns     short loc_18006A851
0x18006a832  mov     rcx, rdi; this
0x18006a835  call    ?Internal_Unload@PlugIn@@AEAAXXZ; PlugIn::Internal_Unload(void)
0x18006a83a  jmp     short loc_18006A851
0x18006a83c  call    cs:__imp_GetLastError
0x18006a842  test    eax, eax
0x18006a844  mov     ebx, eax
0x18006a846  jle     short loc_18006A851
0x18006a848  movzx   ebx, ax
0x18006a84b  or      ebx, 80070000h
0x18006a851  mov     rcx, rdi; lpCriticalSection
0x18006a854  call    cs:__imp_LeaveCriticalSection
0x18006a85a  mov     eax, ebx
0x18006a85c  mov     rcx, [rsp+258h+var_18]
0x18006a864  xor     rcx, rsp; StackCookie
0x18006a867  call    __security_check_cookie
0x18006a86c  lea     r11, [rsp+258h+var_8]
0x18006a874  mov     rbx, [r11+18h]
0x18006a878  mov     rsi, [r11+20h]
0x18006a87c  mov     rsp, r11
0x18006a87f  pop     rdi
0x18006a880  retn
```
