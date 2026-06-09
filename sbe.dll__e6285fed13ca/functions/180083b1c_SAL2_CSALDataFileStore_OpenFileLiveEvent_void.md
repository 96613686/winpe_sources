# SAL2::CSALDataFileStore::OpenFileLiveEvent(void)

- ea: `0x180083b1c`
- end: `0x180083c47`
- name: `?OpenFileLiveEvent@CSALDataFileStore@SAL2@@AEAAJXZ`
- size: `299`
- prototype: `__int64 __fastcall(SAL2::CSALDataFileStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008035c`

## callees

- `0x180001c00`
- `0x180080b28`
- `0x1800812f8`
- `0x180082c60`
- `0x180083b1c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180083bc9`
- `KERNEL32!CreateEventW` at `0x180083bc9`
- `KERNEL32!GetLastError` at `0x180083bdb`
- `KERNEL32!GetLastError` at `0x180083bdb`
- `KERNEL32!OpenEventW` at `0x180083c02`
- `KERNEL32!OpenEventW` at `0x180083c02`

## pseudocode

```c
__int64 __fastcall SAL2::CSALDataFileStore::OpenFileLiveEvent(
        SAL2::CSALDataFileStore *this,
        __int64 a2,
        enum _ACCESS_MODE a3)
{
  __int64 v3; // rdx
  unsigned __int64 v5; // r9
  signed int v6; // ebx
  int v7; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v10; // rax
  unsigned int v12[4]; // [rsp+30h] [rbp-278h] BYREF
  _BYTE v13[48]; // [rsp+40h] [rbp-268h] BYREF
  LPSECURITY_ATTRIBUTES lpEventAttributes; // [rsp+70h] [rbp-238h]
  WCHAR Name[264]; // [rsp+80h] [rbp-228h] BYREF

  v3 = *((_QWORD *)this + 139);
  v12[0] = 0;
  SAL2::CSALSecurityObject::CSALSecurityObject(
    (SAL2::CSALSecurityObject *)v13,
    *(struct SAL2::CW32Sid **)(v3 + 280),
    a3,
    0x100002u,
    v12);
  v6 = v12[0];
  if ( v12[0] )
  {
    if ( (int)v12[0] > 0 )
    {
      v7 = LOWORD(v12[0]);
LABEL_4:
      v6 = v7 | 0x80070000;
    }
  }
  else
  {
    v6 = SAL2::CSALDataFileStore::FormLiveFileEventName(
           *((_DWORD *)this + 272),
           *((_DWORD *)this + 273),
           *((_DWORD *)this + 274),
           v5,
           Name);
    if ( v6 >= 0 )
    {
      EventW = CreateEventW(lpEventAttributes, 1, 0, Name);
      *((_QWORD *)this + 140) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        if ( LastError != 5 )
        {
          if ( LastError <= 0 )
          {
            v6 = LastError;
            goto LABEL_13;
          }
          v7 = (unsigned __int16)LastError;
          goto LABEL_4;
        }
        v10 = OpenEventW(0x100002u, 0, Name);
        *((_QWORD *)this + 140) = v10;
        if ( !v10 )
          v6 = -2147024891;
      }
    }
  }
LABEL_13:
  SAL2::CSALSecurityObject::~CSALSecurityObject((SAL2::CSALSecurityObject *)v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180083b1c  mov     [rsp+arg_8], rbx
0x180083b21  push    rdi
0x180083b22  sub     rsp, 2A0h
0x180083b29  mov     rax, cs:__security_cookie
0x180083b30  xor     rax, rsp
0x180083b33  mov     [rsp+2A8h+var_18], rax
0x180083b3b  mov     rdx, [rcx+458h]
0x180083b42  lea     rax, [rsp+2A8h+var_278]
0x180083b47  mov     rdi, rcx
0x180083b4a  mov     [rsp+2A8h+var_278], 0
0x180083b52  mov     r9d, 100002h; unsigned int
0x180083b58  mov     [rsp+2A8h+Buffer], rax; unsigned int *
0x180083b5d  lea     rcx, [rsp+2A8h+var_268]; this
0x180083b62  mov     rdx, [rdx+118h]; struct SAL2::CW32Sid *
0x180083b69  call    ??0CSALSecurityObject@SAL2@@QEAA@PEAVCW32Sid@1@W4_ACCESS_MODE@@KPEAK@Z; SAL2::CSALSecurityObject::CSALSecurityObject(SAL2::CW32Sid *,_ACCESS_MODE,ulong,ulong *)
0x180083b6e  mov     ebx, [rsp+2A8h+var_278]
0x180083b72  test    ebx, ebx
0x180083b74  jz      short loc_180083B8A
0x180083b76  jle     loc_180083C1A
0x180083b7c  movzx   ebx, bx
0x180083b7f  or      ebx, 80070000h
0x180083b85  jmp     loc_180083C1A
0x180083b8a  mov     r8d, [rdi+448h]; unsigned int
0x180083b91  lea     rax, [rsp+2A8h+Name]
0x180083b99  mov     edx, [rdi+444h]; unsigned int
0x180083b9f  mov     ecx, [rdi+440h]; unsigned int
0x180083ba5  mov     [rsp+2A8h+Buffer], rax; Buffer
0x180083baa  call    ?FormLiveFileEventName@CSALDataFileStore@SAL2@@SAJKKK_KPEAG@Z; SAL2::CSALDataFileStore::FormLiveFileEventName(ulong,ulong,ulong,unsigned __int64,ushort *)
0x180083baf  mov     ebx, eax
0x180083bb1  test    eax, eax
0x180083bb3  js      short loc_180083C1A
0x180083bb5  mov     rcx, [rsp+2A8h+lpEventAttributes]; lpEventAttributes
0x180083bba  lea     r9, [rsp+2A8h+Name]; lpName
0x180083bc2  xor     r8d, r8d; bInitialState
0x180083bc5  lea     edx, [r8+1]; bManualReset
0x180083bc9  call    cs:__imp_CreateEventW
0x180083bcf  mov     [rdi+460h], rax
0x180083bd6  test    rax, rax
0x180083bd9  jnz     short loc_180083C1A
0x180083bdb  call    cs:__imp_GetLastError
0x180083be1  cmp     eax, 5
0x180083be4  jz      short loc_180083BF3
0x180083be6  test    eax, eax
0x180083be8  jg      short loc_180083BEE
0x180083bea  mov     ebx, eax
0x180083bec  jmp     short loc_180083C1A
0x180083bee  movzx   ebx, ax
0x180083bf1  jmp     short loc_180083B7F
0x180083bf3  lea     r8, [rsp+2A8h+Name]; lpName
0x180083bfb  xor     edx, edx; bInheritHandle
0x180083bfd  mov     ecx, 100002h; dwDesiredAccess
0x180083c02  call    cs:__imp_OpenEventW
0x180083c08  test    rax, rax
0x180083c0b  mov     [rdi+460h], rax
0x180083c12  mov     ecx, 80070005h
0x180083c17  cmovz   ebx, ecx
0x180083c1a  lea     rcx, [rsp+2A8h+var_268]; this
0x180083c1f  call    ??1CSALSecurityObject@SAL2@@UEAA@XZ; SAL2::CSALSecurityObject::~CSALSecurityObject(void)
0x180083c24  mov     eax, ebx
0x180083c26  mov     rcx, [rsp+2A8h+var_18]
0x180083c2e  xor     rcx, rsp; StackCookie
0x180083c31  call    __security_check_cookie
0x180083c36  mov     rbx, [rsp+2A8h+arg_8]
0x180083c3e  add     rsp, 2A0h
0x180083c45  pop     rdi
0x180083c46  retn
```
