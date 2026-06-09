# CShareMediaCore::_OnMediaSharingPrivacyLink(void)

- ea: `0x18000fae8`
- end: `0x18000fbc8`
- name: `?_OnMediaSharingPrivacyLink@CShareMediaCore@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b78c`

## callees

- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x18000fae8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fb76`
- `KERNEL32!GetLastError` at `0x18000fb76`
- `SHELL32!ShellExecuteExW` at `0x18000fb68`
- `SHELL32!ShellExecuteExW` at `0x18000fb68`

## string_xrefs

- `0x18000fb37`: `https://go.microsoft.com/fwlink/?linkid=838628`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::_OnMediaSharingPrivacyLink(CShareMediaCore *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-78h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.lpFile = L"https://go.microsoft.com/fwlink/?linkid=838628";
  pExecInfo.fMask = 1024;
  pExecInfo.lpVerb = L"open";
  pExecInfo.nShow = 1;
  if ( ShellExecuteExW(&pExecInfo) )
  {
    v1 = 0;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18000fae8  mov     [rsp+arg_0], rbx
0x18000faed  push    rdi
0x18000faee  sub     rsp, 90h
0x18000faf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fafc  lea     rdi, WPP_GLOBAL_Control
0x18000fb03  cmp     rcx, rdi
0x18000fb06  jz      short loc_18000FB23
0x18000fb08  test    byte ptr [rcx+1Ch], 20h
0x18000fb0c  jz      short loc_18000FB23
0x18000fb0e  mov     rcx, [rcx+10h]
0x18000fb12  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fb19  mov     edx, 3Eh ; '>'
0x18000fb1e  call    WPP_SF_
0x18000fb23  mov     ebx, 70h ; 'p'
0x18000fb28  lea     rcx, [rsp+98h+pExecInfo]; void *
0x18000fb2d  mov     r8d, ebx; Size
0x18000fb30  xor     edx, edx; Val
0x18000fb32  call    memset_0
0x18000fb37  lea     rax, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?linkid"...
0x18000fb3e  mov     [rsp+98h+pExecInfo.cbSize], ebx
0x18000fb42  mov     [rsp+98h+pExecInfo.lpFile], rax
0x18000fb47  lea     rcx, [rsp+98h+pExecInfo]; pExecInfo
0x18000fb4c  lea     rax, aOpen; "open"
0x18000fb53  mov     [rsp+98h+pExecInfo.fMask], 400h
0x18000fb5b  mov     [rsp+98h+pExecInfo.lpVerb], rax
0x18000fb60  mov     [rsp+98h+pExecInfo.nShow], 1
0x18000fb68  call    cs:__imp_ShellExecuteExW
0x18000fb6e  test    eax, eax
0x18000fb70  jz      short loc_18000FB76
0x18000fb72  xor     ebx, ebx
0x18000fb74  jmp     short loc_18000FB8B
0x18000fb76  call    cs:__imp_GetLastError
0x18000fb7c  mov     ebx, eax
0x18000fb7e  test    eax, eax
0x18000fb80  jle     short loc_18000FB8B
0x18000fb82  movzx   ebx, ax
0x18000fb85  or      ebx, 80070000h
0x18000fb8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb92  cmp     rcx, rdi
0x18000fb95  jz      short loc_18000FBB5
0x18000fb97  test    byte ptr [rcx+1Ch], 20h
0x18000fb9b  jz      short loc_18000FBB5
0x18000fb9d  mov     rcx, [rcx+10h]
0x18000fba1  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000fba8  mov     edx, 3Fh ; '?'
0x18000fbad  mov     r9d, ebx
0x18000fbb0  call    WPP_SF_d
0x18000fbb5  mov     eax, ebx
0x18000fbb7  mov     rbx, [rsp+98h+arg_0]
0x18000fbbf  add     rsp, 90h
0x18000fbc6  pop     rdi
0x18000fbc7  retn
```
