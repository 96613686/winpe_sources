# DVRSourceSink::CreateReaderIdEvent(ulong,void * *,_GUID *,void * *)

- ea: `0x18000569c`
- end: `0x1800057ee`
- name: `?CreateReaderIdEvent@DVRSourceSink@@YAJKPEAPEAXPEAU_GUID@@0@Z`
- size: `338`
- prototype: `__int64 __fastcall(ULONG cCountOfExplicitEntries, void **, void **, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006fbc`

## callees

- `0x1800015f0`
- `0x1800024c4`
- `0x1800027c4`
- `0x18000569c`
- `0x1800057f4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000578f`
- `KERNEL32!CreateEventW` at `0x18000578f`
- `KERNEL32!GetLastError` at `0x18000579a`
- `KERNEL32!GetLastError` at `0x18000579a`
- `RPCRT4!UuidCreate` at `0x1800056f9`
- `RPCRT4!UuidCreate` at `0x1800056f9`

## pseudocode

```c
__int64 __fastcall DVRSourceSink::CreateReaderIdEvent(
        ULONG cCountOfExplicitEntries,
        void **a2,
        UUID *a3,
        struct _GUID *a4)
{
  signed int LastError; // eax
  struct _GUID *v9; // rdx
  unsigned __int16 *v10; // r9
  signed int v11; // ebx
  bool v12; // cc
  enum _ACCESS_MODE v13; // r8d
  struct _SECURITY_ATTRIBUTES *v14; // rcx
  HANDLE EventW; // rax
  UUID v16; // xmm0
  enum _ACCESS_MODE v18; // [rsp+20h] [rbp-E0h]
  void *v19; // [rsp+40h] [rbp-C0h] BYREF
  struct _ACL *v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h]
  UUID Uuid; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  v22 = 0;
  v19 = 0;
  v20 = 0;
  Uuid = 0;
  v21 = 0;
  LastError = UuidCreate(&Uuid);
  v11 = LastError;
  v12 = LastError <= 0;
  if ( !LastError )
  {
    v11 = DVRSourceSink::CreateReaderIdEventName(&Uuid, v9, (unsigned __int64)Name, v10);
    if ( v11 < 0 )
      goto LABEL_12;
    if ( cCountOfExplicitEntries )
    {
      LastError = CreateACL(cCountOfExplicitEntries, a2, v13, 2031619, v18, 2u, &v20, &v19);
      v11 = LastError;
      v12 = LastError <= 0;
      if ( LastError )
        goto LABEL_2;
      v14 = (struct _SECURITY_ATTRIBUTES *)&v21;
      *((_QWORD *)&v21 + 1) = v19;
      LODWORD(v21) = 24;
      LODWORD(v22) = 0;
    }
    else
    {
      v14 = 0;
    }
    EventW = CreateEventW(v14, 0, 0, Name);
    if ( EventW )
    {
      v16 = Uuid;
      *(_QWORD *)&a4->Data1 = EventW;
      v11 = 0;
      *a3 = v16;
      goto LABEL_12;
    }
    LastError = GetLastError();
    v11 = LastError;
    v12 = LastError <= 0;
  }
LABEL_2:
  if ( !v12 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  FreeSecurityDescriptors(&v20, &v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000569c  mov     [rsp-8+arg_8], rbx
0x1800056a1  push    rbp
0x1800056a2  push    rsi
0x1800056a3  push    rdi
0x1800056a4  push    r14
0x1800056a6  push    r15
0x1800056a8  lea     rbp, [rsp-1A0h]
0x1800056b0  sub     rsp, 2A0h
0x1800056b7  mov     rax, cs:__security_cookie
0x1800056be  xor     rax, rsp
0x1800056c1  mov     [rbp+1C0h+var_30], rax
0x1800056c8  xor     eax, eax
0x1800056ca  mov     edi, ecx
0x1800056cc  xorps   xmm0, xmm0
0x1800056cf  mov     [rsp+2C0h+var_260], rax
0x1800056d4  xorps   xmm1, xmm1
0x1800056d7  mov     [rsp+2C0h+var_280], rax
0x1800056dc  lea     rcx, [rsp+2C0h+Uuid]; Uuid
0x1800056e1  mov     [rsp+2C0h+var_278], rax
0x1800056e6  movups  xmmword ptr [rsp+2C0h+Uuid.Data1], xmm0
0x1800056eb  mov     r14, r9
0x1800056ee  mov     rsi, r8
0x1800056f1  movups  [rsp+2C0h+var_270], xmm1
0x1800056f6  mov     r15, rdx
0x1800056f9  call    cs:__imp_UuidCreate
0x1800056ff  mov     ebx, eax
0x180005701  test    eax, eax
0x180005703  jz      short loc_180005719
0x180005705  jle     loc_1800057B7
0x18000570b  movzx   ebx, ax
0x18000570e  or      ebx, 80070000h
0x180005714  jmp     loc_1800057B7
0x180005719  lea     r8, [rbp+1C0h+Name]; unsigned __int64
0x18000571d  lea     rcx, [rsp+2C0h+Uuid]; rguid
0x180005722  call    ?CreateReaderIdEventName@DVRSourceSink@@YAJPEAU_GUID@@_KPEAG@Z; DVRSourceSink::CreateReaderIdEventName(_GUID *,unsigned __int64,ushort *)
0x180005727  mov     ebx, eax
0x180005729  test    eax, eax
0x18000572b  js      loc_1800057B7
0x180005731  test    edi, edi
0x180005733  jz      short loc_180005784
0x180005735  lea     rax, [rsp+2C0h+var_280]
0x18000573a  mov     r9d, 1F0003h; unsigned int
0x180005740  mov     [rsp+2C0h+var_288], rax; void **
0x180005745  mov     rdx, r15; void **
0x180005748  lea     rax, [rsp+2C0h+var_278]
0x18000574d  mov     ecx, edi; cCountOfExplicitEntries
0x18000574f  mov     [rsp+2C0h+var_290], rax; struct _ACL **
0x180005754  mov     [rsp+2C0h+var_298], 2; unsigned int
0x18000575c  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180005761  mov     ebx, eax
0x180005763  test    eax, eax
0x180005765  jnz     short loc_180005705
0x180005767  mov     rax, [rsp+2C0h+var_280]
0x18000576c  lea     rcx, [rsp+2C0h+var_270]
0x180005771  mov     qword ptr [rsp+2C0h+var_270+8], rax
0x180005776  mov     dword ptr [rsp+2C0h+var_270], 18h
0x18000577e  mov     dword ptr [rsp+2C0h+var_260], ebx
0x180005782  jmp     short loc_180005786
0x180005784  xor     ecx, ecx; lpEventAttributes
0x180005786  lea     r9, [rbp+1C0h+Name]; lpName
0x18000578a  xor     r8d, r8d; bInitialState
0x18000578d  xor     edx, edx; bManualReset
0x18000578f  call    cs:__imp_CreateEventW
0x180005795  test    rax, rax
0x180005798  jnz     short loc_1800057A9
0x18000579a  call    cs:__imp_GetLastError
0x1800057a0  mov     ebx, eax
0x1800057a2  test    eax, eax
0x1800057a4  jmp     loc_180005705
0x1800057a9  movups  xmm0, xmmword ptr [rsp+2C0h+Uuid.Data1]
0x1800057ae  mov     [r14], rax
0x1800057b1  xor     ebx, ebx
0x1800057b3  movdqu  xmmword ptr [rsi], xmm0
0x1800057b7  lea     rdx, [rsp+2C0h+var_280]; void **
0x1800057bc  lea     rcx, [rsp+2C0h+var_278]; struct _ACL **
0x1800057c1  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x1800057c6  mov     eax, ebx
0x1800057c8  mov     rcx, [rbp+1C0h+var_30]
0x1800057cf  xor     rcx, rsp; StackCookie
0x1800057d2  call    __security_check_cookie
0x1800057d7  mov     rbx, [rsp+2C0h+arg_8]
0x1800057df  add     rsp, 2A0h
0x1800057e6  pop     r15
0x1800057e8  pop     r14
0x1800057ea  pop     rdi
0x1800057eb  pop     rsi
0x1800057ec  pop     rbp
0x1800057ed  retn
```
