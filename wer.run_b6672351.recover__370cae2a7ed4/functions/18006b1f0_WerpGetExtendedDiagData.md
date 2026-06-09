# WerpGetExtendedDiagData

- ea: `0x18006b1f0`
- end: `0x18006b4ac`
- name: `WerpGetExtendedDiagData`
- size: `700`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004c64`
- `0x180020680`
- `0x18006b1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3a2`
- `ntdll!NtQueryInformationProcess` at `0x18006b251`
- `ntdll!NtQueryInformationProcess` at `0x18006b251`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006b2bf`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006b392`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006b2bf`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18006b392`

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
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, v7);
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
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, 2147942699LL);
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
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, 2147943705LL);
    return 2147943705LL;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
  return 2147943568LL;
}

```

## disassembly

```asm
0x18006b1f0  push    rbp
0x18006b1f2  push    rbx
0x18006b1f3  push    rsi
0x18006b1f4  push    rdi
0x18006b1f5  push    r14
0x18006b1f7  mov     rbp, rsp
0x18006b1fa  sub     rsp, 60h
0x18006b1fe  xorps   xmm0, xmm0
0x18006b201  mov     qword ptr [rdx], 0
0x18006b208  mov     dword ptr [r8], 0
0x18006b20f  mov     rsi, r8
0x18006b212  mov     r14, rdx
0x18006b215  mov     [rbp+NumberOfBytesRead], 0
0x18006b21d  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x18006b221  mov     [rbp+Buffer], 0
0x18006b229  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18006b22f  mov     [rbp+arg_10], 0
0x18006b237  xor     edx, edx; ProcessInformationClass
0x18006b239  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18006b242  mov     rdi, rcx
0x18006b245  movups  [rbp+ProcessInformation], xmm0
0x18006b249  movups  [rbp+var_20], xmm0
0x18006b24d  movups  [rbp+var_10], xmm0
0x18006b251  call    cs:__imp_NtQueryInformationProcess
0x18006b258  nop     dword ptr [rax+rax+00h]
0x18006b25d  mov     ebx, eax
0x18006b25f  test    eax, eax
0x18006b261  jns     short loc_18006B29F
0x18006b263  bts     ebx, 1Ch
0x18006b267  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b26e  lea     rdx, WPP_GLOBAL_Control
0x18006b275  cmp     rcx, rdx
0x18006b278  jz      short loc_18006B298
0x18006b27a  test    byte ptr [rcx+1Ch], 1
0x18006b27e  jz      short loc_18006B298
0x18006b280  mov     edx, 0AFh
0x18006b285  mov     rcx, [rcx+10h]
0x18006b289  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006b290  mov     r9d, ebx
0x18006b293  call    WPP_SF_d
0x18006b298  mov     eax, ebx
0x18006b29a  jmp     loc_18006B4A0
0x18006b29f  mov     rdx, qword ptr [rbp+ProcessInformation+8]
0x18006b2a3  lea     rax, [rbp+NumberOfBytesRead]
0x18006b2a7  mov     ebx, 8
0x18006b2ac  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006b2b1  add     rdx, 28h ; '('; lpBaseAddress
0x18006b2b5  lea     r8, [rbp+Buffer]; lpBuffer
0x18006b2b9  mov     r9d, ebx; nSize
0x18006b2bc  mov     rcx, rdi; hProcess
0x18006b2bf  call    cs:__imp_ReadProcessMemory
0x18006b2c6  nop     dword ptr [rax+rax+00h]
0x18006b2cb  test    eax, eax
0x18006b2cd  jnz     short loc_18006B30D
0x18006b2cf  call    cs:__imp_GetLastError
0x18006b2d6  nop     dword ptr [rax+rax+00h]
0x18006b2db  mov     ebx, eax
0x18006b2dd  test    eax, eax
0x18006b2df  jle     short loc_18006B2EA
0x18006b2e1  movzx   ebx, ax
0x18006b2e4  or      ebx, 80070000h
0x18006b2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b2f1  lea     rdx, WPP_GLOBAL_Control
0x18006b2f8  cmp     rcx, rdx
0x18006b2fb  jz      short loc_18006B298
0x18006b2fd  test    byte ptr [rcx+1Ch], 1
0x18006b301  jz      short loc_18006B298
0x18006b303  mov     edx, 0B0h
0x18006b308  jmp     loc_18006B285
0x18006b30d  cmp     [rbp+NumberOfBytesRead], rbx
0x18006b311  jz      short loc_18006B33E
0x18006b313  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b31a  lea     rdx, WPP_GLOBAL_Control
0x18006b321  cmp     rcx, rdx
0x18006b324  jz      loc_18006B422
0x18006b32a  test    byte ptr [rcx+1Ch], 1
0x18006b32e  jz      loc_18006B422
0x18006b334  mov     edx, 0B1h
0x18006b339  jmp     loc_18006B40C
0x18006b33e  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x18006b342  test    rdx, rdx
0x18006b345  jnz     short loc_18006B37F
0x18006b347  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b34e  lea     rdx, WPP_GLOBAL_Control
0x18006b355  cmp     rcx, rdx
0x18006b358  jz      short loc_18006B375
0x18006b35a  test    byte ptr [rcx+1Ch], 4
0x18006b35e  jz      short loc_18006B375
0x18006b360  mov     rcx, [rcx+10h]
0x18006b364  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006b36b  mov     edx, 0B2h
0x18006b370  call    WPP_SF_
0x18006b375  mov     eax, 80070490h
0x18006b37a  jmp     loc_18006B4A0
0x18006b37f  lea     rax, [rbp+NumberOfBytesRead]
0x18006b383  mov     r9, rbx; nSize
0x18006b386  lea     r8, [rbp+arg_10]; lpBuffer
0x18006b38a  mov     [rsp+60h+ReturnLength], rax; lpNumberOfBytesRead
0x18006b38f  mov     rcx, rdi; hProcess
0x18006b392  call    cs:__imp_ReadProcessMemory
0x18006b399  nop     dword ptr [rax+rax+00h]
0x18006b39e  test    eax, eax
0x18006b3a0  jnz     short loc_18006B3E8
0x18006b3a2  call    cs:__imp_GetLastError
0x18006b3a9  nop     dword ptr [rax+rax+00h]
0x18006b3ae  mov     ebx, eax
0x18006b3b0  test    eax, eax
0x18006b3b2  jle     short loc_18006B3BD
0x18006b3b4  movzx   ebx, ax
0x18006b3b7  or      ebx, 80070000h
0x18006b3bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3c4  lea     rdx, WPP_GLOBAL_Control
0x18006b3cb  cmp     rcx, rdx
0x18006b3ce  jz      loc_18006B298
0x18006b3d4  test    byte ptr [rcx+1Ch], 1
0x18006b3d8  jz      loc_18006B298
0x18006b3de  mov     edx, 0B3h
0x18006b3e3  jmp     loc_18006B285
0x18006b3e8  cmp     [rbp+NumberOfBytesRead], rbx
0x18006b3ec  jz      short loc_18006B429
0x18006b3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b3f5  lea     rdx, WPP_GLOBAL_Control
0x18006b3fc  cmp     rcx, rdx
0x18006b3ff  jz      short loc_18006B422
0x18006b401  test    byte ptr [rcx+1Ch], 1
0x18006b405  jz      short loc_18006B422
0x18006b407  mov     edx, 0B4h
0x18006b40c  mov     rcx, [rcx+10h]
0x18006b410  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006b417  mov     r9d, 8007012Bh
0x18006b41d  call    WPP_SF_d
0x18006b422  mov     eax, 8007012Bh
0x18006b427  jmp     short loc_18006B4A0
0x18006b429  mov     rax, [rbp+arg_10]
0x18006b42d  cmp     eax, ebx
0x18006b42f  jnb     short loc_18006B451
0x18006b431  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b438  lea     rdx, WPP_GLOBAL_Control
0x18006b43f  cmp     rcx, rdx
0x18006b442  jz      short loc_18006B48E
0x18006b444  test    byte ptr [rcx+1Ch], 1
0x18006b448  jz      short loc_18006B48E
0x18006b44a  mov     edx, 0B6h
0x18006b44f  jmp     short loc_18006B478
0x18006b451  cmp     dword ptr [rbp+arg_10+4], 57454442h
0x18006b458  jz      short loc_18006B495
0x18006b45a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b461  lea     rdx, WPP_GLOBAL_Control
0x18006b468  cmp     rcx, rdx
0x18006b46b  jz      short loc_18006B48E
0x18006b46d  test    byte ptr [rcx+1Ch], 1
0x18006b471  jz      short loc_18006B48E
0x18006b473  mov     edx, 0B7h
0x18006b478  mov     rcx, [rcx+10h]
0x18006b47c  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18006b483  mov     r9d, 80070519h
0x18006b489  call    WPP_SF_d
0x18006b48e  mov     eax, 80070519h
0x18006b493  jmp     short loc_18006B4A0
0x18006b495  mov     rcx, [rbp+Buffer]
0x18006b499  mov     [r14], rcx
0x18006b49c  mov     [rsi], eax
0x18006b49e  xor     eax, eax
0x18006b4a0  add     rsp, 60h
0x18006b4a4  pop     r14
0x18006b4a6  pop     rdi
0x18006b4a7  pop     rsi
0x18006b4a8  pop     rbx
0x18006b4a9  pop     rbp
0x18006b4aa  retn
```
