# WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::CImpersonationToken(void *)

- ea: `0x18005e60c`
- end: `0x18005e6c3`
- name: `??0CImpersonationToken@CThreadTokenImpersonationProvider@WFDSConMgr@@QEAA@PEAX@Z`
- size: `183`
- prototype: `WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken *__fastcall(WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken *this, HANDLE Token)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18005eb10`

## callees

- `0x180009b5c`
- `0x18005c888`
- `0x18005e60c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005e66c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005e66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e676`

## string_xrefs

- `0x18005e69f`: `onecoreuap\net\wlan\wfdsconmgr\util\src\impersonationprovider.cpp`
- `0x18005e68d`: `SetThreadToken failed, could not impersonate`
- `0x18005e6a6`: `WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::CImpersonationToken`

## pseudocode

```c
WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken *__fastcall WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::CImpersonationToken(
        WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken *this,
        HANDLE Token)
{
  char LastError; // al

  *(_QWORD *)this = &WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_7d681293e58d38db1ed4308781b49152_Traceguids, this, Token);
  }
  if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::CImpersonationToken",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\impersonationprovider.cpp",
      88,
      L"SetThreadToken failed, could not impersonate",
      this);
  }
  return this;
}

```

## disassembly

```asm
0x18005e60c  mov     [rsp+arg_8], rbx
0x18005e611  mov     [rsp+arg_0], rcx
0x18005e616  push    rdi
0x18005e617  sub     rsp, 30h
0x18005e61b  mov     rdi, rdx
0x18005e61e  mov     rbx, rcx
0x18005e621  lea     rax, ??_7CImpersonationToken@CThreadTokenImpersonationProvider@WFDSConMgr@@6B@; const WFDSConMgr::CThreadTokenImpersonationProvider::CImpersonationToken::`vftable'
0x18005e628  mov     [rcx], rax
0x18005e62b  lea     rax, WPP_GLOBAL_Control
0x18005e632  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e639  cmp     rcx, rax
0x18005e63c  jz      short loc_18005E667
0x18005e63e  cmp     byte ptr [rcx+19h], 4
0x18005e642  jb      short loc_18005E667
0x18005e644  test    byte ptr [rcx+1Ch], 1
0x18005e648  jz      short loc_18005E667
0x18005e64a  mov     edx, 0Eh
0x18005e64f  mov     [rsp+38h+var_18], rdi
0x18005e654  mov     r9, rbx
0x18005e657  lea     r8, WPP_7d681293e58d38db1ed4308781b49152_Traceguids
0x18005e65e  mov     rcx, [rcx+10h]
0x18005e662  call    WPP_SF_qq
0x18005e667  mov     rdx, rdi; Token
0x18005e66a  xor     ecx, ecx; Thread
0x18005e66c  call    cs:__imp_SetThreadToken
0x18005e672  test    eax, eax
0x18005e674  jnz     short loc_18005E6B5
0x18005e676  call    cs:__imp_GetLastError
0x18005e67c  test    eax, eax
0x18005e67e  jle     short loc_18005E688
0x18005e680  movzx   eax, ax
0x18005e683  or      eax, 80070000h
0x18005e688  mov     [rsp+38h+var_10], rbx; void *
0x18005e68d  lea     rcx, aSetthreadtoken; "SetThreadToken failed, could not impers"...
0x18005e694  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005e699  mov     r9d, 58h ; 'X'; char
0x18005e69f  lea     r8, aOnecoreuapNetW_15; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005e6a6  lea     rdx, aWfdsconmgrCthr_0; "WFDSConMgr::CThreadTokenImpersonationPr"...
0x18005e6ad  mov     ecx, eax; char
0x18005e6af  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005e6b5  mov     rax, rbx
0x18005e6b8  mov     rbx, [rsp+38h+arg_8]
0x18005e6bd  add     rsp, 30h
0x18005e6c1  pop     rdi
0x18005e6c2  retn
```
