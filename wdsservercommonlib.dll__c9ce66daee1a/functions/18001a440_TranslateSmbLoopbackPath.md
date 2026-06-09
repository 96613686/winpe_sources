# TranslateSmbLoopbackPath

- ea: `0x18001a440`
- end: `0x18001a7a0`
- name: `TranslateSmbLoopbackPath`
- size: `864`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800069c0`
- `0x180006bc0`
- `0x180014ce0`
- `0x180019a40`
- `0x18001a28c`
- `0x18001a440`
- `0x180020400`
- `0x180024990`
- `0x180024b20`
- `0x180024be0`
- `0x18002e468`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18001a4bb`
- `SHLWAPI!PathIsUNCW` at `0x18001a4bb`

## pseudocode

```c
__int64 __fastcall TranslateSmbLoopbackPath(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  void *v7; // r14
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
  void *lpMem; // [rsp+50h] [rbp-30h] BYREF
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
  lpMem = 0;
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
      HostName = GetHostName(ComputerNamePhysicalDnsFullyQualified, (unsigned __int16 **)&lpMem);
      if ( (unsigned int)ElValidateWin32_8((unsigned int)HostName, v19, v20, 4795) )
      {
        if ( HostName > 0 )
          v6 = (unsigned __int16)HostName | 0x80070000;
        else
          v6 = HostName;
        v7 = lpMem;
      }
      else
      {
        v7 = lpMem;
        v21 = CNetworkAddress::AreHostsSame(v38, (PCWSTR)lpMem, &v45);
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
0x18001a440  mov     [rsp-38h+arg_10], rbx
0x18001a445  mov     [rsp-38h+arg_18], r9
0x18001a44a  mov     [rsp-38h+arg_8], rdx
0x18001a44f  push    rbp
0x18001a450  push    rsi
0x18001a451  push    rdi
0x18001a452  push    r12
0x18001a454  push    r13
0x18001a456  push    r14
0x18001a458  push    r15
0x18001a45a  mov     rbp, rsp
0x18001a45d  sub     rsp, 80h
0x18001a464  xor     r15d, r15d
0x18001a467  mov     [rbp+var_8], 4
0x18001a46e  mov     [rbp+lpMem], r15
0x18001a472  xorps   xmm0, xmm0
0x18001a475  mov     [rbp+var_40], r15
0x18001a479  mov     r13, r8
0x18001a47c  mov     [rbp+netname], r15
0x18001a480  mov     r12, rcx
0x18001a483  mov     [rbp+var_50], r15
0x18001a487  mov     ebx, r15d
0x18001a48a  mov     [rbp+var_28], r15
0x18001a48e  mov     r14d, r15d
0x18001a491  mov     [rbp+var_48], r15
0x18001a495  mov     edi, r15d
0x18001a498  mov     [rbp+arg_0], r15d
0x18001a49c  mov     esi, r15d
0x18001a49f  mov     [rbp+var_10], r15
0x18001a4a3  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001a4a8  test    rcx, rcx
0x18001a4ab  jz      loc_18001A723
0x18001a4b1  cmp     [rcx], r15w
0x18001a4b5  jz      loc_18001A723
0x18001a4bb  call    cs:__imp_PathIsUNCW
0x18001a4c2  nop     dword ptr [rax+rax+00h]
0x18001a4c7  test    eax, eax
0x18001a4c9  jnz     short loc_18001A4D3
0x18001a4cb  lea     ebx, [rax+1]
0x18001a4ce  jmp     loc_18001A779
0x18001a4d3  xor     r9d, r9d; unsigned int
0x18001a4d6  lea     r8, SubBlock; "\\"
0x18001a4dd  mov     rdx, r12; unsigned __int16 *
0x18001a4e0  lea     rcx, [rbp+var_20]; this
0x18001a4e4  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001a4e9  mov     r9d, 12ADh
0x18001a4ef  mov     ecx, eax
0x18001a4f1  mov     r14d, eax
0x18001a4f4  call    ElValidateWin32_8
0x18001a4f9  test    eax, eax
0x18001a4fb  jz      short loc_18001A519
0x18001a4fd  test    r14d, r14d
0x18001a500  jg      short loc_18001A50A
0x18001a502  mov     ebx, r14d
0x18001a505  jmp     loc_18001A779
0x18001a50a  movzx   ebx, r14w
0x18001a50e  or      ebx, 80070000h
0x18001a514  jmp     loc_18001A779
0x18001a519  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18001a51d  mov     edx, 1; unsigned int
0x18001a522  lea     rcx, [rbp+var_20]; this
0x18001a526  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001a52b  mov     r9d, 12B0h
0x18001a531  mov     ecx, eax
0x18001a533  mov     r14d, eax
0x18001a536  call    ElValidateWin32_8
0x18001a53b  test    eax, eax
0x18001a53d  jz      short loc_18001A55B
0x18001a53f  test    r14d, r14d
0x18001a542  jg      short loc_18001A54C
0x18001a544  mov     ebx, r14d
0x18001a547  jmp     loc_18001A735
0x18001a54c  movzx   ebx, r14w
0x18001a550  or      ebx, 80070000h
0x18001a556  jmp     loc_18001A735
0x18001a55b  lea     r8, [rbp+netname]; unsigned __int16 **
0x18001a55f  mov     edx, 2; unsigned int
0x18001a564  lea     rcx, [rbp+var_20]; this
0x18001a568  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001a56d  mov     r9d, 12B3h
0x18001a573  mov     ecx, eax
0x18001a575  mov     r14d, eax
0x18001a578  call    ElValidateWin32_8
0x18001a57d  test    eax, eax
0x18001a57f  jnz     short loc_18001A53F
0x18001a581  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x18001a585  lea     ecx, [rax+7]; NameType
0x18001a588  call    ?GetHostName@@YAKW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; GetHostName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18001a58d  mov     r9d, 12BBh
0x18001a593  mov     ecx, eax
0x18001a595  mov     r14d, eax
0x18001a598  call    ElValidateWin32_8
0x18001a59d  test    eax, eax
0x18001a59f  jz      short loc_18001A5BE
0x18001a5a1  test    r14d, r14d
0x18001a5a4  jg      short loc_18001A5AB
0x18001a5a6  mov     ebx, r14d
0x18001a5a9  jmp     short loc_18001A5B5
0x18001a5ab  movzx   ebx, r14w
0x18001a5af  or      ebx, 80070000h
0x18001a5b5  mov     r14, [rbp+lpMem]
0x18001a5b9  jmp     loc_18001A728
0x18001a5be  mov     r14, [rbp+lpMem]
0x18001a5c2  lea     r8, [rbp+arg_0]; int *
0x18001a5c6  mov     rcx, [rbp+var_40]; unsigned __int16 *
0x18001a5ca  mov     rdx, r14; pNodeName
0x18001a5cd  call    ?AreHostsSame@CNetworkAddress@@SAKPEBG0PEAH@Z; CNetworkAddress::AreHostsSame(ushort const *,ushort const *,int *)
0x18001a5d2  mov     r9d, 12C5h
0x18001a5d8  mov     ecx, eax
0x18001a5da  mov     r15d, eax
0x18001a5dd  call    ElValidateWin32_8
0x18001a5e2  test    eax, eax
0x18001a5e4  jz      short loc_18001A602
0x18001a5e6  test    r15d, r15d
0x18001a5e9  jg      short loc_18001A5F3
0x18001a5eb  mov     ebx, r15d
0x18001a5ee  jmp     loc_18001A728
0x18001a5f3  movzx   ebx, r15w
0x18001a5f7  or      ebx, 80070000h
0x18001a5fd  jmp     loc_18001A728
0x18001a602  xor     r15d, r15d
0x18001a605  cmp     [rbp+arg_0], r15d
0x18001a609  jnz     short loc_18001A614
0x18001a60b  lea     ebx, [r15+1]
0x18001a60f  jmp     loc_18001A728
0x18001a614  mov     rdx, [rbp+netname]
0x18001a618  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a61c  mov     rcx, rax
0x18001a61f  inc     rcx
0x18001a622  cmp     [rdx+rcx*2], r15w
0x18001a627  jnz     short loc_18001A61F
0x18001a629  mov     rdx, [rbp+var_40]
0x18001a62d  inc     rax
0x18001a630  cmp     [rdx+rax*2], r15w
0x18001a635  jnz     short loc_18001A62D
0x18001a637  add     rax, 3
0x18001a63b  lea     rdx, [rbp+var_50]; unsigned __int16 **
0x18001a63f  add     rcx, rax
0x18001a642  lea     r15, [r12+rcx*2]
0x18001a646  mov     rcx, [rbp+netname]; netname
0x18001a64a  call    ?GetNetSharePath@@YAKPEBGPEAPEAG@Z; GetNetSharePath(ushort const *,ushort * *)
0x18001a64f  mov     r9d, 12DFh
0x18001a655  mov     ecx, eax
0x18001a657  mov     edi, eax
0x18001a659  call    ElValidateWin32_8
0x18001a65e  test    eax, eax
0x18001a660  jz      short loc_18001A67C
0x18001a662  test    edi, edi
0x18001a664  jg      short loc_18001A66A
0x18001a666  mov     ebx, edi
0x18001a668  jmp     short loc_18001A673
0x18001a66a  movzx   ebx, di
0x18001a66d  or      ebx, 80070000h
0x18001a673  mov     rdi, [rbp+var_50]
0x18001a677  jmp     loc_18001A728
0x18001a67c  mov     rax, [rbp+netname]
0x18001a680  lea     r8, aSS_1; "\\\\%s\\%s"
0x18001a687  mov     r9, [rbp+var_40]
0x18001a68b  lea     rcx, [rbp+var_28]; unsigned __int16 **
0x18001a68f  xor     edx, edx; unsigned __int64
0x18001a691  mov     [rsp+80h+var_60], rax
0x18001a696  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001a69b  mov     r9d, 12EAh
0x18001a6a1  mov     ecx, eax
0x18001a6a3  mov     edi, eax
0x18001a6a5  call    ElValidateWin32_8
0x18001a6aa  test    eax, eax
0x18001a6ac  jnz     short loc_18001A662
0x18001a6ae  mov     rdi, [rbp+var_50]
0x18001a6b2  lea     r8, [rbp+var_48]
0x18001a6b6  mov     rcx, rdi
0x18001a6b9  mov     rdx, r15
0x18001a6bc  call    ConcatenatePaths
0x18001a6c1  mov     r9d, 12F3h
0x18001a6c7  mov     ecx, eax
0x18001a6c9  mov     esi, eax
0x18001a6cb  call    ElValidateWin32_8
0x18001a6d0  xor     r15d, r15d
0x18001a6d3  test    eax, eax
0x18001a6d5  jz      short loc_18001A6EE
0x18001a6d7  test    esi, esi
0x18001a6d9  jg      short loc_18001A6DF
0x18001a6db  mov     ebx, esi
0x18001a6dd  jmp     short loc_18001A6E8
0x18001a6df  movzx   ebx, si
0x18001a6e2  or      ebx, 80070000h
0x18001a6e8  mov     rsi, [rbp+var_48]
0x18001a6ec  jmp     short loc_18001A728
0x18001a6ee  mov     rax, [rbp+arg_8]
0x18001a6f2  test    rax, rax
0x18001a6f5  jz      short loc_18001A6FD
0x18001a6f7  mov     [rax], rdi
0x18001a6fa  mov     rdi, r15
0x18001a6fd  test    r13, r13
0x18001a700  jz      short loc_18001A70E
0x18001a702  mov     rax, [rbp+var_28]
0x18001a706  mov     [r13+0], rax
0x18001a70a  mov     [rbp+var_28], r15
0x18001a70e  mov     rcx, [rbp+arg_18]
0x18001a712  test    rcx, rcx
0x18001a715  jz      short loc_18001A6E8
0x18001a717  mov     rax, [rbp+var_48]
0x18001a71b  mov     rsi, r15
0x18001a71e  mov     [rcx], rax
0x18001a721  jmp     short loc_18001A728
0x18001a723  mov     ebx, 80070057h
0x18001a728  test    r14, r14
0x18001a72b  jz      short loc_18001A735
0x18001a72d  mov     rcx, r14; lpMem
0x18001a730  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a735  mov     rcx, [rbp+var_40]; lpMem
0x18001a739  test    rcx, rcx
0x18001a73c  jz      short loc_18001A743
0x18001a73e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a743  mov     rcx, [rbp+netname]; lpMem
0x18001a747  test    rcx, rcx
0x18001a74a  jz      short loc_18001A751
0x18001a74c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a751  test    rdi, rdi
0x18001a754  jz      short loc_18001A75E
0x18001a756  mov     rcx, rdi; lpMem
0x18001a759  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a75e  mov     rcx, [rbp+var_28]; lpMem
0x18001a762  test    rcx, rcx
0x18001a765  jz      short loc_18001A76C
0x18001a767  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a76c  test    rsi, rsi
0x18001a76f  jz      short loc_18001A779
0x18001a771  mov     rcx, rsi; lpMem
0x18001a774  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a779  lea     rcx, [rbp+var_20]; this
0x18001a77d  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001a782  mov     eax, ebx
0x18001a784  mov     rbx, [rsp+80h+arg_10]
0x18001a78c  add     rsp, 80h
0x18001a793  pop     r15
0x18001a795  pop     r14
0x18001a797  pop     r13
0x18001a799  pop     r12
0x18001a79b  pop     rdi
0x18001a79c  pop     rsi
0x18001a79d  pop     rbp
0x18001a79e  retn
```
