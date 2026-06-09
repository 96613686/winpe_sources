# LoadNaturalInputHandler(void)

- ea: `0x18004eaa0`
- end: `0x18004ed3c`
- name: `?LoadNaturalInputHandler@@YAP6A_JPEAUHWND__@@I_K_J@ZXZ`
- size: `668`
- prototype: `__int64 (*(void))(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e910`
- `0x18004ea60`

## callees

- `0x18004eaa0`
- `0x18004ed44`
- `0x180073718`
- `0x180074ef0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18004ebab`
- `ntdll!NtQueryValueKey` at `0x18004ebab`
- `ntdll!NtClose` at `0x18004ebc4`
- `ntdll!NtClose` at `0x18004ebc4`
- `ntdll!NtOpenKey` at `0x18004eb3c`
- `ntdll!NtOpenKey` at `0x18004eb3c`
- `ntdll!RtlInitUnicodeString` at `0x18004eafc`
- `ntdll!RtlInitUnicodeString` at `0x18004eb58`
- `ntdll!RtlInitUnicodeString` at `0x18004eafc`
- `ntdll!RtlInitUnicodeString` at `0x18004eb58`
- `ntdll!RtlFreeHeap` at `0x18004ebef`
- `ntdll!RtlFreeHeap` at `0x18004ecba`
- `ntdll!RtlFreeHeap` at `0x18004ecf5`
- `ntdll!RtlFreeHeap` at `0x18004ebef`
- `ntdll!RtlFreeHeap` at `0x18004ecba`
- `ntdll!RtlFreeHeap` at `0x18004ecf5`
- `ntdll!RtlAllocateHeap` at `0x18004eb74`
- `ntdll!RtlAllocateHeap` at `0x18004ec43`
- `ntdll!RtlAllocateHeap` at `0x18004eb74`
- `ntdll!RtlAllocateHeap` at `0x18004ec43`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ed0d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ed0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004eca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004eca0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004ec88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004ec88`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ebd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ec56`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ebd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004ec56`

## string_xrefs

- `0x18004eaf1`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Windows`

## pseudocode

```c
__int64 (*LoadNaturalInputHandler(void))(HWND, unsigned int, unsigned __int64, __int64)
{
  FARPROC ProcAddress; // r14
  unsigned __int16 *Heap; // rdi
  NTSTATUS v2; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v4; // rbx
  UINT v6; // r15d
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  HMODULE Library; // rax
  HMODULE v10; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  SIZE_T Size; // [rsp+A0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+38h] BYREF

  ProcAddress = 0;
  Heap = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_98f54186fc203383a3f513efbad818bc_Traceguids);
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(Size) = 260;
  v2 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"NaturalInputHandler");
    while ( 1 )
    {
      if ( Heap )
        RtlFreeHeap(pUserHeap, 0, Heap);
      Heap = (unsigned __int16 *)RtlAllocateHeap(pUserHeap, 8u, (unsigned int)Size);
      if ( !Heap )
        break;
      if ( v2 >= 0 )
        v2 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, Heap, Size, (PULONG)&Size);
      if ( v2 != -2147483643 )
        goto LABEL_11;
    }
    v2 = -1073741801;
  }
LABEL_11:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v2 >= 0 )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v4 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      v6 = SystemDirectoryW + (*((_DWORD *)Heap + 2) >> 1) + 1;
      v7 = (WCHAR *)RtlAllocateHeap(pUserHeap, 8u, 2LL * v6);
      v8 = v7;
      if ( v7 )
      {
        if ( (unsigned int)v4 > GetSystemDirectoryW(v7, v4) )
        {
          v8[(unsigned int)(v4 - 1)] = 92;
          if ( (int)StringCchCopyW(&v8[v4], v6 - (unsigned int)v4, Heap + 6) >= 0 )
          {
            Library = LoadLibraryExW(v8, 0, 0);
            v10 = Library;
            if ( Library )
            {
              ProcAddress = GetProcAddress(Library, "DefaultInputHandler");
              if ( !ProcAddress )
                FreeLibrary(v10);
            }
          }
        }
        RtlFreeHeap(pUserHeap, 0, v8);
      }
    }
  }
  if ( Heap )
    RtlFreeHeap(pUserHeap, 0, Heap);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_98f54186fc203383a3f513efbad818bc_Traceguids, ProcAddress);
  }
  return (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))ProcAddress;
}

```

## disassembly

```asm
0x18004eaa0  mov     [rsp-28h+arg_10], rbx
0x18004eaa5  mov     [rsp-28h+arg_18], rsi
0x18004eaaa  push    rbp
0x18004eaab  push    rdi
0x18004eaac  push    r13
0x18004eaae  push    r14
0x18004eab0  push    r15
0x18004eab2  mov     rbp, rsp
0x18004eab5  sub     rsp, 70h
0x18004eab9  xorps   xmm1, xmm1
0x18004eabc  xor     r14d, r14d
0x18004eabf  xorps   xmm0, xmm0
0x18004eac2  xor     edi, edi
0x18004eac4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004eac8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18004eacc  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x18004ead0  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x18004ead4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eadb  lea     r13, WPP_GLOBAL_Control
0x18004eae2  cmp     rcx, r13
0x18004eae5  jz      short loc_18004EAF1
0x18004eae7  test    byte ptr [rcx+1Ch], 4
0x18004eaeb  jnz     loc_18004ECC5
0x18004eaf1  lea     rdx, ?szWindowsKey@@3QBGB; "\\Registry\\Machine\\Software\\Microsof"...
0x18004eaf8  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004eafc  call    cs:__imp_RtlInitUnicodeString
0x18004eb02  lea     rax, [rbp+DestinationString]
0x18004eb06  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004eb0d  xorps   xmm0, xmm0
0x18004eb10  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004eb14  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004eb18  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x18004eb1c  mov     edx, 20019h; DesiredAccess
0x18004eb21  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004eb28  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004eb2c  mov     [rbp+KeyHandle], rdi
0x18004eb30  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004eb35  mov     dword ptr [rbp+Size], 104h
0x18004eb3c  call    cs:__imp_NtOpenKey
0x18004eb42  mov     ebx, eax
0x18004eb44  mov     esi, 8
0x18004eb49  test    eax, eax
0x18004eb4b  js      short loc_18004EBBB
0x18004eb4d  lea     rdx, aNaturalinputha; "NaturalInputHandler"
0x18004eb54  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004eb58  call    cs:__imp_RtlInitUnicodeString
0x18004eb5e  test    rdi, rdi
0x18004eb61  jnz     loc_18004ECE9
0x18004eb67  mov     r8d, dword ptr [rbp+Size]; Size
0x18004eb6b  mov     edx, esi; Flags
0x18004eb6d  mov     rcx, cs:pUserHeap; HeapHandle
0x18004eb74  call    cs:__imp_RtlAllocateHeap
0x18004eb7a  mov     rdi, rax
0x18004eb7d  test    rax, rax
0x18004eb80  jz      loc_18004ED00
0x18004eb86  test    ebx, ebx
0x18004eb88  js      short loc_18004EBB3
0x18004eb8a  mov     eax, dword ptr [rbp+Size]
0x18004eb8d  lea     rcx, [rbp+Size]
0x18004eb91  mov     [rsp+70h+ResultLength], rcx; ResultLength
0x18004eb96  lea     rdx, [rbp+DestinationString]; ValueName
0x18004eb9a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004eb9e  mov     r9, rdi; KeyValueInformation
0x18004eba1  mov     r8d, 2; KeyValueInformationClass
0x18004eba7  mov     [rsp+70h+Length], eax; Length
0x18004ebab  call    cs:__imp_NtQueryValueKey
0x18004ebb1  mov     ebx, eax
0x18004ebb3  cmp     ebx, 80000005h
0x18004ebb9  jz      short loc_18004EB5E
0x18004ebbb  mov     rcx, [rbp+KeyHandle]; Handle
0x18004ebbf  test    rcx, rcx
0x18004ebc2  jz      short loc_18004EBCA
0x18004ebc4  call    cs:__imp_NtClose
0x18004ebca  test    ebx, ebx
0x18004ebcc  js      short loc_18004EBDE
0x18004ebce  xor     edx, edx; uSize
0x18004ebd0  xor     ecx, ecx; lpBuffer
0x18004ebd2  call    cs:__imp_GetSystemDirectoryW
0x18004ebd8  mov     ebx, eax
0x18004ebda  test    eax, eax
0x18004ebdc  jnz     short loc_18004EC27
0x18004ebde  test    rdi, rdi
0x18004ebe1  jz      short loc_18004EBF5
0x18004ebe3  mov     rcx, cs:pUserHeap; HeapHandle
0x18004ebea  mov     r8, rdi; P
0x18004ebed  xor     edx, edx; Flags
0x18004ebef  call    cs:__imp_RtlFreeHeap
0x18004ebf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebfc  cmp     rcx, r13
0x18004ebff  jz      short loc_18004EC0B
0x18004ec01  test    byte ptr [rcx+1Ch], 4
0x18004ec05  jnz     loc_18004ED15
0x18004ec0b  lea     r11, [rsp+70h+var_s0]
0x18004ec10  mov     rax, r14
0x18004ec13  mov     rbx, [r11+40h]
0x18004ec17  mov     rsi, [r11+48h]
0x18004ec1b  mov     rsp, r11
0x18004ec1e  pop     r15
0x18004ec20  pop     r14
0x18004ec22  pop     r13
0x18004ec24  pop     rdi
0x18004ec25  pop     rbp
0x18004ec26  retn
0x18004ec27  mov     r15d, [rdi+8]
0x18004ec2b  mov     edx, esi; Flags
0x18004ec2d  mov     rcx, cs:pUserHeap; HeapHandle
0x18004ec34  shr     r15d, 1
0x18004ec37  inc     r15d
0x18004ec3a  add     r15d, ebx
0x18004ec3d  mov     r8d, r15d
0x18004ec40  add     r8, r8; Size
0x18004ec43  call    cs:__imp_RtlAllocateHeap
0x18004ec49  mov     rsi, rax
0x18004ec4c  test    rax, rax
0x18004ec4f  jz      short loc_18004EBDE
0x18004ec51  mov     edx, ebx; uSize
0x18004ec53  mov     rcx, rax; lpBuffer
0x18004ec56  call    cs:__imp_GetSystemDirectoryW
0x18004ec5c  cmp     ebx, eax
0x18004ec5e  jbe     short loc_18004ECAE
0x18004ec60  lea     eax, [rbx-1]
0x18004ec63  sub     r15d, ebx
0x18004ec66  mov     edx, r15d; unsigned __int64
0x18004ec69  lea     r8, [rdi+0Ch]; unsigned __int16 *
0x18004ec6d  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18004ec71  mov     word ptr [rsi+rax*2], 5Ch ; '\'
0x18004ec77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ec7c  test    eax, eax
0x18004ec7e  js      short loc_18004ECAE
0x18004ec80  xor     r8d, r8d; dwFlags
0x18004ec83  xor     edx, edx; hFile
0x18004ec85  mov     rcx, rsi; lpLibFileName
0x18004ec88  call    cs:__imp_LoadLibraryExW
0x18004ec8e  mov     rbx, rax
0x18004ec91  test    rax, rax
0x18004ec94  jz      short loc_18004ECAE
0x18004ec96  lea     rdx, aDefaultinputha; "DefaultInputHandler"
0x18004ec9d  mov     rcx, rax; hModule
0x18004eca0  call    cs:__imp_GetProcAddress
0x18004eca6  mov     r14, rax
0x18004eca9  test    rax, rax
0x18004ecac  jz      short loc_18004ED0A
0x18004ecae  mov     rcx, cs:pUserHeap; HeapHandle
0x18004ecb5  mov     r8, rsi; P
0x18004ecb8  xor     edx, edx; Flags
0x18004ecba  call    cs:__imp_RtlFreeHeap
0x18004ecc0  jmp     loc_18004EBDE
0x18004ecc5  cmp     byte ptr [rcx+19h], 4
0x18004ecc9  jb      loc_18004EAF1
0x18004eccf  mov     rcx, [rcx+10h]
0x18004ecd3  lea     r8, WPP_98f54186fc203383a3f513efbad818bc_Traceguids
0x18004ecda  mov     edx, 0Eh
0x18004ecdf  call    WPP_SF_
0x18004ece4  jmp     loc_18004EAF1
0x18004ece9  mov     rcx, cs:pUserHeap; HeapHandle
0x18004ecf0  mov     r8, rdi; P
0x18004ecf3  xor     edx, edx; Flags
0x18004ecf5  call    cs:__imp_RtlFreeHeap
0x18004ecfb  jmp     loc_18004EB67
0x18004ed00  mov     ebx, 0C0000017h
0x18004ed05  jmp     loc_18004EBBB
0x18004ed0a  mov     rcx, rbx; hLibModule
0x18004ed0d  call    cs:__imp_FreeLibrary
0x18004ed13  jmp     short loc_18004ECAE
0x18004ed15  cmp     byte ptr [rcx+19h], 4
0x18004ed19  jb      loc_18004EC0B
0x18004ed1f  mov     rcx, [rcx+10h]
0x18004ed23  lea     r8, WPP_98f54186fc203383a3f513efbad818bc_Traceguids
0x18004ed2a  mov     edx, 0Fh
0x18004ed2f  mov     r9, r14
0x18004ed32  call    WPP_SF_q
0x18004ed37  jmp     loc_18004EC0B
```
