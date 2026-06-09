# QueueServerInstallWorkItem

- ea: `0x18001078c`
- end: `0x180010864`
- name: `QueueServerInstallWorkItem`
- size: `216`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008d20`
- `0x18000a6b0`

## callees

- `0x18001078c`
- `0x1800136f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010844`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180010844`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001084c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001084c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800107ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010813`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010813`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800107c4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1800107c4`

## pseudocode

```c
_BOOL8 QueueServerInstallWorkItem()
{
  DWORD LastError; // ebx
  unsigned int i; // edi

  LastError = 0;
  if ( ServerInstallProcessingEnabled && !PnpSchedulerThreadId )
  {
    for ( i = 0; i <= 0xA; Sleep(1000 * i) )
    {
      if ( QueueUserWorkItem(ServerSchedulerThreadProc, 0, 0x10u) )
      {
        LastError = 0;
        goto LABEL_12;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
          i,
          LastError);
      ++i;
    }
    if ( LastError )
      goto LABEL_14;
LABEL_12:
    PnpSchedulerThreadId = -1;
    if ( ServerInstallList != &ServerInstallList )
      ResetEvent(PnpNoPendingInstallEvents);
  }
LABEL_14:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18001078c  mov     [rsp+arg_0], rbx
0x180010791  push    rdi
0x180010792  sub     rsp, 30h
0x180010796  xor     ebx, ebx
0x180010798  cmp     cs:ServerInstallProcessingEnabled, ebx
0x18001079e  jz      loc_18001084A
0x1800107a4  cmp     cs:PnpSchedulerThreadId, ebx
0x1800107aa  jnz     loc_18001084A
0x1800107b0  xor     edi, edi
0x1800107b2  cmp     edi, 0Ah
0x1800107b5  ja      short loc_18001081F
0x1800107b7  xor     edx, edx; Context
0x1800107b9  lea     rcx, ServerSchedulerThreadProc; Function
0x1800107c0  lea     r8d, [rdx+10h]; Flags
0x1800107c4  call    cs:__imp_QueueUserWorkItem
0x1800107ca  test    eax, eax
0x1800107cc  jnz     short loc_18001081B
0x1800107ce  call    cs:__imp_GetLastError
0x1800107d4  mov     ebx, eax
0x1800107d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107dd  lea     rax, WPP_GLOBAL_Control
0x1800107e4  cmp     rcx, rax
0x1800107e7  jz      short loc_18001080B
0x1800107e9  test    byte ptr [rcx+1Ch], 1
0x1800107ed  jz      short loc_18001080B
0x1800107ef  mov     rcx, [rcx+10h]
0x1800107f3  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x1800107fa  mov     edx, 34h ; '4'
0x1800107ff  mov     [rsp+38h+var_18], ebx
0x180010803  mov     r9d, edi
0x180010806  call    WPP_SF_dd
0x18001080b  inc     edi
0x18001080d  imul    ecx, edi, 3E8h; dwMilliseconds
0x180010813  call    cs:__imp_Sleep
0x180010819  jmp     short loc_1800107B2
0x18001081b  xor     ebx, ebx
0x18001081d  jmp     short loc_180010823
0x18001081f  test    ebx, ebx
0x180010821  jnz     short loc_18001084A
0x180010823  lea     rax, ServerInstallList
0x18001082a  mov     cs:PnpSchedulerThreadId, 0FFFFFFFFh
0x180010834  cmp     cs:ServerInstallList, rax
0x18001083b  jz      short loc_18001084A
0x18001083d  mov     rcx, cs:PnpNoPendingInstallEvents; hEvent
0x180010844  call    cs:__imp_ResetEvent
0x18001084a  mov     ecx, ebx; dwErrCode
0x18001084c  call    cs:__imp_SetLastError
0x180010852  xor     eax, eax
0x180010854  test    ebx, ebx
0x180010856  mov     rbx, [rsp+38h+arg_0]
0x18001085b  setz    al
0x18001085e  add     rsp, 30h
0x180010862  pop     rdi
0x180010863  retn
```
