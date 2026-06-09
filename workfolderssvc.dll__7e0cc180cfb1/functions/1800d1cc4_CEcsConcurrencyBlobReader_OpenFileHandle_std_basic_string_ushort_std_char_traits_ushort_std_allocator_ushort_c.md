# CEcsConcurrencyBlobReader::OpenFileHandle(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_FILE_ID_128,ulong,EcsUniqueHandle<void *,Win32HandleDeleter,-1> &)

- ea: `0x1800d1cc4`
- end: `0x1800d1fdd`
- name: `?OpenFileHandle@CEcsConcurrencyBlobReader@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILE_ID_128@@KAEAV?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@@Z`
- size: `793`
- prototype: `void __fastcall(__int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d1364`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x18000430d`
- `0x180007b9c`
- `0x180007e10`
- `0x180009384`
- `0x180010ee0`
- `0x1800110fc`
- `0x180011314`
- `0x180015150`
- `0x180023c90`
- `0x180062ab8`
- `0x1800d1cc4`
- `0x1800d1fe4`
- `0x1800d25e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800d1f1c`
- `KERNEL32!SetLastError` at `0x1800d1f1c`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1f14`
- `ntdll!RtlNtStatusToDosError` at `0x1800d1f14`
- `ntdll!RtlInitUnicodeString` at `0x1800d1df0`
- `ntdll!RtlInitUnicodeString` at `0x1800d1df0`
- `ntdll!NtCreateFile` at `0x1800d1eeb`
- `ntdll!NtCreateFile` at `0x1800d1eeb`

## string_xrefs

- `0x1800d1d4f`: `CEcsConcurrencyBlobReader::OpenFileHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CEcsConcurrencyBlobReader::OpenFileHandle(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  _BYTE *v7; // rax
  char v8; // cl
  __int64 v9; // rax
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  unsigned int v12; // edx
  unsigned int v13; // r9d
  ULONG CreateOptions; // edi
  signed int v15; // eax
  int i; // esi
  NTSTATUS v17; // eax
  NTSTATUS v18; // ebx
  ULONG v19; // eax
  unsigned int AllocationSize; // [rsp+20h] [rbp-E0h]
  __int64 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  void *v22; // [rsp+68h] [rbp-98h] BYREF
  int LastFailureAsHRESULT; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+74h] [rbp-8Ch]
  char v25; // [rsp+78h] [rbp-88h]
  const char *v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  void *FileHandle; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v34[32]; // [rsp+110h] [rbp+10h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[68] & 2) == 0 || v7[65] < 6u )
    goto LABEL_8;
  v8 = 1;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v24 = 264;
  v25 = v8;
  v26 = "CEcsConcurrencyBlobReader::OpenFileHandle";
  v27 = 0;
  v29 = 0;
  std::wstring::wstring(v33);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v22 = (void *)-1LL;
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v10 = CEcsPath::DosPathNameToRelativeNtPathName(v34, v9);
  std::wstring::operator=(v33, v10);
  std::wstring::~wstring(v34);
  memcmp_0(a2, &c_NullFileId, 0x10u);
  v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
  if ( v12 )
  {
    v22 = (void *)-1LL;
    v15 = CEcsConcurrencyBlobReader::OpenPath(&v22, v12, v11, v13, AllocationSize);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    LastFailureAsHRESULT = v15;
    if ( v15 < 0 )
    {
      HIWORD(v24) = 292;
      LODWORD(pExceptionObject) = v15;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v24) = 292;
    EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v29, &v22);
    DestinationString.Buffer = (PWSTR)a2;
    *(_DWORD *)&DestinationString.Length = 1048592;
    CreateOptions = 90116;
  }
  else
  {
    v22 = 0;
    RtlInitUnicodeString(&DestinationString, v11);
    CreateOptions = 81924;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v22;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = (void *)-1LL;
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
      goto LABEL_28;
    v17 = NtCreateFile(&FileHandle, 0x100081u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 1u, CreateOptions, 0, 0);
    v18 = v17;
    if ( v17 != -1073739511 )
      break;
    CreateOptions &= ~0x10000u;
  }
  if ( v17 == -1073741811 )
  {
    v18 = -1073741766;
LABEL_23:
    v19 = RtlNtStatusToDosError(v18);
    SetLastError(v19);
    if ( v18 != -1073741757 && v18 != -1073741598 && v18 != -1073739511 )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v24) = 359;
      LODWORD(pExceptionObject) = LastFailureAsHRESULT;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = -2134376424;
    LODWORD(pExceptionObject) = -2134376424;
    throw (long *)&pExceptionObject;
  }
  if ( v17 < 0 )
    goto LABEL_23;
LABEL_28:
  EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(a4, &FileHandle);
  std::wstring::~wstring(v33);
  pExceptionObject = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&v29, &pExceptionObject);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x1800d1cc4  push    rbp
0x1800d1cc6  push    rbx
0x1800d1cc7  push    rsi
0x1800d1cc8  push    rdi
0x1800d1cc9  push    r14
0x1800d1ccb  lea     rbp, [rsp-40h]
0x1800d1cd0  sub     rsp, 140h
0x1800d1cd7  mov     rax, cs:__security_cookie
0x1800d1cde  xor     rax, rsp
0x1800d1ce1  mov     [rbp+60h+var_30], rax
0x1800d1ce5  mov     r14, r9
0x1800d1ce8  mov     rbx, rdx
0x1800d1ceb  mov     rdi, rcx
0x1800d1cee  lea     rcx, WPP_GLOBAL_Control
0x1800d1cf5  mov     rax, cs:WPP_GLOBAL_Control
0x1800d1cfc  cmp     rax, rcx
0x1800d1cff  jz      short loc_1800D1D29
0x1800d1d01  test    byte ptr [rax+44h], 2
0x1800d1d05  jz      short loc_1800D1D39
0x1800d1d07  cmp     byte ptr [rax+41h], 6
0x1800d1d0b  jb      short loc_1800D1D29
0x1800d1d0d  mov     edx, 12h
0x1800d1d12  lea     r8, WPP_736b8f8bb467359ad513b1042edd4d13_Traceguids
0x1800d1d19  mov     rcx, [rax+38h]
0x1800d1d1d  call    WPP_SF_
0x1800d1d22  mov     rax, cs:WPP_GLOBAL_Control
0x1800d1d29  test    byte ptr [rax+44h], 2
0x1800d1d2d  jz      short loc_1800D1D39
0x1800d1d2f  cmp     byte ptr [rax+41h], 6
0x1800d1d33  jb      short loc_1800D1D39
0x1800d1d35  mov     cl, 1
0x1800d1d37  jmp     short loc_1800D1D3B
0x1800d1d39  xor     cl, cl
0x1800d1d3b  mov     [rsp+160h+var_F0], 0
0x1800d1d43  mov     [rsp+160h+var_EC], 108h
0x1800d1d4b  mov     [rsp+160h+var_E8], cl
0x1800d1d4f  lea     rax, aCecsconcurrenc_1; "CEcsConcurrencyBlobReader::OpenFileHand"...
0x1800d1d56  mov     [rbp+60h+var_E0], rax
0x1800d1d5a  mov     [rbp+60h+var_D8], 0
0x1800d1d62  mov     [rbp+60h+var_C8], 0
0x1800d1d6a  lea     rcx, [rbp+60h+var_70]
0x1800d1d6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d1d73  nop
0x1800d1d74  xorps   xmm1, xmm1
0x1800d1d77  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm1
0x1800d1d7b  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm1
0x1800d1d7f  movups  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800d1d83  xorps   xmm0, xmm0
0x1800d1d86  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800d1d8a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800d1d8e  mov     [rsp+160h+var_F8], rsi
0x1800d1d93  mov     rcx, rdi
0x1800d1d96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d1d9b  mov     rdx, rax
0x1800d1d9e  lea     rcx, [rbp+60h+var_50]
0x1800d1da2  call    ?DosPathNameToRelativeNtPathName@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; CEcsPath::DosPathNameToRelativeNtPathName(ushort const *)
0x1800d1da7  nop
0x1800d1da8  mov     rdx, rax
0x1800d1dab  lea     rcx, [rbp+60h+var_70]
0x1800d1daf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800d1db4  nop
0x1800d1db5  lea     rcx, [rbp+60h+var_50]
0x1800d1db9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d1dbe  lea     r8d, [rsi+11h]; Size
0x1800d1dc2  lea     rdx, ?c_NullFileId@@3U_FILE_ID_128@@B; Buf2
0x1800d1dc9  mov     rcx, rbx; Buf1
0x1800d1dcc  call    memcmp_0
0x1800d1dd1  mov     edx, eax
0x1800d1dd3  lea     rcx, [rbp+60h+var_70]
0x1800d1dd7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d1ddc  test    edx, edx
0x1800d1dde  jnz     short loc_1800D1DFD
0x1800d1de0  mov     [rsp+160h+var_F8], 0
0x1800d1de9  mov     rdx, rax; SourceString
0x1800d1dec  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1800d1df0  call    cs:__imp_RtlInitUnicodeString
0x1800d1df6  mov     edi, 14004h
0x1800d1dfb  jmp     short loc_1800D1E6A
0x1800d1dfd  mov     [rsp+160h+var_F8], rsi
0x1800d1e02  mov     r8, rax; unsigned __int16 *
0x1800d1e05  lea     rcx, [rsp+160h+var_F8]; FileHandle
0x1800d1e0a  call    ?OpenPath@CEcsConcurrencyBlobReader@@CAKPEAPEAXKPEBGKK@Z; CEcsConcurrencyBlobReader::OpenPath(void * *,ulong,ushort const *,ulong,ulong)
0x1800d1e0f  test    eax, eax
0x1800d1e11  jle     short loc_1800D1E1B
0x1800d1e13  movzx   eax, ax
0x1800d1e16  or      eax, 80070000h
0x1800d1e1b  mov     [rsp+160h+var_F0], eax
0x1800d1e1f  mov     [rsp+160h+var_F0], eax
0x1800d1e23  mov     ecx, 124h
0x1800d1e28  test    eax, eax
0x1800d1e2a  jns     short loc_1800D1E47
0x1800d1e2c  mov     word ptr [rsp+160h+var_EC+2], cx
0x1800d1e31  mov     dword ptr [rsp+160h+pExceptionObject], eax
0x1800d1e35  lea     rdx, _TI1J; pThrowInfo
0x1800d1e3c  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800d1e41  call    _CxxThrowException_0
0x1800d1e47  mov     word ptr [rsp+160h+var_EC], cx
0x1800d1e4c  lea     rdx, [rsp+160h+var_F8]
0x1800d1e51  lea     rcx, [rbp+60h+var_C8]
0x1800d1e55  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x1800d1e5a  mov     [rbp+60h+DestinationString.Buffer], rbx
0x1800d1e5e  mov     dword ptr [rbp+60h+DestinationString.Length], 100010h
0x1800d1e65  mov     edi, 16004h
0x1800d1e6a  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1800d1e71  mov     rax, [rsp+160h+var_F8]
0x1800d1e76  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x1800d1e7a  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d1e81  lea     rax, [rbp+60h+DestinationString]
0x1800d1e85  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1800d1e89  xorps   xmm0, xmm0
0x1800d1e8c  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d1e91  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x1800d1e95  mov     [rbp+60h+FileHandle], rsi
0x1800d1e99  xor     esi, esi
0x1800d1e9b  cmp     esi, 2
0x1800d1e9e  jge     loc_1800D1F8A
0x1800d1ea4  mov     [rsp+160h+EaLength], 0; EaLength
0x1800d1eac  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x1800d1eb5  mov     [rsp+160h+CreateOptions], edi; CreateOptions
0x1800d1eb9  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x1800d1ec1  mov     [rsp+160h+ShareAccess], 0; ShareAccess
0x1800d1ec9  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x1800d1ed1  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x1800d1eda  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x1800d1ede  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1800d1ee2  mov     edx, 100081h; DesiredAccess
0x1800d1ee7  lea     rcx, [rbp+60h+FileHandle]; FileHandle
0x1800d1eeb  call    cs:__imp_NtCreateFile
0x1800d1ef1  mov     ebx, eax
0x1800d1ef3  cmp     eax, 0C0000909h
0x1800d1ef8  jnz     short loc_1800D1F02
0x1800d1efa  btr     edi, 10h
0x1800d1efe  inc     esi
0x1800d1f00  jmp     short loc_1800D1E9B
0x1800d1f02  cmp     eax, 0C000000Dh
0x1800d1f07  jnz     short loc_1800D1F0E
0x1800d1f09  lea     ebx, [rax+2Dh]
0x1800d1f0c  jmp     short loc_1800D1F12
0x1800d1f0e  test    eax, eax
0x1800d1f10  jns     short loc_1800D1F8A
0x1800d1f12  mov     ecx, ebx; Status
0x1800d1f14  call    cs:__imp_RtlNtStatusToDosError
0x1800d1f1a  mov     ecx, eax; dwErrCode
0x1800d1f1c  call    cs:__imp_SetLastError
0x1800d1f22  cmp     ebx, 0C0000043h
0x1800d1f28  jz      short loc_1800D1F6B
0x1800d1f2a  cmp     ebx, 0C00000E2h
0x1800d1f30  jz      short loc_1800D1F6B
0x1800d1f32  cmp     ebx, 0C0000909h
0x1800d1f38  jz      short loc_1800D1F6B
0x1800d1f3a  mov     eax, [rsp+160h+var_F0]
0x1800d1f3e  mov     [rsp+160h+var_F0], eax
0x1800d1f42  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800d1f47  mov     [rsp+160h+var_F0], eax
0x1800d1f4b  mov     ecx, 167h
0x1800d1f50  mov     word ptr [rsp+160h+var_EC+2], cx
0x1800d1f55  mov     dword ptr [rsp+160h+pExceptionObject], eax
0x1800d1f59  lea     rdx, _TI1J; pThrowInfo
0x1800d1f60  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800d1f65  call    _CxxThrowException_0
0x1800d1f6b  mov     eax, 80C80018h
0x1800d1f70  mov     [rsp+160h+var_F0], eax
0x1800d1f74  mov     dword ptr [rsp+160h+pExceptionObject], eax
0x1800d1f78  lea     rdx, _TI1J; pThrowInfo
0x1800d1f7f  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800d1f84  call    _CxxThrowException_0
0x1800d1f8a  lea     rdx, [rbp+60h+FileHandle]
0x1800d1f8e  mov     rcx, r14
0x1800d1f91  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,-1>::reset(void * const &)
0x1800d1f96  nop
0x1800d1f97  lea     rcx, [rbp+60h+var_70]
0x1800d1f9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800d1fa0  nop
0x1800d1fa1  mov     [rsp+160h+pExceptionObject], 0
0x1800d1faa  lea     rdx, [rsp+160h+pExceptionObject]
0x1800d1faf  lea     rcx, [rbp+60h+var_C8]
0x1800d1fb3  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x1800d1fb8  nop
0x1800d1fb9  lea     rcx, [rsp+160h+var_F0]; this
0x1800d1fbe  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800d1fc3  mov     rcx, [rbp+60h+var_30]
0x1800d1fc7  xor     rcx, rsp; StackCookie
0x1800d1fca  call    __security_check_cookie
0x1800d1fcf  add     rsp, 140h
0x1800d1fd6  pop     r14
0x1800d1fd8  pop     rdi
0x1800d1fd9  pop     rsi
0x1800d1fda  pop     rbx
0x1800d1fdb  pop     rbp
0x1800d1fdc  retn
```
