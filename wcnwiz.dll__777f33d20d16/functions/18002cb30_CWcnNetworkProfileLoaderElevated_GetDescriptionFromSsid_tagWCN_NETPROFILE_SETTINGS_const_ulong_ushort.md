# CWcnNetworkProfileLoaderElevated::GetDescriptionFromSsid(tagWCN_NETPROFILE_SETTINGS const *,ulong,ushort *)

- ea: `0x18002cb30`
- end: `0x18002cdae`
- name: `?GetDescriptionFromSsid@CWcnNetworkProfileLoaderElevated@@EEAAJPEBUtagWCN_NETPROFILE_SETTINGS@@KPEAG@Z`
- size: `638`
- prototype: `int(CWcnNetworkProfileLoaderElevated *__hidden this, const struct tagWCN_NETPROFILE_SETTINGS *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e0a0`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18002cb30`
- `0x18002d788`
- `0x18002d9fc`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccd9`
- `KERNEL32!FormatMessageW` at `0x18002ccb7`
- `KERNEL32!FormatMessageW` at `0x18002ccb7`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18002cbe4`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18002cbe4`

## pseudocode

```c
__int64 __fastcall CWcnNetworkProfileLoaderElevated::GetDescriptionFromSsid(
        CWcnNetworkProfileLoaderElevated *this,
        const struct tagWCN_NETPROFILE_SETTINGS *a2,
        DWORD a3,
        unsigned __int16 *a4)
{
  _BYTE *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  int v10; // eax
  CWcnNetworkProfileLoaderElevated *v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  int StringResource; // eax
  unsigned int LastError; // ebx
  const char *v16; // rax
  __int64 v17; // r10
  unsigned int v18; // eax
  __int64 v19; // r10
  int v20; // r8d
  unsigned int v21; // eax
  __int64 v22; // r10
  int v24; // [rsp+40h] [rbp-458h] BYREF
  va_list Arguments[3]; // [rsp+48h] [rbp-450h] BYREF
  _BYTE v26[512]; // [rsp+60h] [rbp-438h] BYREF
  unsigned __int16 Source[256]; // [rsp+260h] [rbp-238h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 32, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !a4 )
  {
    if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && v7[25] >= 2u )
    {
      v18 = (unsigned int)GetIndent(0);
      WPP_SF_sDq(*(_QWORD *)(v19 + 16), 33, v20, v18, a3, (char)a4);
      v7 = WPP_GLOBAL_Control;
    }
    v13 = -2147024809;
    goto LABEL_29;
  }
  v24 = 256;
  Arguments[0] = v26;
  Arguments[1] = 0;
  *a4 = 0;
  v10 = WlanUtf8SsidToDisplayName((char *)a2 + 512, 1, v26, &v24);
  if ( v10 )
  {
    if ( v10 > 0 )
      v12 = (unsigned __int16)v10 | 0x80070000;
    else
      v12 = v10;
    v13 = v12 | 0x80000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_29:
        if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && ((v13 & 0x80000000) != 0 || v7[25] >= 6u) )
        {
          v21 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v22 + 16), 37, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v21, v13);
        }
        return v13;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        (unsigned int)v10,
        v13);
      goto LABEL_13;
    }
  }
  else
  {
    StringResource = CWcnNetworkProfileLoaderElevated::LoadStringResource(v11, 0x1452u, 256, Source);
    v13 = StringResource;
    if ( StringResource < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v13;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_29;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        (unsigned int)StringResource);
      goto LABEL_13;
    }
    if ( FormatMessageW(0x2400u, Source, 0, 0, a4, a3, Arguments) )
    {
LABEL_13:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v13 = LastError | 0x80000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_29;
      v16 = GetIndent(0);
      WPP_SF_s(*(_QWORD *)(v17 + 16), 36, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v16);
      goto LABEL_13;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x18002cb30  push    rbx
0x18002cb32  push    rbp
0x18002cb33  push    rsi
0x18002cb34  push    rdi
0x18002cb35  push    r14
0x18002cb37  sub     rsp, 470h
0x18002cb3e  mov     rax, cs:__security_cookie
0x18002cb45  xor     rax, rsp
0x18002cb48  mov     [rsp+498h+var_38], rax
0x18002cb50  mov     rdi, r9
0x18002cb53  mov     esi, r8d
0x18002cb56  mov     rbx, rdx
0x18002cb59  mov     r10, cs:WPP_GLOBAL_Control
0x18002cb60  lea     rbp, WPP_GLOBAL_Control
0x18002cb67  lea     r14, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002cb6e  cmp     r10, rbp
0x18002cb71  jz      short loc_18002CB9F
0x18002cb73  cmp     byte ptr [r10+19h], 6
0x18002cb78  jb      short loc_18002CB9F
0x18002cb7a  mov     ecx, 1; int
0x18002cb7f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002cb84  mov     rcx, [r10+10h]
0x18002cb88  mov     edx, 20h ; ' '
0x18002cb8d  mov     r9, rax
0x18002cb90  mov     r8, r14
0x18002cb93  call    WPP_SF_s
0x18002cb98  mov     r10, cs:WPP_GLOBAL_Control
0x18002cb9f  test    esi, esi
0x18002cba1  jz      loc_18002CD25
0x18002cba7  test    rdi, rdi
0x18002cbaa  jz      loc_18002CD25
0x18002cbb0  lea     rax, [rsp+498h+var_438]
0x18002cbb5  mov     [rsp+498h+var_458], 100h
0x18002cbbd  mov     [rsp+498h+var_450], rax
0x18002cbc2  lea     rcx, [rbx+200h]
0x18002cbc9  xor     eax, eax
0x18002cbcb  mov     [rsp+498h+var_448], 0
0x18002cbd4  lea     r9, [rsp+498h+var_458]
0x18002cbd9  mov     [rdi], ax
0x18002cbdc  lea     r8, [rsp+498h+var_438]
0x18002cbe1  lea     edx, [rax+1]
0x18002cbe4  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18002cbea  test    eax, eax
0x18002cbec  jz      short loc_18002CC42
0x18002cbee  jg      short loc_18002CBF4
0x18002cbf0  mov     ebx, eax
0x18002cbf2  jmp     short loc_18002CBFD
0x18002cbf4  movzx   ebx, ax
0x18002cbf7  or      ebx, 80070000h
0x18002cbfd  or      ebx, 80000000h
0x18002cc03  mov     r10, cs:WPP_GLOBAL_Control
0x18002cc0a  cmp     r10, rbp
0x18002cc0d  jz      loc_18002CD8E
0x18002cc13  cmp     byte ptr [r10+19h], 2
0x18002cc18  jb      loc_18002CD5E
0x18002cc1e  mov     rcx, [r10+10h]
0x18002cc22  mov     edx, 22h ; '"'
0x18002cc27  mov     r9d, eax
0x18002cc2a  mov     dword ptr [rsp+498h+lpBuffer], ebx
0x18002cc2e  mov     r8, r14
0x18002cc31  call    WPP_SF_Dd
0x18002cc36  mov     r10, cs:WPP_GLOBAL_Control
0x18002cc3d  jmp     loc_18002CD5E
0x18002cc42  lea     r9, [rsp+498h+Source]; unsigned __int16 *
0x18002cc4a  mov     edx, 1452h; int
0x18002cc4f  mov     r8d, 100h; unsigned int
0x18002cc55  call    ?LoadStringResource@CWcnNetworkProfileLoaderElevated@@AEAAJHKPEAG@Z; CWcnNetworkProfileLoaderElevated::LoadStringResource(int,ulong,ushort *)
0x18002cc5a  mov     ebx, eax
0x18002cc5c  test    eax, eax
0x18002cc5e  jns     short loc_18002CC91
0x18002cc60  mov     r10, cs:WPP_GLOBAL_Control
0x18002cc67  cmp     r10, rbp
0x18002cc6a  jz      loc_18002CD8E
0x18002cc70  cmp     byte ptr [r10+19h], 2
0x18002cc75  jb      loc_18002CD5E
0x18002cc7b  mov     rcx, [r10+10h]
0x18002cc7f  mov     edx, 23h ; '#'
0x18002cc84  mov     r9d, eax
0x18002cc87  mov     r8, r14
0x18002cc8a  call    WPP_SF_d
0x18002cc8f  jmp     short loc_18002CC36
0x18002cc91  lea     rax, [rsp+498h+var_450]
0x18002cc96  xor     r9d, r9d; dwLanguageId
0x18002cc99  mov     [rsp+498h+Arguments], rax; Arguments
0x18002cc9e  lea     rdx, [rsp+498h+Source]; lpSource
0x18002cca6  mov     [rsp+498h+nSize], esi; nSize
0x18002ccaa  xor     r8d, r8d; dwMessageId
0x18002ccad  mov     ecx, 2400h; dwFlags
0x18002ccb2  mov     [rsp+498h+lpBuffer], rdi; lpBuffer
0x18002ccb7  call    cs:__imp_FormatMessageW
0x18002ccbd  test    eax, eax
0x18002ccbf  jnz     loc_18002CC36
0x18002ccc5  call    cs:__imp_GetLastError
0x18002cccb  test    eax, eax
0x18002cccd  jg      short loc_18002CCD9
0x18002cccf  call    cs:__imp_GetLastError
0x18002ccd5  mov     ebx, eax
0x18002ccd7  jmp     short loc_18002CCE8
0x18002ccd9  call    cs:__imp_GetLastError
0x18002ccdf  movzx   ebx, ax
0x18002cce2  or      ebx, 80070000h
0x18002cce8  or      ebx, 80000000h
0x18002ccee  mov     r10, cs:WPP_GLOBAL_Control
0x18002ccf5  cmp     r10, rbp
0x18002ccf8  jz      loc_18002CD8E
0x18002ccfe  cmp     byte ptr [r10+19h], 2
0x18002cd03  jb      short loc_18002CD5E
0x18002cd05  xor     ecx, ecx; int
0x18002cd07  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002cd0c  mov     rcx, [r10+10h]
0x18002cd10  mov     edx, 24h ; '$'
0x18002cd15  mov     r9, rax
0x18002cd18  mov     r8, r14
0x18002cd1b  call    WPP_SF_s
0x18002cd20  jmp     loc_18002CC36
0x18002cd25  cmp     r10, rbp
0x18002cd28  jz      short loc_18002CD59
0x18002cd2a  cmp     byte ptr [r10+19h], 2
0x18002cd2f  jb      short loc_18002CD59
0x18002cd31  xor     ecx, ecx; int
0x18002cd33  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002cd38  mov     rcx, [r10+10h]
0x18002cd3c  mov     edx, 21h ; '!'
0x18002cd41  mov     r9, rax
0x18002cd44  mov     qword ptr [rsp+498h+nSize], rdi
0x18002cd49  mov     dword ptr [rsp+498h+lpBuffer], esi
0x18002cd4d  call    WPP_SF_sDq
0x18002cd52  mov     r10, cs:WPP_GLOBAL_Control
0x18002cd59  mov     ebx, 80070057h
0x18002cd5e  cmp     r10, rbp
0x18002cd61  jz      short loc_18002CD8E
0x18002cd63  test    ebx, ebx
0x18002cd65  js      short loc_18002CD6E
0x18002cd67  cmp     byte ptr [r10+19h], 6
0x18002cd6c  jb      short loc_18002CD8E
0x18002cd6e  or      ecx, 0FFFFFFFFh; int
0x18002cd71  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002cd76  mov     rcx, [r10+10h]
0x18002cd7a  mov     edx, 25h ; '%'
0x18002cd7f  mov     r9, rax
0x18002cd82  mov     dword ptr [rsp+498h+lpBuffer], ebx
0x18002cd86  mov     r8, r14
0x18002cd89  call    WPP_SF_sd
0x18002cd8e  mov     eax, ebx
0x18002cd90  mov     rcx, [rsp+498h+var_38]
0x18002cd98  xor     rcx, rsp; StackCookie
0x18002cd9b  call    __security_check_cookie
0x18002cda0  add     rsp, 470h
0x18002cda7  pop     r14
0x18002cda9  pop     rdi
0x18002cdaa  pop     rsi
0x18002cdab  pop     rbp
0x18002cdac  pop     rbx
0x18002cdad  retn
```
