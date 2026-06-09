# CRpcDispatcher::Create(void)

- ea: `0x180032434`
- end: `0x1800325d5`
- name: `?Create@CRpcDispatcher@@AEAAJXZ`
- size: `417`
- prototype: `__int64 __fastcall(CRpcDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d378`

## callees

- `0x180032434`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800325ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032466`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800324a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032466`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800324a0`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180032575`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x180032575`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180032594`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180032594`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRpcDispatcher::Create(CRpcDispatcher *this)
{
  signed int LastError; // eax
  signed int v3; // ebx
  int v4; // eax
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v7; // [rsp+48h] [rbp-B8h]
  __int64 v8; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+60h] [rbp-A0h]
  int v11; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v12; // [rsp+78h] [rbp-88h]
  __int128 v13; // [rsp+80h] [rbp-80h]
  int v14; // [rsp+90h] [rbp-70h]
  __int64 v15; // [rsp+94h] [rbp-6Ch]
  __int64 v16; // [rsp+A0h] [rbp-60h]
  __int64 v17; // [rsp+A8h] [rbp-58h]
  const WCHAR *v18; // [rsp+B0h] [rbp-50h]
  PSECURITY_DESCRIPTOR v19; // [rsp+B8h] [rbp-48h]
  int v20; // [rsp+C0h] [rbp-40h]
  __int64 *v21; // [rsp+C8h] [rbp-38h]
  __int128 v22; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+E0h] [rbp-20h]
  __int64 v24; // [rsp+E4h] [rbp-1Ch]
  __int64 v25; // [rsp+F0h] [rbp-10h]
  __int64 v26; // [rsp+F8h] [rbp-8h]
  const WCHAR *v27; // [rsp+100h] [rbp+0h]
  PSECURITY_DESCRIPTOR v28; // [rsp+108h] [rbp+8h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+138h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp+40h] BYREF

  SecurityDescriptor = 0;
  hMem = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)(A;;GA;;;AC)", 1u, &SecurityDescriptor, 0)
    && ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;WD)(A;;GA;;;AC)", 1u, &hMem, 0) )
  {
    v11 = 0;
    v14 = 32;
    v23 = 32;
    v18 = L"wbiosrvc";
    v12 = qword_1800D3380;
    v19 = hMem;
    v28 = hMem;
    v3 = 0;
    v21 = qword_1800D33E0;
    v7 = L"ncalrpc";
    v9 = SecurityDescriptor;
    v27 = L"wbiosrvc";
    v13 = 0;
    v15 = 1234;
    v16 = 0;
    v17 = 0;
    v20 = 0;
    v22 = 0;
    v24 = 1234;
    v25 = 0;
    v26 = 0;
    v6 = 0;
    v8 = 0;
    v10 = 10;
    v4 = RpcServerInterfaceGroupCreateW(&v11, 2, &v6);
    if ( !v4 )
      goto LABEL_10;
    v3 = v4 | 0x80010000;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v3 < 0 && *((_QWORD *)this + 2) )
  {
    RpcServerInterfaceGroupClose();
    *((_QWORD *)this + 2) = 0;
  }
LABEL_10:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180032434  mov     [rsp-8+arg_0], rbx
0x180032439  push    rbp
0x18003243a  push    rsi
0x18003243b  push    rdi
0x18003243c  lea     rbp, [rsp-10h]
0x180032441  sub     rsp, 110h
0x180032448  xor     esi, esi
0x18003244a  lea     r8, [rbp+20h+SecurityDescriptor]; SecurityDescriptor
0x18003244e  mov     rdi, rcx
0x180032451  mov     [rbp+20h+SecurityDescriptor], rsi
0x180032455  xor     r9d, r9d; SecurityDescriptorSize
0x180032458  mov     [rbp+20h+hMem], rsi
0x18003245c  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)(A;;GA;;;AC)"
0x180032463  lea     edx, [rsi+1]; StringSDRevision
0x180032466  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003246c  test    eax, eax
0x18003246e  jnz     short loc_18003248E
0x180032470  call    cs:__imp_GetLastError
0x180032476  mov     ebx, eax
0x180032478  test    eax, eax
0x18003247a  jle     loc_180032587
0x180032480  movzx   ebx, ax
0x180032483  or      ebx, 80070000h
0x180032489  jmp     loc_180032587
0x18003248e  xor     r9d, r9d; SecurityDescriptorSize
0x180032491  lea     r8, [rbp+20h+hMem]; SecurityDescriptor
0x180032495  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;WD)(A;;GA;;;AC)"
0x18003249c  lea     edx, [r9+1]; StringSDRevision
0x1800324a0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800324a6  test    eax, eax
0x1800324a8  jz      short loc_180032470
0x1800324aa  mov     r9d, 20h ; ' '
0x1800324b0  mov     [rsp+120h+var_B0], esi
0x1800324b4  lea     rdx, ServiceName; "wbiosrvc"
0x1800324bb  mov     [rbp+20h+var_90], r9d
0x1800324bf  xorps   xmm0, xmm0
0x1800324c2  mov     [rbp+20h+var_40], r9d
0x1800324c6  lea     rax, qword_1800D3380
0x1800324cd  mov     [rbp+20h+var_70], rdx
0x1800324d1  mov     [rsp+120h+var_A8], rax
0x1800324d6  lea     rcx, qword_1800D33E0
0x1800324dd  mov     rax, [rbp+20h+hMem]
0x1800324e1  lea     r8, [rsp+120h+var_E0]
0x1800324e6  mov     [rbp+20h+var_68], rax
0x1800324ea  mov     r9d, 1
0x1800324f0  mov     [rbp+20h+var_18], rax
0x1800324f4  mov     ebx, esi
0x1800324f6  lea     rax, ProtSeq; "ncalrpc"
0x1800324fd  mov     [rbp+20h+var_58], rcx
0x180032501  mov     [rsp+120h+var_D8], rax
0x180032506  lea     rcx, [rsp+120h+var_B0]
0x18003250b  mov     rax, [rbp+20h+SecurityDescriptor]
0x18003250f  mov     [rsp+120h+var_C8], rax
0x180032514  lea     rax, [rdi+10h]
0x180032518  mov     [rsp+120h+var_E8], rax
0x18003251d  mov     [rsp+120h+var_F0], rsi
0x180032522  mov     [rbp+20h+var_20], rdx
0x180032526  lea     edx, [r9+1]
0x18003252a  mov     [rsp+120h+var_F8], rsi
0x18003252f  mov     [rsp+120h+var_100], 0FFFFFFFFh
0x180032537  movdqa  [rbp+20h+var_A0], xmm0
0x18003253c  mov     [rbp+20h+var_8C], 4D2h
0x180032544  mov     [rbp+20h+var_80], rsi
0x180032548  mov     [rbp+20h+var_78], rsi
0x18003254c  mov     [rbp+20h+var_60], esi
0x18003254f  movdqa  [rbp+20h+var_50], xmm0
0x180032554  mov     [rbp+20h+var_3C], 4D2h
0x18003255c  mov     [rbp+20h+var_30], rsi
0x180032560  mov     [rbp+20h+var_28], rsi
0x180032564  mov     [rsp+120h+var_E0], esi
0x180032568  mov     [rsp+120h+var_D0], rsi
0x18003256d  mov     [rsp+120h+var_C0], 0Ah
0x180032575  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18003257b  test    eax, eax
0x18003257d  jz      short loc_18003259E
0x18003257f  mov     ebx, eax
0x180032581  or      ebx, 80010000h
0x180032587  test    ebx, ebx
0x180032589  jns     short loc_18003259E
0x18003258b  mov     rcx, [rdi+10h]
0x18003258f  test    rcx, rcx
0x180032592  jz      short loc_18003259E
0x180032594  call    cs:__imp_RpcServerInterfaceGroupClose
0x18003259a  mov     [rdi+10h], rsi
0x18003259e  mov     rcx, [rbp+20h+hMem]; hMem
0x1800325a2  test    rcx, rcx
0x1800325a5  jz      short loc_1800325B1
0x1800325a7  call    cs:__imp_LocalFree
0x1800325ad  mov     [rbp+20h+hMem], rsi
0x1800325b1  mov     rcx, [rbp+20h+SecurityDescriptor]; hMem
0x1800325b5  test    rcx, rcx
0x1800325b8  jz      short loc_1800325C0
0x1800325ba  call    cs:__imp_LocalFree
0x1800325c0  mov     eax, ebx
0x1800325c2  mov     rbx, [rsp+120h+arg_0]
0x1800325ca  add     rsp, 110h
0x1800325d1  pop     rdi
0x1800325d2  pop     rsi
0x1800325d3  pop     rbp
0x1800325d4  retn
```
