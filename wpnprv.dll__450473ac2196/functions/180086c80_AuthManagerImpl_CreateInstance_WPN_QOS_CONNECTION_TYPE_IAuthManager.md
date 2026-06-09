# AuthManagerImpl::CreateInstance(_WPN_QOS_CONNECTION_TYPE,IAuthManager * *)

- ea: `0x180086c80`
- end: `0x180086e50`
- name: `?CreateInstance@AuthManagerImpl@@SAJW4_WPN_QOS_CONNECTION_TYPE@@PEAPEAVIAuthManager@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(int, AuthManagerImpl **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180086bd8`

## callees

- `0x18000795c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x180086334`
- `0x180086c80`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180086d16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180086d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086daa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086daa`

## pseudocode

```c
__int64 __fastcall AuthManagerImpl::CreateInstance(int a1, AuthManagerImpl **a2)
{
  PVOID v4; // rcx
  AuthManagerImpl *v5; // rax
  AuthManagerImpl *v6; // rdi
  char *EventW; // rax
  void *v8; // rsi
  unsigned int v9; // ebx
  signed int LastError; // eax
  PVOID *v11; // rcx
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
  }
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  *a2 = 0;
  v5 = (AuthManagerImpl *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = AuthManagerImpl::AuthManagerImpl(v5);
    if ( v6 )
    {
      EventW = (char *)CreateEventW(0, 1, 0, 0);
      v8 = EventW;
      if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( (v9 & 0x80000000) == 0 )
          v9 = -2147467259;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3B4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v9,
          v13);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v9);
        if ( v8 && v8 != (void *)-1LL )
          CloseHandle(v8);
        (*(void (__fastcall **)(AuthManagerImpl *, __int64))(*(_QWORD *)v6 + 16LL))(v6, 1);
      }
      else
      {
        *((_QWORD *)v6 + 4) = EventW;
        v9 = 0;
        *((_DWORD *)v6 + 2) = a1;
        *a2 = v6;
      }
      goto LABEL_25;
    }
  }
  v9 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x3AD,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
    (const char *)0x8007000ELL,
    v13);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, 2147942414LL);
LABEL_25:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 133, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180086c80  push    rbx
0x180086c82  push    rbp
0x180086c83  push    rsi
0x180086c84  push    rdi
0x180086c85  push    r12
0x180086c87  push    r14
0x180086c89  sub     rsp, 28h
0x180086c8d  mov     r14, rdx
0x180086c90  mov     ebp, ecx
0x180086c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180086c99  lea     r12, WPP_GLOBAL_Control
0x180086ca0  cmp     rcx, r12
0x180086ca3  jz      short loc_180086CC6
0x180086ca5  test    byte ptr [rcx+1Ch], 10h
0x180086ca9  jz      short loc_180086CC6
0x180086cab  cmp     byte ptr [rcx+19h], 6
0x180086caf  jb      short loc_180086CC6
0x180086cb1  mov     rcx, [rcx+10h]
0x180086cb5  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086cbc  mov     edx, 80h
0x180086cc1  call    WPP_SF_
0x180086cc6  test    r14, r14
0x180086cc9  jnz     short loc_180086CD0
0x180086ccb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180086cd0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086cd7  mov     qword ptr [r14], 0
0x180086cde  mov     ecx, 58h ; 'X'; unsigned __int64
0x180086ce3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086ce8  mov     [rsp+58h+arg_8], rax
0x180086ced  test    rax, rax
0x180086cf0  jz      loc_180086DC6
0x180086cf6  mov     rcx, rax; this
0x180086cf9  call    ??0AuthManagerImpl@@AEAA@XZ; AuthManagerImpl::AuthManagerImpl(void)
0x180086cfe  mov     rdi, rax
0x180086d01  test    rax, rax
0x180086d04  jz      loc_180086DC6
0x180086d0a  xor     r9d, r9d; lpName
0x180086d0d  xor     r8d, r8d; bInitialState
0x180086d10  xor     ecx, ecx; lpEventAttributes
0x180086d12  lea     edx, [r9+1]; bManualReset
0x180086d16  call    cs:__imp_CreateEventW
0x180086d1c  mov     rsi, rax
0x180086d1f  lea     rcx, [rax-1]
0x180086d23  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180086d27  ja      short loc_180086D3A
0x180086d29  mov     [rdi+20h], rax
0x180086d2d  xor     ebx, ebx
0x180086d2f  mov     [rdi+8], ebp
0x180086d32  mov     [r14], rdi
0x180086d35  jmp     loc_180086E11
0x180086d3a  call    cs:__imp_GetLastError
0x180086d40  mov     ebx, eax
0x180086d42  test    eax, eax
0x180086d44  jle     short loc_180086D4F
0x180086d46  movzx   ebx, ax
0x180086d49  or      ebx, 80070000h
0x180086d4f  mov     rcx, [rsp+58h]; this
0x180086d54  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086d5b  test    ebx, ebx
0x180086d5d  mov     eax, 80004005h
0x180086d62  mov     edx, 3B4h; void *
0x180086d67  cmovns  ebx, eax
0x180086d6a  mov     r9d, ebx; char *
0x180086d6d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180086d79  cmp     rcx, r12
0x180086d7c  jz      short loc_180086D9C
0x180086d7e  test    byte ptr [rcx+1Ch], 80h
0x180086d82  jz      short loc_180086D9C
0x180086d84  mov     rcx, [rcx+10h]
0x180086d88  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086d8f  mov     edx, 84h
0x180086d94  mov     r9d, ebx
0x180086d97  call    WPP_SF_d
0x180086d9c  test    rsi, rsi
0x180086d9f  jz      short loc_180086DB0
0x180086da1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180086da5  jz      short loc_180086DB0
0x180086da7  mov     rcx, rsi; hObject
0x180086daa  call    cs:__imp_CloseHandle
0x180086db0  mov     rax, [rdi]
0x180086db3  mov     edx, 1
0x180086db8  mov     rcx, rdi
0x180086dbb  mov     rax, [rax+10h]
0x180086dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086dc4  jmp     short loc_180086E11
0x180086dc6  mov     rcx, [rsp+58h]; this
0x180086dcb  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086dd2  mov     ebx, 8007000Eh
0x180086dd7  mov     edx, 3ADh; void *
0x180086ddc  mov     r9d, ebx; char *
0x180086ddf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180086deb  cmp     rcx, r12
0x180086dee  jz      short loc_180086E41
0x180086df0  test    byte ptr [rcx+1Ch], 80h
0x180086df4  jz      short loc_180086E18
0x180086df6  mov     rcx, [rcx+10h]
0x180086dfa  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086e01  mov     edx, 82h
0x180086e06  mov     r9d, 8007000Eh
0x180086e0c  call    WPP_SF_d
0x180086e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e18  cmp     rcx, r12
0x180086e1b  jz      short loc_180086E41
0x180086e1d  test    byte ptr [rcx+1Ch], 10h
0x180086e21  jz      short loc_180086E41
0x180086e23  cmp     byte ptr [rcx+19h], 6
0x180086e27  jb      short loc_180086E41
0x180086e29  mov     rcx, [rcx+10h]
0x180086e2d  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086e34  mov     edx, 85h
0x180086e39  mov     r9d, ebx
0x180086e3c  call    WPP_SF_d
0x180086e41  mov     eax, ebx
0x180086e43  add     rsp, 28h
0x180086e47  pop     r14
0x180086e49  pop     r12
0x180086e4b  pop     rdi
0x180086e4c  pop     rsi
0x180086e4d  pop     rbp
0x180086e4e  pop     rbx
0x180086e4f  retn
```
