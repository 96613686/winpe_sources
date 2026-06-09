# EvtIntSysprepCleanup(void)

- ea: `0x1800266f0`
- end: `0x18002677d`
- name: `?EvtIntSysprepCleanup@@YAKXZ`
- size: `141`
- prototype: `unsigned int(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800266f0`
- `0x18002683c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002676a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002676a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026722`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026722`

## string_xrefs

- `0x180026747`: `Security`

## pseudocode

```c
__int64 EvtIntSysprepCleanup(void)
{
  int v0; // edi
  DWORD v1; // ebx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  while ( 1 )
  {
    dwErrCode = 0;
    SysPrepSingleLog(L"System", &dwErrCode);
    v1 = dwErrCode;
    if ( !dwErrCode )
      break;
    Sleep(0x2710u);
    if ( (unsigned int)++v0 >= 0xC )
      goto LABEL_6;
  }
  SysPrepSingleLog(L"Application", &dwErrCode);
  SysPrepSingleLog(L"Security", &dwErrCode);
  SysPrepSingleLog(L"Setup", &dwErrCode);
  v1 = dwErrCode;
LABEL_6:
  SetLastError(v1);
  return v1;
}

```

## disassembly

```asm
0x1800266f0  mov     [rsp+arg_8], rbx
0x1800266f5  push    rdi
0x1800266f6  sub     rsp, 20h
0x1800266fa  xor     edi, edi
0x1800266fc  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x180026701  mov     [rsp+28h+dwErrCode], 0
0x180026709  lea     rcx, ChannelPath; "System"
0x180026710  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x180026715  mov     ebx, [rsp+28h+dwErrCode]
0x180026719  test    ebx, ebx
0x18002671b  jz      short loc_180026731
0x18002671d  mov     ecx, 2710h; dwMilliseconds
0x180026722  call    cs:__imp_Sleep
0x180026728  inc     edi
0x18002672a  cmp     edi, 0Ch
0x18002672d  jb      short loc_1800266FC
0x18002672f  jmp     short loc_180026768
0x180026731  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x180026736  lea     rcx, aApplication; "Application"
0x18002673d  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x180026742  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x180026747  lea     rcx, aSecurity; "Security"
0x18002674e  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x180026753  lea     rdx, [rsp+28h+dwErrCode]; unsigned int *
0x180026758  lea     rcx, aSetup; "Setup"
0x18002675f  call    ?SysPrepSingleLog@@YAXPEB_WAEAK@Z; SysPrepSingleLog(wchar_t const *,ulong &)
0x180026764  mov     ebx, [rsp+28h+dwErrCode]
0x180026768  mov     ecx, ebx; dwErrCode
0x18002676a  call    cs:__imp_SetLastError
0x180026770  mov     eax, ebx
0x180026772  mov     rbx, [rsp+28h+arg_8]
0x180026777  add     rsp, 20h
0x18002677b  pop     rdi
0x18002677c  retn
```
