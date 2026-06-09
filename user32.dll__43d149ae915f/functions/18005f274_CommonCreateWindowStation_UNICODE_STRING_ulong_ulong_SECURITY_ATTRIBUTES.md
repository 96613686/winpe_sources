# CommonCreateWindowStation(_UNICODE_STRING *,ulong,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18005f274`
- end: `0x18005f608`
- name: `?CommonCreateWindowStation@@YAPEAUHWINSTA__@@PEAU_UNICODE_STRING@@KKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `916`
- prototype: `HWINSTA __fastcall(struct _UNICODE_STRING *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f220`
- `0x180093f40`

## callees

- `0x18001867c`
- `0x180019650`
- `0x180019860`
- `0x180020e80`
- `0x18004ed44`
- `0x1800565e0`
- `0x18005cdc0`
- `0x18005f274`
- `0x180066f50`
- `0x18006eaec`
- `0x180096dc5`
- `0x180096ddd`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserCreateWindowStationEx` at `0x18005f596`
- `win32u!NtUserCreateWindowStationEx` at `0x18005f596`
- `win32u!NtUserCreateWindowStation` at `0x18005f5b8`
- `win32u!NtUserCreateWindowStation` at `0x18005f5b8`
- `ntdll!RtlSetLastWin32Error` at `0x18005f2fa`
- `ntdll!RtlSetLastWin32Error` at `0x18005f2fa`
- `ntdll!NtOpenDirectoryObject` at `0x18005f4ea`
- `ntdll!NtOpenDirectoryObject` at `0x18005f4ea`
- `ntdll!RtlGetActiveConsoleId` at `0x18005f336`
- `ntdll!RtlGetActiveConsoleId` at `0x18005f336`
- `ntdll!NtClose` at `0x18005f5cb`
- `ntdll!NtClose` at `0x18005f5cb`
- `ntdll!RtlInitUnicodeString` at `0x18005f491`
- `ntdll!RtlInitUnicodeString` at `0x18005f491`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005f319`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005f319`

## pseudocode

```c
__int64 __fastcall CommonCreateWindowStation(
        struct _UNICODE_STRING *a1,
        unsigned int a2,
        int a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  __int64 v8; // r15
  ULONG SessionId; // ebx
  ULONG v10; // ebx
  void *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // eax
  unsigned __int64 v14; // rdx
  int v15; // r14d
  NTSTATUS v16; // eax
  void *v17; // rax
  __int64 v18; // rax
  unsigned __int16 v19[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v20; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v21; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v22; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v23; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v24; // [rsp+64h] [rbp-9Ch]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v28; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[800]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t String1[16]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v31[256]; // [rsp+400h] [rbp+300h] BYREF

  v24 = a2;
  FileHandle = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  memset_0(v29, 0, 0x318u);
  if ( !(unsigned int)Feature_MarkWinstaIOForAgentic__private_IsEnabledDeviceUsageNoInline() && (a3 & 0xFFFFFFF0) != 0 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v8 = 0;
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId == (unsigned int)WTSGetServiceSessionId() )
    goto LABEL_11;
  v10 = NtCurrentPeb()->SessionId;
  if ( v10 == (unsigned int)RtlGetActiveConsoleId() )
    goto LABEL_11;
  v19[0] = 0;
  if ( !(unsigned int)GetRemoteKeyboardLayout(String1, v19) )
    goto LABEL_11;
  v23 = -2147483647;
  if ( (a3 & 2) != 0 )
    v23 = -1610612735;
  v11 = OpenKeyboardLayoutFile(String1, v19[0], &v23, &v22, &v21, &v20, (struct tagKBDTABLE_MULT_INTERNAL *)v29);
  if ( !v11 )
  {
LABEL_11:
    *(_DWORD *)v19 = -2147483645;
    GetActiveKeyboardName(String1);
    v13 = *(_DWORD *)v19;
    while ( 1 )
    {
      if ( (a3 & 2) != 0 )
        *(_DWORD *)v19 = v13 | 0x20000000;
      v11 = OpenKeyboardLayoutFile(
              String1,
              0,
              (unsigned int *)v19,
              &v22,
              &v21,
              &v20,
              (struct tagKBDTABLE_MULT_INTERNAL *)v29);
      if ( v11 )
      {
        v12 = v20;
        if ( v20 != 67699721 )
          break;
      }
      if ( !wcscmp_0(String1, L"00000409") || (StringCchCopyW(String1, 9u, L"00000409"), v11) )
      {
        v12 = 67699721;
        break;
      }
      v13 = *(_DWORD *)v19 & 0xFFFFFFFD;
      *(_DWORD *)v19 &= ~2u;
    }
  }
  else
  {
    v12 = v20;
  }
  if ( (unsigned int)CtxInitUser32() )
  {
    RtlInitUnicodeString(&DestinationString, String1);
    v15 = 64;
    if ( a1->Length )
    {
      v28 = 0;
      GetWindowStationName(v31, v14, &v28);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v28;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v16 = NtOpenDirectoryObject(&FileHandle, 4u, &ObjectAttributes);
      if ( v16 < 0 )
      {
        SetLastNtError((unsigned int)v16);
        goto LABEL_37;
      }
      v17 = FileHandle;
    }
    else
    {
      a1 = 0;
      FileHandle = 0;
      v17 = 0;
    }
    ObjectAttributes.RootDirectory = v17;
    ObjectAttributes.Length = 48;
    if ( a4 && a4->bInheritHandle )
      v15 = 66;
    ObjectAttributes.ObjectName = a1;
    ObjectAttributes.Attributes = v15 | (((a3 & 1) == 0) << 7);
    if ( a4 )
      ObjectAttributes.SecurityDescriptor = a4->lpSecurityDescriptor;
    else
      ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    if ( (a3 & 6) != 0 )
      v18 = NtUserCreateWindowStationEx(&ObjectAttributes, v24, v11, v22, v21, v29, &DestinationString, v12, a3);
    else
      v18 = NtUserCreateWindowStation(&ObjectAttributes, v24, v11, v22, v21, v29, &DestinationString, v12);
    v8 = v18;
    if ( FileHandle )
      NtClose(FileHandle);
  }
LABEL_37:
  if ( v11 )
    CloseKeyboardLayoutFile(v11, (struct tagKBDTABLE_MULT_INTERNAL *)v29);
  return v8;
}

```

## disassembly

```asm
0x18005f274  push    rbp
0x18005f276  push    rbx
0x18005f277  push    rsi
0x18005f278  push    rdi
0x18005f279  push    r12
0x18005f27b  push    r13
0x18005f27d  push    r14
0x18005f27f  push    r15
0x18005f281  lea     rbp, [rsp-518h]
0x18005f289  sub     rsp, 618h
0x18005f290  mov     rax, cs:__security_cookie
0x18005f297  xor     rax, rsp
0x18005f29a  mov     [rbp+550h+var_50], rax
0x18005f2a1  xorps   xmm0, xmm0
0x18005f2a4  mov     [rsp+650h+var_5EC], edx
0x18005f2a8  xor     edi, edi
0x18005f2aa  mov     esi, r8d
0x18005f2ad  mov     r12, rcx
0x18005f2b0  mov     [rsp+650h+FileHandle], rdi
0x18005f2b5  xor     edx, edx; Val
0x18005f2b7  mov     [rsp+650h+var_5F4], edi
0x18005f2bb  mov     r8d, 318h; Size
0x18005f2c1  mov     [rsp+650h+var_5F8], edi
0x18005f2c5  lea     rcx, [rbp+550h+var_590]; void *
0x18005f2c9  mov     [rsp+650h+var_5FC], edi
0x18005f2cd  movups  xmmword ptr [rsp+650h+ObjectAttributes.Length], xmm0
0x18005f2d2  mov     r13, r9
0x18005f2d5  movups  xmmword ptr [rbp+550h+ObjectAttributes.ObjectName], xmm0
0x18005f2d9  movups  xmmword ptr [rbp+550h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f2dd  movups  xmmword ptr [rbp+550h+DestinationString.Length], xmm0
0x18005f2e1  call    memset_0
0x18005f2e6  call    Feature_MarkWinstaIOForAgentic__private_IsEnabledDeviceUsageNoInline
0x18005f2eb  test    eax, eax
0x18005f2ed  jnz     short loc_18005F307
0x18005f2ef  test    esi, 0FFFFFFF0h
0x18005f2f5  jz      short loc_18005F307
0x18005f2f7  lea     ecx, [rdi+57h]; LastError
0x18005f2fa  call    cs:__imp_RtlSetLastWin32Error
0x18005f300  xor     eax, eax
0x18005f302  jmp     loc_18005F5E5
0x18005f307  mov     rax, gs:60h
0x18005f310  mov     r15, rdi
0x18005f313  mov     ebx, [rax+2C0h]
0x18005f319  call    cs:__imp_WTSGetServiceSessionId
0x18005f31f  cmp     ebx, eax
0x18005f321  jz      loc_18005F3B9
0x18005f327  mov     rax, gs:60h
0x18005f330  mov     ebx, [rax+2C0h]
0x18005f336  call    cs:__imp_RtlGetActiveConsoleId
0x18005f33c  cmp     ebx, eax
0x18005f33e  jz      short loc_18005F3B9
0x18005f340  lea     rdx, [rsp+650h+var_600]; unsigned __int16 *
0x18005f345  mov     [rsp+650h+var_600], di
0x18005f34a  lea     rcx, [rbp+550h+String1]; unsigned __int16 *
0x18005f351  call    ?GetRemoteKeyboardLayout@@YAHPEAG0@Z; GetRemoteKeyboardLayout(ushort *,ushort *)
0x18005f356  test    eax, eax
0x18005f358  jz      short loc_18005F3B9
0x18005f35a  mov     [rsp+650h+var_5F0], 80000001h
0x18005f362  test    sil, 2
0x18005f366  jz      short loc_18005F370
0x18005f368  mov     [rsp+650h+var_5F0], 0A0000001h
0x18005f370  movzx   edx, [rsp+650h+var_600]; unsigned __int16
0x18005f375  lea     rax, [rbp+550h+var_590]
0x18005f379  mov     [rsp+650h+var_620], rax; struct tagKBDTABLE_MULT_INTERNAL *
0x18005f37e  lea     r9, [rsp+650h+var_5F4]; unsigned int *
0x18005f383  lea     rax, [rsp+650h+var_5FC]
0x18005f388  mov     [rsp+650h+var_628], rax; unsigned int *
0x18005f38d  lea     r8, [rsp+650h+var_5F0]; unsigned int *
0x18005f392  lea     rax, [rsp+650h+var_5F8]
0x18005f397  lea     rcx, [rbp+550h+String1]; unsigned __int16 *
0x18005f39e  mov     [rsp+650h+var_630], rax; unsigned int *
0x18005f3a3  call    ?OpenKeyboardLayoutFile@@YAPEAXPEAGGPEAI111PEAUtagKBDTABLE_MULT_INTERNAL@@@Z; OpenKeyboardLayoutFile(ushort *,ushort,uint *,uint *,uint *,uint *,tagKBDTABLE_MULT_INTERNAL *)
0x18005f3a8  mov     rbx, rax
0x18005f3ab  test    rax, rax
0x18005f3ae  jz      short loc_18005F3B9
0x18005f3b0  mov     edi, [rsp+650h+var_5FC]
0x18005f3b4  jmp     loc_18005F479
0x18005f3b9  lea     rcx, [rbp+550h+String1]; unsigned __int16 *
0x18005f3c0  mov     dword ptr [rsp+650h+var_600], 80000003h
0x18005f3c8  call    GetActiveKeyboardName
0x18005f3cd  mov     eax, dword ptr [rsp+650h+var_600]
0x18005f3d1  mov     r14d, esi
0x18005f3d4  and     r14d, 2
0x18005f3d8  test    r14d, r14d
0x18005f3db  jz      short loc_18005F3E5
0x18005f3dd  bts     eax, 1Dh
0x18005f3e1  mov     dword ptr [rsp+650h+var_600], eax
0x18005f3e5  lea     rax, [rbp+550h+var_590]
0x18005f3e9  xor     edx, edx; unsigned __int16
0x18005f3eb  mov     [rsp+650h+var_620], rax; struct tagKBDTABLE_MULT_INTERNAL *
0x18005f3f0  lea     r9, [rsp+650h+var_5F4]; unsigned int *
0x18005f3f5  lea     rax, [rsp+650h+var_5FC]
0x18005f3fa  mov     [rsp+650h+var_628], rax; unsigned int *
0x18005f3ff  lea     r8, [rsp+650h+var_600]; unsigned int *
0x18005f404  lea     rax, [rsp+650h+var_5F8]
0x18005f409  lea     rcx, [rbp+550h+String1]; unsigned __int16 *
0x18005f410  mov     [rsp+650h+var_630], rax; unsigned int *
0x18005f415  call    ?OpenKeyboardLayoutFile@@YAPEAXPEAGGPEAI111PEAUtagKBDTABLE_MULT_INTERNAL@@@Z; OpenKeyboardLayoutFile(ushort *,ushort,uint *,uint *,uint *,uint *,tagKBDTABLE_MULT_INTERNAL *)
0x18005f41a  mov     rbx, rax
0x18005f41d  test    rax, rax
0x18005f420  jz      short loc_18005F430
0x18005f422  mov     edi, [rsp+650h+var_5FC]
0x18005f426  cmp     edi, 4090409h
0x18005f42c  jnz     short loc_18005F479
0x18005f42e  xor     edi, edi
0x18005f430  lea     rdx, a00000409; "00000409"
0x18005f437  lea     rcx, [rbp+550h+String1]; String1
0x18005f43e  call    wcscmp_0
0x18005f443  test    eax, eax
0x18005f445  jz      short loc_18005F474
0x18005f447  lea     r8, a00000409; "00000409"
0x18005f44e  mov     edx, 9; unsigned __int64
0x18005f453  lea     rcx, [rbp+550h+String1]; unsigned __int16 *
0x18005f45a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005f45f  test    rbx, rbx
0x18005f462  jnz     short loc_18005F474
0x18005f464  mov     eax, dword ptr [rsp+650h+var_600]
0x18005f468  and     eax, 0FFFFFFFDh
0x18005f46b  mov     dword ptr [rsp+650h+var_600], eax
0x18005f46f  jmp     loc_18005F3D8
0x18005f474  mov     edi, 4090409h
0x18005f479  call    CtxInitUser32
0x18005f47e  test    eax, eax
0x18005f480  jz      loc_18005F5D1
0x18005f486  lea     rdx, [rbp+550h+String1]; SourceString
0x18005f48d  lea     rcx, [rbp+550h+DestinationString]; DestinationString
0x18005f491  call    cs:__imp_RtlInitUnicodeString
0x18005f497  xor     ecx, ecx
0x18005f499  lea     r14d, [rcx+40h]
0x18005f49d  cmp     [r12], cx
0x18005f4a2  jz      short loc_18005F509
0x18005f4a4  xorps   xmm0, xmm0
0x18005f4a7  lea     r8, [rbp+550h+var_5A0]; struct _UNICODE_STRING *
0x18005f4ab  lea     rcx, [rbp+550h+var_250]; unsigned __int16 *
0x18005f4b2  movups  xmmword ptr [rbp+550h+var_5A0.Length], xmm0
0x18005f4b6  call    ?GetWindowStationName@@YAXPEAG_KPEAU_UNICODE_STRING@@@Z; GetWindowStationName(ushort *,unsigned __int64,_UNICODE_STRING *)
0x18005f4bb  lea     rax, [rbp+550h+var_5A0]
0x18005f4bf  mov     [rsp+650h+ObjectAttributes.Length], 30h ; '0'
0x18005f4c7  xorps   xmm0, xmm0
0x18005f4ca  mov     [rbp+550h+ObjectAttributes.ObjectName], rax
0x18005f4ce  lea     r8, [rsp+650h+ObjectAttributes]; ObjectAttributes
0x18005f4d3  mov     [rsp+650h+ObjectAttributes.RootDirectory], r15
0x18005f4d8  lea     edx, [r14-3Ch]; DesiredAccess
0x18005f4dc  mov     [rbp+550h+ObjectAttributes.Attributes], r14d
0x18005f4e0  lea     rcx, [rsp+650h+FileHandle]; FileHandle
0x18005f4e5  movdqu  xmmword ptr [rbp+550h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f4ea  call    cs:__imp_NtOpenDirectoryObject
0x18005f4f0  xor     ecx, ecx
0x18005f4f2  test    eax, eax
0x18005f4f4  jns     short loc_18005F502
0x18005f4f6  mov     ecx, eax
0x18005f4f8  call    SetLastNtError
0x18005f4fd  jmp     loc_18005F5D1
0x18005f502  mov     rax, [rsp+650h+FileHandle]
0x18005f507  jmp     short loc_18005F514
0x18005f509  mov     r12, rcx
0x18005f50c  mov     [rsp+650h+FileHandle], rcx
0x18005f511  mov     rax, rcx
0x18005f514  mov     [rsp+650h+ObjectAttributes.RootDirectory], rax
0x18005f519  mov     eax, esi
0x18005f51b  not     eax
0x18005f51d  mov     [rsp+650h+ObjectAttributes.Length], 30h ; '0'
0x18005f525  and     eax, 1
0x18005f528  shl     eax, 7
0x18005f52b  test    r13, r13
0x18005f52e  jz      short loc_18005F53C
0x18005f530  cmp     [r13+10h], ecx
0x18005f534  jz      short loc_18005F53C
0x18005f536  mov     r14d, 42h ; 'B'
0x18005f53c  or      eax, r14d
0x18005f53f  mov     [rbp+550h+ObjectAttributes.ObjectName], r12
0x18005f543  mov     [rbp+550h+ObjectAttributes.Attributes], eax
0x18005f546  test    r13, r13
0x18005f549  jz      short loc_18005F555
0x18005f54b  mov     rax, [r13+8]
0x18005f54f  mov     [rbp+550h+ObjectAttributes.SecurityDescriptor], rax
0x18005f553  jmp     short loc_18005F559
0x18005f555  mov     [rbp+550h+ObjectAttributes.SecurityDescriptor], rcx
0x18005f559  mov     r9d, [rsp+650h+var_5F4]
0x18005f55e  lea     rax, [rbp+550h+DestinationString]
0x18005f562  mov     edx, [rsp+650h+var_5EC]
0x18005f566  mov     r8, rbx
0x18005f569  mov     [rbp+550h+ObjectAttributes.SecurityQualityOfService], rcx
0x18005f56d  lea     rcx, [rsp+650h+ObjectAttributes]
0x18005f572  test    sil, 6
0x18005f576  jz      short loc_18005F59E
0x18005f578  mov     [rsp+650h+var_610], esi
0x18005f57c  mov     [rsp+650h+var_618], edi
0x18005f580  mov     [rsp+650h+var_620], rax
0x18005f585  lea     rax, [rbp+550h+var_590]
0x18005f589  mov     [rsp+650h+var_628], rax
0x18005f58e  mov     eax, [rsp+650h+var_5F8]
0x18005f592  mov     dword ptr [rsp+650h+var_630], eax
0x18005f596  call    cs:__imp_NtUserCreateWindowStationEx
0x18005f59c  jmp     short loc_18005F5BE
0x18005f59e  mov     [rsp+650h+var_618], edi
0x18005f5a2  mov     [rsp+650h+var_620], rax
0x18005f5a7  lea     rax, [rbp+550h+var_590]
0x18005f5ab  mov     [rsp+650h+var_628], rax
0x18005f5b0  mov     eax, [rsp+650h+var_5F8]
0x18005f5b4  mov     dword ptr [rsp+650h+var_630], eax
0x18005f5b8  call    cs:__imp_NtUserCreateWindowStation
0x18005f5be  mov     rcx, [rsp+650h+FileHandle]; Handle
0x18005f5c3  mov     r15, rax
0x18005f5c6  test    rcx, rcx
0x18005f5c9  jz      short loc_18005F5D1
0x18005f5cb  call    cs:__imp_NtClose
0x18005f5d1  test    rbx, rbx
0x18005f5d4  jz      short loc_18005F5E2
0x18005f5d6  lea     rdx, [rbp+550h+var_590]; struct tagKBDTABLE_MULT_INTERNAL *
0x18005f5da  mov     rcx, rbx; void *
0x18005f5dd  call    ?CloseKeyboardLayoutFile@@YAXPEAXPEAUtagKBDTABLE_MULT_INTERNAL@@@Z; CloseKeyboardLayoutFile(void *,tagKBDTABLE_MULT_INTERNAL *)
0x18005f5e2  mov     rax, r15
0x18005f5e5  mov     rcx, [rbp+550h+var_50]
0x18005f5ec  xor     rcx, rsp; StackCookie
0x18005f5ef  call    __security_check_cookie
0x18005f5f4  add     rsp, 618h
0x18005f5fb  pop     r15
0x18005f5fd  pop     r14
0x18005f5ff  pop     r13
0x18005f601  pop     r12
0x18005f603  pop     rdi
0x18005f604  pop     rsi
0x18005f605  pop     rbx
0x18005f606  pop     rbp
0x18005f607  retn
```
