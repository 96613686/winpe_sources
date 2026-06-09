# Record_InternalError_w

- ea: `0x18001c21c`
- end: `0x18001c40c`
- name: `Record_InternalError_w`
- size: `496`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800218c0`
- `0x180021904`

## callees

- `0x18001b69c`
- `0x18001bc98`
- `0x18001bd14`
- `0x18001bfc4`
- `0x18001c21c`
- `0x18002dec0`

## import_xrefs

- `msvcrt!_vsnwprintf_s` at `0x18001c284`
- `msvcrt!_vsnwprintf_s` at `0x18001c284`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c321`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c32f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c33d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c321`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c32f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c33d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c2b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c2b2`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001c37a`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18001c37a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c2e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c2e0`

## pseudocode

```c
BOOLEAN Record_InternalError_w(char *a1, int a2, const wchar_t *a3, ...)
{
  unsigned int v5; // edi
  __int64 v6; // rcx
  __int64 v7; // rsi
  unsigned __int64 v8; // r8
  BOOLEAN result; // al
  __int64 v10; // r8
  _QWORD v11[2]; // [rsp+30h] [rbp-888h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-878h] BYREF
  _QWORD *v13; // [rsp+50h] [rbp-868h]
  __int64 v14; // [rsp+58h] [rbp-860h]
  wchar_t *v15; // [rsp+60h] [rbp-858h]
  int v16; // [rsp+68h] [rbp-850h]
  int v17; // [rsp+6Ch] [rbp-84Ch]
  wchar_t Buffer[1024]; // [rsp+70h] [rbp-848h] BYREF
  va_list va; // [rsp+8D8h] [rbp+20h] BYREF

  va_start(va, a3);
  v11[1] = -2;
  if ( a3 && *a3 )
  {
    v5 = _vsnwprintf_s(Buffer, 0x400u, 0xFFFFFFFFFFFFFFFFuLL, a3, va);
    v11[0] = v5;
    if ( v5 == -1 )
    {
      v5 = 1023;
      LODWORD(v11[0]) = 1023;
    }
  }
  else
  {
    Buffer[0] = 0;
    v5 = 0;
    LODWORD(v11[0]) = 0;
  }
  EnterCriticalSection(&stru_180049CC0);
  try
  {
    try
    {
      std::vector<ErrorRecord>::resize(v6, ((*(&xmmword_180049CE8 + 1) - xmmword_180049CE8) >> 6) + 1);
      v7 = (__int64)*(&xmmword_180049CE8 + 1);
      *(_DWORD *)(v7 - 64) = GetCurrentThreadId();
      *(_BYTE *)(v7 - 60) = 1;
      *(_DWORD *)(v7 - 56) = -1;
      *(_DWORD *)(v7 - 52) = -2147467259;
      *(_DWORD *)(v7 - 40) = a2;
      ErrorRecord::MakeDeepStringCopy((char **)(v7 - 48), a1, v8);
      ErrorRecord::MakeDeepStringCopy((unsigned __int16 **)(v7 - 32), Buffer, 0xFFFFFFFFFFFFFFFFuLL);
      operator delete[](*(void **)(v7 - 24));
      *(_QWORD *)(v7 - 24) = 0;
      operator delete[](*(void **)(v7 - 16));
      *(_QWORD *)(v7 - 16) = 0;
      operator delete[](*(void **)(v7 - 8));
      *(_QWORD *)(v7 - 8) = 0;
    }
    catch ( std::bad_alloc )
    {
      Log_Text_F((__int64)"base\\winsat\\api-dll\\logging.cpp", 1035, "ERROR: cannot allocate memory for error record");
      v5 = v11[0];
    }
  }
  catch ( ... )
  {
    Log_Text_F((__int64)"base\\winsat\\api-dll\\logging.cpp", 1039, "ERROR: unhandled general exception");
    v5 = v11[0];
  }
  LeaveCriticalSection(&stru_180049CC0);
  result = EventEnabled(WINSATAPI_ETW_PROVIDER_Context, &InternalErrorEv);
  if ( result && v5 <= 0xFFFF && (WINSATAPI_ETW_PROVIDEREnableBits & 2) != 0 )
  {
    LOWORD(v11[0]) = v5 + 1;
    v13 = v11;
    v14 = 2;
    v15 = Buffer;
    v16 = 2 * (unsigned __int16)(v5 + 1);
    v17 = 0;
    return McGenEventWrite_EventWriteTransfer(&WINSATAPI_ETW_PROVIDER_Context, &InternalErrorEv, v10, 3u, &v12);
  }
  return result;
}

```

## disassembly

```asm
0x18001c21c  mov     r11, rsp
0x18001c21f  mov     [r11+18h], r8
0x18001c223  mov     [r11+20h], r9
0x18001c227  push    rbx
0x18001c228  push    rsi
0x18001c229  push    rdi
0x18001c22a  push    r12
0x18001c22c  push    r14
0x18001c22e  push    r15
0x18001c230  sub     rsp, 888h
0x18001c237  mov     [rsp+8B8h+var_880], 0FFFFFFFFFFFFFFFEh
0x18001c240  mov     rax, cs:__security_cookie
0x18001c247  xor     rax, rsp
0x18001c24a  mov     [rsp+8B8h+var_48], rax
0x18001c252  mov     r15d, edx
0x18001c255  mov     r12, rcx
0x18001c258  xor     ebx, ebx
0x18001c25a  test    r8, r8
0x18001c25d  jz      short loc_18001C2A0
0x18001c25f  cmp     [r8], bx
0x18001c263  jz      short loc_18001C2A0
0x18001c265  mov     [rsp+8B8h+var_888], rbx
0x18001c26a  lea     rax, [r11+20h]
0x18001c26e  mov     [rsp+8B8h+ArgList], rax; ArgList
0x18001c273  mov     r9, r8; Format
0x18001c276  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001c27a  mov     edx, 400h; BufferCount
0x18001c27f  lea     rcx, [rsp+8B8h+Buffer]; Buffer
0x18001c284  call    cs:__imp__vsnwprintf_s
0x18001c28a  mov     edi, eax
0x18001c28c  mov     dword ptr [rsp+8B8h+var_888], eax
0x18001c290  cmp     eax, 0FFFFFFFFh
0x18001c293  jnz     short loc_18001C2AB
0x18001c295  mov     edi, 3FFh
0x18001c29a  mov     dword ptr [rsp+8B8h+var_888], edi
0x18001c29e  jmp     short loc_18001C2AB
0x18001c2a0  mov     [rsp+8B8h+Buffer], bx
0x18001c2a5  mov     edi, ebx
0x18001c2a7  mov     dword ptr [rsp+8B8h+var_888], ebx
0x18001c2ab  lea     rcx, stru_180049CC0; lpCriticalSection
0x18001c2b2  call    cs:__imp_EnterCriticalSection
0x18001c2b8  nop
0x18001c2b9  mov     rdx, qword ptr cs:xmmword_180049CE8+8
0x18001c2c0  sub     rdx, qword ptr cs:xmmword_180049CE8
0x18001c2c7  sar     rdx, 6
0x18001c2cb  mov     r14d, 1
0x18001c2d1  add     rdx, r14
0x18001c2d4  call    ?resize@?$vector@VErrorRecord@@V?$allocator@VErrorRecord@@@std@@@std@@QEAAX_K@Z; std::vector<ErrorRecord>::resize(unsigned __int64)
0x18001c2d9  mov     rsi, qword ptr cs:xmmword_180049CE8+8
0x18001c2e0  call    cs:__imp_GetCurrentThreadId
0x18001c2e6  mov     [rsi-40h], eax
0x18001c2e9  mov     [rsi-3Ch], r14b
0x18001c2ed  mov     dword ptr [rsi-38h], 0FFFFFFFFh
0x18001c2f4  mov     dword ptr [rsi-34h], 80004005h
0x18001c2fb  mov     [rsi-28h], r15d
0x18001c2ff  lea     rcx, [rsi-30h]; char **
0x18001c303  mov     rdx, r12; char *
0x18001c306  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEADPEBD_K@Z; ErrorRecord::MakeDeepStringCopy(char * &,char const *,unsigned __int64)
0x18001c30b  lea     rcx, [rsi-20h]; unsigned __int16 **
0x18001c30f  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18001c313  lea     rdx, [rsp+8B8h+Buffer]; unsigned __int16 *
0x18001c318  call    ?MakeDeepStringCopy@ErrorRecord@@CAXAEAPEAGPEBG_K@Z; ErrorRecord::MakeDeepStringCopy(ushort * &,ushort const *,unsigned __int64)
0x18001c31d  mov     rcx, [rsi-18h]
0x18001c321  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c327  mov     [rsi-18h], rbx
0x18001c32b  mov     rcx, [rsi-10h]
0x18001c32f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c335  mov     [rsi-10h], rbx
0x18001c339  mov     rcx, [rsi-8]
0x18001c33d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c343  mov     [rsi-8], rbx
0x18001c347  jmp     short loc_18001C353
0x18001c349  xor     ebx, ebx
0x18001c34b  lea     r14d, [rbx+1]
0x18001c34f  mov     edi, dword ptr [rsp+8B8h+var_888]
0x18001c353  jmp     short loc_18001C35F
0x18001c355  xor     ebx, ebx
0x18001c357  lea     r14d, [rbx+1]
0x18001c35b  mov     edi, dword ptr [rsp+8B8h+var_888]
0x18001c35f  lea     rcx, stru_180049CC0; lpCriticalSection
0x18001c366  call    cs:__imp_LeaveCriticalSection
0x18001c36c  lea     rdx, InternalErrorEv; EventDescriptor
0x18001c373  mov     rcx, cs:WINSATAPI_ETW_PROVIDER_Context; RegHandle
0x18001c37a  call    cs:__imp_EventEnabled
0x18001c380  test    al, al
0x18001c382  jz      short loc_18001C3EB
0x18001c384  cmp     edi, 0FFFFh
0x18001c38a  ja      short loc_18001C3EB
0x18001c38c  test    cs:WINSATAPI_ETW_PROVIDEREnableBits, 2
0x18001c393  jz      short loc_18001C3EB
0x18001c395  add     di, r14w
0x18001c399  movzx   eax, di
0x18001c39c  mov     word ptr [rsp+8B8h+var_888], ax
0x18001c3a1  lea     rcx, [rsp+8B8h+var_888]
0x18001c3a6  mov     [rsp+8B8h+var_868], rcx
0x18001c3ab  mov     [rsp+8B8h+var_860], 2
0x18001c3b4  lea     rcx, [rsp+8B8h+Buffer]
0x18001c3b9  mov     [rsp+8B8h+var_858], rcx
0x18001c3be  add     eax, eax
0x18001c3c0  mov     [rsp+8B8h+var_850], eax
0x18001c3c4  mov     [rsp+8B8h+var_84C], ebx
0x18001c3c8  lea     rax, [rsp+8B8h+var_878]
0x18001c3cd  mov     [rsp+8B8h+ArgList], rax
0x18001c3d2  mov     r9d, 3
0x18001c3d8  lea     rdx, InternalErrorEv
0x18001c3df  lea     rcx, WINSATAPI_ETW_PROVIDER_Context
0x18001c3e6  call    McGenEventWrite_EventWriteTransfer
0x18001c3eb  mov     rcx, [rsp+8B8h+var_48]
0x18001c3f3  xor     rcx, rsp; StackCookie
0x18001c3f6  call    __security_check_cookie
0x18001c3fb  add     rsp, 888h
0x18001c402  pop     r15
0x18001c404  pop     r14
0x18001c406  pop     r12
0x18001c408  pop     rdi
0x18001c409  pop     rsi
0x18001c40a  pop     rbx
0x18001c40b  retn
```
