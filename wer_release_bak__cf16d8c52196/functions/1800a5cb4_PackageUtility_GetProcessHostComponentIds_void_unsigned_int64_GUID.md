# PackageUtility::GetProcessHostComponentIds(void *,unsigned __int64 *,_GUID *)

- ea: `0x1800a5cb4`
- end: `0x1800a5dfc`
- name: `?GetProcessHostComponentIds@PackageUtility@@SAJPEAXPEA_KPEAU_GUID@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned __int64 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002054c`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x18002bed4`
- `0x1800a5cb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a5cf8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a5cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5d02`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800a5d5d`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800a5d5d`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800a5da6`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800a5da6`

## pseudocode

```c
__int64 __fastcall PackageUtility::GetProcessHostComponentIds(
        HANDLE ProcessHandle,
        unsigned __int64 *a2,
        struct _GUID *a3)
{
  void **v6; // rax
  DWORD LastError; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int PackageIdentity; // eax
  int TokenHostIdAsUlong64; // eax
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v16 = 0;
  *a3 = 0;
  v6 = (void **)tlx::replace<tlx::file_handle_traits>(&v16);
  if ( OpenProcessToken(ProcessHandle, 8u, v6) )
  {
    v9 = 0;
    PackageIdentity = RtlQueryPackageIdentityEx(v16, 0, 0, 0, 0, a3, 0);
    if ( PackageIdentity < 0 )
    {
      v9 = PackageIdentity | 0x10000000;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids, v9);
    }
    TokenHostIdAsUlong64 = RtlQueryTokenHostIdAsUlong64(v16, a2);
    if ( TokenHostIdAsUlong64 < 0 )
    {
      v9 = TokenHostIdAsUlong64 | 0x10000000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v11 = 25;
        v12 = v9;
        goto LABEL_13;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    v9 = v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 23;
      v12 = v8;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids, v12);
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  return v9;
}

```

## disassembly

```asm
0x1800a5cb4  mov     rax, rsp
0x1800a5cb7  mov     [rax+8], rbx
0x1800a5cbb  mov     [rax+18h], rsi
0x1800a5cbf  push    rdi
0x1800a5cc0  sub     rsp, 40h
0x1800a5cc4  mov     rbx, rcx
0x1800a5cc7  mov     qword ptr [rdx], 0
0x1800a5cce  xorps   xmm0, xmm0
0x1800a5cd1  mov     qword ptr [rax+10h], 0
0x1800a5cd9  lea     rcx, [rax+10h]
0x1800a5cdd  mov     rdi, r8
0x1800a5ce0  movdqu  xmmword ptr [r8], xmm0
0x1800a5ce5  mov     rsi, rdx
0x1800a5ce8  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800a5ced  mov     r8, rax; TokenHandle
0x1800a5cf0  mov     edx, 8; DesiredAccess
0x1800a5cf5  mov     rcx, rbx; ProcessHandle
0x1800a5cf8  call    cs:__imp_OpenProcessToken
0x1800a5cfe  test    eax, eax
0x1800a5d00  jnz     short loc_1800A5D3F
0x1800a5d02  call    cs:__imp_GetLastError
0x1800a5d08  mov     ecx, eax; unsigned int
0x1800a5d0a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a5d0f  mov     ebx, eax
0x1800a5d11  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5d18  lea     rdi, WPP_GLOBAL_Control
0x1800a5d1f  cmp     rcx, rdi
0x1800a5d22  jz      loc_1800A5DE0
0x1800a5d28  test    byte ptr [rcx+1Ch], 1
0x1800a5d2c  jz      loc_1800A5DE0
0x1800a5d32  mov     edx, 17h
0x1800a5d37  mov     r9d, eax
0x1800a5d3a  jmp     loc_1800A5DD0
0x1800a5d3f  mov     rcx, [rsp+48h+arg_8]
0x1800a5d44  xor     ebx, ebx
0x1800a5d46  mov     [rsp+48h+var_18], rbx
0x1800a5d4b  xor     r9d, r9d
0x1800a5d4e  mov     [rsp+48h+var_20], rdi
0x1800a5d53  xor     r8d, r8d
0x1800a5d56  xor     edx, edx
0x1800a5d58  mov     [rsp+48h+var_28], rbx
0x1800a5d5d  call    cs:__imp_RtlQueryPackageIdentityEx
0x1800a5d63  lea     rdi, WPP_GLOBAL_Control
0x1800a5d6a  test    eax, eax
0x1800a5d6c  jns     short loc_1800A5D9E
0x1800a5d6e  mov     ebx, eax
0x1800a5d70  bts     ebx, 1Ch
0x1800a5d74  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5d7b  cmp     rcx, rdi
0x1800a5d7e  jz      short loc_1800A5D9E
0x1800a5d80  test    byte ptr [rcx+1Ch], 2
0x1800a5d84  jz      short loc_1800A5D9E
0x1800a5d86  mov     rcx, [rcx+10h]
0x1800a5d8a  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800a5d91  mov     edx, 18h
0x1800a5d96  mov     r9d, ebx
0x1800a5d99  call    WPP_SF_d
0x1800a5d9e  mov     rcx, [rsp+48h+arg_8]
0x1800a5da3  mov     rdx, rsi
0x1800a5da6  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x1800a5dac  test    eax, eax
0x1800a5dae  jns     short loc_1800A5DE0
0x1800a5db0  mov     ebx, eax
0x1800a5db2  bts     ebx, 1Ch
0x1800a5db6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5dbd  cmp     rcx, rdi
0x1800a5dc0  jz      short loc_1800A5DE0
0x1800a5dc2  test    byte ptr [rcx+1Ch], 2
0x1800a5dc6  jz      short loc_1800A5DE0
0x1800a5dc8  mov     edx, 19h
0x1800a5dcd  mov     r9d, ebx
0x1800a5dd0  mov     rcx, [rcx+10h]
0x1800a5dd4  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800a5ddb  call    WPP_SF_d
0x1800a5de0  lea     rcx, [rsp+48h+arg_8]
0x1800a5de5  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a5dea  mov     rsi, [rsp+48h+arg_10]
0x1800a5def  mov     eax, ebx
0x1800a5df1  mov     rbx, [rsp+48h+arg_0]
0x1800a5df6  add     rsp, 40h
0x1800a5dfa  pop     rdi
0x1800a5dfb  retn
```
