# UpdateFileLogConfig

- ea: `0x18000ca10`
- end: `0x18000ce1d`
- name: `UpdateFileLogConfig`
- size: `1037`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000c28c`
- `0x18000c7d0`
- `0x180032ff0`
- `0x18004d490`

## callees

- `0x18000ca10`
- `0x18000ce30`
- `0x180018138`
- `0x18001a780`
- `0x18004e688`
- `0x18004e854`
- `0x18004ecd0`
- `0x18004ed38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000ca3d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000cb39`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000ca3d`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18000cb39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cb7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cbb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cdfb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc28`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000cd65`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000cd65`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cd39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cd39`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ca79`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ca79`
- `ntdll!RtlReleaseResource` at `0x18000cbdf`
- `ntdll!RtlReleaseResource` at `0x18000cbdf`

## string_xrefs

- `0x18000cdac`: `---------- Log File Opened -----------------\n`

## pseudocode

```c
__int64 UpdateFileLogConfig()
{
  signed int v0; // esi
  void *v1; // r14
  int v2; // edi
  _DWORD *v3; // rbx
  HLOCAL v4; // rcx
  HLOCAL *v5; // rcx
  _QWORD *v6; // rcx
  _WORD *v7; // rdx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  signed int LastError; // eax
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // r9d
  int v18; // r8d
  LPCWSTR *v19; // rcx
  HANDLE FileW; // rax
  _QWORD *v21; // rcx
  unsigned __int64 v22; // r8
  HLOCAL hMem; // [rsp+B0h] [rbp+8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+B8h] [rbp+10h] BYREF
  HLOCAL v25; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+20h]

  v0 = 0;
  v1 = 0;
  hMem = 0;
  v25 = 0;
  v26 = _set_se_translator(SeTransFunc);
  v2 = ReadFileLogConfig(&hMem);
  if ( v2 < 0 )
  {
    v3 = hMem;
  }
  else
  {
    if ( RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      v3 = hMem;
      v4 = _pflstate;
      *(_DWORD *)_pflstate = *(_DWORD *)hMem;
      *((_DWORD *)v4 + 14) = v3[8];
      *((_QWORD *)v4 + 1) = (unsigned int)v3[1];
      *((_DWORD *)v4 + 15) = v3[9];
      if ( *((_QWORD *)v4 + 2) )
      {
        LocalFree(*((HLOCAL *)v4 + 2));
        v4 = _pflstate;
      }
      *((_QWORD *)v4 + 2) = *((_QWORD *)v3 + 2);
      *((_QWORD *)v3 + 2) = 0;
      v5 = (HLOCAL *)_pflstate;
      *((_DWORD *)_pflstate + 16) = v3[10];
      if ( v5[3] )
      {
        FreeLogEntryRangeChain(v5[3]);
        v5 = (HLOCAL *)_pflstate;
      }
      v5[3] = (HLOCAL)*((_QWORD *)v3 + 1);
      *((_QWORD *)v3 + 1) = 0;
      v6 = _pflstate;
      *((_DWORD *)_pflstate + 17) = v3[11];
      v7 = (_WORD *)*((_QWORD *)v3 + 3);
      if ( v7 && *v7 )
      {
        v15 = v6[4];
        if ( !v15 )
          goto LABEL_39;
        v16 = v15 - (_QWORD)v7;
        do
        {
          v17 = *(unsigned __int16 *)((char *)v7 + v16);
          v18 = (unsigned __int16)*v7 - v17;
          if ( v18 )
            break;
          ++v7;
        }
        while ( v17 );
        if ( v18 )
        {
LABEL_39:
          FileSize.QuadPart = 0;
          if ( v6[5] )
            FlushCloseFile();
          _InterlockedExchange(&_lLoggingEnabled, 0);
          v19 = (LPCWSTR *)_pflstate;
          *((_QWORD *)_pflstate + 4) = *((_QWORD *)v3 + 3);
          *((_QWORD *)v3 + 3) = 0;
          FileW = CreateFileW(v19[4], 0x40000000u, 1u, 0, 4u, 0x8000080u, 0);
          *((_QWORD *)_pflstate + 5) = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            v0 = LastError;
            if ( LastError > 0 )
              v0 = (unsigned __int16)LastError | 0x80070000;
            v13 = _pflstate;
            *((_QWORD *)_pflstate + 5) = 0;
            v1 = (void *)v13[4];
            v13[4] = 0;
            EmptyAllBuffers();
          }
          else
          {
            if ( !GetFileSizeEx(FileW, &FileSize) )
            {
              v14 = GetLastError();
              if ( v14 > 0 )
                v14 = (unsigned __int16)v14 | 0x80070000;
              AbortCloseFile(v14);
              v2 = 0;
LABEL_12:
              _set_se_translator(v26);
LABEL_25:
              RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
              goto LABEL_13;
            }
            _InterlockedExchange(&_lLoggingEnabled, 1);
            v21 = _pflstate;
            *((union _LARGE_INTEGER *)_pflstate + 6) = FileSize;
            v22 = v21[1];
            if ( v22 )
              v21[6] = FileSize.QuadPart % v22;
            FileLogAdd(L"---------- Log File Opened -----------------\n");
          }
        }
      }
      else
      {
        if ( v6[5] )
          FlushCloseFile();
        _InterlockedExchange(&_lLoggingEnabled, 0);
      }
      v2 = 0;
      if ( v0 < 0 )
      {
        LocalFree(v1);
        if ( (int)GetSystemErrorString(v0, (unsigned __int16 **)&v25) < 0 )
          goto LABEL_25;
      }
      goto LABEL_12;
    }
    v2 = -2147023537;
    v3 = hMem;
  }
LABEL_13:
  if ( v3 )
  {
    v8 = (void *)*((_QWORD *)v3 + 1);
    if ( v8 )
      FreeLogEntryRangeChain(v8);
    v9 = (void *)*((_QWORD *)v3 + 3);
    if ( v9 )
      LocalFree(v9);
    v10 = (void *)*((_QWORD *)v3 + 2);
    if ( v10 )
      LocalFree(v10);
    LocalFree(v3);
  }
  if ( v25 )
    LocalFree(v25);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ca10  mov     rax, rsp
0x18000ca13  push    rbx
0x18000ca14  push    rsi
0x18000ca15  push    rdi
0x18000ca16  push    r14
0x18000ca18  push    r15
0x18000ca1a  sub     rsp, 80h
0x18000ca21  mov     byte ptr [rax-68h], 0
0x18000ca25  xor     r15d, r15d
0x18000ca28  mov     esi, r15d
0x18000ca2b  mov     r14d, r15d
0x18000ca2e  mov     [rax+8], r15
0x18000ca32  mov     [rax+18h], r15
0x18000ca36  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18000ca3d  call    cs:__imp__set_se_translator
0x18000ca44  nop     dword ptr [rax+rax+00h]
0x18000ca49  mov     [rsp+0A8h+arg_18], rax
0x18000ca51  lea     rcx, [rsp+0A8h+hMem]
0x18000ca59  call    ReadFileLogConfig
0x18000ca5e  mov     edi, eax
0x18000ca60  mov     [rsp+0A8h+var_64], eax
0x18000ca64  test    eax, eax
0x18000ca66  js      loc_18000CC54
0x18000ca6c  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000ca73  add     rcx, 50h ; 'P'; Resource
0x18000ca77  mov     dl, 1; Wait
0x18000ca79  call    cs:__imp_RtlAcquireResourceExclusive
0x18000ca80  nop     dword ptr [rax+rax+00h]
0x18000ca85  test    al, al
0x18000ca87  jz      loc_18000CC61
0x18000ca8d  mov     [rsp+0A8h+var_68], 1
0x18000ca92  mov     rbx, [rsp+0A8h+hMem]
0x18000ca9a  mov     eax, [rbx]
0x18000ca9c  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000caa3  mov     [rcx], eax
0x18000caa5  mov     eax, [rbx+20h]
0x18000caa8  mov     [rcx+38h], eax
0x18000caab  mov     eax, [rbx+4]
0x18000caae  mov     [rcx+8], rax
0x18000cab2  mov     eax, [rbx+24h]
0x18000cab5  mov     [rcx+3Ch], eax
0x18000cab8  mov     rax, [rcx+10h]
0x18000cabc  test    rax, rax
0x18000cabf  jnz     loc_18000CC77
0x18000cac5  mov     rax, [rbx+10h]
0x18000cac9  mov     [rcx+10h], rax
0x18000cacd  mov     [rbx+10h], r15
0x18000cad1  mov     eax, [rbx+28h]
0x18000cad4  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cadb  mov     [rcx+40h], eax
0x18000cade  mov     rax, [rcx+18h]
0x18000cae2  test    rax, rax
0x18000cae5  jnz     loc_18000CC92
0x18000caeb  mov     rax, [rbx+8]
0x18000caef  mov     [rcx+18h], rax
0x18000caf3  mov     [rbx+8], r15
0x18000caf7  mov     eax, [rbx+2Ch]
0x18000cafa  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cb01  mov     [rcx+44h], eax
0x18000cb04  mov     rdx, [rbx+18h]
0x18000cb08  test    rdx, rdx
0x18000cb0b  jnz     loc_18000CCA6
0x18000cb11  cmp     qword ptr [rcx+28h], 0
0x18000cb16  jnz     loc_18000CDBD
0x18000cb1c  mov     eax, r15d
0x18000cb1f  xchg    eax, cs:?_lLoggingEnabled@@3JC; long volatile _lLoggingEnabled
0x18000cb25  mov     edi, r15d
0x18000cb28  mov     [rsp+0A8h+var_64], r15d
0x18000cb2d  test    esi, esi
0x18000cb2f  js      short loc_18000CBAE
0x18000cb31  mov     rcx, [rsp+0A8h+arg_18]
0x18000cb39  call    cs:__imp__set_se_translator
0x18000cb40  nop     dword ptr [rax+rax+00h]
0x18000cb45  cmp     [rsp+0A8h+var_68], 0
0x18000cb4a  jnz     loc_18000CBD4
0x18000cb50  test    rbx, rbx
0x18000cb53  jz      short loc_18000CB8B
0x18000cb55  mov     rcx, [rbx+8]; hMem
0x18000cb59  test    rcx, rcx
0x18000cb5c  jnz     loc_18000CDE0
0x18000cb62  mov     rcx, [rbx+18h]; hMem
0x18000cb66  test    rcx, rcx
0x18000cb69  jnz     loc_18000CDEA
0x18000cb6f  mov     rcx, [rbx+10h]; hMem
0x18000cb73  test    rcx, rcx
0x18000cb76  jnz     loc_18000CDFB
0x18000cb7c  mov     rcx, rbx; hMem
0x18000cb7f  call    cs:__imp_LocalFree
0x18000cb86  nop     dword ptr [rax+rax+00h]
0x18000cb8b  mov     rcx, [rsp+0A8h+arg_10]; hMem
0x18000cb93  test    rcx, rcx
0x18000cb96  jnz     loc_18000CE0C
0x18000cb9c  mov     eax, edi
0x18000cb9e  add     rsp, 80h
0x18000cba5  pop     r15
0x18000cba7  pop     r14
0x18000cba9  pop     rdi
0x18000cbaa  pop     rsi
0x18000cbab  pop     rbx
0x18000cbac  retn
0x18000cbae  mov     rcx, r14; hMem
0x18000cbb1  call    cs:__imp_LocalFree
0x18000cbb8  nop     dword ptr [rax+rax+00h]
0x18000cbbd  lea     rdx, [rsp+0A8h+arg_10]; unsigned __int16 **
0x18000cbc5  mov     ecx, esi; dwMessageId
0x18000cbc7  call    ?GetSystemErrorString@@YAJJPEAPEAG@Z; GetSystemErrorString(long,ushort * *)
0x18000cbcc  test    eax, eax
0x18000cbce  jns     loc_18000CB31
0x18000cbd4  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cbdb  add     rcx, 50h ; 'P'; Resource
0x18000cbdf  call    cs:__imp_RtlReleaseResource
0x18000cbe6  nop     dword ptr [rax+rax+00h]
0x18000cbeb  jmp     loc_18000CB50
0x18000cbf0  call    cs:__imp_GetLastError
0x18000cbf7  nop     dword ptr [rax+rax+00h]
0x18000cbfc  mov     esi, eax
0x18000cbfe  test    eax, eax
0x18000cc00  jle     short loc_18000CC0B
0x18000cc02  movzx   esi, ax
0x18000cc05  or      esi, 80070000h
0x18000cc0b  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cc12  mov     [rax+28h], r15
0x18000cc16  mov     r14, [rax+20h]
0x18000cc1a  mov     [rax+20h], r15
0x18000cc1e  call    ?EmptyAllBuffers@@YAXXZ; EmptyAllBuffers(void)
0x18000cc23  jmp     loc_18000CB25
0x18000cc28  call    cs:__imp_GetLastError
0x18000cc2f  nop     dword ptr [rax+rax+00h]
0x18000cc34  test    eax, eax
0x18000cc36  jle     short loc_18000CC40
0x18000cc38  movzx   eax, ax
0x18000cc3b  or      eax, 80070000h
0x18000cc40  mov     ecx, eax; dwMessageId
0x18000cc42  call    ?AbortCloseFile@@YAXJ@Z; AbortCloseFile(long)
0x18000cc47  mov     edi, r15d
0x18000cc4a  mov     [rsp+0A8h+var_64], r15d
0x18000cc4f  jmp     loc_18000CB31
0x18000cc54  mov     rbx, [rsp+0A8h+hMem]
0x18000cc5c  jmp     loc_18000CB50
0x18000cc61  mov     edi, 8007054Fh
0x18000cc66  mov     [rsp+0A8h+var_64], edi
0x18000cc6a  mov     rbx, [rsp+0A8h+hMem]
0x18000cc72  jmp     loc_18000CB50
0x18000cc77  mov     rcx, rax; hMem
0x18000cc7a  call    cs:__imp_LocalFree
0x18000cc81  nop     dword ptr [rax+rax+00h]
0x18000cc86  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cc8d  jmp     loc_18000CAC5
0x18000cc92  mov     rcx, rax; hMem
0x18000cc95  call    ?FreeLogEntryRangeChain@@YAXPEAULogEntryRange@@@Z; FreeLogEntryRangeChain(LogEntryRange *)
0x18000cc9a  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cca1  jmp     loc_18000CAEB
0x18000cca6  cmp     r15w, [rdx]
0x18000ccaa  jz      loc_18000CB11
0x18000ccb0  mov     rax, [rcx+20h]
0x18000ccb4  test    rax, rax
0x18000ccb7  jz      short loc_18000CCDC
0x18000ccb9  sub     rax, rdx
0x18000ccbc  movzx   r8d, word ptr [rdx]
0x18000ccc0  movzx   r9d, word ptr [rdx+rax]
0x18000ccc5  sub     r8d, r9d
0x18000ccc8  jnz     short loc_18000CCD3
0x18000ccca  add     rdx, 2
0x18000ccce  test    r9d, r9d
0x18000ccd1  jnz     short loc_18000CCBC
0x18000ccd3  test    r8d, r8d
0x18000ccd6  jz      loc_18000CB25
0x18000ccdc  mov     qword ptr [rsp+0A8h+FileSize], r15
0x18000cce4  cmp     qword ptr [rcx+28h], 0
0x18000cce9  jz      short loc_18000CCF4
0x18000cceb  call    ?FlushCloseFile@@YAJXZ; FlushCloseFile(void)
0x18000ccf0  mov     [rsp+0A8h+var_64], eax
0x18000ccf4  mov     eax, r15d
0x18000ccf7  xchg    eax, cs:?_lLoggingEnabled@@3JC; long volatile _lLoggingEnabled
0x18000ccfd  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cd04  mov     rax, [rbx+18h]
0x18000cd08  mov     [rcx+20h], rax
0x18000cd0c  mov     [rbx+18h], r15
0x18000cd10  mov     [rsp+0A8h+hTemplateFile], r15; hTemplateFile
0x18000cd15  mov     [rsp+0A8h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18000cd1d  mov     [rsp+0A8h+dwCreationDisposition], 4; dwCreationDisposition
0x18000cd25  xor     r9d, r9d; lpSecurityAttributes
0x18000cd28  mov     edi, 1
0x18000cd2d  mov     r8d, edi; dwShareMode
0x18000cd30  mov     edx, 40000000h; dwDesiredAccess
0x18000cd35  mov     rcx, [rcx+20h]; lpFileName
0x18000cd39  call    cs:__imp_CreateFileW
0x18000cd40  nop     dword ptr [rax+rax+00h]
0x18000cd45  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cd4c  mov     [rcx+28h], rax
0x18000cd50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cd54  jz      loc_18000CBF0
0x18000cd5a  lea     rdx, [rsp+0A8h+FileSize]; lpFileSize
0x18000cd62  mov     rcx, rax; hFile
0x18000cd65  call    cs:__imp_GetFileSizeEx
0x18000cd6c  nop     dword ptr [rax+rax+00h]
0x18000cd71  test    eax, eax
0x18000cd73  jz      loc_18000CC28
0x18000cd79  xchg    edi, cs:?_lLoggingEnabled@@3JC; long volatile _lLoggingEnabled
0x18000cd7f  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18000cd86  mov     rax, qword ptr [rsp+0A8h+FileSize]
0x18000cd8e  mov     [rcx+30h], rax
0x18000cd92  mov     r8, [rcx+8]
0x18000cd96  test    r8, r8
0x18000cd99  jz      short loc_18000CDAC
0x18000cd9b  xor     edx, edx
0x18000cd9d  mov     rax, qword ptr [rsp+0A8h+FileSize]
0x18000cda5  div     r8
0x18000cda8  mov     [rcx+30h], rdx
0x18000cdac  lea     rcx, aLogFileOpened; "---------- Log File Opened ------------"...
0x18000cdb3  call    FileLogAdd
0x18000cdb8  jmp     loc_18000CB25
0x18000cdbd  call    ?FlushCloseFile@@YAJXZ; FlushCloseFile(void)
0x18000cdc2  mov     [rsp+0A8h+var_64], eax
0x18000cdc6  jmp     loc_18000CB1C
0x18000cdcb  jmp     short loc_18000CDCF
0x18000cdcd  jmp     short $+2
0x18000cdcf  mov     edi, [rsp+0A8h+var_64]
0x18000cdd3  mov     rbx, [rsp+0A8h+hMem]
0x18000cddb  jmp     loc_18000CB31
0x18000cde0  call    ?FreeLogEntryRangeChain@@YAXPEAULogEntryRange@@@Z; FreeLogEntryRangeChain(LogEntryRange *)
0x18000cde5  jmp     loc_18000CB62
0x18000cdea  call    cs:__imp_LocalFree
0x18000cdf1  nop     dword ptr [rax+rax+00h]
0x18000cdf6  jmp     loc_18000CB6F
0x18000cdfb  call    cs:__imp_LocalFree
0x18000ce02  nop     dword ptr [rax+rax+00h]
0x18000ce07  jmp     loc_18000CB7C
0x18000ce0c  call    cs:__imp_LocalFree
0x18000ce13  nop     dword ptr [rax+rax+00h]
0x18000ce18  jmp     loc_18000CB9C
```
