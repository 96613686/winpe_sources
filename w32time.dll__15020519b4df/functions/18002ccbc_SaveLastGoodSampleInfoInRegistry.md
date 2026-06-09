# SaveLastGoodSampleInfoInRegistry

- ea: `0x18002ccbc`
- end: `0x18002cfb1`
- name: `SaveLastGoodSampleInfoInRegistry`
- size: `757`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f8fc`

## callees

- `0x180003ac0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002ccbc`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ce9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ce9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cfa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800676dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800676f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cf81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cfa0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800676dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800676f9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cf48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002cf48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ceff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ceff`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002ce3c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002ce3c`

## string_xrefs

- `0x18002ce35`: `W32TimeConfig`
- `0x18002ce2e`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x18002ce60`: `System\CurrentControlSet\Services\W32Time\Config`
- `0x18002cebb`: `Failed to open config regkey. Error: 0x%x\n`
- `0x18002cdbf`: `Failed at StringCchPrintfW to combine time:%I64u and time server:%s\n`
- `0x18002cf1c`: `Failed to open/create config status regkey. Error: 0x%x\n`

## pseudocode

```c
LSTATUS __fastcall SaveLastGoodSampleInfoInRegistry(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rax
  bool v5; // zf
  int v6; // eax
  LSTATUS result; // eax
  __int64 v8; // rcx
  BYTE *v9; // rax
  __int64 v10; // rdi
  unsigned int PersistedRegistryLocationW; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  HKEY hKey; // [rsp+50h] [rbp-488h] BYREF
  HKEY v16; // [rsp+58h] [rbp-480h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-478h] BYREF
  BYTE Data[2]; // [rsp+70h] [rbp-468h] BYREF
  _BYTE v19[558]; // [rsp+72h] [rbp-466h] BYREF
  WCHAR SubKey; // [rsp+2A0h] [rbp-238h] BYREF
  _BYTE v21[526]; // [rsp+2A2h] [rbp-236h] BYREF

  dwDisposition[0] = 0;
  hKey = 0;
  v16 = 0;
  SubKey = 0;
  memset_0(v21, 0, 0x206u);
  *(_WORD *)Data = 0;
  memset_0(v19, 0, 0x226u);
  v4 = HIDWORD(*a1);
  v5 = (_DWORD)v4 == 30460909;
  if ( (unsigned int)v4 > 0x1D0CBED )
    goto LABEL_8;
  v6 = 0;
  if ( v5 )
    LOBYTE(v6) = *(_DWORD *)a1 > 0x24C8000u;
  if ( v6 )
  {
LABEL_8:
    if ( (int)StringCchPrintfW((unsigned __int16 *)Data, 0x114u, L"%I64u;%s", *a1, a2) >= 0 )
    {
      v8 = 276;
      v9 = Data;
      do
      {
        if ( !*(_WORD *)v9 )
          break;
        v9 += 2;
        --v8;
      }
      while ( v8 );
      v10 = 2 * ((276 - v8) & ((unsigned __int128)-(__int128)(unsigned __int64)v8 >> 64));
      if ( v8 )
      {
        PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                       L"W32TimeConfig",
                                       L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                                       &SubKey,
                                       520,
                                       0);
        if ( PersistedRegistryLocationW )
        {
          result = FileLogAllowEntry(0);
          if ( (_BYTE)result )
            result = FileLogAdd(
                       L"Failed to get time regkey %s. Error: 0x%x\n",
                       L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                       PersistedRegistryLocationW);
        }
        else
        {
          v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20006u, &hKey);
          if ( v12 )
          {
            result = FileLogAllowEntry(0);
            if ( (_BYTE)result )
              result = FileLogAdd(L"Failed to open config regkey. Error: 0x%x\n", v12);
          }
          else
          {
            v13 = RegCreateKeyExW(hKey, L"Status", 0, 0, 0, 2u, 0, &v16, dwDisposition);
            if ( v13 )
            {
              result = FileLogAllowEntry(0);
              if ( (_BYTE)result )
                result = FileLogAdd(L"Failed to open/create config status regkey. Error: 0x%x\n", v13);
            }
            else
            {
              result = RegSetValueExW(v16, L"LastGoodSampleInfo", 0, 1u, Data, v10);
              v14 = result;
              if ( result )
              {
                result = FileLogAllowEntry(1001);
                if ( (_BYTE)result )
                  result = FileLogAdd(L"Failed to save last good sample info. RetVal: 0x%x\n", v14);
              }
            }
          }
        }
        if ( hKey )
        {
          result = RegCloseKey(hKey);
          hKey = 0;
        }
        if ( v16 )
          return RegCloseKey(v16);
      }
      else
      {
        result = FileLogAllowEntry(0);
        if ( (_BYTE)result )
          return FileLogAdd(L"Failed at StringCbLengthW to get the size of wszLastSampleInfo\n");
      }
    }
    else
    {
      result = FileLogAllowEntry(0);
      if ( (_BYTE)result )
        return FileLogAdd(L"Failed at StringCchPrintfW to combine time:%I64u and time server:%s\n", *a1, a2);
    }
  }
  else
  {
    result = FileLogAllowEntry(0);
    if ( (_BYTE)result )
      return FileLogAdd(L"Last good sample info Time value is too low.\n");
  }
  return result;
}

```

## disassembly

```asm
0x18002ccbc  mov     [rsp+arg_10], rbx
0x18002ccc1  push    rsi
0x18002ccc2  push    rdi
0x18002ccc3  push    r14
0x18002ccc5  sub     rsp, 4C0h
0x18002cccc  mov     rax, cs:__security_cookie
0x18002ccd3  xor     rax, rsp
0x18002ccd6  mov     [rsp+4D8h+var_28], rax
0x18002ccde  mov     rdi, rdx
0x18002cce1  mov     rsi, rcx
0x18002cce4  xor     r14d, r14d
0x18002cce7  mov     [rsp+4D8h+dwDisposition], r14d
0x18002ccec  mov     [rsp+4D8h+hKey], r14
0x18002ccf1  mov     [rsp+4D8h+var_480], r14
0x18002ccf6  mov     [rsp+4D8h+SubKey], r14w
0x18002ccff  xor     edx, edx; Val
0x18002cd01  mov     r8d, 206h; Size
0x18002cd07  lea     rcx, [rsp+4D8h+var_236]; void *
0x18002cd0f  call    memset_0
0x18002cd14  mov     word ptr [rsp+4D8h+Data], r14w
0x18002cd1a  xor     edx, edx; Val
0x18002cd1c  mov     r8d, 226h; Size
0x18002cd22  lea     rcx, [rsp+4D8h+var_466]; void *
0x18002cd27  call    memset_0
0x18002cd2c  mov     rax, [rsi]
0x18002cd2f  shr     rax, 20h
0x18002cd33  mov     ecx, 1D0CBEDh
0x18002cd38  cmp     eax, ecx
0x18002cd3a  ja      short loc_18002CD8A
0x18002cd3c  mov     eax, r14d
0x18002cd3f  jnz     short loc_18002CD4A
0x18002cd41  cmp     dword ptr [rsi], 24C8000h
0x18002cd47  setnbe  al
0x18002cd4a  test    eax, eax
0x18002cd4c  jnz     short loc_18002CD8A
0x18002cd4e  xor     ecx, ecx
0x18002cd50  call    FileLogAllowEntry
0x18002cd55  test    al, al
0x18002cd57  jz      short loc_18002CD65
0x18002cd59  lea     rcx, aLastGoodSample; "Last good sample info Time value is too"...
0x18002cd60  call    FileLogAdd
0x18002cd65  mov     rcx, [rsp+4D8h+var_28]
0x18002cd6d  xor     rcx, rsp; StackCookie
0x18002cd70  call    __security_check_cookie
0x18002cd75  mov     rbx, [rsp+4D8h+arg_10]
0x18002cd7d  add     rsp, 4C0h
0x18002cd84  pop     r14
0x18002cd86  pop     rdi
0x18002cd87  pop     rsi
0x18002cd88  retn
0x18002cd8a  mov     [rsp+4D8h+phkResult], rdi
0x18002cd8f  mov     r9, [rsi]
0x18002cd92  lea     r8, aI64uS; "%I64u;%s"
0x18002cd99  mov     ebx, 114h
0x18002cd9e  mov     edx, ebx; unsigned __int64
0x18002cda0  lea     rcx, [rsp+4D8h+Data]; unsigned __int16 *
0x18002cda5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cdaa  test    eax, eax
0x18002cdac  jns     short loc_18002CDCD
0x18002cdae  xor     ecx, ecx
0x18002cdb0  call    FileLogAllowEntry
0x18002cdb5  test    al, al
0x18002cdb7  jz      short loc_18002CD65
0x18002cdb9  mov     r8, rdi
0x18002cdbc  mov     rdx, [rsi]
0x18002cdbf  lea     rcx, aFailedAtString_1; "Failed at StringCchPrintfW to combine t"...
0x18002cdc6  call    FileLogAdd
0x18002cdcb  jmp     short loc_18002CD65
0x18002cdcd  mov     rcx, rbx
0x18002cdd0  lea     rax, [rsp+4D8h+Data]
0x18002cdd5  cmp     [rax], r14w
0x18002cdd9  jz      short loc_18002CDE5
0x18002cddb  add     rax, 2
0x18002cddf  sub     rcx, 1
0x18002cde3  jnz     short loc_18002CDD5
0x18002cde5  mov     rax, rcx
0x18002cde8  sub     rbx, rcx
0x18002cdeb  neg     rax
0x18002cdee  sbb     rdx, rdx
0x18002cdf1  and     rdx, rbx
0x18002cdf4  test    rcx, rcx
0x18002cdf7  lea     rdi, [rdx+rdx]
0x18002cdfb  jnz     short loc_18002CE1B
0x18002cdfd  mov     rdi, r14
0x18002ce00  xor     ecx, ecx
0x18002ce02  call    FileLogAllowEntry
0x18002ce07  test    al, al
0x18002ce09  jz      loc_18002CD65
0x18002ce0f  lea     rcx, aFailedAtString_0; "Failed at StringCbLengthW to get the si"...
0x18002ce16  jmp     loc_18002CD60
0x18002ce1b  mov     [rsp+4D8h+phkResult], r14
0x18002ce20  mov     r9d, 208h
0x18002ce26  lea     r8, [rsp+4D8h+SubKey]
0x18002ce2e  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18002ce35  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x18002ce3c  call    cs:__imp_GetPersistedRegistryLocationW
0x18002ce43  nop     dword ptr [rax+rax+00h]
0x18002ce48  mov     ebx, eax
0x18002ce4a  test    eax, eax
0x18002ce4c  jz      short loc_18002CE78
0x18002ce4e  xor     ecx, ecx
0x18002ce50  call    FileLogAllowEntry
0x18002ce55  test    al, al
0x18002ce57  jz      loc_18002CF77
0x18002ce5d  mov     r8d, ebx
0x18002ce60  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18002ce67  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x18002ce6e  call    FileLogAdd
0x18002ce73  jmp     loc_18002CF77
0x18002ce78  lea     rax, [rsp+4D8h+hKey]
0x18002ce7d  mov     [rsp+4D8h+phkResult], rax; phkResult
0x18002ce82  mov     r9d, 20006h; samDesired
0x18002ce88  xor     r8d, r8d; ulOptions
0x18002ce8b  lea     rdx, [rsp+4D8h+SubKey]; lpSubKey
0x18002ce93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ce9a  call    cs:__imp_RegOpenKeyExW
0x18002cea1  nop     dword ptr [rax+rax+00h]
0x18002cea6  mov     ebx, eax
0x18002cea8  test    eax, eax
0x18002ceaa  jz      short loc_18002CEC7
0x18002ceac  xor     ecx, ecx
0x18002ceae  call    FileLogAllowEntry
0x18002ceb3  test    al, al
0x18002ceb5  jz      loc_18002CF77
0x18002cebb  lea     rcx, aFailedToOpenCo; "Failed to open config regkey. Error: 0x"...
0x18002cec2  jmp     loc_18002CF6F
0x18002cec7  lea     rax, [rsp+4D8h+dwDisposition]
0x18002cecc  mov     [rsp+4D8h+lpdwDisposition], rax; lpdwDisposition
0x18002ced1  lea     rax, [rsp+4D8h+var_480]
0x18002ced6  mov     [rsp+4D8h+var_4A0], rax; phkResult
0x18002cedb  mov     [rsp+4D8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002cee0  mov     [rsp+4D8h+samDesired], 2; samDesired
0x18002cee8  mov     dword ptr [rsp+4D8h+phkResult], r14d; dwOptions
0x18002ceed  xor     r9d, r9d; lpClass
0x18002cef0  xor     r8d, r8d; Reserved
0x18002cef3  lea     rdx, aStatus; "Status"
0x18002cefa  mov     rcx, [rsp+4D8h+hKey]; hKey
0x18002ceff  call    cs:__imp_RegCreateKeyExW
0x18002cf06  nop     dword ptr [rax+rax+00h]
0x18002cf0b  mov     ebx, eax
0x18002cf0d  test    eax, eax
0x18002cf0f  jz      short loc_18002CF25
0x18002cf11  xor     ecx, ecx
0x18002cf13  call    FileLogAllowEntry
0x18002cf18  test    al, al
0x18002cf1a  jz      short loc_18002CF77
0x18002cf1c  lea     rcx, aFailedToOpenCr; "Failed to open/create config status reg"...
0x18002cf23  jmp     short loc_18002CF6F
0x18002cf25  mov     [rsp+4D8h+samDesired], edi; cbData
0x18002cf29  lea     rax, [rsp+4D8h+Data]
0x18002cf2e  mov     [rsp+4D8h+phkResult], rax; lpData
0x18002cf33  mov     r9d, 1; dwType
0x18002cf39  xor     r8d, r8d; Reserved
0x18002cf3c  lea     rdx, ValueName; "LastGoodSampleInfo"
0x18002cf43  mov     rcx, [rsp+4D8h+var_480]; hKey
0x18002cf48  call    cs:__imp_RegSetValueExW
0x18002cf4f  nop     dword ptr [rax+rax+00h]
0x18002cf54  mov     ebx, eax
0x18002cf56  test    eax, eax
0x18002cf58  jz      short loc_18002CF77
0x18002cf5a  mov     ecx, 3E9h
0x18002cf5f  call    FileLogAllowEntry
0x18002cf64  test    al, al
0x18002cf66  jz      short loc_18002CF77
0x18002cf68  lea     rcx, aFailedToSaveLa; "Failed to save last good sample info. R"...
0x18002cf6f  mov     edx, ebx
0x18002cf71  call    FileLogAdd
0x18002cf76  nop
0x18002cf77  mov     rcx, [rsp+4D8h+hKey]; hKey
0x18002cf7c  test    rcx, rcx
0x18002cf7f  jz      short loc_18002CF92
0x18002cf81  call    cs:__imp_RegCloseKey
0x18002cf88  nop     dword ptr [rax+rax+00h]
0x18002cf8d  mov     [rsp+4D8h+hKey], r14
0x18002cf92  mov     rcx, [rsp+4D8h+var_480]; hKey
0x18002cf97  test    rcx, rcx
0x18002cf9a  jz      loc_18002CD65
0x18002cfa0  call    cs:__imp_RegCloseKey
0x18002cfa7  nop     dword ptr [rax+rax+00h]
0x18002cfac  jmp     loc_18002CD65
0x1800676ca  push    rbp
0x1800676cc  sub     rsp, 50h
0x1800676d0  mov     rbp, rdx
0x1800676d3  mov     rcx, [rbp+50h]; hKey
0x1800676d7  test    rcx, rcx
0x1800676da  jz      short loc_1800676F0
0x1800676dc  call    cs:__imp_RegCloseKey
0x1800676e3  nop     dword ptr [rax+rax+00h]
0x1800676e8  mov     qword ptr [rbp+50h], 0
0x1800676f0  mov     rcx, [rbp+58h]; hKey
0x1800676f4  test    rcx, rcx
0x1800676f7  jz      short loc_180067706
0x1800676f9  call    cs:__imp_RegCloseKey
0x180067700  nop     dword ptr [rax+rax+00h]
0x180067705  nop
0x180067706  add     rsp, 50h
0x18006770a  pop     rbp
0x18006770b  retn
```
