# KeyManagement::CreateSecurityProcess(_GUID,ushort const *,uchar const *,unsigned __int64,_TRUSTLET_MAILBOX_KEY *,void * *)

- ea: `0x14027abb0`
- end: `0x14027ae5f`
- name: `?CreateSecurityProcess@KeyManagement@@YAJU_GUID@@PEBGPEBE_KPEAU_TRUSTLET_MAILBOX_KEY@@PEAPEAX@Z`
- size: `687`
- prototype: `__int64 __fastcall(KeyManagement *__hidden this, struct _GUID *, const unsigned __int16 *, const unsigned __int8 *, struct _PS_TRUSTLET_TKSESSION_ID *, struct _TRUSTLET_MAILBOX_KEY *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14027a0b0`

## callees

- `0x1400f0c6c`
- `0x14011ea40`
- `0x14011f6fc`
- `0x14027abb0`
- `0x14027ae68`
- `0x14027b220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14027accb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14027accb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14027adea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14027adea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027acdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027ad21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027acdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027ad21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14027ae19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14027ae19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14027ad11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14027ad11`
- `ntdll!NtClose` at `0x14027ae2f`
- `ntdll!NtClose` at `0x14027ae2f`
- `bcrypt!BCryptGenRandom` at `0x14027ac65`
- `bcrypt!BCryptGenRandom` at `0x14027ac65`

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
0x14027abb0  push    rbp
0x14027abb2  push    rbx
0x14027abb3  push    rsi
0x14027abb4  push    rdi
0x14027abb5  push    r12
0x14027abb7  push    r14
0x14027abb9  push    r15
0x14027abbb  lea     rbp, [rsp-680h]
0x14027abc3  sub     rsp, 780h
0x14027abca  mov     rax, cs:__security_cookie
0x14027abd1  xor     rax, rsp
0x14027abd4  mov     [rbp+6B0h+var_40], rax
0x14027abdb  mov     r12, [rbp+6B0h+arg_20]
0x14027abe2  mov     rdi, r8
0x14027abe5  mov     r14, rdx
0x14027abe8  mov     r15, rcx
0x14027abeb  mov     ebx, 208h
0x14027abf0  lea     rcx, [rbp+6B0h+Buffer]; void *
0x14027abf7  mov     r8d, ebx; Size
0x14027abfa  xor     edx, edx; Val
0x14027abfc  mov     rsi, r9
0x14027abff  call    memset_0
0x14027ac04  mov     r8d, ebx; Size
0x14027ac07  lea     rcx, [rbp+6B0h+var_6B0]; void *
0x14027ac0b  xor     edx, edx; Val
0x14027ac0d  call    memset_0
0x14027ac12  xor     edx, edx; Val
0x14027ac14  lea     r8d, [rbx+40h]; Size
0x14027ac18  lea     rcx, [rbp+6B0h+var_290]; void *
0x14027ac1f  call    memset_0
0x14027ac24  xor     edx, edx; Val
0x14027ac26  mov     qword ptr [rsp+7B0h+pbBuffer], 0
0x14027ac2f  mov     r8d, 80h; Size
0x14027ac35  lea     rcx, [rbp+6B0h+Name]; void *
0x14027ac39  call    memset_0
0x14027ac3e  xorps   xmm0, xmm0
0x14027ac41  mov     [rsp+7B0h+Handle], 0; void **
0x14027ac4a  mov     r9d, 2; dwFlags
0x14027ac50  lea     rdx, [rsp+7B0h+pbBuffer]; pbBuffer
0x14027ac55  xor     ecx, ecx; hAlgorithm
0x14027ac57  movups  xmmword ptr [rsp+7B0h+var_758.Data1], xmm0
0x14027ac5c  lea     r8d, [r9+6]; cbBuffer
0x14027ac60  movups  [rsp+7B0h+var_748], xmm0
0x14027ac65  call    cs:__imp_BCryptGenRandom
0x14027ac6c  nop     dword ptr [rax+rax+00h]
0x14027ac71  mov     ebx, eax
0x14027ac73  test    eax, eax
0x14027ac75  jns     short loc_14027AC80
0x14027ac77  bts     ebx, 1Ch
0x14027ac7b  jmp     loc_14027AE3B
0x14027ac80  lea     r8, [rsp+7B0h+var_758]
0x14027ac85  mov     rdx, rsi
0x14027ac88  mov     rcx, rdi
0x14027ac8b  call    KeyManagement___anonymous_namespace___GenerateSessionId
0x14027ac90  mov     ebx, eax
0x14027ac92  test    eax, eax
0x14027ac94  js      loc_14027AE3B
0x14027ac9a  mov     r9, qword ptr [rsp+7B0h+pbBuffer]
0x14027ac9f  lea     r8, aGlobal016llx; "Global\\%016llX"
0x14027aca6  mov     edx, 40h ; '@'; unsigned __int64
0x14027acab  lea     rcx, [rbp+6B0h+Name]; unsigned __int16 *
0x14027acaf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14027acb4  mov     ebx, eax
0x14027acb6  test    eax, eax
0x14027acb8  js      loc_14027AE3B
0x14027acbe  xor     r8d, r8d; bInitialState
0x14027acc1  lea     r9, [rbp+6B0h+Name]; lpName
0x14027acc5  xor     ecx, ecx; lpEventAttributes
0x14027acc7  lea     edx, [r8+1]; bManualReset
0x14027accb  call    cs:__imp_CreateEventW
0x14027acd2  nop     dword ptr [rax+rax+00h]
0x14027acd7  mov     rdi, rax
0x14027acda  test    rax, rax
0x14027acdd  jnz     short loc_14027AD03
0x14027acdf  call    cs:__imp_GetLastError
0x14027ace6  nop     dword ptr [rax+rax+00h]
0x14027aceb  mov     ebx, eax
0x14027aced  test    eax, eax
0x14027acef  jle     loc_14027AE3B
0x14027acf5  movzx   ebx, ax
0x14027acf8  or      ebx, 80070000h
0x14027acfe  jmp     loc_14027AE3B
0x14027ad03  mov     ebx, 104h
0x14027ad08  lea     rcx, [rbp+6B0h+Buffer]; lpBuffer
0x14027ad0f  mov     edx, ebx; uSize
0x14027ad11  call    cs:__imp_GetSystemDirectoryW
0x14027ad18  nop     dword ptr [rax+rax+00h]
0x14027ad1d  test    eax, eax
0x14027ad1f  jnz     short loc_14027AD45
0x14027ad21  call    cs:__imp_GetLastError
0x14027ad28  nop     dword ptr [rax+rax+00h]
0x14027ad2d  mov     ebx, eax
0x14027ad2f  test    eax, eax
0x14027ad31  jle     loc_14027AE16
0x14027ad37  movzx   ebx, ax
0x14027ad3a  or      ebx, 80070000h
0x14027ad40  jmp     loc_14027AE16
0x14027ad45  lea     rax, aVmspExe; "vmsp.exe"
0x14027ad4c  mov     rdx, rbx; unsigned __int64
0x14027ad4f  lea     r9, [rbp+6B0h+Buffer]
0x14027ad56  mov     [rsp+7B0h+var_790], rax
0x14027ad5b  lea     r8, aSS_0; "%s\\%s"
0x14027ad62  lea     rcx, [rbp+6B0h+var_6B0]; unsigned __int16 *
0x14027ad66  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14027ad6b  mov     ebx, eax
0x14027ad6d  test    eax, eax
0x14027ad6f  js      loc_14027AE16
0x14027ad75  mov     rax, qword ptr [rsp+7B0h+pbBuffer]
0x14027ad7a  lea     r9, [rbp+6B0h+var_6B0]
0x14027ad7e  mov     [rsp+7B0h+var_788], rax
0x14027ad83  lea     r8, aSS016llx; "%s {%s} %016llX"
0x14027ad8a  mov     edx, 124h; unsigned __int64
0x14027ad8f  mov     [rsp+7B0h+var_790], r14
0x14027ad94  lea     rcx, [rbp+6B0h+var_290]; unsigned __int16 *
0x14027ad9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14027ada0  mov     ebx, eax
0x14027ada2  test    eax, eax
0x14027ada4  js      short loc_14027AE16
0x14027ada6  movaps  xmm0, xmmword ptr [r15]
0x14027adaa  lea     rax, [rsp+7B0h+Handle]
0x14027adaf  mov     [rsp+7B0h+var_788], rax; unsigned __int16 *
0x14027adb4  lea     r9, [rbp+6B0h+var_6B0]; struct _TRUSTLET_MAILBOX_KEY *
0x14027adb8  lea     rax, [rbp+6B0h+var_290]
0x14027adbf  movdqa  [rsp+7B0h+var_770], xmm0
0x14027adc5  mov     r8, r12; struct _PS_TRUSTLET_TKSESSION_ID *
0x14027adc8  mov     [rsp+7B0h+var_790], rax; unsigned __int16 *
0x14027adcd  lea     rdx, [rsp+7B0h+var_758]; struct _GUID *
0x14027add2  lea     rcx, [rsp+7B0h+var_770]; this
0x14027add7  call    ?CreateTrustlet@KeyManagement@@YAJU_GUID@@PEAU_PS_TRUSTLET_TKSESSION_ID@@PEAU_TRUSTLET_MAILBOX_KEY@@PEBG3PEAPEAX@Z; KeyManagement::CreateTrustlet(_GUID,_PS_TRUSTLET_TKSESSION_ID *,_TRUSTLET_MAILBOX_KEY *,ushort const *,ushort const *,void * *)
0x14027addc  mov     ebx, eax
0x14027adde  test    eax, eax
0x14027ade0  js      short loc_14027AE16
0x14027ade2  mov     edx, 4E20h; dwMilliseconds
0x14027ade7  mov     rcx, rdi; hHandle
0x14027adea  call    cs:__imp_WaitForSingleObject
0x14027adf1  nop     dword ptr [rax+rax+00h]
0x14027adf6  test    eax, eax
0x14027adf8  jz      short loc_14027AE16
0x14027adfa  cmp     eax, 102h
0x14027adff  jz      short loc_14027AE11
0x14027ae01  cmp     eax, 0FFFFFFFFh
0x14027ae04  jz      loc_14027AD21
0x14027ae0a  mov     ebx, 8000FFFFh
0x14027ae0f  jmp     short loc_14027AE16
0x14027ae11  mov     ebx, 800705B4h
0x14027ae16  mov     rcx, rdi; hObject
0x14027ae19  call    cs:__imp_CloseHandle
0x14027ae20  nop     dword ptr [rax+rax+00h]
0x14027ae25  mov     rcx, [rsp+7B0h+Handle]; Handle
0x14027ae2a  test    rcx, rcx
0x14027ae2d  jz      short loc_14027AE3B
0x14027ae2f  call    cs:__imp_NtClose
0x14027ae36  nop     dword ptr [rax+rax+00h]
0x14027ae3b  mov     eax, ebx
0x14027ae3d  mov     rcx, [rbp+6B0h+var_40]
0x14027ae44  xor     rcx, rsp; StackCookie
0x14027ae47  call    __security_check_cookie
0x14027ae4c  add     rsp, 780h
0x14027ae53  pop     r15
0x14027ae55  pop     r14
0x14027ae57  pop     r12
0x14027ae59  pop     rdi
0x14027ae5a  pop     rsi
0x14027ae5b  pop     rbx
0x14027ae5c  pop     rbp
0x14027ae5d  retn
```
