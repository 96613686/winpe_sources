# Record_Win32Error_w

- ea: `0x18001c414`
- end: `0x18001c662`
- name: `Record_Win32Error_w`
- size: `590`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, char)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180020428`
- `0x180020784`
- `0x180020dcc`
- `0x180021294`
- `0x1800213d0`
- `0x1800214fc`
- `0x1800215b8`
- `0x1800216b0`
- `0x18002177c`
- `0x180021904`
- `0x180024d48`

## callees

- `0x18001b69c`
- `0x18001b7b4`
- `0x18001bc98`
- `0x18001bd14`
- `0x18001bfc4`
- `0x18001c414`
- `0x18002dec0`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x18001c493`
- `msvcrt!_vsnwprintf_s` at `0x18001c493`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c552`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c560`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c552`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c593`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c593`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c4dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c4dc`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001c5a7`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001c5a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c50a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c50a`

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
  v15[1] = -2;
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
    v15[2] = v9;
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
  EnterCriticalSection(&stru_180049CC0);
  try
  {
    try
    {
      std::vector<ErrorRecord>::resize(v10, ((*(&xmmword_180049CE8 + 1) - xmmword_180049CE8) >> 6) + 1);
      v11 = (__int64)*(&xmmword_180049CE8 + 1);
      *(_DWORD *)(v11 - 64) = GetCurrentThreadId();
      *(_BYTE *)(v11 - 60) = 1;
      *(_DWORD *)(v11 - 56) = v4;
      *(_DWORD *)(v11 - 52) = 0;
      *(_DWORD *)(v11 - 40) = a2;
      ErrorRecord::MakeDeepStringCopy((char **)(v11 - 48), a1, v12);
      *(_QWORD *)(v11 - 32) = GetErrorMessage<unsigned short>(v4);
      ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v11 - 24), Buffer, (int)v8);
      operator delete[](*(void **)(v11 - 16));
      *(_QWORD *)(v11 - 16) = 0;
      operator delete[](*(void **)(v11 - 8));
      *(_QWORD *)(v11 - 8) = 0;
    }
    catch ( std::bad_alloc )
    {
      Log_Text_F((__int64)"base\\winsat\\api-dll\\logging.cpp", 762, "ERROR: cannot allocate memory for error record");
      LODWORD(v8) = v15[0];
      v4 = v14;
    }
  }
  catch ( ... )
  {
    Log_Text_F((__int64)"base\\winsat\\api-dll\\logging.cpp", 766, "ERROR: unhandled general exception");
    LODWORD(v8) = v15[0];
    v4 = v14;
  }
  LeaveCriticalSection(&stru_180049CC0);
  if ( EventEnabled(WINSATAPI_ETW_PROVIDER_Context, &Win32ErrorEv)
    && (unsigned int)v8 <= 0xFFFF
    && (WINSATAPI_ETW_PROVIDEREnableBits & 2) != 0 )
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
    McGenEventWrite_EventWriteTransfer(&WINSATAPI_ETW_PROVIDER_Context, &Win32ErrorEv, v13, 4u, &v16);
  }
  return v4;
}

```

## disassembly

```asm
0x18001c414  mov     [rsp+arg_18], r9
0x18001c419  push    rbx
0x18001c41a  push    rsi
0x18001c41b  push    rdi
0x18001c41c  push    r12
0x18001c41e  push    r13
0x18001c420  push    r14
0x18001c422  push    r15
0x18001c424  sub     rsp, 8A0h
0x18001c42b  mov     [rsp+8D8h+var_898], 0FFFFFFFFFFFFFFFEh
0x18001c434  mov     rax, cs:__security_cookie
0x18001c43b  xor     rax, rsp
0x18001c43e  mov     [rsp+8D8h+var_48], rax
0x18001c446  mov     r14d, r8d
0x18001c449  mov     r12d, edx
0x18001c44c  mov     r13, rcx
0x18001c44f  mov     [rsp+8D8h+var_8A8], r8d
0x18001c454  xor     ebx, ebx
0x18001c456  test    r8d, r8d
0x18001c459  jnz     short loc_18001C462
0x18001c45b  xor     eax, eax
0x18001c45d  jmp     loc_18001C63F
0x18001c462  test    r9, r9
0x18001c465  jz      short loc_18001C4C7
0x18001c467  cmp     [r9], bx
0x18001c46b  jz      short loc_18001C4C7
0x18001c46d  mov     [rsp+8D8h+var_8A0], rbx
0x18001c472  lea     rax, [rsp+8D8h+arg_20]
0x18001c47a  mov     [rsp+8D8h+ArgList], rax; ArgList
0x18001c47f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c483  mov     r8, rsi; MaxCount
0x18001c486  mov     edx, 400h; BufferCount
0x18001c48b  lea     rcx, [rsp+8D8h+Buffer]; Buffer
0x18001c493  call    cs:__imp__vsnwprintf_s
0x18001c499  mov     edi, eax
0x18001c49b  mov     dword ptr [rsp+8D8h+var_8A0], eax
0x18001c49f  lea     rcx, [rsp+8D8h+Buffer]
0x18001c4a7  mov     rax, rsi
0x18001c4aa  inc     rax
0x18001c4ad  cmp     [rcx+rax*2], bx
0x18001c4b1  jnz     short loc_18001C4AA
0x18001c4b3  mov     [rsp+8D8h+var_890], rax
0x18001c4b8  cmp     edi, esi
0x18001c4ba  jnz     short loc_18001C4D5
0x18001c4bc  mov     edi, 3FFh
0x18001c4c1  mov     dword ptr [rsp+8D8h+var_8A0], edi
0x18001c4c5  jmp     short loc_18001C4D5
0x18001c4c7  mov     [rsp+8D8h+Buffer], bx
0x18001c4cf  mov     edi, ebx
0x18001c4d1  mov     dword ptr [rsp+8D8h+var_8A0], ebx
0x18001c4d5  lea     rcx, stru_180049CC0; lpCriticalSection
0x18001c4dc  call    cs:__imp_EnterCriticalSection
0x18001c4e2  nop
0x18001c4e3  mov     rdx, qword ptr cs:xmmword_180049CE8+8
0x18001c4ea  sub     rdx, qword ptr cs:xmmword_180049CE8
0x18001c4f1  sar     rdx, 6
0x18001c4f5  mov     r15d, 1
0x18001c4fb  add     rdx, r15
0x18001c4fe  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x18001c503  mov     rsi, qword ptr cs:xmmword_180049CE8+8
0x18001c50a  call    cs:__imp_GetCurrentThreadId
0x18001c510  mov     [rsi-40h], eax
0x18001c513  mov     [rsi-3Ch], r15b
0x18001c517  mov     [rsi-38h], r14d
0x18001c51b  mov     [rsi-34h], ebx
0x18001c51e  mov     [rsi-28h], r12d
0x18001c522  lea     rcx, [rsi-30h]; char **
0x18001c526  mov     rdx, r13; char *
0x18001c529  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x18001c52e  mov     ecx, r14d; dwMessageId
0x18001c531  call    ??$GetErrorMessage@G@@YAPEAGK@Z; GetErrorMessage<ushort>(ulong)
0x18001c536  mov     [rsi-20h], rax
0x18001c53a  movsxd  r8, edi; unsigned __int64
0x18001c53d  lea     rcx, [rsi-18h]; unsigned __int16 **
0x18001c541  lea     rdx, [rsp+8D8h+Buffer]; unsigned __int16 *
0x18001c549  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x18001c54e  mov     rcx, [rsi-10h]
0x18001c552  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c558  mov     [rsi-10h], rbx
0x18001c55c  mov     rcx, [rsi-8]
0x18001c560  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c566  mov     [rsi-8], rbx
0x18001c56a  jmp     short loc_18001C57B
0x18001c56c  xor     ebx, ebx
0x18001c56e  lea     r15d, [rbx+1]
0x18001c572  mov     edi, dword ptr [rsp+8D8h+var_8A0]
0x18001c576  mov     r14d, [rsp+8D8h+var_8A8]
0x18001c57b  jmp     short loc_18001C58C
0x18001c57d  xor     ebx, ebx
0x18001c57f  lea     r15d, [rbx+1]
0x18001c583  mov     edi, dword ptr [rsp+8D8h+var_8A0]
0x18001c587  mov     r14d, [rsp+8D8h+var_8A8]
0x18001c58c  lea     rcx, stru_180049CC0; lpCriticalSection
0x18001c593  call    cs:__imp_LeaveCriticalSection
0x18001c599  lea     rdx, Win32ErrorEv; EventDescriptor
0x18001c5a0  mov     rcx, cs:WINSATAPI_ETW_PROVIDER_Context; RegHandle
0x18001c5a7  call    cs:__imp_EventEnabled
0x18001c5ad  test    al, al
0x18001c5af  jz      loc_18001C63C
0x18001c5b5  cmp     edi, 0FFFFh
0x18001c5bb  ja      short loc_18001C63C
0x18001c5bd  test    cs:WINSATAPI_ETW_PROVIDEREnableBits, 2
0x18001c5c4  jz      short loc_18001C63C
0x18001c5c6  add     di, r15w
0x18001c5ca  movzx   ecx, di
0x18001c5cd  mov     word ptr [rsp+8D8h+var_8A0], cx
0x18001c5d2  mov     [rsp+8D8h+var_8A8], r14d
0x18001c5d7  lea     rax, [rsp+8D8h+var_8A8]
0x18001c5dc  mov     [rsp+8D8h+var_878], rax
0x18001c5e1  mov     r9d, 4
0x18001c5e7  mov     [rsp+8D8h+var_870], r9
0x18001c5ec  lea     rax, [rsp+8D8h+var_8A0]
0x18001c5f1  mov     [rsp+8D8h+var_868], rax
0x18001c5f6  mov     [rsp+8D8h+var_860], 2
0x18001c5ff  lea     rax, [rsp+8D8h+Buffer]
0x18001c607  mov     [rsp+8D8h+var_858], rax
0x18001c60f  add     ecx, ecx
0x18001c611  mov     [rsp+8D8h+var_850], ecx
0x18001c618  mov     [rsp+8D8h+var_84C], ebx
0x18001c61f  lea     rax, [rsp+8D8h+var_888]
0x18001c624  mov     [rsp+8D8h+ArgList], rax
0x18001c629  lea     rdx, Win32ErrorEv
0x18001c630  lea     rcx, WINSATAPI_ETW_PROVIDER_Context
0x18001c637  call    McGenEventWrite_EventWriteTransfer
0x18001c63c  mov     eax, r14d
0x18001c63f  mov     rcx, [rsp+8D8h+var_48]
0x18001c647  xor     rcx, rsp; StackCookie
0x18001c64a  call    __security_check_cookie
0x18001c64f  add     rsp, 8A0h
0x18001c656  pop     r15
0x18001c658  pop     r14
0x18001c65a  pop     r13
0x18001c65c  pop     r12
0x18001c65e  pop     rdi
0x18001c65f  pop     rsi
0x18001c660  pop     rbx
0x18001c661  retn
```
