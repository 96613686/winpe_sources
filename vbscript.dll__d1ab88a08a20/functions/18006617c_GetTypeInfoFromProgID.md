# GetTypeInfoFromProgID

- ea: `0x18006617c`
- end: `0x1800662e9`
- name: `GetTypeInfoFromProgID`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180065b94`

## callees

- `0x180044658`
- `0x180044db4`
- `0x18006617c`
- `0x1800662f0`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLE32!CLSIDFromProgID` at `0x1800661bd`
- `OLE32!CLSIDFromProgID` at `0x1800661bd`
- `ADVAPI32!RegCloseKey` at `0x18006626f`
- `ADVAPI32!RegCloseKey` at `0x1800662b9`
- `ADVAPI32!RegCloseKey` at `0x180079b31`
- `ADVAPI32!RegCloseKey` at `0x18006626f`
- `ADVAPI32!RegCloseKey` at `0x1800662b9`
- `ADVAPI32!RegCloseKey` at `0x180079b31`

## pseudocode

```c
__int64 __fastcall GetTypeInfoFromProgID(const OLECHAR *a1, _QWORD *a2)
{
  HKEY v3; // rbx
  int KeyFromClsid; // edi
  int i; // esi
  __int64 v7; // [rsp+28h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+38h] [rbp-60h]
  IID rclsid; // [rsp+40h] [rbp-58h] BYREF
  CLSID v11; // [rsp+50h] [rbp-48h] BYREF
  CLSID v12; // [rsp+60h] [rbp-38h] BYREF

  *a2 = 0;
  v12 = 0;
  v3 = 0;
  hKey = 0;
  v7 = 0;
  KeyFromClsid = CLSIDFromProgID(a1, &v12);
  if ( KeyFromClsid >= 0 )
  {
    rclsid = v12;
    KeyFromClsid = GetKeyFromClsid(&rclsid, &hKey);
    if ( KeyFromClsid < 0 )
    {
      v3 = hKey;
    }
    else
    {
      rclsid = v12;
      v3 = hKey;
      KeyFromClsid = GetTypeInfoFromTypeLibKey(hKey, &rclsid, &v7);
      if ( KeyFromClsid < 0 )
      {
        for ( i = 1; ; ++i )
        {
          v9 = i;
          if ( i >= 6 )
            break;
          v11 = v12;
          KeyFromClsid = GetTypeInfoFromInprocServer(v3, (__int64)&v11, i, &v7);
          if ( KeyFromClsid >= 0 )
            break;
        }
      }
      if ( v3 )
      {
        RegCloseKey(v3);
        v3 = 0;
      }
      if ( KeyFromClsid >= 0 )
      {
        *a2 = v7;
        v7 = 0;
        KeyFromClsid = 0;
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)KeyFromClsid;
}

```

## disassembly

```asm
0x18006617c  mov     r11, rsp
0x18006617f  mov     [r11+18h], rbx
0x180066183  push    rsi
0x180066184  push    rdi
0x180066185  push    r14
0x180066187  sub     rsp, 80h
0x18006618e  mov     rax, cs:__security_cookie
0x180066195  xor     rax, rsp
0x180066198  mov     [rsp+98h+var_28], rax
0x18006619d  mov     r14, rdx
0x1800661a0  mov     qword ptr [rdx], 0
0x1800661a7  xorps   xmm0, xmm0
0x1800661aa  movups  [rsp+98h+var_38], xmm0
0x1800661af  xor     ebx, ebx
0x1800661b1  mov     [r11-68h], rbx
0x1800661b5  mov     [r11-70h], rbx
0x1800661b9  lea     rdx, [r11-38h]; lpclsid
0x1800661bd  call    cs:__imp_CLSIDFromProgID
0x1800661c4  nop     dword ptr [rax+rax+00h]
0x1800661c9  mov     edi, eax
0x1800661cb  test    eax, eax
0x1800661cd  js      loc_18006629B
0x1800661d3  movaps  xmm0, [rsp+98h+var_38]
0x1800661d8  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x1800661de  lea     rdx, [rsp+98h+hKey]
0x1800661e3  lea     rcx, [rsp+98h+rclsid]; rclsid
0x1800661e8  call    GetKeyFromClsid
0x1800661ed  mov     edi, eax
0x1800661ef  test    eax, eax
0x1800661f1  js      loc_180066296
0x1800661f7  mov     [rsp+98h+var_78], 80004005h
0x1800661ff  movaps  xmm0, [rsp+98h+var_38]
0x180066204  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x18006620a  lea     r8, [rsp+98h+var_70]
0x18006620f  lea     rdx, [rsp+98h+rclsid]
0x180066214  mov     rbx, [rsp+98h+hKey]
0x180066219  mov     rcx, rbx
0x18006621c  call    GetTypeInfoFromTypeLibKey
0x180066221  mov     edi, eax
0x180066223  mov     [rsp+98h+var_78], eax
0x180066227  test    eax, eax
0x180066229  jns     short loc_180066267
0x18006622b  mov     esi, 1
0x180066230  mov     [rsp+98h+var_60], esi
0x180066234  cmp     esi, 6
0x180066237  jge     short loc_180066267
0x180066239  movaps  xmm0, [rsp+98h+var_38]
0x18006623e  movdqa  [rsp+98h+var_48], xmm0
0x180066244  lea     r9, [rsp+98h+var_70]
0x180066249  mov     r8d, esi
0x18006624c  lea     rdx, [rsp+98h+var_48]
0x180066251  mov     rcx, rbx
0x180066254  call    GetTypeInfoFromInprocServer
0x180066259  mov     edi, eax
0x18006625b  mov     [rsp+98h+var_78], eax
0x18006625f  test    eax, eax
0x180066261  jns     short loc_180066267
0x180066263  inc     esi
0x180066265  jmp     short loc_180066230
0x180066267  test    rbx, rbx
0x18006626a  jz      short loc_18006627D
0x18006626c  mov     rcx, rbx; hKey
0x18006626f  call    cs:__imp_RegCloseKey
0x180066276  nop     dword ptr [rax+rax+00h]
0x18006627b  xor     ebx, ebx
0x18006627d  test    edi, edi
0x18006627f  js      short loc_18006629B
0x180066281  mov     rax, [rsp+98h+var_70]
0x180066286  mov     [r14], rax
0x180066289  mov     [rsp+98h+var_70], 0
0x180066292  xor     edi, edi
0x180066294  jmp     short loc_18006629B
0x180066296  mov     rbx, [rsp+98h+hKey]
0x18006629b  mov     rcx, [rsp+98h+var_70]
0x1800662a0  test    rcx, rcx
0x1800662a3  jz      short loc_1800662B1
0x1800662a5  mov     rax, [rcx]
0x1800662a8  mov     rax, [rax+10h]
0x1800662ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662b1  test    rbx, rbx
0x1800662b4  jz      short loc_1800662C5
0x1800662b6  mov     rcx, rbx; hKey
0x1800662b9  call    cs:__imp_RegCloseKey
0x1800662c0  nop     dword ptr [rax+rax+00h]
0x1800662c5  mov     eax, edi
0x1800662c7  mov     rcx, [rsp+98h+var_28]
0x1800662cc  xor     rcx, rsp; StackCookie
0x1800662cf  call    __security_check_cookie
0x1800662d4  mov     rbx, [rsp+98h+arg_10]
0x1800662dc  add     rsp, 80h
0x1800662e3  pop     r14
0x1800662e5  pop     rdi
0x1800662e6  pop     rsi
0x1800662e7  retn
0x180079b1f  push    rbp
0x180079b21  sub     rsp, 20h
0x180079b25  mov     rbp, rdx
0x180079b28  mov     rcx, [rbp+30h]; hKey
0x180079b2c  test    rcx, rcx
0x180079b2f  jz      short loc_180079B3E
0x180079b31  call    cs:__imp_RegCloseKey
0x180079b38  nop     dword ptr [rax+rax+00h]
0x180079b3d  nop
0x180079b3e  add     rsp, 20h
0x180079b42  pop     rbp
0x180079b43  retn
```
