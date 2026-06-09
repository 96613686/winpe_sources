# HandleManagerGoUnsyncd(void)

- ea: `0x180010e24`
- end: `0x18001111a`
- name: `?HandleManagerGoUnsyncd@@YAJXZ`
- size: `758`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000f150`

## callees

- `0x18000a7e0`
- `0x180010748`
- `0x180010e24`
- `0x1800127a0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002a6e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800110fa`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800110fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800110b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800110b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110c6`

## string_xrefs

- `0x180010e61`: `WaitForMultipleObjects: handle ClockDisplnThread is NULL`
- `0x180010fea`: `Logging warning: The time service has not synchronized the system time for %ld seconds because none of the time service providers provided a usable time stamp. The time service will not update the local system time until it is able to synchronize with a time source. If the local system is configured to act as a time server for clients, it will stop advertising as a time source to clients after %ld seconds. The time service will continue to retry and sync time with its time sources. Check system `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int HandleManagerGoUnsyncd(void)
{
  signed int result; // eax
  unsigned int v1; // edi
  __int64 Value; // rax
  unsigned __int64 v3; // r14
  unsigned __int64 v4; // rbp
  __int64 v5; // rax
  __int64 v6; // rdx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // kr00_8
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  __int64 v11; // r9
  __int64 v12; // r10
  __int64 v13; // rdx
  HANDLE Handles; // [rsp+40h] [rbp-48h] BYREF
  HANDLE v15; // [rsp+48h] [rbp-40h]
  unsigned __int64 v16; // [rsp+90h] [rbp+8h] BYREF

  Handles = qword_1800A36D8;
  v16 = 0;
  v15 = hThread;
  if ( hThread )
  {
    v1 = 3 << (*((_DWORD *)qword_1800A42F0 + 26) - 1);
    if ( v1 < 0x15180 )
      v1 = 86400;
    AccurateGetTickCount(&v16);
    Value = asint64::getValue((asint64 *)&dword_1800A45C8);
    v3 = v16;
    v4 = (v16 - Value) / 0x3E8;
    v5 = asint64::getValue((asint64 *)&dword_1800A45D4);
    v6 = ((v3 - v5) * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    v7 = (v6 + ((v3 - v5 - v6) >> 1)) >> 9;
    v8 = qword_1800A4330;
    qword_1800A4330 = 0;
    v9 = v8 / 0x989680;
    if ( (unsigned __int8)FileLogAllowEntry(64) )
    {
      asint64::getValue((asint64 *)&dword_1800A45D4);
      asint64::getValue((asint64 *)&dword_1800A45C8);
      v10 = asint64::getValue((asint64 *)&dword_1800A382C);
      FileLogAdd(
        L"HandleManagerGoUnsyncd: TN:%I64us::: LST:%I64us TSLTS:%lus, LRT:%I64us TSLRS:%lus, LUT:%I64us TSLUS:%lds\n",
        v3 / 0x3E8,
        v10 / 0x3E8,
        (unsigned int)v9,
        v11,
        v4,
        v12,
        v7,
        Handles,
        v15);
    }
    if ( (dword_1800A45B8 & 2) == 0 )
      goto LABEL_15;
    if ( (unsigned __int8)FileLogAllowEntry(17) )
      FileLogAdd(
        L"Logging warning: The time service has not synchronized the system time for %ld seconds because none of the time "
         "service providers provided a usable time stamp. The time service will not update the local system time until it"
         " is able to synchronize with a time source. If the local system is configured to act as a time server for clien"
         "ts, it will stop advertising as a time source to clients after %ld seconds. The time service will continue to r"
         "etry and sync time with its time sources. Check system event log for other W32time events for more details. Run"
         " 'w32tm /resync' to force an instant time synchronization.\n",
        (unsigned int)v9,
        (unsigned int)v7 < v1 ? v1 - (unsigned int)v7 : 0);
    result = LogEvent(&_W32TimeRegistrationHandle, W32TIME_EVENT_TIME_SOURCE_NONE, L"dd", (unsigned int)v9);
    if ( result >= 0 )
    {
LABEL_15:
      if ( byte_1800A45A1
        && (unsigned int)v9 >= *((_DWORD *)qword_1800A42F0 + 27)
        && (unsigned int)v4 >= *((_DWORD *)qword_1800A42F0 + 27) )
      {
        if ( (unsigned __int8)FileLogAllowEntry(17) )
          FileLogAdd(L"Decreasing the poll interval to the lowest value and requesting providers to rediscover time sources.\n");
        if ( dword_1800A381C != *((_DWORD *)qword_1800A42F0 + 25) )
        {
          dword_1800A381C = *((_DWORD *)qword_1800A42F0 + 25);
          byte_1800A3AB8 = 1;
        }
        LOBYTE(v13) = 1;
        HandleManagerNetTopoChange(0, v13);
      }
      if ( (unsigned int)v7 >= v1
        && ((dword_1800A3AA8 = 4, !SetEvent(qword_1800A36D0))
         || WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0) == -1) )
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
      else
      {
        return 0;
      }
    }
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"WaitForMultipleObjects: handle ClockDisplnThread is NULL");
    return -2147467260;
  }
  return result;
}

```

## disassembly

```asm
0x180010e24  mov     r11, rsp
0x180010e27  push    rbx
0x180010e28  push    rbp
0x180010e29  push    rsi
0x180010e2a  push    rdi
0x180010e2b  push    r13
0x180010e2d  push    r14
0x180010e2f  sub     rsp, 58h
0x180010e33  mov     rax, cs:qword_1800A36D8
0x180010e3a  mov     [r11-48h], rax
0x180010e3e  mov     rax, cs:hThread
0x180010e45  mov     qword ptr [r11+8], 0
0x180010e4d  mov     [r11-40h], rax
0x180010e51  test    rax, rax
0x180010e54  jnz     short loc_180010E77
0x180010e56  xor     ecx, ecx
0x180010e58  call    FileLogAllowEntry
0x180010e5d  test    al, al
0x180010e5f  jz      short loc_180010E6D
0x180010e61  lea     rcx, aWaitformultipl; "WaitForMultipleObjects: handle ClockDis"...
0x180010e68  call    FileLogAdd
0x180010e6d  mov     eax, 80004004h
0x180010e72  jmp     loc_18001110C
0x180010e77  mov     rax, cs:qword_1800A42F0
0x180010e7e  mov     edi, 3
0x180010e83  mov     ecx, [rax+68h]
0x180010e86  mov     eax, 15180h
0x180010e8b  dec     ecx
0x180010e8d  shl     edi, cl
0x180010e8f  lea     rcx, [rsp+88h+arg_0]; unsigned __int64 *
0x180010e97  cmp     edi, eax
0x180010e99  cmovb   edi, eax
0x180010e9c  call    ?AccurateGetTickCount@@YAXPEA_K@Z; AccurateGetTickCount(unsigned __int64 *)
0x180010ea1  lea     rcx, dword_1800A45C8; this
0x180010ea8  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x180010ead  mov     r14, [rsp+88h+arg_0]
0x180010eb5  lea     rcx, dword_1800A45D4; this
0x180010ebc  mov     rbp, r14
0x180010ebf  mov     r13, 624DD2F1A9FBE77h
0x180010ec9  sub     rbp, rax
0x180010ecc  mov     rax, r13
0x180010ecf  mul     rbp
0x180010ed2  sub     rbp, rdx
0x180010ed5  shr     rbp, 1
0x180010ed8  add     rbp, rdx
0x180010edb  shr     rbp, 9
0x180010edf  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x180010ee4  mov     rbx, r14
0x180010ee7  mov     ecx, 40h ; '@'
0x180010eec  sub     rbx, rax
0x180010eef  mov     rax, r13
0x180010ef2  mul     rbx
0x180010ef5  mov     rax, 0D6BF94D5E57A42BDh
0x180010eff  sub     rbx, rdx
0x180010f02  shr     rbx, 1
0x180010f05  add     rbx, rdx
0x180010f08  mul     cs:qword_1800A4330
0x180010f0f  shr     rbx, 9
0x180010f13  mov     rsi, rdx
0x180010f16  mov     cs:qword_1800A4330, 0
0x180010f21  shr     rsi, 17h
0x180010f25  call    FileLogAllowEntry
0x180010f2a  test    al, al
0x180010f2c  jz      loc_180010FCC
0x180010f32  lea     rcx, dword_1800A45D4; this
0x180010f39  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x180010f3e  mov     r10, rax
0x180010f41  lea     rcx, dword_1800A45C8; this
0x180010f48  mov     rax, r13
0x180010f4b  mul     r10
0x180010f4e  sub     r10, rdx
0x180010f51  shr     r10, 1
0x180010f54  add     r10, rdx
0x180010f57  shr     r10, 9
0x180010f5b  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x180010f60  mov     r9, rax
0x180010f63  lea     rcx, dword_1800A382C; this
0x180010f6a  mov     rax, r13
0x180010f6d  mul     r9
0x180010f70  sub     r9, rdx
0x180010f73  shr     r9, 1
0x180010f76  add     r9, rdx
0x180010f79  shr     r9, 9
0x180010f7d  call    ?getValue@asint64@@QEAA_JXZ; asint64::getValue(void)
0x180010f82  mov     r8, rax
0x180010f85  mov     [rsp+88h+var_50], ebx
0x180010f89  mov     [rsp+88h+var_58], r10
0x180010f8e  lea     rcx, aHandlemanagerg; "HandleManagerGoUnsyncd: TN:%I64us::: LS"...
0x180010f95  mov     rax, r13
0x180010f98  mov     [rsp+88h+var_60], ebp
0x180010f9c  mul     r8
0x180010f9f  mov     qword ptr [rsp+88h+bAlertable], r9
0x180010fa4  mov     rax, r13
0x180010fa7  sub     r8, rdx
0x180010faa  mov     r9d, esi
0x180010fad  shr     r8, 1
0x180010fb0  add     r8, rdx
0x180010fb3  mul     r14
0x180010fb6  shr     r8, 9
0x180010fba  sub     r14, rdx
0x180010fbd  shr     r14, 1
0x180010fc0  add     rdx, r14
0x180010fc3  shr     rdx, 9
0x180010fc7  call    FileLogAdd
0x180010fcc  mov     eax, cs:dword_1800A45B8
0x180010fd2  mov     r14d, 11h
0x180010fd8  test    al, 2
0x180010fda  jz      short loc_180011035
0x180010fdc  mov     ecx, r14d
0x180010fdf  call    FileLogAllowEntry
0x180010fe4  test    al, al
0x180010fe6  jz      short loc_180011002
0x180010fe8  mov     eax, edi
0x180010fea  lea     rcx, aLoggingWarning_32; "Logging warning: The time service has n"...
0x180010ff1  sub     eax, ebx
0x180010ff3  mov     edx, esi
0x180010ff5  cmp     ebx, edi
0x180010ff7  sbb     r8d, r8d
0x180010ffa  and     r8d, eax
0x180010ffd  call    FileLogAdd
0x180011002  mov     ecx, edi
0x180011004  lea     r8, aDd; "dd"
0x18001100b  sub     ecx, ebx
0x18001100d  lea     rdx, W32TIME_EVENT_TIME_SOURCE_NONE
0x180011014  cmp     ebx, edi
0x180011016  mov     r9d, esi
0x180011019  sbb     eax, eax
0x18001101b  and     eax, ecx
0x18001101d  lea     rcx, ?_W32TimeRegistrationHandle@@3_KA; unsigned __int64 _W32TimeRegistrationHandle
0x180011024  mov     [rsp+88h+bAlertable], eax
0x180011028  call    LogEvent
0x18001102d  test    eax, eax
0x18001102f  js      loc_18001110C
0x180011035  cmp     cs:byte_1800A45A1, 0
0x18001103c  jz      short loc_1800110A1
0x18001103e  mov     rax, cs:qword_1800A42F0
0x180011045  cmp     esi, [rax+6Ch]
0x180011048  jb      short loc_1800110A1
0x18001104a  cmp     ebp, [rax+6Ch]
0x18001104d  jb      short loc_1800110A1
0x18001104f  mov     ecx, r14d
0x180011052  call    FileLogAllowEntry
0x180011057  test    al, al
0x180011059  jz      short loc_180011067
0x18001105b  lea     rcx, aDecreasingTheP; "Decreasing the poll interval to the low"...
0x180011062  call    FileLogAdd
0x180011067  mov     rax, cs:qword_1800A42F0
0x18001106e  mov     ecx, [rax+64h]
0x180011071  mov     eax, cs:dword_1800A381C
0x180011077  cmp     eax, ecx
0x180011079  jz      short loc_180011092
0x18001107b  mov     rax, cs:qword_1800A42F0
0x180011082  mov     ecx, [rax+64h]
0x180011085  mov     cs:dword_1800A381C, ecx
0x18001108b  mov     cs:byte_1800A3AB8, 1
0x180011092  mov     r8d, 3
0x180011098  mov     dl, 1
0x18001109a  xor     ecx, ecx
0x18001109c  call    ?HandleManagerNetTopoChange@@YAJPEA_K_NW4_NetTopoChangeSource@@@Z; HandleManagerNetTopoChange(unsigned __int64 *,bool,_NetTopoChangeSource)
0x1800110a1  cmp     ebx, edi
0x1800110a3  jb      short loc_18001110A
0x1800110a5  mov     rcx, cs:qword_1800A36D0; hEvent
0x1800110ac  mov     cs:dword_1800A3AA8, 4
0x1800110b6  call    cs:__imp_SetEvent
0x1800110bd  nop     dword ptr [rax+rax+00h]
0x1800110c2  test    eax, eax
0x1800110c4  jnz     short loc_1800110E0
0x1800110c6  call    cs:__imp_GetLastError
0x1800110cd  nop     dword ptr [rax+rax+00h]
0x1800110d2  test    eax, eax
0x1800110d4  jle     short loc_18001110C
0x1800110d6  movzx   eax, ax
0x1800110d9  or      eax, 80070000h
0x1800110de  jmp     short loc_18001110C
0x1800110e0  xor     r8d, r8d; bWaitAll
0x1800110e3  mov     [rsp+88h+bAlertable], 0; bAlertable
0x1800110eb  or      ebx, 0FFFFFFFFh
0x1800110ee  lea     rdx, [rsp+88h+Handles]; lpHandles
0x1800110f3  mov     r9d, ebx; dwMilliseconds
0x1800110f6  lea     ecx, [r8+2]; nCount
0x1800110fa  call    cs:__imp_WaitForMultipleObjectsEx
0x180011101  nop     dword ptr [rax+rax+00h]
0x180011106  cmp     eax, ebx
0x180011108  jz      short loc_1800110C6
0x18001110a  xor     eax, eax
0x18001110c  add     rsp, 58h
0x180011110  pop     r14
0x180011112  pop     r13
0x180011114  pop     rdi
0x180011115  pop     rsi
0x180011116  pop     rbp
0x180011117  pop     rbx
0x180011118  retn
```
