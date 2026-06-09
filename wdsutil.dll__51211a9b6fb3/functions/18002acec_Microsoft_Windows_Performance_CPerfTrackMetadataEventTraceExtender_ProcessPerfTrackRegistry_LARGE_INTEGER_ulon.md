# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002acec`
- end: `0x18002af50`
- name: `?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `612`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029f10`

## callees

- `0x18000abfc`
- `0x18002a1dc`
- `0x18002a4d8`
- `0x18002acec`
- `0x1800319f0`

## import_xrefs

- `msvcrt!free` at `0x18002ae85`
- `msvcrt!free` at `0x18002ae85`
- `ADVAPI32!RegCloseKey` at `0x18002ad95`
- `ADVAPI32!RegCloseKey` at `0x18002ae62`
- `ADVAPI32!RegCloseKey` at `0x18002ae9a`
- `ADVAPI32!RegCloseKey` at `0x18002af3e`
- `ADVAPI32!RegCloseKey` at `0x18002ad95`
- `ADVAPI32!RegCloseKey` at `0x18002ae62`
- `ADVAPI32!RegCloseKey` at `0x18002ae9a`
- `ADVAPI32!RegCloseKey` at `0x18002af3e`
- `ADVAPI32!RegEnumKeyExW` at `0x18002adea`
- `ADVAPI32!RegEnumKeyExW` at `0x18002adea`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ad65`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ae37`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ad65`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ae37`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4)
{
  DWORD LowPart; // ebx
  int v6; // r12d
  HKEY v7; // rdi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  DWORD v11; // r14d
  LSTATUS v12; // r15d
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+60h] [rbp-A0h]
  HKEY hKey[3]; // [rsp+68h] [rbp-98h] BYREF
  HKEY v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  WCHAR Name[128]; // [rsp+A0h] [rbp-60h] BYREF

  v22 = -2;
  v15 = a4;
  LowPart = a2.LowPart;
  v6 = (int)this;
  v7 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  phkResult = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\PerfTrack\\InteractionClasses",
         0,
         0x20019u,
         &phkResult);
  if ( !v8 )
  {
    v8 = 0;
    v7 = phkResult;
    v19 = phkResult;
  }
  if ( v8 )
  {
    v9 = ATL::AtlHresultFromWin32(v8);
    if ( v7 )
      RegCloseKey(v7);
    return v9;
  }
  else
  {
    Block = 0;
    v17 = 0;
    v11 = 0;
    do
    {
      LODWORD(phkResult) = 128;
      ftLastWriteTime = 0;
      v12 = RegEnumKeyExW(v7, v11, Name, (LPDWORD)&phkResult, 0, 0, 0, &ftLastWriteTime);
      if ( !v12 && (unsigned int)phkResult < 0x80 )
      {
        memset(hKey, 0, sizeof(hKey));
        ftLastWriteTime = 0;
        if ( !RegOpenKeyExW(v7, Name, 0, 0x20019u, (PHKEY)&ftLastWriteTime) )
        {
          hKey[0] = (HKEY)ftLastWriteTime;
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(
            v6,
            LowPart,
            a3,
            v15,
            (ATL::CRegKey *)hKey,
            (__int64)Name,
            (__int64)&Block);
          Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(
            v6,
            LowPart,
            a3,
            v15,
            (__int64)hKey,
            (__int64)Name,
            (__int64)&Block);
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
        }
      }
      ++v11;
    }
    while ( v12 != 259 );
    free(Block);
    if ( v7 )
      RegCloseKey(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18002acec  push    rbp
0x18002acee  push    rbx
0x18002acef  push    rsi
0x18002acf0  push    rdi
0x18002acf1  push    r12
0x18002acf3  push    r13
0x18002acf5  push    r14
0x18002acf7  push    r15
0x18002acf9  lea     rbp, [rsp-0B8h]
0x18002ad01  sub     rsp, 1B8h
0x18002ad08  mov     [rbp+0F0h+var_158], 0FFFFFFFFFFFFFFFEh
0x18002ad10  mov     rax, cs:__security_cookie
0x18002ad17  xor     rax, rsp
0x18002ad1a  mov     [rbp+0F0h+var_50], rax
0x18002ad21  mov     [rsp+1F0h+var_1A0], r9d
0x18002ad26  mov     r13d, r8d
0x18002ad29  mov     rbx, rdx
0x18002ad2c  mov     r12, rcx
0x18002ad2f  xor     esi, esi
0x18002ad31  mov     edi, esi
0x18002ad33  mov     [rbp+0F0h+var_170], rsi
0x18002ad37  mov     [rbp+0F0h+var_168], rsi
0x18002ad3b  mov     [rbp+0F0h+var_160], rsi
0x18002ad3f  mov     [rsp+1F0h+var_1B0], rsi
0x18002ad44  lea     rax, [rsp+1F0h+var_1B0]
0x18002ad49  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18002ad4e  mov     r9d, 20019h; samDesired
0x18002ad54  xor     r8d, r8d; ulOptions
0x18002ad57  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002ad5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ad65  call    cs:__imp_RegOpenKeyExW
0x18002ad6c  nop     dword ptr [rax+rax+00h]
0x18002ad71  test    eax, eax
0x18002ad73  jnz     short loc_18002AD80
0x18002ad75  mov     eax, esi
0x18002ad77  mov     rdi, [rsp+1F0h+var_1B0]
0x18002ad7c  mov     [rbp+0F0h+var_170], rdi
0x18002ad80  test    eax, eax
0x18002ad82  jz      short loc_18002ADA9
0x18002ad84  mov     ecx, eax; unsigned int
0x18002ad86  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002ad8b  mov     ebx, eax
0x18002ad8d  test    rdi, rdi
0x18002ad90  jz      short loc_18002ADA2
0x18002ad92  mov     rcx, rdi; hKey
0x18002ad95  call    cs:__imp_RegCloseKey
0x18002ad9c  nop     dword ptr [rax+rax+00h]
0x18002ada1  nop
0x18002ada2  mov     eax, ebx
0x18002ada4  jmp     loc_18002AEA9
0x18002ada9  mov     [rsp+1F0h+Block], rsi
0x18002adae  mov     [rsp+1F0h+var_190], esi
0x18002adb2  mov     r14d, esi
0x18002adb5  mov     dword ptr [rsp+1F0h+var_1B0], 80h
0x18002adbd  mov     qword ptr [rsp+1F0h+ftLastWriteTime.dwLowDateTime], rsi
0x18002adc2  lea     rax, [rsp+1F0h+ftLastWriteTime]
0x18002adc7  mov     [rsp+1F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002adcc  mov     [rsp+1F0h+lpcchClass], rsi; lpcchClass
0x18002add1  mov     [rsp+1F0h+lpClass], rsi; lpClass
0x18002add6  mov     [rsp+1F0h+phkResult], rsi; lpReserved
0x18002addb  lea     r9, [rsp+1F0h+var_1B0]; lpcchName
0x18002ade0  lea     r8, [rbp+0F0h+Name]; lpName
0x18002ade4  mov     edx, r14d; dwIndex
0x18002ade7  mov     rcx, rdi; hKey
0x18002adea  call    cs:__imp_RegEnumKeyExW
0x18002adf1  nop     dword ptr [rax+rax+00h]
0x18002adf6  mov     r15d, eax
0x18002adf9  test    eax, eax
0x18002adfb  jnz     short loc_18002AE70
0x18002adfd  cmp     dword ptr [rsp+1F0h+var_1B0], 80h
0x18002ae05  jnb     short loc_18002AE70
0x18002ae07  mov     [rsp+1F0h+hKey], rsi
0x18002ae0c  xor     eax, eax
0x18002ae0e  mov     [rsp+1F0h+var_180], rax
0x18002ae13  mov     [rsp+1F0h+var_178], rax
0x18002ae18  mov     qword ptr [rsp+1F0h+ftLastWriteTime.dwLowDateTime], rax
0x18002ae1d  lea     rax, [rsp+1F0h+ftLastWriteTime]
0x18002ae22  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18002ae27  mov     r9d, 20019h; samDesired
0x18002ae2d  xor     r8d, r8d; ulOptions
0x18002ae30  lea     rdx, [rbp+0F0h+Name]; lpSubKey
0x18002ae34  mov     rcx, rdi; hKey
0x18002ae37  call    cs:__imp_RegOpenKeyExW
0x18002ae3e  nop     dword ptr [rax+rax+00h]
0x18002ae43  xor     ecx, ecx
0x18002ae45  test    eax, eax
0x18002ae47  jnz     short loc_18002AE56
0x18002ae49  mov     rsi, qword ptr [rsp+1F0h+ftLastWriteTime.dwLowDateTime]
0x18002ae4e  mov     [rsp+1F0h+hKey], rsi
0x18002ae53  mov     rcx, rsi
0x18002ae56  test    eax, eax
0x18002ae58  jz      short loc_18002AECD
0x18002ae5a  test    rcx, rcx
0x18002ae5d  jz      short loc_18002AE6E
0x18002ae5f  mov     rcx, rsi; hKey
0x18002ae62  call    cs:__imp_RegCloseKey
0x18002ae69  nop     dword ptr [rax+rax+00h]
0x18002ae6e  xor     esi, esi
0x18002ae70  inc     r14d
0x18002ae73  cmp     r15d, 103h
0x18002ae7a  jnz     loc_18002ADB5
0x18002ae80  mov     rcx, [rsp+1F0h+Block]; Block
0x18002ae85  call    cs:__imp_free
0x18002ae8c  nop     dword ptr [rax+rax+00h]
0x18002ae91  nop
0x18002ae92  test    rdi, rdi
0x18002ae95  jz      short loc_18002AEA7
0x18002ae97  mov     rcx, rdi; hKey
0x18002ae9a  call    cs:__imp_RegCloseKey
0x18002aea1  nop     dword ptr [rax+rax+00h]
0x18002aea6  nop
0x18002aea7  xor     eax, eax
0x18002aea9  mov     rcx, [rbp+0F0h+var_50]
0x18002aeb0  xor     rcx, rsp; StackCookie
0x18002aeb3  call    __security_check_cookie
0x18002aeb8  add     rsp, 1B8h
0x18002aebf  pop     r15
0x18002aec1  pop     r14
0x18002aec3  pop     r13
0x18002aec5  pop     r12
0x18002aec7  pop     rdi
0x18002aec8  pop     rsi
0x18002aec9  pop     rbx
0x18002aeca  pop     rbp
0x18002aecb  retn
0x18002aecd  lea     rax, [rsp+1F0h+Block]
0x18002aed2  mov     [rsp+1F0h+lpcchClass], rax; __int64
0x18002aed7  lea     rax, [rbp+0F0h+Name]
0x18002aedb  mov     [rsp+1F0h+lpClass], rax; __int64
0x18002aee0  lea     rax, [rsp+1F0h+hKey]
0x18002aee5  mov     [rsp+1F0h+phkResult], rax; ATL::CRegKey *
0x18002aeea  mov     r9d, [rsp+1F0h+var_1A0]; int
0x18002aeef  mov     r8d, r13d; int
0x18002aef2  mov     rdx, rbx; int
0x18002aef5  mov     rcx, r12; int
0x18002aef8  call    ?ProcessInteractionClassV0@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV0(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002aefd  lea     rax, [rsp+1F0h+Block]
0x18002af02  mov     [rsp+1F0h+lpcchClass], rax
0x18002af07  lea     rax, [rbp+0F0h+Name]
0x18002af0b  mov     [rsp+1F0h+lpClass], rax
0x18002af10  lea     rax, [rsp+1F0h+hKey]
0x18002af15  mov     [rsp+1F0h+phkResult], rax
0x18002af1a  mov     r9d, [rsp+1F0h+var_1A0]
0x18002af1f  mov     r8d, r13d
0x18002af22  mov     rdx, rbx
0x18002af25  mov     rcx, r12
0x18002af28  call    ?ProcessInteractionClassV1@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKAEAVCRegKey@ATL@@PEBGAEAU?$CHeapAllocation@EVCCRTAllocator@ATL@@@234@@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessInteractionClassV1(_LARGE_INTEGER,ulong,ulong,ATL::CRegKey &,ushort const *,Microsoft::Windows::Performance::CHeapAllocation<uchar,ATL::CCRTAllocator> &)
0x18002af2d  nop
0x18002af2e  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18002af33  xor     esi, esi
0x18002af35  test    rcx, rcx
0x18002af38  jz      loc_18002AE70
0x18002af3e  call    cs:__imp_RegCloseKey
0x18002af45  nop     dword ptr [rax+rax+00h]
0x18002af4a  jmp     loc_18002AE70
```
