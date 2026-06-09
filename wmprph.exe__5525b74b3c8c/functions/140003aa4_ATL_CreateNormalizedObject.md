# ATL::CreateNormalizedObject

- ea: `0x140003aa4`
- end: `0x140003c0b`
- name: `ATL::CreateNormalizedObject`
- size: `359`
- prototype: `__int64 __fastcall(LPCOLESTR lpszProgID)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x140001390`
- `0x140003aa4`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140003b61`
- `ole32!CoCreateInstance` at `0x140003bbb`
- `ole32!CoCreateInstance` at `0x140003be0`
- `ole32!CoCreateInstance` at `0x140003b61`
- `ole32!CoCreateInstance` at `0x140003bbb`
- `ole32!CoCreateInstance` at `0x140003be0`
- `ole32!CLSIDFromProgID` at `0x140003b9a`
- `ole32!CLSIDFromProgID` at `0x140003b9a`
- `ole32!CLSIDFromString` at `0x140003b92`
- `ole32!CLSIDFromString` at `0x140003b92`

## pseudocode

```c
__int64 __fastcall ATL::CreateNormalizedObject(OLECHAR *lpszProgID, __int64 a2, LPVOID *ppv, _BYTE *a4)
{
  OLECHAR v7; // ax
  unsigned int v8; // ecx
  HRESULT Instance; // eax
  __int64 v10; // rax
  HRESULT v11; // eax
  CLSID pclsid; // [rsp+30h] [rbp-38h] BYREF

  *a4 = 0;
  *ppv = 0;
  pclsid = 0;
  if ( lpszProgID )
  {
    v7 = *lpszProgID;
    if ( *lpszProgID )
    {
      v8 = -2147467259;
      if ( ((v7 - 77) & 0xFFDF) == 0
        && ((lpszProgID[1] - 83) & 0xFFDF) == 0
        && ((lpszProgID[2] - 72) & 0xFFDF) == 0
        && ((lpszProgID[3] - 84) & 0xFFDF) == 0
        && ((lpszProgID[4] - 77) & 0xFFDF) == 0
        && ((lpszProgID[5] - 76) & 0xFFDF) == 0
        && lpszProgID[6] == 58 )
      {
        Instance = CoCreateInstance(&CLSID_HTMLDocument, 0, 0x15u, &IID_IUnknown, ppv);
        *a4 = 1;
        v8 = Instance;
        if ( Instance >= 0 )
          return v8;
      }
      v10 = -1;
      do
        ++v10;
      while ( lpszProgID[v10] );
      if ( (int)v10 < 255 )
      {
        if ( *lpszProgID == 123 )
          v11 = CLSIDFromString(lpszProgID, &pclsid);
        else
          v11 = CLSIDFromProgID(lpszProgID, &pclsid);
        if ( v11 < 0 )
          goto LABEL_20;
        v8 = CoCreateInstance(&pclsid, 0, 0x15u, &IID_IUnknown, ppv);
      }
      if ( (v8 & 0x80000000) == 0 )
        return v8;
LABEL_20:
      v8 = CoCreateInstance(&CLSID_WebBrowser, 0, 0x15u, &IID_IUnknown, ppv);
      *a4 = 1;
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003aa4  mov     [rsp+arg_8], rbx
0x140003aa9  push    rbp
0x140003aaa  push    rsi
0x140003aab  push    rdi
0x140003aac  sub     rsp, 50h
0x140003ab0  mov     rax, cs:__security_cookie
0x140003ab7  xor     rax, rsp
0x140003aba  mov     [rsp+68h+var_28], rax
0x140003abf  xor     ebp, ebp
0x140003ac1  xorps   xmm0, xmm0
0x140003ac4  mov     [r9], bpl
0x140003ac7  mov     rsi, r9
0x140003aca  mov     [r8], rbp
0x140003acd  mov     rdi, r8
0x140003ad0  mov     rbx, rcx
0x140003ad3  movups  xmmword ptr [rsp+68h+pclsid.Data1], xmm0
0x140003ad8  test    rcx, rcx
0x140003adb  jz      loc_140003BEF
0x140003ae1  movzx   eax, word ptr [rcx]
0x140003ae4  test    ax, ax
0x140003ae7  jz      loc_140003BEF
0x140003aed  sub     ax, 4Dh ; 'M'
0x140003af1  mov     edx, 0FFDFh
0x140003af6  mov     ecx, 80004005h
0x140003afb  test    dx, ax
0x140003afe  jnz     short loc_140003B70
0x140003b00  movzx   eax, word ptr [rbx+2]
0x140003b04  sub     ax, 53h ; 'S'
0x140003b08  test    dx, ax
0x140003b0b  jnz     short loc_140003B70
0x140003b0d  movzx   eax, word ptr [rbx+4]
0x140003b11  sub     ax, 48h ; 'H'
0x140003b15  test    dx, ax
0x140003b18  jnz     short loc_140003B70
0x140003b1a  movzx   eax, word ptr [rbx+6]
0x140003b1e  sub     ax, 54h ; 'T'
0x140003b22  test    dx, ax
0x140003b25  jnz     short loc_140003B70
0x140003b27  movzx   eax, word ptr [rbx+8]
0x140003b2b  sub     ax, 4Dh ; 'M'
0x140003b2f  test    dx, ax
0x140003b32  jnz     short loc_140003B70
0x140003b34  movzx   eax, word ptr [rbx+0Ah]
0x140003b38  sub     ax, 4Ch ; 'L'
0x140003b3c  test    dx, ax
0x140003b3f  jnz     short loc_140003B70
0x140003b41  cmp     word ptr [rbx+0Ch], 3Ah ; ':'
0x140003b46  jnz     short loc_140003B70
0x140003b48  mov     [rsp+68h+ppv], r8; ppv
0x140003b4d  lea     r9, IID_IUnknown; riid
0x140003b54  lea     r8d, [rbp+15h]; dwClsContext
0x140003b58  xor     edx, edx; pUnkOuter
0x140003b5a  lea     rcx, CLSID_HTMLDocument; rclsid
0x140003b61  call    cs:__imp_CoCreateInstance
0x140003b67  mov     byte ptr [rsi], 1
0x140003b6a  mov     ecx, eax
0x140003b6c  test    eax, eax
0x140003b6e  jns     short loc_140003BEB
0x140003b70  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b74  inc     rax
0x140003b77  cmp     [rbx+rax*2], bp
0x140003b7b  jnz     short loc_140003B74
0x140003b7d  cmp     eax, 0FFh
0x140003b82  jge     short loc_140003BC3
0x140003b84  cmp     word ptr [rbx], 7Bh ; '{'
0x140003b88  lea     rdx, [rsp+68h+pclsid]; lpclsid
0x140003b8d  mov     rcx, rbx; lpszProgID
0x140003b90  jnz     short loc_140003B9A
0x140003b92  call    cs:__imp_CLSIDFromString
0x140003b98  jmp     short loc_140003BA0
0x140003b9a  call    cs:__imp_CLSIDFromProgID
0x140003ba0  test    eax, eax
0x140003ba2  js      short loc_140003BC7
0x140003ba4  xor     edx, edx; pUnkOuter
0x140003ba6  mov     [rsp+68h+ppv], rdi; ppv
0x140003bab  lea     r9, IID_IUnknown; riid
0x140003bb2  lea     rcx, [rsp+68h+pclsid]; rclsid
0x140003bb7  lea     r8d, [rdx+15h]; dwClsContext
0x140003bbb  call    cs:__imp_CoCreateInstance
0x140003bc1  mov     ecx, eax
0x140003bc3  test    ecx, ecx
0x140003bc5  jns     short loc_140003BEB
0x140003bc7  xor     edx, edx; pUnkOuter
0x140003bc9  mov     [rsp+68h+ppv], rdi; ppv
0x140003bce  lea     r9, IID_IUnknown; riid
0x140003bd5  lea     rcx, CLSID_WebBrowser; rclsid
0x140003bdc  lea     r8d, [rdx+15h]; dwClsContext
0x140003be0  call    cs:__imp_CoCreateInstance
0x140003be6  mov     ecx, eax
0x140003be8  mov     byte ptr [rsi], 1
0x140003beb  mov     eax, ecx
0x140003bed  jmp     short loc_140003BF1
0x140003bef  xor     eax, eax
0x140003bf1  mov     rcx, [rsp+68h+var_28]
0x140003bf6  xor     rcx, rsp; StackCookie
0x140003bf9  call    __security_check_cookie
0x140003bfe  mov     rbx, [rsp+68h+arg_8]
0x140003c03  add     rsp, 50h
0x140003c07  pop     rdi
0x140003c08  pop     rsi
0x140003c09  pop     rbp
0x140003c0a  retn
```
