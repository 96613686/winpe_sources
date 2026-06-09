# LoadProbeConfig(CWxString *,CWxString *)

- ea: `0x1800a0d24`
- end: `0x1800a1067`
- name: `?LoadProbeConfig@@YAJPEAVCWxString@@0@Z`
- size: `835`
- prototype: `__int64 __fastcall(struct CWxString *this, struct CWxString *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0354`
- `0x1800accd8`

## callees

- `0x180016c84`
- `0x180019384`
- `0x1800193a0`
- `0x18001c504`
- `0x18001cf34`
- `0x1800a0d24`
- `0x1800a1d10`
- `0x1800c7eb0`
- `0x1800db6b0`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0e4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a0e4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a0ea9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a0f3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a0ea9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a0f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a1038`

## string_xrefs

- `0x1800a0e40`: `SYSTEM\CurrentControlSet\Services\NlaSvc\Parameters\Internet`
- `0x1800a0f0d`: `ActiveWebProbePath`
- `0x1800a0db1`: `www.msftconnecttest.com`

## pseudocode

```c
__int64 __fastcall LoadProbeConfig(struct CWxString *this, struct CWxString *a2)
{
  int v4; // eax
  signed int v5; // ebx
  unsigned int v6; // edi
  LSTATUS v7; // eax
  __int64 v8; // r15
  __int64 *v9; // rsi
  LSTATUS ValueW; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 *v14; // rsi
  LSTATUS v15; // eax
  unsigned int v16; // edx
  unsigned __int16 v17; // r8
  int v18; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-60h]
  PVOID v21; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+50h] [rbp-30h]
  PVOID pvData; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+60h] [rbp-20h]
  DWORD pcbData; // [rsp+68h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-10h] BYREF

  hkey = 0;
  pvData = qword_1800E7D10;
  v24 = 0;
  v21 = qword_1800E7D10;
  v22 = 0;
  pcbData = 0;
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qq(1026, 21, (unsigned int)WPP_646243fd3a0c3965203e888d10e08786_Traceguids, (_DWORD)this, (__int64)a2);
  CWxString::Empty(this);
  CWxString::Empty(a2);
  v4 = CWxString::Set(this, L"www.msftconnecttest.com");
  v5 = v4;
  if ( v4 < 0 || (v4 = CWxString::Set(a2, L"/connecttest.txt"), v5 = v4, v4 < 0) )
  {
    v6 = v4;
    goto LABEL_38;
  }
  v5 = CWxString::ExtendBuffer((CWxString *)&pvData, 0x104u);
  if ( v5 < 0 )
    goto LABEL_33;
  v5 = CWxString::ExtendBuffer((CWxString *)&v21, 0x104u);
  if ( v5 < 0 )
    goto LABEL_33;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\NlaSvc\\Parameters\\Internet",
         0,
         0x20019u,
         &hkey);
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_33;
  v8 = HIDWORD(v24);
  v9 = (__int64 *)pvData;
  pcbData = 2 * HIDWORD(v24);
  ValueW = RegGetValueW(hkey, 0, L"ActiveWebProbeHost", 0x22u, 0, pvData, &pcbData);
  v5 = ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_33;
  v11 = -1;
  if ( v9 == qword_1800E7D10 )
  {
    LODWORD(v12) = v24;
  }
  else
  {
    *((_WORD *)v9 + v8) = 0;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v9 + v12) );
    LODWORD(v24) = v12;
  }
  if ( (_DWORD)v12 )
  {
    v13 = HIDWORD(v22);
    v14 = (__int64 *)v21;
    pcbData = 2 * HIDWORD(v22);
    v15 = RegGetValueW(hkey, 0, L"ActiveWebProbePath", 0x22u, 0, v21, &pcbData);
    v5 = v15;
    if ( v15 > 0 )
      v5 = (unsigned __int16)v15 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_33;
    if ( v14 == qword_1800E7D10 )
    {
      LODWORD(v11) = v22;
    }
    else
    {
      *((_WORD *)v14 + v13) = 0;
      do
        ++v11;
      while ( *((_WORD *)v14 + v11) );
      LODWORD(v22) = v11;
    }
    if ( (_DWORD)v11 )
    {
      v5 = 0;
      v6 = 0;
      if ( *(_WORD *)v14 != 47 )
      {
        v18 = CWxString::Insert((CWxString *)&v21, v16, v17);
        v5 = v18;
        if ( v18 < 0 )
          goto LABEL_33;
        v6 = v18;
      }
      CWxString::Transfer((CWxString *)&pvData, this);
      CWxString::Transfer((CWxString *)&v21, a2);
      goto LABEL_38;
    }
    v5 = -2147024809;
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_33:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 22, WPP_646243fd3a0c3965203e888d10e08786_Traceguids, (unsigned int)v5, phkResult);
  v5 = 0;
  v6 = 0;
LABEL_38:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 23, WPP_646243fd3a0c3965203e888d10e08786_Traceguids, (unsigned int)v5, phkResult);
  CWxString::_Release((CWxString *)&v21);
  CWxString::_Release((CWxString *)&pvData);
  if ( hkey )
    RegCloseKey(hkey);
  return v6;
}

```

## disassembly

```asm
0x1800a0d24  mov     [rsp-38h+arg_10], rbx
0x1800a0d29  push    rbp
0x1800a0d2a  push    rsi
0x1800a0d2b  push    rdi
0x1800a0d2c  push    r12
0x1800a0d2e  push    r13
0x1800a0d30  push    r14
0x1800a0d32  push    r15
0x1800a0d34  mov     rbp, rsp
0x1800a0d37  sub     rsp, 80h
0x1800a0d3e  mov     rax, cs:__security_cookie
0x1800a0d45  xor     rax, rsp
0x1800a0d48  mov     [rbp+var_8], rax
0x1800a0d4c  xor     r13d, r13d
0x1800a0d4f  lea     rax, qword_1800E7D10
0x1800a0d56  mov     [rbp+var_3C], r13d
0x1800a0d5a  mov     r14, rdx
0x1800a0d5d  mov     [rbp+hkey], r13
0x1800a0d61  mov     r12, rcx
0x1800a0d64  mov     [rbp+var_28], rax
0x1800a0d68  mov     [rbp+var_20], r13
0x1800a0d6c  mov     [rbp+var_38], rax
0x1800a0d70  mov     [rbp+var_30], r13
0x1800a0d74  mov     [rbp+var_18], r13d
0x1800a0d78  test    byte ptr cs:xmmword_180107A60, 4
0x1800a0d7f  jz      short loc_1800A0D9E
0x1800a0d81  lea     edx, [r13+15h]
0x1800a0d85  mov     [rsp+80h+phkResult], r14
0x1800a0d8a  mov     ecx, 402h
0x1800a0d8f  lea     r8, WPP_646243fd3a0c3965203e888d10e08786_Traceguids
0x1800a0d96  mov     r9, r12
0x1800a0d99  call    WPP_SF_qq
0x1800a0d9e  mov     rcx, r12; this
0x1800a0da1  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800a0da6  mov     rcx, r14; this
0x1800a0da9  call    ?Empty@CWxString@@QEAAXXZ; CWxString::Empty(void)
0x1800a0dae  mov     rcx, r12; this
0x1800a0db1  lea     rdx, aWwwMsftconnect; "www.msftconnecttest.com"
0x1800a0db8  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800a0dbd  mov     ebx, eax
0x1800a0dbf  test    eax, eax
0x1800a0dc1  jns     short loc_1800A0DCC
0x1800a0dc3  mov     [rbp+var_3C], 767h
0x1800a0dca  jmp     short loc_1800A0DE8
0x1800a0dcc  lea     rdx, aConnecttestTxt; "/connecttest.txt"
0x1800a0dd3  mov     rcx, r14; this
0x1800a0dd6  call    ?Set@CWxString@@QEAAJPEBG@Z; CWxString::Set(ushort const *)
0x1800a0ddb  mov     ebx, eax
0x1800a0ddd  test    eax, eax
0x1800a0ddf  jns     short loc_1800A0DEF
0x1800a0de1  mov     [rbp+var_3C], 768h
0x1800a0de8  mov     edi, eax
0x1800a0dea  jmp     loc_1800A0FFB
0x1800a0def  mov     edi, 104h
0x1800a0df4  lea     rcx, [rbp+var_28]; this
0x1800a0df8  mov     edx, edi; unsigned int
0x1800a0dfa  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1800a0dff  mov     ebx, eax
0x1800a0e01  test    eax, eax
0x1800a0e03  jns     short loc_1800A0E11
0x1800a0e05  mov     [rbp+var_3C], 76Bh
0x1800a0e0c  jmp     loc_1800A0FB7
0x1800a0e11  mov     edx, edi; unsigned int
0x1800a0e13  lea     rcx, [rbp+var_38]; this
0x1800a0e17  call    ?ExtendBuffer@CWxString@@QEAAJK@Z; CWxString::ExtendBuffer(ulong)
0x1800a0e1c  mov     ebx, eax
0x1800a0e1e  test    eax, eax
0x1800a0e20  jns     short loc_1800A0E2E
0x1800a0e22  mov     [rbp+var_3C], 76Ch
0x1800a0e29  jmp     loc_1800A0FB7
0x1800a0e2e  lea     rax, [rbp+hkey]
0x1800a0e32  mov     r9d, 20019h; samDesired
0x1800a0e38  xor     r8d, r8d; ulOptions
0x1800a0e3b  mov     [rsp+80h+phkResult], rax; phkResult
0x1800a0e40  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Nl"...
0x1800a0e47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a0e4e  call    cs:__imp_RegOpenKeyExW
0x1800a0e54  mov     ebx, eax
0x1800a0e56  mov     edi, 80070000h
0x1800a0e5b  test    eax, eax
0x1800a0e5d  jle     short loc_1800A0E64
0x1800a0e5f  movzx   ebx, ax
0x1800a0e62  or      ebx, edi
0x1800a0e64  test    ebx, ebx
0x1800a0e66  jns     short loc_1800A0E74
0x1800a0e68  mov     [rbp+var_3C], 776h
0x1800a0e6f  jmp     loc_1800A0FB7
0x1800a0e74  mov     r15d, dword ptr [rbp+var_20+4]
0x1800a0e78  lea     r8, aActivewebprobe_0; "ActiveWebProbeHost"
0x1800a0e7f  mov     rsi, [rbp+var_28]
0x1800a0e83  mov     r9d, 22h ; '"'; dwFlags
0x1800a0e89  mov     rcx, [rbp+hkey]; hkey
0x1800a0e8d  xor     edx, edx; lpSubKey
0x1800a0e8f  lea     eax, [r15+r15]
0x1800a0e93  mov     [rbp+var_18], eax
0x1800a0e96  lea     rax, [rbp+var_18]
0x1800a0e9a  mov     [rsp+80h+pcbData], rax; pcbData
0x1800a0e9f  mov     [rsp+80h+pvData], rsi; pvData
0x1800a0ea4  mov     [rsp+80h+phkResult], r13; pdwType
0x1800a0ea9  call    cs:__imp_RegGetValueW
0x1800a0eaf  mov     ebx, eax
0x1800a0eb1  test    eax, eax
0x1800a0eb3  jle     short loc_1800A0EBA
0x1800a0eb5  movzx   ebx, ax
0x1800a0eb8  or      ebx, edi
0x1800a0eba  test    ebx, ebx
0x1800a0ebc  jns     short loc_1800A0ECA
0x1800a0ebe  mov     [rbp+var_3C], 783h
0x1800a0ec5  jmp     loc_1800A0FB7
0x1800a0eca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a0ece  lea     rax, qword_1800E7D10
0x1800a0ed5  cmp     rsi, rax
0x1800a0ed8  jz      short loc_1800A0EF1
0x1800a0eda  mov     [rsi+r15*2], r13w
0x1800a0edf  mov     rax, rdi
0x1800a0ee2  inc     rax
0x1800a0ee5  cmp     [rsi+rax*2], r13w
0x1800a0eea  jnz     short loc_1800A0EE2
0x1800a0eec  mov     dword ptr [rbp+var_20], eax
0x1800a0eef  jmp     short loc_1800A0EF4
0x1800a0ef1  mov     eax, dword ptr [rbp+var_20]
0x1800a0ef4  test    eax, eax
0x1800a0ef6  jnz     short loc_1800A0F09
0x1800a0ef8  mov     ebx, 80070057h
0x1800a0efd  mov     [rbp+var_3C], 786h
0x1800a0f04  jmp     loc_1800A0FB7
0x1800a0f09  mov     r15d, dword ptr [rbp+var_30+4]
0x1800a0f0d  lea     r8, aActivewebprobe; "ActiveWebProbePath"
0x1800a0f14  mov     rsi, [rbp+var_38]
0x1800a0f18  mov     r9d, 22h ; '"'; dwFlags
0x1800a0f1e  mov     rcx, [rbp+hkey]; hkey
0x1800a0f22  xor     edx, edx; lpSubKey
0x1800a0f24  lea     eax, [r15+r15]
0x1800a0f28  mov     [rbp+var_18], eax
0x1800a0f2b  lea     rax, [rbp+var_18]
0x1800a0f2f  mov     [rsp+80h+pcbData], rax; pcbData
0x1800a0f34  mov     [rsp+80h+pvData], rsi; pvData
0x1800a0f39  mov     [rsp+80h+phkResult], r13; pdwType
0x1800a0f3e  call    cs:__imp_RegGetValueW
0x1800a0f44  mov     ebx, eax
0x1800a0f46  test    eax, eax
0x1800a0f48  jle     short loc_1800A0F53
0x1800a0f4a  movzx   ebx, ax
0x1800a0f4d  or      ebx, 80070000h
0x1800a0f53  test    ebx, ebx
0x1800a0f55  jns     short loc_1800A0F60
0x1800a0f57  mov     [rbp+var_3C], 793h
0x1800a0f5e  jmp     short loc_1800A0FB7
0x1800a0f60  lea     rax, qword_1800E7D10
0x1800a0f67  cmp     rsi, rax
0x1800a0f6a  jz      short loc_1800A0F80
0x1800a0f6c  mov     [rsi+r15*2], r13w
0x1800a0f71  inc     rdi
0x1800a0f74  cmp     [rsi+rdi*2], r13w
0x1800a0f79  jnz     short loc_1800A0F71
0x1800a0f7b  mov     dword ptr [rbp+var_30], edi
0x1800a0f7e  jmp     short loc_1800A0F83
0x1800a0f80  mov     edi, dword ptr [rbp+var_30]
0x1800a0f83  test    edi, edi
0x1800a0f85  jnz     short loc_1800A0F95
0x1800a0f87  mov     ebx, 80070057h
0x1800a0f8c  mov     [rbp+var_3C], 796h
0x1800a0f93  jmp     short loc_1800A0FB7
0x1800a0f95  cmp     word ptr [rsi], 2Fh ; '/'
0x1800a0f99  mov     ebx, r13d
0x1800a0f9c  mov     edi, r13d
0x1800a0f9f  jz      short loc_1800A0FE3
0x1800a0fa1  lea     rcx, [rbp+var_38]; this
0x1800a0fa5  call    ?Insert@CWxString@@QEAAJKG@Z; CWxString::Insert(ulong,ushort)
0x1800a0faa  mov     ebx, eax
0x1800a0fac  test    eax, eax
0x1800a0fae  jns     short loc_1800A0FE1
0x1800a0fb0  mov     [rbp+var_3C], 79Ah
0x1800a0fb7  test    byte ptr cs:xmmword_180107A60, 4
0x1800a0fbe  jz      short loc_1800A0FD9
0x1800a0fc0  mov     edx, 16h
0x1800a0fc5  lea     r8, WPP_646243fd3a0c3965203e888d10e08786_Traceguids
0x1800a0fcc  mov     ecx, 402h
0x1800a0fd1  mov     r9d, ebx
0x1800a0fd4  call    WPP_SF_d
0x1800a0fd9  mov     ebx, r13d
0x1800a0fdc  mov     edi, r13d
0x1800a0fdf  jmp     short loc_1800A0FFB
0x1800a0fe1  mov     edi, eax
0x1800a0fe3  mov     rdx, r12; struct CWxString *
0x1800a0fe6  lea     rcx, [rbp+var_28]; this
0x1800a0fea  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1800a0fef  mov     rdx, r14; struct CWxString *
0x1800a0ff2  lea     rcx, [rbp+var_38]; this
0x1800a0ff6  call    ?Transfer@CWxString@@QEAAXPEAV1@@Z; CWxString::Transfer(CWxString *)
0x1800a0ffb  test    byte ptr cs:xmmword_180107A60, 4
0x1800a1002  jz      short loc_1800A101D
0x1800a1004  mov     edx, 17h
0x1800a1009  lea     r8, WPP_646243fd3a0c3965203e888d10e08786_Traceguids
0x1800a1010  mov     ecx, 402h
0x1800a1015  mov     r9d, ebx
0x1800a1018  call    WPP_SF_d
0x1800a101d  lea     rcx, [rbp+var_38]; this
0x1800a1021  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800a1026  lea     rcx, [rbp+var_28]; this
0x1800a102a  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800a102f  mov     rcx, [rbp+hkey]; hKey
0x1800a1033  test    rcx, rcx
0x1800a1036  jz      short loc_1800A103E
0x1800a1038  call    cs:__imp_RegCloseKey
0x1800a103e  mov     eax, edi
0x1800a1040  mov     rcx, [rbp+var_8]
0x1800a1044  xor     rcx, rsp; StackCookie
0x1800a1047  call    __security_check_cookie
0x1800a104c  mov     rbx, [rsp+80h+arg_10]
0x1800a1054  add     rsp, 80h
0x1800a105b  pop     r15
0x1800a105d  pop     r14
0x1800a105f  pop     r13
0x1800a1061  pop     r12
0x1800a1063  pop     rdi
0x1800a1064  pop     rsi
0x1800a1065  pop     rbp
0x1800a1066  retn
```
