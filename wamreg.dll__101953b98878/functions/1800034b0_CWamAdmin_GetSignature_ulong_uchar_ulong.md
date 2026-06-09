# CWamAdmin::GetSignature(ulong,uchar *,ulong *)

- ea: `0x1800034b0`
- end: `0x180003686`
- name: `?GetSignature@CWamAdmin@@UEAAJKPEAEPEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x1800034b0`
- `0x180003cdc`
- `0x180004864`
- `0x180005584`
- `0x180005cfc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800035d8`
- `iisutil!PuDbgPrint` at `0x180003658`
- `iisutil!PuDbgPrint` at `0x1800035d8`
- `iisutil!PuDbgPrint` at `0x180003658`

## string_xrefs

- `0x180003596`: `Get Signature on path %S, signature = %08x\n`
- `0x1800035b7`: `Failed to get signature on path %S, hr = %08x\n`
- `0x180003646`: `GetSignature: GetPropPaths failed hr = %08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::GetSignature(CWamAdmin *this, unsigned int a2, unsigned __int8 *a3, unsigned int *a4)
{
  WamRegMetabaseConfig *v7; // rcx
  int v8; // eax
  WamRegGlobal *v9; // rcx
  int v10; // ebx
  unsigned __int16 *v11; // rsi
  unsigned int v12; // edi
  void *v13; // r14
  int SignatureOnPath; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-68h]
  unsigned int v19; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-50h] BYREF
  void *Block; // [rsp+50h] [rbp-48h] BYREF

  v20 = 0;
  WamRegGlobal::AcquireAdmWriteLock(this);
  v8 = WamRegMetabaseConfig::MDGetPropPaths(v7, L"/LM/W3SVC", 0x838u, &v20, &v19);
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        920,
        "CWamAdmin::GetSignature",
        "GetSignature: GetPropPaths failed hr = %08x\n",
        v8);
  }
  else
  {
    v11 = v20;
    v12 = 0;
    Block = 0;
    if ( *v20 )
    {
      do
      {
        if ( v10 < 0 )
          break;
        v12 += 4;
        if ( v12 <= a2 )
        {
          v10 = WamRegGlobal::ConstructFullPath(v9, L"/LM/W3SVC", 9u, v11, (unsigned __int16 **)&Block);
          if ( v10 >= 0 )
          {
            v19 = 0;
            v13 = Block;
            SignatureOnPath = WamRegMetabaseConfig::GetSignatureOnPath(v9, (const unsigned __int16 *)Block, &v19);
            v10 = SignatureOnPath;
            if ( SignatureOnPath < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                LODWORD(v18) = SignatureOnPath;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                  902,
                  "CWamAdmin::GetSignature",
                  "Failed to get signature on path %S, hr = %08x\n",
                  v11,
                  v18);
              }
            }
            else
            {
              v15 = v19;
              *(_DWORD *)a3 = v19;
              a3 += 4;
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                LODWORD(v18) = v15;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                  896,
                  "CWamAdmin::GetSignature",
                  "Get Signature on path %S, signature = %08x\n",
                  v13,
                  v18);
              }
            }
            operator delete(v13);
            Block = 0;
          }
        }
        v16 = -1;
        do
          ++v16;
        while ( v11[v16] );
        v11 += v16 + 1;
      }
      while ( *v11 );
      if ( v12 > a2 )
      {
        *a4 = v12;
        v10 = -2147024774;
      }
    }
    if ( v10 >= 0 )
      *a4 = v12;
  }
  if ( v20 )
    operator delete(v20);
  WamRegGlobal::ReleaseAdmWriteLock(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800034b0  push    rbx
0x1800034b2  push    rsi
0x1800034b3  push    rdi
0x1800034b4  push    r12
0x1800034b6  push    r13
0x1800034b8  push    r14
0x1800034ba  push    r15
0x1800034bc  sub     rsp, 60h
0x1800034c0  xor     r14d, r14d
0x1800034c3  mov     r15, r9
0x1800034c6  mov     [rsp+98h+var_50], r14
0x1800034cb  mov     r13, r8
0x1800034ce  mov     r12d, edx
0x1800034d1  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x1800034d6  lea     rax, [rsp+98h+var_58]
0x1800034db  mov     r8d, 838h; unsigned int
0x1800034e1  lea     r9, [rsp+98h+var_50]; unsigned __int16 **
0x1800034e6  mov     [rsp+98h+var_78], rax; unsigned int *
0x1800034eb  lea     rdx, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x1800034f2  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x1800034f7  mov     ebx, eax
0x1800034f9  test    eax, eax
0x1800034fb  js      loc_180003624
0x180003501  mov     rsi, [rsp+98h+var_50]
0x180003506  mov     edi, r14d
0x180003509  mov     [rsp+98h+Block], r14
0x18000350e  cmp     [rsi], r14w
0x180003512  jz      loc_18000361B
0x180003518  test    ebx, ebx
0x18000351a  js      loc_18000360E
0x180003520  add     edi, 4
0x180003523  cmp     edi, r12d
0x180003526  ja      loc_1800035EE
0x18000352c  lea     rax, [rsp+98h+Block]
0x180003531  mov     r9, rsi; unsigned __int16 *
0x180003534  mov     r8d, 9; unsigned int
0x18000353a  mov     [rsp+98h+var_78], rax; unsigned __int16 **
0x18000353f  lea     rdx, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x180003546  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x18000354b  mov     ebx, eax
0x18000354d  test    eax, eax
0x18000354f  js      loc_1800035EE
0x180003555  mov     [rsp+98h+var_58], r14d
0x18000355a  lea     r8, [rsp+98h+var_58]; unsigned int *
0x18000355f  mov     r14, [rsp+98h+Block]
0x180003564  mov     rdx, r14; unsigned __int16 *
0x180003567  call    ?GetSignatureOnPath@WamRegMetabaseConfig@@QEAAJPEBGPEAK@Z; WamRegMetabaseConfig::GetSignatureOnPath(ushort const *,ulong *)
0x18000356c  mov     ebx, eax
0x18000356e  test    eax, eax
0x180003570  js      short loc_18000359F
0x180003572  mov     eax, [rsp+98h+var_58]
0x180003576  mov     [r13+0], eax
0x18000357a  add     r13, 4
0x18000357e  test    byte ptr cs:g_dwDebugFlags, 3
0x180003585  jz      short loc_1800035DE
0x180003587  mov     [rsp+98h+var_68], eax
0x18000358b  mov     r8d, 380h
0x180003591  mov     [rsp+98h+var_70], r14
0x180003596  lea     rax, aGetSignatureOn; "Get Signature on path %S, signature = %"...
0x18000359d  jmp     short loc_1800035BE
0x18000359f  test    byte ptr cs:g_dwDebugFlags, 3
0x1800035a6  jz      short loc_1800035DE
0x1800035a8  mov     [rsp+98h+var_68], eax
0x1800035ac  mov     r8d, 386h
0x1800035b2  mov     [rsp+98h+var_70], rsi
0x1800035b7  lea     rax, aFailedToGetSig; "Failed to get signature on path %S, hr "...
0x1800035be  mov     rcx, cs:g_pDebug
0x1800035c5  lea     r9, aCwamadminGetsi; "CWamAdmin::GetSignature"
0x1800035cc  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800035d3  mov     [rsp+98h+var_78], rax
0x1800035d8  call    cs:__imp_PuDbgPrint
0x1800035de  mov     rcx, r14; Block
0x1800035e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800035e6  xor     r14d, r14d
0x1800035e9  mov     [rsp+98h+Block], r14
0x1800035ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800035f2  inc     rax
0x1800035f5  cmp     [rsi+rax*2], r14w
0x1800035fa  jnz     short loc_1800035F2
0x1800035fc  lea     rsi, [rsi+rax*2]
0x180003600  add     rsi, 2
0x180003604  cmp     [rsi], r14w
0x180003608  jnz     loc_180003518
0x18000360e  cmp     edi, r12d
0x180003611  jbe     short loc_18000361B
0x180003613  mov     [r15], edi
0x180003616  mov     ebx, 8007007Ah
0x18000361b  test    ebx, ebx
0x18000361d  js      short loc_18000365E
0x18000361f  mov     [r15], edi
0x180003622  jmp     short loc_18000365E
0x180003624  test    byte ptr cs:g_dwDebugFlags, 3
0x18000362b  jz      short loc_18000365E
0x18000362d  mov     rcx, cs:g_pDebug
0x180003634  lea     r9, aCwamadminGetsi; "CWamAdmin::GetSignature"
0x18000363b  mov     dword ptr [rsp+98h+var_70], eax
0x18000363f  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180003646  lea     rax, aGetsignatureGe; "GetSignature: GetPropPaths failed hr = "...
0x18000364d  mov     r8d, 398h
0x180003653  mov     [rsp+98h+var_78], rax
0x180003658  call    cs:__imp_PuDbgPrint
0x18000365e  cmp     [rsp+98h+var_50], r14
0x180003663  jz      short loc_18000366F
0x180003665  mov     rcx, [rsp+98h+var_50]; Block
0x18000366a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000366f  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x180003674  mov     eax, ebx
0x180003676  add     rsp, 60h
0x18000367a  pop     r15
0x18000367c  pop     r14
0x18000367e  pop     r13
0x180003680  pop     r12
0x180003682  pop     rdi
0x180003683  pop     rsi
0x180003684  pop     rbx
0x180003685  retn
```
