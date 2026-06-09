# CErcLuaDownloadAndInstall::DownloadAndInstallUpdates(HWND__ *,ushort *)

- ea: `0x180003868`
- end: `0x1800039ac`
- name: `?DownloadAndInstallUpdates@CErcLuaDownloadAndInstall@@QEAAJPEAUHWND__@@PEAG@Z`
- size: `324`
- prototype: `__int64 __fastcall(CErcLuaDownloadAndInstall *__hidden this, HWND, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800039c0`

## callees

- `0x180003868`
- `0x180006c9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800038cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800038cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800038e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800038e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000394f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000394f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003947`

## pseudocode

```c
__int64 __fastcall CErcLuaDownloadAndInstall::DownloadAndInstallUpdates(
        CErcLuaDownloadAndInstall *this,
        HWND a2,
        unsigned __int16 *a3)
{
  signed int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  char *Thread; // rbx
  signed int v7; // eax
  signed int LastError; // eax

  if ( a3 )
  {
    *(_QWORD *)this = a2;
    *((_QWORD *)this + 1) = a3;
    Thread = (char *)CreateThread(0, 0, CErcLuaDownloadAndInstall::static_DownloadAndInstallThread, this, 0, 0);
    if ( Thread == (char *)-1LL || Thread + 1 == (char *)1 )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2147467259;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 25;
        goto LABEL_23;
      }
    }
    else
    {
      if ( WaitForSingleObject(Thread, 0xFFFFFFFF) == -1 )
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids,
            (unsigned int)v3);
      }
      else
      {
        v3 = 0;
      }
      CloseHandle(Thread);
    }
  }
  else
  {
    v3 = -2147024809;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 24;
LABEL_23:
      WPP_SF_d(v4[2], v5, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003868  mov     [rsp+arg_0], rbx
0x18000386d  push    rdi
0x18000386e  sub     rsp, 30h
0x180003872  test    r8, r8
0x180003875  jnz     short loc_1800038A6
0x180003877  mov     edi, 80070057h
0x18000387c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003883  lea     rax, WPP_GLOBAL_Control
0x18000388a  cmp     rcx, rax
0x18000388d  jz      loc_18000399F
0x180003893  test    byte ptr [rcx+1Ch], 1
0x180003897  jz      loc_18000399F
0x18000389d  lea     edx, [r8+18h]
0x1800038a1  jmp     loc_18000398C
0x1800038a6  mov     [rcx], rdx
0x1800038a9  mov     r9, rcx; lpParameter
0x1800038ac  mov     [rcx+8], r8
0x1800038b0  xor     edx, edx; dwStackSize
0x1800038b2  lea     r8, ?static_DownloadAndInstallThread@CErcLuaDownloadAndInstall@@CAKPEAX@Z; lpStartAddress
0x1800038b9  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800038c2  xor     ecx, ecx; lpThreadAttributes
0x1800038c4  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800038cc  call    cs:__imp_CreateThread
0x1800038d2  mov     rbx, rax
0x1800038d5  inc     rax
0x1800038d8  cmp     rax, 1
0x1800038dc  jbe     short loc_18000394F
0x1800038de  or      edi, 0FFFFFFFFh
0x1800038e1  mov     rcx, rbx; hHandle
0x1800038e4  mov     edx, edi; dwMilliseconds
0x1800038e6  call    cs:__imp_WaitForSingleObject
0x1800038ec  cmp     eax, edi
0x1800038ee  jnz     short loc_180003942
0x1800038f0  call    cs:__imp_GetLastError
0x1800038f6  mov     edi, eax
0x1800038f8  test    eax, eax
0x1800038fa  jle     short loc_180003905
0x1800038fc  movzx   edi, ax
0x1800038ff  or      edi, 80070000h
0x180003905  test    edi, edi
0x180003907  mov     eax, 80004005h
0x18000390c  cmovns  edi, eax
0x18000390f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003916  lea     rax, WPP_GLOBAL_Control
0x18000391d  cmp     rcx, rax
0x180003920  jz      short loc_180003944
0x180003922  test    byte ptr [rcx+1Ch], 1
0x180003926  jz      short loc_180003944
0x180003928  mov     rcx, [rcx+10h]
0x18000392c  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003933  mov     edx, 1Ah
0x180003938  mov     r9d, edi
0x18000393b  call    WPP_SF_d
0x180003940  jmp     short loc_180003944
0x180003942  xor     edi, edi
0x180003944  mov     rcx, rbx; hObject
0x180003947  call    cs:__imp_CloseHandle
0x18000394d  jmp     short loc_18000399F
0x18000394f  call    cs:__imp_GetLastError
0x180003955  mov     edi, eax
0x180003957  test    eax, eax
0x180003959  jle     short loc_180003964
0x18000395b  movzx   edi, ax
0x18000395e  or      edi, 80070000h
0x180003964  test    edi, edi
0x180003966  mov     eax, 80004005h
0x18000396b  cmovns  edi, eax
0x18000396e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003975  lea     rax, WPP_GLOBAL_Control
0x18000397c  cmp     rcx, rax
0x18000397f  jz      short loc_18000399F
0x180003981  test    byte ptr [rcx+1Ch], 1
0x180003985  jz      short loc_18000399F
0x180003987  mov     edx, 19h
0x18000398c  mov     rcx, [rcx+10h]
0x180003990  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003997  mov     r9d, edi
0x18000399a  call    WPP_SF_d
0x18000399f  mov     rbx, [rsp+38h+arg_0]
0x1800039a4  mov     eax, edi
0x1800039a6  add     rsp, 30h
0x1800039aa  pop     rdi
0x1800039ab  retn
```
