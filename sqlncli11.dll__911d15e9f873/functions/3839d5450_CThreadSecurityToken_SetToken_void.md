# CThreadSecurityToken::SetToken(void)

- ea: `0x3839d5450`
- end: `0x3839d5677`
- name: `?SetToken@CThreadSecurityToken@@QEBAJXZ`
- size: `551`
- prototype: `__int64 __fastcall(CThreadSecurityToken *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3839d42a0`
- `0x383ad1630`

## callees

- `0x38391ac10`
- `0x38391aed0`
- `0x3839d5450`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3839d5516`
- `KERNEL32!GetLastError` at `0x3839d5579`
- `KERNEL32!GetLastError` at `0x3839d5516`
- `KERNEL32!GetLastError` at `0x3839d5579`
- `ADVAPI32!RevertToSelf` at `0x3839d54b3`
- `ADVAPI32!RevertToSelf` at `0x3839d54b3`
- `ADVAPI32!SetThreadToken` at `0x3839d556f`
- `ADVAPI32!SetThreadToken` at `0x3839d556f`

## pseudocode

```c
__int64 __fastcall CThreadSecurityToken::SetToken(HANDLE *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  signed int v4; // eax

  v1 = 0;
  if ( *this == (HANDLE)-1LL )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`62'::_bidPtrSA_030_3265[0] && bidID != -1 )
      off_383B15040();
    return (unsigned int)-2147467259;
  }
  else if ( *((_BYTE *)this + 8) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`13'::_bidPtrSA_030_3238[0] && bidID != -1 )
      off_383B15040();
    if ( RevertToSelf() )
    {
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`23'::_bidPtrSA_030_3242[0] && bidID != -1 )
      {
LABEL_11:
        off_383B15040();
        return 0;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      else
        v1 = LastError;
      if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_3247[0] )
      {
        bidTraceW(
          `CThreadSecurityToken::SetToken'::`32'::_bidSrcFileA[0],
          3324928,
          `CThreadSecurityToken::SetToken'::`32'::_bidPtrSA_030_3247[0],
          v1);
        return v1;
      }
    }
  }
  else if ( SetThreadToken(0, *this) )
  {
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`53'::_bidPtrSA_030_3259[0] && bidID != -1 )
      goto LABEL_11;
  }
  else
  {
    v4 = GetLastError();
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    else
      v1 = v4;
    if ( (bidGblFlags & 2) != 0 && `CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_3255[0] )
    {
      bidTraceW(
        `CThreadSecurityToken::SetToken'::`44'::_bidSrcFileA[0],
        3333120,
        `CThreadSecurityToken::SetToken'::`44'::_bidPtrSA_030_3255[0],
        v1);
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x3839d5450  push    rbx
0x3839d5452  sub     rsp, 30h
0x3839d5456  mov     rdx, [rcx]; Token
0x3839d5459  xor     ebx, ebx
0x3839d545b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x3839d545f  jz      loc_3839D5625
0x3839d5465  cmp     [rcx+8], bl
0x3839d5468  jz      loc_3839D556D
0x3839d546e  test    byte ptr cs:_bidGblFlags, 2
0x3839d5475  jz      short loc_3839D54B3
0x3839d5477  mov     rax, cs:?_bidPtrSA_030_3238@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_3238
0x3839d547e  test    rax, rax
0x3839d5481  jz      short loc_3839D54B3
0x3839d5483  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839d548b  jz      short loc_3839D54B3
0x3839d548d  mov     r9, cs:?_bidPtrSA_030_3238@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidPtrSA_030_3238
0x3839d5494  mov     rdx, cs:?_bidSrcFileA@?N@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`13'::_bidSrcFileA
0x3839d549b  mov     rcx, cs:_bidID
0x3839d54a2  mov     r8d, 329800h
0x3839d54a8  mov     [rsp+38h+var_18], rbx
0x3839d54ad  call    cs:off_383B15040
0x3839d54b3  call    cs:__imp_RevertToSelf
0x3839d54b9  test    eax, eax
0x3839d54bb  jz      short loc_3839D5516
0x3839d54bd  test    byte ptr cs:_bidGblFlags, 2
0x3839d54c4  jz      loc_3839D566F
0x3839d54ca  mov     rax, cs:?_bidPtrSA_030_3242@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_3242
0x3839d54d1  test    rax, rax
0x3839d54d4  jz      loc_3839D566F
0x3839d54da  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839d54e2  jz      loc_3839D566F
0x3839d54e8  mov     r9, cs:?_bidPtrSA_030_3242@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidPtrSA_030_3242
0x3839d54ef  mov     rdx, cs:?_bidSrcFileA@?BH@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`23'::_bidSrcFileA
0x3839d54f6  mov     rcx, cs:_bidID
0x3839d54fd  mov     r8d, 32A800h
0x3839d5503  mov     [rsp+38h+var_18], rbx
0x3839d5508  call    cs:off_383B15040
0x3839d550e  mov     eax, ebx
0x3839d5510  add     rsp, 30h
0x3839d5514  pop     rbx
0x3839d5515  retn
0x3839d5516  call    cs:__imp_GetLastError
0x3839d551c  test    eax, eax
0x3839d551e  jg      short loc_3839D5524
0x3839d5520  mov     ebx, eax
0x3839d5522  jmp     short loc_3839D552D
0x3839d5524  movzx   ebx, ax
0x3839d5527  or      ebx, 80070000h
0x3839d552d  test    byte ptr cs:_bidGblFlags, 2
0x3839d5534  jz      loc_3839D566F
0x3839d553a  mov     rax, cs:?_bidPtrSA_030_3247@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_3247
0x3839d5541  test    rax, rax
0x3839d5544  jz      loc_3839D566F
0x3839d554a  mov     r8, cs:?_bidPtrSA_030_3247@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidPtrSA_030_3247
0x3839d5551  mov     rcx, cs:?_bidSrcFileA@?CA@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`32'::_bidSrcFileA
0x3839d5558  mov     r9d, ebx
0x3839d555b  mov     edx, 32BC00h
0x3839d5560  call    _bidTraceW
0x3839d5565  mov     eax, ebx
0x3839d5567  add     rsp, 30h
0x3839d556b  pop     rbx
0x3839d556c  retn
0x3839d556d  xor     ecx, ecx; Thread
0x3839d556f  call    cs:__imp_SetThreadToken
0x3839d5575  test    eax, eax
0x3839d5577  jnz     short loc_3839D55D0
0x3839d5579  call    cs:__imp_GetLastError
0x3839d557f  test    eax, eax
0x3839d5581  jg      short loc_3839D5587
0x3839d5583  mov     ebx, eax
0x3839d5585  jmp     short loc_3839D5590
0x3839d5587  movzx   ebx, ax
0x3839d558a  or      ebx, 80070000h
0x3839d5590  test    byte ptr cs:_bidGblFlags, 2
0x3839d5597  jz      loc_3839D566F
0x3839d559d  mov     rax, cs:?_bidPtrSA_030_3255@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_3255
0x3839d55a4  test    rax, rax
0x3839d55a7  jz      loc_3839D566F
0x3839d55ad  mov     r8, cs:?_bidPtrSA_030_3255@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidPtrSA_030_3255
0x3839d55b4  mov     rcx, cs:?_bidSrcFileA@?CM@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`44'::_bidSrcFileA
0x3839d55bb  mov     r9d, ebx
0x3839d55be  mov     edx, 32DC00h
0x3839d55c3  call    _bidTraceW
0x3839d55c8  mov     eax, ebx
0x3839d55ca  add     rsp, 30h
0x3839d55ce  pop     rbx
0x3839d55cf  retn
0x3839d55d0  test    byte ptr cs:_bidGblFlags, 2
0x3839d55d7  jz      loc_3839D566F
0x3839d55dd  mov     rax, cs:?_bidPtrSA_030_3259@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_3259
0x3839d55e4  test    rax, rax
0x3839d55e7  jz      loc_3839D566F
0x3839d55ed  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839d55f5  jz      short loc_3839D566F
0x3839d55f7  mov     r9, cs:?_bidPtrSA_030_3259@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidPtrSA_030_3259
0x3839d55fe  mov     rdx, cs:?_bidSrcFileA@?DF@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`53'::_bidSrcFileA
0x3839d5605  mov     rcx, cs:_bidID
0x3839d560c  mov     r8d, 32EC00h
0x3839d5612  mov     [rsp+38h+var_18], rbx
0x3839d5617  call    cs:off_383B15040
0x3839d561d  mov     eax, ebx
0x3839d561f  add     rsp, 30h
0x3839d5623  pop     rbx
0x3839d5624  retn
0x3839d5625  test    byte ptr cs:_bidGblFlags, 2
0x3839d562c  jz      short loc_3839D566A
0x3839d562e  mov     rax, cs:?_bidPtrSA_030_3265@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_3265
0x3839d5635  test    rax, rax
0x3839d5638  jz      short loc_3839D566A
0x3839d563a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x3839d5642  jz      short loc_3839D566A
0x3839d5644  mov     r9, cs:?_bidPtrSA_030_3265@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBGEB; ushort const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidPtrSA_030_3265
0x3839d564b  mov     rdx, cs:?_bidSrcFileA@?DO@??SetToken@CThreadSecurityToken@@QEBAJXZ@4REBDEB; char const * const `CThreadSecurityToken::SetToken(void)'::`62'::_bidSrcFileA
0x3839d5652  mov     rcx, cs:_bidID
0x3839d5659  mov     r8d, 330400h
0x3839d565f  mov     [rsp+38h+var_18], rbx
0x3839d5664  call    cs:off_383B15040
0x3839d566a  mov     ebx, 80004005h
0x3839d566f  mov     eax, ebx
0x3839d5671  add     rsp, 30h
0x3839d5675  pop     rbx
0x3839d5676  retn
```
