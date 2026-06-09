# GetTypeInfoFromProgID

- ea: `0x1800643ac`
- end: `0x180064506`
- name: `GetTypeInfoFromProgID`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180063dd8`

## callees

- `0x180043468`
- `0x180043b90`
- `0x1800643ac`
- `0x18006450c`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLE32!CLSIDFromProgID` at `0x1800643ed`
- `OLE32!CLSIDFromProgID` at `0x1800643ed`
- `ADVAPI32!RegCloseKey` at `0x180064499`
- `ADVAPI32!RegCloseKey` at `0x1800644dd`
- `ADVAPI32!RegCloseKey` at `0x180076e11`
- `ADVAPI32!RegCloseKey` at `0x180064499`
- `ADVAPI32!RegCloseKey` at `0x1800644dd`
- `ADVAPI32!RegCloseKey` at `0x180076e11`

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
0x1800643ac  mov     r11, rsp
0x1800643af  mov     [r11+18h], rbx
0x1800643b3  push    rsi
0x1800643b4  push    rdi
0x1800643b5  push    r14
0x1800643b7  sub     rsp, 80h
0x1800643be  mov     rax, cs:__security_cookie
0x1800643c5  xor     rax, rsp
0x1800643c8  mov     [rsp+98h+var_28], rax
0x1800643cd  mov     r14, rdx
0x1800643d0  mov     qword ptr [rdx], 0
0x1800643d7  xorps   xmm0, xmm0
0x1800643da  movups  [rsp+98h+var_38], xmm0
0x1800643df  xor     ebx, ebx
0x1800643e1  mov     [r11-68h], rbx
0x1800643e5  mov     [r11-70h], rbx
0x1800643e9  lea     rdx, [r11-38h]; lpclsid
0x1800643ed  call    cs:__imp_CLSIDFromProgID
0x1800643f3  mov     edi, eax
0x1800643f5  test    eax, eax
0x1800643f7  js      loc_1800644BF
0x1800643fd  movaps  xmm0, [rsp+98h+var_38]
0x180064402  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x180064408  lea     rdx, [rsp+98h+hKey]
0x18006440d  lea     rcx, [rsp+98h+rclsid]; rclsid
0x180064412  call    GetKeyFromClsid
0x180064417  mov     edi, eax
0x180064419  test    eax, eax
0x18006441b  js      loc_1800644BA
0x180064421  mov     [rsp+98h+var_78], 80004005h
0x180064429  movaps  xmm0, [rsp+98h+var_38]
0x18006442e  movdqa  xmmword ptr [rsp+98h+rclsid.Data1], xmm0
0x180064434  lea     r8, [rsp+98h+var_70]
0x180064439  lea     rdx, [rsp+98h+rclsid]
0x18006443e  mov     rbx, [rsp+98h+hKey]
0x180064443  mov     rcx, rbx
0x180064446  call    GetTypeInfoFromTypeLibKey
0x18006444b  mov     edi, eax
0x18006444d  mov     [rsp+98h+var_78], eax
0x180064451  test    eax, eax
0x180064453  jns     short loc_180064491
0x180064455  mov     esi, 1
0x18006445a  mov     [rsp+98h+var_60], esi
0x18006445e  cmp     esi, 6
0x180064461  jge     short loc_180064491
0x180064463  movaps  xmm0, [rsp+98h+var_38]
0x180064468  movdqa  [rsp+98h+var_48], xmm0
0x18006446e  lea     r9, [rsp+98h+var_70]
0x180064473  mov     r8d, esi
0x180064476  lea     rdx, [rsp+98h+var_48]
0x18006447b  mov     rcx, rbx
0x18006447e  call    GetTypeInfoFromInprocServer
0x180064483  mov     edi, eax
0x180064485  mov     [rsp+98h+var_78], eax
0x180064489  test    eax, eax
0x18006448b  jns     short loc_180064491
0x18006448d  inc     esi
0x18006448f  jmp     short loc_18006445A
0x180064491  test    rbx, rbx
0x180064494  jz      short loc_1800644A1
0x180064496  mov     rcx, rbx; hKey
0x180064499  call    cs:__imp_RegCloseKey
0x18006449f  xor     ebx, ebx
0x1800644a1  test    edi, edi
0x1800644a3  js      short loc_1800644BF
0x1800644a5  mov     rax, [rsp+98h+var_70]
0x1800644aa  mov     [r14], rax
0x1800644ad  mov     [rsp+98h+var_70], 0
0x1800644b6  xor     edi, edi
0x1800644b8  jmp     short loc_1800644BF
0x1800644ba  mov     rbx, [rsp+98h+hKey]
0x1800644bf  mov     rcx, [rsp+98h+var_70]
0x1800644c4  test    rcx, rcx
0x1800644c7  jz      short loc_1800644D5
0x1800644c9  mov     rax, [rcx]
0x1800644cc  mov     rax, [rax+10h]
0x1800644d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644d5  test    rbx, rbx
0x1800644d8  jz      short loc_1800644E3
0x1800644da  mov     rcx, rbx; hKey
0x1800644dd  call    cs:__imp_RegCloseKey
0x1800644e3  mov     eax, edi
0x1800644e5  mov     rcx, [rsp+98h+var_28]
0x1800644ea  xor     rcx, rsp; StackCookie
0x1800644ed  call    __security_check_cookie
0x1800644f2  mov     rbx, [rsp+98h+arg_10]
0x1800644fa  add     rsp, 80h
0x180064501  pop     r14
0x180064503  pop     rdi
0x180064504  pop     rsi
0x180064505  retn
0x180076dff  push    rbp
0x180076e01  sub     rsp, 20h
0x180076e05  mov     rbp, rdx
0x180076e08  mov     rcx, [rbp+30h]; hKey
0x180076e0c  test    rcx, rcx
0x180076e0f  jz      short loc_180076E18
0x180076e11  call    cs:__imp_RegCloseKey
0x180076e17  nop
0x180076e18  add     rsp, 20h
0x180076e1c  pop     rbp
0x180076e1d  retn
```
