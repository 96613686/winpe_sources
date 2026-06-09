# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180097e84`
- end: `0x180098176`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002054c`

## callees

- `0x180004bb4`
- `0x180009b40`
- `0x180009bb4`
- `0x18000dad0`
- `0x18000ea64`
- `0x18001fe24`
- `0x180097e84`
- `0x1800992a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800980a1`
- `ntdll!NtQueryInformationProcess` at `0x180097efd`
- `ntdll!NtQueryInformationProcess` at `0x180097efd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f49`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f88`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097ff7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f49`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097f88`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180097ff7`

## pseudocode

```c
__int64 __fastcall UtilGetProcessCommandLine(HANDLE hProcess, __int64 a2)
{
  NTSTATUS v4; // eax
  SIZE_T v5; // rbx
  unsigned int v6; // ebx
  signed int LastError; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  LPCVOID lpBaseAddress[2]; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpBuffer[2]; // [rsp+40h] [rbp-9h] BYREF
  _WORD v15[8]; // [rsp+50h] [rbp+7h] BYREF
  _OWORD ProcessInformation[4]; // [rsp+60h] [rbp+17h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+67h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+C0h] [rbp+77h] BYREF
  __int64 Buffer; // [rsp+C8h] [rbp+7Fh] BYREF

  Buffer = 0;
  lpBuffer[0] = v15;
  lpBuffer[1] = v15;
  v15[0] = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  memset(ProcessInformation, 0, 48);
  *(_OWORD *)lpBaseAddress = 0;
  if ( hProcess && a2 )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength);
    if ( v4 < 0 || ReturnLength != 48 || !*((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_QWORD *)&ProcessInformation[0] + 1),
          ReturnLength,
          (unsigned int)v4,
          ReturnLength,
          *((_QWORD *)&ProcessInformation[0] + 1));
      v6 = -2147467259;
      goto LABEL_37;
    }
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(
           hProcess,
           (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
           &Buffer,
           8u,
           &NumberOfBytesRead)
      && NumberOfBytesRead == 8 )
    {
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead)
        && NumberOfBytesRead == 16
        && lpBaseAddress[1] )
      {
        v5 = 0x2000;
        if ( LOWORD(lpBaseAddress[0]) <= 0x2000u )
          v5 = LOWORD(lpBaseAddress[0]);
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 lpBuffer,
                                 v5 >> 1) )
        {
          v6 = -2147024882;
LABEL_37:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
          return v6;
        }
        NumberOfBytesRead = 0;
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], lpBuffer[0], v5, &NumberOfBytesRead) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(lpBuffer);
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, lpBuffer);
          v6 = 0;
          goto LABEL_37;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_37;
        v9 = 61;
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_37;
        v9 = 60;
      }
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_37;
      v9 = 59;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180097e84  mov     [rsp-8+arg_8], rbx
0x180097e89  push    rbp
0x180097e8a  push    rsi
0x180097e8b  push    rdi
0x180097e8c  lea     rbp, [rsp-47h]
0x180097e91  sub     rsp, 90h
0x180097e98  xorps   xmm0, xmm0
0x180097e9b  mov     [rbp+57h+Buffer], 0
0x180097ea3  lea     rax, [rbp+57h+var_50]
0x180097ea7  mov     rsi, rdx
0x180097eaa  mov     [rbp+57h+lpBuffer], rax
0x180097eae  mov     rdi, rcx
0x180097eb1  lea     rax, [rbp+57h+var_50]
0x180097eb5  mov     [rbp+57h+var_58], rax
0x180097eb9  xor     eax, eax
0x180097ebb  mov     [rbp+57h+var_50], ax
0x180097ebf  mov     [rbp+57h+NumberOfBytesRead], rax
0x180097ec3  mov     [rbp+57h+arg_0], eax
0x180097ec6  movups  [rbp+57h+ProcessInformation], xmm0
0x180097eca  movups  [rbp+57h+var_30], xmm0
0x180097ece  movups  [rbp+57h+var_20], xmm0
0x180097ed2  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x180097ed6  test    rcx, rcx
0x180097ed9  jz      loc_180098127
0x180097edf  test    rdx, rdx
0x180097ee2  jz      loc_180098127
0x180097ee8  lea     rax, [rbp+57h+arg_0]
0x180097eec  mov     r9d, 30h ; '0'; ProcessInformationLength
0x180097ef2  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180097ef6  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180097efb  xor     edx, edx; ProcessInformationClass
0x180097efd  call    cs:__imp_NtQueryInformationProcess
0x180097f03  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x180097f07  mov     r9d, eax
0x180097f0a  mov     r8d, [rbp+57h+arg_0]
0x180097f0e  test    eax, eax
0x180097f10  js      loc_1800980E9
0x180097f16  cmp     r8d, 30h ; '0'
0x180097f1a  jnz     loc_1800980E9
0x180097f20  test    rdx, rdx
0x180097f23  jz      loc_1800980E9
0x180097f29  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097f2d  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097f35  lea     r9d, [r8-28h]; nSize
0x180097f39  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097f3e  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180097f42  add     rdx, 20h ; ' '; lpBaseAddress
0x180097f46  mov     rcx, rdi; hProcess
0x180097f49  call    cs:__imp_ReadProcessMemory
0x180097f4f  test    eax, eax
0x180097f51  jz      loc_1800980A1
0x180097f57  cmp     [rbp+57h+NumberOfBytesRead], 8
0x180097f5c  jnz     loc_1800980A1
0x180097f62  mov     rdx, [rbp+57h+Buffer]
0x180097f66  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097f6a  add     rdx, 70h ; 'p'; lpBaseAddress
0x180097f6e  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097f76  mov     r9d, 10h; nSize
0x180097f7c  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097f81  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x180097f85  mov     rcx, rdi; hProcess
0x180097f88  call    cs:__imp_ReadProcessMemory
0x180097f8e  test    eax, eax
0x180097f90  jz      loc_180098064
0x180097f96  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x180097f9b  jnz     loc_180098064
0x180097fa1  cmp     [rbp+57h+lpBaseAddress+8], 0
0x180097fa6  jz      loc_180098064
0x180097fac  mov     ebx, 2000h
0x180097fb1  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x180097fb5  jb      short loc_180097FBB
0x180097fb7  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x180097fbb  mov     rdx, rbx
0x180097fbe  lea     rcx, [rbp+57h+lpBuffer]
0x180097fc2  shr     rdx, 1
0x180097fc5  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180097fca  test    al, al
0x180097fcc  jnz     short loc_180097FD8
0x180097fce  mov     ebx, 8007000Eh
0x180097fd3  jmp     loc_18009811A
0x180097fd8  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x180097fdc  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180097fe0  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x180097fe4  mov     r9, rbx; nSize
0x180097fe7  mov     rcx, rdi; hProcess
0x180097fea  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x180097fef  mov     [rbp+57h+NumberOfBytesRead], 0
0x180097ff7  call    cs:__imp_ReadProcessMemory
0x180097ffd  test    eax, eax
0x180097fff  jnz     short loc_180098041
0x180098001  call    cs:__imp_GetLastError
0x180098007  mov     ebx, eax
0x180098009  test    eax, eax
0x18009800b  jle     short loc_180098016
0x18009800d  movzx   ebx, ax
0x180098010  or      ebx, 80070000h
0x180098016  mov     rcx, cs:WPP_GLOBAL_Control
0x18009801d  lea     rax, WPP_GLOBAL_Control
0x180098024  cmp     rcx, rax
0x180098027  jz      loc_18009811A
0x18009802d  test    byte ptr [rcx+1Ch], 1
0x180098031  jz      loc_18009811A
0x180098037  mov     edx, 3Dh ; '='
0x18009803c  jmp     loc_1800980D4
0x180098041  mov     rdx, [rbp+57h+NumberOfBytesRead]
0x180098045  lea     rcx, [rbp+57h+lpBuffer]
0x180098049  shr     rdx, 1
0x18009804c  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x180098051  lea     rdx, [rbp+57h+lpBuffer]
0x180098055  mov     rcx, rsi
0x180098058  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18009805d  xor     ebx, ebx
0x18009805f  jmp     loc_18009811A
0x180098064  call    cs:__imp_GetLastError
0x18009806a  mov     ebx, eax
0x18009806c  test    eax, eax
0x18009806e  jle     short loc_180098079
0x180098070  movzx   ebx, ax
0x180098073  or      ebx, 80070000h
0x180098079  mov     rcx, cs:WPP_GLOBAL_Control
0x180098080  lea     rax, WPP_GLOBAL_Control
0x180098087  cmp     rcx, rax
0x18009808a  jz      loc_18009811A
0x180098090  test    byte ptr [rcx+1Ch], 1
0x180098094  jz      loc_18009811A
0x18009809a  mov     edx, 3Ch ; '<'
0x18009809f  jmp     short loc_1800980D4
0x1800980a1  call    cs:__imp_GetLastError
0x1800980a7  mov     ebx, eax
0x1800980a9  test    eax, eax
0x1800980ab  jle     short loc_1800980B6
0x1800980ad  movzx   ebx, ax
0x1800980b0  or      ebx, 80070000h
0x1800980b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980bd  lea     rax, WPP_GLOBAL_Control
0x1800980c4  cmp     rcx, rax
0x1800980c7  jz      short loc_18009811A
0x1800980c9  test    byte ptr [rcx+1Ch], 1
0x1800980cd  jz      short loc_18009811A
0x1800980cf  mov     edx, 3Bh ; ';'
0x1800980d4  mov     rcx, [rcx+10h]
0x1800980d8  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1800980df  mov     r9d, ebx
0x1800980e2  call    WPP_SF_d
0x1800980e7  jmp     short loc_18009811A
0x1800980e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800980f0  lea     rax, WPP_GLOBAL_Control
0x1800980f7  cmp     rcx, rax
0x1800980fa  jz      short loc_180098115
0x1800980fc  test    byte ptr [rcx+1Ch], 1
0x180098100  jz      short loc_180098115
0x180098102  mov     rcx, [rcx+10h]
0x180098106  mov     [rsp+0A0h+var_78], rdx
0x18009810b  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x180098110  call    WPP_SF_DDq
0x180098115  mov     ebx, 80004005h
0x18009811a  lea     rcx, [rbp+57h+lpBuffer]; void *
0x18009811e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180098123  mov     eax, ebx
0x180098125  jmp     short loc_180098163
0x180098127  mov     rcx, cs:WPP_GLOBAL_Control
0x18009812e  lea     rax, WPP_GLOBAL_Control
0x180098135  cmp     rcx, rax
0x180098138  jz      short loc_180098155
0x18009813a  test    byte ptr [rcx+1Ch], 1
0x18009813e  jz      short loc_180098155
0x180098140  mov     rcx, [rcx+10h]
0x180098144  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009814b  mov     edx, 39h ; '9'
0x180098150  call    WPP_SF_
0x180098155  lea     rcx, [rbp+57h+lpBuffer]; void *
0x180098159  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009815e  mov     eax, 80070057h
0x180098163  mov     rbx, [rsp+0A0h+arg_8]
0x18009816b  add     rsp, 90h
0x180098172  pop     rdi
0x180098173  pop     rsi
0x180098174  pop     rbp
0x180098175  retn
```
