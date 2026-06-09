# OsEventsWriteTimestamp

- ea: `0x18005f298`
- end: `0x18005f583`
- name: `OsEventsWriteTimestamp`
- size: `747`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005eac4`
- `0x18005ef80`

## callees

- `0x18001c320`
- `0x18002de70`
- `0x18005f298`
- `0x18005f58c`
- `0x18005f634`
- `0x18005ff90`
- `0x180092008`
- `0x180092ee4`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x18005f3d6`
- `ntdll!RtlComputeCrc32` at `0x18005f3d6`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18005f475`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18005f475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f559`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005f39a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005f39a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005f418`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005f418`

## pseudocode

```c
void __fastcall OsEventsWriteTimestamp(unsigned __int8 a1)
{
  int v1; // r15d
  void *v2; // rbx
  int v3; // ebp
  unsigned int v4; // r14d
  unsigned __int64 v5; // rax
  struct _SYSTEMTIME *v6; // rdi
  int v7; // eax
  ULONG v8; // eax
  __int64 v9; // rcx
  DWORD LastError; // eax
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+10h] BYREF
  LARGE_INTEGER DueTime; // [rsp+70h] [rbp+18h] BYREF

  v1 = a1;
  if ( !g_bHeartBeatsDisabled )
  {
    v2 = 0;
    DueTime.QuadPart = 0;
    dword_18010F6B0 = ((_BYTE)dword_18010F6B0 - 1) & 1;
    OsEventsOpenHeartBeatFiles();
    if ( qword_180111578[2 * (unsigned int)dword_18010F6B0] != -1
      && qword_180111578[2 * (unsigned int)dword_18010F6B0] != 0 )
    {
      v3 = 0;
      if ( !BYTE4(qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1]) )
        v3 = 3 * LODWORD(qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1]);
      v4 = qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1];
      v5 = (unsigned __int64)MIDL_user_allocate(v3 + 2 * v4 + 52 - (v3 + v4 + 52) % v4);
      v2 = (void *)v5;
      if ( v5 )
      {
        v6 = (struct _SYSTEMTIME *)(LODWORD(qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1])
                                  - v5 % LODWORD(qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1])
                                  + v5);
        GetSystemTime(v6);
        v7 = OsEventsSystemUptime(&v6[2].wHour);
        *(_DWORD *)&v6[1].wHour = dword_180111940;
        *(_DWORD *)&v6[1].wSecond = dword_180111944;
        *(_DWORD *)&v6[2].wYear = dword_18011193C;
        *(_DWORD *)&v6[1].wYear = v7;
        *(_DWORD *)&v6[1].wDayOfWeek = v1;
        v8 = RtlComputeCrc32(0, (PUCHAR)v6, 0x30u);
        v9 = (unsigned int)dword_18010F6B0;
        *(_DWORD *)&v6[3].wYear = v8;
        NumberOfBytesWritten = 0;
        if ( WriteFile((HANDLE)qword_180111578[2 * v9], v6, v3 + v4 - (v3 + 52) % v4 + 52, &NumberOfBytesWritten, 0) )
        {
          BYTE4(qword_180111578[2 * (unsigned int)dword_18010F6B0 + 1]) = 1;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, LastError);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
      }
    }
    DueTime.QuadPart = -10000000LL * (unsigned int)dword_180111940;
    if ( !SetWaitableTimer(qword_180111550, &DueTime, 1000 * dword_180111940, 0, 0, 0)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v11);
    }
    if ( !g_bHeartBeatsDisabled && (unsigned int)dword_18010F6B0 < 2 )
      tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180111578[2 * (unsigned int)dword_18010F6B0], 0);
    if ( v2 )
      operator delete(v2);
  }
}

```

## disassembly

```asm
0x18005f298  mov     [rsp+arg_0], rbx
0x18005f29d  mov     [rsp+arg_18], rbp
0x18005f2a2  push    rsi
0x18005f2a3  push    rdi
0x18005f2a4  push    r13
0x18005f2a6  push    r14
0x18005f2a8  push    r15
0x18005f2aa  sub     rsp, 30h
0x18005f2ae  cmp     cs:?g_bHeartBeatsDisabled@@3_NA, 0; bool g_bHeartBeatsDisabled
0x18005f2b5  movzx   r15d, cl
0x18005f2b9  jnz     loc_18005F499
0x18005f2bf  mov     ecx, cs:dword_18010F6B0
0x18005f2c5  xor     ebx, ebx
0x18005f2c7  dec     ecx
0x18005f2c9  mov     qword ptr [rsp+58h+DueTime], rbx
0x18005f2ce  and     ecx, 1
0x18005f2d1  mov     cs:dword_18010F6B0, ecx
0x18005f2d7  call    OsEventsOpenHeartBeatFiles
0x18005f2dc  mov     ecx, cs:dword_18010F6B0
0x18005f2e2  lea     r13, qword_180111578
0x18005f2e9  add     rcx, rcx
0x18005f2ec  lea     rdi, WPP_GLOBAL_Control
0x18005f2f3  mov     rax, [r13+rcx*8+0]
0x18005f2f8  inc     rax
0x18005f2fb  cmp     rax, 1
0x18005f2ff  jbe     loc_18005F43C
0x18005f305  xor     ebp, ebp
0x18005f307  cmp     [r13+rcx*8+0Ch], bl
0x18005f30c  jz      loc_18005F4CD
0x18005f312  mov     r14d, [r13+rcx*8+8]
0x18005f317  xor     edx, edx
0x18005f319  lea     eax, [r14+34h]
0x18005f31d  add     eax, ebp
0x18005f31f  lea     ecx, ds:34h[r14*2]
0x18005f327  div     r14d
0x18005f32a  sub     ecx, edx
0x18005f32c  add     ecx, ebp; size
0x18005f32e  call    MIDL_user_allocate
0x18005f333  mov     rbx, rax
0x18005f336  test    rax, rax
0x18005f339  jnz     short loc_18005F37A
0x18005f33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f342  cmp     rcx, rdi
0x18005f345  jz      loc_18005F43C
0x18005f34b  test    dword ptr [rcx+1Ch], 4000h
0x18005f352  jz      loc_18005F43C
0x18005f358  cmp     byte ptr [rcx+19h], 2
0x18005f35c  jb      loc_18005F43C
0x18005f362  mov     rcx, [rcx+10h]
0x18005f366  lea     edx, [rax+24h]
0x18005f369  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f370  call    WPP_SF_
0x18005f375  jmp     loc_18005F43C
0x18005f37a  mov     eax, cs:dword_18010F6B0
0x18005f380  xor     edx, edx
0x18005f382  add     rax, rax
0x18005f385  mov     ecx, [r13+rax*8+8]
0x18005f38a  mov     rax, rbx
0x18005f38d  div     rcx
0x18005f390  sub     rcx, rdx
0x18005f393  lea     rdi, [rcx+rbx]
0x18005f397  mov     rcx, rdi; lpSystemTime
0x18005f39a  call    cs:__imp_GetSystemTime
0x18005f3a0  lea     rcx, [rdi+28h]
0x18005f3a4  call    OsEventsSystemUptime
0x18005f3a9  mov     ecx, cs:dword_180111940
0x18005f3af  mov     r8d, 30h ; '0'; Length
0x18005f3b5  mov     [rdi+18h], ecx
0x18005f3b8  mov     rdx, rdi; Buffer
0x18005f3bb  mov     ecx, cs:dword_180111944
0x18005f3c1  mov     [rdi+1Ch], ecx
0x18005f3c4  mov     ecx, cs:dword_18011193C
0x18005f3ca  mov     [rdi+20h], ecx
0x18005f3cd  xor     ecx, ecx; InitialCrc
0x18005f3cf  mov     [rdi+10h], eax
0x18005f3d2  mov     [rdi+14h], r15d
0x18005f3d6  call    cs:__imp_RtlComputeCrc32
0x18005f3dc  mov     ecx, cs:dword_18010F6B0
0x18005f3e2  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005f3e7  mov     [rdi+30h], eax
0x18005f3ea  xor     edx, edx
0x18005f3ec  lea     eax, [rbp+34h]
0x18005f3ef  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18005f3f7  div     r14d
0x18005f3fa  add     rcx, rcx
0x18005f3fd  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18005f406  sub     r14d, edx
0x18005f409  mov     rdx, rdi; lpBuffer
0x18005f40c  mov     rcx, [r13+rcx*8+0]; hFile
0x18005f411  lea     r8d, [r14+34h]
0x18005f415  add     r8d, ebp; nNumberOfBytesToWrite
0x18005f418  call    cs:__imp_WriteFile
0x18005f41e  test    eax, eax
0x18005f420  jz      loc_18005F4DA
0x18005f426  mov     eax, cs:dword_18010F6B0
0x18005f42c  lea     rdi, WPP_GLOBAL_Control
0x18005f433  add     rax, rax
0x18005f436  mov     byte ptr [r13+rax*8+0Ch], 1
0x18005f43c  mov     edx, cs:dword_180111940
0x18005f442  xor     r9d, r9d; pfnCompletionRoutine
0x18005f445  imul    rcx, rdx, 0FFFFFFFFFF676980h
0x18005f44c  imul    r8d, edx, 3E8h; lPeriod
0x18005f453  mov     [rsp+58h+fResume], 0; fResume
0x18005f45b  lea     rdx, [rsp+58h+DueTime]; lpDueTime
0x18005f460  mov     qword ptr [rsp+58h+DueTime], rcx
0x18005f465  mov     rcx, cs:qword_180111550; hTimer
0x18005f46c  mov     [rsp+58h+lpOverlapped], 0; lpArgToCompletionRoutine
0x18005f475  call    cs:__imp_SetWaitableTimer
0x18005f47b  test    eax, eax
0x18005f47d  jz      loc_18005F532
0x18005f483  cmp     cs:?g_bHeartBeatsDisabled@@3_NA, 0; bool g_bHeartBeatsDisabled
0x18005f48a  jz      short loc_18005F4B0
0x18005f48c  test    rbx, rbx
0x18005f48f  jz      short loc_18005F499
0x18005f491  mov     rcx, rbx; void *
0x18005f494  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005f499  mov     rbx, [rsp+58h+arg_0]
0x18005f49e  mov     rbp, [rsp+58h+arg_18]
0x18005f4a3  add     rsp, 30h
0x18005f4a7  pop     r15
0x18005f4a9  pop     r14
0x18005f4ab  pop     r13
0x18005f4ad  pop     rdi
0x18005f4ae  pop     rsi
0x18005f4af  retn
0x18005f4b0  mov     eax, cs:dword_18010F6B0
0x18005f4b6  cmp     eax, 2
0x18005f4b9  jnb     short loc_18005F48C
0x18005f4bb  mov     ecx, eax
0x18005f4bd  xor     edx, edx
0x18005f4bf  shl     rcx, 4
0x18005f4c3  add     rcx, r13
0x18005f4c6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005f4cb  jmp     short loc_18005F48C
0x18005f4cd  mov     eax, [r13+rcx*8+8]
0x18005f4d2  lea     ebp, [rax+rax*2]
0x18005f4d5  jmp     loc_18005F312
0x18005f4da  mov     rax, cs:WPP_GLOBAL_Control
0x18005f4e1  lea     rdi, WPP_GLOBAL_Control
0x18005f4e8  cmp     rax, rdi
0x18005f4eb  jz      loc_18005F43C
0x18005f4f1  test    dword ptr [rax+1Ch], 4000h
0x18005f4f8  jz      loc_18005F43C
0x18005f4fe  cmp     byte ptr [rax+19h], 2
0x18005f502  jb      loc_18005F43C
0x18005f508  call    cs:__imp_GetLastError
0x18005f50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f515  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f51c  mov     edx, 25h ; '%'
0x18005f521  mov     r9d, eax
0x18005f524  mov     rcx, [rcx+10h]
0x18005f528  call    WPP_SF_d
0x18005f52d  jmp     loc_18005F43C
0x18005f532  mov     rax, cs:WPP_GLOBAL_Control
0x18005f539  cmp     rax, rdi
0x18005f53c  jz      loc_18005F483
0x18005f542  test    dword ptr [rax+1Ch], 4000h
0x18005f549  jz      loc_18005F483
0x18005f54f  cmp     byte ptr [rax+19h], 2
0x18005f553  jb      loc_18005F483
0x18005f559  call    cs:__imp_GetLastError
0x18005f55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f566  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005f56d  mov     edx, 26h ; '&'
0x18005f572  mov     r9d, eax
0x18005f575  mov     rcx, [rcx+10h]
0x18005f579  call    WPP_SF_d
0x18005f57e  jmp     loc_18005F483
```
