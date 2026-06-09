# Record_Win32Error_w

- ea: `0x14003fa8c`
- end: `0x14003fccf`
- name: `Record_Win32Error_w`
- size: `579`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, char)`
- caller_count: `20`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140010258`
- `0x140013ed4`
- `0x14001a54c`
- `0x14001c2b0`
- `0x14001c73c`
- `0x14001c9e4`
- `0x14003ad38`
- `0x14003b020`
- `0x14003b628`
- `0x14003bdf4`
- `0x140040448`
- `0x140041870`
- `0x14004211c`
- `0x140043900`
- `0x140043c78`
- `0x140043ce4`
- `0x140043f14`
- `0x140043fd0`
- `0x1400482a0`
- `0x140087c40`

## callees

- `0x140001abc`
- `0x14001a3cc`
- `0x14003d15c`
- `0x14003dda0`
- `0x14003de10`
- `0x14003e7c4`
- `0x14003fa8c`
- `0x140113220`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x14003fc14`
- `ADVAPI32!EventEnabled` at `0x14003fc14`
- `KERNEL32!EnterCriticalSection` at `0x14003fb4b`
- `KERNEL32!EnterCriticalSection` at `0x14003fb4b`
- `KERNEL32!LeaveCriticalSection` at `0x14003fc00`
- `KERNEL32!LeaveCriticalSection` at `0x14003fc00`
- `KERNEL32!GetCurrentThreadId` at `0x14003fb79`
- `KERNEL32!GetCurrentThreadId` at `0x14003fb79`
- `msvcrt!_vsnwprintf_s` at `0x14003fb02`
- `msvcrt!_vsnwprintf_s` at `0x14003fb02`

## pseudocode

```c
__int64 Record_Win32Error_w(char *a1, int a2, DWORD a3, const wchar_t *a4, ...)
{
  DWORD v4; // r14d
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rsi
  unsigned __int64 v12; // r8
  __int64 v13; // r8
  DWORD v14; // [rsp+30h] [rbp-8A8h] BYREF
  _QWORD v15[3]; // [rsp+38h] [rbp-8A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp-888h] BYREF
  DWORD *v17; // [rsp+60h] [rbp-878h]
  __int64 v18; // [rsp+68h] [rbp-870h]
  _QWORD *v19; // [rsp+70h] [rbp-868h]
  __int64 v20; // [rsp+78h] [rbp-860h]
  wchar_t *v21; // [rsp+80h] [rbp-858h]
  int v22; // [rsp+88h] [rbp-850h]
  int v23; // [rsp+8Ch] [rbp-84Ch]
  wchar_t Buffer[1024]; // [rsp+90h] [rbp-848h] BYREF
  va_list va; // [rsp+900h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a3;
  v14 = a3;
  if ( !a3 )
    return 0;
  if ( a4 && *a4 )
  {
    v8 = (unsigned int)_vsnwprintf_s(Buffer, 0x400u, 0xFFFFFFFFFFFFFFFFuLL, a4, va);
    v15[0] = v8;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    v15[1] = v9;
    if ( (_DWORD)v8 == -1 )
    {
      LODWORD(v8) = 1023;
      LODWORD(v15[0]) = 1023;
    }
  }
  else
  {
    Buffer[0] = 0;
    LODWORD(v8) = 0;
    LODWORD(v15[0]) = 0;
  }
  EnterCriticalSection(&CriticalSection);
  try
  {
    try
    {
      std::vector<ErrorRecord>::resize(v10, ((qword_1401C65E0 - (__int64)qword_1401C65D8) >> 6) + 1);
      v11 = qword_1401C65E0;
      *(_DWORD *)(v11 - 64) = GetCurrentThreadId();
      *(_BYTE *)(v11 - 60) = 1;
      *(_DWORD *)(v11 - 56) = v4;
      *(_DWORD *)(v11 - 52) = 0;
      *(_DWORD *)(v11 - 40) = a2;
      ErrorRecord::MakeDeepStringCopy((char **)(v11 - 48), a1, v12);
      *(_QWORD *)(v11 - 32) = GetErrorMessage<unsigned short>(v4);
      ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v11 - 24), Buffer, (int)v8);
      operator delete(*(void **)(v11 - 16));
      *(_QWORD *)(v11 - 16) = 0;
      operator delete(*(void **)(v11 - 8));
      *(_QWORD *)(v11 - 8) = 0;
    }
    catch ( std::bad_alloc )
    {
      Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1209, "ERROR: cannot allocate memory for error record");
      LODWORD(v8) = v15[0];
      v4 = v14;
    }
  }
  catch ( ... )
  {
    Log_Text_F((__int64)"base\\winsat\\exe\\logging.cpp", 1213, "ERROR: unhandled general exception");
    LODWORD(v8) = v15[0];
    v4 = v14;
  }
  LeaveCriticalSection(&CriticalSection);
  if ( EventEnabled(WINSAT_ETW_PROVIDER_Context, &Win32ErrorEv)
    && (unsigned int)v8 <= 0xFFFF
    && (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 2) != 0 )
  {
    LOWORD(v15[0]) = v8 + 1;
    v14 = v4;
    v17 = &v14;
    v18 = 4;
    v19 = v15;
    v20 = 2;
    v21 = Buffer;
    v22 = 2 * (unsigned __int16)(v8 + 1);
    v23 = 0;
    McGenEventWrite_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, &Win32ErrorEv, v13, 4u, &v16);
  }
  return v4;
}

```

## disassembly

```asm
0x14003fa8c  mov     [rsp+arg_18], r9
0x14003fa91  push    rbx
0x14003fa92  push    rsi
0x14003fa93  push    rdi
0x14003fa94  push    r12
0x14003fa96  push    r13
0x14003fa98  push    r14
0x14003fa9a  push    r15
0x14003fa9c  sub     rsp, 8A0h
0x14003faa3  mov     rax, cs:__security_cookie
0x14003faaa  xor     rax, rsp
0x14003faad  mov     [rsp+8D8h+var_48], rax
0x14003fab5  mov     r14d, r8d
0x14003fab8  mov     r12d, edx
0x14003fabb  mov     r13, rcx
0x14003fabe  mov     [rsp+8D8h+var_8A8], r8d
0x14003fac3  xor     ebx, ebx
0x14003fac5  test    r8d, r8d
0x14003fac8  jnz     short loc_14003FAD1
0x14003faca  xor     eax, eax
0x14003facc  jmp     loc_14003FCAC
0x14003fad1  test    r9, r9
0x14003fad4  jz      short loc_14003FB36
0x14003fad6  cmp     [r9], bx
0x14003fada  jz      short loc_14003FB36
0x14003fadc  mov     [rsp+8D8h+var_8A0], rbx
0x14003fae1  lea     rax, [rsp+8D8h+arg_20]
0x14003fae9  mov     [rsp+8D8h+ArgList], rax; ArgList
0x14003faee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14003faf2  mov     r8, rsi; MaxCount
0x14003faf5  mov     edx, 400h; BufferCount
0x14003fafa  lea     rcx, [rsp+8D8h+Buffer]; Buffer
0x14003fb02  call    cs:__imp__vsnwprintf_s
0x14003fb08  mov     edi, eax
0x14003fb0a  mov     dword ptr [rsp+8D8h+var_8A0], eax
0x14003fb0e  lea     rcx, [rsp+8D8h+Buffer]
0x14003fb16  mov     rax, rsi
0x14003fb19  inc     rax
0x14003fb1c  cmp     [rcx+rax*2], bx
0x14003fb20  jnz     short loc_14003FB19
0x14003fb22  mov     [rsp+8D8h+var_898], rax
0x14003fb27  cmp     edi, esi
0x14003fb29  jnz     short loc_14003FB44
0x14003fb2b  mov     edi, 3FFh
0x14003fb30  mov     dword ptr [rsp+8D8h+var_8A0], edi
0x14003fb34  jmp     short loc_14003FB44
0x14003fb36  mov     [rsp+8D8h+Buffer], bx
0x14003fb3e  mov     edi, ebx
0x14003fb40  mov     dword ptr [rsp+8D8h+var_8A0], ebx
0x14003fb44  lea     rcx, CriticalSection; lpCriticalSection
0x14003fb4b  call    cs:__imp_EnterCriticalSection
0x14003fb51  nop
0x14003fb52  mov     rdx, cs:qword_1401C65E0
0x14003fb59  sub     rdx, cs:qword_1401C65D8
0x14003fb60  sar     rdx, 6
0x14003fb64  mov     r15d, 1
0x14003fb6a  add     rdx, r15
0x14003fb6d  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x14003fb72  mov     rsi, cs:qword_1401C65E0
0x14003fb79  call    cs:__imp_GetCurrentThreadId
0x14003fb7f  mov     [rsi-40h], eax
0x14003fb82  mov     [rsi-3Ch], r15b
0x14003fb86  mov     [rsi-38h], r14d
0x14003fb8a  mov     [rsi-34h], ebx
0x14003fb8d  mov     [rsi-28h], r12d
0x14003fb91  lea     rcx, [rsi-30h]; char **
0x14003fb95  mov     rdx, r13; char *
0x14003fb98  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x14003fb9d  mov     ecx, r14d; dwMessageId
0x14003fba0  call    ??$GetErrorMessage@G@@YAPEAGK@Z; GetErrorMessage<ushort>(ulong)
0x14003fba5  mov     [rsi-20h], rax
0x14003fba9  movsxd  r8, edi; unsigned __int64
0x14003fbac  lea     rcx, [rsi-18h]; unsigned __int16 **
0x14003fbb0  lea     rdx, [rsp+8D8h+Buffer]; unsigned __int16 *
0x14003fbb8  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x14003fbbd  mov     rcx, [rsi-10h]; Block
0x14003fbc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fbc6  mov     [rsi-10h], rbx
0x14003fbca  mov     rcx, [rsi-8]; Block
0x14003fbce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fbd3  mov     [rsi-8], rbx
0x14003fbd7  jmp     short loc_14003FBE8
0x14003fbd9  xor     ebx, ebx
0x14003fbdb  lea     r15d, [rbx+1]
0x14003fbdf  mov     edi, dword ptr [rsp+8D8h+var_8A0]
0x14003fbe3  mov     r14d, [rsp+8D8h+var_8A8]
0x14003fbe8  jmp     short loc_14003FBF9
0x14003fbea  xor     ebx, ebx
0x14003fbec  lea     r15d, [rbx+1]
0x14003fbf0  mov     edi, dword ptr [rsp+8D8h+var_8A0]
0x14003fbf4  mov     r14d, [rsp+8D8h+var_8A8]
0x14003fbf9  lea     rcx, CriticalSection; lpCriticalSection
0x14003fc00  call    cs:__imp_LeaveCriticalSection
0x14003fc06  lea     rdx, Win32ErrorEv; EventDescriptor
0x14003fc0d  mov     rcx, cs:WINSAT_ETW_PROVIDER_Context; RegHandle
0x14003fc14  call    cs:__imp_EventEnabled
0x14003fc1a  test    al, al
0x14003fc1c  jz      loc_14003FCA9
0x14003fc22  cmp     edi, 0FFFFh
0x14003fc28  ja      short loc_14003FCA9
0x14003fc2a  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, 2
0x14003fc31  jz      short loc_14003FCA9
0x14003fc33  add     di, r15w
0x14003fc37  movzx   ecx, di
0x14003fc3a  mov     word ptr [rsp+8D8h+var_8A0], cx
0x14003fc3f  mov     [rsp+8D8h+var_8A8], r14d
0x14003fc44  lea     rax, [rsp+8D8h+var_8A8]
0x14003fc49  mov     [rsp+8D8h+var_878], rax
0x14003fc4e  mov     r9d, 4
0x14003fc54  mov     [rsp+8D8h+var_870], r9
0x14003fc59  lea     rax, [rsp+8D8h+var_8A0]
0x14003fc5e  mov     [rsp+8D8h+var_868], rax
0x14003fc63  mov     [rsp+8D8h+var_860], 2
0x14003fc6c  lea     rax, [rsp+8D8h+Buffer]
0x14003fc74  mov     [rsp+8D8h+var_858], rax
0x14003fc7c  add     ecx, ecx
0x14003fc7e  mov     [rsp+8D8h+var_850], ecx
0x14003fc85  mov     [rsp+8D8h+var_84C], ebx
0x14003fc8c  lea     rax, [rsp+8D8h+var_888]
0x14003fc91  mov     [rsp+8D8h+ArgList], rax
0x14003fc96  lea     rdx, Win32ErrorEv
0x14003fc9d  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x14003fca4  call    McGenEventWrite_EventWriteTransfer
0x14003fca9  mov     eax, r14d
0x14003fcac  mov     rcx, [rsp+8D8h+var_48]
0x14003fcb4  xor     rcx, rsp; StackCookie
0x14003fcb7  call    __security_check_cookie
0x14003fcbc  add     rsp, 8A0h
0x14003fcc3  pop     r15
0x14003fcc5  pop     r14
0x14003fcc7  pop     r13
0x14003fcc9  pop     r12
0x14003fccb  pop     rdi
0x14003fccc  pop     rsi
0x14003fccd  pop     rbx
0x14003fcce  retn
```
