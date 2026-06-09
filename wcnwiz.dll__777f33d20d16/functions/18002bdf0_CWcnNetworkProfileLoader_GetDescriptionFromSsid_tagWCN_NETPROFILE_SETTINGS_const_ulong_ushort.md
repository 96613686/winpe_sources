# CWcnNetworkProfileLoader::GetDescriptionFromSsid(tagWCN_NETPROFILE_SETTINGS const *,ulong,ushort *)

- ea: `0x18002bdf0`
- end: `0x18002befc`
- name: `?GetDescriptionFromSsid@CWcnNetworkProfileLoader@@MEAAJPEBUtagWCN_NETPROFILE_SETTINGS@@KPEAG@Z`
- size: `268`
- prototype: `__int64 __fastcall(CWcnNetworkProfileLoader *__hidden this, const struct tagWCN_NETPROFILE_SETTINGS *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000d630`
- `0x18000e0a0`
- `0x18000e1dc`
- `0x18002bdf0`
- `0x18002de1c`

## import_xrefs

- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18002be5d`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x18002be5d`

## pseudocode

```c
__int64 __fastcall CWcnNetworkProfileLoader::GetDescriptionFromSsid(
        CWcnNetworkProfileLoader *this,
        const struct tagWCN_NETPROFILE_SETTINGS *a2,
        int a3,
        unsigned __int16 *a4)
{
  const char *Indent; // rax
  __int64 v7; // r10
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  _BYTE *v11; // r10
  unsigned int v12; // eax
  __int64 v13; // r10
  int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 40, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, Indent);
  }
  *a4 = 0;
  v8 = WlanUtf8SsidToDisplayName((char *)a2 + 512, 1, a4, &v15);
  if ( !v8 )
  {
    v10 = 0;
    goto LABEL_12;
  }
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  else
    v9 = v8;
  v10 = v9 | 0x80000000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_13:
      if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && ((v10 & 0x80000000) != 0 || v11[25] >= 6u) )
      {
        v12 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v13 + 16), 42, (unsigned int)WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids, v12, v10);
      }
      return v10;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids,
      (unsigned int)v8,
      v10);
LABEL_12:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  return v10;
}

```

## disassembly

```asm
0x18002bdf0  mov     [rsp+arg_0], rbx
0x18002bdf5  mov     [rsp+arg_8], rsi
0x18002bdfa  mov     [rsp+arg_10], r8d
0x18002bdff  push    rdi
0x18002be00  sub     rsp, 30h
0x18002be04  mov     rbx, r9
0x18002be07  mov     rdi, rdx
0x18002be0a  mov     r10, cs:WPP_GLOBAL_Control
0x18002be11  lea     rsi, WPP_GLOBAL_Control
0x18002be18  cmp     r10, rsi
0x18002be1b  jz      short loc_18002BE46
0x18002be1d  cmp     byte ptr [r10+19h], 6
0x18002be22  jb      short loc_18002BE46
0x18002be24  mov     ecx, 1; int
0x18002be29  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002be2e  mov     rcx, [r10+10h]
0x18002be32  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002be39  mov     edx, 28h ; '('
0x18002be3e  mov     r9, rax
0x18002be41  call    WPP_SF_s
0x18002be46  xor     eax, eax
0x18002be48  lea     rcx, [rdi+200h]
0x18002be4f  lea     r9, [rsp+38h+arg_10]
0x18002be54  mov     [rbx], ax
0x18002be57  mov     r8, rbx
0x18002be5a  lea     edx, [rax+1]
0x18002be5d  call    cs:__imp_WlanUtf8SsidToDisplayName
0x18002be63  test    eax, eax
0x18002be65  jz      short loc_18002BEAD
0x18002be67  jg      short loc_18002BE6D
0x18002be69  mov     ebx, eax
0x18002be6b  jmp     short loc_18002BE76
0x18002be6d  movzx   ebx, ax
0x18002be70  or      ebx, 80070000h
0x18002be76  or      ebx, 80000000h
0x18002be7c  mov     r10, cs:WPP_GLOBAL_Control
0x18002be83  cmp     r10, rsi
0x18002be86  jz      short loc_18002BEEA
0x18002be88  cmp     byte ptr [r10+19h], 2
0x18002be8d  jb      short loc_18002BEB6
0x18002be8f  mov     rcx, [r10+10h]
0x18002be93  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002be9a  mov     edx, 29h ; ')'
0x18002be9f  mov     [rsp+38h+var_18], ebx
0x18002bea3  mov     r9d, eax
0x18002bea6  call    WPP_SF_Dd
0x18002beab  jmp     short loc_18002BEAF
0x18002bead  xor     ebx, ebx
0x18002beaf  mov     r10, cs:WPP_GLOBAL_Control
0x18002beb6  cmp     r10, rsi
0x18002beb9  jz      short loc_18002BEEA
0x18002bebb  test    ebx, ebx
0x18002bebd  js      short loc_18002BEC6
0x18002bebf  cmp     byte ptr [r10+19h], 6
0x18002bec4  jb      short loc_18002BEEA
0x18002bec6  or      ecx, 0FFFFFFFFh; int
0x18002bec9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002bece  mov     rcx, [r10+10h]
0x18002bed2  lea     r8, WPP_2e91079b8bb935e1ad60682478d78d43_Traceguids
0x18002bed9  mov     edx, 2Ah ; '*'
0x18002bede  mov     [rsp+38h+var_18], ebx
0x18002bee2  mov     r9, rax
0x18002bee5  call    WPP_SF_sd
0x18002beea  mov     rsi, [rsp+38h+arg_8]
0x18002beef  mov     eax, ebx
0x18002bef1  mov     rbx, [rsp+38h+arg_0]
0x18002bef6  add     rsp, 30h
0x18002befa  pop     rdi
0x18002befb  retn
```
