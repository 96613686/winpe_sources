# JobStore::CreateIndexEntryP(JobStore::TaskIndex,ushort const *,_SECURITY_ATTRIBUTES * const)

- ea: `0x18004ba7c`
- end: `0x18004bc01`
- name: `?CreateIndexEntryP@JobStore@@AEBAJW4TaskIndex@1@PEBGQEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `389`
- prototype: `int __high(enum JobStore::TaskIndex, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018110`
- `0x180020900`

## callees

- `0x18001fca0`
- `0x180049b74`
- `0x18004ba7c`
- `0x180056794`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004bbe9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004bbe9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bb3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004bb3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bbd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004bbd7`

## string_xrefs

- `0x18004bacb`: `TaskCache\Boot`
- `0x18004bac2`: `TaskCache\Logon`
- `0x18004bab9`: `TaskCache\Plain`
- `0x18004bab0`: `TaskCache\Maintenance`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::CreateIndexEntryP(__int64 a1, int a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  const wchar_t *v10; // rdx
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp+20h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+28h] BYREF

  lpSubKey = 0;
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 != 1 )
          goto LABEL_10;
        v10 = L"TaskCache\\Maintenance";
      }
      else
      {
        v10 = L"TaskCache\\Plain";
      }
    }
    else
    {
      v10 = L"TaskCache\\Logon";
    }
  }
  else
  {
    v10 = L"TaskCache\\Boot";
  }
  ATL::CComBSTR::operator=(&lpSubKey, v10);
LABEL_10:
  ATL::CComBSTR::operator+=(&lpSubKey, L"\\");
  ATL::CComBSTR::operator+=(&lpSubKey, a3);
  dwDisposition = 0;
  hKey = 0;
  v11 = RegCreateKeyExW(*(HKEY *)(a1 + 16), lpSubKey, 0, 0, 0, 0xF003Fu, a4, &hKey, &dwDisposition);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
        a3,
        v12);
    }
  }
  else
  {
    v12 = 0;
    if ( dwDisposition != 1 )
    {
      v12 = -2147024713;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          a3,
          183);
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  SysFreeString((BSTR)lpSubKey);
  return v12;
}

```

## disassembly

```asm
0x18004ba7c  mov     [rsp-18h+arg_10], rbx
0x18004ba81  push    rbp
0x18004ba82  push    rsi
0x18004ba83  push    rdi
0x18004ba84  mov     rbp, rsp
0x18004ba87  sub     rsp, 60h
0x18004ba8b  mov     rbx, r9
0x18004ba8e  mov     rdi, r8
0x18004ba91  mov     rsi, rcx
0x18004ba94  mov     [rbp+lpSubKey], 0
0x18004ba9c  sub     edx, 1
0x18004ba9f  jz      short loc_18004BACB
0x18004baa1  sub     edx, 1
0x18004baa4  jz      short loc_18004BAC2
0x18004baa6  sub     edx, 1
0x18004baa9  jz      short loc_18004BAB9
0x18004baab  cmp     edx, 1
0x18004baae  jnz     short loc_18004BADB
0x18004bab0  lea     rdx, aTaskcacheMaint; "TaskCache\\Maintenance"
0x18004bab7  jmp     short loc_18004BAD2
0x18004bab9  lea     rdx, aTaskcachePlain; "TaskCache\\Plain"
0x18004bac0  jmp     short loc_18004BAD2
0x18004bac2  lea     rdx, aTaskcacheLogon; "TaskCache\\Logon"
0x18004bac9  jmp     short loc_18004BAD2
0x18004bacb  lea     rdx, aTaskcacheBoot; "TaskCache\\Boot"
0x18004bad2  lea     rcx, [rbp+lpSubKey]
0x18004bad6  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004badb  lea     rdx, asc_1800A3DA8; "\\"
0x18004bae2  lea     rcx, [rbp+lpSubKey]
0x18004bae6  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x18004baeb  mov     rdx, rdi
0x18004baee  lea     rcx, [rbp+lpSubKey]
0x18004baf2  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x18004baf7  mov     [rbp+dwDisposition], 0
0x18004bafe  mov     [rbp+hKey], 0
0x18004bb06  lea     rax, [rbp+dwDisposition]
0x18004bb0a  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18004bb0f  lea     rax, [rbp+hKey]
0x18004bb13  mov     [rsp+60h+phkResult], rax; phkResult
0x18004bb18  mov     [rsp+60h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18004bb1d  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18004bb25  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18004bb2d  xor     r9d, r9d; lpClass
0x18004bb30  xor     r8d, r8d; Reserved
0x18004bb33  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18004bb37  mov     rcx, [rsi+10h]; hKey
0x18004bb3b  call    cs:__imp_RegCreateKeyExW
0x18004bb41  mov     ebx, eax
0x18004bb43  test    eax, eax
0x18004bb45  jz      short loc_18004BB7F
0x18004bb47  jle     short loc_18004BB52
0x18004bb49  movzx   ebx, ax
0x18004bb4c  or      ebx, 80070000h
0x18004bb52  lea     rax, WPP_GLOBAL_Control
0x18004bb59  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb60  cmp     rcx, rax
0x18004bb63  jz      short loc_18004BBCE
0x18004bb65  test    dword ptr [rcx+1Ch], 40000h
0x18004bb6c  jz      short loc_18004BBCE
0x18004bb6e  cmp     byte ptr [rcx+19h], 2
0x18004bb72  jb      short loc_18004BBCE
0x18004bb74  mov     edx, 3Bh ; ';'
0x18004bb79  mov     [rsp+60h+dwOptions], ebx
0x18004bb7d  jmp     short loc_18004BBBB
0x18004bb7f  xor     ebx, ebx
0x18004bb81  cmp     [rbp+dwDisposition], 1
0x18004bb85  jz      short loc_18004BBCE
0x18004bb87  mov     ebx, 800700B7h
0x18004bb8c  lea     rax, WPP_GLOBAL_Control
0x18004bb93  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb9a  cmp     rcx, rax
0x18004bb9d  jz      short loc_18004BBCE
0x18004bb9f  test    dword ptr [rcx+1Ch], 40000h
0x18004bba6  jz      short loc_18004BBCE
0x18004bba8  cmp     byte ptr [rcx+19h], 2
0x18004bbac  jb      short loc_18004BBCE
0x18004bbae  mov     edx, 3Ch ; '<'
0x18004bbb3  mov     [rsp+60h+dwOptions], 800700B7h
0x18004bbbb  mov     r9, rdi
0x18004bbbe  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18004bbc5  mov     rcx, [rcx+10h]
0x18004bbc9  call    WPP_SF_Sd
0x18004bbce  mov     rcx, [rbp+hKey]; hKey
0x18004bbd2  test    rcx, rcx
0x18004bbd5  jz      short loc_18004BBE5
0x18004bbd7  call    cs:__imp_RegCloseKey
0x18004bbdd  mov     [rbp+hKey], 0
0x18004bbe5  mov     rcx, [rbp+lpSubKey]; bstrString
0x18004bbe9  call    cs:__imp_SysFreeString
0x18004bbef  mov     eax, ebx
0x18004bbf1  mov     rbx, [rsp+60h+arg_10]
0x18004bbf9  add     rsp, 60h
0x18004bbfd  pop     rdi
0x18004bbfe  pop     rsi
0x18004bbff  pop     rbp
0x18004bc00  retn
```
