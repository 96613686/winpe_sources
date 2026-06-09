# CallHistoryOperationContext::GetFilePropertyPath(UdmObjectId const &,ulong,UdmFileAccess,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,int *)

- ea: `0x1800df304`
- end: `0x1800df696`
- name: `?GetFilePropertyPath@CallHistoryOperationContext@@QEAAJAEBUUdmObjectId@@KW4UdmFileAccess@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAH@Z`
- size: `914`
- prototype: `__int64 __fastcall(CallHistoryOperationContext *this, struct UdmObjectId *, int, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800a5bb0`

## callees

- `0x180008f0c`
- `0x180012988`
- `0x1800303cc`
- `0x180030948`
- `0x18003307c`
- `0x180035c40`
- `0x18003e3e4`
- `0x1800a0728`
- `0x1800df304`
- `0x1800e18b4`
- `0x1800e2fcc`
- `0x1800e3650`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df43a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df43a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df664`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df5c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df5c6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800df4e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800df4e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800df5ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800df5ab`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800df552`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800df552`
- `unistore!GetUSDataFolderPath` at `0x1800df501`
- `unistore!GetUSDataFolderPath` at `0x1800df501`

## string_xrefs

- `0x1800df37b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df5e1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800df64b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall CallHistoryOperationContext::GetFilePropertyPath(
        CallHistoryOperationContext *this,
        struct UdmObjectId *a2,
        int a3,
        int a4,
        __int64 a5,
        _DWORD *a6)
{
  _WORD *v9; // rcx
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rdx
  struct ServiceDataSession *v13; // rcx
  struct CallHistoryDataSession *v14; // rbx
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  struct UdmPropertyValue **v16; // rax
  int FileStreamPath; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  struct CallHistoryDataSession *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD *v29; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v30[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v32[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszPath[264]; // [rsp+490h] [rbp+390h] BYREF

  LODWORD(v26) = a3;
  *a6 = 0;
  v9 = *(_WORD **)a5;
  *(_QWORD *)(a5 + 8) = *(_QWORD *)a5;
  *v9 = 0;
  if ( ((a3 - 2883590) & 0xFFFEFFFF) == 0 )
  {
    v27 = 0;
    v28 = 0;
    LODWORD(v25) = 0;
    v11 = CallHistoryOperationContext::ValidateCallerSecurityForId(
            this,
            a2,
            (enum ObjectAccess *)&v27,
            (enum ObjectAccess *)&v28,
            (int *)&v25);
    if ( (v11 & 0x80000000) != 0 )
    {
      v10 = 709;
      v12 = 1;
      goto LABEL_4;
    }
    if ( v27 != 2 )
    {
      v10 = 711;
      v11 = -2147024891;
      goto LABEL_3;
    }
    if ( a4 == 1 && ((unsigned int)(v28 - 1) <= 1 || (_DWORD)v25) )
      *a6 = 1;
    v13 = *(struct ServiceDataSession **)this;
    v30[0] = 2818049;
    v25 = 0;
    v11 = GetCallHistoryDataSession(v13, &v25);
    if ( (v11 & 0x80000000) != 0 )
    {
      v10 = 722;
      v12 = 1;
      goto LABEL_4;
    }
    v14 = v25;
    v15 = (struct _RTL_CRITICAL_SECTION *)((char *)v25 + 2064);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v25 + 2064));
    LODWORD(v25) = 0;
    v29 = 0;
    v16 = (struct UdmPropertyValue **)tlx::replace<_USRestriction,&void _LocalFreer<_USRestriction>(_USRestriction *)>(&v29);
    FileStreamPath = PropertyMapper_CallHistory(v14, a2, 1u, v30, (int *)&v25, v16);
    v11 = FileStreamPath;
    if ( FileStreamPath < 0 )
    {
      v18 = 734;
LABEL_17:
      v19 = 1;
      v20 = (unsigned int)FileStreamPath;
LABEL_45:
      Log_HREvent(
        v20,
        v19,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v18);
LABEL_46:
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v29);
      LeaveCriticalSection(v15);
      return v11;
    }
    if ( (_DWORD)v25 )
    {
      if ( (*v29 & 0x100) == 0 && v29[2] )
      {
        FileStreamPath = GetFileStreamPath(*((unsigned int *)a2 + 2), (unsigned int)v26, FileName);
        v11 = FileStreamPath;
        if ( FileStreamPath < 0 )
        {
          v18 = 745;
          goto LABEL_17;
        }
        if ( GetFileAttributesW(FileName) == -1 )
        {
          FileStreamPath = GetUSDataFolderPath(v32, 0x104u);
          v11 = FileStreamPath;
          if ( FileStreamPath < 0 )
          {
            v18 = 750;
            goto LABEL_17;
          }
          FileStreamPath = StringCchPrintfW(pszPath, 0x104u, L"%s\\CallHistory", v32);
          v11 = FileStreamPath;
          if ( FileStreamPath < 0 )
          {
            v18 = 753;
            goto LABEL_17;
          }
          v21 = SHCreateDirectoryExW(0, pszPath, 0);
          v11 = v21;
          if ( v21 != 183 && v21 != 80 && v21 )
          {
            if ( v21 > 0 )
              v11 = (unsigned __int16)v21 | 0x80070000;
            v18 = 761;
            goto LABEL_44;
          }
          v26 = 0;
          FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset(&v26, FileW);
          if ( v26 == -1 )
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            Log_HREvent(
              v11,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              771);
            tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v26);
            goto LABEL_46;
          }
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v26);
        }
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                a5,
                                FileName) )
        {
          auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v29);
          LeaveCriticalSection(v15);
          return 0;
        }
        v18 = 774;
        v11 = -2147024882;
        goto LABEL_44;
      }
      v18 = 741;
      v11 = -2147024809;
    }
    else
    {
      v18 = 736;
      v11 = -2147023728;
    }
LABEL_44:
    v19 = 0;
    v20 = v11;
    goto LABEL_45;
  }
  v10 = 699;
  v11 = -2147024809;
LABEL_3:
  v12 = 0;
LABEL_4:
  Log_HREvent(
    v11,
    v12,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
    v10);
  return v11;
}

```

## disassembly

```asm
0x1800df304  mov     [rsp-8+arg_18], rbx
0x1800df309  push    rbp
0x1800df30a  push    rsi
0x1800df30b  push    rdi
0x1800df30c  push    r12
0x1800df30e  push    r13
0x1800df310  push    r14
0x1800df312  push    r15
0x1800df314  lea     rbp, [rsp-5B0h]
0x1800df31c  sub     rsp, 6B0h
0x1800df323  mov     rax, cs:__security_cookie
0x1800df32a  xor     rax, rsp
0x1800df32d  mov     [rbp+5E0h+var_40], rax
0x1800df334  mov     r13, [rbp+5E0h+arg_20]
0x1800df33b  lea     eax, [r8-2C0006h]
0x1800df342  mov     r15, [rbp+5E0h+arg_28]
0x1800df349  xor     edi, edi
0x1800df34b  mov     dword ptr [rsp+6E0h+var_698], r8d
0x1800df350  mov     rsi, rcx
0x1800df353  mov     r12d, r9d
0x1800df356  mov     r14, rdx
0x1800df359  mov     [r15], edi
0x1800df35c  mov     rcx, [r13+0]
0x1800df360  mov     [r13+8], rcx
0x1800df364  mov     [rcx], di
0x1800df367  test    eax, 0FFFEFFFFh
0x1800df36c  jz      short loc_1800DF38E
0x1800df36e  mov     r9d, 2BBh
0x1800df374  mov     ebx, 80070057h
0x1800df379  xor     edx, edx
0x1800df37b  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df382  mov     ecx, ebx
0x1800df384  call    Log_HREvent
0x1800df389  jmp     loc_1800DF66A
0x1800df38e  lea     rax, [rsp+6E0h+var_6A0]
0x1800df393  mov     [rsp+6E0h+var_690], edi
0x1800df397  lea     r9, [rsp+6E0h+var_68C]; enum ObjectAccess *
0x1800df39c  mov     qword ptr [rsp+6E0h+dwCreationDisposition], rax; int *
0x1800df3a1  lea     r8, [rsp+6E0h+var_690]; enum ObjectAccess *
0x1800df3a6  mov     [rsp+6E0h+var_68C], edi
0x1800df3aa  mov     rcx, rsi; this
0x1800df3ad  mov     dword ptr [rsp+6E0h+var_6A0], edi
0x1800df3b1  call    ?ValidateCallerSecurityForId@CallHistoryOperationContext@@QEAAJAEBUUdmObjectId@@PEAW4ObjectAccess@@1PEAH@Z; CallHistoryOperationContext::ValidateCallerSecurityForId(UdmObjectId const &,ObjectAccess *,ObjectAccess *,int *)
0x1800df3b6  mov     ebx, eax
0x1800df3b8  test    eax, eax
0x1800df3ba  jns     short loc_1800DF3C9
0x1800df3bc  mov     r9d, 2C5h
0x1800df3c2  mov     edx, 1
0x1800df3c7  jmp     short loc_1800DF37B
0x1800df3c9  cmp     [rsp+6E0h+var_690], 2
0x1800df3ce  jz      short loc_1800DF3DD
0x1800df3d0  mov     r9d, 2C7h
0x1800df3d6  mov     ebx, 80070005h
0x1800df3db  jmp     short loc_1800DF379
0x1800df3dd  mov     edi, 1
0x1800df3e2  cmp     r12d, edi
0x1800df3e5  jnz     short loc_1800DF3FB
0x1800df3e7  mov     eax, [rsp+6E0h+var_68C]
0x1800df3eb  dec     eax
0x1800df3ed  cmp     eax, edi
0x1800df3ef  jbe     short loc_1800DF3F8
0x1800df3f1  cmp     dword ptr [rsp+6E0h+var_6A0], 0
0x1800df3f6  jz      short loc_1800DF3FB
0x1800df3f8  mov     [r15], edi
0x1800df3fb  mov     rcx, [rsi]; struct ServiceDataSession *
0x1800df3fe  lea     rdx, [rsp+6E0h+var_6A0]; struct CallHistoryDataSession **
0x1800df403  xor     r15d, r15d
0x1800df406  mov     [rsp+6E0h+var_680], 2B0001h
0x1800df40e  mov     [rsp+6E0h+var_6A0], r15
0x1800df413  call    ?GetCallHistoryDataSession@@YAJPEAVServiceDataSession@@PEAPEAVCallHistoryDataSession@@@Z; GetCallHistoryDataSession(ServiceDataSession *,CallHistoryDataSession * *)
0x1800df418  mov     ebx, eax
0x1800df41a  test    eax, eax
0x1800df41c  jns     short loc_1800DF42B
0x1800df41e  mov     r9d, 2D2h
0x1800df424  mov     edx, edi
0x1800df426  jmp     loc_1800DF37B
0x1800df42b  mov     rbx, [rsp+6E0h+var_6A0]
0x1800df430  lea     rsi, [rbx+810h]
0x1800df437  mov     rcx, rsi; lpCriticalSection
0x1800df43a  call    cs:__imp_EnterCriticalSection
0x1800df440  lea     rcx, [rsp+6E0h+var_688]
0x1800df445  mov     dword ptr [rsp+6E0h+var_6A0], r15d
0x1800df44a  mov     [rsp+6E0h+var_688], r15
0x1800df44f  call    ??$replace@U_USRestriction@@$1??$_LocalFreer@U_USRestriction@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_USRestriction@@AEAV?$auto_array_ptr@U_USRestriction@@$1??$_LocalFreer@U_USRestriction@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_USRestriction,&_LocalFreer<_USRestriction>(_USRestriction *)>(tlx::auto_array_ptr<_USRestriction,&_LocalFreer<_USRestriction>(_USRestriction *)> &)
0x1800df454  mov     qword ptr [rsp+6E0h+dwFlagsAndAttributes], rax; struct UdmPropertyValue **
0x1800df459  lea     r9, [rsp+6E0h+var_680]; unsigned int *
0x1800df45e  lea     rax, [rsp+6E0h+var_6A0]
0x1800df463  mov     r8d, edi; unsigned int
0x1800df466  mov     rdx, r14; struct UdmObjectId *
0x1800df469  mov     qword ptr [rsp+6E0h+dwCreationDisposition], rax; int *
0x1800df46e  mov     rcx, rbx; struct CallHistoryDataSession *
0x1800df471  call    ?PropertyMapper_CallHistory@@YAJPEAVCallHistoryDataSession@@AEBUUdmObjectId@@KQEBKPEAHPEAPEAUUdmPropertyValue@@@Z; PropertyMapper_CallHistory(CallHistoryDataSession *,UdmObjectId const &,ulong,ulong const * const,int *,UdmPropertyValue * *)
0x1800df476  mov     ebx, eax
0x1800df478  test    eax, eax
0x1800df47a  jns     short loc_1800DF48B
0x1800df47c  mov     r9d, 2DEh
0x1800df482  mov     edx, edi
0x1800df484  mov     ecx, eax
0x1800df486  jmp     loc_1800DF64B
0x1800df48b  cmp     dword ptr [rsp+6E0h+var_6A0], r15d
0x1800df490  jnz     short loc_1800DF4A2
0x1800df492  mov     r9d, 2E0h
0x1800df498  mov     ebx, 80070490h
0x1800df49d  jmp     loc_1800DF647
0x1800df4a2  mov     rax, [rsp+6E0h+var_688]
0x1800df4a7  test    dword ptr [rax], 100h
0x1800df4ad  jnz     loc_1800DF63C
0x1800df4b3  cmp     [rax+8], r15d
0x1800df4b7  jz      loc_1800DF63C
0x1800df4bd  mov     edx, dword ptr [rsp+6E0h+var_698]
0x1800df4c1  lea     r8, [rsp+6E0h+FileName]
0x1800df4c6  mov     ecx, [r14+8]
0x1800df4ca  call    _GetFileStreamPath
0x1800df4cf  mov     ebx, eax
0x1800df4d1  test    eax, eax
0x1800df4d3  jns     short loc_1800DF4DD
0x1800df4d5  mov     r9d, 2E9h
0x1800df4db  jmp     short loc_1800DF482
0x1800df4dd  lea     rcx, [rsp+6E0h+FileName]; lpFileName
0x1800df4e2  call    cs:__imp_GetFileAttributesW
0x1800df4e8  cmp     eax, 0FFFFFFFFh
0x1800df4eb  jnz     loc_1800DF607
0x1800df4f1  mov     r14d, 104h
0x1800df4f7  lea     rcx, [rbp+5E0h+var_460]
0x1800df4fe  mov     edx, r14d
0x1800df501  call    cs:__imp_?GetUSDataFolderPath@@YAJPEAG_K@Z; GetUSDataFolderPath(ushort *,unsigned __int64)
0x1800df507  mov     ebx, eax
0x1800df509  test    eax, eax
0x1800df50b  jns     short loc_1800DF518
0x1800df50d  mov     r9d, 2EEh
0x1800df513  jmp     loc_1800DF482
0x1800df518  lea     r9, [rbp+5E0h+var_460]
0x1800df51f  mov     rdx, r14; unsigned __int64
0x1800df522  lea     r8, aSCallhistory; "%s\\CallHistory"
0x1800df529  lea     rcx, [rbp+5E0h+pszPath]; unsigned __int16 *
0x1800df530  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800df535  mov     ebx, eax
0x1800df537  test    eax, eax
0x1800df539  jns     short loc_1800DF546
0x1800df53b  mov     r9d, 2F1h
0x1800df541  jmp     loc_1800DF482
0x1800df546  xor     r8d, r8d; psa
0x1800df549  lea     rdx, [rbp+5E0h+pszPath]; pszPath
0x1800df550  xor     ecx, ecx; hwnd
0x1800df552  call    cs:__imp_SHCreateDirectoryExW
0x1800df558  mov     ebx, eax
0x1800df55a  cmp     eax, 0B7h
0x1800df55f  jz      short loc_1800DF580
0x1800df561  cmp     eax, 50h ; 'P'
0x1800df564  jz      short loc_1800DF580
0x1800df566  test    eax, eax
0x1800df568  jz      short loc_1800DF580
0x1800df56a  jle     short loc_1800DF575
0x1800df56c  movzx   ebx, ax
0x1800df56f  or      ebx, 80070000h
0x1800df575  mov     r9d, 2F9h
0x1800df57b  jmp     loc_1800DF647
0x1800df580  xor     r9d, r9d; lpSecurityAttributes
0x1800df583  mov     [rsp+6E0h+hTemplateFile], r15; hTemplateFile
0x1800df588  mov     [rsp+6E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800df590  lea     rcx, [rsp+6E0h+FileName]; lpFileName
0x1800df595  mov     edx, 0C0000000h; dwDesiredAccess
0x1800df59a  mov     [rsp+6E0h+var_698], r15
0x1800df59f  mov     [rsp+6E0h+dwCreationDisposition], 4; dwCreationDisposition
0x1800df5a7  lea     r8d, [r9+3]; dwShareMode
0x1800df5ab  call    cs:__imp_CreateFileW
0x1800df5b1  mov     rdx, rax
0x1800df5b4  lea     rcx, [rsp+6E0h+var_698]
0x1800df5b9  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x1800df5be  cmp     [rsp+6E0h+var_698], 0FFFFFFFFFFFFFFFFh
0x1800df5c4  jnz     short loc_1800DF5FD
0x1800df5c6  call    cs:__imp_GetLastError
0x1800df5cc  mov     ebx, eax
0x1800df5ce  test    eax, eax
0x1800df5d0  jle     short loc_1800DF5DB
0x1800df5d2  movzx   ebx, ax
0x1800df5d5  or      ebx, 80070000h
0x1800df5db  mov     r9d, 303h
0x1800df5e1  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df5e8  xor     edx, edx
0x1800df5ea  mov     ecx, ebx
0x1800df5ec  call    Log_HREvent
0x1800df5f1  lea     rcx, [rsp+6E0h+var_698]
0x1800df5f6  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800df5fb  jmp     short loc_1800DF657
0x1800df5fd  lea     rcx, [rsp+6E0h+var_698]
0x1800df602  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800df607  lea     rdx, [rsp+6E0h+FileName]
0x1800df60c  mov     rcx, r13
0x1800df60f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800df614  test    al, al
0x1800df616  jnz     short loc_1800DF625
0x1800df618  mov     r9d, 306h
0x1800df61e  mov     ebx, 8007000Eh
0x1800df623  jmp     short loc_1800DF647
0x1800df625  lea     rcx, [rsp+6E0h+var_688]
0x1800df62a  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800df62f  mov     rcx, rsi; lpCriticalSection
0x1800df632  call    cs:__imp_LeaveCriticalSection
0x1800df638  xor     eax, eax
0x1800df63a  jmp     short loc_1800DF66C
0x1800df63c  mov     r9d, 2E5h
0x1800df642  mov     ebx, 80070057h
0x1800df647  xor     edx, edx
0x1800df649  mov     ecx, ebx
0x1800df64b  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800df652  call    Log_HREvent
0x1800df657  lea     rcx, [rsp+6E0h+var_688]
0x1800df65c  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800df661  mov     rcx, rsi; lpCriticalSection
0x1800df664  call    cs:__imp_LeaveCriticalSection
0x1800df66a  mov     eax, ebx
0x1800df66c  mov     rcx, [rbp+5E0h+var_40]
0x1800df673  xor     rcx, rsp; StackCookie
0x1800df676  call    __security_check_cookie
0x1800df67b  mov     rbx, [rsp+6E0h+arg_18]
0x1800df683  add     rsp, 6B0h
0x1800df68a  pop     r15
0x1800df68c  pop     r14
0x1800df68e  pop     r13
0x1800df690  pop     r12
0x1800df692  pop     rdi
0x1800df693  pop     rsi
0x1800df694  pop     rbp
0x1800df695  retn
```
