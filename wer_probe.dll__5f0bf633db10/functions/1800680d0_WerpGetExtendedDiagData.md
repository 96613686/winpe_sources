# WerpGetExtendedDiagData

- ea: `0x1800680d0`
- end: `0x18006836a`
- name: `WerpGetExtendedDiagData`
- size: `666`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x1800680d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800681a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800681a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068267`
- `ntdll!NtQueryInformationProcess` at `0x180068131`
- `ntdll!NtQueryInformationProcess` at `0x180068131`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180068199`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006825d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180068199`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006825d`

## pseudocode

```c
__int64 __fastcall WerpGetExtendedDiagData(HANDLE hProcess, _QWORD *a2, _DWORD *a3)
{
  NTSTATUS InformationProcess; // ebx
  unsigned int v7; // ebx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // eax
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  int v15; // eax
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  _OWORD ProcessInformation[3]; // [rsp+30h] [rbp-30h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+98h] [rbp+38h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+40h] BYREF
  LPCVOID Buffer; // [rsp+A8h] [rbp+48h] BYREF

  *a2 = 0;
  *a3 = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v20 = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    v7 = InformationProcess | 0x10000000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v7;
    v9 = 175;
LABEL_5:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, v7);
    return v7;
  }
  if ( !ReadProcessMemory(
          hProcess,
          (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 40LL),
          &Buffer,
          8u,
          &NumberOfBytesRead) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v7;
    v9 = 176;
    goto LABEL_5;
  }
  if ( NumberOfBytesRead != 8 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return 2147942699LL;
    v13 = 177;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, 2147942699LL);
    return 2147942699LL;
  }
  if ( Buffer )
  {
    if ( !ReadProcessMemory(hProcess, Buffer, &v20, 8u, &NumberOfBytesRead) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v7;
      v9 = 179;
      goto LABEL_5;
    }
    if ( NumberOfBytesRead != 8 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147942699LL;
      v13 = 180;
      goto LABEL_32;
    }
    v15 = v20;
    if ( (unsigned int)v20 >= 8 )
    {
      if ( HIDWORD(v20) == 1464157250 )
      {
        *a2 = Buffer;
        *a3 = v15;
        return 0;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147943705LL;
      v17 = 183;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return 2147943705LL;
      v17 = 182;
    }
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, 2147943705LL);
    return 2147943705LL;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800680d0  push    rbp
0x1800680d2  push    rbx
0x1800680d3  push    rsi
0x1800680d4  push    rdi
0x1800680d5  push    r14
0x1800680d7  mov     rbp, rsp
0x1800680da  sub     rsp, 60h
0x1800680de  xorps   xmm0, xmm0
0x1800680e1  mov     qword ptr [rdx], 0
0x1800680e8  mov     dword ptr [r8], 0
0x1800680ef  mov     rsi, r8
0x1800680f2  mov     r14, rdx
0x1800680f5  mov     [rbp+NumberOfBytesRead], 0
0x1800680fd  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x180068101  mov     [rbp+Buffer], 0
0x180068109  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18006810f  mov     [rbp+arg_10], 0
0x180068117  xor     edx, edx; ProcessInformationClass
0x180068119  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x180068122  mov     rdi, rcx
0x180068125  movups  [rbp+ProcessInformation], xmm0
0x180068129  movups  [rbp+var_20], xmm0
0x18006812d  movups  [rbp+var_10], xmm0
0x180068131  call    cs:__imp_NtQueryInformationProcess
0x180068137  mov     ebx, eax
0x180068139  test    eax, eax
0x18006813b  jns     short loc_180068179
0x18006813d  bts     ebx, 1Ch
0x180068141  mov     rcx, cs:WPP_GLOBAL_Control
0x180068148  lea     rdx, WPP_GLOBAL_Control
0x18006814f  cmp     rcx, rdx
0x180068152  jz      short loc_180068172
0x180068154  test    byte ptr [rcx+1Ch], 1
0x180068158  jz      short loc_180068172
0x18006815a  mov     edx, 0AFh
0x18006815f  mov     rcx, [rcx+10h]
0x180068163  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18006816a  mov     r9d, ebx
0x18006816d  call    WPP_SF_d
0x180068172  mov     eax, ebx
0x180068174  jmp     loc_18006835F
0x180068179  mov     rdx, qword ptr [rbp+ProcessInformation+8]
0x18006817d  lea     rax, [rbp+NumberOfBytesRead]
0x180068181  mov     ebx, 8
0x180068186  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006818b  add     rdx, 28h ; '('; lpBaseAddress
0x18006818f  lea     r8, [rbp+Buffer]; lpBuffer
0x180068193  mov     r9d, ebx; nSize
0x180068196  mov     rcx, rdi; hProcess
0x180068199  call    cs:__imp_ReadProcessMemory
0x18006819f  test    eax, eax
0x1800681a1  jnz     short loc_1800681D8
0x1800681a3  call    cs:__imp_GetLastError
0x1800681a9  mov     ebx, eax
0x1800681ab  test    eax, eax
0x1800681ad  jle     short loc_1800681B8
0x1800681af  movzx   ebx, ax
0x1800681b2  or      ebx, 80070000h
0x1800681b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800681bf  lea     rdx, WPP_GLOBAL_Control
0x1800681c6  cmp     rcx, rdx
0x1800681c9  jz      short loc_180068172
0x1800681cb  test    byte ptr [rcx+1Ch], 1
0x1800681cf  jz      short loc_180068172
0x1800681d1  mov     edx, 0B0h
0x1800681d6  jmp     short loc_18006815F
0x1800681d8  cmp     [rbp+NumberOfBytesRead], rbx
0x1800681dc  jz      short loc_180068209
0x1800681de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800681e5  lea     rdx, WPP_GLOBAL_Control
0x1800681ec  cmp     rcx, rdx
0x1800681ef  jz      loc_1800682E1
0x1800681f5  test    byte ptr [rcx+1Ch], 1
0x1800681f9  jz      loc_1800682E1
0x1800681ff  mov     edx, 0B1h
0x180068204  jmp     loc_1800682CB
0x180068209  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x18006820d  test    rdx, rdx
0x180068210  jnz     short loc_18006824A
0x180068212  mov     rcx, cs:WPP_GLOBAL_Control
0x180068219  lea     rdx, WPP_GLOBAL_Control
0x180068220  cmp     rcx, rdx
0x180068223  jz      short loc_180068240
0x180068225  test    byte ptr [rcx+1Ch], 4
0x180068229  jz      short loc_180068240
0x18006822b  mov     rcx, [rcx+10h]
0x18006822f  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180068236  mov     edx, 0B2h
0x18006823b  call    WPP_SF_
0x180068240  mov     eax, 80070490h
0x180068245  jmp     loc_18006835F
0x18006824a  lea     rax, [rbp+NumberOfBytesRead]
0x18006824e  mov     r9, rbx; nSize
0x180068251  lea     r8, [rbp+arg_10]; lpBuffer
0x180068255  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006825a  mov     rcx, rdi; hProcess
0x18006825d  call    cs:__imp_ReadProcessMemory
0x180068263  test    eax, eax
0x180068265  jnz     short loc_1800682A7
0x180068267  call    cs:__imp_GetLastError
0x18006826d  mov     ebx, eax
0x18006826f  test    eax, eax
0x180068271  jle     short loc_18006827C
0x180068273  movzx   ebx, ax
0x180068276  or      ebx, 80070000h
0x18006827c  mov     rcx, cs:WPP_GLOBAL_Control
0x180068283  lea     rdx, WPP_GLOBAL_Control
0x18006828a  cmp     rcx, rdx
0x18006828d  jz      loc_180068172
0x180068293  test    byte ptr [rcx+1Ch], 1
0x180068297  jz      loc_180068172
0x18006829d  mov     edx, 0B3h
0x1800682a2  jmp     loc_18006815F
0x1800682a7  cmp     [rbp+NumberOfBytesRead], rbx
0x1800682ab  jz      short loc_1800682E8
0x1800682ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682b4  lea     rdx, WPP_GLOBAL_Control
0x1800682bb  cmp     rcx, rdx
0x1800682be  jz      short loc_1800682E1
0x1800682c0  test    byte ptr [rcx+1Ch], 1
0x1800682c4  jz      short loc_1800682E1
0x1800682c6  mov     edx, 0B4h
0x1800682cb  mov     rcx, [rcx+10h]
0x1800682cf  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x1800682d6  mov     r9d, 8007012Bh
0x1800682dc  call    WPP_SF_d
0x1800682e1  mov     eax, 8007012Bh
0x1800682e6  jmp     short loc_18006835F
0x1800682e8  mov     rax, [rbp+arg_10]
0x1800682ec  cmp     eax, ebx
0x1800682ee  jnb     short loc_180068310
0x1800682f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682f7  lea     rdx, WPP_GLOBAL_Control
0x1800682fe  cmp     rcx, rdx
0x180068301  jz      short loc_18006834D
0x180068303  test    byte ptr [rcx+1Ch], 1
0x180068307  jz      short loc_18006834D
0x180068309  mov     edx, 0B6h
0x18006830e  jmp     short loc_180068337
0x180068310  cmp     dword ptr [rbp+arg_10+4], 57454442h
0x180068317  jz      short loc_180068354
0x180068319  mov     rcx, cs:WPP_GLOBAL_Control
0x180068320  lea     rdx, WPP_GLOBAL_Control
0x180068327  cmp     rcx, rdx
0x18006832a  jz      short loc_18006834D
0x18006832c  test    byte ptr [rcx+1Ch], 1
0x180068330  jz      short loc_18006834D
0x180068332  mov     edx, 0B7h
0x180068337  mov     rcx, [rcx+10h]
0x18006833b  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x180068342  mov     r9d, 80070519h
0x180068348  call    WPP_SF_d
0x18006834d  mov     eax, 80070519h
0x180068352  jmp     short loc_18006835F
0x180068354  mov     rcx, [rbp+Buffer]
0x180068358  mov     [r14], rcx
0x18006835b  mov     [rsi], eax
0x18006835d  xor     eax, eax
0x18006835f  add     rsp, 60h
0x180068363  pop     r14
0x180068365  pop     rdi
0x180068366  pop     rsi
0x180068367  pop     rbx
0x180068368  pop     rbp
0x180068369  retn
```
