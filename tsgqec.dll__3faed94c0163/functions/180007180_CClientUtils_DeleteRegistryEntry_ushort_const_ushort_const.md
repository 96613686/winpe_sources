# CClientUtils::DeleteRegistryEntry(ushort const *,ushort const *)

- ea: `0x180007180`
- end: `0x18000741f`
- name: `?DeleteRegistryEntry@CClientUtils@@UEAAHPEBG0@Z`
- size: `671`
- prototype: `int(CClientUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003970`
- `0x18000594c`
- `0x180007180`
- `0x180007f84`
- `0x18000a508`
- `0x18000a7b8`
- `0x18000a858`
- `0x18000a8ac`
- `0x18000aac4`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180007343`
- `ADVAPI32!RegDeleteValueW` at `0x180007343`
- `ADVAPI32!RegOpenKeyExW` at `0x18000726b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800072f5`
- `ADVAPI32!RegOpenKeyExW` at `0x18000726b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800072f5`
- `ADVAPI32!RegCloseKey` at `0x1800073a4`
- `ADVAPI32!RegCloseKey` at `0x1800073f1`
- `ADVAPI32!RegCloseKey` at `0x1800073a4`
- `ADVAPI32!RegCloseKey` at `0x1800073f1`

## string_xrefs

- `0x18000721c`: `Unable to get AppContainer registry location.`

## pseudocode

```c
__int64 __fastcall CClientUtils::DeleteRegistryEntry(
        CClientUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // esi
  int AppContainerRegistryLocation; // eax
  char v7; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS v9; // eax
  char v10; // di
  unsigned int v11; // eax
  int v12; // r8d
  int v13; // edx
  LSTATUS v14; // eax
  LSTATUS v15; // edi
  unsigned int v16; // eax
  __int64 v17; // r8
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[272]; // [rsp+40h] [rbp-C0h] BYREF

  phkResult = 0;
  v4 = 0;
  hKey = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  if ( (unsigned int)CClientUtilsWin32::UT_IsRunningInAppContainer() )
  {
    AppContainerRegistryLocation = CClientUtilsWin32::UT_GetAppContainerRegistryLocation(&hKey);
    v7 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Unable to get AppContainer registry location.",
          v7);
      }
      goto LABEL_28;
    }
    v9 = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 23;
      goto LABEL_12;
    }
  }
  else
  {
    v14 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &phkResult);
    v10 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_28;
      }
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 24;
LABEL_12:
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v12, v11, (__int64)SubKey, v10);
      goto LABEL_28;
    }
  }
  if ( RegDeleteValueW(phkResult, a3)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, (__int64)a2);
  }
  v4 = 1;
  v15 = RegCloseKey(phkResult);
  if ( v15
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, v16, v15);
  }
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180007180  mov     [rsp-8+arg_0], rbx
0x180007185  push    rbp
0x180007186  push    rsi
0x180007187  push    rdi
0x180007188  push    r14
0x18000718a  push    r15
0x18000718c  lea     rbp, [rsp-170h]
0x180007194  sub     rsp, 270h
0x18000719b  mov     rax, cs:__security_cookie
0x1800071a2  xor     rax, rsp
0x1800071a5  mov     [rbp+190h+var_30], rax
0x1800071ac  mov     r14, r8
0x1800071af  mov     [rsp+290h+var_260], 0
0x1800071b8  xor     esi, esi
0x1800071ba  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x1800071bf  mov     r8, rdx; unsigned __int16 *
0x1800071c2  mov     [rsp+290h+hKey], rsi
0x1800071c7  mov     r15, rdx
0x1800071ca  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1800071cf  call    ?UT_IsRunningInAppContainer@CClientUtilsWin32@@SAHXZ; CClientUtilsWin32::UT_IsRunningInAppContainer(void)
0x1800071d4  test    eax, eax
0x1800071d6  jz      loc_1800072D6
0x1800071dc  lea     rcx, [rsp+290h+hKey]; HKEY *
0x1800071e1  call    ?UT_GetAppContainerRegistryLocation@CClientUtilsWin32@@SAJPEAPEAUHKEY__@@@Z; CClientUtilsWin32::UT_GetAppContainerRegistryLocation(HKEY__ * *)
0x1800071e6  mov     edi, eax
0x1800071e8  test    eax, eax
0x1800071ea  jns     short loc_18000724E
0x1800071ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071f3  lea     rbx, WPP_GLOBAL_Control
0x1800071fa  cmp     rcx, rbx
0x1800071fd  jz      loc_1800073E7
0x180007203  test    byte ptr [rcx+1Ch], 8
0x180007207  jz      loc_1800073E7
0x18000720d  cmp     byte ptr [rcx+19h], 2
0x180007211  jb      loc_1800073E7
0x180007217  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000721c  lea     rcx, aUnableToGetApp; "Unable to get AppContainer registry loc"...
0x180007223  mov     dword ptr [rsp+290h+var_268], edi
0x180007227  mov     [rsp+290h+phkResult], rcx
0x18000722c  lea     edx, [rsi+16h]
0x18000722f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007236  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x18000723d  mov     r9d, eax
0x180007240  mov     rcx, [rcx+10h]
0x180007244  call    WPP_SF_DsD
0x180007249  jmp     loc_1800073E7
0x18000724e  mov     rcx, [rsp+290h+hKey]; hKey
0x180007253  lea     rax, [rsp+290h+var_260]
0x180007258  mov     r9d, 20006h; samDesired
0x18000725e  mov     [rsp+290h+phkResult], rax; phkResult
0x180007263  xor     r8d, r8d; ulOptions
0x180007266  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18000726b  call    cs:__imp_RegOpenKeyExW
0x180007271  mov     edi, eax
0x180007273  test    eax, eax
0x180007275  jz      loc_18000733B
0x18000727b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007282  lea     rbx, WPP_GLOBAL_Control
0x180007289  cmp     rcx, rbx
0x18000728c  jz      loc_1800073E7
0x180007292  test    byte ptr [rcx+1Ch], 1
0x180007296  jz      loc_1800073E7
0x18000729c  cmp     byte ptr [rcx+19h], 4
0x1800072a0  jb      loc_1800073E7
0x1800072a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800072ab  mov     edx, 17h
0x1800072b0  lea     rcx, [rsp+290h+SubKey]
0x1800072b5  mov     dword ptr [rsp+290h+var_268], edi
0x1800072b9  mov     [rsp+290h+phkResult], rcx
0x1800072be  mov     r9d, eax
0x1800072c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072c8  mov     rcx, [rcx+10h]
0x1800072cc  call    WPP_SF_DSd
0x1800072d1  jmp     loc_1800073E7
0x1800072d6  lea     rax, [rsp+290h+var_260]
0x1800072db  mov     r9d, 20006h; samDesired
0x1800072e1  xor     r8d, r8d; ulOptions
0x1800072e4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800072e9  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1800072ee  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800072f5  call    cs:__imp_RegOpenKeyExW
0x1800072fb  mov     edi, eax
0x1800072fd  test    eax, eax
0x1800072ff  jz      short loc_18000733B
0x180007301  mov     rcx, cs:WPP_GLOBAL_Control
0x180007308  lea     rbx, WPP_GLOBAL_Control
0x18000730f  cmp     rcx, rbx
0x180007312  jz      loc_1800073E7
0x180007318  test    byte ptr [rcx+1Ch], 1
0x18000731c  jz      loc_1800073E7
0x180007322  cmp     byte ptr [rcx+19h], 4
0x180007326  jb      loc_1800073E7
0x18000732c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007331  mov     edx, 18h
0x180007336  jmp     loc_1800072B0
0x18000733b  mov     rcx, [rsp+290h+var_260]; hKey
0x180007340  mov     rdx, r14; lpValueName
0x180007343  call    cs:__imp_RegDeleteValueW
0x180007349  lea     rbx, WPP_GLOBAL_Control
0x180007350  test    eax, eax
0x180007352  jz      short loc_18000739A
0x180007354  mov     rax, cs:WPP_GLOBAL_Control
0x18000735b  cmp     rax, rbx
0x18000735e  jz      short loc_18000739A
0x180007360  test    byte ptr [rax+1Ch], 1
0x180007364  jz      short loc_18000739A
0x180007366  cmp     byte ptr [rax+19h], 4
0x18000736a  jb      short loc_18000739A
0x18000736c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180007371  mov     rcx, cs:WPP_GLOBAL_Control
0x180007378  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x18000737f  mov     edx, 19h
0x180007384  mov     [rsp+290h+var_268], r15; __int64
0x180007389  mov     r9d, eax
0x18000738c  mov     [rsp+290h+phkResult], r14; __int64
0x180007391  mov     rcx, [rcx+10h]; LoggerHandle
0x180007395  call    WPP_SF_DSS
0x18000739a  mov     esi, 1
0x18000739f  mov     rcx, [rsp+290h+var_260]; hKey
0x1800073a4  call    cs:__imp_RegCloseKey
0x1800073aa  mov     edi, eax
0x1800073ac  test    eax, eax
0x1800073ae  jz      short loc_1800073E7
0x1800073b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073b7  cmp     rcx, rbx
0x1800073ba  jz      short loc_1800073E7
0x1800073bc  test    [rcx+1Ch], sil
0x1800073c0  jz      short loc_1800073E7
0x1800073c2  cmp     byte ptr [rcx+19h], 2
0x1800073c6  jb      short loc_1800073E7
0x1800073c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800073cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073d4  lea     edx, [rsi+19h]
0x1800073d7  mov     r9d, eax
0x1800073da  mov     dword ptr [rsp+290h+phkResult], edi
0x1800073de  mov     rcx, [rcx+10h]
0x1800073e2  call    WPP_SF_Dl
0x1800073e7  mov     rcx, [rsp+290h+hKey]; hKey
0x1800073ec  test    rcx, rcx
0x1800073ef  jz      short loc_1800073F7
0x1800073f1  call    cs:__imp_RegCloseKey
0x1800073f7  mov     eax, esi
0x1800073f9  mov     rcx, [rbp+190h+var_30]
0x180007400  xor     rcx, rsp; StackCookie
0x180007403  call    __security_check_cookie
0x180007408  mov     rbx, [rsp+290h+arg_0]
0x180007410  add     rsp, 270h
0x180007417  pop     r15
0x180007419  pop     r14
0x18000741b  pop     rdi
0x18000741c  pop     rsi
0x18000741d  pop     rbp
0x18000741e  retn
```
