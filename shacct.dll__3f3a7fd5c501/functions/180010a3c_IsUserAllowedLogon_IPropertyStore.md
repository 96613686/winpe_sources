# IsUserAllowedLogon(IPropertyStore *)

- ea: `0x180010a3c`
- end: `0x180010b81`
- name: `?IsUserAllowedLogon@@YA_NPEAUIPropertyStore@@@Z`
- size: `325`
- prototype: `bool __fastcall(struct IPropertyStore *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003e20`
- `0x1800063b0`
- `0x180007070`
- `0x18000b410`

## callees

- `0x18000a3c0`
- `0x18000bb20`
- `0x180010a3c`
- `0x180016880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010b0a`
- `samcli!NetUserGetInfo` at `0x180010ae3`
- `samcli!NetUserGetInfo` at `0x180010ae3`
- `netutils!NetApiBufferFree` at `0x180010b00`
- `netutils!NetApiBufferFree` at `0x180010b00`

## pseudocode

```c
char __fastcall IsUserAllowedLogon(struct IPropertyStore *a1)
{
  char v1; // bl
  int UInt32; // eax
  int v4; // r14d
  int v5; // edi
  int v6; // ecx
  int Bool; // eax
  LPCWSTR username; // [rsp+58h] [rbp+38h] BYREF
  int v10; // [rsp+60h] [rbp+40h] BYREF
  LPBYTE bufptr; // [rsp+68h] [rbp+48h] BYREF

  v1 = 0;
  LODWORD(username) = 0;
  IPropertyStore_GetBool(a1, &PKEY_SAM_DontShowInLogonUI, &username);
  if ( !(_DWORD)username )
  {
    v10 = 0;
    UInt32 = IPropertyStore_GetUInt32(a1, &PKEY_SAM_ResidualID, &v10);
    LODWORD(username) = 0;
    v4 = UInt32;
    if ( (int)IPropertyStore_GetBool(a1, &PKEY_SAM_DenyInteractiveLogin, &username) >= 0 )
    {
      v5 = (int)username;
    }
    else
    {
      v5 = 1;
      if ( v4 < 0 )
        return v1;
      username = 0;
      if ( (int)IPropertyStore_GetString(a1, &PKEY_SAM_Name, &username) < 0 )
        return v1;
      bufptr = 0;
      if ( !NetUserGetInfo(0, username, 1u, &bufptr) )
      {
        v5 = (*((_DWORD *)bufptr + 10) | 2) == 2;
        NetApiBufferFree(bufptr);
      }
      CoTaskMemFree((LPVOID)username);
    }
    if ( !v5 && v4 >= 0 )
    {
      LODWORD(username) = 0;
      if ( (int)IPropertyStore_GetUInt32(a1, &PKEY_SAM_UserAccountControl, &username) >= 0 )
      {
        v6 = (unsigned __int8)username & 1;
        LODWORD(bufptr) = v6;
        if ( ((unsigned __int8)username & 1) != 0 && v10 == 500 )
        {
          Bool = IPropertyStore_GetBool(a1, &PKEY_SAM_AccountIsDisabledForLogonUI, &bufptr);
          v6 = (int)bufptr;
          if ( Bool < 0 )
            v6 = 1;
        }
        if ( !v6 )
          return 1;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180010a3c  mov     [rsp-28h+arg_0], rbx
0x180010a41  push    rbp
0x180010a42  push    rsi
0x180010a43  push    rdi
0x180010a44  push    r12
0x180010a46  push    r14
0x180010a48  mov     rbp, rsp
0x180010a4b  sub     rsp, 20h
0x180010a4f  xor     ebx, ebx
0x180010a51  lea     r8, [rbp+username]
0x180010a55  lea     rdx, PKEY_SAM_DontShowInLogonUI
0x180010a5c  mov     dword ptr [rbp+username], ebx
0x180010a5f  mov     rsi, rcx
0x180010a62  call    IPropertyStore_GetBool
0x180010a67  cmp     dword ptr [rbp+username], ebx
0x180010a6a  jnz     loc_180010B6E
0x180010a70  lea     r8, [rbp+arg_10]
0x180010a74  mov     [rbp+arg_10], ebx
0x180010a77  lea     rdx, PKEY_SAM_ResidualID
0x180010a7e  mov     rcx, rsi
0x180010a81  call    IPropertyStore_GetUInt32
0x180010a86  lea     r8, [rbp+username]
0x180010a8a  mov     dword ptr [rbp+username], ebx
0x180010a8d  lea     rdx, PKEY_SAM_DenyInteractiveLogin
0x180010a94  mov     rcx, rsi
0x180010a97  mov     r14d, eax
0x180010a9a  call    IPropertyStore_GetBool
0x180010a9f  lea     r12d, [rbx+1]
0x180010aa3  test    eax, eax
0x180010aa5  jns     short loc_180010B12
0x180010aa7  mov     edi, r12d
0x180010aaa  test    r14d, r14d
0x180010aad  js      loc_180010B6E
0x180010ab3  lea     r8, [rbp+username]
0x180010ab7  mov     [rbp+username], rbx
0x180010abb  lea     rdx, PKEY_SAM_Name
0x180010ac2  mov     rcx, rsi
0x180010ac5  call    IPropertyStore_GetString
0x180010aca  test    eax, eax
0x180010acc  js      loc_180010B6E
0x180010ad2  mov     rdx, [rbp+username]; username
0x180010ad6  lea     r9, [rbp+bufptr]; bufptr
0x180010ada  mov     r8d, r12d; level
0x180010add  mov     [rbp+bufptr], rbx
0x180010ae1  xor     ecx, ecx; servername
0x180010ae3  call    cs:__imp_NetUserGetInfo
0x180010ae9  test    eax, eax
0x180010aeb  jnz     short loc_180010B06
0x180010aed  mov     rcx, [rbp+bufptr]; Buffer
0x180010af1  xor     edi, edi
0x180010af3  mov     eax, [rcx+28h]
0x180010af6  or      eax, 2
0x180010af9  cmp     eax, 2
0x180010afc  setz    dil
0x180010b00  call    cs:__imp_NetApiBufferFree
0x180010b06  mov     rcx, [rbp+username]; pv
0x180010b0a  call    cs:__imp_CoTaskMemFree
0x180010b10  jmp     short loc_180010B15
0x180010b12  mov     edi, dword ptr [rbp+username]
0x180010b15  test    edi, edi
0x180010b17  jnz     short loc_180010B6E
0x180010b19  test    r14d, r14d
0x180010b1c  js      short loc_180010B6E
0x180010b1e  lea     r8, [rbp+username]
0x180010b22  mov     dword ptr [rbp+username], ebx
0x180010b25  lea     rdx, PKEY_SAM_UserAccountControl
0x180010b2c  mov     rcx, rsi
0x180010b2f  call    IPropertyStore_GetUInt32
0x180010b34  test    eax, eax
0x180010b36  js      short loc_180010B6E
0x180010b38  mov     ecx, dword ptr [rbp+username]
0x180010b3b  and     ecx, r12d
0x180010b3e  mov     dword ptr [rbp+bufptr], ecx
0x180010b41  jz      short loc_180010B68
0x180010b43  cmp     [rbp+arg_10], 1F4h
0x180010b4a  jnz     short loc_180010B68
0x180010b4c  lea     r8, [rbp+bufptr]
0x180010b50  mov     rcx, rsi
0x180010b53  lea     rdx, PKEY_SAM_AccountIsDisabledForLogonUI
0x180010b5a  call    IPropertyStore_GetBool
0x180010b5f  mov     ecx, dword ptr [rbp+bufptr]
0x180010b62  test    eax, eax
0x180010b64  cmovs   ecx, r12d
0x180010b68  test    ecx, ecx
0x180010b6a  cmovz   ebx, r12d
0x180010b6e  mov     al, bl
0x180010b70  mov     rbx, [rsp+20h+arg_0]
0x180010b75  add     rsp, 20h
0x180010b79  pop     r14
0x180010b7b  pop     r12
0x180010b7d  pop     rdi
0x180010b7e  pop     rsi
0x180010b7f  pop     rbp
0x180010b80  retn
```
