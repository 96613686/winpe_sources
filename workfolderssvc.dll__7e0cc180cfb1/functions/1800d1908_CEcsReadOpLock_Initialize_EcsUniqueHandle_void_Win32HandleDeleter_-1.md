# CEcsReadOpLock::Initialize(EcsUniqueHandle<void *,Win32HandleDeleter,-1> &)

- ea: `0x1800d1908`
- end: `0x1800d1cbe`
- name: `?Initialize@CEcsReadOpLock@@QEAAXAEAV?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800d1364`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x18001133c`
- `0x18003f2d0`
- `0x1800d1908`
- `0x1800d25e0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x1800d1c63`
- `KERNEL32!SetThreadpoolWait` at `0x1800d1c63`
- `KERNEL32!CreateThreadpoolWait` at `0x1800d1a1c`
- `KERNEL32!CreateThreadpoolWait` at `0x1800d1a1c`
- `KERNEL32!DeviceIoControl` at `0x1800d1ad9`
- `KERNEL32!DeviceIoControl` at `0x1800d1ad9`
- `KERNEL32!GetLastError` at `0x1800d1b14`
- `KERNEL32!GetLastError` at `0x1800d1b14`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800d19cf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800d19cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d1bb9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800d1bb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1c97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1c97`

## string_xrefs

- `0x1800d1994`: `CEcsReadOpLock::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CEcsReadOpLock::Initialize(char *pv, HANDLE *a2)
{
  char *v2; // rsi
  _BYTE *v3; // rax
  char v4; // al
  int v5; // eax
  char *v6; // rcx
  char *v7; // rax
  int v8; // [rsp+40h] [rbp-88h] BYREF
  int v9; // [rsp+44h] [rbp-84h]
  char v10; // [rsp+48h] [rbp-80h]
  const char *v11; // [rsp+50h] [rbp-78h]
  __int64 v12; // [rsp+58h] [rbp-70h]
  char *v13; // [rsp+60h] [rbp-68h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-60h] BYREF
  int LastFailureAsHRESULT; // [rsp+6Ch] [rbp-5Ch] BYREF
  int v16; // [rsp+70h] [rbp-58h] BYREF
  int v17; // [rsp+74h] [rbp-54h] BYREF
  int v18; // [rsp+78h] [rbp-50h] BYREF
  int v19; // [rsp+7Ch] [rbp-4Ch] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-48h] BYREF
  char v21; // [rsp+88h] [rbp-40h]
  const ATL::CAtlException *v22; // [rsp+90h] [rbp-38h] BYREF
  char *v23; // [rsp+D0h] [rbp+8h] BYREF
  HANDLE *v24; // [rsp+D8h] [rbp+10h]
  PTP_WAIT ThreadpoolWait; // [rsp+E0h] [rbp+18h] BYREF

  v24 = a2;
  v23 = pv;
  v2 = pv;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v4 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 2) == 0 || v3[65] < 6u )
    goto LABEL_8;
  v4 = 1;
LABEL_9:
  v8 = 0;
  v9 = 59;
  v10 = v4;
  v11 = "CEcsReadOpLock::Initialize";
  v12 = 0;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, v2 + 104);
  v13 = 0;
  try
  {
    v2[144] = 0;
    if ( !ResetEvent(*((HANDLE *)v2 + 2)) )
    {
      HIWORD(v9) = 73;
      pExceptionObject = EcsGetLastFailureAsHRESULT();
      throw (long *)&pExceptionObject;
    }
    v8 = 0;
    LOWORD(v9) = 73;
    ThreadpoolWait = CreateThreadpoolWait(CEcsReadOpLock::OplockWaitCallback, v2, 0);
    if ( !ThreadpoolWait )
    {
      HIWORD(v9) = 76;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v8 = 0;
    LOWORD(v9) = 76;
    EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(&v13, &ThreadpoolWait);
    *((_WORD *)v2 + 32) = 1;
    *((_WORD *)v2 + 33) = 12;
    *((_DWORD *)v2 + 17) = 3;
    *((_DWORD *)v2 + 18) = 1;
    *((_QWORD *)v2 + 7) = *((_QWORD *)v2 + 2);
    if ( DeviceIoControl(*v24, 0x90240u, v2 + 64, 0xCu, v2 + 76, 0x18u, 0, (LPOVERLAPPED)v2 + 1) )
    {
      v8 = -2147418113;
      HIWORD(v9) = 95;
      v16 = -2147418113;
      throw (long *)&v16;
    }
    v8 = 0;
    LOWORD(v9) = 95;
    if ( GetLastError() != 997 )
    {
      HIWORD(v9) = 100;
      v17 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v17;
    }
    v2[144] = 1;
  }
  catch ( long v19 )
  {
    v8 = v19;
    v2 = v23;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v9) = 106;
    v8 = -2147024882;
    v2 = v23;
  }
  catch ( std::exception )
  {
    HIWORD(v9) = 106;
    v8 = -2147418113;
    v2 = v23;
  }
  catch ( const ATL::CAtlException *v22 )
  {
    HIWORD(v9) = 106;
    v8 = *(_DWORD *)v22;
    v2 = v23;
  }
  v5 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v5 = v8;
    }
    v8 = v5;
    if ( !SetEvent(*((HANDLE *)v2 + 2)) )
    {
      HIWORD(v9) = 116;
      v18 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v18;
    }
    v8 = 0;
    LOWORD(v9) = 118;
  }
  v6 = (char *)*v24;
  *v24 = (HANDLE)-1LL;
  v23 = v6;
  EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(v2 + 8, &v23);
  v7 = v13;
  v13 = 0;
  v23 = v7;
  EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(v2 + 24, &v23);
  SetThreadpoolWait(*((PTP_WAIT *)v2 + 3), *((HANDLE *)v2 + 2), 0);
  v23 = 0;
  EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(&v13, &v23);
  if ( v21 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v21 = 0;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v8);
}

```

## disassembly

```asm
0x1800d1908  mov     [rsp+arg_8], rdx
0x1800d190d  mov     [rsp+arg_0], rcx
0x1800d1912  push    rbx
0x1800d1913  push    rsi
0x1800d1914  push    rdi
0x1800d1915  push    r14
0x1800d1917  push    r15
0x1800d1919  sub     rsp, 0A0h
0x1800d1920  mov     rsi, rcx
0x1800d1923  lea     rbx, WPP_GLOBAL_Control
0x1800d192a  mov     rax, cs:WPP_GLOBAL_Control
0x1800d1931  mov     r14d, 0Ch
0x1800d1937  cmp     rax, rbx
0x1800d193a  jz      short loc_1800D1962
0x1800d193c  test    byte ptr [rax+44h], 2
0x1800d1940  jz      short loc_1800D197B
0x1800d1942  cmp     byte ptr [rax+41h], 6
0x1800d1946  jb      short loc_1800D1962
0x1800d1948  mov     edx, r14d
0x1800d194b  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d1952  mov     rcx, [rax+38h]
0x1800d1956  call    WPP_SF_
0x1800d195b  mov     rax, cs:WPP_GLOBAL_Control
0x1800d1962  test    byte ptr [rax+44h], 2
0x1800d1966  jz      short loc_1800D197B
0x1800d1968  cmp     byte ptr [rax+41h], 6
0x1800d196c  jb      short loc_1800D197B
0x1800d196e  mov     r15d, 1
0x1800d1974  mov     al, r15b
0x1800d1977  xor     edi, edi
0x1800d1979  jmp     short loc_1800D1984
0x1800d197b  xor     edi, edi
0x1800d197d  mov     al, dil
0x1800d1980  lea     r15d, [rdi+1]
0x1800d1984  mov     [rsp+0C8h+var_88], edi
0x1800d1988  mov     [rsp+0C8h+var_84], 3Bh ; ';'
0x1800d1990  mov     [rsp+0C8h+var_80], al
0x1800d1994  lea     rax, aCecsreadoplock_4; "CEcsReadOpLock::Initialize"
0x1800d199b  mov     [rsp+0C8h+var_78], rax
0x1800d19a0  mov     [rsp+0C8h+var_70], rdi
0x1800d19a5  lea     rdx, [rsi+68h]
0x1800d19a9  lea     rcx, [rsp+0C8h+lpCriticalSection]
0x1800d19b1  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x1800d19b6  nop
0x1800d19b7  mov     [rsp+0C8h+var_68], rdi
0x1800d19bc  mov     [rsi+90h], dil
0x1800d19c3  mov     eax, [rsp+0C8h+var_88]
0x1800d19c7  mov     [rsp+0C8h+var_88], eax
0x1800d19cb  mov     rcx, [rsi+10h]; hEvent
0x1800d19cf  call    cs:__imp_ResetEvent
0x1800d19d5  test    eax, eax
0x1800d19d7  jnz     short loc_1800D1A01
0x1800d19d9  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d19de  mov     [rsp+0C8h+var_88], eax
0x1800d19e2  mov     ecx, 49h ; 'I'
0x1800d19e7  mov     word ptr [rsp+0C8h+var_84+2], cx
0x1800d19ec  mov     [rsp+0C8h+pExceptionObject], eax
0x1800d19f0  lea     rdx, _TI1J; pThrowInfo
0x1800d19f7  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800d19fc  call    _CxxThrowException_0
0x1800d1a01  mov     [rsp+0C8h+var_88], edi
0x1800d1a05  mov     ecx, 49h ; 'I'
0x1800d1a0a  mov     word ptr [rsp+0C8h+var_84], cx
0x1800d1a0f  xor     r8d, r8d; pcbe
0x1800d1a12  mov     rdx, rsi; pv
0x1800d1a15  lea     rcx, ?OplockWaitCallback@CEcsReadOpLock@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800d1a1c  call    cs:__imp_CreateThreadpoolWait
0x1800d1a22  mov     [rsp+0C8h+arg_10], rax
0x1800d1a2a  mov     ecx, [rsp+0C8h+var_88]
0x1800d1a2e  mov     [rsp+0C8h+var_88], ecx
0x1800d1a32  test    rax, rax
0x1800d1a35  jnz     short loc_1800D1A5F
0x1800d1a37  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d1a3c  mov     [rsp+0C8h+var_88], eax
0x1800d1a40  mov     ecx, 4Ch ; 'L'
0x1800d1a45  mov     word ptr [rsp+0C8h+var_84+2], cx
0x1800d1a4a  mov     [rsp+0C8h+var_5C], eax
0x1800d1a4e  lea     rdx, _TI1J; pThrowInfo
0x1800d1a55  lea     rcx, [rsp+0C8h+var_5C]; pExceptionObject
0x1800d1a5a  call    _CxxThrowException_0
0x1800d1a5f  mov     [rsp+0C8h+var_88], edi
0x1800d1a63  mov     ecx, 4Ch ; 'L'
0x1800d1a68  mov     word ptr [rsp+0C8h+var_84], cx
0x1800d1a6d  lea     rdx, [rsp+0C8h+arg_10]
0x1800d1a75  lea     rcx, [rsp+0C8h+var_68]
0x1800d1a7a  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WAIT@@UWin32ThreadPoolWaitDeleter@@$0A@@@QEAAXAEBQEAU_TP_WAIT@@@Z; EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(_TP_WAIT * const &)
0x1800d1a7f  lea     r8, [rsi+40h]; lpInBuffer
0x1800d1a83  mov     [r8], r15w
0x1800d1a87  mov     [rsi+42h], r14w
0x1800d1a8c  mov     dword ptr [rsi+44h], 3
0x1800d1a93  mov     [rsi+48h], r15d
0x1800d1a97  lea     rcx, [rsi+20h]
0x1800d1a9b  mov     rax, [rsi+10h]
0x1800d1a9f  mov     [rcx+18h], rax
0x1800d1aa3  mov     eax, [rsp+0C8h+var_88]
0x1800d1aa7  mov     [rsp+0C8h+var_88], eax
0x1800d1aab  lea     rax, [rsi+4Ch]
0x1800d1aaf  mov     [rsp+0C8h+lpOverlapped], rcx; lpOverlapped
0x1800d1ab4  mov     [rsp+0C8h+lpBytesReturned], rdi; lpBytesReturned
0x1800d1ab9  mov     [rsp+0C8h+nOutBufferSize], 18h; nOutBufferSize
0x1800d1ac1  mov     [rsp+0C8h+lpOutBuffer], rax; lpOutBuffer
0x1800d1ac6  mov     r9d, r14d; nInBufferSize
0x1800d1ac9  mov     edx, 90240h; dwIoControlCode
0x1800d1ace  mov     rcx, [rsp+0C8h+arg_8]
0x1800d1ad6  mov     rcx, [rcx]; hDevice
0x1800d1ad9  call    cs:__imp_DeviceIoControl
0x1800d1adf  test    eax, eax
0x1800d1ae1  mov     eax, 5Fh ; '_'
0x1800d1ae6  jz      short loc_1800D1B0B
0x1800d1ae8  mov     ecx, 8000FFFFh
0x1800d1aed  mov     [rsp+0C8h+var_88], ecx
0x1800d1af1  mov     word ptr [rsp+0C8h+var_84+2], ax
0x1800d1af6  mov     [rsp+0C8h+var_58], ecx
0x1800d1afa  lea     rdx, _TI1J; pThrowInfo
0x1800d1b01  lea     rcx, [rsp+0C8h+var_58]; pExceptionObject
0x1800d1b06  call    _CxxThrowException_0
0x1800d1b0b  mov     [rsp+0C8h+var_88], edi
0x1800d1b0f  mov     word ptr [rsp+0C8h+var_84], ax
0x1800d1b14  call    cs:__imp_GetLastError
0x1800d1b1a  cmp     eax, 3E5h
0x1800d1b1f  jz      short loc_1800D1B51
0x1800d1b21  mov     eax, [rsp+0C8h+var_88]
0x1800d1b25  mov     [rsp+0C8h+var_88], eax
0x1800d1b29  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d1b2e  mov     [rsp+0C8h+var_88], eax
0x1800d1b32  mov     ecx, 64h ; 'd'
0x1800d1b37  mov     word ptr [rsp+0C8h+var_84+2], cx
0x1800d1b3c  mov     [rsp+0C8h+var_54], eax
0x1800d1b40  lea     rdx, _TI1J; pThrowInfo
0x1800d1b47  lea     rcx, [rsp+0C8h+var_54]; pExceptionObject
0x1800d1b4c  call    _CxxThrowException_0
0x1800d1b51  mov     [rsi+90h], r15b
0x1800d1b58  jmp     short loc_1800D1B71
0x1800d1b5a  jmp     short loc_1800D1B60
0x1800d1b5c  jmp     short loc_1800D1B60
0x1800d1b5e  jmp     short $+2
0x1800d1b60  mov     rsi, [rsp+0C8h+arg_0]
0x1800d1b68  xor     edi, edi
0x1800d1b6a  lea     rbx, WPP_GLOBAL_Control
0x1800d1b71  mov     eax, [rsp+0C8h+var_88]
0x1800d1b75  test    eax, eax
0x1800d1b77  jns     loc_1800D1C0A
0x1800d1b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d1b84  cmp     rcx, rbx
0x1800d1b87  jz      short loc_1800D1BB1
0x1800d1b89  test    byte ptr [rcx+44h], 2
0x1800d1b8d  jz      short loc_1800D1BB1
0x1800d1b8f  cmp     byte ptr [rcx+41h], 2
0x1800d1b93  jb      short loc_1800D1BB1
0x1800d1b95  mov     edx, 0Dh
0x1800d1b9a  mov     r9d, eax
0x1800d1b9d  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d1ba4  mov     rcx, [rcx+38h]
0x1800d1ba8  call    WPP_SF_d
0x1800d1bad  mov     eax, [rsp+0C8h+var_88]
0x1800d1bb1  mov     [rsp+0C8h+var_88], eax
0x1800d1bb5  mov     rcx, [rsi+10h]; hEvent
0x1800d1bb9  call    cs:__imp_SetEvent
0x1800d1bbf  test    eax, eax
0x1800d1bc1  jnz     short loc_1800D1BEC
0x1800d1bc3  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d1bc8  mov     [rsp+0C8h+var_88], eax
0x1800d1bcc  mov     ecx, 74h ; 't'
0x1800d1bd1  mov     word ptr [rsp+0C8h+var_84+2], cx
0x1800d1bd6  mov     [rsp+0C8h+var_50], eax
0x1800d1bda  lea     rdx, _TI1J; pThrowInfo
0x1800d1be1  lea     rcx, [rsp+0C8h+var_50]; pExceptionObject
0x1800d1be6  call    _CxxThrowException_0
0x1800d1bec  mov     [rsp+0C8h+var_88], edi
0x1800d1bf0  mov     ecx, 74h ; 't'
0x1800d1bf5  mov     word ptr [rsp+0C8h+var_84], cx
0x1800d1bfa  mov     [rsp+0C8h+var_88], edi
0x1800d1bfe  mov     [rsp+0C8h+var_88], edi
0x1800d1c02  lea     eax, [rcx+2]
0x1800d1c05  mov     word ptr [rsp+0C8h+var_84], ax
0x1800d1c0a  mov     rax, [rsp+0C8h+arg_8]
0x1800d1c12  mov     rcx, [rax]
0x1800d1c15  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800d1c1c  mov     [rsp+0C8h+arg_0], rcx
0x1800d1c24  lea     rcx, [rsi+8]
0x1800d1c28  lea     rdx, [rsp+0C8h+arg_0]
0x1800d1c30  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(void * const &)
0x1800d1c35  mov     rax, [rsp+0C8h+var_68]
0x1800d1c3a  mov     [rsp+0C8h+var_68], rdi
0x1800d1c3f  mov     [rsp+0C8h+arg_0], rax
0x1800d1c47  lea     rdx, [rsp+0C8h+arg_0]
0x1800d1c4f  lea     rcx, [rsi+18h]
0x1800d1c53  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WAIT@@UWin32ThreadPoolWaitDeleter@@$0A@@@QEAAXAEBQEAU_TP_WAIT@@@Z; EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(_TP_WAIT * const &)
0x1800d1c58  xor     r8d, r8d; pftTimeout
0x1800d1c5b  mov     rdx, [rsi+10h]; h
0x1800d1c5f  mov     rcx, [rsi+18h]; pwa
0x1800d1c63  call    cs:__imp_SetThreadpoolWait
0x1800d1c69  nop
0x1800d1c6a  mov     [rsp+0C8h+arg_0], rdi
0x1800d1c72  lea     rdx, [rsp+0C8h+arg_0]
0x1800d1c7a  lea     rcx, [rsp+0C8h+var_68]
0x1800d1c7f  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WAIT@@UWin32ThreadPoolWaitDeleter@@$0A@@@QEAAXAEBQEAU_TP_WAIT@@@Z; EcsUniqueHandle<_TP_WAIT *,Win32ThreadPoolWaitDeleter,0>::reset(_TP_WAIT * const &)
0x1800d1c84  nop
0x1800d1c85  cmp     [rsp+0C8h+var_40], dil
0x1800d1c8d  jz      short loc_1800D1CA5
0x1800d1c8f  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x1800d1c97  call    cs:__imp_LeaveCriticalSection
0x1800d1c9d  mov     [rsp+0C8h+var_40], dil
0x1800d1ca5  lea     rcx, [rsp+0C8h+var_88]; this
0x1800d1caa  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d1caf  add     rsp, 0A0h
0x1800d1cb6  pop     r15
0x1800d1cb8  pop     r14
0x1800d1cba  pop     rdi
0x1800d1cbb  pop     rsi
0x1800d1cbc  pop     rbx
0x1800d1cbd  retn
```
