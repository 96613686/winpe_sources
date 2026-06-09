# WinStationVirtualOpen

- ea: `0x180028920`
- end: `0x1800289b3`
- name: `WinStationVirtualOpen`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004554`
- `0x180007890`
- `0x1800119d4`
- `0x180028920`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028971`

## pseudocode

```c
char *__fastcall WinStationVirtualOpen(void *a1, ULONG SessionId, __int64 *a3, DWORD a4)
{
  __int64 v4; // rax
  unsigned int v5; // r8d
  __int64 v6; // rbx
  char *v8; // [rsp+20h] [rbp-38h]
  int v9; // [rsp+28h] [rbp-30h]
  char String1[8]; // [rsp+40h] [rbp-18h] BYREF

  v4 = *a3;
  v5 = 0;
  *(_QWORD *)String1 = v4;
  v6 = 0;
  String1[7] = 0;
  if ( !(_BYTE)v4 )
    goto LABEL_5;
  if ( SessionId != -1 )
    return CreateVirtualChannel(a1, String1, SessionId, a4, v8, v9, v5);
  if ( (unsigned int)IsLocalServer(a1) )
  {
    SessionId = NtCurrentPeb()->SessionId;
    return CreateVirtualChannel(a1, String1, SessionId, a4, v8, v9, v5);
  }
  _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
LABEL_5:
  SetLastError(0x57u);
  return (char *)v6;
}

```

## disassembly

```asm
0x180028920  push    rbx
0x180028922  sub     rsp, 50h
0x180028926  mov     rax, cs:__security_cookie
0x18002892d  xor     rax, rsp
0x180028930  mov     [rsp+58h+var_10], rax
0x180028935  mov     rax, [r8]
0x180028938  xor     r8d, r8d
0x18002893b  mov     qword ptr [rsp+58h+String1], rax
0x180028940  mov     ebx, r8d
0x180028943  mov     [rsp+58h+String1+7], r8b
0x180028948  cmp     [rsp+58h+String1], r8b
0x18002894d  jz      short loc_18002896C
0x18002894f  cmp     edx, 0FFFFFFFFh
0x180028952  jnz     short loc_18002899C
0x180028954  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180028959  test    eax, eax
0x18002895b  jnz     short loc_18002898D
0x18002895d  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180028964  lea     ecx, [rax+4]; int
0x180028967  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002896c  mov     ecx, 57h ; 'W'; dwErrCode
0x180028971  call    cs:__imp_SetLastError
0x180028977  mov     rax, rbx
0x18002897a  mov     rcx, [rsp+58h+var_10]
0x18002897f  xor     rcx, rsp; StackCookie
0x180028982  call    __security_check_cookie
0x180028987  add     rsp, 50h
0x18002898b  pop     rbx
0x18002898c  retn
0x18002898d  mov     rax, gs:60h
0x180028996  mov     edx, [rax+2C0h]
0x18002899c  mov     [rsp+58h+var_28], r8d; unsigned int
0x1800289a1  mov     r8d, edx; unsigned int
0x1800289a4  lea     rdx, [rsp+58h+String1]; String1
0x1800289a9  call    ?CreateVirtualChannel@@YAPEAXPEAXPEBDKHPEADGK@Z; CreateVirtualChannel(void *,char const *,ulong,int,char *,ushort,ulong)
0x1800289ae  mov     rbx, rax
0x1800289b1  jmp     short loc_180028977
```
