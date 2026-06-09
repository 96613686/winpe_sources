# ChangeDispSettingsNotificationA(_UNICODE_STRING *,_devicemodeW *,ulong,long)

- ea: `0x18004ffa4`
- end: `0x180050250`
- name: `?ChangeDispSettingsNotificationA@@YAXPEAU_UNICODE_STRING@@PEAU_devicemodeW@@KJ@Z`
- size: `684`
- prototype: `void __fastcall(PCUNICODE_STRING String2, struct _devicemodeW *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004feb0`

## callees

- `0x18004ffa4`
- `0x180050590`
- `0x180096dc5`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180050090`
- `ntdll!RtlCompareUnicodeString` at `0x180050090`
- `ntdll!RtlInitUnicodeString` at `0x18005007f`
- `ntdll!RtlInitUnicodeString` at `0x18005007f`
- `ntdll!RtlFreeHeap` at `0x180050138`
- `ntdll!RtlFreeHeap` at `0x18005017f`
- `ntdll!RtlFreeHeap` at `0x1800501ab`
- `ntdll!RtlFreeHeap` at `0x180050138`
- `ntdll!RtlFreeHeap` at `0x18005017f`
- `ntdll!RtlFreeHeap` at `0x1800501ab`
- `ntdll!RtlAllocateHeap` at `0x1800500dd`
- `ntdll!RtlAllocateHeap` at `0x180050146`
- `ntdll!RtlAllocateHeap` at `0x1800500dd`
- `ntdll!RtlAllocateHeap` at `0x180050146`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800501c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800501c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800501e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800501e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050196`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050196`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050122`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180050122`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005016b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005016b`

## string_xrefs

- `0x1800500ff`: `MirrorCompatBinaryExtension`
- `0x18005010b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
void __fastcall ChangeDispSettingsNotificationA(PCUNICODE_STRING String2, struct _devicemodeW *a2, int a3, int a4)
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
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(&DisplayDevice.DeviceName[1], 0, 0x342u);
  if ( !String2 )
  {
    if ( !a2 && !a3 && _InterlockedCompareExchange(&dword_1800C9F8C, 0, 1) == 1 && !a4 )
      ((void (*)(void))g_pMirrorLoadedNotifyA)();
    return;
  }
  if ( String2->Buffer )
  {
    DisplayDevice.cb = 424;
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
      if ( !g_hMirrorDrvCompatHelperA )
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
               (volatile signed __int64 *)&g_hMirrorDrvCompatHelperA,
               (signed __int64)Library,
               0) )
        {
          FreeLibrary(Library);
        }
      }
      v17 = g_pMirrorLoadedNotifyA;
      if ( !g_pMirrorLoadedNotifyA )
      {
        ProcAddress = GetProcAddress(g_hMirrorDrvCompatHelperA, "MirrorDrvLoadedNotify");
        if ( !ProcAddress )
          return;
        _InterlockedCompareExchange64(
          (volatile signed __int64 *)&g_pMirrorLoadedNotifyA,
          (signed __int64)ProcAddress,
          0);
        v17 = g_pMirrorLoadedNotifyA;
      }
      ((void (__fastcall *)(PWSTR))v17)(String2->Buffer);
      if ( (a3 & 0x10000000) != 0 && !a4 )
        dword_1800C9F8C = 1;
    }
  }
}

```

## disassembly

```asm
0x18004ffa4  mov     [rsp-8+arg_8], rbx
0x18004ffa9  mov     [rsp-8+arg_10], rsi
0x18004ffae  push    rbp
0x18004ffaf  push    rdi
0x18004ffb0  push    r12
0x18004ffb2  push    r14
0x18004ffb4  push    r15
0x18004ffb6  lea     rbp, [rsp-2C0h]
0x18004ffbe  sub     rsp, 3C0h
0x18004ffc5  mov     rax, cs:__security_cookie
0x18004ffcc  xor     rax, rsp
0x18004ffcf  mov     [rbp+2E0h+var_30], rax
0x18004ffd6  mov     r12d, r8d
0x18004ffd9  mov     rbx, rdx
0x18004ffdc  mov     r14, rcx
0x18004ffdf  xor     edx, edx; Val
0x18004ffe1  mov     r8d, 342h; Size
0x18004ffe7  lea     rcx, [rsp+3E0h+DisplayDevice.DeviceName+2]; void *
0x18004ffec  mov     r15d, r9d
0x18004ffef  call    memset_0
0x18004fff4  test    r14, r14
0x18004fff7  jnz     short loc_180050038
0x18004fff9  test    rbx, rbx
0x18004fffc  jnz     loc_180050225
0x180050002  test    r12d, r12d
0x180050005  jnz     loc_180050225
0x18005000b  xor     ecx, ecx
0x18005000d  lea     eax, [rbx+1]
0x180050010  lock cmpxchg cs:dword_1800C9F8C, ecx
0x180050018  jnz     loc_180050225
0x18005001e  test    r15d, r15d
0x180050021  jnz     loc_180050225
0x180050027  mov     rax, cs:?g_pMirrorLoadedNotifyA@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyA)(ushort const *)
0x18005002e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050033  jmp     loc_180050225
0x180050038  cmp     qword ptr [r14+8], 0
0x18005003d  jz      loc_180050225
0x180050043  xor     eax, eax
0x180050045  mov     [rsp+3E0h+DisplayDevice.cb], 1A8h
0x18005004d  xor     ebx, ebx
0x18005004f  xor     r9d, r9d; dwFlags
0x180050052  mov     [rsp+3E0h+DisplayDevice.DeviceName], ax
0x180050057  lea     r8, [rsp+3E0h+DisplayDevice]; lpDisplayDevice
0x18005005c  mov     edx, ebx; iDevNum
0x18005005e  xor     ecx, ecx; lpDevice
0x180050060  call    EnumDisplayDevicesW
0x180050065  test    eax, eax
0x180050067  jz      loc_180050225
0x18005006d  xorps   xmm0, xmm0
0x180050070  lea     rdx, [rsp+3E0h+DisplayDevice.DeviceName]; SourceString
0x180050075  lea     rcx, [rsp+3E0h+DestinationString]; DestinationString
0x18005007a  movups  xmmword ptr [rsp+3E0h+DestinationString.Length], xmm0
0x18005007f  call    cs:__imp_RtlInitUnicodeString
0x180050085  mov     r8b, 1; CaseInsensitive
0x180050088  lea     rcx, [rsp+3E0h+DestinationString]; String1
0x18005008d  mov     rdx, r14; String2
0x180050090  call    cs:__imp_RtlCompareUnicodeString
0x180050096  test    eax, eax
0x180050098  jz      short loc_1800500A0
0x18005009a  inc     ebx
0x18005009c  xor     eax, eax
0x18005009e  jmp     short loc_18005004F
0x1800500a0  test    byte ptr [rbp+2E0h+DisplayDevice.StateFlags], 8
0x1800500a7  jz      loc_180050225
0x1800500ad  test    byte ptr [rbp+2E0h+DisplayDevice.StateFlags], 40h
0x1800500b4  jnz     loc_180050225
0x1800500ba  cmp     cs:?g_hMirrorDrvCompatHelperA@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hMirrorDrvCompatHelperA
0x1800500c2  jnz     loc_1800501CC
0x1800500c8  mov     rcx, cs:pUserHeap; HeapHandle
0x1800500cf  mov     ebx, 208h
0x1800500d4  mov     r8d, ebx; Size
0x1800500d7  mov     [rsp+3E0h+var_3A0], ebx
0x1800500db  xor     edx, edx; Flags
0x1800500dd  call    cs:__imp_RtlAllocateHeap
0x1800500e3  mov     rdi, rax
0x1800500e6  test    rax, rax
0x1800500e9  jz      loc_180050225
0x1800500ef  lea     rax, [rsp+3E0h+var_3A0]
0x1800500f4  mov     r9d, 10000004h; dwFlags
0x1800500fa  mov     [rsp+3E0h+pcbData], rax; pcbData
0x1800500ff  lea     r8, Value; "MirrorCompatBinaryExtension"
0x180050106  mov     [rsp+3E0h+pvData], rdi; pvData
0x18005010b  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180050112  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180050119  mov     [rsp+3E0h+pdwType], 0; pdwType
0x180050122  call    cs:__imp_RegGetValueW
0x180050128  mov     rcx, cs:pUserHeap; HeapHandle
0x18005012f  xor     edx, edx; Flags
0x180050131  test    eax, eax
0x180050133  jz      short loc_180050143
0x180050135  mov     r8, rdi; P
0x180050138  call    cs:__imp_RtlFreeHeap
0x18005013e  jmp     loc_180050225
0x180050143  mov     r8, rbx; Size
0x180050146  call    cs:__imp_RtlAllocateHeap
0x18005014c  mov     rsi, rax
0x18005014f  test    rax, rax
0x180050152  jnz     short loc_180050162
0x180050154  mov     r8, rdi
0x180050157  mov     rcx, cs:pUserHeap
0x18005015e  xor     edx, edx
0x180050160  jmp     short loc_180050138
0x180050162  mov     r8d, ebx; nSize
0x180050165  mov     rdx, rsi; lpDst
0x180050168  mov     rcx, rdi; lpSrc
0x18005016b  call    cs:__imp_ExpandEnvironmentStringsW
0x180050171  mov     rcx, cs:pUserHeap; HeapHandle
0x180050178  mov     r8, rdi; P
0x18005017b  xor     edx, edx; Flags
0x18005017d  mov     ebx, eax
0x18005017f  call    cs:__imp_RtlFreeHeap
0x180050185  test    ebx, ebx
0x180050187  jnz     short loc_18005018E
0x180050189  mov     r8, rsi
0x18005018c  jmp     short loc_180050157
0x18005018e  xor     r8d, r8d; dwFlags
0x180050191  xor     edx, edx; hFile
0x180050193  mov     rcx, rsi; lpLibFileName
0x180050196  call    cs:__imp_LoadLibraryExW
0x18005019c  mov     rcx, cs:pUserHeap; HeapHandle
0x1800501a3  mov     r8, rsi; P
0x1800501a6  xor     edx, edx; Flags
0x1800501a8  mov     rbx, rax
0x1800501ab  call    cs:__imp_RtlFreeHeap
0x1800501b1  test    rbx, rbx
0x1800501b4  jz      short loc_180050225
0x1800501b6  xor     eax, eax
0x1800501b8  lock cmpxchg cs:?g_hMirrorDrvCompatHelperA@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hMirrorDrvCompatHelperA
0x1800501c1  jz      short loc_1800501CC
0x1800501c3  mov     rcx, rbx; hLibModule
0x1800501c6  call    cs:__imp_FreeLibrary
0x1800501cc  mov     rax, cs:?g_pMirrorLoadedNotifyA@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyA)(ushort const *)
0x1800501d3  test    rax, rax
0x1800501d6  jnz     short loc_180050206
0x1800501d8  mov     rcx, cs:?g_hMirrorDrvCompatHelperA@@3PEAUHINSTANCE__@@EA; hModule
0x1800501df  lea     rdx, aMirrordrvloade; "MirrorDrvLoadedNotify"
0x1800501e6  call    cs:__imp_GetProcAddress
0x1800501ec  mov     rcx, rax
0x1800501ef  test    rax, rax
0x1800501f2  jz      short loc_180050225
0x1800501f4  xor     eax, eax
0x1800501f6  lock cmpxchg cs:?g_pMirrorLoadedNotifyA@@3P6AXPEBG@ZEA, rcx; void (*g_pMirrorLoadedNotifyA)(ushort const *)
0x1800501ff  mov     rax, cs:?g_pMirrorLoadedNotifyA@@3P6AXPEBG@ZEA; void (*g_pMirrorLoadedNotifyA)(ushort const *)
0x180050206  mov     rcx, [r14+8]
0x18005020a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005020f  bt      r12d, 1Ch
0x180050214  jnb     short loc_180050225
0x180050216  test    r15d, r15d
0x180050219  jnz     short loc_180050225
0x18005021b  mov     cs:dword_1800C9F8C, 1
0x180050225  mov     rcx, [rbp+2E0h+var_30]
0x18005022c  xor     rcx, rsp; StackCookie
0x18005022f  call    __security_check_cookie
0x180050234  lea     r11, [rsp+3E0h+var_20]
0x18005023c  mov     rbx, [r11+38h]
0x180050240  mov     rsi, [r11+40h]
0x180050244  mov     rsp, r11
0x180050247  pop     r15
0x180050249  pop     r14
0x18005024b  pop     r12
0x18005024d  pop     rdi
0x18005024e  pop     rbp
0x18005024f  retn
```
