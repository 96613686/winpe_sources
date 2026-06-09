# CDVRSink::InternalClose(void)

- ea: `0x180003440`
- end: `0x1800039e4`
- name: `?InternalClose@CDVRSink@@MEAAJXZ`
- size: `1444`
- prototype: `__int64 __fastcall(CDVRSink *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800015f0`
- `0x180002778`
- `0x180003440`
- `0x180004b7c`
- `0x180009630`
- `0x18002b010`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180003644`
- `KERNEL32!SetFilePointerEx` at `0x180003644`
- `KERNEL32!CloseHandle` at `0x1800035bc`
- `KERNEL32!CloseHandle` at `0x1800038ab`
- `KERNEL32!CloseHandle` at `0x1800038c4`
- `KERNEL32!CloseHandle` at `0x1800038dd`
- `KERNEL32!CloseHandle` at `0x1800039a5`
- `KERNEL32!CloseHandle` at `0x18002a375`
- `KERNEL32!CloseHandle` at `0x1800035bc`
- `KERNEL32!CloseHandle` at `0x1800038ab`
- `KERNEL32!CloseHandle` at `0x1800038c4`
- `KERNEL32!CloseHandle` at `0x1800038dd`
- `KERNEL32!CloseHandle` at `0x1800039a5`
- `KERNEL32!CloseHandle` at `0x18002a375`
- `KERNEL32!SetEvent` at `0x18000359a`
- `KERNEL32!SetEvent` at `0x18000359a`
- `KERNEL32!GetLastError` at `0x180003651`
- `KERNEL32!GetLastError` at `0x18000383d`
- `KERNEL32!GetLastError` at `0x180003651`
- `KERNEL32!GetLastError` at `0x18000383d`
- `KERNEL32!UnmapViewOfFile` at `0x18000388b`
- `KERNEL32!UnmapViewOfFile` at `0x18000388b`
- `KERNEL32!ReleaseMutex` at `0x18000399c`
- `KERNEL32!ReleaseMutex` at `0x18002a36c`
- `KERNEL32!ReleaseMutex` at `0x18000399c`
- `KERNEL32!ReleaseMutex` at `0x18002a36c`
- `KERNEL32!WaitForSingleObject` at `0x1800034cd`
- `KERNEL32!WaitForSingleObject` at `0x1800034cd`
- `KERNEL32!SetFilePointer` at `0x180003707`
- `KERNEL32!SetFilePointer` at `0x180003707`
- `KERNEL32!LeaveCriticalSection` at `0x1800039af`
- `KERNEL32!LeaveCriticalSection` at `0x1800039af`
- `KERNEL32!LeaveCriticalSection` at `0x18002a38a`
- `KERNEL32!WriteFile` at `0x18000369a`
- `KERNEL32!WriteFile` at `0x18000376c`
- `KERNEL32!WriteFile` at `0x18000380d`
- `KERNEL32!WriteFile` at `0x18000369a`
- `KERNEL32!WriteFile` at `0x18000376c`
- `KERNEL32!WriteFile` at `0x18000380d`
- `KERNEL32!EnterCriticalSection` at `0x180003486`
- `KERNEL32!EnterCriticalSection` at `0x180003486`
- `KERNEL32!ReadFile` at `0x18000373b`
- `KERNEL32!ReadFile` at `0x1800037b2`
- `KERNEL32!ReadFile` at `0x18000373b`
- `KERNEL32!ReadFile` at `0x1800037b2`

## pseudocode

```c
__int64 __fastcall CDVRSink::InternalClose(CDVRSink *this)
{
  signed int v2; // edi
  void *v3; // r15
  int v4; // eax
  int v5; // r14d
  void *v6; // rcx
  void *v7; // rcx
  signed int LastError; // eax
  __int64 v9; // rdx
  void *v10; // rcx
  BOOL i; // eax
  __int64 v12; // rax
  int v13; // eax
  DWORD v14; // esi
  __int64 v15; // rax
  __int64 v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rdx
  signed int v21; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-468h] BYREF
  int v24; // [rsp+54h] [rbp-464h]
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp-460h] BYREF
  int v26; // [rsp+5Ch] [rbp-45Ch]
  int v27; // [rsp+60h] [rbp-458h] BYREF
  void *v28; // [rsp+68h] [rbp-450h]
  CDVRSink *v29; // [rsp+70h] [rbp-448h]
  _BYTE Buffer[1024]; // [rsp+80h] [rbp-438h] BYREF

  v29 = this;
  v2 = 0;
  v3 = 0;
  v28 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = *((_DWORD *)this + 2343);
  if ( !v4 )
    goto LABEL_48;
  if ( v4 != 2 || !*((_QWORD *)this + 1160) )
  {
    if ( v4 != 1 )
      goto LABEL_48;
    WaitForSingleObject(*((HANDLE *)this + 1205), 0xFFFFFFFF);
    *(_DWORD *)(*((_QWORD *)this + 1160) + 416LL) = 1;
    v3 = (void *)*((_QWORD *)this + 1205);
    v28 = v3;
    if ( *((_QWORD *)this + 1199) )
    {
      CDVRSink::FlushToDiskLocked(this);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1199) + 40LL))(*((_QWORD *)this + 1199));
      *(_OWORD *)*((_QWORD *)this + 1160) = 0;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1199) + 16LL))(*((_QWORD *)this + 1199));
      *((_QWORD *)this + 1199) = 0;
    }
    v5 = 0;
    v26 = 0;
    while ( v5 < 8 )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 1160) + 40LL * v5 + 76) == 2 )
      {
        if ( !*((_QWORD *)this + v5 + 1206) && !*((_DWORD *)this + v5 + 2428) )
          (*(void (__fastcall **)(CDVRSink *, _QWORD))(*(_QWORD *)this + 336LL))(this, (unsigned int)v5);
        v6 = (void *)*((_QWORD *)this + v5 + 1206);
        if ( v6 )
          SetEvent(v6);
      }
      if ( *(_DWORD *)(*((_QWORD *)this + 1160) + 40LL * v5 + 72) )
      {
        v7 = (void *)*((_QWORD *)this + v5 + 1206);
        if ( v7 )
        {
          CloseHandle(v7);
          *((_QWORD *)this + v5 + 1206) = 0;
        }
        *((_DWORD *)this + v5 + 2428) = 0;
        *(_DWORD *)(*((_QWORD *)this + 1160) + 40LL * v5 + 72) = 0;
        *(_DWORD *)(*((_QWORD *)this + 1160) + 40LL * v5 + 76) = 0;
      }
      v26 = ++v5;
    }
    if ( !*((_DWORD *)this + 2346) || *((_DWORD *)this + 2342) && !*((_DWORD *)this + 2344) )
      goto LABEL_48;
    NumberOfBytesWritten = 0;
    if ( SetFilePointerEx(*((HANDLE *)this + 24), 0, 0, 2u) == -1 )
      goto LABEL_25;
    if ( WriteFile(
           *((HANDLE *)this + 24),
           (LPCVOID)(*((_QWORD *)this + 1160) + *(unsigned int *)(*((_QWORD *)this + 1160) + 388LL)),
           *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL) - *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL),
           &NumberOfBytesWritten,
           0)
      && NumberOfBytesWritten == *(_DWORD *)(*((_QWORD *)this + 1160) + 392LL)
                               - *(_DWORD *)(*((_QWORD *)this + 1160) + 388LL) )
    {
      v9 = NumberOfBytesWritten;
      *((_QWORD *)this + 33) += NumberOfBytesWritten;
      *((_QWORD *)this + 40) += v9;
      v10 = (void *)*((_QWORD *)this + 1163);
      if ( v10 )
      {
        if ( SetFilePointer(v10, *((_DWORD *)this + 2372), 0, 0) != -1 )
        {
          NumberOfBytesRead = 0;
          for ( i = ReadFile(*((HANDLE *)this + 1163), Buffer, 0x400u, &NumberOfBytesRead, 0);
                i;
                i = ReadFile(*((HANDLE *)this + 1163), Buffer, 0x400u, &NumberOfBytesRead, 0) )
          {
            if ( !NumberOfBytesRead )
              goto LABEL_37;
            if ( !WriteFile(*((HANDLE *)this + 24), Buffer, NumberOfBytesRead, &NumberOfBytesWritten, 0) )
              goto LABEL_46;
            v12 = NumberOfBytesWritten;
            if ( NumberOfBytesWritten != NumberOfBytesRead )
              goto LABEL_46;
            *((_QWORD *)this + 33) += NumberOfBytesWritten;
            *((_QWORD *)this + 40) += v12;
          }
        }
LABEL_25:
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_47;
      }
LABEL_37:
      if ( !*((_DWORD *)this + 2382) && *((_DWORD *)this + 2374) )
        v13 = *((_DWORD *)this + 2368);
      else
        v13 = *((_DWORD *)this + 2373);
      v14 = 6 * v13;
      if ( !(6 * v13) )
      {
LABEL_45:
        *((_DWORD *)this + 82) = *((_DWORD *)this + 2346);
        goto LABEL_48;
      }
      if ( WriteFile(
             *((HANDLE *)this + 24),
             (LPCVOID)(*((_QWORD *)this + 1160) + *(unsigned int *)(*((_QWORD *)this + 1160) + 392LL)),
             v14,
             &NumberOfBytesWritten,
             0)
        && NumberOfBytesWritten == v14 )
      {
        v15 = NumberOfBytesWritten;
        *((_QWORD *)this + 33) += NumberOfBytesWritten;
        *((_QWORD *)this + 40) += v15;
        goto LABEL_45;
      }
    }
LABEL_46:
    GetLastError();
    *((_DWORD *)this + 2314) = 3;
    v2 = -1072889832;
LABEL_47:
    v24 = v2;
    goto LABEL_48;
  }
  v3 = (void *)*((_QWORD *)this + 1205);
  v28 = v3;
LABEL_48:
  v16 = *((_QWORD *)this + 1160);
  if ( v16 )
  {
    _InterlockedExchange((volatile __int32 *)(v16 + 408), 0);
    _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 1160) + 384LL), 0);
    if ( *((_DWORD *)this + 2344) )
      UnmapViewOfFile(*((LPCVOID *)this + 1160));
    *((_QWORD *)this + 1160) = 0;
    *((_QWORD *)this + 1205) = 0;
  }
  v17 = (void *)*((_QWORD *)this + 1162);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)this + 1162) = 0;
  }
  v18 = (void *)*((_QWORD *)this + 1161);
  if ( v18 )
  {
    CloseHandle(v18);
    *((_QWORD *)this + 1161) = 0;
  }
  v19 = (void *)*((_QWORD *)this + 1163);
  if ( v19 )
  {
    CloseHandle(v19);
    *((_QWORD *)this + 1163) = 0;
  }
  *((_DWORD *)this + 2337) = 1;
  v27 = 0;
  v20 = 1;
  while ( (*(int (__fastcall **)(char *, __int64, int *))(*((_QWORD *)this + 1159) + 56LL))(
            (char *)this + 9272,
            v20,
            &v27) < 0 )
  {
    v20 = (unsigned int)++*((_DWORD *)this + 2337);
    if ( (unsigned int)v20 > 0xA )
    {
      v2 = -2147467259;
      v24 = -2147467259;
      break;
    }
  }
  *(_QWORD *)((char *)this + 9372) = 0;
  *((_DWORD *)this + 2346) = 0;
  *((_DWORD *)this + 2342) = 0;
  CDVRIndexObject::SetIndexParams((CDVRSink *)((char *)this + 9392), 0, 0, 0, 0, 0, 0, 0, 0, 0);
  v21 = CWMFileSinkV1::InternalClose(this);
  if ( v2 >= 0 )
    v2 = v21;
  v24 = v2;
  if ( v3 )
  {
    ReleaseMutex(v3);
    CloseHandle(v3);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003440  mov     [rsp+arg_8], rbx
0x180003445  mov     [rsp+arg_10], rsi
0x18000344a  push    rdi
0x18000344b  push    r12
0x18000344d  push    r13
0x18000344f  push    r14
0x180003451  push    r15
0x180003453  sub     rsp, 490h
0x18000345a  mov     rax, cs:__security_cookie
0x180003461  xor     rax, rsp
0x180003464  mov     [rsp+4B8h+var_38], rax
0x18000346c  mov     rbx, rcx
0x18000346f  mov     [rsp+4B8h+var_448], rcx
0x180003474  xor     r12d, r12d
0x180003477  mov     edi, r12d
0x18000347a  mov     r15d, r12d
0x18000347d  mov     [rsp+4B8h+var_450], r12
0x180003482  add     rcx, 30h ; '0'; lpCriticalSection
0x180003486  call    cs:__imp_EnterCriticalSection
0x18000348c  nop
0x18000348d  mov     eax, [rbx+249Ch]
0x180003493  test    eax, eax
0x180003495  jz      loc_180003856
0x18000349b  cmp     eax, 2
0x18000349e  jnz     short loc_1800034BA
0x1800034a0  cmp     [rbx+2440h], r12
0x1800034a7  jz      short loc_1800034BA
0x1800034a9  mov     r15, [rbx+25A8h]
0x1800034b0  mov     [rsp+4B8h+var_450], r15
0x1800034b5  jmp     loc_180003856
0x1800034ba  cmp     eax, 1
0x1800034bd  jnz     loc_180003856
0x1800034c3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800034c6  mov     rcx, [rbx+25A8h]; hHandle
0x1800034cd  call    cs:__imp_WaitForSingleObject
0x1800034d3  mov     rax, [rbx+2440h]
0x1800034da  mov     dword ptr [rax+1A0h], 1
0x1800034e4  mov     r15, [rbx+25A8h]
0x1800034eb  mov     [rsp+4B8h+var_450], r15
0x1800034f0  cmp     [rbx+2578h], r12
0x1800034f7  jz      short loc_18000353B
0x1800034f9  mov     rcx, rbx; this
0x1800034fc  call    ?FlushToDiskLocked@CDVRSink@@IEAAXXZ; CDVRSink::FlushToDiskLocked(void)
0x180003501  mov     rcx, [rbx+2578h]
0x180003508  mov     rax, [rcx]
0x18000350b  mov     rax, [rax+28h]
0x18000350f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003514  xorps   xmm0, xmm0
0x180003517  mov     rax, [rbx+2440h]
0x18000351e  movups  xmmword ptr [rax], xmm0
0x180003521  mov     rcx, [rbx+2578h]
0x180003528  mov     rax, [rcx]
0x18000352b  mov     rax, [rax+10h]
0x18000352f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003534  mov     [rbx+2578h], r12
0x18000353b  mov     r14d, r12d
0x18000353e  mov     [rsp+4B8h+var_45C], r12d
0x180003543  cmp     r14d, 8
0x180003547  jge     loc_180003606
0x18000354d  movsxd  rsi, r14d
0x180003550  lea     r12, [rsi+rsi*4]
0x180003554  mov     rax, [rbx+2440h]
0x18000355b  cmp     dword ptr [rax+r12*8+4Ch], 2
0x180003561  jnz     short loc_1800035A0
0x180003563  cmp     qword ptr [rbx+rsi*8+25B0h], 0
0x18000356c  jnz     short loc_18000358D
0x18000356e  cmp     dword ptr [rbx+rsi*4+25F0h], 0
0x180003576  jnz     short loc_18000358D
0x180003578  mov     rax, [rbx]
0x18000357b  mov     edx, r14d
0x18000357e  mov     rcx, rbx
0x180003581  mov     rax, [rax+150h]
0x180003588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000358d  mov     rcx, [rbx+rsi*8+25B0h]; hEvent
0x180003595  test    rcx, rcx
0x180003598  jz      short loc_1800035A0
0x18000359a  call    cs:__imp_SetEvent
0x1800035a0  mov     rax, [rbx+2440h]
0x1800035a7  cmp     dword ptr [rax+r12*8+48h], 0
0x1800035ad  jz      short loc_1800035F9
0x1800035af  mov     rcx, [rbx+rsi*8+25B0h]; hObject
0x1800035b7  test    rcx, rcx
0x1800035ba  jz      short loc_1800035CE
0x1800035bc  call    cs:__imp_CloseHandle
0x1800035c2  mov     qword ptr [rbx+rsi*8+25B0h], 0
0x1800035ce  mov     dword ptr [rbx+rsi*4+25F0h], 0
0x1800035d9  mov     rax, [rbx+2440h]
0x1800035e0  mov     dword ptr [rax+r12*8+48h], 0
0x1800035e9  mov     rax, [rbx+2440h]
0x1800035f0  mov     dword ptr [rax+r12*8+4Ch], 0
0x1800035f9  inc     r14d
0x1800035fc  mov     [rsp+4B8h+var_45C], r14d
0x180003601  jmp     loc_180003543
0x180003606  xor     r12d, r12d
0x180003609  cmp     [rbx+24A8h], r12d
0x180003610  jz      loc_180003856
0x180003616  cmp     [rbx+2498h], r12d
0x18000361d  jz      short loc_18000362C
0x18000361f  cmp     [rbx+24A0h], r12d
0x180003626  jz      loc_180003856
0x18000362c  mov     [rsp+4B8h+NumberOfBytesWritten], r12d
0x180003631  mov     rdx, r12; liDistanceToMove
0x180003634  mov     r9d, 2; dwMoveMethod
0x18000363a  xor     r8d, r8d; lpNewFilePointer
0x18000363d  mov     rcx, [rbx+0C0h]; hFile
0x180003644  call    cs:__imp_SetFilePointerEx
0x18000364a  or      esi, 0FFFFFFFFh
0x18000364d  cmp     eax, esi
0x18000364f  jnz     short loc_18000366F
0x180003651  call    cs:__imp_GetLastError
0x180003657  mov     edi, eax
0x180003659  test    eax, eax
0x18000365b  jle     loc_180003852
0x180003661  movzx   edi, ax
0x180003664  or      edi, 80070000h
0x18000366a  jmp     loc_180003852
0x18000366f  mov     rax, [rbx+2440h]
0x180003676  mov     edx, [rax+184h]
0x18000367c  mov     r8d, [rax+188h]
0x180003683  sub     r8d, edx; nNumberOfBytesToWrite
0x180003686  add     rdx, rax; lpBuffer
0x180003689  mov     [rsp+4B8h+lpOverlapped], r12; lpOverlapped
0x18000368e  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003693  mov     rcx, [rbx+0C0h]; hFile
0x18000369a  call    cs:__imp_WriteFile
0x1800036a0  test    eax, eax
0x1800036a2  jz      loc_18000383D
0x1800036a8  mov     rax, [rbx+2440h]
0x1800036af  mov     ecx, [rax+188h]
0x1800036b5  sub     ecx, [rax+184h]
0x1800036bb  cmp     [rsp+4B8h+NumberOfBytesWritten], ecx
0x1800036bf  jnz     loc_18000383D
0x1800036c5  mov     edx, [rsp+4B8h+NumberOfBytesWritten]
0x1800036c9  mov     rcx, [rbx+108h]
0x1800036d0  add     rcx, rdx
0x1800036d3  mov     [rbx+108h], rcx
0x1800036da  mov     rcx, [rbx+140h]
0x1800036e1  add     rcx, rdx
0x1800036e4  mov     [rbx+140h], rcx
0x1800036eb  mov     rcx, [rbx+2458h]; hFile
0x1800036f2  test    rcx, rcx
0x1800036f5  jz      loc_1800037C2
0x1800036fb  xor     r9d, r9d; dwMoveMethod
0x1800036fe  xor     r8d, r8d; lpDistanceToMoveHigh
0x180003701  mov     edx, [rbx+2510h]; lDistanceToMove
0x180003707  call    cs:__imp_SetFilePointer
0x18000370d  cmp     eax, esi
0x18000370f  jz      loc_180003651
0x180003715  mov     [rsp+4B8h+NumberOfBytesRead], r12d
0x18000371a  mov     [rsp+4B8h+lpOverlapped], r12; lpOverlapped
0x18000371f  lea     r9, [rsp+4B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180003724  mov     esi, 400h
0x180003729  mov     r8d, esi; nNumberOfBytesToRead
0x18000372c  lea     rdx, [rsp+4B8h+Buffer]; lpBuffer
0x180003734  mov     rcx, [rbx+2458h]; hFile
0x18000373b  call    cs:__imp_ReadFile
0x180003741  test    eax, eax
0x180003743  jz      loc_180003651
0x180003749  mov     r8d, [rsp+4B8h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x18000374e  test    r8d, r8d
0x180003751  jz      short loc_1800037BA
0x180003753  mov     [rsp+4B8h+lpOverlapped], r12; lpOverlapped
0x180003758  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000375d  lea     rdx, [rsp+4B8h+Buffer]; lpBuffer
0x180003765  mov     rcx, [rbx+0C0h]; hFile
0x18000376c  call    cs:__imp_WriteFile
0x180003772  test    eax, eax
0x180003774  jz      loc_18000383D
0x18000377a  mov     eax, [rsp+4B8h+NumberOfBytesWritten]
0x18000377e  cmp     eax, [rsp+4B8h+NumberOfBytesRead]
0x180003782  jnz     loc_18000383D
0x180003788  add     [rbx+108h], rax
0x18000378f  add     [rbx+140h], rax
0x180003796  mov     [rsp+4B8h+lpOverlapped], r12; lpOverlapped
0x18000379b  lea     r9, [rsp+4B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800037a0  mov     r8d, esi; nNumberOfBytesToRead
0x1800037a3  lea     rdx, [rsp+4B8h+Buffer]; lpBuffer
0x1800037ab  mov     rcx, [rbx+2458h]; hFile
0x1800037b2  call    cs:__imp_ReadFile
0x1800037b8  jmp     short loc_180003741
0x1800037ba  test    eax, eax
0x1800037bc  jz      loc_180003651
0x1800037c2  cmp     [rbx+2538h], r12d
0x1800037c9  jnz     short loc_1800037D4
0x1800037cb  cmp     [rbx+2518h], r12d
0x1800037d2  jnz     short loc_1800037DC
0x1800037d4  mov     eax, [rbx+2514h]
0x1800037da  jmp     short loc_1800037E2
0x1800037dc  mov     eax, [rbx+2500h]
0x1800037e2  lea     esi, [rax+rax*2]
0x1800037e5  add     esi, esi
0x1800037e7  jz      short loc_18000382F
0x1800037e9  mov     rax, [rbx+2440h]
0x1800037f0  mov     edx, [rax+188h]
0x1800037f6  add     rdx, rax; lpBuffer
0x1800037f9  mov     [rsp+4B8h+lpOverlapped], r12; lpOverlapped
0x1800037fe  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003803  mov     r8d, esi; nNumberOfBytesToWrite
0x180003806  mov     rcx, [rbx+0C0h]; hFile
0x18000380d  call    cs:__imp_WriteFile
0x180003813  test    eax, eax
0x180003815  jz      short loc_18000383D
0x180003817  cmp     [rsp+4B8h+NumberOfBytesWritten], esi
0x18000381b  jnz     short loc_18000383D
0x18000381d  mov     eax, [rsp+4B8h+NumberOfBytesWritten]
0x180003821  add     [rbx+108h], rax
0x180003828  add     [rbx+140h], rax
0x18000382f  mov     eax, [rbx+24A8h]
0x180003835  mov     [rbx+148h], eax
0x18000383b  jmp     short loc_180003856
0x18000383d  call    cs:__imp_GetLastError
0x180003843  mov     dword ptr [rbx+2428h], 3
0x18000384d  mov     edi, 0C00D0018h
0x180003852  mov     [rsp+4B8h+var_464], edi
0x180003856  mov     rcx, [rbx+2440h]
0x18000385d  test    rcx, rcx
0x180003860  jz      short loc_18000389F
0x180003862  mov     eax, r12d
0x180003865  xchg    eax, [rcx+198h]
0x18000386b  mov     rcx, [rbx+2440h]
0x180003872  mov     eax, r12d
0x180003875  xchg    eax, [rcx+180h]
0x18000387b  cmp     [rbx+24A0h], r12d
0x180003882  jz      short loc_180003891
0x180003884  mov     rcx, [rbx+2440h]; lpBaseAddress
0x18000388b  call    cs:__imp_UnmapViewOfFile
0x180003891  mov     [rbx+2440h], r12
0x180003898  mov     [rbx+25A8h], r12
0x18000389f  mov     rcx, [rbx+2450h]; hObject
0x1800038a6  test    rcx, rcx
0x1800038a9  jz      short loc_1800038B8
0x1800038ab  call    cs:__imp_CloseHandle
0x1800038b1  mov     [rbx+2450h], r12
0x1800038b8  mov     rcx, [rbx+2448h]; hObject
0x1800038bf  test    rcx, rcx
0x1800038c2  jz      short loc_1800038D1
0x1800038c4  call    cs:__imp_CloseHandle
0x1800038ca  mov     [rbx+2448h], r12
0x1800038d1  mov     rcx, [rbx+2458h]; hObject
0x1800038d8  test    rcx, rcx
0x1800038db  jz      short loc_1800038EA
0x1800038dd  call    cs:__imp_CloseHandle
0x1800038e3  mov     [rbx+2458h], r12
0x1800038ea  mov     dword ptr [rbx+2484h], 1
0x1800038f4  mov     [rsp+4B8h+var_458], r12d
0x1800038f9  mov     edx, 1
0x1800038fe  lea     rcx, [rbx+2438h]
0x180003905  mov     rax, [rcx]
0x180003908  lea     r8, [rsp+4B8h+var_458]
0x18000390d  mov     rax, [rax+38h]
0x180003911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003916  test    eax, eax
0x180003918  jns     short loc_180003938
0x18000391a  inc     dword ptr [rbx+2484h]
0x180003920  mov     edx, [rbx+2484h]
0x180003926  cmp     edx, 0Ah
0x180003929  jbe     short loc_180003936
0x18000392b  mov     edi, 80004005h
0x180003930  mov     [rsp+4B8h+var_464], edi
0x180003934  jmp     short loc_180003938
0x180003936  jmp     short loc_1800038FE
0x180003938  mov     qword ptr [rbx+249Ch], 0
0x180003943  mov     [rbx+24A8h], r12d
0x18000394a  mov     [rbx+2498h], r12d
0x180003951  lea     rcx, [rbx+24B0h]; this
0x180003958  mov     [rsp+4B8h+var_470], r12; void *
0x18000395d  mov     [rsp+4B8h+var_478], r12; unsigned __int64 *
0x180003962  mov     [rsp+4B8h+var_480], r12; unsigned __int64 *
0x180003967  mov     [rsp+4B8h+var_488], r12; unsigned __int64 *
0x18000396c  mov     [rsp+4B8h+var_490], r12d; unsigned int
0x180003971  mov     [rsp+4B8h+lpOverlapped], r12; unsigned int *
0x180003976  xor     r9d, r9d; unsigned __int8 *
0x180003979  xor     r8d, r8d; unsigned __int8 *
0x18000397c  xor     edx, edx; unsigned __int8 *
0x18000397e  call    ?SetIndexParams@CDVRIndexObject@@QEAAJPEAE00PEAKKPEA_K22PEAX@Z; CDVRIndexObject::SetIndexParams(uchar *,uchar *,uchar *,ulong *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,void *)
0x180003983  mov     rcx, rbx; this
0x180003986  call    ?InternalClose@CWMFileSinkV1@@MEAAJXZ; CWMFileSinkV1::InternalClose(void)
0x18000398b  test    edi, edi
0x18000398d  cmovns  edi, eax
0x180003990  mov     [rsp+4B8h+var_464], edi
0x180003994  test    r15, r15
0x180003997  jz      short loc_1800039AB
0x180003999  mov     rcx, r15; hMutex
0x18000399c  call    cs:__imp_ReleaseMutex
0x1800039a2  mov     rcx, r15; hObject
0x1800039a5  call    cs:__imp_CloseHandle
0x1800039ab  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800039af  call    cs:__imp_LeaveCriticalSection
0x1800039b5  mov     eax, edi
0x1800039b7  mov     rcx, [rsp+4B8h+var_38]
0x1800039bf  xor     rcx, rsp; StackCookie
0x1800039c2  call    __security_check_cookie
0x1800039c7  lea     r11, [rsp+4B8h+var_28]
0x1800039cf  mov     rbx, [r11+38h]
0x1800039d3  mov     rsi, [r11+40h]
0x1800039d7  mov     rsp, r11
0x1800039da  pop     r15
0x1800039dc  pop     r14
0x1800039de  pop     r13
0x1800039e0  pop     r12
  ... truncated ...
```
