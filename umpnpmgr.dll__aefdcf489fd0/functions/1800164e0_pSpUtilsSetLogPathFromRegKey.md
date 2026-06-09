# pSpUtilsSetLogPathFromRegKey

- ea: `0x1800164e0`
- end: `0x18001666f`
- name: `pSpUtilsSetLogPathFromRegKey`
- size: `399`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180016110`
- `0x18001621c`

## callees

- `0x18000c770`
- `0x18000cab0`
- `0x18000fe68`
- `0x1800101d8`
- `0x1800103f8`
- `0x180011198`
- `0x1800164e0`
- `0x180017708`
- `0x180018460`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800165b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016584`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001657a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001657a`

## string_xrefs

- `0x180016548`: `LogPath`

## pseudocode

```c
_BOOL8 pSpUtilsSetLogPathFromRegKey()
{
  DWORD OverrideValue; // ebx
  DWORD v1; // eax
  __int64 v3; // rdi
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v5; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+260h] [rbp+160h] BYREF

  LODWORD(v6) = 520;
  KeyHandle = 0;
  v5 = 0;
  OverrideValue = pSpUtilsOpenSetupKey(&KeyHandle, &v5);
  if ( OverrideValue )
    goto LABEL_9;
  OverrideValue = pSpUtilsQueryOverrideValue(KeyHandle, v5, L"LogPath", Src, (__int64)&v6);
  if ( !OverrideValue )
  {
    v1 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( v1 )
    {
      if ( v1 > 0x104 )
      {
        OverrideValue = 122;
        goto LABEL_5;
      }
      v3 = -1;
      do
        ++v3;
      while ( Dst[v3] );
      if ( pSetupConcatenatePaths((__int64)Dst, L"setupapi.dev.log", 0x104u) )
      {
        OverrideValue = pSetupMakeSurePathExists(Dst);
        if ( OverrideValue )
          goto LABEL_5;
        if ( 2 * (unsigned __int64)(unsigned int)v3 >= 0x208 )
          _report_rangecheckfailure();
        Dst[(unsigned int)v3] = 0;
        if ( (unsigned int)pSpUtilsSetTextLogPath((__int64)Dst, OverrideValue + 1) )
        {
          if ( (unsigned int)pSpUtilsLogSetPath((__int64)Dst) )
            goto LABEL_5;
        }
      }
    }
    OverrideValue = GetLastError();
  }
LABEL_5:
  if ( KeyHandle )
    pSetupCloseKey((unsigned int)KeyHandle);
  if ( v5 )
    pSetupCloseKey((unsigned int)v5);
LABEL_9:
  SetLastError(OverrideValue);
  return OverrideValue == 0;
}

```

## disassembly

```asm
0x1800164e0  push    rbp
0x1800164e2  push    rbx
0x1800164e3  push    rdi
0x1800164e4  push    r15
0x1800164e6  lea     rbp, [rsp-388h]
0x1800164ee  sub     rsp, 488h
0x1800164f5  mov     rax, cs:__security_cookie
0x1800164fc  xor     rax, rsp
0x1800164ff  mov     [rbp+3A0h+var_30], rax
0x180016506  xor     r15d, r15d
0x180016509  mov     dword ptr [rsp+4A0h+var_460], 208h
0x180016511  lea     rdx, [rsp+4A0h+var_468]
0x180016516  mov     [rsp+4A0h+KeyHandle], r15
0x18001651b  lea     rcx, [rsp+4A0h+KeyHandle]
0x180016520  mov     [rsp+4A0h+var_468], r15
0x180016525  call    pSpUtilsOpenSetupKey
0x18001652a  mov     ebx, eax
0x18001652c  test    eax, eax
0x18001652e  jnz     short loc_1800165AE
0x180016530  mov     rdx, [rsp+4A0h+var_468]; HANDLE
0x180016535  lea     rax, [rsp+4A0h+var_460]
0x18001653a  mov     rcx, [rsp+4A0h+KeyHandle]; KeyHandle
0x18001653f  lea     r9d, [r15+1]
0x180016543  mov     [rsp+4A0h+var_478], rax; __int64
0x180016548  lea     r8, aLogpath; "LogPath"
0x18001654f  lea     rax, [rbp+3A0h+Src]
0x180016556  mov     [rsp+4A0h+var_480], rax; void *
0x18001655b  call    pSpUtilsQueryOverrideValue
0x180016560  mov     ebx, eax
0x180016562  test    eax, eax
0x180016564  jnz     short loc_18001658C
0x180016566  mov     ebx, 104h
0x18001656b  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x180016570  mov     r8d, ebx; nSize
0x180016573  lea     rcx, [rbp+3A0h+Src]; lpSrc
0x18001657a  call    cs:__imp_ExpandEnvironmentStringsW
0x180016580  test    eax, eax
0x180016582  jnz     short loc_1800165DA
0x180016584  call    cs:__imp_GetLastError
0x18001658a  mov     ebx, eax
0x18001658c  cmp     [rsp+4A0h+KeyHandle], r15
0x180016591  jz      short loc_18001659D
0x180016593  mov     rcx, [rsp+4A0h+KeyHandle]
0x180016598  call    pSetupCloseKey
0x18001659d  cmp     [rsp+4A0h+var_468], r15
0x1800165a2  jz      short loc_1800165AE
0x1800165a4  mov     rcx, [rsp+4A0h+var_468]
0x1800165a9  call    pSetupCloseKey
0x1800165ae  mov     ecx, ebx; dwErrCode
0x1800165b0  call    cs:__imp_SetLastError
0x1800165b6  test    ebx, ebx
0x1800165b8  mov     eax, r15d
0x1800165bb  setz    al
0x1800165be  mov     rcx, [rbp+3A0h+var_30]
0x1800165c5  xor     rcx, rsp; StackCookie
0x1800165c8  call    __security_check_cookie
0x1800165cd  add     rsp, 488h
0x1800165d4  pop     r15
0x1800165d6  pop     rdi
0x1800165d7  pop     rbx
0x1800165d8  pop     rbp
0x1800165d9  retn
0x1800165da  cmp     eax, ebx
0x1800165dc  jbe     short loc_1800165E5
0x1800165de  mov     ebx, 7Ah ; 'z'
0x1800165e3  jmp     short loc_18001658C
0x1800165e5  lea     rax, [rsp+4A0h+Dst]
0x1800165ea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800165ee  inc     rdi
0x1800165f1  cmp     [rax+rdi*2], r15w
0x1800165f6  jnz     short loc_1800165EE
0x1800165f8  mov     r8d, ebx
0x1800165fb  lea     rdx, aSetupapiDevLog; "setupapi.dev.log"
0x180016602  lea     rcx, [rsp+4A0h+Dst]
0x180016607  call    pSetupConcatenatePaths
0x18001660c  test    eax, eax
0x18001660e  jz      loc_180016584
0x180016614  lea     rcx, [rsp+4A0h+Dst]
0x180016619  call    pSetupMakeSurePathExists
0x18001661e  mov     ebx, eax
0x180016620  test    eax, eax
0x180016622  jnz     loc_18001658C
0x180016628  mov     eax, edi
0x18001662a  lea     rcx, [rax+rax]
0x18001662e  cmp     rcx, 208h
0x180016635  jnb     short loc_180016669
0x180016637  mov     [rsp+rcx+4A0h+Dst], r15w
0x18001663d  lea     edx, [rbx+1]
0x180016640  lea     rcx, [rsp+4A0h+Dst]
0x180016645  call    _pSpUtilsSetTextLogPath
0x18001664a  test    eax, eax
0x18001664c  jz      loc_180016584
0x180016652  lea     rcx, [rsp+4A0h+Dst]
0x180016657  call    _pSpUtilsLogSetPath
0x18001665c  test    eax, eax
0x18001665e  jnz     loc_18001658C
0x180016664  jmp     loc_180016584
0x180016669  call    __report_rangecheckfailure
```
