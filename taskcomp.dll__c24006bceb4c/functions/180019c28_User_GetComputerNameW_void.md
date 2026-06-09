# User::GetComputerNameW(void)

- ea: `0x180019c28`
- end: `0x180019ce7`
- name: `?GetComputerNameW@User@@CAPEBGXZ`
- size: `191`
- prototype: `WCHAR *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001af08`

## callees

- `0x18000878c`
- `0x18000fbb8`
- `0x180019c28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c92`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180019c56`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180019c56`

## pseudocode

```c
WCHAR *User::GetComputerNameW(void)
{
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v2; // [rsp+28h] [rbp-38h]
  char *v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+38h] [rbp-28h]
  __int64 v5; // [rsp+40h] [rbp-20h]
  DWORD LastError; // [rsp+48h] [rbp-18h]
  __int64 v7; // [rsp+4Ch] [rbp-14h]
  DWORD nSize; // [rsp+70h] [rbp+10h] BYREF

  if ( !User::s_computername )
  {
    nSize = 16;
    if ( !GetComputerNameW(&User::s_computername, &nSize) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids);
      }
      v2 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v4 = 0;
      v3 = byte_1800505F8;
      v5 = 0;
      LastError = GetLastError();
      v7 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  return &User::s_computername;
}

```

## disassembly

```asm
0x180019c28  mov     [rsp-8+arg_8], rbx
0x180019c2d  push    rbp
0x180019c2e  mov     rbp, rsp
0x180019c31  sub     rsp, 60h
0x180019c35  xor     ebx, ebx
0x180019c37  cmp     cs:?s_computername@User@@0PAGA, bx; ushort near * User::s_computername
0x180019c3e  jnz     loc_180019CD5
0x180019c44  lea     rdx, [rbp+nSize]; nSize
0x180019c48  mov     [rbp+nSize], 10h
0x180019c4f  lea     rcx, ?s_computername@User@@0PAGA; lpBuffer
0x180019c56  call    cs:__imp_GetComputerNameW
0x180019c5c  test    eax, eax
0x180019c5e  jnz     short loc_180019CD5
0x180019c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c67  lea     rax, WPP_GLOBAL_Control
0x180019c6e  cmp     rcx, rax
0x180019c71  jz      short loc_180019C92
0x180019c73  test    byte ptr [rcx+1Ch], 80h
0x180019c77  jz      short loc_180019C92
0x180019c79  cmp     byte ptr [rcx+19h], 2
0x180019c7d  jb      short loc_180019C92
0x180019c7f  mov     rcx, [rcx+10h]
0x180019c83  lea     edx, [rbx+1Ch]
0x180019c86  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x180019c8d  call    WPP_SF_
0x180019c92  call    cs:__imp_GetLastError
0x180019c98  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180019c9f  mov     [rbp+var_38], bl
0x180019ca2  mov     [rbp+pExceptionObject], rcx
0x180019ca6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180019cad  lea     rcx, byte_1800505F8
0x180019cb4  mov     [rbp+var_28], rbx
0x180019cb8  mov     [rbp+var_30], rcx
0x180019cbc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019cc0  mov     [rbp+var_20], rbx
0x180019cc4  mov     [rbp+var_18], eax
0x180019cc7  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180019ccf  call    _CxxThrowException_0
0x180019cd5  mov     rbx, [rsp+60h+arg_8]
0x180019cda  lea     rax, ?s_computername@User@@0PAGA; ushort near * User::s_computername
0x180019ce1  add     rsp, 60h
0x180019ce5  pop     rbp
0x180019ce6  retn
```
