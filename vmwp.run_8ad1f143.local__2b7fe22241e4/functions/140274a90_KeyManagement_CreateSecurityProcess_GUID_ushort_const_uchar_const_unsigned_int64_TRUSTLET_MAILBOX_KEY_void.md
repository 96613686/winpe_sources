# KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)

- ea: `0x140274a90`
- end: `0x140274d3f`
- name: `?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z`
- size: `687`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, const unsigned __int16 *, const unsigned __int8 *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1402740a0`

## callees

- `0x1400b654c`
- `0x140132960`
- `0x14013361c`
- `0x140274a90`
- `0x140274d48`
- `0x140275100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140274cca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140274cca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140274bab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140274bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274c01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140274c01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140274cf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140274cf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140274bf1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140274bf1`
- `ntdll!NtClose` at `0x140274d0f`
- `ntdll!NtClose` at `0x140274d0f`
- `bcrypt!BCryptGenRandom` at `0x140274b45`
- `bcrypt!BCryptGenRandom` at `0x140274b45`

## pseudocode

```c
__int64 __fastcall KeyManagement::CreateSecurityProcess(
        KeyManagement *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        struct _PS_TRUSTLET_TKSESSION_ID *a5)
{
  NTSTATUS v9; // ebx
  int v10; // ebx
  HANDLE EventW; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  DWORD v14; // eax
  HANDLE Handle[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  UCHAR pbBuffer[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v19; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+68h] [rbp-98h]
  WCHAR Name[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v22[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Buffer[264]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v24[296]; // [rsp+520h] [rbp+420h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v22, 0, 0x208u);
  memset_0(v24, 0, 0x248u);
  *(_QWORD *)pbBuffer = 0;
  memset_0(Name, 0, sizeof(Name));
  Handle[0] = 0;
  v19 = 0;
  v20 = 0;
  v9 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
  if ( v9 < 0 )
    return (unsigned int)(v9 | 0x10000000);
  v10 = KeyManagement::_anonymous_namespace_::GenerateSessionId(a3, a4, &v19);
  if ( v10 >= 0 )
  {
    v10 = StringCchPrintfW(Name, 0x40u, L"Global\\%016llX", *(_QWORD *)pbBuffer);
    if ( v10 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, Name);
      if ( !EventW )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)v10;
      }
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
        goto LABEL_9;
      v10 = StringCchPrintfW(v22, 0x104u, L"%s\\%s", Buffer, L"vmsp.exe");
      if ( v10 >= 0 )
      {
        v10 = StringCchPrintfW(v24, 0x124u, L"%s {%s} %016llX", v22, a2, *(_QWORD *)pbBuffer);
        if ( v10 >= 0 )
        {
          v17 = *(_OWORD *)this;
          v10 = KeyManagement::CreateTrustlet(
                  (KeyManagement *)&v17,
                  &v19,
                  a5,
                  (struct _TRUSTLET_MAILBOX_KEY *)v22,
                  v24,
                  (unsigned __int16 *)Handle);
          if ( v10 >= 0 )
          {
            v14 = WaitForSingleObject(EventW, 0x4E20u);
            if ( v14 )
            {
              if ( v14 == 258 )
              {
                v10 = -2147023436;
              }
              else
              {
                if ( v14 == -1 )
                {
LABEL_9:
                  v13 = GetLastError();
                  v10 = v13;
                  if ( v13 > 0 )
                    v10 = (unsigned __int16)v13 | 0x80070000;
                  goto LABEL_19;
                }
                v10 = -2147418113;
              }
            }
          }
        }
      }
LABEL_19:
      CloseHandle(EventW);
      if ( Handle[0] )
        NtClose(Handle[0]);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140274a90  push    rbp
0x140274a92  push    rbx
0x140274a93  push    rsi
0x140274a94  push    rdi
0x140274a95  push    r12
0x140274a97  push    r14
0x140274a99  push    r15
0x140274a9b  lea     rbp, [rsp-680h]
0x140274aa3  sub     rsp, 780h
0x140274aaa  mov     rax, cs:__security_cookie
0x140274ab1  xor     rax, rsp
0x140274ab4  mov     [rbp+6B0h+var_40], rax
0x140274abb  mov     r12, [rbp+6B0h+arg_20]
0x140274ac2  mov     rdi, r8
0x140274ac5  mov     r14, rdx
0x140274ac8  mov     r15, rcx
0x140274acb  mov     ebx, 208h
0x140274ad0  lea     rcx, [rbp+6B0h+Buffer]; void *
0x140274ad7  mov     r8d, ebx; Size
0x140274ada  xor     edx, edx; Val
0x140274adc  mov     rsi, r9
0x140274adf  call    memset_0
0x140274ae4  mov     r8d, ebx; Size
0x140274ae7  lea     rcx, [rbp+6B0h+var_6B0]; void *
0x140274aeb  xor     edx, edx; Val
0x140274aed  call    memset_0
0x140274af2  xor     edx, edx; Val
0x140274af4  lea     r8d, [rbx+40h]; Size
0x140274af8  lea     rcx, [rbp+6B0h+var_290]; void *
0x140274aff  call    memset_0
0x140274b04  xor     edx, edx; Val
0x140274b06  mov     qword ptr [rsp+7B0h+pbBuffer], 0
0x140274b0f  mov     r8d, 80h; Size
0x140274b15  lea     rcx, [rbp+6B0h+Name]; void *
0x140274b19  call    memset_0
0x140274b1e  xorps   xmm0, xmm0
0x140274b21  mov     [rsp+7B0h+Handle], 0; void **
0x140274b2a  mov     r9d, 2; dwFlags
0x140274b30  lea     rdx, [rsp+7B0h+pbBuffer]; pbBuffer
0x140274b35  xor     ecx, ecx; hAlgorithm
0x140274b37  movups  xmmword ptr [rsp+7B0h+var_758.Data1], xmm0
0x140274b3c  lea     r8d, [r9+6]; cbBuffer
0x140274b40  movups  [rsp+7B0h+var_748], xmm0
0x140274b45  call    cs:__imp_BCryptGenRandom
0x140274b4c  nop     dword ptr [rax+rax+00h]
0x140274b51  mov     ebx, eax
0x140274b53  test    eax, eax
0x140274b55  jns     short loc_140274B60
0x140274b57  bts     ebx, 1Ch
0x140274b5b  jmp     loc_140274D1B
0x140274b60  lea     r8, [rsp+7B0h+var_758]
0x140274b65  mov     rdx, rsi
0x140274b68  mov     rcx, rdi
0x140274b6b  call    KeyManagement___anonymous_namespace___GenerateSessionId
0x140274b70  mov     ebx, eax
0x140274b72  test    eax, eax
0x140274b74  js      loc_140274D1B
0x140274b7a  mov     r9, qword ptr [rsp+7B0h+pbBuffer]
0x140274b7f  lea     r8, aGlobal016llx; "Global\\%016llX"
0x140274b86  mov     edx, 40h ; '@'; unsigned __int64
0x140274b8b  lea     rcx, [rbp+6B0h+Name]; unsigned __int16 *
0x140274b8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274b94  mov     ebx, eax
0x140274b96  test    eax, eax
0x140274b98  js      loc_140274D1B
0x140274b9e  xor     r8d, r8d; bInitialState
0x140274ba1  lea     r9, [rbp+6B0h+Name]; lpName
0x140274ba5  xor     ecx, ecx; lpEventAttributes
0x140274ba7  lea     edx, [r8+1]; bManualReset
0x140274bab  call    cs:__imp_CreateEventW
0x140274bb2  nop     dword ptr [rax+rax+00h]
0x140274bb7  mov     rdi, rax
0x140274bba  test    rax, rax
0x140274bbd  jnz     short loc_140274BE3
0x140274bbf  call    cs:__imp_GetLastError
0x140274bc6  nop     dword ptr [rax+rax+00h]
0x140274bcb  mov     ebx, eax
0x140274bcd  test    eax, eax
0x140274bcf  jle     loc_140274D1B
0x140274bd5  movzx   ebx, ax
0x140274bd8  or      ebx, 80070000h
0x140274bde  jmp     loc_140274D1B
0x140274be3  mov     ebx, 104h
0x140274be8  lea     rcx, [rbp+6B0h+Buffer]; lpBuffer
0x140274bef  mov     edx, ebx; uSize
0x140274bf1  call    cs:__imp_GetSystemDirectoryW
0x140274bf8  nop     dword ptr [rax+rax+00h]
0x140274bfd  test    eax, eax
0x140274bff  jnz     short loc_140274C25
0x140274c01  call    cs:__imp_GetLastError
0x140274c08  nop     dword ptr [rax+rax+00h]
0x140274c0d  mov     ebx, eax
0x140274c0f  test    eax, eax
0x140274c11  jle     loc_140274CF6
0x140274c17  movzx   ebx, ax
0x140274c1a  or      ebx, 80070000h
0x140274c20  jmp     loc_140274CF6
0x140274c25  lea     rax, aVmspExe; "vmsp.exe"
0x140274c2c  mov     rdx, rbx; unsigned __int64
0x140274c2f  lea     r9, [rbp+6B0h+Buffer]
0x140274c36  mov     [rsp+7B0h+var_790], rax
0x140274c3b  lea     r8, aSS_0; "%s\\%s"
0x140274c42  lea     rcx, [rbp+6B0h+var_6B0]; unsigned __int16 *
0x140274c46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274c4b  mov     ebx, eax
0x140274c4d  test    eax, eax
0x140274c4f  js      loc_140274CF6
0x140274c55  mov     rax, qword ptr [rsp+7B0h+pbBuffer]
0x140274c5a  lea     r9, [rbp+6B0h+var_6B0]
0x140274c5e  mov     [rsp+7B0h+var_788], rax
0x140274c63  lea     r8, aSS016llx; "%s {%s} %016llX"
0x140274c6a  mov     edx, 124h; unsigned __int64
0x140274c6f  mov     [rsp+7B0h+var_790], r14
0x140274c74  lea     rcx, [rbp+6B0h+var_290]; unsigned __int16 *
0x140274c7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140274c80  mov     ebx, eax
0x140274c82  test    eax, eax
0x140274c84  js      short loc_140274CF6
0x140274c86  movaps  xmm0, xmmword ptr [r15]
0x140274c8a  lea     rax, [rsp+7B0h+Handle]
0x140274c8f  mov     [rsp+7B0h+var_788], rax; unsigned __int16 *
0x140274c94  lea     r9, [rbp+6B0h+var_6B0]; struct _TRUSTLET_MAILBOX_KEY *
0x140274c98  lea     rax, [rbp+6B0h+var_290]
0x140274c9f  movdqa  [rsp+7B0h+var_770], xmm0
0x140274ca5  mov     r8, r12; struct _PS_TRUSTLET_TKSESSION_ID *
0x140274ca8  mov     [rsp+7B0h+var_790], rax; unsigned __int16 *
0x140274cad  lea     rdx, [rsp+7B0h+var_758]; struct _GUID *
0x140274cb2  lea     rcx, [rsp+7B0h+var_770]; this
0x140274cb7  call    ?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z; KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)
0x140274cbc  mov     ebx, eax
0x140274cbe  test    eax, eax
0x140274cc0  js      short loc_140274CF6
0x140274cc2  mov     edx, 4E20h; dwMilliseconds
0x140274cc7  mov     rcx, rdi; hHandle
0x140274cca  call    cs:__imp_WaitForSingleObject
0x140274cd1  nop     dword ptr [rax+rax+00h]
0x140274cd6  test    eax, eax
0x140274cd8  jz      short loc_140274CF6
0x140274cda  cmp     eax, 102h
0x140274cdf  jz      short loc_140274CF1
0x140274ce1  cmp     eax, 0FFFFFFFFh
0x140274ce4  jz      loc_140274C01
0x140274cea  mov     ebx, 8000FFFFh
0x140274cef  jmp     short loc_140274CF6
0x140274cf1  mov     ebx, 800705B4h
0x140274cf6  mov     rcx, rdi; hObject
0x140274cf9  call    cs:__imp_CloseHandle
0x140274d00  nop     dword ptr [rax+rax+00h]
0x140274d05  mov     rcx, [rsp+7B0h+Handle]; Handle
0x140274d0a  test    rcx, rcx
0x140274d0d  jz      short loc_140274D1B
0x140274d0f  call    cs:__imp_NtClose
0x140274d16  nop     dword ptr [rax+rax+00h]
0x140274d1b  mov     eax, ebx
0x140274d1d  mov     rcx, [rbp+6B0h+var_40]
0x140274d24  xor     rcx, rsp; StackCookie
0x140274d27  call    __security_check_cookie
0x140274d2c  add     rsp, 780h
0x140274d33  pop     r15
0x140274d35  pop     r14
0x140274d37  pop     r12
0x140274d39  pop     rdi
0x140274d3a  pop     rsi
0x140274d3b  pop     rbx
0x140274d3c  pop     rbp
0x140274d3d  retn
```
