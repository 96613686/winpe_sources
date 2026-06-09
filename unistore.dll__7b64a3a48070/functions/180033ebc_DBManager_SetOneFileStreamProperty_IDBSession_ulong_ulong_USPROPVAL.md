# DBManager::SetOneFileStreamProperty(IDBSession *,ulong,ulong,_USPROPVAL *)

- ea: `0x180033ebc`
- end: `0x180034121`
- name: `?SetOneFileStreamProperty@DBManager@@SAJPEAVIDBSession@@KKPEAU_USPROPVAL@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(struct IDBSession *, unsigned int, unsigned int, struct _USPROPVAL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180033dc0`

## callees

- `0x1800068f0`
- `0x180015790`
- `0x1800160b0`
- `0x180028ef4`
- `0x180029be0`
- `0x180033ebc`
- `0x180034128`
- `0x180034540`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034072`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034067`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034067`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034042`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034042`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034055`

## string_xrefs

- `0x180033ee8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180033f1b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::SetOneFileStreamProperty(
        struct IDBSession *a1,
        unsigned int a2,
        unsigned int a3,
        struct _USPROPVAL *a4)
{
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // r9d
  int StreamFilePath; // eax
  struct _SECURITY_ATTRIBUTES *v16; // r9
  unsigned int v17; // edi
  HLOCAL v18; // rdi
  int v19; // eax
  int v20; // ebp
  DWORD v21; // r8d
  const void *v22; // rdx
  HANDLE v23; // rbx
  signed int LastError; // eax
  unsigned int v25; // ebx
  signed int v26; // [rsp+28h] [rbp-50h]
  void *v27; // [rsp+30h] [rbp-48h]
  HANDLE hFile; // [rsp+50h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  if ( !a1 || !a4 )
  {
    v8 = 3219;
LABEL_3:
    v9 = -2147024809;
    v10 = 0;
LABEL_4:
    Log_UnistoreHREvent_0(
      (unsigned int)v9,
      v10,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v8);
    return (unsigned int)v9;
  }
  if ( !(unsigned int)IsFileStreamSupportedInTable(a2) )
    Log_AssertionEvent(
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3221);
  if ( (*((_WORD *)a4 + 3) & 0x200) == 0 )
  {
    if ( *((_DWORD *)a4 + 2) && *((_QWORD *)a4 + 2) )
    {
      v14 = *(_DWORD *)a4;
      hMem = 0;
      StreamFilePath = DBManager::GetStreamFilePath(a1, a2, a3, v14, 0x40000000u, (unsigned __int16 **)&hMem);
      v17 = StreamFilePath;
      if ( StreamFilePath < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)StreamFilePath,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          3237);
      }
      else
      {
        v18 = hMem;
        hFile = (HANDLE)-1LL;
        v19 = StreamHelper::CreateFileAndPath(
                (const unsigned __int16 *)hMem,
                0x40000000u,
                0,
                v16,
                2u,
                v26,
                v27,
                1,
                &hFile);
        v20 = v19;
        if ( v19 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v19,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            3241);
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hFile);
          v17 = v20;
        }
        else
        {
          v21 = *((_DWORD *)a4 + 2);
          v22 = (const void *)*((_QWORD *)a4 + 2);
          v23 = hFile;
          NumberOfBytesWritten = 0;
          if ( WriteFile(hFile, v22, v21, &NumberOfBytesWritten, 0) )
          {
            if ( v23 != (HANDLE)-1LL )
              CloseHandle(v23);
            if ( v18 )
              LocalFree(v18);
            goto LABEL_9;
          }
          LastError = GetLastError();
          v25 = LastError;
          if ( LastError > 0 )
            v25 = (unsigned __int16)LastError | 0x80070000;
          Log_UnistoreHREvent_0(
            v25,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            3245);
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(&hFile);
          v17 = v25;
        }
      }
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
      return v17;
    }
    v8 = 3232;
    goto LABEL_3;
  }
  v9 = DBManager::DeleteFileStreamProps(a1, a2, a3, v13, a4);
  if ( v9 < 0 )
  {
    v8 = 3228;
    v10 = 1;
    goto LABEL_4;
  }
LABEL_9:
  if ( (*(unsigned int (__fastcall **)(struct IDBSession *))(*(_QWORD *)a1 + 112LL))(a1) )
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a1 + 152LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180033ebc  mov     [rsp+arg_8], rbx
0x180033ec1  mov     [rsp+arg_10], rbp
0x180033ec6  push    rsi
0x180033ec7  push    rdi
0x180033ec8  push    r14
0x180033eca  sub     rsp, 60h
0x180033ece  mov     rbx, r9
0x180033ed1  mov     ebp, r8d
0x180033ed4  mov     edi, edx
0x180033ed6  mov     r14, rcx
0x180033ed9  test    rcx, rcx
0x180033edc  jnz     loc_1800340B6
0x180033ee2  mov     r9d, 0C93h
0x180033ee8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180033eef  mov     ebx, 80070057h
0x180033ef4  xor     edx, edx
0x180033ef6  mov     ecx, ebx
0x180033ef8  call    Log_UnistoreHREvent_0
0x180033efd  mov     eax, ebx
0x180033eff  lea     r11, [rsp+78h+var_18]
0x180033f04  mov     rbx, [r11+28h]
0x180033f08  mov     rbp, [r11+30h]
0x180033f0c  mov     rsp, r11
0x180033f0f  pop     r14
0x180033f11  pop     rdi
0x180033f12  pop     rsi
0x180033f13  retn
0x180033f14  mov     ecx, edi; unsigned int
0x180033f16  call    ?IsFileStreamSupportedInTable@@YAHK@Z; IsFileStreamSupportedInTable(ulong)
0x180033f1b  lea     rsi, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180033f22  test    eax, eax
0x180033f24  jnz     short loc_180033F34
0x180033f26  mov     r8d, 0C95h
0x180033f2c  mov     rdx, rsi
0x180033f2f  call    Log_AssertionEvent
0x180033f34  mov     eax, 200h
0x180033f39  test    [rbx+6], ax
0x180033f3d  jz      short loc_180033F87
0x180033f3f  mov     r8d, ebp; unsigned int
0x180033f42  mov     [rsp+78h+lpOverlapped], rbx; struct _USPROPVAL *
0x180033f47  mov     edx, edi; unsigned int
0x180033f49  mov     rcx, r14; struct IDBSession *
0x180033f4c  call    ?DeleteFileStreamProps@DBManager@@SAJPEAVIDBSession@@KKKPEAU_USPROPVAL@@PEAK@Z; DBManager::DeleteFileStreamProps(IDBSession *,ulong,ulong,ulong,_USPROPVAL *,ulong *)
0x180033f51  mov     ebx, eax
0x180033f53  test    eax, eax
0x180033f55  js      loc_1800340C4
0x180033f5b  mov     rax, [r14]
0x180033f5e  mov     rcx, r14
0x180033f61  mov     rax, [rax+70h]
0x180033f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f6a  test    eax, eax
0x180033f6c  jz      short loc_180033F80
0x180033f6e  mov     rax, [r14]
0x180033f71  mov     rcx, r14
0x180033f74  mov     rax, [rax+98h]
0x180033f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f80  xor     eax, eax
0x180033f82  jmp     loc_180033EFF
0x180033f87  cmp     dword ptr [rbx+8], 0
0x180033f8b  ja      loc_1800340D7
0x180033f91  mov     r9d, 0CA0h
0x180033f97  mov     r8, rsi
0x180033f9a  jmp     loc_180033EEF
0x180033f9f  mov     r9d, [rbx]; unsigned int
0x180033fa2  lea     rax, [rsp+78h+hMem]
0x180033fa7  mov     [rsp+78h+var_50], rax; unsigned int
0x180033fac  mov     r8d, ebp; unsigned int
0x180033faf  mov     edx, edi; unsigned int
0x180033fb1  mov     dword ptr [rsp+78h+lpOverlapped], 40000000h; unsigned int
0x180033fb9  mov     rcx, r14; struct IDBSession *
0x180033fbc  mov     [rsp+78h+hMem], 0
0x180033fc5  call    ?GetStreamFilePath@DBManager@@SAJPEAVIDBSession@@KKKKPEAPEAG@Z; DBManager::GetStreamFilePath(IDBSession *,ulong,ulong,ulong,ulong,ushort * *)
0x180033fca  mov     edi, eax
0x180033fcc  test    eax, eax
0x180033fce  js      loc_1800340E7
0x180033fd4  mov     rdi, [rsp+78h+hMem]
0x180033fd9  lea     rax, [rsp+78h+hFile]
0x180033fde  mov     [rsp+78h+var_38], rax; void **
0x180033fe3  xor     r8d, r8d; dwShareMode
0x180033fe6  mov     [rsp+78h+var_40], 1; int
0x180033fee  mov     edx, 40000000h; dwDesiredAccess
0x180033ff3  mov     rcx, rdi; unsigned __int16 *
0x180033ff6  mov     dword ptr [rsp+78h+lpOverlapped], 2; DWORD
0x180033ffe  mov     [rsp+78h+hFile], 0FFFFFFFFFFFFFFFFh
0x180034007  call    ?CreateFileAndPath@StreamHelper@@SAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXHPEAPEAX@Z; StreamHelper::CreateFileAndPath(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,int,void * *)
0x18003400c  mov     ebp, eax
0x18003400e  test    eax, eax
0x180034010  js      loc_1800340FE
0x180034016  mov     r8d, [rbx+8]; nNumberOfBytesToWrite
0x18003401a  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034022  mov     rdx, [rbx+10h]; lpBuffer
0x180034026  mov     rbx, [rsp+78h+hFile]
0x18003402b  mov     rcx, rbx; hFile
0x18003402e  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180034039  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180034042  call    cs:__imp_WriteFile
0x180034048  test    eax, eax
0x18003404a  jz      short loc_180034072
0x18003404c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180034050  jz      short loc_18003405B
0x180034052  mov     rcx, rbx; hObject
0x180034055  call    cs:__imp_CloseHandle
0x18003405b  test    rdi, rdi
0x18003405e  jz      loc_180033F5B
0x180034064  mov     rcx, rdi; hMem
0x180034067  call    cs:__imp_LocalFree
0x18003406d  jmp     loc_180033F5B
0x180034072  call    cs:__imp_GetLastError
0x180034078  mov     ebx, eax
0x18003407a  test    eax, eax
0x18003407c  jle     short loc_180034087
0x18003407e  movzx   ebx, ax
0x180034081  or      ebx, 80070000h
0x180034087  mov     r9d, 0CADh
0x18003408d  mov     r8, rsi
0x180034090  xor     edx, edx
0x180034092  mov     ecx, ebx
0x180034094  call    Log_UnistoreHREvent_0
0x180034099  lea     rcx, [rsp+78h+hFile]
0x18003409e  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x1800340a3  mov     edi, ebx
0x1800340a5  lea     rcx, [rsp+78h+hMem]
0x1800340aa  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x1800340af  mov     eax, edi
0x1800340b1  jmp     loc_180033EFF
0x1800340b6  test    rbx, rbx
0x1800340b9  jz      loc_180033EE2
0x1800340bf  jmp     loc_180033F14
0x1800340c4  mov     r9d, 0C9Ch
0x1800340ca  mov     r8, rsi
0x1800340cd  mov     edx, 1
0x1800340d2  jmp     loc_180033EF6
0x1800340d7  cmp     qword ptr [rbx+10h], 0
0x1800340dc  jz      loc_180033F91
0x1800340e2  jmp     loc_180033F9F
0x1800340e7  mov     r9d, 0CA5h
0x1800340ed  mov     r8, rsi
0x1800340f0  mov     edx, 1
0x1800340f5  mov     ecx, eax
0x1800340f7  call    Log_UnistoreHREvent_0
0x1800340fc  jmp     short loc_1800340A5
0x1800340fe  mov     r9d, 0CA9h
0x180034104  mov     r8, rsi
0x180034107  mov     edx, 1
0x18003410c  mov     ecx, ebp
0x18003410e  call    Log_UnistoreHREvent_0
0x180034113  lea     rcx, [rsp+78h+hFile]
0x180034118  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)
0x18003411d  mov     edi, ebp
0x18003411f  jmp     short loc_1800340A5
```
