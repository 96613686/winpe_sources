# PackageUtility::GetProcessHostComponentIds(void *,unsigned __int64 *,_GUID *)

- ea: `0x1800aab38`
- end: `0x1800aac99`
- name: `?GetProcessHostComponentIds@PackageUtility@@SAJPEAXPEA_KPEAU_GUID@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned __int64 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180021024`

## callees

- `0x180007fd8`
- `0x18001c368`
- `0x180020680`
- `0x18002d930`
- `0x1800aab38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800aab7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800aab7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aab8c`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800aabed`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800aabed`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800aac3c`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800aac3c`

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
0x1800aab38  mov     rax, rsp
0x1800aab3b  mov     [rax+8], rbx
0x1800aab3f  mov     [rax+18h], rsi
0x1800aab43  push    rdi
0x1800aab44  sub     rsp, 40h
0x1800aab48  mov     rbx, rcx
0x1800aab4b  mov     qword ptr [rdx], 0
0x1800aab52  xorps   xmm0, xmm0
0x1800aab55  mov     qword ptr [rax+10h], 0
0x1800aab5d  lea     rcx, [rax+10h]
0x1800aab61  mov     rdi, r8
0x1800aab64  movdqu  xmmword ptr [r8], xmm0
0x1800aab69  mov     rsi, rdx
0x1800aab6c  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800aab71  mov     r8, rax; TokenHandle
0x1800aab74  mov     edx, 8; DesiredAccess
0x1800aab79  mov     rcx, rbx; ProcessHandle
0x1800aab7c  call    cs:__imp_OpenProcessToken
0x1800aab83  nop     dword ptr [rax+rax+00h]
0x1800aab88  test    eax, eax
0x1800aab8a  jnz     short loc_1800AABCF
0x1800aab8c  call    cs:__imp_GetLastError
0x1800aab93  nop     dword ptr [rax+rax+00h]
0x1800aab98  mov     ecx, eax; unsigned int
0x1800aab9a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800aab9f  mov     ebx, eax
0x1800aaba1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaba8  lea     rdi, WPP_GLOBAL_Control
0x1800aabaf  cmp     rcx, rdi
0x1800aabb2  jz      loc_1800AAC7C
0x1800aabb8  test    byte ptr [rcx+1Ch], 1
0x1800aabbc  jz      loc_1800AAC7C
0x1800aabc2  mov     edx, 17h
0x1800aabc7  mov     r9d, eax
0x1800aabca  jmp     loc_1800AAC6C
0x1800aabcf  mov     rcx, [rsp+48h+arg_8]
0x1800aabd4  xor     ebx, ebx
0x1800aabd6  mov     [rsp+48h+var_18], rbx
0x1800aabdb  xor     r9d, r9d
0x1800aabde  mov     [rsp+48h+var_20], rdi
0x1800aabe3  xor     r8d, r8d
0x1800aabe6  xor     edx, edx
0x1800aabe8  mov     [rsp+48h+var_28], rbx
0x1800aabed  call    cs:__imp_RtlQueryPackageIdentityEx
0x1800aabf4  nop     dword ptr [rax+rax+00h]
0x1800aabf9  lea     rdi, WPP_GLOBAL_Control
0x1800aac00  test    eax, eax
0x1800aac02  jns     short loc_1800AAC34
0x1800aac04  mov     ebx, eax
0x1800aac06  bts     ebx, 1Ch
0x1800aac0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aac11  cmp     rcx, rdi
0x1800aac14  jz      short loc_1800AAC34
0x1800aac16  test    byte ptr [rcx+1Ch], 2
0x1800aac1a  jz      short loc_1800AAC34
0x1800aac1c  mov     rcx, [rcx+10h]
0x1800aac20  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800aac27  mov     edx, 18h
0x1800aac2c  mov     r9d, ebx
0x1800aac2f  call    WPP_SF_d
0x1800aac34  mov     rcx, [rsp+48h+arg_8]
0x1800aac39  mov     rdx, rsi
0x1800aac3c  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x1800aac43  nop     dword ptr [rax+rax+00h]
0x1800aac48  test    eax, eax
0x1800aac4a  jns     short loc_1800AAC7C
0x1800aac4c  mov     ebx, eax
0x1800aac4e  bts     ebx, 1Ch
0x1800aac52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aac59  cmp     rcx, rdi
0x1800aac5c  jz      short loc_1800AAC7C
0x1800aac5e  test    byte ptr [rcx+1Ch], 2
0x1800aac62  jz      short loc_1800AAC7C
0x1800aac64  mov     edx, 19h
0x1800aac69  mov     r9d, ebx
0x1800aac6c  mov     rcx, [rcx+10h]
0x1800aac70  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800aac77  call    WPP_SF_d
0x1800aac7c  lea     rcx, [rsp+48h+arg_8]
0x1800aac81  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800aac86  mov     rsi, [rsp+48h+arg_10]
0x1800aac8b  mov     eax, ebx
0x1800aac8d  mov     rbx, [rsp+48h+arg_0]
0x1800aac92  add     rsp, 40h
0x1800aac96  pop     rdi
0x1800aac97  retn
```
