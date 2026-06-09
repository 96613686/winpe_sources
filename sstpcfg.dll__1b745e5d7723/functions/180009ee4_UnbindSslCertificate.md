# UnbindSslCertificate

- ea: `0x180009ee4`
- end: `0x18000a00d`
- name: `UnbindSslCertificate`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180006b6c`
- `0x180007450`

## callees

- `0x180009ee4`
- `0x18000a38c`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180009f3f`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180009f3f`

## pseudocode

```c
__int64 __fastcall UnbindSslCertificate(char a1, void *a2, ULONG a3)
{
  ULONG v6; // ebx
  int v7; // r8d
  const char *v8; // r9
  const wchar_t *v9; // r8
  int v11; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v12[2044]; // [rsp+34h] [rbp-814h] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  v6 = HttpDeleteServiceConfiguration(0, HttpServiceConfigSSLCertInfo, a2, a3, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v8 = "IPv4";
    if ( !a1 )
      v8 = "IPv6";
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, v7, (_DWORD)v8, v6);
  }
  if ( *((_QWORD *)&xmmword_1800146E0 + 1) )
  {
    v9 = L"IPv4";
    LOWORD(v11) = 0;
    if ( !a1 )
      v9 = L"IPv6";
    FormatRRASErrorString(&v11, L"Unbinding of %ws certificate from SSL returned: %d", v9, v6);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
      gSstpCfgEtwContext,
      *((_QWORD *)&xmmword_1800146E0 + 1),
      &v11);
  }
  return v6;
}

```

## disassembly

```asm
0x180009ee4  mov     [rsp+arg_0], rbx
0x180009ee9  mov     [rsp+arg_18], rsi
0x180009eee  push    rdi
0x180009eef  sub     rsp, 840h
0x180009ef6  mov     rax, cs:__security_cookie
0x180009efd  xor     rax, rsp
0x180009f00  mov     [rsp+848h+var_18], rax
0x180009f08  mov     edi, r8d
0x180009f0b  mov     rbx, rdx
0x180009f0e  mov     sil, cl
0x180009f11  xor     eax, eax
0x180009f13  xor     edx, edx; Val
0x180009f15  mov     [rsp+848h+var_818], eax
0x180009f19  mov     r8d, 7FCh; Size
0x180009f1f  lea     rcx, [rsp+848h+var_814]; void *
0x180009f24  call    memset_0
0x180009f29  mov     r9d, edi; ConfigInformationLength
0x180009f2c  mov     [rsp+848h+pOverlapped], 0; pOverlapped
0x180009f35  mov     r8, rbx; pConfigInformation
0x180009f38  mov     edx, 1; ConfigId
0x180009f3d  xor     ecx, ecx; ServiceHandle
0x180009f3f  call    cs:__imp_HttpDeleteServiceConfiguration
0x180009f45  mov     ebx, eax
0x180009f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f4e  lea     rax, WPP_GLOBAL_Control
0x180009f55  cmp     rcx, rax
0x180009f58  jz      short loc_180009F8D
0x180009f5a  test    byte ptr [rcx+1Ch], 40h
0x180009f5e  jz      short loc_180009F8D
0x180009f60  cmp     byte ptr [rcx+19h], 3
0x180009f64  jb      short loc_180009F8D
0x180009f66  mov     rcx, [rcx+10h]
0x180009f6a  lea     rax, aIpv6_1; "IPv6"
0x180009f71  test    sil, sil
0x180009f74  mov     dword ptr [rsp+848h+pOverlapped], ebx
0x180009f78  lea     r9, aIpv4_0; "IPv4"
0x180009f7f  mov     edx, 42h ; 'B'
0x180009f84  cmovz   r9, rax
0x180009f88  call    WPP_SF_sD
0x180009f8d  cmp     qword ptr cs:xmmword_1800146E0+8, 0
0x180009f95  jz      short loc_180009FE6
0x180009f97  xor     eax, eax
0x180009f99  lea     r8, aIpv4_2; "IPv4"
0x180009fa0  mov     word ptr [rsp+848h+var_818], ax
0x180009fa5  lea     rdx, aUnbindingOfWsC; "Unbinding of %ws certificate from SSL r"...
0x180009fac  lea     rax, aIpv6_0; "IPv6"
0x180009fb3  test    sil, sil
0x180009fb6  mov     r9d, ebx
0x180009fb9  lea     rcx, [rsp+848h+var_818]
0x180009fbe  cmovz   r8, rax
0x180009fc2  call    FormatRRASErrorString
0x180009fc7  mov     rdx, qword ptr cs:xmmword_1800146E0+8
0x180009fce  lea     r8, [rsp+848h+var_818]
0x180009fd3  mov     rcx, cs:gSstpCfgEtwContext
0x180009fda  mov     rax, cs:gSstpCfgTemplateFunc
0x180009fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe6  mov     eax, ebx
0x180009fe8  mov     rcx, [rsp+848h+var_18]
0x180009ff0  xor     rcx, rsp; StackCookie
0x180009ff3  call    __security_check_cookie
0x180009ff8  lea     r11, [rsp+848h+var_8]
0x18000a000  mov     rbx, [r11+10h]
0x18000a004  mov     rsi, [r11+28h]
0x18000a008  mov     rsp, r11
0x18000a00b  pop     rdi
0x18000a00c  retn
```
