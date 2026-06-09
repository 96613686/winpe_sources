# JobStore::DestroyMigratedUbpmStatsFiles(void)

- ea: `0x18006b49c`
- end: `0x18006b588`
- name: `?DestroyMigratedUbpmStatsFiles@JobStore@@AEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006d788`

## callees

- `0x180052584`
- `0x180056794`
- `0x18006b49c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b51c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006b51c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006b4db`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006b4db`

## string_xrefs

- `0x18006b4d4`: `%SystemRoot%\System32\logfiles\UbpmMigratedStats`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18006b49c  push    rbx
0x18006b49e  sub     rsp, 250h
0x18006b4a5  mov     rax, cs:__security_cookie
0x18006b4ac  xor     rax, rsp
0x18006b4af  mov     [rsp+258h+var_18], rax
0x18006b4b7  xor     edx, edx; Val
0x18006b4b9  lea     rcx, [rsp+258h+Dst]; void *
0x18006b4be  mov     r8d, 208h; Size
0x18006b4c4  call    memset_0
0x18006b4c9  mov     r8d, 104h; nSize
0x18006b4cf  lea     rdx, [rsp+258h+Dst]; lpDst
0x18006b4d4  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\logfiles\\UbpmM"...
0x18006b4db  call    cs:__imp_ExpandEnvironmentStringsW
0x18006b4e1  test    eax, eax
0x18006b4e3  jnz     short loc_18006B515
0x18006b4e5  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006b4ea  mov     ebx, eax
0x18006b4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b4f3  lea     rax, WPP_GLOBAL_Control
0x18006b4fa  cmp     rcx, rax
0x18006b4fd  jz      short loc_18006B56D
0x18006b4ff  test    dword ptr [rcx+1Ch], 40000h
0x18006b506  jz      short loc_18006B56D
0x18006b508  cmp     byte ptr [rcx+19h], 2
0x18006b50c  jb      short loc_18006B56D
0x18006b50e  mov     edx, 5Bh ; '['
0x18006b513  jmp     short loc_18006B554
0x18006b515  lea     rcx, [rsp+258h+Dst]; lpPathName
0x18006b51a  xor     ebx, ebx
0x18006b51c  call    cs:__imp_RemoveDirectoryW
0x18006b522  test    eax, eax
0x18006b524  jnz     short loc_18006B56D
0x18006b526  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006b52b  mov     ebx, eax
0x18006b52d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b534  lea     rax, WPP_GLOBAL_Control
0x18006b53b  cmp     rcx, rax
0x18006b53e  jz      short loc_18006B56D
0x18006b540  test    dword ptr [rcx+1Ch], 40000h
0x18006b547  jz      short loc_18006B56D
0x18006b549  cmp     byte ptr [rcx+19h], 2
0x18006b54d  jb      short loc_18006B56D
0x18006b54f  mov     edx, 5Ch ; '\'
0x18006b554  mov     rcx, [rcx+10h]
0x18006b558  lea     r9, [rsp+258h+Dst]
0x18006b55d  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006b564  mov     [rsp+258h+var_238], ebx
0x18006b568  call    WPP_SF_Sd
0x18006b56d  mov     eax, ebx
0x18006b56f  mov     rcx, [rsp+258h+var_18]
0x18006b577  xor     rcx, rsp; StackCookie
0x18006b57a  call    __security_check_cookie
0x18006b57f  add     rsp, 250h
0x18006b586  pop     rbx
0x18006b587  retn
```
