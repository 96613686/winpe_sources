# DavImpersonateAndGetUserId

- ea: `0x180005844`
- end: `0x180005913`
- name: `DavImpersonateAndGetUserId`
- size: `207`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer, LPDWORD pcbBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180006d20`

## callees

- `0x180005844`
- `0x18000591c`
- `0x180006618`
- `0x18000b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058a3`
- `ADVAPI32!GetUserNameW` at `0x180005898`
- `ADVAPI32!GetUserNameW` at `0x180005898`

## pseudocode

```c
__int64 __fastcall DavImpersonateAndGetUserId(LPWSTR lpBuffer, LPDWORD pcbBuffer)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  void *v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD LastError; // eax

  v4 = DavImpersonateClient();
  v8 = v4;
  if ( v4 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 204;
LABEL_14:
      WPP_SF_d(v9[2], v10, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v4);
    }
  }
  else
  {
    if ( lpBuffer )
    {
      if ( !GetUserNameW(lpBuffer, pcbBuffer) )
      {
        LastError = GetLastError();
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
      }
    }
    v4 = DavRevertToSelf(v6, v5, v7);
    v8 = v4;
    if ( v4 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 206;
        goto LABEL_14;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180005844  push    rbx
0x180005846  push    rbp
0x180005847  push    rsi
0x180005848  push    rdi
0x180005849  sub     rsp, 28h
0x18000584d  mov     rbp, rdx
0x180005850  mov     rsi, rcx
0x180005853  call    DavImpersonateClient
0x180005858  mov     ebx, eax
0x18000585a  test    eax, eax
0x18000585c  jz      short loc_180005886
0x18000585e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005865  lea     rdi, WPP_GLOBAL_Control
0x18000586c  cmp     rcx, rdi
0x18000586f  jz      loc_180005908
0x180005875  test    byte ptr [rcx+1Ch], 1
0x180005879  jz      loc_180005908
0x18000587f  mov     edx, 0CCh
0x180005884  jmp     short loc_1800058F5
0x180005886  lea     rdi, WPP_GLOBAL_Control
0x18000588d  test    rsi, rsi
0x180005890  jz      short loc_1800058D3
0x180005892  mov     rdx, rbp; pcbBuffer
0x180005895  mov     rcx, rsi; lpBuffer
0x180005898  call    cs:__imp_GetUserNameW
0x18000589e  cmp     eax, 1
0x1800058a1  jz      short loc_1800058D3
0x1800058a3  call    cs:__imp_GetLastError
0x1800058a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058b0  cmp     rcx, rdi
0x1800058b3  jz      short loc_1800058D3
0x1800058b5  test    byte ptr [rcx+1Ch], 1
0x1800058b9  jz      short loc_1800058D3
0x1800058bb  mov     rcx, [rcx+10h]
0x1800058bf  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800058c6  mov     edx, 0CDh
0x1800058cb  mov     r9d, eax
0x1800058ce  call    WPP_SF_d
0x1800058d3  call    DavRevertToSelf
0x1800058d8  mov     ebx, eax
0x1800058da  test    eax, eax
0x1800058dc  jz      short loc_180005908
0x1800058de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058e5  cmp     rcx, rdi
0x1800058e8  jz      short loc_180005908
0x1800058ea  test    byte ptr [rcx+1Ch], 1
0x1800058ee  jz      short loc_180005908
0x1800058f0  mov     edx, 0CEh
0x1800058f5  mov     rcx, [rcx+10h]
0x1800058f9  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180005900  mov     r9d, eax
0x180005903  call    WPP_SF_d
0x180005908  mov     eax, ebx
0x18000590a  add     rsp, 28h
0x18000590e  pop     rdi
0x18000590f  pop     rsi
0x180005910  pop     rbp
0x180005911  pop     rbx
0x180005912  retn
```
