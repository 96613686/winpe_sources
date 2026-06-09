# User::GetComputerNameW(void)

- ea: `0x18001aeec`
- end: `0x18001afb8`
- name: `?GetComputerNameW@User@@CAPEBGXZ`
- size: `204`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c3ac`

## callees

- `0x180008c4c`
- `0x180010570`
- `0x18001aeec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af5c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001af1a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001af1a`

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
      v3 = byte_180052608;
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
0x18001aeec  mov     [rsp-8+arg_8], rbx
0x18001aef1  push    rbp
0x18001aef2  mov     rbp, rsp
0x18001aef5  sub     rsp, 60h
0x18001aef9  xor     ebx, ebx
0x18001aefb  cmp     cs:?s_computername@User@@0PAGA, bx; ushort near * User::s_computername
0x18001af02  jnz     loc_18001AFA5
0x18001af08  lea     rdx, [rbp+nSize]; nSize
0x18001af0c  mov     [rbp+nSize], 10h
0x18001af13  lea     rcx, ?s_computername@User@@0PAGA; lpBuffer
0x18001af1a  call    cs:__imp_GetComputerNameW
0x18001af21  nop     dword ptr [rax+rax+00h]
0x18001af26  test    eax, eax
0x18001af28  jnz     short loc_18001AFA5
0x18001af2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af31  lea     rax, WPP_GLOBAL_Control
0x18001af38  cmp     rcx, rax
0x18001af3b  jz      short loc_18001AF5C
0x18001af3d  test    byte ptr [rcx+1Ch], 80h
0x18001af41  jz      short loc_18001AF5C
0x18001af43  cmp     byte ptr [rcx+19h], 2
0x18001af47  jb      short loc_18001AF5C
0x18001af49  mov     rcx, [rcx+10h]
0x18001af4d  lea     edx, [rbx+1Ch]
0x18001af50  lea     r8, WPP_3208b4761a6e316a80125ecbf0290fa4_Traceguids
0x18001af57  call    WPP_SF_
0x18001af5c  call    cs:__imp_GetLastError
0x18001af63  nop     dword ptr [rax+rax+00h]
0x18001af68  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001af6f  mov     [rbp+var_38], bl
0x18001af72  mov     [rbp+pExceptionObject], rcx
0x18001af76  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001af7d  lea     rcx, byte_180052608
0x18001af84  mov     [rbp+var_28], rbx
0x18001af88  mov     [rbp+var_30], rcx
0x18001af8c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001af90  mov     [rbp+var_20], rbx
0x18001af94  mov     [rbp+var_18], eax
0x18001af97  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001af9f  call    _CxxThrowException_0
0x18001afa5  mov     rbx, [rsp+60h+arg_8]
0x18001afaa  lea     rax, ?s_computername@User@@0PAGA; ushort near * User::s_computername
0x18001afb1  add     rsp, 60h
0x18001afb5  pop     rbp
0x18001afb6  retn
```
