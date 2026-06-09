# PlugIn::Load(void)

- ea: `0x18006dbc4`
- end: `0x18006dd2f`
- name: `?Load@PlugIn@@QEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(PlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800519e0`

## callees

- `0x18002f56c`
- `0x18005dcd4`
- `0x18006db58`
- `0x18006dbc4`
- `0x18006dd38`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dcfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006dcfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006dbf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006dbf2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006dc9f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006dc9f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006dc80`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006dc80`

## string_xrefs

- `0x18006dc79`: `%windir%\system32\taskcomp.dll`

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
0x18006dbc4  mov     [rsp+arg_8], rbx
0x18006dbc9  mov     [rsp+arg_10], rsi
0x18006dbce  push    rdi
0x18006dbcf  sub     rsp, 250h
0x18006dbd6  mov     rax, cs:__security_cookie
0x18006dbdd  xor     rax, rsp
0x18006dbe0  mov     [rsp+258h+var_18], rax
0x18006dbe8  mov     rdi, rcx
0x18006dbeb  xor     ebx, ebx
0x18006dbed  mov     [rsp+258h+var_238], rcx
0x18006dbf2  call    cs:__imp_EnterCriticalSection
0x18006dbf9  nop     dword ptr [rax+rax+00h]
0x18006dbfe  nop
0x18006dbff  cmp     [rdi+28h], rbx
0x18006dc03  jnz     loc_18006DCF8
0x18006dc09  mov     rsi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18006dc10  mov     rcx, rsi; this
0x18006dc13  call    ?WaitForConfiguration@JobStore@@AEBAXXZ; JobStore::WaitForConfiguration(void)
0x18006dc18  mov     rax, [rsi+50h]
0x18006dc1c  mov     ebx, [rax+40h]
0x18006dc1f  mov     rcx, rsi; this
0x18006dc22  call    ?WaitForConfiguration@JobStore@@AEBAXXZ; JobStore::WaitForConfiguration(void)
0x18006dc27  test    ebx, ebx
0x18006dc29  jnz     short loc_18006DC67
0x18006dc2b  lea     rax, WPP_GLOBAL_Control
0x18006dc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18006dc39  cmp     rcx, rax
0x18006dc3c  jz      short loc_18006DC5D
0x18006dc3e  test    byte ptr [rcx+1Ch], 2
0x18006dc42  jz      short loc_18006DC5D
0x18006dc44  cmp     byte ptr [rcx+19h], 3
0x18006dc48  jb      short loc_18006DC5D
0x18006dc4a  lea     edx, [rbx+0Ah]
0x18006dc4d  lea     r8, WPP_3bd1f756d1cf3533ff3385535c09a7f6_Traceguids
0x18006dc54  mov     rcx, [rcx+10h]
0x18006dc58  call    WPP_SF_
0x18006dc5d  mov     ebx, 80070422h
0x18006dc62  jmp     loc_18006DCF8
0x18006dc67  mov     rax, [rsi+50h]
0x18006dc6b  mov     esi, [rax+28h]
0x18006dc6e  mov     r8d, 105h; nSize
0x18006dc74  lea     rdx, [rsp+258h+Dst]; lpDst
0x18006dc79  lea     rcx, aWindirSystem32; "%windir%\\system32\\taskcomp.dll"
0x18006dc80  call    cs:__imp_ExpandEnvironmentStringsW
0x18006dc87  nop     dword ptr [rax+rax+00h]
0x18006dc8c  dec     eax
0x18006dc8e  cmp     eax, 104h
0x18006dc93  ja      short loc_18006DCDD
0x18006dc95  xor     r8d, r8d; dwFlags
0x18006dc98  xor     edx, edx; hFile
0x18006dc9a  lea     rcx, [rsp+258h+Dst]; lpLibFileName
0x18006dc9f  call    cs:__imp_LoadLibraryExW
0x18006dca6  nop     dword ptr [rax+rax+00h]
0x18006dcab  mov     [rdi+28h], rax
0x18006dcaf  test    rax, rax
0x18006dcb2  jz      short loc_18006DCDD
0x18006dcb4  mov     rcx, rdi; this
0x18006dcb7  call    ?LoadFunctionPointers@PlugIn@@AEAAJXZ; PlugIn::LoadFunctionPointers(void)
0x18006dcbc  mov     ebx, eax
0x18006dcbe  test    eax, eax
0x18006dcc0  js      short loc_18006DCD3
0x18006dcc2  mov     ecx, esi
0x18006dcc4  mov     rax, [rdi+30h]
0x18006dcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dccd  mov     ebx, eax
0x18006dccf  test    eax, eax
0x18006dcd1  jns     short loc_18006DCF8
0x18006dcd3  mov     rcx, rdi; this
0x18006dcd6  call    ?Internal_Unload@PlugIn@@AEAAXXZ; PlugIn::Internal_Unload(void)
0x18006dcdb  jmp     short loc_18006DCF8
0x18006dcdd  call    cs:__imp_GetLastError
0x18006dce4  nop     dword ptr [rax+rax+00h]
0x18006dce9  test    eax, eax
0x18006dceb  mov     ebx, eax
0x18006dced  jle     short loc_18006DCF8
0x18006dcef  movzx   ebx, ax
0x18006dcf2  or      ebx, 80070000h
0x18006dcf8  mov     rcx, rdi; lpCriticalSection
0x18006dcfb  call    cs:__imp_LeaveCriticalSection
0x18006dd02  nop     dword ptr [rax+rax+00h]
0x18006dd07  mov     eax, ebx
0x18006dd09  mov     rcx, [rsp+258h+var_18]
0x18006dd11  xor     rcx, rsp; StackCookie
0x18006dd14  call    __security_check_cookie
0x18006dd19  lea     r11, [rsp+258h+var_8]
0x18006dd21  mov     rbx, [r11+18h]
0x18006dd25  mov     rsi, [r11+20h]
0x18006dd29  mov     rsp, r11
0x18006dd2c  pop     rdi
0x18006dd2d  retn
```
