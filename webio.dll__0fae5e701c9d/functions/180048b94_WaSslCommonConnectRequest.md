# WaSslCommonConnectRequest

- ea: `0x180048b94`
- end: `0x180048fc5`
- name: `WaSslCommonConnectRequest`
- size: `1073`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048ac0`
- `0x18008f680`

## callees

- `0x18000fc1c`
- `0x18000ff50`
- `0x18001a450`
- `0x180048b94`
- `0x180048fcc`
- `0x1800490a0`
- `0x1800722f0`
- `0x180096758`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f17`

## pseudocode

```c
__int64 __fastcall WaSslCommonConnectRequest(
        volatile signed __int32 *lpMem,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        _QWORD *a9,
        char a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  char v15; // si
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  __int64 v17; // rdx
  int v18; // r8d
  unsigned int CredentialsHandle; // ebx
  __int64 v20; // rcx
  char v22; // al
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v27; // [rsp+90h] [rbp-58h] BYREF
  unsigned __int8 v28; // [rsp+98h] [rbp-50h] BYREF
  unsigned __int8 v29; // [rsp+99h] [rbp-4Fh] BYREF
  unsigned __int8 v30; // [rsp+9Ah] [rbp-4Eh] BYREF
  unsigned __int8 v31; // [rsp+9Bh] [rbp-4Dh] BYREF
  _BYTE v32[4]; // [rsp+9Ch] [rbp-4Ch] BYREF

  v15 = 1;
  *a9 = 0;
  *(_QWORD *)(a2 + 168) = a3;
  *(_QWORD *)(a2 + 176) = a4;
  *(_QWORD *)(a2 + 40) = a5;
  v27 = 0;
  v32[0] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  _InterlockedAdd((volatile signed __int32 *)(a3 + 4), 1u);
  _InterlockedAdd((volatile signed __int32 *)(a4 + 4), 1u);
  _InterlockedAdd((volatile signed __int32 *)(a5 + 4), 1u);
  WaSslSuspendSender(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
  v16 = (struct _RTL_CRITICAL_SECTION *)(a2 + 1256);
  if ( *(_BYTE *)(a2 + 1433) )
  {
    v15 = 0;
    LeaveCriticalSection(v16);
    CredentialsHandle = 5023;
    goto LABEL_7;
  }
  *(_QWORD *)(a2 + 1096) = a11;
  *(_QWORD *)(a2 + 1104) = a13;
  *(_DWORD *)(a2 + 1088) = a8;
  *(_QWORD *)(a2 + 1120) = 0;
  *(_BYTE *)(a2 + 1112) = 1;
  *(_DWORD *)(a2 + 1080) = a6;
  *(_DWORD *)(a2 + 1084) = a7;
  LeaveCriticalSection(v16);
  _InterlockedAdd(lpMem + 1, 1u);
  if ( !a10 )
  {
    v17 = 0;
    v18 = 0;
LABEL_4:
    if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64, int, int, int, _QWORD *, __int64, int, __int64, volatile signed __int32 *))(*(_QWORD *)(a2 + 16) + 24LL))(
           lpMem,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           v17,
           v18,
           a12,
           lpMem) != 997 )
      WaSslCommonConnectCompletion((LPVOID)lpMem);
    CredentialsHandle = 997;
    v15 = 0;
    goto LABEL_7;
  }
  if ( !*(_QWORD *)(a2 + 64) )
  {
    CredentialsHandle = WaSslRetrieveCredentialsHandle(a2);
    if ( CredentialsHandle )
    {
LABEL_7:
      v20 = v27;
      goto LABEL_8;
    }
  }
  CredentialsHandle = WapSslInitializeSecurityContext(a2, &v27, v32, &v28, &v29, &v30, &v31);
  v22 = xmmword_1800AD720;
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    WPP_SF_Dlllll(v30, v32[0], v29, CredentialsHandle, v28, v29, v32[0], v30, v31);
    v22 = xmmword_1800AD720;
  }
  v20 = v27;
  if ( v27 )
  {
    v24 = *(_QWORD *)(v27 + 48);
    if ( v24 )
    {
      if ( (v22 & 8) != 0 )
      {
        WPP_SF_d(1027, 44, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, *(unsigned int *)(v24 + 16));
        v20 = v27;
      }
    }
  }
  if ( !CredentialsHandle )
  {
    if ( !v28 && !v29 && !v30 && !v31 )
    {
      v23 = *(_QWORD *)(v20 + 48);
      if ( v23 )
      {
        if ( *(_DWORD *)(v20 + 56) == 1 )
        {
          v17 = *(_QWORD *)(v23 + 8);
          v18 = *(_DWORD *)(v23 + 16);
          *(_BYTE *)(a2 + 1233) = 1;
          *(_QWORD *)(a2 + 1224) = v20;
          v27 = 0;
          goto LABEL_4;
        }
      }
    }
    CredentialsHandle = 87;
  }
LABEL_8:
  if ( v20 )
    WaDestroySslIoContext();
  if ( v15 )
  {
    WaSslCommonConnectCompletion((LPVOID)lpMem);
    return 997;
  }
  else if ( CredentialsHandle != 997 && CredentialsHandle != 234 && (xmmword_1800AD710 & 8) != 0 )
  {
    WPP_SF_d(515, 12, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, CredentialsHandle);
  }
  return CredentialsHandle;
}

```

## disassembly

```asm
0x180048b94  mov     r11, rsp
0x180048b97  push    rbx
0x180048b98  push    rsi
0x180048b99  push    rdi
0x180048b9a  push    r12
0x180048b9c  push    r13
0x180048b9e  push    r14
0x180048ba0  push    r15
0x180048ba2  sub     rsp, 0B0h
0x180048ba9  mov     rax, cs:__security_cookie
0x180048bb0  xor     rax, rsp
0x180048bb3  mov     [rsp+0E8h+var_48], rax
0x180048bbb  mov     r15, [rsp+0E8h+arg_40]
0x180048bc3  mov     rdi, rdx
0x180048bc6  mov     rdx, [rsp+0E8h+arg_58]
0x180048bce  mov     rax, r8
0x180048bd1  mov     r14, rcx
0x180048bd4  mov     [rsp+0E8h+var_68], r9
0x180048bdc  mov     rcx, [rsp+0E8h+arg_20]
0x180048be4  mov     esi, 1
0x180048be9  mov     qword ptr [r15], 0
0x180048bf0  mov     [rdi+0A8h], rax
0x180048bf7  mov     [rdi+0B0h], r9
0x180048bfe  mov     [rdi+28h], rcx
0x180048c02  mov     [rsp+0E8h+var_60], rax
0x180048c0a  mov     [rsp+0E8h+var_70], rcx
0x180048c0f  mov     [rsp+0E8h+var_78], rdx
0x180048c14  mov     qword ptr [r11-58h], 0
0x180048c1c  mov     byte ptr [r11-4Ch], 0
0x180048c21  mov     byte ptr [r11-50h], 0
0x180048c26  mov     byte ptr [r11-4Fh], 0
0x180048c2b  mov     byte ptr [r11-4Eh], 0
0x180048c30  mov     byte ptr [r11-4Dh], 0
0x180048c35  lock add [r8+4], esi
0x180048c3a  lock add [r9+4], esi
0x180048c3f  lock add [rcx+4], esi
0x180048c43  mov     rcx, rdi
0x180048c46  call    WaSslSuspendSender
0x180048c4b  lea     rbx, [rdi+4E8h]
0x180048c52  mov     rcx, rbx; lpCriticalSection
0x180048c55  call    cs:__imp_EnterCriticalSection
0x180048c5c  nop     dword ptr [rax+rax+00h]
0x180048c61  cmp     byte ptr [rdi+599h], 0
0x180048c68  mov     rcx, rbx; lpCriticalSection
0x180048c6b  jnz     loc_180048F14
0x180048c71  mov     rax, [rsp+0E8h+arg_50]
0x180048c79  mov     r12d, [rsp+0E8h+arg_28]
0x180048c81  mov     r13d, [rsp+0E8h+arg_30]
0x180048c89  mov     [rdi+448h], rax
0x180048c90  mov     rax, [rsp+0E8h+arg_60]
0x180048c98  mov     [rdi+450h], rax
0x180048c9f  mov     eax, [rsp+0E8h+arg_38]
0x180048ca6  mov     [rdi+440h], eax
0x180048cac  mov     qword ptr [rdi+460h], 0
0x180048cb7  mov     [rdi+458h], sil
0x180048cbe  mov     [rdi+438h], r12d
0x180048cc5  mov     [rdi+43Ch], r13d
0x180048ccc  call    cs:__imp_LeaveCriticalSection
0x180048cd3  nop     dword ptr [rax+rax+00h]
0x180048cd8  lock add [r14+4], esi
0x180048cdd  cmp     [rsp+0E8h+arg_48], 0
0x180048ce5  jnz     loc_180048DD3
0x180048ceb  xor     edx, edx
0x180048ced  xor     r8d, r8d
0x180048cf0  mov     rcx, [rsp+0E8h+var_78]
0x180048cf5  mov     rax, [rdi+10h]
0x180048cf9  mov     r9, [rsp+0E8h+var_70]
0x180048cfe  mov     [rsp+0E8h+var_90], r14
0x180048d03  mov     [rsp+0E8h+var_98], rcx
0x180048d08  mov     ecx, [rsp+0E8h+arg_38]
0x180048d0f  mov     rax, [rax+18h]
0x180048d13  mov     [rsp+0E8h+var_A0], r8d
0x180048d18  mov     r8, [rsp+0E8h+var_68]
0x180048d20  mov     [rsp+0E8h+var_A8], rdx
0x180048d25  mov     rdx, [rsp+0E8h+var_60]
0x180048d2d  mov     [rsp+0E8h+var_B0], r15
0x180048d32  mov     dword ptr [rsp+0E8h+var_B8], ecx
0x180048d36  mov     rcx, r14
0x180048d39  mov     dword ptr [rsp+0E8h+var_C0], r13d
0x180048d3e  mov     dword ptr [rsp+0E8h+var_C8], r12d
0x180048d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d48  cmp     eax, 3E5h
0x180048d4d  jnz     loc_180048F8A
0x180048d53  mov     ebx, 3E5h
0x180048d58  xor     sil, sil
0x180048d5b  mov     rcx, [rsp+0E8h+var_58]
0x180048d63  test    rcx, rcx
0x180048d66  jnz     loc_180048FA0
0x180048d6c  test    ebx, ebx
0x180048d6e  jnz     short loc_180048D96
0x180048d70  mov     eax, ebx
0x180048d72  mov     rcx, [rsp+0E8h+var_48]
0x180048d7a  xor     rcx, rsp; StackCookie
0x180048d7d  call    __security_check_cookie
0x180048d82  add     rsp, 0B0h
0x180048d89  pop     r15
0x180048d8b  pop     r14
0x180048d8d  pop     r13
0x180048d8f  pop     r12
0x180048d91  pop     rdi
0x180048d92  pop     rsi
0x180048d93  pop     rbx
0x180048d94  retn
0x180048d96  test    sil, sil
0x180048d99  jnz     loc_180048FAA
0x180048d9f  cmp     ebx, 3E5h
0x180048da5  jz      short loc_180048D70
0x180048da7  cmp     ebx, 0EAh
0x180048dad  jz      short loc_180048D70
0x180048daf  test    byte ptr cs:xmmword_1800AD710, 8
0x180048db6  jz      short loc_180048D70
0x180048db8  mov     edx, 0Ch
0x180048dbd  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x180048dc4  mov     ecx, 203h
0x180048dc9  mov     r9d, ebx
0x180048dcc  call    WPP_SF_d
0x180048dd1  jmp     short loc_180048D70
0x180048dd3  cmp     qword ptr [rdi+40h], 0
0x180048dd8  jz      loc_180048EFD
0x180048dde  lea     rax, [rsp+0E8h+var_4D]
0x180048de6  mov     rcx, rdi
0x180048de9  mov     [rsp+0E8h+var_B8], rax
0x180048dee  lea     r9, [rsp+0E8h+var_50]
0x180048df6  lea     rax, [rsp+0E8h+var_4E]
0x180048dfe  mov     [rsp+0E8h+var_C0], rax
0x180048e03  lea     r8, [rsp+0E8h+var_4C]
0x180048e0b  lea     rax, [rsp+0E8h+var_4F]
0x180048e13  lea     rdx, [rsp+0E8h+var_58]
0x180048e1b  mov     [rsp+0E8h+var_C8], rax
0x180048e20  call    WapSslInitializeSecurityContext
0x180048e25  mov     ebx, eax
0x180048e27  mov     al, byte ptr cs:xmmword_1800AD720
0x180048e2d  test    al, 8
0x180048e2f  jnz     loc_180048F2D
0x180048e35  mov     rcx, [rsp+0E8h+var_58]
0x180048e3d  xor     r10d, r10d
0x180048e40  test    rcx, rcx
0x180048e43  jnz     short loc_180048EBE
0x180048e45  test    ebx, ebx
0x180048e47  jnz     loc_180048D63
0x180048e4d  cmp     [rsp+0E8h+var_50], r10b
0x180048e55  jnz     loc_180048F80
0x180048e5b  cmp     [rsp+0E8h+var_4F], r10b
0x180048e63  jnz     loc_180048F80
0x180048e69  cmp     [rsp+0E8h+var_4E], r10b
0x180048e71  jnz     loc_180048F80
0x180048e77  cmp     [rsp+0E8h+var_4D], r10b
0x180048e7f  jnz     loc_180048F80
0x180048e85  mov     rax, [rcx+30h]
0x180048e89  test    rax, rax
0x180048e8c  jz      loc_180048F80
0x180048e92  cmp     [rcx+38h], esi
0x180048e95  jnz     loc_180048F80
0x180048e9b  mov     rdx, [rax+8]
0x180048e9f  mov     r8d, [rax+10h]
0x180048ea3  mov     [rdi+4D1h], sil
0x180048eaa  mov     [rdi+4C8h], rcx
0x180048eb1  mov     [rsp+0E8h+var_58], r10
0x180048eb9  jmp     loc_180048CF0
0x180048ebe  mov     r9, [rcx+30h]
0x180048ec2  test    r9, r9
0x180048ec5  jz      loc_180048E45
0x180048ecb  test    al, 8
0x180048ecd  jz      loc_180048E45
0x180048ed3  mov     r9d, [r9+10h]
0x180048ed7  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x180048ede  mov     edx, 2Ch ; ','
0x180048ee3  mov     ecx, 403h
0x180048ee8  call    WPP_SF_d
0x180048eed  mov     rcx, [rsp+0E8h+var_58]
0x180048ef5  xor     r10d, r10d
0x180048ef8  jmp     loc_180048E45
0x180048efd  mov     rcx, rdi
0x180048f00  call    WaSslRetrieveCredentialsHandle
0x180048f05  mov     ebx, eax
0x180048f07  test    eax, eax
0x180048f09  jz      loc_180048DDE
0x180048f0f  jmp     loc_180048D5B
0x180048f14  xor     sil, sil
0x180048f17  call    cs:__imp_LeaveCriticalSection
0x180048f1e  nop     dword ptr [rax+rax+00h]
0x180048f23  mov     ebx, 139Fh
0x180048f28  jmp     loc_180048D5B
0x180048f2d  movzx   r9d, [rsp+0E8h+var_50]
0x180048f36  movzx   eax, [rsp+0E8h+var_4D]
0x180048f3e  movzx   ecx, [rsp+0E8h+var_4E]
0x180048f46  movzx   edx, [rsp+0E8h+var_4C]
0x180048f4e  movzx   r8d, [rsp+0E8h+var_4F]
0x180048f57  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180048f5b  mov     dword ptr [rsp+0E8h+var_B0], ecx
0x180048f5f  mov     dword ptr [rsp+0E8h+var_B8], edx
0x180048f63  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x180048f68  mov     dword ptr [rsp+0E8h+var_C8], r9d
0x180048f6d  mov     r9d, ebx
0x180048f70  call    WPP_SF_Dlllll
0x180048f75  mov     al, byte ptr cs:xmmword_1800AD720
0x180048f7b  jmp     loc_180048E35
0x180048f80  mov     ebx, 57h ; 'W'
0x180048f85  jmp     loc_180048D63
0x180048f8a  mov     r9, [r15]
0x180048f8d  mov     r8d, eax
0x180048f90  mov     rdx, rdi
0x180048f93  mov     rcx, r14; lpMem
0x180048f96  call    WaSslCommonConnectCompletion
0x180048f9b  jmp     loc_180048D53
0x180048fa0  call    WaDestroySslIoContext
0x180048fa5  jmp     loc_180048D6C
0x180048faa  xor     r9d, r9d
0x180048fad  mov     r8d, ebx
0x180048fb0  mov     rdx, rdi
0x180048fb3  mov     rcx, r14; lpMem
0x180048fb6  call    WaSslCommonConnectCompletion
0x180048fbb  mov     ebx, 3E5h
0x180048fc0  jmp     loc_180048D70
```
