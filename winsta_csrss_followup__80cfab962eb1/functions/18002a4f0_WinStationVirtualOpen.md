# WinStationVirtualOpen

- ea: `0x18002a4f0`
- end: `0x18002a58a`
- name: `WinStationVirtualOpen`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005b40`
- `0x18000a784`
- `0x1800124ec`
- `0x18002a4f0`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a541`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a541`

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
0x18002a4f0  push    rbx
0x18002a4f2  sub     rsp, 50h
0x18002a4f6  mov     rax, cs:__security_cookie
0x18002a4fd  xor     rax, rsp
0x18002a500  mov     [rsp+58h+var_10], rax
0x18002a505  mov     rax, [r8]
0x18002a508  xor     r8d, r8d
0x18002a50b  mov     qword ptr [rsp+58h+String1], rax
0x18002a510  mov     ebx, r8d
0x18002a513  mov     [rsp+58h+String1+7], r8b
0x18002a518  cmp     [rsp+58h+String1], r8b
0x18002a51d  jz      short loc_18002A53C
0x18002a51f  cmp     edx, 0FFFFFFFFh
0x18002a522  jnz     short loc_18002A573
0x18002a524  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002a529  test    eax, eax
0x18002a52b  jnz     short loc_18002A564
0x18002a52d  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18002a534  lea     ecx, [rax+4]; int
0x18002a537  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a53c  mov     ecx, 57h ; 'W'; dwErrCode
0x18002a541  call    cs:__imp_SetLastError
0x18002a548  nop     dword ptr [rax+rax+00h]
0x18002a54d  mov     rax, rbx
0x18002a550  mov     rcx, [rsp+58h+var_10]
0x18002a555  xor     rcx, rsp; StackCookie
0x18002a558  call    __security_check_cookie
0x18002a55d  add     rsp, 50h
0x18002a561  pop     rbx
0x18002a562  retn
0x18002a564  mov     rax, gs:60h
0x18002a56d  mov     edx, [rax+2C0h]
0x18002a573  mov     [rsp+58h+var_28], r8d; unsigned int
0x18002a578  mov     r8d, edx; unsigned int
0x18002a57b  lea     rdx, [rsp+58h+String1]; String1
0x18002a580  call    ?CreateVirtualChannel@@YAPEAXPEAXPEBDKHPEADGK@Z; CreateVirtualChannel(void *,char const *,ulong,int,char *,ushort,ulong)
0x18002a585  mov     rbx, rax
0x18002a588  jmp     short loc_18002A54D
```
