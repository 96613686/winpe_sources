# RemoveCriticalPrivileges

- ea: `0x140041c5c`
- end: `0x140041dd5`
- name: `RemoveCriticalPrivileges`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400877f0`

## callees

- `0x140041c5c`
- `0x140053720`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x140041d8a`
- `ntdll!NtAdjustPrivilegesToken` at `0x140041d8a`
- `ntdll!NtDuplicateToken` at `0x140041cc6`
- `ntdll!NtDuplicateToken` at `0x140041cc6`
- `ntdll!NtOpenProcessToken` at `0x140041c96`
- `ntdll!NtOpenProcessToken` at `0x140041c96`
- `ntdll!NtClose` at `0x140041daa`
- `ntdll!NtClose` at `0x140041db5`
- `ntdll!NtClose` at `0x140041daa`
- `ntdll!NtClose` at `0x140041db5`

## pseudocode

```c
__int64 __fastcall RemoveCriticalPrivileges(HANDLE *a1)
{
  NTSTATUS v2; // ebx
  NTSTATUS v3; // eax
  HANDLE Handle; // [rsp+30h] [rbp-89h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-81h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-79h] BYREF
  __int64 v8; // [rsp+50h] [rbp-69h]
  int v9; // [rsp+58h] [rbp-61h]
  __int64 v10; // [rsp+5Ch] [rbp-5Dh]
  int v11; // [rsp+64h] [rbp-55h]
  __int64 v12; // [rsp+68h] [rbp-51h]
  int v13; // [rsp+70h] [rbp-49h]
  __int64 v14; // [rsp+74h] [rbp-45h]
  int v15; // [rsp+7Ch] [rbp-3Dh]
  __int64 v16; // [rsp+80h] [rbp-39h]
  int v17; // [rsp+88h] [rbp-31h]
  __int64 v18; // [rsp+8Ch] [rbp-2Dh]
  int v19; // [rsp+94h] [rbp-25h]
  __int64 v20; // [rsp+98h] [rbp-21h]
  int v21; // [rsp+A0h] [rbp-19h]
  __int64 v22; // [rsp+A4h] [rbp-15h]
  int v23; // [rsp+ACh] [rbp-Dh]
  __int64 v24; // [rsp+B0h] [rbp-9h]
  int v25; // [rsp+B8h] [rbp-1h]
  __int64 v26; // [rsp+BCh] [rbp+3h]
  int v27; // [rsp+C4h] [rbp+Bh]
  __int64 v28; // [rsp+C8h] [rbp+Fh]
  int v29; // [rsp+D0h] [rbp+17h]
  __int64 v30; // [rsp+D4h] [rbp+1Bh]
  int v31; // [rsp+DCh] [rbp+23h]

  TokenHandle = 0;
  Handle = 0;
  v2 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAu, &TokenHandle);
  if ( v2 >= 0 )
  {
    v2 = NtDuplicateToken(TokenHandle, 0x2Fu, 0, 0, TokenPrimary, &Handle);
    if ( v2 >= 0 )
    {
      NewState.Privileges[0].Attributes = 4;
      v9 = 4;
      v11 = 4;
      v13 = 4;
      v15 = 4;
      v17 = 4;
      v19 = 4;
      v21 = 4;
      v23 = 4;
      v25 = 4;
      v27 = 4;
      v29 = 4;
      v31 = 4;
      NewState.PrivilegeCount = 13;
      NewState.Privileges[0].Luid = (LUID)28LL;
      v8 = 7;
      v10 = 10;
      v12 = 17;
      v14 = 18;
      v16 = 8;
      v18 = 9;
      v20 = 25;
      v22 = 3;
      v24 = 5;
      v26 = 31;
      v28 = 32;
      v30 = 36;
      v3 = NtAdjustPrivilegesToken(Handle, 0, &NewState, 0xA0u, 0, 0);
      if ( v3 < 0 )
      {
        v2 = v3;
        NtClose(Handle);
      }
      else
      {
        *a1 = Handle;
        v2 = 0;
        if ( v3 != 262 )
          v2 = v3;
      }
    }
    NtClose(TokenHandle);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140041c5c  push    rbp
0x140041c5e  push    rbx
0x140041c5f  push    rsi
0x140041c60  push    rdi
0x140041c61  lea     rbp, [rsp-3Fh]
0x140041c66  sub     rsp, 0F8h
0x140041c6d  mov     rax, cs:__security_cookie
0x140041c74  xor     rax, rsp
0x140041c77  mov     [rbp+57h+var_30], rax
0x140041c7b  xor     esi, esi
0x140041c7d  lea     r8, [rsp+110h+TokenHandle]; TokenHandle
0x140041c82  mov     rdi, rcx
0x140041c85  mov     [rsp+110h+TokenHandle], rsi
0x140041c8a  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140041c8e  mov     [rsp+110h+Handle], rsi
0x140041c93  lea     edx, [rsi+0Ah]; DesiredAccess
0x140041c96  call    cs:__imp_NtOpenProcessToken
0x140041c9c  mov     ebx, eax
0x140041c9e  test    eax, eax
0x140041ca0  js      loc_140041DBB
0x140041ca6  mov     rcx, [rsp+110h+TokenHandle]; ExistingTokenHandle
0x140041cab  lea     rax, [rsp+110h+Handle]
0x140041cb0  mov     [rsp+110h+NewTokenHandle], rax; NewTokenHandle
0x140041cb5  lea     edx, [rsi+2Fh]; DesiredAccess
0x140041cb8  xor     r9d, r9d; EffectiveOnly
0x140041cbb  mov     [rsp+110h+TokenType], 1; TokenType
0x140041cc3  xor     r8d, r8d; ObjectAttributes
0x140041cc6  call    cs:__imp_NtDuplicateToken
0x140041ccc  mov     ebx, eax
0x140041cce  test    eax, eax
0x140041cd0  js      loc_140041DB0
0x140041cd6  mov     rcx, [rsp+110h+Handle]; TokenHandle
0x140041cdb  lea     eax, [rsi+4]
0x140041cde  mov     [rsp+110h+NewTokenHandle], rsi; ReturnLength
0x140041ce3  lea     r8, [rbp+57h+NewState]; NewState
0x140041ce7  mov     r9d, 0A0h; BufferLength
0x140041ced  mov     [rbp+57h+NewState.Privileges.Attributes], eax
0x140041cf0  xor     edx, edx; DisableAllPrivileges
0x140041cf2  mov     [rbp+57h+var_B8], eax
0x140041cf5  mov     [rbp+57h+var_AC], eax
0x140041cf8  mov     [rbp+57h+var_A0], eax
0x140041cfb  mov     [rbp+57h+var_94], eax
0x140041cfe  mov     [rbp+57h+var_88], eax
0x140041d01  mov     [rbp+57h+var_7C], eax
0x140041d04  mov     [rbp+57h+var_70], eax
0x140041d07  mov     [rbp+57h+var_64], eax
0x140041d0a  mov     [rbp+57h+var_58], eax
0x140041d0d  mov     [rbp+57h+var_4C], eax
0x140041d10  mov     [rbp+57h+var_40], eax
0x140041d13  mov     [rbp+57h+var_34], eax
0x140041d16  mov     [rbp+57h+NewState.PrivilegeCount], 0Dh
0x140041d1d  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], 1Ch
0x140041d25  mov     [rbp+57h+var_C0], 7
0x140041d2d  mov     [rbp+57h+var_B4], 0Ah
0x140041d35  mov     [rbp+57h+var_A8], 11h
0x140041d3d  mov     [rbp+57h+var_9C], 12h
0x140041d45  mov     [rbp+57h+var_90], 8
0x140041d4d  mov     [rbp+57h+var_84], 9
0x140041d55  mov     [rbp+57h+var_78], 19h
0x140041d5d  mov     [rbp+57h+var_6C], 3
0x140041d65  mov     [rbp+57h+var_60], 5
0x140041d6d  mov     [rbp+57h+var_54], 1Fh
0x140041d75  mov     [rbp+57h+var_48], 20h ; ' '
0x140041d7d  mov     [rbp+57h+var_3C], 24h ; '$'
0x140041d85  mov     qword ptr [rsp+110h+TokenType], rsi; PreviousState
0x140041d8a  call    cs:__imp_NtAdjustPrivilegesToken
0x140041d90  mov     rcx, [rsp+110h+Handle]; Handle
0x140041d95  test    eax, eax
0x140041d97  js      short loc_140041DA8
0x140041d99  cmp     eax, 106h
0x140041d9e  mov     [rdi], rcx
0x140041da1  mov     ebx, esi
0x140041da3  cmovnz  ebx, eax
0x140041da6  jmp     short loc_140041DB0
0x140041da8  mov     ebx, eax
0x140041daa  call    cs:__imp_NtClose
0x140041db0  mov     rcx, [rsp+110h+TokenHandle]; Handle
0x140041db5  call    cs:__imp_NtClose
0x140041dbb  mov     eax, ebx
0x140041dbd  mov     rcx, [rbp+57h+var_30]
0x140041dc1  xor     rcx, rsp; StackCookie
0x140041dc4  call    __security_check_cookie
0x140041dc9  add     rsp, 0F8h
0x140041dd0  pop     rdi
0x140041dd1  pop     rsi
0x140041dd2  pop     rbx
0x140041dd3  pop     rbp
0x140041dd4  retn
```
