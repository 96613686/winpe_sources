# GetLockScreenInboxAssetLocation(ushort * *)

- ea: `0x180023bec`
- end: `0x180023e9b`
- name: `?GetLockScreenInboxAssetLocation@@YAJPEAPEAG@Z`
- size: `687`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023ac8`
- `0x1800bfc80`

## callees

- `0x180023bec`
- `0x18003729c`
- `0x180054130`
- `0x180054ad4`
- `0x18005a1b6`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023caf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c3d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023c89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023e6a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023c89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023e6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023d68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023e8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023e8a`

## pseudocode

```c
__int64 __fastcall GetLockScreenInboxAssetLocation(LPVOID *a1)
{
  LSTATUS v2; // ebx
  LSTATUS ValueW; // eax
  bool v4; // sf
  unsigned int v5; // ebx
  unsigned __int16 *v7; // rcx
  __int64 v8; // r10
  unsigned __int16 *pvData; // rax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // r9
  __int64 v12; // rcx
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r11
  __int64 v16; // rdi
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  hkey = HKEY_LOCAL_MACHINE;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", 0, 1u, &hkey);
  if ( v2 )
    goto LABEL_21;
  pcbData = 256;
  ValueW = RegGetValueW(hkey, 0, L"DefaultAssetLocation", 2u, 0, Src, &pcbData);
  v2 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = (unsigned __int16 *)CoTaskMemAlloc(pcbData);
    *a1 = pvData;
    if ( pvData )
    {
      if ( v2 )
      {
        if ( RegGetValueW(hkey, 0, L"DefaultAssetLocation", 2u, 0, pvData, &pcbData) )
        {
          v2 = 1003;
          CoTaskMemFree(*a1);
        }
        else
        {
          v2 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v2 = 14;
    }
  }
  RegCloseKey(hkey);
  v4 = v2 < 0;
  if ( v2 )
  {
LABEL_21:
    *a1 = 0;
    v4 = v2 < 0;
    if ( v2 > 0 )
      v4 = 1;
  }
  if ( v4 )
  {
    *a1 = 0;
    if ( !is_mul_ok(0x18u, 2u) )
    {
      v5 = -2147024362;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE,
        (unsigned int)"Internal\\Shell\\Inc\\LockScreenInboxAssets.h",
        (const char *)v5,
        phkResult);
      return v5;
    }
    v10 = (unsigned __int16 *)CoTaskMemAlloc(0x30u);
    *a1 = v10;
    v11 = v10;
    v5 = v10 == 0 ? 0x8007000E : 0;
    if ( !v10 )
      goto LABEL_8;
    v12 = 23;
    v13 = L"%SystemRoot%\\Web\\Screen";
    v14 = 24;
    v15 = 0;
    do
    {
      if ( !v12 )
        break;
      if ( !*v13 )
        break;
      *v10++ = *v13++;
      --v12;
      ++v15;
      --v14;
    }
    while ( v14 );
    v7 = v10 - 1;
    v8 = v15 - 1;
    if ( v14 )
    {
      v7 = v10;
      v8 = v15;
    }
    *v7 = 0;
    if ( v14 )
    {
      v16 = 24 - v8;
      if ( v8 != 24 && v8 != 23 && (unsigned __int64)(2 * v16) > 2 )
        memset_0(&v11[v8 + 1], 0, 2 * v16 - 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180023bec  mov     [rsp-8+arg_8], rbx
0x180023bf1  mov     [rsp-8+arg_10], rsi
0x180023bf6  push    rbp
0x180023bf7  push    rdi
0x180023bf8  push    r14
0x180023bfa  lea     rbp, [rsp-60h]
0x180023bff  sub     rsp, 160h
0x180023c06  mov     rax, cs:__security_cookie
0x180023c0d  xor     rax, rsp
0x180023c10  mov     [rbp+70h+var_20], rax
0x180023c14  mov     rsi, rcx
0x180023c17  lea     rax, [rsp+170h+hkey]
0x180023c1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023c23  mov     [rsp+170h+phkResult], rax; phkResult
0x180023c28  mov     r9d, 1; samDesired
0x180023c2e  mov     [rsp+170h+hkey], rcx
0x180023c33  xor     r8d, r8d; ulOptions
0x180023c36  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023c3d  call    cs:__imp_RegOpenKeyExW
0x180023c44  nop     dword ptr [rax+rax+00h]
0x180023c49  xor     r14d, r14d
0x180023c4c  mov     ebx, eax
0x180023c4e  test    eax, eax
0x180023c50  jnz     loc_180023DD9
0x180023c56  mov     rcx, [rsp+170h+hkey]; hkey
0x180023c5b  lea     rax, [rsp+170h+var_130]
0x180023c60  mov     [rsp+170h+pcbData], rax; pcbData
0x180023c65  lea     r9d, [rbx+2]; dwFlags
0x180023c69  lea     rax, [rsp+170h+Src]
0x180023c6e  mov     [rsp+170h+var_130], 100h
0x180023c76  mov     [rsp+170h+pvData], rax; pvData
0x180023c7b  lea     r8, aDefaultassetlo; "DefaultAssetLocation"
0x180023c82  xor     edx, edx; lpSubKey
0x180023c84  mov     [rsp+170h+phkResult], r14; int
0x180023c89  call    cs:__imp_RegGetValueW
0x180023c90  nop     dword ptr [rax+rax+00h]
0x180023c95  mov     ebx, eax
0x180023c97  test    eax, eax
0x180023c99  jz      loc_180023D41
0x180023c9f  cmp     eax, 0EAh
0x180023ca4  jz      loc_180023D41
0x180023caa  mov     rcx, [rsp+170h+hkey]; hKey
0x180023caf  call    cs:__imp_RegCloseKey
0x180023cb6  nop     dword ptr [rax+rax+00h]
0x180023cbb  test    ebx, ebx
0x180023cbd  jnz     loc_180023DD9
0x180023cc3  jns     short loc_180023D1A
0x180023cc5  mov     edi, 18h
0x180023cca  mov     [rsi], r14
0x180023ccd  lea     eax, [rdi-16h]
0x180023cd0  mul     rdi
0x180023cd3  test    rdx, rdx
0x180023cd6  jz      loc_180023D65
0x180023cdc  mov     ebx, 80070216h
0x180023ce1  mov     rcx, [rbp+78h]; this
0x180023ce5  lea     r8, aInternalShellI; "Internal\\Shell\\Inc\\LockScreenInboxAs"...
0x180023cec  mov     r9d, ebx; char *
0x180023cef  mov     edx, 0Eh; void *
0x180023cf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cf9  mov     eax, ebx
0x180023cfb  jmp     short loc_180023D1C
0x180023cfd  test    rdx, rdx
0x180023d00  lea     rcx, [rax-2]
0x180023d04  lea     r10, [r11-1]
0x180023d08  cmovnz  rcx, rax
0x180023d0c  cmovnz  r10, r11
0x180023d10  mov     [rcx], r14w
0x180023d14  jnz     loc_180023DF4
0x180023d1a  xor     eax, eax
0x180023d1c  mov     rcx, [rbp+70h+var_20]
0x180023d20  xor     rcx, rsp; StackCookie
0x180023d23  call    __security_check_cookie
0x180023d28  lea     r11, [rsp+170h+var_10]
0x180023d30  mov     rbx, [r11+28h]
0x180023d34  mov     rsi, [r11+30h]
0x180023d38  mov     rsp, r11
0x180023d3b  pop     r14
0x180023d3d  pop     rdi
0x180023d3e  pop     rbp
0x180023d3f  retn
0x180023d41  mov     ecx, [rsp+170h+var_130]; cb
0x180023d45  call    cs:__imp_CoTaskMemAlloc
0x180023d4c  nop     dword ptr [rax+rax+00h]
0x180023d51  mov     [rsi], rax
0x180023d54  test    rax, rax
0x180023d57  jnz     loc_180023E27
0x180023d5d  lea     ebx, [rax+0Eh]
0x180023d60  jmp     loc_180023CAA
0x180023d65  mov     rcx, rax; cb
0x180023d68  call    cs:__imp_CoTaskMemAlloc
0x180023d6f  nop     dword ptr [rax+rax+00h]
0x180023d74  mov     rcx, rax
0x180023d77  mov     [rsi], rax
0x180023d7a  neg     rcx
0x180023d7d  mov     r9, rax
0x180023d80  sbb     ebx, ebx
0x180023d82  not     ebx
0x180023d84  and     ebx, 8007000Eh
0x180023d8a  test    rax, rax
0x180023d8d  jz      loc_180023CE1
0x180023d93  mov     ecx, 17h
0x180023d98  lea     r8, aSystemrootWebS; "%SystemRoot%\\Web\\Screen"
0x180023d9f  mov     rdx, rdi
0x180023da2  mov     r11, r14
0x180023da5  test    rcx, rcx
0x180023da8  jz      loc_180023CFD
0x180023dae  movzx   r10d, word ptr [r8]
0x180023db2  test    r10w, r10w
0x180023db6  jz      loc_180023CFD
0x180023dbc  mov     [rax], r10w
0x180023dc0  add     r8, 2
0x180023dc4  add     rax, 2
0x180023dc8  dec     rcx
0x180023dcb  inc     r11
0x180023dce  sub     rdx, 1
0x180023dd2  jnz     short loc_180023DA5
0x180023dd4  jmp     loc_180023CFD
0x180023dd9  mov     [rsi], r14
0x180023ddc  test    ebx, ebx
0x180023dde  jle     loc_180023CC3
0x180023de4  movzx   ebx, bx
0x180023de7  or      ebx, 80070000h
0x180023ded  test    ebx, ebx
0x180023def  jmp     loc_180023CC3
0x180023df4  sub     rdi, r10
0x180023df7  cmp     rdi, 1
0x180023dfb  jbe     loc_180023D1A
0x180023e01  lea     r8, [rdi+rdi]
0x180023e05  cmp     r8, 2
0x180023e09  jbe     loc_180023D1A
0x180023e0f  add     r9, 2
0x180023e13  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180023e17  xor     edx, edx; Val
0x180023e19  lea     rcx, [r9+r10*2]; void *
0x180023e1d  call    memset_0
0x180023e22  jmp     loc_180023D1A
0x180023e27  test    ebx, ebx
0x180023e29  jnz     short loc_180023E42
0x180023e2b  mov     r8d, [rsp+170h+var_130]; Size
0x180023e30  lea     rdx, [rsp+170h+Src]; Src
0x180023e35  mov     rcx, rax; void *
0x180023e38  call    memcpy_0
0x180023e3d  jmp     loc_180023CAA
0x180023e42  lea     rcx, [rsp+170h+var_130]
0x180023e47  mov     r9d, 2; dwFlags
0x180023e4d  mov     [rsp+170h+pcbData], rcx; pcbData
0x180023e52  lea     r8, aDefaultassetlo; "DefaultAssetLocation"
0x180023e59  mov     rcx, [rsp+170h+hkey]; hkey
0x180023e5e  xor     edx, edx; lpSubKey
0x180023e60  mov     [rsp+170h+pvData], rax; pvData
0x180023e65  mov     [rsp+170h+phkResult], r14; pdwType
0x180023e6a  call    cs:__imp_RegGetValueW
0x180023e71  nop     dword ptr [rax+rax+00h]
0x180023e76  test    eax, eax
0x180023e78  jnz     short loc_180023E82
0x180023e7a  mov     ebx, r14d
0x180023e7d  jmp     loc_180023CAA
0x180023e82  mov     rcx, [rsi]; pv
0x180023e85  mov     ebx, 3EBh
0x180023e8a  call    cs:__imp_CoTaskMemFree
0x180023e91  nop     dword ptr [rax+rax+00h]
0x180023e96  jmp     loc_180023CAA
```
