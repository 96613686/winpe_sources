# ChangeDispSettingsNotificationW(_UNICODE_STRING *,_devicemodeW *,ulong,long)

- ea: `0x1800502d8`
- end: `0x180050584`
- name: `?ChangeDispSettingsNotificationW@@YAXPEAU_UNICODE_STRING@@PEAU_devicemodeW@@KJ@Z`
- size: `684`
- prototype: `void __fastcall(PCUNICODE_STRING String2, struct _devicemodeW *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180050260`

## callees

- `0x1800502d8`
- `0x180050590`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800503c4`
- `ntdll!RtlCompareUnicodeString` at `0x1800503c4`
- `ntdll!RtlInitUnicodeString` at `0x1800503b3`
- `ntdll!RtlInitUnicodeString` at `0x1800503b3`
- `ntdll!RtlFreeHeap` at `0x18005046c`
- `ntdll!RtlFreeHeap` at `0x1800504b3`
- `ntdll!RtlFreeHeap` at `0x1800504df`
- `ntdll!RtlFreeHeap` at `0x18005046c`
- `ntdll!RtlFreeHeap` at `0x1800504b3`
- `ntdll!RtlFreeHeap` at `0x1800504df`
- `ntdll!RtlAllocateHeap` at `0x180050411`
- `ntdll!RtlAllocateHeap` at `0x18005047a`
- `ntdll!RtlAllocateHeap` at `0x180050411`
- `ntdll!RtlAllocateHeap` at `0x18005047a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800504fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800504fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005051a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005051a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800504ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800504ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050456`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050456`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005049f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005049f`

## string_xrefs

- `0x180050433`: `MirrorCompatBinaryExtension`
- `0x18005043f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
void __fastcall ChangeDispSettingsNotificationW(PCUNICODE_STRING String2, struct _devicemodeW *a2, int a3, int a4)
{
  DWORD i; // ebx
  PVOID pvData; // rdi
  LSTATUS ValueW; // eax
  PVOID v11; // rcx
  WCHAR *v12; // r8
  WCHAR *Heap; // rax
  WCHAR *v14; // rsi
  DWORD v15; // ebx
  HMODULE Library; // rbx
  void (*v17)(const unsigned __int16 *); // rax
  FARPROC ProcAddress; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _DISPLAY_DEVICEW DisplayDevice; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(&DisplayDevice.DeviceName[1], 0, 0x342u);
  if ( !String2 )
  {
    if ( !a2 && !a3 && _InterlockedCompareExchange(&dword_1800CA0D0, 0, 1) == 1 && !a4 )
      ((void (*)(void))g_pMirrorLoadedNotifyW)();
    return;
  }
  if ( String2->Buffer )
  {
    DisplayDevice.cb = 840;
    for ( i = 0; ; ++i )
    {
      DisplayDevice.DeviceName[0] = 0;
      if ( !EnumDisplayDevicesW(0, i, &DisplayDevice, 0) )
        return;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, DisplayDevice.DeviceName);
      if ( !RtlCompareUnicodeString(&DestinationString, String2, 1u) )
        break;
    }
    if ( (DisplayDevice.StateFlags & 8) != 0 && (DisplayDevice.StateFlags & 0x40) == 0 )
    {
      if ( !g_hMirrorDrvCompatHelperW )
      {
        pcbData = 520;
        pvData = RtlAllocateHeap(pUserHeap, 0, 0x208u);
        if ( !pvData )
          return;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                   L"MirrorCompatBinaryExtension",
                   0x10000004u,
                   0,
                   pvData,
                   &pcbData);
        v11 = pUserHeap;
        if ( ValueW )
        {
          v12 = (WCHAR *)pvData;
LABEL_18:
          RtlFreeHeap(v11, 0, v12);
          return;
        }
        Heap = (WCHAR *)RtlAllocateHeap(pUserHeap, 0, 0x208u);
        v14 = Heap;
        if ( !Heap )
        {
          v12 = (WCHAR *)pvData;
LABEL_21:
          v11 = pUserHeap;
          goto LABEL_18;
        }
        v15 = ExpandEnvironmentStringsW((LPCWSTR)pvData, Heap, 0x208u);
        RtlFreeHeap(pUserHeap, 0, pvData);
        if ( !v15 )
        {
          v12 = v14;
          goto LABEL_21;
        }
        Library = LoadLibraryExW(v14, 0, 0);
        RtlFreeHeap(pUserHeap, 0, v14);
        if ( !Library )
          return;
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&g_hMirrorDrvCompatHelperW,
               (signed __int64)Library,
               0) )
        {
          FreeLibrary(Library);
        }
      }
      v17 = g_pMirrorLoadedNotifyW;
      if ( !g_pMirrorLoadedNotifyW )
      {
        ProcAddress = GetProcAddress(g_hMirrorDrvCompatHelperW, "MirrorDrvLoadedNotify");
        if ( !ProcAddress )
          return;
        _InterlockedCompareExchange64(
          (volatile signed __int64 *)&g_pMirrorLoadedNotifyW,
          (signed __int64)ProcAddress,
          0);
        v17 = g_pMirrorLoadedNotifyW;
      }
      ((void (__fastcall *)(PWSTR))v17)(String2->Buffer);
      if ( (a3 & 0x10000000) != 0 && !a4 )
        dword_1800CA0D0 = 1;
    }
  }
}

```

## disassembly

```asm
0x1800502d8  mov     [rsp-8+arg_8], rbx
0x1800502dd  mov     [rsp-8+arg_10], rsi
0x1800502e2  push    rbp
0x1800502e3  push    rdi
0x1800502e4  push    r12
0x1800502e6  push    r14
0x1800502e8  push    r15
0x1800502ea  lea     rbp, [rsp-2C0h]
0x1800502f2  sub     rsp, 3C0h
0x1800502f9  mov     rax, cs:__security_cookie
0x180050300  xor     rax, rsp
0x180050303  mov     [rbp+2E0h+var_30], rax
0x18005030a  mov     r12d, r8d
0x18005030d  mov     rbx, rdx
0x180050310  mov     r14, rcx
0x180050313  xor     edx, edx; Val
0x180050315  mov     r8d, 342h; Size
0x18005031b  lea     rcx, [rsp+3E0h+DisplayDevice.DeviceName+2]; void *
0x180050320  mov     r15d, r9d
0x180050323  call    memset_0
0x180050328  test    r14, r14
0x18005032b  jnz     short loc_18005036C
0x18005032d  test    rbx, rbx
0x180050330  jnz     loc_180050559
0x180050336  test    r12d, r12d
0x180050339  jnz     loc_180050559
0x18005033f  xor     ecx, ecx
0x180050341  lea     eax, [rbx+1]
0x180050344  lock cmpxchg cs:dword_1800CA0D0, ecx
0x18005034c  jnz     loc_180050559
0x180050352  test    r15d, r15d
0x180050355  jnz     loc_180050559
0x18005035b  mov     rax, cs:?g_pMirrorLoadedNotifyW@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyW)(ushort const *)
0x180050362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050367  jmp     loc_180050559
0x18005036c  cmp     qword ptr [r14+8], 0
0x180050371  jz      loc_180050559
0x180050377  xor     eax, eax
0x180050379  mov     [rsp+3E0h+DisplayDevice.cb], 348h
0x180050381  xor     ebx, ebx
0x180050383  xor     r9d, r9d; dwFlags
0x180050386  mov     [rsp+3E0h+DisplayDevice.DeviceName], ax
0x18005038b  lea     r8, [rsp+3E0h+DisplayDevice]; lpDisplayDevice
0x180050390  mov     edx, ebx; iDevNum
0x180050392  xor     ecx, ecx; lpDevice
0x180050394  call    EnumDisplayDevicesW
0x180050399  test    eax, eax
0x18005039b  jz      loc_180050559
0x1800503a1  xorps   xmm0, xmm0
0x1800503a4  lea     rdx, [rsp+3E0h+DisplayDevice.DeviceName]; SourceString
0x1800503a9  lea     rcx, [rsp+3E0h+DestinationString]; DestinationString
0x1800503ae  movups  xmmword ptr [rsp+3E0h+DestinationString.Length], xmm0
0x1800503b3  call    cs:__imp_RtlInitUnicodeString
0x1800503b9  mov     r8b, 1; CaseInsensitive
0x1800503bc  lea     rcx, [rsp+3E0h+DestinationString]; String1
0x1800503c1  mov     rdx, r14; String2
0x1800503c4  call    cs:__imp_RtlCompareUnicodeString
0x1800503ca  test    eax, eax
0x1800503cc  jz      short loc_1800503D4
0x1800503ce  inc     ebx
0x1800503d0  xor     eax, eax
0x1800503d2  jmp     short loc_180050383
0x1800503d4  test    byte ptr [rbp+2E0h+DisplayDevice.StateFlags], 8
0x1800503db  jz      loc_180050559
0x1800503e1  test    byte ptr [rbp+2E0h+DisplayDevice.StateFlags], 40h
0x1800503e8  jnz     loc_180050559
0x1800503ee  cmp     cs:?g_hMirrorDrvCompatHelperW@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hMirrorDrvCompatHelperW
0x1800503f6  jnz     loc_180050500
0x1800503fc  mov     rcx, cs:pUserHeap; HeapHandle
0x180050403  mov     ebx, 208h
0x180050408  mov     r8d, ebx; Size
0x18005040b  mov     [rsp+3E0h+var_3A0], ebx
0x18005040f  xor     edx, edx; Flags
0x180050411  call    cs:__imp_RtlAllocateHeap
0x180050417  mov     rdi, rax
0x18005041a  test    rax, rax
0x18005041d  jz      loc_180050559
0x180050423  lea     rax, [rsp+3E0h+var_3A0]
0x180050428  mov     r9d, 10000004h; dwFlags
0x18005042e  mov     [rsp+3E0h+pcbData], rax; pcbData
0x180050433  lea     r8, Value; "MirrorCompatBinaryExtension"
0x18005043a  mov     [rsp+3E0h+pvData], rdi; pvData
0x18005043f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180050446  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005044d  mov     [rsp+3E0h+pdwType], 0; pdwType
0x180050456  call    cs:__imp_RegGetValueW
0x18005045c  mov     rcx, cs:pUserHeap; HeapHandle
0x180050463  xor     edx, edx; Flags
0x180050465  test    eax, eax
0x180050467  jz      short loc_180050477
0x180050469  mov     r8, rdi; P
0x18005046c  call    cs:__imp_RtlFreeHeap
0x180050472  jmp     loc_180050559
0x180050477  mov     r8, rbx; Size
0x18005047a  call    cs:__imp_RtlAllocateHeap
0x180050480  mov     rsi, rax
0x180050483  test    rax, rax
0x180050486  jnz     short loc_180050496
0x180050488  mov     r8, rdi
0x18005048b  mov     rcx, cs:pUserHeap
0x180050492  xor     edx, edx
0x180050494  jmp     short loc_18005046C
0x180050496  mov     r8d, ebx; nSize
0x180050499  mov     rdx, rsi; lpDst
0x18005049c  mov     rcx, rdi; lpSrc
0x18005049f  call    cs:__imp_ExpandEnvironmentStringsW
0x1800504a5  mov     rcx, cs:pUserHeap; HeapHandle
0x1800504ac  mov     r8, rdi; P
0x1800504af  xor     edx, edx; Flags
0x1800504b1  mov     ebx, eax
0x1800504b3  call    cs:__imp_RtlFreeHeap
0x1800504b9  test    ebx, ebx
0x1800504bb  jnz     short loc_1800504C2
0x1800504bd  mov     r8, rsi
0x1800504c0  jmp     short loc_18005048B
0x1800504c2  xor     r8d, r8d; dwFlags
0x1800504c5  xor     edx, edx; hFile
0x1800504c7  mov     rcx, rsi; lpLibFileName
0x1800504ca  call    cs:__imp_LoadLibraryExW
0x1800504d0  mov     rcx, cs:pUserHeap; HeapHandle
0x1800504d7  mov     r8, rsi; P
0x1800504da  xor     edx, edx; Flags
0x1800504dc  mov     rbx, rax
0x1800504df  call    cs:__imp_RtlFreeHeap
0x1800504e5  test    rbx, rbx
0x1800504e8  jz      short loc_180050559
0x1800504ea  xor     eax, eax
0x1800504ec  lock cmpxchg cs:?g_hMirrorDrvCompatHelperW@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hMirrorDrvCompatHelperW
0x1800504f5  jz      short loc_180050500
0x1800504f7  mov     rcx, rbx; hLibModule
0x1800504fa  call    cs:__imp_FreeLibrary
0x180050500  mov     rax, cs:?g_pMirrorLoadedNotifyW@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyW)(ushort const *)
0x180050507  test    rax, rax
0x18005050a  jnz     short loc_18005053A
0x18005050c  mov     rcx, cs:?g_hMirrorDrvCompatHelperW@@3PEAUHINSTANCE__@@EA; hModule
0x180050513  lea     rdx, aMirrordrvloade; "MirrorDrvLoadedNotify"
0x18005051a  call    cs:__imp_GetProcAddress
0x180050520  mov     rcx, rax
0x180050523  test    rax, rax
0x180050526  jz      short loc_180050559
0x180050528  xor     eax, eax
0x18005052a  lock cmpxchg cs:?g_pMirrorLoadedNotifyW@@3P6AXPEBG@ZEA, rcx; void (*g_pMirrorLoadedNotifyW)(ushort const *)
0x180050533  mov     rax, cs:?g_pMirrorLoadedNotifyW@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyW)(ushort const *)
0x18005053a  mov     rcx, [r14+8]
0x18005053e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050543  bt      r12d, 1Ch
0x180050548  jnb     short loc_180050559
0x18005054a  test    r15d, r15d
0x18005054d  jnz     short loc_180050559
0x18005054f  mov     cs:dword_1800CA0D0, 1
0x180050559  mov     rcx, [rbp+2E0h+var_30]
0x180050560  xor     rcx, rsp; StackCookie
0x180050563  call    __security_check_cookie
0x180050568  lea     r11, [rsp+3E0h+var_20]
0x180050570  mov     rbx, [r11+38h]
0x180050574  mov     rsi, [r11+40h]
0x180050578  mov     rsp, r11
0x18005057b  pop     r15
0x18005057d  pop     r14
0x18005057f  pop     r12
0x180050581  pop     rdi
0x180050582  pop     rbp
0x180050583  retn
```
