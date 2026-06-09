# ConvertPathToDevicePath

- ea: `0x180035cdc`
- end: `0x180035f89`
- name: `ConvertPathToDevicePath`
- size: `685`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800369a0`

## callees

- `0x18001baf0`
- `0x18001f038`
- `0x1800201d4`
- `0x1800206f4`
- `0x180021ec0`
- `0x180022a10`
- `0x180035cdc`
- `0x1800361d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180035db0`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180035db0`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180035e40`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180035e40`
- `ntdll!RtlFreeUnicodeString` at `0x180035ddd`
- `ntdll!RtlFreeUnicodeString` at `0x180035de9`
- `ntdll!RtlFreeUnicodeString` at `0x180035f28`
- `ntdll!RtlFreeUnicodeString` at `0x180035f34`
- `ntdll!RtlFreeUnicodeString` at `0x180035f70`
- `ntdll!RtlFreeUnicodeString` at `0x180035f7c`
- `ntdll!RtlFreeUnicodeString` at `0x180035ddd`
- `ntdll!RtlFreeUnicodeString` at `0x180035de9`
- `ntdll!RtlFreeUnicodeString` at `0x180035f28`
- `ntdll!RtlFreeUnicodeString` at `0x180035f34`
- `ntdll!RtlFreeUnicodeString` at `0x180035f70`
- `ntdll!RtlFreeUnicodeString` at `0x180035f7c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180035d4f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180035d4f`

## string_xrefs

- `0x180035e53`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180035eac`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`
- `0x180035f56`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConvertPathToDevicePath(__int64 a1, struct _UNICODE_STRING *a2)
{
  int v4; // eax
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // edi
  USHORT Length; // r8
  PWSTR Buffer; // rdx
  __int64 v10; // rsi
  WCHAR v11; // r14
  DWORD DosDeviceW; // eax
  const char *v14; // r9
  unsigned __int64 v15; // rdi
  int LastError; // eax
  unsigned __int16 v17; // bx
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING v22; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR DeviceName[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v24; // [rsp+44h] [rbp-BCh]
  WCHAR TargetPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *(_DWORD *)DeviceName = 0;
  v24 = 0;
  v22 = 0;
  memset_0(TargetPath, 0, 0x208u);
  UnicodeString = 0;
  v4 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &v22, 0, 0);
  if ( v4 < 0 )
  {
    v5 = (unsigned int)v4;
    v6 = 149;
    goto LABEL_24;
  }
  v7 = 1;
  Length = v22.Length;
  if ( ((unsigned __int64)v22.Length >> 1) - 1 <= 1 )
    goto LABEL_11;
  Buffer = v22.Buffer;
  while ( 1 )
  {
    if ( Buffer[v7] != 58 )
      goto LABEL_10;
    v10 = v7 + 1;
    if ( Buffer[v10] != 92 && Buffer[v10] != 47 )
      goto LABEL_10;
    v11 = Buffer[v7 - 1];
    if ( (unsigned int)_o_iswalpha(v11) )
      break;
    Buffer = v22.Buffer;
    Length = v22.Length;
LABEL_10:
    if ( ++v7 >= ((unsigned __int64)Length >> 1) - 1 )
      goto LABEL_11;
  }
  DeviceName[0] = v11;
  DeviceName[1] = 58;
  if ( v7 == -2 )
  {
LABEL_11:
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v22);
    return 2147942487LL;
  }
  DosDeviceW = QueryDosDeviceW(DeviceName, TargetPath, 0x104u);
  v15 = DosDeviceW;
  if ( !DosDeviceW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xB3,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
                  v14);
    goto LABEL_25;
  }
  v17 = v22.Length + 2 * (1 - v10);
  if ( (unsigned __int16)(v17 + 2 * DosDeviceW) < (unsigned __int16)(2 * DosDeviceW) )
  {
    UnicodeString.MaximumLength = -1;
    v5 = 3221225621LL;
    v6 = 187;
LABEL_24:
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
                  (const char *)v5,
                  *(int *)&UnicodeString.Length);
LABEL_25:
    v18 = LastError;
LABEL_26:
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v22);
    return v18;
  }
  else
  {
    UnicodeString.MaximumLength = v17 + 2 * DosDeviceW;
    UnicodeString.Buffer = (PWSTR)MIDL_user_allocate(UnicodeString.MaximumLength);
    if ( !UnicodeString.Buffer )
    {
      v18 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
        (const char *)0x8007000ELL,
        *(int *)&UnicodeString.Length);
      goto LABEL_26;
    }
    UnicodeString.Length = 0;
    v19 = RtlUnicodeStringCchCatStringN(&UnicodeString, TargetPath, v15);
    if ( v19 < 0 )
    {
      v5 = (unsigned int)v19;
      v6 = 192;
      goto LABEL_24;
    }
    v20 = RtlUnicodeStringCchCatStringN(&UnicodeString, &v22.Buffer[(int)v10], v17);
    if ( v20 < 0 )
    {
      v5 = (unsigned int)v20;
      v6 = 193;
      goto LABEL_24;
    }
    *a2 = UnicodeString;
    UnicodeString = 0;
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v22);
    return 0;
  }
}

```

## disassembly

```asm
0x180035cdc  mov     [rsp-8+arg_10], rbx
0x180035ce1  mov     [rsp-8+arg_18], rsi
0x180035ce6  push    rbp
0x180035ce7  push    rdi
0x180035ce8  push    r12
0x180035cea  push    r14
0x180035cec  push    r15
0x180035cee  lea     rbp, [rsp-170h]
0x180035cf6  sub     rsp, 270h
0x180035cfd  mov     rax, cs:__security_cookie
0x180035d04  xor     rax, rsp
0x180035d07  mov     [rbp+190h+var_30], rax
0x180035d0e  mov     r15, rdx
0x180035d11  mov     rbx, rcx
0x180035d14  xor     eax, eax
0x180035d16  mov     dword ptr [rsp+290h+DeviceName], eax
0x180035d1a  mov     [rsp+290h+var_24C], ax
0x180035d1f  xorps   xmm0, xmm0
0x180035d22  movups  xmmword ptr [rsp+290h+var_260.Length], xmm0
0x180035d27  xor     edx, edx; Val
0x180035d29  mov     r8d, 208h; Size
0x180035d2f  lea     rcx, [rsp+290h+TargetPath]; void *
0x180035d34  call    memset_0
0x180035d39  xorps   xmm0, xmm0
0x180035d3c  movups  xmmword ptr [rsp+290h+UnicodeString.Length], xmm0; int
0x180035d41  xor     r9d, r9d
0x180035d44  xor     r8d, r8d
0x180035d47  lea     rdx, [rsp+290h+var_260]
0x180035d4c  mov     rcx, rbx
0x180035d4f  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180035d55  test    eax, eax
0x180035d57  jns     short loc_180035D66
0x180035d59  mov     r9d, eax
0x180035d5c  mov     edx, 95h
0x180035d61  jmp     loc_180035F56
0x180035d66  mov     ebx, 1
0x180035d6b  mov     edi, ebx
0x180035d6d  movzx   r8d, [rsp+290h+var_260.Length]
0x180035d73  mov     eax, r8d
0x180035d76  shr     rax, 1
0x180035d79  sub     rax, rbx
0x180035d7c  cmp     rax, rbx
0x180035d7f  jbe     short loc_180035DD8
0x180035d81  lea     r12d, [rbx+39h]
0x180035d85  mov     rdx, [rsp+290h+var_260.Buffer]
0x180035d8a  mov     eax, edi
0x180035d8c  cmp     [rdx+rax*2], r12w
0x180035d91  jnz     short loc_180035DC5
0x180035d93  lea     esi, [rdi+1]
0x180035d96  cmp     word ptr [rdx+rsi*2], 5Ch ; '\'
0x180035d9b  jz      short loc_180035DA4
0x180035d9d  cmp     word ptr [rdx+rsi*2], 2Fh ; '/'
0x180035da2  jnz     short loc_180035DC5
0x180035da4  lea     eax, [rdi-1]
0x180035da7  movzx   r14d, word ptr [rdx+rax*2]
0x180035dac  movzx   ecx, r14w
0x180035db0  call    cs:__imp__o_iswalpha
0x180035db6  test    eax, eax
0x180035db8  jnz     short loc_180035E1F
0x180035dba  mov     rdx, [rsp+290h+var_260.Buffer]
0x180035dbf  movzx   r8d, [rsp+290h+var_260.Length]
0x180035dc5  add     edi, ebx
0x180035dc7  movzx   ecx, r8w
0x180035dcb  shr     rcx, 1
0x180035dce  sub     rcx, rbx
0x180035dd1  mov     eax, edi
0x180035dd3  cmp     rax, rcx
0x180035dd6  jb      short loc_180035D8A
0x180035dd8  lea     rcx, [rsp+290h+UnicodeString]; UnicodeString
0x180035ddd  call    cs:__imp_RtlFreeUnicodeString
0x180035de3  nop
0x180035de4  lea     rcx, [rsp+290h+var_260]; UnicodeString
0x180035de9  call    cs:__imp_RtlFreeUnicodeString
0x180035def  mov     eax, 80070057h
0x180035df4  mov     rcx, [rbp+190h+var_30]
0x180035dfb  xor     rcx, rsp; StackCookie
0x180035dfe  call    __security_check_cookie
0x180035e03  lea     r11, [rsp+290h+var_20]
0x180035e0b  mov     rbx, [r11+40h]
0x180035e0f  mov     rsi, [r11+48h]
0x180035e13  mov     rsp, r11
0x180035e16  pop     r15
0x180035e18  pop     r14
0x180035e1a  pop     r12
0x180035e1c  pop     rdi
0x180035e1d  pop     rbp
0x180035e1e  retn
0x180035e1f  mov     [rsp+290h+DeviceName], r14w
0x180035e25  mov     [rsp+290h+DeviceName+2], r12w
0x180035e2b  cmp     esi, 0FFFFFFFFh
0x180035e2e  jz      short loc_180035DD8
0x180035e30  mov     r8d, 104h; ucchMax
0x180035e36  lea     rdx, [rsp+290h+TargetPath]; lpTargetPath
0x180035e3b  lea     rcx, [rsp+290h+DeviceName]; lpDeviceName
0x180035e40  call    cs:__imp_QueryDosDeviceW
0x180035e46  mov     edi, eax
0x180035e48  test    eax, eax
0x180035e4a  jnz     short loc_180035E69
0x180035e4c  mov     rcx, [rbp+198h]; this
0x180035e53  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180035e5a  mov     edx, 0B3h; void *
0x180035e5f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035e64  jmp     loc_180035F69
0x180035e69  sub     bx, si
0x180035e6c  add     bx, bx
0x180035e6f  add     bx, [rsp+290h+var_260.Length]
0x180035e74  movzx   eax, di
0x180035e77  add     ax, ax
0x180035e7a  lea     ecx, [rbx+rax]
0x180035e7d  cmp     cx, ax
0x180035e80  jb      loc_180035F41
0x180035e86  mov     [rsp+290h+UnicodeString.MaximumLength], cx
0x180035e8b  movzx   ecx, cx; size
0x180035e8e  call    MIDL_user_allocate
0x180035e93  mov     [rsp+290h+UnicodeString.Buffer], rax
0x180035e98  test    rax, rax
0x180035e9b  jnz     short loc_180035EC2
0x180035e9d  mov     rcx, [rbp+198h]; this
0x180035ea4  mov     ebx, 8007000Eh
0x180035ea9  mov     r9d, ebx; char *
0x180035eac  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180035eb3  mov     edx, 0BDh; void *
0x180035eb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035ebd  jmp     loc_180035F6B
0x180035ec2  xor     eax, eax
0x180035ec4  mov     [rsp+290h+UnicodeString.Length], ax
0x180035ec9  mov     r8, rdi; unsigned __int64
0x180035ecc  lea     rdx, [rsp+290h+TargetPath]; unsigned __int16 *
0x180035ed1  lea     rcx, [rsp+290h+UnicodeString]; struct _UNICODE_STRING *
0x180035ed6  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x180035edb  test    eax, eax
0x180035edd  jns     short loc_180035EE9
0x180035edf  mov     r9d, eax
0x180035ee2  mov     edx, 0C0h
0x180035ee7  jmp     short loc_180035F56
0x180035ee9  movzx   r8d, bx; unsigned __int64
0x180035eed  movsxd  rcx, esi
0x180035ef0  mov     rax, [rsp+290h+var_260.Buffer]
0x180035ef5  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x180035ef9  lea     rcx, [rsp+290h+UnicodeString]; struct _UNICODE_STRING *
0x180035efe  call    ?RtlUnicodeStringCchCatStringN@@YAJPEAU_UNICODE_STRING@@PEBG_K@Z; RtlUnicodeStringCchCatStringN(_UNICODE_STRING *,ushort const *,unsigned __int64)
0x180035f03  test    eax, eax
0x180035f05  jns     short loc_180035F11
0x180035f07  mov     r9d, eax
0x180035f0a  mov     edx, 0C1h
0x180035f0f  jmp     short loc_180035F56
0x180035f11  movups  xmm0, xmmword ptr [rsp+290h+UnicodeString.Length]
0x180035f16  movdqu  xmmword ptr [r15], xmm0
0x180035f1b  xorps   xmm1, xmm1
0x180035f1e  movups  xmmword ptr [rsp+290h+UnicodeString.Length], xmm1
0x180035f23  lea     rcx, [rsp+290h+UnicodeString]; UnicodeString
0x180035f28  call    cs:__imp_RtlFreeUnicodeString
0x180035f2e  nop
0x180035f2f  lea     rcx, [rsp+290h+var_260]; UnicodeString
0x180035f34  call    cs:__imp_RtlFreeUnicodeString
0x180035f3a  xor     eax, eax
0x180035f3c  jmp     loc_180035DF4
0x180035f41  mov     eax, 0FFFFh
0x180035f46  mov     [rsp+290h+UnicodeString.MaximumLength], ax
0x180035f4b  mov     r9d, 0C0000095h; char *
0x180035f51  mov     edx, 0BBh; void *
0x180035f56  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180035f5d  mov     rcx, [rbp+198h]; this
0x180035f64  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180035f69  mov     ebx, eax
0x180035f6b  lea     rcx, [rsp+290h+UnicodeString]; UnicodeString
0x180035f70  call    cs:__imp_RtlFreeUnicodeString
0x180035f76  nop
0x180035f77  lea     rcx, [rsp+290h+var_260]; UnicodeString
0x180035f7c  call    cs:__imp_RtlFreeUnicodeString
0x180035f82  mov     eax, ebx
0x180035f84  jmp     loc_180035DF4
```
