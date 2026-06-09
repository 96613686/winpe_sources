# USDeleteFileEx

- ea: `0x180061ef0`
- end: `0x180062194`
- name: `USDeleteFileEx`
- size: `676`
- prototype: `signed int __fastcall(unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015a70`
- `0x1800160b0`
- `0x18001635c`
- `0x1800180cc`
- `0x1800687f0`

## callees

- `0x18002995c`
- `0x1800396c8`
- `0x180039898`
- `0x18005b3e0`
- `0x18005db48`
- `0x180061ef0`
- `0x180072260`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062050`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18006216e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18006216e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800620ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800620ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061f22`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061fbf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180062069`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061f22`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180061fbf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180062069`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180061fd0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180061fd0`

## pseudocode

```c
signed int __fastcall USDeleteFileEx(unsigned __int16 *a1)
{
  signed int result; // eax
  signed int LastError; // eax
  __int64 v4; // r8
  int v5; // ebx
  signed int v6; // eax
  void *v7; // rax
  signed int v8; // eax
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // r11
  unsigned __int64 v13; // r9
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+270h] [rbp+170h] BYREF

  if ( DeleteFileW(a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( (unsigned int)(result + 2147024894) <= 1 )
    return 0;
  if ( result == -2147024864 )
  {
    LODWORD(v14) = 0;
    v16[0] = CreateFileW(a1, 0, 3u, 0, 3u, 0x4000000u, 0);
    if ( v16[0] == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v14) = v5;
    }
    else
    {
      v5 = v14;
    }
    if ( (unsigned int)(v5 + 2147024894) <= 1 )
    {
      v5 = 0;
      goto LABEL_41;
    }
    if ( v5 < 0 )
    {
      v9 = 560;
LABEL_28:
      v10 = (unsigned int)v5;
LABEL_31:
      Log_UnistoreHREvent_18(v10, 1, v4, v9);
LABEL_41:
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v16);
      return v5;
    }
    v15 = 0;
    v11 = StringCchLengthW(a1, 0x104u, &v15);
    v5 = v11;
    if ( v11 < 0 )
    {
      v9 = 566;
    }
    else
    {
      v13 = v15;
      do
      {
        if ( v13 <= 1 )
          break;
        --v13;
      }
      while ( a1[v13] != 92 );
      v11 = StringCchCopyNW(PathName, v12, a1, v13);
      v5 = v11;
      if ( v11 >= 0 )
      {
        if ( GetTempFileNameW(PathName, L"OLD", 0, FileName) )
          goto LABEL_13;
        v6 = GetLastError();
        v5 = v6;
        if ( v6 > 0 )
          v5 = (unsigned __int16)v6 | 0x80070000;
        LODWORD(v14) = v5;
        if ( v5 >= 0 )
        {
LABEL_13:
          DeleteFileW(FileName);
          if ( !MoveFileExW(a1, FileName, 1u) )
          {
            v8 = GetLastError();
            if ( v8 > 0 )
              v8 = (unsigned __int16)v8 | 0x80070000;
            LODWORD(v14) = v8;
            DeleteFileW(FileName);
          }
          v5 = v14;
          if ( ((int)v14 <= -2147024895 || (unsigned int)(v14 + 2147024892) <= 0x7FF8FFFB)
            && (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
          {
            v7 = _t_address();
            EtwTraceMessage(&ETWMESSAGE, v7, a1, -2, &v14, 4, 0, -1);
            v5 = v14;
          }
          goto LABEL_41;
        }
        v9 = 584;
        goto LABEL_28;
      }
      v9 = 578;
    }
    v10 = (unsigned int)v11;
    goto LABEL_31;
  }
  return result;
}

```

## disassembly

```asm
0x180061ef0  mov     [rsp-8+arg_8], rbx
0x180061ef5  mov     [rsp-8+arg_10], rdi
0x180061efa  push    rbp
0x180061efb  push    r14
0x180061efd  push    r15
0x180061eff  lea     rbp, [rsp-390h]
0x180061f07  sub     rsp, 490h
0x180061f0e  mov     rax, cs:__security_cookie
0x180061f15  xor     rax, rsp
0x180061f18  mov     [rbp+3A0h+var_20], rax
0x180061f1f  mov     rdi, rcx
0x180061f22  call    cs:__imp_DeleteFileW
0x180061f28  test    eax, eax
0x180061f2a  jnz     short loc_180061F57
0x180061f2c  call    cs:__imp_GetLastError
0x180061f32  mov     r15d, 80070000h
0x180061f38  test    eax, eax
0x180061f3a  jle     short loc_180061F42
0x180061f3c  movzx   eax, ax
0x180061f3f  or      eax, r15d
0x180061f42  lea     ecx, [rax+7FF8FFFEh]
0x180061f48  mov     r14d, 1
0x180061f4e  cmp     ecx, r14d
0x180061f51  ja      loc_180062074
0x180061f57  xor     eax, eax
0x180061f59  mov     rcx, [rbp+3A0h+var_20]
0x180061f60  xor     rcx, rsp; StackCookie
0x180061f63  call    __security_check_cookie
0x180061f68  lea     r11, [rsp+4A0h+var_10]
0x180061f70  mov     rbx, [r11+28h]
0x180061f74  mov     rdi, [r11+30h]
0x180061f78  mov     rsp, r11
0x180061f7b  pop     r15
0x180061f7d  pop     r14
0x180061f7f  pop     rbp
0x180061f80  retn
0x180061f81  call    cs:__imp_GetLastError
0x180061f87  mov     ebx, eax
0x180061f89  test    eax, eax
0x180061f8b  jle     short loc_180061F93
0x180061f8d  movzx   ebx, ax
0x180061f90  or      ebx, r15d
0x180061f93  mov     dword ptr [rsp+4A0h+var_460], ebx
0x180061f97  jmp     loc_1800620C4
0x180061f9c  call    cs:__imp_GetLastError
0x180061fa2  mov     ebx, eax
0x180061fa4  test    eax, eax
0x180061fa6  jle     short loc_180061FAE
0x180061fa8  movzx   ebx, ax
0x180061fab  or      ebx, r15d
0x180061fae  mov     dword ptr [rsp+4A0h+var_460], ebx
0x180061fb2  test    ebx, ebx
0x180061fb4  js      loc_1800620DF
0x180061fba  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180061fbf  call    cs:__imp_DeleteFileW
0x180061fc5  mov     r8d, r14d; dwFlags
0x180061fc8  lea     rdx, [rsp+4A0h+FileName]; lpNewFileName
0x180061fcd  mov     rcx, rdi; lpExistingFileName
0x180061fd0  call    cs:__imp_MoveFileExW
0x180061fd6  test    eax, eax
0x180061fd8  jz      short loc_180062050
0x180061fda  mov     ebx, dword ptr [rsp+4A0h+var_460]
0x180061fde  cmp     ebx, 80070001h
0x180061fe4  jle     short loc_180061FF7
0x180061fe6  lea     eax, [rbx+7FF8FFFCh]
0x180061fec  cmp     eax, 7FF8FFFBh
0x180061ff1  ja      loc_180062183
0x180061ff7  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x180061ffe  jz      loc_180062183
0x180062004  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180062009  mov     [rsp+4A0h+var_468], 0FFFFFFFFFFFFFFFFh
0x180062012  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180062019  mov     rdx, rax; void *
0x18006201c  mov     [rsp+4A0h+hTemplateFile], 0
0x180062025  lea     rax, [rsp+4A0h+var_460]
0x18006202a  mov     qword ptr [rsp+4A0h+dwFlagsAndAttributes], 4
0x180062033  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18006203a  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x18006203f  mov     r8, rdi
0x180062042  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180062047  mov     ebx, dword ptr [rsp+4A0h+var_460]
0x18006204b  jmp     loc_180062183
0x180062050  call    cs:__imp_GetLastError
0x180062056  test    eax, eax
0x180062058  jle     short loc_180062060
0x18006205a  movzx   eax, ax
0x18006205d  or      eax, r15d
0x180062060  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180062065  mov     dword ptr [rsp+4A0h+var_460], eax
0x180062069  call    cs:__imp_DeleteFileW
0x18006206f  jmp     loc_180061FDA
0x180062074  cmp     eax, 80070020h
0x180062079  jnz     loc_180061F59
0x18006207f  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180062088  mov     r8d, 3; dwShareMode
0x18006208e  mov     [rsp+4A0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180062096  xor     r9d, r9d; lpSecurityAttributes
0x180062099  xor     edx, edx; dwDesiredAccess
0x18006209b  mov     [rsp+4A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800620a0  mov     rcx, rdi; lpFileName
0x1800620a3  mov     dword ptr [rsp+4A0h+var_460], 0
0x1800620ab  call    cs:__imp_CreateFileW
0x1800620b1  mov     [rsp+4A0h+var_450], rax
0x1800620b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800620ba  jz      loc_180061F81
0x1800620c0  mov     ebx, dword ptr [rsp+4A0h+var_460]
0x1800620c4  lea     eax, [rbx+7FF8FFFEh]
0x1800620ca  cmp     eax, r14d
0x1800620cd  jbe     loc_180062181
0x1800620d3  test    ebx, ebx
0x1800620d5  jns     short loc_1800620FE
0x1800620d7  mov     r9d, 230h
0x1800620dd  jmp     short loc_1800620E5
0x1800620df  mov     r9d, 248h
0x1800620e5  mov     ecx, ebx
0x1800620e7  jmp     short loc_1800620F1
0x1800620e9  mov     r9d, 236h
0x1800620ef  mov     ecx, eax
0x1800620f1  mov     edx, r14d
0x1800620f4  call    Log_UnistoreHREvent_18
0x1800620f9  jmp     loc_180062183
0x1800620fe  mov     r11d, 104h
0x180062104  mov     [rsp+4A0h+var_458], 0
0x18006210d  mov     edx, r11d; unsigned __int64
0x180062110  lea     r8, [rsp+4A0h+var_458]; unsigned __int64 *
0x180062115  mov     rcx, rdi; unsigned __int16 *
0x180062118  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006211d  mov     ebx, eax
0x18006211f  test    eax, eax
0x180062121  js      short loc_1800620E9
0x180062123  mov     r9, [rsp+4A0h+var_458]
0x180062128  cmp     r9, r14
0x18006212b  jbe     short loc_180062138
0x18006212d  sub     r9, r14; unsigned __int64
0x180062130  cmp     word ptr [rdi+r9*2], 5Ch ; '\'
0x180062136  jnz     short loc_180062128
0x180062138  mov     r8, rdi; unsigned __int16 *
0x18006213b  lea     rcx, [rbp+3A0h+PathName]; unsigned __int16 *
0x180062142  mov     rdx, r11; unsigned __int64
0x180062145  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18006214a  mov     ebx, eax
0x18006214c  test    eax, eax
0x18006214e  jns     short loc_180062158
0x180062150  mov     r9d, 242h
0x180062156  jmp     short loc_1800620EF
0x180062158  lea     r9, [rsp+4A0h+FileName]; lpTempFileName
0x18006215d  xor     r8d, r8d; uUnique
0x180062160  lea     rdx, PrefixString; "OLD"
0x180062167  lea     rcx, [rbp+3A0h+PathName]; lpPathName
0x18006216e  call    cs:__imp_GetTempFileNameW
0x180062174  test    eax, eax
0x180062176  jnz     loc_180061FBA
0x18006217c  jmp     loc_180061F9C
0x180062181  xor     ebx, ebx
0x180062183  lea     rcx, [rsp+4A0h+var_450]
0x180062188  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18006218d  mov     eax, ebx
0x18006218f  jmp     loc_180061F59
```
