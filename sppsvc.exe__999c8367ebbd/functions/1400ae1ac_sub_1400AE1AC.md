# sub_1400AE1AC

- ea: `0x1400ae1ac`
- end: `0x1400ae40f`
- name: `sub_1400AE1AC`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ae668`

## callees

- `0x14006adb4`
- `0x14006d1ec`
- `0x14006d2f8`
- `0x14006de60`
- `0x14007cfb4`
- `0x1400ad618`
- `0x1400ae1ac`
- `0x1400aead0`
- `0x140390f60`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ae280`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400ae280`
- `KERNEL32!GetLastError` at `0x1400ae28a`
- `KERNEL32!GetLastError` at `0x1400ae28a`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1400ae388`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x1400ae388`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1400ae3b1`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1400ae3b1`

## pseudocode

```c
__int64 sub_1400AE1AC()
{
  unsigned int v0; // ebx
  int v1; // eax
  __int64 v2; // rcx
  DWORD LastError; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v8; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v11; // [rsp+58h] [rbp-A8h]
  const wchar_t *v12; // [rsp+60h] [rbp-A0h]
  PSECURITY_DESCRIPTOR v13; // [rsp+68h] [rbp-98h]
  int v14; // [rsp+70h] [rbp-90h]
  int v15; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v16; // [rsp+80h] [rbp-80h]
  const wchar_t *v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  int v19; // [rsp+98h] [rbp-68h]
  int v20; // [rsp+A0h] [rbp-60h] BYREF
  void *v21; // [rsp+A8h] [rbp-58h]
  __int128 v22; // [rsp+B0h] [rbp-50h]
  int v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C4h] [rbp-3Ch]
  void *v25; // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  const wchar_t *v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  WCHAR StringSecurityDescriptor[72]; // [rsp+F0h] [rbp-10h] BYREF

  wcscpy(StringSecurityDescriptor, L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;R;;;AC)");
  SecurityDescriptor = 0;
  if ( dword_1404470AC )
  {
    v0 = -2147024809;
    sub_14006DE60(2147942487LL);
LABEL_13:
    sub_1400AEAD0();
    goto LABEL_14;
  }
  v1 = sub_1400AD618();
  v8 = v1;
  v0 = v1;
  if ( v1 < 0 )
    goto LABEL_4;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v1 = sub_14006D1EC(LastError);
    v0 = v1;
LABEL_4:
    v2 = (unsigned int)v1;
    goto LABEL_11;
  }
  v20 = 0;
  v14 = 100;
  v21 = &unk_1403B92B0;
  v19 = 100;
  v25 = &sub_1400ADD10;
  v23 = 17;
  v27 = L"SPPSVC Default RPC Interface";
  v22 = 0;
  v11 = L"ncalrpc";
  v24 = 1234;
  v12 = L"SPPCTransportEndpoint-00001";
  v13 = SecurityDescriptor;
  v16 = L"ncacn_hvsocket";
  v17 = L"9435CC56-1D9C-4924-AC7D-B60A2C3520E1";
  v26 = 0;
  v28 = 0;
  v10 = 0;
  v15 = 0;
  v18 = 0;
  v4 = RpcServerInterfaceGroupCreateW(
         &v20,
         1,
         &v10,
         (unsigned int)(dword_1404470A8 != 0) + 1,
         -1,
         0,
         0,
         &qword_1404470B0);
  if ( (unsigned int)sub_14006D2F8(v4, &v8) )
  {
    dword_1404470AC = 1;
    v5 = RpcServerInterfaceGroupActivate(qword_1404470B0);
    v6 = sub_14006D2F8(v5, &v8);
    v0 = v8;
    if ( v6 )
      goto LABEL_12;
  }
  else
  {
    v0 = v8;
  }
  v2 = v0;
LABEL_11:
  sub_14006DE60(v2);
LABEL_12:
  if ( (v0 & 0x80000000) != 0 )
    goto LABEL_13;
LABEL_14:
  sub_14007CFB4(v0);
  sub_14006ADB4(&SecurityDescriptor);
  return v0;
}

```

## disassembly

```asm
0x1400ae1ac  mov     [rsp-8+arg_0], rbx
0x1400ae1b1  push    rbp
0x1400ae1b2  lea     rbp, [rsp-90h]
0x1400ae1ba  sub     rsp, 190h
0x1400ae1c1  mov     rax, cs:__security_cookie
0x1400ae1c8  xor     rax, rsp
0x1400ae1cb  mov     [rbp+90h+var_10], rax
0x1400ae1d2  cmp     cs:dword_1404470AC, 0
0x1400ae1d9  movaps  xmm0, cs:xmmword_1403C5E40
0x1400ae1e0  movaps  xmm1, cs:xmmword_1403C5E50
0x1400ae1e7  movups  xmmword ptr [rbp+90h+StringSecurityDescriptor], xmm0
0x1400ae1eb  mov     [rsp+190h+SecurityDescriptor], 0
0x1400ae1f4  movaps  xmm0, cs:xmmword_1403C5E60
0x1400ae1fb  movups  [rbp+90h+var_80], xmm0
0x1400ae1ff  movaps  xmm0, cs:xmmword_1403C5E80
0x1400ae206  movups  [rbp+90h+var_90], xmm1
0x1400ae20a  movaps  xmm1, cs:xmmword_1403C5E70
0x1400ae211  movups  [rbp+90h+var_60], xmm0
0x1400ae215  movaps  xmm0, cs:xmmword_1403C5EA0
0x1400ae21c  movups  [rbp+90h+var_70], xmm1
0x1400ae220  movaps  xmm1, cs:xmmword_1403C5E90
0x1400ae227  movups  [rbp+90h+var_40], xmm0
0x1400ae22b  movups  xmm0, cs:xmmword_1403C5EB0+0Eh
0x1400ae232  movups  [rbp+90h+var_50], xmm1
0x1400ae236  movaps  xmm1, cs:xmmword_1403C5EB0
0x1400ae23d  movups  [rbp+90h+var_30], xmm1
0x1400ae241  movups  [rbp+90h+var_30+0Eh], xmm0
0x1400ae245  jz      short loc_1400AE258
0x1400ae247  mov     ebx, 80070057h
0x1400ae24c  mov     ecx, ebx
0x1400ae24e  call    sub_14006DE60
0x1400ae253  jmp     loc_1400AE3D6
0x1400ae258  call    sub_1400AD618
0x1400ae25d  mov     [rsp+190h+var_150], eax
0x1400ae261  mov     ebx, eax
0x1400ae263  test    eax, eax
0x1400ae265  jns     short loc_1400AE26E
0x1400ae267  mov     ecx, eax
0x1400ae269  jmp     loc_1400AE3CD
0x1400ae26e  xor     r9d, r9d; SecurityDescriptorSize
0x1400ae271  lea     r8, [rsp+190h+SecurityDescriptor]; SecurityDescriptor
0x1400ae276  lea     rcx, [rbp+90h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1400ae27a  lea     ebx, [r9+1]
0x1400ae27e  mov     edx, ebx; StringSDRevision
0x1400ae280  call    cs:ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400ae286  test    eax, eax
0x1400ae288  jnz     short loc_1400AE29B
0x1400ae28a  call    cs:GetLastError
0x1400ae290  mov     ecx, eax
0x1400ae292  call    sub_14006D1EC
0x1400ae297  mov     ebx, eax
0x1400ae299  jmp     short loc_1400AE267
0x1400ae29b  mov     ecx, 64h ; 'd'
0x1400ae2a0  mov     [rbp+90h+var_F0], 0
0x1400ae2a7  lea     rax, unk_1403B92B0
0x1400ae2ae  mov     [rsp+190h+var_120], ecx
0x1400ae2b2  mov     [rbp+90h+var_E8], rax
0x1400ae2b6  lea     r8, [rsp+190h+var_140]
0x1400ae2bb  lea     rax, sub_1400ADD10
0x1400ae2c2  mov     [rbp+90h+var_F8], ecx
0x1400ae2c5  mov     [rbp+90h+var_C0], rax
0x1400ae2c9  lea     rcx, [rbp+90h+var_F0]
0x1400ae2cd  lea     rax, aSppsvcDefaultR; "SPPSVC Default RPC Interface"
0x1400ae2d4  mov     [rbp+90h+var_D0], 11h
0x1400ae2db  mov     [rbp+90h+var_B0], rax
0x1400ae2df  xorps   xmm0, xmm0
0x1400ae2e2  lea     rax, aNcalrpc; "ncalrpc"
0x1400ae2e9  movdqa  [rbp+90h+var_E0], xmm0
0x1400ae2ee  mov     [rsp+190h+var_138], rax
0x1400ae2f3  mov     edx, ebx
0x1400ae2f5  lea     rax, aSppctransporte; "SPPCTransportEndpoint-00001"
0x1400ae2fc  mov     [rbp+90h+var_CC], 4D2h
0x1400ae304  mov     [rsp+190h+var_130], rax
0x1400ae309  mov     rax, [rsp+190h+SecurityDescriptor]
0x1400ae30e  mov     [rsp+190h+var_128], rax
0x1400ae313  lea     rax, Protseq; "ncacn_hvsocket"
0x1400ae31a  mov     [rbp+90h+var_110], rax
0x1400ae31e  lea     rax, a9435cc561d9c49; "9435CC56-1D9C-4924-AC7D-B60A2C3520E1"
0x1400ae325  mov     [rbp+90h+var_108], rax
0x1400ae329  mov     eax, cs:dword_1404470A8
0x1400ae32f  neg     eax
0x1400ae331  mov     [rbp+90h+var_B8], 0
0x1400ae339  lea     rax, qword_1404470B0
0x1400ae340  mov     [rbp+90h+var_A8], 0
0x1400ae348  mov     [rsp+190h+var_158], rax
0x1400ae34d  sbb     r9d, r9d
0x1400ae350  neg     r9d
0x1400ae353  mov     [rsp+190h+var_160], 0
0x1400ae35c  add     r9d, ebx
0x1400ae35f  mov     [rsp+190h+var_168], 0
0x1400ae368  mov     [rsp+190h+var_140], 0
0x1400ae370  mov     [rsp+190h+var_118], 0
0x1400ae378  mov     [rbp+90h+var_100], 0
0x1400ae380  mov     [rsp+190h+var_170], 0FFFFFFFFh
0x1400ae388  call    cs:RpcServerInterfaceGroupCreateW
0x1400ae38e  mov     ecx, eax
0x1400ae390  lea     rdx, [rsp+190h+var_150]
0x1400ae395  call    sub_14006D2F8
0x1400ae39a  test    eax, eax
0x1400ae39c  jnz     short loc_1400AE3A4
0x1400ae39e  mov     ebx, [rsp+190h+var_150]
0x1400ae3a2  jmp     short loc_1400AE3CB
0x1400ae3a4  mov     rcx, cs:qword_1404470B0
0x1400ae3ab  mov     cs:dword_1404470AC, ebx
0x1400ae3b1  call    cs:RpcServerInterfaceGroupActivate
0x1400ae3b7  mov     ecx, eax
0x1400ae3b9  lea     rdx, [rsp+190h+var_150]
0x1400ae3be  call    sub_14006D2F8
0x1400ae3c3  mov     ebx, [rsp+190h+var_150]
0x1400ae3c7  test    eax, eax
0x1400ae3c9  jnz     short loc_1400AE3D2
0x1400ae3cb  mov     ecx, ebx
0x1400ae3cd  call    sub_14006DE60
0x1400ae3d2  test    ebx, ebx
0x1400ae3d4  jns     short loc_1400AE3DB
0x1400ae3d6  call    sub_1400AEAD0
0x1400ae3db  mov     ecx, ebx
0x1400ae3dd  call    sub_14007CFB4
0x1400ae3e2  lea     rcx, [rsp+190h+SecurityDescriptor]
0x1400ae3e7  call    sub_14006ADB4
0x1400ae3ec  mov     eax, ebx
0x1400ae3ee  mov     rcx, [rbp+90h+var_10]
0x1400ae3f5  xor     rcx, rsp; StackCookie
0x1400ae3f8  call    __security_check_cookie
0x1400ae3fd  mov     rbx, [rsp+190h+arg_0]
0x1400ae405  add     rsp, 190h
0x1400ae40c  pop     rbp
0x1400ae40d  retn
```
