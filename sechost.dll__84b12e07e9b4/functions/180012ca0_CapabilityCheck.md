# CapabilityCheck

- ea: `0x180012ca0`
- end: `0x180012e42`
- name: `CapabilityCheck`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018410`

## callees

- `0x180012ca0`
- `0x18001d288`
- `0x180037758`
- `0x1800377ac`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlCheckTokenMembership` at `0x180012e06`
- `ntdll!RtlCheckTokenMembership` at `0x180012e06`
- `ntdll!RtlCapabilityCheck` at `0x180012d69`
- `ntdll!RtlCapabilityCheck` at `0x180012d69`
- `ntdll!RtlCheckTokenCapability` at `0x180012dcd`
- `ntdll!RtlCheckTokenCapability` at `0x180012dcd`
- `ext-ms-win-security-chambers-l1-1-0!GetCapabilitySidsEx` at `0x180012da6`
- `ext-ms-win-security-chambers-l1-1-0!GetCapabilitySidsEx` at `0x180012da6`

## pseudocode

```c
__int64 __fastcall CapabilityCheck(__int64 a1, _WORD *a2, _BYTE *a3)
{
  int CapabilitySids; // ecx
  __int64 v8; // rdx
  _WORD *v9; // rax
  __int16 v10; // dx
  __int64 v11; // rbx
  char v12; // di
  char v13; // [rsp+20h] [rbp-98h] BYREF
  char v14[7]; // [rsp+21h] [rbp-97h] BYREF
  __int128 v15; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v16[48]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v17[48]; // [rsp+68h] [rbp-50h] BYREF

  v14[0] = 0;
  v13 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-1073741811;
  v8 = 0x7FFF;
  v15 = 0;
  v9 = a2;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  CapabilitySids = -1073741811;
  if ( !v8 )
    return (unsigned int)CapabilitySids;
  v10 = 2 * v8;
  *((_QWORD *)&v15 + 1) = a2;
  LOWORD(v15) = -2 - v10;
  WORD1(v15) = -v10;
  if ( (unsigned __int8)IsGetCapabilitySidsExPresent(0) )
  {
    v11 = -6;
    if ( a1 )
      v11 = a1;
    CapabilitySids = IsAppContainer(v11, v14);
    if ( CapabilitySids < 0 )
      return (unsigned int)CapabilitySids;
    CapabilitySids = GetCapabilitySidsEx(a2, v16, v17);
    if ( CapabilitySids < 0 )
      return (unsigned int)CapabilitySids;
    v12 = v14[0];
    if ( v14[0] )
    {
      CapabilitySids = RtlCheckTokenCapability(v11, v17, &v13);
      if ( CapabilitySids < 0 )
        return (unsigned int)CapabilitySids;
      if ( v13 )
      {
        CapabilitySids = IsTokenUserGrantedCapability(v11, v12, &v13);
        if ( CapabilitySids < 0 )
          return (unsigned int)CapabilitySids;
      }
    }
    else
    {
      CapabilitySids = RtlCheckTokenMembership(v11, v16, &v13);
      if ( CapabilitySids < 0 )
        return (unsigned int)CapabilitySids;
      if ( !v13 )
      {
        CapabilitySids = IsTokenUserGrantedCapability(v11, 0, &v13);
        if ( CapabilitySids < 0 )
          return (unsigned int)CapabilitySids;
      }
    }
    *a3 = v13;
    return (unsigned int)CapabilitySids;
  }
  return RtlCapabilityCheck(a1, &v15, a3);
}

```

## disassembly

```asm
0x180012ca0  mov     [rsp+arg_18], rbx
0x180012ca5  push    rbp
0x180012ca6  push    rsi
0x180012ca7  push    rdi
0x180012ca8  sub     rsp, 0A0h
0x180012caf  mov     rax, cs:__security_cookie
0x180012cb6  xor     rax, rsp
0x180012cb9  mov     [rsp+0B8h+var_20], rax
0x180012cc1  mov     [rsp+0B8h+var_97], 0
0x180012cc6  mov     rsi, r8
0x180012cc9  mov     [rsp+0B8h+var_98], 0
0x180012cce  mov     rdi, rdx
0x180012cd1  mov     rbp, rcx
0x180012cd4  test    rdx, rdx
0x180012cd7  jnz     short loc_180012D03
0x180012cd9  mov     ecx, 0C000000Dh
0x180012cde  mov     eax, ecx
0x180012ce0  mov     rcx, [rsp+0B8h+var_20]
0x180012ce8  xor     rcx, rsp; StackCookie
0x180012ceb  call    __security_check_cookie
0x180012cf0  mov     rbx, [rsp+0B8h+arg_18]
0x180012cf8  add     rsp, 0A0h
0x180012cff  pop     rdi
0x180012d00  pop     rsi
0x180012d01  pop     rbp
0x180012d02  retn
0x180012d03  test    rsi, rsi
0x180012d06  jz      short loc_180012CD9
0x180012d08  xorps   xmm0, xmm0
0x180012d0b  mov     edx, 7FFFh
0x180012d10  movups  [rsp+0B8h+var_90], xmm0
0x180012d15  mov     rax, rdi
0x180012d18  cmp     word ptr [rax], 0
0x180012d1c  jz      short loc_180012D28
0x180012d1e  add     rax, 2
0x180012d22  sub     rdx, 1
0x180012d26  jnz     short loc_180012D18
0x180012d28  xor     eax, eax
0x180012d2a  mov     ecx, 0C000000Dh
0x180012d2f  test    rdx, rdx
0x180012d32  cmovnz  ecx, eax
0x180012d35  jz      short loc_180012CDE
0x180012d37  add     dx, dx
0x180012d3a  mov     qword ptr [rsp+0B8h+var_90+8], rdi
0x180012d3f  mov     eax, 0FFFEh
0x180012d44  sub     ax, dx
0x180012d47  mov     word ptr [rsp+0B8h+var_90], ax
0x180012d4c  add     ax, 2
0x180012d50  mov     word ptr [rsp+0B8h+var_90+2], ax
0x180012d55  call    IsGetCapabilitySidsExPresent
0x180012d5a  test    al, al
0x180012d5c  jnz     short loc_180012D74
0x180012d5e  mov     r8, rsi
0x180012d61  lea     rdx, [rsp+0B8h+var_90]
0x180012d66  mov     rcx, rbp
0x180012d69  call    cs:__imp_RtlCapabilityCheck
0x180012d6f  jmp     loc_180012CE0
0x180012d74  test    rbp, rbp
0x180012d77  lea     rdx, [rsp+0B8h+var_97]
0x180012d7c  mov     rbx, 0FFFFFFFFFFFFFFFAh
0x180012d83  cmovnz  rbx, rbp
0x180012d87  mov     rcx, rbx
0x180012d8a  call    IsAppContainer
0x180012d8f  mov     ecx, eax
0x180012d91  test    eax, eax
0x180012d93  js      loc_180012CDE
0x180012d99  lea     r8, [rsp+0B8h+var_50]
0x180012d9e  mov     rcx, rdi
0x180012da1  lea     rdx, [rsp+0B8h+var_80]
0x180012da6  call    cs:__imp_GetCapabilitySidsEx
0x180012dac  mov     ecx, eax
0x180012dae  test    eax, eax
0x180012db0  js      loc_180012CDE
0x180012db6  movzx   edi, [rsp+0B8h+var_97]
0x180012dbb  lea     r8, [rsp+0B8h+var_98]
0x180012dc0  mov     rcx, rbx
0x180012dc3  test    dil, dil
0x180012dc6  jz      short loc_180012E01
0x180012dc8  lea     rdx, [rsp+0B8h+var_50]
0x180012dcd  call    cs:__imp_RtlCheckTokenCapability
0x180012dd3  mov     ecx, eax
0x180012dd5  test    eax, eax
0x180012dd7  js      loc_180012CDE
0x180012ddd  cmp     [rsp+0B8h+var_98], 0
0x180012de2  jz      short loc_180012E36
0x180012de4  lea     r8, [rsp+0B8h+var_98]
0x180012de9  movzx   edx, dil
0x180012ded  mov     rcx, rbx
0x180012df0  call    IsTokenUserGrantedCapability
0x180012df5  mov     ecx, eax
0x180012df7  test    eax, eax
0x180012df9  js      loc_180012CDE
0x180012dff  jmp     short loc_180012E36
0x180012e01  lea     rdx, [rsp+0B8h+var_80]
0x180012e06  call    cs:__imp_RtlCheckTokenMembership
0x180012e0c  mov     ecx, eax
0x180012e0e  test    eax, eax
0x180012e10  js      loc_180012CDE
0x180012e16  cmp     [rsp+0B8h+var_98], 0
0x180012e1b  jnz     short loc_180012E36
0x180012e1d  lea     r8, [rsp+0B8h+var_98]
0x180012e22  xor     edx, edx
0x180012e24  mov     rcx, rbx
0x180012e27  call    IsTokenUserGrantedCapability
0x180012e2c  mov     ecx, eax
0x180012e2e  test    eax, eax
0x180012e30  js      loc_180012CDE
0x180012e36  movzx   eax, [rsp+0B8h+var_98]
0x180012e3b  mov     [rsi], al
0x180012e3d  jmp     loc_180012CDE
```
