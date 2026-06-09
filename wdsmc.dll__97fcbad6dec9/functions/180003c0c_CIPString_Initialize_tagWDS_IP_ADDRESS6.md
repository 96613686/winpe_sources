# CIPString::Initialize(tagWDS_IP_ADDRESS6 *)

- ea: `0x180003c0c`
- end: `0x180003cfe`
- name: `?Initialize@CIPString@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z`
- size: `242`
- prototype: `unsigned int __fastcall(CIPString *__hidden this, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180003590`
- `0x18000b560`
- `0x18000b8e8`
- `0x18000bb0c`
- `0x18000bdd4`
- `0x18000f688`
- `0x1800148b4`
- `0x180015e94`
- `0x180016270`
- `0x180016340`
- `0x180016904`
- `0x180016e70`
- `0x180018770`
- `0x18001e398`
- `0x18001ed10`
- `0x18001fe54`

## callees

- `0x180003c0c`
- `0x180026670`
- `0x180026d3a`

## import_xrefs

- `WS2_32!WSAAddressToStringW` at `0x180003cbc`
- `WS2_32!WSAAddressToStringW` at `0x180003cbc`
- `WS2_32!__imp_WSAGetLastError` at `0x180003cc6`
- `WS2_32!__imp_WSAGetLastError` at `0x180003cc6`

## pseudocode

```c
__int64 __fastcall CIPString::Initialize(WCHAR *this, struct tagWDS_IP_ADDRESS6 *a2)
{
  int v2; // r8d
  __int128 v3; // xmm0
  int v4; // edi
  unsigned int Error; // ebx
  struct sockaddr *p_saAddress; // rcx
  DWORD v8; // eax
  __int64 result; // rax
  DWORD dwAddressStringLength[4]; // [rsp+30h] [rbp-29h] BYREF
  __int128 Src; // [rsp+40h] [rbp-19h] BYREF
  int v12; // [rsp+50h] [rbp-9h]
  _QWORD v13[2]; // [rsp+60h] [rbp+7h] BYREF
  sockaddr saAddress; // [rsp+70h] [rbp+17h] BYREF
  __int64 v15; // [rsp+80h] [rbp+27h]
  int v16; // [rsp+88h] [rbp+2Fh]

  v2 = *((_DWORD *)a2 + 4);
  v3 = *(_OWORD *)a2;
  v4 = 0;
  v12 = v2;
  dwAddressStringLength[0] = 64;
  Src = v3;
  Error = 0;
  v13[0] = 0;
  v13[1] = 0;
  *(_QWORD *)&saAddress.sa_family = 0;
  *(_QWORD *)&saAddress.sa_data[6] = 0;
  v15 = 0;
  v16 = 0;
  if ( v2 == 4 )
  {
    LOWORD(v13[0]) = 2;
    p_saAddress = (struct sockaddr *)v13;
    HIDWORD(v13[0]) = Src;
    v8 = 16;
  }
  else
  {
    if ( v2 != 16 )
    {
      Error = 87;
      goto LABEL_8;
    }
    saAddress.sa_family = 23;
    memmove_0(&saAddress.sa_data[6], &Src, 0x10u);
    p_saAddress = &saAddress;
    v8 = 28;
  }
  if ( WSAAddressToStringW(p_saAddress, v8, 0, this + 2, dwAddressStringLength) )
    Error = WSAGetLastError();
LABEL_8:
  result = Error;
  LOBYTE(v4) = Error != 0;
  *(_DWORD *)this = v4;
  return result;
}

```

## disassembly

```asm
0x180003c0c  mov     [rsp-8+arg_10], rbx
0x180003c11  push    rbp
0x180003c12  push    rsi
0x180003c13  push    rdi
0x180003c14  lea     rbp, [rsp-47h]
0x180003c19  sub     rsp, 0A0h
0x180003c20  mov     rax, cs:__security_cookie
0x180003c27  xor     rax, rsp
0x180003c2a  mov     [rbp+57h+var_20], rax
0x180003c2e  mov     r8d, [rdx+10h]
0x180003c32  xor     eax, eax
0x180003c34  movups  xmm0, xmmword ptr [rdx]
0x180003c37  xor     edi, edi
0x180003c39  mov     [rbp+57h+var_60], r8d
0x180003c3d  mov     [rbp+57h+dwAddressStringLength], 40h ; '@'
0x180003c44  mov     rsi, rcx
0x180003c47  movaps  [rbp+57h+Src], xmm0
0x180003c4b  mov     ebx, edi
0x180003c4d  mov     [rbp+57h+var_50], rax
0x180003c51  mov     [rbp+57h+var_48], rax
0x180003c55  mov     qword ptr [rbp+57h+saAddress.sa_family], rax
0x180003c59  mov     qword ptr [rbp+57h+saAddress.sa_data+6], rax
0x180003c5d  mov     [rbp+57h+var_30], rax
0x180003c61  mov     [rbp+57h+var_28], eax
0x180003c64  cmp     r8d, 4
0x180003c68  jnz     short loc_180003C80
0x180003c6a  lea     eax, [rdi+2]
0x180003c6d  mov     word ptr [rbp+57h+var_50], ax
0x180003c71  lea     rcx, [rbp+57h+var_50]
0x180003c75  mov     eax, dword ptr [rbp+57h+Src]
0x180003c78  mov     dword ptr [rbp+57h+var_50+4], eax
0x180003c7b  lea     eax, [rdi+10h]
0x180003c7e  jmp     short loc_180003CAA
0x180003c80  mov     eax, 10h
0x180003c85  cmp     r8d, eax
0x180003c88  jnz     short loc_180003CD0
0x180003c8a  lea     ecx, [rax+7]
0x180003c8d  mov     r8d, eax; Size
0x180003c90  mov     [rbp+57h+saAddress.sa_family], cx
0x180003c94  lea     rdx, [rbp+57h+Src]; Src
0x180003c98  lea     rcx, [rbp+57h+saAddress.sa_data+6]; void *
0x180003c9c  call    memmove_0
0x180003ca1  lea     rcx, [rbp+57h+saAddress]; lpsaAddress
0x180003ca5  mov     eax, 1Ch
0x180003caa  lea     rdx, [rbp+57h+dwAddressStringLength]
0x180003cae  xor     r8d, r8d; lpProtocolInfo
0x180003cb1  mov     [rsp+0B0h+lpdwAddressStringLength], rdx; lpdwAddressStringLength
0x180003cb6  lea     r9, [rsi+4]; lpszAddressString
0x180003cba  mov     edx, eax; dwAddressLength
0x180003cbc  call    cs:__imp_WSAAddressToStringW
0x180003cc2  test    eax, eax
0x180003cc4  jz      short loc_180003CD5
0x180003cc6  call    cs:__imp_WSAGetLastError
0x180003ccc  mov     ebx, eax
0x180003cce  jmp     short loc_180003CD5
0x180003cd0  mov     ebx, 57h ; 'W'
0x180003cd5  test    ebx, ebx
0x180003cd7  mov     eax, ebx
0x180003cd9  setnz   dil
0x180003cdd  mov     [rsi], edi
0x180003cdf  mov     rcx, [rbp+57h+var_20]
0x180003ce3  xor     rcx, rsp; StackCookie
0x180003ce6  call    __security_check_cookie
0x180003ceb  mov     rbx, [rsp+0B0h+arg_10]
0x180003cf3  add     rsp, 0A0h
0x180003cfa  pop     rdi
0x180003cfb  pop     rsi
0x180003cfc  pop     rbp
0x180003cfd  retn
```
