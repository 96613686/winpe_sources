# LaunchThirdPartyRemediationExe(ushort *,ushort const *)

- ea: `0x180009ac8`
- end: `0x180009cff`
- name: `?LaunchThirdPartyRemediationExe@@YAHPEAGPEBG@Z`
- size: `567`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180008ed0`

## callees

- `0x180008030`
- `0x180008058`
- `0x180008a38`
- `0x180008d98`
- `0x18000917c`
- `0x1800099e8`
- `0x180009ac8`
- `0x180009fd4`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c85`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009b5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009b5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009bd2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009bd2`

## pseudocode

```c
__int64 __fastcall LaunchThirdPartyRemediationExe(LPCWSTR lpSrc, const unsigned __int16 *a2)
{
  DWORD v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned __int8 v6; // bl
  _QWORD *v7; // rcx
  DWORD LastError; // eax
  char *FileW; // rdi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  const char *v13; // r9
  void *v15; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(Dst, 0, 0x208u);
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids,
      (_DWORD)lpSrc,
      (__int64)L"/disable");
  v3 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  v6 = 0;
  if ( !v3 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids, LastError);
LABEL_26:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  FileW = (char *)CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (int)CheckTrust(Dst, &v15) < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v11 = 16;
    }
    else
    {
      if ( LaunchProgramSwitchToDesktop(0, Dst, L"/disable", 1) )
      {
        v6 = 1;
LABEL_23:
        CloseHandle(FileW);
        v7 = WPP_GLOBAL_Control;
        goto LABEL_24;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v11 = 15;
    }
    WPP_SF_(v10[2], v11, &WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids);
    goto LABEL_23;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( FileW )
    goto LABEL_23;
LABEL_24:
  if ( v15 )
  {
    FreeWVTStateData(v15);
    goto LABEL_26;
  }
LABEL_27:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
  {
    v12 = v7[2];
    v13 = "true";
    if ( !v6 )
      v13 = "false";
    WPP_SF_s(v12, v4, v5, v13);
  }
  return v6;
}

```

## disassembly

```asm
0x180009ac8  mov     [rsp+arg_8], rbx
0x180009acd  mov     [rsp+arg_10], rbp
0x180009ad2  push    rdi
0x180009ad3  push    r14
0x180009ad5  push    r15
0x180009ad7  sub     rsp, 270h
0x180009ade  mov     rax, cs:__security_cookie
0x180009ae5  xor     rax, rsp
0x180009ae8  mov     [rsp+288h+var_28], rax
0x180009af0  mov     rbx, rcx
0x180009af3  xor     edx, edx; Val
0x180009af5  lea     rcx, [rsp+288h+Dst]; void *
0x180009afa  mov     r8d, 208h; Size
0x180009b00  call    memset_0
0x180009b05  mov     [rsp+288h+var_248], 0
0x180009b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b15  lea     rbp, WPP_GLOBAL_Control
0x180009b1c  lea     r15, aDisable; "/disable"
0x180009b23  lea     r14, WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids
0x180009b2a  cmp     rcx, rbp
0x180009b2d  jz      short loc_180009B4E
0x180009b2f  test    byte ptr [rcx+1Ch], 8
0x180009b33  jz      short loc_180009B4E
0x180009b35  mov     rcx, [rcx+10h]
0x180009b39  mov     edx, 0Dh
0x180009b3e  mov     r9, rbx
0x180009b41  mov     qword ptr [rsp+288h+dwCreationDisposition], r15
0x180009b46  mov     r8, r14
0x180009b49  call    WPP_SF_SS
0x180009b4e  mov     r8d, 104h; nSize
0x180009b54  lea     rdx, [rsp+288h+Dst]; lpDst
0x180009b59  mov     rcx, rbx; lpSrc
0x180009b5c  call    cs:__imp_ExpandEnvironmentStringsW
0x180009b62  xor     bl, bl
0x180009b64  test    eax, eax
0x180009b66  jnz     short loc_180009BA8
0x180009b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b6f  cmp     rcx, rbp
0x180009b72  jz      loc_180009CD3
0x180009b78  test    byte ptr [rcx+1Ch], 1
0x180009b7c  jz      loc_180009CAB
0x180009b82  call    cs:__imp_GetLastError
0x180009b88  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b8f  mov     edx, 0Eh
0x180009b94  mov     r9d, eax
0x180009b97  mov     r8, r14
0x180009b9a  mov     rcx, [rcx+10h]
0x180009b9e  call    WPP_SF_d
0x180009ba3  jmp     loc_180009CA4
0x180009ba8  xor     r9d, r9d; lpSecurityAttributes
0x180009bab  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x180009bb4  mov     [rsp+288h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180009bbc  lea     rcx, [rsp+288h+Dst]; lpFileName
0x180009bc1  mov     edx, 80000000h; dwDesiredAccess
0x180009bc6  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x180009bce  lea     r8d, [r9+1]; dwShareMode
0x180009bd2  call    cs:__imp_CreateFileW
0x180009bd8  mov     rdi, rax
0x180009bdb  lea     rcx, [rax-1]
0x180009bdf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180009be3  ja      short loc_180009C53
0x180009be5  lea     rdx, [rsp+288h+var_248]; void **
0x180009bea  lea     rcx, [rsp+288h+Dst]; unsigned __int16 *
0x180009bef  call    ?CheckTrust@@YAJPEBGAEAPEAX@Z; CheckTrust(ushort const *,void * &)
0x180009bf4  test    eax, eax
0x180009bf6  js      short loc_180009C3A
0x180009bf8  mov     r9d, 1; int
0x180009bfe  lea     rdx, [rsp+288h+Dst]; unsigned __int16 *
0x180009c03  mov     r8, r15; unsigned __int16 *
0x180009c06  xor     ecx, ecx; HWND
0x180009c08  call    ?LaunchProgramSwitchToDesktop@@YA_NPEAUHWND__@@PEBG1H@Z; LaunchProgramSwitchToDesktop(HWND__ *,ushort const *,ushort const *,int)
0x180009c0d  test    al, al
0x180009c0f  jz      short loc_180009C15
0x180009c11  mov     bl, 1
0x180009c13  jmp     short loc_180009C82
0x180009c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c1c  cmp     rcx, rbp
0x180009c1f  jz      short loc_180009C82
0x180009c21  test    byte ptr [rcx+1Ch], 1
0x180009c25  jz      short loc_180009C82
0x180009c27  mov     edx, 0Fh
0x180009c2c  mov     rcx, [rcx+10h]
0x180009c30  mov     r8, r14
0x180009c33  call    WPP_SF_
0x180009c38  jmp     short loc_180009C82
0x180009c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c41  cmp     rcx, rbp
0x180009c44  jz      short loc_180009C82
0x180009c46  test    byte ptr [rcx+1Ch], 1
0x180009c4a  jz      short loc_180009C82
0x180009c4c  mov     edx, 10h
0x180009c51  jmp     short loc_180009C2C
0x180009c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c5a  cmp     rcx, rbp
0x180009c5d  jz      short loc_180009C7D
0x180009c5f  test    byte ptr [rcx+1Ch], 1
0x180009c63  jz      short loc_180009C7D
0x180009c65  mov     rcx, [rcx+10h]
0x180009c69  mov     edx, 11h
0x180009c6e  mov     r8, r14
0x180009c71  call    WPP_SF_
0x180009c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c7d  test    rdi, rdi
0x180009c80  jz      short loc_180009C92
0x180009c82  mov     rcx, rdi; hObject
0x180009c85  call    cs:__imp_CloseHandle
0x180009c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c92  mov     rax, [rsp+288h+var_248]
0x180009c97  test    rax, rax
0x180009c9a  jz      short loc_180009CAB
0x180009c9c  mov     rcx, rax; void *
0x180009c9f  call    ?FreeWVTStateData@@YAJPEAX@Z; FreeWVTStateData(void *)
0x180009ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cab  cmp     rcx, rbp
0x180009cae  jz      short loc_180009CD3
0x180009cb0  test    byte ptr [rcx+1Ch], 4
0x180009cb4  jz      short loc_180009CD3
0x180009cb6  mov     rcx, [rcx+10h]
0x180009cba  lea     rax, aFalse; "false"
0x180009cc1  test    bl, bl
0x180009cc3  lea     r9, aTrue; "true"
0x180009cca  cmovz   r9, rax
0x180009cce  call    WPP_SF_s
0x180009cd3  movzx   eax, bl
0x180009cd6  mov     rcx, [rsp+288h+var_28]
0x180009cde  xor     rcx, rsp; StackCookie
0x180009ce1  call    __security_check_cookie
0x180009ce6  lea     r11, [rsp+288h+var_18]
0x180009cee  mov     rbx, [r11+28h]
0x180009cf2  mov     rbp, [r11+30h]
0x180009cf6  mov     rsp, r11
0x180009cf9  pop     r15
0x180009cfb  pop     r14
0x180009cfd  pop     rdi
0x180009cfe  retn
```
