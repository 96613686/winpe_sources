# CreateProfile(_GUID &,WTL::CString const &,WTL::CString const &,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,bool,bool,bool,bool,bool,WTL::CString &)

- ea: `0x180025a00`
- end: `0x180025c03`
- name: `?CreateProfile@@YAJAEAU_GUID@@AEBVCString@WTL@@1W4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@_N4444AEAV23@@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct _GUID *, const struct WTL::CString *, const struct WTL::CString *, unsigned int, enum _DOT11_CIPHER_ALGORITHM, bool, bool, bool, bool, bool, struct WTL::CString *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180023550`

## callees

- `0x1800036fc`
- `0x180020800`
- `0x180023054`
- `0x180025a00`
- `0x18002d840`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x180025b3f`
- `wlanapi!WlanFreeMemory` at `0x180025b3f`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180025ab3`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180025ab3`
- `wlanapi!WlanGenerateProfileXmlBasicSettings` at `0x180025b07`
- `wlanapi!WlanGenerateProfileXmlBasicSettings` at `0x180025b07`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CreateProfile(
        struct _GUID *a1,
        const struct WTL::CString *a2,
        const struct WTL::CString *a3,
        unsigned int a4,
        enum _DOT11_CIPHER_ALGORITHM a5,
        bool a6,
        bool a7,
        bool a8,
        bool a9,
        bool a10,
        struct WTL::CString *a11)
{
  __int64 v14; // rdi
  int v15; // ebx
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  PVOID pMemory; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v20[2]; // [rsp+58h] [rbp-60h] BYREF
  int v21; // [rsp+78h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 28, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  }
  pMemory = 0;
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( a5 == DOT11_CIPHER_ALGO_NONE || a6 )
    v14 = 0;
  else
    v14 = *(_QWORD *)a3;
  v15 = WlanStringToUtf8Ssid(*(_QWORD *)a2, v20);
  if ( v15 )
    goto LABEL_12;
  v16 = WlanGenerateProfileXmlBasicSettings(*(_QWORD *)a2, v20, 1, a4, a5, a6, v14, a7, a10, &pMemory);
  v15 = v16;
  if ( !v16 )
  {
    WTL::CString::operator=(a11, (unsigned __int16 *)pMemory);
LABEL_12:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145)
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 30, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids, v16);
    goto LABEL_12;
  }
LABEL_13:
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 145) >= 4u && (*((_BYTE *)v17 + 148) & 1) != 0 )
    WPP_SF_(v17[17], 31, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180025a00  mov     [rsp+arg_0], rbx
0x180025a05  push    rbp
0x180025a06  push    rdi
0x180025a07  push    r12
0x180025a09  push    r14
0x180025a0b  push    r15
0x180025a0d  sub     rsp, 90h
0x180025a14  mov     rax, cs:__security_cookie
0x180025a1b  xor     rax, rsp
0x180025a1e  mov     [rsp+0B8h+var_38], rax
0x180025a26  mov     r15, [rsp+0B8h+arg_50]
0x180025a2e  mov     r12d, r9d
0x180025a31  mov     rdi, r8
0x180025a34  mov     r14, rdx
0x180025a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a3e  lea     rax, WPP_GLOBAL_Control
0x180025a45  cmp     rcx, rax
0x180025a48  jz      short loc_180025A74
0x180025a4a  cmp     byte ptr [rcx+91h], 4
0x180025a51  jb      short loc_180025A74
0x180025a53  test    byte ptr [rcx+94h], 1
0x180025a5a  jz      short loc_180025A74
0x180025a5c  mov     rcx, [rcx+88h]
0x180025a63  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025a6a  mov     edx, 1Ch
0x180025a6f  call    WPP_SF_
0x180025a74  mov     ebp, [rsp+0B8h+arg_20]
0x180025a7b  xor     eax, eax
0x180025a7d  mov     [rsp+0B8h+pMemory], 0
0x180025a86  xorps   xmm0, xmm0
0x180025a89  mov     [rsp+0B8h+var_40], eax
0x180025a8d  movups  [rsp+0B8h+var_60], xmm0
0x180025a92  movups  [rsp+0B8h+var_50], xmm0
0x180025a97  test    ebp, ebp
0x180025a99  jz      short loc_180025AA9
0x180025a9b  cmp     [rsp+0B8h+arg_28], al
0x180025aa2  jnz     short loc_180025AA9
0x180025aa4  mov     rdi, [rdi]
0x180025aa7  jmp     short loc_180025AAB
0x180025aa9  xor     edi, edi
0x180025aab  mov     rcx, [r14]
0x180025aae  lea     rdx, [rsp+0B8h+var_60]
0x180025ab3  call    cs:__imp_WlanStringToUtf8Ssid
0x180025ab9  mov     ebx, eax
0x180025abb  test    eax, eax
0x180025abd  jnz     short loc_180025B24
0x180025abf  movzx   r8d, [rsp+0B8h+arg_28]
0x180025ac8  lea     rcx, [rsp+0B8h+pMemory]
0x180025acd  movzx   eax, [rsp+0B8h+arg_48]
0x180025ad5  mov     r9d, r12d
0x180025ad8  movzx   edx, [rsp+0B8h+arg_30]
0x180025ae0  mov     [rsp+0B8h+var_70], rcx
0x180025ae5  mov     rcx, [r14]
0x180025ae8  mov     [rsp+0B8h+var_78], eax
0x180025aec  mov     [rsp+0B8h+var_80], edx
0x180025af0  lea     rdx, [rsp+0B8h+var_60]
0x180025af5  mov     [rsp+0B8h+var_88], rdi
0x180025afa  mov     [rsp+0B8h+var_90], r8d
0x180025aff  lea     r8d, [rbx+1]
0x180025b03  mov     [rsp+0B8h+var_98], ebp
0x180025b07  call    cs:__imp_WlanGenerateProfileXmlBasicSettings
0x180025b0d  mov     ebx, eax
0x180025b0f  test    eax, eax
0x180025b11  jnz     loc_180025BB2
0x180025b17  mov     rdx, [rsp+0B8h+pMemory]; unsigned __int16 *
0x180025b1c  mov     rcx, r15; this
0x180025b1f  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x180025b24  lea     rdi, WPP_GLOBAL_Control
0x180025b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b32  mov     rax, [rsp+0B8h+pMemory]
0x180025b37  test    rax, rax
0x180025b3a  jz      short loc_180025B4C
0x180025b3c  mov     rcx, rax; pMemory
0x180025b3f  call    cs:__imp_WlanFreeMemory
0x180025b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b4c  cmp     rcx, rdi
0x180025b4f  jz      short loc_180025B7B
0x180025b51  cmp     byte ptr [rcx+91h], 4
0x180025b58  jb      short loc_180025B7B
0x180025b5a  test    byte ptr [rcx+94h], 1
0x180025b61  jz      short loc_180025B7B
0x180025b63  mov     rcx, [rcx+88h]
0x180025b6a  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025b71  mov     edx, 1Fh
0x180025b76  call    WPP_SF_
0x180025b7b  test    ebx, ebx
0x180025b7d  jle     short loc_180025B88
0x180025b7f  movzx   ebx, bx
0x180025b82  or      ebx, 80070000h
0x180025b88  mov     eax, ebx
0x180025b8a  mov     rcx, [rsp+0B8h+var_38]
0x180025b92  xor     rcx, rsp; StackCookie
0x180025b95  call    __security_check_cookie
0x180025b9a  mov     rbx, [rsp+0B8h+arg_0]
0x180025ba2  add     rsp, 90h
0x180025ba9  pop     r15
0x180025bab  pop     r14
0x180025bad  pop     r12
0x180025baf  pop     rdi
0x180025bb0  pop     rbp
0x180025bb1  retn
0x180025bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bb9  lea     rdi, WPP_GLOBAL_Control
0x180025bc0  cmp     rcx, rdi
0x180025bc3  jz      loc_180025B32
0x180025bc9  cmp     byte ptr [rcx+91h], 1
0x180025bd0  jb      loc_180025B32
0x180025bd6  test    byte ptr [rcx+94h], 1
0x180025bdd  jz      loc_180025B32
0x180025be3  mov     rcx, [rcx+88h]
0x180025bea  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025bf1  mov     edx, 1Eh
0x180025bf6  mov     r9d, eax
0x180025bf9  call    WPP_SF_d
0x180025bfe  jmp     loc_180025B2B
```
