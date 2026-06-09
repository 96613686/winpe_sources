# UMReflectorRegister

- ea: `0x180029134`
- end: `0x18002930a`
- name: `UMReflectorRegister`
- size: `470`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025f10`

## callees

- `0x18000b6b4`
- `0x18000b89c`
- `0x180028eb4`
- `0x180029134`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180029263`
- `ntdll!NtOpenFile` at `0x180029263`
- `ntdll!RtlNtStatusToDosError` at `0x180029271`
- `ntdll!RtlNtStatusToDosError` at `0x180029271`
- `ntdll!RtlInitUnicodeString` at `0x18002920e`
- `ntdll!RtlInitUnicodeString` at `0x18002920e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002929d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002929d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800292da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800292da`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800291af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800291af`
- `KERNEL32!LocalAlloc` at `0x180029186`
- `KERNEL32!LocalAlloc` at `0x180029186`
- `KERNEL32!lstrlenW` at `0x180029171`
- `KERNEL32!lstrlenW` at `0x180029171`

## pseudocode

```c
__int64 UMReflectorRegister()
{
  unsigned int v0; // esi
  char *v1; // rax
  _DWORD *v2; // rdi
  ULONG v3; // esi
  NTSTATUS v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-38h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v0 = lstrlenW(L"\\Device\\WebDavRedirector") + 1;
  v1 = (char *)LocalAlloc(0x40u, 2 * v0 + 136);
  v2 = v1;
  DavReflectorHandle = v1;
  if ( !v1 )
  {
    v3 = 8;
LABEL_6:
    if ( v2 )
    {
      v2[16] = 1;
      EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 4));
      DereferenceReflectorBlock(v2);
    }
    DavReflectorHandle = 0;
    return v3;
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
  *((_QWORD *)v2 + 10) = v2 + 18;
  *((_QWORD *)v2 + 9) = v2 + 18;
  *((_QWORD *)v2 + 12) = v2 + 22;
  *((_QWORD *)v2 + 11) = v2 + 22;
  *((_QWORD *)v2 + 14) = v2 + 26;
  *((_QWORD *)v2 + 13) = v2 + 26;
  *v2 = 1;
  v2[16] = 0;
  *((_QWORD *)v2 + 1) = -1;
  *((_QWORD *)v2 + 7) = v2 + 32;
  StringCchCopyW((STRSAFE_LPWSTR)v2 + 64, v0, L"\\Device\\WebDavRedirector");
  RtlInitUnicodeString(&DestinationString, *((PCWSTR *)v2 + 7));
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile((PHANDLE)v2 + 1, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  v3 = v4;
  if ( v4 )
    v3 = RtlNtStatusToDosError(v4);
  if ( v3 )
    goto LABEL_6;
  return v3;
}

```

## disassembly

```asm
0x180029134  mov     rax, rsp
0x180029137  mov     [rax+8], rbx
0x18002913b  mov     [rax+10h], rsi
0x18002913f  mov     [rax+18h], r8
0x180029143  push    rdi
0x180029144  sub     rsp, 80h
0x18002914b  xorps   xmm0, xmm0
0x18002914e  movups  xmmword ptr [rax-58h], xmm0
0x180029152  xorps   xmm1, xmm1
0x180029155  movups  xmmword ptr [rax-48h], xmm1
0x180029159  xor     eax, eax
0x18002915b  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x180029160  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x180029165  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x18002916a  lea     rcx, aDeviceWebdavre; "\\Device\\WebDavRedirector"
0x180029171  call    cs:__imp_lstrlenW
0x180029177  lea     esi, [rax+1]
0x18002917a  lea     edx, ds:88h[rsi*2]; uBytes
0x180029181  mov     ecx, 40h ; '@'; uFlags
0x180029186  call    cs:__imp_LocalAlloc
0x18002918c  mov     rdi, rax
0x18002918f  mov     [rsp+88h+arg_10], rax
0x180029197  mov     cs:DavReflectorHandle, rax
0x18002919e  test    rax, rax
0x1800291a1  jnz     short loc_1800291AB
0x1800291a3  lea     esi, [rax+8]
0x1800291a6  jmp     loc_1800292CA
0x1800291ab  lea     rcx, [rax+10h]; lpCriticalSection
0x1800291af  call    cs:__imp_InitializeCriticalSection
0x1800291b5  nop
0x1800291b6  lea     rax, [rdi+48h]
0x1800291ba  mov     [rax+8], rax
0x1800291be  mov     [rax], rax
0x1800291c1  lea     rax, [rdi+58h]
0x1800291c5  mov     [rax+8], rax
0x1800291c9  mov     [rax], rax
0x1800291cc  lea     rax, [rdi+68h]
0x1800291d0  mov     [rax+8], rax
0x1800291d4  mov     [rax], rax
0x1800291d7  mov     dword ptr [rdi], 1
0x1800291dd  mov     dword ptr [rdi+40h], 0
0x1800291e4  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800291ec  lea     rcx, [rdi+80h]; pszDest
0x1800291f3  mov     [rdi+38h], rcx
0x1800291f7  mov     edx, esi; cchDest
0x1800291f9  lea     r8, aDeviceWebdavre; "\\Device\\WebDavRedirector"
0x180029200  call    StringCchCopyW
0x180029205  mov     rdx, [rdi+38h]; SourceString
0x180029209  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18002920e  call    cs:__imp_RtlInitUnicodeString
0x180029214  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x18002921c  mov     [rsp+88h+ObjectAttributes.RootDirectory], 0
0x180029225  mov     [rsp+88h+ObjectAttributes.Attributes], 40h ; '@'
0x18002922d  lea     rax, [rsp+88h+DestinationString]
0x180029232  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x180029237  xorps   xmm0, xmm0
0x18002923a  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x180029240  mov     [rsp+88h+OpenOptions], 20h ; ' '; OpenOptions
0x180029248  mov     [rsp+88h+ShareAccess], 7; ShareAccess
0x180029250  lea     r9, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x180029255  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x18002925a  mov     edx, 100000h; DesiredAccess
0x18002925f  lea     rcx, [rdi+8]; FileHandle
0x180029263  call    cs:__imp_NtOpenFile
0x180029269  mov     esi, eax
0x18002926b  test    eax, eax
0x18002926d  jz      short loc_1800292C6
0x18002926f  mov     ecx, eax; Status
0x180029271  call    cs:__imp_RtlNtStatusToDosError
0x180029277  mov     esi, eax
0x180029279  jmp     short loc_1800292C6
0x18002927b  mov     esi, eax
0x18002927d  lea     rax, WPP_GLOBAL_Control
0x180029284  mov     rbx, cs:WPP_GLOBAL_Control
0x18002928b  cmp     rbx, rax
0x18002928e  jz      short loc_1800292BE
0x180029290  test    dword ptr [rbx+1Ch], 1000h
0x180029297  jz      short loc_1800292BE
0x180029299  mov     rbx, [rbx+10h]
0x18002929d  call    cs:__imp_GetCurrentThreadId
0x1800292a3  mov     r9d, eax
0x1800292a6  mov     edx, 0Ah
0x1800292ab  mov     [rsp+88h+ShareAccess], esi
0x1800292af  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x1800292b6  mov     rcx, rbx
0x1800292b9  call    WPP_SF_Dd
0x1800292be  mov     rdi, [rsp+88h+arg_10]
0x1800292c6  test    esi, esi
0x1800292c8  jz      short loc_1800292F3
0x1800292ca  test    rdi, rdi
0x1800292cd  jz      short loc_1800292E8
0x1800292cf  mov     dword ptr [rdi+40h], 1
0x1800292d6  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800292da  call    cs:__imp_EnterCriticalSection
0x1800292e0  mov     rcx, rdi; hMem
0x1800292e3  call    DereferenceReflectorBlock
0x1800292e8  mov     cs:DavReflectorHandle, 0
0x1800292f3  mov     eax, esi
0x1800292f5  lea     r11, [rsp+88h+var_8]
0x1800292fd  mov     rbx, [r11+10h]
0x180029301  mov     rsi, [r11+18h]
0x180029305  mov     rsp, r11
0x180029308  pop     rdi
0x180029309  retn
```
