# AcquireCredentialsHandleCommon(ushort *,void *,ulong,void *,void *,void (*)(void *,void *,ulong,void * *,long *),void *,_SecHandle *,_LARGE_INTEGER *,uchar)

- ea: `0x18000996c`
- end: `0x180009c38`
- name: `?AcquireCredentialsHandleCommon@@YAJPEAGPEAXK11P6AX11KPEAPEAXPEAJ@Z1PEAU_SecHandle@@PEAT_LARGE_INTEGER@@E@Z`
- size: `716`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, unsigned int, void *, void *, void (*)(void *, void *, unsigned int, void **, int *), void *, struct _SecHandle *, union _LARGE_INTEGER *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098b0`
- `0x180009910`

## callees

- `0x180007b58`
- `0x18000996c`
- `0x180009c90`
- `0x18001b088`
- `0x18001b14c`
- `0x18001b38c`
- `0x18001b678`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180009b2c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009b2c`
- `ntdll!RtlReleaseResource` at `0x180009b55`
- `ntdll!RtlReleaseResource` at `0x180009b84`
- `ntdll!RtlReleaseResource` at `0x180009b55`
- `ntdll!RtlReleaseResource` at `0x180009b84`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009a42`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009a96`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009a42`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180009a96`

## pseudocode

```c
__int64 __fastcall AcquireCredentialsHandleCommon(
        unsigned __int16 *a1,
        void *a2,
        unsigned int a3,
        void *a4,
        void *a5,
        void (*a6)(void *, void *, unsigned int, void **, int *),
        void *a7,
        struct _SecHandle *a8,
        union _LARGE_INTEGER *a9,
        char a10)
{
  __int64 result; // rax
  int v15; // r8d
  LPVOID v16; // rbx
  __int64 v17; // rax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // r8
  unsigned int v21; // r14d
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rdi
  __int64 v25; // rdi
  LPVOID lpTlsValue; // [rsp+50h] [rbp-41h] BYREF
  union _LARGE_INTEGER *v27; // [rsp+58h] [rbp-39h]
  void *v28; // [rsp+60h] [rbp-31h]
  void (*v29)(void *, void *, unsigned int, void **, int *); // [rsp+68h] [rbp-29h]
  void *v30; // [rsp+70h] [rbp-21h]
  __int64 v31; // [rsp+78h] [rbp-19h] BYREF
  ULONG_PTR v32; // [rsp+80h] [rbp-11h]

  v30 = a5;
  v29 = a6;
  v28 = a7;
  v27 = a9;
  lpTlsValue = 0;
  v32 = 0;
  if ( !a2 )
    return 2148074245LL;
  v31 = -1;
  if ( a10 )
  {
    result = SecLocatePackageExW(0, a2, &lpTlsValue);
    if ( (int)result < 0 )
      return result;
    v16 = lpTlsValue;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v15, *((_QWORD *)lpTlsValue + 13), a3);
    TlsSetValue(SecTlsPackage, v16);
    v17 = *((_QWORD *)v16 + 21);
  }
  else
  {
    result = SecLocatePackageExA(0);
    if ( (int)result < 0 )
      return result;
    v16 = lpTlsValue;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, *((_QWORD *)lpTlsValue + 13), a3);
    TlsSetValue(SecTlsPackage, lpTlsValue);
    v17 = *((_QWORD *)lpTlsValue + 20);
  }
  v21 = (*(__int64 (__fastcall **)(unsigned __int16 *, void *, _QWORD, void *, void *, void (*)(void *, void *, unsigned int, void **, int *), void *, __int64 *, union _LARGE_INTEGER *))(v17 + 24))(
          a1,
          a2,
          a3,
          a4,
          v30,
          v29,
          v28,
          &v31,
          v27);
  if ( !v21 )
  {
    v22 = v31;
    v23 = SecPackageListLockCount;
    if ( v31 == -1 )
      v22 = (__int64)v16;
    v31 = v22;
    while ( (*((_BYTE *)v16 + 36) & 0x10) == 0 )
    {
      v24 = 0;
      if ( v23 )
      {
        do
        {
          RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v24], 1u);
          v23 = SecPackageListLockCount;
          v24 = (unsigned int)(v24 + 1);
        }
        while ( (unsigned int)v24 < SecPackageListLockCount );
      }
      v25 = 0;
      if ( (*((_BYTE *)v16 + 36) & 0x10) == 0 )
      {
        *((_QWORD *)v16 + 6) = v31;
        *((_DWORD *)v16 + 9) |= 0x10u;
        if ( v23 )
        {
          do
          {
            RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v25]);
            v25 = (unsigned int)(v25 + 1);
          }
          while ( (unsigned int)v25 < SecPackageListLockCount );
        }
        goto LABEL_32;
      }
      if ( v23 )
      {
        do
        {
          RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v25]);
          v23 = SecPackageListLockCount;
          v25 = (unsigned int)(v25 + 1);
        }
        while ( (unsigned int)v25 < SecPackageListLockCount );
      }
    }
    v20 = v31;
    if ( *((_QWORD *)v16 + 6) != v31
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SPP(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids,
        *((_QWORD *)v16 + 13),
        v31,
        *((_QWORD *)v16 + 6));
    }
LABEL_32:
    a8->dwUpper = v32;
    a8->dwLower = (ULONG_PTR)v16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DPP(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v20, v21, a8->dwUpper, a8->dwLower);
  return v21;
}

```

## disassembly

```asm
0x18000996c  push    rbp
0x18000996e  push    rbx
0x18000996f  push    rsi
0x180009970  push    rdi
0x180009971  push    r12
0x180009973  push    r13
0x180009975  push    r14
0x180009977  push    r15
0x180009979  lea     rbp, [rsp-7]
0x18000997e  sub     rsp, 98h
0x180009985  mov     rax, cs:__security_cookie
0x18000998c  xor     rax, rsp
0x18000998f  mov     [rbp+3Fh+var_48], rax
0x180009993  mov     rax, [rbp+3Fh+arg_20]
0x180009997  xor     ebx, ebx
0x180009999  mov     r15, [rbp+3Fh+arg_38]
0x1800099a0  mov     r13, r9
0x1800099a3  mov     [rbp+3Fh+var_60], rax
0x1800099a7  mov     r14d, r8d
0x1800099aa  mov     rax, [rbp+3Fh+arg_28]
0x1800099ae  mov     rdi, rdx
0x1800099b1  mov     [rbp+3Fh+var_68], rax
0x1800099b5  mov     r12, rcx
0x1800099b8  mov     rax, [rbp+3Fh+arg_30]
0x1800099bc  mov     [rbp+3Fh+var_70], rax
0x1800099c0  mov     rax, [rbp+3Fh+arg_40]
0x1800099c7  mov     [rbp+3Fh+var_78], rax
0x1800099cb  mov     [rbp+3Fh+lpTlsValue], rbx
0x1800099cf  mov     [rbp+3Fh+var_50], rbx
0x1800099d3  test    rdx, rdx
0x1800099d6  jnz     short loc_1800099E2
0x1800099d8  mov     eax, 80090305h
0x1800099dd  jmp     loc_180009C18
0x1800099e2  xor     ecx, ecx; int
0x1800099e4  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFFh
0x1800099ec  lea     r8, [rbp+3Fh+lpTlsValue]
0x1800099f0  cmp     [rbp+3Fh+arg_48], bl
0x1800099f6  jz      short loc_180009A51
0x1800099f8  call    SecLocatePackageExW
0x1800099fd  test    eax, eax
0x1800099ff  js      loc_180009C18
0x180009a05  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a0c  lea     rsi, WPP_GLOBAL_Control
0x180009a13  mov     rbx, [rbp+3Fh+lpTlsValue]
0x180009a17  cmp     rcx, rsi
0x180009a1a  jz      short loc_180009A39
0x180009a1c  test    byte ptr [rcx+1Ch], 4
0x180009a20  jz      short loc_180009A39
0x180009a22  mov     r9, [rbx+68h]
0x180009a26  mov     edx, 0Dh
0x180009a2b  mov     rcx, [rcx+10h]
0x180009a2f  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180009a34  call    WPP_SF_Sd
0x180009a39  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180009a3f  mov     rdx, rbx; lpTlsValue
0x180009a42  call    cs:__imp_TlsSetValue
0x180009a48  mov     rax, [rbx+0A8h]
0x180009a4f  jmp     short loc_180009AA3
0x180009a51  call    SecLocatePackageExA
0x180009a56  test    eax, eax
0x180009a58  js      loc_180009C18
0x180009a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a65  lea     rsi, WPP_GLOBAL_Control
0x180009a6c  mov     rbx, [rbp+3Fh+lpTlsValue]
0x180009a70  cmp     rcx, rsi
0x180009a73  jz      short loc_180009A8D
0x180009a75  test    byte ptr [rcx+1Ch], 4
0x180009a79  jz      short loc_180009A8D
0x180009a7b  mov     r9, [rbx+68h]
0x180009a7f  mov     rcx, [rcx+10h]
0x180009a83  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x180009a88  call    WPP_SF_sd
0x180009a8d  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180009a93  mov     rdx, rbx; lpTlsValue
0x180009a96  call    cs:__imp_TlsSetValue
0x180009a9c  mov     rax, [rbx+0A0h]
0x180009aa3  mov     rcx, [rbp+3Fh+var_78]
0x180009aa7  mov     r9, r13
0x180009aaa  mov     rax, [rax+18h]
0x180009aae  mov     r8d, r14d
0x180009ab1  mov     [rsp+0D0h+var_90], rcx
0x180009ab6  mov     rdx, rdi
0x180009ab9  lea     rcx, [rbp+3Fh+var_58]
0x180009abd  mov     [rsp+0D0h+var_98], rcx
0x180009ac2  mov     rcx, [rbp+3Fh+var_70]
0x180009ac6  mov     [rsp+0D0h+var_A0], rcx
0x180009acb  mov     rcx, [rbp+3Fh+var_68]
0x180009acf  mov     [rsp+0D0h+var_A8], rcx
0x180009ad4  mov     rcx, [rbp+3Fh+var_60]
0x180009ad8  mov     [rsp+0D0h+var_B0], rcx
0x180009add  mov     rcx, r12
0x180009ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae5  mov     r14d, eax
0x180009ae8  mov     r12d, 10h
0x180009aee  test    eax, eax
0x180009af0  jnz     loc_180009BE3
0x180009af6  mov     rax, [rbp+3Fh+var_58]
0x180009afa  lea     r13, SecPackageListLock
0x180009b01  mov     ecx, cs:SecPackageListLockCount
0x180009b07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009b0b  cmovz   rax, rbx
0x180009b0f  mov     [rbp+3Fh+var_58], rax
0x180009b13  test    [rbx+24h], r12b
0x180009b17  jnz     short loc_180009B96
0x180009b19  xor     edi, edi
0x180009b1b  test    ecx, ecx
0x180009b1d  jz      short loc_180009B3E
0x180009b1f  lea     rcx, [rdi+rdi*2]
0x180009b23  mov     dl, 1; Wait
0x180009b25  shl     rcx, 5
0x180009b29  add     rcx, r13; Resource
0x180009b2c  call    cs:__imp_RtlAcquireResourceExclusive
0x180009b32  mov     ecx, cs:SecPackageListLockCount
0x180009b38  inc     edi
0x180009b3a  cmp     edi, ecx
0x180009b3c  jb      short loc_180009B1F
0x180009b3e  xor     edi, edi
0x180009b40  test    [rbx+24h], r12b
0x180009b44  jz      short loc_180009B69
0x180009b46  test    ecx, ecx
0x180009b48  jz      short loc_180009B13
0x180009b4a  lea     rcx, [rdi+rdi*2]
0x180009b4e  shl     rcx, 5
0x180009b52  add     rcx, r13; Resource
0x180009b55  call    cs:__imp_RtlReleaseResource
0x180009b5b  mov     ecx, cs:SecPackageListLockCount
0x180009b61  inc     edi
0x180009b63  cmp     edi, ecx
0x180009b65  jb      short loc_180009B4A
0x180009b67  jmp     short loc_180009B13
0x180009b69  mov     rax, [rbp+3Fh+var_58]
0x180009b6d  mov     [rbx+30h], rax
0x180009b71  or      [rbx+24h], r12d
0x180009b75  test    ecx, ecx
0x180009b77  jz      short loc_180009BD8
0x180009b79  lea     rcx, [rdi+rdi*2]
0x180009b7d  shl     rcx, 5
0x180009b81  add     rcx, r13; Resource
0x180009b84  call    cs:__imp_RtlReleaseResource
0x180009b8a  inc     edi
0x180009b8c  cmp     edi, cs:SecPackageListLockCount
0x180009b92  jb      short loc_180009B79
0x180009b94  jmp     short loc_180009BD8
0x180009b96  mov     rax, [rbx+30h]
0x180009b9a  mov     r8, [rbp+3Fh+var_58]
0x180009b9e  cmp     rax, r8
0x180009ba1  jz      short loc_180009BD8
0x180009ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009baa  cmp     rcx, rsi
0x180009bad  jz      short loc_180009BD8
0x180009baf  test    byte ptr [rcx+1Ch], 1
0x180009bb3  jz      short loc_180009BD8
0x180009bb5  mov     r9, [rbx+68h]
0x180009bb9  mov     edx, 0Fh
0x180009bbe  mov     rcx, [rcx+10h]
0x180009bc2  mov     [rsp+0D0h+var_A8], rax
0x180009bc7  mov     [rsp+0D0h+var_B0], r8
0x180009bcc  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x180009bd3  call    WPP_SF_SPP
0x180009bd8  mov     rax, [rbp+3Fh+var_50]
0x180009bdc  mov     [r15+8], rax
0x180009be0  mov     [r15], rbx
0x180009be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bea  cmp     rcx, rsi
0x180009bed  jz      short loc_180009C15
0x180009bef  test    byte ptr [rcx+1Ch], 4
0x180009bf3  jz      short loc_180009C15
0x180009bf5  mov     rax, [r15]
0x180009bf8  mov     edx, r12d
0x180009bfb  mov     rcx, [rcx+10h]
0x180009bff  mov     r9d, r14d
0x180009c02  mov     [rsp+0D0h+var_A8], rax
0x180009c07  mov     rax, [r15+8]
0x180009c0b  mov     [rsp+0D0h+var_B0], rax
0x180009c10  call    WPP_SF_DPP
0x180009c15  mov     eax, r14d
0x180009c18  mov     rcx, [rbp+3Fh+var_48]
0x180009c1c  xor     rcx, rsp; StackCookie
0x180009c1f  call    __security_check_cookie
0x180009c24  add     rsp, 98h
0x180009c2b  pop     r15
0x180009c2d  pop     r14
0x180009c2f  pop     r13
0x180009c31  pop     r12
0x180009c33  pop     rdi
0x180009c34  pop     rsi
0x180009c35  pop     rbx
0x180009c36  pop     rbp
0x180009c37  retn
```
