# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18009c274`
- end: `0x18009c591`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021024`

## callees

- `0x180004c64`
- `0x18000add4`
- `0x18000ae48`
- `0x18000db80`
- `0x180020680`
- `0x180025560`
- `0x18009c274`
- `0x18009d94c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c4b5`
- `ntdll!NtQueryInformationProcess` at `0x18009c2ed`
- `ntdll!NtQueryInformationProcess` at `0x18009c2ed`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c33f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c384`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c3f9`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c33f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c384`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18009c3f9`

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
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(
            lpBuffer,
            NumberOfBytesRead >> 1);
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
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v6);
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009c274  mov     [rsp-8+arg_8], rbx
0x18009c279  push    rbp
0x18009c27a  push    rsi
0x18009c27b  push    rdi
0x18009c27c  lea     rbp, [rsp-47h]
0x18009c281  sub     rsp, 90h
0x18009c288  xorps   xmm0, xmm0
0x18009c28b  mov     [rbp+57h+Buffer], 0
0x18009c293  lea     rax, [rbp+57h+var_50]
0x18009c297  mov     rsi, rdx
0x18009c29a  mov     [rbp+57h+lpBuffer], rax
0x18009c29e  mov     rdi, rcx
0x18009c2a1  lea     rax, [rbp+57h+var_50]
0x18009c2a5  mov     [rbp+57h+var_58], rax
0x18009c2a9  xor     eax, eax
0x18009c2ab  mov     [rbp+57h+var_50], ax
0x18009c2af  mov     [rbp+57h+NumberOfBytesRead], rax
0x18009c2b3  mov     [rbp+57h+arg_0], eax
0x18009c2b6  movups  [rbp+57h+ProcessInformation], xmm0
0x18009c2ba  movups  [rbp+57h+var_30], xmm0
0x18009c2be  movups  [rbp+57h+var_20], xmm0
0x18009c2c2  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x18009c2c6  test    rcx, rcx
0x18009c2c9  jz      loc_18009C541
0x18009c2cf  test    rdx, rdx
0x18009c2d2  jz      loc_18009C541
0x18009c2d8  lea     rax, [rbp+57h+arg_0]
0x18009c2dc  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18009c2e2  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18009c2e6  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18009c2eb  xor     edx, edx; ProcessInformationClass
0x18009c2ed  call    cs:__imp_NtQueryInformationProcess
0x18009c2f4  nop     dword ptr [rax+rax+00h]
0x18009c2f9  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x18009c2fd  mov     r9d, eax
0x18009c300  mov     r8d, [rbp+57h+arg_0]
0x18009c304  test    eax, eax
0x18009c306  js      loc_18009C503
0x18009c30c  cmp     r8d, 30h ; '0'
0x18009c310  jnz     loc_18009C503
0x18009c316  test    rdx, rdx
0x18009c319  jz      loc_18009C503
0x18009c31f  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18009c323  mov     [rbp+57h+NumberOfBytesRead], 0
0x18009c32b  lea     r9d, [r8-28h]; nSize
0x18009c32f  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18009c334  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18009c338  add     rdx, 20h ; ' '; lpBaseAddress
0x18009c33c  mov     rcx, rdi; hProcess
0x18009c33f  call    cs:__imp_ReadProcessMemory
0x18009c346  nop     dword ptr [rax+rax+00h]
0x18009c34b  test    eax, eax
0x18009c34d  jz      loc_18009C4B5
0x18009c353  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18009c358  jnz     loc_18009C4B5
0x18009c35e  mov     rdx, [rbp+57h+Buffer]
0x18009c362  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18009c366  add     rdx, 70h ; 'p'; lpBaseAddress
0x18009c36a  mov     [rbp+57h+NumberOfBytesRead], 0
0x18009c372  mov     r9d, 10h; nSize
0x18009c378  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18009c37d  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x18009c381  mov     rcx, rdi; hProcess
0x18009c384  call    cs:__imp_ReadProcessMemory
0x18009c38b  nop     dword ptr [rax+rax+00h]
0x18009c390  test    eax, eax
0x18009c392  jz      loc_18009C472
0x18009c398  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x18009c39d  jnz     loc_18009C472
0x18009c3a3  cmp     [rbp+57h+lpBaseAddress+8], 0
0x18009c3a8  jz      loc_18009C472
0x18009c3ae  mov     ebx, 2000h
0x18009c3b3  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x18009c3b7  jb      short loc_18009C3BD
0x18009c3b9  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x18009c3bd  mov     rdx, rbx
0x18009c3c0  lea     rcx, [rbp+57h+lpBuffer]
0x18009c3c4  shr     rdx, 1
0x18009c3c7  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18009c3cc  test    al, al
0x18009c3ce  jnz     short loc_18009C3DA
0x18009c3d0  mov     ebx, 8007000Eh
0x18009c3d5  jmp     loc_18009C534
0x18009c3da  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x18009c3de  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18009c3e2  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x18009c3e6  mov     r9, rbx; nSize
0x18009c3e9  mov     rcx, rdi; hProcess
0x18009c3ec  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18009c3f1  mov     [rbp+57h+NumberOfBytesRead], 0
0x18009c3f9  call    cs:__imp_ReadProcessMemory
0x18009c400  nop     dword ptr [rax+rax+00h]
0x18009c405  test    eax, eax
0x18009c407  jnz     short loc_18009C44F
0x18009c409  call    cs:__imp_GetLastError
0x18009c410  nop     dword ptr [rax+rax+00h]
0x18009c415  mov     ebx, eax
0x18009c417  test    eax, eax
0x18009c419  jle     short loc_18009C424
0x18009c41b  movzx   ebx, ax
0x18009c41e  or      ebx, 80070000h
0x18009c424  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c42b  lea     rax, WPP_GLOBAL_Control
0x18009c432  cmp     rcx, rax
0x18009c435  jz      loc_18009C534
0x18009c43b  test    byte ptr [rcx+1Ch], 1
0x18009c43f  jz      loc_18009C534
0x18009c445  mov     edx, 3Dh ; '='
0x18009c44a  jmp     loc_18009C4EE
0x18009c44f  mov     rdx, [rbp+57h+NumberOfBytesRead]
0x18009c453  lea     rcx, [rbp+57h+lpBuffer]
0x18009c457  shr     rdx, 1
0x18009c45a  call    ?erase@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::erase(unsigned __int64)
0x18009c45f  lea     rdx, [rbp+57h+lpBuffer]
0x18009c463  mov     rcx, rsi
0x18009c466  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18009c46b  xor     ebx, ebx
0x18009c46d  jmp     loc_18009C534
0x18009c472  call    cs:__imp_GetLastError
0x18009c479  nop     dword ptr [rax+rax+00h]
0x18009c47e  mov     ebx, eax
0x18009c480  test    eax, eax
0x18009c482  jle     short loc_18009C48D
0x18009c484  movzx   ebx, ax
0x18009c487  or      ebx, 80070000h
0x18009c48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c494  lea     rax, WPP_GLOBAL_Control
0x18009c49b  cmp     rcx, rax
0x18009c49e  jz      loc_18009C534
0x18009c4a4  test    byte ptr [rcx+1Ch], 1
0x18009c4a8  jz      loc_18009C534
0x18009c4ae  mov     edx, 3Ch ; '<'
0x18009c4b3  jmp     short loc_18009C4EE
0x18009c4b5  call    cs:__imp_GetLastError
0x18009c4bc  nop     dword ptr [rax+rax+00h]
0x18009c4c1  mov     ebx, eax
0x18009c4c3  test    eax, eax
0x18009c4c5  jle     short loc_18009C4D0
0x18009c4c7  movzx   ebx, ax
0x18009c4ca  or      ebx, 80070000h
0x18009c4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c4d7  lea     rax, WPP_GLOBAL_Control
0x18009c4de  cmp     rcx, rax
0x18009c4e1  jz      short loc_18009C534
0x18009c4e3  test    byte ptr [rcx+1Ch], 1
0x18009c4e7  jz      short loc_18009C534
0x18009c4e9  mov     edx, 3Bh ; ';'
0x18009c4ee  mov     rcx, [rcx+10h]
0x18009c4f2  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c4f9  mov     r9d, ebx
0x18009c4fc  call    WPP_SF_d
0x18009c501  jmp     short loc_18009C534
0x18009c503  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c50a  lea     rax, WPP_GLOBAL_Control
0x18009c511  cmp     rcx, rax
0x18009c514  jz      short loc_18009C52F
0x18009c516  test    byte ptr [rcx+1Ch], 1
0x18009c51a  jz      short loc_18009C52F
0x18009c51c  mov     rcx, [rcx+10h]
0x18009c520  mov     [rsp+0A0h+var_78], rdx
0x18009c525  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x18009c52a  call    WPP_SF_DDq
0x18009c52f  mov     ebx, 80004005h
0x18009c534  lea     rcx, [rbp+57h+lpBuffer]; void *
0x18009c538  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009c53d  mov     eax, ebx
0x18009c53f  jmp     short loc_18009C57D
0x18009c541  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c548  lea     rax, WPP_GLOBAL_Control
0x18009c54f  cmp     rcx, rax
0x18009c552  jz      short loc_18009C56F
0x18009c554  test    byte ptr [rcx+1Ch], 1
0x18009c558  jz      short loc_18009C56F
0x18009c55a  mov     rcx, [rcx+10h]
0x18009c55e  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009c565  mov     edx, 39h ; '9'
0x18009c56a  call    WPP_SF_
0x18009c56f  lea     rcx, [rbp+57h+lpBuffer]; void *
0x18009c573  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18009c578  mov     eax, 80070057h
0x18009c57d  mov     rbx, [rsp+0A0h+arg_8]
0x18009c585  add     rsp, 90h
0x18009c58c  pop     rdi
0x18009c58d  pop     rsi
0x18009c58e  pop     rbp
0x18009c58f  retn
```
