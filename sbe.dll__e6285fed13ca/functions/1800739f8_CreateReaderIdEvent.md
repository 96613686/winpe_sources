# CreateReaderIdEvent

- ea: `0x1800739f8`
- end: `0x180073b40`
- name: `CreateReaderIdEvent`
- size: `328`
- prototype: `__int64 __fastcall(ULONG cCountOfExplicitEntries, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800754a4`

## callees

- `0x180001c00`
- `0x180073368`
- `0x1800739f8`
- `0x180073b48`
- `0x180073ebc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180073ae8`
- `KERNEL32!CreateEventW` at `0x180073ae8`
- `KERNEL32!GetLastError` at `0x180073af3`
- `KERNEL32!GetLastError` at `0x180073af3`
- `RPCRT4!UuidCreate` at `0x180073a52`
- `RPCRT4!UuidCreate` at `0x180073a52`

## pseudocode

```c
__int64 __fastcall CreateReaderIdEvent(ULONG cCountOfExplicitEntries, void **a2, UUID *a3, _QWORD *a4)
{
  signed int LastError; // eax
  signed int v9; // ebx
  bool v10; // cc
  enum _ACCESS_MODE v11; // r8d
  struct _SECURITY_ATTRIBUTES *v12; // rcx
  HANDLE EventW; // rax
  UUID v14; // xmm0
  enum _ACCESS_MODE v16; // [rsp+20h] [rbp-E0h]
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  struct _ACL *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h]
  UUID Uuid; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  v20 = 0;
  v17 = 0;
  v18 = 0;
  Uuid = 0;
  v19 = 0;
  LastError = UuidCreate(&Uuid);
  v9 = LastError;
  v10 = LastError <= 0;
  if ( !LastError )
  {
    v9 = CreateReaderIdEventName(&Uuid);
    if ( v9 < 0 )
      goto LABEL_12;
    if ( cCountOfExplicitEntries )
    {
      LastError = CreateACL(cCountOfExplicitEntries, a2, v11, 2031619, v16, 2u, &v18, &v17);
      v9 = LastError;
      v10 = LastError <= 0;
      if ( LastError )
        goto LABEL_2;
      v12 = (struct _SECURITY_ATTRIBUTES *)&v19;
      *((_QWORD *)&v19 + 1) = v17;
      LODWORD(v19) = 24;
      LODWORD(v20) = 0;
    }
    else
    {
      v12 = 0;
    }
    EventW = CreateEventW(v12, 0, 0, Name);
    if ( EventW )
    {
      v14 = Uuid;
      *a4 = EventW;
      v9 = 0;
      *a3 = v14;
      goto LABEL_12;
    }
    LastError = GetLastError();
    v9 = LastError;
    v10 = LastError <= 0;
  }
LABEL_2:
  if ( !v10 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  FreeSecurityDescriptors(&v18, &v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800739f8  push    rbp
0x1800739fa  push    rbx
0x1800739fb  push    rsi
0x1800739fc  push    rdi
0x1800739fd  push    r14
0x1800739ff  push    r15
0x180073a01  lea     rbp, [rsp-1A8h]
0x180073a09  sub     rsp, 2A8h
0x180073a10  mov     rax, cs:__security_cookie
0x180073a17  xor     rax, rsp
0x180073a1a  mov     [rbp+1D0h+var_40], rax
0x180073a21  xor     eax, eax
0x180073a23  mov     edi, ecx
0x180073a25  xorps   xmm0, xmm0
0x180073a28  mov     [rsp+2D0h+var_270], rax
0x180073a2d  xorps   xmm1, xmm1
0x180073a30  mov     [rsp+2D0h+var_290], rax
0x180073a35  lea     rcx, [rsp+2D0h+Uuid]; Uuid
0x180073a3a  mov     [rsp+2D0h+var_288], rax
0x180073a3f  movups  xmmword ptr [rsp+2D0h+Uuid.Data1], xmm0
0x180073a44  mov     r14, r9
0x180073a47  mov     rsi, r8
0x180073a4a  movups  [rsp+2D0h+var_280], xmm1
0x180073a4f  mov     r15, rdx
0x180073a52  call    cs:__imp_UuidCreate
0x180073a58  mov     ebx, eax
0x180073a5a  test    eax, eax
0x180073a5c  jz      short loc_180073A72
0x180073a5e  jle     loc_180073B10
0x180073a64  movzx   ebx, ax
0x180073a67  or      ebx, 80070000h
0x180073a6d  jmp     loc_180073B10
0x180073a72  lea     r8, [rbp+1D0h+Name]
0x180073a76  lea     rcx, [rsp+2D0h+Uuid]; rguid
0x180073a7b  call    CreateReaderIdEventName
0x180073a80  mov     ebx, eax
0x180073a82  test    eax, eax
0x180073a84  js      loc_180073B10
0x180073a8a  test    edi, edi
0x180073a8c  jz      short loc_180073ADD
0x180073a8e  lea     rax, [rsp+2D0h+var_290]
0x180073a93  mov     r9d, 1F0003h; unsigned int
0x180073a99  mov     [rsp+2D0h+var_298], rax; void **
0x180073a9e  mov     rdx, r15; void **
0x180073aa1  lea     rax, [rsp+2D0h+var_288]
0x180073aa6  mov     ecx, edi; cCountOfExplicitEntries
0x180073aa8  mov     [rsp+2D0h+var_2A0], rax; struct _ACL **
0x180073aad  mov     [rsp+2D0h+var_2A8], 2; unsigned int
0x180073ab5  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180073aba  mov     ebx, eax
0x180073abc  test    eax, eax
0x180073abe  jnz     short loc_180073A5E
0x180073ac0  mov     rax, [rsp+2D0h+var_290]
0x180073ac5  lea     rcx, [rsp+2D0h+var_280]
0x180073aca  mov     qword ptr [rsp+2D0h+var_280+8], rax
0x180073acf  mov     dword ptr [rsp+2D0h+var_280], 18h
0x180073ad7  mov     dword ptr [rsp+2D0h+var_270], ebx
0x180073adb  jmp     short loc_180073ADF
0x180073add  xor     ecx, ecx; lpEventAttributes
0x180073adf  lea     r9, [rbp+1D0h+Name]; lpName
0x180073ae3  xor     r8d, r8d; bInitialState
0x180073ae6  xor     edx, edx; bManualReset
0x180073ae8  call    cs:__imp_CreateEventW
0x180073aee  test    rax, rax
0x180073af1  jnz     short loc_180073B02
0x180073af3  call    cs:__imp_GetLastError
0x180073af9  mov     ebx, eax
0x180073afb  test    eax, eax
0x180073afd  jmp     loc_180073A5E
0x180073b02  movups  xmm0, xmmword ptr [rsp+2D0h+Uuid.Data1]
0x180073b07  mov     [r14], rax
0x180073b0a  xor     ebx, ebx
0x180073b0c  movdqu  xmmword ptr [rsi], xmm0
0x180073b10  lea     rdx, [rsp+2D0h+var_290]; void **
0x180073b15  lea     rcx, [rsp+2D0h+var_288]; struct _ACL **
0x180073b1a  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x180073b1f  mov     eax, ebx
0x180073b21  mov     rcx, [rbp+1D0h+var_40]
0x180073b28  xor     rcx, rsp; StackCookie
0x180073b2b  call    __security_check_cookie
0x180073b30  add     rsp, 2A8h
0x180073b37  pop     r15
0x180073b39  pop     r14
0x180073b3b  pop     rdi
0x180073b3c  pop     rsi
0x180073b3d  pop     rbx
0x180073b3e  pop     rbp
0x180073b3f  retn
```
