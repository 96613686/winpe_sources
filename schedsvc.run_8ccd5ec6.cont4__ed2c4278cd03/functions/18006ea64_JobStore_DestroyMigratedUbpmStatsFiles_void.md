# JobStore::DestroyMigratedUbpmStatsFiles(void)

- ea: `0x18006ea64`
- end: `0x18006eb5d`
- name: `?DestroyMigratedUbpmStatsFiles@JobStore@@AEAAJXZ`
- size: `249`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180070e78`

## callees

- `0x180054c80`
- `0x180059140`
- `0x18006ea64`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006eaea`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006eaea`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006eaa3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006eaa3`

## string_xrefs

- `0x18006ea9c`: `%SystemRoot%\System32\logfiles\UbpmMigratedStats`

## pseudocode

```c
__int64 __fastcall JobStore::DestroyMigratedUbpmStatsFiles(JobStore *this)
{
  int v1; // edx
  tsched *v2; // rcx
  unsigned int LastHrError; // ebx
  _QWORD *v4; // rcx
  int v5; // edx
  int v6; // edx
  tsched *v7; // rcx
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\logfiles\\UbpmMigratedStats", Dst, 0x104u) )
  {
    LastHrError = 0;
    if ( !RemoveDirectoryW(Dst) )
    {
      LastHrError = tsched::GetLastHrError(v7, v6);
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 92;
        goto LABEL_11;
      }
    }
  }
  else
  {
    LastHrError = tsched::GetLastHrError(v2, v1);
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 91;
LABEL_11:
      WPP_SF_Sd(
        v4[2],
        v5,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        (unsigned int)Dst,
        LastHrError);
    }
  }
  return LastHrError;
}

```

## disassembly

```asm
0x18006ea64  push    rbx
0x18006ea66  sub     rsp, 250h
0x18006ea6d  mov     rax, cs:__security_cookie
0x18006ea74  xor     rax, rsp
0x18006ea77  mov     [rsp+258h+var_18], rax
0x18006ea7f  xor     edx, edx; Val
0x18006ea81  lea     rcx, [rsp+258h+Dst]; void *
0x18006ea86  mov     r8d, 208h; Size
0x18006ea8c  call    memset_0
0x18006ea91  mov     r8d, 104h; nSize
0x18006ea97  lea     rdx, [rsp+258h+Dst]; lpDst
0x18006ea9c  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\logfiles\\UbpmM"...
0x18006eaa3  call    cs:__imp_ExpandEnvironmentStringsW
0x18006eaaa  nop     dword ptr [rax+rax+00h]
0x18006eaaf  test    eax, eax
0x18006eab1  jnz     short loc_18006EAE3
0x18006eab3  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006eab8  mov     ebx, eax
0x18006eaba  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eac1  lea     rax, WPP_GLOBAL_Control
0x18006eac8  cmp     rcx, rax
0x18006eacb  jz      short loc_18006EB41
0x18006eacd  test    dword ptr [rcx+1Ch], 40000h
0x18006ead4  jz      short loc_18006EB41
0x18006ead6  cmp     byte ptr [rcx+19h], 2
0x18006eada  jb      short loc_18006EB41
0x18006eadc  mov     edx, 5Bh ; '['
0x18006eae1  jmp     short loc_18006EB28
0x18006eae3  lea     rcx, [rsp+258h+Dst]; lpPathName
0x18006eae8  xor     ebx, ebx
0x18006eaea  call    cs:__imp_RemoveDirectoryW
0x18006eaf1  nop     dword ptr [rax+rax+00h]
0x18006eaf6  test    eax, eax
0x18006eaf8  jnz     short loc_18006EB41
0x18006eafa  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006eaff  mov     ebx, eax
0x18006eb01  mov     rcx, cs:WPP_GLOBAL_Control
0x18006eb08  lea     rax, WPP_GLOBAL_Control
0x18006eb0f  cmp     rcx, rax
0x18006eb12  jz      short loc_18006EB41
0x18006eb14  test    dword ptr [rcx+1Ch], 40000h
0x18006eb1b  jz      short loc_18006EB41
0x18006eb1d  cmp     byte ptr [rcx+19h], 2
0x18006eb21  jb      short loc_18006EB41
0x18006eb23  mov     edx, 5Ch ; '\'
0x18006eb28  mov     rcx, [rcx+10h]
0x18006eb2c  lea     r9, [rsp+258h+Dst]
0x18006eb31  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006eb38  mov     [rsp+258h+var_238], ebx
0x18006eb3c  call    WPP_SF_Sd
0x18006eb41  mov     eax, ebx
0x18006eb43  mov     rcx, [rsp+258h+var_18]
0x18006eb4b  xor     rcx, rsp; StackCookie
0x18006eb4e  call    __security_check_cookie
0x18006eb53  add     rsp, 250h
0x18006eb5a  pop     rbx
0x18006eb5b  retn
```
