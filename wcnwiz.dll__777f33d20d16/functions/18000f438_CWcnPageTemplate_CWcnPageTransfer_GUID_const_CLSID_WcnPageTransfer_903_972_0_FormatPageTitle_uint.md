# CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(uint,...)

- ea: `0x18000f438`
- end: `0x18000f4f0`
- name: `?FormatPageTitle@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@QEAAJIZZ`
- size: `184`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f4f8`
- `0x180013984`
- `0x1800184dc`

## callees

- `0x180001820`
- `0x18000f438`
- `0x18001f25c`

## import_xrefs

- `USER32!SendMessageW` at `0x18000f4b4`
- `USER32!SendMessageW` at `0x18000f4ce`
- `USER32!SendMessageW` at `0x18000f4b4`
- `USER32!SendMessageW` at `0x18000f4ce`

## pseudocode

```c
__int64 CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::FormatPageTitle(
        __int64 a1,
        DWORD a2,
        ...)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  va_list Arguments; // [rsp+20h] [rbp-238h] BYREF
  WCHAR lParam[256]; // [rsp+30h] [rbp-228h] BYREF
  va_list va; // [rsp+270h] [rbp+18h] BYREF

  va_start(va, a2);
  va_copy(Arguments, va);
  v3 = WcnUxFormatStringVaList(a2, 0x100u, lParam, &Arguments);
  Arguments = 0;
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = SendMessageW(*(HWND *)(a1 + 160), 0x481u, *(_QWORD *)(a1 + 168), 0);
    SendMessageW(*(HWND *)(a1 + 160), 0x47Eu, v5, (LPARAM)lParam);
  }
  return v4;
}

```

## disassembly

```asm
0x18000f438  mov     [rsp+arg_8], edx
0x18000f43c  mov     r11, rsp
0x18000f43f  mov     [r11+18h], r8
0x18000f443  mov     [r11+20h], r9
0x18000f447  push    rbx
0x18000f448  push    rdi
0x18000f449  sub     rsp, 248h
0x18000f450  mov     rax, cs:__security_cookie
0x18000f457  xor     rax, rsp
0x18000f45a  mov     [rsp+258h+var_28], rax
0x18000f462  mov     rdi, rcx
0x18000f465  mov     [rsp+258h+Arguments], 0
0x18000f46e  lea     rcx, [r11+18h]
0x18000f472  mov     eax, edx
0x18000f474  mov     [rsp+258h+Arguments], rcx
0x18000f479  lea     r9, [rsp+258h+Arguments]; Arguments
0x18000f47e  mov     ecx, eax; dwMessageId
0x18000f480  lea     r8, [rsp+258h+lParam]; lpBuffer
0x18000f485  mov     edx, 100h; nSize
0x18000f48a  call    ?WcnUxFormatStringVaList@@YAJIKPEAGPEAPEAD@Z; WcnUxFormatStringVaList(uint,ulong,ushort *,char * *)
0x18000f48f  mov     [rsp+258h+Arguments], 0
0x18000f498  mov     ebx, eax
0x18000f49a  test    eax, eax
0x18000f49c  js      short loc_18000F4D4
0x18000f49e  mov     r8, [rdi+0A8h]; wParam
0x18000f4a5  xor     r9d, r9d; lParam
0x18000f4a8  mov     rcx, [rdi+0A0h]; hWnd
0x18000f4af  mov     edx, 481h; Msg
0x18000f4b4  call    cs:__imp_SendMessageW
0x18000f4ba  mov     rcx, [rdi+0A0h]; hWnd
0x18000f4c1  lea     r9, [rsp+258h+lParam]; lParam
0x18000f4c6  movsxd  r8, eax; wParam
0x18000f4c9  mov     edx, 47Eh; Msg
0x18000f4ce  call    cs:__imp_SendMessageW
0x18000f4d4  mov     eax, ebx
0x18000f4d6  mov     rcx, [rsp+258h+var_28]
0x18000f4de  xor     rcx, rsp; StackCookie
0x18000f4e1  call    __security_check_cookie
0x18000f4e6  add     rsp, 248h
0x18000f4ed  pop     rdi
0x18000f4ee  pop     rbx
0x18000f4ef  retn
```
