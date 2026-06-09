# LDAPSearchLoggingClientTraceEventNoReg

- ea: `0x18001e8e0`
- end: `0x18001ea7f`
- name: `LDAPSearchLoggingClientTraceEventNoReg`
- size: `415`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int16 **, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180015640`
- `0x1800308f8`

## callees

- `0x18000b440`
- `0x18001e8e0`
- `0x18001ea90`
- `0x180034510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e92a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e92a`
- `ntdll!EtwEventWrite` at `0x18001ea16`
- `ntdll!EtwEventWrite` at `0x18001ea16`

## pseudocode

```c
_BOOL8 __fastcall LDAPSearchLoggingClientTraceEventNoReg(
        __int64 a1,
        int a2,
        int *a3,
        int *a4,
        unsigned __int16 **a5,
        char a6)
{
  unsigned __int16 **v6; // r14
  int *v7; // rsi
  int *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rax
  bool v11; // zf
  __int64 v12; // rax
  int AttributeList; // eax
  unsigned __int16 *v14; // rdi
  int v15; // ebx
  int v16; // ebx
  DWORD CurrentProcessId; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int16 *v19; // [rsp+28h] [rbp-41h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-39h] BYREF
  int v21; // [rsp+48h] [rbp-21h]
  int v22; // [rsp+4Ch] [rbp-1Dh]
  int *v23; // [rsp+50h] [rbp-19h]
  int v24; // [rsp+58h] [rbp-11h]
  int v25; // [rsp+5Ch] [rbp-Dh]
  unsigned __int16 *v26; // [rsp+60h] [rbp-9h]
  int v27; // [rsp+68h] [rbp-1h]
  int v28; // [rsp+6Ch] [rbp+3h]
  DWORD *p_CurrentProcessId; // [rsp+70h] [rbp+7h]
  __int64 v30; // [rsp+78h] [rbp+Fh]
  int v31; // [rsp+C8h] [rbp+5Fh] BYREF

  v31 = a2;
  v6 = a5;
  v7 = &dword_18004EE04;
  v8 = &dword_18004EE04;
  if ( a4 )
    v7 = a4;
  if ( a3 )
    v8 = a3;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 0;
  if ( !g_RegistrationHandle )
    return 0;
  v9 = -1;
  v20[0] = &v31;
  v10 = -1;
  v20[1] = 4;
  v20[2] = v8;
  do
    v11 = *((_WORD *)v8 + ++v10) == 0;
  while ( !v11 );
  v22 = 0;
  v21 = 2 * v10 + 2;
  v12 = -1;
  v23 = v7;
  do
    v11 = *((_WORD *)v7 + ++v12) == 0;
  while ( !v11 );
  v24 = 2 * v12 + 2;
  v25 = 0;
  AttributeList = GetAttributeList(v6, a6, &v19);
  v14 = v19;
  if ( AttributeList )
  {
    v26 = (unsigned __int16 *)&dword_18004EE04;
    v15 = 2;
  }
  else
  {
    do
      v11 = v19[++v9] == 0;
    while ( !v11 );
    v26 = v19;
    v15 = 2 * v9 + 2;
  }
  p_CurrentProcessId = &CurrentProcessId;
  v27 = v15;
  v28 = 0;
  v30 = 4;
  v16 = EtwEventWrite(g_RegistrationHandle, LDAP_CLIENT_SEARCH_NOREG, 5, v20, CurrentProcessId);
  if ( v14 )
    ldapFree(v14, 1768838476);
  return v16 == 0;
}

```

## disassembly

```asm
0x18001e8e0  mov     [rsp-8+arg_10], rsi
0x18001e8e5  mov     [rsp-8+arg_8], edx
0x18001e8e9  push    rbp
0x18001e8ea  push    rdi
0x18001e8eb  push    r12
0x18001e8ed  push    r14
0x18001e8ef  push    r15
0x18001e8f1  lea     rbp, [rsp-27h]
0x18001e8f6  sub     rsp, 90h
0x18001e8fd  mov     rax, cs:__security_cookie
0x18001e904  xor     rax, rsp
0x18001e907  mov     [rbp+47h+var_30], rax
0x18001e90b  mov     r14, [rbp+47h+arg_20]
0x18001e90f  lea     r12, dword_18004EE04
0x18001e916  test    r9, r9
0x18001e919  mov     rsi, r12
0x18001e91c  mov     rdi, r12
0x18001e91f  cmovnz  rsi, r9
0x18001e923  test    r8, r8
0x18001e926  cmovnz  rdi, r8
0x18001e92a  call    cs:__imp_GetCurrentProcessId
0x18001e931  nop     dword ptr [rax+rax+00h]
0x18001e936  xor     r15d, r15d
0x18001e939  mov     [rbp+47h+var_90], eax
0x18001e93c  cmp     cs:?g_RegistrationHandle@@3_KA, r15; unsigned __int64 g_RegistrationHandle
0x18001e943  mov     [rbp+47h+var_88], r15
0x18001e947  jz      loc_18001EA6D
0x18001e94d  lea     rax, [rbp+47h+arg_8]
0x18001e951  mov     [rsp+0B0h+arg_0], rbx
0x18001e959  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e960  mov     [rbp+47h+var_80], rax
0x18001e964  mov     rax, rbx
0x18001e967  mov     [rbp+47h+var_78], 4
0x18001e96f  mov     [rbp+47h+var_70], rdi
0x18001e973  cmp     [rdi+rax*2+2], r15w
0x18001e979  lea     rax, [rax+1]
0x18001e97d  jnz     short loc_18001E973
0x18001e97f  lea     eax, ds:2[rax*2]
0x18001e986  mov     [rbp+47h+var_64], r15d
0x18001e98a  mov     [rbp+47h+var_68], eax
0x18001e98d  mov     rax, rbx
0x18001e990  mov     [rbp+47h+var_60], rsi
0x18001e994  cmp     [rsi+rax*2+2], r15w
0x18001e99a  lea     rax, [rax+1]
0x18001e99e  jnz     short loc_18001E994
0x18001e9a0  movzx   edx, [rbp+47h+arg_28]; unsigned __int8
0x18001e9a4  lea     eax, ds:2[rax*2]
0x18001e9ab  lea     r8, [rbp+47h+var_88]; unsigned __int16 **
0x18001e9af  mov     [rbp+47h+var_58], eax
0x18001e9b2  mov     rcx, r14; unsigned __int16 **
0x18001e9b5  mov     [rbp+47h+var_54], r15d
0x18001e9b9  call    ?GetAttributeList@@YAJPEAPEAGE0@Z; GetAttributeList(ushort * *,uchar,ushort * *)
0x18001e9be  mov     rdi, [rbp+47h+var_88]
0x18001e9c2  test    eax, eax
0x18001e9c4  jnz     loc_18001EA71
0x18001e9ca  nop     word ptr [rax+rax+00h]
0x18001e9d0  cmp     [rdi+rbx*2+2], r15w
0x18001e9d6  lea     rbx, [rbx+1]
0x18001e9da  jnz     short loc_18001E9D0
0x18001e9dc  mov     [rbp+47h+var_50], rdi
0x18001e9e0  lea     ebx, ds:2[rbx*2]
0x18001e9e7  mov     rcx, cs:?g_RegistrationHandle@@3_KA; unsigned __int64 g_RegistrationHandle
0x18001e9ee  lea     rax, [rbp+47h+var_90]
0x18001e9f2  lea     r9, [rbp+47h+var_80]
0x18001e9f6  mov     [rbp+47h+var_40], rax
0x18001e9fa  mov     r8d, 5
0x18001ea00  mov     [rbp+47h+var_48], ebx
0x18001ea03  lea     rdx, LDAP_CLIENT_SEARCH_NOREG
0x18001ea0a  mov     [rbp+47h+var_44], r15d
0x18001ea0e  mov     [rbp+47h+var_38], 4
0x18001ea16  call    cs:__imp_EtwEventWrite
0x18001ea1d  nop     dword ptr [rax+rax+00h]
0x18001ea22  mov     ebx, eax
0x18001ea24  test    rdi, rdi
0x18001ea27  jnz     short loc_18001EA5E
0x18001ea29  test    ebx, ebx
0x18001ea2b  mov     eax, r15d
0x18001ea2e  mov     rbx, [rsp+0B0h+arg_0]
0x18001ea36  setz    al
0x18001ea39  mov     rcx, [rbp+47h+var_30]
0x18001ea3d  xor     rcx, rsp; StackCookie
0x18001ea40  call    __security_check_cookie
0x18001ea45  mov     rsi, [rsp+0B0h+arg_10]
0x18001ea4d  add     rsp, 90h
0x18001ea54  pop     r15
0x18001ea56  pop     r14
0x18001ea58  pop     r12
0x18001ea5a  pop     rdi
0x18001ea5b  pop     rbp
0x18001ea5c  retn
0x18001ea5e  mov     edx, 696E554Ch
0x18001ea63  mov     rcx, rdi
0x18001ea66  call    ldapFree
0x18001ea6b  jmp     short loc_18001EA29
0x18001ea6d  xor     eax, eax
0x18001ea6f  jmp     short loc_18001EA39
0x18001ea71  mov     [rbp+47h+var_50], r12
0x18001ea75  mov     ebx, 2
0x18001ea7a  jmp     loc_18001E9E7
```
