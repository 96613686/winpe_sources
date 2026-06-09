# SampInitializeComponentRequestedUpdates

- ea: `0x1800730cc`
- end: `0x18007335f`
- name: `SampInitializeComponentRequestedUpdates`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800888c0`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18006f104`
- `0x1800730cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007324a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007324a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073277`
- `ntdll!RtlInitializeCriticalSection` at `0x180073149`
- `ntdll!RtlInitializeCriticalSection` at `0x180073149`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073177`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800731d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073215`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073177`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800731d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073215`
- `LSASRV!LsaIRegisterNotification` at `0x1800732b3`
- `LSASRV!LsaIRegisterNotification` at `0x1800732b3`

## string_xrefs

- `0x18007316a`: `System\CurrentControlSet\Control\SAM\ComponentUpdates\`
- `0x1800731cb`: `System\CurrentControlSet\Control\SAM\ComponentUpdates\BuiltIn`
- `0x18007320b`: `System\CurrentControlSet\Control\SAM\ComponentUpdates\Account`

## pseudocode

```c
__int64 SampInitializeComponentRequestedUpdates()
{
  PUNICODE_STRING v0; // rcx
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rdx
  HANDLE EventW; // rax
  int v5; // eax

  v0 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 289, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( SampProductType != NtProductLanManNt )
  {
    RtlInitializeCriticalSection(&SampProcessingComponentUpdate);
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Control\\SAM\\ComponentUpdates\\",
                  0,
                  0x20019u,
                  &SampComponentUpdates);
    if ( LastError )
    {
      v0 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
        goto LABEL_15;
      v3 = 291;
    }
    else
    {
      LastError = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\SAM\\ComponentUpdates\\BuiltIn",
                    0,
                    0x20019u,
                    &SampComponentUpdatesBuiltIn);
      if ( LastError )
      {
        v0 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
          goto LABEL_15;
        v3 = 292;
      }
      else
      {
        LastError = RegOpenKeyExW(
                      HKEY_LOCAL_MACHINE,
                      L"System\\CurrentControlSet\\Control\\SAM\\ComponentUpdates\\Account",
                      0,
                      0x20019u,
                      &SampComponentUpdatesAccount);
        if ( LastError )
        {
          v0 = WPP_GLOBAL_Control;
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
            goto LABEL_15;
          v3 = 293;
        }
        else
        {
          EventW = CreateEventW(0, 0, 0, 0);
          SampComponentUpdatesWatchEvent = EventW;
          if ( EventW )
          {
            LsaIRegisterNotification(SampComponentUpdatesRegistryWatch, 0, 2, 0, 0, 0, EventW);
            v5 = SampProcessComponentUpdatesWorker(1);
            v1 = v5;
            if ( v5 >= 0 )
            {
              v0 = WPP_GLOBAL_Control;
              goto LABEL_33;
            }
            v0 = WPP_GLOBAL_Control;
            if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
              goto LABEL_9;
            WPP_SF_d(
              WPP_GLOBAL_Control[3].Buffer,
              295,
              WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
              (unsigned int)v5);
            goto LABEL_8;
          }
          v0 = WPP_GLOBAL_Control;
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) >= 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
          {
LABEL_15:
            v1 = -1073741801;
            goto LABEL_33;
          }
          LastError = GetLastError();
          v0 = WPP_GLOBAL_Control;
          v3 = 294;
        }
      }
    }
    WPP_SF_d(v0[3].Buffer, v3, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, LastError);
    v0 = WPP_GLOBAL_Control;
    goto LABEL_15;
  }
  if ( *((char *)&v0[4].MaximumLength + 2) >= 0 || HIBYTE(v0[4].Length) < 4u )
    goto LABEL_9;
  WPP_SF_(v0[3].Buffer, 290, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
LABEL_8:
  v0 = WPP_GLOBAL_Control;
LABEL_9:
  v1 = 0;
LABEL_33:
  if ( *((char *)&v0[4].MaximumLength + 2) < 0 && HIBYTE(v0[4].Length) >= 4u )
  {
    WPP_SF_d(v0[3].Buffer, 296, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v1);
    v0 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v0[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v0[3].Buffer, 297, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v1, v1);
  return v1;
}

```

## disassembly

```asm
0x1800730cc  mov     [rsp+arg_0], rbx
0x1800730d1  mov     [rsp+arg_8], rbp
0x1800730d6  push    r15
0x1800730d8  sub     rsp, 40h
0x1800730dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800730e3  lea     rbp, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x1800730ea  test    byte ptr [rcx+44h], 80h
0x1800730ee  jz      short loc_18007310E
0x1800730f0  cmp     byte ptr [rcx+41h], 4
0x1800730f4  jb      short loc_18007310E
0x1800730f6  mov     rcx, [rcx+38h]
0x1800730fa  mov     edx, 121h
0x1800730ff  mov     r8, rbp
0x180073102  call    WPP_SF_
0x180073107  mov     rcx, cs:WPP_GLOBAL_Control
0x18007310e  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x180073115  jnz     short loc_180073142
0x180073117  test    byte ptr [rcx+44h], 80h
0x18007311b  jz      short loc_18007313B
0x18007311d  cmp     byte ptr [rcx+41h], 4
0x180073121  jb      short loc_18007313B
0x180073123  mov     rcx, [rcx+38h]
0x180073127  mov     edx, 122h
0x18007312c  mov     r8, rbp
0x18007312f  call    WPP_SF_
0x180073134  mov     rcx, cs:WPP_GLOBAL_Control
0x18007313b  xor     ebx, ebx
0x18007313d  jmp     loc_180073304
0x180073142  lea     rcx, ?SampProcessingComponentUpdate@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180073149  call    cs:__imp_RtlInitializeCriticalSection
0x18007314f  lea     rax, ?SampComponentUpdates@@3PEAUHKEY__@@EA; HKEY__ * SampComponentUpdates
0x180073156  mov     ebx, 20019h
0x18007315b  mov     r15, 0FFFFFFFF80000002h
0x180073162  mov     [rsp+48h+phkResult], rax; phkResult
0x180073167  mov     r9d, ebx; samDesired
0x18007316a  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Control\\SAM"...
0x180073171  mov     rcx, r15; hKey
0x180073174  xor     r8d, r8d; ulOptions
0x180073177  call    cs:__imp_RegOpenKeyExW
0x18007317d  test    eax, eax
0x18007317f  jz      short loc_1800731B9
0x180073181  mov     rcx, cs:WPP_GLOBAL_Control
0x180073188  test    byte ptr [rcx+44h], 80h
0x18007318c  jz      short loc_1800731AF
0x18007318e  cmp     byte ptr [rcx+41h], 2
0x180073192  jb      short loc_1800731AF
0x180073194  mov     edx, 123h
0x180073199  mov     rcx, [rcx+38h]
0x18007319d  mov     r8, rbp
0x1800731a0  mov     r9d, eax
0x1800731a3  call    WPP_SF_d
0x1800731a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800731af  mov     ebx, 0C0000017h
0x1800731b4  jmp     loc_180073304
0x1800731b9  lea     rax, ?SampComponentUpdatesBuiltIn@@3PEAUHKEY__@@EA; HKEY__ * SampComponentUpdatesBuiltIn
0x1800731c0  mov     r9d, ebx; samDesired
0x1800731c3  xor     r8d, r8d; ulOptions
0x1800731c6  mov     [rsp+48h+phkResult], rax; phkResult
0x1800731cb  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\SAM"...
0x1800731d2  mov     rcx, r15; hKey
0x1800731d5  call    cs:__imp_RegOpenKeyExW
0x1800731db  test    eax, eax
0x1800731dd  jz      short loc_1800731F9
0x1800731df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800731e6  test    byte ptr [rcx+44h], 80h
0x1800731ea  jz      short loc_1800731AF
0x1800731ec  cmp     byte ptr [rcx+41h], 2
0x1800731f0  jb      short loc_1800731AF
0x1800731f2  mov     edx, 124h
0x1800731f7  jmp     short loc_180073199
0x1800731f9  lea     rax, ?SampComponentUpdatesAccount@@3PEAUHKEY__@@EA; HKEY__ * SampComponentUpdatesAccount
0x180073200  mov     r9d, ebx; samDesired
0x180073203  xor     r8d, r8d; ulOptions
0x180073206  mov     [rsp+48h+phkResult], rax; phkResult
0x18007320b  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\SAM"...
0x180073212  mov     rcx, r15; hKey
0x180073215  call    cs:__imp_RegOpenKeyExW
0x18007321b  test    eax, eax
0x18007321d  jz      short loc_180073240
0x18007321f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073226  test    byte ptr [rcx+44h], 80h
0x18007322a  jz      short loc_1800731AF
0x18007322c  cmp     byte ptr [rcx+41h], 2
0x180073230  jb      loc_1800731AF
0x180073236  mov     edx, 125h
0x18007323b  jmp     loc_180073199
0x180073240  xor     r9d, r9d; lpName
0x180073243  xor     r8d, r8d; bInitialState
0x180073246  xor     edx, edx; bManualReset
0x180073248  xor     ecx, ecx; lpEventAttributes
0x18007324a  call    cs:__imp_CreateEventW
0x180073250  mov     cs:?SampComponentUpdatesWatchEvent@@3PEAXEA, rax; void * SampComponentUpdatesWatchEvent
0x180073257  test    rax, rax
0x18007325a  jnz     short loc_18007328E
0x18007325c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073263  test    byte ptr [rcx+44h], 80h
0x180073267  jz      loc_1800731AF
0x18007326d  cmp     byte ptr [rcx+41h], 2
0x180073271  jb      loc_1800731AF
0x180073277  call    cs:__imp_GetLastError
0x18007327d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073284  mov     edx, 126h
0x180073289  jmp     loc_180073199
0x18007328e  mov     [rsp+48h+var_18], rax
0x180073293  lea     rcx, ?SampComponentUpdatesRegistryWatch@@YAJPEAX@Z; SampComponentUpdatesRegistryWatch(void *)
0x18007329a  xor     r9d, r9d
0x18007329d  mov     [rsp+48h+var_20], 0
0x1800732a5  xor     edx, edx
0x1800732a7  mov     dword ptr [rsp+48h+phkResult], 0
0x1800732af  lea     r8d, [r9+2]
0x1800732b3  call    cs:__imp_LsaIRegisterNotification
0x1800732b9  mov     ecx, 1; int
0x1800732be  call    ?SampProcessComponentUpdatesWorker@@YAJH@Z; SampProcessComponentUpdatesWorker(int)
0x1800732c3  mov     ebx, eax
0x1800732c5  test    eax, eax
0x1800732c7  jns     short loc_1800732FD
0x1800732c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800732d0  test    byte ptr [rcx+44h], 80h
0x1800732d4  jz      loc_18007313B
0x1800732da  cmp     byte ptr [rcx+41h], 2
0x1800732de  jb      loc_18007313B
0x1800732e4  mov     rcx, [rcx+38h]
0x1800732e8  mov     edx, 127h
0x1800732ed  mov     r9d, eax
0x1800732f0  mov     r8, rbp
0x1800732f3  call    WPP_SF_d
0x1800732f8  jmp     loc_180073134
0x1800732fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180073304  test    byte ptr [rcx+44h], 80h
0x180073308  jz      short loc_18007332B
0x18007330a  cmp     byte ptr [rcx+41h], 4
0x18007330e  jb      short loc_18007332B
0x180073310  mov     rcx, [rcx+38h]
0x180073314  mov     edx, 128h
0x180073319  mov     r9d, ebx
0x18007331c  mov     r8, rbp
0x18007331f  call    WPP_SF_d
0x180073324  mov     rcx, cs:WPP_GLOBAL_Control
0x18007332b  test    dword ptr [rcx+44h], 20000h
0x180073332  jz      short loc_18007334C
0x180073334  mov     rcx, [rcx+38h]
0x180073338  mov     edx, 129h
0x18007333d  mov     r9d, ebx
0x180073340  mov     dword ptr [rsp+48h+phkResult], ebx
0x180073344  mov     r8, rbp
0x180073347  call    WPP_SF_Dd
0x18007334c  mov     rbp, [rsp+48h+arg_8]
0x180073351  mov     eax, ebx
0x180073353  mov     rbx, [rsp+48h+arg_0]
0x180073358  add     rsp, 40h
0x18007335c  pop     r15
0x18007335e  retn
```
