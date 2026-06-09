# CWdsService::GenerateServerDuid(uchar * *,ulong *)

- ea: `0x180008c58`
- end: `0x180008e71`
- name: `?GenerateServerDuid@CWdsService@@AEAAKPEAPEAEPEAK@Z`
- size: `537`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c3b4`

## callees

- `0x180001984`
- `0x180008c58`
- `0x18000f0dc`
- `0x18001c150`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008cdc`
- `KERNEL32!GetLastError` at `0x180008d1f`
- `KERNEL32!GetLastError` at `0x180008cdc`
- `KERNEL32!GetLastError` at `0x180008d1f`
- `KERNEL32!GetSystemTime` at `0x180008cb8`
- `KERNEL32!GetSystemTime` at `0x180008cb8`
- `KERNEL32!SystemTimeToFileTime` at `0x180008ccc`
- `KERNEL32!SystemTimeToFileTime` at `0x180008d0f`
- `KERNEL32!SystemTimeToFileTime` at `0x180008ccc`
- `KERNEL32!SystemTimeToFileTime` at `0x180008d0f`
- `WS2_32!__imp_htonl` at `0x180008e0d`
- `WS2_32!__imp_htonl` at `0x180008e0d`
- `WS2_32!__imp_htons` at `0x180008de6`
- `WS2_32!__imp_htons` at `0x180008dfa`
- `WS2_32!__imp_htons` at `0x180008de6`
- `WS2_32!__imp_htons` at `0x180008dfa`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180008e3d`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180008e3d`
- `WdsServerCommonLib!?EnumInterfaces@CNetworkAddress@@SAKKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z` at `0x180008d59`
- `WdsServerCommonLib!?EnumInterfaces@CNetworkAddress@@SAKKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z` at `0x180008d59`

## pseudocode

```c
__int64 __fastcall CWdsService::GenerateServerDuid(CWdsService *this, u_short **a2, unsigned int *a3)
{
  char *v3; // rsi
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  unsigned __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  u_short *v16; // rdi
  unsigned int v18; // [rsp+20h] [rbp-50h] BYREF
  struct tagWDS_INTERFACE_INFO *v19; // [rsp+28h] [rbp-48h] BYREF
  struct _FILETIME v20; // [rsp+30h] [rbp-40h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-38h] BYREF
  SYSTEMTIME v22; // [rsp+40h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  v18 = 0;
  v19 = 0;
  v3 = 0;
  FileTime = 0;
  v20 = 0;
  v22 = 0;
  *(_DWORD *)&v22.wYear = 67536;
  v22.wDay = 1;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&v22, &FileTime) )
  {
    LastError = GetLastError();
    v9 = 1192;
    goto LABEL_3;
  }
  if ( !SystemTimeToFileTime(&SystemTime, &v20) )
  {
    LastError = GetLastError();
    v9 = 1197;
LABEL_3:
    v10 = ElValidateWin32_0(LastError, v7, v8, v9);
    if ( !v10 )
      v10 = 31;
    goto LABEL_17;
  }
  v11 = (*(_QWORD *)&v20 - *(_QWORD *)&FileTime) / 0x989680uLL;
  v10 = CNetworkAddress::EnumInterfaces(0, &v19, &v18);
  if ( (unsigned int)ElValidateWin32_0(v10, v12, v13, 0x4C1u) )
    goto LABEL_17;
  v15 = 0;
  if ( !v18 )
    goto LABEL_13;
  while ( 1 )
  {
    v14 = 48 * v15;
    if ( *((_DWORD *)v19 + 12 * v15 + 9) == 6 )
      break;
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= v18 )
      goto LABEL_13;
  }
  v3 = (char *)v19 + v14 + 20;
  if ( !v3 )
  {
LABEL_13:
    v10 = 2;
    if ( (unsigned int)ElValidateWin32_0(2u, v14, v18, 0x4CFu) )
      goto LABEL_17;
  }
  v16 = (u_short *)operator new[](0xEu, (const struct std::nothrow_t *)&std::nothrow);
  if ( v16 )
  {
    *v16 = htons(1u);
    v16[1] = htons(1u);
    *((_DWORD *)v16 + 1) = htonl(v11);
    *((_DWORD *)v16 + 2) = *(_DWORD *)v3;
    v16[6] = *((_WORD *)v3 + 2);
    *a2 = v16;
    *a3 = 14;
  }
  else
  {
    v10 = 8;
  }
LABEL_17:
  if ( v19 )
    WdsPrivateHpFree(v19);
  return v10;
}

```

## disassembly

```asm
0x180008c58  mov     [rsp-28h+arg_0], rbx
0x180008c5d  mov     [rsp-28h+arg_18], rsi
0x180008c62  push    rbp
0x180008c63  push    rdi
0x180008c64  push    r12
0x180008c66  push    r14
0x180008c68  push    r15
0x180008c6a  mov     rbp, rsp
0x180008c6d  sub     rsp, 70h
0x180008c71  mov     rax, cs:__security_cookie
0x180008c78  xor     rax, rsp
0x180008c7b  mov     [rbp+var_10], rax
0x180008c7f  and     [rbp+var_50], 0
0x180008c83  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180008c87  and     [rbp+var_48], 0
0x180008c8c  xor     esi, esi
0x180008c8e  and     qword ptr [rbp+FileTime.dwLowDateTime], rsi
0x180008c92  xorps   xmm0, xmm0
0x180008c95  and     qword ptr [rbp+var_40.dwLowDateTime], rsi
0x180008c99  xorps   xmm1, xmm1
0x180008c9c  movups  xmmword ptr [rbp+var_30.wYear], xmm0
0x180008ca0  lea     edi, [rsi+1]
0x180008ca3  mov     dword ptr [rbp+var_30.wYear], 107D0h
0x180008caa  mov     [rbp+var_30.wDay], di
0x180008cae  mov     r12, r8
0x180008cb1  mov     r15, rdx
0x180008cb4  movups  xmmword ptr [rbp+SystemTime.wYear], xmm1
0x180008cb8  call    cs:__imp_GetSystemTime
0x180008cbf  nop     dword ptr [rax+rax+00h]
0x180008cc4  lea     rdx, [rbp+FileTime]; lpFileTime
0x180008cc8  lea     rcx, [rbp+var_30]; lpSystemTime
0x180008ccc  call    cs:__imp_SystemTimeToFileTime
0x180008cd3  nop     dword ptr [rax+rax+00h]
0x180008cd8  test    eax, eax
0x180008cda  jnz     short loc_180008D07
0x180008cdc  call    cs:__imp_GetLastError
0x180008ce3  nop     dword ptr [rax+rax+00h]
0x180008ce8  mov     r9d, 4A8h
0x180008cee  mov     ecx, eax
0x180008cf0  call    ElValidateWin32_0
0x180008cf5  mov     ebx, eax
0x180008cf7  test    eax, eax
0x180008cf9  jnz     loc_180008E34
0x180008cff  lea     ebx, [rax+1Fh]
0x180008d02  jmp     loc_180008E34
0x180008d07  lea     rdx, [rbp+var_40]; lpFileTime
0x180008d0b  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180008d0f  call    cs:__imp_SystemTimeToFileTime
0x180008d16  nop     dword ptr [rax+rax+00h]
0x180008d1b  test    eax, eax
0x180008d1d  jnz     short loc_180008D33
0x180008d1f  call    cs:__imp_GetLastError
0x180008d26  nop     dword ptr [rax+rax+00h]
0x180008d2b  mov     r9d, 4ADh
0x180008d31  jmp     short loc_180008CEE
0x180008d33  mov     rcx, qword ptr [rbp+var_40.dwLowDateTime]
0x180008d37  lea     r8, [rbp+var_50]
0x180008d3b  sub     rcx, qword ptr [rbp+FileTime.dwLowDateTime]
0x180008d3f  mov     rax, 0D6BF94D5E57A42BDh
0x180008d49  mul     rcx
0x180008d4c  xor     ecx, ecx
0x180008d4e  mov     r14, rdx
0x180008d51  lea     rdx, [rbp+var_48]
0x180008d55  shr     r14, 17h
0x180008d59  call    cs:__imp_?EnumInterfaces@CNetworkAddress@@SAKKPEAPEAUtagWDS_INTERFACE_INFO@@PEAK@Z; CNetworkAddress::EnumInterfaces(ulong,tagWDS_INTERFACE_INFO * *,ulong *)
0x180008d60  nop     dword ptr [rax+rax+00h]
0x180008d65  mov     ecx, eax
0x180008d67  mov     r9d, 4C1h
0x180008d6d  mov     ebx, eax
0x180008d6f  call    ElValidateWin32_0
0x180008d74  test    eax, eax
0x180008d76  jnz     loc_180008E34
0x180008d7c  mov     r8d, [rbp+var_50]
0x180008d80  xor     ecx, ecx
0x180008d82  test    r8d, r8d
0x180008d85  jz      short loc_180008DAD
0x180008d87  mov     r9, [rbp+var_48]
0x180008d8b  lea     rdx, [rcx+rcx*2]
0x180008d8f  shl     rdx, 4
0x180008d93  cmp     dword ptr [rdx+r9+24h], 6
0x180008d99  jz      short loc_180008DA4
0x180008d9b  add     ecx, edi
0x180008d9d  cmp     ecx, r8d
0x180008da0  jb      short loc_180008D8B
0x180008da2  jmp     short loc_180008DAD
0x180008da4  lea     rsi, [r9+14h]
0x180008da8  add     rsi, rdx
0x180008dab  jnz     short loc_180008DC3
0x180008dad  mov     ebx, 2
0x180008db2  mov     r9d, 4CFh
0x180008db8  mov     ecx, ebx
0x180008dba  call    ElValidateWin32_0
0x180008dbf  test    eax, eax
0x180008dc1  jnz     short loc_180008E34
0x180008dc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008dca  mov     ecx, 0Eh; unsigned __int64
0x180008dcf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008dd4  mov     rdi, rax
0x180008dd7  test    rax, rax
0x180008dda  jnz     short loc_180008DE1
0x180008ddc  lea     ebx, [rax+8]
0x180008ddf  jmp     short loc_180008E34
0x180008de1  mov     ecx, 1; hostshort
0x180008de6  call    cs:__imp_htons
0x180008ded  nop     dword ptr [rax+rax+00h]
0x180008df2  mov     ecx, 1; hostshort
0x180008df7  mov     [rdi], ax
0x180008dfa  call    cs:__imp_htons
0x180008e01  nop     dword ptr [rax+rax+00h]
0x180008e06  mov     ecx, r14d; hostlong
0x180008e09  mov     [rdi+2], ax
0x180008e0d  call    cs:__imp_htonl
0x180008e14  nop     dword ptr [rax+rax+00h]
0x180008e19  mov     [rdi+4], eax
0x180008e1c  mov     eax, [rsi]
0x180008e1e  mov     [rdi+8], eax
0x180008e21  movzx   eax, word ptr [rsi+4]
0x180008e25  mov     [rdi+0Ch], ax
0x180008e29  mov     [r15], rdi
0x180008e2c  mov     dword ptr [r12], 0Eh
0x180008e34  mov     rcx, [rbp+var_48]
0x180008e38  test    rcx, rcx
0x180008e3b  jz      short loc_180008E49
0x180008e3d  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180008e44  nop     dword ptr [rax+rax+00h]
0x180008e49  mov     eax, ebx
0x180008e4b  mov     rcx, [rbp+var_10]
0x180008e4f  xor     rcx, rsp; StackCookie
0x180008e52  call    __security_check_cookie
0x180008e57  lea     r11, [rsp+70h+var_s0]
0x180008e5c  mov     rbx, [r11+30h]
0x180008e60  mov     rsi, [r11+48h]
0x180008e64  mov     rsp, r11
0x180008e67  pop     r15
0x180008e69  pop     r14
0x180008e6b  pop     r12
0x180008e6d  pop     rdi
0x180008e6e  pop     rbp
0x180008e6f  retn
```
