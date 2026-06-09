# SamHandleForDomain(void *,ulong,ulong,void * *,void * *)

- ea: `0x180008b48`
- end: `0x180008ca6`
- name: `?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z`
- size: `350`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x180008b48`
- `0x180008cac`
- `0x1800090dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008c8d`
- `SAMLIB!SamOpenDomain` at `0x180008c04`
- `SAMLIB!SamOpenDomain` at `0x180008c04`
- `SAMLIB!SamConnect` at `0x180008be2`
- `SAMLIB!SamConnect` at `0x180008be2`
- `SAMLIB!SamCloseHandle` at `0x180008c26`
- `SAMLIB!SamCloseHandle` at `0x180008c26`

## pseudocode

```c
__int64 __fastcall SamHandleForDomain(void *a1, unsigned int a2, unsigned int a3, void **a4, void **a5)
{
  void **v5; // r14
  void *v9; // rdi
  int v10; // r15d
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[4]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-18h]
  LPVOID pv; // [rsp+A0h] [rbp+48h] BYREF

  pv = a1;
  v5 = a5;
  *a4 = 0;
  v9 = a1;
  *v5 = 0;
  if ( a1 )
  {
    v11 = 0;
    v10 = 0;
  }
  else
  {
    v10 = 1;
    v11 = CSGetAccountDomainSid(&pv);
    v9 = pv;
  }
  if ( v11 >= 0 )
  {
    v17[0] = 48;
    pv = 0;
    memset(&v17[1], 0, 24);
    v18 = 0;
    v12 = ((__int64 (__fastcall *)(_QWORD, LPVOID *, _QWORD, _QWORD *))SamConnect)(0, &pv, a2, v17);
    if ( v12 < 0 )
    {
      v11 = v12 | 0x10000000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 35;
        goto LABEL_14;
      }
    }
    else
    {
      a5 = 0;
      v13 = SamOpenDomain(pv, a3, v9, &a5);
      if ( v13 >= 0 )
      {
        v11 = 0;
        *v5 = a5;
        *a4 = pv;
        goto LABEL_15;
      }
      SamCloseHandle(pv);
      v11 = v13 | 0x10000000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 34;
LABEL_14:
        WPP_SF_D(v14[2], v15, &WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v11);
      }
    }
  }
LABEL_15:
  if ( v10 )
    CoTaskMemFree(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008b48  mov     [rsp-40h+pv], rcx
0x180008b4d  push    rbp
0x180008b4e  push    rbx
0x180008b4f  push    rsi
0x180008b50  push    rdi
0x180008b51  push    r12
0x180008b53  push    r13
0x180008b55  push    r14
0x180008b57  push    r15
0x180008b59  mov     rbp, rsp
0x180008b5c  sub     rsp, 58h
0x180008b60  mov     r14, [rbp+arg_20]
0x180008b64  mov     rsi, r9
0x180008b67  mov     qword ptr [r9], 0
0x180008b6e  mov     r12d, r8d
0x180008b71  mov     r13d, edx
0x180008b74  mov     rdi, rcx
0x180008b77  mov     qword ptr [r14], 0
0x180008b7e  test    rcx, rcx
0x180008b81  jnz     short loc_180008B98
0x180008b83  lea     rcx, [rbp+pv]
0x180008b87  call    CSGetAccountDomainSid
0x180008b8c  lea     r15d, [rdi+1]
0x180008b90  mov     ebx, eax
0x180008b92  mov     rdi, [rbp+pv]
0x180008b96  jmp     short loc_180008B9D
0x180008b98  xor     ebx, ebx
0x180008b9a  xor     r15d, r15d
0x180008b9d  test    ebx, ebx
0x180008b9f  js      loc_180008C85
0x180008ba5  xorps   xmm0, xmm0
0x180008ba8  mov     [rbp+var_38], 30h ; '0'
0x180008bb0  lea     r9, [rbp+var_38]
0x180008bb4  mov     [rbp+var_20], 0
0x180008bbc  mov     r8d, r13d
0x180008bbf  mov     [rbp+pv], 0
0x180008bc7  lea     rdx, [rbp+pv]
0x180008bcb  mov     [rbp+var_30], 0
0x180008bd3  xor     ecx, ecx
0x180008bd5  mov     [rbp+var_28], 0
0x180008bdd  movdqu  [rbp+var_18], xmm0
0x180008be2  call    cs:__imp_SamConnect
0x180008be8  mov     ebx, eax
0x180008bea  test    eax, eax
0x180008bec  js      short loc_180008C50
0x180008bee  mov     rcx, [rbp+pv]
0x180008bf2  lea     r9, [rbp+arg_20]
0x180008bf6  mov     r8, rdi
0x180008bf9  mov     [rbp+arg_20], 0
0x180008c01  mov     edx, r12d
0x180008c04  call    cs:__imp_SamOpenDomain
0x180008c0a  mov     ebx, eax
0x180008c0c  test    eax, eax
0x180008c0e  js      short loc_180008C22
0x180008c10  mov     rax, [rbp+arg_20]
0x180008c14  xor     ebx, ebx
0x180008c16  mov     [r14], rax
0x180008c19  mov     rax, [rbp+pv]
0x180008c1d  mov     [rsi], rax
0x180008c20  jmp     short loc_180008C85
0x180008c22  mov     rcx, [rbp+pv]
0x180008c26  call    cs:__imp_SamCloseHandle
0x180008c2c  bts     ebx, 1Ch
0x180008c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c37  lea     rax, WPP_GLOBAL_Control
0x180008c3e  cmp     rcx, rax
0x180008c41  jz      short loc_180008C85
0x180008c43  test    byte ptr [rcx+1Ch], 2
0x180008c47  jz      short loc_180008C85
0x180008c49  mov     edx, 22h ; '"'
0x180008c4e  jmp     short loc_180008C72
0x180008c50  bts     ebx, 1Ch
0x180008c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c5b  lea     rax, WPP_GLOBAL_Control
0x180008c62  cmp     rcx, rax
0x180008c65  jz      short loc_180008C85
0x180008c67  test    byte ptr [rcx+1Ch], 2
0x180008c6b  jz      short loc_180008C85
0x180008c6d  mov     edx, 23h ; '#'
0x180008c72  mov     rcx, [rcx+10h]
0x180008c76  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008c7d  mov     r9d, ebx
0x180008c80  call    WPP_SF_D
0x180008c85  test    r15d, r15d
0x180008c88  jz      short loc_180008C93
0x180008c8a  mov     rcx, rdi; pv
0x180008c8d  call    cs:__imp_CoTaskMemFree
0x180008c93  mov     eax, ebx
0x180008c95  add     rsp, 58h
0x180008c99  pop     r15
0x180008c9b  pop     r14
0x180008c9d  pop     r13
0x180008c9f  pop     r12
0x180008ca1  pop     rdi
0x180008ca2  pop     rsi
0x180008ca3  pop     rbx
0x180008ca4  pop     rbp
0x180008ca5  retn
```
