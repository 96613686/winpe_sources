# CMSMtoN::Init(int,int,int,int)

- ea: `0x18000e690`
- end: `0x18000ea8e`
- name: `?Init@CMSMtoN@@UEAAHHHHH@Z`
- size: `1022`
- prototype: `__int64 __fastcall(CMSMtoN *this, int, int, int, DWORD Type)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013560`

## callees

- `0x180001968`
- `0x1800019b4`
- `0x18000e690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e87f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e89c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e919`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e936`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e953`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e87f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e89c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e8fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e919`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e936`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000e953`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e80f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e80f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e841`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e841`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000e96f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000e96f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000e9ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000e9e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ea24`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ea5a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000e9ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000e9e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ea24`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000ea5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e966`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e966`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e993`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e9cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ea10`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ea46`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e993`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000e9cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ea10`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ea46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e773`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000e773`
- `mfperfhelper!__imp_ippStaticInit` at `0x18000e6ab`
- `mfperfhelper!__imp_ippStaticInit` at `0x18000e6ab`

## pseudocode

```c
__int64 __fastcall CMSMtoN::Init(CMSMtoN *this, int a2, int a3, int a4, DWORD Type)
{
  unsigned __int64 v9; // rdx
  void *v10; // rcx
  int v11; // esi
  bool v12; // sf
  int v13; // ebx
  void *v15; // rax
  int v16; // ebx
  int v17; // ebp
  int v18; // esi
  unsigned int v19; // eax
  HANDLE EventW; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE Thread; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF
  int Data; // [rsp+98h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+18h] BYREF

  ippStaticInit();
  v10 = (void *)*((_QWORD *)this + 95);
  v11 = -a3;
  *((_DWORD *)this + 177) = a2;
  *((_DWORD *)this + 179) = a4;
  if ( a3 > 0 )
    v11 = a3;
  v12 = (-Type & 0x80000000) != 0;
  v13 = -Type;
  *((_DWORD *)this + 178) = v11;
  if ( v12 )
    v13 = Type;
  *((_DWORD *)this + 180) = v13;
  *((_DWORD *)this + 181) = 0;
  if ( v10 )
  {
    operator delete(v10, v9);
    *((_QWORD *)this + 95) = 0;
  }
  if ( a2 <= a4 )
    a2 = a4;
  if ( v11 > v13 )
    v13 = v11;
  if ( 4 * (v13 + 2LL) * (a2 + 2LL) != 4 * (v13 + 2) * (a2 + 2) )
    return 4294967289LL;
  v15 = operator new[](4 * (v13 + 2) * (a2 + 2));
  *((_QWORD *)this + 95) = v15;
  if ( v15 )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    *((_DWORD *)this + 176) = 1;
    v16 = 4;
    hKey = 0;
    cbData = 4;
    Type = 0;
    Data = 0;
    v17 = 0;
    v18 = 0;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Scrunch\\WMVideo", 0, 0x20019u, &hKey)
      && !RegQueryValueExW(hKey, L"MT_RESIZER", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type - 4 <= 1 )
    {
      v18 = Data;
      v17 = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v17 == 1 && v18 == -1 )
      *((_DWORD *)this + 176) = 1;
    v19 = *((_DWORD *)this + 176);
    if ( v19 < 4 )
    {
      if ( v19 < 2 )
      {
        *((_DWORD *)this + 176) = 1;
        return 1;
      }
      v16 = 2;
    }
    *((_DWORD *)this + 176) = v16;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 1) = EventW;
    if ( EventW )
    {
      v21 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 2) = v21;
      if ( v21 )
      {
        v22 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 3) = v22;
        if ( v22 )
        {
          v23 = CreateEventW(0, 0, 0, 0);
          *((_QWORD *)this + 4) = v23;
          if ( v23 )
          {
            if ( *((_DWORD *)this + 176) != 4 )
              goto LABEL_46;
            v24 = CreateEventW(0, 0, 0, 0);
            *((_QWORD *)this + 5) = v24;
            if ( v24 )
            {
              v25 = CreateEventW(0, 0, 0, 0);
              *((_QWORD *)this + 6) = v25;
              if ( v25 )
              {
                v26 = CreateEventW(0, 0, 0, 0);
                *((_QWORD *)this + 7) = v26;
                if ( v26 )
                {
                  v27 = CreateEventW(0, 0, 0, 0);
                  *((_QWORD *)this + 8) = v27;
                  if ( v27 )
                  {
LABEL_46:
                    CurrentThread = GetCurrentThread();
                    ThreadPriority = GetThreadPriority(CurrentThread);
                    Thread = CreateThread(0, 0, ThreadFunc0, this, 0, (LPDWORD)this + 26);
                    *((_QWORD *)this + 9) = Thread;
                    if ( Thread )
                    {
                      SetThreadPriority(Thread, ThreadPriority);
                      v31 = CreateThread(0, 0, ThreadFunc1, this, 0, (LPDWORD)this + 27);
                      *((_QWORD *)this + 10) = v31;
                      if ( v31 )
                      {
                        SetThreadPriority(v31, ThreadPriority);
                        if ( *((_DWORD *)this + 176) == 4 )
                        {
                          v32 = CreateThread(0, 0, ThreadFunc2, this, 0, (LPDWORD)this + 28);
                          *((_QWORD *)this + 11) = v32;
                          if ( v32 )
                          {
                            SetThreadPriority(v32, ThreadPriority);
                            v33 = CreateThread(0, 0, ThreadFunc3, this, 0, (LPDWORD)this + 29);
                            *((_QWORD *)this + 12) = v33;
                            if ( v33 )
                            {
                              SetThreadPriority(v33, ThreadPriority);
                              return 1;
                            }
                          }
                          return 0;
                        }
                        return 1;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e690  mov     [rsp+arg_18], rbx
0x18000e695  push    rbp
0x18000e696  push    rsi
0x18000e697  push    rdi
0x18000e698  push    r14
0x18000e69a  push    r15
0x18000e69c  sub     rsp, 60h
0x18000e6a0  mov     r14d, r9d
0x18000e6a3  mov     ebx, r8d
0x18000e6a6  mov     ebp, edx
0x18000e6a8  mov     rdi, rcx
0x18000e6ab  call    cs:__imp_ippStaticInit
0x18000e6b1  mov     rcx, [rdi+2F8h]; void *
0x18000e6b8  mov     esi, ebx
0x18000e6ba  neg     esi
0x18000e6bc  mov     [rdi+2C4h], ebp
0x18000e6c2  mov     [rdi+2CCh], r14d
0x18000e6c9  cmovs   esi, ebx
0x18000e6cc  mov     ebx, [rsp+88h+Type]
0x18000e6d3  neg     ebx
0x18000e6d5  mov     [rdi+2C8h], esi
0x18000e6db  cmovs   ebx, [rsp+88h+Type]
0x18000e6e3  xor     r15d, r15d
0x18000e6e6  mov     [rdi+2D0h], ebx
0x18000e6ec  mov     [rdi+2D4h], r15d
0x18000e6f3  test    rcx, rcx
0x18000e6f6  jz      short loc_18000E704
0x18000e6f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e6fd  mov     [rdi+2F8h], r15
0x18000e704  cmp     ebp, r14d
0x18000e707  cmovle  ebp, r14d
0x18000e70b  cmp     esi, ebx
0x18000e70d  cmovg   ebx, esi
0x18000e710  lea     ecx, [rbp+2]
0x18000e713  lea     eax, [rbx+2]
0x18000e716  imul    ecx, eax
0x18000e719  movsxd  rax, ebx
0x18000e71c  add     rax, 2
0x18000e720  shl     ecx, 2
0x18000e723  movsxd  rdx, ecx
0x18000e726  movsxd  rcx, ebp
0x18000e729  add     rcx, 2
0x18000e72d  imul    rcx, rax
0x18000e731  shl     rcx, 2
0x18000e735  cmp     rcx, rdx
0x18000e738  jz      short loc_18000E744
0x18000e73a  mov     eax, 0FFFFFFF9h
0x18000e73f  jmp     loc_18000EA7A
0x18000e744  mov     rcx, rdx; unsigned __int64
0x18000e747  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e74c  mov     [rdi+2F8h], rax
0x18000e753  test    rax, rax
0x18000e756  jz      loc_18000EA78
0x18000e75c  xorps   xmm0, xmm0
0x18000e75f  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x18000e764  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x18000e769  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000e76e  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000e773  call    cs:__imp_GetSystemInfo
0x18000e779  lea     rax, [rsp+88h+hKey]
0x18000e781  mov     dword ptr [rdi+2C0h], 1
0x18000e78b  mov     ebx, 4
0x18000e790  mov     [rsp+88h+phkResult], rax; phkResult
0x18000e795  mov     r9d, 20019h; samDesired
0x18000e79b  mov     [rsp+88h+hKey], r15
0x18000e7a3  xor     r8d, r8d; ulOptions
0x18000e7a6  mov     [rsp+88h+cbData], ebx
0x18000e7ad  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Scrunch\\WMVideo"
0x18000e7b4  mov     [rsp+88h+Type], r15d
0x18000e7bc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e7c3  mov     [rsp+88h+Data], r15d
0x18000e7cb  mov     ebp, r15d
0x18000e7ce  mov     esi, r15d
0x18000e7d1  call    cs:__imp_RegOpenKeyExW
0x18000e7d7  test    eax, eax
0x18000e7d9  jnz     short loc_18000E834
0x18000e7db  mov     rcx, [rsp+88h+hKey]; hKey
0x18000e7e3  lea     rax, [rsp+88h+cbData]
0x18000e7eb  mov     [rsp+88h+lpcbData], rax; lpcbData
0x18000e7f0  lea     r9, [rsp+88h+Type]; lpType
0x18000e7f8  lea     rax, [rsp+88h+Data]
0x18000e800  xor     r8d, r8d; lpReserved
0x18000e803  lea     rdx, aMtResizer; "MT_RESIZER"
0x18000e80a  mov     [rsp+88h+phkResult], rax; lpData
0x18000e80f  call    cs:__imp_RegQueryValueExW
0x18000e815  test    eax, eax
0x18000e817  jnz     short loc_18000E834
0x18000e819  mov     eax, [rsp+88h+Type]
0x18000e820  add     eax, 0FFFFFFFCh
0x18000e823  cmp     eax, 1
0x18000e826  ja      short loc_18000E834
0x18000e828  mov     esi, [rsp+88h+Data]
0x18000e82f  mov     ebp, 1
0x18000e834  mov     rcx, [rsp+88h+hKey]; hKey
0x18000e83c  test    rcx, rcx
0x18000e83f  jz      short loc_18000E847
0x18000e841  call    cs:__imp_RegCloseKey
0x18000e847  cmp     ebp, 1
0x18000e84a  jnz     short loc_18000E857
0x18000e84c  cmp     esi, 0FFFFFFFFh
0x18000e84f  jnz     short loc_18000E857
0x18000e851  mov     [rdi+2C0h], ebp
0x18000e857  mov     eax, [rdi+2C0h]
0x18000e85d  cmp     eax, ebx
0x18000e85f  jnb     short loc_18000E86F
0x18000e861  cmp     eax, 2
0x18000e864  jb      loc_18000EA67
0x18000e86a  mov     ebx, 2
0x18000e86f  xor     r9d, r9d; lpName
0x18000e872  mov     [rdi+2C0h], ebx
0x18000e878  xor     r8d, r8d; bInitialState
0x18000e87b  xor     edx, edx; bManualReset
0x18000e87d  xor     ecx, ecx; lpEventAttributes
0x18000e87f  call    cs:__imp_CreateEventW
0x18000e885  mov     [rdi+8], rax
0x18000e889  test    rax, rax
0x18000e88c  jz      loc_18000EA78
0x18000e892  xor     r9d, r9d; lpName
0x18000e895  xor     r8d, r8d; bInitialState
0x18000e898  xor     edx, edx; bManualReset
0x18000e89a  xor     ecx, ecx; lpEventAttributes
0x18000e89c  call    cs:__imp_CreateEventW
0x18000e8a2  mov     [rdi+10h], rax
0x18000e8a6  test    rax, rax
0x18000e8a9  jz      loc_18000EA78
0x18000e8af  xor     r9d, r9d; lpName
0x18000e8b2  xor     r8d, r8d; bInitialState
0x18000e8b5  xor     edx, edx; bManualReset
0x18000e8b7  xor     ecx, ecx; lpEventAttributes
0x18000e8b9  call    cs:__imp_CreateEventW
0x18000e8bf  mov     [rdi+18h], rax
0x18000e8c3  test    rax, rax
0x18000e8c6  jz      loc_18000EA78
0x18000e8cc  xor     r9d, r9d; lpName
0x18000e8cf  xor     r8d, r8d; bInitialState
0x18000e8d2  xor     edx, edx; bManualReset
0x18000e8d4  xor     ecx, ecx; lpEventAttributes
0x18000e8d6  call    cs:__imp_CreateEventW
0x18000e8dc  mov     [rdi+20h], rax
0x18000e8e0  test    rax, rax
0x18000e8e3  jz      loc_18000EA78
0x18000e8e9  cmp     dword ptr [rdi+2C0h], 4
0x18000e8f0  jnz     short loc_18000E966
0x18000e8f2  xor     r9d, r9d; lpName
0x18000e8f5  xor     r8d, r8d; bInitialState
0x18000e8f8  xor     edx, edx; bManualReset
0x18000e8fa  xor     ecx, ecx; lpEventAttributes
0x18000e8fc  call    cs:__imp_CreateEventW
0x18000e902  mov     [rdi+28h], rax
0x18000e906  test    rax, rax
0x18000e909  jz      loc_18000EA78
0x18000e90f  xor     r9d, r9d; lpName
0x18000e912  xor     r8d, r8d; bInitialState
0x18000e915  xor     edx, edx; bManualReset
0x18000e917  xor     ecx, ecx; lpEventAttributes
0x18000e919  call    cs:__imp_CreateEventW
0x18000e91f  mov     [rdi+30h], rax
0x18000e923  test    rax, rax
0x18000e926  jz      loc_18000EA78
0x18000e92c  xor     r9d, r9d; lpName
0x18000e92f  xor     r8d, r8d; bInitialState
0x18000e932  xor     edx, edx; bManualReset
0x18000e934  xor     ecx, ecx; lpEventAttributes
0x18000e936  call    cs:__imp_CreateEventW
0x18000e93c  mov     [rdi+38h], rax
0x18000e940  test    rax, rax
0x18000e943  jz      loc_18000EA78
0x18000e949  xor     r9d, r9d; lpName
0x18000e94c  xor     r8d, r8d; bInitialState
0x18000e94f  xor     edx, edx; bManualReset
0x18000e951  xor     ecx, ecx; lpEventAttributes
0x18000e953  call    cs:__imp_CreateEventW
0x18000e959  mov     [rdi+40h], rax
0x18000e95d  test    rax, rax
0x18000e960  jz      loc_18000EA78
0x18000e966  call    cs:__imp_GetCurrentThread
0x18000e96c  mov     rcx, rax; hThread
0x18000e96f  call    cs:__imp_GetThreadPriority
0x18000e975  lea     rcx, [rdi+68h]
0x18000e979  mov     r9, rdi; lpParameter
0x18000e97c  mov     [rsp+88h+lpcbData], rcx; lpThreadId
0x18000e981  lea     r8, ?ThreadFunc0@@YAX_K@Z; lpStartAddress
0x18000e988  xor     ecx, ecx; lpThreadAttributes
0x18000e98a  mov     dword ptr [rsp+88h+phkResult], r15d; dwCreationFlags
0x18000e98f  xor     edx, edx; dwStackSize
0x18000e991  mov     ebx, eax
0x18000e993  call    cs:__imp_CreateThread
0x18000e999  mov     [rdi+48h], rax
0x18000e99d  test    rax, rax
0x18000e9a0  jz      loc_18000EA78
0x18000e9a6  mov     edx, ebx; nPriority
0x18000e9a8  mov     rcx, rax; hThread
0x18000e9ab  call    cs:__imp_SetThreadPriority
0x18000e9b1  lea     rax, [rdi+6Ch]
0x18000e9b5  mov     r9, rdi; lpParameter
0x18000e9b8  mov     [rsp+88h+lpcbData], rax; lpThreadId
0x18000e9bd  lea     r8, ?ThreadFunc1@@YAX_K@Z; lpStartAddress
0x18000e9c4  xor     edx, edx; dwStackSize
0x18000e9c6  mov     dword ptr [rsp+88h+phkResult], r15d; dwCreationFlags
0x18000e9cb  xor     ecx, ecx; lpThreadAttributes
0x18000e9cd  call    cs:__imp_CreateThread
0x18000e9d3  mov     [rdi+50h], rax
0x18000e9d7  test    rax, rax
0x18000e9da  jz      loc_18000EA78
0x18000e9e0  mov     edx, ebx; nPriority
0x18000e9e2  mov     rcx, rax; hThread
0x18000e9e5  call    cs:__imp_SetThreadPriority
0x18000e9eb  cmp     dword ptr [rdi+2C0h], 4
0x18000e9f2  jnz     short loc_18000EA71
0x18000e9f4  lea     rax, [rdi+70h]
0x18000e9f8  mov     r9, rdi; lpParameter
0x18000e9fb  mov     [rsp+88h+lpcbData], rax; lpThreadId
0x18000ea00  lea     r8, ?ThreadFunc2@@YAX_K@Z; lpStartAddress
0x18000ea07  xor     edx, edx; dwStackSize
0x18000ea09  mov     dword ptr [rsp+88h+phkResult], r15d; dwCreationFlags
0x18000ea0e  xor     ecx, ecx; lpThreadAttributes
0x18000ea10  call    cs:__imp_CreateThread
0x18000ea16  mov     [rdi+58h], rax
0x18000ea1a  test    rax, rax
0x18000ea1d  jz      short loc_18000EA78
0x18000ea1f  mov     edx, ebx; nPriority
0x18000ea21  mov     rcx, rax; hThread
0x18000ea24  call    cs:__imp_SetThreadPriority
0x18000ea2a  lea     rax, [rdi+74h]
0x18000ea2e  mov     r9, rdi; lpParameter
0x18000ea31  mov     [rsp+88h+lpcbData], rax; lpThreadId
0x18000ea36  lea     r8, ?ThreadFunc3@@YAX_K@Z; lpStartAddress
0x18000ea3d  xor     edx, edx; dwStackSize
0x18000ea3f  mov     dword ptr [rsp+88h+phkResult], r15d; dwCreationFlags
0x18000ea44  xor     ecx, ecx; lpThreadAttributes
0x18000ea46  call    cs:__imp_CreateThread
0x18000ea4c  mov     [rdi+60h], rax
0x18000ea50  test    rax, rax
0x18000ea53  jz      short loc_18000EA78
0x18000ea55  mov     edx, ebx; nPriority
0x18000ea57  mov     rcx, rax; hThread
0x18000ea5a  call    cs:__imp_SetThreadPriority
0x18000ea60  mov     eax, 1
0x18000ea65  jmp     short loc_18000EA7A
0x18000ea67  mov     dword ptr [rdi+2C0h], 1
0x18000ea71  mov     eax, 1
0x18000ea76  jmp     short loc_18000EA7A
0x18000ea78  xor     eax, eax
0x18000ea7a  mov     rbx, [rsp+88h+arg_18]
0x18000ea82  add     rsp, 60h
0x18000ea86  pop     r15
0x18000ea88  pop     r14
0x18000ea8a  pop     rdi
0x18000ea8b  pop     rsi
0x18000ea8c  pop     rbp
0x18000ea8d  retn
```
