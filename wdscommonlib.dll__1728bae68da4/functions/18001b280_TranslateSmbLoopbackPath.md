# TranslateSmbLoopbackPath

- ea: `0x18001b280`
- end: `0x18001b60a`
- name: `TranslateSmbLoopbackPath`
- size: `906`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800074d0`
- `0x1800076f0`
- `0x180015a00`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001b280`
- `0x180021410`
- `0x180025a80`
- `0x180025c20`
- `0x180025ce0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b570`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b585`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b59a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b570`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b585`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b59a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b5d7`
- `SHLWAPI!PathIsUNCW` at `0x18001b2fb`
- `SHLWAPI!PathIsUNCW` at `0x18001b2fb`

## pseudocode

```c
__int64 __fastcall TranslateSmbLoopbackPath(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  WCHAR *v7; // r14
  unsigned __int16 *v8; // rdi
  void *v9; // rsi
  int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int HostName; // r14d
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r15d
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned __int16 *v26; // r15
  __int64 NetSharePath; // rdi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned __int16 *v36; // [rsp+30h] [rbp-50h] BYREF
  void *v37; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v38; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR netname; // [rsp+48h] [rbp-38h] BYREF
  PCWSTR pNodeName; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int16 *v42[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v43; // [rsp+70h] [rbp-10h]
  int v44; // [rsp+78h] [rbp-8h]
  int v45; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int16 **v46; // [rsp+C8h] [rbp+48h]
  _QWORD *v47; // [rsp+D8h] [rbp+58h]

  v47 = a4;
  v46 = a2;
  v44 = 4;
  pNodeName = 0;
  v38 = 0;
  netname = 0;
  v36 = 0;
  v6 = 0;
  v41 = 0;
  v7 = 0;
  v37 = 0;
  v8 = 0;
  v45 = 0;
  v9 = 0;
  v43 = 0;
  *(_OWORD *)v42 = 0;
  if ( !a1 || !*a1 )
  {
    v6 = -2147024809;
    goto LABEL_46;
  }
  if ( !PathIsUNCW(a1) )
  {
    v6 = 1;
    goto LABEL_58;
  }
  v10 = CTokenString::Initialize(v42, a1, L"\\", 0);
  if ( (unsigned int)ElValidateWin32_8((unsigned int)v10, v11, v12, 4781) )
  {
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    else
      v6 = v10;
    goto LABEL_58;
  }
  v13 = CTokenString::GetAt((CTokenString *)v42, 1u, &v38);
  if ( !(unsigned int)ElValidateWin32_8((unsigned int)v13, v14, v15, 4784) )
  {
    v13 = CTokenString::GetAt((CTokenString *)v42, 2u, &netname);
    if ( !(unsigned int)ElValidateWin32_8((unsigned int)v13, v16, v17, 4787) )
    {
      HostName = GetHostName(ComputerNamePhysicalDnsFullyQualified, (unsigned __int16 **)&pNodeName);
      if ( (unsigned int)ElValidateWin32_8((unsigned int)HostName, v19, v20, 4795) )
      {
        if ( HostName > 0 )
          v6 = (unsigned __int16)HostName | 0x80070000;
        else
          v6 = HostName;
        v7 = (WCHAR *)pNodeName;
      }
      else
      {
        v7 = (WCHAR *)pNodeName;
        v21 = CNetworkAddress::AreHostsSame(v38, pNodeName, &v45);
        if ( (unsigned int)ElValidateWin32_8((unsigned int)v21, v22, v23, 4805) )
        {
          if ( v21 > 0 )
            v6 = (unsigned __int16)v21 | 0x80070000;
          else
            v6 = v21;
        }
        else
        {
          if ( !v45 )
          {
            v6 = 1;
            goto LABEL_46;
          }
          v24 = -1;
          v25 = -1;
          do
            ++v25;
          while ( netname[v25] );
          do
            ++v24;
          while ( v38[v24] );
          v26 = &a1[v24 + 3 + v25];
          NetSharePath = GetNetSharePath(netname, &v36);
          if ( !(unsigned int)ElValidateWin32_8(NetSharePath, v28, v29, 4831) )
          {
            LODWORD(NetSharePath) = FormatString(&v41, 0, L"\\\\%s\\%s", v38, netname);
            if ( !(unsigned int)ElValidateWin32_8((unsigned int)NetSharePath, v30, v31, 4842) )
            {
              v8 = v36;
              v32 = ConcatenatePaths(v36, v26, &v37);
              if ( (unsigned int)ElValidateWin32_8((unsigned int)v32, v33, v34, 4851) )
              {
                if ( v32 > 0 )
                  v6 = (unsigned __int16)v32 | 0x80070000;
                else
                  v6 = v32;
              }
              else
              {
                if ( v46 )
                {
                  *v46 = v8;
                  v8 = 0;
                }
                if ( a3 )
                {
                  *a3 = v41;
                  v41 = 0;
                }
                if ( v47 )
                {
                  v9 = 0;
                  *v47 = v37;
                  goto LABEL_46;
                }
              }
              v9 = v37;
              goto LABEL_46;
            }
          }
          if ( (int)NetSharePath > 0 )
            v6 = (unsigned __int16)NetSharePath | 0x80070000;
          else
            v6 = NetSharePath;
          v8 = v36;
        }
      }
LABEL_46:
      if ( v7 )
        operator delete(v7);
      goto LABEL_48;
    }
  }
  if ( v13 > 0 )
    v6 = (unsigned __int16)v13 | 0x80070000;
  else
    v6 = v13;
LABEL_48:
  if ( v38 )
    operator delete(v38);
  if ( netname )
    operator delete(netname);
  if ( v8 )
    operator delete(v8);
  if ( v41 )
    operator delete(v41);
  if ( v9 )
    operator delete(v9);
LABEL_58:
  CTokenString::Shutdown((CTokenString *)v42);
  return v6;
}

```

## disassembly

```asm
0x18001b280  mov     [rsp-38h+arg_10], rbx
0x18001b285  mov     [rsp-38h+arg_18], r9
0x18001b28a  mov     [rsp-38h+arg_8], rdx
0x18001b28f  push    rbp
0x18001b290  push    rsi
0x18001b291  push    rdi
0x18001b292  push    r12
0x18001b294  push    r13
0x18001b296  push    r14
0x18001b298  push    r15
0x18001b29a  mov     rbp, rsp
0x18001b29d  sub     rsp, 80h
0x18001b2a4  xor     r15d, r15d
0x18001b2a7  mov     [rbp+var_8], 4
0x18001b2ae  mov     [rbp+pNodeName], r15
0x18001b2b2  xorps   xmm0, xmm0
0x18001b2b5  mov     [rbp+var_40], r15
0x18001b2b9  mov     r13, r8
0x18001b2bc  mov     [rbp+netname], r15
0x18001b2c0  mov     r12, rcx
0x18001b2c3  mov     [rbp+var_50], r15
0x18001b2c7  mov     ebx, r15d
0x18001b2ca  mov     [rbp+var_28], r15
0x18001b2ce  mov     r14d, r15d
0x18001b2d1  mov     [rbp+var_48], r15
0x18001b2d5  mov     edi, r15d
0x18001b2d8  mov     [rbp+arg_0], r15d
0x18001b2dc  mov     esi, r15d
0x18001b2df  mov     [rbp+var_10], r15
0x18001b2e3  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001b2e8  test    rcx, rcx
0x18001b2eb  jz      loc_18001B563
0x18001b2f1  cmp     [rcx], r15w
0x18001b2f5  jz      loc_18001B563
0x18001b2fb  call    cs:__imp_PathIsUNCW
0x18001b302  nop     dword ptr [rax+rax+00h]
0x18001b307  test    eax, eax
0x18001b309  jnz     short loc_18001B313
0x18001b30b  lea     ebx, [rax+1]
0x18001b30e  jmp     loc_18001B5E3
0x18001b313  xor     r9d, r9d; unsigned int
0x18001b316  lea     r8, SubBlock; "\\"
0x18001b31d  mov     rdx, r12; unsigned __int16 *
0x18001b320  lea     rcx, [rbp+var_20]; this
0x18001b324  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001b329  mov     r9d, 12ADh
0x18001b32f  mov     ecx, eax
0x18001b331  mov     r14d, eax
0x18001b334  call    ElValidateWin32_8
0x18001b339  test    eax, eax
0x18001b33b  jz      short loc_18001B359
0x18001b33d  test    r14d, r14d
0x18001b340  jg      short loc_18001B34A
0x18001b342  mov     ebx, r14d
0x18001b345  jmp     loc_18001B5E3
0x18001b34a  movzx   ebx, r14w
0x18001b34e  or      ebx, 80070000h
0x18001b354  jmp     loc_18001B5E3
0x18001b359  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18001b35d  mov     edx, 1; unsigned int
0x18001b362  lea     rcx, [rbp+var_20]; this
0x18001b366  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001b36b  mov     r9d, 12B0h
0x18001b371  mov     ecx, eax
0x18001b373  mov     r14d, eax
0x18001b376  call    ElValidateWin32_8
0x18001b37b  test    eax, eax
0x18001b37d  jz      short loc_18001B39B
0x18001b37f  test    r14d, r14d
0x18001b382  jg      short loc_18001B38C
0x18001b384  mov     ebx, r14d
0x18001b387  jmp     loc_18001B57C
0x18001b38c  movzx   ebx, r14w
0x18001b390  or      ebx, 80070000h
0x18001b396  jmp     loc_18001B57C
0x18001b39b  lea     r8, [rbp+netname]; unsigned __int16 **
0x18001b39f  mov     edx, 2; unsigned int
0x18001b3a4  lea     rcx, [rbp+var_20]; this
0x18001b3a8  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001b3ad  mov     r9d, 12B3h
0x18001b3b3  mov     ecx, eax
0x18001b3b5  mov     r14d, eax
0x18001b3b8  call    ElValidateWin32_8
0x18001b3bd  test    eax, eax
0x18001b3bf  jnz     short loc_18001B37F
0x18001b3c1  lea     rdx, [rbp+pNodeName]; unsigned __int16 **
0x18001b3c5  lea     ecx, [rax+7]; NameType
0x18001b3c8  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18001b3cd  mov     r9d, 12BBh
0x18001b3d3  mov     ecx, eax
0x18001b3d5  mov     r14d, eax
0x18001b3d8  call    ElValidateWin32_8
0x18001b3dd  test    eax, eax
0x18001b3df  jz      short loc_18001B3FE
0x18001b3e1  test    r14d, r14d
0x18001b3e4  jg      short loc_18001B3EB
0x18001b3e6  mov     ebx, r14d
0x18001b3e9  jmp     short loc_18001B3F5
0x18001b3eb  movzx   ebx, r14w
0x18001b3ef  or      ebx, 80070000h
0x18001b3f5  mov     r14, [rbp+pNodeName]
0x18001b3f9  jmp     loc_18001B568
0x18001b3fe  mov     r14, [rbp+pNodeName]
0x18001b402  lea     r8, [rbp+arg_0]; int *
0x18001b406  mov     rcx, [rbp+var_40]; unsigned __int16 *
0x18001b40a  mov     rdx, r14; pNodeName
0x18001b40d  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18001b412  mov     r9d, 12C5h
0x18001b418  mov     ecx, eax
0x18001b41a  mov     r15d, eax
0x18001b41d  call    ElValidateWin32_8
0x18001b422  test    eax, eax
0x18001b424  jz      short loc_18001B442
0x18001b426  test    r15d, r15d
0x18001b429  jg      short loc_18001B433
0x18001b42b  mov     ebx, r15d
0x18001b42e  jmp     loc_18001B568
0x18001b433  movzx   ebx, r15w
0x18001b437  or      ebx, 80070000h
0x18001b43d  jmp     loc_18001B568
0x18001b442  xor     r15d, r15d
0x18001b445  cmp     [rbp+arg_0], r15d
0x18001b449  jnz     short loc_18001B454
0x18001b44b  lea     ebx, [r15+1]
0x18001b44f  jmp     loc_18001B568
0x18001b454  mov     rdx, [rbp+netname]
0x18001b458  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b45c  mov     rcx, rax
0x18001b45f  inc     rcx
0x18001b462  cmp     [rdx+rcx*2], r15w
0x18001b467  jnz     short loc_18001B45F
0x18001b469  mov     rdx, [rbp+var_40]
0x18001b46d  inc     rax
0x18001b470  cmp     [rdx+rax*2], r15w
0x18001b475  jnz     short loc_18001B46D
0x18001b477  add     rax, 3
0x18001b47b  lea     rdx, [rbp+var_50]; unsigned __int16 **
0x18001b47f  add     rcx, rax
0x18001b482  lea     r15, [r12+rcx*2]
0x18001b486  mov     rcx, [rbp+netname]; netname
0x18001b48a  call    ?GetNetSharePath@@YAKPEBGPEAPEAG@Z; GetNetSharePath(ushort const *,ushort * *)
0x18001b48f  mov     r9d, 12DFh
0x18001b495  mov     ecx, eax
0x18001b497  mov     edi, eax
0x18001b499  call    ElValidateWin32_8
0x18001b49e  test    eax, eax
0x18001b4a0  jz      short loc_18001B4BC
0x18001b4a2  test    edi, edi
0x18001b4a4  jg      short loc_18001B4AA
0x18001b4a6  mov     ebx, edi
0x18001b4a8  jmp     short loc_18001B4B3
0x18001b4aa  movzx   ebx, di
0x18001b4ad  or      ebx, 80070000h
0x18001b4b3  mov     rdi, [rbp+var_50]
0x18001b4b7  jmp     loc_18001B568
0x18001b4bc  mov     rax, [rbp+netname]
0x18001b4c0  lea     r8, aSS_1; "\\\\%s\\%s"
0x18001b4c7  mov     r9, [rbp+var_40]
0x18001b4cb  lea     rcx, [rbp+var_28]; unsigned __int16 **
0x18001b4cf  xor     edx, edx; unsigned __int64
0x18001b4d1  mov     [rsp+80h+var_60], rax
0x18001b4d6  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001b4db  mov     r9d, 12EAh
0x18001b4e1  mov     ecx, eax
0x18001b4e3  mov     edi, eax
0x18001b4e5  call    ElValidateWin32_8
0x18001b4ea  test    eax, eax
0x18001b4ec  jnz     short loc_18001B4A2
0x18001b4ee  mov     rdi, [rbp+var_50]
0x18001b4f2  lea     r8, [rbp+var_48]
0x18001b4f6  mov     rcx, rdi
0x18001b4f9  mov     rdx, r15
0x18001b4fc  call    ConcatenatePaths
0x18001b501  mov     r9d, 12F3h
0x18001b507  mov     ecx, eax
0x18001b509  mov     esi, eax
0x18001b50b  call    ElValidateWin32_8
0x18001b510  xor     r15d, r15d
0x18001b513  test    eax, eax
0x18001b515  jz      short loc_18001B52E
0x18001b517  test    esi, esi
0x18001b519  jg      short loc_18001B51F
0x18001b51b  mov     ebx, esi
0x18001b51d  jmp     short loc_18001B528
0x18001b51f  movzx   ebx, si
0x18001b522  or      ebx, 80070000h
0x18001b528  mov     rsi, [rbp+var_48]
0x18001b52c  jmp     short loc_18001B568
0x18001b52e  mov     rax, [rbp+arg_8]
0x18001b532  test    rax, rax
0x18001b535  jz      short loc_18001B53D
0x18001b537  mov     [rax], rdi
0x18001b53a  mov     rdi, r15
0x18001b53d  test    r13, r13
0x18001b540  jz      short loc_18001B54E
0x18001b542  mov     rax, [rbp+var_28]
0x18001b546  mov     [r13+0], rax
0x18001b54a  mov     [rbp+var_28], r15
0x18001b54e  mov     rcx, [rbp+arg_18]
0x18001b552  test    rcx, rcx
0x18001b555  jz      short loc_18001B528
0x18001b557  mov     rax, [rbp+var_48]
0x18001b55b  mov     rsi, r15
0x18001b55e  mov     [rcx], rax
0x18001b561  jmp     short loc_18001B568
0x18001b563  mov     ebx, 80070057h
0x18001b568  test    r14, r14
0x18001b56b  jz      short loc_18001B57C
0x18001b56d  mov     rcx, r14
0x18001b570  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b577  nop     dword ptr [rax+rax+00h]
0x18001b57c  mov     rcx, [rbp+var_40]
0x18001b580  test    rcx, rcx
0x18001b583  jz      short loc_18001B591
0x18001b585  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b58c  nop     dword ptr [rax+rax+00h]
0x18001b591  mov     rcx, [rbp+netname]
0x18001b595  test    rcx, rcx
0x18001b598  jz      short loc_18001B5A6
0x18001b59a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b5a1  nop     dword ptr [rax+rax+00h]
0x18001b5a6  test    rdi, rdi
0x18001b5a9  jz      short loc_18001B5BA
0x18001b5ab  mov     rcx, rdi
0x18001b5ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b5b5  nop     dword ptr [rax+rax+00h]
0x18001b5ba  mov     rcx, [rbp+var_28]
0x18001b5be  test    rcx, rcx
0x18001b5c1  jz      short loc_18001B5CF
0x18001b5c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b5ca  nop     dword ptr [rax+rax+00h]
0x18001b5cf  test    rsi, rsi
0x18001b5d2  jz      short loc_18001B5E3
0x18001b5d4  mov     rcx, rsi
0x18001b5d7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b5de  nop     dword ptr [rax+rax+00h]
0x18001b5e3  lea     rcx, [rbp+var_20]; this
0x18001b5e7  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001b5ec  mov     eax, ebx
0x18001b5ee  mov     rbx, [rsp+80h+arg_10]
0x18001b5f6  add     rsp, 80h
0x18001b5fd  pop     r15
0x18001b5ff  pop     r14
0x18001b601  pop     r13
0x18001b603  pop     r12
0x18001b605  pop     rdi
0x18001b606  pop     rsi
0x18001b607  pop     rbp
0x18001b608  retn
```
