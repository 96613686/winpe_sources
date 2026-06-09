# WlanGetExtensibilityInfo

- ea: `0x18004a320`
- end: `0x18004a657`
- name: `WlanGetExtensibilityInfo`
- size: `823`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x180049f3c`
- `0x18004a320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a5b9`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004a454`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004a454`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004a3d5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004a3d5`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18004a4f3`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18004a4f3`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004a5af`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004a5af`

## pseudocode

```c
__int64 __fastcall WlanGetExtensibilityInfo(_QWORD *a1, __int64 a2)
{
  union DOT11_OUI_HEADER *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  _BYTE *v7; // rax
  __int64 DeviceInfoList; // rsi
  DWORD v9; // eax
  __int64 v10; // rdx
  DWORD LastError; // eax
  unsigned int i; // edi
  __int64 v13; // rcx
  _BYTE *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  int v18; // [rsp+30h] [rbp-68h] BYREF
  _OWORD v19[3]; // [rsp+38h] [rbp-60h] BYREF

  v18 = 0;
  memset(v19, 0, sizeof(v19));
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 )
  {
    v5 = 87;
    if ( v4 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)v4 + 28) & 1) == 0 )
      goto LABEL_56;
    WPP_SF_(*((_QWORD *)v4 + 2), 29, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids);
    goto LABEL_55;
  }
  v5 = 0;
  v6 = 1080;
  v7 = (_BYTE *)a2;
  do
  {
    *v7++ = 0;
    --v6;
  }
  while ( v6 );
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 || (v9 = GetLastError(), (v5 = v9) == 0) )
  {
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, LastError);
LABEL_42:
          v4 = WPP_GLOBAL_Control;
        }
LABEL_46:
        if ( DeviceInfoList == -1 )
          goto LABEL_56;
        if ( (unsigned int)DevObjDestroyDeviceInfoList(DeviceInfoList) )
          goto LABEL_55;
        v9 = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
          return v5;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_56;
        v10 = 34;
        goto LABEL_15;
      }
    }
    v4 = WPP_GLOBAL_Control;
    for ( i = 0; ; ++i )
    {
      if ( v18 || i >= 0x3E8 )
      {
        if ( !v5 && !v18 )
          v5 = 2;
        goto LABEL_46;
      }
      v13 = 48;
      v14 = v19;
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
      LODWORD(v19[0]) = 48;
      if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, i, v19) )
        goto LABEL_33;
      v15 = GetLastError();
      v5 = v15;
      if ( v15 == 259 )
      {
        v5 = 2;
        goto LABEL_42;
      }
      if ( !v15 )
      {
LABEL_33:
        v15 = WlanDeviceExtMatch(DeviceInfoList, (__int64)v19, a1, a2, &v18);
        v5 = v15;
        if ( !v15 )
          goto LABEL_39;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 33;
          goto LABEL_38;
        }
      }
      else
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 32;
LABEL_38:
          WPP_SF_d(*((_QWORD *)v4 + 2), v16, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v15);
LABEL_39:
          v4 = WPP_GLOBAL_Control;
          continue;
        }
      }
    }
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v5;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 30;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v4 + 2), v10, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v9);
LABEL_55:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_56:
  if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v4 + 25) >= 4u
    && (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 2), 35, &WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18004a320  mov     [rsp+arg_10], rbx
0x18004a325  push    rbp
0x18004a326  push    rsi
0x18004a327  push    rdi
0x18004a328  push    r13
0x18004a32a  push    r14
0x18004a32c  sub     rsp, 70h
0x18004a330  mov     rax, cs:__security_cookie
0x18004a337  xor     rax, rsp
0x18004a33a  mov     [rsp+98h+var_30], rax
0x18004a33f  xorps   xmm0, xmm0
0x18004a342  mov     [rsp+98h+var_68], 0
0x18004a34a  movups  [rsp+98h+var_60], xmm0
0x18004a34f  mov     rbp, rdx
0x18004a352  mov     r14, rcx
0x18004a355  movups  [rsp+98h+var_50], xmm0
0x18004a35a  movups  [rsp+98h+var_40], xmm0
0x18004a35f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a366  lea     r13, WPP_GLOBAL_Control
0x18004a36d  cmp     rcx, r13
0x18004a370  jz      short loc_18004A39A
0x18004a372  cmp     byte ptr [rcx+19h], 4
0x18004a376  jb      short loc_18004A39A
0x18004a378  test    byte ptr [rcx+1Ch], 1
0x18004a37c  jz      short loc_18004A39A
0x18004a37e  mov     rcx, [rcx+10h]
0x18004a382  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a389  mov     edx, 1Ch
0x18004a38e  call    WPP_SF_
0x18004a393  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a39a  test    r14, r14
0x18004a39d  jz      loc_18004A5E1
0x18004a3a3  test    rbp, rbp
0x18004a3a6  jz      loc_18004A5E1
0x18004a3ac  xor     ebx, ebx
0x18004a3ae  mov     ecx, 438h
0x18004a3b3  mov     rax, rbp
0x18004a3b6  mov     [rax], bl
0x18004a3b8  inc     rax
0x18004a3bb  sub     rcx, 1
0x18004a3bf  jnz     short loc_18004A3B6
0x18004a3c1  xor     r9d, r9d
0x18004a3c4  mov     [rsp+98h+var_78], rbx
0x18004a3c9  xor     r8d, r8d
0x18004a3cc  lea     rcx, GUID_DEVCLASS_NET
0x18004a3d3  xor     edx, edx
0x18004a3d5  call    cs:__imp_DevObjCreateDeviceInfoList
0x18004a3db  mov     rsi, rax
0x18004a3de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a3e2  jnz     short loc_18004A42F
0x18004a3e4  call    cs:__imp_GetLastError
0x18004a3ea  mov     ebx, eax
0x18004a3ec  test    eax, eax
0x18004a3ee  jz      short loc_18004A42F
0x18004a3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3f7  cmp     rcx, r13
0x18004a3fa  jz      loc_18004A634
0x18004a400  cmp     byte ptr [rcx+19h], 1
0x18004a404  jb      loc_18004A60B
0x18004a40a  test    byte ptr [rcx+1Ch], 1
0x18004a40e  jz      loc_18004A60B
0x18004a414  lea     edx, [rsi+1Fh]
0x18004a417  mov     rcx, [rcx+10h]
0x18004a41b  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a422  mov     r9d, eax
0x18004a425  call    WPP_SF_d
0x18004a42a  jmp     loc_18004A604
0x18004a42f  mov     [rsp+98h+var_70], 0
0x18004a438  lea     rdx, GUID_DEVCLASS_NET
0x18004a43f  mov     r9d, 2
0x18004a445  mov     [rsp+98h+var_78], 0
0x18004a44e  xor     r8d, r8d
0x18004a451  mov     rcx, rsi
0x18004a454  call    cs:__imp_DevObjGetClassDevs
0x18004a45a  test    eax, eax
0x18004a45c  jnz     short loc_18004A4AB
0x18004a45e  call    cs:__imp_GetLastError
0x18004a464  mov     ebx, eax
0x18004a466  test    eax, eax
0x18004a468  jz      short loc_18004A4AB
0x18004a46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a471  cmp     rcx, r13
0x18004a474  jz      loc_18004A5A6
0x18004a47a  cmp     byte ptr [rcx+19h], 1
0x18004a47e  jb      loc_18004A5A6
0x18004a484  test    byte ptr [rcx+1Ch], 1
0x18004a488  jz      loc_18004A5A6
0x18004a48e  mov     rcx, [rcx+10h]
0x18004a492  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a499  mov     edx, 1Fh
0x18004a49e  mov     r9d, eax
0x18004a4a1  call    WPP_SF_d
0x18004a4a6  jmp     loc_18004A58F
0x18004a4ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4b2  xor     edi, edi
0x18004a4b4  cmp     [rsp+98h+var_68], 0
0x18004a4b9  jnz     loc_18004A598
0x18004a4bf  cmp     edi, 3E8h
0x18004a4c5  jnb     loc_18004A598
0x18004a4cb  mov     ecx, 30h ; '0'
0x18004a4d0  lea     rax, [rsp+98h+var_60]
0x18004a4d5  mov     byte ptr [rax], 0
0x18004a4d8  inc     rax
0x18004a4db  sub     rcx, 1
0x18004a4df  jnz     short loc_18004A4D5
0x18004a4e1  lea     r8, [rsp+98h+var_60]
0x18004a4e6  mov     dword ptr [rsp+98h+var_60], 30h ; '0'
0x18004a4ee  mov     edx, edi
0x18004a4f0  mov     rcx, rsi
0x18004a4f3  call    cs:__imp_DevObjEnumDeviceInfo
0x18004a4f9  test    eax, eax
0x18004a4fb  jnz     short loc_18004A529
0x18004a4fd  call    cs:__imp_GetLastError
0x18004a503  mov     ebx, eax
0x18004a505  cmp     eax, 103h
0x18004a50a  jz      short loc_18004A58A
0x18004a50c  test    eax, eax
0x18004a50e  jz      short loc_18004A529
0x18004a510  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a517  cmp     rcx, r13
0x18004a51a  jz      short loc_18004A583
0x18004a51c  test    byte ptr [rcx+1Ch], 1
0x18004a520  jz      short loc_18004A583
0x18004a522  mov     edx, 20h ; ' '
0x18004a527  jmp     short loc_18004A569
0x18004a529  lea     rax, [rsp+98h+var_68]
0x18004a52e  mov     r9, rbp
0x18004a531  mov     r8, r14
0x18004a534  mov     [rsp+98h+var_78], rax
0x18004a539  lea     rdx, [rsp+98h+var_60]
0x18004a53e  mov     rcx, rsi
0x18004a541  call    WlanDeviceExtMatch
0x18004a546  mov     ebx, eax
0x18004a548  test    eax, eax
0x18004a54a  jz      short loc_18004A57C
0x18004a54c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a553  cmp     rcx, r13
0x18004a556  jz      short loc_18004A583
0x18004a558  cmp     byte ptr [rcx+19h], 3
0x18004a55c  jb      short loc_18004A583
0x18004a55e  test    byte ptr [rcx+1Ch], 1
0x18004a562  jz      short loc_18004A583
0x18004a564  mov     edx, 21h ; '!'
0x18004a569  mov     rcx, [rcx+10h]
0x18004a56d  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a574  mov     r9d, eax
0x18004a577  call    WPP_SF_d
0x18004a57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a583  inc     edi
0x18004a585  jmp     loc_18004A4B4
0x18004a58a  mov     ebx, 2
0x18004a58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a596  jmp     short loc_18004A5A6
0x18004a598  test    ebx, ebx
0x18004a59a  jnz     short loc_18004A5A6
0x18004a59c  cmp     [rsp+98h+var_68], ebx
0x18004a5a0  lea     eax, [rbx+2]
0x18004a5a3  cmovz   ebx, eax
0x18004a5a6  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004a5aa  jz      short loc_18004A60B
0x18004a5ac  mov     rcx, rsi
0x18004a5af  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18004a5b5  test    eax, eax
0x18004a5b7  jnz     short loc_18004A604
0x18004a5b9  call    cs:__imp_GetLastError
0x18004a5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5c6  cmp     rcx, r13
0x18004a5c9  jz      short loc_18004A634
0x18004a5cb  cmp     byte ptr [rcx+19h], 3
0x18004a5cf  jb      short loc_18004A60B
0x18004a5d1  test    byte ptr [rcx+1Ch], 1
0x18004a5d5  jz      short loc_18004A60B
0x18004a5d7  mov     edx, 22h ; '"'
0x18004a5dc  jmp     loc_18004A417
0x18004a5e1  mov     ebx, 57h ; 'W'
0x18004a5e6  cmp     rcx, r13
0x18004a5e9  jz      short loc_18004A634
0x18004a5eb  test    byte ptr [rcx+1Ch], 1
0x18004a5ef  jz      short loc_18004A60B
0x18004a5f1  mov     rcx, [rcx+10h]
0x18004a5f5  lea     edx, [rbx-3Ah]
0x18004a5f8  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a5ff  call    WPP_SF_
0x18004a604  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a60b  cmp     rcx, r13
0x18004a60e  jz      short loc_18004A634
0x18004a610  cmp     byte ptr [rcx+19h], 4
0x18004a614  jb      short loc_18004A634
0x18004a616  test    byte ptr [rcx+1Ch], 1
0x18004a61a  jz      short loc_18004A634
0x18004a61c  mov     rcx, [rcx+10h]
0x18004a620  lea     r8, WPP_52d70405f63e3f10ed920fefc30aa7c8_Traceguids
0x18004a627  mov     edx, 23h ; '#'
0x18004a62c  mov     r9d, ebx
0x18004a62f  call    WPP_SF_d
0x18004a634  mov     eax, ebx
0x18004a636  mov     rcx, [rsp+98h+var_30]
0x18004a63b  xor     rcx, rsp; StackCookie
0x18004a63e  call    __security_check_cookie
0x18004a643  mov     rbx, [rsp+98h+arg_10]
0x18004a64b  add     rsp, 70h
0x18004a64f  pop     r14
0x18004a651  pop     r13
0x18004a653  pop     rdi
0x18004a654  pop     rsi
0x18004a655  pop     rbp
0x18004a656  retn
```
