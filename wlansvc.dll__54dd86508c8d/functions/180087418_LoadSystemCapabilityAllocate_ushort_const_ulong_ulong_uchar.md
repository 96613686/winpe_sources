# LoadSystemCapabilityAllocate(ushort const *,ulong,ulong *,uchar * *)

- ea: `0x180087418`
- end: `0x180087613`
- name: `?LoadSystemCapabilityAllocate@@YAKPEBGKPEAKPEAPEAE@Z`
- size: `507`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180087228`
- `0x18011e5a8`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180019c60`
- `0x180087418`
- `0x180106340`
- `0x180107330`
- `0x180108234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180087500`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180087515`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180087500`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180087515`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800874e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800874e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087572`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180087572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800875b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800875b4`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800874cc`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x1800874cc`

## string_xrefs

- `0x1800874bd`: `System\CurrentControlSet\Services\WlanSvc`
- `0x1800874d6`: `System\CurrentControlSet\Services\WlanSvc`

## pseudocode

```c
__int64 __fastcall LoadSystemCapabilityAllocate(
        LPCWSTR lpValueName,
        __int64 a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  PVOID *v7; // rcx
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+30h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-248h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 50, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 && a4 )
  {
    if ( IsGetCustomWfdSettingsRegPathPresent()
      && (int)GetCustomRegRootPath(SubKey, 260, L"System\\CurrentControlSet\\Services\\WlanSvc") >= 0
      || (v8 = _o_wcscpy_s(SubKey, 260, L"System\\CurrentControlSet\\Services\\WlanSvc")) == 0 )
    {
      _o_wcscat_s(SubKey, 260, L"\\");
      v8 = _o_wcscat_s(SubKey, 260, L"Parameters\\OEM\\SystemCapabilities");
    }
    if ( !v8 )
    {
      v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
      if ( !v8 )
        v8 = StpQueryRegValueAllocate(hKey, lpValueName, 4u, a3, a4);
      goto LABEL_18;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v8);
LABEL_18:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = 87;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 105) >= 4u && (*((_BYTE *)v7 + 108) & 1) != 0 )
    WPP_SF_d(v7[12], 51, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180087418  mov     [rsp+arg_8], rbx
0x18008741d  push    rbp
0x18008741e  push    rsi
0x18008741f  push    rdi
0x180087420  push    r13
0x180087422  push    r15
0x180087424  sub     rsp, 260h
0x18008742b  mov     rax, cs:__security_cookie
0x180087432  xor     rax, rsp
0x180087435  mov     [rsp+288h+var_38], rax
0x18008743d  mov     rdi, r8
0x180087440  mov     [rsp+288h+hKey], 0
0x180087449  mov     rbp, rcx
0x18008744c  mov     r8d, 208h; Size
0x180087452  lea     rcx, [rsp+288h+SubKey]; void *
0x180087457  xor     edx, edx; Val
0x180087459  mov     rsi, r9
0x18008745c  call    memset_0
0x180087461  mov     rcx, cs:WPP_GLOBAL_Control
0x180087468  lea     r13, WPP_GLOBAL_Control
0x18008746f  cmp     rcx, r13
0x180087472  jz      short loc_18008749C
0x180087474  cmp     byte ptr [rcx+69h], 4
0x180087478  jb      short loc_18008749C
0x18008747a  test    byte ptr [rcx+6Ch], 1
0x18008747e  jz      short loc_18008749C
0x180087480  mov     rcx, [rcx+60h]
0x180087484  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x18008748b  mov     edx, 32h ; '2'
0x180087490  call    WPP_SF_
0x180087495  mov     rcx, cs:WPP_GLOBAL_Control
0x18008749c  test    rdi, rdi
0x18008749f  jz      loc_1800875A2
0x1800874a5  test    rsi, rsi
0x1800874a8  jz      loc_1800875A2
0x1800874ae  call    IsGetCustomWfdSettingsRegPathPresent
0x1800874b3  mov     r15d, 104h
0x1800874b9  test    al, al
0x1800874bb  jz      short loc_1800874D6
0x1800874bd  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Wl"...
0x1800874c4  mov     edx, r15d
0x1800874c7  lea     rcx, [rsp+288h+SubKey]
0x1800874cc  call    cs:__imp_GetCustomRegRootPath
0x1800874d2  test    eax, eax
0x1800874d4  jns     short loc_1800874F1
0x1800874d6  lea     r8, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\Wl"...
0x1800874dd  mov     rdx, r15
0x1800874e0  lea     rcx, [rsp+288h+SubKey]
0x1800874e5  call    cs:__imp__o_wcscpy_s
0x1800874eb  mov     ebx, eax
0x1800874ed  test    eax, eax
0x1800874ef  jnz     short loc_18008751D
0x1800874f1  lea     r8, SubBlock; "\\"
0x1800874f8  mov     rdx, r15
0x1800874fb  lea     rcx, [rsp+288h+SubKey]
0x180087500  call    cs:__imp__o_wcscat_s
0x180087506  lea     r8, aParametersOemS; "Parameters\\OEM\\SystemCapabilities"
0x18008750d  mov     rdx, r15
0x180087510  lea     rcx, [rsp+288h+SubKey]
0x180087515  call    cs:__imp__o_wcscat_s
0x18008751b  mov     ebx, eax
0x18008751d  test    ebx, ebx
0x18008751f  jz      short loc_180087553
0x180087521  mov     rcx, cs:WPP_GLOBAL_Control
0x180087528  cmp     rcx, r13
0x18008752b  jz      short loc_1800875A7
0x18008752d  cmp     byte ptr [rcx+69h], 1
0x180087531  jb      short loc_1800875A7
0x180087533  test    byte ptr [rcx+6Ch], 1
0x180087537  jz      short loc_1800875A7
0x180087539  mov     rcx, [rcx+60h]
0x18008753d  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180087544  mov     edx, 0Ah
0x180087549  mov     r9d, ebx
0x18008754c  call    WPP_SF_d
0x180087551  jmp     short loc_180087599
0x180087553  lea     rax, [rsp+288h+hKey]
0x180087558  mov     r9d, 1; samDesired
0x18008755e  xor     r8d, r8d; ulOptions
0x180087561  mov     [rsp+288h+phkResult], rax; phkResult
0x180087566  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18008756b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180087572  call    cs:__imp_RegOpenKeyExW
0x180087578  mov     ebx, eax
0x18008757a  test    eax, eax
0x18008757c  jnz     short loc_180087599
0x18008757e  mov     rcx, [rsp+288h+hKey]; hKey
0x180087583  lea     r8d, [rax+4]; unsigned int
0x180087587  mov     r9, rdi; unsigned int *
0x18008758a  mov     [rsp+288h+phkResult], rsi; unsigned __int8 **
0x18008758f  mov     rdx, rbp; lpValueName
0x180087592  call    ?StpQueryRegValueAllocate@@YAKPEAUHKEY__@@PEBGKPEAKPEAPEAE@Z; StpQueryRegValueAllocate(HKEY__ *,ushort const *,ulong,ulong *,uchar * *)
0x180087597  mov     ebx, eax
0x180087599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875a0  jmp     short loc_1800875A7
0x1800875a2  mov     ebx, 57h ; 'W'
0x1800875a7  mov     rax, [rsp+288h+hKey]
0x1800875ac  test    rax, rax
0x1800875af  jz      short loc_1800875C1
0x1800875b1  mov     rcx, rax; hKey
0x1800875b4  call    cs:__imp_RegCloseKey
0x1800875ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875c1  cmp     rcx, r13
0x1800875c4  jz      short loc_1800875EA
0x1800875c6  cmp     byte ptr [rcx+69h], 4
0x1800875ca  jb      short loc_1800875EA
0x1800875cc  test    byte ptr [rcx+6Ch], 1
0x1800875d0  jz      short loc_1800875EA
0x1800875d2  mov     rcx, [rcx+60h]
0x1800875d6  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x1800875dd  mov     edx, 33h ; '3'
0x1800875e2  mov     r9d, ebx
0x1800875e5  call    WPP_SF_d
0x1800875ea  mov     eax, ebx
0x1800875ec  mov     rcx, [rsp+288h+var_38]
0x1800875f4  xor     rcx, rsp; StackCookie
0x1800875f7  call    __security_check_cookie
0x1800875fc  mov     rbx, [rsp+288h+arg_8]
0x180087604  add     rsp, 260h
0x18008760b  pop     r15
0x18008760d  pop     r13
0x18008760f  pop     rdi
0x180087610  pop     rsi
0x180087611  pop     rbp
0x180087612  retn
```
